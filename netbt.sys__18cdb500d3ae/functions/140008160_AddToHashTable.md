# AddToHashTable

- ea: `0x140008160`
- end: `0x140008838`
- name: `AddToHashTable`
- size: `1752`
- prototype: ``
- caller_count: `10`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140006e2c`
- `0x140015818`
- `0x140017214`
- `0x14001fc60`
- `0x1400251c4`
- `0x140025c84`
- `0x140028580`
- `0x1400288b8`
- `0x14002b9c8`
- `0x14002bb80`

## callees

- `0x140007ed8`
- `0x140008160`
- `0x1400089c8`
- `0x140009600`
- `0x14001e504`
- `0x140028144`
- `0x140031140`
- `0x140031440`
- `0x140040294`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400081b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400081b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008268`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400082b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008566`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008268`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400082b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008566`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008413`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400084d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008535`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000854f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008413`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400084d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008535`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000854f`
- `ntoskrnl!ExAllocatePool2` at `0x140008296`
- `ntoskrnl!ExAllocatePool2` at `0x1400084b9`
- `ntoskrnl!ExAllocatePool2` at `0x14000879b`
- `ntoskrnl!ExAllocatePool2` at `0x140008296`
- `ntoskrnl!ExAllocatePool2` at `0x1400084b9`
- `ntoskrnl!ExAllocatePool2` at `0x14000879b`

## pseudocode

```c
__int64 __fastcall AddToHashTable(
        _DWORD *a1,
        char *a2,
        _BYTE *a3,
        int a4,
        int a5,
        _DWORD *P,
        __int64 *a7,
        __int64 a8,
        __int16 a9)
{
  void *v10; // rbx
  int v14; // r13d
  __int64 Pool2; // rdi
  _DWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v19; // rbx
  unsigned int v20; // eax
  _BYTE *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  void *v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rax
  _QWORD *v27; // rcx
  void *v28; // rcx
  _DWORD *v29; // rax
  _QWORD *v30; // rcx
  int v31; // esi
  __int64 v32; // rbp
  char *v33; // rax
  char *v34; // rsi
  KIRQL NewIrql; // [rsp+40h] [rbp-68h]
  char v36; // [rsp+41h] [rbp-67h]
  __int64 v37; // [rsp+48h] [rbp-60h] BYREF
  __int64 v38[11]; // [rsp+50h] [rbp-58h] BYREF

  v10 = 0;
  v38[0] = 0;
  v37 = 0;
  if ( !(unsigned int)FindInHashTable(a1, a2, a3, &v37) )
  {
    v19 = v37;
    if ( *(_DWORD *)(v37 + 16) != -87097344 || (*(_DWORD *)(v37 + 72) & 0x20) != 0 )
    {
      v10 = 0;
      goto LABEL_2;
    }
    v31 = *(_DWORD *)(v37 + 32);
    *(_DWORD *)(v37 + 32) = a4;
    if ( (a9 & 0x400) == 0 )
    {
      if ( !P && _bittest16((const signed __int16 *)(v19 + 130), 9u) )
      {
LABEL_72:
        if ( a7 )
          *a7 = v19;
        return 259;
      }
      if ( (int)NbtUpdateRemoteName(a8, v19, (__int64)P, a9) < 0 )
        *(_DWORD *)(v19 + 32) = v31;
    }
    if ( P )
      NbtDereferenceName(P, (__int64)"minio\\netbt\\sys\\hashtbl.c");
    goto LABEL_72;
  }
LABEL_2:
  v36 = *a2;
  v14 = a2[1] & 0xF;
  LODWORD(v37) = *a1;
  Pool2 = (__int64)P;
  NewIrql = KeAcquireSpinLockRaiseToDpc(&Lock);
  if ( !P )
  {
    Pool2 = ExAllocatePool2(64, 184, 812933710);
    if ( Pool2 )
    {
      if ( a1[1] != 1
        || !word_1400395D0
        || (v10 = (void *)ExAllocatePool2(64, 16LL * (unsigned __int16)word_1400395D0, 858808910)) != 0 )
      {
        memset((void *)Pool2, 0, 0xB8u);
        *(_DWORD *)(Pool2 + 32) = a4;
        *(_DWORD *)(Pool2 + 72) = (a5 != 0 ? 4 : 2) | 0x10;
        *(_OWORD *)(Pool2 + 164) = *(_OWORD *)a2;
        if ( (a1[1] & 0xFFFFFFFD) != 0 )
        {
          *(_DWORD *)(Pool2 + 16) = -87097344;
          memset(v10, 0, 16LL * (unsigned __int16)word_1400395D0);
          *(_QWORD *)(Pool2 + 24) = v10;
          *(_WORD *)(Pool2 + 128) = word_1400395D0;
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              *(_DWORD *)(Pool2 + 20),
              12,
              (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
              Pool2,
              *(_DWORD *)(Pool2 + 20),
              *(_DWORD *)(Pool2 + 20) + 1,
              224,
              (__int64)"minio\\netbt\\sys\\hashtbl.c");
          _InterlockedIncrement((volatile signed __int32 *)(Pool2 + 20));
          NbtCheckNameAddrTimer(Pool2);
          if ( *(_DWORD *)(Pool2 + 16) == -87097344 && (unsigned int)++dword_140039760 > 0x100 )
            NbtScheduleRemoteTimeout();
          NbtUpdateRemoteName(a8, Pool2, 0, a9);
        }
        else
        {
          *(_DWORD *)(Pool2 + 16) = -559087616;
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              *(_DWORD *)(Pool2 + 20),
              12,
              (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
              Pool2,
              *(_DWORD *)(Pool2 + 20),
              *(_DWORD *)(Pool2 + 20) + 1,
              215,
              (__int64)"minio\\netbt\\sys\\hashtbl.c");
          _InterlockedIncrement((volatile signed __int32 *)(Pool2 + 20));
          NbtCheckNameAddrTimer(Pool2);
        }
        NbtCheckNameAddrTimer(Pool2);
        goto LABEL_5;
      }
      ExFreePoolWithTag((PVOID)Pool2, 0);
    }
    KeReleaseSpinLock(&Lock, NewIrql);
    if ( (byte_140038411 & 8) != 0 )
      WPP_SF_(523, 15, WPP_ea3294f46db239813d82e8111ee47aa3_Traceguids);
    return 3221225626LL;
  }
  if ( P[4] == -87097344 )
    NbtUpdateRemoteName(a8, (__int64)P, 0, a9);
LABEL_5:
  *(_QWORD *)(Pool2 + 112) = 0;
  *(_DWORD *)(Pool2 + 56) = dword_1400395F8;
  v16 = &a1[4 * ((v14 + 16 * (v36 & 0xFu)) % (unsigned int)v37) + 2];
  v17 = *(_QWORD *)v16;
  if ( *(_DWORD **)(*(_QWORD *)v16 + 8LL) != v16 )
    goto LABEL_45;
  *(_QWORD *)Pool2 = v17;
  *(_QWORD *)(Pool2 + 8) = v16;
  *(_QWORD *)(v17 + 8) = Pool2;
  *(_QWORD *)v16 = Pool2;
  if ( a1[1] == 1 )
    ++dword_140039608;
  if ( a1[1] && *a3 )
  {
    if ( (int)FindInHashTable(a1, a3, 0, v38) >= 0 )
    {
      *(_QWORD *)(Pool2 + 120) = v38[0];
    }
    else
    {
      v20 = 0;
      v21 = a3;
      if ( *a3 )
      {
        do
        {
          if ( v20 > 0xFF )
            break;
          ++v21;
          ++v20;
        }
        while ( *v21 );
        if ( v20 > 0xEF )
        {
          v22 = *(_QWORD *)Pool2;
          if ( *(_QWORD *)(*(_QWORD *)Pool2 + 8LL) == Pool2 )
          {
            v23 = *(_QWORD **)(Pool2 + 8);
            if ( *v23 == Pool2 )
            {
              *v23 = v22;
              *(_QWORD *)(v22 + 8) = v23;
              v24 = *(void **)(Pool2 + 24);
              if ( v24 )
                ExFreePoolWithTag(v24, 0);
              v25 = -1073741823;
LABEL_51:
              *(_DWORD *)(Pool2 + 16) += 10;
              ExFreePoolWithTag((PVOID)Pool2, 0);
              KeReleaseSpinLock(&Lock, NewIrql);
              return v25;
            }
          }
          goto LABEL_45;
        }
      }
      v32 = v20 + 1;
      v33 = (char *)ExAllocatePool2(64, (unsigned __int16)(v20 + 169), 829710926);
      v34 = v33;
      if ( !v33 )
      {
        v26 = *(_QWORD *)Pool2;
        if ( *(_QWORD *)(*(_QWORD *)Pool2 + 8LL) == Pool2 )
        {
          v27 = *(_QWORD **)(Pool2 + 8);
          if ( *v27 == Pool2 )
          {
            *v27 = v26;
            *(_QWORD *)(v26 + 8) = v27;
            v28 = *(void **)(Pool2 + 24);
            if ( v28 )
              ExFreePoolWithTag(v28, 0);
            v25 = -1073741670;
            goto LABEL_51;
          }
        }
LABEL_45:
        __fastfail(3u);
      }
      memset(v33, 0, v32 + 168);
      memmove(v34 + 164, a3, (unsigned int)v32);
      *((_DWORD *)v34 + 18) = 4112;
      *((_DWORD *)v34 + 4) = -87097344;
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *((_DWORD *)v34 + 5),
          12,
          (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
          (_DWORD)v34,
          *((_DWORD *)v34 + 5),
          *((_DWORD *)v34 + 5) + 1,
          84,
          (__int64)"minio\\netbt\\sys\\hashtbl.c");
      _InterlockedIncrement((volatile signed __int32 *)v34 + 5);
      NbtCheckNameAddrTimer(v34);
      if ( *((_DWORD *)v34 + 4) == -87097344 && (unsigned int)++dword_140039760 > 0x100 )
        NbtScheduleRemoteTimeout();
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *((_DWORD *)v34 + 5),
          12,
          (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
          (_DWORD)v34,
          *((_DWORD *)v34 + 5),
          *((_DWORD *)v34 + 5) + 1,
          85,
          (__int64)"minio\\netbt\\sys\\hashtbl.c");
      _InterlockedIncrement((volatile signed __int32 *)v34 + 5);
      NbtCheckNameAddrTimer(v34);
      if ( *((_DWORD *)v34 + 4) == -87097344 )
        --dword_140039760;
      *((_DWORD *)v34 + 28) = v32;
      *(_QWORD *)(Pool2 + 120) = v34;
      v29 = &a1[4 * (((v34[165] & 0xF) + 16 * (v34[164] & 0xFu)) % *a1) + 2];
      v30 = (_QWORD *)*((_QWORD *)v29 + 1);
      if ( (_DWORD *)*v30 != v29 )
        goto LABEL_45;
      *(_QWORD *)v34 = v29;
      *((_QWORD *)v34 + 1) = v30;
      *v30 = v34;
      *((_QWORD *)v29 + 1) = v34;
      if ( a1[1] == 1 )
        ++dword_140039608;
    }
  }
  else
  {
    *(_QWORD *)(Pool2 + 120) = 0;
  }
  if ( a7 )
    *a7 = Pool2;
  KeReleaseSpinLock(&Lock, NewIrql);
  return 0;
}

```

## disassembly

```asm
0x140008160  push    rbx
0x140008162  push    rbp
0x140008163  push    rsi
0x140008164  push    rdi
0x140008165  push    r12
0x140008167  push    r13
0x140008169  push    r14
0x14000816b  push    r15
0x14000816d  sub     rsp, 68h
0x140008171  mov     ebp, r9d
0x140008174  xor     ebx, ebx
0x140008176  lea     r9, [rsp+0A8h+var_60]
0x14000817b  mov     [rsp+0A8h+var_58], rbx
0x140008180  mov     [rsp+0A8h+var_60], rbx
0x140008185  mov     r15, r8
0x140008188  mov     rsi, rdx
0x14000818b  mov     r14, rcx
0x14000818e  call    FindInHashTable
0x140008193  test    eax, eax
0x140008195  jz      loc_140008381
0x14000819b  mov     al, [rsi]
0x14000819d  lea     rcx, Lock; SpinLock
0x1400081a4  movzx   r13d, byte ptr [rsi+1]
0x1400081a9  mov     [rsp+0A8h+var_67], al
0x1400081ad  and     r13d, 0Fh
0x1400081b1  mov     eax, [r14]
0x1400081b4  mov     dword ptr [rsp+0A8h+var_60], eax
0x1400081b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400081bf  nop     dword ptr [rax+rax+00h]
0x1400081c4  mov     rdi, [rsp+0A8h+P]
0x1400081cc  lea     r12, aMinioNetbtSysH_0; "minio\\netbt\\sys\\hashtbl.c"
0x1400081d3  mov     [rsp+0A8h+NewIrql], al
0x1400081d7  test    rdi, rdi
0x1400081da  jz      loc_140008288
0x1400081e0  mov     esi, 0FACF0000h
0x1400081e5  cmp     [rdi+10h], esi
0x1400081e8  jz      loc_1400082DA
0x1400081ee  mov     [rdi+70h], rbx
0x1400081f2  xor     edx, edx
0x1400081f4  mov     eax, cs:dword_1400395F8
0x1400081fa  mov     [rdi+38h], eax
0x1400081fd  movzx   eax, [rsp+0A8h+var_67]
0x140008202  and     eax, 0Fh
0x140008205  shl     eax, 4
0x140008208  add     eax, r13d
0x14000820b  div     dword ptr [rsp+0A8h+var_60]
0x14000820f  mov     eax, edx
0x140008211  shl     rax, 4
0x140008215  add     rax, 8
0x140008219  add     rax, r14
0x14000821c  mov     rcx, [rax]
0x14000821f  cmp     [rcx+8], rax
0x140008223  jnz     loc_14000850A
0x140008229  mov     [rdi], rcx
0x14000822c  mov     [rdi+8], rax
0x140008230  mov     [rcx+8], rdi
0x140008234  mov     [rax], rdi
0x140008237  cmp     dword ptr [r14+4], 1
0x14000823c  jz      loc_140008376
0x140008242  cmp     [r14+4], ebx
0x140008246  jnz     loc_14000839A
0x14000824c  mov     [rdi+78h], rbx
0x140008250  mov     rax, [rsp+0A8h+arg_30]
0x140008258  test    rax, rax
0x14000825b  jnz     short loc_1400082D5
0x14000825d  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x140008261  lea     rcx, Lock; SpinLock
0x140008268  call    cs:__imp_KeReleaseSpinLock
0x14000826f  nop     dword ptr [rax+rax+00h]
0x140008274  xor     eax, eax
0x140008276  add     rsp, 68h
0x14000827a  pop     r15
0x14000827c  pop     r14
0x14000827e  pop     r13
0x140008280  pop     r12
0x140008282  pop     rdi
0x140008283  pop     rsi
0x140008284  pop     rbp
0x140008285  pop     rbx
0x140008286  retn
0x140008288  mov     edx, 0B8h
0x14000828d  mov     r8d, 3074624Eh
0x140008293  lea     ecx, [rdx-78h]
0x140008296  call    cs:__imp_ExAllocatePool2
0x14000829d  nop     dword ptr [rax+rax+00h]
0x1400082a2  mov     rdi, rax
0x1400082a5  test    rax, rax
0x1400082a8  jnz     short loc_1400082FB
0x1400082aa  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x1400082ae  lea     rcx, Lock; SpinLock
0x1400082b5  call    cs:__imp_KeReleaseSpinLock
0x1400082bc  nop     dword ptr [rax+rax+00h]
0x1400082c1  test    cs:byte_140038411, 8
0x1400082c8  jnz     loc_140008768
0x1400082ce  mov     eax, 0C000009Ah
0x1400082d3  jmp     short loc_140008276
0x1400082d5  mov     [rax], rdi
0x1400082d8  jmp     short loc_14000825D
0x1400082da  movzx   r9d, [rsp+0A8h+arg_40]
0x1400082e3  xor     r8d, r8d
0x1400082e6  mov     rcx, [rsp+0A8h+arg_38]
0x1400082ee  mov     rdx, rdi
0x1400082f1  call    NbtUpdateRemoteName
0x1400082f6  jmp     loc_1400081EE
0x1400082fb  cmp     dword ptr [r14+4], 1
0x140008300  jz      loc_140008498
0x140008306  xor     edx, edx; Val
0x140008308  mov     r8d, 0B8h; Size
0x14000830e  mov     rcx, rdi; void *
0x140008311  call    memset
0x140008316  neg     [rsp+0A8h+arg_20]
0x14000831d  mov     [rdi+20h], ebp
0x140008320  sbb     eax, eax
0x140008322  and     eax, 2
0x140008325  add     eax, 2
0x140008328  or      eax, 10h
0x14000832b  mov     [rdi+48h], eax
0x14000832e  movups  xmm0, xmmword ptr [rsi]
0x140008331  movdqu  xmmword ptr [rdi+0A4h], xmm0
0x140008339  test    dword ptr [r14+4], 0FFFFFFFDh
0x140008341  jnz     loc_140008429
0x140008347  mov     dword ptr [rdi+10h], 0DEAD0000h
0x14000834e  test    byte ptr cs:xmmword_140038420+9, 40h
0x140008355  jnz     loc_140008734
0x14000835b  lock inc dword ptr [rdi+14h]
0x14000835f  mov     rcx, rdi
0x140008362  call    NbtCheckNameAddrTimer
0x140008367  mov     rcx, rdi
0x14000836a  call    NbtCheckNameAddrTimer
0x14000836f  xor     ebx, ebx
0x140008371  jmp     loc_1400081EE
0x140008376  inc     cs:dword_140039608
0x14000837c  jmp     loc_140008242
0x140008381  mov     rbx, [rsp+0A8h+var_60]
0x140008386  cmp     dword ptr [rbx+10h], 0FACF0000h
0x14000838d  jz      loc_140008669
0x140008393  xor     ebx, ebx
0x140008395  jmp     loc_14000819B
0x14000839a  cmp     [r15], bl
0x14000839d  jz      loc_14000824C
0x1400083a3  lea     r9, [rsp+0A8h+var_58]
0x1400083a8  xor     r8d, r8d
0x1400083ab  mov     rdx, r15
0x1400083ae  mov     rcx, r14
0x1400083b1  call    FindInHashTable
0x1400083b6  test    eax, eax
0x1400083b8  jns     loc_14000882A
0x1400083be  mov     eax, ebx
0x1400083c0  mov     rcx, r15
0x1400083c3  cmp     [r15], bl
0x1400083c6  jz      loc_140008783
0x1400083cc  cmp     eax, 0FFh
0x1400083d1  ja      short loc_1400083DC
0x1400083d3  inc     rcx
0x1400083d6  inc     eax
0x1400083d8  cmp     [rcx], bl
0x1400083da  jnz     short loc_1400083CC
0x1400083dc  cmp     eax, 0EFh
0x1400083e1  jbe     loc_140008783
0x1400083e7  mov     rax, [rdi]
0x1400083ea  cmp     [rax+8], rdi
0x1400083ee  jnz     loc_14000850A
0x1400083f4  mov     rcx, [rdi+8]
0x1400083f8  cmp     [rcx], rdi
0x1400083fb  jnz     loc_14000850A
0x140008401  mov     [rcx], rax
0x140008404  mov     [rax+8], rcx
0x140008408  mov     rcx, [rdi+18h]; P
0x14000840c  test    rcx, rcx
0x14000840f  jz      short loc_14000841F
0x140008411  xor     edx, edx; Tag
0x140008413  call    cs:__imp_ExFreePoolWithTag
0x14000841a  nop     dword ptr [rax+rax+00h]
0x14000841f  mov     ebx, 0C0000001h
0x140008424  jmp     loc_140008546
0x140008429  mov     esi, 0FACF0000h
0x14000842e  xor     edx, edx; Val
0x140008430  mov     [rdi+10h], esi
0x140008433  mov     rcx, rbx; void *
0x140008436  movzx   r8d, cs:word_1400395D0
0x14000843e  shl     r8, 4; Size
0x140008442  call    memset
0x140008447  mov     [rdi+18h], rbx
0x14000844b  movzx   eax, cs:word_1400395D0
0x140008452  mov     [rdi+80h], ax
0x140008459  test    byte ptr cs:xmmword_140038420+9, 40h
0x140008460  jnz     loc_140008700
0x140008466  lock inc dword ptr [rdi+14h]
0x14000846a  mov     rcx, rdi
0x14000846d  call    NbtCheckNameAddrTimer
0x140008472  cmp     [rdi+10h], esi
0x140008475  jz      short loc_1400084E7
0x140008477  movzx   r9d, [rsp+0A8h+arg_40]
0x140008480  xor     r8d, r8d
0x140008483  mov     rcx, [rsp+0A8h+arg_38]
0x14000848b  mov     rdx, rdi
0x14000848e  call    NbtUpdateRemoteName
0x140008493  jmp     loc_140008367
0x140008498  movzx   eax, cs:word_1400395D0
0x14000849f  test    ax, ax
0x1400084a2  jz      loc_140008306
0x1400084a8  mov     edx, eax
0x1400084aa  mov     ecx, 40h ; '@'
0x1400084af  shl     rdx, 4
0x1400084b3  mov     r8d, 3330624Eh
0x1400084b9  call    cs:__imp_ExAllocatePool2
0x1400084c0  nop     dword ptr [rax+rax+00h]
0x1400084c5  mov     rbx, rax
0x1400084c8  test    rax, rax
0x1400084cb  jnz     loc_140008306
0x1400084d1  xor     edx, edx; Tag
0x1400084d3  mov     rcx, rdi; P
0x1400084d6  call    cs:__imp_ExFreePoolWithTag
0x1400084dd  nop     dword ptr [rax+rax+00h]
0x1400084e2  jmp     loc_1400082AA
0x1400084e7  mov     eax, cs:dword_140039760
0x1400084ed  inc     eax
0x1400084ef  mov     cs:dword_140039760, eax
0x1400084f5  cmp     eax, 100h
0x1400084fa  jbe     loc_140008477
0x140008500  call    NbtScheduleRemoteTimeout
0x140008505  jmp     loc_140008477
0x14000850a  mov     ecx, 3
0x14000850f  int     29h; Win8: RtlFailFast(ecx)
0x140008511  mov     rax, [rdi]
0x140008514  cmp     [rax+8], rdi
0x140008518  jnz     short loc_14000850A
0x14000851a  mov     rcx, [rdi+8]
0x14000851e  cmp     [rcx], rdi
0x140008521  jnz     short loc_14000850A
0x140008523  mov     [rcx], rax
0x140008526  mov     [rax+8], rcx
0x14000852a  mov     rcx, [rdi+18h]; P
0x14000852e  test    rcx, rcx
0x140008531  jz      short loc_140008541
0x140008533  xor     edx, edx; Tag
0x140008535  call    cs:__imp_ExFreePoolWithTag
0x14000853c  nop     dword ptr [rax+rax+00h]
0x140008541  mov     ebx, 0C000009Ah
0x140008546  add     dword ptr [rdi+10h], 0Ah
0x14000854a  xor     edx, edx; Tag
0x14000854c  mov     rcx, rdi; P
0x14000854f  call    cs:__imp_ExFreePoolWithTag
0x140008556  nop     dword ptr [rax+rax+00h]
0x14000855b  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14000855f  lea     rcx, Lock; SpinLock
0x140008566  call    cs:__imp_KeReleaseSpinLock
0x14000856d  nop     dword ptr [rax+rax+00h]
0x140008572  mov     eax, ebx
0x140008574  jmp     loc_140008276
0x140008579  lea     r8, [rbp+0A8h]; Size
0x140008580  xor     edx, edx; Val
0x140008582  mov     rcx, rsi; void *
0x140008585  call    memset
0x14000858a  lea     rcx, [rsi+0A4h]; void *
0x140008591  mov     r8d, ebp; Size
0x140008594  mov     rdx, r15; Src
0x140008597  call    memmove
0x14000859c  mov     ebx, 0FACF0000h
0x1400085a1  mov     dword ptr [rsi+48h], 1010h
0x1400085a8  mov     [rsi+10h], ebx
0x1400085ab  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400085b2  jnz     loc_1400087B8
0x1400085b8  lock inc dword ptr [rsi+14h]
0x1400085bc  mov     rcx, rsi
0x1400085bf  call    NbtCheckNameAddrTimer
0x1400085c4  cmp     [rsi+10h], ebx
0x1400085c7  jnz     short loc_1400085E2
0x1400085c9  mov     eax, cs:dword_140039760
0x1400085cf  inc     eax
0x1400085d1  mov     cs:dword_140039760, eax
0x1400085d7  cmp     eax, 100h
0x1400085dc  ja      loc_1400087EC
0x1400085e2  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400085e9  jnz     loc_1400087F6
0x1400085ef  lock inc dword ptr [rsi+14h]
0x1400085f3  mov     rcx, rsi
0x1400085f6  call    NbtCheckNameAddrTimer
0x1400085fb  cmp     [rsi+10h], ebx
0x1400085fe  jnz     short loc_140008606
0x140008600  dec     cs:dword_140039760
0x140008606  mov     [rsi+70h], ebp
0x140008609  xor     edx, edx
0x14000860b  mov     [rdi+78h], rsi
0x14000860f  movsx   eax, byte ptr [rsi+0A4h]
0x140008616  movsx   ecx, byte ptr [rsi+0A5h]
0x14000861d  and     eax, 0Fh
0x140008620  shl     eax, 4
0x140008623  and     ecx, 0Fh
0x140008626  add     eax, ecx
0x140008628  div     dword ptr [r14]
0x14000862b  mov     eax, edx
0x14000862d  shl     rax, 4
0x140008631  add     rax, 8
0x140008635  add     rax, r14
0x140008638  mov     rcx, [rax+8]
0x14000863c  cmp     [rcx], rax
0x14000863f  jnz     loc_14000850A
0x140008645  mov     [rsi], rax
0x140008648  mov     [rsi+8], rcx
  ... truncated ...
```
