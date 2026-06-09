# ATL::CComObject<DevenvAppQueryLoadService>::~CComObject<DevenvAppQueryLoadService>(void)

- ea: `0x140037090`
- end: `0x140037111`
- name: `??1?$CComObject@VDevenvAppQueryLoadService@@@ATL@@UEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140037120`
- `0x140037220`

## callees

- `0x140002190`
- `0x140037090`

## import_xrefs

- `ADVAPI32!CryptDestroyKey` at `0x1400370ce`
- `ADVAPI32!CryptDestroyKey` at `0x1400370ce`
- `ADVAPI32!CryptReleaseContext` at `0x1400370e2`
- `ADVAPI32!CryptReleaseContext` at `0x1400370e2`
- `KERNEL32!DeleteCriticalSection` at `0x140037104`
- `KERNEL32!DeleteCriticalSection` at `0x140037104`

## pseudocode

```c
void __fastcall ATL::CComObject<DevenvAppQueryLoadService>::~CComObject<DevenvAppQueryLoadService>(__int64 a1)
{
  const struct std::nothrow_t *v2; // rdx
  HCRYPTKEY v3; // rcx
  HCRYPTPROV v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<DevenvAppQueryLoadService>::`vftable'{for `IVsAppQueryLoad'};
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
0x140037090  push    rbx
0x140037092  sub     rsp, 20h
0x140037096  mov     rbx, rcx
0x140037099  lea     rax, ??_7?$CComObject@VDevenvAppQueryLoadService@@@ATL@@6BIVsAppQueryLoad@@@; const ATL::CComObject<DevenvAppQueryLoadService>::`vftable'{for `IVsAppQueryLoad'}
0x1400370a0  mov     [rcx], rax
0x1400370a3  lea     rax, ??_7?$CComObject@VDevenvAppQueryLoadService@@@ATL@@6BIVsAppQueryLoad2@@@; const ATL::CComObject<DevenvAppQueryLoadService>::`vftable'{for `IVsAppQueryLoad2'}
0x1400370aa  mov     [rcx+8], rax
0x1400370ae  mov     dword ptr [rcx+10h], 0C0000001h
0x1400370b5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400370bc  mov     rax, [rcx]
0x1400370bf  call    qword ptr [rax+10h]
0x1400370c2  mov     rcx, [rbx+0B8h]; hKey
0x1400370c9  test    rcx, rcx
0x1400370cc  jz      short loc_1400370D4
0x1400370ce  call    cs:__imp_CryptDestroyKey
0x1400370d4  mov     rcx, [rbx+0B0h]; hProv
0x1400370db  test    rcx, rcx
0x1400370de  jz      short loc_1400370E8
0x1400370e0  xor     edx, edx; dwFlags
0x1400370e2  call    cs:__imp_CryptReleaseContext
0x1400370e8  mov     rcx, [rbx+50h]; void *
0x1400370ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400370f1  and     qword ptr [rbx+50h], 0
0x1400370f6  lea     rcx, [rbx+18h]; lpCriticalSection
0x1400370fa  cmp     byte ptr [rcx+28h], 0
0x1400370fe  jz      short loc_14003710B
0x140037100  mov     byte ptr [rcx+28h], 0
0x140037104  call    cs:__imp_DeleteCriticalSection
0x14003710a  nop
0x14003710b  add     rsp, 20h
0x14003710f  pop     rbx
0x140037110  retn
```
