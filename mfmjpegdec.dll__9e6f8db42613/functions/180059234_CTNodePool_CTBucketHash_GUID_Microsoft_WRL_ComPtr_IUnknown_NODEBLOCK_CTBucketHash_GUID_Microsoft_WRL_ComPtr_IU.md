# CTNodePool<CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODEBLOCK,CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODE,8>::Cleanup(void)

- ea: `0x180059234`
- end: `0x1800592ce`
- name: `?Cleanup@?$CTNodePool@UNODEBLOCK@?$CTBucketHash@U_GUID@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@@VNODE@2@$07@@QEAAXXZ`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180058ea0`
- `0x180058fc0`

## callees

- `0x18005915c`
- `0x180059234`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005928d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005928d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059242`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059242`

## pseudocode

```c
int __fastcall CTNodePool<CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODEBLOCK,CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODE,8>::Cleanup(
        __int64 a1)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v3; // rcx
  void *v4; // rbp
  _QWORD *v5; // rsi
  unsigned int j; // edi
  __int64 i; // rdi

  ProcessHeap = GetProcessHeap();
  v3 = *(_QWORD **)(a1 + 8);
  v4 = ProcessHeap;
  if ( v3 )
  {
    do
    {
      v5 = (_QWORD *)*v3;
      if ( v3 == (_QWORD *)(a1 + 24) )
      {
        for ( i = 0; i != 8; ++i )
          LODWORD(ProcessHeap) = CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODE::`scalar deleting destructor'(*(_QWORD *)(a1 + 8) + 8LL + 32 * i);
      }
      else
      {
        for ( j = 0; j < *(_DWORD *)(a1 + 16); ++j )
          CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODE::`scalar deleting destructor'(*(_QWORD *)(a1 + 8)
                                                                                                 + 8LL + 32LL * j);
        LODWORD(ProcessHeap) = HeapFree(v4, 0, *(LPVOID *)(a1 + 8));
      }
      *(_QWORD *)(a1 + 8) = v5;
      v3 = v5;
    }
    while ( v5 );
  }
  return (int)ProcessHeap;
}

```

## disassembly

```asm
0x180059234  push    rbx
0x180059236  push    rbp
0x180059237  push    rsi
0x180059238  push    rdi
0x180059239  push    r14
0x18005923b  sub     rsp, 20h
0x18005923f  mov     rbx, rcx
0x180059242  call    cs:__imp_GetProcessHeap
0x180059248  mov     rcx, [rbx+8]
0x18005924c  mov     rbp, rax
0x18005924f  test    rcx, rcx
0x180059252  jz      short loc_1800592C3
0x180059254  lea     r14, [rbx+18h]
0x180059258  mov     rsi, [rcx]
0x18005925b  cmp     rcx, r14
0x18005925e  jz      short loc_180059295
0x180059260  xor     edi, edi
0x180059262  cmp     [rbx+10h], edi
0x180059265  jbe     short loc_180059284
0x180059267  mov     rax, [rbx+8]
0x18005926b  add     rax, 8
0x18005926f  mov     ecx, edi
0x180059271  shl     rcx, 5
0x180059275  add     rcx, rax
0x180059278  call    ??_GNODE@?$CTBucketHash@U_GUID@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@@QEAAPEAXI@Z; CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODE::`scalar deleting destructor'(uint)
0x18005927d  inc     edi
0x18005927f  cmp     edi, [rbx+10h]
0x180059282  jb      short loc_180059267
0x180059284  mov     r8, [rbx+8]; lpMem
0x180059288  xor     edx, edx; dwFlags
0x18005928a  mov     rcx, rbp; hHeap
0x18005928d  call    cs:__imp_HeapFree
0x180059293  jmp     short loc_1800592B7
0x180059295  xor     edi, edi
0x180059297  mov     rax, [rbx+8]
0x18005929b  mov     rcx, rdi
0x18005929e  shl     rcx, 5
0x1800592a2  add     rax, 8
0x1800592a6  add     rcx, rax
0x1800592a9  call    ??_GNODE@?$CTBucketHash@U_GUID@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@@QEAAPEAXI@Z; CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::NODE::`scalar deleting destructor'(uint)
0x1800592ae  inc     rdi
0x1800592b1  cmp     rdi, 8
0x1800592b5  jnz     short loc_180059297
0x1800592b7  mov     [rbx+8], rsi
0x1800592bb  mov     rcx, rsi
0x1800592be  test    rsi, rsi
0x1800592c1  jnz     short loc_180059258
0x1800592c3  add     rsp, 20h
0x1800592c7  pop     r14
0x1800592c9  pop     rdi
0x1800592ca  pop     rsi
0x1800592cb  pop     rbp
0x1800592cc  pop     rbx
0x1800592cd  retn
```
