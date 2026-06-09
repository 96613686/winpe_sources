# ATL::CComObject<CEnhancedStorageAct>::CreateInstance(ATL::CComObject<CEnhancedStorageAct> * *)

- ea: `0x180004220`
- end: `0x1800042eb`
- name: `?CreateInstance@?$CComObject@VCEnhancedStorageAct@@@ATL@@SAJPEAPEAV12@@Z`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004380`
- `0x180005960`

## callees

- `0x180001264`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x180003d3c`
- `0x180004220`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageAct>::CreateInstance(volatile int **a1)
{
  unsigned int v3; // esi
  void *v4; // rax
  volatile int *v5; // rdi
  int v6; // eax
  int v7; // edx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  v4 = operator new(0x280u);
  if ( v4 )
    v5 = (volatile int *)ATL::CComObject<CEnhancedStorageAct>::CComObject<CEnhancedStorageAct>(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread(v5 + 2);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v5 + 4));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    ATL::SafeDecrementReferenceMultiThread(v5 + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v5 + 112LL))(v5, 1);
      v5 = 0;
    }
  }
  *a1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180004220  mov     [rsp+arg_18], rbx
0x180004225  mov     [rsp+arg_0], rcx
0x18000422a  push    rsi
0x18000422b  push    rdi
0x18000422c  push    r14
0x18000422e  sub     rsp, 20h
0x180004232  mov     r14, rcx
0x180004235  test    rcx, rcx
0x180004238  jnz     short loc_180004244
0x18000423a  mov     eax, 80004003h
0x18000423f  jmp     loc_1800042DD
0x180004244  mov     qword ptr [rcx], 0
0x18000424b  mov     esi, 8007000Eh
0x180004250  mov     [rsp+38h+arg_8], esi
0x180004254  mov     [rsp+38h+arg_10], 0
0x18000425d  mov     ecx, 280h; Size
0x180004262  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004267  test    rax, rax
0x18000426a  jz      short loc_180004279
0x18000426c  mov     rcx, rax
0x18000426f  call    ??0?$CComObject@VCEnhancedStorageAct@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CEnhancedStorageAct>::CComObject<CEnhancedStorageAct>(void *)
0x180004274  mov     rdi, rax
0x180004277  jmp     short loc_18000427B
0x180004279  xor     edi, edi
0x18000427b  mov     [rsp+38h+arg_10], rdi
0x180004280  jmp     short loc_180004290
0x180004282  mov     r14, [rsp+38h+arg_0]
0x180004287  mov     esi, [rsp+38h+arg_8]
0x18000428b  mov     rdi, [rsp+38h+arg_10]
0x180004290  test    rdi, rdi
0x180004293  jz      short loc_1800042D8
0x180004295  lea     rcx, [rdi+8]; volatile int *
0x180004299  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000429e  lea     rcx, [rdi+10h]; this
0x1800042a2  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800042a7  xor     edx, edx
0x1800042a9  test    eax, eax
0x1800042ab  cmovs   edx, eax
0x1800042ae  xor     esi, esi
0x1800042b0  test    edx, edx
0x1800042b2  cmovs   esi, edx
0x1800042b5  lea     rcx, [rdi+8]; volatile int *
0x1800042b9  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800042be  test    esi, esi
0x1800042c0  jz      short loc_1800042D8
0x1800042c2  mov     rax, [rdi]
0x1800042c5  mov     edx, 1
0x1800042ca  mov     rcx, rdi
0x1800042cd  mov     rax, [rax+70h]
0x1800042d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d6  xor     edi, edi
0x1800042d8  mov     [r14], rdi
0x1800042db  mov     eax, esi
0x1800042dd  mov     rbx, [rsp+38h+arg_18]
0x1800042e2  add     rsp, 20h
0x1800042e6  pop     r14
0x1800042e8  pop     rdi
0x1800042e9  pop     rsi
0x1800042ea  retn
```
