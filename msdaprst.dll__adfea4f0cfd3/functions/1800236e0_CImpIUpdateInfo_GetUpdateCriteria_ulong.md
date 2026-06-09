# CImpIUpdateInfo::GetUpdateCriteria(ulong *)

- ea: `0x1800236e0`
- end: `0x18002377b`
- name: `?GetUpdateCriteria@CImpIUpdateInfo@@UEAAJPEAK@Z`
- size: `155`
- prototype: `__int64 __fastcall(CImpIUpdateInfo *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180016584`
- `0x1800236e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002370c`
- `KERNEL32!GetCurrentThreadId` at `0x18002370c`
- `KERNEL32!LeaveCriticalSection` at `0x18002375c`
- `KERNEL32!LeaveCriticalSection` at `0x18002375c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002372a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002372a`
- `MSDART!UMSEnterCSWraper` at `0x1800236fa`
- `MSDART!UMSEnterCSWraper` at `0x1800236fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIUpdateInfo::GetUpdateCriteria(CImpIUpdateInfo *this, unsigned int *a2)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v2);
  if ( !*(_DWORD *)(v2 + 12) )
    *(_DWORD *)(v2 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v2 + 12);
  ++*(_DWORD *)(v2 + 16);
  SetErrorInfo(0, 0);
  v3 = Exit(-2147467263, 0);
  --*(_DWORD *)(v2 + 16);
  if ( (*(_DWORD *)(v2 + 12))-- == 1 )
    *(_DWORD *)(v2 + 8) = -1;
  v5 = *(_QWORD *)v2;
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return v3;
}

```

## disassembly

```asm
0x1800236e0  mov     [rsp+arg_8], rbx
0x1800236e5  mov     [rsp+arg_10], rsi
0x1800236ea  push    rdi
0x1800236eb  sub     rsp, 20h
0x1800236ef  mov     rbx, [rcx+18h]
0x1800236f3  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800236f7  mov     rcx, rbx
0x1800236fa  call    cs:__imp_UMSEnterCSWraper
0x180023701  nop     dword ptr [rax+rax+00h]
0x180023706  cmp     dword ptr [rbx+0Ch], 0
0x18002370a  jnz     short loc_18002371B
0x18002370c  call    cs:__imp_GetCurrentThreadId
0x180023713  nop     dword ptr [rax+rax+00h]
0x180023718  mov     [rbx+8], eax
0x18002371b  inc     dword ptr [rbx+0Ch]
0x18002371e  inc     dword ptr [rbx+10h]
0x180023721  mov     [rsp+28h+arg_0], rbx
0x180023726  xor     edx, edx; perrinfo
0x180023728  xor     ecx, ecx; dwReserved
0x18002372a  call    cs:__imp_SetErrorInfo
0x180023731  nop     dword ptr [rax+rax+00h]
0x180023736  xor     edx, edx; unsigned int
0x180023738  mov     ecx, 80004001h; int
0x18002373d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180023742  mov     esi, eax
0x180023744  or      eax, 0FFFFFFFFh
0x180023747  add     [rbx+10h], eax
0x18002374a  add     [rbx+0Ch], eax
0x18002374d  jnz     short loc_180023752
0x18002374f  mov     [rbx+8], eax
0x180023752  mov     rcx, [rbx]
0x180023755  dec     dword ptr [rcx+30h]
0x180023758  add     rcx, 8; lpCriticalSection
0x18002375c  call    cs:__imp_LeaveCriticalSection
0x180023763  nop     dword ptr [rax+rax+00h]
0x180023768  mov     eax, esi
0x18002376a  mov     rbx, [rsp+28h+arg_8]
0x18002376f  mov     rsi, [rsp+28h+arg_10]
0x180023774  add     rsp, 20h
0x180023778  pop     rdi
0x180023779  retn
```
