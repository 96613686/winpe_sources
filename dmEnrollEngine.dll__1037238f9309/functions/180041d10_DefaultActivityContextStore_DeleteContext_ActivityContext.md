# DefaultActivityContextStore::DeleteContext(ActivityContext &)

- ea: `0x180041d10`
- end: `0x180041e6b`
- name: `?DeleteContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067a0`
- `0x180007040`
- `0x180007120`
- `0x18000d560`
- `0x18002e1a0`
- `0x180041d10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180041e38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180041e38`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041d58`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041d58`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::DeleteContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  int v2; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  unsigned __int64 v5[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v6[40]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v8[39]; // [rsp+92h] [rbp-6Eh] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-20h] BYREF

  SubKey[0] = 0;
  v6[0] = 0;
  sz = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v5[0] = 0;
  v2 = StringCchLengthW(&sz, 0x27u, v5);
  if ( v2 < 0 )
    return (unsigned int)v2;
  if ( v5[0] - 2 > 0x24 )
    return (unsigned int)-2147418113;
  v2 = StringCchCopyW(v6, 0x27u, v8);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v2 = StringCchLengthW(v6, 0x27u, v5);
  if ( v2 < 0 )
    return (unsigned int)v2;
  if ( v5[0] - 2 > 0x24 )
    return (unsigned int)-2147418113;
  *((_WORD *)&v5[1] + v5[0] + 3) = 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v2 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v6);
  if ( v2 >= 0 )
    RegDeleteTreeW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), SubKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180041d10  mov     [rsp-8+arg_0], rbx
0x180041d15  mov     [rsp-8+arg_10], rdi
0x180041d1a  push    rbp
0x180041d1b  lea     rbp, [rsp-200h]
0x180041d23  sub     rsp, 300h
0x180041d2a  mov     rax, cs:__security_cookie
0x180041d31  xor     rax, rsp
0x180041d34  mov     [rbp+200h+var_10], rax
0x180041d3b  xor     eax, eax
0x180041d3d  lea     rcx, [rdx+8]; rguid
0x180041d41  lea     rdx, [rbp+200h+sz]; lpsz
0x180041d45  mov     [rbp+200h+SubKey], ax
0x180041d49  mov     [rsp+300h+var_2C0], ax
0x180041d4e  mov     [rbp+200h+sz], ax
0x180041d52  lea     edi, [rax+27h]
0x180041d55  mov     r8d, edi; cchMax
0x180041d58  call    cs:__imp_StringFromGUID2
0x180041d5e  cmp     eax, edi
0x180041d60  jnz     loc_180041E40
0x180041d66  lea     r8, [rsp+300h+var_2D0]; unsigned __int64 *
0x180041d6b  mov     [rsp+300h+var_2D0], 0
0x180041d74  mov     edx, edi; unsigned __int64
0x180041d76  lea     rcx, [rbp+200h+sz]; unsigned __int16 *
0x180041d7a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180041d7f  mov     ebx, eax
0x180041d81  test    eax, eax
0x180041d83  js      loc_180041E45
0x180041d89  mov     rax, [rsp+300h+var_2D0]
0x180041d8e  add     rax, 0FFFFFFFFFFFFFFFEh
0x180041d92  cmp     rax, 24h ; '$'
0x180041d96  ja      loc_180041E40
0x180041d9c  lea     r8, [rbp+200h+var_26E]; unsigned __int16 *
0x180041da0  mov     edx, edi; unsigned __int64
0x180041da2  lea     rcx, [rsp+300h+var_2C0]; unsigned __int16 *
0x180041da7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041dac  mov     ebx, eax
0x180041dae  test    eax, eax
0x180041db0  js      loc_180041E45
0x180041db6  lea     r8, [rsp+300h+var_2D0]; unsigned __int64 *
0x180041dbb  mov     edx, edi; unsigned __int64
0x180041dbd  lea     rcx, [rsp+300h+var_2C0]; unsigned __int16 *
0x180041dc2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180041dc7  mov     ebx, eax
0x180041dc9  test    eax, eax
0x180041dcb  js      short loc_180041E45
0x180041dcd  mov     rcx, [rsp+300h+var_2D0]
0x180041dd2  lea     rax, [rcx-2]
0x180041dd6  cmp     rax, 24h ; '$'
0x180041dda  ja      short loc_180041E40
0x180041ddc  xor     eax, eax
0x180041dde  mov     [rsp+rcx*2+300h+var_2C2], ax
0x180041de3  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x180041de8  lea     rcx, [rsp+300h+var_2C0]
0x180041ded  mov     r9, rax
0x180041df0  mov     [rsp+300h+var_2D8], rcx
0x180041df5  lea     r8, aSSS; "%s\\%s\\%s"
0x180041dfc  lea     rcx, aContext_0; "Context"
0x180041e03  mov     edx, 104h; unsigned __int64
0x180041e08  mov     [rsp+300h+var_2E0], rcx
0x180041e0d  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x180041e11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041e16  mov     ebx, eax
0x180041e18  test    eax, eax
0x180041e1a  js      short loc_180041E45
0x180041e1c  xor     ecx, ecx
0x180041e1e  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180041e22  mov     eax, 2000h
0x180041e27  cmp     cs:word_1800AFC84, ax
0x180041e2e  setnz   cl
0x180041e31  add     rcx, 0FFFFFFFF80000001h; hKey
0x180041e38  call    cs:__imp_RegDeleteTreeW
0x180041e3e  jmp     short loc_180041E45
0x180041e40  mov     ebx, 8000FFFFh
0x180041e45  mov     eax, ebx
0x180041e47  mov     rcx, [rbp+200h+var_10]
0x180041e4e  xor     rcx, rsp; StackCookie
0x180041e51  call    __security_check_cookie
0x180041e56  lea     r11, [rsp+300h+var_s0]
0x180041e5e  mov     rbx, [r11+10h]
0x180041e62  mov     rdi, [r11+20h]
0x180041e66  mov     rsp, r11
0x180041e69  pop     rbp
0x180041e6a  retn
```
