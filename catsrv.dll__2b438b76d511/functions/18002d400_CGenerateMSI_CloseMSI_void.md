# CGenerateMSI::CloseMSI(void)

- ea: `0x18002d400`
- end: `0x18002d539`
- name: `?CloseMSI@CGenerateMSI@@UEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18002d400`
- `0x18002e304`
- `0x18002e91c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d4ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d4dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d4dc`
- `msi!__imp_MsiCloseHandle` at `0x18002d4c3`
- `msi!__imp_MsiCloseHandle` at `0x18002d4c3`
- `msi!__imp_MsiDatabaseCommit` at `0x18002d4b8`
- `msi!__imp_MsiDatabaseCommit` at `0x18002d4b8`

## string_xrefs

- `0x18002d42a`: `complus`
- `0x18002d43e`: `#complus.cab`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::CloseMSI(CGenerateMSI *this)
{
  signed int v1; // esi
  int inserted; // edi
  __int64 v4; // rcx
  const unsigned __int16 *v5; // rdx
  MSIHANDLE v6; // ecx
  void *v7; // rcx
  __int64 v8; // rcx

  v1 = 0;
  inserted = 0;
  if ( *((_DWORD *)this + 16) )
  {
    inserted = CGenerateMSI::_InsertRow(
                 this,
                 L"`Media`",
                 L"DiskId, LastSequence, DiskPrompt, Cabinet, VolumeLabel",
                 L"%d, %d, '%s', '%s', '%s'",
                 1,
                 *((_DWORD *)this + 20) - 1,
                 L"StreamCabinet",
                 L"#complus.cab",
                 L"complus");
    if ( inserted >= 0 )
    {
      v4 = *((_QWORD *)this + 77);
      if ( v4 )
      {
        inserted = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
        if ( inserted >= 0 )
        {
          inserted = CGenerateMSI::_AddCabinet(this, v5, *((const unsigned __int16 **)this + 78));
          DeleteFileW(*((LPCWSTR *)this + 78));
        }
      }
    }
  }
  v6 = *((_DWORD *)this + 16);
  if ( v6 )
  {
    v1 = MsiDatabaseCommit(v6);
    MsiCloseHandle(*((_DWORD *)this + 16));
    *((_DWORD *)this + 16) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 78);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 78) = 0;
  }
  v8 = *((_QWORD *)this + 77);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 77) = 0;
  }
  if ( !inserted && v1 )
  {
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
    else
      return (unsigned int)v1;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002d400  mov     r11, rsp
0x18002d403  mov     [r11+8], rbx
0x18002d407  mov     [r11+10h], rsi
0x18002d40b  push    rdi
0x18002d40c  sub     rsp, 50h
0x18002d410  xor     esi, esi
0x18002d412  xor     edi, edi
0x18002d414  mov     rbx, rcx
0x18002d417  cmp     [rcx+40h], esi
0x18002d41a  jz      loc_18002D4B1
0x18002d420  mov     eax, [rcx+50h]
0x18002d423  lea     r9, aDDSSS; "%d, %d, '%s', '%s', '%s'"
0x18002d42a  lea     rcx, aComplus; "complus"
0x18002d431  dec     eax
0x18002d433  mov     [r11-18h], rcx
0x18002d437  lea     r8, aDiskidLastsequ; "DiskId, LastSequence, DiskPrompt, Cabin"...
0x18002d43e  lea     rcx, aComplusCab_0; "#complus.cab"
0x18002d445  mov     [r11-20h], rcx
0x18002d449  lea     rdx, aMedia; "`Media`"
0x18002d450  lea     rcx, aStreamcabinet; "StreamCabinet"
0x18002d457  mov     [r11-28h], rcx
0x18002d45b  mov     rcx, rbx; this
0x18002d45e  mov     [rsp+58h+var_30], eax
0x18002d462  mov     [rsp+58h+var_38], 1
0x18002d46a  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002d46f  mov     edi, eax
0x18002d471  test    eax, eax
0x18002d473  js      short loc_18002D4B1
0x18002d475  mov     rcx, [rbx+268h]
0x18002d47c  test    rcx, rcx
0x18002d47f  jz      short loc_18002D4B1
0x18002d481  mov     rax, [rcx]
0x18002d484  mov     rax, [rax+28h]
0x18002d488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d48d  mov     edi, eax
0x18002d48f  test    eax, eax
0x18002d491  js      short loc_18002D4B1
0x18002d493  mov     r8, [rbx+270h]; unsigned __int16 *
0x18002d49a  mov     rcx, rbx; this
0x18002d49d  call    ?_AddCabinet@CGenerateMSI@@QEAAJPEBG0@Z; CGenerateMSI::_AddCabinet(ushort const *,ushort const *)
0x18002d4a2  mov     rcx, [rbx+270h]; lpFileName
0x18002d4a9  mov     edi, eax
0x18002d4ab  call    cs:__imp_DeleteFileW
0x18002d4b1  mov     ecx, [rbx+40h]; hDatabase
0x18002d4b4  test    ecx, ecx
0x18002d4b6  jz      short loc_18002D4D0
0x18002d4b8  call    cs:__imp_MsiDatabaseCommit
0x18002d4be  mov     ecx, [rbx+40h]; hAny
0x18002d4c1  mov     esi, eax
0x18002d4c3  call    cs:__imp_MsiCloseHandle
0x18002d4c9  mov     dword ptr [rbx+40h], 0
0x18002d4d0  mov     rcx, [rbx+270h]; pv
0x18002d4d7  test    rcx, rcx
0x18002d4da  jz      short loc_18002D4ED
0x18002d4dc  call    cs:__imp_CoTaskMemFree
0x18002d4e2  mov     qword ptr [rbx+270h], 0
0x18002d4ed  mov     rcx, [rbx+268h]
0x18002d4f4  test    rcx, rcx
0x18002d4f7  jz      short loc_18002D510
0x18002d4f9  mov     rax, [rcx]
0x18002d4fc  mov     rax, [rax+10h]
0x18002d500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d505  mov     qword ptr [rbx+268h], 0
0x18002d510  test    edi, edi
0x18002d512  jnz     short loc_18002D527
0x18002d514  test    esi, esi
0x18002d516  jz      short loc_18002D527
0x18002d518  jg      short loc_18002D51E
0x18002d51a  mov     edi, esi
0x18002d51c  jmp     short loc_18002D527
0x18002d51e  movzx   edi, si
0x18002d521  or      edi, 80070000h
0x18002d527  mov     rbx, [rsp+58h+arg_0]
0x18002d52c  mov     eax, edi
0x18002d52e  mov     rsi, [rsp+58h+arg_8]
0x18002d533  add     rsp, 50h
0x18002d537  pop     rdi
0x18002d538  retn
```
