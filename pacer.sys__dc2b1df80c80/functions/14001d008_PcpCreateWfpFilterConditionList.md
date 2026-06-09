# PcpCreateWfpFilterConditionList

- ea: `0x14001d008`
- end: `0x14001d476`
- name: `PcpCreateWfpFilterConditionList`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d284`

## callees

- `0x14000eb54`
- `0x140013600`
- `0x14001d008`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001d14e`
- `ntoskrnl!ExAllocatePool2` at `0x14001d14e`

## pseudocode

```c
__int64 __fastcall PcpCreateWfpFilterConditionList(__int16 a1, __int64 a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v7; // r12
  __int64 v8; // r11
  __int64 v9; // r10
  __int64 v10; // r8
  char v11; // bp
  bool v12; // zf
  char v13; // di
  __int64 v14; // rcx
  __int16 v15; // r14
  __int16 v16; // r15
  __int64 v17; // rax
  __int16 v18; // cx
  __int64 v19; // r13
  int v20; // edx
  int v21; // ecx
  unsigned int v22; // r9d
  unsigned int v23; // r8d
  unsigned int v24; // r10d
  unsigned int v25; // ecx
  __int64 v26; // rbx
  __int64 v27; // rdx
  size_t v28; // r12
  _QWORD *Pool2; // rax
  _QWORD *v30; // rsi
  unsigned int v31; // edi
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  char *v34; // rcx
  _QWORD *v35; // rdx
  __int16 v36; // ax
  __int16 v37; // r15
  __int16 v38; // ax
  __int16 v39; // r14
  unsigned int v40; // eax
  unsigned int v41; // eax
  char v42; // al
  char v43; // al
  char v44; // al
  __int64 result; // rax
  __int16 v46; // [rsp+20h] [rbp-58h]
  __int16 v47; // [rsp+22h] [rbp-56h]
  __int64 v48; // [rsp+28h] [rbp-50h]
  __int64 v49; // [rsp+30h] [rbp-48h]
  __int64 v50; // [rsp+38h] [rbp-40h]

  v7 = a3;
  v8 = 20;
  v9 = 18;
  if ( a1 != 2 )
    v8 = 44;
  v10 = 16;
  if ( a1 != 2 )
  {
    v9 = 42;
    v10 = 40;
  }
  v11 = *(_BYTE *)(v8 + a3);
  v12 = a1 == 2;
  v13 = *(_BYTE *)(v8 + a2);
  v14 = a2;
  v15 = *(_WORD *)(v9 + a2);
  if ( !v12 )
    v14 = 0;
  v16 = *(_WORD *)(v10 + a2);
  if ( !v12 )
    v7 = 0;
  v49 = v14;
  v17 = 0;
  v18 = *(_WORD *)(v10 + a3);
  if ( !v12 )
    v17 = a2;
  v48 = v17;
  v19 = 0;
  if ( !v12 )
    v19 = a3;
  v46 = *(_WORD *)(v10 + a3);
  v50 = v7;
  v47 = *(_WORD *)(v9 + a3);
  v20 = v18 != 0 ? 120 : 48;
  v21 = (v18 != 0) + 1;
  if ( v47 )
  {
    ++v21;
    v20 += 72;
  }
  v22 = v21 + 1;
  v23 = v20 + 72;
  if ( !v11 )
  {
    v22 = v21;
    v23 = v20;
  }
  v24 = v22 + 1;
  if ( a1 == 2 )
  {
    v25 = v23 + 48;
    if ( !*(_DWORD *)(v7 + 8) )
    {
      v25 = v23;
      v24 = v22;
    }
    v26 = v24 + 1;
    v27 = v25 + 48;
    if ( !*(_DWORD *)(v7 + 12) )
    {
      v26 = v24;
      v27 = v25;
    }
  }
  else
  {
    v27 = v23 + 64;
    v26 = v24;
    if ( !*(_BYTE *)(v19 + 8) )
    {
      v27 = v23;
      v26 = v22;
    }
    if ( *(_BYTE *)(v19 + 24) )
    {
      v26 = (unsigned int)(v26 + 1);
      v27 = (unsigned int)(v27 + 64);
    }
  }
  v28 = (unsigned int)v27;
  Pool2 = (_QWORD *)ExAllocatePool2(256, v27, 1717991248);
  v30 = Pool2;
  if ( !Pool2 )
  {
    v31 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids, 3221225626LL);
    }
    LODWORD(v26) = 0;
    v30 = 0;
    goto LABEL_61;
  }
  memset(Pool2, 0, v28);
  v32 = &v30[5 * v26];
  v33 = (_QWORD *)v48;
  v30[4] = v32;
  *(GUID *)v30 = FWPM_CONDITION_IP_LOCAL_INTERFACE;
  *((_DWORD *)v30 + 4) = 0;
  *((_DWORD *)v30 + 6) = 4;
  v34 = (char *)(v30 + 5);
  if ( a1 == 2 )
    v33 = (_QWORD *)v49;
  *v32 = *v33;
  v35 = v32 + 1;
  if ( v46 )
  {
    *((_DWORD *)v35 + 4) = 2;
    *(_DWORD *)v35 = 2;
    if ( v46 == 255 )
    {
      v36 = __ROR2__(v16, 8);
      v37 = v36;
    }
    else
    {
      v36 = __ROR2__(v16 | ~v46, 8);
      v37 = __ROR2__(v46 & v16, 8);
    }
    *((_WORD *)v35 + 4) = v37;
    *((_WORD *)v35 + 12) = v36;
    v30[9] = v35;
    v35 += 4;
    *((_DWORD *)v30 + 14) = 5;
    *(GUID *)v34 = FWPM_CONDITION_IP_LOCAL_PORT;
    *((_DWORD *)v30 + 16) = 258;
    v34 = (char *)(v30 + 10);
  }
  if ( v47 )
  {
    *((_DWORD *)v35 + 4) = 2;
    *(_DWORD *)v35 = 2;
    if ( v47 == 255 )
    {
      v38 = __ROR2__(v15, 8);
      v39 = v38;
    }
    else
    {
      v38 = __ROR2__(v15 | ~v47, 8);
      v39 = __ROR2__(v47 & v15, 8);
    }
    *((_WORD *)v35 + 4) = v39;
    *((_WORD *)v35 + 12) = v38;
    *((_QWORD *)v34 + 4) = v35;
    v35 += 4;
    *((_DWORD *)v34 + 4) = 5;
    *(GUID *)v34 = FWPM_CONDITION_IP_REMOTE_PORT;
    *((_DWORD *)v34 + 6) = 258;
    v34 += 40;
  }
  if ( a1 == 2 )
  {
    v40 = *(_DWORD *)(v50 + 8);
    if ( v40 )
    {
      *((_DWORD *)v35 + 1) = _byteswap_ulong(v40);
      *(_DWORD *)v35 = _byteswap_ulong(*(_DWORD *)(v49 + 8));
      *((_QWORD *)v34 + 4) = v35++;
      *(GUID *)v34 = FWPM_CONDITION_IP_LOCAL_ADDRESS;
      *((_DWORD *)v34 + 4) = 0;
      *((_DWORD *)v34 + 6) = 256;
      v34 += 40;
    }
    v41 = *(_DWORD *)(v50 + 12);
    if ( !v41 )
      goto LABEL_55;
    *((_DWORD *)v35 + 1) = _byteswap_ulong(v41);
    *(_DWORD *)v35 = _byteswap_ulong(*(_DWORD *)(v49 + 12));
    *((_QWORD *)v34 + 4) = v35++;
    *(GUID *)v34 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
    *((_DWORD *)v34 + 6) = 256;
  }
  else
  {
    v42 = *(_BYTE *)(v19 + 8);
    if ( v42 )
    {
      *((_BYTE *)v35 + 16) = v42;
      *(_OWORD *)v35 = *(_OWORD *)(v48 + 8);
      *((_QWORD *)v34 + 4) = v35;
      v35 += 3;
      *(GUID *)v34 = FWPM_CONDITION_IP_LOCAL_ADDRESS;
      *((_DWORD *)v34 + 4) = 0;
      *((_DWORD *)v34 + 6) = 257;
      v34 += 40;
    }
    v43 = *(_BYTE *)(v19 + 24);
    if ( !v43 )
      goto LABEL_55;
    *((_BYTE *)v35 + 16) = v43;
    *(_OWORD *)v35 = *(_OWORD *)(v48 + 24);
    *((_QWORD *)v34 + 4) = v35;
    v35 += 3;
    *(GUID *)v34 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
    *((_DWORD *)v34 + 6) = 257;
  }
  *((_DWORD *)v34 + 4) = 0;
  v34 += 40;
LABEL_55:
  if ( v11 )
  {
    *(_DWORD *)v35 = 1;
    *((_DWORD *)v35 + 4) = 1;
    if ( v11 == 15 )
    {
      v44 = v13;
    }
    else
    {
      v44 = v13 | ~v11;
      v13 &= v11;
    }
    *((_BYTE *)v35 + 8) = v13;
    *((_BYTE *)v35 + 24) = v44;
    *((_DWORD *)v34 + 4) = 5;
    *((_DWORD *)v34 + 6) = 258;
    *(GUID *)v34 = FWPM_CONDITION_IP_PROTOCOL;
    *((_QWORD *)v34 + 4) = v35;
  }
  v31 = 0;
LABEL_61:
  *a5 = v30;
  result = v31;
  *a4 = v26;
  return result;
}

```

## disassembly

```asm
0x14001d008  mov     [rsp+arg_8], rbx
0x14001d00d  mov     [rsp+arg_18], r9
0x14001d012  mov     [rsp+arg_0], cx
0x14001d017  push    rbp
0x14001d018  push    rsi
0x14001d019  push    rdi
0x14001d01a  push    r12
0x14001d01c  push    r13
0x14001d01e  push    r14
0x14001d020  push    r15
0x14001d022  sub     rsp, 40h
0x14001d026  mov     eax, 2Ch ; ','
0x14001d02b  mov     rbx, r8
0x14001d02e  movzx   esi, cx
0x14001d031  mov     r12, rbx
0x14001d034  lea     edi, [rax-2Ah]
0x14001d037  cmp     cx, di
0x14001d03a  lea     r11d, [rax-18h]
0x14001d03e  lea     r10d, [rdi+10h]
0x14001d042  cmovnz  r11d, eax
0x14001d046  lea     r8d, [rdi+0Eh]
0x14001d04a  lea     eax, [rdi+28h]
0x14001d04d  cmovnz  r10d, eax
0x14001d051  lea     eax, [rdi+26h]
0x14001d054  cmovnz  r8d, eax
0x14001d058  xor     r9d, r9d
0x14001d05b  mov     bpl, [r11+rbx]
0x14001d05f  cmp     cx, di
0x14001d062  mov     dil, [r11+rdx]
0x14001d066  mov     rcx, rdx
0x14001d069  movzx   r14d, word ptr [r10+rdx]
0x14001d06e  cmovnz  rcx, r9
0x14001d072  movzx   r15d, word ptr [r8+rdx]
0x14001d077  cmovnz  r12, r9
0x14001d07b  mov     [rsp+78h+var_48], rcx
0x14001d080  mov     eax, r9d
0x14001d083  movzx   ecx, word ptr [r8+rbx]
0x14001d088  cmovnz  rax, rdx
0x14001d08c  mov     [rsp+78h+var_50], rax
0x14001d091  mov     r13d, r9d
0x14001d094  movzx   r9d, word ptr [r10+rbx]
0x14001d099  cmovnz  r13, rbx
0x14001d09d  movzx   eax, cx
0x14001d0a0  mov     [rsp+78h+var_58], cx
0x14001d0a5  neg     ax
0x14001d0a8  mov     [rsp+78h+var_40], r12
0x14001d0ad  movzx   eax, cx
0x14001d0b0  mov     [rsp+78h+var_56], r9w
0x14001d0b6  sbb     edx, edx
0x14001d0b8  and     edx, 48h
0x14001d0bb  add     edx, 30h ; '0'
0x14001d0be  neg     ax
0x14001d0c1  sbb     ecx, ecx
0x14001d0c3  xor     r11d, r11d
0x14001d0c6  neg     ecx
0x14001d0c8  inc     ecx
0x14001d0ca  test    r9w, r9w
0x14001d0ce  jz      short loc_14001D0D5
0x14001d0d0  inc     ecx
0x14001d0d2  add     edx, 48h ; 'H'
0x14001d0d5  test    bpl, bpl
0x14001d0d8  lea     r9d, [rcx+1]
0x14001d0dc  lea     r8d, [rdx+48h]
0x14001d0e0  mov     eax, 2
0x14001d0e5  cmovz   r9d, ecx
0x14001d0e9  cmovz   r8d, edx
0x14001d0ed  lea     r10d, [r9+1]
0x14001d0f1  cmp     si, ax
0x14001d0f4  jnz     short loc_14001D120
0x14001d0f6  mov     eax, [r12+8]
0x14001d0fb  lea     ecx, [r8+30h]
0x14001d0ff  test    eax, eax
0x14001d101  mov     eax, [r12+0Ch]
0x14001d106  cmovz   ecx, r8d
0x14001d10a  cmovz   r10d, r9d
0x14001d10e  test    eax, eax
0x14001d110  lea     ebx, [r10+1]
0x14001d114  lea     edx, [rcx+30h]
0x14001d117  cmovz   ebx, r10d
0x14001d11b  cmovz   edx, ecx
0x14001d11e  jmp     short loc_14001D140
0x14001d120  mov     al, [r13+8]
0x14001d124  lea     edx, [r8+40h]
0x14001d128  test    al, al
0x14001d12a  mov     ebx, r10d
0x14001d12d  cmovz   edx, r8d
0x14001d131  cmovz   ebx, r9d
0x14001d135  cmp     [r13+18h], r11b
0x14001d139  jz      short loc_14001D140
0x14001d13b  inc     ebx
0x14001d13d  add     edx, 40h ; '@'
0x14001d140  mov     ecx, 100h
0x14001d145  mov     r12d, edx
0x14001d148  mov     r8d, 66667750h
0x14001d14e  call    cs:__imp_ExAllocatePool2
0x14001d155  nop     dword ptr [rax+rax+00h]
0x14001d15a  mov     rsi, rax
0x14001d15d  test    rax, rax
0x14001d160  jnz     short loc_14001D1AB
0x14001d162  mov     edi, 0C000009Ah
0x14001d167  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d16e  lea     rax, WPP_GLOBAL_Control
0x14001d175  cmp     rcx, rax
0x14001d178  jz      short loc_14001D1A2
0x14001d17a  cmp     byte ptr [rcx+29h], 2
0x14001d17e  jb      short loc_14001D1A2
0x14001d180  test    dword ptr [rcx+2Ch], 800h
0x14001d187  jz      short loc_14001D1A2
0x14001d189  mov     rcx, [rcx+18h]
0x14001d18d  lea     edx, [rsi+0Ah]
0x14001d190  mov     r9d, 0C000009Ah
0x14001d196  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14001d19d  call    WPP_SF_D
0x14001d1a2  xor     ebx, ebx
0x14001d1a4  xor     esi, esi
0x14001d1a6  jmp     loc_14001D446
0x14001d1ab  mov     r8, r12; Size
0x14001d1ae  xor     edx, edx; Val
0x14001d1b0  mov     rcx, rsi; void *
0x14001d1b3  call    memset
0x14001d1b8  movzx   r9d, [rsp+78h+arg_0]
0x14001d1c1  lea     rcx, [rbx+rbx*4]
0x14001d1c5  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_INTERFACE.Data1
0x14001d1cc  mov     r10, [rsp+78h+var_50]
0x14001d1d1  lea     rdx, [rsi+rcx*8]
0x14001d1d5  mov     r11, [rsp+78h+var_48]
0x14001d1da  xor     r12d, r12d
0x14001d1dd  movzx   r8d, [rsp+78h+var_58]
0x14001d1e3  mov     rax, r10
0x14001d1e6  mov     [rsi+20h], rdx
0x14001d1ea  movdqu  xmmword ptr [rsi], xmm0
0x14001d1ee  lea     ecx, [r12+2]
0x14001d1f3  mov     [rsi+10h], r12d
0x14001d1f7  cmp     r9w, cx
0x14001d1fb  mov     dword ptr [rsi+18h], 4
0x14001d202  lea     rcx, [rsi+28h]
0x14001d206  cmovz   rax, r11
0x14001d20a  mov     rax, [rax]
0x14001d20d  mov     [rdx], rax
0x14001d210  add     rdx, 8
0x14001d214  test    r8w, r8w
0x14001d218  jz      short loc_14001D283
0x14001d21a  lea     eax, [r12+2]
0x14001d21f  mov     [rdx+10h], eax
0x14001d222  mov     [rdx], eax
0x14001d224  mov     eax, 0FFh
0x14001d229  cmp     r8w, ax
0x14001d22d  jz      short loc_14001D249
0x14001d22f  movzx   eax, r8w
0x14001d233  not     ax
0x14001d236  or      ax, r15w
0x14001d23a  and     r15w, r8w
0x14001d23e  ror     ax, 8
0x14001d242  ror     r15w, 8
0x14001d247  jmp     short loc_14001D255
0x14001d249  movzx   eax, r15w
0x14001d24d  ror     ax, 8
0x14001d251  movzx   r15d, ax
0x14001d255  mov     [rdx+8], r15w
0x14001d25a  mov     [rdx+18h], ax
0x14001d25e  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x14001d265  mov     [rcx+20h], rdx
0x14001d269  add     rdx, 20h ; ' '
0x14001d26d  mov     dword ptr [rcx+10h], 5
0x14001d274  movdqu  xmmword ptr [rcx], xmm0
0x14001d278  mov     dword ptr [rcx+18h], 102h
0x14001d27f  add     rcx, 28h ; '('
0x14001d283  movzx   r8d, [rsp+78h+var_56]
0x14001d289  test    r8w, r8w
0x14001d28d  jz      short loc_14001D2FF
0x14001d28f  mov     eax, 2
0x14001d294  mov     [rdx+10h], eax
0x14001d297  mov     [rdx], eax
0x14001d299  mov     eax, 0FFh
0x14001d29e  cmp     r8w, ax
0x14001d2a2  jz      short loc_14001D2BE
0x14001d2a4  movzx   eax, r8w
0x14001d2a8  not     ax
0x14001d2ab  or      ax, r14w
0x14001d2af  and     r14w, r8w
0x14001d2b3  ror     ax, 8
0x14001d2b7  ror     r14w, 8
0x14001d2bc  jmp     short loc_14001D2CA
0x14001d2be  movzx   eax, r14w
0x14001d2c2  ror     ax, 8
0x14001d2c6  movzx   r14d, ax
0x14001d2ca  mov     [rdx+8], r14w
0x14001d2cf  mov     r14d, 28h ; '('
0x14001d2d5  mov     [rdx+18h], ax
0x14001d2d9  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x14001d2e0  mov     [rcx+20h], rdx
0x14001d2e4  add     rdx, 20h ; ' '
0x14001d2e8  mov     dword ptr [rcx+10h], 5
0x14001d2ef  movdqu  xmmword ptr [rcx], xmm0
0x14001d2f3  mov     dword ptr [rcx+18h], 102h
0x14001d2fa  add     rcx, r14
0x14001d2fd  jmp     short loc_14001D305
0x14001d2ff  mov     r14d, 28h ; '('
0x14001d305  mov     eax, 2
0x14001d30a  cmp     r9w, ax
0x14001d30e  jnz     short loc_14001D380
0x14001d310  mov     r8, [rsp+78h+var_40]
0x14001d315  mov     eax, [r8+8]
0x14001d319  test    eax, eax
0x14001d31b  jz      short loc_14001D34B
0x14001d31d  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x14001d324  bswap   eax
0x14001d326  mov     [rdx+4], eax
0x14001d329  mov     eax, [r11+8]
0x14001d32d  bswap   eax
0x14001d32f  mov     [rdx], eax
0x14001d331  mov     [rcx+20h], rdx
0x14001d335  add     rdx, 8
0x14001d339  movdqu  xmmword ptr [rcx], xmm0
0x14001d33d  mov     [rcx+10h], r12d
0x14001d341  mov     dword ptr [rcx+18h], 100h
0x14001d348  add     rcx, r14
0x14001d34b  mov     eax, [r8+0Ch]
0x14001d34f  test    eax, eax
0x14001d351  jz      loc_14001D3EA
0x14001d357  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x14001d35e  bswap   eax
0x14001d360  mov     [rdx+4], eax
0x14001d363  mov     eax, [r11+0Ch]
0x14001d367  bswap   eax
0x14001d369  mov     [rdx], eax
0x14001d36b  mov     [rcx+20h], rdx
0x14001d36f  add     rdx, 8
0x14001d373  movdqu  xmmword ptr [rcx], xmm0
0x14001d377  mov     dword ptr [rcx+18h], 100h
0x14001d37e  jmp     short loc_14001D3E3
0x14001d380  mov     al, [r13+8]
0x14001d384  mov     r8d, 101h
0x14001d38a  test    al, al
0x14001d38c  jz      short loc_14001D3B8
0x14001d38e  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x14001d395  mov     [rdx+10h], al
0x14001d398  movups  xmm0, xmmword ptr [r10+8]
0x14001d39d  movdqu  xmmword ptr [rdx], xmm0
0x14001d3a1  mov     [rcx+20h], rdx
0x14001d3a5  add     rdx, 18h
0x14001d3a9  movdqu  xmmword ptr [rcx], xmm1
0x14001d3ad  mov     [rcx+10h], r12d
0x14001d3b1  mov     [rcx+18h], r8d
0x14001d3b5  add     rcx, r14
0x14001d3b8  mov     al, [r13+18h]
0x14001d3bc  test    al, al
0x14001d3be  jz      short loc_14001D3EA
0x14001d3c0  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x14001d3c7  mov     [rdx+10h], al
0x14001d3ca  movups  xmm0, xmmword ptr [r10+18h]
0x14001d3cf  movdqu  xmmword ptr [rdx], xmm0
0x14001d3d3  mov     [rcx+20h], rdx
0x14001d3d7  add     rdx, 18h
0x14001d3db  movdqu  xmmword ptr [rcx], xmm1
0x14001d3df  mov     [rcx+18h], r8d
0x14001d3e3  mov     [rcx+10h], r12d
0x14001d3e7  add     rcx, r14
0x14001d3ea  test    bpl, bpl
0x14001d3ed  jz      short loc_14001D433
0x14001d3ef  mov     eax, 1
0x14001d3f4  mov     [rdx], eax
0x14001d3f6  mov     [rdx+10h], eax
0x14001d3f9  cmp     bpl, 0Fh
0x14001d3fd  jz      short loc_14001D40C
0x14001d3ff  mov     al, bpl
0x14001d402  not     al
0x14001d404  or      al, dil
0x14001d407  and     dil, bpl
0x14001d40a  jmp     short loc_14001D40F
0x14001d40c  mov     al, dil
0x14001d40f  mov     [rdx+8], dil
0x14001d413  mov     [rdx+18h], al
0x14001d416  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x14001d41d  mov     dword ptr [rcx+10h], 5
0x14001d424  mov     dword ptr [rcx+18h], 102h
0x14001d42b  movdqu  xmmword ptr [rcx], xmm0
0x14001d42f  mov     [rcx+20h], rdx
0x14001d433  mov     rax, [rsp+78h+arg_18]
0x14001d43b  mov     edi, r12d
0x14001d43e  mov     [rsp+78h+arg_18], rax
0x14001d446  mov     rax, [rsp+78h+arg_20]
0x14001d44e  mov     [rax], rsi
0x14001d451  mov     eax, edi
0x14001d453  mov     rcx, [rsp+78h+arg_18]
0x14001d45b  mov     [rcx], ebx
0x14001d45d  mov     rbx, [rsp+78h+arg_8]
0x14001d465  add     rsp, 40h
0x14001d469  pop     r15
0x14001d46b  pop     r14
0x14001d46d  pop     r13
0x14001d46f  pop     r12
0x14001d471  pop     rdi
0x14001d472  pop     rsi
0x14001d473  pop     rbp
0x14001d474  retn
```
