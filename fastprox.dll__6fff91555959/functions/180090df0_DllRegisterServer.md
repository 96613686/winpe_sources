# DllRegisterServer

- ea: `0x180090df0`
- end: `0x180090f5d`
- name: `DllRegisterServer`
- size: `365`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180037120`
- `0x180057b64`
- `0x180057b98`
- `0x180090318`
- `0x180090df0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180090f4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180090f4a`
- `wbemcomn!GetMemLogObject` at `0x180090e36`
- `wbemcomn!GetMemLogObject` at `0x180090ea9`
- `wbemcomn!GetMemLogObject` at `0x180090f08`
- `wbemcomn!GetMemLogObject` at `0x180090e36`
- `wbemcomn!GetMemLogObject` at `0x180090ea9`
- `wbemcomn!GetMemLogObject` at `0x180090f08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090e42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090eb5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090f14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090e42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090eb5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180090f14`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  struct _RTL_CRITICAL_SECTION *v0; // rdx
  HRESULT v2; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v4; // rcx
  __int64 v5; // rdx
  int v6; // edx
  CMemoryLog *v7; // rax
  struct _LIST_ENTRY *i; // rdi
  CMemoryLog *v9; // rax
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !dword_1800D7EC8 )
    return -2147418113;
  CMyInCritSec::CMyInCritSec((CMyInCritSec *)lpCriticalSection, v0);
  if ( !dword_1800D7EC8 )
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
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
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
      v2 = RegisterServer((struct CClassInfo *)&i[-1].Blink, v6);
      if ( v2 < 0 )
        break;
    }
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, -1);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 16;
      goto LABEL_10;
    }
    goto LABEL_25;
  }
  v7 = GetMemLogObject();
  CMemoryLog::Write(v7, -1);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
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
0x180090df0  mov     [rsp+arg_0], rbx
0x180090df5  push    rdi
0x180090df6  sub     rsp, 30h
0x180090dfa  cmp     cs:dword_1800D7EC8, 0
0x180090e01  jnz     short loc_180090E0D
0x180090e03  mov     eax, 8000FFFFh
0x180090e08  jmp     loc_180090F52
0x180090e0d  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x180090e12  call    ??0CMyInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CMyInCritSec::CMyInCritSec(_RTL_CRITICAL_SECTION *)
0x180090e17  nop
0x180090e18  cmp     cs:dword_1800D7EC8, 0
0x180090e1f  jnz     short loc_180090E2B
0x180090e21  mov     ebx, 8000FFFFh
0x180090e26  jmp     loc_180090F45
0x180090e2b  call    ?EnsureInitialized@@YAJXZ; EnsureInitialized(void)
0x180090e30  mov     ebx, eax
0x180090e32  test    eax, eax
0x180090e34  jns     short loc_180090E90
0x180090e36  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090e3c  or      edx, 0FFFFFFFFh
0x180090e3f  mov     rcx, rax
0x180090e42  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090e48  lea     rax, WPP_GLOBAL_Control
0x180090e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180090e56  cmp     rcx, rax
0x180090e59  jz      loc_180090F45
0x180090e5f  test    byte ptr [rcx+1Ch], 1
0x180090e63  jz      loc_180090F45
0x180090e69  cmp     byte ptr [rcx+19h], 2
0x180090e6d  jb      loc_180090F45
0x180090e73  mov     edx, 0Eh
0x180090e78  mov     r9d, ebx
0x180090e7b  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180090e82  mov     rcx, [rcx+10h]
0x180090e86  call    WPP_SF_d
0x180090e8b  jmp     loc_180090F45
0x180090e90  mov     rcx, cs:?g_pServer@@3PEAVCComServer@@EA; CComServer * g_pServer
0x180090e97  mov     rax, [rcx]
0x180090e9a  mov     rax, [rax+20h]
0x180090e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090ea3  mov     ebx, eax
0x180090ea5  test    eax, eax
0x180090ea7  jns     short loc_180090EE1
0x180090ea9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090eaf  or      edx, 0FFFFFFFFh
0x180090eb2  mov     rcx, rax
0x180090eb5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090ebb  lea     rax, WPP_GLOBAL_Control
0x180090ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180090ec9  cmp     rcx, rax
0x180090ecc  jz      short loc_180090F45
0x180090ece  test    byte ptr [rcx+1Ch], 1
0x180090ed2  jz      short loc_180090F45
0x180090ed4  cmp     byte ptr [rcx+19h], 2
0x180090ed8  jb      short loc_180090F45
0x180090eda  mov     edx, 0Fh
0x180090edf  jmp     short loc_180090E78
0x180090ee1  mov     rdi, cs:?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x180090ee8  lea     rax, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x180090eef  cmp     rdi, rax
0x180090ef2  jz      short loc_180090F43
0x180090ef4  lea     rcx, [rdi-8]; struct CClassInfo *
0x180090ef8  call    ?RegisterServer@@YAJPEAUCClassInfo@@H@Z; RegisterServer(CClassInfo *,int)
0x180090efd  mov     ebx, eax
0x180090eff  test    eax, eax
0x180090f01  js      short loc_180090F08
0x180090f03  mov     rdi, [rdi]
0x180090f06  jmp     short loc_180090EE8
0x180090f08  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180090f0e  or      edx, 0FFFFFFFFh
0x180090f11  mov     rcx, rax
0x180090f14  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180090f1a  lea     rax, WPP_GLOBAL_Control
0x180090f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180090f28  cmp     rcx, rax
0x180090f2b  jz      short loc_180090F45
0x180090f2d  test    byte ptr [rcx+1Ch], 1
0x180090f31  jz      short loc_180090F45
0x180090f33  cmp     byte ptr [rcx+19h], 2
0x180090f37  jb      short loc_180090F45
0x180090f39  mov     edx, 10h
0x180090f3e  jmp     loc_180090E78
0x180090f43  xor     ebx, ebx
0x180090f45  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180090f4a  call    cs:__imp_LeaveCriticalSection
0x180090f50  mov     eax, ebx
0x180090f52  mov     rbx, [rsp+38h+arg_0]
0x180090f57  add     rsp, 30h
0x180090f5b  pop     rdi
0x180090f5c  retn
```
