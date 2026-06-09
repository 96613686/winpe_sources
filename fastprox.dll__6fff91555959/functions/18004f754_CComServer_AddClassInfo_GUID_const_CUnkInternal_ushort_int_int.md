# CComServer::AddClassInfo(_GUID const &,CUnkInternal *,ushort *,int,int)

- ea: `0x18004f754`
- end: `0x18004f999`
- name: `?AddClassInfo@CComServer@@IEAAJAEBU_GUID@@PEAVCUnkInternal@@PEAGHH@Z`
- size: `581`
- prototype: `__int64 __fastcall(CComServer *this, const struct _GUID *, struct CUnkInternal *, unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004da90`

## callees

- `0x18004f754`
- `0x18004f9a0`
- `0x18006d500`
- `0x1800700c8`
- `0x18007212c`
- `0x180072230`
- `0x18008fc90`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004f8a8`
- `wbemcomn!GetMemLogObject` at `0x18004f91c`
- `wbemcomn!GetMemLogObject` at `0x18004f956`
- `wbemcomn!GetMemLogObject` at `0x18004f8a8`
- `wbemcomn!GetMemLogObject` at `0x18004f91c`
- `wbemcomn!GetMemLogObject` at `0x18004f956`
- `wbemcomn!?InternalAddRef@CUnkInternal@@QEAAKXZ` at `0x18004f7d5`
- `wbemcomn!?InternalAddRef@CUnkInternal@@QEAAKXZ` at `0x18004f7d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f8b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f92a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f964`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f8b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f92a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f964`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004f784`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004f810`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004f784`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004f810`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CComServer::AddClassInfo(
        CComServer *this,
        const struct _GUID *a2,
        struct CUnkInternal *a3,
        unsigned __int16 *a4,
        int a5,
        int a6)
{
  CComServer *v9; // rax
  CComServer *v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rcx
  unsigned __int16 *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  CWbemRefreshingSvc *v19; // rcx
  __int64 v20; // rdx
  CMemoryLog *v21; // rax
  CComServer *v22; // [rsp+40h] [rbp+8h] BYREF

  v22 = this;
  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147024882);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
    }
    return 2147942414LL;
  }
  v9 = (CComServer *)CWin32DefaultArena::WbemMemAlloc(0x40u);
  v22 = v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = &CClassInfo::`vftable';
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 5) = 0;
    *((_DWORD *)v9 + 12) = 0;
    *((_DWORD *)v9 + 14) = 0;
  }
  else
  {
    v9 = 0;
  }
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v22, v9);
  v10 = v22;
  if ( !v22 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147024882);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 28;
    goto LABEL_16;
  }
  CUnkInternal::InternalAddRef(a3);
  *(_QWORD *)(std::unique_ptr<CClassInfo>::operator->(&v22) + 32) = a3;
  *((_QWORD *)v10 + 3) = a2;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a4[v12] );
  v13 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v12 + 1, 2u));
  *((_QWORD *)v10 + 5) = v13;
  if ( !v13 )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147024882);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 29;
LABEL_16:
    WPP_SF_(*((_QWORD *)v19 + 2), v20, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
LABEL_17:
    std::unique_ptr<CClassInfo>::~unique_ptr<CClassInfo>(&v22);
    return 2147942414LL;
  }
  do
    ++v11;
  while ( a4[v11] );
  StringCchCopyW(v13, v11 + 1, a4);
  *((_DWORD *)v10 + 12) = 1;
  *((_DWORD *)v10 + 13) = a6;
  v14 = (_QWORD *)off_1800D7090;
  if ( (struct _LIST_ENTRY *)*off_1800D7090 != &g_ClassInfoHead )
    __fastfail(3u);
  v15 = (_QWORD *)((char *)v10 + 8);
  *v15 = &g_ClassInfoHead;
  v15[1] = v14;
  *v14 = v15;
  off_1800D7090 = v15;
  std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v22);
  std::unique_ptr<CClassInfo>::~unique_ptr<CClassInfo>(&v22);
  return 0;
}

```

## disassembly

```asm
0x18004f754  mov     [rsp+arg_8], rbx
0x18004f759  mov     [rsp+arg_10], rbp
0x18004f75e  mov     [rsp+arg_0], rcx
0x18004f763  push    rsi
0x18004f764  push    rdi
0x18004f765  push    r14
0x18004f767  sub     rsp, 20h
0x18004f76b  mov     rsi, r9
0x18004f76e  mov     rdi, r8
0x18004f771  mov     rbp, rdx
0x18004f774  xor     r14d, r14d
0x18004f777  test    r8, r8
0x18004f77a  jz      loc_18004F8A8
0x18004f780  lea     ecx, [r14+40h]
0x18004f784  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004f78a  mov     [rsp+38h+arg_0], rax
0x18004f78f  test    rax, rax
0x18004f792  jz      loc_18004F8A0
0x18004f798  lea     rcx, ??_7CClassInfo@@6B@; const CClassInfo::`vftable'
0x18004f79f  mov     [rax], rcx
0x18004f7a2  mov     [rax+18h], r14
0x18004f7a6  mov     [rax+20h], r14
0x18004f7aa  mov     [rax+28h], r14
0x18004f7ae  mov     [rax+30h], r14d
0x18004f7b2  mov     [rax+38h], r14d
0x18004f7b6  mov     rdx, rax
0x18004f7b9  lea     rcx, [rsp+38h+arg_0]
0x18004f7be  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18004f7c3  nop
0x18004f7c4  mov     rbx, [rsp+38h+arg_0]
0x18004f7c9  test    rbx, rbx
0x18004f7cc  jz      loc_18004F91C
0x18004f7d2  mov     rcx, rdi
0x18004f7d5  call    cs:__imp_?InternalAddRef@CUnkInternal@@QEAAKXZ; CUnkInternal::InternalAddRef(void)
0x18004f7db  lea     rcx, [rsp+38h+arg_0]
0x18004f7e0  call    ??C?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEBAPEAUCClassInfo@@XZ; std::unique_ptr<CClassInfo>::operator->(void)
0x18004f7e5  mov     [rax+20h], rdi
0x18004f7e9  mov     [rbx+18h], rbp
0x18004f7ed  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f7f1  mov     rcx, rdi
0x18004f7f4  inc     rcx
0x18004f7f7  cmp     [rsi+rcx*2], r14w
0x18004f7fc  jnz     short loc_18004F7F4
0x18004f7fe  inc     rcx
0x18004f801  mov     eax, 2
0x18004f806  mul     rcx
0x18004f809  cmovb   rax, rdi
0x18004f80d  mov     rcx, rax
0x18004f810  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004f816  mov     [rbx+28h], rax
0x18004f81a  test    rax, rax
0x18004f81d  jz      loc_18004F956
0x18004f823  inc     rdi
0x18004f826  cmp     [rsi+rdi*2], r14w
0x18004f82b  jnz     short loc_18004F823
0x18004f82d  lea     rdx, [rdi+1]; unsigned __int64
0x18004f831  mov     r8, rsi; unsigned __int16 *
0x18004f834  mov     rcx, rax; unsigned __int16 *
0x18004f837  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f83c  mov     dword ptr [rbx+30h], 1
0x18004f843  mov     eax, [rsp+38h+arg_28]
0x18004f847  mov     [rbx+34h], eax
0x18004f84a  mov     rax, cs:off_1800D7090
0x18004f851  lea     rcx, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x18004f858  cmp     [rax], rcx
0x18004f85b  jnz     loc_18004F992
0x18004f861  add     rbx, 8
0x18004f865  mov     [rbx], rcx
0x18004f868  mov     [rbx+8], rax
0x18004f86c  mov     [rax], rbx
0x18004f86f  mov     cs:off_1800D7090, rbx
0x18004f876  lea     rcx, [rsp+38h+arg_0]
0x18004f87b  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18004f880  nop
0x18004f881  lea     rcx, [rsp+38h+arg_0]
0x18004f886  call    ??1?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<CClassInfo>::~unique_ptr<CClassInfo>(void)
0x18004f88b  xor     eax, eax
0x18004f88d  mov     rbx, [rsp+38h+arg_8]
0x18004f892  mov     rbp, [rsp+38h+arg_10]
0x18004f897  add     rsp, 20h
0x18004f89b  pop     r14
0x18004f89d  pop     rdi
0x18004f89e  pop     rsi
0x18004f89f  retn
0x18004f8a0  mov     rax, r14
0x18004f8a3  jmp     loc_18004F7B6
0x18004f8a8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004f8ae  mov     edx, 8007000Eh
0x18004f8b3  mov     rcx, rax
0x18004f8b6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004f8bc  lea     rax, WPP_GLOBAL_Control
0x18004f8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f8ca  cmp     rcx, rax
0x18004f8cd  jz      short loc_18004F912
0x18004f8cf  test    byte ptr [rcx+1Ch], 1
0x18004f8d3  jz      short loc_18004F912
0x18004f8d5  cmp     byte ptr [rcx+19h], 2
0x18004f8d9  jb      short loc_18004F912
0x18004f8db  mov     edx, 1Bh
0x18004f8e0  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x18004f8e7  mov     rcx, [rcx+10h]
0x18004f8eb  call    WPP_SF_
0x18004f8f0  jmp     short loc_18004F912
0x18004f8f2  mov     edx, 1Dh
0x18004f8f7  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x18004f8fe  mov     rcx, [rcx+10h]
0x18004f902  call    WPP_SF_
0x18004f907  nop
0x18004f908  lea     rcx, [rsp+38h+arg_0]
0x18004f90d  call    ??1?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<CClassInfo>::~unique_ptr<CClassInfo>(void)
0x18004f912  mov     eax, 8007000Eh
0x18004f917  jmp     loc_18004F88D
0x18004f91c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004f922  mov     edx, 8007000Eh
0x18004f927  mov     rcx, rax
0x18004f92a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004f930  lea     rax, WPP_GLOBAL_Control
0x18004f937  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f93e  cmp     rcx, rax
0x18004f941  jz      short loc_18004F908
0x18004f943  test    byte ptr [rcx+1Ch], 1
0x18004f947  jz      short loc_18004F908
0x18004f949  cmp     byte ptr [rcx+19h], 2
0x18004f94d  jb      short loc_18004F908
0x18004f94f  mov     edx, 1Ch
0x18004f954  jmp     short loc_18004F8F7
0x18004f956  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004f95c  mov     edx, 8007000Eh
0x18004f961  mov     rcx, rax
0x18004f964  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004f96a  lea     rax, WPP_GLOBAL_Control
0x18004f971  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f978  cmp     rcx, rax
0x18004f97b  jz      short loc_18004F908
0x18004f97d  test    byte ptr [rcx+1Ch], 1
0x18004f981  jz      short loc_18004F908
0x18004f983  cmp     byte ptr [rcx+19h], 2
0x18004f987  jb      loc_18004F908
0x18004f98d  jmp     loc_18004F8F2
0x18004f992  mov     ecx, 3
0x18004f997  int     29h; Win8: RtlFailFast(ecx)
```
