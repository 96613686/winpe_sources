# DllRegisterServer

- ea: `0x180043870`
- end: `0x1800439dd`
- name: `DllRegisterServer`
- size: `365`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180026214`
- `0x180042bb4`
- `0x180042d64`
- `0x180043870`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800438b6`
- `wbemcomn!GetMemLogObject` at `0x180043929`
- `wbemcomn!GetMemLogObject` at `0x180043988`
- `wbemcomn!GetMemLogObject` at `0x1800438b6`
- `wbemcomn!GetMemLogObject` at `0x180043929`
- `wbemcomn!GetMemLogObject` at `0x180043988`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800438c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043935`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043994`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800438c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043935`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043994`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  struct _RTL_CRITICAL_SECTION *v0; // rdx
  HRESULT v2; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v4; // rcx
  __int64 v5; // rdx
  CMemoryLog *v6; // rax
  struct _LIST_ENTRY *i; // rdi
  CMemoryLog *v8; // rax
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !dword_180059C78 )
    return -2147418113;
  CMyInCritSec::CMyInCritSec((CMyInCritSec *)lpCriticalSection, v0);
  if ( !dword_180059C78 )
  {
    v2 = -2147418113;
    goto LABEL_25;
  }
  v2 = EnsureInitialized();
  if ( v2 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -1);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v5 = 14;
    goto LABEL_10;
  }
  v2 = (*(__int64 (__fastcall **)(struct CComServer *))(*(_QWORD *)g_pServer + 32LL))(g_pServer);
  if ( v2 >= 0 )
  {
    for ( i = g_ClassInfoHead.Flink; ; i = i->Flink )
    {
      if ( i == &g_ClassInfoHead )
      {
        v2 = 0;
        goto LABEL_25;
      }
      v2 = RegisterServer((const GUID *const *)&i[-1].Blink);
      if ( v2 < 0 )
        break;
    }
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, -1);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 16;
      goto LABEL_10;
    }
    goto LABEL_25;
  }
  v6 = GetMemLogObject();
  CMemoryLog::Write(v6, -1);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 15;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids, (unsigned int)v2);
  }
LABEL_25:
  LeaveCriticalSection(lpCriticalSection[0]);
  return v2;
}

```

## disassembly

```asm
0x180043870  mov     [rsp+arg_0], rbx
0x180043875  push    rdi
0x180043876  sub     rsp, 30h
0x18004387a  cmp     cs:dword_180059C78, 0
0x180043881  jnz     short loc_18004388D
0x180043883  mov     eax, 8000FFFFh
0x180043888  jmp     loc_1800439D2
0x18004388d  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x180043892  call    ??0CMyInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CMyInCritSec::CMyInCritSec(_RTL_CRITICAL_SECTION *)
0x180043897  nop
0x180043898  cmp     cs:dword_180059C78, 0
0x18004389f  jnz     short loc_1800438AB
0x1800438a1  mov     ebx, 8000FFFFh
0x1800438a6  jmp     loc_1800439C5
0x1800438ab  call    ?EnsureInitialized@@YAJXZ; EnsureInitialized(void)
0x1800438b0  mov     ebx, eax
0x1800438b2  test    eax, eax
0x1800438b4  jns     short loc_180043910
0x1800438b6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800438bc  or      edx, 0FFFFFFFFh
0x1800438bf  mov     rcx, rax
0x1800438c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800438c8  lea     rax, WPP_GLOBAL_Control
0x1800438cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438d6  cmp     rcx, rax
0x1800438d9  jz      loc_1800439C5
0x1800438df  test    byte ptr [rcx+1Ch], 1
0x1800438e3  jz      loc_1800439C5
0x1800438e9  cmp     byte ptr [rcx+19h], 2
0x1800438ed  jb      loc_1800439C5
0x1800438f3  mov     edx, 0Eh
0x1800438f8  mov     r9d, ebx
0x1800438fb  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180043902  mov     rcx, [rcx+10h]
0x180043906  call    WPP_SF_d
0x18004390b  jmp     loc_1800439C5
0x180043910  mov     rcx, cs:?g_pServer@@3PEAVCComServer@@EA; CComServer * g_pServer
0x180043917  mov     rax, [rcx]
0x18004391a  mov     rax, [rax+20h]
0x18004391e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043923  mov     ebx, eax
0x180043925  test    eax, eax
0x180043927  jns     short loc_180043961
0x180043929  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004392f  or      edx, 0FFFFFFFFh
0x180043932  mov     rcx, rax
0x180043935  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004393b  lea     rax, WPP_GLOBAL_Control
0x180043942  mov     rcx, cs:WPP_GLOBAL_Control
0x180043949  cmp     rcx, rax
0x18004394c  jz      short loc_1800439C5
0x18004394e  test    byte ptr [rcx+1Ch], 1
0x180043952  jz      short loc_1800439C5
0x180043954  cmp     byte ptr [rcx+19h], 2
0x180043958  jb      short loc_1800439C5
0x18004395a  mov     edx, 0Fh
0x18004395f  jmp     short loc_1800438F8
0x180043961  mov     rdi, cs:?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x180043968  lea     rax, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x18004396f  cmp     rdi, rax
0x180043972  jz      short loc_1800439C3
0x180043974  lea     rcx, [rdi-8]; struct CClassInfo *
0x180043978  call    ?RegisterServer@@YAJPEAUCClassInfo@@H@Z; RegisterServer(CClassInfo *,int)
0x18004397d  mov     ebx, eax
0x18004397f  test    eax, eax
0x180043981  js      short loc_180043988
0x180043983  mov     rdi, [rdi]
0x180043986  jmp     short loc_180043968
0x180043988  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004398e  or      edx, 0FFFFFFFFh
0x180043991  mov     rcx, rax
0x180043994  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004399a  lea     rax, WPP_GLOBAL_Control
0x1800439a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439a8  cmp     rcx, rax
0x1800439ab  jz      short loc_1800439C5
0x1800439ad  test    byte ptr [rcx+1Ch], 1
0x1800439b1  jz      short loc_1800439C5
0x1800439b3  cmp     byte ptr [rcx+19h], 2
0x1800439b7  jb      short loc_1800439C5
0x1800439b9  mov     edx, 10h
0x1800439be  jmp     loc_1800438F8
0x1800439c3  xor     ebx, ebx
0x1800439c5  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800439ca  call    cs:__imp_LeaveCriticalSection
0x1800439d0  mov     eax, ebx
0x1800439d2  mov     rbx, [rsp+38h+arg_0]
0x1800439d7  add     rsp, 30h
0x1800439db  pop     rdi
0x1800439dc  retn
```
