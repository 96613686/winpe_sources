# CSyncMLCmd::GetResultsDataGeneric(IXmlWriter *)

- ea: `0x18000e490`
- end: `0x18000e934`
- name: `?GetResultsDataGeneric@CSyncMLCmd@@IEBAJPEAUIXmlWriter@@@Z`
- size: `1188`
- prototype: `__int64 __fastcall(CSyncMLCmd *__hidden this, struct IXmlWriter *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010b70`
- `0x1800208f0`
- `0x180020cd0`
- `0x180020ed0`

## callees

- `0x180002590`
- `0x180002a00`
- `0x1800038a0`
- `0x180003b60`
- `0x1800070a0`
- `0x18000e490`
- `0x180014330`
- `0x18001fee0`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e8fe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e8fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSyncMLCmd::GetResultsDataGeneric(CSyncMLCmd *this, struct IXmlWriter *a2)
{
  int v3; // ebx
  __int64 v4; // rax
  unsigned int v5; // r13d
  int v6; // ecx
  int ItemExecHresult; // esi
  int v8; // r12d
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int OmadmStatusCode; // r10d
  __int64 v14; // r15
  _QWORD *v15; // rcx
  __int64 *v16; // rdi
  __int64 v17; // rdi
  __int64 v18; // rbx
  struct IConfigManager2URI *TargetLocURI; // rax
  __int64 *v20; // rdi
  unsigned int v21; // r13d
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 *v25; // rdi
  unsigned int v26; // eax
  int v27; // edx
  const unsigned __int16 *v28; // rcx
  unsigned int v29; // r8d
  unsigned int i; // ebx
  int v32; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v33; // [rsp+64h] [rbp-55h]
  int v34[2]; // [rsp+68h] [rbp-51h] BYREF
  struct IConfigManager2URI *v35; // [rsp+70h] [rbp-49h] BYREF
  struct IXmlWriter *v36; // [rsp+78h] [rbp-41h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-29h] BYREF
  char *v39; // [rsp+A0h] [rbp-19h]
  int v40; // [rsp+A8h] [rbp-11h]
  int v41; // [rsp+ACh] [rbp-Dh]
  int *v42; // [rsp+B0h] [rbp-9h]
  __int64 v43; // [rsp+B8h] [rbp-1h]
  struct IConfigManager2URI **v44; // [rsp+C0h] [rbp+7h]
  __int64 v45; // [rsp+C8h] [rbp+Fh]

  v36 = a2;
  v3 = 0;
  v4 = *((_QWORD *)this + 17);
  if ( !v4 || (v5 = 1, *(_DWORD *)(v4 + 92) != 28) )
    v5 = 0;
  v33 = v5;
  v6 = 0;
  v32 = 0;
  if ( !a2 )
  {
    ItemExecHresult = -2147467261;
    goto LABEL_70;
  }
  ItemExecHresult = 0;
  v8 = 0;
  if ( v5 )
  {
    v8 = *(_DWORD *)(v4 + 56);
    if ( v8 >= 0 )
    {
      v9 = *(_QWORD *)(v4 + 96);
      if ( !v9 || (v8 = *(_DWORD *)(v9 + 132), v8 >= 0) )
        v8 = *(_DWORD *)(v4 + 60);
    }
  }
  v10 = *((unsigned int *)this + 14);
  if ( (int)v10 < 0
    || (v11 = *((_QWORD *)this + 12)) != 0 && (v10 = *(unsigned int *)(v11 + 132), (int)v10 < 0)
    || (v10 = *((unsigned int *)this + 15), (int)v10 < 0) )
  {
    v12 = *((_DWORD *)this + 23);
    OmadmStatusCode = GetOmadmStatusCode(v10, v12, v5, (unsigned int)v8);
    LODWORD(v14) = 1;
  }
  else
  {
    v15 = (_QWORD *)((char *)this + 8);
    *(_QWORD *)&EventDescriptor.Id = (char *)this + 8;
    v16 = (__int64 *)*((_QWORD *)this + 1);
    v14 = (__int64)(*((_QWORD *)this + 2) - (_QWORD)v16) >> 3;
    if ( !v14 )
    {
      *(_QWORD *)&EventDescriptor.Id = (char *)this + 8;
      LODWORD(v14) = 0;
      goto LABEL_64;
    }
    v17 = *v16;
    v3 = *(_DWORD *)(v17 + 88);
    if ( v3 >= 0 )
    {
      v18 = *(_QWORD *)(v17 + 16);
      if ( !v18 || (v3 = *(_DWORD *)(v18 + 132), v3 >= 0) )
      {
        v3 = *(_DWORD *)(v17 + 92);
        v34[0] = v3;
        if ( v3 >= 0 )
        {
          ItemExecHresult = CSyncMLItem::GetItemExecHresult((CSyncMLItem *)v17, v34);
          if ( ItemExecHresult < 0 )
          {
            v6 = v32;
            goto LABEL_70;
          }
          v3 = v34[0];
          if ( v34[0] >= 0 && (!v5 || v8 >= 0) )
          {
            TargetLocURI = CSyncMLItem::GetTargetLocURI((CSyncMLItem *)v17);
            v20 = (__int64 *)TargetLocURI;
            v35 = TargetLocURI;
            if ( TargetLocURI )
              (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)TargetLocURI + 8LL))(TargetLocURI);
            CSyncMLDPU::IsRebootRequiredCommand(*((_QWORD *)this + 10), *((unsigned int *)this + 23), v20, &v32);
            if ( v20 )
              (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
          }
        }
      }
    }
    v12 = *((_DWORD *)this + 23);
    OmadmStatusCode = GetOmadmStatusCode((unsigned int)v3, v12, v5, (unsigned int)v8);
    LODWORD(v35) = OmadmStatusCode;
    v21 = 1;
    if ( (unsigned int)v14 > 1 )
    {
      while ( 1 )
      {
        if ( (v22 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v21), v3 = *(_DWORD *)(v22 + 88), v3 < 0)
          || (v23 = *(_QWORD *)(v22 + 16)) != 0 && (v3 = *(_DWORD *)(v23 + 132), v3 < 0)
          || (v3 = *(_DWORD *)(v22 + 92), v34[0] = v3, v3 < 0) )
        {
          ItemExecHresult = 0;
        }
        else
        {
          ItemExecHresult = CSyncMLItem::GetItemExecHresult((CSyncMLItem *)v22, v34);
          if ( ItemExecHresult < 0 )
            goto LABEL_67;
          v3 = v34[0];
        }
        if ( v3 >= 0 && !v32 && (!v33 || v8 >= 0) )
        {
          v24 = *(_QWORD *)(v22 + 72);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
          v25 = *(__int64 **)(v22 + 72);
          *(_QWORD *)v34 = v25;
          if ( v25 )
            (*(void (__fastcall **)(__int64 *))(*v25 + 8))(v25);
          CSyncMLDPU::IsRebootRequiredCommand(*((_QWORD *)this + 10), *((unsigned int *)this + 23), v25, &v32);
          if ( v25 )
            (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
        }
        v12 = *((_DWORD *)this + 23);
        v26 = GetOmadmStatusCode((unsigned int)v3, v12, v33, (unsigned int)v8);
        OmadmStatusCode = (unsigned int)v35;
        if ( (_DWORD)v35 != v26 )
          break;
        OmadmStatusCode = v26;
        LODWORD(v35) = v26;
        if ( ++v21 >= (unsigned int)v14 )
          goto LABEL_54;
      }
      v15 = (_QWORD *)((char *)this + 8);
      goto LABEL_53;
    }
  }
  v15 = (_QWORD *)((char *)this + 8);
  if ( OmadmStatusCode != -1 )
  {
    *(_QWORD *)&EventDescriptor.Id = (char *)this + 8;
LABEL_53:
    if ( (_DWORD)v14 == 1 )
      goto LABEL_54;
    v5 = v33;
    a2 = v36;
LABEL_64:
    for ( i = 0; i < (unsigned int)v14; a2 = v36 )
    {
      ItemExecHresult = CSyncMLCmd::CreateStatusForItem(this, a2, *(struct CSyncMLItem **)(*v15 + 8LL * i), v5, v8);
      if ( ItemExecHresult < 0 )
        break;
      ++i;
      v15 = *(_QWORD **)&EventDescriptor.Id;
    }
    goto LABEL_67;
  }
LABEL_54:
  v27 = *(_DWORD *)(*((_QWORD *)this + 10) + 44LL);
  if ( v33 )
    v3 = v8;
  if ( v12 == 73 )
  {
    v28 = (const unsigned __int16 *)*((_QWORD *)this + 14);
  }
  else if ( v12 > 0x48 )
  {
    v28 = 0;
  }
  else
  {
    v28 = (&c_rgszSyncMLElem)[v12];
  }
  v29 = CSyncMLDPU::s_dwCurrClientCmdID++;
  ItemExecHresult = AddStatus(
                      v36,
                      OmadmStatusCode,
                      v29,
                      CSyncMLDPU::s_dwCurrServerMsgID,
                      *((const unsigned __int16 **)this + 13),
                      v28,
                      0,
                      0,
                      0,
                      0,
                      v3,
                      v27);
LABEL_67:
  v6 = v32;
  if ( v32 )
    *(_DWORD *)(*((_QWORD *)this + 10) + 444LL) |= 8u;
LABEL_70:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(v35) = ItemExecHresult;
    v32 = v6;
    v44 = &v35;
    v45 = 4;
    v42 = &v32;
    v43 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v39 = byte_180037291;
    v40 = 48;
    v41 = 1;
    v34[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return (unsigned int)ItemExecHresult;
}

```

## disassembly

```asm
0x18000e490  mov     [rsp-8+arg_10], rbx
0x18000e495  push    rbp
0x18000e496  push    rsi
0x18000e497  push    rdi
0x18000e498  push    r12
0x18000e49a  push    r13
0x18000e49c  push    r14
0x18000e49e  push    r15
0x18000e4a0  lea     rbp, [rsp-27h]
0x18000e4a5  sub     rsp, 0E0h
0x18000e4ac  mov     rax, cs:__security_cookie
0x18000e4b3  xor     rax, rsp
0x18000e4b6  mov     [rbp+57h+var_40], rax
0x18000e4ba  mov     [rbp+57h+var_98], rdx
0x18000e4be  mov     r14, rcx
0x18000e4c1  xor     edi, edi
0x18000e4c3  mov     ebx, edi
0x18000e4c5  mov     rax, [rcx+88h]
0x18000e4cc  test    rax, rax
0x18000e4cf  jz      short loc_18000E4DD
0x18000e4d1  cmp     dword ptr [rax+5Ch], 1Ch
0x18000e4d5  mov     r13d, 1
0x18000e4db  jz      short loc_18000E4E0
0x18000e4dd  mov     r13d, edi
0x18000e4e0  mov     [rbp+57h+var_AC], r13d
0x18000e4e4  mov     ecx, edi
0x18000e4e6  mov     [rbp+57h+var_B0], ecx
0x18000e4e9  test    rdx, rdx
0x18000e4ec  jnz     short loc_18000E4F8
0x18000e4ee  mov     esi, 80004003h
0x18000e4f3  jmp     loc_18000E84B
0x18000e4f8  mov     esi, edi
0x18000e4fa  mov     r12d, edi
0x18000e4fd  test    r13d, r13d
0x18000e500  jz      short loc_18000E524
0x18000e502  mov     r12d, [rax+38h]
0x18000e506  test    r12d, r12d
0x18000e509  js      short loc_18000E524
0x18000e50b  mov     rcx, [rax+60h]
0x18000e50f  test    rcx, rcx
0x18000e512  jz      short loc_18000E520
0x18000e514  mov     r12d, [rcx+84h]
0x18000e51b  test    r12d, r12d
0x18000e51e  js      short loc_18000E524
0x18000e520  mov     r12d, [rax+3Ch]
0x18000e524  mov     ecx, [r14+38h]
0x18000e528  test    ecx, ecx
0x18000e52a  js      short loc_18000E547
0x18000e52c  mov     rcx, [r14+60h]
0x18000e530  test    rcx, rcx
0x18000e533  jz      short loc_18000E53F
0x18000e535  mov     ecx, [rcx+84h]
0x18000e53b  test    ecx, ecx
0x18000e53d  js      short loc_18000E547
0x18000e53f  mov     ecx, [r14+3Ch]
0x18000e543  test    ecx, ecx
0x18000e545  jns     short loc_18000E578
0x18000e547  mov     edi, [r14+5Ch]
0x18000e54b  mov     r9d, r12d
0x18000e54e  mov     r8d, r13d
0x18000e551  mov     edx, edi
0x18000e553  call    GetOmadmStatusCode
0x18000e558  mov     r10d, eax
0x18000e55b  mov     r15d, 1
0x18000e561  lea     rcx, [r14+8]
0x18000e565  cmp     r10d, 0FFFFFFFFh
0x18000e569  jz      loc_18000E75C
0x18000e56f  mov     qword ptr [rbp+57h+EventDescriptor.Id], rcx
0x18000e573  jmp     loc_18000E752
0x18000e578  lea     rcx, [r14+8]
0x18000e57c  mov     qword ptr [rbp+57h+EventDescriptor.Id], rcx
0x18000e580  mov     rdi, [rcx]
0x18000e583  mov     r15, [rcx+8]
0x18000e587  sub     r15, rdi
0x18000e58a  sar     r15, 3
0x18000e58e  test    r15, r15
0x18000e591  jz      loc_18000E7E0
0x18000e597  mov     rdi, [rdi]
0x18000e59a  mov     ebx, [rdi+58h]
0x18000e59d  test    ebx, ebx
0x18000e59f  js      loc_18000E637
0x18000e5a5  mov     rbx, [rdi+10h]
0x18000e5a9  test    rbx, rbx
0x18000e5ac  jz      short loc_18000E5B8
0x18000e5ae  mov     ebx, [rbx+84h]
0x18000e5b4  test    ebx, ebx
0x18000e5b6  js      short loc_18000E637
0x18000e5b8  mov     ebx, [rdi+5Ch]
0x18000e5bb  mov     [rbp+57h+var_A8], ebx
0x18000e5be  test    ebx, ebx
0x18000e5c0  js      short loc_18000E637
0x18000e5c2  lea     rdx, [rbp+57h+var_A8]; int *
0x18000e5c6  mov     rcx, rdi; this
0x18000e5c9  call    ?GetItemExecHresult@CSyncMLItem@@QEAAJPEAJ@Z; CSyncMLItem::GetItemExecHresult(long *)
0x18000e5ce  mov     esi, eax
0x18000e5d0  test    eax, eax
0x18000e5d2  js      loc_18000E846
0x18000e5d8  mov     ebx, [rbp+57h+var_A8]
0x18000e5db  test    ebx, ebx
0x18000e5dd  js      short loc_18000E637
0x18000e5df  test    r13d, r13d
0x18000e5e2  jz      short loc_18000E5E9
0x18000e5e4  test    r12d, r12d
0x18000e5e7  js      short loc_18000E637
0x18000e5e9  mov     rcx, rdi; this
0x18000e5ec  call    ?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetTargetLocURI(void)
0x18000e5f1  mov     rdi, rax
0x18000e5f4  mov     [rbp+57h+var_A0], rax
0x18000e5f8  test    rax, rax
0x18000e5fb  jz      short loc_18000E60D
0x18000e5fd  mov     rax, [rax]
0x18000e600  mov     rcx, rdi
0x18000e603  mov     rax, [rax+8]
0x18000e607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e60c  nop
0x18000e60d  lea     r9, [rbp+57h+var_B0]
0x18000e611  mov     r8, rdi
0x18000e614  mov     edx, [r14+5Ch]
0x18000e618  mov     rcx, [r14+50h]
0x18000e61c  call    ?IsRebootRequiredCommand@CSyncMLDPU@@QEAAJW4SyncMLElemType@@PEAUIConfigManager2URI@@PEAH@Z; CSyncMLDPU::IsRebootRequiredCommand(SyncMLElemType,IConfigManager2URI *,int *)
0x18000e621  nop
0x18000e622  test    rdi, rdi
0x18000e625  jz      short loc_18000E637
0x18000e627  mov     rax, [rdi]
0x18000e62a  mov     rcx, rdi
0x18000e62d  mov     rax, [rax+10h]
0x18000e631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e636  nop
0x18000e637  mov     edi, [r14+5Ch]
0x18000e63b  mov     r9d, r12d
0x18000e63e  mov     r8d, r13d
0x18000e641  mov     edx, edi
0x18000e643  mov     ecx, ebx
0x18000e645  call    GetOmadmStatusCode
0x18000e64a  mov     r10d, eax
0x18000e64d  mov     dword ptr [rbp+57h+var_A0], eax
0x18000e650  mov     r13d, 1
0x18000e656  cmp     r15d, r13d
0x18000e659  jbe     loc_18000E561
0x18000e65f  nop
0x18000e660  mov     ecx, r13d
0x18000e663  mov     rax, [r14+8]
0x18000e667  mov     rdi, [rax+rcx*8]
0x18000e66b  mov     ebx, [rdi+58h]
0x18000e66e  test    ebx, ebx
0x18000e670  js      short loc_18000E6AA
0x18000e672  mov     rbx, [rdi+10h]
0x18000e676  test    rbx, rbx
0x18000e679  jz      short loc_18000E685
0x18000e67b  mov     ebx, [rbx+84h]
0x18000e681  test    ebx, ebx
0x18000e683  js      short loc_18000E6AA
0x18000e685  mov     ebx, [rdi+5Ch]
0x18000e688  mov     [rbp+57h+var_A8], ebx
0x18000e68b  test    ebx, ebx
0x18000e68d  js      short loc_18000E6AA
0x18000e68f  lea     rdx, [rbp+57h+var_A8]; int *
0x18000e693  mov     rcx, rdi; this
0x18000e696  call    ?GetItemExecHresult@CSyncMLItem@@QEAAJPEAJ@Z; CSyncMLItem::GetItemExecHresult(long *)
0x18000e69b  mov     esi, eax
0x18000e69d  test    eax, eax
0x18000e69f  js      loc_18000E830
0x18000e6a5  mov     ebx, [rbp+57h+var_A8]
0x18000e6a8  jmp     short loc_18000E6AC
0x18000e6aa  xor     esi, esi
0x18000e6ac  test    ebx, ebx
0x18000e6ae  js      short loc_18000E71D
0x18000e6b0  cmp     [rbp+57h+var_B0], 0
0x18000e6b4  jnz     short loc_18000E71D
0x18000e6b6  cmp     [rbp+57h+var_AC], 0
0x18000e6ba  jz      short loc_18000E6C1
0x18000e6bc  test    r12d, r12d
0x18000e6bf  js      short loc_18000E71D
0x18000e6c1  mov     rcx, [rdi+48h]
0x18000e6c5  test    rcx, rcx
0x18000e6c8  jz      short loc_18000E6D6
0x18000e6ca  mov     rax, [rcx]
0x18000e6cd  mov     rax, [rax+8]
0x18000e6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d6  mov     rdi, [rdi+48h]
0x18000e6da  mov     qword ptr [rbp+57h+var_A8], rdi
0x18000e6de  test    rdi, rdi
0x18000e6e1  jz      short loc_18000E6F3
0x18000e6e3  mov     rax, [rdi]
0x18000e6e6  mov     rcx, rdi
0x18000e6e9  mov     rax, [rax+8]
0x18000e6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6f2  nop
0x18000e6f3  lea     r9, [rbp+57h+var_B0]
0x18000e6f7  mov     r8, rdi
0x18000e6fa  mov     edx, [r14+5Ch]
0x18000e6fe  mov     rcx, [r14+50h]
0x18000e702  call    ?IsRebootRequiredCommand@CSyncMLDPU@@QEAAJW4SyncMLElemType@@PEAUIConfigManager2URI@@PEAH@Z; CSyncMLDPU::IsRebootRequiredCommand(SyncMLElemType,IConfigManager2URI *,int *)
0x18000e707  nop
0x18000e708  test    rdi, rdi
0x18000e70b  jz      short loc_18000E71D
0x18000e70d  mov     rax, [rdi]
0x18000e710  mov     rcx, rdi
0x18000e713  mov     rax, [rax+10h]
0x18000e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e71c  nop
0x18000e71d  mov     edi, [r14+5Ch]
0x18000e721  mov     r9d, r12d
0x18000e724  mov     r8d, [rbp+57h+var_AC]
0x18000e728  mov     edx, edi
0x18000e72a  mov     ecx, ebx
0x18000e72c  call    GetOmadmStatusCode
0x18000e731  mov     r10d, dword ptr [rbp+57h+var_A0]
0x18000e735  cmp     r10d, eax
0x18000e738  jnz     short loc_18000E74E
0x18000e73a  mov     r10d, eax
0x18000e73d  mov     dword ptr [rbp+57h+var_A0], eax
0x18000e740  inc     r13d
0x18000e743  cmp     r13d, r15d
0x18000e746  jb      loc_18000E660
0x18000e74c  jmp     short loc_18000E75C
0x18000e74e  lea     rcx, [r14+8]
0x18000e752  cmp     r15d, 1
0x18000e756  jnz     loc_18000E7EB
0x18000e75c  mov     rax, [r14+50h]
0x18000e760  mov     edx, [rax+2Ch]
0x18000e763  cmp     [rbp+57h+var_AC], 0
0x18000e767  cmovnz  ebx, r12d
0x18000e76b  cmp     edi, 49h ; 'I'
0x18000e76e  jnz     short loc_18000E776
0x18000e770  mov     rcx, [r14+70h]
0x18000e774  jmp     short loc_18000E78D
0x18000e776  cmp     edi, 48h ; 'H'
0x18000e779  ja      short loc_18000E78B
0x18000e77b  movsxd  rax, edi
0x18000e77e  lea     rcx, ?c_rgszSyncMLElem@@3PAPEBGA; ushort const * near * c_rgszSyncMLElem
0x18000e785  mov     rcx, [rcx+rax*8]
0x18000e789  jmp     short loc_18000E78D
0x18000e78b  xor     ecx, ecx
0x18000e78d  mov     r8d, cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA; unsigned int
0x18000e794  lea     eax, [r8+1]
0x18000e798  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, eax; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x18000e79e  mov     [rsp+110h+var_B8], edx; int
0x18000e7a2  mov     [rsp+110h+var_C0], ebx; int
0x18000e7a6  xor     edi, edi
0x18000e7a8  mov     [rsp+110h+var_C8], edi; unsigned int
0x18000e7ac  mov     [rsp+110h+var_D0], rdi; struct CSyncMLItem **
0x18000e7b1  mov     [rsp+110h+var_D8], rdi; unsigned __int16 *
0x18000e7b6  mov     [rsp+110h+var_E0], rdi; unsigned __int16 *
0x18000e7bb  mov     [rsp+110h+UserData], rcx; unsigned __int16 *
0x18000e7c0  mov     rax, [r14+68h]
0x18000e7c4  mov     qword ptr [rsp+110h+UserDataCount], rax; unsigned __int16 *
0x18000e7c9  mov     r9d, cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA; unsigned int
0x18000e7d0  mov     edx, r10d; unsigned int
0x18000e7d3  mov     rcx, [rbp+57h+var_98]; struct IXmlWriter *
0x18000e7d7  call    ?AddStatus@@YAJPEAUIXmlWriter@@KKKPEBG111PEAPEAVCSyncMLItem@@KJH@Z; AddStatus(IXmlWriter *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,CSyncMLItem * *,ulong,long,int)
0x18000e7dc  mov     esi, eax
0x18000e7de  jmp     short loc_18000E832
0x18000e7e0  mov     qword ptr [rbp+57h+EventDescriptor.Id], rcx
0x18000e7e4  xor     edi, edi
0x18000e7e6  mov     r15d, edi
0x18000e7e9  jmp     short loc_18000E7F5
0x18000e7eb  mov     r13d, [rbp+57h+var_AC]
0x18000e7ef  mov     rdx, [rbp+57h+var_98]; struct IXmlWriter *
0x18000e7f3  xor     edi, edi
0x18000e7f5  mov     ebx, edi
0x18000e7f7  test    r15d, r15d
0x18000e7fa  jz      short loc_18000E832
0x18000e7fc  nop     dword ptr [rax+00h]
0x18000e800  mov     eax, ebx
0x18000e802  mov     r8, [rcx]
0x18000e805  mov     [rsp+110h+UserDataCount], r12d; int
0x18000e80a  mov     r9d, r13d; int
0x18000e80d  mov     r8, [r8+rax*8]; struct CSyncMLItem *
0x18000e811  mov     rcx, r14; this
0x18000e814  call    ?CreateStatusForItem@CSyncMLCmd@@IEBAJPEAUIXmlWriter@@PEAVCSyncMLItem@@HJ@Z; CSyncMLCmd::CreateStatusForItem(IXmlWriter *,CSyncMLItem *,int,long)
0x18000e819  mov     esi, eax
0x18000e81b  test    eax, eax
0x18000e81d  js      short loc_18000E832
0x18000e81f  inc     ebx
0x18000e821  cmp     ebx, r15d
0x18000e824  mov     rcx, qword ptr [rbp+57h+EventDescriptor.Id]
0x18000e828  mov     rdx, [rbp+57h+var_98]
0x18000e82c  jb      short loc_18000E800
0x18000e82e  jmp     short loc_18000E832
0x18000e830  xor     edi, edi
0x18000e832  mov     ecx, [rbp+57h+var_B0]
0x18000e835  test    ecx, ecx
0x18000e837  jz      short loc_18000E84B
0x18000e839  mov     rax, [r14+50h]
0x18000e83d  or      dword ptr [rax+1BCh], 8
0x18000e844  jmp     short loc_18000E84B
0x18000e846  mov     ecx, [rbp+57h+var_B0]
0x18000e849  xor     edi, edi
0x18000e84b  mov     eax, cs:dword_18003E048
0x18000e851  cmp     eax, 5
0x18000e854  jbe     loc_18000E90A
0x18000e85a  mov     dword ptr [rbp+57h+var_A0], esi
0x18000e85d  mov     [rbp+57h+var_B0], ecx
0x18000e860  lea     rax, [rbp+57h+var_A0]
0x18000e864  mov     [rbp+57h+var_50], rax
0x18000e868  mov     [rbp+57h+var_48], 4
0x18000e870  lea     rax, [rbp+57h+var_B0]
0x18000e874  mov     [rbp+57h+var_60], rax
0x18000e878  mov     [rbp+57h+var_58], 4
  ... truncated ...
```
