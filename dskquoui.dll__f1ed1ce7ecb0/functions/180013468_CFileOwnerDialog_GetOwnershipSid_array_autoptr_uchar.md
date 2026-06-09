# CFileOwnerDialog::GetOwnershipSid(array_autoptr<uchar> *)

- ea: `0x180013468`
- end: `0x180013874`
- name: `?GetOwnershipSid@CFileOwnerDialog@@AEAAJPEAV?$array_autoptr@E@@@Z`
- size: `1036`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014e68`

## callees

- `0x180006ec0`
- `0x180013468`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001359c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800135da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001376b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001359c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800135da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001376b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800134c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800134c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013495`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800134af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800134af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800134d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800134d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001370e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800137f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001370e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800137f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013836`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001353a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800135cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013611`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013761`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001353a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800135cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013611`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013761`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800136a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013790`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800136a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013790`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013720`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013802`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013720`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013802`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013813`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013813`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFileOwnerDialog::GetOwnershipSid(__int64 a1, __int64 a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  void *v7; // r14
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  void *v11; // rdi
  PSID *v12; // r15
  unsigned int v13; // eax
  __int64 v14; // r14
  SIZE_T LengthSid; // r12
  void *v16; // rbx
  BOOL v17; // esi
  signed int v18; // eax
  PSID *v19; // r14
  SIZE_T v20; // r15
  void *v21; // rbx
  BOOL v22; // esi
  void *v23; // rcx
  void **v25; // [rsp+38h] [rbp-29h] BYREF
  BOOL v26; // [rsp+40h] [rbp-21h]
  LPVOID TokenInformation; // [rsp+48h] [rbp-19h]
  void **v28; // [rsp+50h] [rbp-11h] BYREF
  BOOL v29; // [rsp+58h] [rbp-9h]
  void *v30; // [rsp+60h] [rbp-1h]
  void **v31; // [rsp+68h] [rbp+7h] BYREF
  BOOL v32; // [rsp+70h] [rbp+Fh]
  void *v33; // [rsp+78h] [rbp+17h]
  void **v34; // [rsp+80h] [rbp+1Fh]
  BOOL v35; // [rsp+88h] [rbp+27h]
  void *v36; // [rsp+90h] [rbp+2Fh]
  __int64 TokenInformationLength; // [rsp+C8h] [rbp+67h] BYREF
  void *TokenHandle; // [rsp+D8h] [rbp+77h] BYREF

  TokenInformationLength = a1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008
      || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle)) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_58;
    }
  }
  v6 = -2147467259;
  v26 = 0;
  TokenInformation = 0;
  v25 = &array_autoptr<char>::`vftable';
  LODWORD(TokenInformationLength) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, (PDWORD)&TokenInformationLength) )
  {
    if ( GetLastError() == 122 )
    {
      v7 = operator new((unsigned int)TokenInformationLength);
      v35 = v7 != 0;
      v36 = v7;
      v34 = &array_autoptr<char>::`vftable';
      v26 = v35;
      TokenInformation = v7;
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
    }
  }
  if ( TokenInformation )
  {
    if ( GetTokenInformation(
           TokenHandle,
           TokenGroups,
           TokenInformation,
           TokenInformationLength,
           (PDWORD)&TokenInformationLength) )
    {
      v12 = (PSID *)TokenInformation;
      v13 = 0;
      if ( *(_DWORD *)TokenInformation )
      {
        while ( 1 )
        {
          v14 = 2LL * v13;
          if ( (*((_BYTE *)TokenInformation + 16 * v13 + 16) & 8) != 0 )
            break;
          if ( ++v13 >= *(_DWORD *)TokenInformation )
            goto LABEL_15;
        }
        LengthSid = (int)GetLengthSid(*((PSID *)TokenInformation + 2 * v13 + 1));
        v16 = operator new(LengthSid);
        v29 = v16 != 0;
        v17 = v29;
        v30 = v16;
        v28 = &array_autoptr<char>::`vftable';
        if ( (void ***)a2 != &v28 )
        {
          if ( *(_DWORD *)(a2 + 8) )
            (**(void (__fastcall ***)(__int64))a2)(a2);
          *(_DWORD *)(a2 + 8) = v17;
          *(_QWORD *)(a2 + 16) = v16;
          v17 = 0;
        }
        if ( v17 && v16 )
          LocalFree(v16);
        CopySid(LengthSid, *(PSID *)(a2 + 16), v12[v14 + 1]);
LABEL_50:
        v6 = 0;
        goto LABEL_51;
      }
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
    }
  }
LABEL_15:
  if ( v6 >= 0 )
  {
LABEL_51:
    v23 = *(void **)(a2 + 16);
    if ( v23 && !IsValidSid(v23) )
      v6 = -2147023559;
    goto LABEL_54;
  }
  LODWORD(TokenInformationLength) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) )
  {
    v10 = GetLastError();
    if ( v10 == 122 )
    {
      v11 = operator new((unsigned int)TokenInformationLength);
      v35 = v11 != 0;
      v36 = v11;
      v34 = &array_autoptr<char>::`vftable';
      if ( v26 )
        ((void (__fastcall *)(void ***))*v25)(&v25);
      v26 = v11 != 0;
      TokenInformation = v11;
      goto LABEL_54;
    }
    v6 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
    if ( v6 >= 0 )
    {
      if ( !GetTokenInformation(
              TokenHandle,
              TokenUser,
              TokenInformation,
              TokenInformationLength,
              (PDWORD)&TokenInformationLength) )
      {
        v18 = GetLastError();
        v6 = v18;
        if ( v18 > 0 )
          v6 = (unsigned __int16)v18 | 0x80070000;
        if ( v6 < 0 )
          goto LABEL_54;
        goto LABEL_51;
      }
      v19 = (PSID *)TokenInformation;
      v20 = (int)GetLengthSid(*(PSID *)TokenInformation);
      v21 = operator new(v20);
      v32 = v21 != 0;
      v22 = v32;
      v33 = v21;
      v31 = &array_autoptr<char>::`vftable';
      if ( (void ***)a2 != &v31 )
      {
        if ( *(_DWORD *)(a2 + 8) )
          (**(void (__fastcall ***)(__int64))a2)(a2);
        *(_DWORD *)(a2 + 8) = v22;
        *(_QWORD *)(a2 + 16) = v21;
        v22 = 0;
      }
      if ( v22 && v21 )
        LocalFree(v21);
      CopySid(v20, *(PSID *)(a2 + 16), *v19);
      goto LABEL_50;
    }
  }
LABEL_54:
  v25 = &array_autoptr<char>::`vftable';
  if ( v26 && TokenInformation )
    LocalFree(TokenInformation);
  v25 = &a_ptr<IDiskQuotaUser>::`vftable';
LABEL_58:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013468  mov     rax, rsp
0x18001346b  mov     [rax+10h], rbx
0x18001346f  mov     [rax+20h], rsi
0x180013473  mov     [rax+8], rcx
0x180013477  push    rbp
0x180013478  push    rdi
0x180013479  push    r12
0x18001347b  push    r14
0x18001347d  push    r15
0x18001347f  lea     rbp, [rax-5Fh]
0x180013483  sub     rsp, 90h
0x18001348a  mov     rdi, rdx
0x18001348d  mov     [rbp+57h+TokenHandle], 0
0x180013495  call    cs:__imp_GetCurrentThread
0x18001349b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001349f  mov     ebx, 20008h
0x1800134a4  mov     r8d, 1; OpenAsSelf
0x1800134aa  mov     edx, ebx; DesiredAccess
0x1800134ac  mov     rcx, rax; ThreadHandle
0x1800134af  call    cs:__imp_OpenThreadToken
0x1800134b5  test    eax, eax
0x1800134b7  jnz     short loc_1800134FD
0x1800134b9  call    cs:__imp_GetLastError
0x1800134bf  cmp     eax, 3F0h
0x1800134c4  jnz     short loc_1800134DF
0x1800134c6  call    cs:__imp_GetCurrentProcess
0x1800134cc  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800134d0  mov     edx, ebx; DesiredAccess
0x1800134d2  mov     rcx, rax; ProcessHandle
0x1800134d5  call    cs:__imp_OpenProcessToken
0x1800134db  test    eax, eax
0x1800134dd  jnz     short loc_1800134FD
0x1800134df  call    cs:__imp_GetLastError
0x1800134e5  mov     ebx, eax
0x1800134e7  test    eax, eax
0x1800134e9  jle     loc_180013847
0x1800134ef  movzx   ebx, ax
0x1800134f2  or      ebx, 80070000h
0x1800134f8  jmp     loc_180013847
0x1800134fd  mov     ebx, 80004005h
0x180013502  mov     [rbp+57h+var_78], 0
0x180013509  mov     [rbp+57h+TokenInformation], 0
0x180013511  lea     r12, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x180013518  mov     [rbp+57h+var_80], r12
0x18001351c  mov     dword ptr [rbp+57h+TokenInformationLength], 0
0x180013523  lea     rax, [rbp+57h+TokenInformationLength]
0x180013527  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18001352c  xor     r9d, r9d; TokenInformationLength
0x18001352f  xor     r8d, r8d; TokenInformation
0x180013532  lea     edx, [r9+2]; TokenInformationClass
0x180013536  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001353a  call    cs:__imp_GetTokenInformation
0x180013540  mov     esi, 80070000h
0x180013545  test    eax, eax
0x180013547  jnz     short loc_1800135AD
0x180013549  call    cs:__imp_GetLastError
0x18001354f  cmp     eax, 7Ah ; 'z'
0x180013552  jnz     short loc_18001359C
0x180013554  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; uBytes
0x180013557  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001355c  mov     r14, rax
0x18001355f  xor     ecx, ecx
0x180013561  test    rax, rax
0x180013564  setnz   cl
0x180013567  mov     [rbp+57h+var_30], ecx
0x18001356a  xor     r15d, r15d
0x18001356d  test    rax, rax
0x180013570  setnz   r15b
0x180013574  mov     [rbp+57h+var_28], rax
0x180013578  mov     [rbp+57h+var_38], r12
0x18001357c  cmp     [rbp+57h+var_78], 0
0x180013580  jz      short loc_180013592
0x180013582  mov     rax, [rbp+57h+var_80]
0x180013586  lea     rcx, [rbp+57h+var_80]
0x18001358a  mov     rax, [rax]
0x18001358d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013592  mov     [rbp+57h+var_78], r15d
0x180013596  mov     [rbp+57h+TokenInformation], r14
0x18001359a  jmp     short loc_1800135AD
0x18001359c  call    cs:__imp_GetLastError
0x1800135a2  mov     ebx, eax
0x1800135a4  test    eax, eax
0x1800135a6  jle     short loc_1800135AD
0x1800135a8  movzx   ebx, ax
0x1800135ab  or      ebx, esi
0x1800135ad  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800135b1  test    r8, r8
0x1800135b4  jz      short loc_1800135EB
0x1800135b6  lea     rax, [rbp+57h+TokenInformationLength]
0x1800135ba  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800135bf  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800135c3  mov     edx, 2; TokenInformationClass
0x1800135c8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800135cc  call    cs:__imp_GetTokenInformation
0x1800135d2  test    eax, eax
0x1800135d4  jnz     loc_180013677
0x1800135da  call    cs:__imp_GetLastError
0x1800135e0  mov     ebx, eax
0x1800135e2  test    eax, eax
0x1800135e4  jle     short loc_1800135EB
0x1800135e6  movzx   ebx, ax
0x1800135e9  or      ebx, esi
0x1800135eb  test    ebx, ebx
0x1800135ed  jns     loc_18001380A
0x1800135f3  mov     dword ptr [rbp+57h+TokenInformationLength], 0
0x1800135fa  lea     rax, [rbp+57h+TokenInformationLength]
0x1800135fe  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180013603  xor     r9d, r9d; TokenInformationLength
0x180013606  xor     r8d, r8d; TokenInformation
0x180013609  lea     edx, [r9+1]; TokenInformationClass
0x18001360d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180013611  call    cs:__imp_GetTokenInformation
0x180013617  test    eax, eax
0x180013619  jnz     loc_180013823
0x18001361f  call    cs:__imp_GetLastError
0x180013625  cmp     eax, 7Ah ; 'z'
0x180013628  jnz     loc_180013732
0x18001362e  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; uBytes
0x180013631  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013636  mov     rdi, rax
0x180013639  xor     ecx, ecx
0x18001363b  test    rax, rax
0x18001363e  setnz   cl
0x180013641  mov     [rbp+57h+var_30], ecx
0x180013644  xor     esi, esi
0x180013646  test    rax, rax
0x180013649  setnz   sil
0x18001364d  mov     [rbp+57h+var_28], rax
0x180013651  mov     [rbp+57h+var_38], r12
0x180013655  cmp     [rbp+57h+var_78], 0
0x180013659  jz      short loc_18001366B
0x18001365b  mov     rax, [rbp+57h+var_80]
0x18001365f  lea     rcx, [rbp+57h+var_80]
0x180013663  mov     rax, [rax]
0x180013666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001366b  mov     [rbp+57h+var_78], esi
0x18001366e  mov     [rbp+57h+TokenInformation], rdi
0x180013672  jmp     loc_180013823
0x180013677  mov     r15, [rbp+57h+TokenInformation]
0x18001367b  xor     eax, eax
0x18001367d  cmp     [r15], eax
0x180013680  jbe     loc_1800135EB
0x180013686  mov     r14d, eax
0x180013689  add     r14, r14
0x18001368c  test    byte ptr [r15+r14*8+10h], 8
0x180013692  jnz     short loc_1800136A0
0x180013694  inc     eax
0x180013696  cmp     eax, [r15]
0x180013699  jb      short loc_180013686
0x18001369b  jmp     loc_1800135EB
0x1800136a0  mov     rcx, [r15+r14*8+8]; pSid
0x1800136a5  call    cs:__imp_GetLengthSid
0x1800136ab  movsxd  r12, eax
0x1800136ae  mov     rcx, r12; uBytes
0x1800136b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800136b6  mov     rbx, rax
0x1800136b9  xor     ecx, ecx
0x1800136bb  test    rax, rax
0x1800136be  setnz   cl
0x1800136c1  mov     [rbp+57h+var_60], ecx
0x1800136c4  xor     esi, esi
0x1800136c6  test    rax, rax
0x1800136c9  setnz   sil
0x1800136cd  mov     [rbp+57h+var_58], rax
0x1800136d1  lea     rax, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x1800136d8  mov     [rbp+57h+var_68], rax
0x1800136dc  lea     rax, [rbp+57h+var_68]
0x1800136e0  cmp     rdi, rax
0x1800136e3  jz      short loc_180013702
0x1800136e5  cmp     dword ptr [rdi+8], 0
0x1800136e9  jz      short loc_1800136F9
0x1800136eb  mov     rax, [rdi]
0x1800136ee  mov     rcx, rdi
0x1800136f1  mov     rax, [rax]
0x1800136f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136f9  mov     [rdi+8], esi
0x1800136fc  mov     [rdi+10h], rbx
0x180013700  xor     esi, esi
0x180013702  test    esi, esi
0x180013704  jz      short loc_180013714
0x180013706  test    rbx, rbx
0x180013709  jz      short loc_180013714
0x18001370b  mov     rcx, rbx; hMem
0x18001370e  call    cs:__imp_LocalFree
0x180013714  mov     r8, [r15+r14*8+8]; pSourceSid
0x180013719  mov     rdx, [rdi+10h]; pDestinationSid
0x18001371d  mov     ecx, r12d; nDestinationSidLength
0x180013720  call    cs:__imp_CopySid
0x180013726  lea     r12, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x18001372d  jmp     loc_180013808
0x180013732  test    eax, eax
0x180013734  jg      short loc_18001373A
0x180013736  mov     ebx, eax
0x180013738  jmp     short loc_18001373F
0x18001373a  movzx   ebx, ax
0x18001373d  or      ebx, esi
0x18001373f  test    ebx, ebx
0x180013741  js      loc_180013823
0x180013747  lea     rax, [rbp+57h+TokenInformationLength]
0x18001374b  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180013750  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180013754  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180013758  mov     edx, 1; TokenInformationClass
0x18001375d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180013761  call    cs:__imp_GetTokenInformation
0x180013767  test    eax, eax
0x180013769  jnz     short loc_180013789
0x18001376b  call    cs:__imp_GetLastError
0x180013771  mov     ebx, eax
0x180013773  test    eax, eax
0x180013775  jle     short loc_18001377C
0x180013777  movzx   ebx, ax
0x18001377a  or      ebx, esi
0x18001377c  test    ebx, ebx
0x18001377e  js      loc_180013823
0x180013784  jmp     loc_18001380A
0x180013789  mov     r14, [rbp+57h+TokenInformation]
0x18001378d  mov     rcx, [r14]; pSid
0x180013790  call    cs:__imp_GetLengthSid
0x180013796  movsxd  r15, eax
0x180013799  mov     rcx, r15; uBytes
0x18001379c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800137a1  mov     rbx, rax
0x1800137a4  xor     ecx, ecx
0x1800137a6  test    rax, rax
0x1800137a9  setnz   cl
0x1800137ac  mov     [rbp+57h+var_48], ecx
0x1800137af  xor     esi, esi
0x1800137b1  test    rax, rax
0x1800137b4  setnz   sil
0x1800137b8  mov     [rbp+57h+var_40], rax
0x1800137bc  mov     [rbp+57h+var_50], r12
0x1800137c0  lea     rax, [rbp+57h+var_50]
0x1800137c4  cmp     rdi, rax
0x1800137c7  jz      short loc_1800137E6
0x1800137c9  cmp     dword ptr [rdi+8], 0
0x1800137cd  jz      short loc_1800137DD
0x1800137cf  mov     rax, [rdi]
0x1800137d2  mov     rcx, rdi
0x1800137d5  mov     rax, [rax]
0x1800137d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137dd  mov     [rdi+8], esi
0x1800137e0  mov     [rdi+10h], rbx
0x1800137e4  xor     esi, esi
0x1800137e6  test    esi, esi
0x1800137e8  jz      short loc_1800137F8
0x1800137ea  test    rbx, rbx
0x1800137ed  jz      short loc_1800137F8
0x1800137ef  mov     rcx, rbx; hMem
0x1800137f2  call    cs:__imp_LocalFree
0x1800137f8  mov     r8, [r14]; pSourceSid
0x1800137fb  mov     rdx, [rdi+10h]; pDestinationSid
0x1800137ff  mov     ecx, r15d; nDestinationSidLength
0x180013802  call    cs:__imp_CopySid
0x180013808  xor     ebx, ebx
0x18001380a  mov     rcx, [rdi+10h]; pSid
0x18001380e  test    rcx, rcx
0x180013811  jz      short loc_180013823
0x180013813  call    cs:__imp_IsValidSid
0x180013819  mov     ecx, 80070539h
0x18001381e  test    eax, eax
0x180013820  cmovz   ebx, ecx
0x180013823  mov     [rbp+57h+var_80], r12
0x180013827  cmp     [rbp+57h+var_78], 0
0x18001382b  jz      short loc_18001383C
0x18001382d  mov     rcx, [rbp+57h+TokenInformation]; hMem
0x180013831  test    rcx, rcx
0x180013834  jz      short loc_18001383C
0x180013836  call    cs:__imp_LocalFree
0x18001383c  lea     rax, ??_7?$a_ptr@UIDiskQuotaUser@@@@6B@; const a_ptr<IDiskQuotaUser>::`vftable'
0x180013843  mov     [rbp+57h+var_80], rax
0x180013847  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001384b  test    rcx, rcx
0x18001384e  jz      short loc_180013856
0x180013850  call    cs:__imp_CloseHandle
0x180013856  mov     eax, ebx
0x180013858  lea     r11, [rsp+0B0h+var_20]
0x180013860  mov     rbx, [r11+38h]
0x180013864  mov     rsi, [r11+48h]
0x180013868  mov     rsp, r11
0x18001386b  pop     r15
0x18001386d  pop     r14
0x18001386f  pop     r12
0x180013871  pop     rdi
0x180013872  pop     rbp
0x180013873  retn
```
