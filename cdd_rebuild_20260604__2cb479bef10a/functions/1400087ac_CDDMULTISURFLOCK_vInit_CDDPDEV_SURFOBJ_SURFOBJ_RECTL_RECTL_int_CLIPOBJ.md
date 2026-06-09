# CDDMULTISURFLOCK::vInit(CDDPDEV *,_SURFOBJ * *,_SURFOBJ * *,_RECTL *,_RECTL *,int *,_CLIPOBJ *)

- ea: `0x1400087ac`
- end: `0x1400089e3`
- name: `?vInit@CDDMULTISURFLOCK@@QEAAXPEAUCDDPDEV@@PEAPEAU_SURFOBJ@@1PEAU_RECTL@@2PEAHPEAU_CLIPOBJ@@@Z`
- size: `567`
- prototype: `void __usercall(CDDMULTISURFLOCK *__hidden this@<rcx>, struct CDDPDEV *@<rdx>, struct _SURFOBJ **@<r8>, struct _SURFOBJ **@<r9>, struct _RECTL *, struct _RECTL *, int *, struct _CLIPOBJ *)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x14000919c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`

## callees

- `0x1400087ac`
- `0x1400089ec`
- `0x140009030`
- `0x140018730`
- `0x1400224a0`
- `0x140033f44`

## pseudocode

```c
void __fastcall CDDMULTISURFLOCK::vInit(
        CDDMULTISURFLOCK *this,
        struct CDDPDEV *a2,
        struct _SURFOBJ **a3,
        struct _SURFOBJ **a4,
        struct _RECTL *a5,
        struct _RECTL *a6,
        int *a7,
        struct _CLIPOBJ *a8)
{
  int *v9; // rdx
  struct _SURFOBJ *v13; // rsi
  struct _SURFOBJ *v14; // rcx
  struct _SURFOBJ *v15; // rax
  char v16; // r15
  char v17; // r12
  USHORT v18; // cx
  USHORT v19; // ax
  struct _SURFOBJ *v20; // rax
  struct _SURFOBJ *v21; // rcx
  USHORT iType; // ax
  struct _CLIPOBJ *v23; // r8
  signed __int32 v24[26]; // [rsp+0h] [rbp-68h] BYREF

  *(_QWORD *)this = 0;
  v9 = a7;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 24) = 0;
  v13 = *a3;
  v14 = *a4;
  *a7 = 0;
  if ( v14 <= v13 )
  {
    v15 = v14;
  }
  else
  {
    v15 = v13;
    v13 = v14;
  }
  if ( v15 == v13 && v15 )
  {
    iType = v14->iType;
    if ( iType == 3 )
    {
      *(_QWORD *)this = v14;
      CDDMULTISURFLOCK::vLockBmp1AndPrepareForPunt(this, 0);
    }
    else if ( iType == 1 )
    {
      *((_QWORD *)this + 4) = a2;
      do
      {
        CDDMULTISURFLOCK::vLockShadowW(this, a5, a8);
        _InterlockedOr(v24, 0);
      }
      while ( !(unsigned int)CDDMULTISURFLOCK::bTryLockShadowR(this, a6, v23) );
      *a4 = (struct _SURFOBJ *)*((_QWORD *)a2 + 349);
      *a3 = (struct _SURFOBJ *)*((_QWORD *)a2 + 349);
      *a7 = 1;
    }
    return;
  }
  v16 = 0;
  v17 = 0;
  if ( v15 )
  {
    v18 = v15->iType;
    if ( v18 == 3 )
    {
      *(_QWORD *)this = v15;
      CDDMULTISURFLOCK::vLockBmp1AndPrepareForPunt(this, v15 == *a4);
      v9 = a7;
    }
    else if ( v18 == 1 )
    {
      *((_QWORD *)this + 4) = a2;
      v21 = (struct _SURFOBJ *)*((_QWORD *)a2 + 349);
      if ( v15 == *a4 )
      {
        *a4 = v21;
        v16 = 1;
      }
      else
      {
        *a3 = v21;
        v17 = 1;
        *a7 = 1;
      }
    }
  }
  _InterlockedOr(v24, 0);
  if ( v13 )
  {
    v19 = v13->iType;
    if ( v19 == 3 )
    {
      *((_QWORD *)this + 2) = v13;
      CDDMULTISURFLOCK::vLockBmp2AndPrepareForPunt(this, v13 == *a4);
    }
    else if ( v19 == 1 )
    {
      *((_QWORD *)this + 5) = a2;
      v20 = (struct _SURFOBJ *)*((_QWORD *)a2 + 349);
      if ( v13 != *a4 )
      {
        *a3 = v20;
        v17 = 1;
        *v9 = 1;
LABEL_21:
        if ( v16 )
        {
          DbgLog("CDDMULTISURFLOCK: bTakeShadowW && bTakeShadowR\n");
          __debugbreak();
        }
        goto LABEL_23;
      }
      *a4 = v20;
      v16 = 1;
    }
  }
  if ( v17 )
    goto LABEL_21;
  while ( 1 )
  {
    _InterlockedOr(v24, 0);
    if ( !v16 || (unsigned int)CDDMULTISURFLOCK::bTryLockShadowR(this, a6, (struct _CLIPOBJ *)a3) )
      break;
LABEL_23:
    if ( v17 )
      CDDMULTISURFLOCK::vLockShadowW(this, a5, a8);
  }
}

```

## disassembly

```asm
0x1400087ac  push    rbx
0x1400087ae  push    rbp
0x1400087af  push    rsi
0x1400087b0  push    rdi
0x1400087b1  push    r12
0x1400087b3  push    r13
0x1400087b5  push    r14
0x1400087b7  push    r15
0x1400087b9  sub     rsp, 28h
0x1400087bd  mov     qword ptr [rcx], 0
0x1400087c4  mov     rbp, rdx
0x1400087c7  mov     rdx, [rsp+68h+arg_30]
0x1400087cf  mov     rbx, rcx
0x1400087d2  mov     qword ptr [rcx+8], 0
0x1400087da  mov     r14, r9
0x1400087dd  mov     qword ptr [rcx+10h], 0
0x1400087e5  mov     r13, r8
0x1400087e8  mov     qword ptr [rcx+18h], 0
0x1400087f0  mov     qword ptr [rcx+20h], 0
0x1400087f8  mov     qword ptr [rcx+28h], 0
0x140008800  mov     word ptr [rcx+30h], 0
0x140008806  mov     rsi, [r8]
0x140008809  mov     rcx, [r9]
0x14000880c  mov     dword ptr [rdx], 0
0x140008812  cmp     rcx, rsi
0x140008815  jbe     loc_1400088BA
0x14000881b  mov     rax, rsi
0x14000881e  mov     rsi, rcx
0x140008821  cmp     rax, rsi
0x140008824  jnz     short loc_14000882F
0x140008826  test    rax, rax
0x140008829  jnz     loc_140008927
0x14000882f  xor     r15b, r15b
0x140008832  xor     r12b, r12b
0x140008835  mov     edi, 1
0x14000883a  test    rax, rax
0x14000883d  jz      short loc_140008852
0x14000883f  movzx   ecx, word ptr [rax+4Ch]
0x140008843  cmp     cx, 3
0x140008847  jz      loc_1400089AA
0x14000884d  cmp     cx, di
0x140008850  jz      short loc_1400088C2
0x140008852  lock or [rsp+68h+var_68], 0
0x140008857  test    rsi, rsi
0x14000885a  jz      short loc_140008885
0x14000885c  movzx   eax, word ptr [rsi+4Ch]
0x140008860  cmp     ax, 3
0x140008864  jz      loc_1400089CA
0x14000886a  cmp     ax, di
0x14000886d  jnz     short loc_140008885
0x14000886f  mov     [rbx+28h], rbp
0x140008873  mov     rax, [rbp+0AE8h]
0x14000887a  cmp     rsi, [r14]
0x14000887d  jnz     short loc_1400088DD
0x14000887f  mov     [r14], rax
0x140008882  mov     r15b, dil
0x140008885  test    r12b, r12b
0x140008888  jnz     short loc_1400088E6
0x14000888a  lock or [rsp+68h+var_68], 0
0x14000888f  test    r15b, r15b
0x140008892  jz      short loc_1400088A8
0x140008894  mov     rdx, [rsp+68h+arg_28]; struct _RECTL *
0x14000889c  mov     rcx, rbx; this
0x14000889f  call    ?bTryLockShadowR@CDDMULTISURFLOCK@@QEAAHPEAU_RECTL@@PEAU_CLIPOBJ@@@Z; CDDMULTISURFLOCK::bTryLockShadowR(_RECTL *,_CLIPOBJ *)
0x1400088a4  test    eax, eax
0x1400088a6  jz      short loc_1400088F8
0x1400088a8  add     rsp, 28h
0x1400088ac  pop     r15
0x1400088ae  pop     r14
0x1400088b0  pop     r13
0x1400088b2  pop     r12
0x1400088b4  pop     rdi
0x1400088b5  pop     rsi
0x1400088b6  pop     rbp
0x1400088b7  pop     rbx
0x1400088b8  retn
0x1400088ba  mov     rax, rcx
0x1400088bd  jmp     loc_140008821
0x1400088c2  mov     [rbx+20h], rbp
0x1400088c6  mov     rcx, [rbp+0AE8h]
0x1400088cd  cmp     rax, [r9]
0x1400088d0  jnz     short loc_14000891A
0x1400088d2  mov     [r9], rcx
0x1400088d5  mov     r15b, dil
0x1400088d8  jmp     loc_140008852
0x1400088dd  mov     [r13+0], rax
0x1400088e1  mov     r12b, dil
0x1400088e4  mov     [rdx], edi
0x1400088e6  test    r15b, r15b
0x1400088e9  jz      short loc_1400088F8
0x1400088eb  lea     rcx, aCddmultisurflo_1; "CDDMULTISURFLOCK: bTakeShadowW && bTake"...
0x1400088f2  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x1400088f7  int     3; Trap to Debugger
0x1400088f8  test    r12b, r12b
0x1400088fb  jz      short loc_14000888A
0x1400088fd  mov     r8, [rsp+68h+arg_38]; struct _CLIPOBJ *
0x140008905  mov     rcx, rbx; this
0x140008908  mov     rdx, [rsp+68h+arg_20]; struct _RECTL *
0x140008910  call    ?vLockShadowW@CDDMULTISURFLOCK@@QEAAXPEAU_RECTL@@PEAU_CLIPOBJ@@@Z; CDDMULTISURFLOCK::vLockShadowW(_RECTL *,_CLIPOBJ *)
0x140008915  jmp     loc_14000888A
0x14000891a  mov     [r8], rcx
0x14000891d  mov     r12b, dil
0x140008920  mov     [rdx], edi
0x140008922  jmp     loc_140008852
0x140008927  movzx   eax, word ptr [rcx+4Ch]
0x14000892b  cmp     ax, 3
0x14000892f  jnz     short loc_140008943
0x140008931  mov     [rbx], rcx
0x140008934  xor     edx, edx; int
0x140008936  mov     rcx, rbx; this
0x140008939  call    ?vLockBmp1AndPrepareForPunt@CDDMULTISURFLOCK@@QEAAXH@Z; CDDMULTISURFLOCK::vLockBmp1AndPrepareForPunt(int)
0x14000893e  jmp     loc_1400088A8
0x140008943  mov     edi, 1
0x140008948  cmp     ax, di
0x14000894b  jnz     loc_1400088A8
0x140008951  mov     [rbx+20h], rbp
0x140008955  mov     r8, [rsp+68h+arg_38]; struct _CLIPOBJ *
0x14000895d  mov     rcx, rbx; this
0x140008960  mov     rdx, [rsp+68h+arg_20]; struct _RECTL *
0x140008968  call    ?vLockShadowW@CDDMULTISURFLOCK@@QEAAXPEAU_RECTL@@PEAU_CLIPOBJ@@@Z; CDDMULTISURFLOCK::vLockShadowW(_RECTL *,_CLIPOBJ *)
0x14000896d  lock or [rsp+68h+var_68], 0
0x140008972  mov     rdx, [rsp+68h+arg_28]; struct _RECTL *
0x14000897a  mov     rcx, rbx; this
0x14000897d  call    ?bTryLockShadowR@CDDMULTISURFLOCK@@QEAAHPEAU_RECTL@@PEAU_CLIPOBJ@@@Z; CDDMULTISURFLOCK::bTryLockShadowR(_RECTL *,_CLIPOBJ *)
0x140008982  test    eax, eax
0x140008984  jz      short loc_140008955
0x140008986  mov     rax, [rbp+0AE8h]
0x14000898d  mov     [r14], rax
0x140008990  mov     rax, [rbp+0AE8h]
0x140008997  mov     [r13+0], rax
0x14000899b  mov     rax, [rsp+68h+arg_30]
0x1400089a3  mov     [rax], edi
0x1400089a5  jmp     loc_1400088A8
0x1400089aa  xor     edx, edx
0x1400089ac  mov     [rbx], rax
0x1400089af  cmp     rax, [r9]
0x1400089b2  mov     rcx, rbx; this
0x1400089b5  setz    dl; int
0x1400089b8  call    ?vLockBmp1AndPrepareForPunt@CDDMULTISURFLOCK@@QEAAXH@Z; CDDMULTISURFLOCK::vLockBmp1AndPrepareForPunt(int)
0x1400089bd  mov     rdx, [rsp+68h+arg_30]
0x1400089c5  jmp     loc_140008852
0x1400089ca  xor     edx, edx
0x1400089cc  mov     [rbx+10h], rsi
0x1400089d0  cmp     rsi, [r14]
0x1400089d3  mov     rcx, rbx; this
0x1400089d6  setz    dl; int
0x1400089d9  call    ?vLockBmp2AndPrepareForPunt@CDDMULTISURFLOCK@@QEAAXH@Z; CDDMULTISURFLOCK::vLockBmp2AndPrepareForPunt(int)
0x1400089de  jmp     loc_140008885
```
