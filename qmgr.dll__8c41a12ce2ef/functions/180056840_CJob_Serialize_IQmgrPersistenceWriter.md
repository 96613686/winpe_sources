# CJob::Serialize(IQmgrPersistenceWriter &)

- ea: `0x180056840`
- end: `0x1800577ea`
- name: `?Serialize@CJob@@MEAAJAEAVIQmgrPersistenceWriter@@@Z`
- size: `4010`
- prototype: `int(CJob *__hidden this, struct IQmgrPersistenceWriter *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d3d10`

## callees

- `0x1800231c8`
- `0x180056840`
- `0x1800577f0`
- `0x180057a9c`
- `0x180057b8c`
- `0x180057cac`
- `0x180057e48`
- `0x18009729c`
- `0x1800ab7fc`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056e2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056e2f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056e29`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056e29`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180057085`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180057085`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180057792`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180057792`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CJob::Serialize(CJob *this, struct IQmgrPersistenceWriter *a2)
{
  unsigned int v4; // eax
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  GUID **i; // rbx
  CJobManager *v10; // rbx
  __int64 v11; // rax
  char v12; // bl
  __int64 v13; // rax
  __int64 v14; // rax
  bool v15; // cl
  __int64 v16; // rax
  char v17; // bl
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  char v21; // bl
  __int64 v22; // rax
  __int64 v23; // rax
  CJobManager *v24; // rbx
  _WORD *v25; // r15
  __int64 v26; // r14
  __int64 v27; // rbx
  int v28; // ebx
  _WORD *v29; // r15
  int v30; // r9d
  _QWORD *v31; // r10
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  CEncryptedBlob **v34; // rbx
  void (__fastcall *v35)(struct IQmgrPersistenceWriter *, __int64 *, __int64); // rax
  unsigned __int64 v36; // rbx
  const void *v37; // rdx
  __int64 v38; // rbx
  unsigned __int16 *v39; // rdx
  unsigned __int16 *v40; // rdx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  GUID v45; // [rsp+20h] [rbp-79h] BYREF
  __int128 v46; // [rsp+30h] [rbp-69h] BYREF
  __int128 v47; // [rsp+40h] [rbp-59h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-49h] BYREF
  __int128 v49; // [rsp+58h] [rbp-41h]
  int v50; // [rsp+68h] [rbp-31h]
  int v51; // [rsp+6Ch] [rbp-2Dh]
  int v52; // [rsp+70h] [rbp-29h]
  __int64 v53; // [rsp+100h] [rbp+67h] BYREF
  _QWORD *v54; // [rsp+108h] [rbp+6Fh] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, this);
  *((_BYTE *)this + 1000) = 0;
  v45 = DownloadJobGuid_v10_3_2;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v45, 16);
  LODWORD(v53) = 0;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 164);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v4 = *((_DWORD *)this + 165);
  if ( v4 <= 2 || v4 == 5 )
    v4 = 0;
  LODWORD(v53) = v4;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 166);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v46 = *(_OWORD *)((char *)this + 676);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int128 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v46, 16);
  LODWORD(v53) = **((_DWORD **)this + 87) + 1;
  v5 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 87) + 12LL,
    (unsigned int)(2 * v5));
  LODWORD(v53) = **((_DWORD **)this + 88) + 1;
  v6 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 88) + 12LL,
    (unsigned int)(2 * v6));
  LODWORD(v53) = **((_DWORD **)this + 101) + 1;
  v7 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 101) + 12LL,
    (unsigned int)(2 * v7));
  LODWORD(v53) = **((_DWORD **)this + 102) + 1;
  v8 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 102) + 12LL,
    (unsigned int)(2 * v8));
  SafeWriteSid(a2, (CJob *)((char *)this + 712));
  LODWORD(v53) = *((_DWORD *)this + 201);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 188);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 189);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 210);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 211);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  CJobSecurityDescriptor::Serialize(*((CJobSecurityDescriptor **)this + 104), a2);
  v45 = FileListStorageGuid;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v45, 16);
  LODWORD(v53) = (__int64)(*((_QWORD *)this + 107) - *((_QWORD *)this + 106)) >> 3;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  for ( i = (GUID **)*((_QWORD *)this + 106); i != *((GUID ***)this + 107); ++i )
  {
    v45 = (*i)[24];
    SafeWritePersistentState(a2, &v45, 0x10u);
  }
  v45 = FileListStorageGuid;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v45, 16);
  if ( *((_BYTE *)this + 872) )
  {
    LODWORD(v53) = 1;
    SafeWritePersistentState(a2, &v53, 4u);
    LODWORD(v53) = *((_DWORD *)this + 219);
    SafeWritePersistentState(a2, &v53, 4u);
    LODWORD(v53) = *((_DWORD *)this + 223);
    SafeWritePersistentState(a2, &v53, 4u);
    LODWORD(v53) = *((_DWORD *)this + 224);
    SafeWritePersistentState(a2, &v53, 4u);
    LODWORD(v53) = *((_DWORD *)this + 225);
    SafeWritePersistentState(a2, &v53, 4u);
    LODWORD(v53) = *((_DWORD *)this + 222);
    SafeWritePersistentState(a2, &v53, 4u);
    SafeWritePersistentState(a2, *((unsigned __int16 **)this + 113));
  }
  else
  {
    LODWORD(v53) = 0;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  }
  LODWORD(v53) = *((_DWORD *)this + 230);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 232);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 233);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v53 = *((_QWORD *)this + 118);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  v53 = *((_QWORD *)this + 119);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  v53 = *((_QWORD *)this + 120);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  v53 = *((_QWORD *)this + 121);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  LOBYTE(v53) = *((_BYTE *)this + 1344);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( *((_BYTE *)this + 1344) )
  {
    v45 = *(GUID *)((char *)this + 1348);
    SafeWritePersistentState(a2, &v45, 0x10u);
    LOBYTE(v53) = *((_BYTE *)this + 1376);
    SafeWritePersistentState(a2, &v53, 1u);
    if ( *((_BYTE *)this + 1376) )
    {
      v45 = *(GUID *)((char *)this + 1380);
      SafeWritePersistentState(a2, &v45, 0x10u);
    }
  }
  LODWORD(v53) = *((_DWORD *)this + 73);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v10 = g_Manager;
  WaitForSingleObject(*((HANDLE *)g_Manager + 67), 0xFFFFFFFF);
  *((_DWORD *)v10 + 145) = GetCurrentThreadId();
  LOBYTE(v53) = *((_DWORD *)this + 20) <= 2u;
  LOBYTE(v10) = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( (_BYTE)v10 )
  {
    v53 = *((_QWORD *)this + 4);
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
    v53 = *((_QWORD *)this + 5);
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  }
  v11 = (__int64)this + 384;
  if ( !this )
    v11 = 80;
  LOBYTE(v53) = *(_DWORD *)v11 <= 2u;
  v12 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( v12 )
  {
    v13 = (__int64)this + 336;
    if ( !this )
      v13 = 32;
    v53 = *(_QWORD *)v13;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
    v14 = (__int64)this + 344;
    if ( !this )
      v14 = 40;
    v53 = *(_QWORD *)v14;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  }
  v15 = _InterlockedCompareExchange((volatile signed __int32 *)this + 72, 0, 0) != 0;
  v16 = (__int64)this + 272;
  if ( !this )
    v16 = 80;
  if ( *(_DWORD *)v16 <= 2u || (v17 = 0, v15) )
    v17 = 1;
  LOBYTE(v53) = v17;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( v17 )
  {
    v18 = (__int64)this + 224;
    if ( !this )
      v18 = 32;
    v53 = *(_QWORD *)v18;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
    v19 = (__int64)this + 232;
    if ( !this )
      v19 = 40;
    v53 = *(_QWORD *)v19;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  }
  v20 = (__int64)this + 176;
  if ( !this )
    v20 = 80;
  LOBYTE(v53) = *(_DWORD *)v20 <= 2u;
  v21 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( v21 )
  {
    v22 = (__int64)this + 128;
    if ( !this )
      v22 = 32;
    v54 = *(_QWORD **)v22;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, _QWORD **, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v54, 8);
    v23 = (__int64)this + 136;
    if ( !this )
      v23 = 40;
    v54 = *(_QWORD **)v23;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, _QWORD **, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v54, 8);
  }
  v24 = g_Manager;
  ReleaseMutex(*((HANDLE *)g_Manager + 67));
  *((_DWORD *)v24 + 145) = 0;
  LODWORD(v53) = *((_DWORD *)this + 252);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v25 = (_WORD *)*((_QWORD *)this + 127);
  LOBYTE(v53) = v25 != 0;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  v26 = -1;
  if ( v25 )
  {
    v27 = -1;
    do
      ++v27;
    while ( v25[v27] );
    v28 = v27 + 1;
    LODWORD(v53) = v28;
    SafeWritePersistentState(a2, &v53, 4u);
    SafeWritePersistentState(a2, v25, 2 * v28);
  }
  v29 = (_WORD *)*((_QWORD *)this + 128);
  LOBYTE(v53) = v29 != 0;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( v29 )
  {
    do
      ++v26;
    while ( v29[v26] );
    LODWORD(v53) = v26 + 1;
    SafeWritePersistentState(a2, &v53, 4u);
    SafeWritePersistentState(a2, v29, 2 * (v26 + 1));
  }
  v30 = 0;
  v31 = (_QWORD *)*((_QWORD *)this + 129);
  v32 = (_QWORD *)*v31;
  v54 = (_QWORD *)*v31;
  while ( v32 != v31 )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>,std::_Iterator_base0>::operator++(&v54);
    v32 = v54;
  }
  LODWORD(v53) = v30;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v33 = (_QWORD *)**((_QWORD **)this + 129);
  v54 = v33;
  while ( v33 != *((_QWORD **)this + 129) )
  {
    v34 = (CEncryptedBlob **)v33[5];
    if ( v34 )
    {
      LODWORD(v53) = *((_DWORD *)v33 + 8);
      SafeWritePersistentState(a2, &v53, 4u);
      if ( *v34 )
      {
        LOBYTE(v53) = 1;
        SafeWritePersistentState(a2, &v53, 1u);
        CEncryptedBlob::Serialize(*v34, a2);
      }
      else
      {
        LOBYTE(v53) = 0;
        SafeWritePersistentState(a2, &v53, 1u);
      }
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>,std::_Iterator_base0>::operator++(&v54);
    v33 = v54;
  }
  LODWORD(v53) = *((_DWORD *)this + 264);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v35 = *(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL);
  if ( *((_QWORD *)this + 133) )
  {
    LOBYTE(v53) = 1;
    v35(a2, &v53, 1);
    CEncryptedBlob::Serialize(*((CEncryptedBlob **)this + 133), a2);
  }
  else
  {
    LOBYTE(v53) = 0;
    v35(a2, &v53, 1);
  }
  CClientCertificate::Serialize((CJob *)((char *)this + 1072), a2);
  LODWORD(v53) = *((_DWORD *)this + 302);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 303);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 304);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 305);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 308);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 167);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LOBYTE(v53) = *((_BYTE *)this + 672);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  LOBYTE(v53) = *((_BYTE *)this + 673);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  v53 = *((_QWORD *)this + 95);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  v46 = *(_OWORD *)((char *)this + 788);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int128 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v46, 16);
  LODWORD(v53) = *((_DWORD *)this + 318);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LODWORD(v53) = *((_DWORD *)this + 235);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v36 = *((_QWORD *)this + 164) - *((_QWORD *)this + 163);
  if ( v36 > 0xFFFFFFFF )
  {
    v49 = 0;
    pExceptionObject = &ComError::`vftable';
    v50 = -2147024362;
    v51 = 205;
    v52 = 1;
    throw (ComError *)&pExceptionObject;
  }
  LODWORD(v53) = *((_DWORD *)this + 328) - *((_DWORD *)this + 326);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  v37 = (const void *)*((_QWORD *)this + 163);
  if ( *((const void **)this + 164) != v37 )
    SafeWritePersistentState(a2, v37, v36);
  LODWORD(v53) = *((_DWORD *)this + 319);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LOBYTE(v53) = *((_BYTE *)this + 1268);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  v38 = *((_QWORD *)this + 92);
  v45 = (GUID)xmmword_18011AD60;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v45, 16);
  LOBYTE(v53) = v38 == 0;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  if ( v38 )
  {
    if ( *(_QWORD *)(v38 + 24) <= 7u )
      v39 = (unsigned __int16 *)v38;
    else
      v39 = *(unsigned __int16 **)v38;
    SafeWritePersistentState(a2, v39);
    v40 = (unsigned __int16 *)(v38 + 32);
    if ( *(_QWORD *)(v38 + 56) > 7u )
      v40 = *(unsigned __int16 **)v40;
    SafeWritePersistentState(a2, v40);
    LOBYTE(v53) = *(_BYTE *)(v38 + 68);
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
    LODWORD(v53) = *(_DWORD *)(v38 + 64);
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  }
  v45 = (GUID)xmmword_18011AD60;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v45, 16);
  LODWORD(v53) = *((_DWORD *)this + 320);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  LOBYTE(v53) = *((_BYTE *)this + 1284);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  v47 = *((_OWORD *)this + 83);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int128 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v47, 16);
  LODWORD(v53) = **((_DWORD **)this + 91) + 1;
  v41 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 91) + 12LL,
    (unsigned int)(2 * v41));
  v53 = *((_QWORD *)this + 183);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  v53 = *((_QWORD *)this + 182);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 8);
  LODWORD(v53) = **((_DWORD **)this + 161) + 1;
  v42 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 161) + 12LL,
    (unsigned int)(2 * v42));
  LOBYTE(v53) = *((_BYTE *)this + 1296);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  LOBYTE(v53) = *((_BYTE *)this + 1297);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  LOBYTE(v53) = *((_BYTE *)this + 1504);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  LODWORD(v53) = **((_DWORD **)this + 191) + 1;
  v43 = v53;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 191) + 12LL,
    (unsigned int)(2 * v43));
  LOBYTE(v53) = *((_BYTE *)this + 1536);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v53, 1);
  v45 = DownloadJobGuid_v10_3_2;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v45, 16);
  GetSystemTimeAsFileTime((LPFILETIME)this + 122);
  return 0;
}

```

## disassembly

```asm
0x180056840  mov     [rsp-8+arg_10], rbx
0x180056845  push    rbp
0x180056846  push    rsi
0x180056847  push    rdi
0x180056848  push    r12
0x18005684a  push    r13
0x18005684c  push    r14
0x18005684e  push    r15
0x180056850  lea     rbp, [rsp-27h]
0x180056855  sub     rsp, 0C0h
0x18005685c  mov     rdi, rdx
0x18005685f  mov     rsi, rcx
0x180056862  lea     rax, WPP_GLOBAL_Control
0x180056869  mov     r14d, 1
0x18005686f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056876  cmp     rcx, rax
0x180056879  jz      short loc_180056899
0x18005687b  test    [rcx+1Ch], r14b
0x18005687f  jz      short loc_180056899
0x180056881  mov     edx, 104h
0x180056886  mov     r9, rsi
0x180056889  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x180056890  mov     rcx, [rcx+10h]
0x180056894  call    WPP_SF_q
0x180056899  xor     r12d, r12d
0x18005689c  mov     [rsi+3E8h], r12b
0x1800568a3  movups  xmm0, xmmword ptr cs:?DownloadJobGuid_v10_3_2@@3U_GUID@@A.Data1; _GUID DownloadJobGuid_v10_3_2 ...
0x1800568aa  movdqu  [rbp+57h+var_D0], xmm0
0x1800568af  mov     rax, [rdi]
0x1800568b2  lea     r15d, [r12+10h]
0x1800568b7  mov     r8d, r15d
0x1800568ba  lea     rdx, [rbp+57h+var_D0]
0x1800568be  mov     rcx, rdi
0x1800568c1  mov     rax, [rax+8]
0x1800568c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568ca  mov     dword ptr [rbp+57h+arg_0], r12d
0x1800568ce  mov     rax, [rdi]
0x1800568d1  lea     r13d, [r12+4]
0x1800568d6  mov     r8d, r13d
0x1800568d9  lea     rdx, [rbp+57h+arg_0]
0x1800568dd  mov     rcx, rdi
0x1800568e0  mov     rax, [rax+8]
0x1800568e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568e9  mov     eax, [rsi+290h]
0x1800568ef  mov     dword ptr [rbp+57h+arg_0], eax
0x1800568f2  mov     rax, [rdi]
0x1800568f5  mov     r8d, r13d
0x1800568f8  lea     rdx, [rbp+57h+arg_0]
0x1800568fc  mov     rcx, rdi
0x1800568ff  mov     rax, [rax+8]
0x180056903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056908  mov     eax, [rsi+294h]
0x18005690e  cmp     eax, 2
0x180056911  jbe     short loc_180056918
0x180056913  cmp     eax, 5
0x180056916  jnz     short loc_18005691B
0x180056918  mov     eax, r12d
0x18005691b  mov     dword ptr [rbp+57h+arg_0], eax
0x18005691e  mov     rax, [rdi]
0x180056921  mov     r8d, r13d
0x180056924  lea     rdx, [rbp+57h+arg_0]
0x180056928  mov     rcx, rdi
0x18005692b  mov     rax, [rax+8]
0x18005692f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056934  mov     eax, [rsi+298h]
0x18005693a  mov     dword ptr [rbp+57h+arg_0], eax
0x18005693d  mov     rax, [rdi]
0x180056940  mov     r8d, r13d
0x180056943  lea     rdx, [rbp+57h+arg_0]
0x180056947  mov     rcx, rdi
0x18005694a  mov     rax, [rax+8]
0x18005694e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056953  movups  xmm0, xmmword ptr [rsi+2A4h]
0x18005695a  movdqu  [rbp+57h+var_C0], xmm0
0x18005695f  mov     rax, [rdi]
0x180056962  mov     r8d, r15d
0x180056965  lea     rdx, [rbp+57h+var_C0]
0x180056969  mov     rcx, rdi
0x18005696c  mov     rax, [rax+8]
0x180056970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056975  mov     rax, [rsi+2B8h]
0x18005697c  mov     ebx, [rax]
0x18005697e  inc     ebx
0x180056980  mov     dword ptr [rbp+57h+arg_0], ebx
0x180056983  mov     rax, [rdi]
0x180056986  mov     r8d, r13d
0x180056989  lea     rdx, [rbp+57h+arg_0]
0x18005698d  mov     rcx, rdi
0x180056990  mov     rax, [rax+8]
0x180056994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056999  mov     rax, [rdi]
0x18005699c  lea     r8d, [rbx+rbx]
0x1800569a0  mov     rdx, [rsi+2B8h]
0x1800569a7  add     rdx, 0Ch
0x1800569ab  mov     rcx, rdi
0x1800569ae  mov     rax, [rax+8]
0x1800569b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569b7  mov     rax, [rsi+2C0h]
0x1800569be  mov     ebx, [rax]
0x1800569c0  inc     ebx
0x1800569c2  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800569c5  mov     rax, [rdi]
0x1800569c8  mov     r8d, r13d
0x1800569cb  lea     rdx, [rbp+57h+arg_0]
0x1800569cf  mov     rcx, rdi
0x1800569d2  mov     rax, [rax+8]
0x1800569d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569db  mov     rax, [rdi]
0x1800569de  lea     r8d, [rbx+rbx]
0x1800569e2  mov     rdx, [rsi+2C0h]
0x1800569e9  add     rdx, 0Ch
0x1800569ed  mov     rcx, rdi
0x1800569f0  mov     rax, [rax+8]
0x1800569f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569f9  mov     rax, [rsi+328h]
0x180056a00  mov     ebx, [rax]
0x180056a02  inc     ebx
0x180056a04  mov     dword ptr [rbp+57h+arg_0], ebx
0x180056a07  mov     rax, [rdi]
0x180056a0a  mov     r8d, r13d
0x180056a0d  lea     rdx, [rbp+57h+arg_0]
0x180056a11  mov     rcx, rdi
0x180056a14  mov     rax, [rax+8]
0x180056a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a1d  mov     rax, [rdi]
0x180056a20  lea     r8d, [rbx+rbx]
0x180056a24  mov     rdx, [rsi+328h]
0x180056a2b  add     rdx, 0Ch
0x180056a2f  mov     rcx, rdi
0x180056a32  mov     rax, [rax+8]
0x180056a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a3b  mov     rax, [rsi+330h]
0x180056a42  mov     ebx, [rax]
0x180056a44  inc     ebx
0x180056a46  mov     dword ptr [rbp+57h+arg_0], ebx
0x180056a49  mov     rax, [rdi]
0x180056a4c  mov     r8d, r13d
0x180056a4f  lea     rdx, [rbp+57h+arg_0]
0x180056a53  mov     rcx, rdi
0x180056a56  mov     rax, [rax+8]
0x180056a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a5f  mov     rax, [rdi]
0x180056a62  lea     r8d, [rbx+rbx]
0x180056a66  mov     rdx, [rsi+330h]
0x180056a6d  add     rdx, 0Ch
0x180056a71  mov     rcx, rdi
0x180056a74  mov     rax, [rax+8]
0x180056a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a7d  lea     rdx, [rsi+2C8h]; struct SidHandle *
0x180056a84  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056a87  call    ?SafeWriteSid@@YAXAEAVIQmgrPersistenceWriter@@AEAVSidHandle@@@Z; SafeWriteSid(IQmgrPersistenceWriter &,SidHandle &)
0x180056a8c  mov     eax, [rsi+324h]
0x180056a92  mov     dword ptr [rbp+57h+arg_0], eax
0x180056a95  mov     rax, [rdi]
0x180056a98  mov     r8d, r13d
0x180056a9b  lea     rdx, [rbp+57h+arg_0]
0x180056a9f  mov     rcx, rdi
0x180056aa2  mov     rax, [rax+8]
0x180056aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056aab  mov     eax, [rsi+2F0h]
0x180056ab1  mov     dword ptr [rbp+57h+arg_0], eax
0x180056ab4  mov     rax, [rdi]
0x180056ab7  mov     r8d, r13d
0x180056aba  lea     rdx, [rbp+57h+arg_0]
0x180056abe  mov     rcx, rdi
0x180056ac1  mov     rax, [rax+8]
0x180056ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056aca  mov     eax, [rsi+2F4h]
0x180056ad0  mov     dword ptr [rbp+57h+arg_0], eax
0x180056ad3  mov     rax, [rdi]
0x180056ad6  mov     r8d, r13d
0x180056ad9  lea     rdx, [rbp+57h+arg_0]
0x180056add  mov     rcx, rdi
0x180056ae0  mov     rax, [rax+8]
0x180056ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ae9  mov     eax, [rsi+348h]
0x180056aef  mov     dword ptr [rbp+57h+arg_0], eax
0x180056af2  mov     rax, [rdi]
0x180056af5  mov     r8d, r13d
0x180056af8  lea     rdx, [rbp+57h+arg_0]
0x180056afc  mov     rcx, rdi
0x180056aff  mov     rax, [rax+8]
0x180056b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b08  mov     eax, [rsi+34Ch]
0x180056b0e  mov     dword ptr [rbp+57h+arg_0], eax
0x180056b11  mov     rax, [rdi]
0x180056b14  mov     r8d, r13d
0x180056b17  lea     rdx, [rbp+57h+arg_0]
0x180056b1b  mov     rcx, rdi
0x180056b1e  mov     rax, [rax+8]
0x180056b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b27  mov     rdx, rdi; struct IQmgrPersistenceWriter *
0x180056b2a  mov     rcx, [rsi+340h]; this
0x180056b31  call    ?Serialize@CJobSecurityDescriptor@@QEAAJAEAVIQmgrPersistenceWriter@@@Z; CJobSecurityDescriptor::Serialize(IQmgrPersistenceWriter &)
0x180056b36  movups  xmm0, xmmword ptr cs:?FileListStorageGuid@@3U_GUID@@A.Data1; _GUID FileListStorageGuid ...
0x180056b3d  movdqu  [rbp+57h+var_D0], xmm0
0x180056b42  mov     rax, [rdi]
0x180056b45  mov     r8d, r15d
0x180056b48  lea     rdx, [rbp+57h+var_D0]
0x180056b4c  mov     rcx, rdi
0x180056b4f  mov     rax, [rax+8]
0x180056b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b58  mov     rax, [rsi+358h]
0x180056b5f  sub     rax, [rsi+350h]
0x180056b66  sar     rax, 3
0x180056b6a  mov     dword ptr [rbp+57h+arg_0], eax
0x180056b6d  mov     rax, [rdi]
0x180056b70  mov     r8d, r13d
0x180056b73  lea     rdx, [rbp+57h+arg_0]
0x180056b77  mov     rcx, rdi
0x180056b7a  mov     rax, [rax+8]
0x180056b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b83  mov     rbx, [rsi+350h]
0x180056b8a  mov     r15d, 8
0x180056b90  lea     rdx, [rbp+57h+var_D0]; void *
0x180056b94  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056b97  cmp     rbx, [rsi+358h]
0x180056b9e  jz      short loc_180056BBF
0x180056ba0  mov     rax, [rbx]
0x180056ba3  movups  xmm0, xmmword ptr [rax+180h]
0x180056baa  movdqu  [rbp+57h+var_D0], xmm0
0x180056baf  mov     r8d, 10h; unsigned int
0x180056bb5  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056bba  add     rbx, r15
0x180056bbd  jmp     short loc_180056B90
0x180056bbf  movups  xmm0, xmmword ptr cs:?FileListStorageGuid@@3U_GUID@@A.Data1; _GUID FileListStorageGuid ...
0x180056bc6  movdqu  [rbp+57h+var_D0], xmm0
0x180056bcb  mov     rax, [rdi]
0x180056bce  mov     ebx, 10h
0x180056bd3  mov     r8d, ebx
0x180056bd6  mov     rax, [rax+8]
0x180056bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bdf  mov     r8d, r13d; unsigned int
0x180056be2  lea     rdx, [rbp+57h+arg_0]; void *
0x180056be6  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056be9  cmp     [rsi+368h], r12b
0x180056bf0  jnz     short loc_180056C07
0x180056bf2  mov     dword ptr [rbp+57h+arg_0], r12d
0x180056bf6  mov     rax, [rdi]
0x180056bf9  mov     rax, [rax+8]
0x180056bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c02  jmp     loc_180056C97
0x180056c07  mov     dword ptr [rbp+57h+arg_0], r14d
0x180056c0b  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056c10  mov     eax, [rsi+36Ch]
0x180056c16  mov     dword ptr [rbp+57h+arg_0], eax
0x180056c19  mov     r8d, r13d; unsigned int
0x180056c1c  lea     rdx, [rbp+57h+arg_0]; void *
0x180056c20  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056c23  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056c28  mov     eax, [rsi+37Ch]
0x180056c2e  mov     dword ptr [rbp+57h+arg_0], eax
0x180056c31  mov     r8d, r13d; unsigned int
0x180056c34  lea     rdx, [rbp+57h+arg_0]; void *
0x180056c38  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056c3b  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056c40  mov     eax, [rsi+380h]
0x180056c46  mov     dword ptr [rbp+57h+arg_0], eax
0x180056c49  mov     r8d, r13d; unsigned int
0x180056c4c  lea     rdx, [rbp+57h+arg_0]; void *
0x180056c50  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056c53  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056c58  mov     eax, [rsi+384h]
0x180056c5e  mov     dword ptr [rbp+57h+arg_0], eax
0x180056c61  mov     r8d, r13d; unsigned int
0x180056c64  lea     rdx, [rbp+57h+arg_0]; void *
0x180056c68  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056c6b  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056c70  mov     eax, [rsi+378h]
0x180056c76  mov     dword ptr [rbp+57h+arg_0], eax
0x180056c79  mov     r8d, r13d; unsigned int
0x180056c7c  lea     rdx, [rbp+57h+arg_0]; void *
0x180056c80  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056c83  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180056c88  mov     rdx, [rsi+388h]; unsigned __int16 *
0x180056c8f  mov     rcx, rdi; struct IQmgrPersistenceWriter *
0x180056c92  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEAG@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,ushort *)
0x180056c97  mov     eax, [rsi+398h]
0x180056c9d  mov     dword ptr [rbp+57h+arg_0], eax
0x180056ca0  mov     rax, [rdi]
0x180056ca3  mov     r8d, r13d
0x180056ca6  lea     rdx, [rbp+57h+arg_0]
0x180056caa  mov     rcx, rdi
0x180056cad  mov     rax, [rax+8]
0x180056cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cb6  mov     eax, [rsi+3A0h]
0x180056cbc  mov     dword ptr [rbp+57h+arg_0], eax
0x180056cbf  mov     rax, [rdi]
0x180056cc2  mov     r8d, r13d
0x180056cc5  lea     rdx, [rbp+57h+arg_0]
0x180056cc9  mov     rcx, rdi
0x180056ccc  mov     rax, [rax+8]
0x180056cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cd5  mov     eax, [rsi+3A4h]
0x180056cdb  mov     dword ptr [rbp+57h+arg_0], eax
0x180056cde  mov     rax, [rdi]
0x180056ce1  mov     r8d, r13d
0x180056ce4  lea     rdx, [rbp+57h+arg_0]
0x180056ce8  mov     rcx, rdi
0x180056ceb  mov     rax, [rax+8]
  ... truncated ...
```
