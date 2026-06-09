# _ILUnmarshal

- ea: `0x1800a86e8`
- end: `0x1800a87b1`
- name: `_ILUnmarshal`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8820`

## callees

- `0x18006fb80`
- `0x1800a86e8`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x1800a8782`
- `RPCRT4!RpcRaiseException` at `0x1800a87aa`
- `RPCRT4!RpcRaiseException` at `0x1800a8782`
- `RPCRT4!RpcRaiseException` at `0x1800a87aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800a875f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800a875f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a878c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a878c`

## pseudocode

```c
char *__fastcall ILUnmarshal(unsigned int *a1, unsigned __int64 a2, LPVOID *a3)
{
  SIZE_T v5; // rdi
  char *v6; // r14
  _WORD *v7; // rdx
  unsigned int v8; // ecx
  unsigned int v9; // r8d
  void *v10; // rax
  void *v11; // rbx

  if ( a2 < 4 )
    goto LABEL_15;
  v5 = *a1;
  if ( v5 > a2 - 4 )
    goto LABEL_15;
  v6 = (char *)(a1 + 1);
  if ( !*a1 )
  {
    CoTaskMemFree(*a3);
    v11 = 0;
    goto LABEL_14;
  }
  v7 = a1 + 1;
  v8 = 2;
  if ( *a1 < 2 )
    goto LABEL_15;
  do
  {
    if ( *v7 < 2u )
      break;
    v9 = (unsigned __int16)*v7;
    if ( v9 > *a1 - v8 )
      break;
    v8 += v9;
    v7 = (_WORD *)((char *)v7 + (unsigned __int16)*v7);
  }
  while ( v8 <= *a1 );
  if ( v8 > *a1 || *v7 )
LABEL_15:
    RpcRaiseException(1783);
  v10 = CoTaskMemRealloc(*a3, v5);
  v11 = v10;
  if ( !v10 )
    RpcRaiseException(-2147024882);
  memcpy_0(v10, v6, v5);
LABEL_14:
  *a3 = v11;
  return &v6[v5];
}

```

## disassembly

```asm
0x1800a86e8  push    rbx
0x1800a86ea  push    rsi
0x1800a86eb  push    rdi
0x1800a86ec  push    r14
0x1800a86ee  sub     rsp, 28h
0x1800a86f2  mov     rsi, r8
0x1800a86f5  mov     r9, rcx
0x1800a86f8  cmp     rdx, 4
0x1800a86fc  jb      loc_1800A87A5
0x1800a8702  mov     edi, [rcx]
0x1800a8704  lea     rax, [rdx-4]
0x1800a8708  cmp     rdi, rax
0x1800a870b  ja      loc_1800A87A5
0x1800a8711  cmp     dword ptr [rcx], 0
0x1800a8714  lea     r14, [rcx+4]
0x1800a8718  jz      short loc_1800A8789
0x1800a871a  mov     r10d, 2
0x1800a8720  mov     rdx, r14
0x1800a8723  mov     ecx, r10d
0x1800a8726  cmp     [r9], r10d
0x1800a8729  jb      short loc_1800A87A5
0x1800a872b  cmp     [rdx], r10w
0x1800a872f  jb      short loc_1800A874D
0x1800a8731  mov     eax, [r9]
0x1800a8734  movzx   r8d, word ptr [rdx]
0x1800a8738  sub     eax, ecx
0x1800a873a  cmp     r8d, eax
0x1800a873d  ja      short loc_1800A874D
0x1800a873f  movzx   eax, word ptr [rdx]
0x1800a8742  add     ecx, r8d
0x1800a8745  add     rdx, rax
0x1800a8748  cmp     ecx, [r9]
0x1800a874b  jbe     short loc_1800A872B
0x1800a874d  cmp     ecx, [r9]
0x1800a8750  ja      short loc_1800A87A5
0x1800a8752  xor     eax, eax
0x1800a8754  cmp     ax, [rdx]
0x1800a8757  jnz     short loc_1800A87A5
0x1800a8759  mov     rcx, [rsi]; pv
0x1800a875c  mov     rdx, rdi; cb
0x1800a875f  call    cs:__imp_CoTaskMemRealloc
0x1800a8765  mov     rbx, rax
0x1800a8768  test    rax, rax
0x1800a876b  jz      short loc_1800A877D
0x1800a876d  mov     r8, rdi; Size
0x1800a8770  mov     rdx, r14; Src
0x1800a8773  mov     rcx, rax; void *
0x1800a8776  call    memcpy_0
0x1800a877b  jmp     short loc_1800A8794
0x1800a877d  mov     ecx, 8007000Eh; exception
0x1800a8782  call    cs:__imp_RpcRaiseException
0x1800a8788  int     3; Trap to Debugger
0x1800a8789  mov     rcx, [r8]; pv
0x1800a878c  call    cs:__imp_CoTaskMemFree
0x1800a8792  xor     ebx, ebx
0x1800a8794  mov     [rsi], rbx
0x1800a8797  lea     rax, [r14+rdi]
0x1800a879b  add     rsp, 28h
0x1800a879f  pop     r14
0x1800a87a1  pop     rdi
0x1800a87a2  pop     rsi
0x1800a87a3  pop     rbx
0x1800a87a4  retn
0x1800a87a5  mov     ecx, 6F7h; exception
0x1800a87aa  call    cs:__imp_RpcRaiseException
```
