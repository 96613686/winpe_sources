# NGENService::EventLogWorker(ushort const *,ushort,ulong,ushort const *)

- ea: `0x18002dfa0`
- end: `0x18002e1cd`
- name: `?EventLogWorker@NGENService@@YAXPEBGGK0@Z`
- size: `557`
- prototype: `void(NGENService *__hidden this, const unsigned __int16 *, unsigned __int16, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18002e418`

## callees

- `0x180007d54`
- `0x18002de54`
- `0x18002dfa0`
- `0x180030d84`
- `0x180032654`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002e04a`
- `KERNEL32!LoadLibraryExW` at `0x18002e131`
- `KERNEL32!LoadLibraryExW` at `0x18002e04a`
- `KERNEL32!LoadLibraryExW` at `0x18002e131`
- `KERNEL32!GetProcAddress` at `0x18002e05f`
- `KERNEL32!GetProcAddress` at `0x18002e146`
- `KERNEL32!GetProcAddress` at `0x18002e05f`
- `KERNEL32!GetProcAddress` at `0x18002e146`
- `KERNEL32!HeapFree` at `0x18002e1a4`
- `KERNEL32!HeapFree` at `0x18002e1a4`
- `KERNEL32!GetProcessHeap` at `0x18002e18f`
- `KERNEL32!GetProcessHeap` at `0x18002e18f`

## string_xrefs

- `0x18002e043`: `advapi32.dll`
- `0x18002e12a`: `advapi32.dll`
- `0x18002e085`: `.NET Runtime Optimization Service`
- `0x18002e0b6`: `.NET Runtime Optimization Service (%s) - %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NGENService::EventLogWorker(
        NGENService *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        NGENService *a4)
{
  __int16 v6; // r15
  FARPROC v8; // rax
  HMODULE v9; // rax
  void *v10; // rbx
  __int64 v11; // r8
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  void *v16; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+64h] [rbp-9Ch]
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  __int16 v22; // [rsp+78h] [rbp-88h] BYREF

  v6 = (__int16)a2;
  v20 = 512;
  lpMem = &v22;
  v19 = 2;
  v22 = 0;
  if ( NGENService::g_bProcessNGENService )
  {
    NGENService::LogWorker(a4, a2);
    v8 = (FARPROC)qword_18006FF60;
    if ( qword_18006FF60
      || !bRegisterEventSourceProbed
      && ((v9 = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
        ? (v8 = (FARPROC)qword_18006FF60)
        : (FARPROC)(v8 = GetProcAddress(v9, "RegisterEventSourceW"), qword_18006FF60 = (__int64)v8),
          bRegisterEventSourceProbed = 1,
          v8) )
    {
      v10 = (void *)((__int64 (__fastcall *)(_QWORD, const wchar_t *))v8)(0, L".NET Runtime Optimization Service");
      if ( v10 )
      {
        SString::ConvertToUnicode((SString *)&NGENService::g_sServiceName);
        SString::Printf((SString *)&v19, L".NET Runtime Optimization Service (%s) - %s", ::lpMem, a4);
        SString::ConvertToUnicode((SString *)&v19);
        v18[0] = (unsigned __int16 *)lpMem;
        v18[1] = (unsigned __int16 *)this;
        if ( v6 == 1 )
          CLRReportEvent(v10, 1u, v11, a3, v16, (this != 0) + 1, v17, (const unsigned __int16 **)v18);
        ProcAddress = (FARPROC)qword_18006FF68;
        if ( qword_18006FF68
          || !bDeregisterEventSourceProbed
          && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
            ? (ProcAddress = (FARPROC)qword_18006FF68)
            : (FARPROC)(ProcAddress = GetProcAddress(Library, "DeregisterEventSource"),
                        qword_18006FF68 = (__int64)ProcAddress),
              bDeregisterEventSourceProbed = 1,
              ProcAddress) )
        {
          ((void (__fastcall *)(void *))ProcAddress)(v10);
        }
      }
    }
  }
  if ( (v20 & 0x800000000LL) != 0 )
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
      HeapFree(ProcessHeap, 0, v14);
    }
  }
}

```

## disassembly

```asm
0x18002dfa0  push    rbp
0x18002dfa2  push    rbx
0x18002dfa3  push    rsi
0x18002dfa4  push    rdi
0x18002dfa5  push    r12
0x18002dfa7  push    r13
0x18002dfa9  push    r14
0x18002dfab  push    r15
0x18002dfad  lea     rbp, [rsp-198h]
0x18002dfb5  sub     rsp, 298h
0x18002dfbc  mov     rax, cs:__security_cookie
0x18002dfc3  xor     rax, rsp
0x18002dfc6  mov     [rbp+1D0h+var_50], rax
0x18002dfcd  mov     rsi, r9
0x18002dfd0  mov     r14d, r8d
0x18002dfd3  movzx   r15d, dx
0x18002dfd7  mov     rdi, rcx
0x18002dfda  xor     r12d, r12d
0x18002dfdd  mov     [rsp+2D0h+var_270], r12
0x18002dfe2  mov     [rsp+2D0h+var_270+4], 200h
0x18002dfeb  mov     [rsp+2D0h+lpMem], r12
0x18002dff0  lea     rax, [rsp+2D0h+var_258]
0x18002dff5  mov     [rsp+2D0h+lpMem], rax
0x18002dffa  mov     dword ptr [rsp+2D0h+var_270], 2
0x18002e002  mov     rax, [rsp+2D0h+lpMem]
0x18002e007  mov     [rax], r12w
0x18002e00b  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, r12b
0x18002e012  jz      loc_18002E172
0x18002e018  mov     rcx, r9; this
0x18002e01b  call    ?LogWorker@NGENService@@YAXPEBG@Z
0x18002e020  lea     r13d, [r12+1]
0x18002e025  mov     rax, cs:qword_18006FF60
0x18002e02c  test    rax, rax
0x18002e02f  jnz     short loc_18002E085
0x18002e031  cmp     cs:?bRegisterEventSourceProbed@@3_NA, r12b
0x18002e038  jnz     loc_18002E172
0x18002e03e  xor     r8d, r8d; dwFlags
0x18002e041  xor     edx, edx; hFile
0x18002e043  lea     rcx, aAdvapi32Dll_0
0x18002e04a  call    cs:__imp_LoadLibraryExW
0x18002e050  test    rax, rax
0x18002e053  jz      short loc_18002E06E
0x18002e055  lea     rdx, aRegisterevents
0x18002e05c  mov     rcx, rax; hModule
0x18002e05f  call    cs:__imp_GetProcAddress
0x18002e065  mov     cs:qword_18006FF60, rax
0x18002e06c  jmp     short loc_18002E075
0x18002e06e  mov     rax, cs:qword_18006FF60
0x18002e075  mov     cs:?bRegisterEventSourceProbed@@3_NA, r13b
0x18002e07c  test    rax, rax
0x18002e07f  jz      loc_18002E172
0x18002e085  lea     rdx, aNetRuntimeOpti_0
0x18002e08c  xor     ecx, ecx
0x18002e08e  call    cs:__guard_dispatch_icall_fptr
0x18002e094  mov     rbx, rax
0x18002e097  test    rax, rax
0x18002e09a  jz      loc_18002E172
0x18002e0a0  lea     rcx, ?g_sServiceName@NGENService@@3VSString@@A; this
0x18002e0a7  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18002e0ac  mov     r9, rsi
0x18002e0af  mov     r8, cs:lpMem
0x18002e0b6  lea     rdx, aNetRuntimeOpti_1
0x18002e0bd  lea     rcx, [rsp+2D0h+var_270]; this
0x18002e0c2  call    ?Printf@SString@@QEAAXPEBGZZ
0x18002e0c7  lea     rcx, [rsp+2D0h+var_270]; this
0x18002e0cc  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18002e0d1  mov     rcx, [rsp+2D0h+lpMem]
0x18002e0d6  mov     [rsp+2D0h+var_280], rcx
0x18002e0db  mov     [rsp+2D0h+var_278], rdi
0x18002e0e0  cmp     r15w, r13w
0x18002e0e4  jnz     short loc_18002E110
0x18002e0e6  neg     rdi
0x18002e0e9  sbb     ax, ax
0x18002e0ec  neg     ax
0x18002e0ef  add     ax, r13w
0x18002e0f3  mov     edx, r13d; unsigned __int16
0x18002e0f6  lea     rcx, [rsp+2D0h+var_280]
0x18002e0fb  mov     [rsp+2D0h+var_298], rcx; unsigned __int16 **
0x18002e100  mov     [rsp+2D0h+var_2A8], ax; unsigned __int16
0x18002e105  mov     r9d, r14d; unsigned int
0x18002e108  mov     rcx, rbx; void *
0x18002e10b  call    ?CLRReportEvent@@YAHPEAXGGK0GKPEAPEBG0@Z
0x18002e110  mov     rax, cs:qword_18006FF68
0x18002e117  test    rax, rax
0x18002e11a  jnz     short loc_18002E168
0x18002e11c  cmp     cs:?bDeregisterEventSourceProbed@@3_NA, r12b
0x18002e123  jnz     short loc_18002E172
0x18002e125  xor     r8d, r8d; dwFlags
0x18002e128  xor     edx, edx; hFile
0x18002e12a  lea     rcx, aAdvapi32Dll_0
0x18002e131  call    cs:__imp_LoadLibraryExW
0x18002e137  test    rax, rax
0x18002e13a  jz      short loc_18002E155
0x18002e13c  lea     rdx, aDeregistereven
0x18002e143  mov     rcx, rax; hModule
0x18002e146  call    cs:__imp_GetProcAddress
0x18002e14c  mov     cs:qword_18006FF68, rax
0x18002e153  jmp     short loc_18002E15C
0x18002e155  mov     rax, cs:qword_18006FF68
0x18002e15c  mov     cs:?bDeregisterEventSourceProbed@@3_NA, r13b
0x18002e163  test    rax, rax
0x18002e166  jz      short loc_18002E172
0x18002e168  mov     rcx, rbx
0x18002e16b  call    cs:__guard_dispatch_icall_fptr
0x18002e171  nop
0x18002e172  test    [rsp+2D0h+var_268], 8
0x18002e177  jz      short loc_18002E1AA
0x18002e179  mov     rbx, [rsp+2D0h+lpMem]
0x18002e17e  test    rbx, rbx
0x18002e181  jz      short loc_18002E1AA
0x18002e183  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18002e18a  test    rax, rax
0x18002e18d  jnz     short loc_18002E19C
0x18002e18f  call    cs:__imp_GetProcessHeap
0x18002e195  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18002e19c  mov     r8, rbx; lpMem
0x18002e19f  xor     edx, edx; dwFlags
0x18002e1a1  mov     rcx, rax; hHeap
0x18002e1a4  call    cs:__imp_HeapFree
0x18002e1aa  mov     rcx, [rbp+1D0h+var_50]
0x18002e1b1  xor     rcx, rsp; StackCookie
0x18002e1b4  call    __security_check_cookie
0x18002e1b9  add     rsp, 298h
0x18002e1c0  pop     r15
0x18002e1c2  pop     r14
0x18002e1c4  pop     r13
0x18002e1c6  pop     r12
0x18002e1c8  pop     rdi
0x18002e1c9  pop     rsi
0x18002e1ca  pop     rbx
0x18002e1cb  pop     rbp
0x18002e1cc  retn
```
