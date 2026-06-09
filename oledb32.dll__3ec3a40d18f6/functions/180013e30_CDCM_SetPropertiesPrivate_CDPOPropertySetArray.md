# CDCM::SetPropertiesPrivate(CDPOPropertySetArray *)

- ea: `0x180013e30`
- end: `0x180013fee`
- name: `?SetPropertiesPrivate@CDCM@@QEAAJPEAVCDPOPropertySetArray@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(CDCM *__hidden this, struct CDPOPropertySetArray *)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18005b3a0`
- `0x18005bd4c`
- `0x18005d070`
- `0x180064720`

## callees

- `0x180012784`
- `0x180013870`
- `0x180013e30`
- `0x1800150ac`
- `0x180015be8`
- `0x180022bf8`
- `0x180029560`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180013e5d`
- `KERNEL32!EnterCriticalSection` at `0x180013e5d`
- `KERNEL32!LeaveCriticalSection` at `0x180013f80`
- `KERNEL32!LeaveCriticalSection` at `0x180013f80`
- `ole32!CoTaskMemFree` at `0x180013fab`
- `ole32!CoTaskMemFree` at `0x180013fab`

## pseudocode

```c
__int64 __fastcall CDCM::SetPropertiesPrivate(CDCM *this, struct CDPOPropertySetArray *a2)
{
  unsigned int v3; // ebx
  unsigned int v5; // esi
  struct tagDBPROPSET *v6; // rbp
  unsigned int v7; // r14d
  struct tagDBPROPSET *v8; // r15
  int PropertiesPrivate; // eax
  __int64 Provider; // rdi
  unsigned int v11; // r9d
  __int64 v12; // r8
  __int64 v13; // r10
  __int64 v14; // rdx
  int v15; // eax
  struct tagDBPROPSET *i; // rdi
  struct tagDBPROPSET *v17; // rcx
  unsigned int v19; // [rsp+60h] [rbp+8h] BYREF
  struct tagDBPROPSET *v20; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v19 = 0;
  v20 = 0;
  v5 = 0;
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v7 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 )
  {
    v8 = (struct tagDBPROPSET *)*((_QWORD *)a2 + 1);
    PropertiesPrivate = CDPOPropertySetArray::GetPropertiesPrivate(a2, &v19, &v20, 1);
    v3 = PropertiesPrivate;
    if ( PropertiesPrivate >= 0 )
    {
      v5 = v19;
      v6 = v20;
      Provider = GetProviderPointer<CDCM>(this, &IID_IDBProperties);
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *))(*(_QWORD *)Provider + 40LL))(
             Provider,
             v5,
             v6);
      if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147217887 )
      {
        v11 = 0;
        do
        {
          v12 = 0;
          v13 = v11;
          if ( v8[v13].cProperties )
          {
            do
            {
              v14 = v12;
              v12 = (unsigned int)(v12 + 1);
              v8[v13].rgProperties[v14].dwStatus = v6[v13].rgProperties[v14].dwStatus;
            }
            while ( (unsigned int)v12 < v8[v13].cProperties );
          }
          ++v11;
        }
        while ( v11 < v7 );
        v15 = CDCM::SetPropertiesInternal(this, v7, v8, 0);
        v3 = v15;
        if ( v15 < 0 && (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v15, L"<CDCM::SetPropertiesPrivate|OLEDB|ERR> ", 0x473u);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)Provider + 16LL))(Provider);
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(PropertiesPrivate, L"<CDCM::SetPropertiesPrivate|OLEDB|ERR> ", 0x451u);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v6 )
  {
    for ( i = v6; v5; --v5 )
    {
      v17 = i++;
      TDSLSet<tagDBPROPSET,CDSLProperty>::Free(v17, 1);
    }
    CoTaskMemFree(v6);
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C84C8[0], 1176585, L"<CDCM::SetPropertiesPrivate|Trace|HR> ", v3);
  return v3;
}

```

## disassembly

```asm
0x180013e30  mov     [rsp+arg_10], rbx
0x180013e35  push    rbp
0x180013e36  push    rsi
0x180013e37  push    rdi
0x180013e38  push    r12
0x180013e3a  push    r13
0x180013e3c  push    r14
0x180013e3e  push    r15
0x180013e40  sub     rsp, 20h
0x180013e44  mov     r13, rcx
0x180013e47  xor     ebx, ebx
0x180013e49  add     rcx, 18h; lpCriticalSection
0x180013e4d  mov     [rsp+58h+arg_0], ebx
0x180013e51  mov     [rsp+58h+arg_8], rbx
0x180013e56  mov     rdi, rdx
0x180013e59  xor     esi, esi
0x180013e5b  xor     ebp, ebp
0x180013e5d  call    cs:__imp_EnterCriticalSection
0x180013e63  mov     r14d, [rdi]
0x180013e66  test    r14d, r14d
0x180013e69  jz      loc_180013F7C
0x180013e6f  mov     r15, [rdi+8]
0x180013e73  lea     r9d, [rbx+1]; int
0x180013e77  lea     r8, [rsp+58h+arg_8]; struct tagDBPROPSET **
0x180013e7c  mov     rcx, rdi; this
0x180013e7f  lea     rdx, [rsp+58h+arg_0]; unsigned int *
0x180013e84  call    ?GetPropertiesPrivate@CDPOPropertySetArray@@QEAAJPEAKPEAPEAUtagDBPROPSET@@H@Z; CDPOPropertySetArray::GetPropertiesPrivate(ulong *,tagDBPROPSET * *,int)
0x180013e89  mov     ebx, eax
0x180013e8b  test    eax, eax
0x180013e8d  jns     short loc_180013EB5
0x180013e8f  test    byte ptr cs:_bidGblFlags, 2
0x180013e96  jz      loc_180013F7C
0x180013e9c  mov     r8d, 451h; unsigned int
0x180013ea2  lea     rdx, aCdcmSetpropert; "<CDCM::SetPropertiesPrivate|OLEDB|ERR> "
0x180013ea9  mov     ecx, eax; int
0x180013eab  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180013eb0  jmp     loc_180013F7C
0x180013eb5  mov     esi, [rsp+58h+arg_0]
0x180013eb9  lea     rdx, IID_IDBProperties
0x180013ec0  mov     rbp, [rsp+58h+arg_8]
0x180013ec5  mov     rcx, r13
0x180013ec8  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x180013ecd  mov     rdi, rax
0x180013ed0  mov     r8, rbp
0x180013ed3  mov     edx, esi
0x180013ed5  mov     rcx, [rax]
0x180013ed8  mov     rax, [rcx+28h]
0x180013edc  mov     rcx, rdi
0x180013edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ee4  mov     ebx, eax
0x180013ee6  mov     eax, 80000000h
0x180013eeb  lea     ecx, [rbx+rax]
0x180013eee  test    eax, ecx
0x180013ef0  jnz     short loc_180013EFA
0x180013ef2  cmp     ebx, 80040E21h
0x180013ef8  jnz     short loc_180013F6D
0x180013efa  xor     r9d, r9d
0x180013efd  test    r14d, r14d
0x180013f00  jz      short loc_180013F39
0x180013f02  mov     r10d, r9d
0x180013f05  xor     r8d, r8d
0x180013f08  shl     r10, 5
0x180013f0c  cmp     [r10+r15+8], r8d
0x180013f11  jbe     short loc_180013F31
0x180013f13  mov     rax, [r10+rbp]
0x180013f17  lea     rdx, [r8+r8*8]
0x180013f1b  mov     rcx, [r10+r15]
0x180013f1f  inc     r8d
0x180013f22  mov     eax, [rax+rdx*8+8]
0x180013f26  mov     [rcx+rdx*8+8], eax
0x180013f2a  cmp     r8d, [r10+r15+8]
0x180013f2f  jb      short loc_180013F13
0x180013f31  inc     r9d
0x180013f34  cmp     r9d, r14d
0x180013f37  jb      short loc_180013F02
0x180013f39  xor     r9d, r9d; bool
0x180013f3c  mov     r8, r15; struct tagDBPROPSET *
0x180013f3f  mov     edx, r14d; unsigned int
0x180013f42  mov     rcx, r13; this
0x180013f45  call    ?SetPropertiesInternal@CDCM@@QEAAJKQEAUtagDBPROPSET@@_N@Z; CDCM::SetPropertiesInternal(ulong,tagDBPROPSET * const,bool)
0x180013f4a  mov     ebx, eax
0x180013f4c  test    eax, eax
0x180013f4e  jns     short loc_180013F6D
0x180013f50  test    byte ptr cs:_bidGblFlags, 2
0x180013f57  jz      short loc_180013F6D
0x180013f59  mov     r8d, 473h; unsigned int
0x180013f5f  lea     rdx, aCdcmSetpropert; "<CDCM::SetPropertiesPrivate|OLEDB|ERR> "
0x180013f66  mov     ecx, eax; int
0x180013f68  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180013f6d  mov     rax, [rdi]
0x180013f70  mov     rcx, rdi
0x180013f73  mov     rax, [rax+10h]
0x180013f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f7c  lea     rcx, [r13+18h]; lpCriticalSection
0x180013f80  call    cs:__imp_LeaveCriticalSection
0x180013f86  test    rbp, rbp
0x180013f89  jz      short loc_180013FB1
0x180013f8b  mov     rdi, rbp
0x180013f8e  test    esi, esi
0x180013f90  jz      short loc_180013FA8
0x180013f92  mov     rcx, rdi
0x180013f95  mov     edx, 1
0x180013f9a  add     rdi, 20h ; ' '
0x180013f9e  call    ?Free@?$TDSLSet@UtagDBPROPSET@@VCDSLProperty@@@@QEAAXH@Z; TDSLSet<tagDBPROPSET,CDSLProperty>::Free(int)
0x180013fa3  sub     esi, 1
0x180013fa6  jnz     short loc_180013F92
0x180013fa8  mov     rcx, rbp; pv
0x180013fab  call    cs:__imp_CoTaskMemFree
0x180013fb1  test    byte ptr cs:_bidGblFlags, 2
0x180013fb8  jz      short loc_180013FD7
0x180013fba  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180013fc1  lea     r8, aCdcmSetpropert_2; "<CDCM::SetPropertiesPrivate|Trace|HR> "
0x180013fc8  mov     r9d, ebx
0x180013fcb  mov     edx, 11F409h
0x180013fd0  call    _bidTraceHR
0x180013fd5  mov     ebx, eax
0x180013fd7  mov     eax, ebx
0x180013fd9  mov     rbx, [rsp+58h+arg_10]
0x180013fde  add     rsp, 20h
0x180013fe2  pop     r15
0x180013fe4  pop     r14
0x180013fe6  pop     r13
0x180013fe8  pop     r12
0x180013fea  pop     rdi
0x180013feb  pop     rsi
0x180013fec  pop     rbp
0x180013fed  retn
```
