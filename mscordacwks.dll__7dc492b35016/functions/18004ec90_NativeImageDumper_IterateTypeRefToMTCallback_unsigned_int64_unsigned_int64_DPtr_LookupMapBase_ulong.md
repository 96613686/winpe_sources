# NativeImageDumper::IterateTypeRefToMTCallback(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004ec90`
- end: `0x18004f06f`
- name: `?IterateTypeRefToMTCallback@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `991`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800210f0`
- `0x18004240c`
- `0x180048708`
- `0x18004ec90`
- `0x18005106c`
- `0x180054028`
- `0x180055e00`
- `0x180062a9c`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004ef54`
- `KERNEL32!HeapFree` at `0x18004ef54`
- `KERNEL32!GetProcessHeap` at `0x18004ef3f`
- `KERNEL32!GetProcessHeap` at `0x18004ef3f`

## string_xrefs

- `0x18004ed2f`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NativeImageDumper::IterateTypeRefToMTCallback(
        NativeImageDumper *this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  unsigned __int64 v8; // rax
  unsigned int v9; // esi
  void *v10; // r14
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // [rsp+30h] [rbp-A1h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-99h] BYREF
  int v19; // [rsp+40h] [rbp-91h] BYREF
  __int64 v20; // [rsp+44h] [rbp-8Dh]
  LPVOID lpMem; // [rsp+50h] [rbp-81h]
  __int16 v22; // [rsp+58h] [rbp-79h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Entry");
  if ( (a2 & 1) != 0 )
    a2 = *(_QWORD *)DacInstantiateTypeByAddressHelper(a2 - 1, 8u, 1, 1);
  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 232LL))(
      *((_QWORD *)this + 17),
      "Token",
      a5 | 0x1000000);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      v8 = NativeImageDumper::DataPtrToDisplay(this, a2);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
        *((_QWORD *)this + 17),
        "MethodTable",
        v8);
    }
  }
  v9 = 0;
  if ( a5 )
  {
    if ( a2 )
    {
      if ( (a2 & 1) != 0 )
      {
        NativeImageDumper::WriteElementsFixupTargetAndName(this, (a2 >> 1) & 0x3FFFFFFF);
      }
      else
      {
        v20 = 128;
        lpMem = &v22;
        v19 = 2;
        v22 = 0;
        v17 = a2;
        NativeImageDumper::MethodTableToString(this, &v17, (SString *)&v19);
        if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
            *((_QWORD *)this + 17),
            "fake",
            0);
          if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
          {
            SString::ConvertToUnicode((SString *)&v19);
            (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
              *((_QWORD *)this + 17),
              "Name",
              lpMem);
          }
        }
        if ( (v20 & 0x800000000LL) != 0 )
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
    }
    else if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
        *((_QWORD *)this + 17),
        "fake",
        0);
      if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
        NativeImageDumper::DoWriteFieldMDToken(this, "Name", 0xFFFFFFFF, 0xFFFFFFFF, a5 | 0x1000000, 0);
    }
  }
  else if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "fake",
      0);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
        *((_QWORD *)this + 17),
        "Name",
        "mdtTypeRefNil");
  }
  result = *((unsigned int *)this + 102);
  if ( (result & 0x400) != 0 )
  {
    v13 = DacInstantiateTypeByAddressHelper(*a4, 0x48u, 1, 1);
    LOBYTE(v9) = *(_QWORD *)LookupMapBase::FindHotItemValuePtr(v13, &v18, a5) != 0;
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "hot",
      v9);
    result = *((unsigned int *)this + 102);
    if ( (result & 0x400) != 0 )
      result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  v14 = *((_QWORD *)this + 15);
  if ( v14 <= a2 && a2 < *((_QWORD *)this + 16) + v14 )
  {
    v17 = a2;
    SArray<__DPtr<MethodTable>,1>::AppendEx((NativeImageDumper *)((char *)this + 416));
    v18 = a2;
    result = NativeImageDumper::GetClassFromMT(v15, &v17, &v18);
    v16 = *((_QWORD *)this + 15);
    if ( v16 <= v17 && v17 < *((_QWORD *)this + 16) + v16 )
    {
      v18 = a2;
      return SArray<__DPtr<MethodTable>,1>::AppendEx((NativeImageDumper *)((char *)this + 464));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004ec90  mov     [rsp-8+arg_8], rbx
0x18004ec95  push    rbp
0x18004ec96  push    rsi
0x18004ec97  push    rdi
0x18004ec98  push    r12
0x18004ec9a  push    r13
0x18004ec9c  push    r14
0x18004ec9e  push    r15
0x18004eca0  lea     rbp, [rsp-1Fh]
0x18004eca5  sub     rsp, 0F0h
0x18004ecac  mov     rax, cs:__security_cookie
0x18004ecb3  xor     rax, rsp
0x18004ecb6  mov     [rbp+4Fh+var_40], rax
0x18004ecba  mov     r12, r9
0x18004ecbd  mov     rdi, rdx
0x18004ecc0  mov     rbx, rcx
0x18004ecc3  mov     r15d, [rbp+4Fh+arg_20]
0x18004ecc7  mov     r13d, 400h
0x18004eccd  test    [rcx+198h], r13d
0x18004ecd4  jz      short loc_18004ECF1
0x18004ecd6  mov     rcx, [rcx+88h]
0x18004ecdd  mov     rax, [rcx]
0x18004ece0  lea     rdx, aEntry
0x18004ece7  mov     rax, [rax+58h]
0x18004eceb  call    cs:__guard_dispatch_icall_fptr
0x18004ecf1  test    dil, 1
0x18004ecf5  jz      short loc_18004ED0E
0x18004ecf7  lea     rcx, [rdi-1]; unsigned __int64
0x18004ecfb  mov     r9b, 1; bool
0x18004ecfe  mov     r8b, r9b; bool
0x18004ed01  mov     edx, 8; unsigned int
0x18004ed06  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004ed0b  mov     rdi, [rax]
0x18004ed0e  mov     eax, [rbx+198h]
0x18004ed14  mov     r14d, 1000000h
0x18004ed1a  test    r13d, eax
0x18004ed1d  jz      short loc_18004ED7D
0x18004ed1f  mov     rcx, [rbx+88h]
0x18004ed26  mov     rax, [rcx]
0x18004ed29  mov     r8d, r15d
0x18004ed2c  or      r8d, r14d
0x18004ed2f  lea     rdx, aToken
0x18004ed36  mov     rax, [rax+0E8h]
0x18004ed3d  call    cs:__guard_dispatch_icall_fptr
0x18004ed43  mov     eax, [rbx+198h]
0x18004ed49  test    r13d, eax
0x18004ed4c  jz      short loc_18004ED7D
0x18004ed4e  mov     rdx, rdi; unsigned __int64
0x18004ed51  mov     rcx, rbx; this
0x18004ed54  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004ed59  mov     rcx, [rbx+88h]
0x18004ed60  mov     rdx, [rcx]
0x18004ed63  mov     r9, [rdx+0A8h]
0x18004ed6a  mov     r8, rax
0x18004ed6d  lea     rdx, aMethodtable
0x18004ed74  mov     rax, r9
0x18004ed77  call    cs:__guard_dispatch_icall_fptr
0x18004ed7d  xor     esi, esi
0x18004ed7f  test    r15d, r15d
0x18004ed82  jnz     short loc_18004EDED
0x18004ed84  mov     eax, [rbx+198h]
0x18004ed8a  test    r13d, eax
0x18004ed8d  jz      loc_18004EF5A
0x18004ed93  mov     rcx, [rbx+88h]
0x18004ed9a  mov     rax, [rcx]
0x18004ed9d  xor     r8d, r8d
0x18004eda0  lea     rdx, aFake
0x18004eda7  mov     rax, [rax+100h]
0x18004edae  call    cs:__guard_dispatch_icall_fptr
0x18004edb4  mov     eax, [rbx+198h]
0x18004edba  test    r13d, eax
0x18004edbd  jz      loc_18004EF5A
0x18004edc3  mov     rcx, [rbx+88h]
0x18004edca  mov     rax, [rcx]
0x18004edcd  lea     r8, aMdttyperefnil
0x18004edd4  lea     rdx, aName_0
0x18004eddb  mov     rax, [rax+0D0h]
0x18004ede2  call    cs:__guard_dispatch_icall_fptr
0x18004ede8  jmp     loc_18004EF5A
0x18004eded  test    rdi, rdi
0x18004edf0  jnz     short loc_18004EE5B
0x18004edf2  mov     eax, [rbx+198h]
0x18004edf8  test    r13d, eax
0x18004edfb  jz      loc_18004EF5A
0x18004ee01  mov     rcx, [rbx+88h]
0x18004ee08  mov     rax, [rcx]
0x18004ee0b  xor     r8d, r8d
0x18004ee0e  lea     rdx, aFake
0x18004ee15  mov     rax, [rax+100h]
0x18004ee1c  call    cs:__guard_dispatch_icall_fptr
0x18004ee22  mov     eax, [rbx+198h]
0x18004ee28  test    r13d, eax
0x18004ee2b  jz      loc_18004EF5A
0x18004ee31  mov     eax, r15d
0x18004ee34  or      eax, r14d
0x18004ee37  mov     [rsp+120h+var_F8], rsi; struct IMetaDataImport2 *
0x18004ee3c  mov     [rsp+120h+var_100], eax; unsigned int
0x18004ee40  or      r8d, 0FFFFFFFFh; unsigned int
0x18004ee44  mov     r9d, r8d; unsigned int
0x18004ee47  lea     rdx, aName_0
0x18004ee4e  mov     rcx, rbx; this
0x18004ee51  call    ?DoWriteFieldMDToken@NativeImageDumper@@QEAAXPEBDIIIPEAUIMetaDataImport2@@@Z
0x18004ee56  jmp     loc_18004EF5A
0x18004ee5b  test    dil, 1
0x18004ee5f  jz      short loc_18004EE7A
0x18004ee61  mov     rdx, rdi
0x18004ee64  shr     rdx, 1
0x18004ee67  and     edx, 3FFFFFFFh; unsigned int
0x18004ee6d  mov     rcx, rbx; this
0x18004ee70  call    ?WriteElementsFixupTargetAndName@NativeImageDumper@@QEAAXK@Z
0x18004ee75  jmp     loc_18004EF5A
0x18004ee7a  mov     [rsp+120h+var_E0], rsi
0x18004ee7f  mov     [rsp+120h+var_E0+4], 80h
0x18004ee88  mov     [rsp+120h+lpMem], rsi
0x18004ee8d  lea     rax, [rbp+4Fh+var_C8]
0x18004ee91  mov     [rsp+120h+lpMem], rax
0x18004ee96  mov     dword ptr [rsp+120h+var_E0], 2
0x18004ee9e  mov     rax, [rsp+120h+lpMem]
0x18004eea3  mov     [rax], si
0x18004eea6  mov     [rsp+120h+var_F0], rdi
0x18004eeab  lea     r8, [rsp+120h+var_E0]
0x18004eeb0  lea     rdx, [rsp+120h+var_F0]
0x18004eeb5  mov     rcx, rbx; this
0x18004eeb8  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z
0x18004eebd  mov     eax, [rbx+198h]
0x18004eec3  test    r13d, eax
0x18004eec6  jz      short loc_18004EF22
0x18004eec8  mov     rcx, [rbx+88h]
0x18004eecf  mov     rax, [rcx]
0x18004eed2  xor     r8d, r8d
0x18004eed5  lea     rdx, aFake
0x18004eedc  mov     rax, [rax+100h]
0x18004eee3  call    cs:__guard_dispatch_icall_fptr
0x18004eee9  mov     eax, [rbx+198h]
0x18004eeef  test    r13d, eax
0x18004eef2  jz      short loc_18004EF22
0x18004eef4  lea     rcx, [rsp+120h+var_E0]; this
0x18004eef9  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004eefe  mov     rcx, [rbx+88h]
0x18004ef05  mov     rax, [rcx]
0x18004ef08  mov     r8, [rsp+120h+lpMem]
0x18004ef0d  lea     rdx, aName_0
0x18004ef14  mov     rax, [rax+0D8h]
0x18004ef1b  call    cs:__guard_dispatch_icall_fptr
0x18004ef21  nop
0x18004ef22  test    [rsp+120h+var_D8], 8
0x18004ef27  jz      short loc_18004EF5A
0x18004ef29  mov     r14, [rsp+120h+lpMem]
0x18004ef2e  test    r14, r14
0x18004ef31  jz      short loc_18004EF5A
0x18004ef33  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004ef3a  test    rax, rax
0x18004ef3d  jnz     short loc_18004EF4C
0x18004ef3f  call    cs:__imp_GetProcessHeap
0x18004ef45  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004ef4c  mov     r8, r14; lpMem
0x18004ef4f  xor     edx, edx; dwFlags
0x18004ef51  mov     rcx, rax; hHeap
0x18004ef54  call    cs:__imp_HeapFree
0x18004ef5a  mov     eax, [rbx+198h]
0x18004ef60  test    r13d, eax
0x18004ef63  jz      short loc_18004EFD0
0x18004ef65  mov     r9b, 1; bool
0x18004ef68  mov     r8b, r9b; bool
0x18004ef6b  mov     edx, 48h ; 'H'; unsigned int
0x18004ef70  mov     rcx, [r12]; unsigned __int64
0x18004ef74  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004ef79  mov     r8d, r15d
0x18004ef7c  lea     rdx, [rsp+120h+var_E8]
0x18004ef81  mov     rcx, rax
0x18004ef84  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004ef89  mov     rcx, [rbx+88h]
0x18004ef90  mov     rdx, [rcx]
0x18004ef93  cmp     [rax], rsi
0x18004ef96  setnz   sil
0x18004ef9a  mov     rax, [rdx+100h]
0x18004efa1  mov     r8d, esi
0x18004efa4  lea     rdx, aHot
0x18004efab  call    cs:__guard_dispatch_icall_fptr
0x18004efb1  mov     eax, [rbx+198h]
0x18004efb7  test    r13d, eax
0x18004efba  jz      short loc_18004EFD0
0x18004efbc  mov     rcx, [rbx+88h]
0x18004efc3  mov     rax, [rcx]
0x18004efc6  mov     rax, [rax+60h]
0x18004efca  call    cs:__guard_dispatch_icall_fptr
0x18004efd0  mov     rcx, [rbx+78h]
0x18004efd4  cmp     rcx, rdi
0x18004efd7  ja      short loc_18004F048
0x18004efd9  add     rcx, [rbx+80h]
0x18004efe0  cmp     rdi, rcx
0x18004efe3  jnb     short loc_18004F048
0x18004efe5  mov     [rsp+120h+var_F0], rdi
0x18004efea  lea     rcx, [rbx+1A0h]
0x18004eff1  lea     r8, [rsp+120h+var_F0]
0x18004eff6  lea     rdx, [rsp+120h+var_E8]
0x18004effb  call    ?AppendEx@?$SArray@V?$__DPtr@VMethodTable@@@@$00@@QEAA?AV?$__DPtr@VMethodTable@@@@V2@@Z
0x18004f000  mov     [rsp+120h+var_E8], rdi
0x18004f005  lea     r8, [rsp+120h+var_E8]
0x18004f00a  lea     rdx, [rsp+120h+var_F0]
0x18004f00f  call    ?GetClassFromMT@NativeImageDumper@@AEAA?AV?$__DPtr@VEEClass@@@@V?$__DPtr@VMethodTable@@@@@Z
0x18004f014  mov     rcx, [rbx+78h]
0x18004f018  cmp     rcx, [rsp+120h+var_F0]
0x18004f01d  ja      short loc_18004F048
0x18004f01f  add     rcx, [rbx+80h]
0x18004f026  cmp     [rsp+120h+var_F0], rcx
0x18004f02b  jnb     short loc_18004F048
0x18004f02d  mov     [rsp+120h+var_E8], rdi
0x18004f032  lea     rcx, [rbx+1D0h]
0x18004f039  lea     r8, [rsp+120h+var_E8]
0x18004f03e  lea     rdx, [rsp+120h+var_F0]
0x18004f043  call    ?AppendEx@?$SArray@V?$__DPtr@VMethodTable@@@@$00@@QEAA?AV?$__DPtr@VMethodTable@@@@V2@@Z
0x18004f048  mov     rcx, [rbp+4Fh+var_40]
0x18004f04c  xor     rcx, rsp; StackCookie
0x18004f04f  call    __security_check_cookie
0x18004f054  mov     rbx, [rsp+120h+arg_8]
0x18004f05c  add     rsp, 0F0h
0x18004f063  pop     r15
0x18004f065  pop     r14
0x18004f067  pop     r13
0x18004f069  pop     r12
0x18004f06b  pop     rdi
0x18004f06c  pop     rsi
0x18004f06d  pop     rbp
0x18004f06e  retn
```
