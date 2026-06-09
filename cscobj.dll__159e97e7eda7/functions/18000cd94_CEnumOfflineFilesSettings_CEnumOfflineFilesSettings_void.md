# CEnumOfflineFilesSettings::~CEnumOfflineFilesSettings(void)

- ea: `0x18000cd94`
- end: `0x18000ce29`
- name: `??1CEnumOfflineFilesSettings@@AEAA@XZ`
- size: `149`
- prototype: `void __fastcall(CEnumOfflineFilesSettings *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e470`

## callees

- `0x18000cd94`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cdf5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cdf5`

## pseudocode

```c
void __fastcall CEnumOfflineFilesSettings::~CEnumOfflineFilesSettings(CEnumOfflineFilesSettings *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CEnumOfflineFilesSettings::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 3) = &CInterfaceInGITBase::`vftable';
  v3 = *((_DWORD *)this + 10);
  if ( v3 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v3);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
}

```

## disassembly

```asm
0x18000cd94  push    rbx
0x18000cd96  sub     rsp, 30h
0x18000cd9a  lea     rax, ??_7CEnumOfflineFilesSettings@@6B@; const CEnumOfflineFilesSettings::`vftable'
0x18000cda1  mov     rbx, rcx
0x18000cda4  mov     [rcx], rax
0x18000cda7  mov     rcx, [rcx+10h]
0x18000cdab  test    rcx, rcx
0x18000cdae  jz      short loc_18000CDBC
0x18000cdb0  mov     rax, [rcx]
0x18000cdb3  mov     rax, [rax+10h]
0x18000cdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdbc  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x18000cdc3  mov     [rbx+18h], rax
0x18000cdc7  mov     ebx, [rbx+28h]
0x18000cdca  test    ebx, ebx
0x18000cdcc  jz      short loc_18000CE23
0x18000cdce  xor     edx, edx; pUnkOuter
0x18000cdd0  mov     [rsp+38h+arg_0], 0
0x18000cdd9  lea     rax, [rsp+38h+arg_0]
0x18000cdde  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000cde5  mov     [rsp+38h+ppv], rax; ppv
0x18000cdea  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000cdf1  lea     r8d, [rdx+1]; dwClsContext
0x18000cdf5  call    cs:__imp_CoCreateInstance
0x18000cdfb  test    eax, eax
0x18000cdfd  js      short loc_18000CE23
0x18000cdff  mov     rcx, [rsp+38h+arg_0]
0x18000ce04  mov     edx, ebx
0x18000ce06  mov     rax, [rcx]
0x18000ce09  mov     rax, [rax+20h]
0x18000ce0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce12  mov     rcx, [rsp+38h+arg_0]
0x18000ce17  mov     rax, [rcx]
0x18000ce1a  mov     rax, [rax+10h]
0x18000ce1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce23  add     rsp, 30h
0x18000ce27  pop     rbx
0x18000ce28  retn
```
