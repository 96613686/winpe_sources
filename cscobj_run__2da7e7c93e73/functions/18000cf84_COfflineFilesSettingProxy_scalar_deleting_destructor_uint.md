# COfflineFilesSettingProxy::`scalar deleting destructor'(uint)

- ea: `0x18000cf84`
- end: `0x18000d027`
- name: `??_GCOfflineFilesSettingProxy@@AEAAPEAXI@Z`
- size: `163`
- prototype: `void *__fastcall(COfflineFilesSettingProxy *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000e4e0`

## callees

- `0x18000b7e4`
- `0x18000cf84`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cfde`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cfde`

## pseudocode

```c
COfflineFilesSettingProxy *__fastcall COfflineFilesSettingProxy::`scalar deleting destructor'(
        COfflineFilesSettingProxy *this)
{
  unsigned int v2; // edi
  LPVOID v4; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &COfflineFilesSettingProxy::`vftable'{for `IOfflineFilesSetting'};
  *((_QWORD *)this + 1) = &COfflineFilesSettingProxy::`vftable'{for `IOfflineFilesSettingInit'};
  v2 = *((_DWORD *)this + 10);
  *((_QWORD *)this + 3) = &CInterfaceInGITBase::`vftable';
  if ( v2 )
  {
    v4 = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &v4) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, v2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000cf84  mov     r11, rsp
0x18000cf87  mov     [r11+10h], rbx
0x18000cf8b  push    rdi
0x18000cf8c  sub     rsp, 30h
0x18000cf90  lea     rax, ??_7COfflineFilesSettingProxy@@6BIOfflineFilesSetting@@@; const COfflineFilesSettingProxy::`vftable'{for `IOfflineFilesSetting'}
0x18000cf97  mov     rbx, rcx
0x18000cf9a  mov     [rcx], rax
0x18000cf9d  lea     rax, ??_7COfflineFilesSettingProxy@@6BIOfflineFilesSettingInit@@@; const COfflineFilesSettingProxy::`vftable'{for `IOfflineFilesSettingInit'}
0x18000cfa4  mov     [rcx+8], rax
0x18000cfa8  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x18000cfaf  mov     edi, [rcx+28h]
0x18000cfb2  mov     [rcx+18h], rax
0x18000cfb6  test    edi, edi
0x18000cfb8  jz      short loc_18000D00C
0x18000cfba  xor     edx, edx; pUnkOuter
0x18000cfbc  mov     qword ptr [r11+8], 0
0x18000cfc4  lea     rax, [r11+8]
0x18000cfc8  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000cfcf  mov     [r11-18h], rax
0x18000cfd3  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000cfda  lea     r8d, [rdx+1]; dwClsContext
0x18000cfde  call    cs:__imp_CoCreateInstance
0x18000cfe4  test    eax, eax
0x18000cfe6  js      short loc_18000D00C
0x18000cfe8  mov     rcx, [rsp+38h+arg_0]
0x18000cfed  mov     edx, edi
0x18000cfef  mov     rax, [rcx]
0x18000cff2  mov     rax, [rax+20h]
0x18000cff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cffb  mov     rcx, [rsp+38h+arg_0]
0x18000d000  mov     rax, [rcx]
0x18000d003  mov     rax, [rax+10h]
0x18000d007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00c  mov     edx, 40h ; '@'
0x18000d011  mov     rcx, rbx; Block
0x18000d014  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d019  mov     rax, rbx
0x18000d01c  mov     rbx, [rsp+38h+arg_8]
0x18000d021  add     rsp, 30h
0x18000d025  pop     rdi
0x18000d026  retn
```
