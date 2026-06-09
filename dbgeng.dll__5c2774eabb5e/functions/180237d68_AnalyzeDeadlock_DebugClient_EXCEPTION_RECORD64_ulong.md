# AnalyzeDeadlock(DebugClient *,_EXCEPTION_RECORD64 *,ulong)

- ea: `0x180237d68`
- end: `0x180238234`
- name: `?AnalyzeDeadlock@@YAXPEAVDebugClient@@PEAU_EXCEPTION_RECORD64@@K@Z`
- size: `1228`
- prototype: `void __fastcall(struct DebugClient *, struct _EXCEPTION_RECORD64 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18023c3a0`

## callees

- `0x1800727b8`
- `0x180072c8c`
- `0x18007cf9c`
- `0x18008d550`
- `0x1800986ec`
- `0x18009f864`
- `0x1800b1544`
- `0x1800c1cd8`
- `0x1800f0f40`
- `0x1800f2998`
- `0x180237d68`
- `0x180242de4`
- `0x1802d7bc8`
- `0x1802e3f34`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180237e10`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180238086`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802380ad`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802380d4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180237e10`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180238086`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802380ad`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802380d4`

## string_xrefs

- `0x180237e09`: `ntdll!RtlpWaitForCriticalSection`
- `0x180237f3b`: `Critsec %s owned by thread %d (.%x) caused thread %d (.%x)\n      to timeout entering it.  Breaking in on owner thread, ask\n      yourself why it has held this critsec long enough to deadlock.\n      Use `~%ds` to switch back to timeout thread.\n`
- `0x180237ea6`: `Critsec %s was deleted or was never initialized.\n`
- `0x180237fab`: `Critsec %s ABANDONED owner thread ID is .%x, no such thread.\n`
- `0x1802380a6`: `ntdll!RtlAcquireResourceExclusive`
- `0x18023807f`: `ntdll!RtlAcquireResourceShared`
- `0x1802380cd`: `ntdll!RtlConvertSharedToExclusive`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AnalyzeDeadlock(struct DebugClient *a1, struct _EXCEPTION_RECORD64 *a2, int a3, int a4)
{
  wchar_t *v6; // rdx
  unsigned __int64 v7; // r8
  struct MachineInfo *v8; // rax
  unsigned __int16 *v9; // rax
  unsigned int v10; // esi
  struct ThreadInfo *ThreadBySystemId; // rax
  ThreadInfo *v12; // rdi
  unsigned int v13; // esi
  int v14; // r15d
  unsigned int v15; // r12d
  unsigned int v16; // r13d
  struct MachineInfo *v17; // rcx
  unsigned __int16 *v18; // rax
  struct MachineInfo *v19; // rax
  unsigned __int16 *v20; // rax
  unsigned __int64 v21; // rdx
  struct MachineInfo *v22; // rax
  wchar_t *v23; // rdx
  wchar_t *v24; // rdx
  wchar_t *v25; // rdx
  unsigned __int16 *v26; // rax
  struct MachineInfo *v27; // rcx
  unsigned __int16 *v28; // rax
  wchar_t *v29; // rcx
  wchar_t *v30; // rax
  unsigned int v31[2]; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+28h] [rbp-D8h]
  __int64 v33[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v36[4]; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  wchar_t *String2; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v40; // [rsp+9Ch] [rbp-64h]
  char v41; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v42[64]; // [rsp+170h] [rbp+70h] BYREF

  v38 = -2;
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
    (unsigned int)&String2,
    (unsigned int)&v41,
    100,
    a4,
    1);
  v34 = 0;
  v35 = 0;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  *(_OWORD *)v33 = 0;
  GetSymbol(a2->ExceptionAddress, -1, (__int64)&String2, (__int64)&v34, (__int64)v33);
  v6 = 0;
  if ( v40 >= 2 )
    v6 = String2;
  if ( _wcsicmp(L"ntdll!RtlpWaitForCriticalSection", v6) )
  {
    v23 = 0;
    if ( v40 >= 2 )
      v23 = String2;
    if ( !_wcsicmp(L"ntdll!RtlAcquireResourceShared", v23) )
      goto LABEL_56;
    v24 = 0;
    if ( v40 >= 2 )
      v24 = String2;
    if ( !_wcsicmp(L"ntdll!RtlAcquireResourceExclusive", v24) )
      goto LABEL_56;
    v25 = 0;
    if ( v40 >= 2 )
      v25 = String2;
    if ( _wcsicmp(L"ntdll!RtlConvertSharedToExclusive", v25) )
    {
      dprintf(L"Possible Deadlock in %s ", String2);
      *(_OWORD *)v33 = 0;
      GetSymbol(a2->ExceptionInformation[0], -1, (__int64)&String2, (__int64)&v34, (__int64)v33);
      dprintf(L"Lock %s", String2);
    }
    else
    {
LABEL_56:
      v29 = 0;
      if ( v40 >= 2 )
        v29 = String2;
      v30 = wcsstr(v29, L"!");
      dprintf(L"deadlock in %s ", v30 + 1);
      *(_OWORD *)v33 = 0;
      GetSymbol(a2->ExceptionInformation[0], -1, (__int64)&String2, (__int64)&v34, (__int64)v33);
      dprintf(L"Resource %s", String2);
    }
    if ( v34 )
    {
      v26 = FormatDisp64(v34);
      dprintf(L"+%s", v26);
    }
    if ( g_Target )
    {
      if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
        || (v27 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
      {
        v27 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
      }
    }
    else
    {
      v27 = 0;
    }
    v28 = FormatMachineAddr64(v27, a2->ExceptionInformation[0]);
    dprintf(L" (%s)\n", v28);
    if ( !a3 )
      dprintf(L"!!! second chance !!!\n");
  }
  else
  {
    v7 = a2->ExceptionInformation[0];
    if ( v7 && !(unsigned int)TargetInfo::ReadAllVirtual(g_EventTarget, g_EventProcess, v7, &v35, 0x28u, 0) )
    {
      if ( (_QWORD)v35 )
      {
        v10 = v36[0];
        ThreadBySystemId = ProcessInfo::FindThreadBySystemId(g_Process, v36[0]);
        v12 = ThreadBySystemId;
        if ( ThreadBySystemId )
        {
          v13 = *((_DWORD *)g_Thread + 8);
          v14 = *((_DWORD *)g_Thread + 9);
          v15 = *((_DWORD *)ThreadBySystemId + 9);
          v16 = *((_DWORD *)ThreadBySystemId + 8);
          if ( g_Target )
          {
            if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
              || (v17 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
            {
              v17 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
            }
          }
          else
          {
            v17 = 0;
          }
          v18 = FormatMachineAddr64(v17, a2->ExceptionInformation[0]);
          LODWORD(v32) = v14;
          v31[0] = v13;
          dprintf(
            L"Critsec %s owned by thread %d (.%x) caused thread %d (.%x)\n"
             "      to timeout entering it.  Breaking in on owner thread, ask\n"
             "      yourself why it has held this critsec long enough to deadlock.\n"
             "      Use `~%ds` to switch back to timeout thread.\n",
            v18,
            v16,
            v15,
            *(_QWORD *)v31,
            v32,
            v13);
          g_EventThread = v12;
          SetPromptThread(0, v12, 0, 1);
        }
        else if ( v10 )
        {
          if ( g_Target )
          {
            if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
              || (v19 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
            {
              v19 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
            }
          }
          else
          {
            v19 = 0;
          }
          v20 = FormatMachineAddr64(v19, a2->ExceptionInformation[0]);
          dprintf(L"Critsec %s ABANDONED owner thread ID is .%x, no such thread.\n", v20, v10);
        }
      }
      else
      {
        if ( g_Target )
        {
          if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
            || (v8 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
          {
            v8 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
          }
        }
        else
        {
          v8 = 0;
        }
        v9 = FormatMachineAddr64(v8, a2->ExceptionInformation[0]);
        dprintf(L"Critsec %s was deleted or was never initialized.\n", v9);
      }
    }
    if ( !a3 )
      dprintf(L"!!! second chance !!!\n");
    v21 = a2->ExceptionInformation[0];
    if ( v21 )
    {
      LODWORD(v33[0]) = 0;
      if ( g_Target )
      {
        if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
          || (v22 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
        {
          v22 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
        }
      }
      else
      {
        v22 = 0;
      }
      FormatMachineAddr64(v22, v21);
      CopyNStringW(v42);
      dprintf(L"!critsec %s\n", v42);
      ExtensionInfo::CallAny(0, 0, L"critsec", v42, 0, 0, L"AutomaticallyLoaded", (int *)v33);
    }
  }
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&String2);
}

```

## disassembly

```asm
0x180237d68  push    rbp
0x180237d6a  push    rbx
0x180237d6b  push    rsi
0x180237d6c  push    rdi
0x180237d6d  push    r12
0x180237d6f  push    r13
0x180237d71  push    r14
0x180237d73  push    r15
0x180237d75  lea     rbp, [rsp-108h]
0x180237d7d  sub     rsp, 208h
0x180237d84  mov     [rbp+140h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x180237d8c  mov     rax, cs:__security_cookie
0x180237d93  xor     rax, rsp
0x180237d96  mov     [rbp+140h+var_50], rax
0x180237d9d  mov     r14d, r8d
0x180237da0  mov     rbx, rdx
0x180237da3  mov     byte ptr [rsp+240h+var_220], 1
0x180237da8  mov     r8d, 64h ; 'd'
0x180237dae  lea     rdx, [rbp+140h+var_198]
0x180237db2  lea     rcx, [rbp+140h+String2]
0x180237db6  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x180237dbb  nop
0x180237dbc  xor     r15d, r15d
0x180237dbf  mov     [rsp+240h+var_1F0], r15
0x180237dc4  xorps   xmm0, xmm0
0x180237dc7  xor     eax, eax
0x180237dc9  movups  [rsp+240h+var_1E8], xmm0
0x180237dce  movups  xmmword ptr [rsp+240h+var_1D8], xmm0
0x180237dd3  mov     [rsp+240h+var_1C8], rax
0x180237dd8  movdqu  xmmword ptr [rsp+240h+var_200], xmm0
0x180237dde  lea     rax, [rsp+240h+var_200]
0x180237de3  mov     qword ptr [rsp+240h+var_220], rax; __int64
0x180237de8  lea     r9, [rsp+240h+var_1F0]; __int64
0x180237ded  lea     r8, [rbp+140h+String2]; __int64
0x180237df1  or      edx, 0FFFFFFFFh; int
0x180237df4  mov     rcx, [rbx+10h]; int
0x180237df8  call    ?GetSymbol@@YAH_KKPEAV?$DbsDynamicString@G@@PEA_KV?$shared_ptr@USYMBOL_INFO_AND_NAME@@@std@@@Z; GetSymbol(unsigned __int64,ulong,DbsDynamicString<ushort> *,unsigned __int64 *,std::shared_ptr<SYMBOL_INFO_AND_NAME>)
0x180237dfd  mov     edx, r15d
0x180237e00  cmp     [rbp+140h+var_1A4], 2
0x180237e04  cmovnb  rdx, [rbp+140h+String2]; String2
0x180237e09  lea     rcx, aNtdllRtlpwaitf; "ntdll!RtlpWaitForCriticalSection"
0x180237e10  call    cs:__imp__wcsicmp
0x180237e17  nop     dword ptr [rax+rax+00h]
0x180237e1c  test    eax, eax
0x180237e1e  jnz     loc_180238073
0x180237e24  mov     r8, [rbx+20h]; unsigned __int64
0x180237e28  test    r8, r8
0x180237e2b  jz      loc_180237FB7
0x180237e31  mov     dword ptr [rsp+240h+var_218], r15d; unsigned int
0x180237e36  mov     [rsp+240h+var_220], 28h ; '('; unsigned int
0x180237e3e  lea     r9, [rsp+240h+var_1E8]; void *
0x180237e43  mov     rdx, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x180237e4a  mov     rcx, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; this
0x180237e51  call    ?ReadAllVirtual@TargetInfo@@QEAAJPEAVProcessInfo@@_KPEAXKK@Z; TargetInfo::ReadAllVirtual(ProcessInfo *,unsigned __int64,void *,ulong,ulong)
0x180237e56  test    eax, eax
0x180237e58  jnz     loc_180237FB7
0x180237e5e  cmp     qword ptr [rsp+240h+var_1E8], r15
0x180237e63  jnz     short loc_180237EB7
0x180237e65  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180237e6c  test    rcx, rcx
0x180237e6f  jz      short loc_180237E94
0x180237e71  mov     eax, [rcx+1008h]
0x180237e77  sub     eax, 2
0x180237e7a  cmp     eax, 1
0x180237e7d  ja      short loc_180237E8B
0x180237e7f  mov     rax, [rcx+2A8h]
0x180237e86  test    rax, rax
0x180237e89  jnz     short loc_180237E97
0x180237e8b  mov     rax, [rcx+298h]
0x180237e92  jmp     short loc_180237E97
0x180237e94  mov     rax, r15
0x180237e97  mov     rdx, [rbx+20h]; unsigned __int64
0x180237e9b  mov     rcx, rax; struct MachineInfo *
0x180237e9e  call    ?FormatMachineAddr64@@YAPEAGPEAVMachineInfo@@_K@Z; FormatMachineAddr64(MachineInfo *,unsigned __int64)
0x180237ea3  mov     rdx, rax
0x180237ea6  lea     rcx, aCritsecSWasDel; "Critsec %s was deleted or was never ini"...
0x180237ead  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180237eb2  jmp     loc_180237FB7
0x180237eb7  mov     esi, [rsp+240h+var_1D8]
0x180237ebb  mov     edx, esi; unsigned int
0x180237ebd  mov     rcx, cs:?g_Process@@3PEAVProcessInfo@@EA; this
0x180237ec4  call    ?FindThreadBySystemId@ProcessInfo@@QEAAPEAVThreadInfo@@K@Z; ProcessInfo::FindThreadBySystemId(ulong)
0x180237ec9  mov     rdi, rax
0x180237ecc  test    rax, rax
0x180237ecf  jz      loc_180237F63
0x180237ed5  mov     rcx, cs:?g_Thread@@3PEAVThreadInfo@@EA; ThreadInfo * g_Thread
0x180237edc  mov     esi, [rcx+20h]
0x180237edf  mov     r15d, [rcx+24h]
0x180237ee3  mov     r12d, [rax+24h]
0x180237ee7  mov     r13d, [rax+20h]
0x180237eeb  mov     rdx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180237ef2  test    rdx, rdx
0x180237ef5  jz      short loc_180237F1A
0x180237ef7  mov     ecx, [rdx+1008h]
0x180237efd  sub     ecx, 2
0x180237f00  cmp     ecx, 1
0x180237f03  ja      short loc_180237F11
0x180237f05  mov     rcx, [rdx+2A8h]
0x180237f0c  test    rcx, rcx
0x180237f0f  jnz     short loc_180237F1C
0x180237f11  mov     rcx, [rdx+298h]
0x180237f18  jmp     short loc_180237F1C
0x180237f1a  xor     ecx, ecx; struct MachineInfo *
0x180237f1c  mov     rdx, [rbx+20h]; unsigned __int64
0x180237f20  call    ?FormatMachineAddr64@@YAPEAGPEAVMachineInfo@@_K@Z; FormatMachineAddr64(MachineInfo *,unsigned __int64)
0x180237f25  mov     dword ptr [rsp+240h+var_210], esi
0x180237f29  mov     dword ptr [rsp+240h+var_218], r15d
0x180237f2e  mov     [rsp+240h+var_220], esi
0x180237f32  mov     r9d, r12d
0x180237f35  mov     r8d, r13d
0x180237f38  mov     rdx, rax
0x180237f3b  lea     rcx, aCritsecSOwnedB; "Critsec %s owned by thread %d (.%x) cau"...
0x180237f42  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180237f47  mov     cs:?g_EventThread@@3PEAVThreadInfo@@EA, rdi; ThreadInfo * g_EventThread
0x180237f4e  mov     r9b, 1; bool
0x180237f51  xor     r8d, r8d; unsigned int
0x180237f54  mov     rdx, rdi; struct ThreadInfo *
0x180237f57  xor     ecx, ecx; struct DebugClient *
0x180237f59  call    ?SetPromptThread@@YAXPEAVDebugClient@@PEAVThreadInfo@@K_N@Z; SetPromptThread(DebugClient *,ThreadInfo *,ulong,bool)
0x180237f5e  xor     r15d, r15d
0x180237f61  jmp     short loc_180237FB7
0x180237f63  test    esi, esi
0x180237f65  jz      short loc_180237FB7
0x180237f67  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180237f6e  test    rcx, rcx
0x180237f71  jz      short loc_180237F96
0x180237f73  mov     eax, [rcx+1008h]
0x180237f79  sub     eax, 2
0x180237f7c  cmp     eax, 1
0x180237f7f  ja      short loc_180237F8D
0x180237f81  mov     rax, [rcx+2A8h]
0x180237f88  test    rax, rax
0x180237f8b  jnz     short loc_180237F99
0x180237f8d  mov     rax, [rcx+298h]
0x180237f94  jmp     short loc_180237F99
0x180237f96  mov     rax, r15
0x180237f99  mov     rdx, [rbx+20h]; unsigned __int64
0x180237f9d  mov     rcx, rax; struct MachineInfo *
0x180237fa0  call    ?FormatMachineAddr64@@YAPEAGPEAVMachineInfo@@_K@Z; FormatMachineAddr64(MachineInfo *,unsigned __int64)
0x180237fa5  mov     rdx, rax
0x180237fa8  mov     r8d, esi
0x180237fab  lea     rcx, aCritsecSAbando; "Critsec %s ABANDONED owner thread ID is"...
0x180237fb2  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180237fb7  test    r14d, r14d
0x180237fba  jnz     short loc_180237FC8
0x180237fbc  lea     rcx, aSecondChance; "!!! second chance !!!\n"
0x180237fc3  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180237fc8  mov     rdx, [rbx+20h]; unsigned __int64
0x180237fcc  test    rdx, rdx
0x180237fcf  jz      loc_1802381AA
0x180237fd5  mov     dword ptr [rsp+240h+var_200], r15d
0x180237fda  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180237fe1  test    rcx, rcx
0x180237fe4  jz      short loc_180238009
0x180237fe6  mov     eax, [rcx+1008h]
0x180237fec  sub     eax, 2
0x180237fef  cmp     eax, 1
0x180237ff2  ja      short loc_180238000
0x180237ff4  mov     rax, [rcx+2A8h]
0x180237ffb  test    rax, rax
0x180237ffe  jnz     short loc_18023800C
0x180238000  mov     rax, [rcx+298h]
0x180238007  jmp     short loc_18023800C
0x180238009  mov     rax, r15
0x18023800c  mov     rcx, rax; struct MachineInfo *
0x18023800f  call    ?FormatMachineAddr64@@YAPEAGPEAVMachineInfo@@_K@Z; FormatMachineAddr64(MachineInfo *,unsigned __int64)
0x180238014  mov     rdx, rax
0x180238017  mov     r9d, 40h ; '@'
0x18023801d  or      r8d, 0FFFFFFFFh
0x180238021  lea     rcx, [rbp+140h+var_D0]; void *
0x180238025  call    CopyNStringW
0x18023802a  lea     rdx, [rbp+140h+var_D0]
0x18023802e  lea     rcx, aCritsecS; "!critsec %s\n"
0x180238035  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18023803a  lea     rax, [rsp+240h+var_200]
0x18023803f  mov     [rsp+240h+var_208], rax; int *
0x180238044  lea     rax, aAutomaticallyl; "AutomaticallyLoaded"
0x18023804b  mov     [rsp+240h+var_210], rax; unsigned __int16 *
0x180238050  mov     dword ptr [rsp+240h+var_218], r15d; int
0x180238055  mov     [rsp+240h+var_220], r15d; int
0x18023805a  lea     r9, [rbp+140h+var_D0]; unsigned __int16 *
0x18023805e  lea     r8, aCritsec; "critsec"
0x180238065  xor     edx, edx; struct ExtensionInfo *
0x180238067  xor     ecx, ecx; struct DebugClient *
0x180238069  call    ?CallAny@ExtensionInfo@@SA_NPEAVDebugClient@@PEAV1@PEAGPEBGHH3PEAJ@Z; ExtensionInfo::CallAny(DebugClient *,ExtensionInfo *,ushort *,ushort const *,int,int,ushort const *,long *)
0x18023806e  jmp     loc_1802381AA
0x180238073  mov     rdx, r15
0x180238076  cmp     [rbp+140h+var_1A4], 2
0x18023807a  cmovnb  rdx, [rbp+140h+String2]; String2
0x18023807f  lea     rcx, aNtdllRtlacquir_0; "ntdll!RtlAcquireResourceShared"
0x180238086  call    cs:__imp__wcsicmp
0x18023808d  nop     dword ptr [rax+rax+00h]
0x180238092  test    eax, eax
0x180238094  jz      loc_1802381D7
0x18023809a  mov     rdx, r15
0x18023809d  cmp     [rbp+140h+var_1A4], 2
0x1802380a1  cmovnb  rdx, [rbp+140h+String2]; String2
0x1802380a6  lea     rcx, aNtdllRtlacquir; "ntdll!RtlAcquireResourceExclusive"
0x1802380ad  call    cs:__imp__wcsicmp
0x1802380b4  nop     dword ptr [rax+rax+00h]
0x1802380b9  test    eax, eax
0x1802380bb  jz      loc_1802381D7
0x1802380c1  mov     rdx, r15
0x1802380c4  cmp     [rbp+140h+var_1A4], 2
0x1802380c8  cmovnb  rdx, [rbp+140h+String2]; String2
0x1802380cd  lea     rcx, aNtdllRtlconver; "ntdll!RtlConvertSharedToExclusive"
0x1802380d4  call    cs:__imp__wcsicmp
0x1802380db  nop     dword ptr [rax+rax+00h]
0x1802380e0  test    eax, eax
0x1802380e2  jz      loc_1802381D7
0x1802380e8  mov     rdx, [rbp+140h+String2]
0x1802380ec  lea     rcx, aPossibleDeadlo_0; "Possible Deadlock in %s "
0x1802380f3  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802380f8  xorps   xmm0, xmm0
0x1802380fb  movdqu  xmmword ptr [rsp+240h+var_200], xmm0
0x180238101  lea     rax, [rsp+240h+var_200]
0x180238106  mov     qword ptr [rsp+240h+var_220], rax; __int64
0x18023810b  lea     r9, [rsp+240h+var_1F0]; __int64
0x180238110  lea     r8, [rbp+140h+String2]; __int64
0x180238114  or      edx, 0FFFFFFFFh; int
0x180238117  mov     rcx, [rbx+20h]; int
0x18023811b  call    ?GetSymbol@@YAH_KKPEAV?$DbsDynamicString@G@@PEA_KV?$shared_ptr@USYMBOL_INFO_AND_NAME@@@std@@@Z; GetSymbol(unsigned __int64,ulong,DbsDynamicString<ushort> *,unsigned __int64 *,std::shared_ptr<SYMBOL_INFO_AND_NAME>)
0x180238120  lea     rcx, aLockS; "Lock %s"
0x180238127  mov     rdx, [rbp+140h+String2]
0x18023812b  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180238130  mov     rcx, [rsp+240h+var_1F0]; unsigned __int64
0x180238135  test    rcx, rcx
0x180238138  jz      short loc_18023814E
0x18023813a  call    ?FormatDisp64@@YAPEAG_K@Z; FormatDisp64(unsigned __int64)
0x18023813f  mov     rdx, rax
0x180238142  lea     rcx, aS_31; "+%s"
0x180238149  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18023814e  mov     rdx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180238155  test    rdx, rdx
0x180238158  jz      short loc_18023817D
0x18023815a  mov     eax, [rdx+1008h]
0x180238160  sub     eax, 2
0x180238163  cmp     eax, 1
0x180238166  ja      short loc_180238174
0x180238168  mov     rcx, [rdx+2A8h]
0x18023816f  test    rcx, rcx
0x180238172  jnz     short loc_180238180
0x180238174  mov     rcx, [rdx+298h]
0x18023817b  jmp     short loc_180238180
0x18023817d  mov     rcx, r15; struct MachineInfo *
0x180238180  mov     rdx, [rbx+20h]; unsigned __int64
0x180238184  call    ?FormatMachineAddr64@@YAPEAGPEAVMachineInfo@@_K@Z; FormatMachineAddr64(MachineInfo *,unsigned __int64)
0x180238189  mov     rdx, rax
0x18023818c  lea     rcx, aS_38; " (%s)\n"
0x180238193  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180238198  test    r14d, r14d
0x18023819b  jnz     short loc_1802381AA
0x18023819d  lea     rcx, aSecondChance; "!!! second chance !!!\n"
0x1802381a4  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802381a9  nop
0x1802381aa  lea     rcx, [rbp+140h+String2]
0x1802381ae  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1802381b3  mov     rcx, [rbp+140h+var_50]
0x1802381ba  xor     rcx, rsp; StackCookie
0x1802381bd  call    __security_check_cookie
0x1802381c2  add     rsp, 208h
0x1802381c9  pop     r15
0x1802381cb  pop     r14
0x1802381cd  pop     r13
0x1802381cf  pop     r12
0x1802381d1  pop     rdi
0x1802381d2  pop     rsi
0x1802381d3  pop     rbx
0x1802381d4  pop     rbp
0x1802381d5  retn
0x1802381d7  mov     rcx, r15
0x1802381da  cmp     [rbp+140h+var_1A4], 2
0x1802381de  cmovnb  rcx, [rbp+140h+String2]; Str
0x1802381e3  lea     rdx, asc_1805E7014; "!"
0x1802381ea  call    wcsstr
0x1802381ef  lea     rdx, [rax+2]
0x1802381f3  lea     rcx, aDeadlockInS; "deadlock in %s "
0x1802381fa  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802381ff  xorps   xmm0, xmm0
0x180238202  movdqu  xmmword ptr [rsp+240h+var_200], xmm0
0x180238208  lea     rax, [rsp+240h+var_200]
0x18023820d  mov     qword ptr [rsp+240h+var_220], rax; __int64
0x180238212  lea     r9, [rsp+240h+var_1F0]; __int64
0x180238217  lea     r8, [rbp+140h+String2]; __int64
0x18023821b  or      edx, 0FFFFFFFFh; int
0x18023821e  mov     rcx, [rbx+20h]; int
0x180238222  call    ?GetSymbol@@YAH_KKPEAV?$DbsDynamicString@G@@PEA_KV?$shared_ptr@USYMBOL_INFO_AND_NAME@@@std@@@Z; GetSymbol(unsigned __int64,ulong,DbsDynamicString<ushort> *,unsigned __int64 *,std::shared_ptr<SYMBOL_INFO_AND_NAME>)
0x180238227  lea     rcx, aResourceS; "Resource %s"
0x18023822e  jmp     loc_180238127
```
