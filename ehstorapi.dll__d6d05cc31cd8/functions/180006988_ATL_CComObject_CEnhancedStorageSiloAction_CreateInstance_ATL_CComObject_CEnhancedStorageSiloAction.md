# ATL::CComObject<CEnhancedStorageSiloAction>::CreateInstance(ATL::CComObject<CEnhancedStorageSiloAction> * *)

- ea: `0x180006988`
- end: `0x180006a5e`
- name: `?CreateInstance@?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@SAJPEAPEAV12@@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006af0`

## callees

- `0x180001264`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x180006308`
- `0x180006988`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSiloAction>::CreateInstance(__int64 *a1)
{
  unsigned int v3; // edi
  void *v4; // rax
  __int64 v5; // rbx
  int v6; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  v4 = operator new(0x68u);
  if ( v4 )
    v5 = ATL::CComObject<CEnhancedStorageSiloAction>::CComObject<CEnhancedStorageSiloAction>(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)(v5 + 8));
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v5 + 16));
    if ( v6 >= 0 )
    {
      *(_QWORD *)(v5 + 96) = 0;
      v6 = 0;
    }
    v3 = 0;
    if ( v6 < 0 )
      v3 = v6;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)(v5 + 8));
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 48LL))(v5, 1);
      v5 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *a1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180006988  mov     [rsp+arg_18], rbx
0x18000698d  mov     [rsp+arg_0], rcx
0x180006992  push    rsi
0x180006993  push    rdi
0x180006994  push    r14
0x180006996  sub     rsp, 20h
0x18000699a  mov     rsi, rcx
0x18000699d  test    rcx, rcx
0x1800069a0  jnz     short loc_1800069AC
0x1800069a2  mov     eax, 80004003h
0x1800069a7  jmp     loc_180006A50
0x1800069ac  mov     qword ptr [rcx], 0
0x1800069b3  mov     edi, 8007000Eh
0x1800069b8  mov     [rsp+38h+arg_8], edi
0x1800069bc  mov     [rsp+38h+arg_10], 0
0x1800069c5  mov     ecx, 68h ; 'h'; Size
0x1800069ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069cf  test    rax, rax
0x1800069d2  jz      short loc_1800069E1
0x1800069d4  mov     rcx, rax
0x1800069d7  call    ??0?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CEnhancedStorageSiloAction>::CComObject<CEnhancedStorageSiloAction>(void *)
0x1800069dc  mov     rbx, rax
0x1800069df  jmp     short loc_1800069E3
0x1800069e1  xor     ebx, ebx
0x1800069e3  mov     [rsp+38h+arg_10], rbx
0x1800069e8  jmp     short loc_1800069F8
0x1800069ea  mov     rsi, [rsp+38h+arg_0]
0x1800069ef  mov     edi, [rsp+38h+arg_8]
0x1800069f3  mov     rbx, [rsp+38h+arg_10]
0x1800069f8  test    rbx, rbx
0x1800069fb  jz      short loc_180006A4B
0x1800069fd  lea     rcx, [rbx+8]; volatile int *
0x180006a01  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180006a06  lea     rcx, [rbx+10h]; this
0x180006a0a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006a0f  test    eax, eax
0x180006a11  js      short loc_180006A1D
0x180006a13  mov     qword ptr [rbx+60h], 0
0x180006a1b  xor     eax, eax
0x180006a1d  xor     edi, edi
0x180006a1f  test    eax, eax
0x180006a21  cmovs   edi, eax
0x180006a24  lea     rcx, [rbx+8]; volatile int *
0x180006a28  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006a2d  test    edi, edi
0x180006a2f  jz      short loc_180006A49
0x180006a31  mov     rax, [rbx]
0x180006a34  mov     edx, 1
0x180006a39  mov     rcx, rbx
0x180006a3c  mov     rax, [rax+30h]
0x180006a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a45  xor     ebx, ebx
0x180006a47  jmp     short loc_180006A4B
0x180006a49  xor     edi, edi
0x180006a4b  mov     [rsi], rbx
0x180006a4e  mov     eax, edi
0x180006a50  mov     rbx, [rsp+38h+arg_18]
0x180006a55  add     rsp, 20h
0x180006a59  pop     r14
0x180006a5b  pop     rdi
0x180006a5c  pop     rsi
0x180006a5d  retn
```
