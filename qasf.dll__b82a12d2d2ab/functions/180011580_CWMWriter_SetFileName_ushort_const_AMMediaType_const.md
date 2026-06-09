# CWMWriter::SetFileName(ushort const *,_AMMediaType const *)

- ea: `0x180011580`
- end: `0x180011687`
- name: `?SetFileName@CWMWriter@@UEAAJPEBGPEBU_AMMediaType@@@Z`
- size: `263`
- prototype: `int(CWMWriter *__hidden this, const unsigned __int16 *, const struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180001014`
- `0x180002660`
- `0x18000f414`
- `0x180010948`
- `0x180011580`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800115a5`
- `KERNEL32!EnterCriticalSection` at `0x1800115a5`
- `KERNEL32!LeaveCriticalSection` at `0x180011676`
- `KERNEL32!LeaveCriticalSection` at `0x180011676`
- `KERNEL32!lstrlenW` at `0x1800115be`
- `KERNEL32!lstrlenW` at `0x1800115be`

## pseudocode

```c
__int64 __fastcall CWMWriter::SetFileName(CWMWriter *this, const unsigned __int16 *a2, const struct _AMMediaType *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  HRESULT WMWriter; // ebx
  int v8; // eax
  void *v9; // rcx
  int v10; // ebp
  unsigned __int64 v11; // rbp
  unsigned __int16 *v12; // rax
  char *v13; // rdi
  CWMWriter *v14; // rcx
  HRESULT v15; // eax

  if ( !a2 )
    return 2147500035LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( !*((_DWORD *)this - 24) )
  {
    v8 = lstrlenW(a2);
    v9 = (void *)*((_QWORD *)this + 19);
    v10 = v8;
    if ( v9 )
    {
      operator delete(v9);
      *((_QWORD *)this + 19) = 0;
    }
    v11 = v10 + 1;
    v12 = (unsigned __int16 *)operator new[](saturated_mul(v11, 2u));
    *((_QWORD *)this + 19) = v12;
    if ( !v12 )
    {
      WMWriter = -2147024882;
      goto LABEL_17;
    }
    StringCchCopyW(v12, v11, a2);
    if ( !*((_QWORD *)this - 5) )
    {
LABEL_16:
      WMWriter = 0;
      goto LABEL_17;
    }
    v13 = (char *)this - 136;
    v14 = (CWMWriter *)((char *)this - 136);
    if ( *((_QWORD *)this + 22) )
    {
      v15 = CWMWriter::Open(v14);
    }
    else
    {
      WMWriter = CWMWriter::CreateWMWriter(v14);
      if ( WMWriter < 0 )
        goto LABEL_15;
      v15 = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)v13 + 19) + 40LL))(v13 + 152, v13 + 364);
    }
    WMWriter = v15;
LABEL_15:
    if ( WMWriter < 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  WMWriter = -2147220953;
LABEL_17:
  LeaveCriticalSection(v6);
  return (unsigned int)WMWriter;
}

```

## disassembly

```asm
0x180011580  push    rbx
0x180011582  push    rbp
0x180011583  push    rsi
0x180011584  push    rdi
0x180011585  sub     rsp, 28h
0x180011589  mov     rdi, rdx
0x18001158c  mov     rbx, rcx
0x18001158f  test    rdx, rdx
0x180011592  jnz     short loc_18001159E
0x180011594  mov     eax, 80004003h
0x180011599  jmp     loc_18001167E
0x18001159e  lea     rsi, [rcx+68h]
0x1800115a2  mov     rcx, rsi; lpCriticalSection
0x1800115a5  call    cs:__imp_EnterCriticalSection
0x1800115ab  cmp     dword ptr [rbx-60h], 0
0x1800115af  jz      short loc_1800115BB
0x1800115b1  mov     ebx, 80040227h
0x1800115b6  jmp     loc_180011673
0x1800115bb  mov     rcx, rdi; lpString
0x1800115be  call    cs:__imp_lstrlenW
0x1800115c4  mov     rcx, [rbx+98h]; void *
0x1800115cb  mov     ebp, eax
0x1800115cd  test    rcx, rcx
0x1800115d0  jz      short loc_1800115E2
0x1800115d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800115d7  mov     qword ptr [rbx+98h], 0
0x1800115e2  lea     eax, [rbp+1]
0x1800115e5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800115ec  movsxd  rbp, eax
0x1800115ef  mov     eax, 2
0x1800115f4  mul     rbp
0x1800115f7  cmovb   rax, rcx
0x1800115fb  mov     rcx, rax; unsigned __int64
0x1800115fe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011603  mov     [rbx+98h], rax
0x18001160a  test    rax, rax
0x18001160d  jnz     short loc_180011616
0x18001160f  mov     ebx, 8007000Eh
0x180011614  jmp     short loc_180011673
0x180011616  mov     r8, rdi; unsigned __int16 *
0x180011619  mov     rdx, rbp; unsigned __int64
0x18001161c  mov     rcx, rax; unsigned __int16 *
0x18001161f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011624  cmp     qword ptr [rbx-28h], 0
0x180011629  jz      short loc_180011671
0x18001162b  cmp     qword ptr [rbx+0B0h], 0
0x180011633  lea     rdi, [rbx-88h]
0x18001163a  mov     rcx, rdi; this
0x18001163d  jnz     short loc_180011666
0x18001163f  call    ?CreateWMWriter@CWMWriter@@QEAAJXZ; CWMWriter::CreateWMWriter(void)
0x180011644  mov     ebx, eax
0x180011646  test    eax, eax
0x180011648  js      short loc_18001166D
0x18001164a  lea     rcx, [rdi+98h]
0x180011651  mov     rax, [rcx]
0x180011654  lea     rdx, [rdi+16Ch]
0x18001165b  mov     rax, [rax+28h]
0x18001165f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011664  jmp     short loc_18001166B
0x180011666  call    ?Open@CWMWriter@@QEAAJXZ; CWMWriter::Open(void)
0x18001166b  mov     ebx, eax
0x18001166d  test    ebx, ebx
0x18001166f  js      short loc_180011673
0x180011671  xor     ebx, ebx
0x180011673  mov     rcx, rsi; lpCriticalSection
0x180011676  call    cs:__imp_LeaveCriticalSection
0x18001167c  mov     eax, ebx
0x18001167e  add     rsp, 28h
0x180011682  pop     rdi
0x180011683  pop     rsi
0x180011684  pop     rbp
0x180011685  pop     rbx
0x180011686  retn
```
