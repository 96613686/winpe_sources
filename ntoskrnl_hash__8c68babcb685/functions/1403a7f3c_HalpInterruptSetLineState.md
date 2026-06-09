# HalpInterruptSetLineState

- ea: `0x1403a7f3c`
- end: `0x1403a836b`
- name: `HalpInterruptSetLineState`
- size: `1071`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1403a6ef0`
- `0x1403a86fc`
- `0x1403a8870`
- `0x1404ead9c`
- `0x14058ee00`

## callees

- `0x1403374a4`
- `0x140337544`
- `0x1403a2f60`
- `0x1403a4754`
- `0x1403a47e0`
- `0x1403a4a2c`
- `0x1403a7f3c`
- `0x1403a85c4`
- `0x1403a8678`
- `0x1403a8840`
- `0x140541bf0`

## string_xrefs

- `0x1403a81ab`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1403a82c6`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1403a8321`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x14071143b`: `minkernel\hals\lib\interrupts\common\connect.c`

## pseudocode

```c
__int64 __fastcall HalpInterruptSetLineState(
        unsigned __int64 *a1,
        unsigned int a2,
        char a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // r14d
  char v8; // r15
  char v9; // bl
  char v10; // al
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // edi
  signed int v14; // ebx
  ULONG_PTR v15; // rax
  __int64 v16; // rcx
  ULONG_PTR v17; // rsi
  __int64 v18; // rax
  __int64 **v19; // rax
  __int64 *i; // rdi
  signed int v21; // ecx
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // r12
  __int128 v25; // xmm10
  __int64 v26; // r13
  ULONG_PTR v27; // rbx
  __int128 v28; // xmm6
  __int128 v29; // xmm7
  __int128 v30; // xmm8
  __int64 v31; // xmm9_8
  _DWORD *v32; // r15
  int v33; // r8d
  unsigned int v35; // esi
  _DWORD *LinesForGsiRange; // rax
  int v37; // edx
  int v38; // ecx
  int v39; // r8d
  int BestRouting; // eax
  unsigned int v41; // r9d
  int Priority; // eax
  char v43; // cl
  unsigned __int8 v44; // r9
  unsigned __int64 v45; // rax
  __int64 v46; // rax
  ULONG_PTR BugCheckParameter4; // r11
  signed __int32 v48[6]; // [rsp+8h] [rbp-81h] BYREF
  __int128 v49; // [rsp+30h] [rbp-59h]
  unsigned __int64 v50; // [rsp+D8h] [rbp+4Fh] BYREF
  unsigned int v51; // [rsp+E0h] [rbp+57h]
  char v52; // [rsp+E8h] [rbp+5Fh]
  int v53; // [rsp+F0h] [rbp+67h]

  v53 = a4;
  v52 = a3;
  v51 = a2;
  v7 = a5;
  if ( a5 == 3 )
  {
    v8 = 1;
    v7 = 2;
  }
  else if ( a5 == 4 )
  {
    v8 = 1;
    v7 = 1;
  }
  else
  {
    v8 = 0;
  }
  v9 = 0;
  v50 = *a1;
  LOBYTE(a5) = v8;
  v10 = HalpAcquireHighLevelLock(&HalpInterruptOverridesLock);
  v11 = HalpInterruptOverrides;
  v12 = HIDWORD(v50);
  while ( (__int64 *)v11 != &HalpInterruptOverrides )
  {
    if ( *(_QWORD *)(v11 + 16) == v50 )
    {
      v9 = 1;
      v50 = *(_QWORD *)(v11 + 24);
      v7 = *(_DWORD *)(v11 + 36);
      v53 = *(_DWORD *)(v11 + 32);
      break;
    }
    v11 = *(_QWORD *)v11;
  }
  LOBYTE(v12) = v10;
  HalpReleaseHighLevelLock(&HalpInterruptOverridesLock, v12);
  if ( v9 || *(_DWORD *)(HalpInterruptController + 240) != 2 )
    goto LABEL_41;
  v13 = v50;
  v14 = HIDWORD(v50);
  if ( (unsigned int)(v50 - 45056) <= 1 )
  {
    v35 = HIDWORD(v50);
    if ( (_DWORD)v50 == 45057 )
      v35 = HIDWORD(v50) + 8;
    LinesForGsiRange = (_DWORD *)HalpInterruptFindLinesForGsiRange(v35, v35 + 1);
    if ( LinesForGsiRange )
    {
      v14 = v35 + LinesForGsiRange[5] - LinesForGsiRange[7];
      v13 = LinesForGsiRange[4];
      v50 = __PAIR64__(v14, v13);
    }
  }
  while ( 1 )
  {
    v15 = HalpInterruptLookupController(v13);
    v17 = v15;
    if ( !v15 )
    {
      LODWORD(v49) = 2220;
      v37 = 17;
      v38 = 0;
      goto LABEL_35;
    }
    if ( (*(_DWORD *)(v15 + 248) & 2) != 0 )
      KeBugCheckEx(0x5Cu, 0x200u, HalpInterruptLastProblem, v15, 0x7931847u);
    v18 = HalpInterruptLookupController(v16);
    if ( !v18 )
    {
LABEL_34:
      LODWORD(v49) = 2244;
      v37 = 18;
      v38 = v17;
LABEL_35:
      HalpInterruptSetProblemEx(v38, v37, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", v49);
      return (unsigned int)-1073741275;
    }
    v19 = (__int64 **)(v18 + 264);
    for ( i = *v19; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)v19 )
        goto LABEL_34;
      v21 = *((_DWORD *)i + 5);
      if ( v21 <= v14 && *((_DWORD *)i + 6) > v14 )
        break;
    }
    if ( !i )
      goto LABEL_34;
    v22 = v14 - v21;
    v23 = i[6];
    v24 = 2LL * v22;
    if ( *(_BYTE *)(v23 + 16LL * v22) )
      break;
    v25 = *(_OWORD *)(v23 + 16LL * v22);
    v26 = 56LL * v22;
    v27 = v26 + i[5];
    v28 = *(_OWORD *)v27;
    v29 = *(_OWORD *)(v27 + 16);
    v30 = *(_OWORD *)(v27 + 32);
    v31 = *(_QWORD *)(v27 + 48);
    if ( *(_BYTE *)(v23 + 8 * v24 + 12) )
    {
      if ( !HalpHvPresent
        && (*(_DWORD *)(v27 + 48) != v51
         || *(_DWORD *)(v27 + 8) != v53
         || *(_DWORD *)v27 != v7
         || *(_BYTE *)(v27 + 4) != v8) )
      {
        HalpInterruptSetProblemEx(v17, 32, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2299);
        KeBugCheckEx(0x5Cu, 0x202u, v27, *(unsigned int *)(v27 + 48), BugCheckParameter4);
      }
      *(_DWORD *)(v27 + 12) |= 0x10u;
      v32 = (_DWORD *)(v27 + 16);
    }
    else
    {
      v39 = HalpInterruptDestinationToTarget(v23, a6, v27 + 24);
      if ( v39 < 0 )
      {
        HalpInterruptSetProblemEx(
          v17,
          22,
          v39,
          -1,
          (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c",
          2334);
LABEL_50:
        v46 = i[5];
        *(_OWORD *)(v46 + v26) = v28;
        *(_OWORD *)(v46 + v26 + 16) = v29;
        *(_OWORD *)(v46 + v26 + 32) = v30;
        *(_QWORD *)(v46 + v26 + 48) = v31;
        *(_OWORD *)(i[6] + 8 * v24) = v25;
        return (unsigned int)v33;
      }
      v32 = (_DWORD *)(v27 + 16);
      BestRouting = HalpInterruptFindBestRouting(&v50, *(_QWORD *)a7, v27 + 16);
      v33 = BestRouting;
      if ( BestRouting < 0 )
        goto LABEL_50;
      v41 = v51;
      *(_BYTE *)(v27 + 4) = a5;
      *(_DWORD *)(v27 + 8) = v53;
      *(_DWORD *)v27 = v7;
      *(_DWORD *)(v27 + 12) = 16;
      *(_DWORD *)(v27 + 48) = v41;
      Priority = HalpInterruptGetPriority(v17, v41, (unsigned int)BestRouting);
      v43 = v52;
      *(_DWORD *)(v27 + 52) = Priority;
      *((_BYTE *)&HalpHwToSwIrqlMap + ((unsigned __int64)v44 >> 4)) = v43;
    }
    _InterlockedOr(v48, 0);
    v33 = HalpInterruptSetLineStateInternal(v17, &v50, v27);
    if ( v33 < 0 )
      goto LABEL_50;
    if ( *(_DWORD *)(v27 + 20) == *(_DWORD *)(a7 + 4) && *v32 == *(_DWORD *)a7 )
      return 0;
    v45 = *(_QWORD *)v32;
    v8 = a5;
    v50 = v45;
LABEL_41:
    v13 = v50;
    v14 = HIDWORD(v50);
  }
  HalpInterruptSetProblemEx(v17, 19, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2257);
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x1403a7f3c  mov     rax, rsp
0x1403a7f3f  mov     [rax+20h], r9d
0x1403a7f43  mov     [rax+18h], r8b
0x1403a7f47  mov     [rax+10h], edx
0x1403a7f4a  push    rbp
0x1403a7f4b  push    rbx
0x1403a7f4c  push    rsi
0x1403a7f4d  push    rdi
0x1403a7f4e  push    r12
0x1403a7f50  push    r13
0x1403a7f52  push    r14
0x1403a7f54  push    r15
0x1403a7f56  lea     rbp, [rax-47h]
0x1403a7f5a  sub     rsp, 88h
0x1403a7f61  mov     r14d, [rbp+3Fh+arg_20]
0x1403a7f65  movaps  xmmword ptr [rax-58h], xmm6
0x1403a7f69  movaps  xmmword ptr [rax-68h], xmm7
0x1403a7f6d  movaps  xmmword ptr [rax-78h], xmm8
0x1403a7f72  movaps  [rsp+0C0h+var_88+8], xmm9
0x1403a7f78  movaps  [rsp+0C0h+var_98+8], xmm10
0x1403a7f7e  cmp     r14d, 3
0x1403a7f82  jz      loc_1403A818D
0x1403a7f88  cmp     r14d, 4
0x1403a7f8c  jz      loc_1403A8286
0x1403a7f92  xor     r15b, r15b
0x1403a7f95  mov     rax, [rcx]
0x1403a7f98  xor     bl, bl
0x1403a7f9a  lea     rcx, HalpInterruptOverridesLock; SpinLock
0x1403a7fa1  mov     [rbp+3Fh+arg_0], rax
0x1403a7fa5  mov     byte ptr [rbp+3Fh+arg_20], r15b
0x1403a7fa9  call    HalpAcquireHighLevelLock
0x1403a7fae  mov     rcx, cs:HalpInterruptOverrides
0x1403a7fb5  mov     r9b, al
0x1403a7fb8  mov     edx, dword ptr [rbp+3Fh+arg_0+4]
0x1403a7fbb  mov     r8d, dword ptr [rbp+3Fh+arg_0]
0x1403a7fbf  lea     rax, HalpInterruptOverrides
0x1403a7fc6  cmp     rcx, rax
0x1403a7fc9  jz      short loc_1403A7FEE
0x1403a7fcb  cmp     [rcx+10h], r8d
0x1403a7fcf  jz      loc_1403A824E
0x1403a7fd5  mov     rcx, [rcx]
0x1403a7fd8  jmp     short loc_1403A7FBF
0x1403a7fda  mov     rax, [rcx+18h]
0x1403a7fde  mov     bl, 1
0x1403a7fe0  mov     [rbp+3Fh+arg_0], rax
0x1403a7fe4  mov     eax, [rcx+20h]
0x1403a7fe7  mov     r14d, [rcx+24h]
0x1403a7feb  mov     [rbp+3Fh+arg_18], eax
0x1403a7fee  mov     dl, r9b
0x1403a7ff1  lea     rcx, HalpInterruptOverridesLock
0x1403a7ff8  call    HalpReleaseHighLevelLock
0x1403a7ffd  test    bl, bl
0x1403a7fff  jnz     loc_1403A8267
0x1403a8005  mov     rax, cs:HalpInterruptController
0x1403a800c  cmp     dword ptr [rax+0F0h], 2
0x1403a8013  jnz     loc_1403A8267
0x1403a8019  mov     edi, dword ptr [rbp+3Fh+arg_0]
0x1403a801c  mov     ebx, dword ptr [rbp+3Fh+arg_0+4]
0x1403a801f  lea     eax, [rdi-0B000h]
0x1403a8025  cmp     eax, 1
0x1403a8028  jbe     loc_1403A8157
0x1403a802e  mov     ecx, edi
0x1403a8030  call    HalpInterruptLookupController
0x1403a8035  mov     rsi, rax
0x1403a8038  test    rax, rax
0x1403a803b  jz      loc_1403A8272
0x1403a8041  mov     edx, [rax+0F8h]
0x1403a8047  test    dl, 2
0x1403a804a  jnz     loc_1403A8348
0x1403a8050  call    HalpInterruptLookupController
0x1403a8055  test    rax, rax
0x1403a8058  jz      loc_1403A819B
0x1403a805e  add     rax, 108h
0x1403a8064  mov     rdi, [rax]
0x1403a8067  cmp     rdi, rax
0x1403a806a  jz      loc_1403A819B
0x1403a8070  mov     ecx, [rdi+14h]
0x1403a8073  cmp     ecx, ebx
0x1403a8075  jg      short loc_1403A807C
0x1403a8077  cmp     [rdi+18h], ebx
0x1403a807a  jg      short loc_1403A8081
0x1403a807c  mov     rdi, [rdi]
0x1403a807f  jmp     short loc_1403A8067
0x1403a8081  test    rdi, rdi
0x1403a8084  jz      loc_1403A819B
0x1403a808a  sub     ebx, ecx
0x1403a808c  mov     rcx, [rdi+30h]
0x1403a8090  mov     r12d, ebx
0x1403a8093  add     r12, r12
0x1403a8096  mov     eax, ebx
0x1403a8098  cmp     byte ptr [rcx+r12*8], 0
0x1403a809d  jnz     loc_1403A8316
0x1403a80a3  mov     rbx, [rdi+28h]
0x1403a80a7  movups  xmm10, xmmword ptr [rcx+r12*8]
0x1403a80ac  imul    r13, rax, 38h ; '8'
0x1403a80b0  add     rbx, r13
0x1403a80b3  cmp     byte ptr [rcx+r12*8+0Ch], 0
0x1403a80b9  movups  xmm6, xmmword ptr [rbx]
0x1403a80bc  movups  xmm7, xmmword ptr [rbx+10h]
0x1403a80c0  movups  xmm8, xmmword ptr [rbx+20h]
0x1403a80c5  movsd   xmm9, qword ptr [rbx+30h]
0x1403a80cb  jz      loc_1403A81CE
0x1403a80d1  cmp     cs:HalpHvPresent, 0
0x1403a80d8  jz      loc_1403A8294
0x1403a80de  or      dword ptr [rbx+0Ch], 10h
0x1403a80e2  lea     r15, [rbx+10h]
0x1403a80e6  lock or [rsp+0C0h+var_C0], 0
0x1403a80eb  mov     r8, rbx
0x1403a80ee  lea     rdx, [rbp+3Fh+arg_0]
0x1403a80f2  mov     rcx, rsi
0x1403a80f5  call    HalpInterruptSetLineStateInternal
0x1403a80fa  mov     r8d, eax
0x1403a80fd  test    eax, eax
0x1403a80ff  js      loc_1403A82EB
0x1403a8105  mov     rcx, [rbp+3Fh+arg_30]
0x1403a8109  mov     eax, [rcx+4]
0x1403a810c  cmp     [rbx+14h], eax
0x1403a810f  jnz     loc_1403A825C
0x1403a8115  mov     eax, [rcx]
0x1403a8117  cmp     [r15], eax
0x1403a811a  jnz     loc_1403A825C
0x1403a8120  xor     r8d, r8d
0x1403a8123  movaps  xmm6, [rsp+0C0h+var_58+8]
0x1403a8128  mov     eax, r8d
0x1403a812b  movaps  xmm7, [rsp+0C0h+var_68+8]
0x1403a8130  movaps  xmm8, [rsp+0C0h+var_78+8]
0x1403a8136  movaps  xmm9, [rsp+0C0h+var_88+8]
0x1403a813c  movaps  xmm10, [rsp+0C0h+var_98+8]
0x1403a8142  add     rsp, 88h
0x1403a8149  pop     r15
0x1403a814b  pop     r14
0x1403a814d  pop     r13
0x1403a814f  pop     r12
0x1403a8151  pop     rdi
0x1403a8152  pop     rsi
0x1403a8153  pop     rbx
0x1403a8154  pop     rbp
0x1403a8155  retn
0x1403a8157  mov     esi, ebx
0x1403a8159  cmp     edi, 0B001h
0x1403a815f  jnz     short loc_1403A8164
0x1403a8161  add     esi, 8
0x1403a8164  lea     edx, [rsi+1]
0x1403a8167  mov     ecx, esi
0x1403a8169  call    HalpInterruptFindLinesForGsiRange
0x1403a816e  test    rax, rax
0x1403a8171  jz      loc_1403A802E
0x1403a8177  mov     ebx, [rax+14h]
0x1403a817a  sub     ebx, [rax+1Ch]
0x1403a817d  add     ebx, esi
0x1403a817f  mov     dword ptr [rbp+3Fh+arg_0+4], ebx
0x1403a8182  mov     edi, [rax+10h]
0x1403a8185  mov     dword ptr [rbp+3Fh+arg_0], edi
0x1403a8188  jmp     loc_1403A802E
0x1403a818d  mov     r15b, 1
0x1403a8190  mov     r14d, 2
0x1403a8196  jmp     loc_1403A7F95
0x1403a819b  mov     dword ptr [rsp+0C0h+var_98], 8C4h
0x1403a81a3  mov     edx, 12h
0x1403a81a8  mov     rcx, rsi
0x1403a81ab  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a81b2  or      r9d, 0FFFFFFFFh
0x1403a81b6  xor     r8d, r8d
0x1403a81b9  mov     [rsp+0C0h+BugCheckParameter4], rax
0x1403a81be  call    HalpInterruptSetProblemEx
0x1403a81c3  mov     r8d, 0C0000225h
0x1403a81c9  jmp     loc_1403A8123
0x1403a81ce  mov     rdx, [rbp+3Fh+arg_28]
0x1403a81d2  lea     r8, [rbx+18h]
0x1403a81d6  call    HalpInterruptDestinationToTarget
0x1403a81db  mov     r8d, eax
0x1403a81de  test    eax, eax
0x1403a81e0  js      loc_1403A82C6
0x1403a81e6  mov     rdx, [rbp+3Fh+arg_30]
0x1403a81ea  lea     r15, [rbx+10h]
0x1403a81ee  mov     r8, r15
0x1403a81f1  lea     rcx, [rbp+3Fh+arg_0]
0x1403a81f5  mov     rdx, [rdx]
0x1403a81f8  call    HalpInterruptFindBestRouting
0x1403a81fd  mov     r8d, eax
0x1403a8200  test    eax, eax
0x1403a8202  js      loc_1403A82EB
0x1403a8208  mov     al, byte ptr [rbp+3Fh+arg_20]
0x1403a820b  mov     rcx, rsi
0x1403a820e  mov     r9d, [rbp+3Fh+arg_8]
0x1403a8212  mov     [rbx+4], al
0x1403a8215  mov     edx, r9d
0x1403a8218  mov     eax, [rbp+3Fh+arg_18]
0x1403a821b  mov     [rbx+8], eax
0x1403a821e  mov     [rbx], r14d
0x1403a8221  mov     dword ptr [rbx+0Ch], 10h
0x1403a8228  mov     [rbx+30h], r9d
0x1403a822c  call    HalpInterruptGetPriority
0x1403a8231  mov     cl, [rbp+3Fh+arg_10]
0x1403a8234  lea     rdx, HalpHwToSwIrqlMap
0x1403a823b  mov     [rbx+34h], eax
0x1403a823e  movzx   eax, r9b
0x1403a8242  shr     rax, 4
0x1403a8246  mov     [rax+rdx], cl
0x1403a8249  jmp     loc_1403A80E6
0x1403a824e  cmp     [rcx+14h], edx
0x1403a8251  jnz     loc_1403A7FD5
0x1403a8257  jmp     loc_1403A7FDA
0x1403a825c  mov     rax, [r15]
0x1403a825f  mov     r15b, byte ptr [rbp+3Fh+arg_20]
0x1403a8263  mov     [rbp+3Fh+arg_0], rax
0x1403a8267  mov     edi, dword ptr [rbp+3Fh+arg_0]
0x1403a826a  mov     ebx, dword ptr [rbp+3Fh+arg_0+4]
0x1403a826d  jmp     loc_1403A802E
0x1403a8272  mov     dword ptr [rsp+0C0h+var_98], 8ACh
0x1403a827a  mov     edx, 11h
0x1403a827f  xor     ecx, ecx
0x1403a8281  jmp     loc_1403A81AB
0x1403a8286  mov     r15b, 1
0x1403a8289  mov     r14d, 1
0x1403a828f  jmp     loc_1403A7F95
0x1403a8294  mov     r11d, [rbp+3Fh+arg_8]
0x1403a8298  cmp     [rbx+30h], r11d
0x1403a829c  jnz     loc_140711430
0x1403a82a2  mov     eax, [rbp+3Fh+arg_18]
0x1403a82a5  cmp     [rbx+8], eax
0x1403a82a8  jnz     loc_140711430
0x1403a82ae  cmp     [rbx], r14d
0x1403a82b1  jnz     loc_140711430
0x1403a82b7  cmp     [rbx+4], r15b
0x1403a82bb  jnz     loc_140711430
0x1403a82c1  jmp     loc_1403A80DE
0x1403a82c6  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a82cd  mov     dword ptr [rsp+0C0h+var_98], 91Eh
0x1403a82d5  or      r9d, 0FFFFFFFFh
0x1403a82d9  mov     [rsp+0C0h+BugCheckParameter4], rax
0x1403a82de  mov     edx, 16h
0x1403a82e3  mov     rcx, rsi
0x1403a82e6  call    HalpInterruptSetProblemEx
0x1403a82eb  mov     rax, [rdi+28h]
0x1403a82ef  movups  xmmword ptr [rax+r13], xmm6
0x1403a82f4  movups  xmmword ptr [rax+r13+10h], xmm7
0x1403a82fa  movups  xmmword ptr [rax+r13+20h], xmm8
0x1403a8300  movsd   qword ptr [rax+r13+30h], xmm9
0x1403a8307  mov     rax, [rdi+30h]
0x1403a830b  movdqu  xmmword ptr [rax+r12*8], xmm10
0x1403a8311  jmp     loc_1403A8123
0x1403a8316  xor     r8d, r8d
0x1403a8319  mov     dword ptr [rsp+0C0h+var_98], 8D1h
0x1403a8321  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1403a8328  or      r9d, 0FFFFFFFFh
0x1403a832c  mov     rcx, rsi
0x1403a832f  mov     [rsp+0C0h+BugCheckParameter4], rax
0x1403a8334  lea     edx, [r8+13h]
0x1403a8338  call    HalpInterruptSetProblemEx
0x1403a833d  mov     r8d, 0C000000Dh
0x1403a8343  jmp     loc_1403A8123
0x1403a8348  movsxd  r8, cs:HalpInterruptLastProblem; BugCheckParameter2
0x1403a834f  mov     r9, rsi; BugCheckParameter3
0x1403a8352  mov     edx, 200h; BugCheckParameter1
0x1403a8357  mov     [rsp+0C0h+BugCheckParameter4], 7931847h; BugCheckParameter4
0x1403a8360  mov     ecx, 5Ch ; '\'; BugCheckCode
0x1403a8365  call    KeBugCheckEx
0x140711430  xor     r8d, r8d
0x140711433  mov     dword ptr [rsp+0C0h+var_98], 8FBh
0x14071143b  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140711442  or      r9d, 0FFFFFFFFh
0x140711446  mov     rcx, rsi
0x140711449  mov     [rsp+0C0h+BugCheckParameter4], rax
0x14071144e  lea     edx, [r8+20h]
0x140711452  call    HalpInterruptSetProblemEx
0x140711457  mov     r9d, [rbx+30h]; BugCheckParameter3
0x14071145b  mov     r8, rbx; BugCheckParameter2
0x14071145e  mov     edx, 202h; BugCheckParameter1
0x140711463  mov     [rsp+0C0h+BugCheckParameter4], r11; BugCheckParameter4
0x140711468  mov     ecx, 5Ch ; '\'; BugCheckCode
0x14071146d  call    KeBugCheckEx
```
