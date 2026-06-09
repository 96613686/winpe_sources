# ASN1BERDecEndOfContents

- ea: `0x180001b30`
- end: `0x180001c10`
- name: `ASN1BERDecEndOfContents`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x180001f80`
- `0x1800026b0`
- `0x180002c20`
- `0x180003270`
- `0x180003be0`
- `0x180004a60`
- `0x180005300`
- `0x180009c10`

## callees

- `0x180001b30`
- `0x180001f50`
- `0x180004310`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001bfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001bfa`

## pseudocode

```c
__int64 __fastcall ASN1BERDecEndOfContents(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  unsigned int v5; // edi
  __int64 v6; // rax
  void *v7; // rcx
  _BYTE *v9; // rax
  _BYTE *v10; // rax

  v3 = a2;
  v5 = -1003;
  if ( !a2 )
    v3 = a1;
  if ( a3 )
  {
    if ( *(_QWORD *)(v3 + 40) == a3 )
    {
      *(_QWORD *)(a1 + 40) = a3;
      v5 = 0;
    }
  }
  else if ( (unsigned int)ASN1BERDecCheck((_DWORD *)v3, 2u) )
  {
    v9 = *(_BYTE **)(v3 + 40);
    if ( !*v9 && !v9[1] )
    {
      v10 = v9 + 2;
      *(_QWORD *)(v3 + 40) = v10;
      if ( v3 != a1 )
        *(_QWORD *)(a1 + 40) = v10;
      v5 = 0;
    }
  }
  else
  {
    v5 = -1002;
  }
  if ( v3 && v3 != a1 )
  {
    v6 = *(_QWORD *)(v3 + 56);
    if ( v3 != v6 )
      *(_QWORD *)(v6 + 64) = 0;
    v7 = *(void **)(v3 + 16);
    if ( v7 && (*(_BYTE *)(v3 + 52) & 0x10) != 0 )
      LocalFree(v7);
    LocalFree((HLOCAL)v3);
  }
  if ( !v5 )
    return 1;
  ASN1DecSetError(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x180001b30  mov     [rsp+arg_0], rbx
0x180001b35  mov     [rsp+arg_8], rsi
0x180001b3a  push    rdi
0x180001b3b  sub     rsp, 20h
0x180001b3f  mov     rbx, rdx
0x180001b42  mov     rsi, rcx
0x180001b45  mov     edi, 0FFFFFC15h
0x180001b4a  test    rdx, rdx
0x180001b4d  jz      loc_180001BF2
0x180001b53  test    r8, r8
0x180001b56  jz      short loc_180001BB0
0x180001b58  cmp     [rbx+28h], r8
0x180001b5c  jnz     short loc_180001B64
0x180001b5e  mov     [rcx+28h], r8
0x180001b62  xor     edi, edi
0x180001b64  test    rbx, rbx
0x180001b67  jz      short loc_180001B97
0x180001b69  cmp     rbx, rsi
0x180001b6c  jz      short loc_180001B97
0x180001b6e  mov     rax, [rbx+38h]
0x180001b72  cmp     rbx, rax
0x180001b75  jz      short loc_180001B7F
0x180001b77  mov     qword ptr [rax+40h], 0
0x180001b7f  mov     rcx, [rbx+10h]; hMem
0x180001b83  test    rcx, rcx
0x180001b86  jz      short loc_180001B8E
0x180001b88  test    byte ptr [rbx+34h], 10h
0x180001b8c  jnz     short loc_180001BFA
0x180001b8e  mov     rcx, rbx; hMem
0x180001b91  call    cs:__imp_LocalFree
0x180001b97  test    edi, edi
0x180001b99  jnz     short loc_180001C02
0x180001b9b  mov     eax, 1
0x180001ba0  mov     rbx, [rsp+28h+arg_0]
0x180001ba5  mov     rsi, [rsp+28h+arg_8]
0x180001baa  add     rsp, 20h
0x180001bae  pop     rdi
0x180001baf  retn
0x180001bb0  mov     edx, 2
0x180001bb5  mov     rcx, rbx
0x180001bb8  call    ASN1BERDecCheck
0x180001bbd  test    eax, eax
0x180001bbf  jz      short loc_180001BE8
0x180001bc1  mov     rax, [rbx+28h]
0x180001bc5  cmp     byte ptr [rax], 0
0x180001bc8  jnz     short loc_180001B64
0x180001bca  cmp     byte ptr [rax+1], 0
0x180001bce  jnz     short loc_180001B64
0x180001bd0  add     rax, 2
0x180001bd4  mov     [rbx+28h], rax
0x180001bd8  cmp     rbx, rsi
0x180001bdb  jz      short loc_180001BE1
0x180001bdd  mov     [rsi+28h], rax
0x180001be1  xor     edi, edi
0x180001be3  jmp     loc_180001B64
0x180001be8  mov     edi, 0FFFFFC16h
0x180001bed  jmp     loc_180001B64
0x180001bf2  mov     rbx, rsi
0x180001bf5  jmp     loc_180001B53
0x180001bfa  call    cs:__imp_LocalFree
0x180001c00  jmp     short loc_180001B8E
0x180001c02  mov     edx, edi
0x180001c04  mov     rcx, rsi
0x180001c07  call    ASN1DecSetError
0x180001c0c  xor     eax, eax
0x180001c0e  jmp     short loc_180001BA0
```
