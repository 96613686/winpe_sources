# CEventLogger::WriteHelperClassEvent(tagNDFEventChannel,short,ushort const *,ushort const *)

- ea: `0x180022a80`
- end: `0x180022c44`
- name: `?WriteHelperClassEvent@CEventLogger@@UEAAJW4tagNDFEventChannel@@FPEBG1@Z`
- size: `452`
- prototype: `int __high(enum tagNDFEventChannel, __int16, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006fa0`
- `0x1800215e4`
- `0x180022a80`
- `0x18002c840`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180022af9`
- `msvcrt!wcsnlen` at `0x180022b5c`
- `msvcrt!wcsnlen` at `0x180022af9`
- `msvcrt!wcsnlen` at `0x180022b5c`
- `ADVAPI32!EventWrite` at `0x180022bf0`
- `ADVAPI32!EventWrite` at `0x180022bf0`
- `ADVAPI32!EventEnabled` at `0x180022bd2`
- `ADVAPI32!EventEnabled` at `0x180022bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022b76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022b76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022bfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022bfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c04`

## pseudocode

```c
__int64 __fastcall CEventLogger::WriteHelperClassEvent(
        __int64 a1,
        int a2,
        __int16 a3,
        const wchar_t *a4,
        wchar_t *Source)
{
  wchar_t *v5; // r15
  ULONG v7; // ebx
  int v8; // edx
  const EVENT_DESCRIPTOR *v9; // rdi
  size_t v10; // rax
  unsigned __int64 v11; // r13
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  size_t v15; // rax
  unsigned __int64 v16; // r13
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // r14
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 *v20; // [rsp+30h] [rbp-30h]
  int v21; // [rsp+38h] [rbp-28h]
  int v22; // [rsp+3Ch] [rbp-24h]
  __int16 *v23; // [rsp+40h] [rbp-20h]
  __int64 v24; // [rsp+48h] [rbp-18h]
  __int16 v25; // [rsp+B0h] [rbp+50h] BYREF

  v25 = a3;
  v5 = Source;
  if ( a4 && Source )
  {
    v7 = 0;
    if ( a2 )
    {
      v8 = a2 - 1;
      if ( v8 )
      {
        if ( v8 != 1 )
          return v7;
        v9 = &NDFHelperClassDebugEvtDesc;
      }
      else
      {
        v9 = (const EVENT_DESCRIPTOR *)NDFHelperClassAdminEvtDesc;
      }
    }
    else
    {
      v9 = (const EVENT_DESCRIPTOR *)NDFHelperClassOperationalEvtDesc;
    }
    v10 = wcsnlen(a4, 0x100u);
    v11 = (int)wil::safe_cast_failfast<int,unsigned __int64,0>(v10 + 1);
    v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v11);
    v13 = v12;
    if ( !v12 )
      return 2147942414LL;
    StringCchCopyW(v12, v11, a4);
    v13[v11 - 1] = 0;
    UserData.Ptr = (ULONGLONG)v13;
    UserData.Size = 2 * v11;
    UserData.Reserved = 0;
    v15 = wcsnlen(v5, 0x2000u);
    v16 = (int)wil::safe_cast_failfast<int,unsigned __int64,0>(v15 + 1);
    v17 = (unsigned __int16 *)CoTaskMemAlloc(2 * v16);
    v18 = v17;
    if ( !v17 )
    {
      CoTaskMemFree(v13);
      return 2147942414LL;
    }
    StringCchCopyW(v17, v16, v5);
    v18[v16 - 1] = 0;
    v21 = 2 * v16;
    v23 = &v25;
    v20 = v18;
    v22 = 0;
    v24 = 2;
    if ( EventEnabled(NETDIAG_EVT_GUID_Context, v9) )
      v7 = EventWrite(NETDIAG_EVT_GUID_Context, v9, 3u, &UserData);
    CoTaskMemFree(v13);
    CoTaskMemFree(v18);
    if ( (int)v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return v7;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180022a80  mov     [rsp-38h+arg_0], rbx
0x180022a85  mov     [rsp-38h+arg_10], r8w
0x180022a8b  push    rbp
0x180022a8c  push    rsi
0x180022a8d  push    rdi
0x180022a8e  push    r12
0x180022a90  push    r13
0x180022a92  push    r14
0x180022a94  push    r15
0x180022a96  mov     rbp, rsp
0x180022a99  sub     rsp, 60h
0x180022a9d  mov     rax, cs:__security_cookie
0x180022aa4  xor     rax, rsp
0x180022aa7  mov     [rbp+var_10], rax
0x180022aab  mov     r15, [rbp+Source]
0x180022aaf  mov     r14, r9
0x180022ab2  test    r9, r9
0x180022ab5  jz      loc_180022C1B
0x180022abb  test    r15, r15
0x180022abe  jz      loc_180022C1B
0x180022ac4  xor     ebx, ebx
0x180022ac6  test    edx, edx
0x180022ac8  jz      short loc_180022AEA
0x180022aca  sub     edx, 1
0x180022acd  jz      short loc_180022AE1
0x180022acf  cmp     edx, 1
0x180022ad2  jnz     loc_180022C17
0x180022ad8  lea     rdi, NDFHelperClassDebugEvtDesc
0x180022adf  jmp     short loc_180022AF1
0x180022ae1  lea     rdi, NDFHelperClassAdminEvtDesc
0x180022ae8  jmp     short loc_180022AF1
0x180022aea  lea     rdi, NDFHelperClassOperationalEvtDesc
0x180022af1  mov     edx, 100h; MaxCount
0x180022af6  mov     rcx, r14; Source
0x180022af9  call    cs:__imp_wcsnlen
0x180022aff  lea     rcx, [rax+1]
0x180022b03  call    ??$safe_cast_failfast@H_K$0A@@wil@@YAH_K@Z; wil::safe_cast_failfast<int,unsigned __int64,0>(unsigned __int64)
0x180022b08  movsxd  r13, eax
0x180022b0b  lea     rcx, ds:0[r13*2]; cb
0x180022b13  call    cs:__imp_CoTaskMemAlloc
0x180022b19  mov     rsi, rax
0x180022b1c  test    rax, rax
0x180022b1f  jnz     short loc_180022B2B
0x180022b21  mov     eax, 8007000Eh
0x180022b26  jmp     loc_180022C20
0x180022b2b  mov     r8, r14; unsigned __int16 *
0x180022b2e  mov     rdx, r13; unsigned __int64
0x180022b31  mov     rcx, rsi; unsigned __int16 *
0x180022b34  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022b39  xor     r11d, r11d
0x180022b3c  lea     eax, ds:0[r13*2]
0x180022b44  mov     [rsi+r13*2-2], r11w
0x180022b4a  mov     edx, 2000h; MaxCount
0x180022b4f  mov     rcx, r15; Source
0x180022b52  mov     [rbp+UserData.Ptr], rsi
0x180022b56  mov     [rbp+UserData.Size], eax
0x180022b59  mov     dword ptr [rbp+UserData.0Ch], ebx
0x180022b5c  call    cs:__imp_wcsnlen
0x180022b62  lea     rcx, [rax+1]
0x180022b66  call    ??$safe_cast_failfast@H_K$0A@@wil@@YAH_K@Z; wil::safe_cast_failfast<int,unsigned __int64,0>(unsigned __int64)
0x180022b6b  movsxd  r13, eax
0x180022b6e  lea     rcx, ds:0[r13*2]; cb
0x180022b76  call    cs:__imp_CoTaskMemAlloc
0x180022b7c  mov     r14, rax
0x180022b7f  test    rax, rax
0x180022b82  jnz     short loc_180022B8F
0x180022b84  mov     rcx, rsi; pv
0x180022b87  call    cs:__imp_CoTaskMemFree
0x180022b8d  jmp     short loc_180022B21
0x180022b8f  mov     r8, r15; unsigned __int16 *
0x180022b92  mov     rdx, r13; unsigned __int64
0x180022b95  mov     rcx, r14; unsigned __int16 *
0x180022b98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022b9d  xor     r11d, r11d
0x180022ba0  lea     eax, ds:0[r13*2]
0x180022ba8  mov     [r14+r13*2-2], r11w
0x180022bae  mov     rdx, rdi; EventDescriptor
0x180022bb1  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022bb8  mov     [rbp+var_28], eax
0x180022bbb  lea     rax, [rbp+arg_10]
0x180022bbf  mov     [rbp+var_20], rax
0x180022bc3  mov     [rbp+var_30], r14
0x180022bc7  mov     [rbp+var_24], ebx
0x180022bca  mov     [rbp+var_18], 2
0x180022bd2  call    cs:__imp_EventEnabled
0x180022bd8  test    al, al
0x180022bda  jz      short loc_180022BF8
0x180022bdc  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022be3  lea     r9, [rbp+UserData]; UserData
0x180022be7  mov     r8d, 3; UserDataCount
0x180022bed  mov     rdx, rdi; EventDescriptor
0x180022bf0  call    cs:__imp_EventWrite
0x180022bf6  mov     ebx, eax
0x180022bf8  mov     rcx, rsi; pv
0x180022bfb  call    cs:__imp_CoTaskMemFree
0x180022c01  mov     rcx, r14; pv
0x180022c04  call    cs:__imp_CoTaskMemFree
0x180022c0a  test    ebx, ebx
0x180022c0c  jle     short loc_180022C17
0x180022c0e  movzx   ebx, bx
0x180022c11  or      ebx, 80070000h
0x180022c17  mov     eax, ebx
0x180022c19  jmp     short loc_180022C20
0x180022c1b  mov     eax, 80070057h
0x180022c20  mov     rcx, [rbp+var_10]
0x180022c24  xor     rcx, rsp; StackCookie
0x180022c27  call    __security_check_cookie
0x180022c2c  mov     rbx, [rsp+60h+arg_0]
0x180022c34  add     rsp, 60h
0x180022c38  pop     r15
0x180022c3a  pop     r14
0x180022c3c  pop     r13
0x180022c3e  pop     r12
0x180022c40  pop     rdi
0x180022c41  pop     rsi
0x180022c42  pop     rbp
0x180022c43  retn
```
