# CTransactedStream::PartialWrite(ulong,ulong,uchar const *,ushort,ushort)

- ea: `0x18006107c`
- end: `0x1800611e0`
- name: `?PartialWrite@CTransactedStream@@AEAAJKKPEBEGG@Z`
- size: `356`
- prototype: `int(CTransactedStream *__hidden this, unsigned int, unsigned int, const unsigned __int8 *, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008f64`

## callees

- `0x180008ea4`
- `0x18000a61c`
- `0x18000a68c`
- `0x180010cf0`
- `0x180034570`
- `0x18006107c`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800611c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800611c0`

## pseudocode

```c
__int64 __fastcall CTransactedStream::PartialWrite(
        CTransactedStream *this,
        unsigned int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned __int16 a5,
        unsigned __int16 a6)
{
  CDeltaList *v6; // r12
  unsigned __int8 *v8; // rbx
  unsigned int DataSectorSize; // r15d
  char DataSectorShift; // r13
  int Buffer; // eax
  int v13; // edi
  __int64 v14; // r8
  struct ILockBytes *DataILB; // rax
  unsigned int v17; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+10h]
  int v21; // [rsp+90h] [rbp+18h]

  v21 = a3;
  v20 = a2;
  v6 = (CTransactedStream *)((char *)this + 136);
  v8 = 0;
  pv = 0;
  v19 = 0;
  DataSectorSize = CDeltaList::GetDataSectorSize((CTransactedStream *)((char *)this + 136));
  DataSectorShift = CDeltaList::GetDataSectorShift(v6);
  if ( a6 == (_WORD)DataSectorSize )
    goto LABEL_7;
  v17 = 0;
  Buffer = GetBuffer(DataSectorSize, DataSectorSize, (unsigned __int8 **)&pv, &v17);
  v8 = (unsigned __int8 *)pv;
  v13 = Buffer;
  if ( Buffer >= 0 )
  {
    v14 = *((_QWORD *)this + 15);
    if ( !v14
      || !(v14 + *(_QWORD *)NtCurrentTeb()->ReservedForOle)
      || (v13 = PSStream::ReadAt(
                  (PSStream *)(v14 + *(_QWORD *)NtCurrentTeb()->ReservedForOle),
                  (unsigned __int64)v20 << DataSectorShift,
                  pv,
                  DataSectorSize,
                  &v19),
          v13 >= 0) )
    {
      memcpy_0(&v8[a5], a4, a6);
      a4 = v8;
LABEL_7:
      DataILB = CDeltaList::GetDataILB(v6);
      v13 = ((__int64 (__fastcall *)(struct ILockBytes *, unsigned __int64, const unsigned __int8 *, _QWORD, unsigned int *))DataILB->lpVtbl->WriteAt)(
              DataILB,
              (unsigned __int64)(unsigned int)(v21 + 1) << DataSectorShift,
              a4,
              DataSectorSize,
              &v19);
    }
  }
  CoTaskMemFree(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18006107c  mov     rax, rsp
0x18006107f  mov     [rax+20h], rbx
0x180061083  mov     [rax+18h], r8d
0x180061087  mov     [rax+10h], edx
0x18006108a  push    rbp
0x18006108b  push    rsi
0x18006108c  push    rdi
0x18006108d  push    r12
0x18006108f  push    r13
0x180061091  push    r14
0x180061093  push    r15
0x180061095  sub     rsp, 40h
0x180061099  lea     r12, [rcx+88h]
0x1800610a0  mov     r14, rcx
0x1800610a3  xor     ebx, ebx
0x1800610a5  mov     rcx, r12; this
0x1800610a8  mov     rbp, r9
0x1800610ab  mov     [rax-40h], rbx
0x1800610af  mov     [rax+8], ebx
0x1800610b2  call    ?GetDataSectorSize@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorSize(void)
0x1800610b7  mov     rcx, r12; this
0x1800610ba  movzx   r15d, ax
0x1800610be  call    ?GetDataSectorShift@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorShift(void)
0x1800610c3  movzx   r13d, ax
0x1800610c7  cmp     [rsp+78h+arg_28], r15w
0x1800610d0  jz      loc_18006117F
0x1800610d6  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800610db  mov     [rsp+78h+var_48], ebx
0x1800610df  lea     r8, [rsp+78h+pv]; unsigned __int8 **
0x1800610e4  mov     edx, r15d; unsigned int
0x1800610e7  mov     ecx, r15d; unsigned int
0x1800610ea  call    ?GetBuffer@@YAJKKPEAPEAEPEAK@Z; GetBuffer(ulong,ulong,uchar * *,ulong *)
0x1800610ef  mov     rbx, [rsp+78h+pv]
0x1800610f4  mov     edi, eax
0x1800610f6  test    eax, eax
0x1800610f8  js      loc_1800611BD
0x1800610fe  mov     r8, [r14+78h]
0x180061102  test    r8, r8
0x180061105  jz      short loc_180061160
0x180061107  mov     rax, gs:30h
0x180061110  mov     rcx, [rax+1758h]
0x180061117  mov     rax, [rcx]
0x18006111a  add     rax, r8
0x18006111d  jz      short loc_180061160
0x18006111f  mov     rax, gs:30h
0x180061128  mov     cl, r13b
0x18006112b  mov     edx, [rsp+78h+arg_8]
0x180061132  mov     r9d, r15d; unsigned int
0x180061135  shl     rdx, cl; unsigned __int64
0x180061138  mov     rcx, [rax+1758h]
0x18006113f  lea     rax, [rsp+78h+arg_0]
0x180061147  mov     [rsp+78h+var_58], rax; unsigned int *
0x18006114c  mov     rcx, [rcx]
0x18006114f  add     rcx, r8; this
0x180061152  mov     r8, rbx; void *
0x180061155  call    ?ReadAt@PSStream@@QEAAJ_KPEAXKPEAK@Z; PSStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x18006115a  mov     edi, eax
0x18006115c  test    eax, eax
0x18006115e  js      short loc_1800611BD
0x180061160  movzx   ecx, [rsp+78h+arg_20]
0x180061168  mov     rdx, rbp; Src
0x18006116b  movzx   r8d, [rsp+78h+arg_28]; Size
0x180061174  add     rcx, rbx; void *
0x180061177  call    memcpy_0
0x18006117c  mov     rbp, rbx
0x18006117f  mov     rcx, r12; this
0x180061182  call    ?GetDataILB@CDeltaList@@QEAAPEAUILockBytes@@XZ; CDeltaList::GetDataILB(void)
0x180061187  mov     edx, [rsp+78h+arg_10]
0x18006118e  mov     r10, rax
0x180061191  inc     edx
0x180061193  mov     cl, r13b
0x180061196  shl     rdx, cl
0x180061199  mov     r9d, r15d
0x18006119c  mov     r8, [rax]
0x18006119f  lea     rcx, [rsp+78h+arg_0]
0x1800611a7  mov     [rsp+78h+var_58], rcx
0x1800611ac  mov     rcx, r10
0x1800611af  mov     rax, [r8+20h]
0x1800611b3  mov     r8, rbp
0x1800611b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611bb  mov     edi, eax
0x1800611bd  mov     rcx, rbx; pv
0x1800611c0  call    cs:__imp_CoTaskMemFree
0x1800611c6  mov     rbx, [rsp+78h+arg_18]
0x1800611ce  mov     eax, edi
0x1800611d0  add     rsp, 40h
0x1800611d4  pop     r15
0x1800611d6  pop     r14
0x1800611d8  pop     r13
0x1800611da  pop     r12
0x1800611dc  pop     rdi
0x1800611dd  pop     rsi
0x1800611de  pop     rbp
0x1800611df  retn
```
