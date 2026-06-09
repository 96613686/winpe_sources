# SIdxKeyTable::AddKey(char *,ushort,ulong)

- ea: `0x1800109d0`
- end: `0x180010f94`
- name: `?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z`
- size: `1476`
- prototype: `__int64 __fastcall(void **this, char *, unsigned __int16, int)`
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010fe4`
- `0x180019868`
- `0x180027eb4`
- `0x180037fb0`
- `0x180038570`

## callees

- `0x1800012b8`
- `0x18000fcf0`
- `0x1800106f0`
- `0x1800109d0`
- `0x180010fa0`
- `0x180012fd0`
- `0x180023828`
- `0x18002b7c2`
- `0x1800371ac`
- `0x1800371d0`
- `0x180037244`
- `0x180038c30`
- `0x180038c6c`
- `0x180038ca0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180010a1d`
- `wbemcomn!GetMemLogObject` at `0x180010d33`
- `wbemcomn!GetMemLogObject` at `0x180010a1d`
- `wbemcomn!GetMemLogObject` at `0x180010d33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010a2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010d41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010a2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010d41`

## pseudocode

```c
__int64 __fastcall SIdxKeyTable::AddKey(void **this, char *a2, unsigned __int16 a3, int a4)
{
  unsigned int v4; // esi
  char **v5; // r14
  void **v7; // rbx
  __int64 v8; // rax
  CMemoryLog *v9; // rax
  CVarObjHeap *v10; // rcx
  _WORD *v12; // r13
  unsigned int v13; // edi
  unsigned int v14; // r15d
  _WORD *v15; // rax
  __int64 v16; // rbp
  _WORD *v17; // r8
  SIdxStringPool *v18; // r15
  char *v19; // r12
  __int64 v20; // r9
  int v21; // r11d
  int i; // r10d
  char *v23; // rcx
  int v24; // edx
  int v25; // edi
  unsigned __int16 v26; // di
  __int16 v27; // bx
  __int64 v28; // r13
  unsigned int v29; // ecx
  __int64 v30; // rdi
  __int16 v31; // ax
  __int64 v32; // r12
  __int64 v33; // r15
  unsigned int v34; // ebp
  int v35; // ecx
  __int64 k; // rdi
  __int64 j; // rcx
  unsigned __int16 v38; // r8
  __int64 v39; // rdi
  unsigned int v40; // ebx
  unsigned __int64 v41; // rdx
  char *v42; // r8
  CMemoryLog *MemLogObject; // rax
  __int64 v44; // rdx
  unsigned int v45; // ebx
  unsigned int v46; // eax
  void *v47; // rax
  unsigned int v48; // eax
  void *v49; // rax
  unsigned int v50; // ebx
  char *v51; // rax
  __int64 v52; // rdi
  void *v53; // rax
  __int64 v54; // rdi
  unsigned int v55; // [rsp+20h] [rbp-68h] BYREF
  _WORD *v56; // [rsp+28h] [rbp-60h]
  char **v57; // [rsp+30h] [rbp-58h] BYREF
  void *v58; // [rsp+38h] [rbp-50h]
  unsigned int v60; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int16 v61; // [rsp+A0h] [rbp+18h]
  int v62; // [rsp+A8h] [rbp+20h]

  v62 = a4;
  v61 = a3;
  v4 = 0;
  v5 = 0;
  v60 = 0;
  v57 = 0;
  v7 = this;
  if ( !a2 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 87);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v44 = 92;
    goto LABEL_59;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !(_DWORD)v8 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, 87);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v44 = 93;
LABEL_59:
    WPP_SF_d(*((_QWORD *)v10 + 2), v44, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    return 87;
  }
  v12 = 0;
  v58 = _BtrMemAlloc((unsigned int)(v8 + 1));
  if ( !v58 )
  {
    v14 = 8;
    goto LABEL_37;
  }
  v13 = *((_DWORD *)v7 + 6);
  if ( v13 == *((_DWORD *)v7 + 3) )
  {
    SafeInt<unsigned long>::MixedSizeMultiply<int>(&v55, v13, 2);
    v45 = v55;
    v46 = SafeInt<unsigned long>::multiply(v55, 2);
    v47 = _BtrMemReAlloc(this[2], v46);
    if ( !v47 )
    {
      v14 = 8;
      goto LABEL_36;
    }
    *((_DWORD *)this + 6) = v45;
    this[2] = v47;
    v48 = SafeInt<unsigned long>::multiply(v45, 4);
    v49 = _BtrMemReAlloc(this[4], v48);
    if ( !v49 )
    {
      v14 = 8;
      goto LABEL_36;
    }
    this[4] = v49;
    SafeInt<unsigned long>::MixedSizeAddition<int>(&v55, v45);
    v50 = SafeInt<unsigned long>::multiply(v55, 4);
    v51 = (char *)_BtrMemReAlloc(this[5], v50);
    if ( !v51 )
    {
      v14 = 8;
      goto LABEL_36;
    }
    v39 = v13 + 1;
    this[5] = v51;
    v40 = v50 - v39;
    v41 = v40;
    if ( v40 )
    {
      v42 = &v51[4 * v39];
      if ( ((unsigned __int8)v42 & 4) == 0 )
        goto LABEL_50;
      *(_DWORD *)v42 = -1;
      v41 = v40 - 1LL;
      if ( v40 != 1 )
      {
        v42 += 4;
LABEL_50:
        v7 = this;
        memset(v42, 0xFFu, 8 * (v41 >> 1));
        if ( (v41 & 1) != 0 )
          *(_DWORD *)&v42[4 * v41 - 4] = -1;
        goto LABEL_9;
      }
    }
    v7 = this;
  }
LABEL_9:
  v14 = ParseIntoTokens(a2, &v60, &v57);
  if ( v14 )
  {
    v4 = v60;
    v5 = v57;
  }
  else
  {
    v4 = v60;
    v15 = _BtrMemAlloc(2LL * v60);
    v5 = v57;
    v12 = v15;
    v56 = v15;
    if ( v15 )
    {
      v16 = 0;
      v17 = v15;
      while ( (unsigned int)v16 < v4 )
      {
        v18 = (SIdxStringPool *)v7[8];
        v19 = v5[v16];
        if ( *(_DWORD *)v18 )
        {
          LOWORD(v20) = 0;
          v21 = *(_DWORD *)v18 - 1;
          for ( i = 0; ; i = v20 )
          {
            while ( 1 )
            {
              if ( i > v21 )
              {
                v26 = v20;
                goto LABEL_24;
              }
              v20 = (v21 + i) / 2;
              v23 = v5[v16];
              do
              {
                v24 = (unsigned __int8)v23[*((_QWORD *)v18 + 3)
                                         + *(unsigned __int16 *)(*((_QWORD *)v18 + 1) + 2 * v20)
                                         - (_QWORD)v19];
                v25 = (unsigned __int8)*v23 - v24;
                if ( v25 )
                  break;
                ++v23;
              }
              while ( v24 );
              if ( v25 >= 0 )
                break;
              v21 = v20 - 1;
            }
            if ( v25 <= 0 )
              break;
            LODWORD(v20) = v20 + 1;
          }
          v26 = (v21 + i) / 2;
        }
        else
        {
          v26 = 0;
LABEL_24:
          v60 = 0;
          v14 = SIdxStringPool::AddStr(v18, v19, v26, (int *)&v60);
          if ( v14 )
            goto LABEL_36;
          v27 = v60;
          if ( v60 )
          {
            SIdxKeyTable::AdjustKeyCodes((SIdxKeyTable *)this, v26, v60);
            for ( j = 0; (unsigned int)j < (unsigned int)v16; j = (unsigned int)(j + 1) )
            {
              v38 = v12[j];
              if ( v38 >= v26 )
                v12[j] = v38 + v27;
            }
          }
          v7 = this;
        }
        v12[v16] = v26;
        v17 = v12;
        v16 = (unsigned int)(v16 + 1);
      }
      if ( *((_DWORD *)v7 + 14) - *((_DWORD *)v7 + 15) >= (unsigned int)(v16 + 1) )
        goto LABEL_30;
      SafeInt<unsigned long>::MixedSizeMultiply<int>(&v55, *((unsigned int *)v7 + 14), 2);
      SafeInt<unsigned long>::MixedSizeAddition<int>(&v60, (unsigned int)v16);
      v52 = (unsigned int)SafeInt<unsigned long>::addition(v55, v60);
      SafeInt<unsigned long>::MixedSizeMultiply<unsigned __int64>(&v60, v52, 2);
      v53 = _BtrMemReAlloc(v7[6], v60);
      if ( v53 )
      {
        v7[6] = v53;
        v17 = v12;
        *((_DWORD *)v7 + 14) = v52;
LABEL_30:
        v28 = *((unsigned int *)v7 + 15);
        *((_WORD *)v7[6] + v28) = v16;
        v29 = ++*((_DWORD *)v7 + 15);
        if ( (_DWORD)v16 )
        {
          v30 = 0;
          do
          {
            v31 = v17[v30];
            v30 = (unsigned int)(v30 + 1);
            *((_WORD *)v7[6] + v29) = v31;
            v29 = *((_DWORD *)v7 + 15) + 1;
            *((_DWORD *)v7 + 15) = v29;
          }
          while ( (unsigned int)v30 < (unsigned int)v16 );
        }
        v32 = 2LL * v61;
        v33 = 4LL * v61;
        v34 = *((_DWORD *)v7 + 3) - v61;
        if ( v34 )
        {
          v54 = (unsigned int)v61 + 1;
          memmove_0((char *)this[2] + 2 * v54, (char *)this[2] + v32, 2LL * v34);
          memmove_0((char *)this[4] + 4 * v54, (char *)this[4] + v33, 4LL * v34);
          v7 = this;
          memmove_0((char *)this[5] + 4 * v54, (char *)this[5] + v33, 4LL * (v34 + 1));
        }
        v35 = v62;
        *(_WORD *)((char *)v7[2] + v32) = v28;
        v12 = v56;
        *(_DWORD *)((char *)v7[4] + v33) = v35;
        ++*((_DWORD *)v7 + 3);
        v14 = 0;
        goto LABEL_36;
      }
      v14 = 8;
    }
    else
    {
      v14 = 8;
    }
  }
LABEL_36:
  _BtrMemFree(v58);
LABEL_37:
  for ( k = 0; (unsigned int)k < v4; k = (unsigned int)(k + 1) )
    _BtrMemFree(v5[k]);
  _BtrMemFree(v5);
  if ( v12 )
    _BtrMemFree(v12);
  return v14;
}

```

## disassembly

```asm
0x1800109d0  mov     rax, rsp
0x1800109d3  mov     [rax+20h], r9d
0x1800109d7  mov     [rax+18h], r8w
0x1800109dc  mov     [rax+8], rcx
0x1800109e0  push    rbx
0x1800109e1  push    rbp
0x1800109e2  push    rsi
0x1800109e3  push    r14
0x1800109e5  sub     rsp, 68h
0x1800109e9  xor     esi, esi
0x1800109eb  xor     r14d, r14d
0x1800109ee  mov     [rax+10h], esi
0x1800109f1  mov     rbp, rdx
0x1800109f4  mov     [rax-58h], r14
0x1800109f8  mov     rbx, rcx
0x1800109fb  test    rdx, rdx
0x1800109fe  jz      loc_180010D33
0x180010a04  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010a0b  nop     dword ptr [rax+rax+00h]
0x180010a10  inc     rax
0x180010a13  cmp     [rax+rdx], sil
0x180010a17  jnz     short loc_180010A10
0x180010a19  test    eax, eax
0x180010a1b  jnz     short loc_180010A57
0x180010a1d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180010a23  mov     rcx, rax
0x180010a26  mov     edx, 57h ; 'W'
0x180010a2b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180010a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a38  lea     rax, WPP_GLOBAL_Control
0x180010a3f  cmp     rcx, rax
0x180010a42  jnz     loc_180010D79
0x180010a48  mov     eax, 57h ; 'W'
0x180010a4d  add     rsp, 68h
0x180010a51  pop     r14
0x180010a53  pop     rsi
0x180010a54  pop     rbp
0x180010a55  pop     rbx
0x180010a56  retn
0x180010a57  mov     [rsp+88h+var_28], rdi
0x180010a5c  lea     ecx, [rax+1]; unsigned __int64
0x180010a5f  mov     [rsp+88h+var_38], r13
0x180010a64  xor     r13d, r13d
0x180010a67  mov     [rsp+88h+var_40], r15
0x180010a6c  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180010a71  mov     [rsp+88h+var_50], rax
0x180010a76  test    rax, rax
0x180010a79  jz      loc_180010C8C
0x180010a7f  mov     edi, [rbx+18h]
0x180010a82  cmp     edi, [rbx+0Ch]
0x180010a85  jz      loc_180010DAD
0x180010a8b  lea     r8, [rsp+88h+var_58]; char ***
0x180010a90  mov     rcx, rbp; char *
0x180010a93  lea     rdx, [rsp+88h+arg_8]; unsigned int *
0x180010a9b  call    ?ParseIntoTokens@@YAKPEADPEAKPEAPEAPEAD@Z; ParseIntoTokens(char *,ulong *,char * * *)
0x180010aa0  mov     r15d, eax
0x180010aa3  test    eax, eax
0x180010aa5  jnz     loc_180010E83
0x180010aab  mov     esi, [rsp+88h+arg_8]
0x180010ab2  mov     ecx, esi
0x180010ab4  add     rcx, rcx; unsigned __int64
0x180010ab7  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180010abc  mov     r14, [rsp+88h+var_58]
0x180010ac1  mov     r13, rax
0x180010ac4  mov     [rsp+88h+var_60], rax
0x180010ac9  test    rax, rax
0x180010acc  jz      loc_180010E94
0x180010ad2  mov     [rsp+88h+var_30], r12
0x180010ad7  xor     ebp, ebp
0x180010ad9  mov     r8, rax
0x180010adc  cmp     ebp, esi
0x180010ade  jnb     loc_180010BB5
0x180010ae4  mov     r15, [rbx+40h]
0x180010ae8  mov     r12, [r14+rbp*8]
0x180010aec  mov     eax, [r15]
0x180010aef  test    eax, eax
0x180010af1  jz      loc_180010E9F
0x180010af7  xor     r9d, r9d
0x180010afa  lea     r11d, [rax-1]
0x180010afe  xor     r10d, r10d
0x180010b01  cmp     r10d, r11d
0x180010b04  jg      short loc_180010B57
0x180010b06  mov     rcx, [r15+8]
0x180010b0a  lea     eax, [r11+r10]
0x180010b0e  cdq
0x180010b0f  sub     eax, edx
0x180010b11  sar     eax, 1
0x180010b13  movsxd  r9, eax
0x180010b16  movzx   r8d, word ptr [rcx+r9*2]
0x180010b1b  mov     rcx, r12
0x180010b1e  add     r8, [r15+18h]
0x180010b22  sub     r8, r12
0x180010b25  nop     word ptr [rax+rax+00000000h]
0x180010b30  movzx   edi, byte ptr [rcx]
0x180010b33  movzx   edx, byte ptr [rcx+r8]
0x180010b38  sub     edi, edx
0x180010b3a  jnz     short loc_180010B43
0x180010b3c  inc     rcx
0x180010b3f  test    edx, edx
0x180010b41  jnz     short loc_180010B30
0x180010b43  test    edi, edi
0x180010b45  js      short loc_180010B51
0x180010b47  jle     short loc_180010BA1
0x180010b49  inc     r9d
0x180010b4c  mov     r10d, r9d
0x180010b4f  jmp     short loc_180010B01
0x180010b51  lea     r11d, [r9-1]
0x180010b55  jmp     short loc_180010B01
0x180010b57  movzx   edi, r9w
0x180010b5b  lea     r9, [rsp+88h+arg_8]; int *
0x180010b63  mov     [rsp+88h+arg_8], 0
0x180010b6e  movzx   r8d, di; unsigned __int16
0x180010b72  mov     rdx, r12; char *
0x180010b75  mov     rcx, r15; this
0x180010b78  call    ?AddStr@SIdxStringPool@@QEAAKPEADGPEAH@Z; SIdxStringPool::AddStr(char *,ushort,int *)
0x180010b7d  mov     r15d, eax
0x180010b80  test    eax, eax
0x180010b82  jnz     loc_180010C40
0x180010b88  mov     ebx, [rsp+88h+arg_8]
0x180010b8f  test    ebx, ebx
0x180010b91  jnz     loc_180010C94
0x180010b97  mov     rbx, [rsp+88h+arg_0]
0x180010b9f  jmp     short loc_180010BA5
0x180010ba1  movzx   edi, r9w
0x180010ba5  mov     [r13+rbp*2+0], di
0x180010bab  mov     r8, r13
0x180010bae  inc     ebp
0x180010bb0  jmp     loc_180010ADC
0x180010bb5  mov     edx, [rbx+38h]
0x180010bb8  lea     eax, [rbp+1]
0x180010bbb  mov     ecx, edx
0x180010bbd  sub     ecx, [rbx+3Ch]
0x180010bc0  cmp     ecx, eax
0x180010bc2  jb      loc_180010EA6
0x180010bc8  mov     r13d, [rbx+3Ch]
0x180010bcc  mov     rax, [rbx+30h]
0x180010bd0  mov     [rax+r13*2], bp
0x180010bd5  inc     dword ptr [rbx+3Ch]
0x180010bd8  mov     ecx, [rbx+3Ch]
0x180010bdb  test    ebp, ebp
0x180010bdd  jz      short loc_180010BFE
0x180010bdf  xor     edi, edi
0x180010be1  movzx   eax, word ptr [r8+rdi*2]
0x180010be6  inc     edi
0x180010be8  mov     edx, ecx
0x180010bea  mov     rcx, [rbx+30h]
0x180010bee  mov     [rcx+rdx*2], ax
0x180010bf2  mov     ecx, [rbx+3Ch]
0x180010bf5  inc     ecx
0x180010bf7  mov     [rbx+3Ch], ecx
0x180010bfa  cmp     edi, ebp
0x180010bfc  jb      short loc_180010BE1
0x180010bfe  movzx   eax, [rsp+88h+arg_10]
0x180010c06  mov     ebp, [rbx+0Ch]
0x180010c09  lea     r12, [rax+rax]
0x180010c0d  lea     r15, ds:0[rax*4]
0x180010c15  sub     ebp, eax
0x180010c17  jnz     loc_180010F1B
0x180010c1d  mov     rax, [rbx+10h]
0x180010c21  mov     ecx, [rsp+88h+arg_18]
0x180010c28  mov     [r12+rax], r13w
0x180010c2d  mov     rax, [rbx+20h]
0x180010c31  mov     r13, [rsp+88h+var_60]
0x180010c36  mov     [r15+rax], ecx
0x180010c3a  inc     dword ptr [rbx+0Ch]
0x180010c3d  xor     r15d, r15d
0x180010c40  mov     r12, [rsp+88h+var_30]
0x180010c45  mov     rcx, [rsp+88h+var_50]; void *
0x180010c4a  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180010c4f  xor     edi, edi
0x180010c51  test    esi, esi
0x180010c53  jz      short loc_180010C64
0x180010c55  mov     rcx, [r14+rdi*8]; void *
0x180010c59  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180010c5e  inc     edi
0x180010c60  cmp     edi, esi
0x180010c62  jb      short loc_180010C55
0x180010c64  mov     rcx, r14; void *
0x180010c67  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180010c6c  mov     rdi, [rsp+88h+var_28]
0x180010c71  test    r13, r13
0x180010c74  jnz     loc_180010F87
0x180010c7a  mov     r13, [rsp+88h+var_38]
0x180010c7f  mov     eax, r15d
0x180010c82  mov     r15, [rsp+88h+var_40]
0x180010c87  jmp     loc_180010A4D
0x180010c8c  mov     r15d, 8
0x180010c92  jmp     short loc_180010C4F
0x180010c94  mov     rcx, [rsp+88h+arg_0]; this
0x180010c9c  mov     r8d, ebx; int
0x180010c9f  movzx   edx, di; unsigned __int16
0x180010ca2  call    ?AdjustKeyCodes@SIdxKeyTable@@QEAAXGH@Z; SIdxKeyTable::AdjustKeyCodes(ushort,int)
0x180010ca7  xor     ecx, ecx
0x180010ca9  test    ebp, ebp
0x180010cab  jz      loc_180010B97
0x180010cb1  mov     r9, r13
0x180010cb4  nop     dword ptr [rax+00h]
0x180010cb8  nop     dword ptr [rax+rax+00000000h]
0x180010cc0  movzx   r8d, word ptr [r9+rcx*2]
0x180010cc5  lea     rdx, [r9+rcx*2]
0x180010cc9  cmp     r8w, di
0x180010ccd  jnb     short loc_180010CDA
0x180010ccf  inc     ecx
0x180010cd1  cmp     ecx, ebp
0x180010cd3  jb      short loc_180010CC0
0x180010cd5  jmp     loc_180010B97
0x180010cda  lea     eax, [r8+rbx]
0x180010cde  mov     [rdx], ax
0x180010ce1  jmp     short loc_180010CCF
0x180010ce3  inc     edi
0x180010ce5  mov     [r15+28h], rax
0x180010ce9  sub     ebx, edi
0x180010ceb  mov     edx, ebx
0x180010ced  jz      loc_180010E76
0x180010cf3  lea     r8, [rax+rdi*4]
0x180010cf7  test    r8b, 4
0x180010cfb  jnz     loc_180010E60
0x180010d01  mov     rbx, [rsp+88h+arg_0]
0x180010d09  mov     rcx, rdx
0x180010d0c  shr     rcx, 1
0x180010d0f  mov     rdi, r8
0x180010d12  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010d19  rep stosq
0x180010d1c  test    dl, 1
0x180010d1f  jz      loc_180010A8B
0x180010d25  mov     dword ptr [r8+rdx*4-4], 0FFFFFFFFh
0x180010d2e  jmp     loc_180010A8B
0x180010d33  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180010d39  mov     rcx, rax
0x180010d3c  mov     edx, 57h ; 'W'
0x180010d41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180010d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d4e  lea     rax, WPP_GLOBAL_Control
0x180010d55  cmp     rcx, rax
0x180010d58  jz      loc_180010A48
0x180010d5e  test    byte ptr [rcx+1Ch], 1
0x180010d62  jz      loc_180010A48
0x180010d68  cmp     byte ptr [rcx+19h], 2
0x180010d6c  jb      loc_180010A48
0x180010d72  mov     edx, 5Ch ; '\'
0x180010d77  jmp     short loc_180010D92
0x180010d79  test    byte ptr [rcx+1Ch], 1
0x180010d7d  jz      loc_180010A48
0x180010d83  cmp     byte ptr [rcx+19h], 2
0x180010d87  jb      loc_180010A48
0x180010d8d  mov     edx, 5Dh ; ']'
0x180010d92  mov     rcx, [rcx+10h]
0x180010d96  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180010d9d  mov     r9d, 57h ; 'W'
0x180010da3  call    WPP_SF_d
0x180010da8  jmp     loc_180010A48
0x180010dad  mov     r8d, 2
0x180010db3  lea     rcx, [rsp+88h+var_68]
0x180010db8  mov     edx, edi
0x180010dba  call    ??$MixedSizeMultiply@H@?$SafeInt@K@@CA?AV0@V0@H@Z; SafeInt<ulong>::MixedSizeMultiply<int>(SafeInt<ulong>,int)
0x180010dbf  mov     ebx, [rsp+88h+var_68]
0x180010dc3  mov     edx, 2
0x180010dc8  mov     ecx, ebx
0x180010dca  call    ?multiply@?$SafeInt@K@@CAKKK@Z; SafeInt<ulong>::multiply(ulong,ulong)
0x180010dcf  mov     r15, [rsp+88h+arg_0]
0x180010dd7  mov     edx, eax; unsigned int
0x180010dd9  mov     rcx, [r15+10h]; void *
0x180010ddd  call    ?_BtrMemReAlloc@@YAPEAXPEAXK@Z; _BtrMemReAlloc(void *,ulong)
0x180010de2  test    rax, rax
0x180010de5  jnz     short loc_180010DF2
0x180010de7  mov     r15d, 8
0x180010ded  jmp     loc_180010C45
0x180010df2  mov     edx, 4
0x180010df7  mov     [r15+18h], ebx
0x180010dfb  mov     ecx, ebx
0x180010dfd  mov     [r15+10h], rax
0x180010e01  call    ?multiply@?$SafeInt@K@@CAKKK@Z; SafeInt<ulong>::multiply(ulong,ulong)
0x180010e06  mov     rcx, [r15+20h]; void *
0x180010e0a  mov     edx, eax; unsigned int
0x180010e0c  call    ?_BtrMemReAlloc@@YAPEAXPEAXK@Z; _BtrMemReAlloc(void *,ulong)
0x180010e11  test    rax, rax
0x180010e14  jnz     short loc_180010E21
0x180010e16  mov     r15d, 8
0x180010e1c  jmp     loc_180010C45
0x180010e21  mov     edx, ebx
0x180010e23  mov     [r15+20h], rax
0x180010e27  lea     rcx, [rsp+88h+var_68]
0x180010e2c  call    ??$MixedSizeAddition@H@?$SafeInt@K@@CA?AV0@V0@H@Z; SafeInt<ulong>::MixedSizeAddition<int>(SafeInt<ulong>,int)
0x180010e31  mov     ecx, [rsp+88h+var_68]
0x180010e35  mov     edx, 4
0x180010e3a  call    ?multiply@?$SafeInt@K@@CAKKK@Z; SafeInt<ulong>::multiply(ulong,ulong)
0x180010e3f  mov     rcx, [r15+28h]; void *
0x180010e43  mov     edx, eax; unsigned int
0x180010e45  mov     ebx, eax
0x180010e47  call    ?_BtrMemReAlloc@@YAPEAXPEAXK@Z; _BtrMemReAlloc(void *,ulong)
0x180010e4c  test    rax, rax
0x180010e4f  jnz     loc_180010CE3
0x180010e55  mov     r15d, 8
0x180010e5b  jmp     loc_180010C45
0x180010e60  mov     dword ptr [r8], 0FFFFFFFFh
0x180010e67  sub     rdx, 1
0x180010e6b  jz      short loc_180010E76
0x180010e6d  add     r8, 4
0x180010e71  jmp     loc_180010D01
0x180010e76  mov     rbx, [rsp+88h+arg_0]
  ... truncated ...
```
