# CImpIColumnsInfo::MapColumnIDs(unsigned __int64,tagDBID const * const,unsigned __int64 * const)

- ea: `0x180011d10`
- end: `0x180011fa3`
- name: `?MapColumnIDs@CImpIColumnsInfo@@UEAAJ_KQEBUtagDBID@@QEA_K@Z`
- size: `659`
- prototype: `__int64 __fastcall(CImpIColumnsInfo *__hidden this, unsigned __int64, const struct tagDBID *const, unsigned __int64 *const)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800023c0`
- `0x180011d10`
- `0x180016584`
- `0x18001b008`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011d5b`
- `KERNEL32!GetCurrentThreadId` at `0x180011d5b`
- `KERNEL32!LeaveCriticalSection` at `0x180011da0`
- `KERNEL32!LeaveCriticalSection` at `0x180011ddd`
- `KERNEL32!LeaveCriticalSection` at `0x180011f7c`
- `KERNEL32!LeaveCriticalSection` at `0x180011da0`
- `KERNEL32!LeaveCriticalSection` at `0x180011ddd`
- `KERNEL32!LeaveCriticalSection` at `0x180011f7c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011d78`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011d78`
- `MSDART!UMSEnterCSWraper` at `0x180011d45`
- `MSDART!UMSEnterCSWraper` at `0x180011d45`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIColumnsInfo::MapColumnIDs(
        CImpIColumnsInfo *this,
        unsigned __int64 a2,
        const struct tagDBID *const a3,
        unsigned __int64 *const a4)
{
  __int64 v7; // rbx
  DWORD *v8; // rdi
  bool v9; // zf
  __int64 v10; // rcx
  unsigned int v12; // esi
  __int64 v13; // rcx
  unsigned int v14; // esi
  unsigned int v15; // ebp
  __int64 v16; // r15
  __int64 v17; // rcx
  unsigned __int64 ulPropid; // rdx
  char *v19; // rax
  unsigned int BidObjectID; // eax
  unsigned int v21; // eax
  wchar_t *v22; // r8
  char *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx

  v7 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v7);
  v8 = (DWORD *)(v7 + 8);
  if ( !*(_DWORD *)(v7 + 12) )
    *v8 = GetCurrentThreadId();
  ++*(_DWORD *)(v7 + 12);
  ++*(_DWORD *)(v7 + 16);
  SetErrorInfo(0, 0);
  if ( !a2 )
  {
    --*(_DWORD *)(v7 + 16);
    v9 = (*(_DWORD *)(v7 + 12))-- == 1;
    if ( v9 )
      *v8 = -1;
    v10 = *(_QWORD *)v7;
    --*(_DWORD *)(v10 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
    return 0;
  }
  if ( a3 && a4 )
  {
    v14 = 0;
    v15 = 0;
    v16 = 0;
    do
    {
      v17 = (unsigned int)v16;
      ulPropid = a3[v17].uName.ulPropid;
      if ( !(_DWORD)ulPropid
        || (unsigned int)ulPropid > *(_DWORD *)(*((_QWORD *)this + 3) + 152LL)
        || a3[v17].eKind != 1 )
      {
        goto LABEL_20;
      }
      v19 = (char *)a3[v17].uGuid.pguid - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v19 )
        v19 = (char *)(*((_QWORD *)&a3[v17].uGuid.pguid + 1) - *(_QWORD *)GUID_NULL.Data4);
      if ( !v19 )
      {
        a4[v16] = ulPropid;
      }
      else
      {
LABEL_20:
        a4[v16] = -1;
        ++v14;
        if ( (bidGblFlags & 2) != 0 && off_1800498F0[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
          bidTraceW(off_180049248[0], 194560, off_1800498F0[0], BidObjectID, v16);
        }
      }
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < a2 );
    if ( !v14 )
      goto LABEL_33;
    if ( v14 >= a2 )
    {
      v15 = -2147217887;
      if ( (bidGblFlags & 2) == 0 || !off_1800498E0[0] )
        goto LABEL_33;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_1800498E0[0];
      v23 = off_180049238[0];
      v24 = 212992;
    }
    else
    {
      v15 = 265946;
      if ( (bidGblFlags & 2) == 0 || !off_1800498E8[0] )
        goto LABEL_33;
      v21 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(*((_QWORD *)this + 3) + 112LL));
      v22 = off_1800498E8[0];
      v23 = off_180049240[0];
      v24 = 206848;
    }
    bidTraceW(v23, v24, v22, v21, v14);
LABEL_33:
    --*(_DWORD *)(v7 + 16);
    v9 = (*(_DWORD *)(v7 + 12))-- == 1;
    if ( v9 )
      *v8 = -1;
    v25 = *(_QWORD *)v7;
    --*(_DWORD *)(v25 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 8));
    return v15;
  }
  v12 = Exit(-2147024809, 0);
  --*(_DWORD *)(v7 + 16);
  v9 = (*(_DWORD *)(v7 + 12))-- == 1;
  if ( v9 )
    *v8 = -1;
  v13 = *(_QWORD *)v7;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v12;
}

```

## disassembly

```asm
0x180011d10  mov     [rsp+arg_10], rbx
0x180011d15  mov     [rsp+arg_0], rcx
0x180011d1a  push    rbp
0x180011d1b  push    rsi
0x180011d1c  push    rdi
0x180011d1d  push    r12
0x180011d1f  push    r13
0x180011d21  push    r14
0x180011d23  push    r15
0x180011d25  sub     rsp, 40h
0x180011d29  mov     r13, r9
0x180011d2c  mov     r14, r8
0x180011d2f  mov     r12, rdx
0x180011d32  mov     rbx, [rcx+18h]
0x180011d36  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180011d3a  mov     [rsp+78h+arg_8], rbx
0x180011d42  mov     rcx, rbx
0x180011d45  call    cs:__imp_UMSEnterCSWraper
0x180011d4c  nop     dword ptr [rax+rax+00h]
0x180011d51  lea     rdi, [rbx+8]
0x180011d55  cmp     dword ptr [rbx+0Ch], 0
0x180011d59  jnz     short loc_180011D69
0x180011d5b  call    cs:__imp_GetCurrentThreadId
0x180011d62  nop     dword ptr [rax+rax+00h]
0x180011d67  mov     [rdi], eax
0x180011d69  inc     dword ptr [rbx+0Ch]
0x180011d6c  inc     dword ptr [rbx+10h]
0x180011d6f  mov     [rsp+78h+var_48], rbx
0x180011d74  xor     edx, edx; perrinfo
0x180011d76  xor     ecx, ecx; dwReserved
0x180011d78  call    cs:__imp_SetErrorInfo
0x180011d7f  nop     dword ptr [rax+rax+00h]
0x180011d84  test    r12, r12
0x180011d87  jnz     short loc_180011DB3
0x180011d89  or      edx, 0FFFFFFFFh
0x180011d8c  add     [rbx+10h], edx
0x180011d8f  add     [rbx+0Ch], edx
0x180011d92  jnz     short loc_180011D96
0x180011d94  mov     [rdi], edx
0x180011d96  mov     rcx, [rbx]
0x180011d99  dec     dword ptr [rcx+30h]
0x180011d9c  add     rcx, 8; lpCriticalSection
0x180011da0  call    cs:__imp_LeaveCriticalSection
0x180011da7  nop     dword ptr [rax+rax+00h]
0x180011dac  xor     eax, eax
0x180011dae  jmp     loc_180011F8A
0x180011db3  test    r14, r14
0x180011db6  jnz     short loc_180011DF0
0x180011db8  xor     edx, edx; unsigned int
0x180011dba  mov     ecx, 80070057h; int
0x180011dbf  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180011dc4  mov     esi, eax
0x180011dc6  or      edx, 0FFFFFFFFh
0x180011dc9  add     [rbx+10h], edx
0x180011dcc  add     [rbx+0Ch], edx
0x180011dcf  jnz     short loc_180011DD3
0x180011dd1  mov     [rdi], edx
0x180011dd3  mov     rcx, [rbx]
0x180011dd6  dec     dword ptr [rcx+30h]
0x180011dd9  add     rcx, 8; lpCriticalSection
0x180011ddd  call    cs:__imp_LeaveCriticalSection
0x180011de4  nop     dword ptr [rax+rax+00h]
0x180011de9  mov     eax, esi
0x180011deb  jmp     loc_180011F8A
0x180011df0  test    r13, r13
0x180011df3  jz      short loc_180011DB8
0x180011df5  xor     esi, esi
0x180011df7  xor     ebp, ebp
0x180011df9  xor     r15d, r15d
0x180011dfc  test    r12, r12
0x180011dff  jz      loc_180011F65
0x180011e05  mov     rbx, [rsp+78h+arg_0]
0x180011e0d  mov     ecx, r15d
0x180011e10  shl     rcx, 5
0x180011e14  mov     edx, [rcx+r14+18h]
0x180011e19  cmp     edx, 1
0x180011e1c  jb      short loc_180011E57
0x180011e1e  mov     rax, [rbx+18h]
0x180011e22  cmp     edx, [rax+98h]
0x180011e28  ja      short loc_180011E57
0x180011e2a  cmp     dword ptr [rcx+r14+10h], 1
0x180011e30  jnz     short loc_180011E57
0x180011e32  mov     rax, [rcx+r14]
0x180011e36  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180011e3d  jnz     short loc_180011E4B
0x180011e3f  mov     rax, [rcx+r14+8]
0x180011e44  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180011e4b  test    rax, rax
0x180011e4e  jnz     short loc_180011E57
0x180011e50  mov     [r13+r15*8+0], rdx
0x180011e55  jmp     short loc_180011EA4
0x180011e57  mov     qword ptr [r13+r15*8+0], 0FFFFFFFFFFFFFFFFh
0x180011e60  inc     esi
0x180011e62  test    byte ptr cs:_bidGblFlags, 2
0x180011e69  jz      short loc_180011EA4
0x180011e6b  mov     rax, cs:off_1800498F0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011e72  test    rax, rax
0x180011e75  jz      short loc_180011EA4
0x180011e77  mov     rcx, [rbx+18h]
0x180011e7b  add     rcx, 70h ; 'p'; this
0x180011e7f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011e84  mov     r8, cs:off_1800498F0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011e8b  mov     rcx, cs:off_180049248; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180011e92  mov     [rsp+78h+var_58], r15d
0x180011e97  mov     r9d, eax
0x180011e9a  mov     edx, 2F800h
0x180011e9f  call    _bidTraceW
0x180011ea4  inc     r15d
0x180011ea7  mov     eax, r15d
0x180011eaa  cmp     rax, r12
0x180011ead  jb      loc_180011E0D
0x180011eb3  test    esi, esi
0x180011eb5  mov     rbx, [rsp+78h+arg_8]
0x180011ebd  jz      loc_180011F65
0x180011ec3  mov     eax, esi
0x180011ec5  cmp     rax, r12
0x180011ec8  jnb     short loc_180011F12
0x180011eca  mov     ebp, 40EDAh
0x180011ecf  test    byte ptr cs:_bidGblFlags, 2
0x180011ed6  jz      loc_180011F65
0x180011edc  mov     rax, cs:off_1800498E8; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011ee3  test    rax, rax
0x180011ee6  jz      short loc_180011F65
0x180011ee8  mov     rcx, [rsp+78h+arg_0]
0x180011ef0  mov     rcx, [rcx+18h]
0x180011ef4  add     rcx, 70h ; 'p'; this
0x180011ef8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011efd  mov     r8, cs:off_1800498E8; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011f04  mov     rcx, cs:off_180049240; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180011f0b  mov     edx, 32800h
0x180011f10  jmp     short loc_180011F54
0x180011f12  mov     ebp, 80040E21h
0x180011f17  test    byte ptr cs:_bidGblFlags, 2
0x180011f1e  jz      short loc_180011F65
0x180011f20  mov     rax, cs:off_1800498E0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011f27  test    rax, rax
0x180011f2a  jz      short loc_180011F65
0x180011f2c  mov     rcx, [rsp+78h+arg_0]
0x180011f34  mov     rcx, [rcx+18h]
0x180011f38  add     rcx, 70h ; 'p'; this
0x180011f3c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180011f41  mov     r8, cs:off_1800498E0; "<CImpIColumnsInfo::MapColumnIDs|ERR|PER"...
0x180011f48  mov     rcx, cs:off_180049238; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180011f4f  mov     edx, 34000h
0x180011f54  mov     [rsp+78h+var_50], ebp
0x180011f58  mov     [rsp+78h+var_58], esi
0x180011f5c  mov     r9d, eax
0x180011f5f  call    _bidTraceW
0x180011f64  nop
0x180011f65  or      edx, 0FFFFFFFFh
0x180011f68  add     [rbx+10h], edx
0x180011f6b  add     [rbx+0Ch], edx
0x180011f6e  jnz     short loc_180011F72
0x180011f70  mov     [rdi], edx
0x180011f72  mov     rcx, [rbx]
0x180011f75  dec     dword ptr [rcx+30h]
0x180011f78  add     rcx, 8; lpCriticalSection
0x180011f7c  call    cs:__imp_LeaveCriticalSection
0x180011f83  nop     dword ptr [rax+rax+00h]
0x180011f88  mov     eax, ebp
0x180011f8a  mov     rbx, [rsp+78h+arg_10]
0x180011f92  add     rsp, 40h
0x180011f96  pop     r15
0x180011f98  pop     r14
0x180011f9a  pop     r13
0x180011f9c  pop     r12
0x180011f9e  pop     rdi
0x180011f9f  pop     rsi
0x180011fa0  pop     rbp
0x180011fa1  retn
```
