# Activate(ulong,long (*)(_DRM_STATUS_MSG,long,void *,void *),uint,ushort *,ushort *,ushort *,uint,void *,HWND__ *,uint)

- ea: `0x18002b454`
- end: `0x18002bcbc`
- name: `?Activate@@YAJKP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZIPEAG33I1PEAUHWND__@@I@Z`
- size: `2152`
- prototype: `__int64 __fastcall(unsigned int, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), unsigned int, unsigned __int16 *, unsigned __int16 *, wchar_t *String1, unsigned int, void *, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ad10`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x18000420c`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180019e28`
- `0x18001a1fc`
- `0x18002b454`
- `0x18002d044`
- `0x180037b58`
- `0x1800385a0`
- `0x18005bd8a`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18002bb48`
- `msvcrt!_beginthreadex` at `0x18002bb48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b65a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b65a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b672`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b736`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b672`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b736`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b667`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc57`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=3
__int64 __fastcall Activate(
        unsigned int a1,
        int (*a2)(enum _DRM_STATUS_MSG, int, void *, void *),
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        wchar_t *String1,
        unsigned int a7,
        void *a8,
        HWND a9,
        unsigned int a10)
{
  void *v11; // r12
  void **v12; // rsi
  void *v13; // r13
  void *v14; // r15
  signed int ThreadTermEvent; // ebx
  const unsigned __int16 *v16; // r9
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rax
  unsigned __int64 v19; // r8
  signed __int64 v20; // rbx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  DRMOS *v23; // rcx
  void *v24; // rax
  HANDLE v25; // rbx
  DRMOS *v26; // rcx
  const unsigned __int16 *v27; // r9
  unsigned int v28; // eax
  HANDLE v29; // rax
  struct _SECURITY_ATTRIBUTES *v30; // rdx
  HANDLE v31; // rax
  HANDLE v32; // r13
  signed int LastError; // eax
  void **v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rax
  void **v37; // r13
  unsigned __int64 v38; // r8
  signed __int64 v39; // rbx
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rcx
  unsigned __int16 *v43; // rax
  unsigned __int16 *v44; // rax
  __int64 v45; // rdx
  unsigned __int64 v46; // r8
  signed __int64 v47; // rbx
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  __int64 v52; // rcx
  unsigned __int16 *v53; // rax
  unsigned __int64 v54; // rdx
  signed __int64 v55; // rbx
  unsigned __int64 v56; // rcx
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rcx
  unsigned __int16 *v59; // rax
  unsigned int v60; // ecx
  bool v61; // zf
  char v62; // al
  unsigned int (__stdcall *v63)(void *); // r8
  signed int v64; // eax
  void *v65; // rcx
  void *v66; // rcx
  HANDLE v68; // [rsp+30h] [rbp-98h]
  HANDLE v69; // [rsp+38h] [rbp-90h]
  unsigned int ThrdAddr; // [rsp+44h] [rbp-84h] BYREF
  void **v71; // [rsp+48h] [rbp-80h]
  void **v72; // [rsp+50h] [rbp-78h]
  void *Block; // [rsp+68h] [rbp-60h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+70h] [rbp-58h] BYREF
  __int64 v75; // [rsp+88h] [rbp-40h]

  v75 = -2;
  ThrdAddr = 0;
  v11 = 0;
  v12 = 0;
  Block = 0;
  v13 = 0;
  v14 = 0;
  v69 = 0;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  EventAttributes.lpSecurityDescriptor = 0;
  if ( (a7 & 1) == 0 && (a7 & 0xA) == 0 )
  {
    ThreadTermEvent = -2147024809;
    goto LABEL_140;
  }
  if ( ((a7 & 2) != 0 || String1) && !(unsigned __int8)DRMIsValidStringT<unsigned short>(String1, 0, a3, a4)
    || a5 && !(unsigned __int8)DRMIsValidStringT<unsigned short>(a5, 0, a3, a4)
    || a4 && !(unsigned __int8)DRMIsValidStringT<unsigned short>(a4, 0, a3, a4) )
  {
    ThreadTermEvent = -2147024809;
    goto LABEL_119;
  }
  _RTLTRACE("[msdrm]:wszServer = %S,wszUserID = %S,wszUserType = %S ", a4, a5, String1);
  v17 = 0x7FFFFFFF;
  v18 = L"UDRMActivation_";
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  ThreadTermEvent = v17 == 0 ? 0x80070057 : 0;
  v19 = (0x7FFFFFFF - v17) & -(__int64)(v17 != 0);
  if ( !v17 )
  {
    v14 = 0;
    goto LABEL_140;
  }
  v20 = v19 + 1;
  if ( v19 + 1 < v19 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v17);
  v21 = HIDWORD(v20);
  if ( v20 < 0 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v21);
  v22 = 2LL * (unsigned int)v20;
  v23 = (DRMOS *)(v21 << 33);
  if ( (unsigned __int64)v23 + v22 < v22 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v23);
  if ( (DRMOS *)((char *)v23 + v22) )
  {
    v24 = operator new[](saturated_mul(v20, 2u));
    Block = v24;
    if ( !v24 )
    {
      ThreadTermEvent = -2147024882;
      v14 = 0;
      goto LABEL_140;
    }
    ThreadTermEvent = StringCchCopyW((unsigned __int16 *)v24, v20, L"UDRMActivation_");
    if ( ThreadTermEvent < 0 )
    {
      v14 = 0;
      goto LABEL_140;
    }
  }
  v25 = DRMOS::OpenEventA(v23, 1, (DRMOS *)Block, v16);
  v68 = v25;
  if ( !v25 )
  {
    ThreadTermEvent = -2147024809;
    v13 = 0;
LABEL_119:
    v14 = 0;
    goto LABEL_140;
  }
  if ( (a7 & 8) != 0 )
  {
    SetEvent(v25);
    ThreadTermEvent = 0;
    Sleep(0x64u);
    v14 = 0;
LABEL_37:
    v13 = v68;
    goto LABEL_140;
  }
  ResetEvent(v25);
  v28 = a7 & 1;
  if ( (a7 & 1) != 0 )
  {
    v29 = DRMOS::OpenEventA(v26, 1, (DRMOS *)L"UDRMActivation_Machine", v27);
    if ( v29 )
    {
      ThreadTermEvent = -2147168456;
      v14 = v29;
      goto LABEL_37;
    }
    v31 = DRMOS::CreateEventA(&EventAttributes, v30, 0, (DRMOS *)L"UDRMActivation_Machine");
    v32 = v31;
    v69 = v31;
    if ( !v31 )
    {
      LastError = GetLastError();
      ThreadTermEvent = LastError;
      if ( LastError > 0 )
        ThreadTermEvent = (unsigned __int16)LastError | 0x80070000;
      if ( ThreadTermEvent >= 0 )
        ThreadTermEvent = -2147467259;
      goto LABEL_36;
    }
    ResetEvent(v31);
    v28 = a7 & 1;
  }
  else
  {
    v32 = 0;
  }
  if ( (a7 & 2) != 0 && !v28 )
  {
    ThreadTermEvent = IsActivated(0, 1u);
    if ( ThreadTermEvent < 0 )
    {
LABEL_36:
      v14 = v69;
      goto LABEL_37;
    }
    v25 = v68;
  }
  v34 = (void **)operator new(0x58u);
  v12 = v34;
  v71 = v34;
  if ( !v34 )
  {
    v12 = 0;
    ThreadTermEvent = -2147024882;
    goto LABEL_36;
  }
  *(_DWORD *)v34 = 0;
  v34[1] = 0;
  v34[2] = 0;
  v34[3] = 0;
  v34[4] = 0;
  v34[5] = 0;
  v34[6] = 0;
  v34[9] = 0;
  v34[10] = 0;
  v72 = v34;
  v34[7] = a2;
  v34[8] = a8;
  *(_DWORD *)v34 = a7;
  v34[4] = v25;
  v34[6] = a9;
  *((_DWORD *)v34 + 18) = a1;
  *((_DWORD *)v34 + 19) = a10;
  v34[5] = v32;
  if ( String1 )
  {
    v35 = 0x7FFFFFFF;
    v36 = String1;
    v37 = v12;
    do
    {
      if ( !*v36 )
        break;
      ++v36;
      --v35;
    }
    while ( v35 );
    ThreadTermEvent = v35 == 0 ? 0x80070057 : 0;
    v38 = (0x7FFFFFFF - v35) & -(__int64)(v35 != 0);
    if ( !v35 )
    {
      v13 = 0;
      v14 = 0;
      goto LABEL_140;
    }
    v39 = v38 + 1;
    if ( v38 + 1 < v38 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v35);
    v40 = HIDWORD(v39);
    if ( v39 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v40);
    v41 = 2LL * (unsigned int)v39;
    v42 = v40 << 33;
    if ( v42 + v41 < v41 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v42);
    if ( v42 + v41 )
    {
      v43 = (unsigned __int16 *)operator new[](saturated_mul(v39, 2u));
      v12[2] = v43;
      if ( !v43 )
      {
        ThreadTermEvent = -2147024882;
        v13 = 0;
        v14 = 0;
        goto LABEL_140;
      }
      ThreadTermEvent = StringCchCopyW(v43, v39, String1);
      if ( ThreadTermEvent < 0 )
      {
        v13 = 0;
        v14 = 0;
        goto LABEL_140;
      }
    }
  }
  else
  {
    v37 = v34;
  }
  v44 = a4;
  if ( a4 )
  {
    v45 = 0x7FFFFFFF;
    do
    {
      if ( !*v44 )
        break;
      ++v44;
      --v45;
    }
    while ( v45 );
    ThreadTermEvent = v45 == 0 ? 0x80070057 : 0;
    v46 = (0x7FFFFFFF - v45) & -(__int64)(v45 != 0);
    if ( !v45 )
    {
      v13 = 0;
      v14 = 0;
      goto LABEL_140;
    }
    v47 = v46 + 1;
    if ( v46 + 1 < v46 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v45);
    v48 = HIDWORD(v47);
    if ( v47 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v48);
    v49 = 2LL * (unsigned int)v47;
    v50 = v48 << 33;
    if ( v50 + v49 < v49 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v50);
    if ( v50 + v49 )
    {
      v51 = (unsigned __int16 *)operator new[](saturated_mul(v47, 2u));
      v37[3] = v51;
      if ( !v51 )
      {
        ThreadTermEvent = -2147024882;
        v13 = 0;
        v14 = 0;
        goto LABEL_140;
      }
      ThreadTermEvent = StringCchCopyW(v51, v47, a4);
      if ( ThreadTermEvent < 0 )
      {
        v13 = 0;
        v14 = 0;
        goto LABEL_140;
      }
    }
  }
  try
  {
    if ( a5 )
    {
      v52 = 0x7FFFFFFF;
      v53 = a5;
      do
      {
        if ( !*v53 )
          break;
        ++v53;
        --v52;
      }
      while ( v52 );
      ThreadTermEvent = v52 == 0 ? 0x80070057 : 0;
      v54 = (0x7FFFFFFF - v52) & ((unsigned __int128)-(__int128)(unsigned __int64)v52 >> 64);
      if ( !v52 )
      {
        v13 = 0;
        v14 = 0;
        goto LABEL_140;
      }
      v55 = v54 + 1;
      if ( v54 + 1 < v54 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v52);
      v56 = HIDWORD(v55);
      if ( v55 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v56);
      v57 = 2LL * (unsigned int)v55;
      v58 = v56 << 33;
      if ( v58 + v57 < v57 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v58);
      if ( v58 + v57 )
      {
        v59 = (unsigned __int16 *)operator new[](saturated_mul(v55, 2u));
        v37[1] = v59;
        if ( !v59 )
        {
          ThreadTermEvent = -2147024882;
          v13 = 0;
          v14 = 0;
          goto LABEL_140;
        }
        ThreadTermEvent = StringCchCopyW(v59, v55, a5);
        if ( ThreadTermEvent < 0 )
        {
          v13 = 0;
          v14 = 0;
          goto LABEL_140;
        }
      }
    }
    ThreadTermEvent = GetThreadTermEvent(a1, 0, v37 + 10);
    if ( ThreadTermEvent < 0 )
      goto LABEL_105;
    v60 = a7 & 2;
    if ( (a7 & 2) != 0 && String1 )
    {
      v61 = wcscmp_0(String1, L"WindowsAuthProvider") == 0;
      v62 = a7;
      if ( v61 && (a7 & 0x10) == 0 )
        goto LABEL_99;
      v60 = a7 & 2;
    }
    else
    {
      v62 = a7;
    }
    if ( (v62 & 0x10) != 0 )
    {
      if ( !v60 || !String1 || !wcscmp_0(String1, L"WindowsAuthProvider") )
      {
LABEL_99:
        v63 = SilentActivationProc;
LABEL_100:
        v11 = (void *)_beginthreadex(0, 0, v63, v37, 0, &ThrdAddr);
        if ( !v11 )
        {
          v64 = GetLastError();
          ThreadTermEvent = v64;
          if ( v64 > 0 )
            ThreadTermEvent = (unsigned __int16)v64 | 0x80070000;
          if ( ThreadTermEvent >= 0 )
            ThreadTermEvent = -2147467259;
          goto LABEL_105;
        }
        ThreadTermEvent = 0;
        v13 = 0;
        v14 = 0;
        goto LABEL_140;
      }
    }
    else if ( (a7 & 1) == 0 && (!String1 || !wcscmp_0(String1, L"PassportAuthProvider")) )
    {
      v63 = (unsigned int (__stdcall *)(void *))ActivationProc;
      goto LABEL_100;
    }
    ThreadTermEvent = -2147024809;
LABEL_105:
    v13 = 0;
    v14 = 0;
  }
  catch ( SafeIntException )
  {
    v12 = v72;
    v11 = 0;
    ThreadTermEvent = -2147467259;
    v13 = 0;
    goto LABEL_119;
  }
LABEL_140:
  operator delete(Block);
  if ( v13 )
    CloseHandle(v13);
  if ( v14 )
    CloseHandle(v14);
  if ( v11 )
  {
    SetThreadInfo(a1, 0, v11);
  }
  else if ( v12 )
  {
    operator delete(v12[3]);
    operator delete(v12[1]);
    operator delete(v12[2]);
    v65 = v12[4];
    if ( v65 )
      CloseHandle(v65);
    v66 = v12[5];
    if ( v66 )
      CloseHandle(v66);
    operator delete(v12);
  }
  return (unsigned int)ThreadTermEvent;
}

```

## disassembly

```asm
0x18002b454  mov     rax, rsp
0x18002b457  mov     [rax+20h], r9
0x18002b45b  mov     [rax+18h], r8d
0x18002b45f  mov     [rax+10h], rdx
0x18002b463  mov     [rax+8], ecx
0x18002b466  push    rbx
0x18002b467  push    rsi
0x18002b468  push    rdi
0x18002b469  push    r12
0x18002b46b  push    r13
0x18002b46d  push    r14
0x18002b46f  push    r15
0x18002b471  sub     rsp, 90h
0x18002b478  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18002b480  mov     rbx, r9
0x18002b483  xor     edi, edi
0x18002b485  mov     [rsp+0C8h+var_84], edi
0x18002b489  mov     r12d, edi
0x18002b48c  mov     esi, edi
0x18002b48e  mov     [rsp+0C8h+Block], rdi
0x18002b493  mov     r13d, edi
0x18002b496  mov     r15d, edi
0x18002b499  mov     [rsp+0C8h+var_90], rdi
0x18002b49e  mov     qword ptr [rax-58h], 18h
0x18002b4a6  mov     qword ptr [rax-48h], 1
0x18002b4ae  mov     [rax-50h], rdi
0x18002b4b2  mov     eax, [rsp+0C8h+arg_30]
0x18002b4b9  mov     ecx, eax
0x18002b4bb  and     ecx, 1
0x18002b4be  mov     [rsp+0C8h+var_88], ecx
0x18002b4c2  jnz     short loc_18002B4D2
0x18002b4c4  test    al, 0Ah
0x18002b4c6  jnz     short loc_18002B4D2
0x18002b4c8  mov     ebx, 80070057h
0x18002b4cd  jmp     loc_18002B6EE
0x18002b4d2  and     eax, 2
0x18002b4d5  mov     [rsp+0C8h+arg_10], eax
0x18002b4dc  mov     r15, [rsp+0C8h+String1]
0x18002b4e4  jnz     short loc_18002B4EB
0x18002b4e6  test    r15, r15
0x18002b4e9  jz      short loc_18002B4FD
0x18002b4eb  xor     edx, edx
0x18002b4ed  mov     rcx, r15
0x18002b4f0  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18002b4f5  test    al, al
0x18002b4f7  jz      loc_18002BC18
0x18002b4fd  mov     r14, [rsp+0C8h+arg_20]
0x18002b505  test    r14, r14
0x18002b508  jz      short loc_18002B51C
0x18002b50a  xor     edx, edx
0x18002b50c  mov     rcx, r14
0x18002b50f  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18002b514  test    al, al
0x18002b516  jz      loc_18002BC18
0x18002b51c  test    rbx, rbx
0x18002b51f  jz      short loc_18002B533
0x18002b521  xor     edx, edx
0x18002b523  mov     rcx, rbx
0x18002b526  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18002b52b  test    al, al
0x18002b52d  jz      loc_18002BC18
0x18002b533  mov     r9, r15
0x18002b536  mov     r8, r14
0x18002b539  mov     rdx, rbx
0x18002b53c  lea     rcx, aMsdrmWszserver_1; "[msdrm]:wszServer = %S,wszUserID = %S,w"...
0x18002b543  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002b548  nop
0x18002b549  mov     ecx, 7FFFFFFFh
0x18002b54e  mov     edx, ecx
0x18002b550  lea     rax, ?g_wszActCancelEventName@@3QBGB; "UDRMActivation_"
0x18002b557  cmp     [rax], di
0x18002b55a  jz      short loc_18002B566
0x18002b55c  add     rax, 2
0x18002b560  sub     rdx, 1
0x18002b564  jnz     short loc_18002B557
0x18002b566  mov     rax, rdx
0x18002b569  neg     rax
0x18002b56c  sbb     ebx, ebx
0x18002b56e  not     ebx
0x18002b570  mov     r14d, 80070057h
0x18002b576  and     ebx, r14d
0x18002b579  mov     rax, rdx
0x18002b57c  sub     rcx, rdx
0x18002b57f  neg     rax
0x18002b582  sbb     r8, r8
0x18002b585  and     r8, rcx
0x18002b588  test    rdx, rdx
0x18002b58b  jnz     short loc_18002B595
0x18002b58d  mov     r15, rdi
0x18002b590  jmp     loc_18002B6EE
0x18002b595  lea     rbx, [r8+1]
0x18002b599  cmp     rbx, r8
0x18002b59c  jb      loc_18002BC7A
0x18002b5a2  mov     rcx, rbx
0x18002b5a5  shr     rcx, 20h
0x18002b5a9  mov     rax, rcx
0x18002b5ac  shr     rax, 1Fh
0x18002b5b0  test    eax, eax
0x18002b5b2  jnz     loc_18002BC80
0x18002b5b8  mov     eax, ebx
0x18002b5ba  add     rax, rax
0x18002b5bd  shl     rcx, 21h; this
0x18002b5c1  lea     rdx, [rcx+rax]
0x18002b5c5  cmp     rdx, rax
0x18002b5c8  jb      loc_18002BC85
0x18002b5ce  test    rdx, rdx
0x18002b5d1  jz      short loc_18002B625
0x18002b5d3  mov     eax, 2
0x18002b5d8  mul     rbx
0x18002b5db  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b5e2  cmovb   rax, rcx
0x18002b5e6  mov     rcx, rax; unsigned __int64
0x18002b5e9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b5ee  mov     [rsp+0C8h+Block], rax
0x18002b5f3  test    rax, rax
0x18002b5f6  jnz     short loc_18002B605
0x18002b5f8  mov     ebx, 8007000Eh
0x18002b5fd  mov     r15, rdi
0x18002b600  jmp     loc_18002B6EE
0x18002b605  lea     r8, ?g_wszActCancelEventName@@3QBGB; "UDRMActivation_"
0x18002b60c  mov     rdx, rbx; unsigned __int64
0x18002b60f  mov     rcx, rax; unsigned __int16 *
0x18002b612  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b617  mov     ebx, eax
0x18002b619  test    eax, eax
0x18002b61b  jns     short loc_18002B625
0x18002b61d  mov     r15, rdi
0x18002b620  jmp     loc_18002B6EE
0x18002b625  mov     r8, [rsp+0C8h+Block]; int
0x18002b62a  mov     edx, 1; unsigned int
0x18002b62f  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x18002b634  mov     rbx, rax
0x18002b637  mov     [rsp+0C8h+var_98], rax
0x18002b63c  test    rax, rax
0x18002b63f  jnz     short loc_18002B64C
0x18002b641  mov     ebx, r14d
0x18002b644  mov     r13, rax
0x18002b647  jmp     loc_18002BC10
0x18002b64c  mov     eax, [rsp+0C8h+arg_30]
0x18002b653  mov     rcx, rbx; hEvent
0x18002b656  test    al, 8
0x18002b658  jz      short loc_18002B672
0x18002b65a  call    cs:__imp_SetEvent
0x18002b660  mov     ebx, edi
0x18002b662  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002b667  call    cs:__imp_Sleep
0x18002b66d  mov     r15, rdi
0x18002b670  jmp     short loc_18002B6E9
0x18002b672  call    cs:__imp_ResetEvent
0x18002b678  mov     eax, [rsp+0C8h+var_88]
0x18002b67c  test    eax, eax
0x18002b67e  jz      loc_18002B742
0x18002b684  lea     r8, ?g_wszActMachineEventName@@3QBGB; "UDRMActivation_Machine"
0x18002b68b  mov     edx, 1; unsigned int
0x18002b690  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x18002b695  test    rax, rax
0x18002b698  jz      short loc_18002B6A4
0x18002b69a  mov     ebx, 8004CF38h
0x18002b69f  mov     r15, rax
0x18002b6a2  jmp     short loc_18002B6E9
0x18002b6a4  lea     r9, ?g_wszActMachineEventName@@3QBGB; "UDRMActivation_Machine"
0x18002b6ab  xor     r8d, r8d; int
0x18002b6ae  lea     rcx, [rsp+0C8h+EventAttributes]; lpEventAttributes
0x18002b6b3  call    ?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18002b6b8  mov     r13, rax
0x18002b6bb  mov     [rsp+0C8h+var_90], rax
0x18002b6c0  test    rax, rax
0x18002b6c3  jnz     short loc_18002B733
0x18002b6c5  call    cs:__imp_GetLastError
0x18002b6cb  mov     ebx, eax
0x18002b6cd  test    eax, eax
0x18002b6cf  jle     short loc_18002B6DA
0x18002b6d1  movzx   ebx, ax
0x18002b6d4  or      ebx, 80070000h
0x18002b6da  mov     eax, 80004005h
0x18002b6df  test    ebx, ebx
0x18002b6e1  cmovns  ebx, eax
0x18002b6e4  mov     r15, [rsp+0C8h+var_90]
0x18002b6e9  mov     r13, [rsp+0C8h+var_98]
0x18002b6ee  mov     rcx, [rsp+0C8h+Block]; Block
0x18002b6f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b6f8  test    r13, r13
0x18002b6fb  jz      short loc_18002B706
0x18002b6fd  mov     rcx, r13; hObject
0x18002b700  call    cs:__imp_CloseHandle
0x18002b706  test    r15, r15
0x18002b709  jz      short loc_18002B714
0x18002b70b  mov     rcx, r15; hObject
0x18002b70e  call    cs:__imp_CloseHandle
0x18002b714  test    r12, r12
0x18002b717  jz      loc_18002BC1F
0x18002b71d  mov     r8, r12; void *
0x18002b720  xor     edx, edx; unsigned int
0x18002b722  mov     ecx, [rsp+0C8h+arg_0]; unsigned int
0x18002b729  call    ?SetThreadInfo@@YAJKIPEAX@Z; SetThreadInfo(ulong,uint,void *)
0x18002b72e  jmp     loc_18002BC65
0x18002b733  mov     rcx, rax; hEvent
0x18002b736  call    cs:__imp_ResetEvent
0x18002b73c  mov     eax, [rsp+0C8h+var_88]
0x18002b740  jmp     short loc_18002B745
0x18002b742  mov     r13, rdi
0x18002b745  cmp     [rsp+0C8h+arg_10], edi
0x18002b74c  jz      short loc_18002B767
0x18002b74e  test    eax, eax
0x18002b750  jnz     short loc_18002B767
0x18002b752  lea     edx, [rax+1]; unsigned int
0x18002b755  xor     ecx, ecx; unsigned __int16 *
0x18002b757  call    ?IsActivated@@YAJPEAGI@Z; IsActivated(ushort *,uint)
0x18002b75c  mov     ebx, eax
0x18002b75e  test    eax, eax
0x18002b760  js      short loc_18002B6E4
0x18002b762  mov     rbx, [rsp+0C8h+var_98]
0x18002b767  mov     ecx, 58h ; 'X'; Size
0x18002b76c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b771  mov     rsi, rax
0x18002b774  mov     [rsp+0C8h+var_80], rax
0x18002b779  test    rax, rax
0x18002b77c  jz      loc_18002BBF2
0x18002b782  mov     [rax], edi
0x18002b784  mov     [rax+8], rdi
0x18002b788  mov     [rax+10h], rdi
0x18002b78c  mov     [rax+18h], rdi
0x18002b790  mov     [rax+20h], rdi
0x18002b794  mov     [rax+28h], rdi
0x18002b798  mov     [rax+30h], rdi
0x18002b79c  mov     [rax+48h], rdi
0x18002b7a0  mov     [rax+50h], rdi
0x18002b7a4  mov     [rsp+0C8h+var_78], rax
0x18002b7a9  test    rax, rax
0x18002b7ac  jz      loc_18002BBF5
0x18002b7b2  mov     rax, [rsp+0C8h+arg_8]
0x18002b7ba  mov     [rsi+38h], rax
0x18002b7be  mov     rax, [rsp+0C8h+arg_38]
0x18002b7c6  mov     [rsi+40h], rax
0x18002b7ca  mov     eax, [rsp+0C8h+arg_30]
0x18002b7d1  mov     [rsi], eax
0x18002b7d3  mov     [rsi+20h], rbx
0x18002b7d7  mov     rax, [rsp+0C8h+arg_40]
0x18002b7df  mov     [rsi+30h], rax
0x18002b7e3  mov     eax, [rsp+0C8h+arg_0]
0x18002b7ea  mov     [rsi+48h], eax
0x18002b7ed  mov     eax, [rsp+0C8h+arg_48]
0x18002b7f4  mov     [rsi+4Ch], eax
0x18002b7f7  mov     [rsp+0C8h+var_98], rdi
0x18002b7fc  mov     [rsi+28h], r13
0x18002b800  test    r15, r15
0x18002b803  jz      loc_18002B8F6
0x18002b809  mov     ecx, 7FFFFFFFh
0x18002b80e  mov     edx, ecx
0x18002b810  mov     rax, r15
0x18002b813  mov     r13, rsi
0x18002b816  cmp     [rax], di
0x18002b819  jz      short loc_18002B825
0x18002b81b  add     rax, 2
0x18002b81f  sub     rdx, 1
0x18002b823  jnz     short loc_18002B816
0x18002b825  mov     rax, rdx
0x18002b828  neg     rax
0x18002b82b  sbb     ebx, ebx
0x18002b82d  not     ebx
0x18002b82f  and     ebx, r14d
0x18002b832  mov     rax, rdx
0x18002b835  sub     rcx, rdx
0x18002b838  neg     rax
0x18002b83b  sbb     r8, r8
0x18002b83e  and     r8, rcx
0x18002b841  test    rdx, rdx
0x18002b844  jnz     short loc_18002B853
0x18002b846  mov     r13, [rsp+0C8h+var_98]
0x18002b84b  mov     r15, r13
0x18002b84e  jmp     loc_18002B6EE
0x18002b853  lea     rbx, [r8+1]
0x18002b857  cmp     rbx, r8
0x18002b85a  jb      loc_18002BC8B
0x18002b860  mov     rcx, rbx
0x18002b863  shr     rcx, 20h
0x18002b867  mov     rax, rcx
0x18002b86a  shr     rax, 1Fh
0x18002b86e  test    eax, eax
0x18002b870  jnz     loc_18002BC90
0x18002b876  mov     eax, ebx
0x18002b878  add     rax, rax
0x18002b87b  shl     rcx, 21h
0x18002b87f  lea     rdx, [rcx+rax]
0x18002b883  cmp     rdx, rax
0x18002b886  jb      loc_18002BC95
0x18002b88c  test    rdx, rdx
0x18002b88f  jz      short loc_18002B8E8
0x18002b891  mov     eax, 2
0x18002b896  mul     rbx
0x18002b899  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b8a0  cmovb   rax, rcx
0x18002b8a4  mov     rcx, rax; unsigned __int64
0x18002b8a7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b8ac  mov     [rsi+10h], rax
0x18002b8b0  test    rax, rax
0x18002b8b3  jnz     short loc_18002B8C7
0x18002b8b5  mov     ebx, 8007000Eh
0x18002b8ba  mov     r13, [rsp+0C8h+var_98]
0x18002b8bf  mov     r15, r13
  ... truncated ...
```
