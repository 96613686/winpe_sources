# Registrar::UnregisterServer(ushort const *,Registrar::ServerKind)

- ea: `0x180040b78`
- end: `0x180040c61`
- name: `?UnregisterServer@Registrar@@QEAAJPEBGW4ServerKind@1@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035aa0`

## callees

- `0x180006194`
- `0x180040a54`
- `0x180040b78`
- `0x180040c68`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040bd0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040bd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040c34`

## pseudocode

```c
__int64 __fastcall Registrar::UnregisterServer(_DWORD *a1)
{
  bool v1; // zf
  const IID *v4; // rcx
  HRESULT v5; // ebx
  HKEY v6; // rcx
  int i; // esi
  HRESULT v8; // eax
  LPOLESTR lpsz; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int16 v10[64]; // [rsp+30h] [rbp-98h] BYREF

  v1 = a1[2] == 0;
  lpsz = 0;
  if ( v1 )
    return 2147500037LL;
  v4 = *(const IID **)(*(_QWORD *)a1 + 8LL);
  if ( !v4 )
    return 2147549183LL;
  v5 = StringFromCLSID(v4, &lpsz);
  if ( v5 >= 0 )
  {
    v5 = StringCchPrintfW(v10, 0x3Fu, L"Software\\Classes\\AppID\\%s", lpsz);
    if ( v5 >= 0 )
    {
      recursiveDeleteKey(v6, v10);
      v5 = 0;
      for ( i = 0; i < a1[2]; ++i )
      {
        v8 = Registrar::UnregisterComClass((const struct Registrar::ClassInfo *)(*(_QWORD *)a1 + 48LL * i));
        if ( v8 < 0 )
          v5 = v8;
      }
    }
  }
  CoTaskMemFree(lpsz);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180040b78  mov     [rsp+arg_8], rbx
0x180040b7d  mov     [rsp+arg_10], rsi
0x180040b82  push    rdi
0x180040b83  sub     rsp, 0C0h
0x180040b8a  mov     rax, cs:__security_cookie
0x180040b91  xor     rax, rsp
0x180040b94  mov     [rsp+0C8h+var_18], rax
0x180040b9c  cmp     dword ptr [rcx+8], 0
0x180040ba0  mov     rdi, rcx
0x180040ba3  mov     [rsp+0C8h+lpsz], 0
0x180040bac  jnz     short loc_180040BB8
0x180040bae  mov     eax, 80004005h
0x180040bb3  jmp     loc_180040C3C
0x180040bb8  mov     rax, [rcx]
0x180040bbb  mov     rcx, [rax+8]; rclsid
0x180040bbf  test    rcx, rcx
0x180040bc2  jnz     short loc_180040BCB
0x180040bc4  mov     eax, 8000FFFFh
0x180040bc9  jmp     short loc_180040C3C
0x180040bcb  lea     rdx, [rsp+0C8h+lpsz]; lplpsz
0x180040bd0  call    cs:__imp_StringFromCLSID
0x180040bd6  mov     ebx, eax
0x180040bd8  test    eax, eax
0x180040bda  js      short loc_180040C2F
0x180040bdc  mov     r9, [rsp+0C8h+lpsz]
0x180040be1  lea     r8, aSoftwareClasse; "Software\\Classes\\AppID\\%s"
0x180040be8  mov     edx, 3Fh ; '?'; unsigned __int64
0x180040bed  lea     rcx, [rsp+0C8h+var_98]; unsigned __int16 *
0x180040bf2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040bf7  mov     ebx, eax
0x180040bf9  test    eax, eax
0x180040bfb  js      short loc_180040C2F
0x180040bfd  lea     rdx, [rsp+0C8h+var_98]; unsigned __int16 *
0x180040c02  call    ?recursiveDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; recursiveDeleteKey(HKEY__ *,ushort const *)
0x180040c07  xor     ebx, ebx
0x180040c09  xor     esi, esi
0x180040c0b  cmp     [rdi+8], ebx
0x180040c0e  jle     short loc_180040C2F
0x180040c10  movsxd  rax, esi
0x180040c13  lea     rcx, [rax+rax*2]
0x180040c17  shl     rcx, 4
0x180040c1b  add     rcx, [rdi]; struct Registrar::ClassInfo *
0x180040c1e  call    ?UnregisterComClass@Registrar@@CAJAEBUClassInfo@1@@Z; Registrar::UnregisterComClass(Registrar::ClassInfo const &)
0x180040c23  test    eax, eax
0x180040c25  cmovs   ebx, eax
0x180040c28  inc     esi
0x180040c2a  cmp     esi, [rdi+8]
0x180040c2d  jl      short loc_180040C10
0x180040c2f  mov     rcx, [rsp+0C8h+lpsz]; pv
0x180040c34  call    cs:__imp_CoTaskMemFree
0x180040c3a  mov     eax, ebx
0x180040c3c  mov     rcx, [rsp+0C8h+var_18]
0x180040c44  xor     rcx, rsp; StackCookie
0x180040c47  call    __security_check_cookie
0x180040c4c  lea     r11, [rsp+0C8h+var_8]
0x180040c54  mov     rbx, [r11+18h]
0x180040c58  mov     rsi, [r11+20h]
0x180040c5c  mov     rsp, r11
0x180040c5f  pop     rdi
0x180040c60  retn
```
