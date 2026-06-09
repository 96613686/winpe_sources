# DllUnregisterServer

- ea: `0x180090f70`
- end: `0x1800910f2`
- name: `DllUnregisterServer`
- size: `386`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180037120`
- `0x180057b64`
- `0x180057b98`
- `0x180090af0`
- `0x180090f70`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910e1`
- `wbemcomn!GetMemLogObject` at `0x180090fb5`
- `wbemcomn!GetMemLogObject` at `0x18009102f`
- `wbemcomn!GetMemLogObject` at `0x180091090`
- `wbemcomn!GetMemLogObject` at `0x180090fb5`
- `wbemcomn!GetMemLogObject` at `0x18009102f`
- `wbemcomn!GetMemLogObject` at `0x180091090`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090fc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009103b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009109c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090fc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009103b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18009109c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  struct _RTL_CRITICAL_SECTION *v0; // rdx
  HRESULT v2; // ebx
  CMemoryLog *v3; // rax
  int v4; // ebx
  CMemoryLog *MemLogObject; // rax
  struct _LIST_ENTRY *i; // rbx
  int v7; // esi
  CMemoryLog *v8; // rax
  LPCRITICAL_SECTION lpCriticalSection[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( !dword_1800D7EC8 )
    return -2147418113;
  CMyInCritSec::CMyInCritSec((CMyInCritSec *)lpCriticalSection, v0);
  if ( dword_1800D7EC8 )
  {
    v2 = EnsureInitialized();
    if ( v2 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(struct CComServer *))(*(_QWORD *)g_pServer + 40LL))(g_pServer);
      if ( v4 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -1);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids,
            (unsigned int)v4);
        }
      }
      for ( i = g_ClassInfoHead.Flink; i != &g_ClassInfoHead; i = i->Flink )
      {
        v7 = UnregisterServer((const GUID *const *)&i[-1].Blink);
        if ( v7 < 0 )
        {
          v8 = GetMemLogObject();
          CMemoryLog::Write(v8, -1);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids,
              (unsigned int)v7);
          }
        }
      }
      v2 = 0;
    }
    else
    {
      v3 = GetMemLogObject();
      CMemoryLog::Write(v3, -1);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids,
          (unsigned int)v2);
      }
    }
  }
  else
  {
    v2 = -2147418113;
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  return v2;
}

```

## disassembly

```asm
0x180090f70  push    rbx
0x180090f72  push    rbp
0x180090f73  push    rsi
0x180090f74  push    rdi
0x180090f75  sub     rsp, 38h
0x180090f79  cmp     cs:dword_1800D7EC8, 0
0x180090f80  jnz     short loc_180090F8C
0x180090f82  mov     eax, 8000FFFFh
0x180090f87  jmp     loc_1800910E9
0x180090f8c  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180090f91  call    ??0CMyInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CMyInCritSec::CMyInCritSec(_RTL_CRITICAL_SECTION *)
0x180090f96  nop
0x180090f97  cmp     cs:dword_1800D7EC8, 0
0x180090f9e  jnz     short loc_180090FAA
0x180090fa0  mov     ebx, 8000FFFFh
0x180090fa5  jmp     loc_1800910DC
0x180090faa  call    ?EnsureInitialized@@YAJXZ; EnsureInitialized(void)
0x180090faf  mov     ebx, eax
0x180090fb1  test    eax, eax
0x180090fb3  jns     short loc_18009100F
0x180090fb5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090fbb  or      edx, 0FFFFFFFFh
0x180090fbe  mov     rcx, rax
0x180090fc1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090fc7  lea     rdi, WPP_GLOBAL_Control
0x180090fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180090fd5  cmp     rcx, rdi
0x180090fd8  jz      loc_1800910DC
0x180090fde  test    byte ptr [rcx+1Ch], 1
0x180090fe2  jz      loc_1800910DC
0x180090fe8  cmp     byte ptr [rcx+19h], 2
0x180090fec  jb      loc_1800910DC
0x180090ff2  mov     edx, 11h
0x180090ff7  mov     r9d, ebx
0x180090ffa  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180091001  mov     rcx, [rcx+10h]
0x180091005  call    WPP_SF_d
0x18009100a  jmp     loc_1800910DC
0x18009100f  mov     rcx, cs:?g_pServer@@3PEAVCComServer@@EA; CComServer * g_pServer
0x180091016  mov     rax, [rcx]
0x180091019  mov     rax, [rax+28h]
0x18009101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091022  mov     ebx, eax
0x180091024  lea     rdi, WPP_GLOBAL_Control
0x18009102b  test    eax, eax
0x18009102d  jns     short loc_180091071
0x18009102f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180091035  or      edx, 0FFFFFFFFh
0x180091038  mov     rcx, rax
0x18009103b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180091041  mov     rcx, cs:WPP_GLOBAL_Control
0x180091048  cmp     rcx, rdi
0x18009104b  jz      short loc_180091071
0x18009104d  test    byte ptr [rcx+1Ch], 1
0x180091051  jz      short loc_180091071
0x180091053  cmp     byte ptr [rcx+19h], 2
0x180091057  jb      short loc_180091071
0x180091059  mov     edx, 12h
0x18009105e  mov     r9d, ebx
0x180091061  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180091068  mov     rcx, [rcx+10h]
0x18009106c  call    WPP_SF_d
0x180091071  mov     rbx, cs:?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x180091078  lea     rbp, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x18009107f  jmp     short loc_1800910D5
0x180091081  lea     rcx, [rbx-8]; struct CClassInfo *
0x180091085  call    ?UnregisterServer@@YAJPEAUCClassInfo@@H@Z; UnregisterServer(CClassInfo *,int)
0x18009108a  mov     esi, eax
0x18009108c  test    eax, eax
0x18009108e  jns     short loc_1800910D2
0x180091090  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180091096  or      edx, 0FFFFFFFFh
0x180091099  mov     rcx, rax
0x18009109c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800910a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800910a9  cmp     rcx, rdi
0x1800910ac  jz      short loc_1800910D2
0x1800910ae  test    byte ptr [rcx+1Ch], 1
0x1800910b2  jz      short loc_1800910D2
0x1800910b4  cmp     byte ptr [rcx+19h], 2
0x1800910b8  jb      short loc_1800910D2
0x1800910ba  mov     edx, 13h
0x1800910bf  mov     r9d, esi
0x1800910c2  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x1800910c9  mov     rcx, [rcx+10h]
0x1800910cd  call    WPP_SF_d
0x1800910d2  mov     rbx, [rbx]
0x1800910d5  cmp     rbx, rbp
0x1800910d8  jnz     short loc_180091081
0x1800910da  xor     ebx, ebx
0x1800910dc  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800910e1  call    cs:__imp_LeaveCriticalSection
0x1800910e7  mov     eax, ebx
0x1800910e9  add     rsp, 38h
0x1800910ed  pop     rdi
0x1800910ee  pop     rsi
0x1800910ef  pop     rbp
0x1800910f0  pop     rbx
0x1800910f1  retn
```
