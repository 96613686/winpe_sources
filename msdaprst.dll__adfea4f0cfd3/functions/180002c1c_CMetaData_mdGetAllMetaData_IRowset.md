# CMetaData::mdGetAllMetaData(IRowset *)

- ea: `0x180002c1c`
- end: `0x180002dde`
- name: `?mdGetAllMetaData@CMetaData@@QEAAXPEAUIRowset@@@Z`
- size: `450`
- prototype: `void __fastcall(CMetaData *__hidden this, struct IRowset *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1800071b0`
- `0x18001b768`

## callees

- `0x180002728`
- `0x180002770`
- `0x180002b24`
- `0x180002c1c`
- `0x1800030a8`
- `0x1800031e4`
- `0x18000378c`
- `0x180003c70`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002d98`
- `ole32!CoTaskMemFree` at `0x180002da9`
- `ole32!CoTaskMemFree` at `0x180002dba`
- `ole32!CoTaskMemFree` at `0x180002d98`
- `ole32!CoTaskMemFree` at `0x180002da9`
- `ole32!CoTaskMemFree` at `0x180002dba`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMetaData::mdGetAllMetaData(CMetaData *this, struct IRowset *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // ebx
  int v8; // ebx
  CMetaData *v9; // rcx
  unsigned int v10; // ebx
  struct IRowset *v11; // rdx
  LPVOID v12; // rax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v15; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+30h] BYREF
  struct tagDBCOLUMNINFO *v17; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v17 = 0;
  pv = 0;
  v15 = 0;
  if ( !(unsigned int)CMetaData::mdGetColumnsUpdateInfo(this, a2, (unsigned __int16 **)&pv, &v15) )
  {
    v4 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsInfo,
           &v13);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049498[0] )
          bidTraceW(off_1800491B8[0], 203776, off_180049498[0], (unsigned int)v4, 199);
      }
      ThrowHR(v5);
    }
    v14 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagDBCOLUMNINFO **, LPVOID *))(*(_QWORD *)v13 + 24LL))(
           v13,
           &v14,
           &v17,
           &pv);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049490[0] )
        bidTraceW(off_1800491B8[0], 206848, off_180049490[0], (unsigned int)v6, 202);
      ThrowHR(v7);
    }
    v8 = DownsizeToULONGThrow<unsigned __int64>(v14);
    v10 = CMetaData::mdGetHiddenCount(v9, a2) + v8;
    if ( (unsigned int)CMetaData::mdFNeedColumnsRowset(this, a2, v10, v17) )
      CMetaData::mdGetColumnsRowsetData(this, a2, v10);
    if ( !*((_QWORD *)this + 4) )
      CMetaData::mdGetColumnsInfo(this, v11, v10, v17);
  }
  v12 = pv;
  pv = 0;
  *((_QWORD *)this + 2) = v12;
  *((_QWORD *)this + 3) = v15;
  CoTaskMemFree(0);
  CoTaskMemFree(pv);
  CoTaskMemFree(v17);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v13);
}

```

## disassembly

```asm
0x180002c1c  mov     [rsp-18h+arg_0], rbx
0x180002c21  push    rbp
0x180002c22  push    rsi
0x180002c23  push    rdi
0x180002c24  mov     rbp, rsp
0x180002c27  sub     rsp, 50h
0x180002c2b  mov     rsi, rdx
0x180002c2e  mov     rdi, rcx
0x180002c31  mov     [rbp+var_20], 0
0x180002c39  mov     [rbp+arg_18], 0
0x180002c41  mov     [rbp+pv], 0
0x180002c49  mov     [rbp+var_10], 0
0x180002c51  lea     r9, [rbp+var_10]; unsigned __int8 **
0x180002c55  lea     r8, [rbp+pv]; unsigned __int16 **
0x180002c59  call    ?mdGetColumnsUpdateInfo@CMetaData@@AEAAHPEAUIRowset@@PEAPEAGPEAPEAE@Z; CMetaData::mdGetColumnsUpdateInfo(IRowset *,ushort * *,uchar * *)
0x180002c5e  test    eax, eax
0x180002c60  jnz     loc_180002D7E
0x180002c66  mov     rax, [rsi]
0x180002c69  lea     r8, [rbp+var_20]
0x180002c6d  lea     rdx, IID_IColumnsInfo
0x180002c74  mov     rcx, rsi
0x180002c77  mov     rax, [rax]
0x180002c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7f  mov     ebx, eax
0x180002c81  test    eax, eax
0x180002c83  jns     short loc_180002CC5
0x180002c85  test    byte ptr cs:_bidGblFlags, 2
0x180002c8c  jz      short loc_180002CBD
0x180002c8e  mov     rcx, cs:off_180049498; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002c95  test    rcx, rcx
0x180002c98  jz      short loc_180002CBD
0x180002c9a  mov     [rsp+50h+var_30], 0C7h
0x180002ca2  mov     r9d, eax
0x180002ca5  mov     r8, cs:off_180049498; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002cac  mov     edx, 31C00h
0x180002cb1  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002cb8  call    _bidTraceW
0x180002cbd  mov     ecx, ebx; int
0x180002cbf  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180002cc5  mov     [rbp+var_18], 0
0x180002ccd  mov     rcx, [rbp+var_20]
0x180002cd1  mov     rax, [rcx]
0x180002cd4  lea     r9, [rbp+pv]
0x180002cd8  lea     r8, [rbp+arg_18]
0x180002cdc  lea     rdx, [rbp+var_18]
0x180002ce0  mov     rax, [rax+18h]
0x180002ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce9  mov     ebx, eax
0x180002ceb  test    eax, eax
0x180002ced  jns     short loc_180002D2F
0x180002cef  test    byte ptr cs:_bidGblFlags, 2
0x180002cf6  jz      short loc_180002D27
0x180002cf8  mov     rcx, cs:off_180049490; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002cff  test    rcx, rcx
0x180002d02  jz      short loc_180002D27
0x180002d04  mov     [rsp+50h+var_30], 0CAh
0x180002d0c  mov     r9d, eax
0x180002d0f  mov     r8, cs:off_180049490; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002d16  mov     edx, 32800h
0x180002d1b  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002d22  call    _bidTraceW
0x180002d27  mov     ecx, ebx; int
0x180002d29  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180002d2f  mov     rcx, [rbp+var_18]
0x180002d33  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180002d38  mov     ebx, eax
0x180002d3a  mov     rdx, rsi; struct IRowset *
0x180002d3d  call    ?mdGetHiddenCount@CMetaData@@AEAAKPEAUIRowset@@@Z; CMetaData::mdGetHiddenCount(IRowset *)
0x180002d42  add     ebx, eax
0x180002d44  mov     r9, [rbp+arg_18]; struct tagDBCOLUMNINFO *
0x180002d48  mov     r8d, ebx; unsigned int
0x180002d4b  mov     rdx, rsi; struct IRowset *
0x180002d4e  mov     rcx, rdi; this
0x180002d51  call    ?mdFNeedColumnsRowset@CMetaData@@AEAAHPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@@Z; CMetaData::mdFNeedColumnsRowset(IRowset *,ulong,tagDBCOLUMNINFO *)
0x180002d56  test    eax, eax
0x180002d58  jz      short loc_180002D68
0x180002d5a  mov     r8d, ebx; unsigned int
0x180002d5d  mov     rdx, rsi; struct IRowset *
0x180002d60  mov     rcx, rdi; this
0x180002d63  call    ?mdGetColumnsRowsetData@CMetaData@@AEAAXPEAUIRowset@@K@Z; CMetaData::mdGetColumnsRowsetData(IRowset *,ulong)
0x180002d68  cmp     qword ptr [rdi+20h], 0
0x180002d6d  jnz     short loc_180002D7E
0x180002d6f  mov     r9, [rbp+arg_18]; struct tagDBCOLUMNINFO *
0x180002d73  mov     r8d, ebx; unsigned int
0x180002d76  mov     rcx, rdi; this
0x180002d79  call    ?mdGetColumnsInfo@CMetaData@@AEAAXPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@@Z; CMetaData::mdGetColumnsInfo(IRowset *,ulong,tagDBCOLUMNINFO *)
0x180002d7e  mov     rax, [rbp+pv]
0x180002d82  mov     [rbp+pv], 0
0x180002d8a  mov     [rdi+10h], rax
0x180002d8e  mov     rax, [rbp+var_10]
0x180002d92  mov     [rdi+18h], rax
0x180002d96  xor     ecx, ecx; pv
0x180002d98  call    cs:__imp_CoTaskMemFree
0x180002d9f  nop     dword ptr [rax+rax+00h]
0x180002da4  nop
0x180002da5  mov     rcx, [rbp+pv]; pv
0x180002da9  call    cs:__imp_CoTaskMemFree
0x180002db0  nop     dword ptr [rax+rax+00h]
0x180002db5  nop
0x180002db6  mov     rcx, [rbp+arg_18]; pv
0x180002dba  call    cs:__imp_CoTaskMemFree
0x180002dc1  nop     dword ptr [rax+rax+00h]
0x180002dc6  nop
0x180002dc7  lea     rcx, [rbp+var_20]
0x180002dcb  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180002dd0  mov     rbx, [rsp+50h+arg_0]
0x180002dd5  add     rsp, 50h
0x180002dd9  pop     rdi
0x180002dda  pop     rsi
0x180002ddb  pop     rbp
0x180002ddc  retn
```
