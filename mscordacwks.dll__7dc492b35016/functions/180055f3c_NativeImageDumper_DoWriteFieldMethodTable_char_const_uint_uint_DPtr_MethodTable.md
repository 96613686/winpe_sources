# NativeImageDumper::DoWriteFieldMethodTable(char const *,uint,uint,__DPtr<MethodTable>)

- ea: `0x180055f3c`
- end: `0x180056099`
- name: `?DoWriteFieldMethodTable@NativeImageDumper@@QEAAXPEBDIIV?$__DPtr@VMethodTable@@@@@Z`
- size: `349`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, __int64)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x18004e3b8`
- `0x180050298`
- `0x1800504bc`
- `0x180054a1c`
- `0x18005609c`
- `0x1800564c8`
- `0x18005bb2c`
- `0x18005dd88`

## callees

- `0x18004240c`
- `0x18005106c`
- `0x180054434`
- `0x180055f3c`
- `0x18007344c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180056075`
- `KERNEL32!HeapFree` at `0x180056075`
- `KERNEL32!GetProcessHeap` at `0x180056060`
- `KERNEL32!GetProcessHeap` at `0x180056060`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall NativeImageDumper::DoWriteFieldMethodTable(
        NativeImageDumper *this,
        const char *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  unsigned int v5; // r14d
  int result; // eax
  LPVOID v9; // rbx
  unsigned __int64 v10; // rax
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v13; // [rsp+40h] [rbp-A1h] BYREF
  int v14; // [rsp+50h] [rbp-91h] BYREF
  __int64 v15; // [rsp+54h] [rbp-8Dh]
  LPVOID lpMem; // [rsp+60h] [rbp-81h]
  __int16 v17; // [rsp+68h] [rbp-79h] BYREF

  v5 = a3;
  if ( !*a5 )
    return (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
             *((_QWORD *)this + 17),
             a2,
             a3,
             8,
             0);
  result = NativeImageDumper::DoWriteFieldAsFixup(this, a2, a3, 8u, *a5);
  if ( !result )
  {
    v15 = 128;
    lpMem = &v17;
    v14 = 2;
    v17 = 0;
    v13 = *a5;
    NativeImageDumper::MethodTableToString(this, &v13, (SString *)&v14);
    SString::ConvertToUnicode((SString *)&v14);
    v9 = lpMem;
    v10 = NativeImageDumper::DataPtrToDisplay(this, *a5);
    result = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64, LPVOID))(**((_QWORD **)this + 17) + 376LL))(
               *((_QWORD *)this + 17),
               a2,
               v5,
               8,
               v10,
               v9);
    if ( (v15 & 0x800000000LL) != 0 )
    {
      v11 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        return HeapFree(ProcessHeap, 0, v11);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055f3c  push    rbp
0x180055f3e  push    rbx
0x180055f3f  push    rsi
0x180055f40  push    rdi
0x180055f41  push    r12
0x180055f43  push    r14
0x180055f45  push    r15
0x180055f47  lea     rbp, [rsp-1Fh]
0x180055f4c  sub     rsp, 100h
0x180055f53  mov     rax, cs:__security_cookie
0x180055f5a  xor     rax, rsp
0x180055f5d  mov     [rbp+4Fh+var_40], rax
0x180055f61  mov     r14d, r8d
0x180055f64  mov     rsi, rdx
0x180055f67  mov     rdi, rcx
0x180055f6a  mov     r15, [rbp+4Fh+arg_20]
0x180055f6e  mov     rax, [r15]
0x180055f71  xor     r12d, r12d
0x180055f74  lea     r9d, [r12+8]; unsigned int
0x180055f79  test    rax, rax
0x180055f7c  jnz     short loc_180055F9F
0x180055f7e  mov     rcx, [rcx+88h]
0x180055f85  mov     rax, [rcx]
0x180055f88  mov     [rsp+130h+var_110], r12
0x180055f8d  mov     rax, [rax+140h]
0x180055f94  call    cs:__guard_dispatch_icall_fptr
0x180055f9a  jmp     loc_18005607B
0x180055f9f  mov     [rsp+130h+var_110], rax; unsigned __int64
0x180055fa4  call    ?DoWriteFieldAsFixup@NativeImageDumper@@QEAAHPEBDII_K@Z; NativeImageDumper::DoWriteFieldAsFixup(char const *,uint,uint,unsigned __int64)
0x180055fa9  test    eax, eax
0x180055fab  jnz     loc_18005607B
0x180055fb1  mov     [rsp+130h+var_E0], r12
0x180055fb6  mov     [rsp+130h+var_E0+4], 80h
0x180055fbf  mov     [rsp+130h+lpMem], r12
0x180055fc4  lea     rax, [rbp+4Fh+var_C8]
0x180055fc8  mov     [rsp+130h+lpMem], rax
0x180055fcd  mov     dword ptr [rsp+130h+var_E0], 2
0x180055fd5  mov     rax, [rsp+130h+lpMem]
0x180055fda  mov     [rax], r12w
0x180055fde  mov     rax, [r15]
0x180055fe1  mov     [rsp+130h+var_F0], rax
0x180055fe6  lea     r8, [rsp+130h+var_E0]
0x180055feb  lea     rdx, [rsp+130h+var_F0]
0x180055ff0  mov     rcx, rdi; this
0x180055ff3  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z; NativeImageDumper::MethodTableToString(__DPtr<MethodTable>,SString &)
0x180055ff8  lea     rcx, [rsp+130h+var_E0]; this
0x180055ffd  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180056002  mov     rbx, [rsp+130h+lpMem]
0x180056007  mov     rdx, [r15]; unsigned __int64
0x18005600a  mov     rcx, rdi; this
0x18005600d  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180056012  mov     rcx, [rdi+88h]
0x180056019  mov     rdx, [rcx]
0x18005601c  mov     r10, [rdx+178h]
0x180056023  mov     [rsp+130h+var_108], rbx
0x180056028  mov     [rsp+130h+var_110], rax
0x18005602d  mov     r9d, 8
0x180056033  mov     r8d, r14d
0x180056036  mov     rdx, rsi
0x180056039  mov     rax, r10
0x18005603c  call    cs:__guard_dispatch_icall_fptr
0x180056042  nop
0x180056043  test    [rsp+130h+var_D8], 8
0x180056048  jz      short loc_18005607B
0x18005604a  mov     rbx, [rsp+130h+lpMem]
0x18005604f  test    rbx, rbx
0x180056052  jz      short loc_18005607B
0x180056054  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005605b  test    rax, rax
0x18005605e  jnz     short loc_18005606D
0x180056060  call    cs:__imp_GetProcessHeap
0x180056066  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005606d  mov     r8, rbx; lpMem
0x180056070  xor     edx, edx; dwFlags
0x180056072  mov     rcx, rax; hHeap
0x180056075  call    cs:__imp_HeapFree
0x18005607b  mov     rcx, [rbp+4Fh+var_40]
0x18005607f  xor     rcx, rsp; StackCookie
0x180056082  call    __security_check_cookie
0x180056087  add     rsp, 100h
0x18005608e  pop     r15
0x180056090  pop     r14
0x180056092  pop     r12
0x180056094  pop     rdi
0x180056095  pop     rsi
0x180056096  pop     rbx
0x180056097  pop     rbp
0x180056098  retn
```
