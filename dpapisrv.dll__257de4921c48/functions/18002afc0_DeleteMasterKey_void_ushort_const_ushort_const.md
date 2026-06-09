# DeleteMasterKey(void *,ushort const *,ushort const *)

- ea: `0x18002afc0`
- end: `0x18002b0e5`
- name: `?DeleteMasterKey@@YAHPEAXPEBG1@Z`
- size: `293`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e9c0`
- `0x18002ea4c`

## callees

- `0x180007f10`
- `0x1800244b8`
- `0x18002afc0`
- `0x18002f3f4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b0c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b0c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b03c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b03c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b0a1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b0a1`

## string_xrefs

- `0x18002b056`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall DeleteMasterKey(void *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  size_t v7; // r14
  size_t v8; // r15
  WCHAR *v9; // rax
  WCHAR *v10; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  do
    ++v3;
  while ( a3[v3] );
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      80,
      (unsigned int)WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      (_DWORD)a2,
      (__int64)a3);
  v7 = (unsigned int)(2 * v5);
  v8 = (unsigned int)(2 * v3);
  v9 = (WCHAR *)LocalAlloc(0, v8 + v7 + 4);
  v10 = v9;
  if ( v9 )
  {
    memcpy_0(v9, a2, v7);
    *(WCHAR *)((char *)v10 + v7) = 92;
    memcpy_0((char *)v10 + v7 + 2, a3, v8);
    *(WCHAR *)((char *)v10 + v7 + v8 + 2) = 0;
    DeleteFileW(v10);
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 4) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v13, v12, a3, a2);
    LocalFree(v10);
    return 1;
  }
  else
  {
    DebugTraceError(
      8,
      "ERROR_NOT_ENOUGH_MEMORY",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
      3035);
    return 0;
  }
}

```

## disassembly

```asm
0x18002afc0  push    rbx
0x18002afc2  push    rbp
0x18002afc3  push    rsi
0x18002afc4  push    rdi
0x18002afc5  push    r12
0x18002afc7  push    r14
0x18002afc9  push    r15
0x18002afcb  sub     rsp, 30h
0x18002afcf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002afd3  mov     rsi, r8
0x18002afd6  mov     rdi, rbx
0x18002afd9  xor     r12d, r12d
0x18002afdc  mov     rbp, rdx
0x18002afdf  inc     rdi
0x18002afe2  cmp     [rdx+rdi*2], r12w
0x18002afe7  jnz     short loc_18002AFDF
0x18002afe9  inc     rbx
0x18002afec  cmp     [r8+rbx*2], r12w
0x18002aff1  jnz     short loc_18002AFE9
0x18002aff3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002affa  lea     rax, WPP_GLOBAL_Control
0x18002b001  cmp     rcx, rax
0x18002b004  jz      short loc_18002B029
0x18002b006  test    byte ptr [rcx+1Ch], 4
0x18002b00a  jz      short loc_18002B029
0x18002b00c  mov     rcx, [rcx+10h]
0x18002b010  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002b017  mov     edx, 50h ; 'P'
0x18002b01c  mov     [rsp+68h+var_48], rsi
0x18002b021  mov     r9, rbp
0x18002b024  call    WPP_SF_SS
0x18002b029  lea     eax, [rdi+rdi]
0x18002b02c  xor     ecx, ecx; uFlags
0x18002b02e  lea     rdx, [rax+4]
0x18002b032  mov     r14d, eax
0x18002b035  lea     r15d, [rbx+rbx]
0x18002b039  add     rdx, r15; uBytes
0x18002b03c  call    cs:__imp_LocalAlloc
0x18002b043  nop     dword ptr [rax+rax+00h]
0x18002b048  mov     rdi, rax
0x18002b04b  test    rax, rax
0x18002b04e  jnz     short loc_18002B070
0x18002b050  mov     r9d, 0BDBh
0x18002b056  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002b05d  lea     rdx, aErrorNotEnough; "ERROR_NOT_ENOUGH_MEMORY"
0x18002b064  lea     ecx, [rax+8]
0x18002b067  call    DebugTraceError
0x18002b06c  xor     eax, eax
0x18002b06e  jmp     short loc_18002B0D5
0x18002b070  mov     r8, r14; Size
0x18002b073  mov     rdx, rbp; Src
0x18002b076  mov     rcx, rdi; void *
0x18002b079  call    memcpy_0
0x18002b07e  lea     rbx, [r14+rdi]
0x18002b082  mov     word ptr [r14+rdi], 5Ch ; '\'
0x18002b089  lea     rcx, [rbx+2]; void *
0x18002b08d  mov     r8, r15; Size
0x18002b090  mov     rdx, rsi; Src
0x18002b093  call    memcpy_0
0x18002b098  mov     rcx, rdi; lpFileName
0x18002b09b  mov     [rbx+r15+2], r12w
0x18002b0a1  call    cs:__imp_DeleteFileW
0x18002b0a8  nop     dword ptr [rax+rax+00h]
0x18002b0ad  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 4
0x18002b0b4  jz      short loc_18002B0C1
0x18002b0b6  mov     r9, rbp
0x18002b0b9  mov     r8, rsi
0x18002b0bc  call    McTemplateU0zz_EtwEventWriteTransfer
0x18002b0c1  mov     rcx, rdi; hMem
0x18002b0c4  call    cs:__imp_LocalFree
0x18002b0cb  nop     dword ptr [rax+rax+00h]
0x18002b0d0  mov     eax, 1
0x18002b0d5  add     rsp, 30h
0x18002b0d9  pop     r15
0x18002b0db  pop     r14
0x18002b0dd  pop     r12
0x18002b0df  pop     rdi
0x18002b0e0  pop     rsi
0x18002b0e1  pop     rbp
0x18002b0e2  pop     rbx
0x18002b0e3  retn
```
