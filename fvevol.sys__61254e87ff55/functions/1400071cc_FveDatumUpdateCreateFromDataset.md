# FveDatumUpdateCreateFromDataset

- ea: `0x1400071cc`
- end: `0x140007313`
- name: `FveDatumUpdateCreateFromDataset`
- size: `327`
- prototype: `__int64 __fastcall(PUCHAR pbInput)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400675c4`
- `0x1400678d8`

## callees

- `0x140005e60`
- `0x1400071cc`
- `0x14000731c`
- `0x1400074f8`

## import_xrefs

- `ksecdd!BCryptDestroyHash` at `0x1400072c0`
- `ksecdd!BCryptDestroyHash` at `0x1400072c0`
- `ksecdd!BCryptFinishHash` at `0x1400072a4`
- `ksecdd!BCryptFinishHash` at `0x1400072a4`
- `ksecdd!BCryptHashData` at `0x14000727a`
- `ksecdd!BCryptHashData` at `0x14000727a`
- `ksecdd!BCryptCreateHash` at `0x140007249`
- `ksecdd!BCryptCreateHash` at `0x140007249`

## pseudocode

```c
__int64 __fastcall FveDatumUpdateCreateFromDataset(PUCHAR pbInput, _QWORD *a2, __int64 a3)
{
  NTSTATUS updated; // ebx
  __int64 v6; // rdi
  NTSTATUS v7; // eax
  char v8; // r8
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-18h] BYREF
  char v11; // [rsp+48h] [rbp-10h]
  int v12; // [rsp+49h] [rbp-Fh]
  __int16 v13; // [rsp+4Dh] [rbp-Bh]
  char v14; // [rsp+4Fh] [rbp-9h]
  __int64 v15; // [rsp+88h] [rbp+30h] BYREF

  phHash = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  *a2 = 0;
  v15 = 0;
  v11 = 0;
  updated = FveDatumUpdateCreate(pbInput, a2, a3, &v15);
  if ( updated < 0 )
    goto LABEL_16;
  updated = FveSha256Initialize();
  if ( updated < 0 )
    goto LABEL_16;
  updated = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( updated < 0 )
    goto LABEL_16;
  v11 = 1;
  if ( !pbInput )
  {
    updated = -1073741811;
    goto LABEL_16;
  }
  updated = BCryptHashData(phHash, pbInput, *((_DWORD *)pbInput + 3), 0);
  if ( updated < 0 )
  {
LABEL_16:
    v6 = v15;
    goto LABEL_9;
  }
  v6 = v15;
  if ( v15 == -12 )
  {
    updated = -1073741811;
  }
  else
  {
    updated = BCryptFinishHash(phHash, (PUCHAR)(v15 + 12), 0x20u, 0);
    if ( updated >= 0 )
    {
      *a2 = v6;
      v6 = 0;
    }
  }
LABEL_9:
  if ( v11 )
  {
    v7 = BCryptDestroyHash(phHash);
    v8 = v11;
    if ( v7 >= 0 )
      v8 = 0;
    v11 = v8;
  }
  if ( v6 )
    FveDatumFree(v6);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400071cc  push    rbp
0x1400071ce  push    rbx
0x1400071cf  push    rsi
0x1400071d0  push    rdi
0x1400071d1  mov     rbp, rsp
0x1400071d4  sub     rsp, 58h
0x1400071d8  xor     eax, eax
0x1400071da  mov     [rbp+phHash], 0
0x1400071e2  lea     r9, [rbp+arg_8]
0x1400071e6  mov     [rbp+var_F], eax
0x1400071e9  mov     [rbp+var_B], ax
0x1400071ed  mov     rsi, rdx
0x1400071f0  mov     [rbp+var_9], al
0x1400071f3  mov     rdi, rcx
0x1400071f6  mov     [rdx], rax
0x1400071f9  mov     [rbp+arg_8], rax
0x1400071fd  mov     [rbp+var_10], 0
0x140007201  call    FveDatumUpdateCreate
0x140007206  mov     ebx, eax
0x140007208  test    eax, eax
0x14000720a  js      loc_1400072EE
0x140007210  call    FveSha256Initialize
0x140007215  mov     ebx, eax
0x140007217  test    eax, eax
0x140007219  js      loc_1400072EE
0x14000721f  mov     rcx, cs:hAlgorithm; hAlgorithm
0x140007226  lea     rdx, [rbp+phHash]; phHash
0x14000722a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140007232  xor     r9d, r9d; cbHashObject
0x140007235  mov     [rsp+58h+cbSecret], 0; cbSecret
0x14000723d  xor     r8d, r8d; pbHashObject
0x140007240  mov     [rsp+58h+pbSecret], 0; pbSecret
0x140007249  call    cs:__imp_BCryptCreateHash
0x140007250  nop     dword ptr [rax+rax+00h]
0x140007255  mov     ebx, eax
0x140007257  test    eax, eax
0x140007259  js      loc_1400072EE
0x14000725f  mov     [rbp+var_10], 1
0x140007263  test    rdi, rdi
0x140007266  jz      loc_140007302
0x14000726c  mov     r8d, [rdi+0Ch]; cbInput
0x140007270  xor     r9d, r9d; dwFlags
0x140007273  mov     rcx, [rbp+phHash]; hHash
0x140007277  mov     rdx, rdi; pbInput
0x14000727a  call    cs:__imp_BCryptHashData
0x140007281  nop     dword ptr [rax+rax+00h]
0x140007286  mov     ebx, eax
0x140007288  test    eax, eax
0x14000728a  js      short loc_1400072EE
0x14000728c  mov     rdi, [rbp+arg_8]
0x140007290  lea     rdx, [rdi+0Ch]; pbOutput
0x140007294  test    rdx, rdx
0x140007297  jz      short loc_1400072FB
0x140007299  mov     rcx, [rbp+phHash]; hHash
0x14000729d  xor     r9d, r9d; dwFlags
0x1400072a0  lea     r8d, [r9+20h]; cbOutput
0x1400072a4  call    cs:__imp_BCryptFinishHash
0x1400072ab  nop     dword ptr [rax+rax+00h]
0x1400072b0  mov     ebx, eax
0x1400072b2  test    eax, eax
0x1400072b4  jns     short loc_1400072F4
0x1400072b6  cmp     [rbp+var_10], 0
0x1400072ba  jz      short loc_1400072DD
0x1400072bc  mov     rcx, [rbp+phHash]; hHash
0x1400072c0  call    cs:__imp_BCryptDestroyHash
0x1400072c7  nop     dword ptr [rax+rax+00h]
0x1400072cc  movzx   r8d, [rbp+var_10]
0x1400072d1  xor     edx, edx
0x1400072d3  test    eax, eax
0x1400072d5  cmovns  r8d, edx
0x1400072d9  mov     [rbp+var_10], r8b
0x1400072dd  test    rdi, rdi
0x1400072e0  jnz     short loc_140007309
0x1400072e2  mov     eax, ebx
0x1400072e4  add     rsp, 58h
0x1400072e8  pop     rdi
0x1400072e9  pop     rsi
0x1400072ea  pop     rbx
0x1400072eb  pop     rbp
0x1400072ec  retn
0x1400072ee  mov     rdi, [rbp+arg_8]
0x1400072f2  jmp     short loc_1400072B6
0x1400072f4  mov     [rsi], rdi
0x1400072f7  xor     edi, edi
0x1400072f9  jmp     short loc_1400072B6
0x1400072fb  mov     ebx, 0C000000Dh
0x140007300  jmp     short loc_1400072B6
0x140007302  mov     ebx, 0C000000Dh
0x140007307  jmp     short loc_1400072EE
0x140007309  mov     rcx, rdi
0x14000730c  call    FveDatumFree
0x140007311  jmp     short loc_1400072E2
```
