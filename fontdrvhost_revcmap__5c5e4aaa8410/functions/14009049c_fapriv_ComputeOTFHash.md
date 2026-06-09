# fapriv_ComputeOTFHash

- ea: `0x14009049c`
- end: `0x140090856`
- name: `fapriv_ComputeOTFHash`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008f8cc`

## callees

- `0x14008fc14`
- `0x140090440`
- `0x14009049c`
- `0x14009085c`
- `0x14009087c`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall fapriv_ComputeOTFHash(_QWORD *a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  __int64 v4; // r14
  unsigned int v8; // ebp
  __int64 v9; // r15
  __int64 v11; // rdi
  unsigned int v12; // ebx
  __int64 (__fastcall *v13)(_QWORD, __int64); // rax
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // r14
  __int64 v17; // rbx
  int v18; // r13d
  unsigned int v19; // eax
  unsigned int v20; // r14d
  unsigned int v21; // r13d
  unsigned int v22; // eax
  unsigned int i; // r14d
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int j; // r14d
  unsigned int v27; // [rsp+30h] [rbp-58h]
  int v28; // [rsp+34h] [rbp-54h]
  __int128 v29; // [rsp+38h] [rbp-50h] BYREF
  __int64 v30; // [rsp+48h] [rbp-40h]
  unsigned int v31; // [rsp+90h] [rbp+8h]
  unsigned int v35; // [rsp+B0h] [rbp+28h]

  v29 = 0;
  v30 = 0;
  v4 = a4;
  v8 = 4096;
  while ( 1 )
  {
    v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD))a1[5])(*a1, v8);
    if ( v9 )
      break;
    v8 -= 512;
    if ( v8 <= 0x200 )
      return 4294967293LL;
  }
  v11 = 0;
  if ( !a3[3] || !a3[4] )
  {
    v12 = -4;
    goto LABEL_44;
  }
  if ( (unsigned int)otfNav_GetOTFTableDirectory(a1, a2, &v29)
    || ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))a1[3])(*a1, a2, 0, 0) )
  {
    v12 = -2;
    goto LABEL_44;
  }
  v13 = (__int64 (__fastcall *)(_QWORD, __int64))a1[5];
  if ( !v13 )
  {
    v12 = -6;
    goto LABEL_14;
  }
  v14 = v13(0, 96);
  v11 = v14;
  if ( !v14 )
  {
    v12 = -5;
    goto LABEL_14;
  }
  *(_DWORD *)v14 = 1732584193;
  v15 = 0;
  *(_DWORD *)(v14 + 4) = -271733879;
  *(_DWORD *)(v14 + 8) = -1732584194;
  *(_DWORD *)(v14 + 12) = 271733878;
  *(_DWORD *)(v14 + 16) = -1009589776;
  *(_QWORD *)(v14 + 20) = 0;
  *(_DWORD *)(v14 + 92) = 0;
  while ( 1 )
  {
    v35 = v15;
    if ( v15 >= WORD2(v29) )
      break;
    v16 = v30;
    v17 = 16LL * v15;
    if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))a1[3])(
           *a1,
           a2,
           *(unsigned int *)(v17 + v30 + 8),
           0) )
    {
      goto LABEL_42;
    }
    if ( *(_DWORD *)(v17 + v16) == 541476419 )
    {
      v18 = *(_DWORD *)(v17 + v16 + 12);
      v28 = a3[6];
      v19 = (a3[5] - *(_DWORD *)(v17 + v16 + 8)) / v8;
      v27 = a3[5] - *(_DWORD *)(v17 + v16 + 8);
      v20 = 0;
      v31 = v19;
      while ( v20 < v19 )
      {
        v12 = ReadAndHash((_DWORD)a1, a2, v9, v8, v11);
        if ( v12 )
          goto LABEL_43;
        v19 = v31;
        ++v20;
      }
      if ( v27 % v8 )
      {
        v12 = ReadAndHash((_DWORD)a1, a2, v9, v27 % v8, v11);
        if ( v12 )
          goto LABEL_43;
      }
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))a1[3])(
             *a1,
             a2,
             (unsigned int)(a3[5] + a3[6]),
             0) )
      {
        goto LABEL_42;
      }
      v21 = v18 - v28 - v27;
      v22 = v21 / v8;
      for ( i = 0; i < v22; ++i )
      {
        v12 = ReadAndHash((_DWORD)a1, a2, v9, v8, v11);
        if ( v12 )
          goto LABEL_43;
        v22 = v21 / v8;
      }
    }
    else
    {
      if ( *(_DWORD *)(v17 + v16) == 1684104552 )
      {
        if ( *(_DWORD *)(v17 + v16 + 12) >= v8
          || ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, __int64, __int64))a1[1])(
               *a1,
               v9,
               *(unsigned int *)(v17 + v16 + 12),
               1,
               a2) != 1 )
        {
LABEL_42:
          v12 = -2;
LABEL_43:
          v4 = a4;
          goto LABEL_44;
        }
        *(_DWORD *)(v9 + 8) = 0;
        v24 = fapriv_HashUpdate(v11, v9, *(unsigned int *)(v17 + v16 + 12));
        goto LABEL_40;
      }
      v21 = *(_DWORD *)(v17 + v16 + 12);
      v25 = v21 / v8;
      for ( j = 0; j < v25; ++j )
      {
        v12 = ReadAndHash((_DWORD)a1, a2, v9, v8, v11);
        if ( v12 )
          goto LABEL_43;
        v25 = v21 / v8;
      }
    }
    if ( !(v21 % v8) )
      goto LABEL_41;
    v24 = ReadAndHash((_DWORD)a1, a2, v9, v21 % v8, v11);
LABEL_40:
    v12 = v24;
    if ( v24 )
      goto LABEL_43;
LABEL_41:
    v15 = v35 + 1;
  }
  v4 = a4;
  v12 = fapriv_HashFinalize(v11, a1, a4);
LABEL_14:
  v11 = 0;
LABEL_44:
  if ( v30 )
    ((void (__fastcall *)(_QWORD))a1[6])(*a1);
  if ( v11 )
    fapriv_HashFinalize(v11, a1, v4);
  ((void (__fastcall *)(_QWORD, __int64))a1[6])(*a1, v9);
  return v12;
}

```

## disassembly

```asm
0x14009049c  mov     r11, rsp
0x14009049f  mov     [r11+10h], rbx
0x1400904a3  mov     [r11+20h], r9
0x1400904a7  mov     [r11+18h], r8
0x1400904ab  push    rbp
0x1400904ac  push    rsi
0x1400904ad  push    rdi
0x1400904ae  push    r12
0x1400904b0  push    r13
0x1400904b2  push    r14
0x1400904b4  push    r15
0x1400904b6  sub     rsp, 50h
0x1400904ba  xorps   xmm0, xmm0
0x1400904bd  xor     eax, eax
0x1400904bf  movups  [rsp+88h+var_50], xmm0
0x1400904c4  mov     [r11-40h], rax
0x1400904c8  mov     r14, r9
0x1400904cb  mov     rbx, r8
0x1400904ce  mov     r12, rdx
0x1400904d1  mov     rsi, rcx
0x1400904d4  mov     ebp, 1000h
0x1400904d9  mov     rcx, [rsi]
0x1400904dc  mov     rax, [rsi+28h]
0x1400904e0  mov     edx, ebp
0x1400904e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400904e7  mov     r15, rax
0x1400904ea  test    rax, rax
0x1400904ed  jnz     short loc_140090506
0x1400904ef  add     ebp, 0FFFFFE00h
0x1400904f5  cmp     ebp, 200h
0x1400904fb  ja      short loc_1400904D9
0x1400904fd  lea     eax, [r15-3]
0x140090501  jmp     loc_14009081A
0x140090506  xor     edi, edi
0x140090508  cmp     [rbx+0Ch], edi
0x14009050b  jz      loc_14009084F
0x140090511  cmp     [rbx+10h], edi
0x140090514  jz      loc_14009084F
0x14009051a  lea     r8, [rsp+88h+var_50]
0x14009051f  mov     rdx, r12
0x140090522  mov     rcx, rsi
0x140090525  call    otfNav_GetOTFTableDirectory
0x14009052a  test    eax, eax
0x14009052c  jz      short loc_140090538
0x14009052e  mov     ebx, 0FFFFFFFEh
0x140090533  jmp     loc_1400907E0
0x140090538  mov     rcx, [rsi]
0x14009053b  xor     r9d, r9d
0x14009053e  mov     rax, [rsi+18h]
0x140090542  xor     r8d, r8d
0x140090545  mov     rdx, r12
0x140090548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009054d  test    eax, eax
0x14009054f  jnz     short loc_14009052E
0x140090551  mov     rax, [rsi+28h]
0x140090555  test    rax, rax
0x140090558  jnz     short loc_14009055F
0x14009055a  lea     ebx, [rax-6]
0x14009055d  jmp     short loc_140090576
0x14009055f  mov     edx, 60h ; '`'
0x140090564  xor     ecx, ecx
0x140090566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009056b  mov     rdi, rax
0x14009056e  test    rax, rax
0x140090571  jnz     short loc_14009057D
0x140090573  lea     ebx, [rax-5]
0x140090576  xor     edi, edi
0x140090578  jmp     loc_1400907E0
0x14009057d  mov     dword ptr [rax], 67452301h
0x140090583  xor     ecx, ecx
0x140090585  mov     dword ptr [rax+4], 0EFCDAB89h
0x14009058c  mov     dword ptr [rax+8], 98BADCFEh
0x140090593  mov     dword ptr [rax+0Ch], 10325476h
0x14009059a  mov     dword ptr [rax+10h], 0C3D2E1F0h
0x1400905a1  mov     qword ptr [rax+14h], 0
0x1400905a9  mov     dword ptr [rax+5Ch], 0
0x1400905b0  movzx   eax, word ptr [rsp+88h+var_50+4]
0x1400905b5  mov     [rsp+88h+arg_20], ecx
0x1400905bc  cmp     ecx, eax
0x1400905be  jnb     loc_140090832
0x1400905c4  mov     r14, [rsp+88h+var_40]
0x1400905c9  xor     r9d, r9d
0x1400905cc  mov     rax, [rsi+18h]
0x1400905d0  mov     rdx, r12
0x1400905d3  mov     ebx, ecx
0x1400905d5  mov     rcx, [rsi]
0x1400905d8  shl     rbx, 4
0x1400905dc  mov     r8d, [rbx+r14+8]
0x1400905e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400905e6  test    eax, eax
0x1400905e8  jnz     loc_1400907D3
0x1400905ee  cmp     dword ptr [rbx+r14], 20464643h
0x1400905f6  jnz     loc_140090705
0x1400905fc  mov     rax, [rsp+88h+arg_10]
0x140090604  xor     edx, edx
0x140090606  mov     r13d, [rbx+r14+0Ch]
0x14009060b  mov     ecx, [rax+14h]
0x14009060e  sub     ecx, [rbx+r14+8]
0x140090613  mov     eax, [rax+18h]
0x140090616  mov     [rsp+88h+var_54], eax
0x14009061a  mov     eax, ecx
0x14009061c  div     ebp
0x14009061e  mov     [rsp+88h+var_58], ecx
0x140090622  xor     r14d, r14d
0x140090625  mov     [rsp+88h+arg_0], eax
0x14009062c  cmp     r14d, eax
0x14009062f  jnb     short loc_14009065D
0x140090631  mov     r9d, ebp
0x140090634  mov     [rsp+88h+var_68], rdi
0x140090639  mov     r8, r15
0x14009063c  mov     rdx, r12
0x14009063f  mov     rcx, rsi
0x140090642  call    ReadAndHash
0x140090647  mov     ebx, eax
0x140090649  test    eax, eax
0x14009064b  jnz     loc_1400907D8
0x140090651  mov     eax, [rsp+88h+arg_0]
0x140090658  inc     r14d
0x14009065b  jmp     short loc_14009062C
0x14009065d  mov     r14d, [rsp+88h+var_58]
0x140090662  xor     edx, edx
0x140090664  mov     eax, r14d
0x140090667  div     ebp
0x140090669  test    edx, edx
0x14009066b  jz      short loc_14009068D
0x14009066d  mov     r9d, edx
0x140090670  mov     [rsp+88h+var_68], rdi
0x140090675  mov     rdx, r12
0x140090678  mov     r8, r15
0x14009067b  mov     rcx, rsi
0x14009067e  call    ReadAndHash
0x140090683  mov     ebx, eax
0x140090685  test    eax, eax
0x140090687  jnz     loc_1400907D8
0x14009068d  mov     rbx, [rsp+88h+arg_10]
0x140090695  xor     r9d, r9d
0x140090698  mov     rcx, [rsi]
0x14009069b  mov     rdx, r12
0x14009069e  mov     rax, [rsi+18h]
0x1400906a2  mov     r8d, [rbx+18h]
0x1400906a6  add     r8d, [rbx+14h]
0x1400906aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400906af  test    eax, eax
0x1400906b1  jnz     loc_1400907D3
0x1400906b7  sub     r13d, [rsp+88h+var_54]
0x1400906bc  xor     edx, edx
0x1400906be  sub     r13d, r14d
0x1400906c1  mov     eax, r13d
0x1400906c4  div     ebp
0x1400906c6  xor     r14d, r14d
0x1400906c9  mov     [rsp+88h+arg_0], eax
0x1400906d0  cmp     r14d, eax
0x1400906d3  jnb     loc_14009079E
0x1400906d9  mov     r9d, ebp
0x1400906dc  mov     [rsp+88h+var_68], rdi
0x1400906e1  mov     r8, r15
0x1400906e4  mov     rdx, r12
0x1400906e7  mov     rcx, rsi
0x1400906ea  call    ReadAndHash
0x1400906ef  mov     ebx, eax
0x1400906f1  test    eax, eax
0x1400906f3  jnz     loc_1400907D8
0x1400906f9  mov     eax, [rsp+88h+arg_0]
0x140090700  inc     r14d
0x140090703  jmp     short loc_1400906D0
0x140090705  cmp     dword ptr [rbx+r14], 64616568h
0x14009070d  jnz     short loc_14009075B
0x14009070f  cmp     [rbx+r14+0Ch], ebp
0x140090714  jnb     loc_1400907D3
0x14009071a  mov     r8d, [rbx+r14+0Ch]
0x14009071f  mov     r9d, 1
0x140090725  mov     rcx, [rsi]
0x140090728  mov     rdx, r15
0x14009072b  mov     rax, [rsi+8]
0x14009072f  mov     [rsp+88h+var_68], r12
0x140090734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090739  cmp     rax, 1
0x14009073d  jnz     loc_1400907D3
0x140090743  xor     eax, eax
0x140090745  mov     rdx, r15
0x140090748  mov     [r15+8], eax
0x14009074c  mov     rcx, rdi
0x14009074f  mov     r8d, [rbx+r14+0Ch]
0x140090754  call    fapriv_HashUpdate
0x140090759  jmp     short loc_1400907BF
0x14009075b  mov     r13d, [rbx+r14+0Ch]
0x140090760  xor     edx, edx
0x140090762  mov     eax, r13d
0x140090765  div     ebp
0x140090767  xor     r14d, r14d
0x14009076a  mov     [rsp+88h+arg_0], eax
0x140090771  cmp     r14d, eax
0x140090774  jnb     short loc_14009079E
0x140090776  mov     r9d, ebp
0x140090779  mov     [rsp+88h+var_68], rdi
0x14009077e  mov     r8, r15
0x140090781  mov     rdx, r12
0x140090784  mov     rcx, rsi
0x140090787  call    ReadAndHash
0x14009078c  mov     ebx, eax
0x14009078e  test    eax, eax
0x140090790  jnz     short loc_1400907D8
0x140090792  mov     eax, [rsp+88h+arg_0]
0x140090799  inc     r14d
0x14009079c  jmp     short loc_140090771
0x14009079e  xor     edx, edx
0x1400907a0  mov     eax, r13d
0x1400907a3  div     ebp
0x1400907a5  test    edx, edx
0x1400907a7  jz      short loc_1400907C5
0x1400907a9  mov     r9d, edx
0x1400907ac  mov     [rsp+88h+var_68], rdi
0x1400907b1  mov     rdx, r12
0x1400907b4  mov     r8, r15
0x1400907b7  mov     rcx, rsi
0x1400907ba  call    ReadAndHash
0x1400907bf  mov     ebx, eax
0x1400907c1  test    eax, eax
0x1400907c3  jnz     short loc_1400907D8
0x1400907c5  mov     ecx, [rsp+88h+arg_20]
0x1400907cc  inc     ecx
0x1400907ce  jmp     loc_1400905B0
0x1400907d3  mov     ebx, 0FFFFFFFEh
0x1400907d8  mov     r14, [rsp+88h+arg_18]
0x1400907e0  mov     rdx, [rsp+88h+var_40]
0x1400907e5  test    rdx, rdx
0x1400907e8  jz      short loc_1400907F6
0x1400907ea  mov     rcx, [rsi]
0x1400907ed  mov     rax, [rsi+30h]
0x1400907f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400907f6  test    rdi, rdi
0x1400907f9  jz      short loc_140090809
0x1400907fb  mov     r8, r14
0x1400907fe  mov     rdx, rsi
0x140090801  mov     rcx, rdi
0x140090804  call    fapriv_HashFinalize
0x140090809  mov     rcx, [rsi]
0x14009080c  mov     rdx, r15
0x14009080f  mov     rax, [rsi+30h]
0x140090813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140090818  mov     eax, ebx
0x14009081a  mov     rbx, [rsp+88h+arg_8]
0x140090822  add     rsp, 50h
0x140090826  pop     r15
0x140090828  pop     r14
0x14009082a  pop     r13
0x14009082c  pop     r12
0x14009082e  pop     rdi
0x14009082f  pop     rsi
0x140090830  pop     rbp
0x140090831  retn
0x140090832  mov     r14, [rsp+88h+arg_18]
0x14009083a  mov     rdx, rsi
0x14009083d  mov     r8, r14
0x140090840  mov     rcx, rdi
0x140090843  call    fapriv_HashFinalize
0x140090848  mov     ebx, eax
0x14009084a  jmp     loc_140090576
0x14009084f  mov     ebx, 0FFFFFFFCh
0x140090854  jmp     short loc_1400907E0
```
