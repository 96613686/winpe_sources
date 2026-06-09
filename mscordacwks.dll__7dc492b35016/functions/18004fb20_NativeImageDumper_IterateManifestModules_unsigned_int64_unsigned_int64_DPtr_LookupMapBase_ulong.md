# NativeImageDumper::IterateManifestModules(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004fb20`
- end: `0x18004fdd4`
- name: `?IterateManifestModules@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `692`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800210f0`
- `0x18004240c`
- `0x180045fa8`
- `0x18004fb20`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004fd01`
- `KERNEL32!HeapFree` at `0x18004fd01`
- `KERNEL32!GetProcessHeap` at `0x18004fcec`
- `KERNEL32!GetProcessHeap` at `0x18004fcec`

## string_xrefs

- `0x18004fbc3`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::IterateManifestModules(
        NativeImageDumper *this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  unsigned __int64 v8; // rax
  unsigned int v9; // edi
  void *v10; // rsi
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  void *v13; // rax
  _BYTE v14[16]; // [rsp+30h] [rbp-91h] BYREF
  int v15; // [rsp+40h] [rbp-81h] BYREF
  __int64 v16; // [rsp+44h] [rbp-7Dh]
  LPVOID lpMem; // [rsp+50h] [rbp-71h]
  __int16 v18; // [rsp+58h] [rbp-69h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Entry");
  if ( (a2 & 1) != 0 )
    a2 = *(_QWORD *)DacInstantiateTypeByAddressHelper(a2 - 1, 8u, 1, 1);
  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 232LL))(
      *((_QWORD *)this + 17),
      "Token",
      a5 | 0x23000000);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      v8 = NativeImageDumper::DataPtrToDisplay(this, a2);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
        *((_QWORD *)this + 17),
        "Module",
        v8);
      if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
          *((_QWORD *)this + 17),
          "fake",
          0);
    }
  }
  v9 = 0;
  if ( a5 && a2 )
  {
    v16 = 128;
    lpMem = &v18;
    v15 = 2;
    v18 = 0;
    NativeImageDumper::AppendTokenName(
      this,
      a5 | 0x23000000,
      (struct SString *)&v15,
      *((struct IMetaDataImport2 **)this + 29),
      0);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v15);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        lpMem);
    }
    if ( (v16 & 0x800000000LL) != 0 )
    {
      v10 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v10);
      }
    }
  }
  else if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
      *((_QWORD *)this + 17),
      "Name",
      "mdtAssemblyRefNil");
  }
  result = *((unsigned int *)this + 102);
  if ( (result & 0x400) != 0 )
  {
    v13 = DacInstantiateTypeByAddressHelper(*a4, 0x48u, 1, 1);
    LOBYTE(v9) = *(_QWORD *)LookupMapBase::FindHotItemValuePtr(v13, v14, a5) != 0;
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "hot",
      v9);
    result = *((unsigned int *)this + 102);
    if ( (result & 0x400) != 0 )
      return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  return result;
}

```

## disassembly

```asm
0x18004fb20  mov     [rsp-8+arg_8], rbx
0x18004fb25  mov     [rsp-8+arg_10], rsi
0x18004fb2a  push    rbp
0x18004fb2b  push    rdi
0x18004fb2c  push    r12
0x18004fb2e  push    r14
0x18004fb30  push    r15
0x18004fb32  lea     rbp, [rsp-2Fh]
0x18004fb37  sub     rsp, 0F0h
0x18004fb3e  mov     rax, cs:__security_cookie
0x18004fb45  xor     rax, rsp
0x18004fb48  mov     [rbp+4Fh+var_30], rax
0x18004fb4c  mov     r15, r9
0x18004fb4f  mov     rsi, rdx
0x18004fb52  mov     rbx, rcx
0x18004fb55  mov     r14d, [rbp+4Fh+arg_20]
0x18004fb59  mov     r12d, 400h
0x18004fb5f  test    [rcx+198h], r12d
0x18004fb66  jz      short loc_18004FB83
0x18004fb68  mov     rcx, [rcx+88h]
0x18004fb6f  mov     rax, [rcx]
0x18004fb72  lea     rdx, aEntry
0x18004fb79  mov     rax, [rax+58h]
0x18004fb7d  call    cs:__guard_dispatch_icall_fptr
0x18004fb83  test    sil, 1
0x18004fb87  jz      short loc_18004FBA0
0x18004fb89  lea     rcx, [rsi-1]; unsigned __int64
0x18004fb8d  mov     r9b, 1; bool
0x18004fb90  mov     r8b, r9b; bool
0x18004fb93  mov     edx, 8; unsigned int
0x18004fb98  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004fb9d  mov     rsi, [rax]
0x18004fba0  mov     eax, [rbx+198h]
0x18004fba6  test    r12d, eax
0x18004fba9  jz      loc_18004FC3D
0x18004fbaf  mov     rcx, [rbx+88h]
0x18004fbb6  mov     rax, [rcx]
0x18004fbb9  mov     r8d, r14d
0x18004fbbc  or      r8d, 23000000h
0x18004fbc3  lea     rdx, aToken
0x18004fbca  mov     rax, [rax+0E8h]
0x18004fbd1  call    cs:__guard_dispatch_icall_fptr
0x18004fbd7  mov     eax, [rbx+198h]
0x18004fbdd  test    r12d, eax
0x18004fbe0  jz      short loc_18004FC3D
0x18004fbe2  mov     rdx, rsi; unsigned __int64
0x18004fbe5  mov     rcx, rbx; this
0x18004fbe8  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004fbed  mov     rcx, [rbx+88h]
0x18004fbf4  mov     rdx, [rcx]
0x18004fbf7  mov     r9, [rdx+0A8h]
0x18004fbfe  mov     r8, rax
0x18004fc01  lea     rdx, aModule_2
0x18004fc08  mov     rax, r9
0x18004fc0b  call    cs:__guard_dispatch_icall_fptr
0x18004fc11  mov     eax, [rbx+198h]
0x18004fc17  test    r12d, eax
0x18004fc1a  jz      short loc_18004FC3D
0x18004fc1c  mov     rcx, [rbx+88h]
0x18004fc23  mov     rax, [rcx]
0x18004fc26  xor     r8d, r8d
0x18004fc29  lea     rdx, aFake
0x18004fc30  mov     rax, [rax+100h]
0x18004fc37  call    cs:__guard_dispatch_icall_fptr
0x18004fc3d  xor     edi, edi
0x18004fc3f  test    r14d, r14d
0x18004fc42  jz      loc_18004FD09
0x18004fc48  test    rsi, rsi
0x18004fc4b  jz      loc_18004FD09
0x18004fc51  mov     [rsp+110h+var_D0], rdi
0x18004fc56  mov     [rbp+4Fh+var_D0+4], 80h
0x18004fc5e  mov     [rbp+4Fh+lpMem], rdi
0x18004fc62  lea     rax, [rbp+4Fh+var_B8]
0x18004fc66  mov     [rbp+4Fh+lpMem], rax
0x18004fc6a  mov     dword ptr [rsp+110h+var_D0], 2
0x18004fc72  mov     rax, [rbp+4Fh+lpMem]
0x18004fc76  mov     [rax], di
0x18004fc79  mov     edx, r14d
0x18004fc7c  or      edx, 23000000h; unsigned int
0x18004fc82  mov     [rsp+110h+var_F0], dil; bool
0x18004fc87  mov     r9, [rbx+0E8h]; struct IMetaDataImport2 *
0x18004fc8e  lea     r8, [rsp+110h+var_D0]; struct SString *
0x18004fc93  mov     rcx, rbx; this
0x18004fc96  call    ?AppendTokenName@NativeImageDumper@@QEAAXIAEAVSString@@PEAUIMetaDataImport2@@_N@Z
0x18004fc9b  test    [rbx+198h], r12d
0x18004fca2  jz      short loc_18004FCD1
0x18004fca4  lea     rcx, [rsp+110h+var_D0]; this
0x18004fca9  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004fcae  mov     rcx, [rbx+88h]
0x18004fcb5  mov     rax, [rcx]
0x18004fcb8  mov     r8, [rbp+4Fh+lpMem]
0x18004fcbc  lea     rdx, aName_0
0x18004fcc3  mov     rax, [rax+0D8h]
0x18004fcca  call    cs:__guard_dispatch_icall_fptr
0x18004fcd0  nop
0x18004fcd1  test    [rbp+4Fh+var_C8], 8
0x18004fcd5  jz      short loc_18004FD37
0x18004fcd7  mov     rsi, [rbp+4Fh+lpMem]
0x18004fcdb  test    rsi, rsi
0x18004fcde  jz      short loc_18004FD37
0x18004fce0  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004fce7  test    rax, rax
0x18004fcea  jnz     short loc_18004FCF9
0x18004fcec  call    cs:__imp_GetProcessHeap
0x18004fcf2  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004fcf9  mov     r8, rsi; lpMem
0x18004fcfc  xor     edx, edx; dwFlags
0x18004fcfe  mov     rcx, rax; hHeap
0x18004fd01  call    cs:__imp_HeapFree
0x18004fd07  jmp     short loc_18004FD37
0x18004fd09  test    [rbx+198h], r12d
0x18004fd10  jz      short loc_18004FD37
0x18004fd12  mov     rcx, [rbx+88h]
0x18004fd19  mov     rax, [rcx]
0x18004fd1c  lea     r8, aMdtassemblyref
0x18004fd23  lea     rdx, aName_0
0x18004fd2a  mov     rax, [rax+0D0h]
0x18004fd31  call    cs:__guard_dispatch_icall_fptr
0x18004fd37  mov     eax, [rbx+198h]
0x18004fd3d  test    r12d, eax
0x18004fd40  jz      short loc_18004FDAC
0x18004fd42  mov     r9b, 1; bool
0x18004fd45  mov     r8b, r9b; bool
0x18004fd48  mov     edx, 48h ; 'H'; unsigned int
0x18004fd4d  mov     rcx, [r15]; unsigned __int64
0x18004fd50  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004fd55  mov     r8d, r14d
0x18004fd58  lea     rdx, [rsp+110h+var_E0]
0x18004fd5d  mov     rcx, rax
0x18004fd60  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004fd65  mov     rcx, [rbx+88h]
0x18004fd6c  mov     rdx, [rcx]
0x18004fd6f  cmp     [rax], rdi
0x18004fd72  setnz   dil
0x18004fd76  mov     rax, [rdx+100h]
0x18004fd7d  mov     r8d, edi
0x18004fd80  lea     rdx, aHot
0x18004fd87  call    cs:__guard_dispatch_icall_fptr
0x18004fd8d  mov     eax, [rbx+198h]
0x18004fd93  test    r12d, eax
0x18004fd96  jz      short loc_18004FDAC
0x18004fd98  mov     rcx, [rbx+88h]
0x18004fd9f  mov     rax, [rcx]
0x18004fda2  mov     rax, [rax+60h]
0x18004fda6  call    cs:__guard_dispatch_icall_fptr
0x18004fdac  mov     rcx, [rbp+4Fh+var_30]
0x18004fdb0  xor     rcx, rsp; StackCookie
0x18004fdb3  call    __security_check_cookie
0x18004fdb8  lea     r11, [rsp+110h+var_20]
0x18004fdc0  mov     rbx, [r11+38h]
0x18004fdc4  mov     rsi, [r11+40h]
0x18004fdc8  mov     rsp, r11
0x18004fdcb  pop     r15
0x18004fdcd  pop     r14
0x18004fdcf  pop     r12
0x18004fdd1  pop     rdi
0x18004fdd2  pop     rbp
0x18004fdd3  retn
```
