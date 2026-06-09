# W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)

- ea: `0x18000a340`
- end: `0x18000aace`
- name: `?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `1934`
- prototype: ``
- caller_count: `14`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008bc0`
- `0x180008d60`
- `0x18001ccec`
- `0x18001cd9c`
- `0x18001cf90`
- `0x18001cfc0`
- `0x18001d0f8`
- `0x18001dff0`
- `0x18001e694`
- `0x18001ecc0`
- `0x1800224c0`
- `0x18002dc30`
- `0x18002dcb8`
- `0x18002e960`

## callees

- `0x18000a340`
- `0x18000ad00`
- `0x180014d00`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000aa63`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000aa63`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a37e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a3a6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a448`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aa0d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a37e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a3a6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a448`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aa0d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a59a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a9ec`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a59a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a9ec`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a5b4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aa92`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a5b4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aa92`

## pseudocode

```c
__int64 __fastcall W3_SERVER::GlobalNotify(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // r12
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned int *v8; // r15
  __int64 v9; // rbx
  int (__fastcall ***v10)(_QWORD, GUID **); // rax
  VIRTUAL_MODULE **v11; // rdi
  _QWORD *v12; // rsi
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall **v15)(__int64); // rax
  __int64 (__fastcall *v16)(__int64); // rax
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ebx
  __int64 (__fastcall **v23)(__int64); // rax
  __int64 (__fastcall *v24)(__int64); // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  const wchar_t *v27; // rax
  __int64 v29; // rbx
  int *v30; // rbx
  int i; // eax
  __int64 v32; // rcx
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  GUID *v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h]
  GUID *v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h]
  const wchar_t *v38; // [rsp+50h] [rbp-B0h]
  int v39; // [rsp+58h] [rbp-A8h]
  int v40; // [rsp+5Ch] [rbp-A4h]
  __int128 v41; // [rsp+60h] [rbp-A0h]
  int v42; // [rsp+70h] [rbp-90h]
  int v43; // [rsp+74h] [rbp-8Ch]
  int v44; // [rsp+78h] [rbp-88h]
  _QWORD v45[2]; // [rsp+7Ch] [rbp-84h] BYREF
  FILETIME FileTime1; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h]
  _QWORD *Ptr; // [rsp+A0h] [rbp-60h]
  GUID *v49; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-50h]
  const wchar_t *v51; // [rsp+C0h] [rbp-40h] BYREF
  int v52; // [rsp+C8h] [rbp-38h]
  __int64 v53; // [rsp+D0h] [rbp-30h]
  int v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h]
  const wchar_t *v56; // [rsp+E8h] [rbp-18h]
  int v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+100h] [rbp+0h]
  __int64 v60; // [rsp+108h] [rbp+8h]
  const wchar_t *v61; // [rsp+110h] [rbp+10h]
  int v62; // [rsp+118h] [rbp+18h]
  int *v63; // [rsp+120h] [rbp+20h]
  int v64; // [rsp+128h] [rbp+28h]
  const wchar_t *v65; // [rsp+130h] [rbp+30h]

  v47 = a3;
  v5 = 0;
  Ptr = BUFFER::QueryPtr((BUFFER *)(a1 + 560));
  if ( a2 == 32 )
  {
    v6 = 5;
  }
  else
  {
    if ( a2 != 128 )
    {
      if ( a2 > 0x20000 )
      {
        if ( a2 > 0x2000000 )
        {
          if ( a2 > 0x20000000 )
          {
            if ( a2 == 0x40000000 )
            {
              v6 = 30;
              goto LABEL_3;
            }
            if ( a2 == 0x80000000 )
            {
              v6 = 31;
              goto LABEL_3;
            }
          }
          else
          {
            switch ( a2 )
            {
              case 0x20000000u:
                v6 = 29;
                goto LABEL_3;
              case 0x4000000u:
                v6 = 26;
                goto LABEL_3;
              case 0x8000000u:
                v6 = 27;
                goto LABEL_3;
              case 0x10000000u:
                v6 = 28;
                goto LABEL_3;
            }
          }
        }
        else
        {
          if ( a2 == 0x2000000 )
          {
            v6 = 25;
            goto LABEL_3;
          }
          if ( a2 > 0x200000 )
          {
            switch ( a2 )
            {
              case 0x400000u:
                v6 = 22;
                goto LABEL_3;
              case 0x800000u:
                v6 = 23;
                goto LABEL_3;
              case 0x1000000u:
                v6 = 24;
                goto LABEL_3;
            }
          }
          else
          {
            switch ( a2 )
            {
              case 0x200000u:
                v6 = 21;
                goto LABEL_3;
              case 0x40000u:
                v6 = 18;
                goto LABEL_3;
              case 0x80000u:
                v6 = 19;
                goto LABEL_3;
              case 0x100000u:
                v6 = 20;
                goto LABEL_3;
            }
          }
        }
      }
      else
      {
        if ( a2 == 0x20000 )
        {
          v6 = 17;
          goto LABEL_3;
        }
        if ( a2 > 0x200 )
        {
          if ( a2 > 0x2000 )
          {
            switch ( a2 )
            {
              case 0x4000u:
                v6 = 14;
                goto LABEL_3;
              case 0x8000u:
                v6 = 15;
                goto LABEL_3;
              case 0x10000u:
                v6 = 16;
                goto LABEL_3;
            }
          }
          else
          {
            switch ( a2 )
            {
              case 0x2000u:
                v6 = 13;
                goto LABEL_3;
              case 0x400u:
                v6 = 10;
                goto LABEL_3;
              case 0x800u:
                v6 = 11;
                goto LABEL_3;
              case 0x1000u:
                v6 = 12;
                goto LABEL_3;
            }
          }
        }
        else
        {
          if ( a2 == 512 )
          {
            v6 = 9;
            goto LABEL_3;
          }
          if ( a2 > 8 )
          {
            switch ( a2 )
            {
              case 0x10u:
                v6 = 4;
                goto LABEL_3;
              case 0x40u:
                v6 = 6;
                goto LABEL_3;
              case 0x100u:
                v6 = 8;
                goto LABEL_3;
            }
          }
          else
          {
            if ( a2 == 8 )
            {
              v6 = 3;
              goto LABEL_3;
            }
            if ( a2 != 1 )
            {
              if ( a2 == 2 )
              {
                v6 = 1;
                goto LABEL_3;
              }
              if ( a2 == 4 )
              {
                v6 = 2;
                goto LABEL_3;
              }
            }
          }
        }
      }
      v6 = 0;
      goto LABEL_3;
    }
    v6 = 7;
  }
LABEL_3:
  v7 = *(unsigned int *)(a1 + 4 * v6 + 1112);
  v8 = (unsigned int *)((char *)BUFFER::QueryPtr((BUFFER *)(a1 + 1056)) + 4 * v7);
  if ( a2 == 256 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
    v10 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 272LL))(v9);
    v49 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v50 = 0;
    if ( (**v10)(v10, &v49) >= 0 && DWORD1(v50) >= 5 && DWORD2(v50) && ((_DWORD)v50 == 256 || (v50 & 0x100) != 0) )
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 272LL))(v9);
  }
  else if ( a2 == 4096 )
  {
    v11 = (VIRTUAL_MODULE **)BUFFER::QueryPtr((BUFFER *)(a1 + 560));
    FileTime1 = 0;
    if ( *(_DWORD *)(a1 + 1584) )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 1588));
      if ( *(_DWORD *)(a1 + 1584) )
      {
        v29 = *(unsigned int *)(a1 + 1180);
        v30 = (int *)((char *)BUFFER::QueryPtr((BUFFER *)(a1 + 1056)) + 4 * v29);
        for ( i = *v30; i != -1; ++v30 )
        {
          VIRTUAL_MODULE::Resume(v11[i]);
          i = v30[1];
        }
        v32 = *(_QWORD *)(a1 + 1496);
        if ( v32
          && (*(int (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v32 + 176LL))(v32, &FileTime1) >= 0
          && CompareFileTime(&FileTime1, (const FILETIME *)(a1 + 1612)) == 1 )
        {
          (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 112LL))(a1, L"MACHINE/WEBROOT/APPHOST");
        }
        *(_DWORD *)(a1 + 1584) = 0;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 1588));
    }
  }
  v12 = Ptr;
  while ( 1 )
  {
    v13 = *v8;
    if ( (_DWORD)v13 == -1 )
      break;
    v14 = v12[v13];
    if ( v5 )
    {
      v36 = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
      memset(v45, 0, 12);
      v35 = 256;
      v34 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v15 = *(__int64 (__fastcall ***)(__int64))v14;
      v37 = 4;
      v38 = L"PRE_BEGIN_REQUEST_START";
      v39 = 1;
      v16 = *v15;
      v40 = 5;
      v44 = 2;
      v41 = 0;
      v42 = 0;
      v43 = 1;
      v51 = L"ContextId";
      v52 = 72;
      v53 = 0;
      v54 = 16;
      v55 = 0;
      v56 = L"ModuleName";
      v57 = 31;
      v58 = v16(v14);
      if ( v58 )
      {
        v17 = -1;
        do
          v18 = *(_WORD *)(v58 + 2 * v17++ + 2) == 0;
        while ( !v18 );
        v19 = 2 * v17 + 2;
      }
      else
      {
        v19 = 0;
      }
      v59 = v19;
      v60 = 0;
      *(_QWORD *)((char *)v45 + 4) = &v51;
      (*(void (__fastcall **)(__int64, GUID **))(*(_QWORD *)v5 + 16LL))(v5, &v34);
    }
    if ( a2 == 128 || a2 == 2 || a2 == 4 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 1588));
      v20 = *(_QWORD *)(v14 + 104);
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        *(_QWORD *)(v14 + 104) = 0;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 1588));
    }
    v21 = VIRTUAL_MODULE::GlobalDoWork(v14, a2, v47);
    v22 = v21;
    if ( v5 )
    {
      v33 = v21;
      v51 = L"ContextId";
      memset(v45, 0, 12);
      v35 = 256;
      v34 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v36 = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
      v38 = L"PRE_BEGIN_REQUEST_END";
      v42 = 0;
      v53 = 0;
      v55 = 0;
      v56 = L"ModuleName";
      v23 = *(__int64 (__fastcall ***)(__int64))v14;
      v37 = 5;
      v39 = 1;
      v40 = 5;
      v24 = *v23;
      v44 = 3;
      v41 = 0;
      v43 = 1;
      v52 = 72;
      v54 = 16;
      v57 = 31;
      v25 = v24(v14);
      v58 = v25;
      v26 = v25;
      if ( v25 )
      {
        v25 = -1;
        do
          v18 = *(_WORD *)(v26 + 2 * v25++ + 2) == 0;
        while ( !v18 );
        LODWORD(v25) = 2 * v25 + 2;
      }
      v59 = v25;
      v61 = L"NotificationStatus";
      v63 = &v33;
      v60 = 0;
      v62 = 19;
      v64 = 4;
      if ( v33 )
      {
        if ( v33 == 1 )
          v27 = L"NOTIFICATION_HANDLED";
        else
          v27 = 0;
      }
      else
      {
        v27 = L"NOTIFICATION_CONTINUE";
      }
      v65 = v27;
      *(_QWORD *)((char *)v45 + 4) = &v51;
      (*(void (__fastcall **)(__int64, GUID **))(*(_QWORD *)v5 + 16LL))(v5, &v34);
    }
    if ( v22 == 1 )
      return 1;
    ++v8;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a340  mov     [rsp-8+arg_8], rbx
0x18000a345  push    rbp
0x18000a346  push    rsi
0x18000a347  push    rdi
0x18000a348  push    r12
0x18000a34a  push    r13
0x18000a34c  push    r14
0x18000a34e  push    r15
0x18000a350  lea     rbp, [rsp-50h]
0x18000a355  sub     rsp, 150h
0x18000a35c  mov     rax, cs:__security_cookie
0x18000a363  xor     rax, rsp
0x18000a366  mov     [rbp+80h+var_40], rax
0x18000a36a  mov     r14, rcx
0x18000a36d  mov     [rbp+80h+var_E8], r8
0x18000a371  add     rcx, 230h
0x18000a378  mov     r13d, edx
0x18000a37b  xor     r12d, r12d
0x18000a37e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a384  mov     [rbp+80h+var_E0], rax
0x18000a388  cmp     r13d, 20h ; ' '
0x18000a38c  jnz     loc_18000A755
0x18000a392  mov     eax, 5
0x18000a397  mov     ebx, [r14+rax*4+458h]
0x18000a39f  lea     rcx, [r14+420h]
0x18000a3a6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a3ac  lea     r15, [rax+rbx*4]
0x18000a3b0  cmp     r13d, 100h
0x18000a3b7  jnz     short loc_18000A438
0x18000a3b9  mov     rcx, [rbp+80h+var_E8]
0x18000a3bd  mov     rax, [rcx]
0x18000a3c0  mov     rax, [rax+8]
0x18000a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3c9  mov     rbx, rax
0x18000a3cc  mov     rcx, rbx
0x18000a3cf  mov     rax, [rax]
0x18000a3d2  mov     rax, [rax+110h]
0x18000a3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3de  mov     rcx, rax
0x18000a3e1  lea     rdx, [rbp+80h+var_D8]
0x18000a3e5  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000a3ec  xorps   xmm0, xmm0
0x18000a3ef  mov     [rbp+80h+var_D8], rax
0x18000a3f3  movdqu  [rbp+80h+var_D0], xmm0
0x18000a3f8  mov     rax, [rcx]
0x18000a3fb  mov     rax, [rax]
0x18000a3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a403  test    eax, eax
0x18000a405  js      short loc_18000A462
0x18000a407  cmp     dword ptr [rbp+80h+var_D0+4], 5
0x18000a40b  jb      short loc_18000A462
0x18000a40d  cmp     dword ptr [rbp+80h+var_D0+8], r12d
0x18000a411  jz      short loc_18000A462
0x18000a413  mov     rax, qword ptr [rbp+80h+var_D0]
0x18000a417  cmp     eax, r13d
0x18000a41a  jz      short loc_18000A421
0x18000a41c  test    r13d, eax
0x18000a41f  jz      short loc_18000A462
0x18000a421  mov     rax, [rbx]
0x18000a424  mov     rcx, rbx
0x18000a427  mov     rax, [rax+110h]
0x18000a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a433  mov     r12, rax
0x18000a436  jmp     short loc_18000A462
0x18000a438  cmp     r13d, 1000h
0x18000a43f  jnz     short loc_18000A462
0x18000a441  lea     rcx, [r14+230h]
0x18000a448  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a44e  mov     rdi, rax
0x18000a451  mov     qword ptr [rbp+80h+FileTime1.dwLowDateTime], r12
0x18000a455  cmp     [r14+630h], r12d
0x18000a45c  jnz     loc_18000A9E5
0x18000a462  mov     rsi, [rbp+80h+var_E0]
0x18000a466  mov     eax, [r15]
0x18000a469  lea     r8, aModulename; "ModuleName"
0x18000a470  lea     rdx, aContextid; "ContextId"
0x18000a477  lea     r9, aPreBeginReques_1; "PRE_BEGIN_REQUEST_START"
0x18000a47e  lea     rcx, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000a485  cmp     eax, 0FFFFFFFFh
0x18000a488  jz      loc_18000A768
0x18000a48e  mov     rdi, [rsi+rax*8]
0x18000a492  test    r12, r12
0x18000a495  jz      loc_18000A586
0x18000a49b  xor     eax, eax
0x18000a49d  mov     [rsp+180h+var_140], rcx
0x18000a4a2  mov     [rsp+180h+var_104], rax
0x18000a4a7  xor     ebx, ebx
0x18000a4a9  mov     [rbp+80h+var_FC], eax
0x18000a4ac  xorps   xmm0, xmm0
0x18000a4af  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000a4b6  mov     [rsp+180h+var_148], 100h
0x18000a4bf  mov     [rsp+180h+var_150], rax
0x18000a4c4  mov     rcx, rdi
0x18000a4c7  mov     rax, [rdi]
0x18000a4ca  mov     [rsp+180h+var_138], 4
0x18000a4d3  mov     [rsp+180h+var_130], r9
0x18000a4d8  mov     [rsp+180h+var_128], 1
0x18000a4e0  mov     rax, [rax]
0x18000a4e3  mov     [rsp+180h+var_124], 5
0x18000a4eb  mov     [rsp+180h+var_108], 2
0x18000a4f3  movdqa  [rsp+180h+var_120], xmm0
0x18000a4f9  mov     [rsp+180h+var_110], ebx
0x18000a4fd  mov     [rsp+180h+var_10C], 1
0x18000a505  mov     [rbp+80h+var_C0], rdx
0x18000a509  mov     [rbp+80h+var_B8], 48h ; 'H'
0x18000a510  mov     [rbp+80h+var_B0], rbx
0x18000a514  mov     [rbp+80h+var_A8], 10h
0x18000a51b  mov     [rbp+80h+var_A0], rbx
0x18000a51f  mov     [rbp+80h+var_98], r8
0x18000a523  mov     [rbp+80h+var_90], 1Fh
0x18000a52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a52f  mov     [rbp+80h+var_88], rax
0x18000a533  mov     rcx, rax
0x18000a536  test    rax, rax
0x18000a539  jz      loc_18000A703
0x18000a53f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a546  nop     word ptr [rax+rax+00000000h]
0x18000a550  cmp     [rcx+rax*2+2], bx
0x18000a555  lea     rax, [rax+1]
0x18000a559  jnz     short loc_18000A550
0x18000a55b  lea     eax, ds:2[rax*2]
0x18000a562  mov     [rbp+80h+var_80], eax
0x18000a565  lea     rdx, [rsp+180h+var_150]
0x18000a56a  lea     rax, [rbp+80h+var_C0]
0x18000a56e  mov     [rbp+80h+var_78], rbx
0x18000a572  mov     [rbp+80h+var_104+4], rax
0x18000a576  mov     rcx, r12
0x18000a579  mov     rax, [r12]
0x18000a57d  mov     rax, [rax+10h]
0x18000a581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a586  cmp     r13d, 80h
0x18000a58d  jnz     loc_18000A76C
0x18000a593  lea     rcx, [r14+634h]
0x18000a59a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a5a0  mov     rcx, [rdi+68h]
0x18000a5a4  test    rcx, rcx
0x18000a5a7  jnz     loc_18000AA9D
0x18000a5ad  lea     rcx, [r14+634h]
0x18000a5b4  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a5ba  mov     r8, [rbp+80h+var_E8]
0x18000a5be  mov     edx, r13d
0x18000a5c1  mov     rcx, rdi
0x18000a5c4  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000a5c9  mov     ebx, eax
0x18000a5cb  test    r12, r12
0x18000a5ce  jz      loc_18000A6F5
0x18000a5d4  mov     [rsp+180h+var_160], eax
0x18000a5d8  lea     rcx, aContextid; "ContextId"
0x18000a5df  xor     eax, eax
0x18000a5e1  mov     [rbp+80h+var_C0], rcx
0x18000a5e5  mov     [rsp+180h+var_104], rax
0x18000a5ea  xorps   xmm0, xmm0
0x18000a5ed  mov     [rbp+80h+var_FC], eax
0x18000a5f0  mov     rcx, rdi
0x18000a5f3  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000a5fa  mov     [rsp+180h+var_148], 100h
0x18000a603  mov     [rsp+180h+var_150], rax
0x18000a608  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000a60f  mov     [rsp+180h+var_140], rax
0x18000a614  lea     rax, aPreBeginReques_0; "PRE_BEGIN_REQUEST_END"
0x18000a61b  mov     [rsp+180h+var_130], rax
0x18000a620  xor     eax, eax
0x18000a622  mov     [rsp+180h+var_110], eax
0x18000a626  mov     [rbp+80h+var_B0], rax
0x18000a62a  mov     [rbp+80h+var_A0], rax
0x18000a62e  lea     rax, aModulename; "ModuleName"
0x18000a635  mov     [rbp+80h+var_98], rax
0x18000a639  mov     rax, [rdi]
0x18000a63c  mov     [rsp+180h+var_138], 5
0x18000a645  mov     [rsp+180h+var_128], 1
0x18000a64d  mov     [rsp+180h+var_124], 5
0x18000a655  mov     rax, [rax]
0x18000a658  mov     [rsp+180h+var_108], 3
0x18000a660  movdqa  [rsp+180h+var_120], xmm0
0x18000a666  mov     [rsp+180h+var_10C], 1
0x18000a66e  mov     [rbp+80h+var_B8], 48h ; 'H'
0x18000a675  mov     [rbp+80h+var_A8], 10h
0x18000a67c  mov     [rbp+80h+var_90], 1Fh
0x18000a683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a688  mov     [rbp+80h+var_88], rax
0x18000a68c  mov     rcx, rax
0x18000a68f  test    rax, rax
0x18000a692  jnz     short loc_18000A70A
0x18000a694  mov     [rbp+80h+var_80], eax
0x18000a697  lea     rax, aNotificationst; "NotificationStatus"
0x18000a69e  mov     [rbp+80h+var_70], rax
0x18000a6a2  lea     rax, [rsp+180h+var_160]
0x18000a6a7  mov     [rbp+80h+var_60], rax
0x18000a6ab  mov     eax, [rsp+180h+var_160]
0x18000a6af  mov     [rbp+80h+var_78], 0
0x18000a6b7  mov     [rbp+80h+var_68], 13h
0x18000a6be  mov     [rbp+80h+var_58], 4
0x18000a6c5  test    eax, eax
0x18000a6c7  jnz     loc_18000AAB6
0x18000a6cd  lea     rax, aNotificationCo; "NOTIFICATION_CONTINUE"
0x18000a6d4  mov     [rbp+80h+var_50], rax
0x18000a6d8  lea     rdx, [rsp+180h+var_150]
0x18000a6dd  lea     rax, [rbp+80h+var_C0]
0x18000a6e1  mov     rcx, r12
0x18000a6e4  mov     [rbp+80h+var_104+4], rax
0x18000a6e8  mov     rax, [r12]
0x18000a6ec  mov     rax, [rax+10h]
0x18000a6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f5  cmp     ebx, 1
0x18000a6f8  jz      short loc_18000A729
0x18000a6fa  add     r15, 4
0x18000a6fe  jmp     loc_18000A466
0x18000a703  mov     eax, ebx
0x18000a705  jmp     loc_18000A562
0x18000a70a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a711  cmp     word ptr [rcx+rax*2+2], 0
0x18000a717  lea     rax, [rax+1]
0x18000a71b  jnz     short loc_18000A711
0x18000a71d  lea     eax, ds:2[rax*2]
0x18000a724  jmp     loc_18000A694
0x18000a729  mov     eax, 1
0x18000a72e  mov     rcx, [rbp+80h+var_40]
0x18000a732  xor     rcx, rsp; StackCookie
0x18000a735  call    __security_check_cookie
0x18000a73a  mov     rbx, [rsp+180h+arg_8]
0x18000a742  add     rsp, 150h
0x18000a749  pop     r15
0x18000a74b  pop     r14
0x18000a74d  pop     r13
0x18000a74f  pop     r12
0x18000a751  pop     rdi
0x18000a752  pop     rsi
0x18000a753  pop     rbp
0x18000a754  retn
0x18000a755  cmp     r13d, 80h
0x18000a75c  jnz     short loc_18000A785
0x18000a75e  mov     eax, 7
0x18000a763  jmp     loc_18000A397
0x18000a768  xor     eax, eax
0x18000a76a  jmp     short loc_18000A72E
0x18000a76c  cmp     r13d, 2
0x18000a770  jz      loc_18000A593
0x18000a776  cmp     r13d, 4
0x18000a77a  jnz     loc_18000A5BA
0x18000a780  jmp     loc_18000A593
0x18000a785  cmp     r13d, 20000h
0x18000a78c  ja      loc_18000A8BE
0x18000a792  jz      loc_18000A8B4
0x18000a798  cmp     r13d, 200h
0x18000a79f  ja      loc_18000A825
0x18000a7a5  jz      short loc_18000A81B
0x18000a7a7  cmp     r13d, 8
0x18000a7ab  ja      short loc_18000A7E4
0x18000a7ad  jz      short loc_18000A7DA
0x18000a7af  mov     eax, r13d
0x18000a7b2  sub     eax, 1
0x18000a7b5  jz      loc_18000A9D4
0x18000a7bb  sub     eax, 1
0x18000a7be  jz      short loc_18000A7D0
0x18000a7c0  cmp     eax, 2
0x18000a7c3  jnz     loc_18000A9D4
0x18000a7c9  mov     eax, eax
0x18000a7cb  jmp     loc_18000A397
0x18000a7d0  mov     eax, 1
0x18000a7d5  jmp     loc_18000A397
0x18000a7da  mov     eax, 3
0x18000a7df  jmp     loc_18000A397
0x18000a7e4  cmp     r13d, 10h
0x18000a7e8  jz      short loc_18000A811
0x18000a7ea  cmp     r13d, 40h ; '@'
0x18000a7ee  jz      short loc_18000A807
0x18000a7f0  cmp     r13d, 100h
0x18000a7f7  jnz     loc_18000A9D4
0x18000a7fd  mov     eax, 8
0x18000a802  jmp     loc_18000A397
0x18000a807  mov     eax, 6
0x18000a80c  jmp     loc_18000A397
0x18000a811  mov     eax, 4
0x18000a816  jmp     loc_18000A397
0x18000a81b  mov     eax, 9
0x18000a820  jmp     loc_18000A397
0x18000a825  cmp     r13d, 2000h
0x18000a82c  ja      short loc_18000A877
0x18000a82e  jz      short loc_18000A86D
0x18000a830  cmp     r13d, 400h
0x18000a837  jz      short loc_18000A863
0x18000a839  cmp     r13d, 800h
0x18000a840  jz      short loc_18000A859
0x18000a842  cmp     r13d, 1000h
0x18000a849  jnz     loc_18000A9D4
0x18000a84f  mov     eax, 0Ch
0x18000a854  jmp     loc_18000A397
0x18000a859  mov     eax, 0Bh
0x18000a85e  jmp     loc_18000A397
0x18000a863  mov     eax, 0Ah
0x18000a868  jmp     loc_18000A397
0x18000a86d  mov     eax, 0Dh
0x18000a872  jmp     loc_18000A397
0x18000a877  cmp     r13d, 4000h
0x18000a87e  jz      short loc_18000A8AA
0x18000a880  cmp     r13d, 8000h
0x18000a887  jz      short loc_18000A8A0
0x18000a889  cmp     r13d, 10000h
0x18000a890  jnz     loc_18000A9D4
0x18000a896  mov     eax, 10h
  ... truncated ...
```
