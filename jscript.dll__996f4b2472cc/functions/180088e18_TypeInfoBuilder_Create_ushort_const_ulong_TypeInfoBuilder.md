# TypeInfoBuilder::Create(ushort const *,ulong,TypeInfoBuilder * *)

- ea: `0x180088e18`
- end: `0x180089059`
- name: `?Create@TypeInfoBuilder@@SAJPEBGKPEAPEAV1@@Z`
- size: `577`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct TypeInfoBuilder **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180077dd0`

## callees

- `0x1800585d0`
- `0x180074ecc`
- `0x180088e18`
- `0x1800890fc`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x180088e92`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x180088e92`

## pseudocode

```c
__int64 __fastcall TypeInfoBuilder::Create(const unsigned __int16 *a1, unsigned int a2, ICreateTypeLib2 ***a3)
{
  ICreateTypeLib2 **v6; // rax
  ICreateTypeLib2 **v7; // rbx
  HRESULT DispatchTypeInfo; // edi
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  struct ITypeInfo *v13; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  v6 = (ICreateTypeLib2 **)operator new(0x18u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    v6[2] = 0;
    DispatchTypeInfo = GetDispatchTypeInfo(&v13);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v9 = v7 + 2;
    DispatchTypeInfo = CreateTypeLib2(SYS_WIN32, L"JSDeb.tlb", v7 + 2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 80LL))(*v9, a2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 32LL))(
                         *v9,
                         L"JScriptTypeLib");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 56LL))(
                         *v9,
                         L"JScript Type Library");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v9 + 40LL))(*v9, 10, 8);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v9 + 48LL))(*v9, &IID_IScriptTypeLib);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 88LL))(*v9, 0);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v10 = *v9;
    v11 = v7 + 1;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, ICreateTypeLib2 **))(*(_QWORD *)v10 + 24LL))(
                         v10,
                         a1,
                         4,
                         v7 + 1);
    if ( DispatchTypeInfo < 0
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v11 + 40LL))(
                               *v11,
                               L"JScript Type Info"),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v11 + 24LL))(
                               *v11,
                               &IID_IScriptTypeInfo),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v11 + 56LL))(*v11, 10, 8),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, struct ITypeInfo *, unsigned int *))(*(_QWORD *)*v11 + 64LL))(
                               *v11,
                               v13,
                               &v14),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v11 + 80LL))(*v11, 0, v14),
          DispatchTypeInfo < 0) )
    {
LABEL_17:
      TypeInfoBuilder::Release((TypeInfoBuilder *)v7);
    }
    else
    {
      DispatchTypeInfo = 0;
      *a3 = v7;
    }
  }
  else
  {
    DispatchTypeInfo = -2147024882;
  }
  if ( v13 )
    ((void (__fastcall *)(struct ITypeInfo *))v13->lpVtbl->Release)(v13);
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x180088e18  mov     rax, rsp
0x180088e1b  push    rbx
0x180088e1c  push    rbp
0x180088e1d  push    rsi
0x180088e1e  push    rdi
0x180088e1f  push    r14
0x180088e21  push    r15
0x180088e23  sub     rsp, 48h
0x180088e27  mov     r15, rcx
0x180088e2a  mov     dword ptr [rax+20h], 0
0x180088e31  mov     ecx, 18h; Size
0x180088e36  mov     qword ptr [rax-48h], 0
0x180088e3e  mov     r14, r8
0x180088e41  mov     ebp, edx
0x180088e43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180088e48  mov     rbx, rax
0x180088e4b  test    rax, rax
0x180088e4e  jz      loc_18008902E
0x180088e54  lea     rcx, [rsp+78h+var_48]; struct ITypeInfo **
0x180088e59  mov     qword ptr [rax], 0
0x180088e60  mov     qword ptr [rax+8], 0
0x180088e68  mov     qword ptr [rax+10h], 0
0x180088e70  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x180088e75  mov     edi, eax
0x180088e77  test    eax, eax
0x180088e79  js      loc_180089024
0x180088e7f  lea     rsi, [rbx+10h]
0x180088e83  mov     ecx, 1; syskind
0x180088e88  mov     r8, rsi; ppctlib
0x180088e8b  lea     rdx, aJsdebTlb; "JSDeb.tlb"
0x180088e92  call    cs:__imp_CreateTypeLib2
0x180088e99  nop     dword ptr [rax+rax+00h]
0x180088e9e  mov     edi, eax
0x180088ea0  test    eax, eax
0x180088ea2  js      loc_180089024
0x180088ea8  mov     rcx, [rsi]
0x180088eab  mov     edx, ebp
0x180088ead  mov     rax, [rcx]
0x180088eb0  mov     rax, [rax+50h]
0x180088eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088eb9  mov     edi, eax
0x180088ebb  test    eax, eax
0x180088ebd  js      loc_180089024
0x180088ec3  mov     rcx, [rsi]
0x180088ec6  lea     rdx, aJscripttypelib; "JScriptTypeLib"
0x180088ecd  mov     rax, [rcx]
0x180088ed0  mov     rax, [rax+20h]
0x180088ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ed9  mov     edi, eax
0x180088edb  test    eax, eax
0x180088edd  js      loc_180089024
0x180088ee3  mov     rcx, [rsi]
0x180088ee6  lea     rdx, aJscriptTypeLib; "JScript Type Library"
0x180088eed  mov     rax, [rcx]
0x180088ef0  mov     rax, [rax+38h]
0x180088ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ef9  mov     edi, eax
0x180088efb  test    eax, eax
0x180088efd  js      loc_180089024
0x180088f03  mov     rcx, [rsi]
0x180088f06  mov     ebp, 8
0x180088f0b  mov     r8d, ebp
0x180088f0e  mov     rax, [rcx]
0x180088f11  lea     edx, [rbp+2]
0x180088f14  mov     rax, [rax+28h]
0x180088f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f1d  mov     edi, eax
0x180088f1f  test    eax, eax
0x180088f21  js      loc_180089024
0x180088f27  mov     rcx, [rsi]
0x180088f2a  lea     rdx, IID_IScriptTypeLib
0x180088f31  mov     rax, [rcx]
0x180088f34  mov     rax, [rax+30h]
0x180088f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f3d  mov     edi, eax
0x180088f3f  test    eax, eax
0x180088f41  js      loc_180089024
0x180088f47  mov     rcx, [rsi]
0x180088f4a  xor     edx, edx
0x180088f4c  mov     rax, [rcx]
0x180088f4f  mov     rax, [rax+58h]
0x180088f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f58  mov     edi, eax
0x180088f5a  test    eax, eax
0x180088f5c  js      loc_180089024
0x180088f62  mov     rcx, [rsi]
0x180088f65  lea     r8d, [rbp-4]
0x180088f69  lea     rsi, [rbx+8]
0x180088f6d  mov     rdx, r15
0x180088f70  mov     r9, rsi
0x180088f73  mov     rax, [rcx]
0x180088f76  mov     rax, [rax+18h]
0x180088f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f7f  mov     edi, eax
0x180088f81  test    eax, eax
0x180088f83  js      loc_180089024
0x180088f89  mov     rcx, [rsi]
0x180088f8c  lea     rdx, aJscriptTypeInf; "JScript Type Info"
0x180088f93  mov     rax, [rcx]
0x180088f96  mov     rax, [rax+28h]
0x180088f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f9f  mov     edi, eax
0x180088fa1  test    eax, eax
0x180088fa3  js      short loc_180089024
0x180088fa5  mov     rcx, [rsi]
0x180088fa8  lea     rdx, IID_IScriptTypeInfo
0x180088faf  mov     rax, [rcx]
0x180088fb2  mov     rax, [rax+18h]
0x180088fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fbb  mov     edi, eax
0x180088fbd  test    eax, eax
0x180088fbf  js      short loc_180089024
0x180088fc1  mov     rcx, [rsi]
0x180088fc4  lea     edx, [rbp+2]
0x180088fc7  mov     r8d, ebp
0x180088fca  mov     rax, [rcx]
0x180088fcd  mov     rax, [rax+38h]
0x180088fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fd6  mov     edi, eax
0x180088fd8  test    eax, eax
0x180088fda  js      short loc_180089024
0x180088fdc  mov     rcx, [rsi]
0x180088fdf  lea     r8, [rsp+78h+arg_18]
0x180088fe7  mov     rdx, [rsp+78h+var_48]
0x180088fec  mov     rax, [rcx]
0x180088fef  mov     rax, [rax+40h]
0x180088ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ff8  mov     edi, eax
0x180088ffa  test    eax, eax
0x180088ffc  js      short loc_180089024
0x180088ffe  mov     rcx, [rsi]
0x180089001  xor     edx, edx
0x180089003  mov     r8d, [rsp+78h+arg_18]
0x18008900b  mov     rax, [rcx]
0x18008900e  mov     rax, [rax+50h]
0x180089012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089017  mov     edi, eax
0x180089019  test    eax, eax
0x18008901b  js      short loc_180089024
0x18008901d  xor     edi, edi
0x18008901f  mov     [r14], rbx
0x180089022  jmp     short loc_180089033
0x180089024  mov     rcx, rbx; this
0x180089027  call    ?Release@TypeInfoBuilder@@QEAAXXZ; TypeInfoBuilder::Release(void)
0x18008902c  jmp     short loc_180089033
0x18008902e  mov     edi, 8007000Eh
0x180089033  mov     rcx, [rsp+78h+var_48]
0x180089038  test    rcx, rcx
0x18008903b  jz      short loc_180089049
0x18008903d  mov     rax, [rcx]
0x180089040  mov     rax, [rax+10h]
0x180089044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089049  mov     eax, edi
0x18008904b  add     rsp, 48h
0x18008904f  pop     r15
0x180089051  pop     r14
0x180089053  pop     rdi
0x180089054  pop     rsi
0x180089055  pop     rbp
0x180089056  pop     rbx
0x180089057  retn
```
