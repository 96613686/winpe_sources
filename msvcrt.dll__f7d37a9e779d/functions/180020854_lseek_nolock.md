# _lseek_nolock

- ea: `0x180020854`
- end: `0x1800208e5`
- name: `_lseek_nolock`
- size: `145`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001ee10`
- `0x180020684`
- `0x180020750`
- `0x180020ee8`
- `0x1800227c0`

## callees

- `0x180007ea8`
- `0x180007f00`
- `0x18001ffd0`
- `0x180020854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208a0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020893`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020893`

## pseudocode

```c
__int64 __fastcall lseek_nolock(int a1, LONG a2, DWORD a3)
{
  __int64 v3; // rbx
  void *osfhandle; // rax
  DWORD v8; // edi
  DWORD LastError; // eax

  v3 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *errno() = 9;
    return 0xFFFFFFFFLL;
  }
  v8 = SetFilePointer(osfhandle, a2, 0, a3);
  if ( v8 == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      dosmaperr(LastError);
      return 0xFFFFFFFFLL;
    }
  }
  *(_BYTE *)(_pioinfo[v3 >> 5] + 56 * (v3 & 0x1F) + 8) &= ~2u;
  return v8;
}

```

## disassembly

```asm
0x180020854  mov     [rsp+arg_0], rbx
0x180020859  mov     [rsp+arg_8], rsi
0x18002085e  push    rdi
0x18002085f  sub     rsp, 20h
0x180020863  movsxd  rbx, ecx
0x180020866  mov     edi, r8d
0x180020869  mov     ecx, ebx; FileHandle
0x18002086b  mov     esi, edx
0x18002086d  call    _get_osfhandle
0x180020872  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020876  jnz     short loc_180020888
0x180020878  call    _errno
0x18002087d  mov     dword ptr [rax], 9
0x180020883  or      eax, 0FFFFFFFFh
0x180020886  jmp     short loc_1800208D5
0x180020888  mov     r9d, edi; dwMoveMethod
0x18002088b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002088e  mov     edx, esi; lDistanceToMove
0x180020890  mov     rcx, rax; hFile
0x180020893  call    cs:__imp_SetFilePointer
0x180020899  mov     edi, eax
0x18002089b  cmp     eax, 0FFFFFFFFh
0x18002089e  jnz     short loc_1800208B3
0x1800208a0  call    cs:__imp_GetLastError
0x1800208a6  test    eax, eax
0x1800208a8  jz      short loc_1800208B3
0x1800208aa  mov     ecx, eax
0x1800208ac  call    _dosmaperr
0x1800208b1  jmp     short loc_180020883
0x1800208b3  mov     eax, ebx
0x1800208b5  lea     r8, __pioinfo
0x1800208bc  and     eax, 1Fh
0x1800208bf  mov     rdx, rbx
0x1800208c2  imul    rcx, rax, 38h ; '8'
0x1800208c6  sar     rdx, 5
0x1800208ca  mov     rax, [r8+rdx*8]
0x1800208ce  and     byte ptr [rax+rcx+8], 0FDh
0x1800208d3  mov     eax, edi
0x1800208d5  mov     rbx, [rsp+28h+arg_0]
0x1800208da  mov     rsi, [rsp+28h+arg_8]
0x1800208df  add     rsp, 20h
0x1800208e3  pop     rdi
0x1800208e4  retn
```
