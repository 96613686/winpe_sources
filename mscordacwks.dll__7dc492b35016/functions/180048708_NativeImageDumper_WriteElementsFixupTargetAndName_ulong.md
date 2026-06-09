# NativeImageDumper::WriteElementsFixupTargetAndName(ulong)

- ea: `0x180048708`
- end: `0x180048870`
- name: `?WriteElementsFixupTargetAndName@NativeImageDumper@@QEAAXK@Z`
- size: `360`
- prototype: `void __fastcall(NativeImageDumper *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180046cc4`
- `0x180047554`
- `0x18004ec90`
- `0x18004f5a0`
- `0x180054434`

## callees

- `0x18004240c`
- `0x1800476dc`
- `0x180048708`
- `0x18007344c`
- `0x1800777d0`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004884b`
- `KERNEL32!HeapFree` at `0x18004884b`
- `KERNEL32!GetProcessHeap` at `0x180048836`
- `KERNEL32!GetProcessHeap` at `0x180048836`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NativeImageDumper::WriteElementsFixupTargetAndName(NativeImageDumper *this, __int64 a2)
{
  unsigned int v2; // edi
  unsigned __int64 RvaData; // rax
  unsigned __int64 v5; // rax
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+20h] [rbp-69h] BYREF
  __int64 v9; // [rsp+24h] [rbp-65h]
  LPVOID lpMem; // [rsp+30h] [rbp-59h]
  __int16 v11; // [rsp+38h] [rbp-51h] BYREF

  v2 = a2;
  if ( (_DWORD)a2 )
  {
    RvaData = PEDecoder::GetRvaData((char *)this + 64, a2, 0);
    v5 = NativeImageDumper::DataPtrToDisplay(this, RvaData);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
      *((_QWORD *)this + 17),
      "FixupTargetValue",
      v5);
    v9 = 128;
    lpMem = &v11;
    v8 = 2;
    v11 = 0;
    NativeImageDumper::FixupBlobToString(this, v2, (struct SString *)&v8);
    SString::ConvertToUnicode((SString *)&v8);
    (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
      *((_QWORD *)this + 17),
      "FixupTargetName",
      lpMem);
    if ( (v9 & 0x800000000LL) != 0 )
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
  else
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 168LL))(
      *((_QWORD *)this + 17),
      "FixupTargetValue",
      0);
    (*(void (__fastcall **)(_QWORD, const char *, const wchar_t *))(**((_QWORD **)this + 17) + 216LL))(
      *((_QWORD *)this + 17),
      "FixupTargetName",
      L"NULL");
  }
}

```

## disassembly

```asm
0x180048708  mov     [rsp-8+arg_10], rbx
0x18004870d  push    rbp
0x18004870e  push    rsi
0x18004870f  push    rdi
0x180048710  lea     rbp, [rsp-47h]
0x180048715  sub     rsp, 0D0h
0x18004871c  mov     rax, cs:__security_cookie
0x180048723  xor     rax, rsp
0x180048726  mov     [rbp+57h+var_20], rax
0x18004872a  mov     edi, edx
0x18004872c  mov     rbx, rcx
0x18004872f  xor     esi, esi
0x180048731  test    edx, edx
0x180048733  jnz     short loc_180048780
0x180048735  mov     rcx, [rcx+88h]
0x18004873c  mov     rax, [rcx]
0x18004873f  xor     r8d, r8d
0x180048742  lea     rdx, aFixuptargetval; "FixupTargetValue"
0x180048749  mov     rax, [rax+0A8h]
0x180048750  call    cs:__guard_dispatch_icall_fptr
0x180048756  mov     rcx, [rbx+88h]
0x18004875d  mov     rax, [rcx]
0x180048760  lea     r8, aNull_2; "NULL"
0x180048767  lea     rdx, aFixuptargetnam; "FixupTargetName"
0x18004876e  mov     rax, [rax+0D8h]
0x180048775  call    cs:__guard_dispatch_icall_fptr
0x18004877b  jmp     loc_180048851
0x180048780  add     rcx, 40h ; '@'
0x180048784  xor     r8d, r8d
0x180048787  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18004878c  mov     rdx, rax; unsigned __int64
0x18004878f  mov     rcx, rbx; this
0x180048792  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180048797  mov     rcx, [rbx+88h]
0x18004879e  mov     rdx, [rcx]
0x1800487a1  mov     r9, [rdx+0A8h]
0x1800487a8  mov     r8, rax
0x1800487ab  lea     rdx, aFixuptargetval; "FixupTargetValue"
0x1800487b2  mov     rax, r9
0x1800487b5  call    cs:__guard_dispatch_icall_fptr
0x1800487bb  mov     [rbp+57h+var_C0], rsi
0x1800487bf  mov     [rbp+57h+var_C0+4], 80h
0x1800487c7  mov     [rbp+57h+lpMem], rsi
0x1800487cb  lea     rax, [rbp+57h+var_A8]
0x1800487cf  mov     [rbp+57h+lpMem], rax
0x1800487d3  mov     dword ptr [rbp+57h+var_C0], 2
0x1800487da  mov     rax, [rbp+57h+lpMem]
0x1800487de  mov     [rax], si
0x1800487e1  lea     r8, [rbp+57h+var_C0]; struct SString *
0x1800487e5  mov     edx, edi; unsigned int
0x1800487e7  mov     rcx, rbx; this
0x1800487ea  call    ?FixupBlobToString@NativeImageDumper@@QEAAXKAEAVSString@@@Z; NativeImageDumper::FixupBlobToString(ulong,SString &)
0x1800487ef  lea     rcx, [rbp+57h+var_C0]; this
0x1800487f3  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800487f8  mov     rcx, [rbx+88h]
0x1800487ff  mov     rax, [rcx]
0x180048802  mov     r8, [rbp+57h+lpMem]
0x180048806  lea     rdx, aFixuptargetnam; "FixupTargetName"
0x18004880d  mov     rax, [rax+0D8h]
0x180048814  call    cs:__guard_dispatch_icall_fptr
0x18004881a  nop
0x18004881b  test    [rbp+57h+var_B8], 8
0x18004881f  jz      short loc_180048851
0x180048821  mov     rbx, [rbp+57h+lpMem]
0x180048825  test    rbx, rbx
0x180048828  jz      short loc_180048851
0x18004882a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180048831  test    rax, rax
0x180048834  jnz     short loc_180048843
0x180048836  call    cs:__imp_GetProcessHeap
0x18004883c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180048843  mov     r8, rbx; lpMem
0x180048846  xor     edx, edx; dwFlags
0x180048848  mov     rcx, rax; hHeap
0x18004884b  call    cs:__imp_HeapFree
0x180048851  mov     rcx, [rbp+57h+var_20]
0x180048855  xor     rcx, rsp; StackCookie
0x180048858  call    __security_check_cookie
0x18004885d  mov     rbx, [rsp+0E0h+arg_10]
0x180048865  add     rsp, 0D0h
0x18004886c  pop     rdi
0x18004886d  pop     rsi
0x18004886e  pop     rbp
0x18004886f  retn
```
