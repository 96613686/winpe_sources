# CPersistDSO::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x1800154d0`
- end: `0x18001565e`
- name: `?SetProperties@CPersistDSO@@UEAAJKQEAUtagDBPROPSET@@@Z`
- size: `398`
- prototype: `int(CPersistDSO *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800154d0`
- `0x180016584`
- `0x18002d9a4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015518`
- `KERNEL32!GetCurrentThreadId` at `0x180015518`
- `KERNEL32!LeaveCriticalSection` at `0x1800155de`
- `KERNEL32!LeaveCriticalSection` at `0x18001563a`
- `KERNEL32!LeaveCriticalSection` at `0x1800155de`
- `KERNEL32!LeaveCriticalSection` at `0x18001563a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001553e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001553e`
- `MSDART!UMSEnterCSWraper` at `0x1800154fe`
- `MSDART!UMSEnterCSWraper` at `0x1800154fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::SetProperties(GUID *this, unsigned int a2, struct tagDBPROPSET *const a3)
{
  GUID *v6; // rbx
  unsigned __int8 *v7; // rdi
  unsigned int v8; // edx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // esi
  bool v12; // zf
  __int64 v13; // rcx
  unsigned int v15; // ebx
  __int64 v16; // rcx
  int v17; // [rsp+30h] [rbp-48h] BYREF
  GUID *v18; // [rsp+38h] [rbp-40h]
  unsigned __int8 *v19; // [rsp+40h] [rbp-38h]
  GUID *v20; // [rsp+48h] [rbp-30h]
  int v22; // [rsp+88h] [rbp+10h]
  GUID *v23; // [rsp+98h] [rbp+20h]

  v6 = this + 3;
  v23 = this + 3;
  UMSEnterCSWraper(&this[3]);
  v7 = &v6->Data4[4];
  v19 = &v6->Data4[4];
  if ( !*(_DWORD *)&v6->Data4[4] )
    *(_DWORD *)v6->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v7;
  v18 = v6 + 1;
  ++v6[1].Data1;
  v20 = v6;
  SetErrorInfo(0, 0);
  this[6] = IID_IDBProperties;
  *(_DWORD *)&this[263].Data2 = 0;
  if ( a2 == 1 )
  {
    v9 = *(_QWORD *)&a3->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
    if ( !v9 )
      v9 = *(_QWORD *)a3->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
    if ( !v9 )
      this[292].Data1 = 0;
  }
  try
  {
    v10 = CUtlProps::utlSetProperties(
            (CUtlProps *)this[287].Data4,
            v8,
            a2,
            a3,
            (const struct CBidGenericBase *)this[286].Data4,
            0);
    this[292].Data1 = 1;
    v11 = Exit(v10, 0xBB8u);
  }
  catch ( long v17 )
  {
    v22 = v17;
    goto LABEL_12;
  }
  catch ( ... )
  {
    v22 = -2147467259;
LABEL_12:
    this[292].Data1 = 1;
    v15 = Exit(v22, 0);
    --v18->Data1;
    v12 = (*(_DWORD *)v19)-- == 1;
    if ( v12 )
      *(_DWORD *)v23->Data4 = -1;
    v16 = *(_QWORD *)&v23->Data1;
    --*(_DWORD *)(v16 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
    return v15;
  }
  --v6[1].Data1;
  v12 = (*(_DWORD *)v7)-- == 1;
  if ( v12 )
    *(_DWORD *)v6->Data4 = -1;
  v13 = *(_QWORD *)&v6->Data1;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x1800154d0  mov     [rsp+arg_10], rbx
0x1800154d5  mov     [rsp+arg_0], rcx
0x1800154da  push    rsi
0x1800154db  push    rdi
0x1800154dc  push    r12
0x1800154de  push    r14
0x1800154e0  push    r15
0x1800154e2  sub     rsp, 50h
0x1800154e6  mov     r15, r8
0x1800154e9  mov     r12d, edx
0x1800154ec  mov     rsi, rcx
0x1800154ef  lea     rbx, [rcx+30h]
0x1800154f3  mov     [rsp+78h+arg_18], rbx
0x1800154fb  mov     rcx, rbx
0x1800154fe  call    cs:__imp_UMSEnterCSWraper
0x180015505  nop     dword ptr [rax+rax+00h]
0x18001550a  lea     rdi, [rbx+0Ch]
0x18001550e  mov     [rsp+78h+var_38], rdi
0x180015513  cmp     dword ptr [rdi], 0
0x180015516  jnz     short loc_180015527
0x180015518  call    cs:__imp_GetCurrentThreadId
0x18001551f  nop     dword ptr [rax+rax+00h]
0x180015524  mov     [rbx+8], eax
0x180015527  inc     dword ptr [rdi]
0x180015529  lea     r14, [rbx+10h]
0x18001552d  mov     [rsp+78h+var_40], r14
0x180015532  inc     dword ptr [r14]
0x180015535  mov     [rsp+78h+var_30], rbx
0x18001553a  xor     edx, edx; perrinfo
0x18001553c  xor     ecx, ecx; dwReserved
0x18001553e  call    cs:__imp_SetErrorInfo
0x180015545  nop     dword ptr [rax+rax+00h]
0x18001554a  movups  xmm0, xmmword ptr cs:IID_IDBProperties.Data1
0x180015551  movdqu  xmmword ptr [rsi+60h], xmm0
0x180015556  mov     dword ptr [rsi+1074h], 0
0x180015560  cmp     r12d, 1
0x180015564  jnz     short loc_180015589
0x180015566  mov     rax, [r15+0Ch]
0x18001556a  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180015571  jnz     short loc_18001557E
0x180015573  mov     rax, [r15+14h]
0x180015577  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x18001557e  test    rax, rax
0x180015581  jnz     short loc_180015589
0x180015583  mov     [rsi+1240h], eax
0x180015589  lea     rax, [rsi+11E8h]
0x180015590  lea     rcx, [rsi+11F8h]; this
0x180015597  mov     [rsp+78h+var_50], 0; int
0x18001559f  mov     [rsp+78h+var_58], rax; struct CBidGenericBase *
0x1800155a4  mov     r9, r15; struct tagDBPROPSET *
0x1800155a7  mov     r8d, r12d; unsigned int
0x1800155aa  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x1800155af  mov     dword ptr [rsi+1240h], 1
0x1800155b9  mov     edx, 0BB8h; unsigned int
0x1800155be  mov     ecx, eax; int
0x1800155c0  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800155c5  mov     esi, eax
0x1800155c7  or      edx, 0FFFFFFFFh
0x1800155ca  add     [r14], edx
0x1800155cd  add     [rdi], edx
0x1800155cf  jnz     short loc_1800155D4
0x1800155d1  mov     [rbx+8], edx
0x1800155d4  mov     rcx, [rbx]
0x1800155d7  dec     dword ptr [rcx+30h]
0x1800155da  add     rcx, 8; lpCriticalSection
0x1800155de  call    cs:__imp_LeaveCriticalSection
0x1800155e5  nop     dword ptr [rax+rax+00h]
0x1800155ea  mov     eax, esi
0x1800155ec  jmp     short loc_180015648
0x1800155ee  jmp     short $+2
0x1800155f0  mov     rax, [rsp+78h+arg_0]
0x1800155f8  mov     dword ptr [rax+1240h], 1
0x180015602  xor     edx, edx; unsigned int
0x180015604  mov     ecx, [rsp+78h+arg_8]; int
0x18001560b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180015610  mov     ebx, eax
0x180015612  or      edx, 0FFFFFFFFh
0x180015615  mov     rcx, [rsp+78h+var_40]
0x18001561a  add     [rcx], edx
0x18001561c  mov     rcx, [rsp+78h+var_38]
0x180015621  add     [rcx], edx
0x180015623  mov     rcx, [rsp+78h+arg_18]
0x18001562b  jnz     short loc_180015630
0x18001562d  mov     [rcx+8], edx
0x180015630  mov     rcx, [rcx]
0x180015633  dec     dword ptr [rcx+30h]
0x180015636  add     rcx, 8; lpCriticalSection
0x18001563a  call    cs:__imp_LeaveCriticalSection
0x180015641  nop     dword ptr [rax+rax+00h]
0x180015646  mov     eax, ebx
0x180015648  mov     rbx, [rsp+78h+arg_10]
0x180015650  add     rsp, 50h
0x180015654  pop     r15
0x180015656  pop     r14
0x180015658  pop     r12
0x18001565a  pop     rdi
0x18001565b  pop     rsi
0x18001565c  retn
```
