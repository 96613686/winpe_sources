# CPersistDSO::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180014840`
- end: `0x180014972`
- name: `?GetProperties@CPersistDSO@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `306`
- prototype: `int(CPersistDSO *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014840`
- `0x180016584`
- `0x18002d31c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001488e`
- `KERNEL32!GetCurrentThreadId` at `0x18001488e`
- `KERNEL32!LeaveCriticalSection` at `0x180014948`
- `KERNEL32!LeaveCriticalSection` at `0x180014948`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800148b3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800148b3`
- `MSDART!UMSEnterCSWraper` at `0x180014874`
- `MSDART!UMSEnterCSWraper` at `0x180014874`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::GetProperties(
        CPersistDSO *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  CPersistDSO *v8; // rbx
  _QWORD *v9; // r14
  _DWORD *v10; // rdi
  _DWORD *v11; // rsi
  int Properties; // eax
  unsigned int v13; // r15d
  __int64 v15; // rcx
  int v18; // [rsp+30h] [rbp-58h]
  int v19; // [rsp+30h] [rbp-58h]
  int v20; // [rsp+34h] [rbp-54h] BYREF
  char *v21; // [rsp+38h] [rbp-50h]
  _DWORD *v22; // [rsp+40h] [rbp-48h]
  _DWORD *v23; // [rsp+48h] [rbp-40h]
  _QWORD *v24; // [rsp+50h] [rbp-38h]

  v8 = this;
  v9 = (_QWORD *)((char *)this + 48);
  v21 = (char *)this + 48;
  UMSEnterCSWraper((char *)this + 48);
  v10 = (_DWORD *)((char *)v8 + 60);
  v22 = (_DWORD *)((char *)v8 + 60);
  if ( !*((_DWORD *)v8 + 15) )
    *((_DWORD *)v8 + 14) = GetCurrentThreadId();
  ++*v10;
  v11 = (_DWORD *)((char *)v8 + 64);
  v23 = (_DWORD *)((char *)v8 + 64);
  ++*((_DWORD *)v8 + 16);
  v24 = v9;
  SetErrorInfo(0, 0);
  try
  {
    *((GUID *)v8 + 6) = IID_IDBProperties;
    *((_DWORD *)v8 + 1053) = 0;
    Properties = CUtlProps::utlGetProperties(
                   (CPersistDSO *)((char *)v8 + 4600),
                   a2,
                   a3,
                   a4,
                   a5,
                   (CPersistDSO *)((char *)v8 + 4584));
  }
  catch ( long v20 )
  {
    v18 = v20;
    v11 = v23;
    v10 = v22;
    v9 = v21;
    Properties = v18;
    v8 = this;
  }
  catch ( ... )
  {
    v19 = -2147467259;
    v11 = v23;
    v10 = v22;
    v9 = v21;
    Properties = v19;
    v8 = this;
  }
  v13 = Exit(Properties, 0xBB9u);
  --*v11;
  if ( (*v10)-- == 1 )
    *((_DWORD *)v8 + 14) = -1;
  v15 = *v9;
  --*(_DWORD *)(v15 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  return v13;
}

```

## disassembly

```asm
0x180014840  mov     [rsp+arg_8], rbx
0x180014845  mov     [rsp+arg_10], rsi
0x18001484a  mov     [rsp+arg_0], rcx
0x18001484f  push    rdi
0x180014850  push    r12
0x180014852  push    r13
0x180014854  push    r14
0x180014856  push    r15
0x180014858  sub     rsp, 60h
0x18001485c  mov     r15, r9
0x18001485f  mov     r12, r8
0x180014862  mov     r13d, edx
0x180014865  mov     rbx, rcx
0x180014868  lea     r14, [rcx+30h]
0x18001486c  mov     [rsp+88h+var_50], r14
0x180014871  mov     rcx, r14
0x180014874  call    cs:__imp_UMSEnterCSWraper
0x18001487b  nop     dword ptr [rax+rax+00h]
0x180014880  lea     rdi, [rbx+3Ch]
0x180014884  mov     [rsp+88h+var_48], rdi
0x180014889  cmp     dword ptr [rdi], 0
0x18001488c  jnz     short loc_18001489D
0x18001488e  call    cs:__imp_GetCurrentThreadId
0x180014895  nop     dword ptr [rax+rax+00h]
0x18001489a  mov     [rbx+38h], eax
0x18001489d  inc     dword ptr [rdi]
0x18001489f  lea     rsi, [rbx+40h]
0x1800148a3  mov     [rsp+88h+var_40], rsi
0x1800148a8  inc     dword ptr [rsi]
0x1800148aa  mov     [rsp+88h+var_38], r14
0x1800148af  xor     edx, edx; perrinfo
0x1800148b1  xor     ecx, ecx; dwReserved
0x1800148b3  call    cs:__imp_SetErrorInfo
0x1800148ba  nop     dword ptr [rax+rax+00h]
0x1800148bf  movups  xmm0, xmmword ptr cs:IID_IDBProperties.Data1
0x1800148c6  movdqu  xmmword ptr [rbx+60h], xmm0
0x1800148cb  mov     dword ptr [rbx+1074h], 0
0x1800148d5  lea     rax, [rbx+11E8h]
0x1800148dc  lea     rcx, [rbx+11F8h]; this
0x1800148e3  mov     [rsp+88h+var_60], rax; struct CBidGenericBase *
0x1800148e8  mov     rax, [rsp+88h+arg_20]
0x1800148f0  mov     [rsp+88h+var_68], rax; struct tagDBPROPSET **
0x1800148f5  mov     r9, r15; unsigned int *
0x1800148f8  mov     r8, r12; struct tagDBPROPIDSET *
0x1800148fb  mov     edx, r13d; unsigned int
0x1800148fe  call    ?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x180014903  nop
0x180014904  jmp     short loc_180014923
0x180014906  jmp     short $+2
0x180014908  mov     rsi, [rsp+88h+var_40]
0x18001490d  mov     rdi, [rsp+88h+var_48]
0x180014912  mov     r14, [rsp+88h+var_50]
0x180014917  mov     eax, [rsp+88h+var_58]
0x18001491b  mov     rbx, [rsp+88h+arg_0]
0x180014923  mov     edx, 0BB9h; unsigned int
0x180014928  mov     ecx, eax; int
0x18001492a  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001492f  mov     r15d, eax
0x180014932  or      eax, 0FFFFFFFFh
0x180014935  add     [rsi], eax
0x180014937  add     [rdi], eax
0x180014939  jnz     short loc_18001493E
0x18001493b  mov     [rbx+38h], eax
0x18001493e  mov     rcx, [r14]
0x180014941  dec     dword ptr [rcx+30h]
0x180014944  add     rcx, 8; lpCriticalSection
0x180014948  call    cs:__imp_LeaveCriticalSection
0x18001494f  nop     dword ptr [rax+rax+00h]
0x180014954  mov     eax, r15d
0x180014957  lea     r11, [rsp+88h+var_28]
0x18001495c  mov     rbx, [r11+38h]
0x180014960  mov     rsi, [r11+40h]
0x180014964  mov     rsp, r11
0x180014967  pop     r15
0x180014969  pop     r14
0x18001496b  pop     r13
0x18001496d  pop     r12
0x18001496f  pop     rdi
0x180014970  retn
```
