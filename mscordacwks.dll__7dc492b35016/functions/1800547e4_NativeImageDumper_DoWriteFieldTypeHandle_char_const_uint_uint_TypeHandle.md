# NativeImageDumper::DoWriteFieldTypeHandle(char const *,uint,uint,TypeHandle)

- ea: `0x1800547e4`
- end: `0x18005495b`
- name: `?DoWriteFieldTypeHandle@NativeImageDumper@@QEAAXPEBDIIVTypeHandle@@@Z`
- size: `375`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x1800508a8`
- `0x18005495c`
- `0x1800564c8`
- `0x18005bb2c`
- `0x18005dd88`
- `0x18005e9d0`

## callees

- `0x180040f74`
- `0x18004240c`
- `0x18005106c`
- `0x180054434`
- `0x1800544a8`
- `0x1800547e4`
- `0x18007344c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180054935`
- `KERNEL32!HeapFree` at `0x180054935`
- `KERNEL32!GetProcessHeap` at `0x180054920`
- `KERNEL32!GetProcessHeap` at `0x180054920`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall NativeImageDumper::DoWriteFieldTypeHandle(
        NativeImageDumper *a1,
        const char *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int64 a5)
{
  int result; // eax
  LPVOID v10; // rsi
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  _QWORD *v13; // rcx
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+54h] [rbp-ACh]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  __int16 v20; // [rsp+68h] [rbp-98h] BYREF

  v18 = 128;
  lpMem = &v20;
  v17 = 2;
  v20 = 0;
  result = NativeImageDumper::DoWriteFieldAsFixup(a1, a2, a3, a4, a5);
  if ( !result )
  {
    if ( (a5 & 2) != 0 )
    {
      v16 = a5 & 0xFFFFFFFFFFFFFFFDuLL;
      NativeImageDumper::TypeDescToString(a1);
    }
    else
    {
      v16 = a5;
      NativeImageDumper::MethodTableToString(a1, &v16, (SString *)&v17);
    }
    SString::Append((SString *)&v17, L" (from TypeHandle)");
    SString::ConvertToUnicode((SString *)&v17);
    v10 = lpMem;
    v11 = **((_QWORD **)a1 + 17);
    v12 = NativeImageDumper::DataPtrToDisplay(a1, a5);
    v13 = (_QWORD *)*((_QWORD *)a1 + 17);
    if ( a3 == -1 )
      result = (*(__int64 (__fastcall **)(_QWORD *, const char *, unsigned __int64, LPVOID))(v11 + 176))(
                 v13,
                 a2,
                 v12,
                 v10);
    else
      result = (*(__int64 (__fastcall **)(_QWORD *, const char *, _QWORD, _QWORD, unsigned __int64, LPVOID))(v11 + 376))(
                 v13,
                 a2,
                 a3,
                 a4,
                 v12,
                 v10);
  }
  if ( (v18 & 0x800000000LL) != 0 )
  {
    v14 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      return HeapFree(ProcessHeap, 0, v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800547e4  push    rbp
0x1800547e6  push    rbx
0x1800547e7  push    rsi
0x1800547e8  push    rdi
0x1800547e9  push    r12
0x1800547eb  push    r13
0x1800547ed  push    r14
0x1800547ef  push    r15
0x1800547f1  lea     rbp, [rsp-8]
0x1800547f6  sub     rsp, 108h
0x1800547fd  mov     rax, cs:__security_cookie
0x180054804  xor     rax, rsp
0x180054807  mov     [rbp+40h+var_50], rax
0x18005480b  mov     r13d, r9d
0x18005480e  mov     r15d, r8d
0x180054811  mov     r12, rdx
0x180054814  mov     r14, rcx
0x180054817  xor     edi, edi
0x180054819  mov     [rsp+140h+var_F0], rdi
0x18005481e  mov     [rsp+140h+var_F0+4], 80h
0x180054827  mov     [rsp+140h+lpMem], rdi
0x18005482c  lea     rax, [rsp+140h+var_D8]
0x180054831  mov     [rsp+140h+lpMem], rax
0x180054836  mov     dword ptr [rsp+140h+var_F0], 2
0x18005483e  mov     rax, [rsp+140h+lpMem]
0x180054843  mov     [rax], di
0x180054846  mov     rbx, [rbp+40h+arg_20]
0x18005484a  mov     [rsp+140h+var_120], rbx; unsigned __int64
0x18005484f  call    ?DoWriteFieldAsFixup@NativeImageDumper@@QEAAHPEBDII_K@Z; NativeImageDumper::DoWriteFieldAsFixup(char const *,uint,uint,unsigned __int64)
0x180054854  test    eax, eax
0x180054856  jnz     loc_180054903
0x18005485c  lea     r8, [rsp+140h+var_F0]
0x180054861  lea     rdx, [rsp+140h+var_100]
0x180054866  mov     rcx, r14; this
0x180054869  test    bl, 2
0x18005486c  jz      short loc_180054881
0x18005486e  mov     rax, rbx
0x180054871  and     rax, 0FFFFFFFFFFFFFFFDh
0x180054875  mov     [rsp+140h+var_100], rax
0x18005487a  call    ?TypeDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VTypeDesc@@@@AEAVSString@@@Z; NativeImageDumper::TypeDescToString(__DPtr<TypeDesc>,SString &)
0x18005487f  jmp     short loc_18005488B
0x180054881  mov     [rsp+140h+var_100], rbx
0x180054886  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z; NativeImageDumper::MethodTableToString(__DPtr<MethodTable>,SString &)
0x18005488b  lea     rdx, aFromTypehandle; " (from TypeHandle)"
0x180054892  lea     rcx, [rsp+140h+var_F0]; this
0x180054897  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18005489c  lea     rcx, [rsp+140h+var_F0]; this
0x1800548a1  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800548a6  mov     rsi, [rsp+140h+lpMem]
0x1800548ab  mov     rax, [r14+88h]
0x1800548b2  mov     rdx, rbx; unsigned __int64
0x1800548b5  mov     rcx, r14; this
0x1800548b8  mov     rdi, [rax]
0x1800548bb  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x1800548c0  mov     rdx, r12
0x1800548c3  mov     rcx, [r14+88h]
0x1800548ca  cmp     r15d, 0FFFFFFFFh
0x1800548ce  jnz     short loc_1800548E5
0x1800548d0  mov     r8, rax
0x1800548d3  mov     r9, rsi
0x1800548d6  mov     rax, [rdi+0B0h]
0x1800548dd  call    cs:__guard_dispatch_icall_fptr
0x1800548e3  jmp     short loc_180054903
0x1800548e5  mov     [rsp+140h+var_118], rsi
0x1800548ea  mov     [rsp+140h+var_120], rax
0x1800548ef  mov     r9d, r13d
0x1800548f2  mov     r8d, r15d
0x1800548f5  mov     rax, [rdi+178h]
0x1800548fc  call    cs:__guard_dispatch_icall_fptr
0x180054902  nop
0x180054903  test    [rsp+140h+var_E8], 8
0x180054908  jz      short loc_18005493B
0x18005490a  mov     rbx, [rsp+140h+lpMem]
0x18005490f  test    rbx, rbx
0x180054912  jz      short loc_18005493B
0x180054914  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005491b  test    rax, rax
0x18005491e  jnz     short loc_18005492D
0x180054920  call    cs:__imp_GetProcessHeap
0x180054926  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005492d  mov     r8, rbx; lpMem
0x180054930  xor     edx, edx; dwFlags
0x180054932  mov     rcx, rax; hHeap
0x180054935  call    cs:__imp_HeapFree
0x18005493b  mov     rcx, [rbp+40h+var_50]
0x18005493f  xor     rcx, rsp; StackCookie
0x180054942  call    __security_check_cookie
0x180054947  add     rsp, 108h
0x18005494e  pop     r15
0x180054950  pop     r14
0x180054952  pop     r13
0x180054954  pop     r12
0x180054956  pop     rdi
0x180054957  pop     rsi
0x180054958  pop     rbx
0x180054959  pop     rbp
0x18005495a  retn
```
