# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x180015a78`
- end: `0x180015be4`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `364`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b4d0`

## callees

- `0x180015a78`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b59`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180015bb8`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180015bcc`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180015bb8`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180015bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015b7e`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
{
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  void (__fastcall *v5)(_QWORD); // rax
  __int64 v6; // rax
  _QWORD *v7; // rsi
  _QWORD *v8; // rbx
  __int64 v9; // rbx
  void *v10; // rcx
  _OWORD Buf2[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]

  if ( !a1 )
    return 2147942487LL;
  v3 = (_QWORD *)*((_QWORD *)a1 + 4);
  if ( v3 )
  {
    while ( *v3 )
    {
      v4 = v3[4];
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      v5 = (void (__fastcall *)(_QWORD))v3[8];
      v3[4] = 0;
      v5(0);
      v6 = 56;
      if ( *(_DWORD *)a1 != 176 )
        v6 = 72;
      v3 = (_QWORD *)((char *)v3 + v6);
    }
  }
  v12 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  if ( memcmp_0((char *)a1 + 56, Buf2, 0x28u) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  if ( memcmp_0((char *)a1 + 96, Buf2, 0x28u) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  if ( memcmp_0((char *)a1 + 136, Buf2, 0x28u) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  v7 = (_QWORD *)*((_QWORD *)a1 + 29);
  if ( v7 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v7)(v7[1]);
      v8 = (_QWORD *)v7[2];
      CoTaskMemFree(v7);
      v7 = v8;
    }
    while ( v8 );
  }
  if ( *((_QWORD *)a1 + 6) && *((_BYTE *)a1 + 192) )
  {
    if ( *((_QWORD *)a1 + 27) )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(*((_QWORD *)a1 + 27) + 8 * v9);
        if ( v10 )
          HeapDestroy(v10);
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= *((_DWORD *)a1 + 52) );
    }
    HeapDestroy(*((HANDLE *)a1 + 6));
  }
  return 0;
}

```

## disassembly

```asm
0x180015a78  mov     [rsp+arg_0], rbx
0x180015a7d  mov     [rsp+arg_8], rsi
0x180015a82  push    rdi
0x180015a83  sub     rsp, 50h
0x180015a87  mov     rdi, rcx
0x180015a8a  test    rcx, rcx
0x180015a8d  jnz     short loc_180015A99
0x180015a8f  mov     eax, 80070057h
0x180015a94  jmp     loc_180015BD4
0x180015a99  mov     rbx, [rcx+20h]
0x180015a9d  test    rbx, rbx
0x180015aa0  jz      short loc_180015AE6
0x180015aa2  jmp     short loc_180015AE0
0x180015aa4  mov     rcx, [rbx+20h]
0x180015aa8  test    rcx, rcx
0x180015aab  jz      short loc_180015AB9
0x180015aad  mov     rax, [rcx]
0x180015ab0  mov     rax, [rax+10h]
0x180015ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ab9  mov     rax, [rbx+40h]
0x180015abd  xor     ecx, ecx
0x180015abf  mov     qword ptr [rbx+20h], 0
0x180015ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015acc  cmp     dword ptr [rdi], 0B0h
0x180015ad2  mov     eax, 38h ; '8'
0x180015ad7  lea     ecx, [rax+10h]
0x180015ada  cmovnz  eax, ecx
0x180015add  add     rbx, rax
0x180015ae0  cmp     qword ptr [rbx], 0
0x180015ae4  jnz     short loc_180015AA4
0x180015ae6  xor     eax, eax
0x180015ae8  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180015aed  xorps   xmm0, xmm0
0x180015af0  mov     [rsp+58h+var_18], rax
0x180015af5  lea     rcx, [rdi+38h]; Buf1
0x180015af9  movups  [rsp+58h+Buf2], xmm0
0x180015afe  lea     esi, [rax+28h]
0x180015b01  mov     r8d, esi; Size
0x180015b04  movups  [rsp+58h+var_28], xmm0
0x180015b09  call    memcmp_0
0x180015b0e  test    eax, eax
0x180015b10  jz      short loc_180015B1C
0x180015b12  lea     rcx, [rdi+38h]; lpCriticalSection
0x180015b16  call    cs:__imp_DeleteCriticalSection
0x180015b1c  mov     r8, rsi; Size
0x180015b1f  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180015b24  lea     rcx, [rdi+60h]; Buf1
0x180015b28  call    memcmp_0
0x180015b2d  test    eax, eax
0x180015b2f  jz      short loc_180015B3B
0x180015b31  lea     rcx, [rdi+60h]; lpCriticalSection
0x180015b35  call    cs:__imp_DeleteCriticalSection
0x180015b3b  lea     rbx, [rdi+88h]
0x180015b42  mov     r8, rsi; Size
0x180015b45  mov     rcx, rbx; Buf1
0x180015b48  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180015b4d  call    memcmp_0
0x180015b52  test    eax, eax
0x180015b54  jz      short loc_180015B5F
0x180015b56  mov     rcx, rbx; lpCriticalSection
0x180015b59  call    cs:__imp_DeleteCriticalSection
0x180015b5f  mov     rsi, [rdi+0E8h]
0x180015b66  test    rsi, rsi
0x180015b69  jz      short loc_180015B8C
0x180015b6b  mov     rcx, [rsi+8]
0x180015b6f  mov     rax, [rsi]
0x180015b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b77  mov     rbx, [rsi+10h]
0x180015b7b  mov     rcx, rsi; pv
0x180015b7e  call    cs:__imp_CoTaskMemFree
0x180015b84  mov     rsi, rbx
0x180015b87  test    rbx, rbx
0x180015b8a  jnz     short loc_180015B6B
0x180015b8c  cmp     qword ptr [rdi+30h], 0
0x180015b91  jz      short loc_180015BD2
0x180015b93  cmp     byte ptr [rdi+0C0h], 0
0x180015b9a  jz      short loc_180015BD2
0x180015b9c  cmp     qword ptr [rdi+0D8h], 0
0x180015ba4  jz      short loc_180015BC8
0x180015ba6  xor     ebx, ebx
0x180015ba8  mov     rax, [rdi+0D8h]
0x180015baf  mov     rcx, [rax+rbx*8]; hHeap
0x180015bb3  test    rcx, rcx
0x180015bb6  jz      short loc_180015BBE
0x180015bb8  call    cs:__imp_HeapDestroy
0x180015bbe  inc     ebx
0x180015bc0  cmp     ebx, [rdi+0D0h]
0x180015bc6  jbe     short loc_180015BA8
0x180015bc8  mov     rcx, [rdi+30h]; hHeap
0x180015bcc  call    cs:__imp_HeapDestroy
0x180015bd2  xor     eax, eax
0x180015bd4  mov     rbx, [rsp+58h+arg_0]
0x180015bd9  mov     rsi, [rsp+58h+arg_8]
0x180015bde  add     rsp, 50h
0x180015be2  pop     rdi
0x180015be3  retn
```
