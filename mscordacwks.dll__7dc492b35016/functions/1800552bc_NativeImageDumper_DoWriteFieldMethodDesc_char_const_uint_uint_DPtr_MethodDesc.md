# NativeImageDumper::DoWriteFieldMethodDesc(char const *,uint,uint,__DPtr<MethodDesc>)

- ea: `0x1800552bc`
- end: `0x18005541c`
- name: `?DoWriteFieldMethodDesc@NativeImageDumper@@QEAAXPEBDIIV?$__DPtr@VMethodDesc@@@@@Z`
- size: `352`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, __int64)`
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x18004c9ec`
- `0x18004e3b8`
- `0x180050678`
- `0x180050b3c`
- `0x180050ca8`
- `0x180054a1c`
- `0x1800564c8`
- `0x1800592c8`
- `0x1800599a4`
- `0x18005bb2c`

## callees

- `0x18004240c`
- `0x180054434`
- `0x1800552bc`
- `0x18005541c`
- `0x18007344c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800553f6`
- `KERNEL32!HeapFree` at `0x1800553f6`
- `KERNEL32!GetProcessHeap` at `0x1800553e1`
- `KERNEL32!GetProcessHeap` at `0x1800553e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall NativeImageDumper::DoWriteFieldMethodDesc(
        NativeImageDumper *this,
        const char *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int64 *a5)
{
  int result; // eax
  LPVOID v10; // rbx
  unsigned __int64 v11; // rax
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+54h] [rbp-ACh]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  __int16 v17; // [rsp+68h] [rbp-98h] BYREF

  if ( !*a5 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 320LL))(*((_QWORD *)this + 17));
  result = NativeImageDumper::DoWriteFieldAsFixup(this, a2, a3, a4, *a5);
  if ( !result )
  {
    v15 = 128;
    lpMem = &v17;
    v14 = 2;
    v17 = 0;
    NativeImageDumper::MethodDescToString(this);
    SString::ConvertToUnicode((SString *)&v14);
    v10 = lpMem;
    v11 = NativeImageDumper::DataPtrToDisplay(this, *a5);
    result = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD, unsigned __int64, LPVOID))(**((_QWORD **)this + 17) + 376LL))(
               *((_QWORD *)this + 17),
               a2,
               a3,
               a4,
               v11,
               v10);
    if ( (v15 & 0x800000000LL) != 0 )
    {
      v12 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        return HeapFree(ProcessHeap, 0, v12);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800552bc  push    rbp
0x1800552be  push    rbx
0x1800552bf  push    rsi
0x1800552c0  push    rdi
0x1800552c1  push    r12
0x1800552c3  push    r13
0x1800552c5  push    r14
0x1800552c7  push    r15
0x1800552c9  lea     rbp, [rsp-8]
0x1800552ce  sub     rsp, 108h
0x1800552d5  mov     rax, cs:__security_cookie
0x1800552dc  xor     rax, rsp
0x1800552df  mov     [rbp+40h+var_50], rax
0x1800552e3  mov     r15d, r9d
0x1800552e6  mov     r14d, r8d
0x1800552e9  mov     rsi, rdx
0x1800552ec  mov     rdi, rcx
0x1800552ef  mov     r12, [rbp+40h+arg_20]
0x1800552f3  mov     rax, [r12]
0x1800552f7  xor     r13d, r13d
0x1800552fa  test    rax, rax
0x1800552fd  jnz     short loc_180055320
0x1800552ff  mov     rcx, [rcx+88h]
0x180055306  mov     rax, [rcx]
0x180055309  mov     [rsp+140h+var_120], r13
0x18005530e  mov     rax, [rax+140h]
0x180055315  call    cs:__guard_dispatch_icall_fptr
0x18005531b  jmp     loc_1800553FC
0x180055320  mov     [rsp+140h+var_120], rax; unsigned __int64
0x180055325  call    ?DoWriteFieldAsFixup@NativeImageDumper@@QEAAHPEBDII_K@Z; NativeImageDumper::DoWriteFieldAsFixup(char const *,uint,uint,unsigned __int64)
0x18005532a  test    eax, eax
0x18005532c  jnz     loc_1800553FC
0x180055332  mov     [rsp+140h+var_F0], r13
0x180055337  mov     [rsp+140h+var_F0+4], 80h
0x180055340  mov     [rsp+140h+lpMem], r13
0x180055345  lea     rax, [rsp+140h+var_D8]
0x18005534a  mov     [rsp+140h+lpMem], rax
0x18005534f  mov     dword ptr [rsp+140h+var_F0], 2
0x180055357  mov     rax, [rsp+140h+lpMem]
0x18005535c  mov     [rax], r13w
0x180055360  mov     rax, [r12]
0x180055364  mov     [rsp+140h+var_100], rax
0x180055369  lea     r8, [rsp+140h+var_F0]
0x18005536e  lea     rdx, [rsp+140h+var_100]
0x180055373  mov     rcx, rdi; this
0x180055376  call    ?MethodDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@AEAVSString@@@Z; NativeImageDumper::MethodDescToString(__DPtr<MethodDesc>,SString &)
0x18005537b  lea     rcx, [rsp+140h+var_F0]; this
0x180055380  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180055385  mov     rbx, [rsp+140h+lpMem]
0x18005538a  mov     rdx, [r12]; unsigned __int64
0x18005538e  mov     rcx, rdi; this
0x180055391  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180055396  mov     rcx, [rdi+88h]
0x18005539d  mov     rdx, [rcx]
0x1800553a0  mov     r10, [rdx+178h]
0x1800553a7  mov     [rsp+140h+var_118], rbx
0x1800553ac  mov     [rsp+140h+var_120], rax
0x1800553b1  mov     r9d, r15d
0x1800553b4  mov     r8d, r14d
0x1800553b7  mov     rdx, rsi
0x1800553ba  mov     rax, r10
0x1800553bd  call    cs:__guard_dispatch_icall_fptr
0x1800553c3  nop
0x1800553c4  test    [rsp+140h+var_E8], 8
0x1800553c9  jz      short loc_1800553FC
0x1800553cb  mov     rbx, [rsp+140h+lpMem]
0x1800553d0  test    rbx, rbx
0x1800553d3  jz      short loc_1800553FC
0x1800553d5  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800553dc  test    rax, rax
0x1800553df  jnz     short loc_1800553EE
0x1800553e1  call    cs:__imp_GetProcessHeap
0x1800553e7  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800553ee  mov     r8, rbx; lpMem
0x1800553f1  xor     edx, edx; dwFlags
0x1800553f3  mov     rcx, rax; hHeap
0x1800553f6  call    cs:__imp_HeapFree
0x1800553fc  mov     rcx, [rbp+40h+var_50]
0x180055400  xor     rcx, rsp; StackCookie
0x180055403  call    __security_check_cookie
0x180055408  add     rsp, 108h
0x18005540f  pop     r15
0x180055411  pop     r14
0x180055413  pop     r13
0x180055415  pop     r12
0x180055417  pop     rdi
0x180055418  pop     rsi
0x180055419  pop     rbx
0x18005541a  pop     rbp
0x18005541b  retn
```
