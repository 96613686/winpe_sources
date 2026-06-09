# EventObjectCollection::RemoveItemFromMap(ushort const *)

- ea: `0x180018000`
- end: `0x18001818a`
- name: `?RemoveItemFromMap@EventObjectCollection@@AEAAJPEBG@Z`
- size: `394`
- prototype: `int(EventObjectCollection *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180017f90`
- `0x180028440`
- `0x180030400`

## callees

- `0x180003d54`
- `0x18000c910`
- `0x180018000`
- `0x180018190`
- `0x180018258`
- `0x1800189cc`
- `0x18003ecb0`
- `0x1800434ba`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x180018041`
- `msvcrt!malloc` at `0x180018041`
- `msvcrt!free` at `0x18001816b`
- `msvcrt!free` at `0x18001816b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018153`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001813d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001813d`

## string_xrefs

- `0x18001810f`: `com\complus\src\events\tier1\enum.cpp`

## pseudocode

```c
__int64 __fastcall EventObjectCollection::RemoveItemFromMap(EventObjectCollection *this, const unsigned __int16 *a2)
{
  int v4; // esi
  size_t v5; // r14
  void *v6; // rax
  void *v7; // rdi
  void *v9; // r14
  __int64 v10; // rsi
  unsigned int v11; // [rsp+20h] [rbp-48h]
  __int64 v12; // [rsp+28h] [rbp-40h] BYREF
  void *v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+38h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-28h]
  void *v16; // [rsp+80h] [rbp+18h] BYREF
  __int64 v17; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  v4 = 1;
  v5 = 2LL * ((unsigned int)safe_lstrlenW(a2) + 1);
  v6 = malloc(v5);
  v7 = v6;
  v16 = v6;
  if ( !v6 )
    return 2147942414LL;
  memcpy_0(v6, a2, v5);
  v9 = 0;
  v13 = 0;
  CLockES::CLockES((CLockES *)&v14, (EventObjectCollection *)((char *)this + 104));
  v17 = 0;
  if ( (unsigned int)Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::find(
                       (char *)this + 56,
                       &v16,
                       &v17) )
  {
    v9 = *(void **)(*(_QWORD *)v17 + 32LL);
    v13 = v9;
    v4 = 0;
  }
  v11 = v4;
  if ( !v4 )
  {
    v10 = 0;
    v12 = 0;
    if ( (unsigned int)Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::find(
                         (char *)this + 56,
                         &v16,
                         &v12) )
      v10 = *(_QWORD *)(*(_QWORD *)v12 + 40LL);
    if ( !v10 )
      InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x25Eu, 0x80001203, 0x10u);
    Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::remove((char *)this + 56, &v16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    CoTaskMemFree(v9);
    --*((_DWORD *)this + 24);
  }
  if ( v14 )
    LeaveCriticalSection(lpCriticalSection);
  if ( v7 )
    free(v7);
  return v11;
}

```

## disassembly

```asm
0x180018000  mov     rax, rsp
0x180018003  mov     [rax+8], rsi
0x180018007  mov     [rax+10h], rdi
0x18001800b  push    r12
0x18001800d  push    r14
0x18001800f  push    r15
0x180018011  sub     rsp, 50h
0x180018015  mov     r12, rdx
0x180018018  mov     r15, rcx
0x18001801b  mov     dword ptr [rax-48h], 0
0x180018022  mov     qword ptr [rax+18h], 0
0x18001802a  mov     rcx, rdx; unsigned __int16 *
0x18001802d  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180018032  mov     esi, 1
0x180018037  lea     r14d, [rsi+rax]
0x18001803b  add     r14, r14
0x18001803e  mov     rcx, r14; Size
0x180018041  call    cs:__imp_malloc
0x180018047  mov     rdi, rax
0x18001804a  mov     [rsp+68h+arg_10], rax
0x180018052  test    rax, rax
0x180018055  jnz     short loc_180018061
0x180018057  mov     eax, 8007000Eh
0x18001805c  jmp     loc_180018175
0x180018061  mov     r8, r14; Size
0x180018064  mov     rdx, r12; Src
0x180018067  mov     rcx, rax; void *
0x18001806a  call    memcpy_0
0x18001806f  xor     r14d, r14d
0x180018072  mov     [rsp+68h+var_38], r14
0x180018077  lea     rdx, [r15+68h]; struct CSemExclusiveES *
0x18001807b  lea     rcx, [rsp+68h+var_30]; this
0x180018080  call    ??0CLockES@@QEAA@AEAVCSemExclusiveES@@@Z; CLockES::CLockES(CSemExclusiveES &)
0x180018085  lea     r12, [r15+38h]
0x180018089  mov     [rsp+68h+arg_18], r14
0x180018091  lea     r8, [rsp+68h+arg_18]
0x180018099  lea     rdx, [rsp+68h+arg_10]
0x1800180a1  mov     rcx, r12
0x1800180a4  call    ?find@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEBAHAEBQEAGPEAPEAPEAVAssoc@1@@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::find(ushort * const &,Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc * * *)
0x1800180a9  test    eax, eax
0x1800180ab  jz      short loc_1800180C3
0x1800180ad  mov     rax, [rsp+68h+arg_18]
0x1800180b5  mov     rcx, [rax]
0x1800180b8  mov     r14, [rcx+20h]
0x1800180bc  mov     [rsp+68h+var_38], r14
0x1800180c1  xor     esi, esi
0x1800180c3  mov     [rsp+68h+var_48], esi
0x1800180c7  mov     eax, [rsp+68h+var_48]
0x1800180cb  test    eax, eax
0x1800180cd  jnz     short loc_180018147
0x1800180cf  xor     esi, esi
0x1800180d1  mov     [rsp+68h+var_40], rsi
0x1800180d6  lea     r8, [rsp+68h+var_40]
0x1800180db  lea     rdx, [rsp+68h+arg_10]
0x1800180e3  mov     rcx, r12
0x1800180e6  call    ?find@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEBAHAEBQEAGPEAPEAPEAVAssoc@1@@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::find(ushort * const &,Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc * * *)
0x1800180eb  test    eax, eax
0x1800180ed  jz      short loc_1800180FB
0x1800180ef  mov     rax, [rsp+68h+var_40]
0x1800180f4  mov     rdx, [rax]
0x1800180f7  mov     rsi, [rdx+28h]
0x1800180fb  test    rsi, rsi
0x1800180fe  jnz     short loc_18001811B
0x180018100  mov     edx, 25Eh; unsigned int
0x180018105  lea     r9d, [rsi+10h]; unsigned __int16
0x180018109  mov     r8d, 80001203h; unsigned int
0x18001810f  lea     rcx, aComComplusSrcE_21; "com\\complus\\src\\events\\tier1\\enum."...
0x180018116  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001811b  lea     rdx, [rsp+68h+arg_10]
0x180018123  mov     rcx, r12
0x180018126  call    ?remove@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAAXAEBQEAG@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::remove(ushort * const &)
0x18001812b  mov     rax, [rsi]
0x18001812e  mov     rcx, rsi
0x180018131  mov     rax, [rax+10h]
0x180018135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001813a  mov     rcx, r14; pv
0x18001813d  call    cs:__imp_CoTaskMemFree
0x180018143  dec     dword ptr [r15+60h]
0x180018147  cmp     [rsp+68h+var_30], 0
0x18001814c  jz      short loc_180018159
0x18001814e  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180018153  call    cs:__imp_LeaveCriticalSection
0x180018159  jmp     short loc_180018163
0x18001815b  mov     rdi, [rsp+68h+arg_10]
0x180018163  test    rdi, rdi
0x180018166  jz      short loc_180018171
0x180018168  mov     rcx, rdi; Block
0x18001816b  call    cs:__imp_free
0x180018171  mov     eax, [rsp+68h+var_48]
0x180018175  mov     rsi, [rsp+68h+arg_0]
0x18001817a  mov     rdi, [rsp+68h+arg_8]
0x18001817f  add     rsp, 50h
0x180018183  pop     r15
0x180018185  pop     r14
0x180018187  pop     r12
0x180018189  retn
0x1800446ae  push    rbp
0x1800446b0  sub     rsp, 20h
0x1800446b4  mov     rbp, rdx
0x1800446b7  lea     rdx, [rbp+20h]; int *
0x1800446bb  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x1800446c0  nop
0x1800446c1  add     rsp, 20h
0x1800446c5  pop     rbp
0x1800446c6  retn
```
