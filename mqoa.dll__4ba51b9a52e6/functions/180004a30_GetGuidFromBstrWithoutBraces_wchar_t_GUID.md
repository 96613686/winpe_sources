# GetGuidFromBstrWithoutBraces(wchar_t *,_GUID *)

- ea: `0x180004a30`
- end: `0x180004ab5`
- name: `?GetGuidFromBstrWithoutBraces@@YAJPEA_WPEAU_GUID@@@Z`
- size: `133`
- prototype: `int(wchar_t *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005980`

## callees

- `0x180004a30`
- `0x1800075ec`
- `0x1800273b0`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180004a8f`
- `ole32!CLSIDFromString` at `0x180004a8f`

## pseudocode

```c
HRESULT __fastcall GetGuidFromBstrWithoutBraces(wchar_t *a1, struct _GUID *a2)
{
  int v3; // eax
  HRESULT result; // eax
  OLECHAR sz[40]; // [rsp+20h] [rbp-68h] BYREF

  if ( a1 )
    v3 = StringCchPrintfW(sz, 0x27u, L"{%s}", a1);
  else
    v3 = StringCchPrintfW(sz, 0x27u, L"{}");
  if ( v3 < 0 )
    return -1072824296;
  result = CLSIDFromString(sz, a2);
  if ( result < 0 )
    return -1072824296;
  return result;
}

```

## disassembly

```asm
0x180004a30  push    rbx
0x180004a32  sub     rsp, 80h
0x180004a39  mov     rax, cs:__security_cookie
0x180004a40  xor     rax, rsp
0x180004a43  mov     [rsp+88h+var_18], rax
0x180004a48  mov     rbx, rdx
0x180004a4b  mov     edx, 27h ; '''; unsigned __int64
0x180004a50  test    rcx, rcx
0x180004a53  jz      short loc_180004A6B
0x180004a55  mov     r9, rcx
0x180004a58  lea     r8, aS_0; "{%s}"
0x180004a5f  lea     rcx, [rsp+88h+sz]; wchar_t *
0x180004a64  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004a69  jmp     short loc_180004A7C
0x180004a6b  lea     r8, asc_18002F194; "{}"
0x180004a72  lea     rcx, [rsp+88h+sz]; wchar_t *
0x180004a77  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004a7c  test    eax, eax
0x180004a7e  jns     short loc_180004A87
0x180004a80  mov     eax, 0C00E0018h
0x180004a85  jmp     short loc_180004A9F
0x180004a87  mov     rdx, rbx; pclsid
0x180004a8a  lea     rcx, [rsp+88h+sz]; lpsz
0x180004a8f  call    cs:__imp_CLSIDFromString
0x180004a95  test    eax, eax
0x180004a97  mov     ecx, 0C00E0018h
0x180004a9c  cmovs   eax, ecx
0x180004a9f  mov     rcx, [rsp+88h+var_18]
0x180004aa4  xor     rcx, rsp; StackCookie
0x180004aa7  call    __security_check_cookie
0x180004aac  add     rsp, 80h
0x180004ab3  pop     rbx
0x180004ab4  retn
```
