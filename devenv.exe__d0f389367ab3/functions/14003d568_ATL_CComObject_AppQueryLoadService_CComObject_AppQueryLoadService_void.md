# ATL::CComObject<AppQueryLoadService>::~CComObject<AppQueryLoadService>(void)

- ea: `0x14003d568`
- end: `0x14003d5e9`
- name: `??1?$CComObject@VAppQueryLoadService@@@ATL@@UEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14003dae0`
- `0x14003e540`

## callees

- `0x140002190`
- `0x14003d568`

## import_xrefs

- `ADVAPI32!CryptDestroyKey` at `0x14003d5a6`
- `ADVAPI32!CryptDestroyKey` at `0x14003d5a6`
- `ADVAPI32!CryptReleaseContext` at `0x14003d5ba`
- `ADVAPI32!CryptReleaseContext` at `0x14003d5ba`
- `KERNEL32!DeleteCriticalSection` at `0x14003d5dc`
- `KERNEL32!DeleteCriticalSection` at `0x14003d5dc`

## pseudocode

```c
void __fastcall ATL::CComObject<AppQueryLoadService>::~CComObject<AppQueryLoadService>(__int64 a1)
{
  const struct std::nothrow_t *v2; // rdx
  HCRYPTKEY v3; // rcx
  HCRYPTPROV v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<AppQueryLoadService>::`vftable'{for `IVsAppQueryLoad'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<DevenvAppQueryLoadService>::`vftable'{for `IVsAppQueryLoad2'};
  *(_DWORD *)(a1 + 16) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(_QWORD *)(a1 + 184);
  if ( v3 )
    CryptDestroyKey(v3);
  v4 = *(_QWORD *)(a1 + 176);
  if ( v4 )
    CryptReleaseContext(v4, 0);
  operator delete(*(void **)(a1 + 80), v2);
  *(_QWORD *)(a1 + 80) = 0;
  if ( *(_BYTE *)(a1 + 64) )
  {
    *(_BYTE *)(a1 + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  }
}

```

## disassembly

```asm
0x14003d568  push    rbx
0x14003d56a  sub     rsp, 20h
0x14003d56e  mov     rbx, rcx
0x14003d571  lea     rax, ??_7?$CComObject@VAppQueryLoadService@@@ATL@@6BIVsAppQueryLoad@@@; const ATL::CComObject<AppQueryLoadService>::`vftable'{for `IVsAppQueryLoad'}
0x14003d578  mov     [rcx], rax
0x14003d57b  lea     rax, ??_7?$CComObject@VDevenvAppQueryLoadService@@@ATL@@6BIVsAppQueryLoad2@@@; const ATL::CComObject<DevenvAppQueryLoadService>::`vftable'{for `IVsAppQueryLoad2'}
0x14003d582  mov     [rcx+8], rax
0x14003d586  mov     dword ptr [rcx+10h], 0C0000001h
0x14003d58d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14003d594  mov     rax, [rcx]
0x14003d597  call    qword ptr [rax+10h]
0x14003d59a  mov     rcx, [rbx+0B8h]; hKey
0x14003d5a1  test    rcx, rcx
0x14003d5a4  jz      short loc_14003D5AC
0x14003d5a6  call    cs:__imp_CryptDestroyKey
0x14003d5ac  mov     rcx, [rbx+0B0h]; hProv
0x14003d5b3  test    rcx, rcx
0x14003d5b6  jz      short loc_14003D5C0
0x14003d5b8  xor     edx, edx; dwFlags
0x14003d5ba  call    cs:__imp_CryptReleaseContext
0x14003d5c0  mov     rcx, [rbx+50h]; void *
0x14003d5c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003d5c9  and     qword ptr [rbx+50h], 0
0x14003d5ce  lea     rcx, [rbx+18h]; lpCriticalSection
0x14003d5d2  cmp     byte ptr [rcx+28h], 0
0x14003d5d6  jz      short loc_14003D5E3
0x14003d5d8  mov     byte ptr [rcx+28h], 0
0x14003d5dc  call    cs:__imp_DeleteCriticalSection
0x14003d5e2  nop
0x14003d5e3  add     rsp, 20h
0x14003d5e7  pop     rbx
0x14003d5e8  retn
```
