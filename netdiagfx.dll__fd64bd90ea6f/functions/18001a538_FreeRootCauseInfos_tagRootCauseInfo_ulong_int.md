# FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)

- ea: `0x18001a538`
- end: `0x18001a5ae`
- name: `?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z`
- size: `118`
- prototype: `void __fastcall(struct tagRootCauseInfo *pv, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180017b94`

## callees

- `0x18001a4e4`
- `0x18001a538`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a566`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a566`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a59b`

## pseudocode

```c
void __fastcall FreeRootCauseInfos(struct tagRootCauseInfo *pv, unsigned int a2, int a3)
{
  unsigned int v6; // r14d
  __int64 v7; // r15
  unsigned int repairCount; // edx
  RepairInfoEx *pRepairs; // rcx

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      CoTaskMemFree(pv[v7].pwszDescription);
      repairCount = pv[v7].repairCount;
      pRepairs = pv[v7].pRepairs;
      pv[v7].pwszDescription = 0;
      FreeRepairInfoExs(pRepairs, repairCount, 1);
      ++v6;
      ++v7;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18001a538  test    rcx, rcx
0x18001a53b  jz      short locret_18001A5AD
0x18001a53d  push    rbx
0x18001a53e  push    rbp
0x18001a53f  push    rsi
0x18001a540  push    rdi
0x18001a541  push    r14
0x18001a543  push    r15
0x18001a545  sub     rsp, 28h
0x18001a549  mov     ebp, r8d
0x18001a54c  mov     esi, edx
0x18001a54e  mov     rdi, rcx
0x18001a551  test    edx, edx
0x18001a553  jz      short loc_18001A5A1
0x18001a555  xor     r14d, r14d
0x18001a558  xor     r15d, r15d
0x18001a55b  mov     rbx, r15
0x18001a55e  shl     rbx, 6
0x18001a562  mov     rcx, [rbx+rdi]; pv
0x18001a566  call    cs:__imp_CoTaskMemFree
0x18001a56c  movzx   edx, word ptr [rbx+rdi+38h]; unsigned int
0x18001a571  mov     r8d, 1; int
0x18001a577  mov     rcx, [rbx+rdi+30h]; pv
0x18001a57c  mov     qword ptr [rbx+rdi], 0
0x18001a584  call    ?FreeRepairInfoExs@@YAXPEAUtagRepairInfoEx@@KH@Z; FreeRepairInfoExs(tagRepairInfoEx *,ulong,int)
0x18001a589  inc     r14d
0x18001a58c  inc     r15
0x18001a58f  cmp     r14d, esi
0x18001a592  jb      short loc_18001A55B
0x18001a594  test    ebp, ebp
0x18001a596  jz      short loc_18001A5A1
0x18001a598  mov     rcx, rdi; pv
0x18001a59b  call    cs:__imp_CoTaskMemFree
0x18001a5a1  add     rsp, 28h
0x18001a5a5  pop     r15
0x18001a5a7  pop     r14
0x18001a5a9  pop     rdi
0x18001a5aa  pop     rsi
0x18001a5ab  pop     rbp
0x18001a5ac  pop     rbx
0x18001a5ad  retn
```
