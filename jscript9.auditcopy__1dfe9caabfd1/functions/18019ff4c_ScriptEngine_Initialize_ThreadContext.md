# ScriptEngine::Initialize(ThreadContext *)

- ea: `0x18019ff4c`
- end: `0x1801a0160`
- name: `?Initialize@ScriptEngine@@QEAAXPEAVThreadContext@@@Z`
- size: `532`
- prototype: `void __fastcall(ScriptEngine *__hidden this, struct ThreadContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18020b358`
- `0x180220eac`

## callees

- `0x18002e2a8`
- `0x18012dca4`
- `0x1801312b0`
- `0x180190d0c`
- `0x18019ff4c`
- `0x180220a50`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18019ffb1`
- `KERNEL32!LoadLibraryExW` at `0x18019ffb1`
- `KERNEL32!InitializeCriticalSection` at `0x1801a0034`
- `KERNEL32!InitializeCriticalSection` at `0x1801a0034`
- `KERNEL32!GetProcAddress` at `0x18019ffd3`
- `KERNEL32!GetProcAddress` at `0x18019fff0`
- `KERNEL32!GetProcAddress` at `0x18019ffd3`
- `KERNEL32!GetProcAddress` at `0x18019fff0`

## string_xrefs

- `0x18019ffa4`: `amsi.dll`
- `0x18019ffc9`: `AmsiInitialize`
- `0x18019ffe6`: `AmsiScanString`

## pseudocode

```c
void __fastcall ScriptEngine::Initialize(ScriptEngine *this, struct ThreadContext *a2)
{
  unsigned int v3; // ebx
  int BrowserProcess; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  char *(__fastcall *v15)(ArenaAllocator *, unsigned __int64 *); // [rsp+20h] [rbp-28h] BYREF
  int v16; // [rsp+28h] [rbp-20h]
  int v17; // [rsp+2Ch] [rbp-1Ch]

  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 231) = 4;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck((__int64)`wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl'::`2'::impl);
  v3 = ScriptEngine::GetScriptingHostProcess() - 1;
  BrowserProcess = ScriptEngine::GetBrowserProcess();
  if ( v3 <= 1 || (unsigned int)(BrowserProcess - 24) <= 1 )
  {
    Library = LoadLibraryExW(L"amsi.dll", 0, 0x800u);
    *((_QWORD *)this + 126) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "AmsiInitialize");
      v7 = GetProcAddress(*((HMODULE *)this + 126), "AmsiScanString");
      *((_QWORD *)this + 123) = v7;
      if ( ProcAddress )
      {
        if ( v7 && ((int (__fastcall *)(_QWORD, char *))ProcAddress)(*((_QWORD *)this + 39), (char *)this + 976) < 0 )
          *((_QWORD *)this + 122) = 0;
      }
    }
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  v8 = operator new<HeapAllocator>(
         96,
         (__int64)HeapAllocator::Instance,
         (__int64 (__fastcall *)(__int64, __int64))HeapAllocator::Alloc);
  v15 = (char *(__fastcall *)(ArenaAllocator *, unsigned __int64 *))v8;
  v9 = v8;
  if ( v8 )
  {
    v10 = *((_QWORD *)this + 3);
    *(_QWORD *)v8 = Js::Throw::OutOfMemory;
    *(_QWORD *)(v8 + 8) = Js::MemoryHelper::RecoverUnusedMemory;
    *(_QWORD *)(v8 + 16) = 0;
    *(_QWORD *)(v8 + 24) = 0;
    *(_QWORD *)(v8 + 32) = 0;
    *(_QWORD *)(v8 + 40) = v10 + 160;
    *(_QWORD *)(v8 + 48) = 0;
    *(_BYTE *)(v8 + 56) = 0;
    *(_QWORD *)(v8 + 64) = 0;
    *(_QWORD *)(v8 + 72) = 0;
    *(_DWORD *)(v8 + 80) = 0;
    *(_QWORD *)(v8 + 88) = 0;
  }
  else
  {
    v9 = 0;
  }
  v11 = v17;
  v15 = ArenaAllocator::Alloc;
  *((_QWORD *)this + 30) = v9;
  v16 = 0;
  v17 = v11;
  v12 = operator new<ArenaAllocator>(40, v9, (__int64)&v15);
  if ( v12 )
  {
    *(_DWORD *)(v12 + 16) = 4;
    *(_QWORD *)(v12 + 24) = v9;
    *(_QWORD *)v12 = 0;
    *(_QWORD *)(v12 + 8) = 0;
  }
  else
  {
    v12 = 0;
  }
  v13 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 95) = v12;
  v15 = ArenaAllocator::Alloc;
  v16 = 0;
  v14 = operator new<ArenaAllocator>(40, v13, (__int64)&v15);
  if ( v14 )
  {
    *(_DWORD *)(v14 + 16) = 4;
    *(_QWORD *)(v14 + 24) = v13;
    *(_QWORD *)v14 = 0;
    *(_QWORD *)(v14 + 8) = 0;
  }
  else
  {
    v14 = 0;
  }
  *((_QWORD *)this + 96) = v14;
}

```

## disassembly

```asm
0x18019ff4c  mov     rax, rsp
0x18019ff4f  mov     [rax+18h], rbx
0x18019ff53  mov     [rax+10h], rdx
0x18019ff57  mov     [rax+8], rcx
0x18019ff5b  push    rbp
0x18019ff5c  push    rsi
0x18019ff5d  push    rdi
0x18019ff5e  sub     rsp, 30h
0x18019ff62  mov     rdi, rcx
0x18019ff65  mov     [rcx+18h], rdx
0x18019ff69  mov     rax, rdx
0x18019ff6c  mov     dword ptr [rcx+39Ch], 4
0x18019ff76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl(void)'::`2'::impl
0x18019ff7d  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18019ff82  call    ?GetScriptingHostProcess@ScriptEngine@@QEAA?AW4_WSH_PROCESS@@XZ; ScriptEngine::GetScriptingHostProcess(void)
0x18019ff87  lea     ebx, [rax-1]
0x18019ff8a  call    ?GetBrowserProcess@ScriptEngine@@QEAA?AW4_BROWSER_PROCESS@@XZ; ScriptEngine::GetBrowserProcess(void)
0x18019ff8f  xor     ebp, ebp
0x18019ff91  cmp     ebx, 1
0x18019ff94  jbe     short loc_18019FFA2
0x18019ff96  add     eax, 0FFFFFFE8h
0x18019ff99  cmp     eax, 1
0x18019ff9c  ja      loc_1801A002D
0x18019ffa2  xor     edx, edx; hFile
0x18019ffa4  lea     rcx, LibFileName; "amsi.dll"
0x18019ffab  mov     r8d, 800h; dwFlags
0x18019ffb1  call    cs:__imp_LoadLibraryExW
0x18019ffb8  nop     dword ptr [rax+rax+00h]
0x18019ffbd  mov     [rdi+3F0h], rax
0x18019ffc4  test    rax, rax
0x18019ffc7  jz      short loc_1801A002D
0x18019ffc9  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x18019ffd0  mov     rcx, rax; hModule
0x18019ffd3  call    cs:__imp_GetProcAddress
0x18019ffda  nop     dword ptr [rax+rax+00h]
0x18019ffdf  mov     rcx, [rdi+3F0h]; hModule
0x18019ffe6  lea     rdx, aAmsiscanstring; "AmsiScanString"
0x18019ffed  mov     rsi, rax
0x18019fff0  call    cs:__imp_GetProcAddress
0x18019fff7  nop     dword ptr [rax+rax+00h]
0x18019fffc  mov     [rdi+3D8h], rax
0x1801a0003  test    rsi, rsi
0x1801a0006  jz      short loc_1801A002D
0x1801a0008  test    rax, rax
0x1801a000b  jz      short loc_1801A002D
0x1801a000d  mov     rcx, [rdi+138h]
0x1801a0014  lea     rbx, [rdi+3D0h]
0x1801a001b  mov     rdx, rbx
0x1801a001e  mov     rax, rsi
0x1801a0021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0026  test    eax, eax
0x1801a0028  jns     short loc_1801A002D
0x1801a002a  mov     [rbx], rbp
0x1801a002d  lea     rcx, [rdi+278h]; lpCriticalSection
0x1801a0034  call    cs:__imp_InitializeCriticalSection
0x1801a003b  nop     dword ptr [rax+rax+00h]
0x1801a0040  lea     r8, ?Alloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1801a0047  mov     ecx, 60h ; '`'
0x1801a004c  lea     rdx, ?Instance@HeapAllocator@@2U1@A; HeapAllocator HeapAllocator::Instance
0x1801a0053  call    ??$?2UHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@P80@EAAPEAD0@Z@Z; operator new<HeapAllocator>(unsigned __int64,HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64))
0x1801a0058  mov     [rsp+48h+var_28], rax
0x1801a005d  mov     rbx, rax
0x1801a0060  test    rax, rax
0x1801a0063  jz      short loc_1801A00AE
0x1801a0065  mov     rcx, [rdi+18h]
0x1801a0069  lea     rax, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801a0070  mov     [rbx], rax
0x1801a0073  add     rcx, 0A0h
0x1801a007a  lea     rax, ?RecoverUnusedMemory@MemoryHelper@Js@@SAXXZ; Js::MemoryHelper::RecoverUnusedMemory(void)
0x1801a0081  mov     [rbx+8], rax
0x1801a0085  mov     [rbx+10h], rbp
0x1801a0089  mov     [rbx+18h], rbp
0x1801a008d  mov     [rbx+20h], rbp
0x1801a0091  mov     [rbx+28h], rcx
0x1801a0095  mov     [rbx+30h], rbp
0x1801a0099  mov     [rbx+38h], bpl
0x1801a009d  mov     [rbx+40h], rbp
0x1801a00a1  mov     [rbx+48h], rbp
0x1801a00a5  mov     [rbx+50h], ebp
0x1801a00a8  mov     [rbx+58h], rbp
0x1801a00ac  jmp     short loc_1801A00B1
0x1801a00ae  mov     rbx, rbp
0x1801a00b1  mov     eax, [rsp+48h+var_1C]
0x1801a00b5  lea     rsi, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801a00bc  lea     r8, [rsp+48h+var_28]
0x1801a00c1  mov     [rsp+48h+var_28], rsi
0x1801a00c6  mov     rdx, rbx
0x1801a00c9  mov     [rdi+0F0h], rbx
0x1801a00d0  mov     ecx, 28h ; '('
0x1801a00d5  mov     [rsp+48h+var_20], ebp
0x1801a00d9  mov     [rsp+48h+var_1C], eax
0x1801a00dd  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801a00e2  test    rax, rax
0x1801a00e5  jz      short loc_1801A00FB
0x1801a00e7  mov     dword ptr [rax+10h], 4
0x1801a00ee  mov     [rax+18h], rbx
0x1801a00f2  mov     [rax], rbp
0x1801a00f5  mov     [rax+8], rbp
0x1801a00f9  jmp     short loc_1801A00FE
0x1801a00fb  mov     rax, rbp
0x1801a00fe  mov     rbx, [rdi+0F0h]
0x1801a0105  lea     r8, [rsp+48h+var_28]
0x1801a010a  mov     [rdi+2F8h], rax
0x1801a0111  mov     rdx, rbx
0x1801a0114  mov     eax, [rsp+48h+var_1C]
0x1801a0118  mov     ecx, 28h ; '('
0x1801a011d  mov     [rsp+48h+var_28], rsi
0x1801a0122  mov     [rsp+48h+var_20], ebp
0x1801a0126  mov     [rsp+48h+var_1C], eax
0x1801a012a  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801a012f  test    rax, rax
0x1801a0132  jz      short loc_1801A0148
0x1801a0134  mov     dword ptr [rax+10h], 4
0x1801a013b  mov     [rax+18h], rbx
0x1801a013f  mov     [rax], rbp
0x1801a0142  mov     [rax+8], rbp
0x1801a0146  jmp     short loc_1801A014B
0x1801a0148  mov     rax, rbp
0x1801a014b  mov     rbx, [rsp+48h+arg_10]
0x1801a0150  mov     [rdi+300h], rax
0x1801a0157  add     rsp, 30h
0x1801a015b  pop     rdi
0x1801a015c  pop     rsi
0x1801a015d  pop     rbp
0x1801a015e  retn
```
