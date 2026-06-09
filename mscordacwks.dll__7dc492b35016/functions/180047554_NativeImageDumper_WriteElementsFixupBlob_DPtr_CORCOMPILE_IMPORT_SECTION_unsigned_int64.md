# NativeImageDumper::WriteElementsFixupBlob(__DPtr<CORCOMPILE_IMPORT_SECTION>,unsigned __int64)

- ea: `0x180047554`
- end: `0x1800476d9`
- name: `?WriteElementsFixupBlob@NativeImageDumper@@QEAAXV?$__DPtr@UCORCOMPILE_IMPORT_SECTION@@@@_K@Z`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180046cc4`
- `0x18004c7f0`

## callees

- `0x1800210f0`
- `0x180047554`
- `0x180048708`
- `0x18005106c`
- `0x1800544a8`
- `0x18005541c`
- `0x18007344c`
- `0x180076604`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180047699`
- `KERNEL32!HeapFree` at `0x180047699`
- `KERNEL32!GetProcessHeap` at `0x180047684`
- `KERNEL32!GetProcessHeap` at `0x180047684`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NativeImageDumper::WriteElementsFixupBlob(
        NativeImageDumper *this,
        unsigned __int64 *a2,
        unsigned __int64 a3)
{
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v8; // [rsp+20h] [rbp-89h] BYREF
  int v9; // [rsp+30h] [rbp-79h] BYREF
  __int64 v10; // [rsp+34h] [rbp-75h]
  LPVOID lpMem; // [rsp+40h] [rbp-69h]
  __int16 v12; // [rsp+48h] [rbp-61h] BYREF

  if ( !*a2 || (a3 & 0x80000001) == 0x80000001 )
  {
    NativeImageDumper::WriteElementsFixupTargetAndName(this, (a3 >> 1) & 0x3FFFFFFF);
  }
  else
  {
    v10 = 128;
    lpMem = &v12;
    v9 = 2;
    v12 = 0;
    if ( *((_BYTE *)DacInstantiateTypeByAddressHelper(*a2, 0x14u, 1, 1) + 10) == 4 )
    {
      if ( (a3 & 2) != 0 )
      {
        v8 = a3 & 0xFFFFFFFFFFFFFFFDuLL;
        NativeImageDumper::TypeDescToString(this);
      }
      else
      {
        v8 = a3;
        NativeImageDumper::MethodTableToString(this, &v8, (SString *)&v9);
      }
    }
    else
    {
      if ( *((_BYTE *)DacInstantiateTypeByAddressHelper(*a2, 0x14u, 1, 1) + 10) != 5 )
        ThrowHR(-2147467259);
      v8 = a3;
      NativeImageDumper::MethodDescToString(this);
    }
    SString::ConvertToUnicode((SString *)&v9);
    (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
      *((_QWORD *)this + 17),
      "FixupTargetName",
      lpMem);
    if ( (v10 & 0x800000000LL) != 0 )
    {
      v6 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v6);
      }
    }
  }
}

```

## disassembly

```asm
0x180047554  push    rbp
0x180047556  push    rbx
0x180047557  push    rsi
0x180047558  push    rdi
0x180047559  push    r14
0x18004755b  lea     rbp, [rsp-37h]
0x180047560  sub     rsp, 0E0h
0x180047567  mov     rax, cs:__security_cookie
0x18004756e  xor     rax, rsp
0x180047571  mov     [rbp+57h+var_30], rax
0x180047575  mov     rbx, r8
0x180047578  mov     rsi, rdx
0x18004757b  mov     rdi, rcx
0x18004757e  xor     r14d, r14d
0x180047581  cmp     [rdx], r14
0x180047584  jz      loc_1800476A1
0x18004758a  mov     rax, rbx
0x18004758d  mov     ecx, 80000001h
0x180047592  and     rax, rcx
0x180047595  cmp     rax, rcx
0x180047598  jz      loc_1800476A1
0x18004759e  mov     [rbp+57h+var_D0], r14
0x1800475a2  mov     [rbp+57h+var_D0+4], 80h
0x1800475aa  mov     [rbp+57h+lpMem], r14
0x1800475ae  lea     rax, [rbp+57h+var_B8]
0x1800475b2  mov     [rbp+57h+lpMem], rax
0x1800475b6  mov     dword ptr [rbp+57h+var_D0], 2
0x1800475bd  mov     rax, [rbp+57h+lpMem]
0x1800475c1  mov     [rax], r14w
0x1800475c5  mov     r9b, 1; bool
0x1800475c8  mov     r8b, r9b; bool
0x1800475cb  lea     edx, [r14+14h]; unsigned int
0x1800475cf  mov     rcx, [rsi]; unsigned __int64
0x1800475d2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800475d7  cmp     byte ptr [rax+0Ah], 4
0x1800475db  jnz     short loc_18004760A
0x1800475dd  lea     r8, [rbp+57h+var_D0]
0x1800475e1  lea     rdx, [rsp+100h+var_E0]
0x1800475e6  mov     rcx, rdi; this
0x1800475e9  test    bl, 2
0x1800475ec  jz      short loc_1800475FE
0x1800475ee  and     rbx, 0FFFFFFFFFFFFFFFDh
0x1800475f2  mov     [rsp+100h+var_E0], rbx
0x1800475f7  call    ?TypeDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VTypeDesc@@@@AEAVSString@@@Z; NativeImageDumper::TypeDescToString(__DPtr<TypeDesc>,SString &)
0x1800475fc  jmp     short loc_18004763D
0x1800475fe  mov     [rsp+100h+var_E0], rbx
0x180047603  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z; NativeImageDumper::MethodTableToString(__DPtr<MethodTable>,SString &)
0x180047608  jmp     short loc_18004763D
0x18004760a  mov     r9b, 1; bool
0x18004760d  mov     r8b, r9b; bool
0x180047610  mov     edx, 14h; unsigned int
0x180047615  mov     rcx, [rsi]; unsigned __int64
0x180047618  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004761d  cmp     byte ptr [rax+0Ah], 5
0x180047621  jnz     loc_1800476CE
0x180047627  mov     [rsp+100h+var_E0], rbx
0x18004762c  lea     r8, [rbp+57h+var_D0]
0x180047630  lea     rdx, [rsp+100h+var_E0]
0x180047635  mov     rcx, rdi; this
0x180047638  call    ?MethodDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@AEAVSString@@@Z; NativeImageDumper::MethodDescToString(__DPtr<MethodDesc>,SString &)
0x18004763d  lea     rcx, [rbp+57h+var_D0]; this
0x180047641  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180047646  mov     rcx, [rdi+88h]
0x18004764d  mov     rax, [rcx]
0x180047650  mov     r8, [rbp+57h+lpMem]
0x180047654  lea     rdx, aFixuptargetnam; "FixupTargetName"
0x18004765b  mov     rax, [rax+0D8h]
0x180047662  call    cs:__guard_dispatch_icall_fptr
0x180047668  nop
0x180047669  test    [rbp+57h+var_C8], 8
0x18004766d  jz      short loc_1800476B4
0x18004766f  mov     rbx, [rbp+57h+lpMem]
0x180047673  test    rbx, rbx
0x180047676  jz      short loc_1800476B4
0x180047678  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18004767f  test    rax, rax
0x180047682  jnz     short loc_180047691
0x180047684  call    cs:__imp_GetProcessHeap
0x18004768a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180047691  mov     r8, rbx; lpMem
0x180047694  xor     edx, edx; dwFlags
0x180047696  mov     rcx, rax; hHeap
0x180047699  call    cs:__imp_HeapFree
0x18004769f  jmp     short loc_1800476B4
0x1800476a1  shr     rbx, 1
0x1800476a4  and     ebx, 3FFFFFFFh
0x1800476aa  mov     edx, ebx; unsigned int
0x1800476ac  mov     rcx, rdi; this
0x1800476af  call    ?WriteElementsFixupTargetAndName@NativeImageDumper@@QEAAXK@Z; NativeImageDumper::WriteElementsFixupTargetAndName(ulong)
0x1800476b4  mov     rcx, [rbp+57h+var_30]
0x1800476b8  xor     rcx, rsp; StackCookie
0x1800476bb  call    __security_check_cookie
0x1800476c0  add     rsp, 0E0h
0x1800476c7  pop     r14
0x1800476c9  pop     rdi
0x1800476ca  pop     rsi
0x1800476cb  pop     rbx
0x1800476cc  pop     rbp
0x1800476cd  retn
0x1800476ce  mov     ecx, 80004005h; int
0x1800476d3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
