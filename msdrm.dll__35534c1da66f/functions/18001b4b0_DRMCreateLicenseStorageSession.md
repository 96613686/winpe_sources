# DRMCreateLicenseStorageSession

- ea: `0x18001b4b0`
- end: `0x18001b773`
- name: `DRMCreateLicenseStorageSession`
- size: `707`
- prototype: `HRESULT __stdcall(DRMENVHANDLE hEnv, DRMHANDLE hDefaultLibrary, DRMHSESSION hClient, UINT uFlags, PWSTR wszIssuanceLicense, DRMHSESSION *phLicenseStorage)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18005a044`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x180004328`
- `0x1800046c8`
- `0x18001b4b0`
- `0x18001eb48`
- `0x18001ef30`
- `0x18001fa40`
- `0x18002325c`
- `0x1800239dc`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b561`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b70f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b561`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b70f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b54d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b66d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b54d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b66d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6f9`

## string_xrefs

- `0x18001b4c7`: `[msdrm]:+DRMCreateLicenseStorageSession\n`
- `0x18001b754`: `[msdrm]:-DRMCreateLicenseStorageSession HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMCreateLicenseStorageSession(
        DRMENVHANDLE hEnv,
        DRMHANDLE hDefaultLibrary,
        DRMHSESSION hClient,
        UINT uFlags,
        PWSTR wszIssuanceLicense,
        DRMHSESSION *phLicenseStorage)
{
  __int64 v10; // r8
  __int64 v11; // r9
  CHandleTable *v12; // rcx
  DRMHSESSION *v13; // r14
  void *v14; // rdi
  CDRMCBase *v15; // rbp
  __int64 v16; // rbx
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  CDRMCBase *v18; // rax
  CDRMCBase *v19; // rbx
  HRESULT ReaderEvents; // edi
  unsigned int v21; // ebp
  void *Block; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+18h] BYREF

  _RTLTRACE("[msdrm]:+DRMCreateLicenseStorageSession\n");
  v24 = 0;
  if ( hClient
    && (unsigned __int8)DRMIsValidStringT<unsigned short>(wszIssuanceLicense, 0, v10, v11)
    && (v13 = phLicenseStorage) != 0 )
  {
    Block = 0;
    if ( CHandleTable::Get(v12, hClient, (struct DRMCInt **)&Block) < 0 )
      goto LABEL_21;
    v14 = Block;
    if ( !Block )
      goto LABEL_21;
    if ( *(_DWORD *)Block == 2 )
    {
      v16 = *((_QWORD *)Block + 1);
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 88));
      v17 = (struct _RTL_CRITICAL_SECTION *)(v16 + 88);
      if ( *(_DWORD *)(v16 + 136) == -1 )
      {
        v15 = 0;
        LeaveCriticalSection(v17);
      }
      else
      {
        LeaveCriticalSection(v17);
        v15 = (CDRMCBase *)*((_QWORD *)v14 + 1);
      }
    }
    else
    {
      v15 = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 4, 0xFFFFFFFF) == 1 )
      operator delete(v14);
    if ( v15 )
    {
      v18 = (CDRMCBase *)operator new(0x140u);
      v19 = v18;
      if ( v18 )
      {
        CDRMCBase::CDRMCBase(v18);
        *((_QWORD *)v19 + 19) = 0;
        *((_QWORD *)v19 + 20) = 0;
        *((_DWORD *)v19 + 42) = 0;
        *((_QWORD *)v19 + 22) = 0;
        *((_QWORD *)v19 + 23) = 0;
        *((_QWORD *)v19 + 24) = 0;
        *((_QWORD *)v19 + 25) = 0;
        *((_QWORD *)v19 + 26) = 0;
        *((_QWORD *)v19 + 27) = 0;
        *((_QWORD *)v19 + 31) = 0;
        *((_DWORD *)v19 + 64) = 0;
        *((_QWORD *)v19 + 33) = 0;
        *((_QWORD *)v19 + 34) = 0;
        *((_QWORD *)v19 + 35) = 0;
        *((_DWORD *)v19 + 72) = 0;
        *((_QWORD *)v19 + 37) = 0;
        *((_QWORD *)v19 + 38) = 0;
        *((_QWORD *)v19 + 28) = 0;
        *((_QWORD *)v19 + 29) = 0;
        *((_DWORD *)v19 + 60) = 0;
        *((_DWORD *)v19 + 34) = 0;
        *((_QWORD *)v19 + 18) = 0;
        *(_QWORD *)v19 = &CDRMReader::`vftable';
        *((_QWORD *)v19 + 16) = 0;
        *((_QWORD *)v19 + 39) = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88));
        *((_QWORD *)v19 + 2) = v15;
        CDRMCBase::AddRef(v15);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88));
        ReaderEvents = CDRMReader::SetAssetHeader(v19, wszIssuanceLicense);
        if ( ReaderEvents < 0 )
          goto LABEL_19;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88));
        *((_DWORD *)v19 + 42) = uFlags;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88));
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88));
        *((_DWORD *)v19 + 33) = hEnv;
        *((_DWORD *)v19 + 34) = hDefaultLibrary;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88));
        ReaderEvents = DRMCInt::CreateHandle(3u, v19, &v24);
        if ( ReaderEvents < 0
          || (EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88)),
              v21 = v24,
              *((_DWORD *)v19 + 32) = v24,
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 88)),
              ReaderEvents = CDRMReader::CreateReaderEvents(v19, v21),
              ReaderEvents < 0) )
        {
LABEL_19:
          (**(void (__fastcall ***)(CDRMCBase *, __int64))v19)(v19, 1);
        }
        else
        {
          *v13 = v21;
        }
      }
      else
      {
        ReaderEvents = -2147024882;
      }
    }
    else
    {
LABEL_21:
      ReaderEvents = -2147024890;
    }
  }
  else
  {
    ReaderEvents = -2147024809;
  }
  _RTLTRACE("[msdrm]:-DRMCreateLicenseStorageSession HR=%x\n", ReaderEvents);
  return ReaderEvents;
}

```

## disassembly

```asm
0x18001b4b0  push    rbx
0x18001b4b2  push    rbp
0x18001b4b3  push    rsi
0x18001b4b4  push    rdi
0x18001b4b5  push    r12
0x18001b4b7  push    r13
0x18001b4b9  push    r14
0x18001b4bb  push    r15
0x18001b4bd  sub     rsp, 38h
0x18001b4c1  mov     r13d, ecx
0x18001b4c4  mov     r15d, r9d
0x18001b4c7  lea     rcx, aMsdrmDrmcreate_7; "[msdrm]:+DRMCreateLicenseStorageSession"...
0x18001b4ce  mov     ebx, r8d
0x18001b4d1  mov     r12d, edx
0x18001b4d4  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001b4d9  xor     esi, esi
0x18001b4db  mov     [rsp+78h+arg_10], esi
0x18001b4e2  test    ebx, ebx
0x18001b4e4  jz      loc_18001B74D
0x18001b4ea  mov     rcx, [rsp+78h+wszIssuanceLicense]
0x18001b4f2  xor     edx, edx
0x18001b4f4  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001b4f9  test    al, al
0x18001b4fb  jz      loc_18001B74D
0x18001b501  mov     r14, [rsp+78h+phLicenseStorage]
0x18001b509  test    r14, r14
0x18001b50c  jz      loc_18001B74D
0x18001b512  lea     r8, [rsp+78h+Block]; struct DRMCInt **
0x18001b517  mov     [rsp+78h+Block], rsi
0x18001b51c  mov     edx, ebx; unsigned int
0x18001b51e  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001b523  test    eax, eax
0x18001b525  js      loc_18001B746
0x18001b52b  mov     rdi, [rsp+78h+Block]
0x18001b530  test    rdi, rdi
0x18001b533  jz      loc_18001B746
0x18001b539  cmp     dword ptr [rdi], 2
0x18001b53c  jz      short loc_18001B542
0x18001b53e  mov     ebp, esi
0x18001b540  jmp     short loc_18001B575
0x18001b542  mov     rbx, [rdi+8]
0x18001b546  lea     rsi, [rbx+58h]
0x18001b54a  mov     rcx, rsi; lpCriticalSection
0x18001b54d  call    cs:__imp_EnterCriticalSection
0x18001b553  cmp     dword ptr [rbx+88h], 0FFFFFFFFh
0x18001b55a  mov     rcx, rsi; lpCriticalSection
0x18001b55d  jnz     short loc_18001B569
0x18001b55f  xor     ebp, ebp
0x18001b561  call    cs:__imp_LeaveCriticalSection
0x18001b567  jmp     short loc_18001B573
0x18001b569  call    cs:__imp_LeaveCriticalSection
0x18001b56f  mov     rbp, [rdi+8]
0x18001b573  xor     esi, esi
0x18001b575  or      eax, 0FFFFFFFFh
0x18001b578  lock xadd [rdi+10h], eax
0x18001b57d  cmp     eax, 1
0x18001b580  jnz     short loc_18001B58A
0x18001b582  mov     rcx, rdi; Block
0x18001b585  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b58a  test    rbp, rbp
0x18001b58d  jz      loc_18001B746
0x18001b593  mov     ecx, 140h; Size
0x18001b598  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b59d  mov     rbx, rax
0x18001b5a0  test    rax, rax
0x18001b5a3  jz      loc_18001B73F
0x18001b5a9  mov     rcx, rax; this
0x18001b5ac  call    ??0CDRMCBase@@QEAA@XZ; CDRMCBase::CDRMCBase(void)
0x18001b5b1  mov     [rbx+98h], rsi
0x18001b5b8  lea     rax, ??_7CDRMReader@@6B@; const CDRMReader::`vftable'
0x18001b5bf  mov     [rbx+0A0h], rsi
0x18001b5c6  mov     [rbx+0A8h], esi
0x18001b5cc  mov     [rbx+0B0h], rsi
0x18001b5d3  mov     [rbx+0B8h], rsi
0x18001b5da  mov     [rbx+0C0h], rsi
0x18001b5e1  mov     [rbx+0C8h], rsi
0x18001b5e8  mov     [rbx+0D0h], rsi
0x18001b5ef  mov     [rbx+0D8h], rsi
0x18001b5f6  mov     [rbx+0F8h], rsi
0x18001b5fd  mov     [rbx+100h], esi
0x18001b603  mov     [rbx+108h], rsi
0x18001b60a  mov     [rbx+110h], rsi
0x18001b611  mov     [rbx+118h], rsi
0x18001b618  mov     [rbx+120h], esi
0x18001b61e  mov     [rbx+128h], rsi
0x18001b625  mov     [rbx+130h], rsi
0x18001b62c  mov     [rbx+0E0h], rsi
0x18001b633  mov     [rbx+0E8h], rsi
0x18001b63a  mov     [rbx+0F0h], esi
0x18001b640  mov     [rbx+88h], esi
0x18001b646  mov     [rbx+90h], rsi
0x18001b64d  lea     rsi, [rbx+58h]
0x18001b651  mov     rcx, rsi; lpCriticalSection
0x18001b654  mov     [rbx], rax
0x18001b657  mov     qword ptr [rbx+80h], 0
0x18001b662  mov     qword ptr [rbx+138h], 0
0x18001b66d  call    cs:__imp_EnterCriticalSection
0x18001b673  mov     rcx, rbp; this
0x18001b676  mov     [rbx+10h], rbp
0x18001b67a  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18001b67f  mov     rcx, rsi; lpCriticalSection
0x18001b682  call    cs:__imp_LeaveCriticalSection
0x18001b688  mov     rdx, [rsp+78h+wszIssuanceLicense]; unsigned __int16 *
0x18001b690  mov     rcx, rbx; this
0x18001b693  call    ?SetAssetHeader@CDRMReader@@QEAAJPEAG@Z; CDRMReader::SetAssetHeader(ushort *)
0x18001b698  mov     edi, eax
0x18001b69a  test    eax, eax
0x18001b69c  js      loc_18001B72A
0x18001b6a2  mov     rcx, rsi; lpCriticalSection
0x18001b6a5  call    cs:__imp_EnterCriticalSection
0x18001b6ab  mov     rcx, rsi; lpCriticalSection
0x18001b6ae  mov     [rbx+0A8h], r15d
0x18001b6b5  call    cs:__imp_LeaveCriticalSection
0x18001b6bb  mov     rcx, rsi; lpCriticalSection
0x18001b6be  call    cs:__imp_EnterCriticalSection
0x18001b6c4  mov     rcx, rsi; lpCriticalSection
0x18001b6c7  mov     [rbx+84h], r13d
0x18001b6ce  mov     [rbx+88h], r12d
0x18001b6d5  call    cs:__imp_LeaveCriticalSection
0x18001b6db  lea     r8, [rsp+78h+arg_10]; unsigned int *
0x18001b6e3  mov     rdx, rbx; void *
0x18001b6e6  mov     ecx, 3; unsigned int
0x18001b6eb  call    ?CreateHandle@DRMCInt@@SAJIPEAXPEAK@Z; DRMCInt::CreateHandle(uint,void *,ulong *)
0x18001b6f0  mov     edi, eax
0x18001b6f2  test    eax, eax
0x18001b6f4  js      short loc_18001B72A
0x18001b6f6  mov     rcx, rsi; lpCriticalSection
0x18001b6f9  call    cs:__imp_EnterCriticalSection
0x18001b6ff  mov     ebp, [rsp+78h+arg_10]
0x18001b706  mov     rcx, rsi; lpCriticalSection
0x18001b709  mov     [rbx+80h], ebp
0x18001b70f  call    cs:__imp_LeaveCriticalSection
0x18001b715  mov     edx, ebp; unsigned int
0x18001b717  mov     rcx, rbx; this
0x18001b71a  call    ?CreateReaderEvents@CDRMReader@@QEAAJK@Z; CDRMReader::CreateReaderEvents(ulong)
0x18001b71f  mov     edi, eax
0x18001b721  test    eax, eax
0x18001b723  js      short loc_18001B72A
0x18001b725  mov     [r14], ebp
0x18001b728  jmp     short loc_18001B752
0x18001b72a  mov     rax, [rbx]
0x18001b72d  mov     edx, 1
0x18001b732  mov     rcx, rbx
0x18001b735  mov     rax, [rax]
0x18001b738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b73d  jmp     short loc_18001B752
0x18001b73f  mov     edi, 8007000Eh
0x18001b744  jmp     short loc_18001B752
0x18001b746  mov     edi, 80070006h
0x18001b74b  jmp     short loc_18001B752
0x18001b74d  mov     edi, 80070057h
0x18001b752  mov     edx, edi
0x18001b754  lea     rcx, aMsdrmDrmcreate_3; "[msdrm]:-DRMCreateLicenseStorageSession"...
0x18001b75b  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001b760  mov     eax, edi
0x18001b762  add     rsp, 38h
0x18001b766  pop     r15
0x18001b768  pop     r14
0x18001b76a  pop     r13
0x18001b76c  pop     r12
0x18001b76e  pop     rdi
0x18001b76f  pop     rsi
0x18001b770  pop     rbp
0x18001b771  pop     rbx
0x18001b772  retn
```
