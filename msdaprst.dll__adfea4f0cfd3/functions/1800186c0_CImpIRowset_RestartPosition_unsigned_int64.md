# CImpIRowset::RestartPosition(unsigned __int64)

- ea: `0x1800186c0`
- end: `0x180018798`
- name: `?RestartPosition@CImpIRowset@@UEAAJ_K@Z`
- size: `216`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001156c`
- `0x180016584`
- `0x1800186c0`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800186f0`
- `KERNEL32!GetCurrentThreadId` at `0x1800186f0`
- `KERNEL32!LeaveCriticalSection` at `0x180018780`
- `KERNEL32!LeaveCriticalSection` at `0x180018780`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001870d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001870d`
- `MSDART!UMSEnterCSWraper` at `0x1800186da`
- `MSDART!UMSEnterCSWraper` at `0x1800186da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowset::RestartPosition(CImpIRowset *this, __int64 a2)
{
  __int64 v4; // rbx
  DWORD *v5; // rdi
  __int64 v6; // r9
  int v7; // ecx
  unsigned int v8; // esi
  __int64 v10; // rcx

  v4 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v4);
  v5 = (DWORD *)(v4 + 8);
  if ( !*(_DWORD *)(v4 + 12) )
    *v5 = GetCurrentThreadId();
  ++*(_DWORD *)(v4 + 12);
  ++*(_DWORD *)(v4 + 16);
  SetErrorInfo(0, 0);
  if ( (unsigned int)CBitArray::ArrayEmpty(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL)) )
  {
    v7 = -2147217883;
  }
  else
  {
    *(_DWORD *)(v6 + 248) &= ~0x100u;
    *(_DWORD *)(*((_QWORD *)this + 3) + 240LL) = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3), a2);
  }
  v8 = Exit(v7, 0);
  --*(_DWORD *)(v4 + 16);
  if ( (*(_DWORD *)(v4 + 12))-- == 1 )
    *v5 = -1;
  v10 = *(_QWORD *)v4;
  --*(_DWORD *)(v10 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
  return v8;
}

```

## disassembly

```asm
0x1800186c0  push    rbx
0x1800186c2  push    rbp
0x1800186c3  push    rsi
0x1800186c4  push    rdi
0x1800186c5  sub     rsp, 28h
0x1800186c9  mov     rbp, rdx
0x1800186cc  mov     rsi, rcx
0x1800186cf  mov     rbx, [rcx+18h]
0x1800186d3  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800186d7  mov     rcx, rbx
0x1800186da  call    cs:__imp_UMSEnterCSWraper
0x1800186e1  nop     dword ptr [rax+rax+00h]
0x1800186e6  lea     rdi, [rbx+8]
0x1800186ea  cmp     dword ptr [rbx+0Ch], 0
0x1800186ee  jnz     short loc_1800186FE
0x1800186f0  call    cs:__imp_GetCurrentThreadId
0x1800186f7  nop     dword ptr [rax+rax+00h]
0x1800186fc  mov     [rdi], eax
0x1800186fe  inc     dword ptr [rbx+0Ch]
0x180018701  inc     dword ptr [rbx+10h]
0x180018704  mov     [rsp+48h+arg_0], rbx
0x180018709  xor     edx, edx; perrinfo
0x18001870b  xor     ecx, ecx; dwReserved
0x18001870d  call    cs:__imp_SetErrorInfo
0x180018714  nop     dword ptr [rax+rax+00h]
0x180018719  mov     r9, [rsi+18h]
0x18001871d  mov     rcx, [r9+0D0h]; this
0x180018724  call    ?ArrayEmpty@CBitArray@@QEAAJXZ; CBitArray::ArrayEmpty(void)
0x180018729  test    eax, eax
0x18001872b  jz      short loc_180018734
0x18001872d  mov     ecx, 80040E25h
0x180018732  jmp     short loc_180018760
0x180018734  btr     dword ptr [r9+0F8h], 8
0x18001873d  mov     rax, [rsi+18h]
0x180018741  mov     dword ptr [rax+0F0h], 0
0x18001874b  mov     rcx, [rsi+18h]
0x18001874f  mov     rax, [rcx]
0x180018752  mov     rdx, rbp
0x180018755  mov     rax, [rax+48h]
0x180018759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001875e  mov     ecx, eax; int
0x180018760  xor     edx, edx; unsigned int
0x180018762  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180018767  mov     esi, eax
0x180018769  or      edx, 0FFFFFFFFh
0x18001876c  add     [rbx+10h], edx
0x18001876f  add     [rbx+0Ch], edx
0x180018772  jnz     short loc_180018776
0x180018774  mov     [rdi], edx
0x180018776  mov     rcx, [rbx]
0x180018779  dec     dword ptr [rcx+30h]
0x18001877c  add     rcx, 8; lpCriticalSection
0x180018780  call    cs:__imp_LeaveCriticalSection
0x180018787  nop     dword ptr [rax+rax+00h]
0x18001878c  mov     eax, esi
0x18001878e  add     rsp, 28h
0x180018792  pop     rdi
0x180018793  pop     rsi
0x180018794  pop     rbp
0x180018795  pop     rbx
0x180018796  retn
```
