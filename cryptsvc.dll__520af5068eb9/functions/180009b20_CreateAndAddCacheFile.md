# _CreateAndAddCacheFile

- ea: `0x180009b20`
- end: `0x180009be2`
- name: `_CreateAndAddCacheFile`
- size: `194`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _QWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028f0`

## callees

- `0x1800068b0`
- `0x180009b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bd0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009b49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009b49`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180009ba5`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180009ba5`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180009bb5`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180009bb5`

## pseudocode

```c
__int64 __fastcall CreateAndAddCacheFile(__int64 a1, _OWORD *a2, _QWORD *a3, _OWORD *a4)
{
  char *v8; // rax
  _QWORD *v9; // rbx
  __int128 v10; // xmm1
  __int64 v11; // rcx
  __int128 v13; // [rsp+20h] [rbp-38h] BYREF

  v13 = 0;
  v8 = (char *)LocalAlloc(0x40u, 0x58u);
  v9 = v8;
  if ( v8 )
  {
    *(_OWORD *)(v8 + 24) = *a2;
    v10 = a2[1];
    *((_DWORD *)v8 + 14) = 1;
    *(_OWORD *)(v8 + 40) = v10;
    if ( a3 )
      *(_QWORD *)(v8 + 60) = *a3;
    if ( a4 )
      *(_OWORD *)(v8 + 68) = *a4;
    *((_QWORD *)&v13 + 1) = v8 + 24;
    v11 = *(_QWORD *)(a1 + 104);
    LODWORD(v13) = 32;
    if ( (unsigned int)I_CryptCreateLruEntry(v11, &v13, v8, v8 + 16) )
    {
      I_CryptInsertLruEntry(v9[2], 0);
      return 1;
    }
  }
  else
  {
    SetLastError(0x8007000E);
  }
  PkiFree(v9);
  return 0;
}

```

## disassembly

```asm
0x180009b20  push    rbx
0x180009b22  push    rbp
0x180009b23  push    rsi
0x180009b24  push    rdi
0x180009b25  push    r14
0x180009b27  sub     rsp, 30h
0x180009b2b  mov     rsi, rdx
0x180009b2e  mov     rbp, rcx
0x180009b31  xorps   xmm0, xmm0
0x180009b34  mov     edx, 58h ; 'X'; uBytes
0x180009b39  mov     ecx, 40h ; '@'; uFlags
0x180009b3e  mov     rdi, r9
0x180009b41  movups  [rsp+58h+var_38], xmm0
0x180009b46  mov     r14, r8
0x180009b49  call    cs:__imp_LocalAlloc
0x180009b4f  mov     rbx, rax
0x180009b52  test    rax, rax
0x180009b55  jz      short loc_180009BCB
0x180009b57  lea     rcx, [rax+18h]
0x180009b5b  movups  xmm0, xmmword ptr [rsi]
0x180009b5e  movups  xmmword ptr [rcx], xmm0
0x180009b61  movups  xmm1, xmmword ptr [rsi+10h]
0x180009b65  mov     dword ptr [rax+38h], 1
0x180009b6c  movups  xmmword ptr [rcx+10h], xmm1
0x180009b70  test    r14, r14
0x180009b73  jz      short loc_180009B7C
0x180009b75  mov     rax, [r14]
0x180009b78  mov     [rbx+3Ch], rax
0x180009b7c  test    rdi, rdi
0x180009b7f  jz      short loc_180009B88
0x180009b81  movups  xmm0, xmmword ptr [rdi]
0x180009b84  movups  xmmword ptr [rbx+44h], xmm0
0x180009b88  mov     qword ptr [rsp+58h+var_38+8], rcx
0x180009b8d  lea     r9, [rbx+10h]
0x180009b91  mov     rcx, [rbp+68h]
0x180009b95  lea     rdx, [rsp+58h+var_38]
0x180009b9a  mov     r8, rbx
0x180009b9d  mov     dword ptr [rsp+58h+var_38], 20h ; ' '
0x180009ba5  call    cs:__imp_I_CryptCreateLruEntry
0x180009bab  test    eax, eax
0x180009bad  jz      short loc_180009BD6
0x180009baf  mov     rcx, [rbx+10h]
0x180009bb3  xor     edx, edx
0x180009bb5  call    cs:__imp_I_CryptInsertLruEntry
0x180009bbb  mov     eax, 1
0x180009bc0  add     rsp, 30h
0x180009bc4  pop     r14
0x180009bc6  pop     rdi
0x180009bc7  pop     rsi
0x180009bc8  pop     rbp
0x180009bc9  pop     rbx
0x180009bca  retn
0x180009bcb  mov     ecx, 8007000Eh; dwErrCode
0x180009bd0  call    cs:__imp_SetLastError
0x180009bd6  mov     rcx, rbx; hMem
0x180009bd9  call    PkiFree
0x180009bde  xor     eax, eax
0x180009be0  jmp     short loc_180009BC0
```
