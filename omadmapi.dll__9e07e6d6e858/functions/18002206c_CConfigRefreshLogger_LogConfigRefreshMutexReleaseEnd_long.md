# CConfigRefreshLogger::LogConfigRefreshMutexReleaseEnd(long)

- ea: `0x18002206c`
- end: `0x180022158`
- name: `?LogConfigRefreshMutexReleaseEnd@CConfigRefreshLogger@@QEAAXJ@Z`
- size: `236`
- prototype: `void __fastcall(CConfigRefreshLogger *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800118a0`

## callees

- `0x1800013dc`
- `0x1800031b0`
- `0x180014514`
- `0x18002206c`

## pseudocode

```c
void __fastcall CConfigRefreshLogger::LogConfigRefreshMutexReleaseEnd(
        CConfigRefreshLogger *this,
        int a2,
        __int64 a3,
        int a4)
{
  int v5; // [rsp+40h] [rbp-40h] BYREF
  char *v6; // [rsp+48h] [rbp-38h] BYREF
  __int64 v7; // [rsp+50h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+58h] [rbp-28h] BYREF
  int *v9; // [rsp+68h] [rbp-18h]
  __int64 v10; // [rsp+70h] [rbp-10h]

  if ( (unsigned int)dword_180032098 > 5 )
  {
    a3 = 0x400000000000LL;
    if ( (qword_1800320A8 & 0x400000000000LL) != 0 && (qword_1800320B0 & 0x400000000000LL) == qword_1800320B0 )
    {
      v5 = a2;
      v6 = (char *)this + 16;
      v7 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&dword_18002B4C4,
        0,
        a4,
        (__int64)&v7,
        (__int64)&v5,
        (__int64)&v6);
    }
  }
  if ( a2 < 0 && (byte_180032C41 & 2) != 0 )
  {
    v5 = a2;
    v9 = &v5;
    v10 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context,
      (const EVENT_DESCRIPTOR *)ConfigRefreshMutexReleaseFailure,
      a3,
      2u,
      &v8);
  }
}

```

## disassembly

```asm
0x18002206c  mov     r11, rsp
0x18002206f  mov     [r11+8], rbx
0x180022073  push    rbp
0x180022074  mov     rbp, rsp
0x180022077  sub     rsp, 80h
0x18002207e  mov     rax, cs:__security_cookie
0x180022085  xor     rax, rsp
0x180022088  mov     [rbp+var_8], rax
0x18002208c  mov     eax, cs:dword_180032098
0x180022092  mov     ebx, edx
0x180022094  cmp     eax, 5
0x180022097  jbe     short loc_1800220F8
0x180022099  mov     rdx, cs:qword_1800320B0
0x1800220a0  mov     r8, 400000000000h
0x1800220aa  mov     rax, cs:qword_1800320A8
0x1800220b1  test    r8, rax
0x1800220b4  jz      short loc_1800220F8
0x1800220b6  mov     rax, rdx
0x1800220b9  and     rax, r8
0x1800220bc  cmp     rax, rdx
0x1800220bf  jnz     short loc_1800220F8
0x1800220c1  lea     rax, [rcx+10h]
0x1800220c5  mov     [rbp+var_40], ebx
0x1800220c8  mov     [rbp+var_38], rax
0x1800220cc  lea     rdx, dword_18002B4C4
0x1800220d3  lea     rax, [rbp+var_38]
0x1800220d7  mov     [rbp+var_30], 2000000h
0x1800220df  mov     [r11-58h], rax
0x1800220e3  lea     rax, [rbp+var_40]
0x1800220e7  mov     [r11-60h], rax
0x1800220eb  lea     rax, [rbp+var_30]
0x1800220ef  mov     [r11-68h], rax
0x1800220f3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800220f8  test    ebx, ebx
0x1800220fa  jns     short loc_18002213A
0x1800220fc  mov     r9d, 2
0x180022102  test    cs:byte_180032C41, r9b
0x180022109  jz      short loc_18002213A
0x18002210b  lea     rax, [rbp+var_40]
0x18002210f  mov     [rbp+var_40], ebx
0x180022112  mov     [rbp+var_18], rax
0x180022116  lea     rdx, ConfigRefreshMutexReleaseFailure
0x18002211d  lea     rax, [rbp+var_28]
0x180022121  mov     [rbp+var_10], 4
0x180022129  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180022130  mov     [rsp+80h+var_60], rax
0x180022135  call    McGenEventWrite_EventWriteTransfer
0x18002213a  mov     rcx, [rbp+var_8]
0x18002213e  xor     rcx, rsp; StackCookie
0x180022141  call    __security_check_cookie
0x180022146  mov     rbx, [rsp+80h+arg_0]
0x18002214e  add     rsp, 80h
0x180022155  pop     rbp
0x180022156  retn
```
