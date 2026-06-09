# NGENService::IsLatestServiceVersion(void)

- ea: `0x18001a25c`
- end: `0x18001a3a0`
- name: `?IsLatestServiceVersion@NGENService@@YA_NXZ`
- size: `324`
- prototype: `bool __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18001b340`

## callees

- `0x180006680`
- `0x18001a25c`
- `0x180030d84`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001a2ef`
- `KERNEL32!LoadLibraryExW` at `0x18001a2ef`
- `KERNEL32!GetProcAddress` at `0x18001a304`
- `KERNEL32!GetProcAddress` at `0x18001a304`
- `KERNEL32!HeapFree` at `0x18001a370`
- `KERNEL32!HeapFree` at `0x18001a370`
- `KERNEL32!GetProcessHeap` at `0x18001a35b`
- `KERNEL32!GetProcessHeap` at `0x18001a35b`

## string_xrefs

- `0x18001a2e8`: `mscoree.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall NGENService::IsLatestServiceVersion(NGENService *this)
{
  LPVOID v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  bool v4; // bl
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD v8[4]; // [rsp+28h] [rbp-E0h] BYREF
  int v9; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+3Ch] [rbp-CCh]
  LPVOID lpMem; // [rsp+48h] [rbp-C0h]
  __int16 v12; // [rsp+50h] [rbp-B8h] BYREF

  v10 = 512;
  lpMem = &v12;
  v9 = 2;
  v12 = 0;
  Helpers::GetVersionDirectoryFromCurrentModulePath((struct SString *)&v9);
  v8[0] = 0;
  SString::ConvertToUnicode((SString *)&v9);
  v1 = lpMem;
  ProcAddress = (FARPROC)qword_180070870;
  v4 = (!qword_180070870
     && ((Library = LoadLibraryExW(L"mscoree.dll", 0, 0)) == 0
       ? (ProcAddress = (FARPROC)qword_180070870)
       : (FARPROC)(ProcAddress = GetProcAddress(Library, "CorIsLatestSvc"), qword_180070870 = (__int64)ProcAddress),
         !ProcAddress)
     || ((int (__fastcall *)(LPVOID, _DWORD *))ProcAddress)(v1, v8) >= 0)
    && v8[0] == 1;
  if ( (v10 & 0x800000000LL) != 0 )
  {
    v5 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v5);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001a25c  mov     rax, rsp
0x18001a25f  mov     [rax+8], rbx
0x18001a263  mov     [rax+10h], rsi
0x18001a267  mov     [rax+18h], rdi
0x18001a26b  push    rbp
0x18001a26c  lea     rbp, [rax-168h]
0x18001a273  sub     rsp, 260h
0x18001a27a  mov     rax, cs:__security_cookie
0x18001a281  xor     rax, rsp
0x18001a284  mov     [rbp+160h+var_10], rax
0x18001a28b  xor     esi, esi
0x18001a28d  mov     qword ptr [rsp+260h+var_230], rsi
0x18001a292  mov     qword ptr [rsp+34h], 200h
0x18001a29b  mov     [rsp+260h+lpMem], rsi
0x18001a2a0  lea     rax, [rsp+260h+var_218]
0x18001a2a5  mov     [rsp+260h+lpMem], rax
0x18001a2aa  mov     [rsp+260h+var_230], 2
0x18001a2b2  mov     rax, [rsp+260h+lpMem]
0x18001a2b7  mov     [rax], si
0x18001a2ba  lea     rcx, [rsp+260h+var_230]; this
0x18001a2bf  call    ?GetVersionDirectoryFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryFromCurrentModulePath(SString &)
0x18001a2c4  mov     [rsp+260h+var_240], esi
0x18001a2c8  lea     rcx, [rsp+260h+var_230]; this
0x18001a2cd  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001a2d2  mov     rbx, [rsp+260h+lpMem]
0x18001a2d7  mov     rax, cs:qword_180070870
0x18001a2de  test    rax, rax
0x18001a2e1  jnz     short loc_18001A31F
0x18001a2e3  xor     r8d, r8d; dwFlags
0x18001a2e6  xor     edx, edx; hFile
0x18001a2e8  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x18001a2ef  call    cs:__imp_LoadLibraryExW
0x18001a2f5  test    rax, rax
0x18001a2f8  jz      short loc_18001A313
0x18001a2fa  lea     rdx, aCorislatestsvc; "CorIsLatestSvc"
0x18001a301  mov     rcx, rax; hModule
0x18001a304  call    cs:__imp_GetProcAddress
0x18001a30a  mov     cs:qword_180070870, rax
0x18001a311  jmp     short loc_18001A31A
0x18001a313  mov     rax, cs:qword_180070870
0x18001a31a  test    rax, rax
0x18001a31d  jz      short loc_18001A336
0x18001a31f  lea     rdx, [rsp+260h+var_240]
0x18001a324  mov     rcx, rbx
0x18001a327  call    cs:__guard_dispatch_icall_fptr
0x18001a32d  test    eax, eax
0x18001a32f  jns     short loc_18001A336
0x18001a331  mov     bl, sil
0x18001a334  jmp     short loc_18001A33E
0x18001a336  cmp     [rsp+260h+var_240], 1
0x18001a33b  setz    bl
0x18001a33e  test    byte ptr [rsp+260h+var_228], 8
0x18001a343  jz      short loc_18001A376
0x18001a345  mov     rdi, [rsp+260h+lpMem]
0x18001a34a  test    rdi, rdi
0x18001a34d  jz      short loc_18001A376
0x18001a34f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a356  test    rax, rax
0x18001a359  jnz     short loc_18001A368
0x18001a35b  call    cs:__imp_GetProcessHeap
0x18001a361  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a368  mov     r8, rdi; lpMem
0x18001a36b  xor     edx, edx; dwFlags
0x18001a36d  mov     rcx, rax; hHeap
0x18001a370  call    cs:__imp_HeapFree
0x18001a376  mov     al, bl
0x18001a378  mov     rcx, [rbp+160h+var_10]
0x18001a37f  xor     rcx, rsp; StackCookie
0x18001a382  call    __security_check_cookie
0x18001a387  lea     r11, [rsp+260h+var_s0]
0x18001a38f  mov     rbx, [r11+10h]
0x18001a393  mov     rsi, [r11+18h]
0x18001a397  mov     rdi, [r11+20h]
0x18001a39b  mov     rsp, r11
0x18001a39e  pop     rbp
0x18001a39f  retn
```
