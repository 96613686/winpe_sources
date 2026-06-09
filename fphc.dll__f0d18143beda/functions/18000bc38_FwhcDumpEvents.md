# FwhcDumpEvents

- ea: `0x18000bc38`
- end: `0x18000bcbd`
- name: `FwhcDumpEvents`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008d7c`
- `0x18000be30`
- `0x18000d108`

## callees

- `0x18000bc38`
- `0x18000eed4`
- `0x18001055c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bc61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bc8a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bc61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bc8a`

## pseudocode

```c
void __fastcall FwhcDumpEvents(const WCHAR *a1, unsigned int a2, __int64 a3)
{
  __int64 i; // rbx
  LPCWSTR lpOutputString[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]

  *(_OWORD *)lpOutputString = 0;
  v7 = 0;
  if ( gEnableSpew )
  {
    OutputDebugStringW(a1);
    for ( i = 0; (unsigned int)i < a2; v7 = 0 )
    {
      WfpFwpmNetEventPrint(WfpSwprintf, lpOutputString, 0, *(_QWORD *)(a3 + 8 * i));
      OutputDebugStringW(lpOutputString[0]);
      WfpMemFree(lpOutputString);
      i = (unsigned int)(i + 1);
      *(_OWORD *)lpOutputString = 0;
    }
  }
}

```

## disassembly

```asm
0x18000bc38  mov     rax, rsp
0x18000bc3b  mov     [rax+8], rbx
0x18000bc3f  mov     [rax+10h], rsi
0x18000bc43  push    rdi
0x18000bc44  sub     rsp, 40h
0x18000bc48  cmp     cs:gEnableSpew, 0
0x18000bc4f  xorps   xmm0, xmm0
0x18000bc52  movups  xmmword ptr [rax-28h], xmm0
0x18000bc56  mov     rsi, r8
0x18000bc59  mov     edi, edx
0x18000bc5b  movups  xmmword ptr [rax-18h], xmm0
0x18000bc5f  jz      short loc_18000BCAD
0x18000bc61  call    cs:__imp_OutputDebugStringW
0x18000bc67  xor     ebx, ebx
0x18000bc69  test    edi, edi
0x18000bc6b  jz      short loc_18000BCAD
0x18000bc6d  mov     r9, [rsi+rbx*8]
0x18000bc71  lea     rdx, [rsp+48h+lpOutputString]
0x18000bc76  xor     r8d, r8d
0x18000bc79  lea     rcx, WfpSwprintf
0x18000bc80  call    WfpFwpmNetEventPrint
0x18000bc85  mov     rcx, [rsp+48h+lpOutputString]; lpOutputString
0x18000bc8a  call    cs:__imp_OutputDebugStringW
0x18000bc90  lea     rcx, [rsp+48h+lpOutputString]
0x18000bc95  call    WfpMemFree
0x18000bc9a  xorps   xmm0, xmm0
0x18000bc9d  inc     ebx
0x18000bc9f  movups  xmmword ptr [rsp+48h+lpOutputString], xmm0
0x18000bca4  movups  [rsp+48h+var_18], xmm0
0x18000bca9  cmp     ebx, edi
0x18000bcab  jb      short loc_18000BC6D
0x18000bcad  mov     rbx, [rsp+48h+arg_0]
0x18000bcb2  mov     rsi, [rsp+48h+arg_8]
0x18000bcb7  add     rsp, 40h
0x18000bcbb  pop     rdi
0x18000bcbc  retn
```
