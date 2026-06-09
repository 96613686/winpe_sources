# WppTraceCallback

- ea: `0x14000b310`
- end: `0x14000b59b`
- name: `WppTraceCallback`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140004e10`
- `0x140004ec0`
- `0x1400051c0`
- `0x14000b310`

## pseudocode

```c
__int64 __fastcall WppTraceCallback(
        unsigned __int8 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int *a4,
        __int64 a5,
        unsigned int *a6)
{
  unsigned int *v6; // r15
  __int64 v9; // rbx
  unsigned int v10; // ecx
  _DWORD *v11; // rcx
  bool v12; // zf
  __int64 v13; // rbp
  unsigned int v14; // ebx
  __int64 v15; // rax
  const void **v16; // r14
  unsigned int v17; // esi
  unsigned int v18; // r12d
  unsigned int i; // edx
  __int64 v20; // rcx
  __int128 v21; // xmm0
  __int64 v23; // [rsp+30h] [rbp-38h]
  int v24; // [rsp+70h] [rbp+8h] BYREF

  v6 = a6;
  *a6 = 0;
  if ( a1 > 5u )
  {
    if ( a1 != 6 && a1 != 7 )
    {
      if ( a1 != 8 )
        return (unsigned int)-1073741808;
      v13 = a5;
      v14 = 0;
      v15 = a5;
      if ( a5 )
      {
        do
        {
          v15 = *(_QWORD *)(v15 + 16);
          ++v14;
        }
        while ( v15 );
        if ( v14 > 0x3F )
          return (unsigned int)-1073741811;
      }
      v16 = *(const void ***)(a5 + 32);
      v17 = 32 * v14 + 24;
      if ( v16 )
      {
        v18 = 32 * v14 + 24;
        v17 += *(unsigned __int16 *)v16 + 2;
      }
      else
      {
        v18 = 0;
      }
      if ( v17 > a3 )
      {
        v10 = -1073741789;
        if ( a3 >= 4 )
        {
          *a4 = v17;
          *v6 = 4;
        }
        return v10;
      }
      memset(a4, 0, a3);
      *a4 = v17;
      a4[2] = v18;
      a4[4] = v14;
      if ( v16 )
      {
        *(_WORD *)((char *)a4 + v18) = *(_WORD *)v16;
        memmove((char *)a4 + v18 + 2, v16[1], *(unsigned __int16 *)v16);
      }
      for ( i = 0; i < v14; v13 = *(_QWORD *)(v13 + 16) )
      {
        v20 = i++;
        v20 *= 32;
        v21 = *(_OWORD *)*(_QWORD *)(v13 + 8);
        *(unsigned int *)((char *)a4 + v20 + 40) = 528384;
        *(_OWORD *)((char *)a4 + v20 + 24) = v21;
        *(_BYTE *)(v13 + 41) = 0;
        *(_DWORD *)(v13 + 44) = 0;
      }
      *v6 = v17;
    }
    return 0;
  }
  if ( a1 != 5 && (!a1 || a1 != 4) )
    return (unsigned int)-1073741808;
  v9 = a5;
  v24 = 0;
  LODWORD(a6) = 0;
  if ( !a5 )
    return (unsigned int)-1073741163;
  if ( a3 < 0x30 )
    return (unsigned int)-1073741811;
  do
  {
    v11 = *(_DWORD **)(v9 + 8);
    if ( *v11 == a4[6] && v11[1] == a4[7] && v11[2] == a4[8] && v11[3] == a4[9] )
      break;
    v9 = *(_QWORD *)(v9 + 16);
  }
  while ( v9 );
  if ( !v9 )
    return (unsigned int)-1073741163;
  v10 = 0;
  if ( a1 == 5 )
  {
    *(_DWORD *)(v9 + 44) = 0;
    *(_QWORD *)(v9 + 24) = 0;
    *(_BYTE *)(v9 + 41) = 0;
  }
  else
  {
    v12 = WPPTraceSuite == 2;
    v23 = *((_QWORD *)a4 + 1);
    *(_QWORD *)(v9 + 24) = v23;
    if ( v12 )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, int *, __int64, unsigned int **, unsigned int *))pfnWppQueryTraceInformation)(
                            3,
                            &v24,
                            4,
                            &a6,
                            a4) )
        *(_BYTE *)(v9 + 41) = v24;
      return (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int **, unsigned int *))pfnWppQueryTraceInformation)(
                             2,
                             v9 + 44,
                             4,
                             &a6,
                             a4);
    }
    else
    {
      *(_DWORD *)(v9 + 44) = HIDWORD(v23);
      *(_BYTE *)(v9 + 41) = BYTE2(v23);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14000b310  mov     [rsp+arg_8], rbx
0x14000b315  mov     [rsp+arg_10], rbp
0x14000b31a  push    rsi
0x14000b31b  push    rdi
0x14000b31c  push    r12
0x14000b31e  push    r14
0x14000b320  push    r15
0x14000b322  sub     rsp, 40h
0x14000b326  mov     r15, [rsp+68h+arg_28]
0x14000b32e  mov     rdi, r9
0x14000b331  movzx   r9d, cl
0x14000b335  mov     edx, r9d
0x14000b338  mov     dword ptr [r15], 0
0x14000b33f  cmp     r9d, 5
0x14000b343  ja      loc_14000B47C
0x14000b349  jz      short loc_14000B377
0x14000b34b  test    cl, cl
0x14000b34d  jz      loc_14000B493
0x14000b353  sub     edx, 1
0x14000b356  jz      loc_14000B493
0x14000b35c  sub     edx, 1
0x14000b35f  jz      loc_14000B493
0x14000b365  sub     edx, 1
0x14000b368  jz      loc_14000B493
0x14000b36e  cmp     edx, 1
0x14000b371  jnz     loc_14000B493
0x14000b377  mov     rbx, [rsp+68h+arg_20]
0x14000b37f  mov     [rsp+68h+arg_0], 0
0x14000b387  mov     dword ptr [rsp+68h+arg_28], 0
0x14000b392  test    rbx, rbx
0x14000b395  jnz     short loc_14000B3A1
0x14000b397  mov     ecx, 0C0000295h
0x14000b39c  jmp     loc_14000B569
0x14000b3a1  cmp     r8d, 30h ; '0'
0x14000b3a5  jb      loc_14000B4BF
0x14000b3ab  mov     edx, [rdi+18h]
0x14000b3ae  mov     rcx, [rbx+8]
0x14000b3b2  cmp     [rcx], edx
0x14000b3b4  jnz     short loc_14000B3CE
0x14000b3b6  mov     eax, [rdi+1Ch]
0x14000b3b9  cmp     [rcx+4], eax
0x14000b3bc  jnz     short loc_14000B3CE
0x14000b3be  mov     eax, [rdi+20h]
0x14000b3c1  cmp     [rcx+8], eax
0x14000b3c4  jnz     short loc_14000B3CE
0x14000b3c6  mov     eax, [rdi+24h]
0x14000b3c9  cmp     [rcx+0Ch], eax
0x14000b3cc  jz      short loc_14000B3D7
0x14000b3ce  mov     rbx, [rbx+10h]
0x14000b3d2  test    rbx, rbx
0x14000b3d5  jnz     short loc_14000B3AE
0x14000b3d7  test    rbx, rbx
0x14000b3da  jz      short loc_14000B397
0x14000b3dc  xor     ecx, ecx
0x14000b3de  cmp     r9b, 5
0x14000b3e2  jnz     short loc_14000B3F3
0x14000b3e4  mov     [rbx+2Ch], ecx
0x14000b3e7  mov     [rbx+18h], rcx
0x14000b3eb  mov     [rbx+29h], cl
0x14000b3ee  jmp     loc_14000B569
0x14000b3f3  cmp     cs:WPPTraceSuite, 2
0x14000b3fa  mov     rax, [rdi+8]
0x14000b3fe  mov     [rsp+68h+var_38], rax
0x14000b403  mov     [rbx+18h], rax
0x14000b407  jnz     short loc_14000B469
0x14000b409  mov     rax, cs:pfnWppQueryTraceInformation
0x14000b410  lea     r9, [rsp+68h+arg_28]
0x14000b418  mov     r8d, 4
0x14000b41e  mov     [rsp+68h+var_48], rdi
0x14000b423  lea     rdx, [rsp+68h+arg_0]
0x14000b428  lea     ecx, [r8-1]
0x14000b42c  call    _guard_dispatch_icall
0x14000b431  test    eax, eax
0x14000b433  jnz     short loc_14000B43C
0x14000b435  mov     al, byte ptr [rsp+68h+arg_0]
0x14000b439  mov     [rbx+29h], al
0x14000b43c  mov     rax, cs:pfnWppQueryTraceInformation
0x14000b443  lea     rdx, [rbx+2Ch]
0x14000b447  mov     ecx, 2
0x14000b44c  mov     [rsp+68h+var_48], rdi
0x14000b451  lea     r9, [rsp+68h+arg_28]
0x14000b459  lea     r8d, [rcx+2]
0x14000b45d  call    _guard_dispatch_icall
0x14000b462  mov     ecx, eax
0x14000b464  jmp     loc_14000B569
0x14000b469  mov     eax, dword ptr [rsp+68h+var_38+4]
0x14000b46d  mov     [rbx+2Ch], eax
0x14000b470  mov     al, byte ptr [rsp+68h+var_38+2]
0x14000b474  mov     [rbx+29h], al
0x14000b477  jmp     loc_14000B569
0x14000b47c  sub     edx, 6
0x14000b47f  jz      loc_14000B567
0x14000b485  sub     edx, 1
0x14000b488  jz      loc_14000B567
0x14000b48e  sub     edx, 1
0x14000b491  jz      short loc_14000B49D
0x14000b493  mov     ecx, 0C0000010h
0x14000b498  jmp     loc_14000B569
0x14000b49d  mov     rbp, [rsp+68h+arg_20]
0x14000b4a5  xor     ebx, ebx
0x14000b4a7  mov     rax, rbp
0x14000b4aa  test    rbp, rbp
0x14000b4ad  jz      short loc_14000B4C9
0x14000b4af  mov     rax, [rax+10h]
0x14000b4b3  inc     ebx
0x14000b4b5  test    rax, rax
0x14000b4b8  jnz     short loc_14000B4AF
0x14000b4ba  cmp     ebx, 3Fh ; '?'
0x14000b4bd  jbe     short loc_14000B4C9
0x14000b4bf  mov     ecx, 0C000000Dh
0x14000b4c4  jmp     loc_14000B569
0x14000b4c9  mov     r14, [rbp+20h]
0x14000b4cd  mov     esi, ebx
0x14000b4cf  shl     esi, 5
0x14000b4d2  add     esi, 18h
0x14000b4d5  test    r14, r14
0x14000b4d8  jnz     short loc_14000B4DF
0x14000b4da  xor     r12d, r12d
0x14000b4dd  jmp     short loc_14000B4EB
0x14000b4df  movzx   eax, word ptr [r14]
0x14000b4e3  mov     r12d, esi
0x14000b4e6  add     eax, 2
0x14000b4e9  add     esi, eax
0x14000b4eb  cmp     esi, r8d
0x14000b4ee  ja      loc_14000B585
0x14000b4f4  mov     r8d, r8d; Size
0x14000b4f7  xor     edx, edx; Val
0x14000b4f9  mov     rcx, rdi; void *
0x14000b4fc  call    memset
0x14000b501  mov     [rdi], esi
0x14000b503  mov     [rdi+8], r12d
0x14000b507  mov     [rdi+10h], ebx
0x14000b50a  test    r14, r14
0x14000b50d  jz      short loc_14000B52E
0x14000b50f  movzx   eax, word ptr [r14]
0x14000b513  mov     ecx, r12d
0x14000b516  mov     [rcx+rdi], ax
0x14000b51a  add     rcx, 2
0x14000b51e  movzx   r8d, word ptr [r14]; Size
0x14000b522  add     rcx, rdi; void *
0x14000b525  mov     rdx, [r14+8]; Src
0x14000b529  call    memmove
0x14000b52e  xor     edx, edx
0x14000b530  test    ebx, ebx
0x14000b532  jz      short loc_14000B564
0x14000b534  mov     rax, [rbp+8]
0x14000b538  mov     ecx, edx
0x14000b53a  inc     edx
0x14000b53c  shl     rcx, 5
0x14000b540  movups  xmm0, xmmword ptr [rax]
0x14000b543  mov     dword ptr [rcx+rdi+28h], 81000h
0x14000b54b  movdqu  xmmword ptr [rcx+rdi+18h], xmm0
0x14000b551  mov     byte ptr [rbp+29h], 0
0x14000b555  mov     dword ptr [rbp+2Ch], 0
0x14000b55c  mov     rbp, [rbp+10h]
0x14000b560  cmp     edx, ebx
0x14000b562  jb      short loc_14000B534
0x14000b564  mov     [r15], esi
0x14000b567  xor     ecx, ecx
0x14000b569  lea     r11, [rsp+68h+var_28]
0x14000b56e  mov     eax, ecx
0x14000b570  mov     rbx, [r11+38h]
0x14000b574  mov     rbp, [r11+40h]
0x14000b578  mov     rsp, r11
0x14000b57b  pop     r15
0x14000b57d  pop     r14
0x14000b57f  pop     r12
0x14000b581  pop     rdi
0x14000b582  pop     rsi
0x14000b583  retn
0x14000b585  mov     ecx, 0C0000023h
0x14000b58a  cmp     r8d, 4
0x14000b58e  jb      short loc_14000B569
0x14000b590  mov     [rdi], esi
0x14000b592  mov     dword ptr [r15], 4
0x14000b599  jmp     short loc_14000B569
```
