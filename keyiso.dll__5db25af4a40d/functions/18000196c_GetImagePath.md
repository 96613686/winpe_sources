# _GetImagePath

- ea: `0x18000196c`
- end: `0x180001a43`
- name: `_GetImagePath`
- size: `215`
- prototype: `__int64 __fastcall(const void **, WCHAR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001824`

## callees

- `0x18000196c`
- `0x180002d20`
- `0x180003cf0`
- `0x180006280`
- `0x180018928`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001988`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800019c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001988`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800019c9`

## string_xrefs

- `0x1800019de`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall GetImagePath(const void **a1, WCHAR **a2)
{
  UINT SystemDirectoryW; // eax
  UINT v5; // ebx
  WCHAR *v6; // rsi
  __int64 v7; // r9
  WCHAR *v8; // rax
  unsigned int v9; // edi
  UINT v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rdx

  *a2 = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v5 = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    v8 = (WCHAR *)MSCryptAlloc(*(unsigned __int16 *)a1 + 4LL + 2LL * SystemDirectoryW);
    v6 = v8;
    if ( !v8 )
    {
      v9 = -1073741801;
      v7 = 1058;
      goto LABEL_8;
    }
    v10 = GetSystemDirectoryW(v8, v5);
    if ( v10 )
    {
      v11 = v10;
      v9 = 0;
      v6[v10] = 92;
      memcpy_0(&v6[v10 + 1], a1[1], *(unsigned __int16 *)a1);
      v12 = v11 + ((unsigned __int64)*(unsigned __int16 *)a1 >> 1);
      *a2 = v6;
      v6[v12 + 1] = 0;
      return v9;
    }
    v7 = 1067;
  }
  else
  {
    v6 = 0;
    v7 = 1049;
  }
  v9 = -1073741766;
LABEL_8:
  DebugTraceError(v9, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v7);
  if ( v6 )
    MSCryptFree(v6);
  return v9;
}

```

## disassembly

```asm
0x18000196c  push    rbx
0x18000196e  push    rbp
0x18000196f  push    rsi
0x180001970  push    rdi
0x180001971  push    r14
0x180001973  sub     rsp, 20h
0x180001977  mov     r14, rdx
0x18000197a  mov     qword ptr [rdx], 0
0x180001981  mov     rbp, rcx
0x180001984  xor     edx, edx; uSize
0x180001986  xor     ecx, ecx; lpBuffer
0x180001988  call    cs:__imp_GetSystemDirectoryW
0x18000198e  mov     ebx, eax
0x180001990  test    eax, eax
0x180001992  jnz     short loc_18000199E
0x180001994  xor     esi, esi
0x180001996  mov     r9d, 419h
0x18000199c  jmp     short loc_1800019D9
0x18000199e  movzx   eax, word ptr [rbp+0]
0x1800019a2  add     rax, 4
0x1800019a6  lea     rcx, [rax+rbx*2]
0x1800019aa  call    MSCryptAlloc
0x1800019af  mov     rsi, rax
0x1800019b2  test    rax, rax
0x1800019b5  jnz     short loc_1800019C4
0x1800019b7  mov     edi, 0C0000017h
0x1800019bc  mov     r9d, 422h
0x1800019c2  jmp     short loc_1800019DE
0x1800019c4  mov     edx, ebx; uSize
0x1800019c6  mov     rcx, rsi; lpBuffer
0x1800019c9  call    cs:__imp_GetSystemDirectoryW
0x1800019cf  test    eax, eax
0x1800019d1  jnz     short loc_180001A02
0x1800019d3  mov     r9d, 42Bh
0x1800019d9  mov     edi, 0C000003Ah
0x1800019de  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800019e5  mov     ecx, edi
0x1800019e7  lea     rdx, aSresult; "sResult"
0x1800019ee  call    DebugTraceError
0x1800019f3  test    rsi, rsi
0x1800019f6  jz      short loc_180001A36
0x1800019f8  mov     rcx, rsi
0x1800019fb  call    MSCryptFree
0x180001a00  jmp     short loc_180001A36
0x180001a02  mov     ebx, eax
0x180001a04  xor     edi, edi
0x180001a06  mov     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180001a0c  lea     rcx, [rbx+1]
0x180001a10  movzx   r8d, word ptr [rbp+0]; Size
0x180001a15  lea     rcx, [rsi+rcx*2]; void *
0x180001a19  mov     rdx, [rbp+8]; Src
0x180001a1d  call    memcpy_0
0x180001a22  movzx   edx, word ptr [rbp+0]
0x180001a26  shr     rdx, 1
0x180001a29  add     rdx, rbx
0x180001a2c  mov     [r14], rsi
0x180001a2f  xor     ecx, ecx
0x180001a31  mov     [rsi+rdx*2+2], cx
0x180001a36  mov     eax, edi
0x180001a38  add     rsp, 20h
0x180001a3c  pop     r14
0x180001a3e  pop     rdi
0x180001a3f  pop     rsi
0x180001a40  pop     rbp
0x180001a41  pop     rbx
0x180001a42  retn
```
