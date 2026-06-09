# CImpIRowsetInfo::GetSpecification(_GUID const &,IUnknown * *)

- ea: `0x1800204d0`
- end: `0x1800205a6`
- name: `?GetSpecification@CImpIRowsetInfo@@UEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(CImpIRowsetInfo *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180016584`
- `0x1800204d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020503`
- `KERNEL32!GetCurrentThreadId` at `0x180020503`
- `KERNEL32!LeaveCriticalSection` at `0x180020556`
- `KERNEL32!LeaveCriticalSection` at `0x180020584`
- `KERNEL32!LeaveCriticalSection` at `0x180020556`
- `KERNEL32!LeaveCriticalSection` at `0x180020584`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020520`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020520`
- `MSDART!UMSEnterCSWraper` at `0x1800204ed`
- `MSDART!UMSEnterCSWraper` at `0x1800204ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetInfo::GetSpecification(
        CImpIRowsetInfo *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  __int64 v4; // rbx
  DWORD *v5; // rdi
  unsigned int v6; // esi
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // rcx

  v4 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v4);
  v5 = (DWORD *)(v4 + 8);
  if ( !*(_DWORD *)(v4 + 12) )
    *v5 = GetCurrentThreadId();
  ++*(_DWORD *)(v4 + 12);
  ++*(_DWORD *)(v4 + 16);
  SetErrorInfo(0, 0);
  if ( a3 )
  {
    *a3 = 0;
    --*(_DWORD *)(v4 + 16);
    v7 = (*(_DWORD *)(v4 + 12))-- == 1;
    if ( v7 )
      *v5 = -1;
    v10 = *(_QWORD *)v4;
    --*(_DWORD *)(v10 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
    return 1;
  }
  else
  {
    v6 = Exit(-2147024809, 0);
    --*(_DWORD *)(v4 + 16);
    v7 = (*(_DWORD *)(v4 + 12))-- == 1;
    if ( v7 )
      *v5 = -1;
    v8 = *(_QWORD *)v4;
    --*(_DWORD *)(v8 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    return v6;
  }
}

```

## disassembly

```asm
0x1800204d0  mov     [rsp+arg_8], rbx
0x1800204d5  mov     [rsp+arg_10], rsi
0x1800204da  push    rdi
0x1800204db  sub     rsp, 20h
0x1800204df  mov     rsi, r8
0x1800204e2  mov     rbx, [rcx+18h]
0x1800204e6  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800204ea  mov     rcx, rbx
0x1800204ed  call    cs:__imp_UMSEnterCSWraper
0x1800204f4  nop     dword ptr [rax+rax+00h]
0x1800204f9  lea     rdi, [rbx+8]
0x1800204fd  cmp     dword ptr [rbx+0Ch], 0
0x180020501  jnz     short loc_180020511
0x180020503  call    cs:__imp_GetCurrentThreadId
0x18002050a  nop     dword ptr [rax+rax+00h]
0x18002050f  mov     [rdi], eax
0x180020511  inc     dword ptr [rbx+0Ch]
0x180020514  inc     dword ptr [rbx+10h]
0x180020517  mov     [rsp+28h+arg_0], rbx
0x18002051c  xor     edx, edx; perrinfo
0x18002051e  xor     ecx, ecx; dwReserved
0x180020520  call    cs:__imp_SetErrorInfo
0x180020527  nop     dword ptr [rax+rax+00h]
0x18002052c  test    rsi, rsi
0x18002052f  jnz     short loc_180020566
0x180020531  xor     edx, edx; unsigned int
0x180020533  mov     ecx, 80070057h; int
0x180020538  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002053d  mov     esi, eax
0x18002053f  or      edx, 0FFFFFFFFh
0x180020542  add     [rbx+10h], edx
0x180020545  add     [rbx+0Ch], edx
0x180020548  jnz     short loc_18002054C
0x18002054a  mov     [rdi], edx
0x18002054c  mov     rcx, [rbx]
0x18002054f  dec     dword ptr [rcx+30h]
0x180020552  add     rcx, 8; lpCriticalSection
0x180020556  call    cs:__imp_LeaveCriticalSection
0x18002055d  nop     dword ptr [rax+rax+00h]
0x180020562  mov     eax, esi
0x180020564  jmp     short loc_180020595
0x180020566  mov     qword ptr [rsi], 0
0x18002056d  or      edx, 0FFFFFFFFh
0x180020570  add     [rbx+10h], edx
0x180020573  add     [rbx+0Ch], edx
0x180020576  jnz     short loc_18002057A
0x180020578  mov     [rdi], edx
0x18002057a  mov     rcx, [rbx]
0x18002057d  dec     dword ptr [rcx+30h]
0x180020580  add     rcx, 8; lpCriticalSection
0x180020584  call    cs:__imp_LeaveCriticalSection
0x18002058b  nop     dword ptr [rax+rax+00h]
0x180020590  mov     eax, 1
0x180020595  mov     rbx, [rsp+28h+arg_8]
0x18002059a  mov     rsi, [rsp+28h+arg_10]
0x18002059f  add     rsp, 20h
0x1800205a3  pop     rdi
0x1800205a4  retn
```
