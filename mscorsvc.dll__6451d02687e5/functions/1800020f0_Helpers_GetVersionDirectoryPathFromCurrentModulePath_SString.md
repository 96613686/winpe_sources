# Helpers::GetVersionDirectoryPathFromCurrentModulePath(SString &)

- ea: `0x1800020f0`
- end: `0x180002320`
- name: `?GetVersionDirectoryPathFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z`
- size: `560`
- prototype: `void __fastcall(struct SString *this)`
- caller_count: `9`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180001808`
- `0x180005d58`
- `0x1800064a8`
- `0x180006680`
- `0x180013cd0`
- `0x180016eb0`
- `0x18001a9d8`
- `0x180022344`
- `0x18002c124`

## callees

- `0x180001f48`
- `0x180002024`
- `0x1800020f0`
- `0x180030ab8`
- `0x180030d84`
- `0x180032ef4`
- `0x18003303c`
- `0x180034fd4`
- `0x1800351e8`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180002146`
- `KERNEL32!GetModuleFileNameW` at `0x180002146`
- `KERNEL32!GetModuleHandleW` at `0x180002125`
- `KERNEL32!GetModuleHandleW` at `0x180002125`
- `KERNEL32!HeapFree` at `0x1800022e5`
- `KERNEL32!HeapFree` at `0x1800022e5`
- `KERNEL32!GetProcessHeap` at `0x1800022d0`
- `KERNEL32!GetProcessHeap` at `0x1800022d0`

## string_xrefs

- `0x18000211e`: `mscorsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Helpers::GetVersionDirectoryPathFromCurrentModulePath(struct SString *this)
{
  HMODULE ModuleHandleW; // rax
  DWORD ModuleFileNameW; // eax
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  char *v6; // [rsp+20h] [rbp-E0h] BYREF
  BOOL v7; // [rsp+28h] [rbp-D8h]
  LPVOID v8; // [rsp+38h] [rbp-C8h] BYREF
  BOOL v9; // [rsp+40h] [rbp-C0h]
  unsigned int v10; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+54h] [rbp-ACh]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  __int16 v13; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[264]; // [rsp+270h] [rbp+170h] BYREF

  ModuleHandleW = GetModuleHandleW(L"mscorsvc.dll");
  if ( !ModuleHandleW || (ModuleFileNameW = GetModuleFileNameW(ModuleHandleW, Filename, 0x104u)) == 0 )
    ThrowLastError();
  if ( ModuleFileNameW == 260 )
    ThrowHR(-2147418113);
  v11 = 512;
  lpMem = &v13;
  v10 = 2;
  v13 = 0;
  SString::Set((SString *)&v10, Filename);
  if ( (~(HIDWORD(v11) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v10) )
    SString::ConvertToUnicode((SString *)&v10);
  if ( (v11 & 0x1000000000LL) != 0 )
    SBuffer::ReallocateBuffer(&v10, (unsigned int)v11, 1);
  if ( (v11 & 0x200000000LL) != 0
    && ((BYTE4(v11) & 7) != 7 || SString::s_IsANSIMultibyte)
    && !(unsigned int)SString::ScanASCII((SString *)&v10) )
  {
    SString::ConvertToUnicode((SString *)&v10);
  }
  v6 = (char *)lpMem + (int)(((v10 >> ((v11 & 0x100000000LL) == 0)) - 1) << ((v11 & 0x100000000LL) == 0));
  v7 = (v11 & 0x100000000LL) == 0;
  SString::FindBack((SString *)&v10, (struct SString::CIterator *)&v6, L"\\");
  if ( (~(HIDWORD(v11) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v10) )
    SString::ConvertToUnicode((SString *)&v10);
  if ( (v11 & 0x1000000000LL) != 0 )
    SBuffer::ReallocateBuffer(&v10, (unsigned int)v11, 1);
  v8 = lpMem;
  v9 = (v11 & 0x100000000LL) == 0;
  SString::Set(
    this,
    (const struct SString *)&v10,
    (const struct SString::CIterator *)&v8,
    (const struct SString::CIterator *)&v6);
  if ( (v11 & 0x800000000LL) != 0 )
  {
    v4 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v4);
    }
  }
}

```

## disassembly

```asm
0x1800020f0  mov     [rsp-8+arg_8], rbx
0x1800020f5  mov     [rsp-8+arg_10], rdi
0x1800020fa  push    rbp
0x1800020fb  lea     rbp, [rsp-390h]
0x180002103  sub     rsp, 490h
0x18000210a  mov     rax, cs:__security_cookie
0x180002111  xor     rax, rsp
0x180002114  mov     [rbp+390h+var_10], rax
0x18000211b  mov     rbx, rcx
0x18000211e  lea     rcx, ModuleName; "mscorsvc.dll"
0x180002125  call    cs:__imp_GetModuleHandleW
0x18000212b  xor     edi, edi
0x18000212d  test    rax, rax
0x180002130  jz      loc_18000231A
0x180002136  mov     r8d, 104h; nSize
0x18000213c  lea     rdx, [rbp+390h+Filename]; lpFilename
0x180002143  mov     rcx, rax; hModule
0x180002146  call    cs:__imp_GetModuleFileNameW
0x18000214c  test    eax, eax
0x18000214e  jz      loc_18000231A
0x180002154  cmp     eax, 104h
0x180002159  jz      loc_18000230F
0x18000215f  mov     [rsp+490h+var_440], rdi
0x180002164  mov     [rsp+490h+var_440+4], 200h
0x18000216d  mov     [rsp+490h+lpMem], rdi
0x180002172  lea     rax, [rsp+490h+var_428]
0x180002177  mov     [rsp+490h+lpMem], rax
0x18000217c  mov     dword ptr [rsp+490h+var_440], 2
0x180002184  mov     rax, [rsp+490h+lpMem]
0x180002189  mov     [rax], di
0x18000218c  lea     rdx, [rbp+390h+Filename]; unsigned __int16 *
0x180002193  lea     rcx, [rsp+490h+var_440]; this
0x180002198  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18000219d  nop
0x18000219e  mov     eax, [rsp+490h+var_438]
0x1800021a2  shr     eax, 1
0x1800021a4  not     eax
0x1800021a6  test    al, 1
0x1800021a8  jnz     short loc_1800021C2
0x1800021aa  lea     rcx, [rsp+490h+var_440]; this
0x1800021af  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x1800021b4  test    eax, eax
0x1800021b6  jnz     short loc_1800021C2
0x1800021b8  lea     rcx, [rsp+490h+var_440]; this
0x1800021bd  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800021c2  test    byte ptr [rsp+490h+var_438], 10h
0x1800021c7  jz      short loc_1800021DD
0x1800021c9  mov     r8d, 1
0x1800021cf  mov     edx, dword ptr [rsp+490h+var_440+4]
0x1800021d3  lea     rcx, [rsp+490h+var_440]
0x1800021d8  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x1800021dd  mov     eax, [rsp+490h+var_438]
0x1800021e1  test    al, 2
0x1800021e3  jz      short loc_18000220C
0x1800021e5  and     eax, 7
0x1800021e8  cmp     al, 7
0x1800021ea  jnz     short loc_1800021F4
0x1800021ec  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x1800021f2  jz      short loc_18000220C
0x1800021f4  lea     rcx, [rsp+490h+var_440]; this
0x1800021f9  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x1800021fe  test    eax, eax
0x180002200  jnz     short loc_18000220C
0x180002202  lea     rcx, [rsp+490h+var_440]; this
0x180002207  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000220c  mov     ecx, [rsp+490h+var_438]
0x180002210  not     ecx
0x180002212  and     ecx, 1
0x180002215  mov     eax, dword ptr [rsp+490h+var_440]
0x180002219  shr     eax, cl
0x18000221b  dec     eax
0x18000221d  shl     eax, cl
0x18000221f  cdqe
0x180002221  add     rax, [rsp+490h+lpMem]
0x180002226  mov     [rsp+490h+var_470], rax
0x18000222b  mov     [rsp+490h+var_468], ecx
0x18000222f  lea     r8, asc_180049544; "\\"
0x180002236  lea     rdx, [rsp+490h+var_470]; struct SString::CIterator *
0x18000223b  lea     rcx, [rsp+490h+var_440]; this
0x180002240  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@PEBG@Z; SString::FindBack(SString::CIterator &,ushort const *)
0x180002245  mov     eax, [rsp+490h+var_438]
0x180002249  shr     eax, 1
0x18000224b  not     eax
0x18000224d  test    al, 1
0x18000224f  jnz     short loc_180002269
0x180002251  lea     rcx, [rsp+490h+var_440]; this
0x180002256  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18000225b  test    eax, eax
0x18000225d  jnz     short loc_180002269
0x18000225f  lea     rcx, [rsp+490h+var_440]; this
0x180002264  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180002269  test    byte ptr [rsp+490h+var_438], 10h
0x18000226e  jz      short loc_180002284
0x180002270  mov     r8d, 1
0x180002276  mov     edx, dword ptr [rsp+490h+var_440+4]
0x18000227a  lea     rcx, [rsp+490h+var_440]
0x18000227f  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180002284  mov     rax, [rsp+490h+lpMem]
0x180002289  mov     [rsp+490h+var_458], rax
0x18000228e  mov     eax, [rsp+490h+var_438]
0x180002292  not     eax
0x180002294  and     eax, 1
0x180002297  mov     [rsp+490h+var_450], eax
0x18000229b  lea     r9, [rsp+490h+var_470]; struct SString::CIterator *
0x1800022a0  lea     r8, [rsp+490h+var_458]; struct SString::CIterator *
0x1800022a5  lea     rdx, [rsp+490h+var_440]; struct SString *
0x1800022aa  mov     rcx, rbx; this
0x1800022ad  call    ?Set@SString@@QEAAXAEBV1@AEBVCIterator@1@1@Z; SString::Set(SString const &,SString::CIterator const &,SString::CIterator const &)
0x1800022b2  nop
0x1800022b3  test    byte ptr [rsp+490h+var_438], 8
0x1800022b8  jz      short loc_1800022EB
0x1800022ba  mov     rbx, [rsp+490h+lpMem]
0x1800022bf  test    rbx, rbx
0x1800022c2  jz      short loc_1800022EB
0x1800022c4  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800022cb  test    rax, rax
0x1800022ce  jnz     short loc_1800022DD
0x1800022d0  call    cs:__imp_GetProcessHeap
0x1800022d6  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800022dd  mov     r8, rbx; lpMem
0x1800022e0  xor     edx, edx; dwFlags
0x1800022e2  mov     rcx, rax; hHeap
0x1800022e5  call    cs:__imp_HeapFree
0x1800022eb  mov     rcx, [rbp+390h+var_10]
0x1800022f2  xor     rcx, rsp; StackCookie
0x1800022f5  call    __security_check_cookie
0x1800022fa  lea     r11, [rsp+490h+var_s0]
0x180002302  mov     rbx, [r11+18h]
0x180002306  mov     rdi, [r11+20h]
0x18000230a  mov     rsp, r11
0x18000230d  pop     rbp
0x18000230e  retn
0x18000230f  mov     ecx, 8000FFFFh; int
0x180002314  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000231a  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
```
