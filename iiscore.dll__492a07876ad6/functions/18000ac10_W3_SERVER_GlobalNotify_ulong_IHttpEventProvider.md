# W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)

- ea: `0x18000ac10`
- end: `0x18000b3d6`
- name: `?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `1990`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800092c0`
- `0x180009480`
- `0x18001e64c`
- `0x18001e704`
- `0x18001e940`
- `0x18001e970`
- `0x18001ead4`
- `0x18001fa50`
- `0x180020148`
- `0x180020804`
- `0x180024140`
- `0x1800306ac`
- `0x180030738`
- `0x180031534`

## callees

- `0x18000ac10`
- `0x18000b640`
- `0x180015e40`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b35f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b35f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac7c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad24`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b303`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac7c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ad24`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b303`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae7a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b2dc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae7a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b2dc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae9a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b394`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae9a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b394`

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
  _QWORD *v14; // rdi
  __int64 (__fastcall **v15)(_QWORD); // rax
  __int64 (__fastcall *v16)(_QWORD *); // rax
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ebx
  __int64 (__fastcall **v23)(_QWORD); // rax
  __int64 (__fastcall *v24)(_QWORD *); // rax
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
    v14 = (_QWORD *)v12[v13];
    if ( v5 )
    {
      v36 = &`IISRequestNotificationEvents::GetAreaGuid'::`2'::AreaGuid;
      memset(v45, 0, 12);
      v35 = 256;
      v34 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v15 = (__int64 (__fastcall **)(_QWORD))*v14;
      v37 = 4;
      v38 = L"PRE_BEGIN_REQUEST_START";
      v39 = 1;
      v16 = (__int64 (__fastcall *)(_QWORD *))*v15;
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
      v20 = v14[13];
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v14[13] = 0;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 1588));
    }
    v21 = VIRTUAL_MODULE::GlobalDoWork((__int64)v14, a2, v47);
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
      v23 = (__int64 (__fastcall **)(_QWORD))*v14;
      v37 = 5;
      v39 = 1;
      v40 = 5;
      v24 = (__int64 (__fastcall *)(_QWORD *))*v23;
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
0x18000ac10  mov     [rsp-8+arg_8], rbx
0x18000ac15  push    rbp
0x18000ac16  push    rsi
0x18000ac17  push    rdi
0x18000ac18  push    r12
0x18000ac1a  push    r13
0x18000ac1c  push    r14
0x18000ac1e  push    r15
0x18000ac20  lea     rbp, [rsp-50h]
0x18000ac25  sub     rsp, 150h
0x18000ac2c  mov     rax, cs:__security_cookie
0x18000ac33  xor     rax, rsp
0x18000ac36  mov     [rbp+80h+var_40], rax
0x18000ac3a  mov     r14, rcx
0x18000ac3d  mov     [rbp+80h+var_E8], r8
0x18000ac41  add     rcx, 230h
0x18000ac48  mov     r13d, edx
0x18000ac4b  xor     r12d, r12d
0x18000ac4e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ac55  nop     dword ptr [rax+rax+00h]
0x18000ac5a  mov     [rbp+80h+var_E0], rax
0x18000ac5e  cmp     r13d, 20h ; ' '
0x18000ac62  jnz     loc_18000B045
0x18000ac68  mov     eax, 5
0x18000ac6d  mov     ebx, [r14+rax*4+458h]
0x18000ac75  lea     rcx, [r14+420h]
0x18000ac7c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ac83  nop     dword ptr [rax+rax+00h]
0x18000ac88  lea     r15, [rax+rbx*4]
0x18000ac8c  cmp     r13d, 100h
0x18000ac93  jnz     short loc_18000AD14
0x18000ac95  mov     rcx, [rbp+80h+var_E8]
0x18000ac99  mov     rax, [rcx]
0x18000ac9c  mov     rax, [rax+8]
0x18000aca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca5  mov     rbx, rax
0x18000aca8  mov     rcx, rbx
0x18000acab  mov     rax, [rax]
0x18000acae  mov     rax, [rax+110h]
0x18000acb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acba  mov     rcx, rax
0x18000acbd  lea     rdx, [rbp+80h+var_D8]
0x18000acc1  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000acc8  xorps   xmm0, xmm0
0x18000accb  mov     [rbp+80h+var_D8], rax
0x18000accf  movdqu  [rbp+80h+var_D0], xmm0
0x18000acd4  mov     rax, [rcx]
0x18000acd7  mov     rax, [rax]
0x18000acda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acdf  test    eax, eax
0x18000ace1  js      short loc_18000AD44
0x18000ace3  cmp     dword ptr [rbp+80h+var_D0+4], 5
0x18000ace7  jb      short loc_18000AD44
0x18000ace9  cmp     dword ptr [rbp+80h+var_D0+8], r12d
0x18000aced  jz      short loc_18000AD44
0x18000acef  mov     rax, qword ptr [rbp+80h+var_D0]
0x18000acf3  cmp     eax, r13d
0x18000acf6  jz      short loc_18000ACFD
0x18000acf8  test    r13d, eax
0x18000acfb  jz      short loc_18000AD44
0x18000acfd  mov     rax, [rbx]
0x18000ad00  mov     rcx, rbx
0x18000ad03  mov     rax, [rax+110h]
0x18000ad0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad0f  mov     r12, rax
0x18000ad12  jmp     short loc_18000AD44
0x18000ad14  cmp     r13d, 1000h
0x18000ad1b  jnz     short loc_18000AD44
0x18000ad1d  lea     rcx, [r14+230h]
0x18000ad24  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ad2b  nop     dword ptr [rax+rax+00h]
0x18000ad30  mov     rdi, rax
0x18000ad33  mov     qword ptr [rbp+80h+FileTime1.dwLowDateTime], r12
0x18000ad37  cmp     [r14+630h], r12d
0x18000ad3e  jnz     loc_18000B2D5
0x18000ad44  mov     rsi, [rbp+80h+var_E0]
0x18000ad48  mov     eax, [r15]
0x18000ad4b  lea     r8, aModulename; "ModuleName"
0x18000ad52  lea     rdx, aContextid; "ContextId"
0x18000ad59  lea     r9, aPreBeginReques_1; "PRE_BEGIN_REQUEST_START"
0x18000ad60  lea     rcx, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000ad67  cmp     eax, 0FFFFFFFFh
0x18000ad6a  jz      loc_18000B058
0x18000ad70  mov     rdi, [rsi+rax*8]
0x18000ad74  test    r12, r12
0x18000ad77  jz      loc_18000AE66
0x18000ad7d  xor     eax, eax
0x18000ad7f  mov     [rsp+180h+var_140], rcx
0x18000ad84  mov     [rsp+180h+var_104], rax
0x18000ad89  xor     ebx, ebx
0x18000ad8b  mov     [rbp+80h+var_FC], eax
0x18000ad8e  xorps   xmm0, xmm0
0x18000ad91  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000ad98  mov     [rsp+180h+var_148], 100h
0x18000ada1  mov     [rsp+180h+var_150], rax
0x18000ada6  mov     rcx, rdi
0x18000ada9  mov     rax, [rdi]
0x18000adac  mov     [rsp+180h+var_138], 4
0x18000adb5  mov     [rsp+180h+var_130], r9
0x18000adba  mov     [rsp+180h+var_128], 1
0x18000adc2  mov     rax, [rax]
0x18000adc5  mov     [rsp+180h+var_124], 5
0x18000adcd  mov     [rsp+180h+var_108], 2
0x18000add5  movdqa  [rsp+180h+var_120], xmm0
0x18000addb  mov     [rsp+180h+var_110], ebx
0x18000addf  mov     [rsp+180h+var_10C], 1
0x18000ade7  mov     [rbp+80h+var_C0], rdx
0x18000adeb  mov     [rbp+80h+var_B8], 48h ; 'H'
0x18000adf2  mov     [rbp+80h+var_B0], rbx
0x18000adf6  mov     [rbp+80h+var_A8], 10h
0x18000adfd  mov     [rbp+80h+var_A0], rbx
0x18000ae01  mov     [rbp+80h+var_98], r8
0x18000ae05  mov     [rbp+80h+var_90], 1Fh
0x18000ae0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae11  mov     [rbp+80h+var_88], rax
0x18000ae15  mov     rcx, rax
0x18000ae18  test    rax, rax
0x18000ae1b  jz      loc_18000AFEF
0x18000ae21  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ae28  nop     dword ptr [rax+rax+00000000h]
0x18000ae30  cmp     [rcx+rax*2+2], bx
0x18000ae35  lea     rax, [rax+1]
0x18000ae39  jnz     short loc_18000AE30
0x18000ae3b  lea     eax, ds:2[rax*2]
0x18000ae42  mov     [rbp+80h+var_80], eax
0x18000ae45  lea     rdx, [rsp+180h+var_150]
0x18000ae4a  lea     rax, [rbp+80h+var_C0]
0x18000ae4e  mov     [rbp+80h+var_78], rbx
0x18000ae52  mov     [rbp+80h+var_104+4], rax
0x18000ae56  mov     rcx, r12
0x18000ae59  mov     rax, [r12]
0x18000ae5d  mov     rax, [rax+10h]
0x18000ae61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae66  cmp     r13d, 80h
0x18000ae6d  jnz     loc_18000B05C
0x18000ae73  lea     rcx, [r14+634h]
0x18000ae7a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ae81  nop     dword ptr [rax+rax+00h]
0x18000ae86  mov     rcx, [rdi+68h]
0x18000ae8a  test    rcx, rcx
0x18000ae8d  jnz     loc_18000B3A5
0x18000ae93  lea     rcx, [r14+634h]
0x18000ae9a  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000aea1  nop     dword ptr [rax+rax+00h]
0x18000aea6  mov     r8, [rbp+80h+var_E8]
0x18000aeaa  mov     edx, r13d
0x18000aead  mov     rcx, rdi
0x18000aeb0  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000aeb5  mov     ebx, eax
0x18000aeb7  test    r12, r12
0x18000aeba  jz      loc_18000AFE1
0x18000aec0  mov     [rsp+180h+var_160], eax
0x18000aec4  lea     rcx, aContextid; "ContextId"
0x18000aecb  xor     eax, eax
0x18000aecd  mov     [rbp+80h+var_C0], rcx
0x18000aed1  mov     [rsp+180h+var_104], rax
0x18000aed6  xorps   xmm0, xmm0
0x18000aed9  mov     [rbp+80h+var_FC], eax
0x18000aedc  mov     rcx, rdi
0x18000aedf  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000aee6  mov     [rsp+180h+var_148], 100h
0x18000aeef  mov     [rsp+180h+var_150], rax
0x18000aef4  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISRequestNotificationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISRequestNotificationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000aefb  mov     [rsp+180h+var_140], rax
0x18000af00  lea     rax, aPreBeginReques_0; "PRE_BEGIN_REQUEST_END"
0x18000af07  mov     [rsp+180h+var_130], rax
0x18000af0c  xor     eax, eax
0x18000af0e  mov     [rsp+180h+var_110], eax
0x18000af12  mov     [rbp+80h+var_B0], rax
0x18000af16  mov     [rbp+80h+var_A0], rax
0x18000af1a  lea     rax, aModulename; "ModuleName"
0x18000af21  mov     [rbp+80h+var_98], rax
0x18000af25  mov     rax, [rdi]
0x18000af28  mov     [rsp+180h+var_138], 5
0x18000af31  mov     [rsp+180h+var_128], 1
0x18000af39  mov     [rsp+180h+var_124], 5
0x18000af41  mov     rax, [rax]
0x18000af44  mov     [rsp+180h+var_108], 3
0x18000af4c  movdqa  [rsp+180h+var_120], xmm0
0x18000af52  mov     [rsp+180h+var_10C], 1
0x18000af5a  mov     [rbp+80h+var_B8], 48h ; 'H'
0x18000af61  mov     [rbp+80h+var_A8], 10h
0x18000af68  mov     [rbp+80h+var_90], 1Fh
0x18000af6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af74  mov     [rbp+80h+var_88], rax
0x18000af78  mov     rcx, rax
0x18000af7b  test    rax, rax
0x18000af7e  jnz     short loc_18000AFF6
0x18000af80  mov     [rbp+80h+var_80], eax
0x18000af83  lea     rax, aNotificationst; "NotificationStatus"
0x18000af8a  mov     [rbp+80h+var_70], rax
0x18000af8e  lea     rax, [rsp+180h+var_160]
0x18000af93  mov     [rbp+80h+var_60], rax
0x18000af97  mov     eax, [rsp+180h+var_160]
0x18000af9b  mov     [rbp+80h+var_78], 0
0x18000afa3  mov     [rbp+80h+var_68], 13h
0x18000afaa  mov     [rbp+80h+var_58], 4
0x18000afb1  test    eax, eax
0x18000afb3  jnz     loc_18000B3BE
0x18000afb9  lea     rax, aNotificationCo; "NOTIFICATION_CONTINUE"
0x18000afc0  mov     [rbp+80h+var_50], rax
0x18000afc4  lea     rdx, [rsp+180h+var_150]
0x18000afc9  lea     rax, [rbp+80h+var_C0]
0x18000afcd  mov     rcx, r12
0x18000afd0  mov     [rbp+80h+var_104+4], rax
0x18000afd4  mov     rax, [r12]
0x18000afd8  mov     rax, [rax+10h]
0x18000afdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe1  cmp     ebx, 1
0x18000afe4  jz      short loc_18000B018
0x18000afe6  add     r15, 4
0x18000afea  jmp     loc_18000AD48
0x18000afef  mov     eax, ebx
0x18000aff1  jmp     loc_18000AE42
0x18000aff6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000affd  nop     dword ptr [rax]
0x18000b000  cmp     word ptr [rcx+rax*2+2], 0
0x18000b006  lea     rax, [rax+1]
0x18000b00a  jnz     short loc_18000B000
0x18000b00c  lea     eax, ds:2[rax*2]
0x18000b013  jmp     loc_18000AF80
0x18000b018  mov     eax, 1
0x18000b01d  mov     rcx, [rbp+80h+var_40]
0x18000b021  xor     rcx, rsp; StackCookie
0x18000b024  call    __security_check_cookie
0x18000b029  mov     rbx, [rsp+180h+arg_8]
0x18000b031  add     rsp, 150h
0x18000b038  pop     r15
0x18000b03a  pop     r14
0x18000b03c  pop     r13
0x18000b03e  pop     r12
0x18000b040  pop     rdi
0x18000b041  pop     rsi
0x18000b042  pop     rbp
0x18000b043  retn
0x18000b045  cmp     r13d, 80h
0x18000b04c  jnz     short loc_18000B075
0x18000b04e  mov     eax, 7
0x18000b053  jmp     loc_18000AC6D
0x18000b058  xor     eax, eax
0x18000b05a  jmp     short loc_18000B01D
0x18000b05c  cmp     r13d, 2
0x18000b060  jz      loc_18000AE73
0x18000b066  cmp     r13d, 4
0x18000b06a  jnz     loc_18000AEA6
0x18000b070  jmp     loc_18000AE73
0x18000b075  cmp     r13d, 20000h
0x18000b07c  ja      loc_18000B1AE
0x18000b082  jz      loc_18000B1A4
0x18000b088  cmp     r13d, 200h
0x18000b08f  ja      loc_18000B115
0x18000b095  jz      short loc_18000B10B
0x18000b097  cmp     r13d, 8
0x18000b09b  ja      short loc_18000B0D4
0x18000b09d  jz      short loc_18000B0CA
0x18000b09f  mov     eax, r13d
0x18000b0a2  sub     eax, 1
0x18000b0a5  jz      loc_18000B2C4
0x18000b0ab  sub     eax, 1
0x18000b0ae  jz      short loc_18000B0C0
0x18000b0b0  cmp     eax, 2
0x18000b0b3  jnz     loc_18000B2C4
0x18000b0b9  mov     eax, eax
0x18000b0bb  jmp     loc_18000AC6D
0x18000b0c0  mov     eax, 1
0x18000b0c5  jmp     loc_18000AC6D
0x18000b0ca  mov     eax, 3
0x18000b0cf  jmp     loc_18000AC6D
0x18000b0d4  cmp     r13d, 10h
0x18000b0d8  jz      short loc_18000B101
0x18000b0da  cmp     r13d, 40h ; '@'
0x18000b0de  jz      short loc_18000B0F7
0x18000b0e0  cmp     r13d, 100h
0x18000b0e7  jnz     loc_18000B2C4
0x18000b0ed  mov     eax, 8
0x18000b0f2  jmp     loc_18000AC6D
0x18000b0f7  mov     eax, 6
0x18000b0fc  jmp     loc_18000AC6D
0x18000b101  mov     eax, 4
0x18000b106  jmp     loc_18000AC6D
0x18000b10b  mov     eax, 9
0x18000b110  jmp     loc_18000AC6D
0x18000b115  cmp     r13d, 2000h
0x18000b11c  ja      short loc_18000B167
0x18000b11e  jz      short loc_18000B15D
0x18000b120  cmp     r13d, 400h
0x18000b127  jz      short loc_18000B153
0x18000b129  cmp     r13d, 800h
0x18000b130  jz      short loc_18000B149
0x18000b132  cmp     r13d, 1000h
0x18000b139  jnz     loc_18000B2C4
0x18000b13f  mov     eax, 0Ch
0x18000b144  jmp     loc_18000AC6D
0x18000b149  mov     eax, 0Bh
0x18000b14e  jmp     loc_18000AC6D
0x18000b153  mov     eax, 0Ah
0x18000b158  jmp     loc_18000AC6D
0x18000b15d  mov     eax, 0Dh
0x18000b162  jmp     loc_18000AC6D
0x18000b167  cmp     r13d, 4000h
  ... truncated ...
```
