# CImpIRowsetInfo::GetReferencedRowset(unsigned __int64,_GUID const &,IUnknown * *)

- ea: `0x1800203e0`
- end: `0x1800204bd`
- name: `?GetReferencedRowset@CImpIRowsetInfo@@UEAAJ_KAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(CImpIRowsetInfo *__hidden this, unsigned __int64, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180016584`
- `0x1800203e0`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002041a`
- `KERNEL32!GetCurrentThreadId` at `0x18002041a`
- `KERNEL32!LeaveCriticalSection` at `0x1800204a1`
- `KERNEL32!LeaveCriticalSection` at `0x1800204a1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020437`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020437`
- `MSDART!UMSEnterCSWraper` at `0x180020404`
- `MSDART!UMSEnterCSWraper` at `0x180020404`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetInfo::GetReferencedRowset(
        CImpIRowsetInfo *this,
        unsigned __int64 a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  unsigned int *v10; // rcx
  int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // esi
  __int64 v15; // rcx

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( a4 )
  {
    *a4 = 0;
    v10 = (unsigned int *)*((_QWORD *)this + 3);
    if ( a2 <= v10[38] )
    {
      v12 = (*(__int64 (__fastcall **)(unsigned int *, _QWORD, const struct _GUID *, struct IUnknown **))(*(_QWORD *)v10 + 40LL))(
              v10,
              (unsigned int)a2,
              a3,
              a4);
      goto LABEL_9;
    }
    v11 = -2147217835;
  }
  else
  {
    v11 = -2147024809;
  }
  v12 = Exit(v11, 0);
LABEL_9:
  v13 = v12;
  --*(_DWORD *)(v8 + 16);
  if ( (*(_DWORD *)(v8 + 12))-- == 1 )
    *v9 = -1;
  v15 = *(_QWORD *)v8;
  --*(_DWORD *)(v15 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  return v13;
}

```

## disassembly

```asm
0x1800203e0  push    rbx
0x1800203e2  push    rbp
0x1800203e3  push    rsi
0x1800203e4  push    rdi
0x1800203e5  push    r14
0x1800203e7  push    r15
0x1800203e9  sub     rsp, 38h
0x1800203ed  mov     rsi, r9
0x1800203f0  mov     r15, r8
0x1800203f3  mov     r14, rdx
0x1800203f6  mov     rbp, rcx
0x1800203f9  mov     rbx, [rcx+18h]
0x1800203fd  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180020401  mov     rcx, rbx
0x180020404  call    cs:__imp_UMSEnterCSWraper
0x18002040b  nop     dword ptr [rax+rax+00h]
0x180020410  lea     rdi, [rbx+8]
0x180020414  cmp     dword ptr [rbx+0Ch], 0
0x180020418  jnz     short loc_180020428
0x18002041a  call    cs:__imp_GetCurrentThreadId
0x180020421  nop     dword ptr [rax+rax+00h]
0x180020426  mov     [rdi], eax
0x180020428  inc     dword ptr [rbx+0Ch]
0x18002042b  inc     dword ptr [rbx+10h]
0x18002042e  mov     [rsp+68h+arg_0], rbx
0x180020433  xor     edx, edx; perrinfo
0x180020435  xor     ecx, ecx; dwReserved
0x180020437  call    cs:__imp_SetErrorInfo
0x18002043e  nop     dword ptr [rax+rax+00h]
0x180020443  test    rsi, rsi
0x180020446  jz      short loc_18002047C
0x180020448  mov     qword ptr [rsi], 0
0x18002044f  mov     rcx, [rbp+18h]
0x180020453  mov     eax, [rcx+98h]
0x180020459  cmp     r14, rax
0x18002045c  jbe     short loc_180020465
0x18002045e  mov     ecx, 80040E55h
0x180020463  jmp     short loc_180020481
0x180020465  mov     rax, [rcx]
0x180020468  mov     edx, r14d
0x18002046b  mov     r9, rsi
0x18002046e  mov     r8, r15
0x180020471  mov     rax, [rax+28h]
0x180020475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002047a  jmp     short loc_180020488
0x18002047c  mov     ecx, 80070057h; int
0x180020481  xor     edx, edx; unsigned int
0x180020483  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180020488  mov     esi, eax
0x18002048a  or      edx, 0FFFFFFFFh
0x18002048d  add     [rbx+10h], edx
0x180020490  add     [rbx+0Ch], edx
0x180020493  jnz     short loc_180020497
0x180020495  mov     [rdi], edx
0x180020497  mov     rcx, [rbx]
0x18002049a  dec     dword ptr [rcx+30h]
0x18002049d  add     rcx, 8; lpCriticalSection
0x1800204a1  call    cs:__imp_LeaveCriticalSection
0x1800204a8  nop     dword ptr [rax+rax+00h]
0x1800204ad  mov     eax, esi
0x1800204af  add     rsp, 38h
0x1800204b3  pop     r15
0x1800204b5  pop     r14
0x1800204b7  pop     rdi
0x1800204b8  pop     rsi
0x1800204b9  pop     rbp
0x1800204ba  pop     rbx
0x1800204bb  retn
```
