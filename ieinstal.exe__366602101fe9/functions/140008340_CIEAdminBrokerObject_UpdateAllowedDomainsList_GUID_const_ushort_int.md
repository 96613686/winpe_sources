# CIEAdminBrokerObject::UpdateAllowedDomainsList(_GUID const &,ushort *,int)

- ea: `0x140008340`
- end: `0x1400083a0`
- name: `?UpdateAllowedDomainsList@CIEAdminBrokerObject@@UEAAJAEBU_GUID@@PEAGH@Z`
- size: `96`
- prototype: `__int64 __fastcall(CIEAdminBrokerObject *__hidden this, const struct _GUID *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008340`

## import_xrefs

- `iertutil!__imp_?EDL_InitializeAllowedDomainsList@@YAJAEBU_GUID@@PEBG@Z` at `0x14000837a`
- `iertutil!__imp_?EDL_InitializeAllowedDomainsList@@YAJAEBU_GUID@@PEBG@Z` at `0x14000837a`
- `iertutil!__imp_?EDL_AddNewDomain@@YAJAEBU_GUID@@PEBG@Z` at `0x140008388`
- `iertutil!__imp_?EDL_AddNewDomain@@YAJAEBU_GUID@@PEBG@Z` at `0x140008388`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::UpdateAllowedDomainsList(
        CIEAdminBrokerObject *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        int a4)
{
  unsigned int v5; // r10d
  __int64 v6; // rdx

  v5 = -2147467259;
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    v5 = -2147024891;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)(v6 + 88) && *(_QWORD *)a2->Data4 == *(_QWORD *)(v6 + 96) )
    {
      if ( a4 )
        return (unsigned int)EDL_AddNewDomain(a2, a3);
      else
        return (unsigned int)EDL_InitializeAllowedDomainsList(a2, a3);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140008340  sub     rsp, 28h
0x140008344  mov     r11, rdx
0x140008347  mov     r10d, 80004005h
0x14000834d  mov     rdx, [rcx+10h]
0x140008351  test    rdx, rdx
0x140008354  jz      short loc_140008397
0x140008356  mov     rax, [r11]
0x140008359  mov     r10d, 80070005h
0x14000835f  cmp     rax, [rdx+58h]
0x140008363  jnz     short loc_140008397
0x140008365  mov     rax, [r11+8]
0x140008369  cmp     rax, [rdx+60h]
0x14000836d  jnz     short loc_140008397
0x14000836f  mov     rdx, r8
0x140008372  mov     rcx, r11
0x140008375  test    r9d, r9d
0x140008378  jnz     short loc_140008388
0x14000837a  call    cs:__imp_?EDL_InitializeAllowedDomainsList@@YAJAEBU_GUID@@PEBG@Z; EDL_InitializeAllowedDomainsList(_GUID const &,ushort const *)
0x140008381  nop     dword ptr [rax+rax+00h]
0x140008386  jmp     short loc_140008394
0x140008388  call    cs:__imp_?EDL_AddNewDomain@@YAJAEBU_GUID@@PEBG@Z; EDL_AddNewDomain(_GUID const &,ushort const *)
0x14000838f  nop     dword ptr [rax+rax+00h]
0x140008394  mov     r10d, eax
0x140008397  mov     eax, r10d
0x14000839a  add     rsp, 28h
0x14000839e  retn
```
