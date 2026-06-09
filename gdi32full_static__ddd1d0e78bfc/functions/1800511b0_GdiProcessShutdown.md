# GdiProcessShutdown

- ea: `0x1800511b0`
- end: `0x180051305`
- name: `GdiProcessShutdown`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005b9f8`

## callees

- `0x1800511b0`
- `0x18005130c`
- `0x1800513dc`
- `0x180051438`
- `0x180051588`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18005120f`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18005120f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051230`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051230`
- `GDI32!pGdiSharedMemory` at `0x1800511b4`
- `GDI32!pGdiDevCaps` at `0x1800511d0`
- `GDI32!pGdiSharedHandleTable` at `0x1800511c2`
- `ntdll!RtlDeleteCriticalSection` at `0x18005126b`
- `ntdll!RtlDeleteCriticalSection` at `0x180051286`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512a1`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512bc`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512d7`
- `ntdll!RtlDeleteCriticalSection` at `0x18005126b`
- `ntdll!RtlDeleteCriticalSection` at `0x180051286`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512a1`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512bc`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512d7`
- `ntdll!RtlDeleteCriticalSection` at `0x1800512f9`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
NTSTATUS GdiProcessShutdown()
{
  NTSTATUS result; // eax

  pGdiSharedMemory = 0;
  pGdiSharedHandleTable = 0;
  pGdiDevCaps = 0;
  if ( ghUniStore )
  {
    UniStorShutdownInternal(ghUniStore);
    ghUniStore = 0;
  }
  UspShutdownMemory();
  ReleaseLocks();
  if ( gdwTlsIndex != -1 )
    TlsFree(gdwTlsIndex);
  vUMPDWow64Shutdown();
  if ( gbLpk )
    DeleteCriticalSection(&csFontIdCache);
  result = gbInitialized;
  if ( (gbInitialized & 1) != 0 )
  {
    RtlDeleteCriticalSection(&semUMPD);
    result = gbInitialized;
  }
  if ( (result & 2) != 0 )
  {
    RtlDeleteCriticalSection(&semColorSpaceCache);
    result = gbInitialized;
  }
  if ( (result & 4) != 0 )
  {
    RtlDeleteCriticalSection(&semColorTransformCache);
    result = gbInitialized;
  }
  if ( (result & 8) != 0 )
  {
    RtlDeleteCriticalSection(&semListIcmInfo);
    result = gbInitialized;
  }
  if ( (result & 0x10) != 0 )
  {
    RtlDeleteCriticalSection(&semLocal);
    result = gbInitialized;
  }
  if ( (result & 0x20) != 0 )
    return RtlDeleteCriticalSection(&semGlLoad);
  return result;
}

```

## disassembly

```asm
0x1800511b0  sub     rsp, 28h
0x1800511b4  mov     rax, cs:__imp_pGdiSharedMemory
0x1800511bb  mov     qword ptr [rax], 0
0x1800511c2  mov     rax, cs:__imp_pGdiSharedHandleTable
0x1800511c9  mov     qword ptr [rax], 0
0x1800511d0  mov     rax, cs:__imp_pGdiDevCaps
0x1800511d7  mov     qword ptr [rax], 0
0x1800511de  mov     rcx, cs:?ghUniStore@@3PEAXEA; struct _UNISTOR_CLIENT *
0x1800511e5  test    rcx, rcx
0x1800511e8  jz      short loc_1800511FA
0x1800511ea  call    ?UniStorShutdownInternal@@YAXPEAU_UNISTOR_CLIENT@@@Z; UniStorShutdownInternal(_UNISTOR_CLIENT *)
0x1800511ef  mov     cs:?ghUniStore@@3PEAXEA, 0; void * ghUniStore
0x1800511fa  call    ?UspShutdownMemory@@YAXXZ; UspShutdownMemory(void)
0x1800511ff  call    ?ReleaseLocks@@YAXXZ; ReleaseLocks(void)
0x180051204  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18005120a  cmp     ecx, 0FFFFFFFFh
0x18005120d  jz      short loc_18005121B
0x18005120f  call    cs:__imp_TlsFree
0x180051216  nop     dword ptr [rax+rax+00h]
0x18005121b  call    vUMPDWow64Shutdown
0x180051220  cmp     cs:gbLpk, 0
0x180051227  jz      short loc_18005123C
0x180051229  lea     rcx, csFontIdCache; lpCriticalSection
0x180051230  call    cs:__imp_DeleteCriticalSection
0x180051237  nop     dword ptr [rax+rax+00h]
0x18005123c  mov     eax, cs:gbInitialized
0x180051242  test    al, 1
0x180051244  jnz     short loc_180051264
0x180051246  test    al, 2
0x180051248  jnz     short loc_18005127F
0x18005124a  test    al, 4
0x18005124c  jnz     short loc_18005129A
0x18005124e  test    al, 8
0x180051250  jnz     short loc_1800512B5
0x180051252  test    al, 10h
0x180051254  jnz     short loc_1800512D0
0x180051256  test    al, 20h
0x180051258  jnz     loc_1800512EE
0x18005125e  add     rsp, 28h
0x180051262  retn
0x180051264  lea     rcx, semUMPD; CriticalSection
0x18005126b  call    cs:__imp_RtlDeleteCriticalSection
0x180051272  nop     dword ptr [rax+rax+00h]
0x180051277  mov     eax, cs:gbInitialized
0x18005127d  jmp     short loc_180051246
0x18005127f  lea     rcx, semColorSpaceCache; CriticalSection
0x180051286  call    cs:__imp_RtlDeleteCriticalSection
0x18005128d  nop     dword ptr [rax+rax+00h]
0x180051292  mov     eax, cs:gbInitialized
0x180051298  jmp     short loc_18005124A
0x18005129a  lea     rcx, semColorTransformCache; CriticalSection
0x1800512a1  call    cs:__imp_RtlDeleteCriticalSection
0x1800512a8  nop     dword ptr [rax+rax+00h]
0x1800512ad  mov     eax, cs:gbInitialized
0x1800512b3  jmp     short loc_18005124E
0x1800512b5  lea     rcx, semListIcmInfo; CriticalSection
0x1800512bc  call    cs:__imp_RtlDeleteCriticalSection
0x1800512c3  nop     dword ptr [rax+rax+00h]
0x1800512c8  mov     eax, cs:gbInitialized
0x1800512ce  jmp     short loc_180051252
0x1800512d0  lea     rcx, semLocal; CriticalSection
0x1800512d7  call    cs:__imp_RtlDeleteCriticalSection
0x1800512de  nop     dword ptr [rax+rax+00h]
0x1800512e3  mov     eax, cs:gbInitialized
0x1800512e9  jmp     loc_180051256
0x1800512ee  lea     rcx, semGlLoad
0x1800512f5  add     rsp, 28h
0x1800512f9  jmp     cs:__imp_RtlDeleteCriticalSection
```
