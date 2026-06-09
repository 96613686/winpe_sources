# CVoiceFilter::GetCoeff(__int64,long,ulong &,ulong &,ulong &)

- ea: `0x18000b1d0`
- end: `0x18000b4a8`
- name: `?GetCoeff@CVoiceFilter@@QEAAX_JJAEAK11@Z`
- size: `728`
- prototype: `void(CVoiceFilter *__hidden this, __int64, int, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c710`
- `0x18000d3b0`

## callees

- `0x18000b1d0`
- `0x18000b4b0`

## pseudocode

```c
void __fastcall CVoiceFilter::GetCoeff(
        CVoiceFilter *this,
        __int64 a2,
        int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int *v6; // rsi
  CVoiceFilter *v10; // r11
  unsigned int v11; // ecx
  unsigned int v12; // edx
  unsigned int v13; // r10d
  __int64 v14; // r8
  int v15; // edi
  int v16; // ecx
  int v17; // edx
  __int64 **v18; // rax
  __int64 *v19; // rcx
  int i; // edx
  int v21; // r9d
  __int64 **v22; // rax
  __int64 *v23; // rcx
  int j; // edx
  unsigned int v25; // edx
  int v26; // r9d
  __int64 v27; // rdx
  int v28; // eax
  int v29; // ebp
  __int64 v30; // rdi
  __int64 v31; // r8
  int v32; // r11d
  int v33; // r9d
  int v34; // r11d
  __int64 v35; // rax
  __int64 v36; // r8
  int v37; // r10d
  int v38; // ecx
  int v39; // r14d
  unsigned int v40; // ebp
  unsigned int v41; // edi
  unsigned int v42; // edx
  unsigned int *v43; // rax
  __int64 v44; // [rsp+40h] [rbp+8h] BYREF

  v6 = a5;
  v10 = this;
  if ( *((_WORD *)this + 1) == 0x7FFF )
  {
    v11 = 0;
    v12 = 0x40000000;
    v13 = 0;
  }
  else
  {
    v14 = *((_QWORD *)this + 2);
    v15 = *((__int16 *)this + 2);
    if ( *(_DWORD *)(v14 + 72) )
    {
      v18 = *(__int64 ***)(v14 + 64);
      v19 = *v18;
      for ( i = *((_DWORD *)v18 + 4); v19; v19 = (__int64 *)*v19 )
      {
        if ( v19[1] > a2 )
          break;
        i = *((_DWORD *)v19 + 4);
      }
      v21 = i * *(__int16 *)(v14 + 32) / 127;
      v22 = *(__int64 ***)(v14 + 48);
      v23 = *v22;
      for ( j = *((_DWORD *)v22 + 4); v23; v23 = (__int64 *)*v23 )
      {
        if ( v23[1] > a2 )
          break;
        j = *((_DWORD *)v23 + 4);
      }
      v25 = (int)((unsigned __int64)(2164392969LL * j * *(__int16 *)(v14 + 30)) >> 32) >> 6;
      v26 = *(__int16 *)(v14 + 28) + (v25 >> 31) + v25 + v21;
      v16 = 0;
      v27 = a2 - *(_QWORD *)(v14 + 40) - *(_QWORD *)(v14 + 8);
      if ( v27 >= 0 )
        v28 = *((__int16 *)&CVoiceLFO::m_snSineTable + (unsigned __int8)((unsigned int)(v27 * *(_DWORD *)v14) >> 16));
      else
        v28 = 0;
      v17 = v28 * v26 / 100;
    }
    else
    {
      v16 = 0;
      v17 = 0;
    }
    v29 = v17 + v15;
    v30 = *((_QWORD *)v10 + 3);
    if ( *(_DWORD *)(v30 + 72) && *(_WORD *)(v30 + 50) )
      v16 = (int)(CVoiceEG::GetLevel(*((CVoiceEG **)v10 + 3), a2, &v44, 0) * *(__int16 *)(v30 + 50)) / 1000;
    v31 = *((int *)v10 + 2);
    v32 = a3 + v16 + *((_DWORD *)v10 + 10) + *((_DWORD *)v10 + 11) + v29;
    if ( v32 < 0 || (v33 = v32 / 100, v32 / 100 < 0) )
    {
      v11 = *((_DWORD *)&CVoiceFilter::m_aB2 + 89 * v31);
      v13 = *((_DWORD *)&CVoiceFilter::m_aB1 + 89 * v31);
      v12 = *((_DWORD *)&CVoiceFilter::m_aK + 89 * v31);
    }
    else if ( v33 < 88 )
    {
      v34 = v32 % 100;
      v35 = v33 + 89 * v31;
      v36 = 4 * v35 + 4;
      v37 = *((_DWORD *)&CVoiceFilter::m_aB1 + v35);
      v38 = *((_DWORD *)&CVoiceFilter::m_aB2 + v35);
      v39 = *((_DWORD *)&CVoiceFilter::m_aK + v35);
      v40 = *(_DWORD *)((char *)&CVoiceFilter::m_aK + v36) - v39;
      v41 = v37 - *(_DWORD *)((char *)&CVoiceFilter::m_aB1 + v36);
      v42 = v38 - *(_DWORD *)((char *)&CVoiceFilter::m_aB2 + v36);
      if ( v33 < 84 )
      {
        v11 = v38 - v34 * v42 / 0x64;
        v13 = v37 - v34 * v41 / 0x64;
        v12 = v39 + v34 * v40 / 0x64;
      }
      else
      {
        v11 = v38 - v34 * (v42 >> 1) / 0x32;
        v13 = v37 - v34 * (v41 >> 1) / 0x32;
        v12 = v39 + v34 * (v40 >> 1) / 0x32;
      }
    }
    else
    {
      v11 = *((_DWORD *)&qword_180016CB8[43] + 89 * v31);
      v13 = *((_DWORD *)&qword_180019938[43] + 89 * v31);
      v12 = *((_DWORD *)&qword_1800182F8[43] + 89 * v31);
    }
  }
  v43 = a6;
  *a4 = v12;
  *v6 = v13;
  *v43 = v11;
}

```

## disassembly

```asm
0x18000b1d0  push    rbx
0x18000b1d2  push    rsi
0x18000b1d3  push    r14
0x18000b1d5  sub     rsp, 20h
0x18000b1d9  mov     rsi, [rsp+38h+arg_20]
0x18000b1de  mov     eax, 7FFFh
0x18000b1e3  mov     rbx, r9
0x18000b1e6  mov     r14d, r8d
0x18000b1e9  mov     r10, rdx
0x18000b1ec  mov     r11, rcx
0x18000b1ef  cmp     [rcx+2], ax
0x18000b1f3  jnz     short loc_18000B204
0x18000b1f5  xor     ecx, ecx
0x18000b1f7  mov     edx, 40000000h
0x18000b1fc  mov     r10d, ecx
0x18000b1ff  jmp     loc_18000B493
0x18000b204  mov     r8, [rcx+10h]
0x18000b208  mov     [rsp+38h+arg_8], rbp
0x18000b20d  mov     [rsp+38h+arg_10], rdi
0x18000b212  movsx   edi, word ptr [rcx+4]
0x18000b216  cmp     dword ptr [r8+48h], 0
0x18000b21b  mov     [rsp+38h+arg_18], r15
0x18000b220  lea     r15, cs:180000000h
0x18000b227  jnz     short loc_18000B232
0x18000b229  xor     ecx, ecx
0x18000b22b  mov     edx, ecx
0x18000b22d  jmp     loc_18000B2F8
0x18000b232  mov     rax, [r8+40h]
0x18000b236  mov     rcx, [rax]
0x18000b239  mov     edx, [rax+10h]
0x18000b23c  test    rcx, rcx
0x18000b23f  jz      short loc_18000B252
0x18000b241  cmp     [rcx+8], r10
0x18000b245  jg      short loc_18000B252
0x18000b247  mov     edx, [rcx+10h]
0x18000b24a  mov     rcx, [rcx]
0x18000b24d  test    rcx, rcx
0x18000b250  jnz     short loc_18000B241
0x18000b252  movsx   ecx, word ptr [r8+20h]
0x18000b257  mov     eax, 81020409h
0x18000b25c  imul    ecx, edx
0x18000b25f  imul    ecx
0x18000b261  lea     r9d, [rcx+rdx]
0x18000b265  sar     r9d, 6
0x18000b269  mov     eax, r9d
0x18000b26c  shr     eax, 1Fh
0x18000b26f  add     r9d, eax
0x18000b272  mov     rax, [r8+30h]
0x18000b276  mov     rcx, [rax]
0x18000b279  mov     edx, [rax+10h]
0x18000b27c  test    rcx, rcx
0x18000b27f  jz      short loc_18000B292
0x18000b281  cmp     [rcx+8], r10
0x18000b285  jg      short loc_18000B292
0x18000b287  mov     edx, [rcx+10h]
0x18000b28a  mov     rcx, [rcx]
0x18000b28d  test    rcx, rcx
0x18000b290  jnz     short loc_18000B281
0x18000b292  movsx   ecx, word ptr [r8+1Eh]
0x18000b297  mov     eax, 81020409h
0x18000b29c  imul    ecx, edx
0x18000b29f  imul    ecx
0x18000b2a1  add     edx, ecx
0x18000b2a3  movsx   ecx, word ptr [r8+1Ch]
0x18000b2a8  sar     edx, 6
0x18000b2ab  mov     eax, edx
0x18000b2ad  shr     eax, 1Fh
0x18000b2b0  add     edx, eax
0x18000b2b2  add     r9d, edx
0x18000b2b5  mov     rdx, r10
0x18000b2b8  sub     rdx, [r8+28h]
0x18000b2bc  add     r9d, ecx
0x18000b2bf  xor     ecx, ecx
0x18000b2c1  sub     rdx, [r8+8]
0x18000b2c5  jns     short loc_18000B2CB
0x18000b2c7  mov     eax, ecx
0x18000b2c9  jmp     short loc_18000B2E2
0x18000b2cb  mov     eax, [r8]
0x18000b2ce  imul    rax, rdx
0x18000b2d2  sar     rax, 10h
0x18000b2d6  movzx   eax, al
0x18000b2d9  movsx   eax, rva ?m_snSineTable@CVoiceLFO@@0PAFA[r15+rax*2]; short near * CVoiceLFO::m_snSineTable ...
0x18000b2e2  imul    r9d, eax
0x18000b2e6  mov     eax, 51EB851Fh
0x18000b2eb  imul    r9d
0x18000b2ee  sar     edx, 5
0x18000b2f1  mov     eax, edx
0x18000b2f3  shr     eax, 1Fh
0x18000b2f6  add     edx, eax
0x18000b2f8  lea     ebp, [rdx+rdi]
0x18000b2fb  mov     rdi, [r11+18h]
0x18000b2ff  cmp     dword ptr [rdi+48h], 0
0x18000b303  jz      short loc_18000B339
0x18000b305  cmp     word ptr [rdi+32h], 0
0x18000b30a  jz      short loc_18000B339
0x18000b30c  xor     r9d, r9d; int
0x18000b30f  lea     r8, [rsp+38h+arg_0]; __int64 *
0x18000b314  mov     rdx, r10; __int64
0x18000b317  mov     rcx, rdi; this
0x18000b31a  call    ?GetLevel@CVoiceEG@@AEAAJ_JPEA_JH@Z; CVoiceEG::GetLevel(__int64,__int64 *,int)
0x18000b31f  movsx   ecx, word ptr [rdi+32h]
0x18000b323  imul    ecx, eax
0x18000b326  mov     eax, 10624DD3h
0x18000b32b  imul    ecx
0x18000b32d  mov     ecx, edx
0x18000b32f  sar     ecx, 6
0x18000b332  mov     eax, ecx
0x18000b334  shr     eax, 1Fh
0x18000b337  add     ecx, eax
0x18000b339  mov     eax, [r11+2Ch]
0x18000b33d  movsxd  r8, dword ptr [r11+8]
0x18000b341  add     eax, [r11+28h]
0x18000b345  lea     r11d, [rax+rbp]
0x18000b349  add     r11d, ecx
0x18000b34c  mov     rcx, r8
0x18000b34f  add     r11d, r14d
0x18000b352  js      loc_18000B465
0x18000b358  mov     eax, 51EB851Fh
0x18000b35d  imul    r11d
0x18000b360  mov     r9d, edx
0x18000b363  sar     r9d, 5
0x18000b367  mov     eax, r9d
0x18000b36a  shr     eax, 1Fh
0x18000b36d  add     r9d, eax
0x18000b370  js      loc_18000B465
0x18000b376  cmp     r9d, 58h ; 'X'
0x18000b37a  jl      short loc_18000B3A0
0x18000b37c  imul    rax, rcx, 164h
0x18000b383  mov     ecx, [rax+r15+16E10h]
0x18000b38b  mov     r10d, [rax+r15+19A90h]
0x18000b393  mov     edx, [rax+r15+18450h]
0x18000b39b  jmp     loc_18000B484
0x18000b3a0  imul    rdx, rcx, 59h ; 'Y'
0x18000b3a4  imul    eax, r9d, 64h ; 'd'
0x18000b3a8  movsxd  rcx, r9d
0x18000b3ab  sub     r11d, eax
0x18000b3ae  lea     rax, [rcx+rdx]
0x18000b3b2  lea     r8, ds:4[rax*4]
0x18000b3ba  mov     ebp, [r8+r15+182F0h]
0x18000b3c2  lea     rax, [rcx+rdx]
0x18000b3c6  mov     r10d, ds:rva ?m_aB1@CVoiceFilter@@2PAY0FJ@KA[r15+rax*4]; ulong (near * CVoiceFilter::m_aB1)[89] ...
0x18000b3ce  mov     edi, r10d
0x18000b3d1  mov     ecx, ds:rva ?m_aB2@CVoiceFilter@@2PAY0FJ@KA[r15+rax*4]; ulong (near * CVoiceFilter::m_aB2)[89] ...
0x18000b3d9  mov     edx, ecx
0x18000b3db  mov     r14d, ds:rva ?m_aK@CVoiceFilter@@2PAY0FJ@KA[r15+rax*4]; ulong (near * CVoiceFilter::m_aK)[89] ...
0x18000b3e3  sub     ebp, r14d
0x18000b3e6  sub     edi, [r8+r15+19930h]
0x18000b3ee  mov     eax, 51EB851Fh
0x18000b3f3  sub     edx, [r8+r15+16CB0h]
0x18000b3fb  cmp     r9d, 54h ; 'T'
0x18000b3ff  jl      short loc_18000B436
0x18000b401  shr     edx, 1
0x18000b403  imul    edx, r11d
0x18000b407  shr     edi, 1
0x18000b409  imul    edi, r11d
0x18000b40d  shr     ebp, 1
0x18000b40f  imul    ebp, r11d
0x18000b413  mul     edx
0x18000b415  mov     eax, 51EB851Fh
0x18000b41a  shr     edx, 4
0x18000b41d  sub     ecx, edx
0x18000b41f  mul     edi
0x18000b421  mov     eax, 51EB851Fh
0x18000b426  shr     edx, 4
0x18000b429  sub     r10d, edx
0x18000b42c  mul     ebp
0x18000b42e  shr     edx, 4
0x18000b431  add     edx, r14d
0x18000b434  jmp     short loc_18000B484
0x18000b436  imul    edx, r11d
0x18000b43a  imul    edi, r11d
0x18000b43e  imul    ebp, r11d
0x18000b442  mul     edx
0x18000b444  mov     eax, 51EB851Fh
0x18000b449  shr     edx, 5
0x18000b44c  sub     ecx, edx
0x18000b44e  mul     edi
0x18000b450  mov     eax, 51EB851Fh
0x18000b455  shr     edx, 5
0x18000b458  sub     r10d, edx
0x18000b45b  mul     ebp
0x18000b45d  shr     edx, 5
0x18000b460  add     edx, r14d
0x18000b463  jmp     short loc_18000B484
0x18000b465  imul    rax, rcx, 164h
0x18000b46c  mov     ecx, [rax+r15+16CB0h]
0x18000b474  mov     r10d, [rax+r15+19930h]
0x18000b47c  mov     edx, [rax+r15+182F0h]
0x18000b484  mov     rdi, [rsp+38h+arg_10]
0x18000b489  mov     rbp, [rsp+38h+arg_8]
0x18000b48e  mov     r15, [rsp+38h+arg_18]
0x18000b493  mov     rax, [rsp+38h+arg_28]
0x18000b498  mov     [rbx], edx
0x18000b49a  mov     [rsi], r10d
0x18000b49d  mov     [rax], ecx
0x18000b49f  add     rsp, 20h
0x18000b4a3  pop     r14
0x18000b4a5  pop     rsi
0x18000b4a6  pop     rbx
0x18000b4a7  retn
```
