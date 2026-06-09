# FragmentAndQueue

- ea: `0x140030144`
- end: `0x1400305a8`
- name: `FragmentAndQueue`
- size: `1124`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140031b80`

## callees

- `0x14000a68c`
- `0x14001090c`
- `0x1400161f0`
- `0x140016400`
- `0x140030144`
- `0x1400320f0`
- `0x1400321d0`
- `0x140035750`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14003026c`
- `ntoskrnl!DbgPrint` at `0x1400302e1`
- `ntoskrnl!DbgPrint` at `0x14003026c`
- `ntoskrnl!DbgPrint` at `0x1400302e1`

## string_xrefs

- `0x1400302cc`: `NDISWAN: FragmentAndQueue SendDesc == NULL! LinkCB: 0x%p\n`
- `0x140030265`: `NDISWAN: FragmentAndQueue LinkCBCount %d\n`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall FragmentAndQueue(_DWORD *a1, __int64 a2, __int64 a3, _QWORD *a4, unsigned int a5)
{
  unsigned int v5; // edi
  __int64 v6; // r15
  unsigned int v8; // r11d
  __int64 v9; // rbx
  _DWORD *v11; // r10
  __int64 v12; // r9
  _DWORD *v13; // rsi
  unsigned int v14; // r8d
  int v15; // ecx
  unsigned int v16; // ebp
  unsigned int v17; // eax
  unsigned int v18; // r13d
  _DWORD *v19; // rdx
  int v20; // ecx
  __int64 v21; // r8
  _QWORD *v22; // rdi
  __int64 v23; // rax
  __int64 SendDesc; // rax
  _QWORD *v25; // rax
  unsigned int *v26; // rcx
  unsigned int v27; // edx
  unsigned int v28; // edi
  __int64 v29; // rdx
  unsigned __int8 v30; // r9
  char v31; // cl
  int v32; // eax
  __int64 v33; // rax
  __int64 *v34; // rax
  PDEVICE_OBJECT *result; // rax
  int v36; // [rsp+30h] [rbp-128h]
  unsigned int v37; // [rsp+34h] [rbp-124h]
  unsigned int v38; // [rsp+38h] [rbp-120h]
  unsigned int v39; // [rsp+3Ch] [rbp-11Ch]
  unsigned int v40; // [rsp+40h] [rbp-118h]
  _DWORD *v41; // [rsp+48h] [rbp-110h]
  char *v42; // [rsp+50h] [rbp-108h]
  __int64 v44; // [rsp+60h] [rbp-F8h]
  __int64 v45; // [rsp+68h] [rbp-F0h]
  __int64 v46; // [rsp+70h] [rbp-E8h]
  _BYTE Src[128]; // [rsp+80h] [rbp-D8h] BYREF

  v5 = 0;
  v6 = *(_QWORD *)(a3 + 48);
  v8 = *(_DWORD *)(a3 + 100);
  v9 = a3;
  v38 = *(_DWORD *)(a3 + 32);
  v11 = a1;
  v40 = v8;
  v12 = (int)v38;
  v37 = 0;
  v13 = &a1[8 * v12 + 28 + 2 * v12];
  v46 = v6;
  if ( (a1[4] & 0x400) != 0 )
  {
    v14 = v13[7];
    v15 = v8 / v14;
    if ( !(v8 / v14) )
      v15 = 1;
    v16 = v11[40];
    v17 = v15 + 1;
    if ( v8 <= v15 * v14 )
      v17 = v15;
    if ( v17 <= v16 )
      v16 = v17;
  }
  else
  {
    v16 = a5;
  }
  if ( v8 )
  {
    v18 = v8;
    v19 = *(_DWORD **)(v9 + 40);
    v20 = *(_DWORD *)(a2 + 12);
    v44 = *(_QWORD *)(v9 + 112);
    v42 = (char *)(*(_QWORD *)(v9 + 88) + *(unsigned int *)(a2 + 8));
    v36 = v20;
    v41 = v19;
    v45 = *(_QWORD *)(v44 + 16) + *(unsigned __int16 *)(*(_QWORD *)(v44 + 16) + 10LL);
    while ( 1 )
    {
      v21 = v20 & 0x10;
      v39 = v20 & 0x10;
      if ( (v20 & 0x10) == 0 )
      {
        if ( (_QWORD *)*a4 == a4 && !(unsigned int)GetSendingLinks(v11, v38, a4) )
        {
          DbgPrint("NDISWAN: FragmentAndQueue LinkCBCount %d\n", 0);
          goto LABEL_49;
        }
        v22 = (_QWORD *)*a4;
        if ( *(_QWORD **)(*a4 + 8LL) != a4 )
          goto LABEL_51;
        v23 = *v22;
        if ( *(_QWORD **)(*v22 + 8LL) != v22 )
          goto LABEL_51;
        *a4 = v23;
        *(_QWORD *)(v23 + 8) = a4;
        v41 = v22 - 30;
        SendDesc = NdisWanAllocateSendDesc(v22 - 30);
        v9 = SendDesc;
        if ( !SendDesc )
        {
          v25 = (_QWORD *)a4[1];
          if ( (_QWORD *)*v25 != a4 )
            goto LABEL_51;
          *v22 = a4;
          v22[1] = v25;
          *v25 = v22;
          a4[1] = v22;
          DbgPrint("NDISWAN: FragmentAndQueue SendDesc == NULL! LinkCB: 0x%p\n", v41);
          v5 = v37;
          goto LABEL_49;
        }
        *(_QWORD *)(SendDesc + 48) = v6;
        *(_QWORD *)(SendDesc + 112) = v44;
        *(_DWORD *)(SendDesc + 32) = v38;
        *(_DWORD *)a2 = v41[72];
        *(_DWORD *)(a2 + 12) = v36;
        BuildLinkHeader(a2, Src);
        v21 = v39;
        v11 = a1;
        v8 = v40;
        v19 = v22 - 30;
      }
      if ( v16 <= 1 )
        goto LABEL_31;
      v26 = v13 + 6;
      v27 = v19[48] * v8 / 0x64;
      if ( (v11[4] & 0x400) != 0 )
      {
        v28 = v13[7];
        if ( v27 <= v28 )
          v28 = v27;
      }
      else
      {
        v28 = *v26;
        if ( v27 >= *v26 )
          v28 = v27;
      }
      if ( v28 > v18 || v18 - v28 < *v26 )
      {
LABEL_31:
        v16 = 1;
        v28 = v18;
      }
      v29 = (unsigned __int8)-((_DWORD)v21 != 0) & 0x80;
      v30 = ((_DWORD)v21 != 0 ? 0x80 : 0) | 0x40;
      if ( v16 != 1 )
        v30 = (_DWORD)v21 != 0 ? 0x80 : 0;
      if ( *(_DWORD *)(a2 + 32) )
      {
        v29 = *(_QWORD *)(a2 + 40) + 1LL;
        if ( (*(_DWORD *)a2 & 0x400) != 0 )
          v29 = *(_QWORD *)(a2 + 40);
        v13[5] &= v11[24];
        v21 = (unsigned int)v13[5];
        v31 = *(_BYTE *)(a2 + 4);
        if ( (*(_DWORD *)a2 & 0x20) != 0 )
        {
          v21 = (unsigned int)v21 >> 8;
          LOBYTE(v21) = v30 | (16 * v31) | v21;
          *(_BYTE *)(v29 + 1) = v21;
          *(_BYTE *)(v29 + 2) = *((_BYTE *)v13 + 20);
        }
        else
        {
          *(_BYTE *)(v29 + 1) = v30 | (4 * v31);
          *(_BYTE *)(v29 + 2) = *((_BYTE *)v13 + 22);
          *(_BYTE *)(v29 + 3) = BYTE1(v13[5]);
          *(_BYTE *)(v29 + 4) = *((_BYTE *)v13 + 20);
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, v29, v21, (unsigned int)v13[5], v30, v28);
      }
      ++v13[5];
      if ( v39 )
      {
        v36 &= ~0x10u;
      }
      else
      {
        memmove(*(void **)(v9 + 88), Src, *(unsigned int *)(a2 + 8));
        memmove((void *)(*(_QWORD *)(v9 + 88) + *(unsigned int *)(a2 + 8)), v42, v28);
        _InterlockedAdd((volatile signed __int32 *)(v45 + 40), 1u);
      }
      v32 = *(_DWORD *)(a2 + 8);
      *(_DWORD *)(v9 + 28) |= 1u;
      *(_DWORD *)(v9 + 96) = v32;
      v33 = *(_QWORD *)(v9 + 80);
      *(_DWORD *)(v9 + 100) = v28;
      *(_DWORD *)(*(_QWORD *)(v33 + 8) + 24LL) = v28 + *(_DWORD *)(a2 + 8);
      v34 = (__int64 *)*((_QWORD *)v13 + 1);
      if ( (_DWORD *)*v34 != v13 )
LABEL_51:
        __fastfail(3u);
      v42 += v28;
      v18 -= v28;
      v6 = v46;
      v5 = v37 + 1;
      *(_QWORD *)v9 = v13;
      *(_QWORD *)(v9 + 8) = v34;
      *v34 = v9;
      *((_QWORD *)v13 + 1) = v9;
      ++v13[4];
      ++v37;
      --v16;
LABEL_49:
      if ( !v18 )
      {
        v12 = (int)v38;
        break;
      }
      v11 = a1;
      v8 = v40;
      v19 = v41;
      LOBYTE(v20) = v36;
    }
  }
  _InterlockedAdd((volatile signed __int32 *)(48 * v12 + v6 + 152), v5);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return (PDEVICE_OBJECT *)WPP_SF_qD(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 45,
                                 WPP_8fab404a276b37b5b154f85d9d785092_Traceguids,
                                 *(_QWORD *)(v9 + 112),
                                 *(_DWORD *)(v9 + 24));
  }
  return result;
}

```

## disassembly

```asm
0x140030144  push    rbx
0x140030146  push    rbp
0x140030147  push    rsi
0x140030148  push    rdi
0x140030149  push    r12
0x14003014b  push    r13
0x14003014d  push    r14
0x14003014f  push    r15
0x140030151  sub     rsp, 118h
0x140030158  mov     rax, cs:__security_cookie
0x14003015f  xor     rax, rsp
0x140030162  mov     [rsp+158h+var_58], rax
0x14003016a  movsxd  rax, dword ptr [r8+20h]
0x14003016e  xor     edi, edi
0x140030170  mov     r15, [r8+30h]
0x140030174  mov     r14, r9
0x140030177  mov     r11d, [r8+64h]
0x14003017b  mov     rbx, r8
0x14003017e  mov     r12, rdx
0x140030181  mov     [rsp+158h+var_100], rcx
0x140030186  lea     rsi, ds:0Eh[rax*4]
0x14003018e  mov     [rsp+158h+var_120], eax
0x140030192  add     rsi, rax
0x140030195  mov     [rsp+158h+var_E0], rax
0x14003019a  test    dword ptr [rcx+10h], 400h
0x1400301a1  lea     ebp, [rdi+1]
0x1400301a4  mov     r10, rcx
0x1400301a7  mov     [rsp+158h+var_118], r11d
0x1400301ac  mov     r9, rax
0x1400301af  mov     [rsp+158h+var_124], edi
0x1400301b3  lea     rsi, [rcx+rsi*8]
0x1400301b7  mov     [rsp+158h+var_E8], r15
0x1400301bc  jz      short loc_1400301EC
0x1400301be  mov     r8d, [rsi+1Ch]
0x1400301c2  xor     edx, edx
0x1400301c4  mov     eax, r11d
0x1400301c7  div     r8d
0x1400301ca  test    eax, eax
0x1400301cc  mov     ecx, eax
0x1400301ce  cmovz   ecx, ebp
0x1400301d1  mov     ebp, [r10+0A0h]
0x1400301d8  imul    r8d, ecx
0x1400301dc  lea     eax, [rcx+1]
0x1400301df  cmp     r11d, r8d
0x1400301e2  cmovbe  eax, ecx
0x1400301e5  cmp     eax, ebp
0x1400301e7  cmovbe  ebp, eax
0x1400301ea  jmp     short loc_1400301F3
0x1400301ec  mov     ebp, [rsp+158h+arg_20]
0x1400301f3  test    r11d, r11d
0x1400301f6  jz      loc_140030532
0x1400301fc  mov     rax, [rbx+70h]
0x140030200  mov     r13d, r11d
0x140030203  mov     r9d, [r12+8]
0x140030208  add     r9, [rbx+58h]
0x14003020c  mov     rdx, [rbx+28h]
0x140030210  mov     ecx, [r12+0Ch]
0x140030215  mov     [rsp+158h+var_F8], rax
0x14003021a  mov     rax, [rax+10h]
0x14003021e  mov     [rsp+158h+var_108], r9
0x140030223  mov     [rsp+158h+var_128], ecx
0x140030227  mov     [rsp+158h+var_110], rdx
0x14003022c  movzx   r8d, word ptr [rax+0Ah]
0x140030231  add     r8, rax
0x140030234  mov     [rsp+158h+var_F0], r8
0x140030239  mov     r8d, ecx
0x14003023c  and     r8d, 10h
0x140030240  mov     [rsp+158h+var_11C], r8d
0x140030245  jnz     loc_140030346
0x14003024b  cmp     [r14], r14
0x14003024e  jnz     short loc_14003027D
0x140030250  mov     edx, [rsp+158h+var_120]
0x140030254  mov     r8, r14
0x140030257  mov     rcx, r10
0x14003025a  call    GetSendingLinks
0x14003025f  test    eax, eax
0x140030261  jnz     short loc_14003027D
0x140030263  xor     edx, edx
0x140030265  lea     rcx, aNdiswanFragmen_0; "NDISWAN: FragmentAndQueue LinkCBCount %"...
0x14003026c  call    cs:__imp_DbgPrint
0x140030273  nop     dword ptr [rax+rax+00h]
0x140030278  jmp     loc_140030509
0x14003027d  mov     rdi, [r14]
0x140030280  cmp     [rdi+8], r14
0x140030284  jnz     loc_140030526
0x14003028a  mov     rax, [rdi]
0x14003028d  cmp     [rax+8], rdi
0x140030291  jnz     loc_140030526
0x140030297  mov     [r14], rax
0x14003029a  mov     [rax+8], r14
0x14003029e  lea     rax, [rdi-0F0h]
0x1400302a5  mov     rcx, rax
0x1400302a8  mov     [rsp+158h+var_110], rax
0x1400302ad  call    NdisWanAllocateSendDesc
0x1400302b2  mov     rbx, rax
0x1400302b5  test    rax, rax
0x1400302b8  jnz     short loc_1400302F6
0x1400302ba  mov     rax, [r14+8]
0x1400302be  cmp     [rax], r14
0x1400302c1  jnz     loc_140030526
0x1400302c7  mov     rdx, [rsp+158h+var_110]
0x1400302cc  lea     rcx, aNdiswanFragmen; "NDISWAN: FragmentAndQueue SendDesc == N"...
0x1400302d3  mov     [rdi], r14
0x1400302d6  mov     [rdi+8], rax
0x1400302da  mov     [rax], rdi
0x1400302dd  mov     [r14+8], rdi
0x1400302e1  call    cs:__imp_DbgPrint
0x1400302e8  nop     dword ptr [rax+rax+00h]
0x1400302ed  mov     edi, [rsp+158h+var_124]
0x1400302f1  jmp     loc_140030509
0x1400302f6  mov     [rax+30h], r15
0x1400302fa  lea     rdx, [rsp+158h+Src]
0x140030302  mov     rax, [rsp+158h+var_F8]
0x140030307  mov     rcx, r12
0x14003030a  mov     [rbx+70h], rax
0x14003030e  mov     eax, [rsp+158h+var_120]
0x140030312  mov     [rbx+20h], eax
0x140030315  mov     rax, [rsp+158h+var_110]
0x14003031a  mov     eax, [rax+120h]
0x140030320  mov     [r12], eax
0x140030324  mov     eax, [rsp+158h+var_128]
0x140030328  mov     [r12+0Ch], eax
0x14003032d  call    BuildLinkHeader
0x140030332  mov     r8d, [rsp+158h+var_11C]
0x140030337  mov     r10, [rsp+158h+var_100]
0x14003033c  mov     r11d, [rsp+158h+var_118]
0x140030341  mov     rdx, [rsp+158h+var_110]
0x140030346  mov     r15d, 1
0x14003034c  cmp     ebp, r15d
0x14003034f  jbe     short loc_140030393
0x140030351  mov     ecx, r11d
0x140030354  mov     eax, 51EB851Fh
0x140030359  imul    ecx, [rdx+0C0h]
0x140030360  mul     ecx
0x140030362  lea     rcx, [rsi+18h]
0x140030366  shr     edx, 5
0x140030369  test    dword ptr [r10+10h], 400h
0x140030371  jz      short loc_14003037D
0x140030373  mov     edi, [rsi+1Ch]
0x140030376  cmp     edx, edi
0x140030378  cmovbe  edi, edx
0x14003037b  jmp     short loc_140030385
0x14003037d  mov     edi, [rcx]
0x14003037f  cmp     edx, edi
0x140030381  jb      short loc_140030385
0x140030383  mov     edi, edx
0x140030385  cmp     edi, r13d
0x140030388  ja      short loc_140030393
0x14003038a  mov     eax, r13d
0x14003038d  sub     eax, edi
0x14003038f  cmp     eax, [rcx]
0x140030391  jnb     short loc_140030399
0x140030393  mov     ebp, r15d
0x140030396  mov     edi, r13d
0x140030399  mov     eax, r8d
0x14003039c  neg     eax
0x14003039e  sbb     cl, cl
0x1400303a0  and     cl, 80h
0x1400303a3  movzx   edx, cl
0x1400303a6  mov     al, dl
0x1400303a8  or      al, 40h
0x1400303aa  cmp     ebp, r15d
0x1400303ad  movzx   r9d, al
0x1400303b1  cmovnz  r9d, edx
0x1400303b5  cmp     dword ptr [r12+20h], 0
0x1400303bb  jz      short loc_140030421
0x1400303bd  mov     rcx, [r12+28h]
0x1400303c2  test    dword ptr [r12], 400h
0x1400303ca  mov     eax, [r10+60h]
0x1400303ce  lea     rdx, [rcx+1]
0x1400303d2  cmovnz  rdx, rcx
0x1400303d6  and     [rsi+14h], eax
0x1400303d9  mov     eax, [r12]
0x1400303dd  mov     r8d, [rsi+14h]
0x1400303e1  mov     cl, [r12+4]
0x1400303e6  test    al, 20h
0x1400303e8  jz      short loc_140030403
0x1400303ea  shr     r8d, 8
0x1400303ee  shl     cl, 4
0x1400303f1  or      r8b, cl
0x1400303f4  or      r8b, r9b
0x1400303f7  mov     [rdx+1], r8b
0x1400303fb  mov     al, [rsi+14h]
0x1400303fe  mov     [rdx+2], al
0x140030401  jmp     short loc_140030421
0x140030403  shl     cl, 2
0x140030406  or      cl, r9b
0x140030409  mov     [rdx+1], cl
0x14003040c  mov     al, [rsi+16h]
0x14003040f  mov     [rdx+2], al
0x140030412  mov     eax, [rsi+14h]
0x140030415  shr     eax, 8
0x140030418  mov     [rdx+3], al
0x14003041b  mov     al, [rsi+14h]
0x14003041e  mov     [rdx+4], al
0x140030421  mov     rcx, cs:WPP_GLOBAL_Control
0x140030428  lea     rax, WPP_GLOBAL_Control
0x14003042f  cmp     rcx, rax
0x140030432  jz      short loc_14003045C
0x140030434  test    dword ptr [rcx+2Ch], 1000h
0x14003043b  jz      short loc_14003045C
0x14003043d  cmp     byte ptr [rcx+29h], 4
0x140030441  jb      short loc_14003045C
0x140030443  mov     rcx, [rcx+18h]
0x140030447  movzx   eax, r9b
0x14003044b  mov     r9d, [rsi+14h]
0x14003044f  mov     [rsp+158h+var_130], edi
0x140030453  mov     [rsp+158h+var_138], eax
0x140030457  call    WPP_SF_DDd
0x14003045c  add     [rsi+14h], r15d
0x140030460  cmp     [rsp+158h+var_11C], 0
0x140030465  mov     r15d, edi
0x140030468  jnz     short loc_1400304A8
0x14003046a  mov     r8d, [r12+8]; Size
0x14003046f  lea     rdx, [rsp+158h+Src]; Src
0x140030477  mov     rcx, [rbx+58h]; void *
0x14003047b  call    memmove
0x140030480  mov     ecx, [r12+8]
0x140030485  mov     r8d, r15d; Size
0x140030488  add     rcx, [rbx+58h]; void *
0x14003048c  mov     rdx, [rsp+158h+var_108]; Src
0x140030491  call    memmove
0x140030496  mov     rax, [rsp+158h+var_F0]
0x14003049b  mov     r8d, 1
0x1400304a1  lock add [rax+28h], r8d
0x1400304a6  jmp     short loc_1400304B3
0x1400304a8  and     [rsp+158h+var_128], 0FFFFFFEFh
0x1400304ad  mov     r8d, 1
0x1400304b3  mov     eax, [r12+8]
0x1400304b8  or      [rbx+1Ch], r8d
0x1400304bc  mov     [rbx+60h], eax
0x1400304bf  mov     rax, [rbx+50h]
0x1400304c3  mov     [rbx+64h], edi
0x1400304c6  mov     edx, [r12+8]
0x1400304cb  add     edx, edi
0x1400304cd  mov     rcx, [rax+8]
0x1400304d1  mov     [rcx+18h], edx
0x1400304d4  mov     rax, [rsi+8]
0x1400304d8  cmp     [rax], rsi
0x1400304db  jnz     short loc_140030526
0x1400304dd  add     [rsp+158h+var_108], r15
0x1400304e2  sub     r13d, edi
0x1400304e5  mov     edi, [rsp+158h+var_124]
0x1400304e9  mov     r15, [rsp+158h+var_E8]
0x1400304ee  add     edi, r8d
0x1400304f1  mov     [rbx], rsi
0x1400304f4  mov     [rbx+8], rax
0x1400304f8  mov     [rax], rbx
0x1400304fb  mov     [rsi+8], rbx
0x1400304ff  add     [rsi+10h], r8d
0x140030503  mov     [rsp+158h+var_124], edi
0x140030507  dec     ebp
0x140030509  test    r13d, r13d
0x14003050c  jz      short loc_14003052D
0x14003050e  mov     r10, [rsp+158h+var_100]
0x140030513  mov     r11d, [rsp+158h+var_118]
0x140030518  mov     rdx, [rsp+158h+var_110]
0x14003051d  mov     ecx, [rsp+158h+var_128]
0x140030521  jmp     loc_140030239
0x140030526  mov     ecx, 3
0x14003052b  int     29h; Win8: RtlFailFast(ecx)
0x14003052d  mov     r9, [rsp+158h+var_E0]
0x140030532  lea     rax, [r9+r9*2]
0x140030536  shl     rax, 4
0x14003053a  lock add [rax+r15+98h], edi
0x140030543  mov     rcx, cs:WPP_GLOBAL_Control
0x14003054a  lea     rax, WPP_GLOBAL_Control
0x140030551  cmp     rcx, rax
0x140030554  jz      short loc_140030583
0x140030556  mov     eax, [rcx+2Ch]
0x140030559  test    al, 8
0x14003055b  jz      short loc_140030583
0x14003055d  cmp     byte ptr [rcx+29h], 5
0x140030561  jb      short loc_140030583
0x140030563  mov     eax, [rbx+18h]
0x140030566  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x14003056d  mov     r9, [rbx+70h]
0x140030571  mov     edx, 2Dh ; '-'
0x140030576  mov     rcx, [rcx+18h]
0x14003057a  mov     [rsp+158h+var_138], eax
0x14003057e  call    WPP_SF_qD
0x140030583  mov     rcx, [rsp+158h+var_58]
0x14003058b  xor     rcx, rsp; StackCookie
0x14003058e  call    __security_check_cookie
0x140030593  add     rsp, 118h
0x14003059a  pop     r15
0x14003059c  pop     r14
0x14003059e  pop     r13
0x1400305a0  pop     r12
0x1400305a2  pop     rdi
0x1400305a3  pop     rsi
0x1400305a4  pop     rbp
0x1400305a5  pop     rbx
0x1400305a6  retn
```
