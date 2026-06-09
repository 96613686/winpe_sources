# NbtCompleteLmhSvcRequest

- ea: `0x14005006c`
- end: `0x140050468`
- name: `NbtCompleteLmhSvcRequest`
- size: `1020`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64, char)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14001ba80`
- `0x14004d740`

## callees

- `0x140006900`
- `0x140007be8`
- `0x140007c4c`
- `0x140007df8`
- `0x140009e1c`
- `0x14000d594`
- `0x14000e268`
- `0x1400251c4`
- `0x140030f40`
- `0x140031140`
- `0x1400400a4`
- `0x140040294`
- `0x140041850`
- `0x14005006c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005020a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005020a`

## pseudocode

```c
void __fastcall NbtCompleteLmhSvcRequest(_QWORD *P, unsigned int *a2, int a3, unsigned int a4, const void *a5, char a6)
{
  int v7; // ebp
  size_t v8; // r12
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // r14
  __int64 v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx
  char *v16; // xmm0_8
  char *v17; // rcx
  __int64 v18; // rbp
  int v19; // edx
  int v20; // ecx
  int v21; // r9d
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // rax
  __int64 DeviceFromInterface; // rbx
  unsigned int v26; // ebp
  int v27; // [rsp+20h] [rbp-118h]
  int v28; // [rsp+28h] [rbp-110h]
  __int64 v29; // [rsp+50h] [rbp-E8h]
  __m128i v32; // [rsp+70h] [rbp-C8h]
  _DWORD v33[28]; // [rsp+80h] [rbp-B8h] BYREF

  v7 = 17;
  v8 = a4;
  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_(1049, 33, WPP_e595452688c43ce128ab41f39d85d938_Traceguids);
  v9 = P[3];
  v10 = P[2];
  v11 = *(_QWORD *)(v9 + 32);
  v29 = P[4];
  if ( v10 )
  {
    SetNameState(*(PVOID *)(v10 + 48));
    *(_QWORD *)(v10 + 48) = 0;
  }
  NbtCancelCancelRoutine(*(_QWORD *)(v9 + 24));
  v13 = -1073741634;
  *(_QWORD *)(v9 + 88) = 0;
  if ( a3 == 1 && !v10 )
    v7 = *(_DWORD *)(v9 + 224);
  if ( !a6 )
  {
    if ( v7 == 22 )
    {
      v24 = *(_QWORD *)(v9 + 96);
      v18 = v29;
      if ( v24 )
        *(_DWORD *)(v24 + 260) |= 1u;
      goto LABEL_23;
    }
    goto LABEL_22;
  }
  if ( !v11 || *(_DWORD *)(v11 + 360) != 1131832644 )
    goto LABEL_22;
  if ( !a3 )
    goto LABEL_42;
  if ( a3 != 1 )
  {
LABEL_22:
    v18 = v29;
LABEL_23:
    if ( v10 )
      NbtDereferenceTracker(v10, 0, 2804, "minio\\netbt\\sys\\parse.c");
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
      WPP_SF_d(1049, 36, WPP_e595452688c43ce128ab41f39d85d938_Traceguids, v13);
    CompleteClientReq(v18, v9, v13);
    goto LABEL_28;
  }
  if ( a5 )
  {
    v14 = *(_QWORD *)(v9 + 320);
    if ( v14 )
    {
      if ( (unsigned int)(*(_DWORD *)(v14 + 2) - 1) <= 1 )
      {
        v15 = *(_QWORD *)(v14 + 22);
        v32 = *(__m128i *)(v14 + 22);
        v16 = (char *)_mm_srli_si128(v32, 8).m128i_u64[0];
        v17 = (char *)(v15 - *(_QWORD *)(v9 + 328));
        if ( !v17 )
          v17 = &v16[-*(_QWORD *)(v9 + 336)];
        if ( !v17 )
        {
          if ( (unsigned int)v8 >= (int)v8 + 2 || v8 + 2 > WORD1(v15) )
          {
            v13 = -1073741789;
            goto LABEL_22;
          }
          memmove(v16, a5, v8);
          v32.m128i_i16[0] = v8;
          *(_WORD *)&v16[2 * (v8 >> 1)] = 0;
          *(_DWORD *)(*(_QWORD *)(v9 + 320) + 2LL) = 3;
          *(__m128i *)(*(_QWORD *)(v9 + 320) + 22LL) = v32;
          if ( (xmmword_140038420 & 0x40) != 0 )
          {
            v28 = (int)a5;
            WPP_SF_dsS(v20, v19, v12, v21);
          }
        }
      }
    }
  }
  if ( v7 != 17 || *(_DWORD *)(v11 + 340) == 1 )
  {
LABEL_42:
    LOBYTE(v12) = 1;
    DeviceFromInterface = GetDeviceFromInterface(_byteswap_ulong(*a2), v11, v12);
    v26 = LockAndAddToHashTable((_DWORD)qword_140039468, *(_QWORD *)(v9 + 40), (_DWORD)Str2, *a2, v27, v28);
    if ( DeviceFromInterface )
      NBT_DEREFERENCE_DEVICE(DeviceFromInterface, 10);
    v13 = 0;
    if ( v26 != 259 )
      v13 = v26;
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
      WPP_SF_d(1049, 35, WPP_e595452688c43ce128ab41f39d85d938_Traceguids, v13);
    goto LABEL_22;
  }
  v22 = 0;
  do
  {
    v23 = a2[v22];
    v33[v22] = v23;
    if ( !v23 )
      break;
    v22 = (unsigned int)(v22 + 1);
  }
  while ( (int)v22 < 26 );
  v18 = v29;
  *(_DWORD *)(v9 + 240) |= 0x80u;
  *(_QWORD *)(v9 + 160) = v29;
  v33[26] = 0;
  v13 = NbtSendNodeStatus(v11, 0, (unsigned int)v33, v9, (__int64)ExtractServerNameCompletion);
  if ( (v13 & 0x80000000) != 0 )
    goto LABEL_23;
  if ( v10 )
    NbtDereferenceTracker(v10, 0, 2733, "minio\\netbt\\sys\\parse.c");
LABEL_28:
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14005006c  mov     [rsp+arg_10], rbx
0x140050071  push    rbp
0x140050072  push    rsi
0x140050073  push    rdi
0x140050074  push    r12
0x140050076  push    r13
0x140050078  push    r14
0x14005007a  push    r15
0x14005007c  sub     rsp, 100h
0x140050083  mov     rax, cs:__security_cookie
0x14005008a  xor     rax, rsp
0x14005008d  mov     [rsp+138h+var_48], rax
0x140050095  mov     rax, [rsp+138h+arg_20]
0x14005009d  mov     r13, rcx
0x1400500a0  mov     [rsp+138h+Src], rax
0x1400500a5  mov     ebp, 11h
0x1400500aa  mov     r12d, r9d
0x1400500ad  mov     [rsp+138h+var_E0], r8d
0x1400500b2  mov     [rsp+138h+var_D8], rdx
0x1400500b7  test    byte ptr cs:xmmword_140038420+3, 2
0x1400500be  jnz     loc_14005032F
0x1400500c4  mov     rdi, [r13+18h]
0x1400500c8  mov     rsi, [r13+10h]
0x1400500cc  mov     rax, [r13+20h]
0x1400500d0  mov     r15b, [rsp+138h+arg_28]
0x1400500d8  mov     r14, [rdi+20h]
0x1400500dc  mov     [rsp+138h+var_E8], rax
0x1400500e1  test    rsi, rsi
0x1400500e4  jz      short loc_1400500FA
0x1400500e6  mov     rcx, [rsi+30h]; P
0x1400500ea  mov     r8b, r15b
0x1400500ed  call    SetNameState
0x1400500f2  mov     qword ptr [rsi+30h], 0
0x1400500fa  mov     rcx, [rdi+18h]
0x1400500fe  call    NbtCancelCancelRoutine
0x140050103  mov     ecx, [rsp+138h+var_E0]
0x140050107  mov     ebx, 0C00000BEh
0x14005010c  mov     qword ptr [rdi+58h], 0
0x140050114  cmp     ecx, 1
0x140050117  jnz     short loc_140050122
0x140050119  test    rsi, rsi
0x14005011c  jz      loc_14005034F
0x140050122  test    r15b, r15b
0x140050125  jz      loc_14005035A
0x14005012b  test    r14, r14
0x14005012e  jz      loc_1400501DC
0x140050134  cmp     dword ptr [r14+168h], 43766544h
0x14005013f  jnz     loc_1400501DC
0x140050145  test    ecx, ecx
0x140050147  jz      loc_140050395
0x14005014d  cmp     ecx, 1
0x140050150  jnz     loc_1400501DC
0x140050156  mov     r9, [rsp+138h+Src]
0x14005015b  test    r9, r9
0x14005015e  jz      loc_14005028C
0x140050164  mov     rcx, [rdi+140h]
0x14005016b  test    rcx, rcx
0x14005016e  jz      loc_14005028C
0x140050174  mov     eax, [rcx+2]
0x140050177  dec     eax
0x140050179  cmp     eax, 1
0x14005017c  ja      loc_14005028C
0x140050182  movups  xmm0, xmmword ptr [rcx+16h]
0x140050186  movq    rdx, xmm0
0x14005018b  mov     rcx, rdx
0x14005018e  movups  [rsp+138h+var_C8], xmm0
0x140050193  psrldq  xmm0, 8
0x140050198  movq    r15, xmm0
0x14005019d  sub     rcx, [rdi+148h]
0x1400501a4  jnz     short loc_1400501B0
0x1400501a6  mov     rcx, r15
0x1400501a9  sub     rcx, [rdi+150h]
0x1400501b0  test    rcx, rcx
0x1400501b3  jnz     loc_14005028C
0x1400501b9  lea     eax, [r12+2]
0x1400501be  cmp     r12d, eax
0x1400501c1  ja      short loc_1400501D7
0x1400501c3  shr     rdx, 10h
0x1400501c7  lea     rax, [r12+2]
0x1400501cc  movzx   ecx, dx
0x1400501cf  mov     rbx, r12
0x1400501d2  cmp     rax, rcx
0x1400501d5  jbe     short loc_140050242
0x1400501d7  mov     ebx, 0C0000023h
0x1400501dc  mov     rbp, [rsp+138h+var_E8]
0x1400501e1  test    rsi, rsi
0x1400501e4  jnz     loc_14005042E
0x1400501ea  test    byte ptr cs:xmmword_140038420+3, 2
0x1400501f1  jnz     loc_14005044A
0x1400501f7  mov     r8d, ebx
0x1400501fa  mov     rdx, rdi
0x1400501fd  mov     rcx, rbp
0x140050200  call    CompleteClientReq
0x140050205  xor     edx, edx; Tag
0x140050207  mov     rcx, r13; P
0x14005020a  call    cs:__imp_ExFreePoolWithTag
0x140050211  nop     dword ptr [rax+rax+00h]
0x140050216  mov     rcx, [rsp+138h+var_48]
0x14005021e  xor     rcx, rsp; StackCookie
0x140050221  call    __security_check_cookie
0x140050226  mov     rbx, [rsp+138h+arg_10]
0x14005022e  add     rsp, 100h
0x140050235  pop     r15
0x140050237  pop     r14
0x140050239  pop     r13
0x14005023b  pop     r12
0x14005023d  pop     rdi
0x14005023e  pop     rsi
0x14005023f  pop     rbp
0x140050240  retn
0x140050242  mov     r8, rbx; Size
0x140050245  mov     rdx, r9; Src
0x140050248  mov     rcx, r15; void *
0x14005024b  call    memmove
0x140050250  shr     rbx, 1
0x140050253  xor     eax, eax
0x140050255  mov     word ptr [rsp+138h+var_C8], r12w
0x14005025b  movups  xmm0, [rsp+138h+var_C8]
0x140050260  mov     [r15+rbx*2], ax
0x140050265  mov     rax, [rdi+140h]
0x14005026c  mov     dword ptr [rax+2], 3
0x140050273  mov     rax, [rdi+140h]
0x14005027a  movdqu  xmmword ptr [rax+16h], xmm0
0x14005027f  test    byte ptr cs:xmmword_140038420, 40h
0x140050286  jnz     loc_140050381
0x14005028c  cmp     ebp, 11h
0x14005028f  jnz     loc_140050395
0x140050295  cmp     dword ptr [r14+154h], 1
0x14005029d  jz      loc_140050395
0x1400502a3  mov     r15, [rsp+138h+var_D8]
0x1400502a8  xor     edx, edx
0x1400502aa  mov     eax, [r15+rdx*4]
0x1400502ae  mov     [rsp+rdx*4+138h+var_B8], eax
0x1400502b5  test    eax, eax
0x1400502b7  jz      short loc_1400502C0
0x1400502b9  inc     edx
0x1400502bb  cmp     edx, 1Ah
0x1400502be  jl      short loc_1400502AA
0x1400502c0  mov     rbp, [rsp+138h+var_E8]
0x1400502c5  lea     rax, ExtractServerNameCompletion
0x1400502cc  bts     dword ptr [rdi+0F0h], 7
0x1400502d4  lea     r8, [rsp+138h+var_B8]
0x1400502dc  mov     r9, rdi
0x1400502df  mov     [rdi+0A0h], rbp
0x1400502e6  xor     edx, edx
0x1400502e8  mov     [rsp+138h+var_118], rax
0x1400502ed  mov     rcx, r14
0x1400502f0  mov     [rsp+138h+var_50], 0
0x1400502fb  call    NbtSendNodeStatus
0x140050300  mov     ebx, eax
0x140050302  test    eax, eax
0x140050304  js      loc_1400501E1
0x14005030a  test    rsi, rsi
0x14005030d  jz      loc_140050205
0x140050313  lea     r9, aMinioNetbtSysP; "minio\\netbt\\sys\\parse.c"
0x14005031a  xor     edx, edx
0x14005031c  mov     r8d, 0AADh
0x140050322  mov     rcx, rsi
0x140050325  call    NbtDereferenceTracker
0x14005032a  jmp     loc_140050205
0x14005032f  mov     edx, 21h ; '!'
0x140050334  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14005033b  mov     ecx, 419h
0x140050340  call    WPP_SF_
0x140050345  mov     rdx, [rsp+138h+var_D8]
0x14005034a  jmp     loc_1400500C4
0x14005034f  mov     ebp, [rdi+0E0h]
0x140050355  jmp     loc_140050122
0x14005035a  cmp     ebp, 16h
0x14005035d  jnz     loc_1400501DC
0x140050363  mov     rax, [rdi+60h]
0x140050367  mov     rbp, [rsp+138h+var_E8]
0x14005036c  test    rax, rax
0x14005036f  jz      loc_1400501E1
0x140050375  or      dword ptr [rax+104h], 1
0x14005037c  jmp     loc_1400501E1
0x140050381  mov     rax, [rsp+138h+Src]
0x140050386  mov     qword ptr [rsp+138h+var_110], rax
0x14005038b  call    WPP_SF_dsS
0x140050390  jmp     loc_14005028C
0x140050395  mov     r15, [rsp+138h+var_D8]
0x14005039a  mov     r8b, 1
0x14005039d  mov     rdx, r14
0x1400503a0  mov     ecx, [r15]
0x1400503a3  bswap   ecx
0x1400503a5  call    GetDeviceFromInterface
0x1400503aa  cmp     [rsp+138h+var_E0], 1
0x1400503af  mov     ecx, 8
0x1400503b4  mov     r9d, [r15]
0x1400503b7  mov     rbx, rax
0x1400503ba  mov     r8, cs:Str2
0x1400503c1  mov     rdx, [rdi+28h]
0x1400503c5  lea     eax, [rcx+28h]
0x1400503c8  cmovnz  cx, ax
0x1400503cc  mov     [rsp+138h+var_F8], cx
0x1400503d1  mov     rcx, cs:qword_140039468
0x1400503d8  mov     [rsp+138h+var_100], rbx
0x1400503dd  call    LockAndAddToHashTable
0x1400503e2  mov     ebp, eax
0x1400503e4  test    rbx, rbx
0x1400503e7  jz      short loc_1400503F8
0x1400503e9  xor     r8d, r8d
0x1400503ec  mov     rcx, rbx
0x1400503ef  lea     edx, [r8+0Ah]
0x1400503f3  call    NBT_DEREFERENCE_DEVICE
0x1400503f8  xor     ebx, ebx
0x1400503fa  cmp     ebp, 103h
0x140050400  cmovnz  ebx, ebp
0x140050403  test    byte ptr cs:xmmword_140038420+3, 2
0x14005040a  jz      loc_1400501DC
0x140050410  mov     edx, 23h ; '#'
0x140050415  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14005041c  mov     ecx, 419h
0x140050421  mov     r9d, ebx
0x140050424  call    WPP_SF_d
0x140050429  jmp     loc_1400501DC
0x14005042e  lea     r9, aMinioNetbtSysP; "minio\\netbt\\sys\\parse.c"
0x140050435  xor     edx, edx
0x140050437  mov     r8d, 0AF4h
0x14005043d  mov     rcx, rsi
0x140050440  call    NbtDereferenceTracker
0x140050445  jmp     loc_1400501EA
0x14005044a  mov     edx, 24h ; '$'
0x14005044f  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x140050456  mov     ecx, 419h
0x14005045b  mov     r9d, ebx
0x14005045e  call    WPP_SF_d
0x140050463  jmp     loc_1400501F7
```
