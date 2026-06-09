# DbgkWerCaptureLiveKernelDump2

- ea: `0x140ade650`
- end: `0x140ade8c9`
- name: `DbgkWerCaptureLiveKernelDump2`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14060d920`
- `0x140ade5d0`

## callees

- `0x140214b10`
- `0x1402a2f90`
- `0x14036f270`
- `0x140751fac`
- `0x140752294`
- `0x1407522b4`
- `0x140ade650`
- `0x140ade8d0`
- `0x140bb1410`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x140ade843`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x140ade843`

## string_xrefs

- `0x140ade857`: `DBGK: DbgkWerCaptureLiveKernelDump: WerLiveKernelCreateReport failed, status 0x%x.\n\n`

## pseudocode

```c
__int64 __fastcall DbgkWerCaptureLiveKernelDump2(
        _WORD *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  char v7; // di
  unsigned int v13; // ebx
  __int64 Pool2; // rsi
  __int64 v15; // rdx
  _WORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  _WORD *v19; // r8
  _WORD *v20; // rcx
  int v21; // eax
  int v22; // ecx
  unsigned int v23; // ecx
  int v24; // eax
  unsigned int v25; // eax
  char v26[4]; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v27; // [rsp+24h] [rbp-54h] BYREF
  _QWORD v28[10]; // [rsp+28h] [rbp-50h] BYREF

  v7 = 1;
  v26[0] = 1;
  v27 = 0;
  v28[0] = 0;
  if ( KeGetCurrentIrql() )
  {
    DbgPrintEx(5u, 1u, "DBGK: DbgkWerCaptureLiveKernelDump2: called at IRQL > PASSIVE_LEVEL\n");
    return 3221225800LL;
  }
  if ( !DbgkpWerInitialized )
  {
    DbgPrintEx(5u, 1u, "DBGK: DbgkWerCaptureLiveKernelDump2: called before initialization.\n");
    return 3221225635LL;
  }
  if ( (unsigned __int8)DbgkpWerIsFullLiveDumpDisabled() )
  {
    DbgPrintEx(5u, 1u, "DBGK: Full Live Kernel Dumps are disabled. Failing request.\n");
    return 3221227524LL;
  }
  if ( !a7 )
  {
    DbgPrintEx(5u, 1u, "DBGK: DbgkWerCaptureLiveKernelDump2: Called without dump control.\n");
    return 3221225485LL;
  }
  KeEnterCriticalRegion();
  if ( _InterlockedExchange(&DbgkpBusy, 1) != 1 )
  {
    Pool2 = ExAllocatePool2(256, 176, 0x57676244u);
    if ( !Pool2 )
    {
      v13 = -1073741670;
LABEL_36:
      _InterlockedExchange(&DbgkpBusy, 0);
      goto LABEL_37;
    }
    if ( a1 )
    {
      v15 = 16;
      v16 = a1;
      v17 = 16;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v17;
      }
      while ( v17 );
      v13 = v17 == 0 ? 0xC000000D : 0;
      if ( !v17 )
        goto LABEL_35;
      v18 = 2147483646;
      v19 = (_WORD *)Pool2;
      do
      {
        if ( !v18 )
          break;
        if ( !*a1 )
          break;
        *v19++ = *a1++;
        --v18;
        --v15;
      }
      while ( v15 );
      v20 = v19 - 1;
      v13 = v15 == 0 ? 0x80000005 : 0;
      if ( v15 )
        v20 = v19;
      *v20 = 0;
      if ( v15 )
      {
        v21 = DbgkpWerDefaultPolicy;
        if ( (*(_BYTE *)(a7 + 24) & 2) != 0 )
          v21 = 1;
        v27 = v21;
        v22 = *(_DWORD *)(Pool2 + 104);
        *(_QWORD *)(Pool2 + 56) = a5;
        v23 = v22 & 0xFFFFFFFD;
        *(_QWORD *)(Pool2 + 64) = a6;
        *(_DWORD *)(Pool2 + 32) = a2;
        *(_QWORD *)(Pool2 + 40) = a3;
        *(_QWORD *)(Pool2 + 48) = a4;
        *(_QWORD *)(Pool2 + 72) = a7;
        if ( (*(_DWORD *)(a7 + 24) & 8) == 0 )
          v23 |= 2u;
        *(_DWORD *)(Pool2 + 104) = v23;
        v28[0] = 0;
        v24 = WerLiveKernelCreateReport(Pool2, &v27, v28);
        v13 = v24;
        if ( v24 < 0 )
        {
          DbgPrintEx(
            5u,
            0,
            "DBGK: DbgkWerCaptureLiveKernelDump: WerLiveKernelCreateReport failed, status 0x%x.\n\n",
            v24);
LABEL_35:
          DbgkpWerCleanupContext(Pool2);
          DbgkpWerFreePool(Pool2);
          goto LABEL_36;
        }
        v25 = DbgkpWerProcessPolicyResult(Pool2, v27, v28[0], v26);
        v7 = v26[0];
        v13 = v25;
      }
      if ( !v7 )
        goto LABEL_37;
      goto LABEL_35;
    }
    v13 = -1073741811;
    goto LABEL_35;
  }
  v13 = -1073741267;
LABEL_37:
  KeLeaveCriticalRegion();
  return v13;
}

```

## disassembly

```asm
0x140ade650  push    rbx
0x140ade652  push    rbp
0x140ade653  push    rsi
0x140ade654  push    rdi
0x140ade655  push    r12
0x140ade657  push    r13
0x140ade659  push    r14
0x140ade65b  push    r15
0x140ade65d  sub     rsp, 38h
0x140ade661  xor     ebx, ebx
0x140ade663  mov     edi, 1
0x140ade668  mov     [rsp+78h+var_58], dil
0x140ade66d  mov     r15, r9
0x140ade670  mov     [rsp+78h+var_54], ebx
0x140ade674  mov     r12, r8
0x140ade677  mov     [rsp+78h+var_50], rbx
0x140ade67c  mov     r13d, edx
0x140ade67f  mov     r14, rcx
0x140ade682  mov     rax, cr8
0x140ade686  test    al, al
0x140ade688  jz      short loc_140ADE6A5
0x140ade68a  lea     r8, aDbgkDbgkwercap; "DBGK: DbgkWerCaptureLiveKernelDump2: ca"...
0x140ade691  mov     edx, edi; Level
0x140ade693  lea     ecx, [rdi+4]; ComponentId
0x140ade696  call    DbgPrintEx
0x140ade69b  mov     eax, 0C0000148h
0x140ade6a0  jmp     loc_140ADE8B7
0x140ade6a5  cmp     cs:DbgkpWerInitialized, bl
0x140ade6ab  jnz     short loc_140ADE6CA
0x140ade6ad  lea     r8, aDbgkDbgkwercap_2; "DBGK: DbgkWerCaptureLiveKernelDump2: ca"...
0x140ade6b4  mov     edx, edi; Level
0x140ade6b6  mov     ecx, 5; ComponentId
0x140ade6bb  call    DbgPrintEx
0x140ade6c0  mov     eax, 0C00000A3h
0x140ade6c5  jmp     loc_140ADE8B7
0x140ade6ca  call    DbgkpWerIsFullLiveDumpDisabled
0x140ade6cf  test    al, al
0x140ade6d1  jz      short loc_140ADE6F0
0x140ade6d3  lea     r8, aDbgkFullLiveKe; "DBGK: Full Live Kernel Dumps are disabl"...
0x140ade6da  mov     edx, edi; Level
0x140ade6dc  mov     ecx, 5; ComponentId
0x140ade6e1  call    DbgPrintEx
0x140ade6e6  mov     eax, 0C0000804h
0x140ade6eb  jmp     loc_140ADE8B7
0x140ade6f0  mov     rbp, [rsp+78h+arg_30]
0x140ade6f8  test    rbp, rbp
0x140ade6fb  jnz     short loc_140ADE718
0x140ade6fd  lea     r8, aDbgkDbgkwercap_1; "DBGK: DbgkWerCaptureLiveKernelDump2: Ca"...
0x140ade704  mov     edx, edi; Level
0x140ade706  lea     ecx, [rbp+5]; ComponentId
0x140ade709  call    DbgPrintEx
0x140ade70e  mov     eax, 0C000000Dh
0x140ade713  jmp     loc_140ADE8B7
0x140ade718  call    KeEnterCriticalRegion
0x140ade71d  mov     eax, edi
0x140ade71f  xchg    eax, cs:DbgkpBusy
0x140ade725  cmp     eax, edi
0x140ade727  jnz     short loc_140ADE733
0x140ade729  mov     ebx, 0C000022Dh
0x140ade72e  jmp     loc_140ADE8B0
0x140ade733  mov     edx, 0B0h
0x140ade738  mov     r8d, 57676244h
0x140ade73e  lea     ecx, [rdx+50h]
0x140ade741  call    ExAllocatePool2
0x140ade746  xor     r9d, r9d
0x140ade749  mov     rsi, rax
0x140ade74c  test    rax, rax
0x140ade74f  jnz     short loc_140ADE75B
0x140ade751  mov     ebx, 0C000009Ah
0x140ade756  jmp     loc_140ADE8A7
0x140ade75b  test    r14, r14
0x140ade75e  jz      loc_140ADE88F
0x140ade764  mov     edx, 10h
0x140ade769  mov     rax, r14
0x140ade76c  mov     ecx, edx
0x140ade76e  cmp     [rax], r9w
0x140ade772  jz      short loc_140ADE77D
0x140ade774  add     rax, 2
0x140ade778  sub     rcx, rdi
0x140ade77b  jnz     short loc_140ADE76E
0x140ade77d  mov     rax, rcx
0x140ade780  neg     rax
0x140ade783  sbb     ebx, ebx
0x140ade785  not     ebx
0x140ade787  and     ebx, 0C000000Dh
0x140ade78d  test    rcx, rcx
0x140ade790  jz      loc_140ADE894
0x140ade796  mov     eax, 7FFFFFFEh
0x140ade79b  mov     r8, rsi
0x140ade79e  test    rax, rax
0x140ade7a1  jz      short loc_140ADE7C0
0x140ade7a3  movzx   ecx, word ptr [r14]
0x140ade7a7  test    cx, cx
0x140ade7aa  jz      short loc_140ADE7C0
0x140ade7ac  mov     [r8], cx
0x140ade7b0  add     r14, 2
0x140ade7b4  add     r8, 2
0x140ade7b8  sub     rax, rdi
0x140ade7bb  sub     rdx, rdi
0x140ade7be  jnz     short loc_140ADE79E
0x140ade7c0  mov     rax, rdx
0x140ade7c3  lea     rcx, [r8-2]
0x140ade7c7  neg     rax
0x140ade7ca  sbb     ebx, ebx
0x140ade7cc  not     ebx
0x140ade7ce  and     ebx, 80000005h
0x140ade7d4  test    rdx, rdx
0x140ade7d7  cmovnz  rcx, r8
0x140ade7db  mov     [rcx], r9w
0x140ade7df  jz      loc_140ADE888
0x140ade7e5  test    byte ptr [rbp+18h], 2
0x140ade7e9  mov     eax, cs:DbgkpWerDefaultPolicy
0x140ade7ef  cmovnz  eax, edi
0x140ade7f2  mov     [rsp+78h+var_54], eax
0x140ade7f6  mov     rax, [rsp+78h+arg_20]
0x140ade7fe  mov     ecx, [rsi+68h]
0x140ade801  mov     [rsi+38h], rax
0x140ade805  and     ecx, 0FFFFFFFDh
0x140ade808  mov     rax, [rsp+78h+arg_28]
0x140ade810  mov     [rsi+40h], rax
0x140ade814  mov     [rsi+20h], r13d
0x140ade818  mov     [rsi+28h], r12
0x140ade81c  mov     [rsi+30h], r15
0x140ade820  mov     [rsi+48h], rbp
0x140ade824  mov     eax, [rbp+18h]
0x140ade827  test    al, 8
0x140ade829  jnz     short loc_140ADE82E
0x140ade82b  or      ecx, 2
0x140ade82e  mov     [rsi+68h], ecx
0x140ade831  lea     r8, [rsp+78h+var_50]
0x140ade836  mov     rcx, rsi
0x140ade839  mov     [rsp+78h+var_50], r9
0x140ade83e  lea     rdx, [rsp+78h+var_54]
0x140ade843  call    cs:__imp_WerLiveKernelCreateReport
0x140ade84a  nop     dword ptr [rax+rax+00h]
0x140ade84f  mov     ebx, eax
0x140ade851  test    eax, eax
0x140ade853  jns     short loc_140ADE86B
0x140ade855  xor     edx, edx; Level
0x140ade857  lea     r8, aDbgkDbgkwercap_0; "DBGK: DbgkWerCaptureLiveKernelDump: Wer"...
0x140ade85e  mov     r9d, eax
0x140ade861  lea     ecx, [rdx+5]; ComponentId
0x140ade864  call    DbgPrintEx
0x140ade869  jmp     short loc_140ADE894
0x140ade86b  mov     r8, [rsp+78h+var_50]
0x140ade870  lea     r9, [rsp+78h+var_58]
0x140ade875  mov     edx, [rsp+78h+var_54]
0x140ade879  mov     rcx, rsi
0x140ade87c  call    DbgkpWerProcessPolicyResult
0x140ade881  mov     dil, [rsp+78h+var_58]
0x140ade886  mov     ebx, eax
0x140ade888  test    dil, dil
0x140ade88b  jnz     short loc_140ADE894
0x140ade88d  jmp     short loc_140ADE8B0
0x140ade88f  mov     ebx, 0C000000Dh
0x140ade894  mov     rcx, rsi
0x140ade897  call    DbgkpWerCleanupContext
0x140ade89c  mov     rcx, rsi
0x140ade89f  call    DbgkpWerFreePool
0x140ade8a4  xor     r9d, r9d
0x140ade8a7  mov     eax, r9d
0x140ade8aa  xchg    eax, cs:DbgkpBusy
0x140ade8b0  call    KeLeaveCriticalRegion
0x140ade8b5  mov     eax, ebx
0x140ade8b7  add     rsp, 38h
0x140ade8bb  pop     r15
0x140ade8bd  pop     r14
0x140ade8bf  pop     r13
0x140ade8c1  pop     r12
0x140ade8c3  pop     rdi
0x140ade8c4  pop     rsi
0x140ade8c5  pop     rbp
0x140ade8c6  pop     rbx
0x140ade8c7  retn
```
