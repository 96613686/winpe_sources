# CSnapin::CSnapin(CComponentData *)

- ea: `0x18001b700`
- end: `0x18001b897`
- name: `??0CSnapin@@QEAA@PEAVCComponentData@@@Z`
- size: `407`
- prototype: `CSnapin *__fastcall(CSnapin *__hidden this, struct CComponentData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005a10`

## callees

- `0x18001435c`
- `0x18001b658`
- `0x18001b700`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001b7c0`
- `KERNEL32!InitializeCriticalSection` at `0x18001b7c0`

## pseudocode

```c
CSnapin *__fastcall CSnapin::CSnapin(CSnapin *this, struct CComponentData *a2)
{
  CSnapin *result; // rax

  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_WORD *)this + 40) = 0;
  *(_QWORD *)this = &CSnapin::`vftable'{for `IComponent'};
  *((_QWORD *)this + 1) = &CSnapin::`vftable'{for `IExtendPropertySheet'};
  *((_QWORD *)this + 2) = &CSnapin::`vftable'{for `IExtendContextMenu'};
  *((_QWORD *)this + 3) = &CSnapin::`vftable'{for `IResultDataCompare'};
  *((_QWORD *)this + 4) = &CSnapin::`vftable'{for `IResultOwnerData'};
  *((_QWORD *)this + 5) = &CSnapin::`vftable'{for `IResultPrshtActions'};
  *((_QWORD *)this + 6) = &CSnapin::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 7) = &CSnapin::`vftable'{for `CDLink'};
  if ( !CDll::s_cObjs )
    InitGlobals();
  _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
  *((_DWORD *)this + 21) = 1;
  CResultRecs::CResultRecs((CSnapin *)((char *)this + 88));
  *((_QWORD *)this + 183) = 0;
  *((_DWORD *)this + 380) = 0;
  *((_QWORD *)this + 191) = 0;
  *((_QWORD *)this + 192) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1544));
  *((_QWORD *)this + 198) = 0;
  *((_DWORD *)this + 373) = 82;
  *((_DWORD *)this + 379) = 82;
  result = this;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 205) = 0;
  *((_QWORD *)this + 206) = 0;
  *((_QWORD *)this + 207) = 0;
  *((_QWORD *)this + 199) = a2;
  *((_DWORD *)this + 400) = 8;
  *((_DWORD *)this + 368) = 149;
  *((_DWORD *)this + 369) = 47;
  *((_DWORD *)this + 370) = 162;
  *((_DWORD *)this + 371) = 55;
  *((_DWORD *)this + 372) = 90;
  *((_DWORD *)this + 374) = 73;
  *((_DWORD *)this + 375) = 134;
  *((_DWORD *)this + 376) = 69;
  *((_DWORD *)this + 377) = 49;
  *((_DWORD *)this + 378) = 97;
  return result;
}

```

## disassembly

```asm
0x18001b700  mov     [rsp+arg_0], rbx
0x18001b705  mov     [rsp+arg_8], rsi
0x18001b70a  push    rdi
0x18001b70b  sub     rsp, 20h
0x18001b70f  xor     esi, esi
0x18001b711  lea     rax, ??_7CSnapin@@6BIComponent@@@; const CSnapin::`vftable'{for `IComponent'}
0x18001b718  mov     [rcx+40h], rsi
0x18001b71c  mov     rdi, rdx
0x18001b71f  mov     [rcx+48h], rsi
0x18001b723  mov     rbx, rcx
0x18001b726  mov     [rcx+50h], si
0x18001b72a  mov     [rcx], rax
0x18001b72d  lea     rax, ??_7CSnapin@@6BIExtendPropertySheet@@@; const CSnapin::`vftable'{for `IExtendPropertySheet'}
0x18001b734  mov     [rcx+8], rax
0x18001b738  lea     rax, ??_7CSnapin@@6BIExtendContextMenu@@@; const CSnapin::`vftable'{for `IExtendContextMenu'}
0x18001b73f  mov     [rcx+10h], rax
0x18001b743  lea     rax, ??_7CSnapin@@6BIResultDataCompare@@@; const CSnapin::`vftable'{for `IResultDataCompare'}
0x18001b74a  mov     [rcx+18h], rax
0x18001b74e  lea     rax, ??_7CSnapin@@6BIResultOwnerData@@@; const CSnapin::`vftable'{for `IResultOwnerData'}
0x18001b755  mov     [rcx+20h], rax
0x18001b759  lea     rax, ??_7CSnapin@@6BIResultPrshtActions@@@; const CSnapin::`vftable'{for `IResultPrshtActions'}
0x18001b760  mov     [rcx+28h], rax
0x18001b764  lea     rax, ??_7CSnapin@@6BIPersistStream@@@; const CSnapin::`vftable'{for `IPersistStream'}
0x18001b76b  mov     [rcx+30h], rax
0x18001b76f  lea     rax, ??_7CSnapin@@6BCDLink@@@; const CSnapin::`vftable'{for `CDLink'}
0x18001b776  mov     [rcx+38h], rax
0x18001b77a  cmp     cs:?s_cObjs@CDll@@2KA, esi; ulong CDll::s_cObjs
0x18001b780  jnz     short loc_18001B787
0x18001b782  call    ?InitGlobals@@YAXXZ; InitGlobals(void)
0x18001b787  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x18001b78e  lea     rcx, [rbx+58h]; this
0x18001b792  mov     dword ptr [rbx+54h], 1
0x18001b799  call    ??0CResultRecs@@QEAA@XZ; CResultRecs::CResultRecs(void)
0x18001b79e  mov     [rbx+5B8h], rsi
0x18001b7a5  lea     rcx, [rbx+608h]; lpCriticalSection
0x18001b7ac  mov     [rbx+5F0h], esi
0x18001b7b2  mov     [rbx+5F8h], rsi
0x18001b7b9  mov     [rbx+600h], rsi
0x18001b7c0  call    cs:__imp_InitializeCriticalSection
0x18001b7c6  mov     eax, 52h ; 'R'
0x18001b7cb  mov     [rbx+630h], rsi
0x18001b7d2  mov     [rbx+5D4h], eax
0x18001b7d8  mov     [rbx+5ECh], eax
0x18001b7de  mov     rax, rbx
0x18001b7e1  mov     [rbx+648h], rsi
0x18001b7e8  mov     [rbx+650h], rsi
0x18001b7ef  mov     [rbx+658h], rsi
0x18001b7f6  mov     [rbx+660h], rsi
0x18001b7fd  mov     [rbx+668h], rsi
0x18001b804  mov     [rbx+670h], rsi
0x18001b80b  mov     [rbx+678h], rsi
0x18001b812  mov     rsi, [rsp+28h+arg_8]
0x18001b817  mov     [rbx+638h], rdi
0x18001b81e  mov     dword ptr [rbx+640h], 8
0x18001b828  mov     dword ptr [rbx+5C0h], 95h
0x18001b832  mov     dword ptr [rbx+5C4h], 2Fh ; '/'
0x18001b83c  mov     dword ptr [rbx+5C8h], 0A2h
0x18001b846  mov     dword ptr [rbx+5CCh], 37h ; '7'
0x18001b850  mov     dword ptr [rbx+5D0h], 5Ah ; 'Z'
0x18001b85a  mov     dword ptr [rbx+5D8h], 49h ; 'I'
0x18001b864  mov     dword ptr [rbx+5DCh], 86h
0x18001b86e  mov     dword ptr [rbx+5E0h], 45h ; 'E'
0x18001b878  mov     dword ptr [rbx+5E4h], 31h ; '1'
0x18001b882  mov     dword ptr [rbx+5E8h], 61h ; 'a'
0x18001b88c  mov     rbx, [rsp+28h+arg_0]
0x18001b891  add     rsp, 20h
0x18001b895  pop     rdi
0x18001b896  retn
```
