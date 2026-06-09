# ATL::CComObject<CDpUrlAccessor>::CreateInstance(ATL::CComObject<CDpUrlAccessor> * *)

- ea: `0x18000487c`
- end: `0x180004970`
- name: `?CreateInstance@?$CComObject@VCDpUrlAccessor@@@ATL@@SAJPEAPEAV12@@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004020`

## callees

- `0x1800011c4`
- `0x1800028fc`
- `0x180002e98`
- `0x18000487c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDpUrlAccessor>::CreateInstance(__int64 *a1)
{
  __int64 *v1; // rsi
  unsigned int v3; // edi
  void *v4; // rax
  __int64 v5; // rbx
  signed __int32 v6; // eax
  int v7; // ecx
  int v8; // eax
  signed __int32 v9; // eax
  __int64 v11; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0xE0u);
    if ( v4 )
      v5 = ATL::CComObject<CDpUrlAccessor>::CComObject<CDpUrlAccessor>((__int64)v4);
    else
      v5 = 0;
    v11 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v11;
  }
  if ( v5 )
  {
    do
      v6 = *(_DWORD *)(v5 + 8);
    while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6) );
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v5 + 16));
    if ( v7 >= 0 )
      *(_BYTE *)(v5 + 56) = 1;
    v8 = 0;
    if ( v7 < 0 )
      v8 = v7;
    v3 = 0;
    if ( v8 < 0 )
      v3 = v8;
    do
      v9 = *(_DWORD *)(v5 + 8);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v9 - 1, v9) );
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 152LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000487c  mov     [rsp+arg_18], rbx
0x180004881  mov     [rsp+arg_0], rcx
0x180004886  push    rsi
0x180004887  push    rdi
0x180004888  push    r14
0x18000488a  sub     rsp, 20h
0x18000488e  mov     rsi, rcx
0x180004891  test    rcx, rcx
0x180004894  jnz     short loc_1800048A0
0x180004896  mov     eax, 80004003h
0x18000489b  jmp     loc_180004962
0x1800048a0  mov     qword ptr [rcx], 0
0x1800048a7  mov     edi, 8007000Eh
0x1800048ac  mov     [rsp+38h+arg_8], edi
0x1800048b0  mov     [rsp+38h+arg_10], 0
0x1800048b9  mov     ecx, 0E0h; Size
0x1800048be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800048c3  test    rax, rax
0x1800048c6  jz      short loc_1800048D5
0x1800048c8  mov     rcx, rax
0x1800048cb  call    ??0?$CComObject@VCDpUrlAccessor@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CDpUrlAccessor>::CComObject<CDpUrlAccessor>(void *)
0x1800048d0  mov     rbx, rax
0x1800048d3  jmp     short loc_1800048D7
0x1800048d5  xor     ebx, ebx
0x1800048d7  mov     [rsp+38h+arg_10], rbx
0x1800048dc  jmp     short loc_1800048EC
0x1800048de  mov     rsi, [rsp+38h+arg_0]
0x1800048e3  mov     edi, [rsp+38h+arg_8]
0x1800048e7  mov     rbx, [rsp+38h+arg_10]
0x1800048ec  test    rbx, rbx
0x1800048ef  jz      short loc_18000495D
0x1800048f1  mov     r14d, 7FFFFFFFh
0x1800048f7  jmp     short loc_180004903
0x1800048f9  lea     ecx, [rax+1]
0x1800048fc  lock cmpxchg [rbx+8], ecx
0x180004901  jz      short loc_18000490B
0x180004903  mov     eax, [rbx+8]
0x180004906  cmp     eax, r14d
0x180004909  jnz     short loc_1800048F9
0x18000490b  lea     rcx, [rbx+10h]; this
0x18000490f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004914  mov     ecx, eax
0x180004916  test    eax, eax
0x180004918  js      short loc_18000491E
0x18000491a  mov     byte ptr [rbx+38h], 1
0x18000491e  xor     eax, eax
0x180004920  test    ecx, ecx
0x180004922  cmovs   eax, ecx
0x180004925  xor     edi, edi
0x180004927  test    eax, eax
0x180004929  cmovs   edi, eax
0x18000492c  jmp     short loc_180004938
0x18000492e  lea     ecx, [rax-1]
0x180004931  lock cmpxchg [rbx+8], ecx
0x180004936  jz      short loc_180004940
0x180004938  mov     eax, [rbx+8]
0x18000493b  cmp     eax, r14d
0x18000493e  jnz     short loc_18000492E
0x180004940  test    edi, edi
0x180004942  jz      short loc_18000495D
0x180004944  mov     rax, [rbx]
0x180004947  mov     edx, 1
0x18000494c  mov     rcx, rbx
0x18000494f  mov     rax, [rax+98h]
0x180004956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000495b  xor     ebx, ebx
0x18000495d  mov     [rsi], rbx
0x180004960  mov     eax, edi
0x180004962  mov     rbx, [rsp+38h+arg_18]
0x180004967  add     rsp, 20h
0x18000496b  pop     r14
0x18000496d  pop     rdi
0x18000496e  pop     rsi
0x18000496f  retn
```
