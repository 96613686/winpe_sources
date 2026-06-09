# ATL::CComCreator<ATL::CComObject<CEnhancedStorageSilo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009d90`
- end: `0x180009e80`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageSilo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009b20`

## callees

- `0x180001264`
- `0x180002008`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x180006a64`
- `0x180009d90`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CEnhancedStorageSilo>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  void *v7; // rax
  volatile int *v8; // rbx
  int v9; // eax
  CEnhancedStorageSilo *v10; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x60u);
  if ( v7 )
    v8 = (volatile int *)ATL::CComObject<CEnhancedStorageSilo>::CComObject<CEnhancedStorageSilo>(v7);
  else
    v8 = 0;
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread(v8 + 2);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    if ( v9 >= 0 )
      v9 = CEnhancedStorageSilo::FinalConstruct(v10);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread(v8 + 2);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 64LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009d90  mov     [rsp+arg_10], r8
0x180009d95  mov     [rsp+arg_8], rdx
0x180009d9a  mov     [rsp+arg_0], rcx
0x180009d9f  push    rbx
0x180009da0  push    rsi
0x180009da1  push    rdi
0x180009da2  push    r14
0x180009da4  push    r15
0x180009da6  sub     rsp, 20h
0x180009daa  mov     rsi, r8
0x180009dad  mov     r15, rdx
0x180009db0  test    r8, r8
0x180009db3  jnz     short loc_180009DBF
0x180009db5  mov     eax, 80004003h
0x180009dba  jmp     loc_180009E74
0x180009dbf  mov     qword ptr [r8], 0
0x180009dc6  mov     edi, 8007000Eh
0x180009dcb  mov     dword ptr [rsp+48h+arg_0], edi
0x180009dcf  mov     [rsp+48h+arg_18], 0
0x180009dd8  mov     ecx, 60h ; '`'; Size
0x180009ddd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009de2  test    rax, rax
0x180009de5  jz      short loc_180009DF4
0x180009de7  mov     rcx, rax
0x180009dea  call    ??0?$CComObject@VCEnhancedStorageSilo@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CEnhancedStorageSilo>::CComObject<CEnhancedStorageSilo>(void *)
0x180009def  mov     rbx, rax
0x180009df2  jmp     short loc_180009DF6
0x180009df4  xor     ebx, ebx
0x180009df6  mov     [rsp+48h+arg_18], rbx
0x180009dfb  jmp     short loc_180009E10
0x180009dfd  mov     rsi, [rsp+48h+arg_10]
0x180009e02  mov     r15, [rsp+48h+arg_8]
0x180009e07  mov     edi, dword ptr [rsp+48h+arg_0]
0x180009e0b  mov     rbx, [rsp+48h+arg_18]
0x180009e10  test    rbx, rbx
0x180009e13  jz      short loc_180009E72
0x180009e15  lea     rcx, [rbx+8]; volatile int *
0x180009e19  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180009e1e  lea     rcx, [rbx+10h]; this
0x180009e22  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009e27  test    eax, eax
0x180009e29  js      short loc_180009E30
0x180009e2b  call    ?FinalConstruct@CEnhancedStorageSilo@@QEAAJXZ; CEnhancedStorageSilo::FinalConstruct(void)
0x180009e30  xor     edi, edi
0x180009e32  test    eax, eax
0x180009e34  cmovs   edi, eax
0x180009e37  lea     rcx, [rbx+8]; volatile int *
0x180009e3b  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180009e40  test    edi, edi
0x180009e42  jnz     short loc_180009E5E
0x180009e44  mov     rax, [rbx]
0x180009e47  mov     r8, rsi
0x180009e4a  mov     rdx, r15
0x180009e4d  mov     rcx, rbx
0x180009e50  mov     rax, [rax]
0x180009e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e58  mov     edi, eax
0x180009e5a  test    eax, eax
0x180009e5c  jz      short loc_180009E72
0x180009e5e  mov     rdx, [rbx]
0x180009e61  mov     rax, [rdx+40h]
0x180009e65  mov     edx, 1
0x180009e6a  mov     rcx, rbx
0x180009e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e72  mov     eax, edi
0x180009e74  add     rsp, 20h
0x180009e78  pop     r15
0x180009e7a  pop     r14
0x180009e7c  pop     rdi
0x180009e7d  pop     rsi
0x180009e7e  pop     rbx
0x180009e7f  retn
```
