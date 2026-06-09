# CreateCompressorOrDecompressor

- ea: `0x180011f60`
- end: `0x1800120a3`
- name: `CreateCompressorOrDecompressor`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f30`
- `0x180011f50`

## callees

- `0x180011f60`
- `0x1800120ac`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012069`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012069`

## pseudocode

```c
__int64 __fastcall CreateCompressorOrDecompressor(int a1, __int64 a2, __int64 *a3, int a4)
{
  int v5; // edi
  unsigned int v6; // ecx
  int v7; // eax
  unsigned int v8; // ecx
  __int64 (__fastcall *v9)(); // rsi
  __int64 v10; // r14
  __int64 (__fastcall *v11)(); // rbp
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 *v14; // r9
  __int64 v15; // rax
  DWORD v17; // ecx

  v5 = a1;
  if ( !a3 )
    goto LABEL_18;
  v6 = a1 & 0xDFFFFFFF;
  if ( v6 - 1 > 4 )
    goto LABEL_18;
  v7 = CmpsRegistrySettings;
  v8 = 2 * v6;
  if ( a4 )
  {
    if ( !_bittest(&v7, v8) )
    {
      v5 |= 0x40000000u;
      goto LABEL_6;
    }
LABEL_14:
    v17 = 769;
    goto LABEL_15;
  }
  if ( _bittest(&v7, (unsigned __int8)(v8 + 1)) )
    goto LABEL_14;
LABEL_6:
  if ( a2 )
  {
    v9 = *(__int64 (__fastcall **)())a2;
    if ( *(_QWORD *)a2 )
    {
      v11 = *(__int64 (__fastcall **)())(a2 + 8);
      if ( v11 )
      {
        v10 = *(_QWORD *)(a2 + 16);
        goto LABEL_8;
      }
    }
LABEL_18:
    v17 = 87;
    goto LABEL_15;
  }
  v9 = CompressInternalAllocate;
  v10 = 0;
  v11 = CompressInternalFree;
LABEL_8:
  v12 = ((__int64 (__fastcall *)(__int64, __int64))v9)(v10, 40);
  v13 = v12;
  if ( v12 )
  {
    *(_QWORD *)(v12 + 4) = 0;
    v14 = &qword_18001D120;
    *(_DWORD *)(v12 + 12) = 0;
    *(_DWORD *)v12 = v5;
    *(_QWORD *)(v12 + 16) = v9;
    *(_QWORD *)(v12 + 24) = v11;
    *(_QWORD *)(v12 + 32) = v10;
    if ( (v5 & 0x40000000) == 0 )
      v14 = &qword_18001D000;
    v15 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64))v14[6 * (v5 & 0x9FFFFFFF)])(
            v9,
            v11,
            v10);
    *(_QWORD *)(v13 + 8) = v15;
    if ( v15 )
    {
      *a3 = v13;
      return 1;
    }
    CmpsFreeContext(v13);
  }
  v17 = 8;
LABEL_15:
  SetLastError(v17);
  return 0;
}

```

## disassembly

```asm
0x180011f60  push    rbx
0x180011f62  push    rbp
0x180011f63  push    rsi
0x180011f64  push    rdi
0x180011f65  push    r14
0x180011f67  push    r15
0x180011f69  sub     rsp, 28h
0x180011f6d  mov     r15, r8
0x180011f70  mov     r10, rdx
0x180011f73  mov     edi, ecx
0x180011f75  test    r8, r8
0x180011f78  jz      loc_180012082
0x180011f7e  btr     ecx, 1Dh
0x180011f82  lea     eax, [rcx-1]
0x180011f85  cmp     eax, 4
0x180011f88  ja      loc_180012082
0x180011f8e  mov     eax, cs:CmpsRegistrySettings
0x180011f94  add     ecx, ecx
0x180011f96  test    r9d, r9d
0x180011f99  jz      loc_180012056
0x180011f9f  bt      eax, ecx
0x180011fa2  jb      loc_180012064
0x180011fa8  bts     edi, 1Eh
0x180011fac  test    r10, r10
0x180011faf  jnz     loc_180012089
0x180011fb5  lea     rsi, CompressInternalAllocate
0x180011fbc  xor     r14d, r14d
0x180011fbf  lea     rbp, CompressInternalFree
0x180011fc6  mov     edx, 28h ; '('
0x180011fcb  mov     rcx, r14
0x180011fce  mov     rax, rsi
0x180011fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fd6  mov     rbx, rax
0x180011fd9  test    rax, rax
0x180011fdc  jz      loc_18001207B
0x180011fe2  mov     qword ptr [rax+4], 0
0x180011fea  lea     r9, qword_18001D120
0x180011ff1  mov     dword ptr [rax+0Ch], 0
0x180011ff8  mov     ecx, 9FFFFFFFh
0x180011ffd  mov     [rax], edi
0x180011fff  bt      edi, 1Eh
0x180012003  mov     [rax+10h], rsi
0x180012007  mov     r8, r14
0x18001200a  mov     [rax+18h], rbp
0x18001200e  mov     rdx, rbp
0x180012011  mov     [rax+20h], r14
0x180012015  lea     rax, qword_18001D000
0x18001201c  cmovnb  r9, rax
0x180012020  mov     eax, edi
0x180012022  and     rax, rcx
0x180012025  mov     rcx, rsi
0x180012028  lea     rax, [rax+rax*2]
0x18001202c  add     rax, rax
0x18001202f  mov     rax, [r9+rax*8]
0x180012033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012038  mov     [rbx+8], rax
0x18001203c  test    rax, rax
0x18001203f  jz      short loc_180012073
0x180012041  mov     [r15], rbx
0x180012044  mov     eax, 1
0x180012049  add     rsp, 28h
0x18001204d  pop     r15
0x18001204f  pop     r14
0x180012051  pop     rdi
0x180012052  pop     rsi
0x180012053  pop     rbp
0x180012054  pop     rbx
0x180012055  retn
0x180012056  inc     ecx
0x180012058  movzx   edx, cl
0x18001205b  bt      eax, edx
0x18001205e  jnb     loc_180011FAC
0x180012064  mov     ecx, 301h; dwErrCode
0x180012069  call    cs:__imp_SetLastError
0x18001206f  xor     eax, eax
0x180012071  jmp     short loc_180012049
0x180012073  mov     rcx, rbx
0x180012076  call    CmpsFreeContext
0x18001207b  mov     ecx, 8
0x180012080  jmp     short loc_180012069
0x180012082  mov     ecx, 57h ; 'W'
0x180012087  jmp     short loc_180012069
0x180012089  mov     rsi, [r10]
0x18001208c  test    rsi, rsi
0x18001208f  jz      short loc_180012082
0x180012091  mov     rbp, [r10+8]
0x180012095  test    rbp, rbp
0x180012098  jz      short loc_180012082
0x18001209a  mov     r14, [r10+10h]
0x18001209e  jmp     loc_180011FC6
```
