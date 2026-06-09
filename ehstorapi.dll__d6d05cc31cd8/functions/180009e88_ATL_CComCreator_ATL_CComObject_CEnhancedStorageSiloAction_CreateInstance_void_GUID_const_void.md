# ATL::CComCreator<ATL::CComObject<CEnhancedStorageSiloAction>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009e88`
- end: `0x180009f7d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009b50`

## callees

- `0x180001264`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x180006308`
- `0x180009e88`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CEnhancedStorageSiloAction>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rbx
  int v9; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x68u);
  if ( v7 )
    v8 = ATL::CComObject<CEnhancedStorageSiloAction>::CComObject<CEnhancedStorageSiloAction>(v7);
  else
    v8 = 0;
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)(v8 + 8));
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 16));
    if ( v9 >= 0 )
    {
      *(_QWORD *)(v8 + 96) = 0;
      v9 = 0;
    }
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)(v8 + 8));
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009e88  mov     [rsp+arg_10], r8
0x180009e8d  mov     [rsp+arg_8], rdx
0x180009e92  mov     [rsp+arg_0], rcx
0x180009e97  push    rbx
0x180009e98  push    rsi
0x180009e99  push    rdi
0x180009e9a  push    r14
0x180009e9c  push    r15
0x180009e9e  sub     rsp, 20h
0x180009ea2  mov     rsi, r8
0x180009ea5  mov     r15, rdx
0x180009ea8  test    r8, r8
0x180009eab  jnz     short loc_180009EB7
0x180009ead  mov     eax, 80004003h
0x180009eb2  jmp     loc_180009F71
0x180009eb7  mov     qword ptr [r8], 0
0x180009ebe  mov     edi, 8007000Eh
0x180009ec3  mov     dword ptr [rsp+48h+arg_0], edi
0x180009ec7  mov     [rsp+48h+arg_18], 0
0x180009ed0  mov     ecx, 68h ; 'h'; Size
0x180009ed5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009eda  test    rax, rax
0x180009edd  jz      short loc_180009EEC
0x180009edf  mov     rcx, rax
0x180009ee2  call    ??0?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CEnhancedStorageSiloAction>::CComObject<CEnhancedStorageSiloAction>(void *)
0x180009ee7  mov     rbx, rax
0x180009eea  jmp     short loc_180009EEE
0x180009eec  xor     ebx, ebx
0x180009eee  mov     [rsp+48h+arg_18], rbx
0x180009ef3  jmp     short loc_180009F08
0x180009ef5  mov     rsi, [rsp+48h+arg_10]
0x180009efa  mov     r15, [rsp+48h+arg_8]
0x180009eff  mov     edi, dword ptr [rsp+48h+arg_0]
0x180009f03  mov     rbx, [rsp+48h+arg_18]
0x180009f08  test    rbx, rbx
0x180009f0b  jz      short loc_180009F6F
0x180009f0d  lea     rcx, [rbx+8]; volatile int *
0x180009f11  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180009f16  lea     rcx, [rbx+10h]; this
0x180009f1a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009f1f  test    eax, eax
0x180009f21  js      short loc_180009F2D
0x180009f23  mov     qword ptr [rbx+60h], 0
0x180009f2b  xor     eax, eax
0x180009f2d  xor     edi, edi
0x180009f2f  test    eax, eax
0x180009f31  cmovs   edi, eax
0x180009f34  lea     rcx, [rbx+8]; volatile int *
0x180009f38  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180009f3d  test    edi, edi
0x180009f3f  jnz     short loc_180009F5B
0x180009f41  mov     rax, [rbx]
0x180009f44  mov     r8, rsi
0x180009f47  mov     rdx, r15
0x180009f4a  mov     rcx, rbx
0x180009f4d  mov     rax, [rax]
0x180009f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f55  mov     edi, eax
0x180009f57  test    eax, eax
0x180009f59  jz      short loc_180009F6F
0x180009f5b  mov     rdx, [rbx]
0x180009f5e  mov     rax, [rdx+30h]
0x180009f62  mov     edx, 1
0x180009f67  mov     rcx, rbx
0x180009f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f6f  mov     eax, edi
0x180009f71  add     rsp, 20h
0x180009f75  pop     r15
0x180009f77  pop     r14
0x180009f79  pop     rdi
0x180009f7a  pop     rsi
0x180009f7b  pop     rbx
0x180009f7c  retn
```
