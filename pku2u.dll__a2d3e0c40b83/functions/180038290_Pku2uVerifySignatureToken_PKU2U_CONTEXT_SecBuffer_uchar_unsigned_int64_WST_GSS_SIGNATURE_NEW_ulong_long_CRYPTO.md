# Pku2uVerifySignatureToken(_PKU2U_CONTEXT *,_SecBuffer *,uchar,unsigned __int64,_WST_GSS_SIGNATURE_NEW * *,ulong *,long *,_CRYPTO_SYSTEM * *,unsigned __int64 *)

- ea: `0x180038290`
- end: `0x1800385a6`
- name: `?Pku2uVerifySignatureToken@@YAJPEAU_PKU2U_CONTEXT@@PEAU_SecBuffer@@E_KPEAPEAU_WST_GSS_SIGNATURE_NEW@@PEAKPEAJPEAPEAU_CRYPTO_SYSTEM@@PEA_K@Z`
- size: `790`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, struct _SecBuffer *, unsigned __int8, unsigned __int64, struct _WST_GSS_SIGNATURE_NEW **, unsigned int *, int *, struct _CRYPTO_SYSTEM **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180037ed8`

## callees

- `0x180023cb8`
- `0x180023ce0`
- `0x18002b408`
- `0x1800321d8`
- `0x180038290`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x1800383ab`
- `cryptdll!CDLocateCSystem` at `0x1800383ab`

## pseudocode

```c
__int64 __fastcall Pku2uVerifySignatureToken(
        struct _PKU2U_CONTEXT *a1,
        struct _SecBuffer *a2,
        __int64 a3,
        __int64 a4,
        struct _WST_GSS_SIGNATURE_NEW **a5,
        unsigned int *a6,
        int *a7,
        struct _CRYPTO_SYSTEM **a8,
        unsigned __int64 *a9)
{
  bool v9; // cf
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _WORD *pvBuffer; // rsi
  _WORD *v14; // rsi
  __int64 v15; // r9
  int v16; // ecx
  unsigned int v17; // ebx
  unsigned int v18; // r14d
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  __int64 *v22; // r14
  unsigned __int64 v23; // rcx
  char v24; // ah
  char v25; // r8
  __int64 v26; // rdx
  char v27; // cl
  char v28; // al
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  __int64 v32; // [rsp+30h] [rbp-28h]
  __int64 v33; // [rsp+38h] [rbp-20h] BYREF
  __int64 v34; // [rsp+40h] [rbp-18h] BYREF

  v9 = a2->cbBuffer < 0x1C;
  v34 = 0;
  v33 = 0;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893048;
    v12 = 20;
LABEL_48:
    WPP_SF_(v11[2], v12, WPP_801de8da242a398af64deff044103c73_Traceguids);
    return (unsigned int)-2146893048;
  }
  pvBuffer = a2->pvBuffer;
  if ( *pvBuffer != 1028 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893048;
    v12 = 21;
    goto LABEL_48;
  }
  v14 = pvBuffer + 1;
  if ( *((_BYTE *)v14 + 1) != 0xFF || *(_DWORD *)(v14 + 1) != -1 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893041;
    v30 = 24;
    goto LABEL_43;
  }
  v15 = *((unsigned int *)a1 + 56);
  v16 = *((_DWORD *)a1 + 56) - 17;
  if ( v16 )
  {
    if ( v16 != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_801de8da242a398af64deff044103c73_Traceguids, v15);
      return (unsigned int)-2146893054;
    }
    v18 = -149;
    v19 = (*(_BYTE *)v14 & 2) != 0 ? -151 : 16;
  }
  else
  {
    v18 = -148;
    v19 = (*(_BYTE *)v14 & 2) != 0 ? -150 : 15;
  }
  *a7 = v19;
  v20 = CDLocateCSystem(v18, &v33);
  v17 = v20;
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_801de8da242a398af64deff044103c73_Traceguids, v18, v20);
    return v17;
  }
  v21 = *((_DWORD *)a1 + 16);
  if ( (v21 & 0x400) != 0 || (v22 = (__int64 *)((char *)a1 + 296), (v21 & 0x1000C) == 0x10000) )
    v22 = &v34;
  v23 = HIDWORD(*v22);
  BYTE3(v32) = BYTE4(*v22);
  LOBYTE(v32) = BYTE3(v23);
  BYTE1(v32) = BYTE2(v23);
  v24 = BYTE1(v23);
  LODWORD(v23) = *(_DWORD *)v22;
  BYTE2(v32) = v24;
  BYTE4(v32) = BYTE3(v23);
  BYTE5(v32) = BYTE2(v23);
  BYTE6(v32) = BYTE1(v23);
  HIBYTE(v32) = v23;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_dii(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_801de8da242a398af64deff044103c73_Traceguids,
      0,
      v32,
      *(_QWORD *)(v14 + 3));
  if ( (*((_BYTE *)a1 + 64) & 0xC) == 0 )
    goto LABEL_34;
  v25 = 0;
  v26 = 0;
  do
  {
    v27 = *((_BYTE *)v14 + v26 + 6);
    v28 = *((_BYTE *)&v32 + v26++);
    v25 |= v28 ^ v27;
  }
  while ( v26 != 8 );
  if ( !v25 )
  {
LABEL_34:
    *a9 = *(_QWORD *)(v14 + 3);
    if ( (*((_BYTE *)a1 + 40) & 2) == 0 || (*(_BYTE *)v14 & 1) != 0 )
    {
      ++*v22;
      *a5 = (struct _WST_GSS_SIGNATURE_NEW *)v14;
      return v17;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893041;
    v30 = 29;
LABEL_43:
    WPP_SF_(v29[2], v30, WPP_801de8da242a398af64deff044103c73_Traceguids);
    return (unsigned int)-2146893041;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_801de8da242a398af64deff044103c73_Traceguids);
  return (unsigned int)-2146893040;
}

```

## disassembly

```asm
0x180038290  push    rbp
0x180038292  push    rbx
0x180038293  push    rsi
0x180038294  push    rdi
0x180038295  push    r12
0x180038297  push    r13
0x180038299  push    r14
0x18003829b  push    r15
0x18003829d  mov     rbp, rsp
0x1800382a0  sub     rsp, 58h
0x1800382a4  cmp     dword ptr [rdx], 1Ch
0x1800382a7  mov     r15, rcx
0x1800382aa  mov     r12, [rbp+arg_20]
0x1800382ae  mov     r8, [rbp+arg_30]
0x1800382b2  mov     r13, [rbp+arg_40]
0x1800382b9  mov     [rbp+var_18], 0
0x1800382c1  mov     [rbp+var_20], 0
0x1800382c9  jnb     short loc_1800382F6
0x1800382cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382d2  lea     rdi, WPP_GLOBAL_Control
0x1800382d9  cmp     rcx, rdi
0x1800382dc  jz      loc_18003858E
0x1800382e2  test    byte ptr [rcx+1Ch], 1
0x1800382e6  jz      loc_18003858E
0x1800382ec  mov     edx, 14h
0x1800382f1  jmp     loc_18003857E
0x1800382f6  mov     rsi, [rdx+8]
0x1800382fa  cmp     byte ptr [rsi], 4
0x1800382fd  jnz     loc_180038560
0x180038303  cmp     byte ptr [rsi+1], 4
0x180038307  jnz     loc_180038560
0x18003830d  add     rsi, 2
0x180038311  cmp     byte ptr [rsi+1], 0FFh
0x180038315  jnz     loc_18003852B
0x18003831b  cmp     dword ptr [rsi+2], 0FFFFFFFFh
0x18003831f  jnz     loc_18003852B
0x180038325  mov     r9d, [rcx+0E0h]
0x18003832c  mov     ecx, r9d
0x18003832f  sub     ecx, 11h
0x180038332  jz      short loc_18003838A
0x180038334  cmp     ecx, 1
0x180038337  jz      short loc_180038371
0x180038339  mov     rcx, cs:WPP_GLOBAL_Control
0x180038340  lea     rdi, WPP_GLOBAL_Control
0x180038347  cmp     rcx, rdi
0x18003834a  jz      short loc_180038367
0x18003834c  test    byte ptr [rcx+1Ch], 1
0x180038350  jz      short loc_180038367
0x180038352  mov     rcx, [rcx+10h]
0x180038356  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x18003835d  mov     edx, 19h
0x180038362  call    WPP_SF_d
0x180038367  mov     ebx, 80090302h
0x18003836c  jmp     loc_180038593
0x180038371  mov     al, [rsi]
0x180038373  mov     r14d, 0FFFFFF6Bh
0x180038379  and     al, 2
0x18003837b  neg     al
0x18003837d  sbb     ecx, ecx
0x18003837f  and     ecx, 0FFFFFF59h
0x180038385  add     ecx, 10h
0x180038388  jmp     short loc_1800383A1
0x18003838a  mov     al, [rsi]
0x18003838c  mov     r14d, 0FFFFFF6Ch
0x180038392  and     al, 2
0x180038394  neg     al
0x180038396  sbb     ecx, ecx
0x180038398  and     ecx, 0FFFFFF5Bh
0x18003839e  add     ecx, 0Fh
0x1800383a1  mov     [r8], ecx
0x1800383a4  lea     rdx, [rbp+var_20]
0x1800383a8  mov     ecx, r14d
0x1800383ab  call    cs:__imp_CDLocateCSystem
0x1800383b1  mov     ebx, eax
0x1800383b3  test    eax, eax
0x1800383b5  jns     short loc_1800383F9
0x1800383b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383be  lea     rdi, WPP_GLOBAL_Control
0x1800383c5  cmp     rcx, rdi
0x1800383c8  jz      loc_180038593
0x1800383ce  test    byte ptr [rcx+1Ch], 1
0x1800383d2  jz      loc_180038593
0x1800383d8  mov     rcx, [rcx+10h]
0x1800383dc  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x1800383e3  mov     edx, 1Ah
0x1800383e8  mov     dword ptr [rsp+58h+var_38], eax
0x1800383ec  mov     r9d, r14d
0x1800383ef  call    WPP_SF_dd
0x1800383f4  jmp     loc_180038593
0x1800383f9  mov     eax, [r15+40h]
0x1800383fd  bt      eax, 0Ah
0x180038401  jb      short loc_180038416
0x180038403  and     eax, 1000Ch
0x180038408  lea     r14, [r15+128h]
0x18003840f  cmp     eax, 10000h
0x180038414  jnz     short loc_18003841A
0x180038416  lea     r14, [rbp+var_18]
0x18003841a  mov     rcx, [r14]
0x18003841d  shr     rcx, 20h
0x180038421  mov     eax, ecx
0x180038423  mov     byte ptr [rbp+var_28+3], cl
0x180038426  shr     eax, 18h
0x180038429  mov     byte ptr [rbp+var_28], al
0x18003842c  mov     eax, ecx
0x18003842e  shr     eax, 10h
0x180038431  mov     byte ptr [rbp+var_28+1], al
0x180038434  mov     eax, ecx
0x180038436  mov     ecx, [r14]
0x180038439  shr     eax, 8
0x18003843c  mov     byte ptr [rbp+var_28+2], al
0x18003843f  mov     eax, ecx
0x180038441  shr     eax, 18h
0x180038444  mov     byte ptr [rbp+var_28+4], al
0x180038447  mov     eax, ecx
0x180038449  shr     eax, 10h
0x18003844c  mov     byte ptr [rbp+var_28+5], al
0x18003844f  mov     eax, ecx
0x180038451  shr     eax, 8
0x180038454  mov     byte ptr [rbp+var_28+6], al
0x180038457  mov     byte ptr [rbp+var_28+7], cl
0x18003845a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038461  lea     rdi, WPP_GLOBAL_Control
0x180038468  cmp     rcx, rdi
0x18003846b  jz      short loc_18003849D
0x18003846d  test    byte ptr [rcx+1Ch], 40h
0x180038471  jz      short loc_18003849D
0x180038473  mov     rax, [rsi+6]
0x180038477  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x18003847e  mov     rcx, [rcx+10h]
0x180038482  mov     edx, 1Bh
0x180038487  mov     [rsp+58h+var_30], rax
0x18003848c  xor     r9d, r9d
0x18003848f  mov     rax, [rbp+var_28]
0x180038493  mov     [rsp+58h+var_38], rax
0x180038498  call    WPP_SF_dii
0x18003849d  test    byte ptr [r15+40h], 0Ch
0x1800384a2  jz      short loc_1800384F5
0x1800384a4  xor     r8b, r8b
0x1800384a7  xor     edx, edx
0x1800384a9  mov     cl, [rdx+rsi+6]
0x1800384ad  mov     al, byte ptr [rbp+rdx+var_28]
0x1800384b1  inc     rdx
0x1800384b4  xor     cl, al
0x1800384b6  or      r8b, cl
0x1800384b9  cmp     rdx, 8
0x1800384bd  jnz     short loc_1800384A9
0x1800384bf  test    r8b, r8b
0x1800384c2  jz      short loc_1800384F5
0x1800384c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384cb  cmp     rcx, rdi
0x1800384ce  jz      short loc_1800384EB
0x1800384d0  test    byte ptr [rcx+1Ch], 1
0x1800384d4  jz      short loc_1800384EB
0x1800384d6  mov     rcx, [rcx+10h]
0x1800384da  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x1800384e1  mov     edx, 1Ch
0x1800384e6  call    WPP_SF_
0x1800384eb  mov     ebx, 80090310h
0x1800384f0  jmp     loc_180038593
0x1800384f5  mov     rax, [rsi+6]
0x1800384f9  mov     [r13+0], rax
0x1800384fd  test    byte ptr [r15+28h], 2
0x180038502  jz      short loc_180038522
0x180038504  test    byte ptr [rsi], 1
0x180038507  jnz     short loc_180038522
0x180038509  mov     rcx, cs:WPP_GLOBAL_Control
0x180038510  cmp     rcx, rdi
0x180038513  jz      short loc_180038559
0x180038515  test    byte ptr [rcx+1Ch], 1
0x180038519  jz      short loc_180038559
0x18003851b  mov     edx, 1Dh
0x180038520  jmp     short loc_180038549
0x180038522  inc     qword ptr [r14]
0x180038525  mov     [r12], rsi
0x180038529  jmp     short loc_180038593
0x18003852b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038532  lea     rdi, WPP_GLOBAL_Control
0x180038539  cmp     rcx, rdi
0x18003853c  jz      short loc_180038559
0x18003853e  test    byte ptr [rcx+1Ch], 1
0x180038542  jz      short loc_180038559
0x180038544  mov     edx, 18h
0x180038549  mov     rcx, [rcx+10h]
0x18003854d  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180038554  call    WPP_SF_
0x180038559  mov     ebx, 8009030Fh
0x18003855e  jmp     short loc_180038593
0x180038560  mov     rcx, cs:WPP_GLOBAL_Control
0x180038567  lea     rdi, WPP_GLOBAL_Control
0x18003856e  cmp     rcx, rdi
0x180038571  jz      short loc_18003858E
0x180038573  test    byte ptr [rcx+1Ch], 1
0x180038577  jz      short loc_18003858E
0x180038579  mov     edx, 15h
0x18003857e  mov     rcx, [rcx+10h]
0x180038582  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180038589  call    WPP_SF_
0x18003858e  mov     ebx, 80090308h
0x180038593  mov     eax, ebx
0x180038595  add     rsp, 58h
0x180038599  pop     r15
0x18003859b  pop     r14
0x18003859d  pop     r13
0x18003859f  pop     r12
0x1800385a1  pop     rdi
0x1800385a2  pop     rsi
0x1800385a3  pop     rbx
0x1800385a4  pop     rbp
0x1800385a5  retn
```
