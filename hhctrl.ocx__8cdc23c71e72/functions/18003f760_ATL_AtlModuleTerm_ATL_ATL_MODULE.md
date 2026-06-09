# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x18003f760`
- end: `0x18003f8cb`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180041920`

## callees

- `0x18000171c`
- `0x18003f760`
- `0x180075c36`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x18003f89f`
- `KERNEL32!HeapDestroy` at `0x18003f8b3`
- `KERNEL32!HeapDestroy` at `0x18003f89f`
- `KERNEL32!HeapDestroy` at `0x18003f8b3`
- `KERNEL32!DeleteCriticalSection` at `0x18003f7fe`
- `KERNEL32!DeleteCriticalSection` at `0x18003f81d`
- `KERNEL32!DeleteCriticalSection` at `0x18003f841`
- `KERNEL32!DeleteCriticalSection` at `0x18003f7fe`
- `KERNEL32!DeleteCriticalSection` at `0x18003f81d`
- `KERNEL32!DeleteCriticalSection` at `0x18003f841`

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
      operator delete(v7);
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
0x18003f760  mov     [rsp+arg_0], rbx
0x18003f765  mov     [rsp+arg_8], rsi
0x18003f76a  push    rdi
0x18003f76b  sub     rsp, 50h
0x18003f76f  mov     rdi, rcx
0x18003f772  test    rcx, rcx
0x18003f775  jnz     short loc_18003F781
0x18003f777  mov     eax, 80070057h
0x18003f77c  jmp     loc_18003F8BB
0x18003f781  mov     rbx, [rcx+20h]
0x18003f785  test    rbx, rbx
0x18003f788  jz      short loc_18003F7CE
0x18003f78a  jmp     short loc_18003F7C8
0x18003f78c  mov     rcx, [rbx+20h]
0x18003f790  test    rcx, rcx
0x18003f793  jz      short loc_18003F7A1
0x18003f795  mov     rax, [rcx]
0x18003f798  mov     rax, [rax+10h]
0x18003f79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7a1  mov     rax, [rbx+40h]
0x18003f7a5  xor     ecx, ecx
0x18003f7a7  mov     qword ptr [rbx+20h], 0
0x18003f7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7b4  cmp     dword ptr [rdi], 0B0h
0x18003f7ba  mov     eax, 38h ; '8'
0x18003f7bf  lea     ecx, [rax+10h]
0x18003f7c2  cmovnz  eax, ecx
0x18003f7c5  add     rbx, rax
0x18003f7c8  cmp     qword ptr [rbx], 0
0x18003f7cc  jnz     short loc_18003F78C
0x18003f7ce  xor     eax, eax
0x18003f7d0  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18003f7d5  xorps   xmm0, xmm0
0x18003f7d8  mov     [rsp+58h+var_18], rax
0x18003f7dd  lea     rcx, [rdi+38h]; Buf1
0x18003f7e1  movups  [rsp+58h+Buf2], xmm0
0x18003f7e6  lea     esi, [rax+28h]
0x18003f7e9  mov     r8d, esi; Size
0x18003f7ec  movups  [rsp+58h+var_28], xmm0
0x18003f7f1  call    memcmp_0
0x18003f7f6  test    eax, eax
0x18003f7f8  jz      short loc_18003F804
0x18003f7fa  lea     rcx, [rdi+38h]; lpCriticalSection
0x18003f7fe  call    cs:__imp_DeleteCriticalSection
0x18003f804  mov     r8, rsi; Size
0x18003f807  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18003f80c  lea     rcx, [rdi+60h]; Buf1
0x18003f810  call    memcmp_0
0x18003f815  test    eax, eax
0x18003f817  jz      short loc_18003F823
0x18003f819  lea     rcx, [rdi+60h]; lpCriticalSection
0x18003f81d  call    cs:__imp_DeleteCriticalSection
0x18003f823  lea     rbx, [rdi+88h]
0x18003f82a  mov     r8, rsi; Size
0x18003f82d  mov     rcx, rbx; Buf1
0x18003f830  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18003f835  call    memcmp_0
0x18003f83a  test    eax, eax
0x18003f83c  jz      short loc_18003F847
0x18003f83e  mov     rcx, rbx; lpCriticalSection
0x18003f841  call    cs:__imp_DeleteCriticalSection
0x18003f847  mov     rsi, [rdi+0E8h]
0x18003f84e  test    rsi, rsi
0x18003f851  jz      short loc_18003F873
0x18003f853  mov     rcx, [rsi+8]
0x18003f857  mov     rax, [rsi]
0x18003f85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f85f  mov     rbx, [rsi+10h]
0x18003f863  mov     rcx, rsi; Block
0x18003f866  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f86b  mov     rsi, rbx
0x18003f86e  test    rbx, rbx
0x18003f871  jnz     short loc_18003F853
0x18003f873  cmp     qword ptr [rdi+30h], 0
0x18003f878  jz      short loc_18003F8B9
0x18003f87a  cmp     byte ptr [rdi+0C0h], 0
0x18003f881  jz      short loc_18003F8B9
0x18003f883  cmp     qword ptr [rdi+0D8h], 0
0x18003f88b  jz      short loc_18003F8AF
0x18003f88d  xor     ebx, ebx
0x18003f88f  mov     rax, [rdi+0D8h]
0x18003f896  mov     rcx, [rax+rbx*8]; hHeap
0x18003f89a  test    rcx, rcx
0x18003f89d  jz      short loc_18003F8A5
0x18003f89f  call    cs:__imp_HeapDestroy
0x18003f8a5  inc     ebx
0x18003f8a7  cmp     ebx, [rdi+0D0h]
0x18003f8ad  jbe     short loc_18003F88F
0x18003f8af  mov     rcx, [rdi+30h]; hHeap
0x18003f8b3  call    cs:__imp_HeapDestroy
0x18003f8b9  xor     eax, eax
0x18003f8bb  mov     rbx, [rsp+58h+arg_0]
0x18003f8c0  mov     rsi, [rsp+58h+arg_8]
0x18003f8c5  add     rsp, 50h
0x18003f8c9  pop     rdi
0x18003f8ca  retn
```
