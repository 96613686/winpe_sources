# EtwpUpdateEnableInfoAndCallback

- ea: `0x18006a990`
- end: `0x18006ac0f`
- name: `EtwpUpdateEnableInfoAndCallback`
- size: `639`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180033cf0`
- `0x180064360`
- `0x18006a6e0`
- `0x18006aee0`
- `0x18008f4e0`

## callees

- `0x1800183a0`
- `0x180032ed8`
- `0x18003313c`
- `0x1800332d0`
- `0x18006a990`
- `0x18006ac20`
- `0x180095160`
- `0x1800959f4`
- `0x1800e248c`
- `0x1800eddcc`
- `0x180100b80`
- `0x180100ca0`

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
0x18006a990  push    rbx
0x18006a992  push    rbp
0x18006a993  push    rsi
0x18006a994  push    rdi
0x18006a995  push    r12
0x18006a997  push    r13
0x18006a999  push    r14
0x18006a99b  push    r15
0x18006a99d  sub     rsp, 28h
0x18006a9a1  mov     esi, [rdx+48h]
0x18006a9a4  xor     r14b, r14b
0x18006a9a7  mov     rbx, rdx
0x18006a9aa  mov     rdi, rcx
0x18006a9ad  mov     r13d, 3FFFh
0x18006a9b3  cmp     esi, 2
0x18006a9b6  jz      short loc_18006AA19
0x18006a9b8  movzx   eax, word ptr [rdx+4Eh]
0x18006a9bc  mov     r12d, 4
0x18006a9c2  mov     r15, [rcx+0F0h]
0x18006a9c9  test    ax, ax
0x18006a9cc  js      loc_18006AA5B
0x18006a9d2  xor     bpl, bpl
0x18006a9d5  lea     r8, [rcx+60h]
0x18006a9d9  mov     rax, [rbx+60h]
0x18006a9dd  test    esi, esi
0x18006a9df  movzx   r14d, byte ptr [r8+14h]
0x18006a9e4  mov     [r8], rax
0x18006a9e7  mov     rax, [rbx+58h]
0x18006a9eb  mov     [r8+8], rax
0x18006a9ef  movzx   eax, byte ptr [rbx+4Ch]
0x18006a9f3  mov     [r8+15h], al
0x18006a9f7  mov     eax, [rbx+50h]
0x18006a9fa  mov     [r8+10h], eax
0x18006a9fe  setnz   al
0x18006aa01  mov     [r8+14h], al
0x18006aa05  cmp     word ptr [rbx+4Eh], 0
0x18006aa0a  jl      loc_18006AAE3
0x18006aa10  test    bpl, bpl
0x18006aa13  jnz     loc_18006AAAF
0x18006aa19  cmp     dword ptr [rbx+48h], 0
0x18006aa1d  jz      short loc_18006AA4A
0x18006aa1f  movzx   eax, word ptr [rdi+56h]
0x18006aa23  mov     rdx, rdi
0x18006aa26  and     ax, r13w
0x18006aa2a  mov     rcx, rbx
0x18006aa2d  cmp     ax, 2
0x18006aa31  jz      short loc_18006AA51
0x18006aa33  call    EtwpEventApiCallback
0x18006aa38  add     rsp, 28h
0x18006aa3c  pop     r15
0x18006aa3e  pop     r14
0x18006aa40  pop     r13
0x18006aa42  pop     r12
0x18006aa44  pop     rdi
0x18006aa45  pop     rsi
0x18006aa46  pop     rbp
0x18006aa47  pop     rbx
0x18006aa48  retn
0x18006aa4a  test    r14b, r14b
0x18006aa4d  jz      short loc_18006AA38
0x18006aa4f  jmp     short loc_18006AA1F
0x18006aa51  xor     r8d, r8d
0x18006aa54  call    EtwpRegisterGuidsApiCallback
0x18006aa59  jmp     short loc_18006AA38
0x18006aa5b  cmp     esi, 1
0x18006aa5e  jz      loc_18006AB3B
0x18006aa64  test    r15, r15
0x18006aa67  jz      loc_18006AB9B
0x18006aa6d  mov     rcx, r15
0x18006aa70  call    EtwpAcquireGuidEntryExclusive
0x18006aa75  movzx   r9d, byte ptr [rbx+4Eh]
0x18006aa7a  xor     edx, edx
0x18006aa7c  cmp     edx, r12d
0x18006aa7f  jnb     loc_18006AB4F
0x18006aa85  lea     rcx, [rdx+rdx*2]
0x18006aa89  cmp     [r15+rcx*8+4Ch], r14b
0x18006aa8e  lea     r8, [r15+rcx*8]
0x18006aa92  jz      short loc_18006AADF
0x18006aa94  cmp     [r8+4Eh], r9b
0x18006aa98  jnz     short loc_18006AADF
0x18006aa9a  mov     r12d, edx
0x18006aa9d  add     r8, 38h ; '8'
0x18006aaa1  jz      loc_18006AB4F
0x18006aaa7  mov     bpl, 1
0x18006aaaa  jmp     loc_18006A9D9
0x18006aaaf  lea     rcx, [r15+28h]
0x18006aab3  mov     dword ptr [r15+30h], 0
0x18006aabb  call    RtlReleaseSRWLockExclusive
0x18006aac0  cmp     r12d, 4
0x18006aac4  jnb     loc_18006AA19
0x18006aaca  test    esi, esi
0x18006aacc  jnz     loc_18006AA19
0x18006aad2  mov     rcx, r15
0x18006aad5  call    EtwpDereferenceUmGuidEntry
0x18006aada  jmp     loc_18006AA19
0x18006aadf  inc     edx
0x18006aae1  jmp     short loc_18006AA7C
0x18006aae3  cmp     r12d, 4
0x18006aae7  jnb     short loc_18006AB08
0x18006aae9  movups  xmm0, xmmword ptr [r8]
0x18006aaed  mov     eax, r12d
0x18006aaf0  add     rax, 5
0x18006aaf4  lea     rax, [rax+rax*2]
0x18006aaf8  movups  xmmword ptr [rdi+rax*8], xmm0
0x18006aafc  movsd   xmm1, qword ptr [r8+10h]
0x18006ab02  movsd   qword ptr [rdi+rax*8+10h], xmm1
0x18006ab08  mov     rcx, rdi
0x18006ab0b  call    EtwpUpdatePrivateEnableInfo
0x18006ab10  movzx   ecx, word ptr [rdi+56h]
0x18006ab14  movzx   eax, cx
0x18006ab17  and     ax, r13w
0x18006ab1b  cmp     ax, 2
0x18006ab1f  jz      short loc_18006AB2A
0x18006ab21  test    cx, cx
0x18006ab24  jns     loc_18006AA10
0x18006ab2a  movzx   ecx, word ptr [rbx+4Eh]
0x18006ab2e  mov     rdx, rdi
0x18006ab31  call    EtwpGetUmProcessImageInfo
0x18006ab36  jmp     loc_18006AA10
0x18006ab3b  mov     ecx, eax
0x18006ab3d  call    EtwpIsPrivateLoggerOn
0x18006ab42  test    al, al
0x18006ab44  jz      loc_18006AA38
0x18006ab4a  jmp     loc_18006AA64
0x18006ab4f  test    esi, esi
0x18006ab51  jz      short loc_18006ABC5
0x18006ab53  xor     r12d, r12d
0x18006ab56  cmp     r12d, 4
0x18006ab5a  jnb     short loc_18006AB71
0x18006ab5c  lea     rcx, [r12+r12*2]
0x18006ab60  cmp     [r15+rcx*8+4Ch], r14b
0x18006ab65  lea     r8, [r15+rcx*8]
0x18006ab69  jnz     short loc_18006ABC0
0x18006ab6b  add     r8, 38h ; '8'
0x18006ab6f  jnz     short loc_18006AB87
0x18006ab71  lea     rcx, [r15+28h]
0x18006ab75  mov     dword ptr [r15+30h], 0
0x18006ab7d  call    RtlReleaseSRWLockExclusive
0x18006ab82  jmp     loc_18006AA38
0x18006ab87  mov     rcx, r15
0x18006ab8a  mov     [r8+16h], r9b
0x18006ab8e  call    EtwpReferenceUmGuidEntry
0x18006ab93  mov     bpl, 1
0x18006ab96  jmp     loc_18006A9D9
0x18006ab9b  test    esi, esi
0x18006ab9d  jz      loc_18006AA38
0x18006aba3  lea     rcx, [rdi+20h]; Buf1
0x18006aba7  call    EtwpFindGuidEntry
0x18006abac  mov     r15, rax
0x18006abaf  test    rax, rax
0x18006abb2  jz      short loc_18006ABE1
0x18006abb4  mov     [rdi+0F0h], r15
0x18006abbb  jmp     loc_18006AA6D
0x18006abc0  inc     r12d
0x18006abc3  jmp     short loc_18006AB56
0x18006abc5  xor     edx, edx
0x18006abc7  cmp     edx, 4
0x18006abca  jnb     short loc_18006AB71
0x18006abcc  lea     rcx, [rdx+rdx*2]
0x18006abd0  lea     r8, [rdi+rcx*8]
0x18006abd4  cmp     [r8+8Ch], r14b
0x18006abdb  jnz     short loc_18006ABF7
0x18006abdd  inc     edx
0x18006abdf  jmp     short loc_18006ABC7
0x18006abe1  lea     rcx, [rdi+20h]
0x18006abe5  call    EtwpAllocateUmGuidEntry
0x18006abea  mov     r15, rax
0x18006abed  test    rax, rax
0x18006abf0  jnz     short loc_18006ABB4
0x18006abf2  jmp     loc_18006AA38
0x18006abf7  cmp     [r8+8Eh], r9b
0x18006abfe  jnz     short loc_18006ABDD
0x18006ac00  add     r8, 78h ; 'x'
0x18006ac04  jnz     loc_18006AAA7
0x18006ac0a  jmp     loc_18006AB71
```
