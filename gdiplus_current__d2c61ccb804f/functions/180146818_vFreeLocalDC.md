# vFreeLocalDC

- ea: `0x180146818`
- end: `0x180146961`
- name: `vFreeLocalDC`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ee0dc`
- `0x1800f8690`

## callees

- `0x180146818`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014685b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801468a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146934`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014685b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801468a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146934`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180146955`
- `GDI32!DeleteDC` at `0x18014682e`
- `GDI32!DeleteDC` at `0x18014682e`
- `GDI32!DeleteObject` at `0x180146843`
- `GDI32!DeleteObject` at `0x18014688b`
- `GDI32!DeleteObject` at `0x1801468df`
- `GDI32!DeleteObject` at `0x180146843`
- `GDI32!DeleteObject` at `0x18014688b`
- `GDI32!DeleteObject` at `0x1801468df`

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
0x180146818  mov     [rsp+arg_0], rbx
0x18014681d  push    rdi
0x18014681e  sub     rsp, 20h
0x180146822  mov     rdi, rcx
0x180146825  mov     rcx, [rcx+28h]; hdc
0x180146829  test    rcx, rcx
0x18014682c  jz      short loc_18014683A
0x18014682e  call    cs:__imp_DeleteDC
0x180146835  nop     dword ptr [rax+rax+00h]
0x18014683a  mov     rcx, [rdi+38h]; ho
0x18014683e  test    rcx, rcx
0x180146841  jz      short loc_18014684F
0x180146843  call    cs:__imp_DeleteObject
0x18014684a  nop     dword ptr [rax+rax+00h]
0x18014684f  mov     rcx, [rdi+190h]; hMem
0x180146856  test    rcx, rcx
0x180146859  jz      short loc_180146867
0x18014685b  call    cs:__imp_LocalFree
0x180146862  nop     dword ptr [rax+rax+00h]
0x180146867  cmp     qword ptr [rdi+228h], 0
0x18014686f  jz      short loc_1801468B4
0x180146871  xor     ebx, ebx
0x180146873  cmp     [rdi+208h], ebx
0x180146879  jbe     short loc_1801468A1
0x18014687b  mov     rax, [rdi+228h]
0x180146882  mov     rcx, [rax+rbx*8]; ho
0x180146886  test    rcx, rcx
0x180146889  jz      short loc_180146897
0x18014688b  call    cs:__imp_DeleteObject
0x180146892  nop     dword ptr [rax+rax+00h]
0x180146897  inc     ebx
0x180146899  cmp     ebx, [rdi+208h]
0x18014689f  jb      short loc_18014687B
0x1801468a1  mov     rcx, [rdi+228h]; hMem
0x1801468a8  call    cs:__imp_LocalFree
0x1801468af  nop     dword ptr [rax+rax+00h]
0x1801468b4  cmp     qword ptr [rdi+1A0h], 0
0x1801468bc  jz      short loc_180146915
0x1801468be  xor     ebx, ebx
0x1801468c0  cmp     [rdi+198h], ebx
0x1801468c6  jbe     short loc_1801468F5
0x1801468c8  mov     rax, [rdi+1A0h]
0x1801468cf  mov     ecx, ebx
0x1801468d1  shl     rcx, 5
0x1801468d5  mov     rcx, [rcx+rax+8]; ho
0x1801468da  test    rcx, rcx
0x1801468dd  jz      short loc_1801468EB
0x1801468df  call    cs:__imp_DeleteObject
0x1801468e6  nop     dword ptr [rax+rax+00h]
0x1801468eb  inc     ebx
0x1801468ed  cmp     ebx, [rdi+198h]
0x1801468f3  jb      short loc_1801468C8
0x1801468f5  mov     rcx, [rdi+1A0h]
0x1801468fc  jmp     short loc_180146909
0x1801468fe  mov     rax, [rcx+10h]
0x180146902  mov     [rdi+230h], rax
0x180146909  call    cs:__imp_LocalFree
0x180146910  nop     dword ptr [rax+rax+00h]
0x180146915  mov     rcx, [rdi+230h]; hMem
0x18014691c  test    rcx, rcx
0x18014691f  jnz     short loc_1801468FE
0x180146921  mov     rcx, [rdi+1D0h]; hMem
0x180146928  test    rcx, rcx
0x18014692b  jz      short loc_180146948
0x18014692d  mov     rbx, [rcx+1D0h]
0x180146934  call    cs:__imp_LocalFree
0x18014693b  nop     dword ptr [rax+rax+00h]
0x180146940  mov     rcx, rbx
0x180146943  test    rbx, rbx
0x180146946  jnz     short loc_18014692D
0x180146948  mov     rcx, rdi
0x18014694b  mov     rbx, [rsp+28h+arg_0]
0x180146950  add     rsp, 20h
0x180146954  pop     rdi
0x180146955  jmp     cs:__imp_LocalFree
```
