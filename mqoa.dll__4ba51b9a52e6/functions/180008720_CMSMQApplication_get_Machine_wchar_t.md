# CMSMQApplication::get_Machine(wchar_t * *)

- ea: `0x180008720`
- end: `0x180008853`
- name: `?get_Machine@CMSMQApplication@@UEAAJPEAPEA_W@Z`
- size: `307`
- prototype: `__int64 __fastcall(CMSMQApplication *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003b70`
- `0x18000406c`
- `0x180005430`
- `0x180008720`
- `0x18000cb34`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800087cf`
- `KERNEL32!GetLastError` at `0x1800087cf`
- `KERNEL32!LeaveCriticalSection` at `0x180008769`
- `KERNEL32!LeaveCriticalSection` at `0x180008769`
- `KERNEL32!GetComputerNameW` at `0x1800087c5`
- `KERNEL32!GetComputerNameW` at `0x1800087c5`
- `USER32!CharLowerW` at `0x1800087f6`
- `USER32!CharLowerW` at `0x1800087f6`
- `OLEAUT32!__imp_SysAllocString` at `0x180008801`
- `OLEAUT32!__imp_SysAllocString` at `0x180008801`
- `OLEAUT32!__imp_SysFreeString` at `0x1800087aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800087e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180008821`
- `OLEAUT32!__imp_SysFreeString` at `0x18000882d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800087aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800087e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180008821`
- `OLEAUT32!__imp_SysFreeString` at `0x18000882d`
- `OLEAUT32!__imp_SysStringLen` at `0x180008778`
- `OLEAUT32!__imp_SysStringLen` at `0x180008778`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQApplication::get_Machine(CMSMQApplication *this, wchar_t **a2)
{
  OLECHAR *v4; // rbx
  wchar_t *v5; // rax
  unsigned int ErrorHelper; // edi
  DWORD LastError; // eax
  wchar_t *v9; // rax
  BSTR pbstr; // [rsp+20h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-30h] BYREF

  pbstr = 0;
  CCriticalSection::Lock((CMSMQApplication *)((char *)this + 72));
  ATL::CComBSTR::operator=(&pbstr, (char *)this + 120);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v4 = pbstr;
  if ( SysStringLen(pbstr) )
  {
    v5 = ATL::CComBSTR::Copy((ATL::CComBSTR *)&pbstr);
    *a2 = v5;
    if ( !v5 )
      goto LABEL_3;
  }
  else
  {
    LODWORD(pbstr) = 16;
    if ( !GetComputerNameW(Buffer, (LPDWORD)&pbstr) )
    {
      LastError = GetLastError();
      ErrorHelper = CreateErrorHelper(LastError, 9);
      SysFreeString(v4);
      return ErrorHelper;
    }
    CharLowerW(Buffer);
    v9 = SysAllocString(Buffer);
    *a2 = v9;
    if ( !v9 )
    {
LABEL_3:
      ErrorHelper = CreateErrorHelper(2147942414LL, 9);
      SysFreeString(v4);
      return ErrorHelper;
    }
  }
  SysFreeString(v4);
  return 0;
}

```

## disassembly

```asm
0x180008720  mov     [rsp+arg_10], rbx
0x180008725  mov     [rsp+arg_18], rsi
0x18000872a  push    rdi
0x18000872b  sub     rsp, 50h
0x18000872f  mov     rax, cs:__security_cookie
0x180008736  xor     rax, rsp
0x180008739  mov     [rsp+58h+var_10], rax
0x18000873e  mov     rsi, rdx
0x180008741  mov     rdi, rcx
0x180008744  mov     [rsp+58h+pbstr], 0
0x18000874d  add     rcx, 48h ; 'H'; this
0x180008751  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180008756  lea     rdx, [rdi+78h]
0x18000875a  lea     rcx, [rsp+58h+pbstr]
0x18000875f  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x180008764  nop
0x180008765  lea     rcx, [rdi+48h]; lpCriticalSection
0x180008769  call    cs:__imp_LeaveCriticalSection
0x18000876f  nop
0x180008770  mov     rbx, [rsp+58h+pbstr]
0x180008775  mov     rcx, rbx; pbstr
0x180008778  call    cs:__imp_SysStringLen
0x18000877e  test    eax, eax
0x180008780  jz      short loc_1800087B3
0x180008782  lea     rcx, [rsp+58h+pbstr]; this
0x180008787  call    ?Copy@CComBSTR@ATL@@QEBAPEA_WXZ; ATL::CComBSTR::Copy(void)
0x18000878c  mov     [rsi], rax
0x18000878f  test    rax, rax
0x180008792  jnz     loc_18000882A
0x180008798  lea     edx, [rax+9]
0x18000879b  mov     ecx, 8007000Eh
0x1800087a0  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800087a5  mov     edi, eax
0x1800087a7  mov     rcx, rbx; bstrString
0x1800087aa  call    cs:__imp_SysFreeString
0x1800087b0  nop
0x1800087b1  jmp     short loc_1800087ED
0x1800087b3  mov     dword ptr [rsp+58h+pbstr], 10h
0x1800087bb  lea     rdx, [rsp+58h+pbstr]; nSize
0x1800087c0  lea     rcx, [rsp+58h+Buffer]; lpBuffer
0x1800087c5  call    cs:__imp_GetComputerNameW
0x1800087cb  test    eax, eax
0x1800087cd  jnz     short loc_1800087F1
0x1800087cf  call    cs:__imp_GetLastError
0x1800087d5  mov     ecx, eax
0x1800087d7  mov     edx, 9
0x1800087dc  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800087e1  mov     edi, eax
0x1800087e3  mov     rcx, rbx; bstrString
0x1800087e6  call    cs:__imp_SysFreeString
0x1800087ec  nop
0x1800087ed  mov     eax, edi
0x1800087ef  jmp     short loc_180008836
0x1800087f1  lea     rcx, [rsp+58h+Buffer]; lpsz
0x1800087f6  call    cs:__imp_CharLowerW
0x1800087fc  lea     rcx, [rsp+58h+Buffer]; psz
0x180008801  call    cs:__imp_SysAllocString
0x180008807  mov     [rsi], rax
0x18000880a  test    rax, rax
0x18000880d  jnz     short loc_18000882A
0x18000880f  lea     edx, [rax+9]
0x180008812  mov     ecx, 8007000Eh
0x180008817  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18000881c  mov     edi, eax
0x18000881e  mov     rcx, rbx; bstrString
0x180008821  call    cs:__imp_SysFreeString
0x180008827  nop
0x180008828  jmp     short loc_1800087ED
0x18000882a  mov     rcx, rbx; bstrString
0x18000882d  call    cs:__imp_SysFreeString
0x180008833  nop
0x180008834  xor     eax, eax
0x180008836  mov     rcx, [rsp+58h+var_10]
0x18000883b  xor     rcx, rsp; StackCookie
0x18000883e  call    __security_check_cookie
0x180008843  mov     rbx, [rsp+58h+arg_10]
0x180008848  mov     rsi, [rsp+58h+arg_18]
0x18000884d  add     rsp, 50h
0x180008851  pop     rdi
0x180008852  retn
```
