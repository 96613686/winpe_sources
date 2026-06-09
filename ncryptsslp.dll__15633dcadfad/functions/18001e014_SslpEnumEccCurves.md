# SslpEnumEccCurves

- ea: `0x18001e014`
- end: `0x18001e0d5`
- name: `SslpEnumEccCurves`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e0dc`
- `0x18001eb90`

## callees

- `0x180007940`
- `0x18000b654`
- `0x180012fa4`
- `0x18001e014`
- `0x180024fb0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001e070`
- `ntdll!RtlReleaseResource` at `0x18001e0c1`
- `ntdll!RtlReleaseResource` at `0x18001e070`
- `ntdll!RtlReleaseResource` at `0x18001e0c1`
- `ntdll!RtlAcquireResourceShared` at `0x18001e049`
- `ntdll!RtlAcquireResourceShared` at `0x18001e049`

## string_xrefs

- `0x18001e07b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\enum.c`

## pseudocode

```c
__int64 __fastcall SslpEnumEccCurves(__int64 a1, int *a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  void *v6; // rax
  void *v7; // rdi
  int v8; // ebx

  *a3 = 0;
  *a2 = 0;
  v5 = BuildEccCurves();
  if ( !v5 )
  {
    RtlAcquireResourceShared(&g_EccCurvesRWLock, 1u);
    v6 = (void *)SafeAllocaAllocateFromHeap(780LL * (unsigned int)g_EccCurvesCount);
    v7 = v6;
    if ( v6 )
    {
      v8 = g_EccCurvesCount;
      memmove(v6, g_EccCurves, 780LL * (unsigned int)g_EccCurvesCount);
      *a3 = v7;
      *a2 = v8;
      RtlReleaseResource(&g_EccCurvesRWLock);
      return 0;
    }
    else
    {
      RtlReleaseResource(&g_EccCurvesRWLock);
      v5 = -2146893810;
      DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\enum.c", 1517);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001e014  push    rbx
0x18001e016  push    rsi
0x18001e017  push    rdi
0x18001e018  push    r14
0x18001e01a  sub     rsp, 28h
0x18001e01e  mov     qword ptr [r8], 0
0x18001e025  mov     rsi, r8
0x18001e028  mov     dword ptr [rdx], 0
0x18001e02e  mov     r14, rdx
0x18001e031  call    BuildEccCurves
0x18001e036  mov     ebx, eax
0x18001e038  test    eax, eax
0x18001e03a  jnz     loc_18001E0C9
0x18001e040  mov     dl, 1; Wait
0x18001e042  lea     rcx, g_EccCurvesRWLock; Resource
0x18001e049  call    cs:__imp_RtlAcquireResourceShared
0x18001e04f  mov     eax, cs:g_EccCurvesCount
0x18001e055  imul    rcx, rax, 30Ch
0x18001e05c  call    SafeAllocaAllocateFromHeap
0x18001e061  mov     rdi, rax
0x18001e064  test    rax, rax
0x18001e067  jnz     short loc_18001E098
0x18001e069  lea     rcx, g_EccCurvesRWLock; Resource
0x18001e070  call    cs:__imp_RtlReleaseResource
0x18001e076  mov     ebx, 8009000Eh
0x18001e07b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e082  mov     ecx, ebx
0x18001e084  lea     rdx, aStatus; "Status"
0x18001e08b  mov     r9d, 5EDh
0x18001e091  call    DebugTraceError
0x18001e096  jmp     short loc_18001E0C9
0x18001e098  mov     ebx, cs:g_EccCurvesCount
0x18001e09e  mov     rcx, rdi; void *
0x18001e0a1  mov     rdx, cs:g_EccCurves; Src
0x18001e0a8  imul    r8, rbx, 30Ch; Size
0x18001e0af  call    memmove
0x18001e0b4  mov     [rsi], rdi
0x18001e0b7  lea     rcx, g_EccCurvesRWLock; Resource
0x18001e0be  mov     [r14], ebx
0x18001e0c1  call    cs:__imp_RtlReleaseResource
0x18001e0c7  xor     ebx, ebx
0x18001e0c9  mov     eax, ebx
0x18001e0cb  add     rsp, 28h
0x18001e0cf  pop     r14
0x18001e0d1  pop     rdi
0x18001e0d2  pop     rsi
0x18001e0d3  pop     rbx
0x18001e0d4  retn
```
