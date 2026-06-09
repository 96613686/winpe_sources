# WriteOptsToRegistry

- ea: `0x180010bec`
- end: `0x180010d86`
- name: `WriteOptsToRegistry`
- size: `410`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18000c738`

## callees

- `0x1800016c8`
- `0x18000da44`
- `0x180010364`
- `0x180010574`
- `0x1800106fc`
- `0x180010970`
- `0x180010bec`
- `0x180010d8c`
- `0x180011374`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180010ced`
- `msvcrt!wcscat_s` at `0x180010ced`
- `msvcrt!wcscpy_s` at `0x180010c5e`
- `msvcrt!wcscpy_s` at `0x180010c5e`

## pseudocode

```c
LSTATUS __fastcall WriteOptsToRegistry(HKEY hKey, __int64 a2)
{
  __int64 v2; // r8
  const wchar_t *v5; // r8
  unsigned __int64 v6; // rcx
  wchar_t *v7; // rdx
  __int64 v8; // rax
  wchar_t Destination[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Source[264]; // [rsp+240h] [rbp+140h] BYREF

  v2 = *(_QWORD *)(a2 + 64);
  Source[259] = 0;
  Destination[259] = 0;
  DaBuildRegistryPath(0, L"Persistent\\", v2, Source);
  v5 = *(const wchar_t **)(*(_QWORD *)(a2 + 16) + 8LL);
  if ( v5 )
  {
    wcscpy_s(Destination, 0x104u, v5);
    v6 = -1;
    v7 = Destination;
    v8 = -1;
    do
      ++v8;
    while ( Destination[v8] );
    if ( v8 )
    {
      if ( Destination[v8 - 1] == 92 || Destination[v8 - 1] == 58 )
      {
        v7 = (wchar_t *)(2 * v8 - 2);
        if ( (unsigned __int64)v7 >= 0x208 )
          goto LABEL_15;
        *(wchar_t *)((char *)Destination + (_QWORD)v7) = 0;
      }
      do
        ++v6;
      while ( Destination[v6] );
      if ( Destination[v6 - 1] != 58 )
        goto LABEL_13;
      v6 = 2 * v6 - 2;
      if ( v6 < 0x208 )
      {
        *(wchar_t *)((char *)Destination + v6) = 0;
LABEL_13:
        wcscat_s(Source, 0x104u, Destination);
        goto LABEL_14;
      }
LABEL_15:
      _report_rangecheckfailure(v6, v7, 520);
    }
  }
LABEL_14:
  WriteLoginOpts(hKey, Source, *(_QWORD *)(a2 + 8));
  WriteMountOpts(hKey, Source, *(_QWORD *)a2);
  WriteFileAccessAndCaseOpts(hKey, Source, *(_QWORD *)a2);
  WriteCacheOpts(hKey, Source, (const BYTE *)a2);
  WriteBrowseOpts(*(BYTE **)(a2 + 24));
  return WriteSymLinksOpts(hKey, Source, *(_QWORD *)a2);
}

```

## disassembly

```asm
0x180010bec  mov     [rsp-8+arg_10], rbx
0x180010bf1  push    rbp
0x180010bf2  push    rsi
0x180010bf3  push    rdi
0x180010bf4  lea     rbp, [rsp-360h]
0x180010bfc  sub     rsp, 460h
0x180010c03  mov     rax, cs:__security_cookie
0x180010c0a  xor     rax, rsp
0x180010c0d  mov     [rbp+370h+var_20], rax
0x180010c14  mov     r8, [rdx+40h]
0x180010c18  lea     r9, [rbp+370h+Source]
0x180010c1f  mov     rbx, rdx
0x180010c22  mov     rdi, rcx
0x180010c25  xor     esi, esi
0x180010c27  lea     rdx, aPersistent_0; "Persistent\\"
0x180010c2e  xor     ecx, ecx
0x180010c30  mov     [rbp+370h+var_2A], si
0x180010c37  mov     [rbp+370h+var_23A], si
0x180010c3e  call    DaBuildRegistryPath
0x180010c43  mov     rax, [rbx+10h]
0x180010c47  mov     r8, [rax+8]; Source
0x180010c4b  test    r8, r8
0x180010c4e  jz      loc_180010CF9
0x180010c54  mov     edx, 104h; SizeInWords
0x180010c59  lea     rcx, [rsp+470h+Destination]; Destination
0x180010c5e  call    cs:__imp_wcscpy_s
0x180010c65  nop     dword ptr [rax+rax+00h]
0x180010c6a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010c6e  lea     rdx, [rsp+470h+Destination]
0x180010c73  mov     rax, rcx
0x180010c76  inc     rax
0x180010c79  cmp     [rdx+rax*2], si
0x180010c7d  jnz     short loc_180010C76
0x180010c7f  test    rax, rax
0x180010c82  jz      short loc_180010CF9
0x180010c84  cmp     [rsp+rax*2+470h+var_442], 5Ch ; '\'
0x180010c8a  mov     r8d, 208h
0x180010c90  jz      short loc_180010C9A
0x180010c92  cmp     [rsp+rax*2+470h+var_442], 3Ah ; ':'
0x180010c98  jnz     short loc_180010CB0
0x180010c9a  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180010ca2  cmp     rdx, r8
0x180010ca5  jnb     loc_180010D80
0x180010cab  mov     [rsp+rdx+470h+Destination], si
0x180010cb0  lea     rax, [rsp+470h+Destination]
0x180010cb5  inc     rcx
0x180010cb8  cmp     [rax+rcx*2], si
0x180010cbc  jnz     short loc_180010CB5
0x180010cbe  cmp     [rsp+rcx*2+470h+var_442], 3Ah ; ':'
0x180010cc4  jnz     short loc_180010CDC
0x180010cc6  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x180010cce  cmp     rcx, r8
0x180010cd1  jnb     loc_180010D80
0x180010cd7  mov     [rsp+rcx+470h+Destination], si
0x180010cdc  lea     r8, [rsp+470h+Destination]; Source
0x180010ce1  mov     edx, 104h; SizeInWords
0x180010ce6  lea     rcx, [rbp+370h+Source]; Destination
0x180010ced  call    cs:__imp_wcscat_s
0x180010cf4  nop     dword ptr [rax+rax+00h]
0x180010cf9  mov     r8, [rbx+8]
0x180010cfd  lea     rdx, [rbp+370h+Source]; Source
0x180010d04  mov     rcx, rdi; hKey
0x180010d07  call    WriteLoginOpts
0x180010d0c  mov     r8, [rbx]
0x180010d0f  lea     rdx, [rbp+370h+Source]; Source
0x180010d16  mov     rcx, rdi; hKey
0x180010d19  call    WriteMountOpts
0x180010d1e  mov     r8, [rbx]
0x180010d21  lea     rdx, [rbp+370h+Source]; Source
0x180010d28  mov     rcx, rdi; hKey
0x180010d2b  call    WriteFileAccessAndCaseOpts
0x180010d30  mov     r8, rbx
0x180010d33  lea     rdx, [rbp+370h+Source]; Source
0x180010d3a  mov     rcx, rdi; hKey
0x180010d3d  call    WriteCacheOpts
0x180010d42  mov     rcx, [rbx+18h]; lpData
0x180010d46  call    WriteBrowseOpts
0x180010d4b  mov     r8, [rbx]
0x180010d4e  lea     rdx, [rbp+370h+Source]
0x180010d55  mov     rcx, rdi
0x180010d58  call    WriteSymLinksOpts
0x180010d5d  mov     rcx, [rbp+370h+var_20]
0x180010d64  xor     rcx, rsp; StackCookie
0x180010d67  call    __security_check_cookie
0x180010d6c  mov     rbx, [rsp+470h+arg_10]
0x180010d74  add     rsp, 460h
0x180010d7b  pop     rdi
0x180010d7c  pop     rsi
0x180010d7d  pop     rbp
0x180010d7e  retn
0x180010d80  call    __report_rangecheckfailure
```
