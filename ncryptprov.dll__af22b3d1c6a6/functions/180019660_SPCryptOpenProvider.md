# SPCryptOpenProvider

- ea: `0x180019660`
- end: `0x1800198e2`
- name: `SPCryptOpenProvider`
- size: `642`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x180019660`
- `0x1800198f0`
- `0x180038970`
- `0x1800398b0`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180019788`
- `ntdll!RtlInitializeResource` at `0x180019788`
- `ntdll!RtlAllocateHeap` at `0x1800196f6`
- `ntdll!RtlAllocateHeap` at `0x1800196f6`

## string_xrefs

- `0x1800197a1`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180019800`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180019857`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180019878`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x1800198a0`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x1800198bb`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall SPCryptOpenProvider(_QWORD *a1, _WORD *a2, int a3)
{
  __int64 v5; // rax
  size_t v6; // rdi
  unsigned int v7; // ebx
  unsigned int v9; // r15d
  char *Heap; // rax
  int v11; // edx
  char *v12; // rsi
  unsigned int AppContainerInfo; // eax
  __int64 v14; // r9
  __int64 v15; // rcx

  if ( a1 )
  {
    if ( (a3 & 0xFFFFFFBF) != 0 )
    {
      v7 = -2146893815;
      v14 = 870;
      v15 = 2148073481LL;
    }
    else
    {
      if ( a2 )
      {
        v5 = -1;
        do
          ++v5;
        while ( a2[v5] );
        v6 = 2 * v5 + 2;
        if ( v6 <= 0xFFFF )
        {
          v9 = 2 * v5 + 162;
          Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
          v12 = Heap;
          if ( Heap )
          {
            memset_0(Heap, 0, v9);
            *(_DWORD *)v12 = v9;
            *(_QWORD *)(v12 + 4) = 1263751248;
            *((_QWORD *)v12 + 2) = v12 + 160;
            *((_QWORD *)v12 + 4) = 0;
            *((_DWORD *)v12 + 12) = 0;
            *((_DWORD *)v12 + 13) = 0;
            *((_DWORD *)v12 + 14) = 0;
            *((_DWORD *)v12 + 15) = 0;
            AppContainerInfo = GetAppContainerInfo();
            if ( AppContainerInfo )
              DebugTraceError(
                AppContainerInfo,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
                932);
            memcpy_0(*((void **)v12 + 2), a2, v6);
            RtlInitializeResource((PRTL_RESOURCE)(v12 + 64));
            *a1 = v12;
            return 0;
          }
          else
          {
            v7 = -2146893810;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v11,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
                (unsigned int)"Status",
                14,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
                131);
          }
        }
        else
        {
          return (unsigned int)-2146893805;
        }
        return v7;
      }
      v7 = -2146893805;
      v14 = 876;
      v15 = 2148073491LL;
    }
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v14);
    return v7;
  }
  v7 = -2146893785;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
      96);
  return v7;
}

```

## disassembly

```asm
0x180019660  push    rbx
0x180019662  push    rsi
0x180019663  push    rdi
0x180019664  push    r12
0x180019666  push    r14
0x180019668  push    r15
0x18001966a  sub     rsp, 48h
0x18001966e  mov     rbx, rdx
0x180019671  mov     r14, rcx
0x180019674  xor     esi, esi
0x180019676  test    rcx, rcx
0x180019679  jz      loc_180019829
0x18001967f  test    r8d, 0FFFFFFBFh
0x180019686  jnz     loc_18001986D
0x18001968c  test    rdx, rdx
0x18001968f  jz      loc_180019895
0x180019695  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001969c  nop     dword ptr [rax+00h]
0x1800196a0  lea     rax, [rax+1]
0x1800196a4  cmp     [rdx+rax*2], si
0x1800196a8  jnz     short loc_1800196A0
0x1800196aa  lea     rdi, ds:2[rax*2]
0x1800196b2  cmp     rdi, 0FFFFh
0x1800196b9  jbe     short loc_1800196DA
0x1800196bb  mov     ebx, 80090013h
0x1800196c0  test    rsi, rsi
0x1800196c3  jnz     loc_1800198D5
0x1800196c9  mov     eax, ebx
0x1800196cb  add     rsp, 48h
0x1800196cf  pop     r15
0x1800196d1  pop     r14
0x1800196d3  pop     r12
0x1800196d5  pop     rdi
0x1800196d6  pop     rsi
0x1800196d7  pop     rbx
0x1800196d8  retn
0x1800196da  lea     r15d, [rdi+0A0h]
0x1800196e1  mov     r12d, r15d
0x1800196e4  mov     rcx, gs:60h
0x1800196ed  mov     r8d, r15d; Size
0x1800196f0  xor     edx, edx; Flags
0x1800196f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800196f6  call    cs:__imp_RtlAllocateHeap
0x1800196fd  nop     dword ptr [rax+rax+00h]
0x180019702  mov     rsi, rax
0x180019705  mov     [rsp+78h+arg_0], rax
0x18001970d  test    rax, rax
0x180019710  jz      loc_1800197D2
0x180019716  mov     r8d, r12d; Size
0x180019719  xor     edx, edx; Val
0x18001971b  mov     rcx, rax; void *
0x18001971e  call    memset_0
0x180019723  mov     [rsi], r15d
0x180019726  mov     qword ptr [rsi+4], 4B535050h
0x18001972e  lea     rax, [rsi+0A0h]
0x180019735  mov     [rsi+10h], rax
0x180019739  mov     qword ptr [rsi+20h], 0
0x180019741  lea     rcx, [rsi+30h]
0x180019745  mov     dword ptr [rcx], 0
0x18001974b  lea     rdx, [rsi+34h]
0x18001974f  mov     dword ptr [rdx], 0
0x180019755  lea     r8, [rsi+38h]
0x180019759  mov     dword ptr [r8], 0
0x180019760  mov     dword ptr [rsi+3Ch], 0
0x180019767  call    GetAppContainerInfo
0x18001976c  test    eax, eax
0x18001976e  jnz     loc_1800198B5
0x180019774  mov     r8, rdi; Size
0x180019777  mov     rdx, rbx; Src
0x18001977a  mov     rcx, [rsi+10h]; void *
0x18001977e  call    memcpy_0
0x180019783  nop
0x180019784  lea     rcx, [rsi+40h]; Resource
0x180019788  call    cs:__imp_RtlInitializeResource
0x18001978f  nop     dword ptr [rax+rax+00h]
0x180019794  jmp     short loc_1800197C6
0x180019796  mov     ebx, 8009000Eh
0x18001979b  mov     r9d, 3AEh
0x1800197a1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800197a8  lea     rdx, aStatus; "Status"
0x1800197af  mov     ecx, 8009000Eh
0x1800197b4  call    DebugTraceError
0x1800197b9  mov     rsi, [rsp+78h+arg_0]
0x1800197c1  jmp     loc_1800196C0
0x1800197c6  mov     [r14], rsi
0x1800197c9  xor     esi, esi
0x1800197cb  xor     ebx, ebx
0x1800197cd  jmp     loc_1800196C0
0x1800197d2  mov     ebx, 8009000Eh
0x1800197d7  lea     rax, WPP_GLOBAL_Control
0x1800197de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197e5  cmp     rcx, rax
0x1800197e8  jz      loc_1800196C0
0x1800197ee  test    byte ptr [rcx+1Ch], 1
0x1800197f2  jz      loc_1800196C0
0x1800197f8  mov     [rsp+78h+var_48], 383h
0x180019800  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019807  mov     [rsp+78h+var_50], r8
0x18001980c  mov     [rsp+78h+var_58], 8009000Eh
0x180019814  lea     r9, aStatus; "Status"
0x18001981b  mov     rcx, [rcx+10h]
0x18001981f  call    WPP_SF_sDsd
0x180019824  jmp     loc_1800196C0
0x180019829  mov     ebx, 80090027h
0x18001982e  lea     rax, WPP_GLOBAL_Control
0x180019835  mov     rcx, cs:WPP_GLOBAL_Control
0x18001983c  cmp     rcx, rax
0x18001983f  jz      loc_1800196C0
0x180019845  test    byte ptr [rcx+1Ch], 1
0x180019849  jz      loc_1800196C0
0x18001984f  mov     [rsp+78h+var_48], 360h
0x180019857  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001985e  mov     [rsp+78h+var_50], r8
0x180019863  mov     [rsp+78h+var_58], 80090027h
0x18001986b  jmp     short loc_180019814
0x18001986d  mov     ebx, 80090009h
0x180019872  mov     r9d, 366h
0x180019878  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001987f  lea     rdx, aStatus; "Status"
0x180019886  mov     ecx, 80090009h
0x18001988b  call    DebugTraceError
0x180019890  jmp     loc_1800196C0
0x180019895  mov     ebx, 80090013h
0x18001989a  mov     r9d, 36Ch
0x1800198a0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800198a7  lea     rdx, aStatus; "Status"
0x1800198ae  mov     ecx, 80090013h
0x1800198b3  jmp     short loc_18001988B
0x1800198b5  mov     r9d, 3A4h
0x1800198bb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800198c2  lea     rdx, aStatus; "Status"
0x1800198c9  mov     ecx, eax
0x1800198cb  call    DebugTraceError
0x1800198d0  jmp     loc_180019774
0x1800198d5  mov     rcx, rsi
0x1800198d8  call    MSCryptFree
0x1800198dd  jmp     loc_1800196C9
```
