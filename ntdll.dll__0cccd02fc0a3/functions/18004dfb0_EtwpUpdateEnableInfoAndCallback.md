# EtwpUpdateEnableInfoAndCallback

- ea: `0x18004dfb0`
- end: `0x18004e22f`
- name: `EtwpUpdateEnableInfoAndCallback`
- size: `639`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180047760`
- `0x18004d2d0`
- `0x18004dd00`
- `0x18004e500`
- `0x18007f748`

## callees

- `0x1800183a0`
- `0x180033bd8`
- `0x180033e3c`
- `0x180033fe0`
- `0x18004dfb0`
- `0x18004e240`
- `0x180088d00`
- `0x180089594`
- `0x1800e1e7c`
- `0x1800ed2ec`
- `0x180100560`
- `0x180100680`

## pseudocode

```c
void __fastcall EtwpUpdateEnableInfoAndCallback(__int64 a1, __int64 a2)
{
  int v2; // esi
  char v3; // r14
  __int64 j; // r12
  __int64 GuidEntry; // r15
  char v8; // bp
  __int64 v9; // r8
  char v10; // r9
  __int64 i; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int16 v14; // cx
  __int64 k; // rdx
  __int64 v16; // r8

  v2 = *(_DWORD *)(a2 + 72);
  v3 = 0;
  if ( v2 == 2 )
  {
LABEL_6:
    if ( *(_DWORD *)(a2 + 72) || v3 )
    {
      if ( (*(_WORD *)(a1 + 86) & 0x3FFF) == 2 )
        EtwpRegisterGuidsApiCallback(a2, a1, 0);
      else
        EtwpEventApiCallback(a2, a1);
    }
    return;
  }
  LODWORD(j) = 4;
  GuidEntry = *(_QWORD *)(a1 + 240);
  if ( *(__int16 *)(a2 + 78) >= 0 )
  {
    v8 = 0;
    v9 = a1 + 96;
LABEL_4:
    v3 = *(_BYTE *)(v9 + 20);
    *(_QWORD *)v9 = *(_QWORD *)(a2 + 96);
    *(_QWORD *)(v9 + 8) = *(_QWORD *)(a2 + 88);
    *(_BYTE *)(v9 + 21) = *(_BYTE *)(a2 + 76);
    *(_DWORD *)(v9 + 16) = *(_DWORD *)(a2 + 80);
    *(_BYTE *)(v9 + 20) = v2 != 0;
    if ( *(__int16 *)(a2 + 78) < 0 )
    {
      if ( (unsigned int)j < 4 )
      {
        v13 = 3 * ((unsigned int)j + 5LL);
        *(_OWORD *)(a1 + 8 * v13) = *(_OWORD *)v9;
        *(_QWORD *)(a1 + 8 * v13 + 16) = *(_QWORD *)(v9 + 16);
      }
      EtwpUpdatePrivateEnableInfo(a1);
      v14 = *(_WORD *)(a1 + 86);
      if ( (v14 & 0x3FFF) == 2 || v14 < 0 )
        EtwpGetUmProcessImageInfo(*(unsigned __int16 *)(a2 + 78), a1);
    }
    if ( v8 )
    {
      *(_DWORD *)(GuidEntry + 48) = 0;
      RtlReleaseSRWLockExclusive(GuidEntry + 40);
      if ( (unsigned int)j < 4 && !v2 )
        EtwpDereferenceUmGuidEntry(GuidEntry);
    }
    goto LABEL_6;
  }
  if ( v2 != 1 || (unsigned __int8)EtwpIsPrivateLoggerOn(*(unsigned __int16 *)(a2 + 78)) )
  {
    if ( !GuidEntry )
    {
      if ( !v2 )
        return;
      GuidEntry = EtwpFindGuidEntry((void *)(a1 + 32));
      if ( !GuidEntry )
      {
        GuidEntry = EtwpAllocateUmGuidEntry(a1 + 32);
        if ( !GuidEntry )
          return;
      }
      *(_QWORD *)(a1 + 240) = GuidEntry;
    }
    EtwpAcquireGuidEntryExclusive(GuidEntry);
    v10 = *(_BYTE *)(a2 + 78);
    for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
    {
      v12 = GuidEntry + 24 * i;
      if ( *(_BYTE *)(v12 + 76) && *(_BYTE *)(v12 + 78) == v10 )
      {
        LODWORD(j) = i;
        v9 = v12 + 56;
        if ( v9 )
        {
LABEL_20:
          v8 = 1;
          goto LABEL_4;
        }
        break;
      }
    }
    if ( v2 )
    {
      for ( j = 0; (unsigned int)j < 4; j = (unsigned int)(j + 1) )
      {
        if ( !*(_BYTE *)(GuidEntry + 24 * j + 76) )
        {
          if ( GuidEntry + 24 * j == -56 )
            break;
          *(_BYTE *)(GuidEntry + 24 * j + 78) = v10;
          EtwpReferenceUmGuidEntry(GuidEntry);
          v8 = 1;
          goto LABEL_4;
        }
      }
    }
    else
    {
      for ( k = 0; (unsigned int)k < 4; k = (unsigned int)(k + 1) )
      {
        v16 = a1 + 24 * k;
        if ( *(_BYTE *)(v16 + 140) && *(_BYTE *)(v16 + 142) == v10 )
        {
          v9 = v16 + 120;
          if ( v9 )
            goto LABEL_20;
          break;
        }
      }
    }
    *(_DWORD *)(GuidEntry + 48) = 0;
    RtlReleaseSRWLockExclusive(GuidEntry + 40);
  }
}

```

## disassembly

```asm
0x18004dfb0  push    rbx
0x18004dfb2  push    rbp
0x18004dfb3  push    rsi
0x18004dfb4  push    rdi
0x18004dfb5  push    r12
0x18004dfb7  push    r13
0x18004dfb9  push    r14
0x18004dfbb  push    r15
0x18004dfbd  sub     rsp, 28h
0x18004dfc1  mov     esi, [rdx+48h]
0x18004dfc4  xor     r14b, r14b
0x18004dfc7  mov     rbx, rdx
0x18004dfca  mov     rdi, rcx
0x18004dfcd  mov     r13d, 3FFFh
0x18004dfd3  cmp     esi, 2
0x18004dfd6  jz      short loc_18004E039
0x18004dfd8  movzx   eax, word ptr [rdx+4Eh]
0x18004dfdc  mov     r12d, 4
0x18004dfe2  mov     r15, [rcx+0F0h]
0x18004dfe9  test    ax, ax
0x18004dfec  js      loc_18004E07B
0x18004dff2  xor     bpl, bpl
0x18004dff5  lea     r8, [rcx+60h]
0x18004dff9  mov     rax, [rbx+60h]
0x18004dffd  test    esi, esi
0x18004dfff  movzx   r14d, byte ptr [r8+14h]
0x18004e004  mov     [r8], rax
0x18004e007  mov     rax, [rbx+58h]
0x18004e00b  mov     [r8+8], rax
0x18004e00f  movzx   eax, byte ptr [rbx+4Ch]
0x18004e013  mov     [r8+15h], al
0x18004e017  mov     eax, [rbx+50h]
0x18004e01a  mov     [r8+10h], eax
0x18004e01e  setnz   al
0x18004e021  mov     [r8+14h], al
0x18004e025  cmp     word ptr [rbx+4Eh], 0
0x18004e02a  jl      loc_18004E103
0x18004e030  test    bpl, bpl
0x18004e033  jnz     loc_18004E0CF
0x18004e039  cmp     dword ptr [rbx+48h], 0
0x18004e03d  jz      short loc_18004E06A
0x18004e03f  movzx   eax, word ptr [rdi+56h]
0x18004e043  mov     rdx, rdi
0x18004e046  and     ax, r13w
0x18004e04a  mov     rcx, rbx
0x18004e04d  cmp     ax, 2
0x18004e051  jz      short loc_18004E071
0x18004e053  call    EtwpEventApiCallback
0x18004e058  add     rsp, 28h
0x18004e05c  pop     r15
0x18004e05e  pop     r14
0x18004e060  pop     r13
0x18004e062  pop     r12
0x18004e064  pop     rdi
0x18004e065  pop     rsi
0x18004e066  pop     rbp
0x18004e067  pop     rbx
0x18004e068  retn
0x18004e06a  test    r14b, r14b
0x18004e06d  jz      short loc_18004E058
0x18004e06f  jmp     short loc_18004E03F
0x18004e071  xor     r8d, r8d
0x18004e074  call    EtwpRegisterGuidsApiCallback
0x18004e079  jmp     short loc_18004E058
0x18004e07b  cmp     esi, 1
0x18004e07e  jz      loc_18004E15B
0x18004e084  test    r15, r15
0x18004e087  jz      loc_18004E1BB
0x18004e08d  mov     rcx, r15
0x18004e090  call    EtwpAcquireGuidEntryExclusive
0x18004e095  movzx   r9d, byte ptr [rbx+4Eh]
0x18004e09a  xor     edx, edx
0x18004e09c  cmp     edx, r12d
0x18004e09f  jnb     loc_18004E16F
0x18004e0a5  lea     rcx, [rdx+rdx*2]
0x18004e0a9  cmp     [r15+rcx*8+4Ch], r14b
0x18004e0ae  lea     r8, [r15+rcx*8]
0x18004e0b2  jz      short loc_18004E0FF
0x18004e0b4  cmp     [r8+4Eh], r9b
0x18004e0b8  jnz     short loc_18004E0FF
0x18004e0ba  mov     r12d, edx
0x18004e0bd  add     r8, 38h ; '8'
0x18004e0c1  jz      loc_18004E16F
0x18004e0c7  mov     bpl, 1
0x18004e0ca  jmp     loc_18004DFF9
0x18004e0cf  lea     rcx, [r15+28h]
0x18004e0d3  mov     dword ptr [r15+30h], 0
0x18004e0db  call    RtlReleaseSRWLockExclusive
0x18004e0e0  cmp     r12d, 4
0x18004e0e4  jnb     loc_18004E039
0x18004e0ea  test    esi, esi
0x18004e0ec  jnz     loc_18004E039
0x18004e0f2  mov     rcx, r15
0x18004e0f5  call    EtwpDereferenceUmGuidEntry
0x18004e0fa  jmp     loc_18004E039
0x18004e0ff  inc     edx
0x18004e101  jmp     short loc_18004E09C
0x18004e103  cmp     r12d, 4
0x18004e107  jnb     short loc_18004E128
0x18004e109  movups  xmm0, xmmword ptr [r8]
0x18004e10d  mov     eax, r12d
0x18004e110  add     rax, 5
0x18004e114  lea     rax, [rax+rax*2]
0x18004e118  movups  xmmword ptr [rdi+rax*8], xmm0
0x18004e11c  movsd   xmm1, qword ptr [r8+10h]
0x18004e122  movsd   qword ptr [rdi+rax*8+10h], xmm1
0x18004e128  mov     rcx, rdi
0x18004e12b  call    EtwpUpdatePrivateEnableInfo
0x18004e130  movzx   ecx, word ptr [rdi+56h]
0x18004e134  movzx   eax, cx
0x18004e137  and     ax, r13w
0x18004e13b  cmp     ax, 2
0x18004e13f  jz      short loc_18004E14A
0x18004e141  test    cx, cx
0x18004e144  jns     loc_18004E030
0x18004e14a  movzx   ecx, word ptr [rbx+4Eh]
0x18004e14e  mov     rdx, rdi
0x18004e151  call    EtwpGetUmProcessImageInfo
0x18004e156  jmp     loc_18004E030
0x18004e15b  mov     ecx, eax
0x18004e15d  call    EtwpIsPrivateLoggerOn
0x18004e162  test    al, al
0x18004e164  jz      loc_18004E058
0x18004e16a  jmp     loc_18004E084
0x18004e16f  test    esi, esi
0x18004e171  jz      short loc_18004E1E5
0x18004e173  xor     r12d, r12d
0x18004e176  cmp     r12d, 4
0x18004e17a  jnb     short loc_18004E191
0x18004e17c  lea     rcx, [r12+r12*2]
0x18004e180  cmp     [r15+rcx*8+4Ch], r14b
0x18004e185  lea     r8, [r15+rcx*8]
0x18004e189  jnz     short loc_18004E1E0
0x18004e18b  add     r8, 38h ; '8'
0x18004e18f  jnz     short loc_18004E1A7
0x18004e191  lea     rcx, [r15+28h]
0x18004e195  mov     dword ptr [r15+30h], 0
0x18004e19d  call    RtlReleaseSRWLockExclusive
0x18004e1a2  jmp     loc_18004E058
0x18004e1a7  mov     rcx, r15
0x18004e1aa  mov     [r8+16h], r9b
0x18004e1ae  call    EtwpReferenceUmGuidEntry
0x18004e1b3  mov     bpl, 1
0x18004e1b6  jmp     loc_18004DFF9
0x18004e1bb  test    esi, esi
0x18004e1bd  jz      loc_18004E058
0x18004e1c3  lea     rcx, [rdi+20h]; Buf1
0x18004e1c7  call    EtwpFindGuidEntry
0x18004e1cc  mov     r15, rax
0x18004e1cf  test    rax, rax
0x18004e1d2  jz      short loc_18004E201
0x18004e1d4  mov     [rdi+0F0h], r15
0x18004e1db  jmp     loc_18004E08D
0x18004e1e0  inc     r12d
0x18004e1e3  jmp     short loc_18004E176
0x18004e1e5  xor     edx, edx
0x18004e1e7  cmp     edx, 4
0x18004e1ea  jnb     short loc_18004E191
0x18004e1ec  lea     rcx, [rdx+rdx*2]
0x18004e1f0  lea     r8, [rdi+rcx*8]
0x18004e1f4  cmp     [r8+8Ch], r14b
0x18004e1fb  jnz     short loc_18004E217
0x18004e1fd  inc     edx
0x18004e1ff  jmp     short loc_18004E1E7
0x18004e201  lea     rcx, [rdi+20h]
0x18004e205  call    EtwpAllocateUmGuidEntry
0x18004e20a  mov     r15, rax
0x18004e20d  test    rax, rax
0x18004e210  jnz     short loc_18004E1D4
0x18004e212  jmp     loc_18004E058
0x18004e217  cmp     [r8+8Eh], r9b
0x18004e21e  jnz     short loc_18004E1FD
0x18004e220  add     r8, 78h ; 'x'
0x18004e224  jnz     loc_18004E0C7
0x18004e22a  jmp     loc_18004E191
```
