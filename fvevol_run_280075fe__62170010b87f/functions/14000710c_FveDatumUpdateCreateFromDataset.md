# FveDatumUpdateCreateFromDataset

- ea: `0x14000710c`
- end: `0x140007253`
- name: `FveDatumUpdateCreateFromDataset`
- size: `327`
- prototype: `__int64 __fastcall(PUCHAR pbInput)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140065534`
- `0x140065848`

## callees

- `0x140005e50`
- `0x14000710c`
- `0x14000725c`
- `0x140007438`

## import_xrefs

- `ksecdd!BCryptDestroyHash` at `0x140007200`
- `ksecdd!BCryptDestroyHash` at `0x140007200`
- `ksecdd!BCryptFinishHash` at `0x1400071e4`
- `ksecdd!BCryptFinishHash` at `0x1400071e4`
- `ksecdd!BCryptHashData` at `0x1400071ba`
- `ksecdd!BCryptHashData` at `0x1400071ba`
- `ksecdd!BCryptCreateHash` at `0x140007189`
- `ksecdd!BCryptCreateHash` at `0x140007189`

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
0x14000710c  push    rbp
0x14000710e  push    rbx
0x14000710f  push    rsi
0x140007110  push    rdi
0x140007111  mov     rbp, rsp
0x140007114  sub     rsp, 58h
0x140007118  xor     eax, eax
0x14000711a  mov     [rbp+phHash], 0
0x140007122  lea     r9, [rbp+arg_8]
0x140007126  mov     [rbp+var_F], eax
0x140007129  mov     [rbp+var_B], ax
0x14000712d  mov     rsi, rdx
0x140007130  mov     [rbp+var_9], al
0x140007133  mov     rdi, rcx
0x140007136  mov     [rdx], rax
0x140007139  mov     [rbp+arg_8], rax
0x14000713d  mov     [rbp+var_10], 0
0x140007141  call    FveDatumUpdateCreate
0x140007146  mov     ebx, eax
0x140007148  test    eax, eax
0x14000714a  js      loc_14000722E
0x140007150  call    FveSha256Initialize
0x140007155  mov     ebx, eax
0x140007157  test    eax, eax
0x140007159  js      loc_14000722E
0x14000715f  mov     rcx, cs:hAlgorithm; hAlgorithm
0x140007166  lea     rdx, [rbp+phHash]; phHash
0x14000716a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140007172  xor     r9d, r9d; cbHashObject
0x140007175  mov     [rsp+58h+cbSecret], 0; cbSecret
0x14000717d  xor     r8d, r8d; pbHashObject
0x140007180  mov     [rsp+58h+pbSecret], 0; pbSecret
0x140007189  call    cs:__imp_BCryptCreateHash
0x140007190  nop     dword ptr [rax+rax+00h]
0x140007195  mov     ebx, eax
0x140007197  test    eax, eax
0x140007199  js      loc_14000722E
0x14000719f  mov     [rbp+var_10], 1
0x1400071a3  test    rdi, rdi
0x1400071a6  jz      loc_140007242
0x1400071ac  mov     r8d, [rdi+0Ch]; cbInput
0x1400071b0  xor     r9d, r9d; dwFlags
0x1400071b3  mov     rcx, [rbp+phHash]; hHash
0x1400071b7  mov     rdx, rdi; pbInput
0x1400071ba  call    cs:__imp_BCryptHashData
0x1400071c1  nop     dword ptr [rax+rax+00h]
0x1400071c6  mov     ebx, eax
0x1400071c8  test    eax, eax
0x1400071ca  js      short loc_14000722E
0x1400071cc  mov     rdi, [rbp+arg_8]
0x1400071d0  lea     rdx, [rdi+0Ch]; pbOutput
0x1400071d4  test    rdx, rdx
0x1400071d7  jz      short loc_14000723B
0x1400071d9  mov     rcx, [rbp+phHash]; hHash
0x1400071dd  xor     r9d, r9d; dwFlags
0x1400071e0  lea     r8d, [r9+20h]; cbOutput
0x1400071e4  call    cs:__imp_BCryptFinishHash
0x1400071eb  nop     dword ptr [rax+rax+00h]
0x1400071f0  mov     ebx, eax
0x1400071f2  test    eax, eax
0x1400071f4  jns     short loc_140007234
0x1400071f6  cmp     [rbp+var_10], 0
0x1400071fa  jz      short loc_14000721D
0x1400071fc  mov     rcx, [rbp+phHash]; hHash
0x140007200  call    cs:__imp_BCryptDestroyHash
0x140007207  nop     dword ptr [rax+rax+00h]
0x14000720c  movzx   r8d, [rbp+var_10]
0x140007211  xor     edx, edx
0x140007213  test    eax, eax
0x140007215  cmovns  r8d, edx
0x140007219  mov     [rbp+var_10], r8b
0x14000721d  test    rdi, rdi
0x140007220  jnz     short loc_140007249
0x140007222  mov     eax, ebx
0x140007224  add     rsp, 58h
0x140007228  pop     rdi
0x140007229  pop     rsi
0x14000722a  pop     rbx
0x14000722b  pop     rbp
0x14000722c  retn
0x14000722e  mov     rdi, [rbp+arg_8]
0x140007232  jmp     short loc_1400071F6
0x140007234  mov     [rsi], rdi
0x140007237  xor     edi, edi
0x140007239  jmp     short loc_1400071F6
0x14000723b  mov     ebx, 0C000000Dh
0x140007240  jmp     short loc_1400071F6
0x140007242  mov     ebx, 0C000000Dh
0x140007247  jmp     short loc_14000722E
0x140007249  mov     rcx, rdi
0x14000724c  call    FveDatumFree
0x140007251  jmp     short loc_140007222
```
