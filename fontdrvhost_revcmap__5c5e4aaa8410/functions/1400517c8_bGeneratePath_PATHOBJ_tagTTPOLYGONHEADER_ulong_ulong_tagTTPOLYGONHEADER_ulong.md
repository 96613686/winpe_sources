# bGeneratePath(_PATHOBJ *,tagTTPOLYGONHEADER *,ulong,ulong *,tagTTPOLYGONHEADER *,ulong)

- ea: `0x1400517c8`
- end: `0x140051b53`
- name: `?bGeneratePath@@YAHPEAU_PATHOBJ@@PEAUtagTTPOLYGONHEADER@@KPEAK1K@Z`
- size: `907`
- prototype: `__int64 __usercall@<rax>(PATHOBJ *ppo@<rcx>, struct tagTTPOLYGONHEADER *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, struct tagTTPOLYGONHEADER *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140027fa4`
- `0x140029a44`

## callees

- `0x1400517c8`
- `0x140051b5c`
- `0x140051cc8`
- `0x140051d78`
- `0x140051e28`
- `0x140051ed4`
- `0x140075de0`
- `0x140076eea`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140051b3f`
- `KERNEL32!GlobalFree` at `0x140051b3f`
- `KERNEL32!GlobalAlloc` at `0x140051a9c`
- `KERNEL32!GlobalAlloc` at `0x140051a9c`

## pseudocode

```c
__int64 __fastcall bGeneratePath(
        PATHOBJ *ppo,
        POINTFIX *a2,
        unsigned int a3,
        unsigned int *a4,
        struct tagTTPOLYGONHEADER *a5,
        unsigned int a6)
{
  char *v6; // r15
  POINTFIX *v7; // rbx
  POINTFIX *v9; // rdx
  unsigned __int64 v10; // rdi
  POINTFIX *v12; // rax
  POINTFIX *v13; // rsi
  _WORD *v14; // r9
  unsigned int i; // ecx
  unsigned __int64 v16; // rax
  ULONG x_high; // ecx
  unsigned int v18; // r12d
  size_t v19; // rdx
  unsigned int v20; // r13d
  POINTFIX *p_pptfx; // r12
  unsigned int v22; // edx
  struct _POINTFIX *p_y; // rax
  unsigned int v24; // [rsp+20h] [rbp-118h]
  struct _POINTFIX *v25; // [rsp+28h] [rbp-110h]
  int v26; // [rsp+28h] [rbp-110h]
  _WORD *v27; // [rsp+30h] [rbp-108h]
  POINTFIX *v28; // [rsp+38h] [rbp-100h]
  __int64 v29; // [rsp+40h] [rbp-F8h]
  POINTFIX *v30; // [rsp+50h] [rbp-E8h]
  POINTFIX pptfx; // [rsp+60h] [rbp-D8h] BYREF

  v6 = 0;
  v7 = a2;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    v6 = (char *)a5 + a6;
  v9 = (POINTFIX *)((char *)a2 + a3);
  v28 = (POINTFIX *)((char *)v7 + a3);
  v10 = (unsigned __int64)a5 & -(__int64)(a5 != 0);
  while ( v7 < v9 )
  {
    if ( (unsigned __int64)((char *)v9 - (char *)v7) < 0x10 || a5 && (unsigned __int64)&v6[-v10] < 0x10 )
      return 0;
    if ( ppo )
    {
      if ( !PATHOBJ_bMoveTo(ppo, v7[1]) )
        return 0;
      v9 = v28;
    }
    v12 = (POINTFIX *)((char *)v7 + (unsigned int)v7->x);
    v25 = v7 + 1;
    v30 = v12;
    v13 = v7 + 2;
    v14 = (_WORD *)(v10 + 16);
    for ( i = 16; ; i = v18 + v24 )
    {
      v24 = i;
      v27 = v14;
      if ( v13 >= v12 )
        break;
      v16 = (char *)v9 - (char *)v13;
      if ( (unsigned __int64)((char *)v9 - (char *)v13) < 4 )
        return 0;
      x_high = HIWORD(v13->x);
      v18 = 8 * x_high + 4;
      v19 = v18;
      v29 = v18;
      if ( v16 < v18 )
        return 0;
      if ( LOWORD(v13->x) == 1 )
      {
        if ( ppo )
        {
          if ( !PATHOBJ_bPolyLineTo(ppo, (POINTFIX *)&v13->y, x_high) )
            return 0;
          v14 = v27;
          v19 = v18;
        }
        if ( a5 )
        {
          if ( v6 - (char *)v14 < v19 )
            return 0;
          memcpy_0(v14, v13, v19);
        }
      }
      else
      {
        v20 = x_high - 1;
        if ( x_high - 1 > 6 )
        {
          p_pptfx = (POINTFIX *)GlobalAlloc(0, 24LL * (x_high - 1));
          if ( !p_pptfx )
            return 0;
        }
        else
        {
          p_pptfx = &pptfx;
        }
        vQsplineToPolyBezier(v20, v25, (struct _POINTFIX *)&v13->y, p_pptfx);
        if ( !ppo || (v26 = 0, PATHOBJ_bPolyBezierTo(ppo, p_pptfx, 3 * v20)) )
          v26 = 1;
        v22 = 3 * v20;
        if ( a5 )
        {
          if ( v6 - (char *)v27 < (unsigned __int64)(24 * v20 + 4) )
            return 0;
          v27[1] = v22;
          *v27 = 3;
          memcpy_0(v27 + 2, p_pptfx, 8LL * v22);
        }
        if ( v20 > 6 )
          GlobalFree(p_pptfx);
        if ( !v26 )
          return 0;
        v18 = 24 * v20 + 4;
      }
      v9 = v28;
      p_y = (struct _POINTFIX *)&v13[HIWORD(v13->x) - 1].y;
      v13 = (POINTFIX *)((char *)v13 + v29);
      v25 = p_y;
      v14 = (_WORD *)((char *)v27 + v18);
      v12 = v30;
    }
    if ( ppo )
    {
      if ( !PATHOBJ_bPolyLineTo(ppo, v7 + 1, 1u) || !PATHOBJ_bCloseFigure(ppo) )
        return 0;
      i = v24;
    }
    if ( a4 )
      *a4 += i;
    if ( a5 )
    {
      if ( (unsigned __int64)&v6[-v10] < 0x10 )
        return 0;
      *(_DWORD *)(v10 + 4) = 24;
      *(_DWORD *)v10 = i;
      *(POINTFIX *)(v10 + 8) = v7[1];
    }
    v9 = v28;
    v7 = (POINTFIX *)((char *)v7 + (unsigned int)v7->x);
    v10 += i;
  }
  return 1;
}

```

## disassembly

```asm
0x1400517c8  mov     [rsp+arg_10], rbx
0x1400517cd  push    rbp
0x1400517ce  push    rsi
0x1400517cf  push    rdi
0x1400517d0  push    r12
0x1400517d2  push    r13
0x1400517d4  push    r14
0x1400517d6  push    r15
0x1400517d8  sub     rsp, 100h
0x1400517df  mov     rax, cs:__security_cookie
0x1400517e6  xor     rax, rsp
0x1400517e9  mov     [rsp+138h+var_48], rax
0x1400517f1  mov     rbp, [rsp+138h+arg_20]
0x1400517f9  xor     r15d, r15d
0x1400517fc  mov     [rsp+138h+var_E0], r9
0x140051801  mov     rbx, rdx
0x140051804  mov     r14, rcx
0x140051807  test    r9, r9
0x14005180a  jnz     loc_140051B24
0x140051810  test    rbp, rbp
0x140051813  jnz     loc_140051B2C
0x140051819  mov     edx, r8d
0x14005181c  mov     rax, rbp
0x14005181f  add     rdx, rbx
0x140051822  neg     rax
0x140051825  mov     [rsp+138h+var_100], rdx
0x14005182a  sbb     rdi, rdi
0x14005182d  and     rdi, rbp
0x140051830  mov     r8d, 1
0x140051836  cmp     rbx, rdx
0x140051839  jnb     loc_140051A8C
0x14005183f  mov     rax, rdx
0x140051842  sub     rax, rbx
0x140051845  cmp     rax, 10h
0x140051849  jnb     short loc_140051878
0x14005184b  xor     eax, eax
0x14005184d  mov     rcx, [rsp+138h+var_48]
0x140051855  xor     rcx, rsp; StackCookie
0x140051858  call    __security_check_cookie
0x14005185d  mov     rbx, [rsp+138h+arg_10]
0x140051865  add     rsp, 100h
0x14005186c  pop     r15
0x14005186e  pop     r14
0x140051870  pop     r13
0x140051872  pop     r12
0x140051874  pop     rdi
0x140051875  pop     rsi
0x140051876  pop     rbp
0x140051877  retn
0x140051878  test    rbp, rbp
0x14005187b  jnz     loc_140051AB3
0x140051881  test    r14, r14
0x140051884  jz      short loc_1400518A1
0x140051886  mov     rdx, [rbx+8]; ptfx
0x14005188a  mov     rcx, r14; ppo
0x14005188d  call    PATHOBJ_bMoveTo
0x140051892  test    eax, eax
0x140051894  jz      short loc_14005184B
0x140051896  mov     rdx, [rsp+138h+var_100]
0x14005189b  mov     r8d, 1; cptfx
0x1400518a1  mov     eax, [rbx]
0x1400518a3  lea     r10, [rbx+8]
0x1400518a7  add     rax, rbx
0x1400518aa  mov     [rsp+138h+var_110], r10
0x1400518af  mov     [rsp+138h+var_E8], rax
0x1400518b4  lea     rsi, [rbx+10h]
0x1400518b8  lea     r9, [rdi+10h]
0x1400518bc  mov     ecx, 10h
0x1400518c1  mov     [rsp+138h+var_118], ecx
0x1400518c5  mov     [rsp+138h+var_108], r9
0x1400518ca  cmp     rsi, rax
0x1400518cd  jnb     loc_140051A31
0x1400518d3  mov     rax, rdx
0x1400518d6  sub     rax, rsi
0x1400518d9  cmp     rax, 4
0x1400518dd  jb      loc_14005184B
0x1400518e3  movzx   ecx, word ptr [rsi+2]
0x1400518e7  lea     r12d, ds:4[rcx*8]
0x1400518ef  mov     edx, r12d
0x1400518f2  mov     [rsp+138h+var_F8], rdx
0x1400518f7  cmp     rax, rdx
0x1400518fa  jb      loc_14005184B
0x140051900  cmp     [rsi], r8w
0x140051904  jz      loc_1400519E4
0x14005190a  lea     r13d, [rcx-1]
0x14005190e  lea     eax, ds:0[r13*2]
0x140051916  add     eax, r13d
0x140051919  cmp     r13d, 6
0x14005191d  ja      loc_140051A94
0x140051923  lea     r12, [rsp+138h+pptfx]
0x140051928  mov     rdx, [rsp+138h+var_110]; struct _POINTFIX *
0x14005192d  lea     r8, [rsi+4]; struct _POINTFIX *
0x140051931  mov     r9, r12; struct _POINTFIX *
0x140051934  mov     ecx, r13d; unsigned int
0x140051937  call    ?vQsplineToPolyBezier@@YAXKPEAU_POINTFIX@@00@Z; vQsplineToPolyBezier(ulong,_POINTFIX *,_POINTFIX *,_POINTFIX *)
0x14005193c  test    r14, r14
0x14005193f  jz      short loc_140051963
0x140051941  lea     r8d, ds:0[r13*2]
0x140051949  mov     rdx, r12; pptfx
0x14005194c  add     r8d, r13d; cptfx
0x14005194f  mov     rcx, r14; ppo
0x140051952  call    PATHOBJ_bPolyBezierTo
0x140051957  mov     dword ptr [rsp+138h+var_110], 0
0x14005195f  test    eax, eax
0x140051961  jz      short loc_14005196B
0x140051963  mov     dword ptr [rsp+138h+var_110], 1
0x14005196b  lea     edx, ds:0[r13*2]
0x140051973  add     edx, r13d
0x140051976  lea     eax, ds:4[rdx*8]
0x14005197d  mov     dword ptr [rsp+138h+var_F0], eax
0x140051981  test    rbp, rbp
0x140051984  jnz     loc_140051AC8
0x14005198a  cmp     r13d, 6
0x14005198e  ja      loc_140051B3C
0x140051994  cmp     dword ptr [rsp+138h+var_110], 0
0x140051999  jz      loc_14005184B
0x14005199f  mov     r12, [rsp+138h+var_F0]
0x1400519a4  movzx   eax, word ptr [rsi+2]
0x1400519a8  mov     r8d, 1
0x1400519ae  mov     r9, [rsp+138h+var_108]
0x1400519b3  mov     ecx, [rsp+138h+var_118]
0x1400519b7  mov     rdx, [rsp+138h+var_100]
0x1400519bc  lea     rax, ds:0FFFFFFFFFFFFFFFCh[rax*8]
0x1400519c4  add     rax, rsi
0x1400519c7  add     rsi, [rsp+138h+var_F8]
0x1400519cc  mov     [rsp+138h+var_110], rax
0x1400519d1  mov     eax, r12d
0x1400519d4  add     r9, rax
0x1400519d7  mov     rax, [rsp+138h+var_E8]
0x1400519dc  add     ecx, r12d
0x1400519df  jmp     loc_1400518C1
0x1400519e4  test    r14, r14
0x1400519e7  jz      short loc_140051A0A
0x1400519e9  mov     r8d, ecx; cptfx
0x1400519ec  lea     rdx, [rsi+4]; pptfx
0x1400519f0  mov     rcx, r14; ppo
0x1400519f3  call    PATHOBJ_bPolyLineTo
0x1400519f8  test    eax, eax
0x1400519fa  jz      loc_14005184B
0x140051a00  mov     r9, [rsp+138h+var_108]
0x140051a05  mov     rdx, [rsp+138h+var_F8]
0x140051a0a  test    rbp, rbp
0x140051a0d  jz      short loc_1400519A4
0x140051a0f  mov     rax, r15
0x140051a12  sub     rax, r9
0x140051a15  cmp     rax, rdx
0x140051a18  jb      loc_14005184B
0x140051a1e  mov     r8, rdx; Size
0x140051a21  mov     rcx, r9; void *
0x140051a24  mov     rdx, rsi; Src
0x140051a27  call    memcpy_0
0x140051a2c  jmp     loc_1400519A4
0x140051a31  lea     rsi, [rbx+8]
0x140051a35  test    r14, r14
0x140051a38  jz      short loc_140051A61
0x140051a3a  mov     rdx, rsi; pptfx
0x140051a3d  mov     rcx, r14; ppo
0x140051a40  call    PATHOBJ_bPolyLineTo
0x140051a45  test    eax, eax
0x140051a47  jz      loc_14005184B
0x140051a4d  mov     rcx, r14; ppo
0x140051a50  call    PATHOBJ_bCloseFigure
0x140051a55  test    eax, eax
0x140051a57  jz      loc_14005184B
0x140051a5d  mov     ecx, [rsp+138h+var_118]
0x140051a61  mov     r12, [rsp+138h+var_E0]
0x140051a66  test    r12, r12
0x140051a69  jnz     loc_140051B4A
0x140051a6f  test    rbp, rbp
0x140051a72  jnz     loc_140051AFF
0x140051a78  mov     eax, [rbx]
0x140051a7a  mov     rdx, [rsp+138h+var_100]
0x140051a7f  add     rbx, rax
0x140051a82  mov     eax, ecx
0x140051a84  add     rdi, rax
0x140051a87  jmp     loc_140051830
0x140051a8c  mov     eax, r8d
0x140051a8f  jmp     loc_14005184D
0x140051a94  mov     edx, eax
0x140051a96  xor     ecx, ecx; uFlags
0x140051a98  shl     rdx, 3; dwBytes
0x140051a9c  call    cs:__imp_GlobalAlloc
0x140051aa2  mov     r12, rax
0x140051aa5  test    rax, rax
0x140051aa8  jnz     loc_140051928
0x140051aae  jmp     loc_14005184B
0x140051ab3  mov     rax, r15
0x140051ab6  sub     rax, rdi
0x140051ab9  cmp     rax, 10h
0x140051abd  jb      loc_14005184B
0x140051ac3  jmp     loc_140051881
0x140051ac8  mov     r9, [rsp+138h+var_108]
0x140051acd  mov     rcx, r15
0x140051ad0  sub     rcx, r9
0x140051ad3  cmp     rcx, rax
0x140051ad6  jb      loc_14005184B
0x140051adc  mov     r8d, edx
0x140051adf  lea     rcx, [r9+4]; void *
0x140051ae3  mov     [r9+2], dx
0x140051ae8  mov     rdx, r12; Src
0x140051aeb  shl     r8, 3; Size
0x140051aef  mov     word ptr [r9], 3
0x140051af5  call    memcpy_0
0x140051afa  jmp     loc_14005198A
0x140051aff  mov     rax, r15
0x140051b02  sub     rax, rdi
0x140051b05  cmp     rax, 10h
0x140051b09  jb      loc_14005184B
0x140051b0f  mov     dword ptr [rdi+4], 18h
0x140051b16  mov     [rdi], ecx
0x140051b18  mov     rax, [rsi]
0x140051b1b  mov     [rdi+8], rax
0x140051b1f  jmp     loc_140051A78
0x140051b24  mov     [r9], r15d
0x140051b27  jmp     loc_140051810
0x140051b2c  mov     r15d, [rsp+138h+arg_28]
0x140051b34  add     r15, rbp
0x140051b37  jmp     loc_140051819
0x140051b3c  mov     rcx, r12; hMem
0x140051b3f  call    cs:__imp_GlobalFree
0x140051b45  jmp     loc_140051994
0x140051b4a  add     [r12], ecx
0x140051b4e  jmp     loc_140051A6F
```
