# _GetImagePath

- ea: `0x180008c1c`
- end: `0x180008cf3`
- name: `_GetImagePath`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008a90`

## callees

- `0x180008c1c`
- `0x180009cd0`
- `0x18000a770`
- `0x18000e120`
- `0x18001f15d`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008c38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008c62`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008c38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008c62`

## string_xrefs

- `0x180008ccf`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall GetImagePath(const void **a1, WCHAR **a2)
{
  UINT SystemDirectoryW; // eax
  UINT v5; // ebx
  WCHAR *v6; // rax
  WCHAR *v7; // rsi
  UINT v8; // eax
  __int64 v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v13; // r9

  *a2 = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v5 = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    v6 = (WCHAR *)SafeAllocaAllocateFromHeap(*(unsigned __int16 *)a1 + 4LL + 2LL * SystemDirectoryW);
    v7 = v6;
    if ( !v6 )
    {
      v10 = -1073741801;
      v13 = 1058;
      goto LABEL_10;
    }
    v8 = GetSystemDirectoryW(v6, v5);
    if ( v8 )
    {
      v9 = v8;
      v10 = 0;
      v7[v8] = 92;
      memcpy_0(&v7[v8 + 1], a1[1], *(unsigned __int16 *)a1);
      v11 = v9 + ((unsigned __int64)*(unsigned __int16 *)a1 >> 1);
      *a2 = v7;
      v7[v11 + 1] = 0;
      return v10;
    }
    v13 = 1067;
  }
  else
  {
    v7 = 0;
    v13 = 1049;
  }
  v10 = -1073741766;
LABEL_10:
  DebugTraceError(v10, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v13);
  if ( v7 )
    MSCryptFree(v7);
  return v10;
}

```

## disassembly

```asm
0x180008c1c  push    rbx
0x180008c1e  push    rbp
0x180008c1f  push    rsi
0x180008c20  push    rdi
0x180008c21  push    r14
0x180008c23  sub     rsp, 20h
0x180008c27  mov     r14, rdx
0x180008c2a  mov     qword ptr [rdx], 0
0x180008c31  mov     rbp, rcx
0x180008c34  xor     edx, edx; uSize
0x180008c36  xor     ecx, ecx; lpBuffer
0x180008c38  call    cs:__imp_GetSystemDirectoryW
0x180008c3e  mov     ebx, eax
0x180008c40  test    eax, eax
0x180008c42  jz      short loc_180008CAD
0x180008c44  movzx   eax, word ptr [rbp+0]
0x180008c48  add     rax, 4
0x180008c4c  lea     rcx, [rax+rbx*2]
0x180008c50  call    SafeAllocaAllocateFromHeap
0x180008c55  mov     rsi, rax
0x180008c58  test    rax, rax
0x180008c5b  jz      short loc_180008CB7
0x180008c5d  mov     edx, ebx; uSize
0x180008c5f  mov     rcx, rax; lpBuffer
0x180008c62  call    cs:__imp_GetSystemDirectoryW
0x180008c68  test    eax, eax
0x180008c6a  jz      short loc_180008CC4
0x180008c6c  mov     ebx, eax
0x180008c6e  xor     edi, edi
0x180008c70  mov     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180008c76  lea     rcx, [rbx+1]
0x180008c7a  movzx   r8d, word ptr [rbp+0]; Size
0x180008c7f  lea     rcx, [rsi+rcx*2]; void *
0x180008c83  mov     rdx, [rbp+8]; Src
0x180008c87  call    memcpy_0
0x180008c8c  movzx   edx, word ptr [rbp+0]
0x180008c90  shr     rdx, 1
0x180008c93  add     rdx, rbx
0x180008c96  mov     [r14], rsi
0x180008c99  xor     ecx, ecx
0x180008c9b  mov     [rsi+rdx*2+2], cx
0x180008ca0  mov     eax, edi
0x180008ca2  add     rsp, 20h
0x180008ca6  pop     r14
0x180008ca8  pop     rdi
0x180008ca9  pop     rsi
0x180008caa  pop     rbp
0x180008cab  pop     rbx
0x180008cac  retn
0x180008cad  xor     esi, esi
0x180008caf  mov     r9d, 419h
0x180008cb5  jmp     short loc_180008CCA
0x180008cb7  mov     edi, 0C0000017h
0x180008cbc  mov     r9d, 422h
0x180008cc2  jmp     short loc_180008CCF
0x180008cc4  mov     r9d, 42Bh
0x180008cca  mov     edi, 0C000003Ah
0x180008ccf  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008cd6  mov     ecx, edi
0x180008cd8  lea     rdx, aSresult; "sResult"
0x180008cdf  call    DebugTraceError
0x180008ce4  test    rsi, rsi
0x180008ce7  jz      short loc_180008CA0
0x180008ce9  mov     rcx, rsi
0x180008cec  call    MSCryptFree
0x180008cf1  jmp     short loc_180008CA0
```
