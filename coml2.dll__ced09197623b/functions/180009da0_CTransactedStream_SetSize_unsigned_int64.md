# CTransactedStream::SetSize(unsigned __int64)

- ea: `0x180009da0`
- end: `0x18000a07c`
- name: `?SetSize@CTransactedStream@@QEAAJ_K@Z`
- size: `732`
- prototype: `__int64 __fastcall(CTransactedStream *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008f64`
- `0x180009d7c`

## callees

- `0x18000587c`
- `0x180008e6c`
- `0x180008ea4`
- `0x180008f30`
- `0x180009da0`
- `0x18000a084`
- `0x18000a61c`
- `0x18000a68c`
- `0x18000a6fc`
- `0x18000b530`
- `0x18000b5c4`
- `0x180010cf0`
- `0x180032bf8`
- `0x180032d7c`
- `0x180034570`
- `0x18003e13c`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eb6`

## pseudocode

```c
__int64 __fastcall CTransactedStream::SetSize(CTransactedStream *this, unsigned __int64 a2)
{
  unsigned __int8 *v2; // r12
  CDeltaList *v3; // rdi
  CDeltaList *v6; // rcx
  CDeltaList *v7; // rcx
  int inited; // eax
  int Map; // ebx
  unsigned __int64 DataSectorSize; // r13
  __int64 v11; // r10
  unsigned __int64 v12; // rsi
  CFat *DataFat; // rax
  unsigned __int64 i; // r13
  __int64 v16; // rdx
  CMStream *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  PSStream *v20; // r10
  struct ILockBytes *DataILB; // rax
  unsigned int v22; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-1Ch] BYREF
  int v24; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v25; // [rsp+40h] [rbp-10h] BYREF
  char DataSectorShift; // [rsp+98h] [rbp+48h]
  unsigned int v27; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  v3 = (CTransactedStream *)((char *)this + 136);
  v25 = 0;
  v28 = 0;
  v6 = (CTransactedStream *)((char *)this + 136);
  if ( a2 )
  {
    if ( (unsigned int)CDeltaList::IsEmpty(v6) )
      inited = CDeltaList::Init(v7, a2, this);
    else
      inited = CDeltaList::InitResize(v7, a2);
    Map = inited;
    if ( inited < 0 )
      goto LABEL_16;
  }
  else
  {
    Map = 0;
    CDeltaList::Empty(v6);
  }
  if ( a2 <= *((_QWORD *)this + 14) )
    goto LABEL_23;
  DataSectorSize = CDeltaList::GetDataSectorSize(v3);
  DataSectorShift = CDeltaList::GetDataSectorShift(v3);
  v27 = 0;
  if ( v11 )
    v12 = (v11 - 1) / (unsigned __int64)(unsigned int)DataSectorSize;
  else
    LODWORD(v12) = 0;
  Map = CDeltaList::GetMap(v3, v12, 0, &v27);
  if ( Map >= 0 )
  {
    if ( v27 == -2 )
    {
      v18 = *((_QWORD *)this + 15);
      if ( v18 )
      {
        if ( v18 + *(_QWORD *)NtCurrentTeb()->ReservedForOle && *((_QWORD *)this + 14) )
        {
          v23 = 0;
          Map = GetBuffer(DataSectorSize, DataSectorSize, &v25, &v23);
          if ( Map < 0 )
          {
            v2 = v25;
            goto LABEL_16;
          }
          v19 = *((_QWORD *)this + 15);
          v22 = 0;
          if ( v19 )
            v20 = (PSStream *)(v19 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
          else
            v20 = 0;
          v2 = v25;
          Map = PSStream::ReadAt(v20, (unsigned __int64)(unsigned int)v12 << DataSectorShift, v25, DataSectorSize, &v22);
          if ( Map < 0 )
            goto LABEL_16;
          if ( v22 < (unsigned int)DataSectorSize )
            memset_0(&v2[v22], 0, (unsigned int)DataSectorSize - v22);
          Map = CDeltaList::GetMap(v3, v12, 1u, &v27);
          if ( Map < 0 )
            goto LABEL_16;
          v24 = 0;
          DataILB = CDeltaList::GetDataILB(v3);
          Map = ((__int64 (__fastcall *)(struct ILockBytes *, unsigned __int64, unsigned __int8 *, _QWORD, int *))DataILB->lpVtbl->WriteAt)(
                  DataILB,
                  (unsigned __int64)(v27 + 1) << DataSectorShift,
                  v2,
                  (unsigned int)DataSectorSize,
                  &v24);
          if ( Map < 0 )
            goto LABEL_16;
          LODWORD(v12) = v12 + 1;
        }
      }
    }
    DataFat = CDeltaList::GetDataFat(v3);
    Map = CFat::FindMaxSect(DataFat, &v28);
    if ( Map >= 0 )
    {
      --v28;
      for ( i = (a2 - 1) / DataSectorSize; (unsigned int)v12 <= (unsigned int)i; LODWORD(v12) = v12 + 1 )
      {
        Map = CDeltaList::GetMap(v3, v12, 1u, &v27);
        if ( Map < 0 )
          goto LABEL_15;
      }
      if ( (unsigned int)CDeltaList::IsNoScratch(v3) )
        v16 = *((_QWORD *)v3 + 3);
      else
        v16 = *((_QWORD *)v3 + 2);
      if ( v16 )
        v17 = (CMStream *)(v16 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v17 = 0;
      if ( (int)CMStream::SetSize(v17) < 0 )
      {
LABEL_15:
        CDeltaList::ReleaseInvalidSects(v3, v28);
        goto LABEL_16;
      }
LABEL_23:
      *((_QWORD *)this + 14) = a2;
    }
  }
LABEL_16:
  CoTaskMemFree(v2);
  return (unsigned int)Map;
}

```

## disassembly

```asm
0x180009da0  mov     [rsp-38h+arg_0], rbx
0x180009da5  push    rbp
0x180009da6  push    rsi
0x180009da7  push    rdi
0x180009da8  push    r12
0x180009daa  push    r13
0x180009dac  push    r14
0x180009dae  push    r15
0x180009db0  mov     rbp, rsp
0x180009db3  sub     rsp, 50h
0x180009db7  xor     r12d, r12d
0x180009dba  lea     rdi, [rcx+88h]
0x180009dc1  mov     [rbp+var_10], r12
0x180009dc5  mov     r14, rcx
0x180009dc8  mov     [rbp+arg_18], r12d
0x180009dcc  mov     r15, rdx
0x180009dcf  mov     rcx, rdi; this
0x180009dd2  test    rdx, rdx
0x180009dd5  jz      short loc_180009DF8
0x180009dd7  call    ?IsEmpty@CDeltaList@@QEAAHXZ; CDeltaList::IsEmpty(void)
0x180009ddc  mov     rdx, r15; unsigned __int64
0x180009ddf  test    eax, eax
0x180009de1  jnz     loc_180009F26
0x180009de7  call    ?InitResize@CDeltaList@@QEAAJ_K@Z; CDeltaList::InitResize(unsigned __int64)
0x180009dec  mov     ebx, eax
0x180009dee  test    eax, eax
0x180009df0  js      loc_180009EB3
0x180009df6  jmp     short loc_180009DFF
0x180009df8  xor     ebx, ebx
0x180009dfa  call    ?Empty@CDeltaList@@QEAAXXZ; CDeltaList::Empty(void)
0x180009dff  mov     r10, [r14+70h]
0x180009e03  cmp     r15, r10
0x180009e06  jbe     loc_180009F19
0x180009e0c  mov     rcx, rdi; this
0x180009e0f  call    ?GetDataSectorSize@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorSize(void)
0x180009e14  mov     rcx, rdi; this
0x180009e17  movzx   r13d, ax
0x180009e1b  call    ?GetDataSectorShift@CDeltaList@@QEAAGXZ; CDeltaList::GetDataSectorShift(void)
0x180009e20  mov     [rbp+arg_8], ax
0x180009e24  mov     ecx, r13d
0x180009e27  mov     [rbp+arg_10], r12d
0x180009e2b  test    r10, r10
0x180009e2e  jz      loc_180009F1F
0x180009e34  lea     rax, [r10-1]
0x180009e38  xor     edx, edx
0x180009e3a  div     rcx
0x180009e3d  mov     rsi, rax
0x180009e40  lea     r9, [rbp+arg_10]; unsigned int *
0x180009e44  xor     r8d, r8d; unsigned int
0x180009e47  mov     edx, esi; unsigned int
0x180009e49  mov     rcx, rdi; this
0x180009e4c  call    ?GetMap@CDeltaList@@QEAAJKKPEAK@Z; CDeltaList::GetMap(ulong,ulong,ulong *)
0x180009e51  mov     ebx, eax
0x180009e53  test    eax, eax
0x180009e55  js      short loc_180009EB3
0x180009e57  cmp     [rbp+arg_10], 0FFFFFFFEh
0x180009e5b  jz      loc_180009F33
0x180009e61  mov     rcx, rdi; this
0x180009e64  call    ?GetDataFat@CDeltaList@@QEAAPEAVCFat@@XZ; CDeltaList::GetDataFat(void)
0x180009e69  lea     rdx, [rbp+arg_18]; unsigned int *
0x180009e6d  mov     rcx, rax; this
0x180009e70  call    ?FindMaxSect@CFat@@QEAAJPEAK@Z; CFat::FindMaxSect(ulong *)
0x180009e75  mov     ebx, eax
0x180009e77  test    eax, eax
0x180009e79  js      short loc_180009EB3
0x180009e7b  dec     [rbp+arg_18]
0x180009e7e  lea     rax, [r15-1]
0x180009e82  xor     edx, edx
0x180009e84  div     r13
0x180009e87  mov     r13, rax
0x180009e8a  cmp     esi, eax
0x180009e8c  ja      short loc_180009EDD
0x180009e8e  lea     r9, [rbp+arg_10]; unsigned int *
0x180009e92  mov     r8d, 1; unsigned int
0x180009e98  mov     edx, esi; unsigned int
0x180009e9a  mov     rcx, rdi; this
0x180009e9d  call    ?GetMap@CDeltaList@@QEAAJKKPEAK@Z; CDeltaList::GetMap(ulong,ulong,ulong *)
0x180009ea2  mov     ebx, eax
0x180009ea4  test    eax, eax
0x180009ea6  jns     short loc_180009ED6
0x180009ea8  mov     edx, [rbp+arg_18]; unsigned int
0x180009eab  mov     rcx, rdi; this
0x180009eae  call    ?ReleaseInvalidSects@CDeltaList@@QEAAJK@Z; CDeltaList::ReleaseInvalidSects(ulong)
0x180009eb3  mov     rcx, r12; pv
0x180009eb6  call    cs:__imp_CoTaskMemFree
0x180009ebc  mov     eax, ebx
0x180009ebe  mov     rbx, [rsp+50h+arg_0]
0x180009ec6  add     rsp, 50h
0x180009eca  pop     r15
0x180009ecc  pop     r14
0x180009ece  pop     r13
0x180009ed0  pop     r12
0x180009ed2  pop     rdi
0x180009ed3  pop     rsi
0x180009ed4  pop     rbp
0x180009ed5  retn
0x180009ed6  inc     esi
0x180009ed8  cmp     esi, r13d
0x180009edb  jbe     short loc_180009E8E
0x180009edd  mov     rcx, rdi; this
0x180009ee0  call    ?IsNoScratch@CDeltaList@@QEAAHXZ; CDeltaList::IsNoScratch(void)
0x180009ee5  test    eax, eax
0x180009ee7  jnz     loc_180009F8C
0x180009eed  mov     rdx, [rdi+10h]
0x180009ef1  test    rdx, rdx
0x180009ef4  jz      loc_180009F95
0x180009efa  mov     rax, gs:30h
0x180009f03  mov     rcx, [rax+1758h]
0x180009f0a  mov     rcx, [rcx]
0x180009f0d  add     rcx, rdx; this
0x180009f10  call    ?SetSize@CMStream@@QEAAJXZ; CMStream::SetSize(void)
0x180009f15  test    eax, eax
0x180009f17  js      short loc_180009EA8
0x180009f19  mov     [r14+70h], r15
0x180009f1d  jmp     short loc_180009EB3
0x180009f1f  xor     esi, esi
0x180009f21  jmp     loc_180009E40
0x180009f26  mov     r8, r14; struct CTransactedStream *
0x180009f29  call    ?Init@CDeltaList@@QEAAJ_KPEAVCTransactedStream@@@Z; CDeltaList::Init(unsigned __int64,CTransactedStream *)
0x180009f2e  jmp     loc_180009DEC
0x180009f33  mov     rdx, [r14+78h]
0x180009f37  test    rdx, rdx
0x180009f3a  jz      loc_180009E61
0x180009f40  mov     rax, gs:30h
0x180009f49  mov     rcx, [rax+1758h]
0x180009f50  mov     rax, [rcx]
0x180009f53  add     rax, rdx
0x180009f56  jz      loc_180009E61
0x180009f5c  cmp     [r14+70h], r12
0x180009f60  jz      loc_180009E61
0x180009f66  lea     r9, [rbp+var_1C]; unsigned int *
0x180009f6a  mov     [rbp+var_1C], r12d
0x180009f6e  lea     r8, [rbp+var_10]; unsigned __int8 **
0x180009f72  mov     edx, r13d; unsigned int
0x180009f75  mov     ecx, r13d; unsigned int
0x180009f78  call    ?GetBuffer@@YAJKKPEAPEAEPEAK@Z; GetBuffer(ulong,ulong,uchar * *,ulong *)
0x180009f7d  mov     ebx, eax
0x180009f7f  test    eax, eax
0x180009f81  jns     short loc_180009F9C
0x180009f83  mov     r12, [rbp+var_10]
0x180009f87  jmp     loc_180009EB3
0x180009f8c  mov     rdx, [rdi+18h]
0x180009f90  jmp     loc_180009EF1
0x180009f95  xor     ecx, ecx
0x180009f97  jmp     loc_180009F10
0x180009f9c  mov     rdx, [r14+78h]
0x180009fa0  mov     [rbp+var_20], r12d
0x180009fa4  test    rdx, rdx
0x180009fa7  jz      loc_18000A074
0x180009fad  mov     rax, gs:30h
0x180009fb6  mov     rcx, [rax+1758h]
0x180009fbd  mov     r10, [rcx]
0x180009fc0  add     r10, rdx
0x180009fc3  movzx   ecx, [rbp+arg_8]
0x180009fc7  lea     rax, [rbp+var_20]
0x180009fcb  mov     r12, [rbp+var_10]
0x180009fcf  mov     r9d, r13d; unsigned int
0x180009fd2  mov     edx, esi
0x180009fd4  mov     r8, r12; void *
0x180009fd7  shl     rdx, cl; unsigned __int64
0x180009fda  mov     rcx, r10; this
0x180009fdd  mov     [rsp+50h+var_30], rax; unsigned int *
0x180009fe2  call    ?ReadAt@PSStream@@QEAAJ_KPEAXKPEAK@Z; PSStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x180009fe7  mov     ebx, eax
0x180009fe9  test    eax, eax
0x180009feb  js      loc_180009EB3
0x180009ff1  mov     ecx, [rbp+var_20]
0x180009ff4  cmp     ecx, r13d
0x180009ff7  jnb     short loc_18000A009
0x180009ff9  mov     r8d, r13d
0x180009ffc  xor     edx, edx; Val
0x180009ffe  sub     r8d, ecx; Size
0x18000a001  add     rcx, r12; void *
0x18000a004  call    memset_0
0x18000a009  lea     r9, [rbp+arg_10]; unsigned int *
0x18000a00d  mov     r8d, 1; unsigned int
0x18000a013  mov     edx, esi; unsigned int
0x18000a015  mov     rcx, rdi; this
0x18000a018  call    ?GetMap@CDeltaList@@QEAAJKKPEAK@Z; CDeltaList::GetMap(ulong,ulong,ulong *)
0x18000a01d  mov     ebx, eax
0x18000a01f  test    eax, eax
0x18000a021  js      loc_180009EB3
0x18000a027  mov     rcx, rdi; this
0x18000a02a  mov     [rbp+var_18], 0
0x18000a031  call    ?GetDataILB@CDeltaList@@QEAAPEAUILockBytes@@XZ; CDeltaList::GetDataILB(void)
0x18000a036  mov     edx, [rbp+arg_10]
0x18000a039  mov     r10, rax
0x18000a03c  movzx   ecx, [rbp+arg_8]
0x18000a040  inc     edx
0x18000a042  shl     rdx, cl
0x18000a045  mov     r9d, r13d
0x18000a048  mov     rcx, [rax]
0x18000a04b  mov     r8, r12
0x18000a04e  mov     rax, [rcx+20h]
0x18000a052  lea     rcx, [rbp+var_18]
0x18000a056  mov     [rsp+50h+var_30], rcx
0x18000a05b  mov     rcx, r10
0x18000a05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a063  mov     ebx, eax
0x18000a065  test    eax, eax
0x18000a067  js      loc_180009EB3
0x18000a06d  inc     esi
0x18000a06f  jmp     loc_180009E61
0x18000a074  xor     r10d, r10d
0x18000a077  jmp     loc_180009FC3
```
