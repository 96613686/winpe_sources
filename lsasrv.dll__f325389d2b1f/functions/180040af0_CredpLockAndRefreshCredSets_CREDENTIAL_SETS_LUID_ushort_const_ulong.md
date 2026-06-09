# CredpLockAndRefreshCredSets(_CREDENTIAL_SETS *,_LUID *,ushort const * *,ulong)

- ea: `0x180040af0`
- end: `0x180041388`
- name: `?CredpLockAndRefreshCredSets@@YAXPEAU_CREDENTIAL_SETS@@PEAU_LUID@@PEAPEBGK@Z`
- size: `2200`
- prototype: `void __fastcall(struct _CREDENTIAL_SETS *, struct _LUID *, unsigned __int16 **, unsigned int)`
- caller_count: `14`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18003f4e0`
- `0x180040814`
- `0x1800419c0`
- `0x1800432c0`
- `0x180044e00`
- `0x180085e88`
- `0x180086380`
- `0x1800c13cc`
- `0x1800c1cfc`
- `0x1800c2050`
- `0x1800c21b0`
- `0x1800c2814`
- `0x1800c35f4`
- `0x1800c559c`

## callees

- `0x180011278`
- `0x1800284d4`
- `0x18003a68c`
- `0x180040af0`
- `0x180041fd0`
- `0x180076aec`
- `0x180081810`
- `0x180097c3c`
- `0x1800c7180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040be3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800411b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800411b6`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x180040d29`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x180040d29`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180040cc9`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180040cc9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180040cee`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180040cee`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180040d19`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180040d19`
- `ntdll!NtClose` at `0x180041340`
- `ntdll!NtClose` at `0x180041340`
- `ntdll!RtlEnterCriticalSection` at `0x180040b35`
- `ntdll!RtlEnterCriticalSection` at `0x180040b35`
- `ntdll!NtSetInformationThread` at `0x180041377`
- `ntdll!NtSetInformationThread` at `0x180041377`
- `ntdll!NtOpenThreadToken` at `0x18004102a`
- `ntdll!NtOpenThreadToken` at `0x18004102a`

## pseudocode

```c
void __fastcall CredpLockAndRefreshCredSets(
        struct _CREDENTIAL_SETS *a1,
        struct _LUID *a2,
        unsigned __int16 **a3,
        unsigned int a4)
{
  __int64 v5; // rcx
  char v6; // r14
  LsaHandleCache *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  char v13; // bp
  __int64 v14; // rcx
  __int64 v15; // rdi
  void *v16; // rcx
  DWORD v17; // eax
  LsaHandleCache *v18; // rcx
  int IsImpersonated; // eax
  char v20; // bp
  int v21; // eax
  const wchar_t *v22; // r9
  __int64 v23; // rdx
  struct _LUID v24; // rax
  int CredSet; // eax
  LsaHandleCache *v26; // rcx
  __int64 v27; // rdx
  const wchar_t *v28; // r9
  void *v29; // r8
  int v30; // edx
  const wchar_t *v31; // r9
  const wchar_t *v32; // r9
  unsigned int v33; // eax
  unsigned __int8 v34[4]; // [rsp+40h] [rbp-58h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+44h] [rbp-54h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-50h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-48h] BYREF
  __int64 ThreadInformation; // [rsp+A0h] [rbp+8h] BYREF

  v34[0] = 0;
  v5 = *(_QWORD *)a1;
  TokenHandle = 0;
  NumberOfBytesTransferred = 0;
  v6 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 48));
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v28 = L"True";
    if ( !*((_DWORD *)a1 + 5) )
      v28 = L"False";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 375, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, v28);
    v10 = WPP_GLOBAL_Control;
  }
  v11 = *((_QWORD *)a1 + 1);
  if ( !*(_BYTE *)(v11 + 308) )
  {
    v24 = *a2;
    if ( *a2 != qword_18019AB58 && v24 != qword_18019AB50 && v24 != qword_18019AB48 )
    {
      if ( v10 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x400000) != 0 )
        WPP_SF_Dd(*((_QWORD *)v10 + 2), 377, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, a2->LowPart, a2->HighPart);
      return;
    }
    v6 = 1;
    *(_WORD *)(v11 + 308) = 1;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        376,
        WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
        a2->LowPart,
        a2->HighPart);
    }
  }
  v12 = 1;
  v13 = 0;
  LOBYTE(ThreadInformation) = 0;
  while ( 1 )
  {
    if ( v12 > 3 )
      goto LABEL_17;
    if ( v12 == 1 )
      goto LABEL_15;
    v14 = 32;
    if ( v12 != 2 )
      v14 = 24;
    v15 = *(_QWORD *)(v14 + *(_QWORD *)a1);
    if ( v6 )
    {
      if ( !*(_WORD *)(v15 + 40) )
      {
        v29 = TokenHandle;
        if ( !TokenHandle )
        {
          IsImpersonated = CredpEnsureUserIsImpersonated(a2, v34);
          if ( IsImpersonated < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            {
              goto LABEL_17;
            }
            v23 = 378;
            goto LABEL_40;
          }
          LOBYTE(ThreadInformation) = 1;
          IsImpersonated = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
          if ( IsImpersonated < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            {
              goto LABEL_17;
            }
            v23 = 379;
            goto LABEL_40;
          }
          v29 = TokenHandle;
        }
        IsImpersonated = CredpQueryUserApplicationDataPath((struct _CREDENTIAL_SET *)v15, v12, v29);
        if ( IsImpersonated < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          {
            goto LABEL_17;
          }
          v23 = 380;
          goto LABEL_40;
        }
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          v31 = L"enterprise";
          if ( v12 != 3 )
            v31 = L"local";
          WPP_SF_SDDS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v30,
            (unsigned int)&WPP_GLOBAL_Control,
            (_DWORD)v31,
            a2->LowPart,
            a2->HighPart,
            v15 + 40);
        }
        *(_BYTE *)(v15 + 25) = 1;
      }
      v13 = ThreadInformation;
    }
    if ( !*(_BYTE *)(v15 + 24) && *(_BYTE *)(v15 + 25) )
    {
      if ( v13 )
      {
LABEL_52:
        *(_BYTE *)(v15 + 24) = 1;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          v32 = L"enterprise";
          if ( v12 != 3 )
            v32 = L"local";
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 383, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, v32);
        }
        if ( !v6 && !DisableStorageMonitoring && !*(_QWORD *)(v15 + 32) )
        {
          v33 = CredpSetupStorageChangeNotification((struct _CREDENTIAL_SET *)v15, v12, (void **)(v15 + 32));
          if ( v33 )
          {
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 384, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, v33);
            }
          }
        }
        CredSet = CredpReadCredSet(a2, a1, v12, 0, a3, a4);
        if ( CredSet < 0 )
        {
          *(_BYTE *)(v15 + 24) = 0;
          *(_BYTE *)(v15 + 25) = CredSet == -1073741420;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            v27 = 385;
LABEL_89:
            WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, (unsigned int)CredSet);
            goto LABEL_15;
          }
        }
        goto LABEL_15;
      }
      IsImpersonated = CredpEnsureUserIsImpersonated(a2, v34);
      if ( IsImpersonated >= 0 )
      {
        v13 = 1;
        LOBYTE(ThreadInformation) = 1;
        goto LABEL_52;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      {
        goto LABEL_17;
      }
      v23 = 382;
LABEL_40:
      WPP_SF_d(*((_QWORD *)v18 + 2), v23, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, (unsigned int)IsImpersonated);
      goto LABEL_17;
    }
    v16 = *(void **)(v15 + 32);
    if ( !v16 )
      goto LABEL_15;
    if ( *(_BYTE *)(v15 + 27) )
      goto LABEL_17;
    v17 = WaitForSingleObject(v16, 0);
    if ( !v17 )
      break;
    if ( v17 != 258 )
    {
      CredSet = GetLastError();
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v27 = 392;
        goto LABEL_89;
      }
    }
LABEL_15:
    ++v12;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    v22 = L"enterprise";
    if ( v12 != 3 )
      v22 = L"local";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 386, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, v22);
  }
  if ( !v13 )
  {
    IsImpersonated = CredpEnsureUserIsImpersonated(a2, v34);
    if ( IsImpersonated >= 0 )
    {
      LOBYTE(ThreadInformation) = 1;
      goto LABEL_23;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
    {
      goto LABEL_17;
    }
    v23 = 387;
    goto LABEL_40;
  }
  do
  {
LABEL_23:
    memset(&Overlapped, 0, sizeof(Overlapped));
    if ( !ReadDirectoryChangesW(*(HANDLE *)(v15 + 32), 0, 0, 0, 0x19u, 0, &Overlapped, 0) )
    {
      IsImpersonated = GetLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v23 = 388;
        goto LABEL_40;
      }
      goto LABEL_17;
    }
  }
  while ( GetOverlappedResult(*(HANDLE *)(v15 + 32), &Overlapped, &NumberOfBytesTransferred, 0) );
  IsImpersonated = GetLastError();
  if ( IsImpersonated == 996 )
  {
    CancelIo(*(HANDLE *)(v15 + 32));
    if ( FindNextChangeNotification(*(HANDLE *)(v15 + 32)) )
    {
      v20 = 0;
      if ( !*(_BYTE *)(v15 + 24) )
      {
        v20 = 1;
        *(_BYTE *)(v15 + 24) = 1;
      }
      v21 = CredpReadCredSet(a2, a1, v12, v20 ^ 1u, a3, a4);
      if ( v21 >= 0 )
        goto LABEL_30;
      if ( v20 )
        *(_BYTE *)(v15 + 24) = 0;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          391,
          WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (unsigned int)v21);
LABEL_30:
        v13 = ThreadInformation;
        goto LABEL_15;
      }
      v13 = ThreadInformation;
      goto LABEL_15;
    }
    IsImpersonated = GetLastError();
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v23 = 389;
      goto LABEL_40;
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v23 = 390;
      goto LABEL_40;
    }
  }
LABEL_17:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( v34[0] )
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
}

```

## disassembly

```asm
0x180040af0  mov     [rsp+arg_18], rsi
0x180040af5  push    rdi
0x180040af6  push    r12
0x180040af8  push    r13
0x180040afa  push    r14
0x180040afc  push    r15
0x180040afe  sub     rsp, 70h
0x180040b02  mov     rsi, rcx
0x180040b05  mov     [rsp+98h+var_58], 0
0x180040b0a  mov     rcx, [rcx]
0x180040b0d  xor     edi, edi
0x180040b0f  xorps   xmm0, xmm0
0x180040b12  mov     [rsp+98h+TokenHandle], rdi
0x180040b17  add     rcx, 30h ; '0'; CriticalSection
0x180040b1b  mov     [rsp+98h+NumberOfBytesTransferred], edi
0x180040b1f  xor     r14b, r14b
0x180040b22  mov     r12d, r9d
0x180040b25  mov     r13, r8
0x180040b28  mov     r15, rdx
0x180040b2b  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x180040b30  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x180040b35  call    cs:__imp_RtlEnterCriticalSection
0x180040b3c  nop     dword ptr [rax+rax+00h]
0x180040b41  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b48  lea     r8, WPP_GLOBAL_Control
0x180040b4f  cmp     rcx, r8
0x180040b52  jz      short loc_180040B61
0x180040b54  test    dword ptr [rcx+1Ch], 200h
0x180040b5b  jnz     loc_180040FA2
0x180040b61  mov     rdx, [rsi+8]
0x180040b65  cmp     [rdx+134h], dil
0x180040b6c  jz      loc_180040E2A
0x180040b72  mov     [rsp+98h+arg_8], rbx
0x180040b7a  lea     rdx, aLocal; "local"
0x180040b81  mov     [rsp+98h+arg_10], rbp
0x180040b89  mov     ebx, 1
0x180040b8e  xor     bpl, bpl
0x180040b91  mov     eax, 18h
0x180040b96  mov     byte ptr [rsp+98h+ThreadInformation], bpl
0x180040b9e  cmp     ebx, 3
0x180040ba1  ja      loc_180040C2C
0x180040ba7  cmp     ebx, 1
0x180040baa  jz      short loc_180040C11
0x180040bac  cmp     ebx, 2
0x180040baf  mov     ecx, 20h ; ' '
0x180040bb4  cmovnz  rcx, rax
0x180040bb8  mov     rax, [rsi]
0x180040bbb  mov     rdi, [rcx+rax]
0x180040bbf  test    r14b, r14b
0x180040bc2  jnz     loc_180040FDF
0x180040bc8  cmp     byte ptr [rdi+18h], 0
0x180040bcc  jz      loc_180040ED8
0x180040bd2  mov     rcx, [rdi+20h]; hHandle
0x180040bd6  test    rcx, rcx
0x180040bd9  jz      short loc_180040C0C
0x180040bdb  cmp     byte ptr [rdi+1Bh], 0
0x180040bdf  jnz     short loc_180040C2C
0x180040be1  xor     edx, edx; dwMilliseconds
0x180040be3  call    cs:__imp_WaitForSingleObject
0x180040bea  nop     dword ptr [rax+rax+00h]
0x180040bef  test    eax, eax
0x180040bf1  jz      short loc_180040C6C
0x180040bf3  cmp     eax, 102h
0x180040bf8  jnz     loc_1800411B6
0x180040bfe  lea     r8, WPP_GLOBAL_Control
0x180040c05  lea     rdx, aLocal; "local"
0x180040c0c  mov     eax, 18h
0x180040c11  inc     ebx
0x180040c13  jmp     short loc_180040B9E
0x180040c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c1c  lea     rdx, WPP_GLOBAL_Control
0x180040c23  cmp     rcx, rdx
0x180040c26  jnz     loc_180041329
0x180040c2c  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x180040c31  mov     rbp, [rsp+98h+arg_10]
0x180040c39  mov     rbx, [rsp+98h+arg_8]
0x180040c41  test    rcx, rcx
0x180040c44  jnz     loc_180041340
0x180040c4a  cmp     [rsp+98h+var_58], 0
0x180040c4f  jnz     loc_180041351
0x180040c55  mov     rsi, [rsp+98h+arg_18]
0x180040c5d  add     rsp, 70h
0x180040c61  pop     r15
0x180040c63  pop     r14
0x180040c65  pop     r13
0x180040c67  pop     r12
0x180040c69  pop     rdi
0x180040c6a  retn
0x180040c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c73  lea     rax, WPP_GLOBAL_Control
0x180040c7a  cmp     rcx, rax
0x180040c7d  jnz     loc_180040DA1
0x180040c83  test    bpl, bpl
0x180040c86  jz      loc_180040D7F
0x180040c8c  xorps   xmm0, xmm0
0x180040c8f  mov     [rsp+98h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180040c98  lea     rax, [rsp+98h+Overlapped]
0x180040c9d  xor     r9d, r9d; bWatchSubtree
0x180040ca0  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x180040ca5  xor     r8d, r8d; nBufferLength
0x180040ca8  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x180040cad  mov     [rsp+98h+lpBytesReturned], 0; lpBytesReturned
0x180040cb6  xor     edx, edx; lpBuffer
0x180040cb8  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x180040cbd  mov     rcx, [rdi+20h]; hDirectory
0x180040cc1  mov     [rsp+98h+dwNotifyFilter], 19h; dwNotifyFilter
0x180040cc9  call    cs:__imp_ReadDirectoryChangesW
0x180040cd0  nop     dword ptr [rax+rax+00h]
0x180040cd5  test    eax, eax
0x180040cd7  jz      loc_180040DDD
0x180040cdd  mov     rcx, [rdi+20h]; hFile
0x180040ce1  lea     r8, [rsp+98h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180040ce6  xor     r9d, r9d; bWait
0x180040ce9  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x180040cee  call    cs:__imp_GetOverlappedResult
0x180040cf5  nop     dword ptr [rax+rax+00h]
0x180040cfa  test    eax, eax
0x180040cfc  jnz     short loc_180040C8C
0x180040cfe  call    cs:__imp_GetLastError
0x180040d05  nop     dword ptr [rax+rax+00h]
0x180040d0a  cmp     eax, 3E4h
0x180040d0f  jnz     loc_180040C15
0x180040d15  mov     rcx, [rdi+20h]; hFile
0x180040d19  call    cs:__imp_CancelIo
0x180040d20  nop     dword ptr [rax+rax+00h]
0x180040d25  mov     rcx, [rdi+20h]; hChangeHandle
0x180040d29  call    cs:__imp_FindNextChangeNotification
0x180040d30  nop     dword ptr [rax+rax+00h]
0x180040d35  test    eax, eax
0x180040d37  jz      loc_180040F68
0x180040d3d  xor     bpl, bpl
0x180040d40  cmp     [rdi+18h], bpl
0x180040d44  jz      loc_1800411E8
0x180040d4a  movzx   r9d, bpl
0x180040d4e  mov     dword ptr [rsp+98h+lpBytesReturned], r12d; unsigned int
0x180040d53  xor     r9b, 1; unsigned __int8
0x180040d57  mov     qword ptr [rsp+98h+dwNotifyFilter], r13; unsigned __int16 **
0x180040d5c  mov     r8d, ebx; unsigned int
0x180040d5f  mov     rdx, rsi; struct _CREDENTIAL_SETS *
0x180040d62  mov     rcx, r15; struct _LUID *
0x180040d65  call    ?CredpReadCredSet@@YAJPEAU_LUID@@PEAU_CREDENTIAL_SETS@@KEPEAPEBGK@Z; CredpReadCredSet(_LUID *,_CREDENTIAL_SETS *,ulong,uchar,ushort const * *,ulong)
0x180040d6a  test    eax, eax
0x180040d6c  js      loc_1800411F4
0x180040d72  movzx   ebp, byte ptr [rsp+98h+ThreadInformation]
0x180040d7a  jmp     loc_180040BFE
0x180040d7f  lea     rdx, [rsp+98h+var_58]; unsigned __int8 *
0x180040d84  mov     rcx, r15; struct _LUID *
0x180040d87  call    ?CredpEnsureUserIsImpersonated@@YAJPEAU_LUID@@PEAE@Z; CredpEnsureUserIsImpersonated(_LUID *,uchar *)
0x180040d8c  test    eax, eax
0x180040d8e  js      loc_1800412FB
0x180040d94  mov     byte ptr [rsp+98h+ThreadInformation], 1
0x180040d9c  jmp     loc_180040C8C
0x180040da1  test    dword ptr [rcx+1Ch], 400000h
0x180040da8  jz      loc_180040C83
0x180040dae  mov     rcx, [rcx+10h]
0x180040db2  lea     rax, aLocal; "local"
0x180040db9  cmp     ebx, 3
0x180040dbc  lea     r9, aEnterprise; "enterprise"
0x180040dc3  mov     edx, 182h
0x180040dc8  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180040dcf  cmovnz  r9, rax
0x180040dd3  call    WPP_SF_S
0x180040dd8  jmp     loc_180040C83
0x180040ddd  call    cs:__imp_GetLastError
0x180040de4  nop     dword ptr [rax+rax+00h]
0x180040de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180040df0  lea     rdx, WPP_GLOBAL_Control
0x180040df7  cmp     rcx, rdx
0x180040dfa  jz      loc_180040C2C
0x180040e00  test    dword ptr [rcx+1Ch], 200h
0x180040e07  jz      loc_180040C2C
0x180040e0d  mov     edx, 184h
0x180040e12  mov     rcx, [rcx+10h]
0x180040e16  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180040e1d  mov     r9d, eax
0x180040e20  call    WPP_SF_d
0x180040e25  jmp     loc_180040C2C
0x180040e2a  mov     rax, [r15]
0x180040e2d  cmp     rax, cs:qword_18019AB58
0x180040e34  jnz     short loc_180040E8B
0x180040e36  mov     r14b, 1
0x180040e39  mov     word ptr [rdx+134h], 1
0x180040e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e49  cmp     rcx, r8
0x180040e4c  jz      loc_180040B72
0x180040e52  test    dword ptr [rcx+1Ch], 400000h
0x180040e59  jz      loc_180040B72
0x180040e5f  mov     eax, [r15+4]
0x180040e63  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180040e6a  mov     r9d, [r15]
0x180040e6d  mov     edx, 178h
0x180040e72  mov     rcx, [rcx+10h]
0x180040e76  mov     [rsp+98h+dwNotifyFilter], eax
0x180040e7a  call    WPP_SF_Dd
0x180040e7f  lea     r8, WPP_GLOBAL_Control
0x180040e86  jmp     loc_180040B72
0x180040e8b  cmp     rax, cs:qword_18019AB50
0x180040e92  jz      short loc_180040E36
0x180040e94  cmp     rax, cs:qword_18019AB48
0x180040e9b  jz      short loc_180040E36
0x180040e9d  cmp     rcx, r8
0x180040ea0  jz      loc_180040C55
0x180040ea6  test    dword ptr [rcx+1Ch], 400000h
0x180040ead  jz      loc_180040C55
0x180040eb3  mov     eax, [r15+4]
0x180040eb7  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180040ebe  mov     r9d, [r15]
0x180040ec1  mov     edx, 179h
0x180040ec6  mov     rcx, [rcx+10h]
0x180040eca  mov     [rsp+98h+dwNotifyFilter], eax
0x180040ece  call    WPP_SF_Dd
0x180040ed3  jmp     loc_180040C55
0x180040ed8  cmp     byte ptr [rdi+19h], 0
0x180040edc  jz      loc_180040BD2
0x180040ee2  test    bpl, bpl
0x180040ee5  jz      loc_1800410C2
0x180040eeb  mov     byte ptr [rdi+18h], 1
0x180040eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ef6  cmp     rcx, r8
0x180040ef9  jnz     loc_1800410F5
0x180040eff  test    r14b, r14b
0x180040f02  jz      loc_18004112A
0x180040f08  mov     dword ptr [rsp+98h+lpBytesReturned], r12d; unsigned int
0x180040f0d  xor     r9d, r9d; unsigned __int8
0x180040f10  mov     r8d, ebx; unsigned int
0x180040f13  mov     qword ptr [rsp+98h+dwNotifyFilter], r13; unsigned __int16 **
0x180040f18  mov     rdx, rsi; struct _CREDENTIAL_SETS *
0x180040f1b  mov     rcx, r15; struct _LUID *
0x180040f1e  call    ?CredpReadCredSet@@YAJPEAU_LUID@@PEAU_CREDENTIAL_SETS@@KEPEAPEBGK@Z; CredpReadCredSet(_LUID *,_CREDENTIAL_SETS *,ulong,uchar,ushort const * *,ulong)
0x180040f23  test    eax, eax
0x180040f25  jns     loc_180040BFE
0x180040f2b  mov     byte ptr [rdi+18h], 0
0x180040f2f  cmp     eax, 0C0000194h
0x180040f34  lea     r8, WPP_GLOBAL_Control
0x180040f3b  setz    cl
0x180040f3e  mov     [rdi+19h], cl
0x180040f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f48  cmp     rcx, r8
0x180040f4b  jz      loc_180040C05
0x180040f51  test    dword ptr [rcx+1Ch], 200h
0x180040f58  jz      loc_180040C05
0x180040f5e  mov     edx, 181h
0x180040f63  jmp     loc_18004119E
0x180040f68  call    cs:__imp_GetLastError
0x180040f6f  nop     dword ptr [rax+rax+00h]
0x180040f74  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f7b  lea     rdx, WPP_GLOBAL_Control
0x180040f82  cmp     rcx, rdx
0x180040f85  jz      loc_180040C2C
0x180040f8b  test    dword ptr [rcx+1Ch], 200h
0x180040f92  jz      loc_180040C2C
0x180040f98  mov     edx, 185h
0x180040f9d  jmp     loc_180040E12
0x180040fa2  cmp     [rsi+14h], edi
0x180040fa5  lea     rax, aFalse_0; "False"
0x180040fac  mov     rcx, [rcx+10h]
0x180040fb0  lea     r9, aTrue; "True"
0x180040fb7  cmovz   r9, rax
0x180040fbb  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180040fc2  mov     edx, 177h
0x180040fc7  call    WPP_SF_S
0x180040fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fd3  lea     r8, WPP_GLOBAL_Control
0x180040fda  jmp     loc_180040B61
0x180040fdf  lea     rbp, [rdi+28h]
0x180040fe3  xor     eax, eax
0x180040fe5  cmp     ax, [rbp+0]
0x180040fe9  jnz     loc_1800410B5
0x180040fef  mov     r8, [rsp+98h+TokenHandle]
0x180040ff4  test    r8, r8
0x180040ff7  jnz     short loc_180041043
0x180040ff9  lea     rdx, [rsp+98h+var_58]; unsigned __int8 *
0x180040ffe  mov     rcx, r15; struct _LUID *
0x180041001  call    ?CredpEnsureUserIsImpersonated@@YAJPEAU_LUID@@PEAE@Z; CredpEnsureUserIsImpersonated(_LUID *,uchar *)
0x180041006  test    eax, eax
0x180041008  js      loc_180041271
0x18004100e  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x180041013  mov     byte ptr [rsp+98h+ThreadInformation], 1
0x18004101b  mov     r8b, 1; OpenAsSelf
0x18004101e  mov     edx, 0Ch; DesiredAccess
0x180041023  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18004102a  call    cs:__imp_NtOpenThreadToken
0x180041031  nop     dword ptr [rax+rax+00h]
0x180041036  test    eax, eax
0x180041038  js      loc_180041243
0x18004103e  mov     r8, [rsp+98h+TokenHandle]; void *
0x180041043  mov     edx, ebx; unsigned int
0x180041045  mov     rcx, rdi; struct _CREDENTIAL_SET *
0x180041048  call    ?CredpQueryUserApplicationDataPath@@YAJPEAU_CREDENTIAL_SET@@KPEAX@Z; CredpQueryUserApplicationDataPath(_CREDENTIAL_SET *,ulong,void *)
0x18004104d  test    eax, eax
0x18004104f  js      loc_18004129F
0x180041055  mov     rcx, cs:WPP_GLOBAL_Control
0x18004105c  lea     r8, WPP_GLOBAL_Control
0x180041063  cmp     rcx, r8
0x180041066  jz      short loc_1800410AA
0x180041068  test    dword ptr [rcx+1Ch], 400000h
0x18004106f  jz      short loc_1800410AA
0x180041071  mov     rcx, [rcx+10h]
0x180041075  lea     rax, aLocal; "local"
0x18004107c  cmp     ebx, 3
  ... truncated ...
```
