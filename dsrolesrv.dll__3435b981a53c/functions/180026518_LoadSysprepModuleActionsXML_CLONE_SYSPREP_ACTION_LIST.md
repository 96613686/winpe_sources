# LoadSysprepModuleActionsXML(CLONE_SYSPREP_ACTION_LIST *)

- ea: `0x180026518`
- end: `0x18002660c`
- name: `?LoadSysprepModuleActionsXML@@YAKPEAVCLONE_SYSPREP_ACTION_LIST@@@Z`
- size: `244`
- prototype: `DWORD __fastcall(struct CLONE_SYSPREP_ACTION_LIST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026914`

## callees

- `0x18001ce20`
- `0x180026518`
- `0x180026ce8`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180026578`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180026578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026582`

## string_xrefs

- `0x180026539`: `Cleanup.xml`
- `0x180026545`: `Generalize.xml`
- `0x180026551`: `Specialize.xml`

## pseudocode

```c
DWORD __fastcall LoadSysprepModuleActionsXML(struct CLONE_SYSPREP_ACTION_LIST *a1)
{
  int CloneXML; // edi
  int i; // ebx
  _QWORD v4[2]; // [rsp+38h] [rbp-460h] BYREF
  _QWORD v5[3]; // [rsp+48h] [rbp-450h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-438h] BYREF
  OLECHAR psz[264]; // [rsp+270h] [rbp-228h] BYREF

  CloneXML = 0;
  v5[0] = L"Cleanup.xml";
  v5[1] = L"Generalize.xml";
  v5[2] = L"Specialize.xml";
  v4[0] = &CLONE_SYSPREP_ACTION_LIST_PARSER::`vftable';
  v4[1] = a1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  for ( i = 0; (unsigned __int64)i < 3; ++i )
  {
    StringCchPrintfW(psz, 0x104u, L"%ws\\Sysprep\\ActionFiles\\%ws", Buffer, v5[i]);
    CloneXML = LoadCloneXML(psz, 0, 0, (struct CloneXMLParser *)v4);
    if ( CloneXML )
      break;
  }
  return CloneXML;
}

```

## disassembly

```asm
0x180026518  mov     [rsp+arg_0], rbx
0x18002651d  push    rdi
0x18002651e  sub     rsp, 490h
0x180026525  mov     rax, cs:__security_cookie
0x18002652c  xor     rax, rsp
0x18002652f  mov     [rsp+498h+var_18], rax
0x180026537  xor     edi, edi
0x180026539  lea     rax, aCleanupXml; "Cleanup.xml"
0x180026540  mov     [rsp+498h+var_450], rax
0x180026545  lea     rax, aGeneralizeXml; "Generalize.xml"
0x18002654c  mov     [rsp+498h+var_448], rax
0x180026551  lea     rax, aSpecializeXml; "Specialize.xml"
0x180026558  mov     [rsp+498h+var_440], rax
0x18002655d  lea     rax, ??_7CLONE_SYSPREP_ACTION_LIST_PARSER@@6B@; const CLONE_SYSPREP_ACTION_LIST_PARSER::`vftable'
0x180026564  mov     [rsp+498h+var_460], rax
0x180026569  mov     [rsp+498h+var_458], rcx
0x18002656e  mov     edx, 104h; uSize
0x180026573  lea     rcx, [rsp+498h+Buffer]; lpBuffer
0x180026578  call    cs:__imp_GetSystemDirectoryW
0x18002657e  test    eax, eax
0x180026580  jnz     short loc_1800265A9
0x180026582  call    cs:__imp_GetLastError
0x180026588  mov     rcx, [rsp+498h+var_18]
0x180026590  xor     rcx, rsp; StackCookie
0x180026593  call    __security_check_cookie
0x180026598  mov     rbx, [rsp+498h+arg_0]
0x1800265a0  add     rsp, 490h
0x1800265a7  pop     rdi
0x1800265a8  retn
0x1800265a9  xor     ebx, ebx
0x1800265ab  mov     [rsp+498h+var_468], ebx
0x1800265af  movsxd  rax, ebx
0x1800265b2  cmp     rax, 3
0x1800265b6  jnb     short loc_180026605
0x1800265b8  mov     rax, [rsp+rax*8+498h+var_450]
0x1800265bd  mov     [rsp+498h+var_478], rax
0x1800265c2  lea     r9, [rsp+498h+Buffer]
0x1800265c7  lea     r8, aWsSysprepActio; "%ws\\Sysprep\\ActionFiles\\%ws"
0x1800265ce  mov     edx, 104h; unsigned __int64
0x1800265d3  lea     rcx, [rsp+498h+psz]; unsigned __int16 *
0x1800265db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800265e0  lea     r9, [rsp+498h+var_460]; struct CloneXMLParser *
0x1800265e5  xor     r8d, r8d; OLECHAR *
0x1800265e8  xor     edx, edx; OLECHAR *
0x1800265ea  lea     rcx, [rsp+498h+psz]; psz
0x1800265f2  call    ?LoadCloneXML@@YAJPEAG00PEAVCloneXMLParser@@@Z; LoadCloneXML(ushort *,ushort *,ushort *,CloneXMLParser *)
0x1800265f7  mov     edi, eax
0x1800265f9  mov     [rsp+498h+var_464], eax
0x1800265fd  test    eax, eax
0x1800265ff  jnz     short loc_180026605
0x180026601  inc     ebx
0x180026603  jmp     short loc_1800265AB
0x180026605  mov     eax, edi
0x180026607  jmp     loc_180026588
0x18002c74b  push    rbp
0x18002c74d  sub     rsp, 30h
0x18002c751  mov     rbp, rdx
0x18002c754  add     rsp, 30h
0x18002c758  pop     rbp
0x18002c759  retn
```
