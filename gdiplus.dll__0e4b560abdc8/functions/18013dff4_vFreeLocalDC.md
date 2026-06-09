# vFreeLocalDC

- ea: `0x18013dff4`
- end: `0x18013e13d`
- name: `vFreeLocalDC`
- size: `329`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ddd98`
- `0x1800e74f0`

## callees

- `0x18013dff4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e037`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e084`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e0e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e037`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e084`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e0e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013e131`
- `GDI32!DeleteDC` at `0x18013e00a`
- `GDI32!DeleteDC` at `0x18013e00a`
- `GDI32!DeleteObject` at `0x18013e01f`
- `GDI32!DeleteObject` at `0x18013e067`
- `GDI32!DeleteObject` at `0x18013e0bb`
- `GDI32!DeleteObject` at `0x18013e01f`
- `GDI32!DeleteObject` at `0x18013e067`
- `GDI32!DeleteObject` at `0x18013e0bb`

## pseudocode

```c
HLOCAL __fastcall vFreeLocalDC(__int64 a1)
{
  HDC v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 i; // rbx
  void *v6; // rcx
  unsigned int j; // ebx
  void *v8; // rcx
  _QWORD *k; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx

  v2 = *(HDC *)(a1 + 40);
  if ( v2 )
    DeleteDC(v2);
  v3 = *(void **)(a1 + 56);
  if ( v3 )
    DeleteObject(v3);
  v4 = *(void **)(a1 + 400);
  if ( v4 )
    LocalFree(v4);
  if ( *(_QWORD *)(a1 + 552) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 520); i = (unsigned int)(i + 1) )
    {
      v6 = *(void **)(*(_QWORD *)(a1 + 552) + 8 * i);
      if ( v6 )
        DeleteObject(v6);
    }
    LocalFree(*(HLOCAL *)(a1 + 552));
  }
  if ( !*(_QWORD *)(a1 + 416) )
    goto LABEL_21;
  for ( j = 0; j < *(_DWORD *)(a1 + 408); ++j )
  {
    v8 = *(void **)(32LL * j + *(_QWORD *)(a1 + 416) + 8);
    if ( v8 )
      DeleteObject(v8);
  }
  for ( k = *(_QWORD **)(a1 + 416); ; *(_QWORD *)(a1 + 560) = k[2] )
  {
    LocalFree(k);
LABEL_21:
    k = *(_QWORD **)(a1 + 560);
    if ( !k )
      break;
  }
  v10 = *(_QWORD **)(a1 + 464);
  if ( v10 )
  {
    do
    {
      v11 = (_QWORD *)v10[58];
      LocalFree(v10);
      v10 = v11;
    }
    while ( v11 );
  }
  return LocalFree((HLOCAL)a1);
}

```

## disassembly

```asm
0x18013dff4  mov     [rsp+arg_0], rbx
0x18013dff9  push    rdi
0x18013dffa  sub     rsp, 20h
0x18013dffe  mov     rdi, rcx
0x18013e001  mov     rcx, [rcx+28h]; hdc
0x18013e005  test    rcx, rcx
0x18013e008  jz      short loc_18013E016
0x18013e00a  call    cs:__imp_DeleteDC
0x18013e011  nop     dword ptr [rax+rax+00h]
0x18013e016  mov     rcx, [rdi+38h]; ho
0x18013e01a  test    rcx, rcx
0x18013e01d  jz      short loc_18013E02B
0x18013e01f  call    cs:__imp_DeleteObject
0x18013e026  nop     dword ptr [rax+rax+00h]
0x18013e02b  mov     rcx, [rdi+190h]; hMem
0x18013e032  test    rcx, rcx
0x18013e035  jz      short loc_18013E043
0x18013e037  call    cs:__imp_LocalFree
0x18013e03e  nop     dword ptr [rax+rax+00h]
0x18013e043  cmp     qword ptr [rdi+228h], 0
0x18013e04b  jz      short loc_18013E090
0x18013e04d  xor     ebx, ebx
0x18013e04f  cmp     [rdi+208h], ebx
0x18013e055  jbe     short loc_18013E07D
0x18013e057  mov     rax, [rdi+228h]
0x18013e05e  mov     rcx, [rax+rbx*8]; ho
0x18013e062  test    rcx, rcx
0x18013e065  jz      short loc_18013E073
0x18013e067  call    cs:__imp_DeleteObject
0x18013e06e  nop     dword ptr [rax+rax+00h]
0x18013e073  inc     ebx
0x18013e075  cmp     ebx, [rdi+208h]
0x18013e07b  jb      short loc_18013E057
0x18013e07d  mov     rcx, [rdi+228h]; hMem
0x18013e084  call    cs:__imp_LocalFree
0x18013e08b  nop     dword ptr [rax+rax+00h]
0x18013e090  cmp     qword ptr [rdi+1A0h], 0
0x18013e098  jz      short loc_18013E0F1
0x18013e09a  xor     ebx, ebx
0x18013e09c  cmp     [rdi+198h], ebx
0x18013e0a2  jbe     short loc_18013E0D1
0x18013e0a4  mov     rax, [rdi+1A0h]
0x18013e0ab  mov     ecx, ebx
0x18013e0ad  shl     rcx, 5
0x18013e0b1  mov     rcx, [rcx+rax+8]; ho
0x18013e0b6  test    rcx, rcx
0x18013e0b9  jz      short loc_18013E0C7
0x18013e0bb  call    cs:__imp_DeleteObject
0x18013e0c2  nop     dword ptr [rax+rax+00h]
0x18013e0c7  inc     ebx
0x18013e0c9  cmp     ebx, [rdi+198h]
0x18013e0cf  jb      short loc_18013E0A4
0x18013e0d1  mov     rcx, [rdi+1A0h]
0x18013e0d8  jmp     short loc_18013E0E5
0x18013e0da  mov     rax, [rcx+10h]
0x18013e0de  mov     [rdi+230h], rax
0x18013e0e5  call    cs:__imp_LocalFree
0x18013e0ec  nop     dword ptr [rax+rax+00h]
0x18013e0f1  mov     rcx, [rdi+230h]; hMem
0x18013e0f8  test    rcx, rcx
0x18013e0fb  jnz     short loc_18013E0DA
0x18013e0fd  mov     rcx, [rdi+1D0h]; hMem
0x18013e104  test    rcx, rcx
0x18013e107  jz      short loc_18013E124
0x18013e109  mov     rbx, [rcx+1D0h]
0x18013e110  call    cs:__imp_LocalFree
0x18013e117  nop     dword ptr [rax+rax+00h]
0x18013e11c  mov     rcx, rbx
0x18013e11f  test    rbx, rbx
0x18013e122  jnz     short loc_18013E109
0x18013e124  mov     rcx, rdi
0x18013e127  mov     rbx, [rsp+28h+arg_0]
0x18013e12c  add     rsp, 20h
0x18013e130  pop     rdi
0x18013e131  jmp     cs:__imp_LocalFree
```
