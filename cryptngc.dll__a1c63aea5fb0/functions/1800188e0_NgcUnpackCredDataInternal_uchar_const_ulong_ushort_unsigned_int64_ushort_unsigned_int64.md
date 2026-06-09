# NgcUnpackCredDataInternal(uchar const *,ulong,ushort * *,unsigned __int64 *,ushort * *,unsigned __int64 *)

- ea: `0x1800188e0`
- end: `0x1800198be`
- name: `?NgcUnpackCredDataInternal@@YAJPEBEKPEAPEAGPEA_K12@Z`
- size: `4062`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned __int64 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001887c`
- `0x1800341d0`

## callees

- `0x180004720`
- `0x18000edb0`
- `0x18000f280`
- `0x1800158e0`
- `0x18001750c`
- `0x1800188e0`
- `0x18001aa4c`
- `0x18002a314`
- `0x18002b31c`
- `0x18002c898`
- `0x18002cb1c`
- `0x18002dff0`
- `0x18002e02c`
- `0x18002e7a6`
- `0x18002e850`
- `0x18002f7db`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018e11`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018e11`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001954a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800196c0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001979c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019879`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001954a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800196c0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001979c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019434`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001944c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019434`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001944c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018dda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018dda`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcUnpackCredDataInternal(
        const unsigned __int8 *a1,
        __int64 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        unsigned __int16 **a5,
        unsigned __int64 *a6)
{
  const unsigned __int8 *v6; // rdi
  char *v7; // rax
  const unsigned __int8 *v8; // r13
  const unsigned __int8 *v9; // r8
  __int64 v10; // r10
  unsigned int v11; // r9d
  const unsigned __int8 *v12; // r15
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  const unsigned __int8 *v15; // rax
  int v16; // ebx
  unsigned __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  char *v20; // rax
  size_t v21; // rbx
  size_t v22; // r12
  char *v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // r8d
  const char *v26; // r9
  char *v27; // r14
  __int16 v28; // ax
  char *v29; // rax
  __int64 v30; // rax
  const unsigned __int8 *v31; // r15
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // rbx
  __int64 v34; // r12
  size_t v35; // rcx
  _QWORD *v36; // r13
  void *v37; // rax
  size_t v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // r15
  __int16 v41; // ax
  char *v42; // rax
  __int64 v43; // rax
  const unsigned __int8 *v44; // r9
  __int64 v45; // rdx
  unsigned int v46; // r8d
  const char *v47; // r9
  __int16 v48; // ax
  __int16 *v49; // rdx
  const unsigned __int8 *v50; // rbx
  __int64 v51; // rdx
  __int64 v52; // rcx
  const unsigned __int8 *v53; // rdi
  __int64 v54; // rdx
  __int64 v55; // rcx
  unsigned __int64 v56; // rax
  __int64 v57; // rcx
  unsigned __int16 *v58; // rax
  unsigned __int64 v60; // rdx
  void *v61; // rcx
  unsigned int v62; // [rsp+30h] [rbp-118h] BYREF
  unsigned int v63; // [rsp+38h] [rbp-110h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-108h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-F8h] BYREF
  const unsigned __int8 *v66; // [rsp+58h] [rbp-F0h] BYREF
  char *v67; // [rsp+60h] [rbp-E8h]
  unsigned __int16 **v68; // [rsp+68h] [rbp-E0h]
  unsigned __int64 *v69; // [rsp+70h] [rbp-D8h]
  unsigned __int16 **v70; // [rsp+78h] [rbp-D0h]
  unsigned __int64 *v71; // [rsp+80h] [rbp-C8h]
  char *v72; // [rsp+88h] [rbp-C0h]
  wchar_t String[8]; // [rsp+90h] [rbp-B8h] BYREF
  unsigned __int64 v74; // [rsp+A0h] [rbp-A8h]
  unsigned __int64 v75; // [rsp+A8h] [rbp-A0h]
  wchar_t v76[8]; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v77; // [rsp+C0h] [rbp-88h]
  __int64 v78; // [rsp+C8h] [rbp-80h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-78h] BYREF
  char *v80; // [rsp+E0h] [rbp-68h]
  int v81; // [rsp+E8h] [rbp-60h]
  int v82; // [rsp+ECh] [rbp-5Ch]
  unsigned int *v83; // [rsp+F0h] [rbp-58h]
  __int64 v84; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v69 = a4;
  v68 = a3;
  v6 = a1;
  v70 = a5;
  v71 = a6;
  v63 = 0;
  if ( (unsigned int)a2 < 0x2C )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = byte_18005F271;
      v81 = 44;
LABEL_130:
      v80 = v7;
      UserData.Reserved = 2;
      v82 = 1;
      v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      return 2147942487LL;
    }
    return 2147942487LL;
  }
  if ( (unsigned int)a2 > 0xFFFF )
    goto LABEL_131;
  v8 = &a1[(unsigned __int16)a2];
  v66 = v8;
  if ( v8 < a1 )
    goto LABEL_131;
  a2 = *((unsigned __int16 *)a1 + 8);
  if ( (unsigned int)a2 < 0x28 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = byte_18005F23D;
      v81 = 40;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  a1 += *((unsigned int *)a1 + 3);
  if ( a1 < v6 )
    goto LABEL_131;
  v9 = &a1[a2];
  if ( &a1[a2] < a1 )
    goto LABEL_131;
  if ( v8 < v9 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = &byte_18005F1FF;
      v81 = 50;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  if ( (_DWORD)a2 != *(_DWORD *)a1 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = (char *)&unk_18005F1C0;
      v81 = 51;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  a2 = (unsigned int)(a2 - 40);
  v10 = *((unsigned int *)a1 + 8);
  v11 = 2 * v10;
  if ( !is_mul_ok(2u, v10) )
LABEL_131:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(a1, a2);
  if ( (unsigned int)a2 <= v11 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = byte_18005F175;
      v81 = 63;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  v12 = &a1[2 * v10 + 40];
  if ( !v12 )
  {
    v16 = -2147024809;
LABEL_125:
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = v16;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v80 = byte_18005F13B;
      v81 = 46;
      v82 = 1;
      v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    return (unsigned int)v16;
  }
  v13 = (unsigned __int64)((unsigned int)a2 - v11) >> 1;
  v14 = v13;
  v15 = v12;
  if ( v13 )
  {
    while ( *(_WORD *)v15 )
    {
      v15 += 2;
      if ( !--v14 )
        goto LABEL_23;
    }
    v16 = 0;
    v17 = v13 - v14;
  }
  else
  {
LABEL_23:
    v16 = -2147024809;
    v17 = 0;
  }
  v62 = v16;
  if ( v16 < 0 )
    goto LABEL_125;
  v18 = 2 * v17;
  if ( !v18 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = byte_18005F103;
      v81 = 44;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  if ( (v18 & 1) != 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = &byte_18005F0C7;
      v81 = 48;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  if ( v9 < &v12[v18 + 2] )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v7 = byte_18005F089;
      v81 = 50;
      goto LABEL_130;
    }
    return 2147942487LL;
  }
  v19 = 0x7FFFFFFF;
  v20 = (char *)v12;
  do
  {
    if ( !*(_WORD *)v20 )
      break;
    v20 += 2;
    --v19;
  }
  while ( v19 );
  v21 = 2 * ((v20 - (char *)v12) >> 1);
  v22 = v21 + 2;
  v23 = (char *)LocalAlloc(0, v21 + 2);
  v27 = v23;
  v67 = v23;
  if ( v23 )
  {
    if ( v21 )
    {
      if ( v22 < v21 )
      {
        memset_0(v23, 0, v22);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v23, v12, v21);
      }
    }
    *(_WORD *)&v27[v21] = 0;
  }
  v72 = v27;
  v63 = 2;
  if ( !v27 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v25, v26);
  v28 = *((_WORD *)v6 + 12);
  if ( !v28 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v29 = byte_18005F045;
      v81 = 56;
LABEL_123:
      v80 = v29;
      UserData.Reserved = 2;
      v82 = 1;
      v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      goto LABEL_106;
    }
    goto LABEL_106;
  }
  if ( (v28 & 1) != 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v29 = byte_18005EFFD;
      v81 = 60;
      goto LABEL_123;
    }
    goto LABEL_106;
  }
  v30 = *((unsigned int *)v6 + 5);
  v31 = &v6[v30];
  if ( &v6[v30] < v6 || (v24 = *((unsigned __int16 *)v6 + 12), &v31[v24] < v31) )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(retaddr, v24);
  if ( v8 < &v31[*((unsigned __int16 *)v6 + 12)] )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v29 = byte_18005EFB3;
      v81 = 62;
      goto LABEL_123;
    }
LABEL_106:
    LocalFree(v27);
    return 2147942487LL;
  }
  v32 = (unsigned __int64)*((unsigned __int16 *)v6 + 12) >> 1;
  *(_OWORD *)String = 0;
  v74 = 0;
  v75 = 0;
  if ( v32 <= 7 )
  {
    v74 = v32;
    v75 = 7;
    v33 = v32;
    memcpy_0(String, v31, v33 * 2);
    String[v33] = 0;
    goto LABEL_145;
  }
  v34 = v32 | 7;
  if ( (v32 | 7) < 0xA )
    v34 = 10;
  if ( (unsigned __int64)(v34 + 1) > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_137;
  v35 = 2 * (v34 + 1);
  if ( v35 )
  {
    if ( v35 < 0x1000 )
    {
      v36 = operator new(v35);
      goto LABEL_66;
    }
    if ( v35 + 39 >= v35 )
    {
      v37 = operator new(v35 + 39);
      if ( !v37 )
        goto LABEL_115;
      v36 = (_QWORD *)(((unsigned __int64)v37 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v36 - 1) = v37;
      goto LABEL_66;
    }
LABEL_137:
    std::_Throw_bad_array_new_length();
  }
  v36 = 0;
LABEL_66:
  *(_QWORD *)String = v36;
  v74 = v32;
  v75 = v34;
  v38 = 2 * v32;
  memcpy_0(v36, v31, v38);
  *(_WORD *)((char *)v36 + v38) = 0;
  v8 = v66;
LABEL_145:
  try
  {
    v40 = std::stoull(String);
  }
  catch ( std::exception )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)&dword_18005EF5C,
        0,
        0,
        (__int64)&v62);
    }
    if ( v75 > 7 )
      std::_Deallocate<16>(*(_QWORD *)String, 2 * v75 + 2);
    v27 = v67;
    goto LABEL_120;
  }
  v41 = *((_WORD *)v6 + 16);
  if ( !v41 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v42 = byte_18005EF2B;
      v81 = 48;
LABEL_110:
      v80 = v42;
      UserData.Reserved = 2;
      v82 = 1;
      v63 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      goto LABEL_111;
    }
    goto LABEL_111;
  }
  if ( (v41 & 1) != 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      v83 = &v62;
      v84 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v42 = byte_18005EEEB;
      v81 = 52;
      goto LABEL_110;
    }
LABEL_111:
    if ( v75 <= 7 )
    {
LABEL_120:
      v74 = 0;
      v75 = 7;
      String[0] = 0;
      goto LABEL_106;
    }
    v60 = 2 * v75 + 2;
    if ( v60 < 0x1000 )
    {
      operator delete(*(void **)String, v60);
      goto LABEL_120;
    }
    v61 = *(void **)(*(_QWORD *)String - 8LL);
    if ( (unsigned __int64)(*(_QWORD *)String - (_QWORD)v61 - 8LL) <= 0x1F )
    {
      operator delete(v61, 2 * v75 + 41);
      goto LABEL_120;
    }
LABEL_115:
    __fastfail(5u);
  }
  v43 = *((unsigned int *)v6 + 7);
  v44 = &v6[v43];
  if ( &v6[v43] < v6 || (v45 = *((unsigned __int16 *)v6 + 16), &v44[v45] < v44) )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v39, v45);
  if ( v8 < &v44[*((unsigned __int16 *)v6 + 16)] )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)&word_18005EE9E,
        0,
        0,
        (__int64)&v62);
    }
LABEL_105:
    std::wstring::~wstring(String);
    goto LABEL_106;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &hMem,
    v44,
    (unsigned __int64)*((unsigned __int16 *)v6 + 16) >> 1);
  v63 = 9;
  if ( !hMem )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v46, v47);
  v48 = *((_WORD *)v6 + 20);
  if ( !v48 )
  {
    if ( (unsigned int)dword_18006E000 <= 2 )
      goto LABEL_103;
    v49 = &word_18005EE56;
    goto LABEL_102;
  }
  v50 = (const unsigned __int8 *)*((unsigned __int16 *)v6 + 20);
  if ( (v48 & 1) != 0 )
  {
    if ( (unsigned int)dword_18006E000 <= 2 )
      goto LABEL_103;
    v49 = word_18005EE0A;
LABEL_102:
    v62 = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (_DWORD)v49,
      0,
      0,
      (__int64)&v62);
LABEL_103:
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_105;
  }
  v66 = (const unsigned __int8 *)*((unsigned int *)v6 + 9);
  v52 = *(_QWORD *)SafeInt<__int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(
                     &v66,
                     &v63);
  if ( v52 < 0 )
  {
    v52 = -v52;
    if ( v52 <= (unsigned __int64)v6 )
    {
      v53 = &v6[-v52];
      goto LABEL_86;
    }
LABEL_135:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v52, v51);
  }
  if ( &v6[v52] < v6 )
    goto LABEL_135;
  v53 = &v6[v52];
LABEL_86:
  v66 = v50;
  v55 = *(_QWORD *)SafeInt<__int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(
                     &v66,
                     &EventDescriptor);
  if ( v55 >= 0 )
  {
    v56 = (unsigned __int64)&v53[v55];
    if ( &v53[v55] >= v53 )
      goto LABEL_90;
LABEL_134:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v55, v54);
  }
  v55 = -v55;
  if ( v55 > (unsigned __int64)v53 )
    goto LABEL_134;
  v56 = (unsigned __int64)&v53[-v55];
LABEL_90:
  if ( (unsigned __int64)v8 < v56 )
  {
    if ( (unsigned int)dword_18006E000 <= 2 )
      goto LABEL_103;
    v49 = (__int16 *)&dword_18005EDBC;
    goto LABEL_102;
  }
  *(_OWORD *)v76 = 0;
  v77 = 0;
  v78 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v76, v53, (unsigned __int64)v50 >> 1);
  try
  {
    v57 = std::stoull(v76);
  }
  catch ( std::exception )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v62 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)&dword_18005ED6C,
        0,
        0,
        (__int64)&v62);
    }
    std::wstring::~wstring(v76);
    if ( hMem )
      LocalFree(hMem);
    v27 = v67;
    goto LABEL_105;
  }
  *v68 = (unsigned __int16 *)v27;
  *v69 = v40;
  v58 = (unsigned __int16 *)hMem;
  hMem = 0;
  *v70 = v58;
  *v71 = v57;
  std::wstring::~wstring(v76);
  if ( hMem )
    LocalFree(hMem);
  std::wstring::~wstring(String);
  return v62;
}

```

## disassembly

```asm
0x1800188e0  mov     r11, rsp
0x1800188e3  push    rbx
0x1800188e4  push    rsi
0x1800188e5  push    rdi
0x1800188e6  push    r12
0x1800188e8  push    r13
0x1800188ea  push    r14
0x1800188ec  push    r15
0x1800188ee  sub     rsp, 110h
0x1800188f5  mov     rax, cs:__security_cookie
0x1800188fc  xor     rax, rsp
0x1800188ff  mov     [rsp+148h+var_48], rax
0x180018907  mov     [rsp+148h+var_D8], r9
0x18001890c  mov     [rsp+148h+var_E0], r8
0x180018911  mov     rdi, rcx
0x180018914  mov     rax, [rsp+148h+arg_20]
0x18001891c  mov     [rsp+148h+var_D0], rax
0x180018921  mov     rax, [rsp+148h+arg_28]
0x180018929  mov     [rsp+148h+var_C8], rax
0x180018931  xor     esi, esi
0x180018933  mov     [rsp+148h+var_110], esi
0x180018937  cmp     edx, 2Ch ; ','
0x18001893a  jnb     short loc_1800189A2
0x18001893c  mov     eax, cs:dword_18006E000
0x180018942  cmp     eax, 2
0x180018945  jbe     loc_180019452
0x18001894b  mov     [rsp+148h+var_118], 80070057h
0x180018953  lea     rax, [rsp+148h+var_118]
0x180018958  mov     [r11-58h], rax
0x18001895c  mov     qword ptr [r11-50h], 4
0x180018964  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x18001896c  movzx   eax, cs:word_18005F267
0x180018973  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018977  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x18001897c  mov     rax, cs:off_18006E008
0x180018983  mov     [r11-78h], rax
0x180018987  movzx   eax, word ptr [rax]
0x18001898a  mov     [r11-70h], eax
0x18001898e  lea     rax, byte_18005F271
0x180018995  mov     dword ptr [r11-60h], 2Ch ; ','
0x18001899d  jmp     loc_18001981C
0x1800189a2  cmp     edx, 0FFFFh
0x1800189a8  ja      loc_180019884
0x1800189ae  movzx   eax, dx
0x1800189b1  test    rax, rax
0x1800189b4  jns     short loc_1800189CF
0x1800189b6  neg     rax
0x1800189b9  cmp     rax, rdi
0x1800189bc  ja      loc_180019884
0x1800189c2  mov     r13, rdi
0x1800189c5  sub     r13, rax
0x1800189c8  mov     [rsp+148h+var_F0], r13
0x1800189cd  jmp     short loc_1800189E1
0x1800189cf  lea     r13, [rcx+rax]
0x1800189d3  mov     [rsp+148h+var_F0], r13
0x1800189d8  cmp     r13, rdi
0x1800189db  jb      loc_180019884
0x1800189e1  movzx   edx, word ptr [rcx+10h]
0x1800189e5  cmp     edx, 28h ; '('
0x1800189e8  jnb     short loc_180018A62
0x1800189ea  mov     eax, cs:dword_18006E000
0x1800189f0  cmp     eax, 2
0x1800189f3  jbe     loc_180019452
0x1800189f9  mov     [rsp+148h+var_118], 80070057h
0x180018a01  lea     rax, [rsp+148h+var_118]
0x180018a06  mov     [rsp+148h+var_58], rax
0x180018a0e  mov     [rsp+148h+var_50], 4
0x180018a1a  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018a22  movzx   eax, cs:word_18005F233
0x180018a29  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018a2d  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018a32  mov     rax, cs:off_18006E008
0x180018a39  mov     [rsp+148h+var_78.Ptr], rax
0x180018a41  movzx   eax, word ptr [rax]
0x180018a44  mov     [rsp+148h+var_78.Size], eax
0x180018a4b  lea     rax, byte_18005F23D
0x180018a52  mov     [rsp+148h+var_60], 28h ; '('
0x180018a5d  jmp     loc_18001981C
0x180018a62  mov     eax, [rcx+0Ch]
0x180018a65  test    rax, rax
0x180018a68  jns     short loc_180018A7B
0x180018a6a  neg     rax
0x180018a6d  cmp     rax, rdi
0x180018a70  ja      loc_180019884
0x180018a76  sub     rcx, rax
0x180018a79  jmp     short loc_180018A87
0x180018a7b  add     rcx, rax
0x180018a7e  cmp     rcx, rdi
0x180018a81  jb      loc_180019884
0x180018a87  mov     rax, rdx
0x180018a8a  test    rdx, rdx
0x180018a8d  jns     short loc_180018AA3
0x180018a8f  neg     rax
0x180018a92  cmp     rax, rcx
0x180018a95  ja      loc_180019884
0x180018a9b  mov     r8, rcx
0x180018a9e  sub     r8, rax
0x180018aa1  jmp     short loc_180018AB0
0x180018aa3  lea     r8, [rcx+rdx]
0x180018aa7  cmp     r8, rcx
0x180018aaa  jb      loc_180019884
0x180018ab0  cmp     r13, r8
0x180018ab3  jnb     short loc_180018B2D
0x180018ab5  mov     eax, cs:dword_18006E000
0x180018abb  cmp     eax, 2
0x180018abe  jbe     loc_180019452
0x180018ac4  mov     [rsp+148h+var_118], 80070057h
0x180018acc  lea     rax, [rsp+148h+var_118]
0x180018ad1  mov     [rsp+148h+var_58], rax
0x180018ad9  mov     [rsp+148h+var_50], 4
0x180018ae5  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018aed  movzx   eax, cs:word_18005F1F5
0x180018af4  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018af8  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018afd  mov     rax, cs:off_18006E008
0x180018b04  mov     [rsp+148h+var_78.Ptr], rax
0x180018b0c  movzx   eax, word ptr [rax]
0x180018b0f  mov     [rsp+148h+var_78.Size], eax
0x180018b16  lea     rax, byte_18005F1FF
0x180018b1d  mov     [rsp+148h+var_60], 32h ; '2'
0x180018b28  jmp     loc_18001981C
0x180018b2d  cmp     edx, [rcx]
0x180018b2f  jnz     loc_1800197A9
0x180018b35  cmp     edx, 28h ; '('
0x180018b38  jb      loc_180019884
0x180018b3e  add     edx, 0FFFFFFD8h
0x180018b41  mov     r10d, [rcx+20h]
0x180018b45  lea     r9, [r10+r10]
0x180018b49  mov     rax, r9
0x180018b4c  shr     rax, 20h
0x180018b50  test    eax, eax
0x180018b52  jnz     loc_180019884
0x180018b58  cmp     edx, r9d
0x180018b5b  ja      short loc_180018BD5
0x180018b5d  mov     eax, cs:dword_18006E000
0x180018b63  cmp     eax, 2
0x180018b66  jbe     loc_180019452
0x180018b6c  mov     [rsp+148h+var_118], 80070057h
0x180018b74  lea     rax, [rsp+148h+var_118]
0x180018b79  mov     [rsp+148h+var_58], rax
0x180018b81  mov     [rsp+148h+var_50], 4
0x180018b8d  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018b95  movzx   eax, cs:word_18005F16B
0x180018b9c  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018ba0  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018ba5  mov     rax, cs:off_18006E008
0x180018bac  mov     [rsp+148h+var_78.Ptr], rax
0x180018bb4  movzx   eax, word ptr [rax]
0x180018bb7  mov     [rsp+148h+var_78.Size], eax
0x180018bbe  lea     rax, byte_18005F175
0x180018bc5  mov     [rsp+148h+var_60], 3Fh ; '?'
0x180018bd0  jmp     loc_18001981C
0x180018bd5  lea     r15, [r10+14h]
0x180018bd9  lea     r15, [rcx+r15*2]
0x180018bdd  test    r15, r15
0x180018be0  jz      loc_1800196CB
0x180018be6  sub     edx, r9d
0x180018be9  shr     rdx, 1
0x180018bec  mov     rcx, rdx
0x180018bef  mov     rax, r15
0x180018bf2  jz      short loc_180018C07
0x180018bf4  cmp     [rax], si
0x180018bf7  jz      loc_180018C9C
0x180018bfd  add     rax, 2
0x180018c01  sub     rcx, 1
0x180018c05  jnz     short loc_180018BF4
0x180018c07  mov     ebx, 80070057h
0x180018c0c  mov     rdx, rsi
0x180018c0f  mov     [rsp+148h+var_118], ebx
0x180018c13  test    ebx, ebx
0x180018c15  js      loc_1800196D0
0x180018c1b  add     rdx, rdx
0x180018c1e  jnz     loc_180018CA6
0x180018c24  mov     eax, cs:dword_18006E000
0x180018c2a  cmp     eax, 2
0x180018c2d  jbe     loc_180019452
0x180018c33  mov     [rsp+148h+var_118], 80070057h
0x180018c3b  lea     rax, [rsp+148h+var_118]
0x180018c40  mov     [rsp+148h+var_58], rax
0x180018c48  mov     [rsp+148h+var_50], 4
0x180018c54  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018c5c  movzx   eax, cs:word_18005F0F9
0x180018c63  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018c67  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018c6c  mov     rax, cs:off_18006E008
0x180018c73  mov     [rsp+148h+var_78.Ptr], rax
0x180018c7b  movzx   eax, word ptr [rax]
0x180018c7e  mov     [rsp+148h+var_78.Size], eax
0x180018c85  lea     rax, byte_18005F103
0x180018c8c  mov     [rsp+148h+var_60], 2Ch ; ','
0x180018c97  jmp     loc_18001981C
0x180018c9c  mov     ebx, esi
0x180018c9e  sub     rdx, rcx
0x180018ca1  jmp     loc_180018C0F
0x180018ca6  test    dl, 1
0x180018ca9  jz      short loc_180018D23
0x180018cab  mov     eax, cs:dword_18006E000
0x180018cb1  cmp     eax, 2
0x180018cb4  jbe     loc_180019452
0x180018cba  mov     [rsp+148h+var_118], 80070057h
0x180018cc2  lea     rax, [rsp+148h+var_118]
0x180018cc7  mov     [rsp+148h+var_58], rax
0x180018ccf  mov     [rsp+148h+var_50], 4
0x180018cdb  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018ce3  movzx   eax, cs:word_18005F0BD
0x180018cea  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018cee  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018cf3  mov     rax, cs:off_18006E008
0x180018cfa  mov     [rsp+148h+var_78.Ptr], rax
0x180018d02  movzx   eax, word ptr [rax]
0x180018d05  mov     [rsp+148h+var_78.Size], eax
0x180018d0c  lea     rax, byte_18005F0C7
0x180018d13  mov     [rsp+148h+var_60], 30h ; '0'
0x180018d1e  jmp     loc_18001981C
0x180018d23  lea     rax, [r15+2]
0x180018d27  add     rax, rdx
0x180018d2a  cmp     r8, rax
0x180018d2d  jnb     short loc_180018DA7
0x180018d2f  mov     eax, cs:dword_18006E000
0x180018d35  cmp     eax, 2
0x180018d38  jbe     loc_180019452
0x180018d3e  mov     [rsp+148h+var_118], 80070057h
0x180018d46  lea     rax, [rsp+148h+var_118]
0x180018d4b  mov     [rsp+148h+var_58], rax
0x180018d53  mov     [rsp+148h+var_50], 4
0x180018d5f  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018d67  movzx   eax, cs:word_18005F07F
0x180018d6e  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018d72  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018d77  mov     rax, cs:off_18006E008
0x180018d7e  mov     [rsp+148h+var_78.Ptr], rax
0x180018d86  movzx   eax, word ptr [rax]
0x180018d89  mov     [rsp+148h+var_78.Size], eax
0x180018d90  lea     rax, byte_18005F089
0x180018d97  mov     [rsp+148h+var_60], 32h ; '2'
0x180018da2  jmp     loc_18001981C
0x180018da7  mov     rax, [rsp+148h]
0x180018daf  mov     ecx, 7FFFFFFFh
0x180018db4  mov     rax, r15
0x180018db7  cmp     word ptr [rax], 0
0x180018dbb  jz      short loc_180018DC7
0x180018dbd  add     rax, 2
0x180018dc1  sub     rcx, 1
0x180018dc5  jnz     short loc_180018DB7
0x180018dc7  sub     rax, r15
0x180018dca  sar     rax, 1
0x180018dcd  lea     rbx, [rax+rax]
0x180018dd1  lea     r12, [rbx+2]
0x180018dd5  mov     rdx, r12; uBytes
0x180018dd8  xor     ecx, ecx; uFlags
0x180018dda  call    cs:__imp_LocalAlloc
0x180018de0  mov     r14, rax
0x180018de3  mov     [rsp+148h+var_E8], rax
0x180018de8  test    rax, rax
0x180018deb  jz      short loc_180018E27
0x180018ded  test    rbx, rbx
0x180018df0  jz      short loc_180018E22
0x180018df2  mov     rcx, rax; void *
0x180018df5  cmp     r12, rbx
0x180018df8  jb      short loc_180018E07
0x180018dfa  mov     r8, rbx; Size
0x180018dfd  mov     rdx, r15; Src
0x180018e00  call    memcpy_0
0x180018e05  jmp     short loc_180018E22
0x180018e07  mov     r8, r12; Size
0x180018e0a  xor     edx, edx; Val
0x180018e0c  call    memset_0
0x180018e11  call    cs:__imp__o__errno
0x180018e17  mov     dword ptr [rax], 22h ; '"'
0x180018e1d  call    _invalid_parameter_noinfo
0x180018e22  mov     [r14+rbx], si
0x180018e27  mov     [rsp+148h+var_C0], r14
0x180018e2f  mov     [rsp+148h+var_110], 2
0x180018e37  mov     rcx, [rsp+148h]; this
0x180018e3f  test    r14, r14
0x180018e42  jz      loc_1800198B3
0x180018e48  movzx   eax, word ptr [rdi+18h]
0x180018e4c  test    ax, ax
0x180018e4f  jnz     short loc_180018EC9
0x180018e51  mov     eax, cs:dword_18006E000
0x180018e57  cmp     eax, 2
0x180018e5a  jbe     loc_180019449
0x180018e60  mov     [rsp+148h+var_118], 80070057h
0x180018e68  lea     rax, [rsp+148h+var_118]
0x180018e6d  mov     [rsp+148h+var_58], rax
0x180018e75  mov     [rsp+148h+var_50], 4
0x180018e81  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x180018e89  movzx   eax, cs:word_18005F03B
0x180018e90  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x180018e94  mov     [rsp+148h+EventDescriptor.Keyword], rsi
0x180018e99  mov     rax, cs:off_18006E008
0x180018ea0  mov     [rsp+148h+var_78.Ptr], rax
0x180018ea8  movzx   eax, word ptr [rax]
0x180018eab  mov     [rsp+148h+var_78.Size], eax
0x180018eb2  lea     rax, byte_18005F045
0x180018eb9  mov     [rsp+148h+var_60], 38h ; '8'
0x180018ec4  jmp     loc_180019663
0x180018ec9  mov     rbx, rax
0x180018ecc  test    al, 1
0x180018ece  jnz     loc_1800195F0
  ... truncated ...
```
