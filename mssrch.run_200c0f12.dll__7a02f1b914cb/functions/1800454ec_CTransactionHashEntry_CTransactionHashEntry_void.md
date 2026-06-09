# CTransactionHashEntry::~CTransactionHashEntry(void)

- ea: `0x1800454ec`
- end: `0x180045678`
- name: `??1CTransactionHashEntry@@QEAA@XZ`
- size: `396`
- prototype: `void __fastcall(CTransactionHashEntry *__hidden this)`
- caller_count: `49`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000afec`
- `0x180022c40`
- `0x18002a7d0`
- `0x18002bff8`
- `0x18002e4b8`
- `0x180030ab0`
- `0x180031940`
- `0x1800434a0`
- `0x180043a14`
- `0x18004773c`
- `0x180048630`
- `0x18008fc70`
- `0x1800c8618`
- `0x1800c8d90`
- `0x1800dc730`
- `0x1800dd7f0`
- `0x1800eb1e0`
- `0x1800eb600`
- `0x1800ebb18`
- `0x1800ebfc8`
- `0x180116260`
- `0x18011f2c4`
- `0x180120a1c`
- `0x1801edf70`
- `0x1801ee140`
- `0x1801efd9c`
- `0x1801f2658`
- `0x1801f2bac`
- `0x1801f3bf0`
- `0x1801f3fc0`
- `0x1801f4710`
- `0x1802234cc`
- `0x180224964`
- `0x180224fff`
- `0x180225235`
- `0x18022540d`
- `0x180225573`
- `0x180225672`
- `0x18022649e`
- `0x180226768`
- `0x18022cf82`
- `0x18022f114`
- `0x18022f228`
- `0x18022f2c9`
- `0x18023257f`
- `0x18023bd6c`
- `0x18023dd21`
- `0x18023dd45`
- `0x18023df7a`

## callees

- `0x180012318`
- `0x1800454ec`
- `0x1800771ac`
- `0x1801249b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004550e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004560c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004563e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004565f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004550e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004560c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004563e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004565f`

## pseudocode

```c
void __fastcall CTransactionHashEntry::~CTransactionHashEntry(CTransactionHashEntry *this)
{
  char *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  unsigned __int64 v4; // rdx
  void *v5; // rcx
  unsigned int v6; // esi
  __int64 v7; // rbp
  __int64 v8; // rdi
  void *v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // rbp
  __int64 v12; // rdi
  void *v13; // rcx
  unsigned __int64 v14; // [rsp+40h] [rbp+8h] BYREF
  void *v15; // [rsp+48h] [rbp+10h] BYREF

  v2 = (char *)*((_QWORD *)this + 7);
  if ( v2 != (char *)this + 64 )
    CoTaskMemFree(v2);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = 0;
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 34);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  if ( *((_DWORD *)this + 64) )
  {
    v6 = 0;
    do
    {
      v7 = *((_QWORD *)this + 31);
      v8 = 2LL * v6;
      v9 = *(void **)(v7 + 16LL * v6 + 8);
      if ( v9 )
        CoTaskMemFree(v9);
      ++v6;
      *(_QWORD *)(v7 + 8 * v8 + 8) = 0;
      *(_DWORD *)(v7 + 8 * v8) = 0;
    }
    while ( v6 < *((_DWORD *)this + 64) );
    CoTaskMemFree(*((LPVOID *)this + 31));
    *((_QWORD *)this + 31) = 0;
    *((_DWORD *)this + 64) = 0;
  }
  if ( *((_DWORD *)this + 60) )
  {
    v10 = 0;
    do
    {
      v11 = *((_QWORD *)this + 29);
      v12 = 2LL * v10;
      v13 = *(void **)(v11 + 16LL * v10 + 8);
      if ( v13 )
        CoTaskMemFree(v13);
      ++v10;
      *(_QWORD *)(v11 + 8 * v12 + 8) = 0;
      *(_DWORD *)(v11 + 8 * v12) = 0;
    }
    while ( v10 < *((_DWORD *)this + 60) );
    CoTaskMemFree(*((LPVOID *)this + 29));
    *((_QWORD *)this + 29) = 0;
    *((_DWORD *)this + 60) = 0;
  }
  v4 = *((_QWORD *)this + 25);
  if ( v4 > 7 )
  {
    v5 = (void *)*((_QWORD *)this + 22);
    v14 = 2 * v4 + 2;
    v15 = v5;
    if ( v14 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v15, &v14);
      v5 = v15;
    }
    operator delete(v5);
  }
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 7;
  *((_WORD *)this + 88) = 0;
}

```

## disassembly

```asm
0x1800454ec  mov     [rsp+arg_10], rbx
0x1800454f1  mov     [rsp+arg_18], rbp
0x1800454f6  push    rsi
0x1800454f7  push    rdi
0x1800454f8  push    r14
0x1800454fa  sub     rsp, 20h
0x1800454fe  mov     rbx, rcx
0x180045501  mov     rcx, [rcx+38h]; pv
0x180045505  lea     rax, [rbx+40h]
0x180045509  cmp     rcx, rax
0x18004550c  jz      short loc_180045514
0x18004550e  call    cs:__imp_CoTaskMemFree
0x180045514  xor     r14d, r14d
0x180045517  mov     [rbx+38h], r14
0x18004551b  mov     [rbx+0E8h], r14
0x180045522  mov     [rbx+0F0h], r14d
0x180045529  mov     rcx, [rbx+110h]; this
0x180045530  test    rcx, rcx
0x180045533  jz      short loc_18004553A
0x180045535  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004553a  mov     eax, [rbx+100h]
0x180045540  test    eax, eax
0x180045542  jnz     loc_1800455D2
0x180045548  mov     eax, [rbx+0F0h]
0x18004554e  test    eax, eax
0x180045550  jnz     loc_180045625
0x180045556  mov     rdx, [rbx+0C8h]
0x18004555d  cmp     rdx, 7
0x180045561  jbe     short loc_18004558A
0x180045563  mov     rcx, [rbx+0B0h]; Block
0x18004556a  lea     rdx, ds:2[rdx*2]
0x180045572  mov     [rsp+38h+arg_0], rdx
0x180045577  mov     [rsp+38h+arg_8], rcx
0x18004557c  cmp     rdx, 1000h
0x180045583  jnb     short loc_1800455B7
0x180045585  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004558a  mov     rbp, [rsp+38h+arg_18]
0x18004558f  mov     [rbx+0C0h], r14
0x180045596  mov     qword ptr [rbx+0C8h], 7
0x1800455a1  mov     [rbx+0B0h], r14w
0x1800455a9  mov     rbx, [rsp+38h+arg_10]
0x1800455ae  add     rsp, 20h
0x1800455b2  pop     r14
0x1800455b4  pop     rdi
0x1800455b5  pop     rsi
0x1800455b6  retn
0x1800455b7  lea     rdx, [rsp+38h+arg_0]; unsigned __int64 *
0x1800455bc  lea     rcx, [rsp+38h+arg_8]; void **
0x1800455c1  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800455c6  mov     rdx, [rsp+38h+arg_0]
0x1800455cb  mov     rcx, [rsp+38h+arg_8]
0x1800455d0  jmp     short loc_180045585
0x1800455d2  mov     esi, r14d
0x1800455d5  mov     rbp, [rbx+0F8h]
0x1800455dc  mov     edi, esi
0x1800455de  add     rdi, rdi
0x1800455e1  mov     rcx, [rbp+rdi*8+8]; pv
0x1800455e6  test    rcx, rcx
0x1800455e9  jz      short loc_1800455F1
0x1800455eb  call    cs:__imp_CoTaskMemFree
0x1800455f1  inc     esi
0x1800455f3  mov     [rbp+rdi*8+8], r14
0x1800455f8  mov     [rbp+rdi*8+0], r14d
0x1800455fd  cmp     esi, [rbx+100h]
0x180045603  jb      short loc_1800455D5
0x180045605  mov     rcx, [rbx+0F8h]; pv
0x18004560c  call    cs:__imp_CoTaskMemFree
0x180045612  mov     [rbx+0F8h], r14
0x180045619  mov     [rbx+100h], r14d
0x180045620  jmp     loc_180045548
0x180045625  mov     esi, r14d
0x180045628  mov     rbp, [rbx+0E8h]
0x18004562f  mov     edi, esi
0x180045631  add     rdi, rdi
0x180045634  mov     rcx, [rbp+rdi*8+8]; pv
0x180045639  test    rcx, rcx
0x18004563c  jz      short loc_180045644
0x18004563e  call    cs:__imp_CoTaskMemFree
0x180045644  inc     esi
0x180045646  mov     [rbp+rdi*8+8], r14
0x18004564b  mov     [rbp+rdi*8+0], r14d
0x180045650  cmp     esi, [rbx+0F0h]
0x180045656  jb      short loc_180045628
0x180045658  mov     rcx, [rbx+0E8h]; pv
0x18004565f  call    cs:__imp_CoTaskMemFree
0x180045665  mov     [rbx+0E8h], r14
0x18004566c  mov     [rbx+0F0h], r14d
0x180045673  jmp     loc_180045556
```
