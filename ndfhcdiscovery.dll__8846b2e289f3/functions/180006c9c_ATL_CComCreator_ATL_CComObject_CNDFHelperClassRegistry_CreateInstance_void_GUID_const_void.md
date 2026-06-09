# ATL::CComCreator<ATL::CComObject<CNDFHelperClassRegistry>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006c9c`
- end: `0x180006d84`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNDFHelperClassRegistry@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006a40`

## callees

- `0x1800012e0`
- `0x180005270`
- `0x180006c9c`
- `0x1800079f0`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CNDFHelperClassRegistry>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rbx
  int v9; // ecx
  int v10; // eax
  __int64 v13; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x2B8u);
    if ( v7 )
      v8 = ATL::CComObject<CNDFHelperClassRegistry>::CComObject<CNDFHelperClassRegistry>((__int64)v7);
    else
      v8 = 0;
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 16));
    if ( v9 >= 0 )
      *(_BYTE *)(v8 + 56) = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006c9c  mov     [rsp+arg_10], r8
0x180006ca1  mov     [rsp+arg_8], rdx
0x180006ca6  mov     [rsp+arg_0], rcx
0x180006cab  push    rbx
0x180006cac  push    rsi
0x180006cad  push    rdi
0x180006cae  push    r14
0x180006cb0  sub     rsp, 38h
0x180006cb4  mov     rsi, r8
0x180006cb7  mov     r14, rdx
0x180006cba  test    r8, r8
0x180006cbd  jnz     short loc_180006CC9
0x180006cbf  mov     eax, 80004003h
0x180006cc4  jmp     loc_180006D79
0x180006cc9  mov     qword ptr [r8], 0
0x180006cd0  mov     edi, 8007000Eh
0x180006cd5  mov     dword ptr [rsp+58h+arg_0], edi
0x180006cd9  mov     [rsp+58h+arg_18], 0
0x180006ce2  mov     ecx, 2B8h; Size
0x180006ce7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006cec  mov     [rsp+58h+var_38], rax
0x180006cf1  test    rax, rax
0x180006cf4  jz      short loc_180006D03
0x180006cf6  mov     rcx, rax
0x180006cf9  call    ??0?$CComObject@VCNDFHelperClassRegistry@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CNDFHelperClassRegistry>::CComObject<CNDFHelperClassRegistry>(void *)
0x180006cfe  mov     rbx, rax
0x180006d01  jmp     short loc_180006D05
0x180006d03  xor     ebx, ebx
0x180006d05  mov     [rsp+58h+arg_18], rbx
0x180006d0a  jmp     short loc_180006D1F
0x180006d0c  mov     rsi, [rsp+58h+arg_10]
0x180006d11  mov     r14, [rsp+58h+arg_8]
0x180006d16  mov     edi, dword ptr [rsp+58h+arg_0]
0x180006d1a  mov     rbx, [rsp+58h+arg_18]
0x180006d1f  test    rbx, rbx
0x180006d22  jz      short loc_180006D77
0x180006d24  lea     rcx, [rbx+10h]; this
0x180006d28  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006d2d  mov     ecx, eax
0x180006d2f  test    eax, eax
0x180006d31  js      short loc_180006D37
0x180006d33  mov     byte ptr [rbx+38h], 1
0x180006d37  xor     eax, eax
0x180006d39  test    ecx, ecx
0x180006d3b  cmovs   eax, ecx
0x180006d3e  xor     edi, edi
0x180006d40  test    eax, eax
0x180006d42  cmovs   edi, eax
0x180006d45  test    edi, edi
0x180006d47  jnz     short loc_180006D63
0x180006d49  mov     rax, [rbx]
0x180006d4c  mov     r8, rsi
0x180006d4f  mov     rdx, r14
0x180006d52  mov     rcx, rbx
0x180006d55  mov     rax, [rax]
0x180006d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d5d  mov     edi, eax
0x180006d5f  test    eax, eax
0x180006d61  jz      short loc_180006D77
0x180006d63  mov     r8, [rbx]
0x180006d66  mov     edx, 1
0x180006d6b  mov     rcx, rbx
0x180006d6e  mov     rax, [r8+48h]
0x180006d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d77  mov     eax, edi
0x180006d79  add     rsp, 38h
0x180006d7d  pop     r14
0x180006d7f  pop     rdi
0x180006d80  pop     rsi
0x180006d81  pop     rbx
0x180006d82  retn
```
