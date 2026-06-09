# CMSMQManagement::get_Machine(wchar_t * *)

- ea: `0x1800237c0`
- end: `0x180023903`
- name: `?get_Machine@CMSMQManagement@@UEAAJPEAPEA_W@Z`
- size: `323`
- prototype: `__int64 __fastcall(CMSMQManagement *__hidden this, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012de0`
- `0x180012df0`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x1800237c0`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002387b`
- `KERNEL32!GetLastError` at `0x18002387b`
- `KERNEL32!LeaveCriticalSection` at `0x18002380d`
- `KERNEL32!LeaveCriticalSection` at `0x180023847`
- `KERNEL32!LeaveCriticalSection` at `0x180023853`
- `KERNEL32!LeaveCriticalSection` at `0x180023892`
- `KERNEL32!LeaveCriticalSection` at `0x1800238ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800238dd`
- `KERNEL32!LeaveCriticalSection` at `0x18002380d`
- `KERNEL32!LeaveCriticalSection` at `0x180023847`
- `KERNEL32!LeaveCriticalSection` at `0x180023853`
- `KERNEL32!LeaveCriticalSection` at `0x180023892`
- `KERNEL32!LeaveCriticalSection` at `0x1800238ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800238dd`
- `KERNEL32!GetComputerNameW` at `0x180023871`
- `KERNEL32!GetComputerNameW` at `0x180023871`
- `USER32!CharLowerW` at `0x1800238a3`
- `USER32!CharLowerW` at `0x1800238a3`
- `OLEAUT32!__imp_SysAllocString` at `0x180023827`
- `OLEAUT32!__imp_SysAllocString` at `0x1800238ae`
- `OLEAUT32!__imp_SysAllocString` at `0x180023827`
- `OLEAUT32!__imp_SysAllocString` at `0x1800238ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQManagement::get_Machine(CMSMQManagement *this, wchar_t **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  unsigned int ErrorHelper; // ebx
  const OLECHAR *v7; // rcx
  wchar_t *v8; // rax
  DWORD LastError; // eax
  wchar_t *v10; // rax
  DWORD nSize; // [rsp+20h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-30h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  CCriticalSection::Lock((CMSMQManagement *)((char *)this + 88));
  if ( !*((_DWORD *)this + 33) )
  {
    ErrorHelper = CreateErrorHelper(3222143124LL, 11);
    LeaveCriticalSection(v4);
    return ErrorHelper;
  }
  v7 = (const OLECHAR *)*((_QWORD *)this + 17);
  if ( v7 )
  {
    v8 = SysAllocString(v7);
    *a2 = v8;
    if ( !v8 )
    {
      ErrorHelper = CreateErrorHelper(2147942414LL, 11);
      LeaveCriticalSection(v4);
      return ErrorHelper;
    }
    LeaveCriticalSection(v4);
  }
  else
  {
    nSize = 16;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      LastError = GetLastError();
      ErrorHelper = CreateErrorHelper(LastError, 11);
      LeaveCriticalSection(v4);
      return ErrorHelper;
    }
    CharLowerW(Buffer);
    v10 = SysAllocString(Buffer);
    *a2 = v10;
    if ( !v10 )
    {
      ErrorHelper = CreateErrorHelper(2147942414LL, 11);
      LeaveCriticalSection(v4);
      return ErrorHelper;
    }
    LeaveCriticalSection(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800237c0  mov     [rsp+arg_10], rbx
0x1800237c5  mov     [rsp+arg_18], rsi
0x1800237ca  push    rdi
0x1800237cb  sub     rsp, 50h
0x1800237cf  mov     rax, cs:__security_cookie
0x1800237d6  xor     rax, rsp
0x1800237d9  mov     [rsp+58h+var_10], rax
0x1800237de  mov     rsi, rdx
0x1800237e1  mov     rbx, rcx
0x1800237e4  lea     rdi, [rcx+58h]
0x1800237e8  mov     rcx, rdi; this
0x1800237eb  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800237f0  cmp     dword ptr [rbx+84h], 0
0x1800237f7  jnz     short loc_18002381B
0x1800237f9  mov     edx, 0Bh
0x1800237fe  mov     ecx, 0C00E0094h
0x180023803  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180023808  mov     ebx, eax
0x18002380a  mov     rcx, rdi; lpCriticalSection
0x18002380d  call    cs:__imp_LeaveCriticalSection
0x180023813  nop
0x180023814  mov     eax, ebx
0x180023816  jmp     loc_1800238E6
0x18002381b  mov     rcx, [rbx+88h]; psz
0x180023822  test    rcx, rcx
0x180023825  jz      short loc_18002385F
0x180023827  call    cs:__imp_SysAllocString
0x18002382d  mov     [rsi], rax
0x180023830  test    rax, rax
0x180023833  jnz     short loc_180023850
0x180023835  lea     edx, [rax+0Bh]
0x180023838  mov     ecx, 8007000Eh
0x18002383d  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x180023842  mov     ebx, eax
0x180023844  mov     rcx, rdi; lpCriticalSection
0x180023847  call    cs:__imp_LeaveCriticalSection
0x18002384d  nop
0x18002384e  jmp     short loc_180023814
0x180023850  mov     rcx, rdi; lpCriticalSection
0x180023853  call    cs:__imp_LeaveCriticalSection
0x180023859  nop
0x18002385a  jmp     loc_1800238E4
0x18002385f  mov     [rsp+58h+nSize], 10h
0x180023867  lea     rdx, [rsp+58h+nSize]; nSize
0x18002386c  lea     rcx, [rsp+58h+Buffer]; lpBuffer
0x180023871  call    cs:__imp_GetComputerNameW
0x180023877  test    eax, eax
0x180023879  jnz     short loc_18002389E
0x18002387b  call    cs:__imp_GetLastError
0x180023881  mov     ecx, eax
0x180023883  mov     edx, 0Bh
0x180023888  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18002388d  mov     ebx, eax
0x18002388f  mov     rcx, rdi; lpCriticalSection
0x180023892  call    cs:__imp_LeaveCriticalSection
0x180023898  nop
0x180023899  jmp     loc_180023814
0x18002389e  lea     rcx, [rsp+58h+Buffer]; lpsz
0x1800238a3  call    cs:__imp_CharLowerW
0x1800238a9  lea     rcx, [rsp+58h+Buffer]; psz
0x1800238ae  call    cs:__imp_SysAllocString
0x1800238b4  mov     [rsi], rax
0x1800238b7  test    rax, rax
0x1800238ba  jnz     short loc_1800238DA
0x1800238bc  lea     edx, [rax+0Bh]
0x1800238bf  mov     ecx, 8007000Eh
0x1800238c4  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800238c9  mov     ebx, eax
0x1800238cb  mov     rcx, rdi; lpCriticalSection
0x1800238ce  call    cs:__imp_LeaveCriticalSection
0x1800238d4  nop
0x1800238d5  jmp     loc_180023814
0x1800238da  mov     rcx, rdi; lpCriticalSection
0x1800238dd  call    cs:__imp_LeaveCriticalSection
0x1800238e3  nop
0x1800238e4  xor     eax, eax
0x1800238e6  mov     rcx, [rsp+58h+var_10]
0x1800238eb  xor     rcx, rsp; StackCookie
0x1800238ee  call    __security_check_cookie
0x1800238f3  mov     rbx, [rsp+58h+arg_10]
0x1800238f8  mov     rsi, [rsp+58h+arg_18]
0x1800238fd  add     rsp, 50h
0x180023901  pop     rdi
0x180023902  retn
```
