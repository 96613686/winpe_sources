# Dfdll::CSubscription::TimeElapsedSince(__int64 &,ushort const *)

- ea: `0x180011ba8`
- end: `0x18001213f`
- name: `?TimeElapsedSince@CSubscription@Dfdll@@IEAAJAEA_JPEBG@Z`
- size: `1431`
- prototype: `int(Dfdll::CSubscription *__hidden this, __int64 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000972c`
- `0x180009c44`

## callees

- `0x180011ba8`
- `0x1800122cc`
- `0x180012b30`
- `0x180012bd0`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012025`
- `KERNEL32!GetLastError` at `0x180012085`
- `KERNEL32!GetLastError` at `0x180012025`
- `KERNEL32!GetLastError` at `0x180012085`
- `KERNEL32!GetSystemTime` at `0x18001206d`
- `KERNEL32!GetSystemTime` at `0x18001206d`
- `KERNEL32!SystemTimeToFileTime` at `0x18001201b`
- `KERNEL32!SystemTimeToFileTime` at `0x18001207b`
- `KERNEL32!SystemTimeToFileTime` at `0x18001201b`
- `KERNEL32!SystemTimeToFileTime` at `0x18001207b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::TimeElapsedSince(
        Dfdll::CSubscription *this,
        __int64 *a2,
        unsigned __int16 *a3)
{
  int v3; // ebx
  void **v5; // [rsp+30h] [rbp-29h]
  int v6; // [rsp+38h] [rbp-21h]
  __int64 v7; // [rsp+40h] [rbp-19h]
  void **v8; // [rsp+48h] [rbp-11h]
  void *v9; // [rsp+50h] [rbp-9h]
  int v10; // [rsp+58h] [rbp-1h]

  if ( a3 )
  {
    v6 = 0;
    v7 = 0;
    v5 = &Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::`vftable';
    v9 = 0;
    v10 = 0;
    v8 = &Dfdll::CBuffer<unsigned int>::`vftable';
    v3 = Dfdll::CConvert::ToUINTArray(a3);
    if ( v3 >= 0 )
      v3 = -2147024809;
    v5 = &Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::`vftable';
    v8 = &Dfdll::CBuffer<unsigned int>::`vftable';
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011ba8  mov     [rsp-8+arg_0], rbx
0x180011bad  mov     [rsp-8+arg_18], rsi
0x180011bb2  push    rbp
0x180011bb3  push    rdi
0x180011bb4  push    r12
0x180011bb6  push    r14
0x180011bb8  push    r15
0x180011bba  lea     rbp, [rsp-37h]
0x180011bbf  sub     rsp, 90h
0x180011bc6  mov     rax, cs:__security_cookie
0x180011bcd  xor     rax, rsp
0x180011bd0  mov     [rbp+57h+var_30], rax
0x180011bd4  mov     rax, r8
0x180011bd7  mov     rsi, rdx
0x180011bda  xor     r14d, r14d
0x180011bdd  test    r8, r8
0x180011be0  jnz     short loc_180011BEC
0x180011be2  mov     ebx, 80070057h
0x180011be7  jmp     loc_180012115
0x180011bec  mov     [rbp+57h+var_78], r14d
0x180011bf0  mov     [rbp+57h+var_70], r14
0x180011bf4  lea     r15, ??_7?$CArray@V?$CBuffer@I@Dfdll@@I@Dfdll@@6B@; const Dfdll::CArray<Dfdll::CBuffer<uint>,uint>::`vftable'
0x180011bfb  mov     [rbp+57h+var_80], r15
0x180011bff  mov     [rbp+57h+var_60], r14
0x180011c03  mov     [rbp+57h+var_58], r14d
0x180011c07  lea     r12, ??_7?$CBuffer@I@Dfdll@@6B@; const Dfdll::CBuffer<uint>::`vftable'
0x180011c0e  mov     [rbp+57h+var_68], r12
0x180011c12  lea     r8, [rbp+57h+var_80]
0x180011c16  lea     rdx, asc_180021120; "/ :"
0x180011c1d  mov     rcx, rax; unsigned __int16 *
0x180011c20  call    ?ToUINTArray@CConvert@Dfdll@@SAJPEBG0AEAV?$CArray@V?$CBuffer@I@Dfdll@@I@2@@Z; Dfdll::CConvert::ToUINTArray(ushort const *,ushort const *,Dfdll::CArray<Dfdll::CBuffer<uint>,uint> &)
0x180011c25  mov     ebx, eax
0x180011c27  test    eax, eax
0x180011c29  jns     short loc_180011C47
0x180011c2b  mov     [rbp+57h+var_80], r15
0x180011c2f  mov     [rbp+57h+var_68], r12
0x180011c33  mov     rcx, [rbp+57h+var_60]; void *
0x180011c37  test    rcx, rcx
0x180011c3a  jz      short loc_180011C42
0x180011c3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011c41  nop
0x180011c42  jmp     loc_180012115
0x180011c47  cmp     [rbp+57h+var_78], 6
0x180011c4b  jz      short loc_180011C6E
0x180011c4d  mov     ebx, 80070057h
0x180011c52  mov     [rbp+57h+var_80], r15
0x180011c56  mov     [rbp+57h+var_68], r12
0x180011c5a  mov     rcx, [rbp+57h+var_60]; void *
0x180011c5e  test    rcx, rcx
0x180011c61  jz      short loc_180011C69
0x180011c63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011c68  nop
0x180011c69  jmp     loc_180012115
0x180011c6e  mov     edi, r14d
0x180011c71  mov     rbx, r14
0x180011c74  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180011c78  mov     [rbp+57h+var_88], r14
0x180011c7c  mov     rax, [rbp+57h+var_80]
0x180011c80  lea     rdx, [rbp+57h+var_88]
0x180011c84  lea     rcx, [rbp+57h+var_80]
0x180011c88  mov     rax, [rax+28h]
0x180011c8c  call    cs:__guard_dispatch_icall_fptr
0x180011c92  mov     ecx, eax
0x180011c94  test    eax, eax
0x180011c96  js      short loc_180011CC1
0x180011c98  mov     rcx, [rbp+57h+var_88]
0x180011c9c  mov     rax, [rcx]
0x180011c9f  lea     r8, [rbp+57h+FileTime]
0x180011ca3  xor     edx, edx
0x180011ca5  mov     rax, [rax+40h]
0x180011ca9  call    cs:__guard_dispatch_icall_fptr
0x180011caf  mov     ecx, eax
0x180011cb1  test    eax, eax
0x180011cb3  js      short loc_180011CC1
0x180011cb5  mov     rbx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180011cb9  mov     eax, r14d
0x180011cbc  mov     ecx, r14d
0x180011cbf  jmp     short loc_180011CCF
0x180011cc1  mov     eax, r14d
0x180011cc4  test    ecx, ecx
0x180011cc6  cmovs   eax, ecx
0x180011cc9  mov     ecx, eax
0x180011ccb  test    eax, eax
0x180011ccd  js      short loc_180011CD1
0x180011ccf  mov     edi, [rbx]
0x180011cd1  mov     ebx, r14d
0x180011cd4  test    ecx, ecx
0x180011cd6  cmovs   ebx, eax
0x180011cd9  test    ebx, ebx
0x180011cdb  jns     short loc_180011CF9
0x180011cdd  mov     [rbp+57h+var_80], r15
0x180011ce1  mov     [rbp+57h+var_68], r12
0x180011ce5  mov     rcx, [rbp+57h+var_60]; void *
0x180011ce9  test    rcx, rcx
0x180011cec  jz      short loc_180011CF4
0x180011cee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011cf3  nop
0x180011cf4  jmp     loc_180012115
0x180011cf9  mov     [rbp+57h+SystemTime.wYear], di
0x180011cfd  mov     rbx, r14
0x180011d00  mov     [rbp+57h+var_88], r14
0x180011d04  cmp     [rbp+57h+var_78], 1
0x180011d08  ja      short loc_180011D11
0x180011d0a  mov     ebx, 80070057h
0x180011d0f  jmp     short loc_180011D79
0x180011d11  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180011d15  mov     rax, [rbp+57h+var_80]
0x180011d19  lea     rdx, [rbp+57h+FileTime]
0x180011d1d  lea     rcx, [rbp+57h+var_80]
0x180011d21  mov     rax, [rax+28h]
0x180011d25  call    cs:__guard_dispatch_icall_fptr
0x180011d2b  mov     ecx, eax
0x180011d2d  test    eax, eax
0x180011d2f  js      short loc_180011D5D
0x180011d31  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180011d35  mov     rax, [rcx]
0x180011d38  lea     r8, [rbp+57h+var_88]
0x180011d3c  mov     edx, 1
0x180011d41  mov     rax, [rax+40h]
0x180011d45  call    cs:__guard_dispatch_icall_fptr
0x180011d4b  mov     ecx, eax
0x180011d4d  test    eax, eax
0x180011d4f  js      short loc_180011D5D
0x180011d51  mov     rbx, [rbp+57h+var_88]
0x180011d55  mov     eax, r14d
0x180011d58  mov     ecx, r14d
0x180011d5b  jmp     short loc_180011D6B
0x180011d5d  mov     eax, r14d
0x180011d60  test    ecx, ecx
0x180011d62  cmovs   eax, ecx
0x180011d65  mov     ecx, eax
0x180011d67  test    eax, eax
0x180011d69  js      short loc_180011D6D
0x180011d6b  mov     edi, [rbx]
0x180011d6d  mov     ebx, r14d
0x180011d70  test    ecx, ecx
0x180011d72  cmovs   ebx, eax
0x180011d75  test    ebx, ebx
0x180011d77  jns     short loc_180011D95
0x180011d79  mov     [rbp+57h+var_80], r15
0x180011d7d  mov     [rbp+57h+var_68], r12
0x180011d81  mov     rcx, [rbp+57h+var_60]; void *
0x180011d85  test    rcx, rcx
0x180011d88  jz      short loc_180011D90
0x180011d8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011d8f  nop
0x180011d90  jmp     loc_180012115
0x180011d95  mov     [rbp+57h+SystemTime.wMonth], di
0x180011d99  mov     rbx, r14
0x180011d9c  mov     [rbp+57h+var_88], r14
0x180011da0  cmp     [rbp+57h+var_78], 2
0x180011da4  ja      short loc_180011DAD
0x180011da6  mov     ebx, 80070057h
0x180011dab  jmp     short loc_180011E15
0x180011dad  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180011db1  mov     rax, [rbp+57h+var_80]
0x180011db5  lea     rdx, [rbp+57h+FileTime]
0x180011db9  lea     rcx, [rbp+57h+var_80]
0x180011dbd  mov     rax, [rax+28h]
0x180011dc1  call    cs:__guard_dispatch_icall_fptr
0x180011dc7  mov     ecx, eax
0x180011dc9  test    eax, eax
0x180011dcb  js      short loc_180011DF9
0x180011dcd  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180011dd1  mov     rax, [rcx]
0x180011dd4  lea     r8, [rbp+57h+var_88]
0x180011dd8  mov     edx, 2
0x180011ddd  mov     rax, [rax+40h]
0x180011de1  call    cs:__guard_dispatch_icall_fptr
0x180011de7  mov     ecx, eax
0x180011de9  test    eax, eax
0x180011deb  js      short loc_180011DF9
0x180011ded  mov     rbx, [rbp+57h+var_88]
0x180011df1  mov     eax, r14d
0x180011df4  mov     ecx, r14d
0x180011df7  jmp     short loc_180011E07
0x180011df9  mov     eax, r14d
0x180011dfc  test    ecx, ecx
0x180011dfe  cmovs   eax, ecx
0x180011e01  mov     ecx, eax
0x180011e03  test    eax, eax
0x180011e05  js      short loc_180011E09
0x180011e07  mov     edi, [rbx]
0x180011e09  mov     ebx, r14d
0x180011e0c  test    ecx, ecx
0x180011e0e  cmovs   ebx, eax
0x180011e11  test    ebx, ebx
0x180011e13  jns     short loc_180011E31
0x180011e15  mov     [rbp+57h+var_80], r15
0x180011e19  mov     [rbp+57h+var_68], r12
0x180011e1d  mov     rcx, [rbp+57h+var_60]; void *
0x180011e21  test    rcx, rcx
0x180011e24  jz      short loc_180011E2C
0x180011e26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011e2b  nop
0x180011e2c  jmp     loc_180012115
0x180011e31  mov     [rbp+57h+SystemTime.wDay], di
0x180011e35  mov     rbx, r14
0x180011e38  mov     [rbp+57h+var_88], r14
0x180011e3c  cmp     [rbp+57h+var_78], 3
0x180011e40  ja      short loc_180011E49
0x180011e42  mov     ebx, 80070057h
0x180011e47  jmp     short loc_180011EB1
0x180011e49  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180011e4d  mov     rax, [rbp+57h+var_80]
0x180011e51  lea     rdx, [rbp+57h+FileTime]
0x180011e55  lea     rcx, [rbp+57h+var_80]
0x180011e59  mov     rax, [rax+28h]
0x180011e5d  call    cs:__guard_dispatch_icall_fptr
0x180011e63  mov     ecx, eax
0x180011e65  test    eax, eax
0x180011e67  js      short loc_180011E95
0x180011e69  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180011e6d  mov     rax, [rcx]
0x180011e70  lea     r8, [rbp+57h+var_88]
0x180011e74  mov     edx, 3
0x180011e79  mov     rax, [rax+40h]
0x180011e7d  call    cs:__guard_dispatch_icall_fptr
0x180011e83  mov     ecx, eax
0x180011e85  test    eax, eax
0x180011e87  js      short loc_180011E95
0x180011e89  mov     rbx, [rbp+57h+var_88]
0x180011e8d  mov     eax, r14d
0x180011e90  mov     ecx, r14d
0x180011e93  jmp     short loc_180011EA3
0x180011e95  mov     eax, r14d
0x180011e98  test    ecx, ecx
0x180011e9a  cmovs   eax, ecx
0x180011e9d  mov     ecx, eax
0x180011e9f  test    eax, eax
0x180011ea1  js      short loc_180011EA5
0x180011ea3  mov     edi, [rbx]
0x180011ea5  mov     ebx, r14d
0x180011ea8  test    ecx, ecx
0x180011eaa  cmovs   ebx, eax
0x180011ead  test    ebx, ebx
0x180011eaf  jns     short loc_180011ECD
0x180011eb1  mov     [rbp+57h+var_80], r15
0x180011eb5  mov     [rbp+57h+var_68], r12
0x180011eb9  mov     rcx, [rbp+57h+var_60]; void *
0x180011ebd  test    rcx, rcx
0x180011ec0  jz      short loc_180011EC8
0x180011ec2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011ec7  nop
0x180011ec8  jmp     loc_180012115
0x180011ecd  mov     [rbp+57h+SystemTime.wHour], di
0x180011ed1  mov     rbx, r14
0x180011ed4  mov     [rbp+57h+var_88], r14
0x180011ed8  cmp     [rbp+57h+var_78], 4
0x180011edc  ja      short loc_180011EE5
0x180011ede  mov     ebx, 80070057h
0x180011ee3  jmp     short loc_180011F4D
0x180011ee5  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180011ee9  mov     rax, [rbp+57h+var_80]
0x180011eed  lea     rdx, [rbp+57h+FileTime]
0x180011ef1  lea     rcx, [rbp+57h+var_80]
0x180011ef5  mov     rax, [rax+28h]
0x180011ef9  call    cs:__guard_dispatch_icall_fptr
0x180011eff  mov     ecx, eax
0x180011f01  test    eax, eax
0x180011f03  js      short loc_180011F31
0x180011f05  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180011f09  mov     rax, [rcx]
0x180011f0c  lea     r8, [rbp+57h+var_88]
0x180011f10  mov     edx, 4
0x180011f15  mov     rax, [rax+40h]
0x180011f19  call    cs:__guard_dispatch_icall_fptr
0x180011f1f  mov     ecx, eax
0x180011f21  test    eax, eax
0x180011f23  js      short loc_180011F31
0x180011f25  mov     rbx, [rbp+57h+var_88]
0x180011f29  mov     eax, r14d
0x180011f2c  mov     ecx, r14d
0x180011f2f  jmp     short loc_180011F3F
0x180011f31  mov     eax, r14d
0x180011f34  test    ecx, ecx
0x180011f36  cmovs   eax, ecx
0x180011f39  mov     ecx, eax
0x180011f3b  test    eax, eax
0x180011f3d  js      short loc_180011F41
0x180011f3f  mov     edi, [rbx]
0x180011f41  mov     ebx, r14d
0x180011f44  test    ecx, ecx
0x180011f46  cmovs   ebx, eax
0x180011f49  test    ebx, ebx
0x180011f4b  jns     short loc_180011F69
0x180011f4d  mov     [rbp+57h+var_80], r15
0x180011f51  mov     [rbp+57h+var_68], r12
0x180011f55  mov     rcx, [rbp+57h+var_60]; void *
0x180011f59  test    rcx, rcx
0x180011f5c  jz      short loc_180011F64
0x180011f5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011f63  nop
0x180011f64  jmp     loc_180012115
0x180011f69  mov     [rbp+57h+SystemTime.wMinute], di
0x180011f6d  mov     rbx, r14
0x180011f70  mov     [rbp+57h+var_88], r14
0x180011f74  cmp     [rbp+57h+var_78], 5
0x180011f78  ja      short loc_180011F81
0x180011f7a  mov     ebx, 80070057h
  ... truncated ...
```
