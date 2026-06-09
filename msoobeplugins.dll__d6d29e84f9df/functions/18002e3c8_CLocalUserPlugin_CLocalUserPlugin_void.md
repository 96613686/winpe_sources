# CLocalUserPlugin::~CLocalUserPlugin(void)

- ea: `0x18002e3c8`
- end: `0x18002e487`
- name: `??1CLocalUserPlugin@@EEAA@XZ`
- size: `191`
- prototype: `void __fastcall(CLocalUserPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e490`

## callees

- `0x18002e3c8`
- `0x1800bf08c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e468`

## pseudocode

```c
void __fastcall CLocalUserPlugin::~CLocalUserPlugin(CLocalUserPlugin *this)
{
  _BYTE *v2; // rax
  __int64 v3; // rcx
  __int64 i; // rcx
  _BYTE *v5; // rax
  __int64 v6; // rcx
  __int64 j; // rcx

  *(_QWORD *)this = &CLocalUserPlugin::`vftable'{for `CBasePlugin'};
  *((_QWORD *)this + 3) = &CLocalUserPlugin::`vftable'{for `IOOBEUserNamePlugin'};
  *((_QWORD *)this + 4) = &CLocalUserPlugin::`vftable'{for `IOOBEPasswordPlugin'};
  *((_QWORD *)this + 5) = &CLocalUserPlugin::`vftable'{for `IOOBEGlobalSettingsCacheListener'};
  CoTaskMemFree(*((LPVOID *)this + 6));
  v2 = (_BYTE *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&v2[2 * v3] );
    for ( i = 2 * v3; i; --i )
      *v2++ = 0;
    CoTaskMemFree(*((LPVOID *)this + 7));
  }
  v5 = (_BYTE *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&v5[2 * v6] );
    for ( j = 2 * v6; j; --j )
      *v5++ = 0;
    CoTaskMemFree(*((LPVOID *)this + 8));
  }
  _InterlockedDecrement(&g_cRefCount);
  CBasePlugin::~CBasePlugin(this);
}

```

## disassembly

```asm
0x18002e3c8  mov     [rsp+arg_0], rbx
0x18002e3cd  push    rdi
0x18002e3ce  sub     rsp, 20h
0x18002e3d2  mov     rbx, rcx
0x18002e3d5  lea     rax, ??_7CLocalUserPlugin@@6BCBasePlugin@@@; const CLocalUserPlugin::`vftable'{for `CBasePlugin'}
0x18002e3dc  mov     [rcx], rax
0x18002e3df  lea     rax, ??_7CLocalUserPlugin@@6BIOOBEUserNamePlugin@@@; const CLocalUserPlugin::`vftable'{for `IOOBEUserNamePlugin'}
0x18002e3e6  mov     [rcx+18h], rax
0x18002e3ea  lea     rax, ??_7CLocalUserPlugin@@6BIOOBEPasswordPlugin@@@; const CLocalUserPlugin::`vftable'{for `IOOBEPasswordPlugin'}
0x18002e3f1  mov     [rcx+20h], rax
0x18002e3f5  lea     rax, ??_7CLocalUserPlugin@@6BIOOBEGlobalSettingsCacheListener@@@; const CLocalUserPlugin::`vftable'{for `IOOBEGlobalSettingsCacheListener'}
0x18002e3fc  mov     [rcx+28h], rax
0x18002e400  mov     rcx, [rcx+30h]; pv
0x18002e404  call    cs:__imp_CoTaskMemFree
0x18002e40a  mov     rax, [rbx+38h]
0x18002e40e  xor     edi, edi
0x18002e410  test    rax, rax
0x18002e413  jz      short loc_18002E43D
0x18002e415  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e419  inc     rcx
0x18002e41c  cmp     [rax+rcx*2], di
0x18002e420  jnz     short loc_18002E419
0x18002e422  add     rcx, rcx
0x18002e425  jz      short loc_18002E433
0x18002e427  mov     [rax], dil
0x18002e42a  inc     rax
0x18002e42d  sub     rcx, 1
0x18002e431  jnz     short loc_18002E427
0x18002e433  mov     rcx, [rbx+38h]; pv
0x18002e437  call    cs:__imp_CoTaskMemFree
0x18002e43d  mov     rax, [rbx+40h]
0x18002e441  test    rax, rax
0x18002e444  jz      short loc_18002E46E
0x18002e446  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e44a  inc     rcx
0x18002e44d  cmp     [rax+rcx*2], di
0x18002e451  jnz     short loc_18002E44A
0x18002e453  add     rcx, rcx
0x18002e456  jz      short loc_18002E464
0x18002e458  mov     [rax], dil
0x18002e45b  inc     rax
0x18002e45e  sub     rcx, 1
0x18002e462  jnz     short loc_18002E458
0x18002e464  mov     rcx, [rbx+40h]; pv
0x18002e468  call    cs:__imp_CoTaskMemFree
0x18002e46e  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x18002e475  mov     rcx, rbx; this
0x18002e478  mov     rbx, [rsp+28h+arg_0]
0x18002e47d  add     rsp, 20h
0x18002e481  pop     rdi
0x18002e482  jmp     ??1CBasePlugin@@MEAA@XZ; CBasePlugin::~CBasePlugin(void)
```
