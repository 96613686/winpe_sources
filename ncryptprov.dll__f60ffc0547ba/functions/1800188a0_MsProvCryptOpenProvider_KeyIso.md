# MsProvCryptOpenProvider_KeyIso

- ea: `0x1800188a0`
- end: `0x180018c0f`
- name: `MsProvCryptOpenProvider_KeyIso`
- size: `879`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x1800188a0`
- `0x180018c18`
- `0x180018c60`
- `0x180018d14`
- `0x180019010`
- `0x180038970`
- `0x180063010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800189fb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800189fb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018a1c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018b36`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018a1c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018b36`
- `ntdll!RtlAllocateHeap` at `0x1800188d9`
- `ntdll!RtlAllocateHeap` at `0x1800188d9`

## string_xrefs

- `0x180018b56`: `onecore\ds\security\cryptoapi\ncrypt\storage\interface.c`
- `0x180018b96`: `onecore\ds\security\cryptoapi\ncrypt\storage\interface.c`
- `0x180018bc5`: `onecore\ds\security\cryptoapi\ncrypt\storage\interface.c`
- `0x180018bf5`: `onecore\ds\security\cryptoapi\ncrypt\storage\interface.c`

## pseudocode

```c
__int64 __fastcall MsProvCryptOpenProvider_KeyIso(_QWORD *a1, __int64 a2, unsigned int a3)
{
  char *Heap; // rax
  char *v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rdx
  char *v10; // rax
  __int64 *v11; // rcx
  __int128 v12; // xmm0
  int v13; // eax
  unsigned int v14; // r15d
  char *v15; // rax
  __int64 *v16; // rcx
  __int128 v17; // xmm0
  int v18; // r8d
  int v20; // eax
  int v21; // edx
  __int64 v22; // r9

  if ( a1 )
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x218u);
    v7 = Heap;
    if ( !Heap )
    {
      DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\interface.c", 727);
      return 2148073486LL;
    }
    memset_0(Heap + 4, 0, 0x214u);
    v8 = 2;
    *(_DWORD *)v7 = 1145324612;
    v9 = 2;
    v10 = v7 + 8;
    v11 = &LocalKeyStorageFunctionTable;
    do
    {
      v10 += 128;
      v12 = *(_OWORD *)v11;
      v11 += 16;
      *((_OWORD *)v10 - 8) = v12;
      *((_OWORD *)v10 - 7) = *((_OWORD *)v11 - 7);
      *((_OWORD *)v10 - 6) = *((_OWORD *)v11 - 6);
      *((_OWORD *)v10 - 5) = *((_OWORD *)v11 - 5);
      *((_OWORD *)v10 - 4) = *((_OWORD *)v11 - 4);
      *((_OWORD *)v10 - 3) = *((_OWORD *)v11 - 3);
      *((_OWORD *)v10 - 2) = *((_OWORD *)v11 - 2);
      *((_OWORD *)v10 - 1) = *((_OWORD *)v11 - 1);
      --v9;
    }
    while ( v9 );
    v13 = (*((__int64 (__fastcall **)(char *, __int64, _QWORD))v7 + 2))(v7 + 520, a2, a3);
    v14 = v13;
    if ( v13 < 0 )
    {
      v22 = 759;
    }
    else
    {
      v15 = v7 + 264;
      v16 = &IsolationClientFunctionTable;
      do
      {
        v15 += 128;
        v17 = *(_OWORD *)v16;
        v16 += 16;
        *((_OWORD *)v15 - 8) = v17;
        *((_OWORD *)v15 - 7) = *((_OWORD *)v16 - 7);
        *((_OWORD *)v15 - 6) = *((_OWORD *)v16 - 6);
        *((_OWORD *)v15 - 5) = *((_OWORD *)v16 - 5);
        *((_OWORD *)v15 - 4) = *((_OWORD *)v16 - 4);
        *((_OWORD *)v15 - 3) = *((_OWORD *)v16 - 3);
        *((_OWORD *)v15 - 2) = *((_OWORD *)v16 - 2);
        *((_OWORD *)v15 - 1) = *((_OWORD *)v16 - 1);
        --v8;
      }
      while ( v8 );
      RtlAcquireSRWLockExclusive(&qword_18007A5F0);
      if ( !dword_18007A5F8 )
      {
        v20 = KeyIsoServerBind();
        v14 = v20;
        if ( v20 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v21,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\interface.c",
              (unsigned int)"Status",
              v20,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\interface.c",
              20);
          RtlReleaseSRWLockExclusive(&qword_18007A5F0);
          goto LABEL_26;
        }
        dword_18007A5F8 = 1;
      }
      RtlReleaseSRWLockExclusive(&qword_18007A5F0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_a5b9c631da783ce152883bc4773a2313_Traceguids,
          (unsigned int)dword_18007A5F8);
      v13 = (*((__int64 (__fastcall **)(char *, __int64, _QWORD))v7 + 34))(v7 + 528, a2, a3);
      v14 = v13;
      if ( v13 >= 0 )
      {
        *a1 = v7;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_SDP(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v18, a2, a3, (char)v7);
        return 0;
      }
      v22 = 813;
    }
    DebugTraceError((unsigned int)v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\interface.c", v22);
LABEL_26:
    MsProvCryptFreeProvider(v7);
    return v14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\interface.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\interface.c",
      202);
  return 2148073511LL;
}

```

## disassembly

```asm
0x1800188a0  mov     [rsp+arg_10], rbx
0x1800188a5  push    rbp
0x1800188a6  push    rsi
0x1800188a7  push    r14
0x1800188a9  sub     rsp, 40h
0x1800188ad  mov     ebp, r8d
0x1800188b0  mov     r14, rdx
0x1800188b3  mov     rbx, rcx
0x1800188b6  test    rcx, rcx
0x1800188b9  jz      loc_180018A89
0x1800188bf  mov     rcx, gs:60h
0x1800188c8  xor     edx, edx; Flags
0x1800188ca  mov     r8d, 218h; Size
0x1800188d0  mov     [rsp+58h+arg_0], rdi
0x1800188d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800188d9  call    cs:__imp_RtlAllocateHeap
0x1800188e0  nop     dword ptr [rax+rax+00h]
0x1800188e5  mov     rdi, rax
0x1800188e8  test    rax, rax
0x1800188eb  jz      loc_180018BBF
0x1800188f1  lea     rcx, [rax+4]; void *
0x1800188f5  mov     [rsp+58h+arg_8], r15
0x1800188fa  xor     edx, edx; Val
0x1800188fc  mov     r8d, 214h; Size
0x180018902  call    memset_0
0x180018907  mov     esi, 2
0x18001890c  mov     dword ptr [rdi], 44444444h
0x180018912  mov     edx, esi
0x180018914  lea     rax, [rdi+8]
0x180018918  lea     rcx, LocalKeyStorageFunctionTable
0x18001891f  lea     rax, [rax+80h]
0x180018926  movups  xmm0, xmmword ptr [rcx]
0x180018929  lea     rcx, [rcx+80h]
0x180018930  movups  xmmword ptr [rax-80h], xmm0
0x180018934  movups  xmm1, xmmword ptr [rcx-70h]
0x180018938  movups  xmmword ptr [rax-70h], xmm1
0x18001893c  movups  xmm0, xmmword ptr [rcx-60h]
0x180018940  movups  xmmword ptr [rax-60h], xmm0
0x180018944  movups  xmm1, xmmword ptr [rcx-50h]
0x180018948  movups  xmmword ptr [rax-50h], xmm1
0x18001894c  movups  xmm0, xmmword ptr [rcx-40h]
0x180018950  movups  xmmword ptr [rax-40h], xmm0
0x180018954  movups  xmm1, xmmword ptr [rcx-30h]
0x180018958  movups  xmmword ptr [rax-30h], xmm1
0x18001895c  movups  xmm0, xmmword ptr [rcx-20h]
0x180018960  movups  xmmword ptr [rax-20h], xmm0
0x180018964  movups  xmm1, xmmword ptr [rcx-10h]
0x180018968  movups  xmmword ptr [rax-10h], xmm1
0x18001896c  sub     rdx, 1
0x180018970  jnz     short loc_18001891F
0x180018972  mov     rax, [rdi+10h]
0x180018976  lea     rcx, [rdi+208h]
0x18001897d  mov     r8d, ebp
0x180018980  mov     rdx, r14
0x180018983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018988  mov     r15d, eax
0x18001898b  test    eax, eax
0x18001898d  js      loc_180018BE7
0x180018993  lea     rax, [rdi+108h]
0x18001899a  lea     rcx, IsolationClientFunctionTable
0x1800189a1  lea     rax, [rax+80h]
0x1800189a8  movups  xmm0, xmmword ptr [rcx]
0x1800189ab  lea     rcx, [rcx+80h]
0x1800189b2  movups  xmmword ptr [rax-80h], xmm0
0x1800189b6  movups  xmm1, xmmword ptr [rcx-70h]
0x1800189ba  movups  xmmword ptr [rax-70h], xmm1
0x1800189be  movups  xmm0, xmmword ptr [rcx-60h]
0x1800189c2  movups  xmmword ptr [rax-60h], xmm0
0x1800189c6  movups  xmm1, xmmword ptr [rcx-50h]
0x1800189ca  movups  xmmword ptr [rax-50h], xmm1
0x1800189ce  movups  xmm0, xmmword ptr [rcx-40h]
0x1800189d2  movups  xmmword ptr [rax-40h], xmm0
0x1800189d6  movups  xmm1, xmmword ptr [rcx-30h]
0x1800189da  movups  xmmword ptr [rax-30h], xmm1
0x1800189de  movups  xmm0, xmmword ptr [rcx-20h]
0x1800189e2  movups  xmmword ptr [rax-20h], xmm0
0x1800189e6  movups  xmm1, xmmword ptr [rcx-10h]
0x1800189ea  movups  xmmword ptr [rax-10h], xmm1
0x1800189ee  sub     rsi, 1
0x1800189f2  jnz     short loc_1800189A1
0x1800189f4  lea     rcx, qword_18007A5F0
0x1800189fb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180018a02  nop     dword ptr [rax+rax+00h]
0x180018a07  mov     eax, cs:dword_18007A5F8
0x180018a0d  test    eax, eax
0x180018a0f  jz      loc_180018B0A
0x180018a15  lea     rcx, qword_18007A5F0
0x180018a1c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018a23  nop     dword ptr [rax+rax+00h]
0x180018a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a2f  lea     rsi, WPP_GLOBAL_Control
0x180018a36  cmp     rcx, rsi
0x180018a39  jnz     short loc_180018ABA
0x180018a3b  mov     rax, [rdi+110h]
0x180018a42  lea     rcx, [rdi+210h]
0x180018a49  mov     r8d, ebp
0x180018a4c  mov     rdx, r14
0x180018a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a54  mov     r15d, eax
0x180018a57  test    eax, eax
0x180018a59  js      loc_180018BEF
0x180018a5f  mov     [rbx], rdi
0x180018a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a69  cmp     rcx, rsi
0x180018a6c  jnz     short loc_180018AE5
0x180018a6e  xor     eax, eax
0x180018a70  mov     r15, [rsp+58h+arg_8]
0x180018a75  mov     rdi, [rsp+58h+arg_0]
0x180018a7a  mov     rbx, [rsp+58h+arg_10]
0x180018a7f  add     rsp, 40h
0x180018a83  pop     r14
0x180018a85  pop     rsi
0x180018a86  pop     rbp
0x180018a87  retn
0x180018a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a90  lea     rsi, WPP_GLOBAL_Control
0x180018a97  cmp     rcx, rsi
0x180018a9a  jz      short loc_180018AA6
0x180018a9c  test    byte ptr [rcx+1Ch], 1
0x180018aa0  jnz     loc_180018B52
0x180018aa6  mov     rbx, [rsp+58h+arg_10]
0x180018aab  mov     eax, 80090027h
0x180018ab0  add     rsp, 40h
0x180018ab4  pop     r14
0x180018ab6  pop     rsi
0x180018ab7  pop     rbp
0x180018ab8  retn
0x180018aba  test    byte ptr [rcx+1Ch], 20h
0x180018abe  jz      loc_180018A3B
0x180018ac4  mov     rcx, [rcx+10h]
0x180018ac8  lea     r8, WPP_a5b9c631da783ce152883bc4773a2313_Traceguids
0x180018acf  mov     r9d, cs:dword_18007A5F8
0x180018ad6  mov     edx, 0Dh
0x180018adb  call    WPP_SF_d
0x180018ae0  jmp     loc_180018A3B
0x180018ae5  test    byte ptr [rcx+1Ch], 20h
0x180018ae9  jz      short loc_180018A6E
0x180018aeb  mov     rcx, [rcx+10h]
0x180018aef  mov     edx, 0Eh
0x180018af4  mov     [rsp+58h+var_30], rdi
0x180018af9  mov     r9, r14
0x180018afc  mov     [rsp+58h+var_38], ebp
0x180018b00  call    WPP_SF_SDP
0x180018b05  jmp     loc_180018A6E
0x180018b0a  call    KeyIsoServerBind
0x180018b0f  mov     r15d, eax
0x180018b12  test    eax, eax
0x180018b14  jns     short loc_180018B83
0x180018b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b1d  lea     rsi, WPP_GLOBAL_Control
0x180018b24  cmp     rcx, rsi
0x180018b27  jz      short loc_180018B2F
0x180018b29  test    byte ptr [rcx+1Ch], 1
0x180018b2d  jnz     short loc_180018B92
0x180018b2f  lea     rcx, qword_18007A5F0
0x180018b36  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018b3d  nop     dword ptr [rax+rax+00h]
0x180018b42  mov     rcx, rdi; P
0x180018b45  call    MsProvCryptFreeProvider
0x180018b4a  mov     eax, r15d
0x180018b4d  jmp     loc_180018A70
0x180018b52  mov     rcx, [rcx+10h]
0x180018b56  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180018b5d  mov     [rsp+58h+var_28], 2CAh
0x180018b65  lea     r9, aStatus; "Status"
0x180018b6c  mov     [rsp+58h+var_30], r8
0x180018b71  mov     [rsp+58h+var_38], 80090027h
0x180018b79  call    WPP_SF_sDsd
0x180018b7e  jmp     loc_180018AA6
0x180018b83  mov     cs:dword_18007A5F8, 1
0x180018b8d  jmp     loc_180018A15
0x180018b92  mov     rcx, [rcx+10h]
0x180018b96  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180018b9d  mov     [rsp+58h+var_28], 314h
0x180018ba5  lea     r9, aStatus; "Status"
0x180018bac  mov     [rsp+58h+var_30], r8
0x180018bb1  mov     [rsp+58h+var_38], eax
0x180018bb5  call    WPP_SF_sDsd
0x180018bba  jmp     loc_180018B2F
0x180018bbf  mov     r9d, 2D7h
0x180018bc5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180018bcc  lea     rdx, aStatus; "Status"
0x180018bd3  mov     ecx, 8009000Eh
0x180018bd8  call    DebugTraceError
0x180018bdd  mov     eax, 8009000Eh
0x180018be2  jmp     loc_180018A75
0x180018be7  mov     r9d, 2F7h
0x180018bed  jmp     short loc_180018BF5
0x180018bef  mov     r9d, 32Dh
0x180018bf5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180018bfc  mov     ecx, eax
0x180018bfe  lea     rdx, aStatus; "Status"
0x180018c05  call    DebugTraceError
0x180018c0a  jmp     loc_180018B42
```
