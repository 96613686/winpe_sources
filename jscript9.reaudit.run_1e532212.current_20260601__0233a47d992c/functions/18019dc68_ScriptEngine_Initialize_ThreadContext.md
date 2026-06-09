# ScriptEngine::Initialize(ThreadContext *)

- ea: `0x18019dc68`
- end: `0x18019de5f`
- name: `?Initialize@ScriptEngine@@QEAAXPEAVThreadContext@@@Z`
- size: `503`
- prototype: `void __fastcall(ScriptEngine *__hidden this, struct ThreadContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180207de8`
- `0x18021d1ac`

## callees

- `0x1800230d4`
- `0x180107364`
- `0x180109220`
- `0x18019021c`
- `0x18019dc68`
- `0x18021cd70`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18019dcc9`
- `KERNEL32!LoadLibraryExW` at `0x18019dcc9`
- `KERNEL32!InitializeCriticalSection` at `0x18019dd3a`
- `KERNEL32!InitializeCriticalSection` at `0x18019dd3a`
- `KERNEL32!GetProcAddress` at `0x18019dce5`
- `KERNEL32!GetProcAddress` at `0x18019dcfc`
- `KERNEL32!GetProcAddress` at `0x18019dce5`
- `KERNEL32!GetProcAddress` at `0x18019dcfc`

## string_xrefs

- `0x18019dcbc`: `amsi.dll`
- `0x18019dcdb`: `AmsiInitialize`
- `0x18019dcf2`: `AmsiScanString`

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
  char *(__fastcall *v15)(ArenaAllocator *__hidden, unsigned __int64); // [rsp+20h] [rbp-28h] BYREF
  int v16; // [rsp+28h] [rbp-20h]
  int v17; // [rsp+2Ch] [rbp-1Ch]

  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 231) = 4;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl'::`2'::impl);
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
  v8 = operator new<HeapAllocator>(96, HeapAllocator::Instance, HeapAllocator::Alloc);
  v15 = (char *(__fastcall *)(ArenaAllocator *__hidden, unsigned __int64))v8;
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
  v12 = operator new<ArenaAllocator>(40, v9, &v15);
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
  v14 = operator new<ArenaAllocator>(40, v13, &v15);
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
0x18019dc68  mov     rax, rsp
0x18019dc6b  mov     [rax+18h], rbx
0x18019dc6f  mov     [rax+10h], rdx
0x18019dc73  mov     [rax+8], rcx
0x18019dc77  push    rbp
0x18019dc78  push    rsi
0x18019dc79  push    rdi
0x18019dc7a  sub     rsp, 30h
0x18019dc7e  mov     rdi, rcx
0x18019dc81  mov     [rcx+18h], rdx
0x18019dc85  mov     rax, rdx
0x18019dc88  mov     dword ptr [rcx+39Ch], 4
0x18019dc92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::GetImpl(void)'::`2'::impl
0x18019dc99  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_AMSI@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_AMSI>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18019dc9e  call    ?GetScriptingHostProcess@ScriptEngine@@QEAA?AW4_WSH_PROCESS@@XZ; ScriptEngine::GetScriptingHostProcess(void)
0x18019dca3  lea     ebx, [rax-1]
0x18019dca6  call    ?GetBrowserProcess@ScriptEngine@@QEAA?AW4_BROWSER_PROCESS@@XZ; ScriptEngine::GetBrowserProcess(void)
0x18019dcab  xor     ebp, ebp
0x18019dcad  cmp     ebx, 1
0x18019dcb0  jbe     short loc_18019DCBA
0x18019dcb2  add     eax, 0FFFFFFE8h
0x18019dcb5  cmp     eax, 1
0x18019dcb8  ja      short loc_18019DD33
0x18019dcba  xor     edx, edx; hFile
0x18019dcbc  lea     rcx, LibFileName; "amsi.dll"
0x18019dcc3  mov     r8d, 800h; dwFlags
0x18019dcc9  call    cs:__imp_LoadLibraryExW
0x18019dccf  mov     [rdi+3F0h], rax
0x18019dcd6  test    rax, rax
0x18019dcd9  jz      short loc_18019DD33
0x18019dcdb  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x18019dce2  mov     rcx, rax; hModule
0x18019dce5  call    cs:__imp_GetProcAddress
0x18019dceb  mov     rcx, [rdi+3F0h]; hModule
0x18019dcf2  lea     rdx, aAmsiscanstring; "AmsiScanString"
0x18019dcf9  mov     rsi, rax
0x18019dcfc  call    cs:__imp_GetProcAddress
0x18019dd02  mov     [rdi+3D8h], rax
0x18019dd09  test    rsi, rsi
0x18019dd0c  jz      short loc_18019DD33
0x18019dd0e  test    rax, rax
0x18019dd11  jz      short loc_18019DD33
0x18019dd13  mov     rcx, [rdi+138h]
0x18019dd1a  lea     rbx, [rdi+3D0h]
0x18019dd21  mov     rdx, rbx
0x18019dd24  mov     rax, rsi
0x18019dd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dd2c  test    eax, eax
0x18019dd2e  jns     short loc_18019DD33
0x18019dd30  mov     [rbx], rbp
0x18019dd33  lea     rcx, [rdi+278h]; lpCriticalSection
0x18019dd3a  call    cs:__imp_InitializeCriticalSection
0x18019dd40  lea     r8, ?Alloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18019dd47  mov     ecx, 60h ; '`'
0x18019dd4c  lea     rdx, ?Instance@HeapAllocator@@2U1@A; HeapAllocator HeapAllocator::Instance
0x18019dd53  call    ??$?2UHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@P80@EAAPEAD0@Z@Z; operator new<HeapAllocator>(unsigned __int64,HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64))
0x18019dd58  mov     [rsp+48h+var_28], rax
0x18019dd5d  mov     rbx, rax
0x18019dd60  test    rax, rax
0x18019dd63  jz      short loc_18019DDAE
0x18019dd65  mov     rcx, [rdi+18h]
0x18019dd69  lea     rax, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x18019dd70  mov     [rbx], rax
0x18019dd73  add     rcx, 0A0h
0x18019dd7a  lea     rax, ?RecoverUnusedMemory@MemoryHelper@Js@@SAXXZ; Js::MemoryHelper::RecoverUnusedMemory(void)
0x18019dd81  mov     [rbx+8], rax
0x18019dd85  mov     [rbx+10h], rbp
0x18019dd89  mov     [rbx+18h], rbp
0x18019dd8d  mov     [rbx+20h], rbp
0x18019dd91  mov     [rbx+28h], rcx
0x18019dd95  mov     [rbx+30h], rbp
0x18019dd99  mov     [rbx+38h], bpl
0x18019dd9d  mov     [rbx+40h], rbp
0x18019dda1  mov     [rbx+48h], rbp
0x18019dda5  mov     [rbx+50h], ebp
0x18019dda8  mov     [rbx+58h], rbp
0x18019ddac  jmp     short loc_18019DDB1
0x18019ddae  mov     rbx, rbp
0x18019ddb1  mov     eax, [rsp+48h+var_1C]
0x18019ddb5  lea     rsi, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x18019ddbc  lea     r8, [rsp+48h+var_28]
0x18019ddc1  mov     [rsp+48h+var_28], rsi
0x18019ddc6  mov     rdx, rbx
0x18019ddc9  mov     [rdi+0F0h], rbx
0x18019ddd0  mov     ecx, 28h ; '('
0x18019ddd5  mov     [rsp+48h+var_20], ebp
0x18019ddd9  mov     [rsp+48h+var_1C], eax
0x18019dddd  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x18019dde2  test    rax, rax
0x18019dde5  jz      short loc_18019DDFB
0x18019dde7  mov     dword ptr [rax+10h], 4
0x18019ddee  mov     [rax+18h], rbx
0x18019ddf2  mov     [rax], rbp
0x18019ddf5  mov     [rax+8], rbp
0x18019ddf9  jmp     short loc_18019DDFE
0x18019ddfb  mov     rax, rbp
0x18019ddfe  mov     rbx, [rdi+0F0h]
0x18019de05  lea     r8, [rsp+48h+var_28]
0x18019de0a  mov     [rdi+2F8h], rax
0x18019de11  mov     rdx, rbx
0x18019de14  mov     eax, [rsp+48h+var_1C]
0x18019de18  mov     ecx, 28h ; '('
0x18019de1d  mov     [rsp+48h+var_28], rsi
0x18019de22  mov     [rsp+48h+var_20], ebp
0x18019de26  mov     [rsp+48h+var_1C], eax
0x18019de2a  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x18019de2f  test    rax, rax
0x18019de32  jz      short loc_18019DE48
0x18019de34  mov     dword ptr [rax+10h], 4
0x18019de3b  mov     [rax+18h], rbx
0x18019de3f  mov     [rax], rbp
0x18019de42  mov     [rax+8], rbp
0x18019de46  jmp     short loc_18019DE4B
0x18019de48  mov     rax, rbp
0x18019de4b  mov     rbx, [rsp+48h+arg_10]
0x18019de50  mov     [rdi+300h], rax
0x18019de57  add     rsp, 30h
0x18019de5b  pop     rdi
0x18019de5c  pop     rsi
0x18019de5d  pop     rbp
0x18019de5e  retn
```
