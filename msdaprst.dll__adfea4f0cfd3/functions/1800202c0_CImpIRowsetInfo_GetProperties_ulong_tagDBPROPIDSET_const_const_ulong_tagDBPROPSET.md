# CImpIRowsetInfo::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x1800202c0`
- end: `0x1800203d5`
- name: `?GetProperties@CImpIRowsetInfo@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `277`
- prototype: `int(CImpIRowsetInfo *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180016584`
- `0x1800202c0`
- `0x18002d31c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002030d`
- `KERNEL32!GetCurrentThreadId` at `0x18002030d`
- `KERNEL32!LeaveCriticalSection` at `0x1800203ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800203ab`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020332`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020332`
- `MSDART!UMSEnterCSWraper` at `0x1800202f3`
- `MSDART!UMSEnterCSWraper` at `0x1800202f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIRowsetInfo::GetProperties(
        CImpIRowsetInfo *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  __int64 v9; // rbx
  _DWORD *v10; // rdi
  _DWORD *v11; // rsi
  int Properties; // eax
  unsigned int v13; // r14d
  __int64 v15; // rcx
  int v17; // [rsp+30h] [rbp-58h] BYREF
  __int64 v18; // [rsp+38h] [rbp-50h]
  _DWORD *v19; // [rsp+40h] [rbp-48h]
  _DWORD *v20; // [rsp+48h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-38h]

  v9 = *((_QWORD *)this + 3) + 128LL;
  v18 = v9;
  UMSEnterCSWraper(v9);
  v10 = (_DWORD *)(v9 + 12);
  v19 = (_DWORD *)(v9 + 12);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*v10;
  v11 = (_DWORD *)(v9 + 16);
  v20 = (_DWORD *)(v9 + 16);
  ++*(_DWORD *)(v9 + 16);
  v21 = v9;
  SetErrorInfo(0, 0);
  try
  {
    Properties = CUtlProps::utlGetProperties(
                   (CUtlProps *)(*((_QWORD *)this + 3) + 400LL),
                   a2,
                   a3,
                   a4,
                   a5,
                   (const struct CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
  }
  catch ( long v17 )
  {
    Properties = v17;
    v9 = v18;
    v10 = v19;
    v11 = v20;
  }
  v13 = Exit(Properties, 0xBB9u);
  --*v11;
  if ( (*v10)-- == 1 )
    *(_DWORD *)(v9 + 8) = -1;
  v15 = *(_QWORD *)v9;
  --*(_DWORD *)(v15 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  return v13;
}

```

## disassembly

```asm
0x1800202c0  mov     [rsp+arg_8], rbx
0x1800202c5  mov     [rsp+arg_10], rsi
0x1800202ca  push    rdi
0x1800202cb  push    r12
0x1800202cd  push    r13
0x1800202cf  push    r14
0x1800202d1  push    r15
0x1800202d3  sub     rsp, 60h
0x1800202d7  mov     r15, r9
0x1800202da  mov     r12, r8
0x1800202dd  mov     r13d, edx
0x1800202e0  mov     r14, rcx
0x1800202e3  mov     rbx, [rcx+18h]
0x1800202e7  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800202eb  mov     [rsp+88h+var_50], rbx
0x1800202f0  mov     rcx, rbx
0x1800202f3  call    cs:__imp_UMSEnterCSWraper
0x1800202fa  nop     dword ptr [rax+rax+00h]
0x1800202ff  lea     rdi, [rbx+0Ch]
0x180020303  mov     [rsp+88h+var_48], rdi
0x180020308  cmp     dword ptr [rdi], 0
0x18002030b  jnz     short loc_18002031C
0x18002030d  call    cs:__imp_GetCurrentThreadId
0x180020314  nop     dword ptr [rax+rax+00h]
0x180020319  mov     [rbx+8], eax
0x18002031c  inc     dword ptr [rdi]
0x18002031e  lea     rsi, [rbx+10h]
0x180020322  mov     [rsp+88h+var_40], rsi
0x180020327  inc     dword ptr [rsi]
0x180020329  mov     [rsp+88h+var_38], rbx
0x18002032e  xor     edx, edx; perrinfo
0x180020330  xor     ecx, ecx; dwReserved
0x180020332  call    cs:__imp_SetErrorInfo
0x180020339  nop     dword ptr [rax+rax+00h]
0x18002033e  mov     rcx, [r14+18h]
0x180020342  lea     rax, [rcx+70h]
0x180020346  add     rcx, 190h; this
0x18002034d  mov     [rsp+88h+var_60], rax; struct CBidGenericBase *
0x180020352  mov     rax, [rsp+88h+arg_20]
0x18002035a  mov     [rsp+88h+var_68], rax; struct tagDBPROPSET **
0x18002035f  mov     r9, r15; unsigned int *
0x180020362  mov     r8, r12; struct tagDBPROPIDSET *
0x180020365  mov     edx, r13d; unsigned int
0x180020368  call    ?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x18002036d  nop
0x18002036e  jmp     short loc_180020386
0x180020370  mov     eax, [rsp+88h+arg_0]
0x180020377  mov     rbx, [rsp+88h+var_50]
0x18002037c  mov     rdi, [rsp+88h+var_48]
0x180020381  mov     rsi, [rsp+88h+var_40]
0x180020386  mov     edx, 0BB9h; unsigned int
0x18002038b  mov     ecx, eax; int
0x18002038d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180020392  mov     r14d, eax
0x180020395  or      eax, 0FFFFFFFFh
0x180020398  add     [rsi], eax
0x18002039a  add     [rdi], eax
0x18002039c  jnz     short loc_1800203A1
0x18002039e  mov     [rbx+8], eax
0x1800203a1  mov     rcx, [rbx]
0x1800203a4  dec     dword ptr [rcx+30h]
0x1800203a7  add     rcx, 8; lpCriticalSection
0x1800203ab  call    cs:__imp_LeaveCriticalSection
0x1800203b2  nop     dword ptr [rax+rax+00h]
0x1800203b7  mov     eax, r14d
0x1800203ba  lea     r11, [rsp+88h+var_28]
0x1800203bf  mov     rbx, [r11+38h]
0x1800203c3  mov     rsi, [r11+40h]
0x1800203c7  mov     rsp, r11
0x1800203ca  pop     r15
0x1800203cc  pop     r14
0x1800203ce  pop     r13
0x1800203d0  pop     r12
0x1800203d2  pop     rdi
0x1800203d3  retn
```
