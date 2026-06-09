# DRMAcquireAdvisories

- ea: `0x18001a290`
- end: `0x18001a66c`
- name: `DRMAcquireAdvisories`
- size: `988`
- prototype: `HRESULT __stdcall(DRMHSESSION hLicenseStorage, PWSTR wszLicense, PWSTR wszURL, void *pvContext)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x18000442c`
- `0x1800046c8`
- `0x180019e28`
- `0x18001a1fc`
- `0x18001a290`
- `0x18001f8e0`
- `0x18001fa40`
- `0x18001fba0`
- `0x18001fbdc`
- `0x18001ff90`
- `0x1800205ec`
- `0x180022730`
- `0x18002348c`
- `0x18002398c`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18001a5ce`
- `msvcrt!_beginthreadex` at `0x18001a5ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a42a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a42a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a40d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5d9`

## string_xrefs

- `0x18001a2bc`: `[msdrm]:+DRMAcquireAdvisories wszURL=%S\n`
- `0x18001a646`: `[msdrm]:-DRMAcquireAdvisories HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMAcquireAdvisories(DRMHSESSION hLicenseStorage, PWSTR wszLicense, PWSTR wszURL, void *pvContext)
{
  DRMHSESSION v5; // esi
  __int64 v7; // r8
  __int64 v8; // r9
  CDRMReader *v9; // r15
  volatile signed __int32 *v10; // rdi
  unsigned __int16 *v11; // r14
  volatile signed __int32 *Pointer; // rax
  HRESULT LicenseFromChain; // ebx
  CHandleTable *v14; // rcx
  void *v15; // rbx
  CDRMCBase *DRMClient; // r12
  unsigned int v17; // edx
  CDRMCBase *v18; // rcx
  void *v19; // rdi
  __int64 v20; // rbx
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  unsigned __int16 *v22; // rbx
  unsigned __int16 **v23; // rax
  unsigned __int16 **v24; // rdi
  void **v25; // r14
  void **v26; // rsi
  int v27; // eax
  void *v28; // rcx
  void *v29; // rax
  signed int LastError; // eax
  unsigned int ThrdAddr; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  volatile signed __int32 *v34; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v35; // [rsp+48h] [rbp-18h]
  unsigned __int16 *v36; // [rsp+50h] [rbp-10h] BYREF

  v5 = hLicenseStorage;
  _RTLTRACE("[msdrm]:+DRMAcquireAdvisories wszURL=%S\n", wszURL);
  v9 = 0;
  v35 = 0;
  v10 = 0;
  v36 = 0;
  v11 = 0;
  ThrdAddr = 0;
  if ( !v5
    || wszLicense && !(unsigned __int8)DRMIsValidStringT<unsigned short>(wszLicense, 0, v7, v8)
    || wszURL && !(unsigned __int8)DRMIsValidStringT<unsigned short>(wszURL, 0, v7, v8)
    || !wszLicense && !wszURL )
  {
    LicenseFromChain = -2147024809;
    goto LABEL_68;
  }
  Pointer = (volatile signed __int32 *)DRMCInt::GetPointer(1u, v5);
  v34 = Pointer;
  if ( !Pointer )
    goto LABEL_9;
  v14 = (CHandleTable *)(unsigned int)(*Pointer - 2);
  if ( *Pointer == 2 )
  {
    Block = 0;
    if ( CHandleTable::Get(v14, v5, (struct DRMCInt **)&Block) >= 0 && (v19 = Block) != 0 )
    {
      if ( *(_DWORD *)Block == 2 )
      {
        v20 = *((_QWORD *)Block + 1);
        EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 88));
        v21 = (struct _RTL_CRITICAL_SECTION *)(v20 + 88);
        if ( *(_DWORD *)(v20 + 136) == -1 )
        {
          DRMClient = 0;
          LeaveCriticalSection(v21);
        }
        else
        {
          LeaveCriticalSection(v21);
          DRMClient = (CDRMCBase *)*((_QWORD *)v19 + 1);
        }
        v5 = hLicenseStorage;
      }
      else
      {
        DRMClient = 0;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 4, 0xFFFFFFFF) == 1 )
        operator delete(v19);
    }
    else
    {
      DRMClient = 0;
    }
    if ( DRMClient )
    {
      v17 = 2;
      v18 = DRMClient;
LABEL_21:
      if ( (unsigned int)CDRMCBase::IsThreadAlive(v18, v17) )
      {
        LicenseFromChain = -2147168456;
LABEL_24:
        v10 = v34;
        goto LABEL_68;
      }
      if ( wszLicense )
      {
        LicenseFromChain = CDRMCBase::GetLicenseFromChain(DRMClient, wszLicense, &v36);
        if ( (int)(LicenseFromChain + 0x80000000) >= 0 && LicenseFromChain != -2147168418 )
        {
          v11 = v36;
          goto LABEL_24;
        }
        v22 = v36;
        v35 = v36;
      }
      else
      {
        v22 = v35;
      }
      v23 = (unsigned __int16 **)operator new(0x48u);
      v24 = v23;
      if ( !v23 )
      {
        LicenseFromChain = -2147024882;
        goto LABEL_65;
      }
      *(_DWORD *)v23 = 0;
      v23[1] = 0;
      v23[4] = 0;
      v23[5] = 0;
      v23[6] = 0;
      *((_BYTE *)v23 + 56) = 1;
      v23[8] = 0;
      v23[2] = (unsigned __int16 *)CDRMClient::GetCallback(DRMClient);
      v25 = (void **)(v24 + 1);
      *(_DWORD *)v24 = v5;
      v24[3] = (unsigned __int16 *)pvContext;
      v26 = (void **)(v24 + 4);
      v24[1] = 0;
      v24[4] = 0;
      v24[5] = 0;
      v24[6] = 0;
      *((_BYTE *)v24 + 56) = v9 != 0;
      if ( !wszLicense )
        goto LABEL_74;
      if ( v22 )
        wszLicense = v22;
      LicenseFromChain = CDRMCBase::DuplicateStringEx(0, wszLicense, v24 + 1);
      if ( LicenseFromChain >= 0 )
      {
LABEL_74:
        if ( !wszURL
          || !*wszURL
          || (LicenseFromChain = CDRMCBase::DuplicateStringEx(0, wszURL, v24 + 4), LicenseFromChain >= 0) )
        {
          LicenseFromChain = GetThreadTermEvent(hLicenseStorage, 2 - (unsigned int)(v9 != 0), (void **)v24 + 8);
          if ( LicenseFromChain >= 0 )
          {
            v27 = v9 ? CDRMReader::DeleteRevocationListCache(v9) : CDRMClient::DeleteAllCache(DRMClient, 4u);
            LicenseFromChain = v27;
            if ( v27 >= 0 )
            {
              v29 = (void *)_beginthreadex(0, 0, AdvAcquisitionProc, v24, 0, &ThrdAddr);
              if ( v29 )
              {
                SetThreadInfo(hLicenseStorage, 2 - (v9 != 0), v29);
                goto LABEL_65;
              }
              LastError = GetLastError();
              LicenseFromChain = LastError;
              if ( LastError > 0 )
                LicenseFromChain = (unsigned __int16)LastError | 0x80070000;
              if ( LicenseFromChain >= 0 )
                LicenseFromChain = -2147467259;
            }
          }
        }
      }
      operator delete(*v25);
      v28 = *v26;
      *v25 = 0;
      operator delete(v28);
      *v26 = 0;
      operator delete(v24);
LABEL_65:
      v10 = v34;
      v11 = v35;
      goto LABEL_68;
    }
LABEL_23:
    LicenseFromChain = -2147024890;
    goto LABEL_24;
  }
  if ( *Pointer == 3 )
  {
    Block = 0;
    if ( CHandleTable::Get(v14, v5, (struct DRMCInt **)&Block) >= 0 )
    {
      v15 = Block;
      if ( Block )
      {
        if ( *(_DWORD *)Block == 3 && (int)CDRMReader::IsInitialized(*((CDRMReader **)Block + 1)) >= 0 )
          v9 = (CDRMReader *)*((_QWORD *)v15 + 1);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 4, 0xFFFFFFFF) == 1 )
          operator delete(v15);
        if ( v9 )
        {
          DRMClient = CDRMCBase::GetDRMClient(v9);
          v17 = 1;
          v18 = v9;
          goto LABEL_21;
        }
      }
    }
    goto LABEL_23;
  }
LABEL_9:
  LicenseFromChain = -2147024890;
  v10 = Pointer;
LABEL_68:
  operator delete(v11);
  if ( v10 && _InterlockedExchangeAdd(v10 + 4, 0xFFFFFFFF) == 1 )
    operator delete((void *)v10);
  _RTLTRACE("[msdrm]:-DRMAcquireAdvisories HR=%x\n", LicenseFromChain);
  return LicenseFromChain;
}

```

## disassembly

```asm
0x18001a290  mov     rax, rsp
0x18001a293  mov     [rax+10h], rbx
0x18001a297  mov     [rax+20h], r9
0x18001a29b  mov     [rax+18h], r8
0x18001a29f  mov     [rax+8], ecx
0x18001a2a2  push    rbp
0x18001a2a3  push    rsi
0x18001a2a4  push    rdi
0x18001a2a5  push    r12
0x18001a2a7  push    r13
0x18001a2a9  push    r14
0x18001a2ab  push    r15
0x18001a2ad  mov     rbp, rsp
0x18001a2b0  sub     rsp, 60h
0x18001a2b4  mov     r13, rdx
0x18001a2b7  mov     esi, ecx
0x18001a2b9  mov     rdx, r8
0x18001a2bc  lea     rcx, aMsdrmDrmacquir_0; "[msdrm]:+DRMAcquireAdvisories wszURL=%S"...
0x18001a2c3  mov     rbx, r8
0x18001a2c6  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001a2cb  xor     r15d, r15d
0x18001a2ce  mov     [rbp+var_18], r15
0x18001a2d2  mov     edi, r15d
0x18001a2d5  mov     [rbp+var_10], r15
0x18001a2d9  mov     r14d, r15d
0x18001a2dc  mov     [rbp+var_30], r15d
0x18001a2e0  test    esi, esi
0x18001a2e2  jz      loc_18001A61D
0x18001a2e8  test    r13, r13
0x18001a2eb  jz      short loc_18001A2FF
0x18001a2ed  xor     edx, edx
0x18001a2ef  mov     rcx, r13
0x18001a2f2  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001a2f7  test    al, al
0x18001a2f9  jz      loc_18001A61D
0x18001a2ff  test    rbx, rbx
0x18001a302  jz      short loc_18001A316
0x18001a304  xor     edx, edx
0x18001a306  mov     rcx, rbx
0x18001a309  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001a30e  test    al, al
0x18001a310  jz      loc_18001A61D
0x18001a316  test    r13, r13
0x18001a319  jnz     short loc_18001A324
0x18001a31b  test    rbx, rbx
0x18001a31e  jz      loc_18001A61D
0x18001a324  mov     edx, esi; unsigned int
0x18001a326  mov     ecx, 1; unsigned int
0x18001a32b  call    ?GetPointer@DRMCInt@@SAPEAXIK@Z; DRMCInt::GetPointer(uint,ulong)
0x18001a330  mov     [rbp+var_20], rax
0x18001a334  test    rax, rax
0x18001a337  jnz     short loc_18001A346
0x18001a339  mov     ebx, 80070006h
0x18001a33e  mov     rdi, rax
0x18001a341  jmp     loc_18001A622
0x18001a346  mov     ecx, [rax]
0x18001a348  sub     ecx, 2; this
0x18001a34b  jz      loc_18001A3D7
0x18001a351  cmp     ecx, 1
0x18001a354  jnz     short loc_18001A339
0x18001a356  lea     r8, [rbp+Block]; struct DRMCInt **
0x18001a35a  mov     [rbp+Block], r15
0x18001a35e  mov     edx, esi; unsigned int
0x18001a360  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001a365  test    eax, eax
0x18001a367  js      short loc_18001A3C9
0x18001a369  mov     rbx, [rbp+Block]
0x18001a36d  test    rbx, rbx
0x18001a370  jz      short loc_18001A3C9
0x18001a372  cmp     dword ptr [rbx], 3
0x18001a375  jnz     short loc_18001A388
0x18001a377  mov     rcx, [rbx+8]; this
0x18001a37b  call    ?IsInitialized@CDRMReader@@QEAAJXZ; CDRMReader::IsInitialized(void)
0x18001a380  test    eax, eax
0x18001a382  js      short loc_18001A388
0x18001a384  mov     r15, [rbx+8]
0x18001a388  or      eax, 0FFFFFFFFh
0x18001a38b  lock xadd [rbx+10h], eax
0x18001a390  cmp     eax, 1
0x18001a393  jnz     short loc_18001A39D
0x18001a395  mov     rcx, rbx; Block
0x18001a398  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a39d  test    r15, r15
0x18001a3a0  jz      short loc_18001A3C9
0x18001a3a2  mov     rcx, r15; this
0x18001a3a5  call    ?GetDRMClient@CDRMCBase@@QEAAPEAVCDRMClient@@XZ; CDRMCBase::GetDRMClient(void)
0x18001a3aa  mov     r12, rax
0x18001a3ad  mov     edx, 1; unsigned int
0x18001a3b2  mov     rcx, r15; this
0x18001a3b5  call    ?IsThreadAlive@CDRMCBase@@QEAAHI@Z; CDRMCBase::IsThreadAlive(uint)
0x18001a3ba  test    eax, eax
0x18001a3bc  jz      loc_18001A462
0x18001a3c2  mov     ebx, 8004CF38h
0x18001a3c7  jmp     short loc_18001A3CE
0x18001a3c9  mov     ebx, 80070006h
0x18001a3ce  mov     rdi, [rbp+var_20]
0x18001a3d2  jmp     loc_18001A622
0x18001a3d7  lea     r8, [rbp+Block]; struct DRMCInt **
0x18001a3db  mov     [rbp+Block], r15
0x18001a3df  mov     edx, esi; unsigned int
0x18001a3e1  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001a3e6  test    eax, eax
0x18001a3e8  jns     short loc_18001A3EF
0x18001a3ea  mov     r12, r15
0x18001a3ed  jmp     short loc_18001A44C
0x18001a3ef  mov     rdi, [rbp+Block]
0x18001a3f3  test    rdi, rdi
0x18001a3f6  jz      short loc_18001A3EA
0x18001a3f8  cmp     dword ptr [rdi], 2
0x18001a3fb  jz      short loc_18001A402
0x18001a3fd  mov     r12, r15
0x18001a400  jmp     short loc_18001A437
0x18001a402  mov     rbx, [rdi+8]
0x18001a406  lea     rsi, [rbx+58h]
0x18001a40a  mov     rcx, rsi; lpCriticalSection
0x18001a40d  call    cs:__imp_EnterCriticalSection
0x18001a413  cmp     dword ptr [rbx+88h], 0FFFFFFFFh
0x18001a41a  mov     rcx, rsi; lpCriticalSection
0x18001a41d  jnz     short loc_18001A42A
0x18001a41f  mov     r12, r15
0x18001a422  call    cs:__imp_LeaveCriticalSection
0x18001a428  jmp     short loc_18001A434
0x18001a42a  call    cs:__imp_LeaveCriticalSection
0x18001a430  mov     r12, [rdi+8]
0x18001a434  mov     esi, [rbp+arg_0]
0x18001a437  or      eax, 0FFFFFFFFh
0x18001a43a  lock xadd [rdi+10h], eax
0x18001a43f  cmp     eax, 1
0x18001a442  jnz     short loc_18001A44C
0x18001a444  mov     rcx, rdi; Block
0x18001a447  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a44c  test    r12, r12
0x18001a44f  jz      loc_18001A3C9
0x18001a455  mov     edx, 2
0x18001a45a  mov     rcx, r12
0x18001a45d  jmp     loc_18001A3B5
0x18001a462  test    r13, r13
0x18001a465  jz      short loc_18001A49F
0x18001a467  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18001a46b  mov     rdx, r13; unsigned __int16 *
0x18001a46e  mov     rcx, r12; this
0x18001a471  call    ?GetLicenseFromChain@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::GetLicenseFromChain(ushort *,ushort * *)
0x18001a476  mov     ebx, eax
0x18001a478  mov     eax, 80000000h
0x18001a47d  lea     ecx, [rbx+rax]
0x18001a480  test    eax, ecx
0x18001a482  jnz     short loc_18001A495
0x18001a484  cmp     ebx, 8004CF5Eh
0x18001a48a  jz      short loc_18001A495
0x18001a48c  mov     r14, [rbp+var_10]
0x18001a490  jmp     loc_18001A3CE
0x18001a495  mov     rbx, [rbp+var_10]
0x18001a499  mov     [rbp+var_18], rbx
0x18001a49d  jmp     short loc_18001A4A3
0x18001a49f  mov     rbx, [rbp+var_18]
0x18001a4a3  mov     ecx, 48h ; 'H'; Size
0x18001a4a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a4ad  mov     rdi, rax
0x18001a4b0  test    rax, rax
0x18001a4b3  jz      loc_18001A616
0x18001a4b9  mov     rcx, r12; this
0x18001a4bc  mov     [rax], r14d
0x18001a4bf  mov     [rax+8], r14
0x18001a4c3  mov     [rax+20h], r14
0x18001a4c7  mov     [rax+28h], r14
0x18001a4cb  mov     [rax+30h], r14
0x18001a4cf  mov     byte ptr [rax+38h], 1
0x18001a4d3  mov     [rax+40h], r14
0x18001a4d7  call    ?GetCallback@CDRMClient@@QEAAP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZXZ; CDRMClient::GetCallback(void)
0x18001a4dc  xor     ecx, ecx; this
0x18001a4de  mov     [rdi+10h], rax
0x18001a4e2  mov     rax, [rbp+arg_18]
0x18001a4e6  lea     r14, [rdi+8]
0x18001a4ea  test    r15, r15
0x18001a4ed  mov     [rdi], esi
0x18001a4ef  mov     [rdi+18h], rax
0x18001a4f3  lea     rsi, [rdi+20h]
0x18001a4f7  setnz   al
0x18001a4fa  mov     [r14], rcx
0x18001a4fd  mov     [rsi], rcx
0x18001a500  mov     [rdi+28h], rcx
0x18001a504  mov     [rdi+30h], rcx
0x18001a508  mov     [rdi+38h], al
0x18001a50b  test    r13, r13
0x18001a50e  jz      short loc_18001A52A
0x18001a510  test    rbx, rbx
0x18001a513  mov     r8, r14; unsigned __int16 **
0x18001a516  cmovnz  r13, rbx
0x18001a51a  mov     rdx, r13; unsigned __int16 *
0x18001a51d  call    ?DuplicateStringEx@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::DuplicateStringEx(ushort *,ushort * *)
0x18001a522  xor     ecx, ecx; this
0x18001a524  mov     ebx, eax
0x18001a526  test    eax, eax
0x18001a528  js      short loc_18001A578
0x18001a52a  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18001a52e  test    rdx, rdx
0x18001a531  jz      short loc_18001A546
0x18001a533  cmp     [rdx], cx
0x18001a536  jz      short loc_18001A546
0x18001a538  mov     r8, rsi; unsigned __int16 **
0x18001a53b  call    ?DuplicateStringEx@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::DuplicateStringEx(ushort *,ushort * *)
0x18001a540  mov     ebx, eax
0x18001a542  test    eax, eax
0x18001a544  js      short loc_18001A578
0x18001a546  mov     ecx, [rbp+arg_0]; unsigned int
0x18001a549  lea     r8, [rdi+40h]; void **
0x18001a54d  mov     rax, r15
0x18001a550  neg     rax
0x18001a553  sbb     r13d, r13d
0x18001a556  lea     edx, [r13+2]; unsigned int
0x18001a55a  call    ?GetThreadTermEvent@@YAJKIPEAPEAX@Z; GetThreadTermEvent(ulong,uint,void * *)
0x18001a55f  mov     ebx, eax
0x18001a561  test    eax, eax
0x18001a563  js      short loc_18001A578
0x18001a565  test    r15, r15
0x18001a568  jz      short loc_18001A5A0
0x18001a56a  mov     rcx, r15; this
0x18001a56d  call    ?DeleteRevocationListCache@CDRMReader@@QEAAJXZ; CDRMReader::DeleteRevocationListCache(void)
0x18001a572  mov     ebx, eax
0x18001a574  test    eax, eax
0x18001a576  jns     short loc_18001A5AF
0x18001a578  mov     rcx, [r14]; Block
0x18001a57b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a580  mov     rcx, [rsi]; Block
0x18001a583  mov     qword ptr [r14], 0
0x18001a58a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a58f  mov     rcx, rdi; Block
0x18001a592  mov     qword ptr [rsi], 0
0x18001a599  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a59e  jmp     short loc_18001A60C
0x18001a5a0  mov     edx, 4; unsigned int
0x18001a5a5  mov     rcx, r12; this
0x18001a5a8  call    ?DeleteAllCache@CDRMClient@@QEAAJI@Z; CDRMClient::DeleteAllCache(uint)
0x18001a5ad  jmp     short loc_18001A572
0x18001a5af  lea     rax, [rbp+var_30]
0x18001a5b3  mov     r9, rdi; ArgList
0x18001a5b6  mov     [rsp+60h+ThrdAddr], rax; ThrdAddr
0x18001a5bb  lea     r8, ?AdvAcquisitionProc@@YAIPEAX@Z; StartAddress
0x18001a5c2  xor     edx, edx; StackSize
0x18001a5c4  mov     [rsp+60h+InitFlag], 0; InitFlag
0x18001a5cc  xor     ecx, ecx; Security
0x18001a5ce  call    cs:__imp__beginthreadex
0x18001a5d4  test    rax, rax
0x18001a5d7  jnz     short loc_18001A5FD
0x18001a5d9  call    cs:__imp_GetLastError
0x18001a5df  mov     ebx, eax
0x18001a5e1  test    eax, eax
0x18001a5e3  jle     short loc_18001A5EE
0x18001a5e5  movzx   ebx, ax
0x18001a5e8  or      ebx, 80070000h
0x18001a5ee  test    ebx, ebx
0x18001a5f0  mov     eax, 80004005h
0x18001a5f5  cmovns  ebx, eax
0x18001a5f8  jmp     loc_18001A578
0x18001a5fd  mov     ecx, [rbp+arg_0]; unsigned int
0x18001a600  lea     edx, [r13+2]; unsigned int
0x18001a604  mov     r8, rax; void *
0x18001a607  call    ?SetThreadInfo@@YAJKIPEAX@Z; SetThreadInfo(ulong,uint,void *)
0x18001a60c  mov     rdi, [rbp+var_20]
0x18001a610  mov     r14, [rbp+var_18]
0x18001a614  jmp     short loc_18001A622
0x18001a616  mov     ebx, 8007000Eh
0x18001a61b  jmp     short loc_18001A60C
0x18001a61d  mov     ebx, 80070057h
0x18001a622  mov     rcx, r14; Block
0x18001a625  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a62a  test    rdi, rdi
0x18001a62d  jz      short loc_18001A644
0x18001a62f  or      eax, 0FFFFFFFFh
0x18001a632  lock xadd [rdi+10h], eax
0x18001a637  cmp     eax, 1
0x18001a63a  jnz     short loc_18001A644
0x18001a63c  mov     rcx, rdi; Block
0x18001a63f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a644  mov     edx, ebx
0x18001a646  lea     rcx, aMsdrmDrmacquir; "[msdrm]:-DRMAcquireAdvisories HR=%x\n"
0x18001a64d  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001a652  mov     eax, ebx
0x18001a654  mov     rbx, [rsp+60h+arg_8]
0x18001a65c  add     rsp, 60h
0x18001a660  pop     r15
0x18001a662  pop     r14
0x18001a664  pop     r13
0x18001a666  pop     r12
0x18001a668  pop     rdi
0x18001a669  pop     rsi
0x18001a66a  pop     rbp
0x18001a66b  retn
```
