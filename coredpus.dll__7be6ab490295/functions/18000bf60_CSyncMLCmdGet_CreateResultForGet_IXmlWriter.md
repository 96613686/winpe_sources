# CSyncMLCmdGet::CreateResultForGet(IXmlWriter *)

- ea: `0x18000bf60`
- end: `0x18000c5f6`
- name: `?CreateResultForGet@CSyncMLCmdGet@@AEBAJPEAUIXmlWriter@@@Z`
- size: `1686`
- prototype: `__int64 __fastcall(CSyncMLCmdGet *__hidden this, struct IXmlWriter *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020cd0`

## callees

- `0x180002860`
- `0x1800044e0`
- `0x18000bf60`
- `0x180010654`
- `0x180014330`
- `0x18002085c`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c5c0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c5c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c211`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c456`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c4eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c211`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c456`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c4eb`
- `DMCmnUtils!InvStrCmpIW` at `0x18000c1eb`
- `DMCmnUtils!InvStrCmpIW` at `0x18000c367`
- `DMCmnUtils!InvStrCmpIW` at `0x18000c1eb`
- `DMCmnUtils!InvStrCmpIW` at `0x18000c367`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncMLCmdGet::CreateResultForGet(CSyncMLCmdGet *this, struct IXmlWriter *a2)
{
  CSyncMLCmdGet *v3; // r14
  int v4; // ebx
  STRSAFE_PCNZWCH v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  wchar_t *v8; // rax
  __int64 v9; // rdx
  wchar_t *v10; // rax
  struct IConfigManager2URI *v11; // r12
  wchar_t *v12; // rdx
  int v13; // edi
  __int64 v14; // r13
  __int64 v15; // r15
  unsigned int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  const unsigned __int16 *v19; // rcx
  CSyncMLCmd *v20; // rcx
  BSTR v21; // rax
  int v22; // r14d
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned __int16 *v26; // rdi
  const unsigned __int16 *Type; // rax
  const unsigned __int16 *v28; // rdi
  __int64 v29; // rcx
  int v30; // eax
  ULONG UserDataCount[2]; // [rsp+20h] [rbp-79h]
  ULONG UserDataCounta[2]; // [rsp+20h] [rbp-79h]
  BSTR bstrString; // [rsp+30h] [rbp-69h] BYREF
  int v35; // [rsp+38h] [rbp-61h] BYREF
  wchar_t *v36; // [rsp+40h] [rbp-59h]
  STRSAFE_PCNZWCH v37; // [rsp+48h] [rbp-51h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  STRSAFE_PCNZWCH v39; // [rsp+60h] [rbp-39h]
  wchar_t *v40; // [rsp+68h] [rbp-31h]
  __int64 v41; // [rsp+70h] [rbp-29h]
  CSyncMLCmdGet *v42; // [rsp+78h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  int *v44; // [rsp+90h] [rbp-9h]
  int v45; // [rsp+98h] [rbp-1h]
  int v46; // [rsp+9Ch] [rbp+3h]
  int *v47; // [rsp+A0h] [rbp+7h]
  __int64 v48; // [rsp+A8h] [rbp+Fh]

  v3 = this;
  v42 = this;
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_83;
  }
  v5 = off_18003E2E0;
  v39 = off_18003E2E0;
  if ( !off_18003E2E0 )
    goto LABEL_82;
  v6 = 0x7FFFFFFF;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v7;
  }
  while ( v7 );
  v4 = -2147024809;
  if ( !v7 )
    goto LABEL_82;
  v8 = off_18003E2A8[0];
  v40 = off_18003E2A8[0];
  if ( !off_18003E2A8[0] )
    goto LABEL_82;
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  if ( !v9 )
  {
LABEL_82:
    v4 = -2147024809;
    goto LABEL_83;
  }
  v10 = off_18003E2E8[0];
  v36 = off_18003E2E8[0];
  if ( off_18003E2E8[0] )
  {
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v6;
    }
    while ( v6 );
    if ( v6 )
    {
      v4 = 0;
      v11 = 0;
      v12 = off_18003E358[0];
      *(wchar_t **)&EventDescriptor.Id = off_18003E358[0];
      v37 = off_18003E470;
      v41 = (__int64)(*((_QWORD *)v3 + 22) - *((_QWORD *)v3 + 21)) >> 3;
      v13 = 0;
      v35 = 0;
      v14 = 0;
      if ( (_DWORD)v41 )
      {
        while ( 1 )
        {
          bstrString = 0;
          v15 = *(_QWORD *)(*((_QWORD *)v3 + 21) + 8 * v14);
          if ( !v13 )
          {
            v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, wchar_t *, _QWORD))a2->lpVtbl->WriteStartElement)(
                   a2,
                   0,
                   v12,
                   0);
            if ( v4 < 0 )
              goto LABEL_78;
            v16 = CSyncMLDPU::s_dwCurrClientCmdID++;
            UserDataCount[0] = v16;
            v4 = AddSubnode(a2, 0, off_18003E258[0], 1, *(_QWORD *)UserDataCount);
            if ( v4 < 0 )
              goto LABEL_78;
            UserDataCounta[0] = CSyncMLDPU::s_dwCurrServerMsgID;
            v4 = AddSubnode(a2, 0, off_18003E290[0], 1, *(_QWORD *)UserDataCounta);
            if ( v4 < 0 )
              goto LABEL_78;
            v4 = AddSubnode(a2, 0, off_18003E260[0], 2, *((_QWORD *)v3 + 13));
            if ( v4 < 0 )
              goto LABEL_78;
            v35 = 1;
          }
          v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, STRSAFE_PCNZWCH, _QWORD))a2->lpVtbl->WriteStartElement)(
                 a2,
                 0,
                 v39,
                 0);
          if ( v4 < 0 )
            goto LABEL_78;
          v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, wchar_t *, _QWORD))a2->lpVtbl->WriteStartElement)(
                 a2,
                 0,
                 v40,
                 0);
          if ( v4 < 0 )
            goto LABEL_78;
          v17 = *(_QWORD *)(v15 + 72);
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          v11 = *(struct IConfigManager2URI **)(v15 + 72);
          v18 = *((_QWORD *)v3 + 9);
          if ( v18 )
          {
            v19 = *(const unsigned __int16 **)(v18 + 24);
            if ( (!v19 || !InvStrCmpIW(v19, L"1.0")) && (unsigned int)CSyncMLCmd::IsWmiQuery(v11) == 1 )
            {
              v20 = (CSyncMLCmd *)bstrString;
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              CSyncMLCmd::GetOriginalQueryPath(v20, v11, &bstrString);
            }
          }
          v21 = bstrString;
          if ( !bstrString )
          {
            v4 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v11 + 64LL))(
                   v11,
                   0,
                   *(unsigned int *)(v15 + 108),
                   &bstrString);
            if ( v4 < 0 )
              goto LABEL_78;
            v21 = bstrString;
          }
          v4 = AddSubnode(a2, 0, off_18003E280[0], 2, v21);
          if ( v4 < 0 || (v4 = ((__int64 (__fastcall *)(struct IXmlWriter *))a2->lpVtbl->WriteEndElement)(a2), v4 < 0) )
          {
LABEL_78:
            if ( bstrString )
              SysFreeString(bstrString);
LABEL_80:
            if ( v11 )
              (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v11 + 16LL))(v11);
            break;
          }
          v22 = 0;
          v23 = *(_QWORD *)(v15 + 16);
          if ( !v23 )
          {
            v24 = *(_QWORD *)(v15 + 8);
            if ( !v24 )
              goto LABEL_44;
            while ( 1 )
            {
              v23 = *(_QWORD *)(v24 + 96);
              if ( v23 )
                break;
              v24 = *(_QWORD *)(v24 + 136);
              if ( !v24 )
                goto LABEL_44;
            }
          }
          v29 = 0;
          while ( *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v29) )
          {
            v29 = (unsigned int)(v29 + 1);
            if ( (unsigned int)v29 >= 0x10 )
            {
              LODWORD(v29) = -1;
              break;
            }
          }
          v30 = *(_DWORD *)(v23 + 128);
          if ( _bittest(&v30, v29) )
            v25 = *(_QWORD *)(v23 + 8LL * (unsigned int)v29);
          else
            LODWORD(v25) = 1;
          if ( (_DWORD)v25 != 7 )
          {
            if ( (unsigned int)v25 > 0xD )
              goto LABEL_49;
            goto LABEL_45;
          }
LABEL_44:
          LODWORD(v25) = 1;
LABEL_45:
          v26 = (&c_rgszCfgNodeDataType)[(int)v25];
          if ( v26 )
          {
            if ( (_DWORD)v25 != 1 )
            {
              v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, wchar_t *, _QWORD))a2->lpVtbl->WriteStartElement)(
                     a2,
                     0,
                     v36,
                     0);
              if ( v4 < 0 )
                goto LABEL_78;
              v22 = 1;
              v4 = AddSubnode(a2, v37, off_18003E390[0], 2, v26);
              if ( v4 < 0 )
                goto LABEL_78;
            }
          }
LABEL_49:
          Type = CSyncMLItem::GetType((CSyncMLItem *)v15);
          v28 = Type;
          if ( Type && InvStrCmpIW(L"text/plain", Type) )
          {
            if ( !v22 )
            {
              v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, wchar_t *, _QWORD))a2->lpVtbl->WriteStartElement)(
                     a2,
                     0,
                     v36,
                     0);
              if ( v4 < 0 )
                goto LABEL_78;
              v22 = 1;
            }
            v4 = AddSubnode(a2, v37, off_18003E3F8[0], 2, v28);
            if ( v4 < 0 )
              goto LABEL_78;
          }
          if ( v22 )
          {
            v4 = ((__int64 (__fastcall *)(struct IXmlWriter *))a2->lpVtbl->WriteEndElement)(a2);
            if ( v4 < 0 )
              goto LABEL_78;
          }
          if ( *(_QWORD *)(v15 + 80) )
          {
            v4 = AddSubnode(a2, 0, off_18003E2D8[0], 2, *(_QWORD *)(v15 + 80));
            if ( v4 < 0 )
              goto LABEL_78;
          }
          v4 = ((__int64 (__fastcall *)(struct IXmlWriter *))a2->lpVtbl->WriteEndElement)(a2);
          if ( v4 < 0 )
            goto LABEL_78;
          if ( v11 )
          {
            (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v11 + 16LL))(v11);
            v11 = 0;
          }
          if ( bstrString )
            SysFreeString(bstrString);
          v14 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v14 >= (unsigned int)v41 )
          {
            if ( v35 )
              v4 = ((__int64 (__fastcall *)(struct IXmlWriter *))a2->lpVtbl->WriteEndElement)(a2);
            goto LABEL_80;
          }
          v13 = v35;
          v3 = v42;
          v12 = *(wchar_t **)&EventDescriptor.Id;
        }
      }
    }
  }
LABEL_83:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v35 = v4;
    v47 = &v35;
    v48 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v44 = &dword_1800365D4;
    v45 = 31;
    v46 = 1;
    LODWORD(bstrString) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000bf60  mov     [rsp-8+arg_10], rbx
0x18000bf65  push    rbp
0x18000bf66  push    rsi
0x18000bf67  push    rdi
0x18000bf68  push    r12
0x18000bf6a  push    r13
0x18000bf6c  push    r14
0x18000bf6e  push    r15
0x18000bf70  lea     rbp, [rsp-27h]
0x18000bf75  sub     rsp, 0C0h
0x18000bf7c  mov     rax, cs:__security_cookie
0x18000bf83  xor     rax, rsp
0x18000bf86  mov     [rbp+57h+var_40], rax
0x18000bf8a  mov     rsi, rdx
0x18000bf8d  mov     r14, rcx
0x18000bf90  mov     [rbp+57h+var_78], rcx
0x18000bf94  test    rdx, rdx
0x18000bf97  jnz     short loc_18000BFA3
0x18000bf99  mov     ebx, 80070057h
0x18000bf9e  jmp     loc_18000C51C
0x18000bfa3  mov     rax, cs:off_18003E2E0; "Item"
0x18000bfaa  mov     [rbp+57h+var_90], rax
0x18000bfae  test    rax, rax
0x18000bfb1  jz      loc_18000C513
0x18000bfb7  mov     ecx, 7FFFFFFFh
0x18000bfbc  mov     edx, ecx
0x18000bfbe  xchg    ax, ax
0x18000bfc0  cmp     word ptr [rax], 0
0x18000bfc4  jz      short loc_18000BFD0
0x18000bfc6  add     rax, 2
0x18000bfca  sub     rdx, 1
0x18000bfce  jnz     short loc_18000BFC0
0x18000bfd0  mov     ebx, 80070057h
0x18000bfd5  mov     r8d, ebx
0x18000bfd8  xor     eax, eax
0x18000bfda  test    rdx, rdx
0x18000bfdd  cmovnz  r8d, eax
0x18000bfe1  jz      loc_18000C519
0x18000bfe7  mov     rax, cs:off_18003E2A8; "Source"
0x18000bfee  mov     [rbp+57h+var_88], rax
0x18000bff2  test    rax, rax
0x18000bff5  jz      loc_18000C50E
0x18000bffb  mov     rdx, rcx
0x18000bffe  xchg    ax, ax
0x18000c000  cmp     word ptr [rax], 0
0x18000c004  jz      short loc_18000C010
0x18000c006  add     rax, 2
0x18000c00a  sub     rdx, 1
0x18000c00e  jnz     short loc_18000C000
0x18000c010  mov     r8d, ebx
0x18000c013  xor     eax, eax
0x18000c015  test    rdx, rdx
0x18000c018  cmovnz  r8d, eax
0x18000c01c  jz      loc_18000C519
0x18000c022  mov     rax, cs:off_18003E2E8; "Meta"
0x18000c029  mov     [rbp+57h+var_B0], rax
0x18000c02d  test    rax, rax
0x18000c030  jz      loc_18000C51C
0x18000c036  cmp     word ptr [rax], 0
0x18000c03a  jz      short loc_18000C046
0x18000c03c  add     rax, 2
0x18000c040  sub     rcx, 1
0x18000c044  jnz     short loc_18000C036
0x18000c046  xor     eax, eax
0x18000c048  test    rcx, rcx
0x18000c04b  cmovnz  ebx, eax
0x18000c04e  jz      loc_18000C51C
0x18000c054  xor     r12d, r12d
0x18000c057  mov     rdx, cs:off_18003E358; "Results"
0x18000c05e  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdx
0x18000c062  mov     rax, cs:off_18003E470; "syncml:metinf"
0x18000c069  mov     [rbp+57h+var_A8], rax
0x18000c06d  mov     rax, [r14+0B0h]
0x18000c074  sub     rax, [r14+0A8h]
0x18000c07b  sar     rax, 3
0x18000c07f  mov     [rbp+57h+var_80], rax
0x18000c083  xor     edi, edi
0x18000c085  mov     [rbp+57h+var_B8], edi
0x18000c088  xor     r13d, r13d
0x18000c08b  test    eax, eax
0x18000c08d  jz      loc_18000C51C
0x18000c093  nop     dword ptr [rax+00h]
0x18000c097  nop     word ptr [rax+rax+00000000h]
0x18000c0a0  mov     [rbp+57h+bstrString], 0
0x18000c0a8  mov     rax, [r14+0A8h]
0x18000c0af  mov     r15, [rax+r13*8]
0x18000c0b3  test    edi, edi
0x18000c0b5  jnz     loc_18000C16F
0x18000c0bb  mov     rax, [rsi]
0x18000c0be  xor     r9d, r9d
0x18000c0c1  mov     r8, rdx
0x18000c0c4  xor     edx, edx
0x18000c0c6  mov     rcx, rsi
0x18000c0c9  mov     rax, [rax+0D8h]
0x18000c0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0d5  mov     ebx, eax
0x18000c0d7  test    eax, eax
0x18000c0d9  js      loc_18000C4E2
0x18000c0df  mov     ecx, cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x18000c0e5  lea     eax, [rcx+1]
0x18000c0e8  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, eax; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x18000c0ee  mov     [rsp+0F0h+UserDataCount], ecx
0x18000c0f2  mov     r9d, 1
0x18000c0f8  mov     r8, cs:off_18003E258; "CmdID"
0x18000c0ff  xor     edx, edx
0x18000c101  mov     rcx, rsi
0x18000c104  call    AddSubnode
0x18000c109  mov     ebx, eax
0x18000c10b  test    eax, eax
0x18000c10d  js      loc_18000C4E2
0x18000c113  mov     eax, cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA; ulong CSyncMLDPU::s_dwCurrServerMsgID
0x18000c119  mov     [rsp+0F0h+UserDataCount], eax
0x18000c11d  mov     r9d, 1
0x18000c123  mov     r8, cs:off_18003E290; "MsgRef"
0x18000c12a  xor     edx, edx
0x18000c12c  mov     rcx, rsi
0x18000c12f  call    AddSubnode
0x18000c134  mov     ebx, eax
0x18000c136  test    eax, eax
0x18000c138  js      loc_18000C4E2
0x18000c13e  mov     rax, [r14+68h]
0x18000c142  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x18000c147  mov     r9d, 2
0x18000c14d  mov     r8, cs:off_18003E260; "CmdRef"
0x18000c154  xor     edx, edx
0x18000c156  mov     rcx, rsi
0x18000c159  call    AddSubnode
0x18000c15e  mov     ebx, eax
0x18000c160  test    eax, eax
0x18000c162  js      loc_18000C4E2
0x18000c168  mov     [rbp+57h+var_B8], 1
0x18000c16f  mov     rax, [rsi]
0x18000c172  xor     r9d, r9d
0x18000c175  mov     r8, [rbp+57h+var_90]
0x18000c179  xor     edx, edx
0x18000c17b  mov     rcx, rsi
0x18000c17e  mov     rax, [rax+0D8h]
0x18000c185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c18a  mov     ebx, eax
0x18000c18c  test    eax, eax
0x18000c18e  js      loc_18000C4E2
0x18000c194  mov     rax, [rsi]
0x18000c197  xor     r9d, r9d
0x18000c19a  mov     r8, [rbp+57h+var_88]
0x18000c19e  xor     edx, edx
0x18000c1a0  mov     rcx, rsi
0x18000c1a3  mov     rax, [rax+0D8h]
0x18000c1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1af  mov     ebx, eax
0x18000c1b1  test    eax, eax
0x18000c1b3  js      loc_18000C4E2
0x18000c1b9  mov     rcx, [r15+48h]
0x18000c1bd  test    rcx, rcx
0x18000c1c0  jz      short loc_18000C1CE
0x18000c1c2  mov     rax, [rcx]
0x18000c1c5  mov     rax, [rax+8]
0x18000c1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ce  mov     r12, [r15+48h]
0x18000c1d2  mov     rax, [r14+48h]
0x18000c1d6  test    rax, rax
0x18000c1d9  jz      short loc_18000C231
0x18000c1db  mov     rcx, [rax+18h]
0x18000c1df  test    rcx, rcx
0x18000c1e2  jz      short loc_18000C1FB
0x18000c1e4  lea     rdx, a10; "1.0"
0x18000c1eb  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18000c1f2  nop     dword ptr [rax+rax+00h]
0x18000c1f7  test    eax, eax
0x18000c1f9  jnz     short loc_18000C231
0x18000c1fb  mov     rcx, r12; struct IConfigManager2URI *
0x18000c1fe  call    ?IsWmiQuery@CSyncMLCmd@@KAHPEAUIConfigManager2URI@@@Z; CSyncMLCmd::IsWmiQuery(IConfigManager2URI *)
0x18000c203  cmp     eax, 1
0x18000c206  jnz     short loc_18000C231
0x18000c208  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000c20c  test    rcx, rcx
0x18000c20f  jz      short loc_18000C225
0x18000c211  call    cs:__imp_SysFreeString
0x18000c218  nop     dword ptr [rax+rax+00h]
0x18000c21d  mov     [rbp+57h+bstrString], 0
0x18000c225  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000c229  mov     rdx, r12; struct IConfigManager2URI *
0x18000c22c  call    ?GetOriginalQueryPath@CSyncMLCmd@@IEBAJPEAUIConfigManager2URI@@PEAPEAG@Z; CSyncMLCmd::GetOriginalQueryPath(IConfigManager2URI *,ushort * *)
0x18000c231  mov     rax, [rbp+57h+bstrString]
0x18000c235  test    rax, rax
0x18000c238  jnz     short loc_18000C262
0x18000c23a  mov     rax, [r12]
0x18000c23e  lea     r9, [rbp+57h+bstrString]
0x18000c242  mov     r8d, [r15+6Ch]
0x18000c246  xor     edx, edx
0x18000c248  mov     rcx, r12
0x18000c24b  mov     rax, [rax+40h]
0x18000c24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c254  mov     ebx, eax
0x18000c256  test    eax, eax
0x18000c258  js      loc_18000C4E2
0x18000c25e  mov     rax, [rbp+57h+bstrString]
0x18000c262  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x18000c267  mov     r9d, 2
0x18000c26d  mov     r8, cs:off_18003E280; "LocURI"
0x18000c274  xor     edx, edx
0x18000c276  mov     rcx, rsi
0x18000c279  call    AddSubnode
0x18000c27e  mov     ebx, eax
0x18000c280  test    eax, eax
0x18000c282  js      loc_18000C4E2
0x18000c288  mov     rax, [rsi]
0x18000c28b  mov     rcx, rsi
0x18000c28e  mov     rax, [rax+78h]
0x18000c292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c297  mov     ebx, eax
0x18000c299  test    eax, eax
0x18000c29b  js      loc_18000C4E2
0x18000c2a1  xor     r14d, r14d
0x18000c2a4  mov     rdx, [r15+10h]
0x18000c2a8  test    rdx, rdx
0x18000c2ab  jnz     loc_18000C47B
0x18000c2b1  mov     rax, [r15+8]
0x18000c2b5  test    rax, rax
0x18000c2b8  jz      short loc_18000C2D9
0x18000c2ba  nop     word ptr [rax+rax+00h]
0x18000c2c0  mov     rdx, [rax+60h]
0x18000c2c4  test    rdx, rdx
0x18000c2c7  jnz     loc_18000C47B
0x18000c2cd  mov     rax, [rax+88h]
0x18000c2d4  test    rax, rax
0x18000c2d7  jnz     short loc_18000C2C0
0x18000c2d9  mov     ecx, 1
0x18000c2de  movsxd  rax, ecx
0x18000c2e1  lea     rdx, __ImageBase
0x18000c2e8  mov     rdi, rva ?c_rgszCfgNodeDataType@@3PAPEBGA[rdx+rax*8]; ushort const * near * c_rgszCfgNodeDataType ...
0x18000c2f0  test    rdi, rdi
0x18000c2f3  jz      short loc_18000C34D
0x18000c2f5  cmp     ecx, 1
0x18000c2f8  jz      short loc_18000C34D
0x18000c2fa  mov     rax, [rsi]
0x18000c2fd  xor     r9d, r9d
0x18000c300  mov     r8, [rbp+57h+var_B0]
0x18000c304  xor     edx, edx
0x18000c306  mov     rcx, rsi
0x18000c309  mov     rax, [rax+0D8h]
0x18000c310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c315  mov     ebx, eax
0x18000c317  test    eax, eax
0x18000c319  js      loc_18000C4E2
0x18000c31f  mov     r14d, 1
0x18000c325  mov     qword ptr [rsp+0F0h+UserDataCount], rdi
0x18000c32a  mov     r9d, 2
0x18000c330  mov     r8, cs:off_18003E390; "Format"
0x18000c337  mov     rdx, [rbp+57h+var_A8]
0x18000c33b  mov     rcx, rsi
0x18000c33e  call    AddSubnode
0x18000c343  mov     ebx, eax
0x18000c345  test    eax, eax
0x18000c347  js      loc_18000C4E2
0x18000c34d  mov     rcx, r15; this
0x18000c350  call    ?GetType@CSyncMLItem@@QEBAPEBGXZ; CSyncMLItem::GetType(void)
0x18000c355  mov     rdi, rax
0x18000c358  test    rax, rax
0x18000c35b  jz      short loc_18000C3CF
0x18000c35d  mov     rdx, rax
0x18000c360  lea     rcx, ?gc_szDefaultType@@3QBGB; "text/plain"
0x18000c367  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18000c36e  nop     dword ptr [rax+rax+00h]
0x18000c373  test    eax, eax
0x18000c375  jz      short loc_18000C3CF
0x18000c377  test    r14d, r14d
0x18000c37a  jnz     short loc_18000C3A7
0x18000c37c  mov     rcx, [rsi]
0x18000c37f  mov     rax, [rcx+0D8h]
0x18000c386  xor     r9d, r9d
0x18000c389  mov     r8, [rbp+57h+var_B0]
0x18000c38d  xor     edx, edx
0x18000c38f  mov     rcx, rsi
0x18000c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c397  mov     ebx, eax
0x18000c399  test    eax, eax
0x18000c39b  js      loc_18000C4E2
0x18000c3a1  mov     r14d, 1
0x18000c3a7  mov     qword ptr [rsp+0F0h+UserDataCount], rdi
0x18000c3ac  mov     r9d, 2
0x18000c3b2  mov     r8, cs:off_18003E3F8; "Type"
0x18000c3b9  mov     rdx, [rbp+57h+var_A8]
0x18000c3bd  mov     rcx, rsi
0x18000c3c0  call    AddSubnode
0x18000c3c5  mov     ebx, eax
0x18000c3c7  test    eax, eax
0x18000c3c9  js      loc_18000C4E2
0x18000c3cf  test    r14d, r14d
0x18000c3d2  jz      short loc_18000C3ED
0x18000c3d4  mov     rax, [rsi]
0x18000c3d7  mov     rcx, rsi
0x18000c3da  mov     rax, [rax+78h]
0x18000c3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e3  mov     ebx, eax
0x18000c3e5  test    eax, eax
0x18000c3e7  js      loc_18000C4E2
0x18000c3ed  mov     rax, [r15+50h]
0x18000c3f1  test    rax, rax
0x18000c3f4  jz      short loc_18000C41C
0x18000c3f6  mov     qword ptr [rsp+0F0h+UserDataCount], rax
  ... truncated ...
```
