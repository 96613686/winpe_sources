# DllUnregisterServer

- ea: `0x1800439f0`
- end: `0x180043b72`
- name: `DllUnregisterServer`
- size: `386`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180026214`
- `0x180042bb4`
- `0x18004330c`
- `0x1800439f0`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180043a35`
- `wbemcomn!GetMemLogObject` at `0x180043aaf`
- `wbemcomn!GetMemLogObject` at `0x180043b10`
- `wbemcomn!GetMemLogObject` at `0x180043a35`
- `wbemcomn!GetMemLogObject` at `0x180043aaf`
- `wbemcomn!GetMemLogObject` at `0x180043b10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043a41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043abb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043b1c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043a41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043abb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043b1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043b61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043b61`

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

  if ( !dword_180059C78 )
    return -2147418113;
  CMyInCritSec::CMyInCritSec((CMyInCritSec *)lpCriticalSection, v0);
  if ( dword_180059C78 )
  {
    v2 = EnsureInitialized();
    if ( v2 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(struct CComServer *))(*(_QWORD *)g_pServer + 40LL))(g_pServer);
      if ( v4 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -1);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
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
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
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
0x1800439f0  push    rbx
0x1800439f2  push    rbp
0x1800439f3  push    rsi
0x1800439f4  push    rdi
0x1800439f5  sub     rsp, 38h
0x1800439f9  cmp     cs:dword_180059C78, 0
0x180043a00  jnz     short loc_180043A0C
0x180043a02  mov     eax, 8000FFFFh
0x180043a07  jmp     loc_180043B69
0x180043a0c  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180043a11  call    ??0CMyInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CMyInCritSec::CMyInCritSec(_RTL_CRITICAL_SECTION *)
0x180043a16  nop
0x180043a17  cmp     cs:dword_180059C78, 0
0x180043a1e  jnz     short loc_180043A2A
0x180043a20  mov     ebx, 8000FFFFh
0x180043a25  jmp     loc_180043B5C
0x180043a2a  call    ?EnsureInitialized@@YAJXZ; EnsureInitialized(void)
0x180043a2f  mov     ebx, eax
0x180043a31  test    eax, eax
0x180043a33  jns     short loc_180043A8F
0x180043a35  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043a3b  or      edx, 0FFFFFFFFh
0x180043a3e  mov     rcx, rax
0x180043a41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043a47  lea     rdi, WPP_GLOBAL_Control
0x180043a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a55  cmp     rcx, rdi
0x180043a58  jz      loc_180043B5C
0x180043a5e  test    byte ptr [rcx+1Ch], 1
0x180043a62  jz      loc_180043B5C
0x180043a68  cmp     byte ptr [rcx+19h], 2
0x180043a6c  jb      loc_180043B5C
0x180043a72  mov     edx, 11h
0x180043a77  mov     r9d, ebx
0x180043a7a  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180043a81  mov     rcx, [rcx+10h]
0x180043a85  call    WPP_SF_d
0x180043a8a  jmp     loc_180043B5C
0x180043a8f  mov     rcx, cs:?g_pServer@@3PEAVCComServer@@EA; CComServer * g_pServer
0x180043a96  mov     rax, [rcx]
0x180043a99  mov     rax, [rax+28h]
0x180043a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043aa2  mov     ebx, eax
0x180043aa4  lea     rdi, WPP_GLOBAL_Control
0x180043aab  test    eax, eax
0x180043aad  jns     short loc_180043AF1
0x180043aaf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043ab5  or      edx, 0FFFFFFFFh
0x180043ab8  mov     rcx, rax
0x180043abb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ac8  cmp     rcx, rdi
0x180043acb  jz      short loc_180043AF1
0x180043acd  test    byte ptr [rcx+1Ch], 1
0x180043ad1  jz      short loc_180043AF1
0x180043ad3  cmp     byte ptr [rcx+19h], 2
0x180043ad7  jb      short loc_180043AF1
0x180043ad9  mov     edx, 12h
0x180043ade  mov     r9d, ebx
0x180043ae1  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180043ae8  mov     rcx, [rcx+10h]
0x180043aec  call    WPP_SF_d
0x180043af1  mov     rbx, cs:?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x180043af8  lea     rbp, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x180043aff  jmp     short loc_180043B55
0x180043b01  lea     rcx, [rbx-8]; struct CClassInfo *
0x180043b05  call    ?UnregisterServer@@YAJPEAUCClassInfo@@H@Z; UnregisterServer(CClassInfo *,int)
0x180043b0a  mov     esi, eax
0x180043b0c  test    eax, eax
0x180043b0e  jns     short loc_180043B52
0x180043b10  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043b16  or      edx, 0FFFFFFFFh
0x180043b19  mov     rcx, rax
0x180043b1c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b29  cmp     rcx, rdi
0x180043b2c  jz      short loc_180043B52
0x180043b2e  test    byte ptr [rcx+1Ch], 1
0x180043b32  jz      short loc_180043B52
0x180043b34  cmp     byte ptr [rcx+19h], 2
0x180043b38  jb      short loc_180043B52
0x180043b3a  mov     edx, 13h
0x180043b3f  mov     r9d, esi
0x180043b42  lea     r8, WPP_b1551c743f9f3b83c2bb722e23d745b2_Traceguids
0x180043b49  mov     rcx, [rcx+10h]
0x180043b4d  call    WPP_SF_d
0x180043b52  mov     rbx, [rbx]
0x180043b55  cmp     rbx, rbp
0x180043b58  jnz     short loc_180043B01
0x180043b5a  xor     ebx, ebx
0x180043b5c  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180043b61  call    cs:__imp_LeaveCriticalSection
0x180043b67  mov     eax, ebx
0x180043b69  add     rsp, 38h
0x180043b6d  pop     rdi
0x180043b6e  pop     rsi
0x180043b6f  pop     rbp
0x180043b70  pop     rbx
0x180043b71  retn
```
