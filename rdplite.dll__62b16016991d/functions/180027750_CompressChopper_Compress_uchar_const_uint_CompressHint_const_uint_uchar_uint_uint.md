# CompressChopper::Compress(uchar const *,uint,_CompressHint const *,uint,uchar *,uint,uint *)

- ea: `0x180027750`
- end: `0x180027a65`
- name: `?Compress@CompressChopper@@UEAAJPEBEIPEBU_CompressHint@@IPEAEIPEAI@Z`
- size: `789`
- prototype: `__int64 __fastcall(CompressChopper *__hidden this, const unsigned __int8 *, unsigned int, const struct _CompressHint *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180027750`
- `0x18002a010`

## pseudocode

```c
Compress *__fastcall CompressChopper::Compress(
        Compress *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        const struct _CompressHint *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned int v9; // r10d
  unsigned int v11; // r11d
  int v12; // eax
  unsigned int v13; // edi
  int v15; // eax
  unsigned int v16; // r9d
  unsigned __int8 *v17; // rdx
  unsigned int v18; // ecx
  unsigned __int8 *v19; // r14
  unsigned int v20; // ebp
  int v21; // eax
  int v22; // r13d
  unsigned int v23; // esi
  unsigned int *v24; // r12
  __int64 v25; // rdx
  unsigned int v26; // ebx
  unsigned int v27; // ebp
  bool v28; // cc
  unsigned int v29; // r11d
  unsigned int v30; // edx
  int v31; // eax
  const struct _CompressHint *v32; // r12
  __int64 v33; // r14
  unsigned int v34; // edi
  unsigned int v35; // r10d
  unsigned int v36; // ecx
  unsigned int v37; // r13d
  unsigned int v38; // r9d
  unsigned int v39; // r9d
  __int64 v40; // rcx
  unsigned int v42; // [rsp+50h] [rbp-78h]
  unsigned int v43; // [rsp+54h] [rbp-74h]
  unsigned int v44; // [rsp+58h] [rbp-70h]
  int v45; // [rsp+5Ch] [rbp-6Ch]
  const unsigned __int8 *v46; // [rsp+68h] [rbp-60h]
  unsigned int *v47; // [rsp+70h] [rbp-58h]
  int v48; // [rsp+78h] [rbp-50h]
  unsigned int v49; // [rsp+D0h] [rbp+8h] BYREF
  const unsigned __int8 *v50; // [rsp+D8h] [rbp+10h]
  unsigned int v51; // [rsp+E0h] [rbp+18h]
  const struct _CompressHint *v52; // [rsp+E8h] [rbp+20h]

  v52 = a4;
  v51 = a3;
  v50 = a2;
  v9 = 0;
  v11 = (*((_DWORD *)this + 16) + a3 - 1) / *((_DWORD *)this + 16);
  v44 = 0;
  v12 = *((_DWORD *)this + 17);
  v13 = a3;
  v49 = 0;
  if ( v11 >= 2 )
    v15 = v11 * (v12 + 4) + 7;
  else
    v15 = v12 + 1;
  v16 = a7;
  if ( a7 < a3 + v15 || v11 > 0xFFFF )
  {
LABEL_34:
    v18 = -2147467259;
    goto LABEL_35;
  }
  if ( v11 >= 2 )
  {
    v19 = a6;
    v20 = a7 - 7;
    v21 = 0;
    v46 = a2;
    v22 = (int)a2;
    v43 = a3;
    v23 = a3;
    *a6 = -31;
    v24 = (unsigned int *)(v19 + 7);
    *(_DWORD *)(v19 + 3) = a3;
    while ( 1 )
    {
      v45 = v21;
      v47 = v24;
      if ( !v23 )
      {
        *(_WORD *)(v19 + 1) = v21;
        v9 = (_DWORD)v24 - (_DWORD)v19;
        v18 = 0;
        goto LABEL_35;
      }
      v25 = *((unsigned int *)this + 17);
      if ( v20 < (unsigned __int64)(v25 + 4) )
        goto LABEL_34;
      v26 = *((_DWORD *)this + 16);
      v27 = v20 - 4;
      if ( v23 >= 2 * v26 )
        goto LABEL_14;
      v28 = v23 <= v26;
      v26 = v23;
      if ( !v28 )
        break;
      v29 = v27;
LABEL_16:
      v30 = v22 - (_DWORD)v50;
      v31 = v22 - (_DWORD)v50;
      v42 = 0;
      v48 = v22 - (_DWORD)v50;
      if ( a5 )
      {
        v32 = v52;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        do
        {
          v36 = *((_DWORD *)v32 + 3 * v33);
          v37 = v36;
          if ( v36 <= v30 )
            v37 = v30;
          v38 = v36 + *((_DWORD *)v32 + 3 * v33 + 1);
          if ( v38 >= v26 + v30 )
            v38 = v26 + v30;
          if ( v38 > v37 )
          {
            v39 = v38 - v37;
            if ( v39 >= 0xA && v35 < 0x64 )
            {
              v40 = v35++;
              *((_DWORD *)this + 3 * v40 + 18) = v37 - v30;
              v40 *= 3;
              *((_DWORD *)this + v40 + 19) = v39;
              *((_DWORD *)this + v40 + 20) = *((_DWORD *)v32 + 3 * v33 + 2);
            }
          }
          ++v34;
          ++v33;
        }
        while ( v34 < a5 );
        v13 = v51;
        v23 = v43;
        v19 = a6;
        v24 = v47;
        v16 = a7;
        v31 = v48;
        v42 = v35;
        v9 = v44;
      }
      if ( v26 + v31 > v13 || v29 + (_DWORD)v24 + 4 - (_DWORD)v19 > v16 )
        goto LABEL_34;
      v18 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int8 *, _QWORD, char *, unsigned int, unsigned int *, unsigned int, unsigned int *))(**((_QWORD **)this + 7) + 48LL))(
              *((_QWORD *)this + 7),
              v46,
              v26,
              (char *)this + 72,
              v42,
              v24 + 1,
              v29,
              &v49);
      if ( v18 )
      {
        v9 = v49;
        goto LABEL_35;
      }
      v16 = a7;
      v23 -= v26;
      *v24 = v49;
      v9 = v49;
      v20 = v27 - v49;
      v46 += v26;
      HIWORD(v21) = HIWORD(v45);
      v24 = (unsigned int *)((char *)v24 + v49 + 4);
      v43 = v23;
      v22 = (int)v46;
      LOWORD(v21) = v45 + 1;
      v44 = v49;
    }
    v26 = v23 >> 1;
LABEL_14:
    v29 = v26 + v25;
    goto LABEL_16;
  }
  v17 = a6;
  *a6 = -32;
  v18 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int8 *, _QWORD, const struct _CompressHint *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *))(**((_QWORD **)this + 7) + 48LL))(
          *((_QWORD *)this + 7),
          a2,
          a3,
          a4,
          a5,
          v17 + 1,
          v16 - 1,
          &v49);
  v9 = v49 + 1;
LABEL_35:
  *a8 = v9;
  return (Compress *)v18;
}

```

## disassembly

```asm
0x180027750  mov     [rsp+arg_18], r9
0x180027755  mov     [rsp+arg_10], r8d
0x18002775a  mov     [rsp+arg_8], rdx
0x18002775f  push    rbx
0x180027760  push    rbp
0x180027761  push    rsi
0x180027762  push    rdi
0x180027763  push    r12
0x180027765  push    r13
0x180027767  push    r14
0x180027769  push    r15
0x18002776b  sub     rsp, 88h
0x180027772  mov     rbx, rdx
0x180027775  lea     eax, [r8-1]
0x180027779  add     eax, [rcx+40h]
0x18002777c  xor     edx, edx
0x18002777e  div     dword ptr [rcx+40h]
0x180027781  xor     r10d, r10d
0x180027784  mov     rsi, r9
0x180027787  mov     r11d, eax
0x18002778a  mov     [rsp+0C8h+var_70], r10d
0x18002778f  mov     eax, [rcx+44h]
0x180027792  mov     edi, r8d
0x180027795  mov     [rsp+0C8h+arg_0], r10d
0x18002779d  mov     r15, rcx
0x1800277a0  cmp     r11d, 2
0x1800277a4  jnb     short loc_1800277AA
0x1800277a6  inc     eax
0x1800277a8  jmp     short loc_1800277B4
0x1800277aa  add     eax, 4
0x1800277ad  imul    eax, r11d
0x1800277b1  add     eax, 7
0x1800277b4  mov     r9d, [rsp+0C8h+arg_30]
0x1800277bc  add     eax, edi
0x1800277be  cmp     r9d, eax
0x1800277c1  jb      loc_180027A3F
0x1800277c7  cmp     r11d, 0FFFFh
0x1800277ce  ja      loc_180027A3F
0x1800277d4  cmp     r11d, 2
0x1800277d8  jnb     short loc_180027839
0x1800277da  mov     rdx, [rsp+0C8h+arg_28]
0x1800277e2  lea     r8d, [r9-1]
0x1800277e6  lea     r9, [rsp+0C8h+arg_0]
0x1800277ee  mov     [rsp+0C8h+var_90], r9
0x1800277f3  mov     r9, rsi
0x1800277f6  mov     [rsp+0C8h+var_98], r8d
0x1800277fb  mov     r8d, edi
0x1800277fe  mov     byte ptr [rdx], 0E0h
0x180027801  inc     rdx
0x180027804  mov     rcx, [rcx+38h]
0x180027808  mov     [rsp+0C8h+var_A0], rdx
0x18002780d  mov     edx, [rsp+0C8h+arg_20]
0x180027814  mov     [rsp+0C8h+var_A8], edx
0x180027818  mov     rdx, rbx
0x18002781b  mov     rax, [rcx]
0x18002781e  mov     rax, [rax+30h]
0x180027822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027827  mov     r10d, [rsp+0C8h+arg_0]
0x18002782f  mov     ecx, eax
0x180027831  inc     r10d
0x180027834  jmp     loc_180027A44
0x180027839  mov     r14, [rsp+0C8h+arg_28]
0x180027841  lea     ebp, [r9-7]
0x180027845  xor     eax, eax
0x180027847  mov     [rsp+0C8h+var_60], rbx
0x18002784c  mov     r13, rbx
0x18002784f  mov     [rsp+0C8h+var_74], edi
0x180027853  mov     esi, edi
0x180027855  mov     byte ptr [r14], 0E1h
0x180027859  lea     r12, [r14+7]
0x18002785d  mov     [r14+3], edi
0x180027861  lea     r8d, [rax+1]
0x180027865  mov     [rsp+0C8h+var_6C], eax
0x180027869  mov     [rsp+0C8h+var_58], r12
0x18002786e  test    esi, esi
0x180027870  jz      loc_180027A30
0x180027876  mov     edx, [r15+44h]
0x18002787a  mov     eax, ebp
0x18002787c  lea     rcx, [rdx+4]
0x180027880  cmp     rax, rcx
0x180027883  jb      loc_180027A3F
0x180027889  mov     ebx, [r15+40h]
0x18002788d  add     ebp, 0FFFFFFFCh
0x180027890  lea     eax, [rbx+rbx]
0x180027893  cmp     esi, eax
0x180027895  jnb     short loc_18002789F
0x180027897  cmp     esi, ebx
0x180027899  mov     ebx, esi
0x18002789b  jbe     short loc_1800278A5
0x18002789d  shr     ebx, 1
0x18002789f  lea     r11d, [rbx+rdx]
0x1800278a3  jmp     short loc_1800278A8
0x1800278a5  mov     r11d, ebp
0x1800278a8  xor     ecx, ecx
0x1800278aa  mov     edx, r13d
0x1800278ad  sub     edx, dword ptr [rsp+0C8h+arg_8]
0x1800278b4  mov     eax, edx
0x1800278b6  mov     [rsp+0C8h+var_78], ecx
0x1800278ba  mov     qword ptr [rsp+0C8h+var_50], rax
0x1800278bf  cmp     [rsp+0C8h+arg_20], ecx
0x1800278c6  jbe     loc_18002797A
0x1800278cc  mov     r12, [rsp+0C8h+arg_18]
0x1800278d4  lea     esi, [rbx+rdx]
0x1800278d7  mov     r14d, ecx
0x1800278da  mov     edi, ecx
0x1800278dc  mov     r10d, ecx
0x1800278df  lea     rax, [r14+r14*2]
0x1800278e3  mov     ecx, [r12+rax*4]
0x1800278e7  mov     r13d, ecx
0x1800278ea  mov     r9d, [r12+rax*4+4]
0x1800278ef  cmp     ecx, edx
0x1800278f1  cmovbe  r13d, edx
0x1800278f5  add     r9d, ecx
0x1800278f8  cmp     r9d, esi
0x1800278fb  cmovnb  r9d, esi
0x1800278ff  cmp     r9d, r13d
0x180027902  jbe     short loc_18002793C
0x180027904  sub     r9d, r13d
0x180027907  cmp     r9d, 0Ah
0x18002790b  jb      short loc_18002793C
0x18002790d  cmp     r10d, 64h ; 'd'
0x180027911  jnb     short loc_18002793C
0x180027913  mov     ecx, r10d
0x180027916  sub     r13d, edx
0x180027919  add     r10d, r8d
0x18002791c  lea     rax, [rcx+rcx*2]
0x180027920  mov     [r15+rax*4+48h], r13d
0x180027925  lea     rcx, [rcx+rcx*2]
0x180027929  lea     rax, [r14+r14*2]
0x18002792d  mov     [r15+rcx*4+4Ch], r9d
0x180027932  mov     eax, [r12+rax*4+8]
0x180027937  mov     [r15+rcx*4+50h], eax
0x18002793c  add     edi, r8d
0x18002793f  add     r14, r8
0x180027942  cmp     edi, [rsp+0C8h+arg_20]
0x180027949  jb      short loc_1800278DF
0x18002794b  mov     edi, [rsp+0C8h+arg_10]
0x180027952  mov     esi, [rsp+0C8h+var_74]
0x180027956  mov     r14, [rsp+0C8h+arg_28]
0x18002795e  mov     r12, [rsp+0C8h+var_58]
0x180027963  mov     r9d, [rsp+0C8h+arg_30]
0x18002796b  mov     rax, qword ptr [rsp+0C8h+var_50]
0x180027970  mov     [rsp+0C8h+var_78], r10d
0x180027975  mov     r10d, [rsp+0C8h+var_70]
0x18002797a  add     eax, ebx
0x18002797c  cmp     eax, edi
0x18002797e  ja      loc_180027A3F
0x180027984  lea     r13, [r12+4]
0x180027989  mov     eax, r13d
0x18002798c  sub     eax, r14d
0x18002798f  add     eax, r11d
0x180027992  cmp     eax, r9d
0x180027995  ja      loc_180027A3F
0x18002799b  mov     rcx, [r15+38h]
0x18002799f  lea     rdx, [rsp+0C8h+arg_0]
0x1800279a7  mov     [rsp+0C8h+var_90], rdx
0x1800279ac  lea     r9, [r15+48h]
0x1800279b0  mov     edx, [rsp+0C8h+var_78]
0x1800279b4  mov     r8d, ebx
0x1800279b7  mov     [rsp+0C8h+var_98], r11d
0x1800279bc  mov     rax, [rcx]
0x1800279bf  mov     [rsp+0C8h+var_A0], r13
0x1800279c4  mov     [rsp+0C8h+var_A8], edx
0x1800279c8  mov     rdx, [rsp+0C8h+var_60]
0x1800279cd  mov     rax, [rax+30h]
0x1800279d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279d6  mov     ecx, eax
0x1800279d8  test    eax, eax
0x1800279da  jnz     short loc_180027A26
0x1800279dc  mov     eax, [rsp+0C8h+arg_0]
0x1800279e3  lea     r8d, [rcx+1]
0x1800279e7  mov     r9d, [rsp+0C8h+arg_30]
0x1800279ef  sub     esi, ebx
0x1800279f1  mov     [r12], eax
0x1800279f5  mov     r10d, [rsp+0C8h+arg_0]
0x1800279fd  mov     eax, ebx
0x1800279ff  sub     ebp, r10d
0x180027a02  add     [rsp+0C8h+var_60], rax
0x180027a07  mov     eax, [rsp+0C8h+var_6C]
0x180027a0b  lea     r12, [r10+r13]
0x180027a0f  mov     [rsp+0C8h+var_74], esi
0x180027a13  mov     r13, [rsp+0C8h+var_60]
0x180027a18  add     ax, r8w
0x180027a1c  mov     [rsp+0C8h+var_70], r10d
0x180027a21  jmp     loc_180027865
0x180027a26  mov     r10d, [rsp+0C8h+arg_0]
0x180027a2e  jmp     short loc_180027A44
0x180027a30  mov     r10d, r12d
0x180027a33  mov     [r14+1], ax
0x180027a38  sub     r10d, r14d
0x180027a3b  xor     ecx, ecx
0x180027a3d  jmp     short loc_180027A44
0x180027a3f  mov     ecx, 80004005h
0x180027a44  mov     rax, [rsp+0C8h+arg_38]
0x180027a4c  mov     [rax], r10d
0x180027a4f  mov     eax, ecx
0x180027a51  add     rsp, 88h
0x180027a58  pop     r15
0x180027a5a  pop     r14
0x180027a5c  pop     r13
0x180027a5e  pop     r12
0x180027a60  pop     rdi
0x180027a61  pop     rsi
0x180027a62  pop     rbp
0x180027a63  pop     rbx
0x180027a64  retn
```
