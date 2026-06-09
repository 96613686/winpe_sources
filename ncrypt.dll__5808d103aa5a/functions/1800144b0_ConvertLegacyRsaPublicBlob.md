# ConvertLegacyRsaPublicBlob

- ea: `0x1800144b0`
- end: `0x180014640`
- name: `ConvertLegacyRsaPublicBlob`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x18000d02c`
- `0x1800144b0`
- `0x180014648`
- `0x1800146b0`
- `0x18001f175`

## string_xrefs

- `0x180014571`: `onecore\ds\security\cryptoapi\ncrypt\common\translate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyRsaPublicBlob(__int64 a1, __int64 a2, char *a3, __int64 a4, unsigned int *a5)
{
  int v7; // edx
  unsigned int v8; // ebx
  int v9; // r8d
  unsigned int v10; // r9d
  _DWORD *v11; // r10
  unsigned int v12; // r11d
  int v14; // ebp
  int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // ebx
  unsigned int v18; // eax
  char *v19; // r9
  char *v20; // r14
  char *v21; // rcx
  char *i; // rdx
  int v23; // [rsp+48h] [rbp-30h] BYREF

  v8 = VerifyLegacyRsaPublicBlob();
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v9,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\translate.c",
        74);
    return v8;
  }
  else
  {
    if ( !a1 || v12 < 0x14 )
      return 2148073511LL;
    if ( v11 )
      *v11 = (HIDWORD(*(_QWORD *)a1) == 9216) + 1;
    v14 = *(_DWORD *)(a1 + 12);
    v15 = *(_DWORD *)(a1 + 16);
    v16 = (unsigned int)(v14 + 7) >> 3;
    v23 = v15;
    if ( (v15 & 0xFF000000) != 0 )
    {
      v17 = 4;
    }
    else if ( (v15 & 0xFF0000) != 0 )
    {
      v17 = 3;
    }
    else
    {
      v17 = ((v15 & 0xFF00) != 0) + 1;
    }
    v18 = v17 + v16 + 24;
    *a5 = v18;
    if ( !a3 )
      return 0;
    if ( v10 >= v18 )
    {
      memset_0(a3, 0, v10);
      *(_DWORD *)a3 = 826364754;
      v19 = (char *)&v23;
      *((_DWORD *)a3 + 1) = v14;
      *((_DWORD *)a3 + 2) = v17;
      *((_DWORD *)a3 + 3) = v16;
      *((_QWORD *)a3 + 2) = 0;
      v20 = a3 + 24;
      v21 = &v20[v17];
      for ( i = v21 - 1; i >= v20; --i )
        *i = *v19++;
      ReverseMemCopy(v21, a1 + 20, v16);
      return 0;
    }
    return 2148073512LL;
  }
}

```

## disassembly

```asm
0x1800144b0  mov     [rsp+arg_8], rbx
0x1800144b5  push    rbp
0x1800144b6  push    rsi
0x1800144b7  push    rdi
0x1800144b8  push    r14
0x1800144ba  push    r15
0x1800144bc  sub     rsp, 50h
0x1800144c0  mov     r15, [rsp+78h+arg_20]
0x1800144c8  mov     r14, r8
0x1800144cb  mov     r10, [rsp+78h+arg_28]
0x1800144d3  mov     r11d, edx
0x1800144d6  mov     rdi, rcx
0x1800144d9  call    VerifyLegacyRsaPublicBlob
0x1800144de  mov     ebx, eax
0x1800144e0  test    eax, eax
0x1800144e2  jnz     short loc_180014554
0x1800144e4  test    rdi, rdi
0x1800144e7  jnz     short loc_180014502
0x1800144e9  mov     eax, 80090027h
0x1800144ee  mov     rbx, [rsp+78h+arg_8]
0x1800144f6  add     rsp, 50h
0x1800144fa  pop     r15
0x1800144fc  pop     r14
0x1800144fe  pop     rdi
0x1800144ff  pop     rsi
0x180014500  pop     rbp
0x180014501  retn
0x180014502  cmp     r11d, 14h
0x180014506  jb      short loc_1800144E9
0x180014508  test    r10, r10
0x18001450b  jnz     loc_180014609
0x180014511  mov     ebp, [rdi+0Ch]
0x180014514  mov     eax, [rdi+8]
0x180014517  mov     [rsp+78h+var_38], eax
0x18001451b  mov     eax, [rdi+10h]
0x18001451e  lea     esi, [rbp+7]
0x180014521  mov     [rsp+78h+var_34], ebp
0x180014525  shr     esi, 3
0x180014528  mov     [rsp+78h+var_30], eax
0x18001452c  test    eax, 0FF000000h
0x180014531  jnz     short loc_18001459C
0x180014533  test    eax, 0FF0000h
0x180014538  jz      loc_180014624
0x18001453e  mov     ebx, 3
0x180014543  lea     eax, [rsi+18h]
0x180014546  add     eax, ebx
0x180014548  mov     [r15], eax
0x18001454b  test    r14, r14
0x18001454e  jnz     short loc_1800145A3
0x180014550  xor     eax, eax
0x180014552  jmp     short loc_1800144EE
0x180014554  mov     rcx, cs:WPP_GLOBAL_Control
0x18001455b  lea     rax, WPP_GLOBAL_Control
0x180014562  cmp     rcx, rax
0x180014565  jz      short loc_180014595
0x180014567  test    byte ptr [rcx+1Ch], 1
0x18001456b  jz      short loc_180014595
0x18001456d  mov     rcx, [rcx+10h]
0x180014571  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014578  mov     [rsp+78h+var_48], 4Ah ; 'J'
0x180014580  lea     r9, aStatus; "Status"
0x180014587  mov     [rsp+78h+var_50], rax
0x18001458c  mov     [rsp+78h+var_58], ebx
0x180014590  call    WPP_SF_sDsd
0x180014595  mov     eax, ebx
0x180014597  jmp     loc_1800144EE
0x18001459c  mov     ebx, 4
0x1800145a1  jmp     short loc_180014543
0x1800145a3  cmp     r9d, eax
0x1800145a6  jb      loc_180014636
0x1800145ac  mov     r8d, r9d; Size
0x1800145af  xor     edx, edx; Val
0x1800145b1  mov     rcx, r14; void *
0x1800145b4  call    memset_0
0x1800145b9  mov     dword ptr [r14], 31415352h
0x1800145c0  lea     r9, [rsp+78h+var_30]
0x1800145c5  mov     [r14+4], ebp
0x1800145c9  mov     [r14+8], ebx
0x1800145cd  mov     [r14+0Ch], esi
0x1800145d1  mov     qword ptr [r14+10h], 0
0x1800145d9  add     r14, 18h
0x1800145dd  mov     ecx, ebx
0x1800145df  add     rcx, r14
0x1800145e2  lea     rdx, [rcx-1]
0x1800145e6  jmp     short loc_1800145F3
0x1800145e8  mov     al, [r9]
0x1800145eb  mov     [rdx], al
0x1800145ed  dec     rdx
0x1800145f0  inc     r9
0x1800145f3  cmp     rdx, r14
0x1800145f6  jnb     short loc_1800145E8
0x1800145f8  lea     rdx, [rdi+14h]
0x1800145fc  mov     r8d, esi
0x1800145ff  call    ReverseMemCopy
0x180014604  jmp     loc_180014550
0x180014609  mov     rax, [rdi]
0x18001460c  xor     ecx, ecx
0x18001460e  shr     rax, 20h
0x180014612  cmp     eax, 2400h
0x180014617  setz    cl
0x18001461a  inc     ecx
0x18001461c  mov     [r10], ecx
0x18001461f  jmp     loc_180014511
0x180014624  and     eax, 0FF00h
0x180014629  neg     eax
0x18001462b  sbb     ebx, ebx
0x18001462d  neg     ebx
0x18001462f  inc     ebx
0x180014631  jmp     loc_180014543
0x180014636  mov     eax, 80090028h
0x18001463b  jmp     loc_1800144EE
```
