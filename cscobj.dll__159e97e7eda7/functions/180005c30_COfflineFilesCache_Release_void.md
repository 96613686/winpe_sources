# COfflineFilesCache::Release(void)

- ea: `0x180005c30`
- end: `0x180005d0a`
- name: `?Release@COfflineFilesCache@@UEAAKXZ`
- size: `218`
- prototype: `unsigned int __fastcall(COfflineFilesCache *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e4c0`
- `0x18000e4d0`

## callees

- `0x180005c30`
- `0x18000b7e4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005cc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005cc5`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::Release(COfflineFilesCache *this)
{
  unsigned __int32 v2; // ebx
  unsigned int v4; // esi
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &COfflineFilesCache::`vftable'{for `IOfflineFilesCache2'};
    *((_QWORD *)this + 1) = &COfflineFilesCache::`vftable'{for `IOfflineFilesItemContainer'};
    *((_QWORD *)this + 2) = &COfflineFilesCache::`vftable'{for `IConnectionPointContainer'};
    _InterlockedDecrement(&g_cRefDll);
    v4 = *((_DWORD *)this + 12);
    *((_QWORD *)this + 4) = &CInterfaceInGITBase::`vftable';
    if ( v4 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v4);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180005c30  mov     [rsp+arg_10], rbx
0x180005c35  push    rdi
0x180005c36  sub     rsp, 30h
0x180005c3a  mov     rdi, rcx
0x180005c3d  mov     ebx, 0FFFFFFFFh
0x180005c42  lock xadd [rcx+18h], ebx
0x180005c47  sub     ebx, 1
0x180005c4a  jz      short loc_180005C59
0x180005c4c  mov     eax, ebx
0x180005c4e  mov     rbx, [rsp+38h+arg_10]
0x180005c53  add     rsp, 30h
0x180005c57  pop     rdi
0x180005c58  retn
0x180005c59  test    rdi, rdi
0x180005c5c  jz      short loc_180005C4C
0x180005c5e  lea     rax, ??_7COfflineFilesCache@@6BIOfflineFilesCache2@@@; const COfflineFilesCache::`vftable'{for `IOfflineFilesCache2'}
0x180005c65  mov     [rsp+38h+arg_8], rsi
0x180005c6a  mov     [rcx], rax
0x180005c6d  lea     rax, ??_7COfflineFilesCache@@6BIOfflineFilesItemContainer@@@; const COfflineFilesCache::`vftable'{for `IOfflineFilesItemContainer'}
0x180005c74  mov     [rcx+8], rax
0x180005c78  lea     rax, ??_7COfflineFilesCache@@6BIConnectionPointContainer@@@; const COfflineFilesCache::`vftable'{for `IConnectionPointContainer'}
0x180005c7f  mov     [rcx+10h], rax
0x180005c83  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x180005c8a  lock dec cs:?g_cRefDll@@3JA; long g_cRefDll
0x180005c91  mov     esi, [rcx+30h]
0x180005c94  mov     [rcx+20h], rax
0x180005c98  test    esi, esi
0x180005c9a  jz      short loc_180005CF3
0x180005c9c  lea     rax, [rsp+38h+arg_0]
0x180005ca1  mov     [rsp+38h+arg_0], 0
0x180005caa  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180005cb1  mov     [rsp+38h+ppv], rax; ppv
0x180005cb6  xor     edx, edx; pUnkOuter
0x180005cb8  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180005cbf  mov     r8d, 1; dwClsContext
0x180005cc5  call    cs:__imp_CoCreateInstance
0x180005ccb  test    eax, eax
0x180005ccd  js      short loc_180005CF3
0x180005ccf  mov     rcx, [rsp+38h+arg_0]
0x180005cd4  mov     edx, esi
0x180005cd6  mov     rax, [rcx]
0x180005cd9  mov     rax, [rax+20h]
0x180005cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce2  mov     rcx, [rsp+38h+arg_0]
0x180005ce7  mov     rax, [rcx]
0x180005cea  mov     rax, [rax+10h]
0x180005cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf3  mov     edx, 48h ; 'H'
0x180005cf8  mov     rcx, rdi; Block
0x180005cfb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005d00  mov     rsi, [rsp+38h+arg_8]
0x180005d05  jmp     loc_180005C4C
```
