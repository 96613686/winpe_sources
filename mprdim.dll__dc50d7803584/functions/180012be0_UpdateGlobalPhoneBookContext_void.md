# UpdateGlobalPhoneBookContext(void)

- ea: `0x180012be0`
- end: `0x180012c20`
- name: `?UpdateGlobalPhoneBookContext@@YAXXZ`
- size: `64`
- prototype: `void(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800033c8`
- `0x1800042a8`
- `0x1800057f0`
- `0x180006fac`
- `0x18000e270`
- `0x180011eb0`
- `0x180027f74`

## callees

- `0x180012be0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012beb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012beb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c19`
- `MPRDDM!DdmUpdateGlobalPhoneBookContext` at `0x180012c08`
- `MPRDDM!DdmUpdateGlobalPhoneBookContext` at `0x180012c08`

## pseudocode

```c
void UpdateGlobalPhoneBookContext(void)
{
  AcquireSRWLockExclusive(&gblPbkContextRWLock);
  if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    DdmUpdateGlobalPhoneBookContext(&gblPbkContext, &g_dwRasApiPbkTlsIndex);
  ReleaseSRWLockExclusive(&gblPbkContextRWLock);
}

```

## disassembly

```asm
0x180012be0  sub     rsp, 28h
0x180012be4  lea     rcx, ?gblPbkContextRWLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180012beb  call    cs:__imp_AcquireSRWLockExclusive
0x180012bf1  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x180012bf8  jz      short loc_180012C0E
0x180012bfa  lea     rdx, ?g_dwRasApiPbkTlsIndex@@3KA; ulong g_dwRasApiPbkTlsIndex
0x180012c01  lea     rcx, ?gblPbkContext@@3PEAXEA; void * gblPbkContext
0x180012c08  call    cs:__imp_DdmUpdateGlobalPhoneBookContext
0x180012c0e  lea     rcx, ?gblPbkContextRWLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gblPbkContextRWLock
0x180012c15  add     rsp, 28h
0x180012c19  jmp     cs:__imp_ReleaseSRWLockExclusive
```
