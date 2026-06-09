# GdiProcessShutdown

- ea: `0x18004b300`
- end: `0x18004b4a5`
- name: `GdiProcessShutdown`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180057424`

## callees

- `0x180046ff4`
- `0x18004b300`
- `0x18004b4ac`
- `0x18004b560`
- `0x18004b5b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18004b365`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18004b365`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b396`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b396`
- `GDI32!pGdiSharedMemory` at `0x18004b30a`
- `GDI32!pGdiDevCaps` at `0x18004b326`
- `GDI32!pGdiSharedHandleTable` at `0x18004b318`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b40f`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b422`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b43a`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b452`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b46a`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b482`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b49a`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b40f`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b422`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b43a`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b452`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b46a`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b482`
- `ntdll!RtlDeleteCriticalSection` at `0x18004b49a`
- `ntdll!RtlEnterCriticalSection` at `0x18004b3e5`
- `ntdll!RtlEnterCriticalSection` at `0x18004b3e5`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=1
NTSTATUS GdiProcessShutdown()
{
  struct _UMPD *i; // rbx
  __int64 v1; // rax
  NTSTATUS result; // eax
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

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
  for ( i = qword_1800FBB00; i; i = (struct _UMPD *)*((_QWORD *)i + 1) )
  {
    v1 = *((_QWORD *)i + 8);
    if ( v1 )
    {
      v4 = *((_QWORD *)i + 8);
      v3 = (struct _RTL_CRITICAL_SECTION *)(v1 + 16);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v1 + 16));
      if ( *((_DWORD *)i + 9) )
      {
        *((_DWORD *)i + 9) = 0;
        PROXYPORT::UnloadDriver((PROXYPORT *)&v4, *((_QWORD *)i + 9), 0, 0);
      }
      RtlDeleteCriticalSection(v3);
    }
  }
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
0x18004b300  mov     [rsp+arg_8], rbx
0x18004b305  push    rdi
0x18004b306  sub     rsp, 20h
0x18004b30a  mov     rax, cs:__imp_pGdiSharedMemory
0x18004b311  mov     qword ptr [rax], 0
0x18004b318  mov     rax, cs:__imp_pGdiSharedHandleTable
0x18004b31f  mov     qword ptr [rax], 0
0x18004b326  mov     rax, cs:__imp_pGdiDevCaps
0x18004b32d  mov     qword ptr [rax], 0
0x18004b334  mov     rcx, cs:?ghUniStore@@3PEAXEA; struct _UNISTOR_CLIENT *
0x18004b33b  test    rcx, rcx
0x18004b33e  jz      short loc_18004B350
0x18004b340  call    ?UniStorShutdownInternal@@YAXPEAU_UNISTOR_CLIENT@@@Z; UniStorShutdownInternal(_UNISTOR_CLIENT *)
0x18004b345  mov     cs:?ghUniStore@@3PEAXEA, 0; void * ghUniStore
0x18004b350  call    ?UspShutdownMemory@@YAXXZ; UspShutdownMemory(void)
0x18004b355  call    ?ReleaseLocks@@YAXXZ; ReleaseLocks(void)
0x18004b35a  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18004b360  cmp     ecx, 0FFFFFFFFh
0x18004b363  jz      short loc_18004B36B
0x18004b365  call    cs:__imp_TlsFree
0x18004b36b  mov     rbx, cs:qword_1800FBB00
0x18004b372  test    rbx, rbx
0x18004b375  jz      short loc_18004B386
0x18004b377  mov     rax, [rbx+40h]
0x18004b37b  test    rax, rax
0x18004b37e  jnz     short loc_18004B3D9
0x18004b380  mov     rbx, [rbx+8]
0x18004b384  jmp     short loc_18004B372
0x18004b386  cmp     cs:gbLpk, 0
0x18004b38d  jz      short loc_18004B39C
0x18004b38f  lea     rcx, csFontIdCache; lpCriticalSection
0x18004b396  call    cs:__imp_DeleteCriticalSection
0x18004b39c  mov     eax, cs:gbInitialized
0x18004b3a2  test    al, 1
0x18004b3a4  jnz     short loc_18004B41B
0x18004b3a6  test    al, 2
0x18004b3a8  jnz     loc_18004B433
0x18004b3ae  test    al, 4
0x18004b3b0  jnz     loc_18004B44B
0x18004b3b6  test    al, 8
0x18004b3b8  jnz     loc_18004B463
0x18004b3be  test    al, 10h
0x18004b3c0  jnz     loc_18004B47B
0x18004b3c6  test    al, 20h
0x18004b3c8  jnz     loc_18004B493
0x18004b3ce  mov     rbx, [rsp+28h+arg_8]
0x18004b3d3  add     rsp, 20h
0x18004b3d7  pop     rdi
0x18004b3d8  retn
0x18004b3d9  mov     [rsp+28h+arg_0], rax
0x18004b3de  lea     rdi, [rax+10h]
0x18004b3e2  mov     rcx, rdi; CriticalSection
0x18004b3e5  call    cs:__imp_RtlEnterCriticalSection
0x18004b3eb  cmp     dword ptr [rbx+24h], 0
0x18004b3ef  jz      short loc_18004B40C
0x18004b3f1  mov     dword ptr [rbx+24h], 0
0x18004b3f8  xor     r9d, r9d; int
0x18004b3fb  xor     r8d, r8d; void *
0x18004b3fe  mov     rdx, [rbx+48h]; unsigned __int64
0x18004b402  lea     rcx, [rsp+28h+arg_0]; this
0x18004b407  call    ?UnloadDriver@PROXYPORT@@QEAAX_KPEAXH@Z; PROXYPORT::UnloadDriver(unsigned __int64,void *,int)
0x18004b40c  mov     rcx, rdi; CriticalSection
0x18004b40f  call    cs:__imp_RtlDeleteCriticalSection
0x18004b415  nop
0x18004b416  jmp     loc_18004B380
0x18004b41b  lea     rcx, semUMPD; CriticalSection
0x18004b422  call    cs:__imp_RtlDeleteCriticalSection
0x18004b428  mov     eax, cs:gbInitialized
0x18004b42e  jmp     loc_18004B3A6
0x18004b433  lea     rcx, semColorSpaceCache; CriticalSection
0x18004b43a  call    cs:__imp_RtlDeleteCriticalSection
0x18004b440  mov     eax, cs:gbInitialized
0x18004b446  jmp     loc_18004B3AE
0x18004b44b  lea     rcx, semColorTransformCache; CriticalSection
0x18004b452  call    cs:__imp_RtlDeleteCriticalSection
0x18004b458  mov     eax, cs:gbInitialized
0x18004b45e  jmp     loc_18004B3B6
0x18004b463  lea     rcx, semListIcmInfo; CriticalSection
0x18004b46a  call    cs:__imp_RtlDeleteCriticalSection
0x18004b470  mov     eax, cs:gbInitialized
0x18004b476  jmp     loc_18004B3BE
0x18004b47b  lea     rcx, semLocal; CriticalSection
0x18004b482  call    cs:__imp_RtlDeleteCriticalSection
0x18004b488  mov     eax, cs:gbInitialized
0x18004b48e  jmp     loc_18004B3C6
0x18004b493  lea     rcx, semGlLoad; CriticalSection
0x18004b49a  call    cs:__imp_RtlDeleteCriticalSection
0x18004b4a0  jmp     loc_18004B3CE
```
