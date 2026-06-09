# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x1800121bc`
- end: `0x180012329`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `365`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180056b00`

## callees

- `0x1800121bc`
- `0x180055822`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001225a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012279`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001229d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001225a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012279`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001229d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800122c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800122c2`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800122fd`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180012311`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800122fd`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180012311`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rsi
  _QWORD *v7; // rbx
  __int64 v8; // rbx
  void *v9; // rcx
  _OWORD Buf2[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-18h]

  if ( !a1 )
    return 2147942487LL;
  v3 = *((_QWORD *)a1 + 4);
  if ( v3 )
  {
    while ( *(_QWORD *)v3 )
    {
      v4 = *(_QWORD *)(v3 + 32);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *(_QWORD *)(v3 + 32) = 0;
      (*(void (__fastcall **)(_QWORD))(v3 + 64))(0);
      v5 = 56;
      if ( *(_DWORD *)a1 != 176 )
        v5 = 72;
      v3 += v5;
    }
  }
  memset(Buf2, 0, sizeof(Buf2));
  v11 = 0;
  if ( memcmp_0((char *)a1 + 56, Buf2, 0x28u) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  if ( memcmp_0((char *)a1 + 96, Buf2, 0x28u) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  if ( memcmp_0((char *)a1 + 136, Buf2, 0x28u) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  v6 = (_QWORD *)*((_QWORD *)a1 + 29);
  if ( v6 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v6)(v6[1]);
      v7 = (_QWORD *)v6[2];
      CoTaskMemFree(v6);
      v6 = v7;
    }
    while ( v7 );
  }
  if ( *((_QWORD *)a1 + 6) && *((_BYTE *)a1 + 192) )
  {
    if ( *((_QWORD *)a1 + 27) )
    {
      v8 = 0;
      do
      {
        v9 = *(void **)(*((_QWORD *)a1 + 27) + 8 * v8);
        if ( v9 )
          HeapDestroy(v9);
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 <= *((_DWORD *)a1 + 52) );
    }
    HeapDestroy(*((HANDLE *)a1 + 6));
  }
  return 0;
}

```

## disassembly

```asm
0x1800121bc  mov     [rsp+arg_0], rbx
0x1800121c1  mov     [rsp+arg_8], rsi
0x1800121c6  push    rdi
0x1800121c7  sub     rsp, 50h
0x1800121cb  mov     rdi, rcx
0x1800121ce  test    rcx, rcx
0x1800121d1  jnz     short loc_1800121DD
0x1800121d3  mov     eax, 80070057h
0x1800121d8  jmp     loc_180012319
0x1800121dd  mov     rbx, [rcx+20h]
0x1800121e1  test    rbx, rbx
0x1800121e4  jz      short loc_18001222A
0x1800121e6  jmp     short loc_180012224
0x1800121e8  mov     rcx, [rbx+20h]
0x1800121ec  test    rcx, rcx
0x1800121ef  jz      short loc_1800121FD
0x1800121f1  mov     rax, [rcx]
0x1800121f4  mov     rax, [rax+10h]
0x1800121f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121fd  mov     qword ptr [rbx+20h], 0
0x180012205  xor     ecx, ecx
0x180012207  mov     rax, [rbx+40h]
0x18001220b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012210  mov     eax, 38h ; '8'
0x180012215  lea     ecx, [rax+10h]
0x180012218  cmp     dword ptr [rdi], 0B0h
0x18001221e  cmovnz  eax, ecx
0x180012221  add     rbx, rax
0x180012224  cmp     qword ptr [rbx], 0
0x180012228  jnz     short loc_1800121E8
0x18001222a  xorps   xmm0, xmm0
0x18001222d  xor     eax, eax
0x18001222f  movups  [rsp+58h+Buf2], xmm0
0x180012234  movups  [rsp+58h+var_28], xmm0
0x180012239  mov     [rsp+58h+var_18], rax
0x18001223e  lea     esi, [rax+28h]
0x180012241  mov     r8d, esi; Size
0x180012244  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180012249  lea     rcx, [rdi+38h]; Buf1
0x18001224d  call    memcmp_0
0x180012252  test    eax, eax
0x180012254  jz      short loc_180012260
0x180012256  lea     rcx, [rdi+38h]; lpCriticalSection
0x18001225a  call    cs:__imp_DeleteCriticalSection
0x180012260  mov     r8, rsi; Size
0x180012263  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180012268  lea     rcx, [rdi+60h]; Buf1
0x18001226c  call    memcmp_0
0x180012271  test    eax, eax
0x180012273  jz      short loc_18001227F
0x180012275  lea     rcx, [rdi+60h]; lpCriticalSection
0x180012279  call    cs:__imp_DeleteCriticalSection
0x18001227f  lea     rbx, [rdi+88h]
0x180012286  mov     r8, rsi; Size
0x180012289  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18001228e  mov     rcx, rbx; Buf1
0x180012291  call    memcmp_0
0x180012296  test    eax, eax
0x180012298  jz      short loc_1800122A3
0x18001229a  mov     rcx, rbx; lpCriticalSection
0x18001229d  call    cs:__imp_DeleteCriticalSection
0x1800122a3  mov     rsi, [rdi+0E8h]
0x1800122aa  test    rsi, rsi
0x1800122ad  jz      short loc_1800122D1
0x1800122af  mov     rcx, [rsi+8]
0x1800122b3  mov     rax, [rsi]
0x1800122b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122bb  mov     rbx, [rsi+10h]
0x1800122bf  mov     rcx, rsi; pv
0x1800122c2  call    cs:__imp_CoTaskMemFree
0x1800122c8  nop
0x1800122c9  mov     rsi, rbx
0x1800122cc  test    rbx, rbx
0x1800122cf  jnz     short loc_1800122AF
0x1800122d1  cmp     qword ptr [rdi+30h], 0
0x1800122d6  jz      short loc_180012317
0x1800122d8  cmp     byte ptr [rdi+0C0h], 0
0x1800122df  jz      short loc_180012317
0x1800122e1  cmp     qword ptr [rdi+0D8h], 0
0x1800122e9  jz      short loc_18001230D
0x1800122eb  xor     ebx, ebx
0x1800122ed  mov     rax, [rdi+0D8h]
0x1800122f4  mov     rcx, [rax+rbx*8]; hHeap
0x1800122f8  test    rcx, rcx
0x1800122fb  jz      short loc_180012303
0x1800122fd  call    cs:__imp_HeapDestroy
0x180012303  inc     ebx
0x180012305  cmp     ebx, [rdi+0D0h]
0x18001230b  jbe     short loc_1800122ED
0x18001230d  mov     rcx, [rdi+30h]; hHeap
0x180012311  call    cs:__imp_HeapDestroy
0x180012317  xor     eax, eax
0x180012319  mov     rbx, [rsp+58h+arg_0]
0x18001231e  mov     rsi, [rsp+58h+arg_8]
0x180012323  add     rsp, 50h
0x180012327  pop     rdi
0x180012328  retn
```
