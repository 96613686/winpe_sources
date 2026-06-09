# HalpInterruptSetLineState

- ea: `0x14024512c`
- end: `0x14024555b`
- name: `HalpInterruptSetLineState`
- size: `1071`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1402440e0`
- `0x1402458ec`
- `0x140245a60`
- `0x1404db654`
- `0x140587890`

## callees

- `0x140240338`
- `0x140241944`
- `0x1402419d0`
- `0x140241c1c`
- `0x14024512c`
- `0x1402457b4`
- `0x140245868`
- `0x140245a30`
- `0x140245e6c`
- `0x1402551d4`
- `0x14053a530`

## string_xrefs

- `0x14024539b`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1402454b6`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x140245511`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x1407052b3`: `minkernel\hals\lib\interrupts\common\connect.c`

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
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // edi
  signed int v16; // ebx
  ULONG_PTR v17; // rax
  __int64 v18; // rcx
  ULONG_PTR v19; // rsi
  __int64 v20; // rax
  __int64 **v21; // rax
  __int64 *i; // rdi
  signed int v23; // ecx
  unsigned int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // r12
  __int128 v27; // xmm10
  __int64 v28; // r13
  ULONG_PTR v29; // rbx
  __int128 v30; // xmm6
  __int128 v31; // xmm7
  __int128 v32; // xmm8
  __int64 v33; // xmm9_8
  _DWORD *v34; // r15
  int v35; // r8d
  unsigned int v37; // esi
  _DWORD *LinesForGsiRange; // rax
  int v39; // edx
  int v40; // ecx
  int v41; // r8d
  int BestRouting; // eax
  unsigned int v43; // r9d
  int Priority; // eax
  char v45; // cl
  unsigned __int8 v46; // r9
  unsigned __int64 v47; // rax
  __int64 v48; // rax
  ULONG_PTR BugCheckParameter4; // r11
  signed __int32 v50[6]; // [rsp+8h] [rbp-81h] BYREF
  __int128 v51; // [rsp+30h] [rbp-59h]
  unsigned __int64 v52; // [rsp+D8h] [rbp+4Fh] BYREF
  unsigned int v53; // [rsp+E0h] [rbp+57h]
  char v54; // [rsp+E8h] [rbp+5Fh]
  int v55; // [rsp+F0h] [rbp+67h]

  v55 = a4;
  v54 = a3;
  v53 = a2;
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
  v52 = *a1;
  LOBYTE(a5) = v8;
  v10 = HalpAcquireHighLevelLock(&HalpInterruptOverridesLock);
  v11 = HalpInterruptOverrides;
  LOBYTE(v12) = v10;
  v13 = HIDWORD(v52);
  v14 = (unsigned int)v52;
  while ( (__int64 *)v11 != &HalpInterruptOverrides )
  {
    if ( *(_QWORD *)(v11 + 16) == v52 )
    {
      v9 = 1;
      v52 = *(_QWORD *)(v11 + 24);
      v7 = *(_DWORD *)(v11 + 36);
      v55 = *(_DWORD *)(v11 + 32);
      break;
    }
    v11 = *(_QWORD *)v11;
  }
  LOBYTE(v13) = v10;
  HalpReleaseHighLevelLock(&HalpInterruptOverridesLock, v13, v14, v12);
  if ( v9 || *(_DWORD *)(HalpInterruptController + 240) != 2 )
    goto LABEL_41;
  v15 = v52;
  v16 = HIDWORD(v52);
  if ( (unsigned int)(v52 - 45056) <= 1 )
  {
    v37 = HIDWORD(v52);
    if ( (_DWORD)v52 == 45057 )
      v37 = HIDWORD(v52) + 8;
    LinesForGsiRange = (_DWORD *)HalpInterruptFindLinesForGsiRange(v37, v37 + 1);
    if ( LinesForGsiRange )
    {
      v16 = v37 + LinesForGsiRange[5] - LinesForGsiRange[7];
      v15 = LinesForGsiRange[4];
      v52 = __PAIR64__(v16, v15);
    }
  }
  while ( 1 )
  {
    v17 = HalpInterruptLookupController(v15);
    v19 = v17;
    if ( !v17 )
    {
      LODWORD(v51) = 2220;
      v39 = 17;
      v40 = 0;
      goto LABEL_35;
    }
    if ( (*(_DWORD *)(v17 + 248) & 2) != 0 )
      KeBugCheckEx(0x5Cu, 0x200u, HalpInterruptLastProblem, v17, 0x7931847u);
    v20 = HalpInterruptLookupController(v18);
    if ( !v20 )
    {
LABEL_34:
      LODWORD(v51) = 2244;
      v39 = 18;
      v40 = v19;
LABEL_35:
      HalpInterruptSetProblemEx(v40, v39, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", v51);
      return (unsigned int)-1073741275;
    }
    v21 = (__int64 **)(v20 + 264);
    for ( i = *v21; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)v21 )
        goto LABEL_34;
      v23 = *((_DWORD *)i + 5);
      if ( v23 <= v16 && *((_DWORD *)i + 6) > v16 )
        break;
    }
    if ( !i )
      goto LABEL_34;
    v24 = v16 - v23;
    v25 = i[6];
    v26 = 2LL * v24;
    if ( *(_BYTE *)(v25 + 16LL * v24) )
      break;
    v27 = *(_OWORD *)(v25 + 16LL * v24);
    v28 = 56LL * v24;
    v29 = v28 + i[5];
    v30 = *(_OWORD *)v29;
    v31 = *(_OWORD *)(v29 + 16);
    v32 = *(_OWORD *)(v29 + 32);
    v33 = *(_QWORD *)(v29 + 48);
    if ( *(_BYTE *)(v25 + 8 * v26 + 12) )
    {
      if ( !HalpHvPresent
        && (*(_DWORD *)(v29 + 48) != v53
         || *(_DWORD *)(v29 + 8) != v55
         || *(_DWORD *)v29 != v7
         || *(_BYTE *)(v29 + 4) != v8) )
      {
        HalpInterruptSetProblemEx(v19, 32, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2299);
        KeBugCheckEx(0x5Cu, 0x202u, v29, *(unsigned int *)(v29 + 48), BugCheckParameter4);
      }
      *(_DWORD *)(v29 + 12) |= 0x10u;
      v34 = (_DWORD *)(v29 + 16);
    }
    else
    {
      v41 = HalpInterruptDestinationToTarget(v25, a6, v29 + 24);
      if ( v41 < 0 )
      {
        HalpInterruptSetProblemEx(
          v19,
          22,
          v41,
          -1,
          (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c",
          2334);
LABEL_50:
        v48 = i[5];
        *(_OWORD *)(v48 + v28) = v30;
        *(_OWORD *)(v48 + v28 + 16) = v31;
        *(_OWORD *)(v48 + v28 + 32) = v32;
        *(_QWORD *)(v48 + v28 + 48) = v33;
        *(_OWORD *)(i[6] + 8 * v26) = v27;
        return (unsigned int)v35;
      }
      v34 = (_DWORD *)(v29 + 16);
      BestRouting = HalpInterruptFindBestRouting(&v52, *(_QWORD *)a7, v29 + 16);
      v35 = BestRouting;
      if ( BestRouting < 0 )
        goto LABEL_50;
      v43 = v53;
      *(_BYTE *)(v29 + 4) = a5;
      *(_DWORD *)(v29 + 8) = v55;
      *(_DWORD *)v29 = v7;
      *(_DWORD *)(v29 + 12) = 16;
      *(_DWORD *)(v29 + 48) = v43;
      Priority = HalpInterruptGetPriority(v19, v43, (unsigned int)BestRouting);
      v45 = v54;
      *(_DWORD *)(v29 + 52) = Priority;
      *((_BYTE *)&HalpHwToSwIrqlMap + ((unsigned __int64)v46 >> 4)) = v45;
    }
    _InterlockedOr(v50, 0);
    v35 = HalpInterruptSetLineStateInternal(v19, &v52, v29);
    if ( v35 < 0 )
      goto LABEL_50;
    if ( *(_DWORD *)(v29 + 20) == *(_DWORD *)(a7 + 4) && *v34 == *(_DWORD *)a7 )
      return 0;
    v47 = *(_QWORD *)v34;
    v8 = a5;
    v52 = v47;
LABEL_41:
    v15 = v52;
    v16 = HIDWORD(v52);
  }
  HalpInterruptSetProblemEx(v19, 19, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2257);
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14024512c  mov     rax, rsp
0x14024512f  mov     [rax+20h], r9d
0x140245133  mov     [rax+18h], r8b
0x140245137  mov     [rax+10h], edx
0x14024513a  push    rbp
0x14024513b  push    rbx
0x14024513c  push    rsi
0x14024513d  push    rdi
0x14024513e  push    r12
0x140245140  push    r13
0x140245142  push    r14
0x140245144  push    r15
0x140245146  lea     rbp, [rax-47h]
0x14024514a  sub     rsp, 88h
0x140245151  mov     r14d, [rbp+3Fh+arg_20]
0x140245155  movaps  xmmword ptr [rax-58h], xmm6
0x140245159  movaps  xmmword ptr [rax-68h], xmm7
0x14024515d  movaps  xmmword ptr [rax-78h], xmm8
0x140245162  movaps  [rsp+0C0h+var_88+8], xmm9
0x140245168  movaps  [rsp+0C0h+var_98+8], xmm10
0x14024516e  cmp     r14d, 3
0x140245172  jz      loc_14024537D
0x140245178  cmp     r14d, 4
0x14024517c  jz      loc_140245476
0x140245182  xor     r15b, r15b
0x140245185  mov     rax, [rcx]
0x140245188  xor     bl, bl
0x14024518a  lea     rcx, HalpInterruptOverridesLock; SpinLock
0x140245191  mov     [rbp+3Fh+arg_0], rax
0x140245195  mov     byte ptr [rbp+3Fh+arg_20], r15b
0x140245199  call    HalpAcquireHighLevelLock
0x14024519e  mov     rcx, cs:HalpInterruptOverrides
0x1402451a5  mov     r9b, al
0x1402451a8  mov     edx, dword ptr [rbp+3Fh+arg_0+4]
0x1402451ab  mov     r8d, dword ptr [rbp+3Fh+arg_0]
0x1402451af  lea     rax, HalpInterruptOverrides
0x1402451b6  cmp     rcx, rax
0x1402451b9  jz      short loc_1402451DE
0x1402451bb  cmp     [rcx+10h], r8d
0x1402451bf  jz      loc_14024543E
0x1402451c5  mov     rcx, [rcx]
0x1402451c8  jmp     short loc_1402451AF
0x1402451ca  mov     rax, [rcx+18h]
0x1402451ce  mov     bl, 1
0x1402451d0  mov     [rbp+3Fh+arg_0], rax
0x1402451d4  mov     eax, [rcx+20h]
0x1402451d7  mov     r14d, [rcx+24h]
0x1402451db  mov     [rbp+3Fh+arg_18], eax
0x1402451de  mov     dl, r9b
0x1402451e1  lea     rcx, HalpInterruptOverridesLock
0x1402451e8  call    HalpReleaseHighLevelLock
0x1402451ed  test    bl, bl
0x1402451ef  jnz     loc_140245457
0x1402451f5  mov     rax, cs:HalpInterruptController
0x1402451fc  cmp     dword ptr [rax+0F0h], 2
0x140245203  jnz     loc_140245457
0x140245209  mov     edi, dword ptr [rbp+3Fh+arg_0]
0x14024520c  mov     ebx, dword ptr [rbp+3Fh+arg_0+4]
0x14024520f  lea     eax, [rdi-0B000h]
0x140245215  cmp     eax, 1
0x140245218  jbe     loc_140245347
0x14024521e  mov     ecx, edi
0x140245220  call    HalpInterruptLookupController
0x140245225  mov     rsi, rax
0x140245228  test    rax, rax
0x14024522b  jz      loc_140245462
0x140245231  mov     edx, [rax+0F8h]
0x140245237  test    dl, 2
0x14024523a  jnz     loc_140245538
0x140245240  call    HalpInterruptLookupController
0x140245245  test    rax, rax
0x140245248  jz      loc_14024538B
0x14024524e  add     rax, 108h
0x140245254  mov     rdi, [rax]
0x140245257  cmp     rdi, rax
0x14024525a  jz      loc_14024538B
0x140245260  mov     ecx, [rdi+14h]
0x140245263  cmp     ecx, ebx
0x140245265  jg      short loc_14024526C
0x140245267  cmp     [rdi+18h], ebx
0x14024526a  jg      short loc_140245271
0x14024526c  mov     rdi, [rdi]
0x14024526f  jmp     short loc_140245257
0x140245271  test    rdi, rdi
0x140245274  jz      loc_14024538B
0x14024527a  sub     ebx, ecx
0x14024527c  mov     rcx, [rdi+30h]
0x140245280  mov     r12d, ebx
0x140245283  add     r12, r12
0x140245286  mov     eax, ebx
0x140245288  cmp     byte ptr [rcx+r12*8], 0
0x14024528d  jnz     loc_140245506
0x140245293  mov     rbx, [rdi+28h]
0x140245297  movups  xmm10, xmmword ptr [rcx+r12*8]
0x14024529c  imul    r13, rax, 38h ; '8'
0x1402452a0  add     rbx, r13
0x1402452a3  cmp     byte ptr [rcx+r12*8+0Ch], 0
0x1402452a9  movups  xmm6, xmmword ptr [rbx]
0x1402452ac  movups  xmm7, xmmword ptr [rbx+10h]
0x1402452b0  movups  xmm8, xmmword ptr [rbx+20h]
0x1402452b5  movsd   xmm9, qword ptr [rbx+30h]
0x1402452bb  jz      loc_1402453BE
0x1402452c1  cmp     cs:HalpHvPresent, 0
0x1402452c8  jz      loc_140245484
0x1402452ce  or      dword ptr [rbx+0Ch], 10h
0x1402452d2  lea     r15, [rbx+10h]
0x1402452d6  lock or [rsp+0C0h+var_C0], 0
0x1402452db  mov     r8, rbx
0x1402452de  lea     rdx, [rbp+3Fh+arg_0]
0x1402452e2  mov     rcx, rsi
0x1402452e5  call    HalpInterruptSetLineStateInternal
0x1402452ea  mov     r8d, eax
0x1402452ed  test    eax, eax
0x1402452ef  js      loc_1402454DB
0x1402452f5  mov     rcx, [rbp+3Fh+arg_30]
0x1402452f9  mov     eax, [rcx+4]
0x1402452fc  cmp     [rbx+14h], eax
0x1402452ff  jnz     loc_14024544C
0x140245305  mov     eax, [rcx]
0x140245307  cmp     [r15], eax
0x14024530a  jnz     loc_14024544C
0x140245310  xor     r8d, r8d
0x140245313  movaps  xmm6, [rsp+0C0h+var_58+8]
0x140245318  mov     eax, r8d
0x14024531b  movaps  xmm7, [rsp+0C0h+var_68+8]
0x140245320  movaps  xmm8, [rsp+0C0h+var_78+8]
0x140245326  movaps  xmm9, [rsp+0C0h+var_88+8]
0x14024532c  movaps  xmm10, [rsp+0C0h+var_98+8]
0x140245332  add     rsp, 88h
0x140245339  pop     r15
0x14024533b  pop     r14
0x14024533d  pop     r13
0x14024533f  pop     r12
0x140245341  pop     rdi
0x140245342  pop     rsi
0x140245343  pop     rbx
0x140245344  pop     rbp
0x140245345  retn
0x140245347  mov     esi, ebx
0x140245349  cmp     edi, 0B001h
0x14024534f  jnz     short loc_140245354
0x140245351  add     esi, 8
0x140245354  lea     edx, [rsi+1]
0x140245357  mov     ecx, esi
0x140245359  call    HalpInterruptFindLinesForGsiRange
0x14024535e  test    rax, rax
0x140245361  jz      loc_14024521E
0x140245367  mov     ebx, [rax+14h]
0x14024536a  sub     ebx, [rax+1Ch]
0x14024536d  add     ebx, esi
0x14024536f  mov     dword ptr [rbp+3Fh+arg_0+4], ebx
0x140245372  mov     edi, [rax+10h]
0x140245375  mov     dword ptr [rbp+3Fh+arg_0], edi
0x140245378  jmp     loc_14024521E
0x14024537d  mov     r15b, 1
0x140245380  mov     r14d, 2
0x140245386  jmp     loc_140245185
0x14024538b  mov     dword ptr [rsp+0C0h+var_98], 8C4h
0x140245393  mov     edx, 12h
0x140245398  mov     rcx, rsi
0x14024539b  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1402453a2  or      r9d, 0FFFFFFFFh
0x1402453a6  xor     r8d, r8d
0x1402453a9  mov     [rsp+0C0h+BugCheckParameter4], rax
0x1402453ae  call    HalpInterruptSetProblemEx
0x1402453b3  mov     r8d, 0C0000225h
0x1402453b9  jmp     loc_140245313
0x1402453be  mov     rdx, [rbp+3Fh+arg_28]
0x1402453c2  lea     r8, [rbx+18h]
0x1402453c6  call    HalpInterruptDestinationToTarget
0x1402453cb  mov     r8d, eax
0x1402453ce  test    eax, eax
0x1402453d0  js      loc_1402454B6
0x1402453d6  mov     rdx, [rbp+3Fh+arg_30]
0x1402453da  lea     r15, [rbx+10h]
0x1402453de  mov     r8, r15
0x1402453e1  lea     rcx, [rbp+3Fh+arg_0]
0x1402453e5  mov     rdx, [rdx]
0x1402453e8  call    HalpInterruptFindBestRouting
0x1402453ed  mov     r8d, eax
0x1402453f0  test    eax, eax
0x1402453f2  js      loc_1402454DB
0x1402453f8  mov     al, byte ptr [rbp+3Fh+arg_20]
0x1402453fb  mov     rcx, rsi
0x1402453fe  mov     r9d, [rbp+3Fh+arg_8]
0x140245402  mov     [rbx+4], al
0x140245405  mov     edx, r9d
0x140245408  mov     eax, [rbp+3Fh+arg_18]
0x14024540b  mov     [rbx+8], eax
0x14024540e  mov     [rbx], r14d
0x140245411  mov     dword ptr [rbx+0Ch], 10h
0x140245418  mov     [rbx+30h], r9d
0x14024541c  call    HalpInterruptGetPriority
0x140245421  mov     cl, [rbp+3Fh+arg_10]
0x140245424  lea     rdx, HalpHwToSwIrqlMap
0x14024542b  mov     [rbx+34h], eax
0x14024542e  movzx   eax, r9b
0x140245432  shr     rax, 4
0x140245436  mov     [rax+rdx], cl
0x140245439  jmp     loc_1402452D6
0x14024543e  cmp     [rcx+14h], edx
0x140245441  jnz     loc_1402451C5
0x140245447  jmp     loc_1402451CA
0x14024544c  mov     rax, [r15]
0x14024544f  mov     r15b, byte ptr [rbp+3Fh+arg_20]
0x140245453  mov     [rbp+3Fh+arg_0], rax
0x140245457  mov     edi, dword ptr [rbp+3Fh+arg_0]
0x14024545a  mov     ebx, dword ptr [rbp+3Fh+arg_0+4]
0x14024545d  jmp     loc_14024521E
0x140245462  mov     dword ptr [rsp+0C0h+var_98], 8ACh
0x14024546a  mov     edx, 11h
0x14024546f  xor     ecx, ecx
0x140245471  jmp     loc_14024539B
0x140245476  mov     r15b, 1
0x140245479  mov     r14d, 1
0x14024547f  jmp     loc_140245185
0x140245484  mov     r11d, [rbp+3Fh+arg_8]
0x140245488  cmp     [rbx+30h], r11d
0x14024548c  jnz     loc_1407052A8
0x140245492  mov     eax, [rbp+3Fh+arg_18]
0x140245495  cmp     [rbx+8], eax
0x140245498  jnz     loc_1407052A8
0x14024549e  cmp     [rbx], r14d
0x1402454a1  jnz     loc_1407052A8
0x1402454a7  cmp     [rbx+4], r15b
0x1402454ab  jnz     loc_1407052A8
0x1402454b1  jmp     loc_1402452CE
0x1402454b6  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1402454bd  mov     dword ptr [rsp+0C0h+var_98], 91Eh
0x1402454c5  or      r9d, 0FFFFFFFFh
0x1402454c9  mov     [rsp+0C0h+BugCheckParameter4], rax
0x1402454ce  mov     edx, 16h
0x1402454d3  mov     rcx, rsi
0x1402454d6  call    HalpInterruptSetProblemEx
0x1402454db  mov     rax, [rdi+28h]
0x1402454df  movups  xmmword ptr [rax+r13], xmm6
0x1402454e4  movups  xmmword ptr [rax+r13+10h], xmm7
0x1402454ea  movups  xmmword ptr [rax+r13+20h], xmm8
0x1402454f0  movsd   qword ptr [rax+r13+30h], xmm9
0x1402454f7  mov     rax, [rdi+30h]
0x1402454fb  movdqu  xmmword ptr [rax+r12*8], xmm10
0x140245501  jmp     loc_140245313
0x140245506  xor     r8d, r8d
0x140245509  mov     dword ptr [rsp+0C0h+var_98], 8D1h
0x140245511  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140245518  or      r9d, 0FFFFFFFFh
0x14024551c  mov     rcx, rsi
0x14024551f  mov     [rsp+0C0h+BugCheckParameter4], rax
0x140245524  lea     edx, [r8+13h]
0x140245528  call    HalpInterruptSetProblemEx
0x14024552d  mov     r8d, 0C000000Dh
0x140245533  jmp     loc_140245313
0x140245538  movsxd  r8, cs:HalpInterruptLastProblem; BugCheckParameter2
0x14024553f  mov     r9, rsi; BugCheckParameter3
0x140245542  mov     edx, 200h; BugCheckParameter1
0x140245547  mov     [rsp+0C0h+BugCheckParameter4], 7931847h; BugCheckParameter4
0x140245550  mov     ecx, 5Ch ; '\'; BugCheckCode
0x140245555  call    KeBugCheckEx
0x1407052a8  xor     r8d, r8d
0x1407052ab  mov     dword ptr [rsp+0C0h+var_98], 8FBh
0x1407052b3  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x1407052ba  or      r9d, 0FFFFFFFFh
0x1407052be  mov     rcx, rsi
0x1407052c1  mov     [rsp+0C0h+BugCheckParameter4], rax
0x1407052c6  lea     edx, [r8+20h]
0x1407052ca  call    HalpInterruptSetProblemEx
0x1407052cf  mov     r9d, [rbx+30h]; BugCheckParameter3
0x1407052d3  mov     r8, rbx; BugCheckParameter2
0x1407052d6  mov     edx, 202h; BugCheckParameter1
0x1407052db  mov     [rsp+0C0h+BugCheckParameter4], r11; BugCheckParameter4
0x1407052e0  mov     ecx, 5Ch ; '\'; BugCheckCode
0x1407052e5  call    KeBugCheckEx
```
