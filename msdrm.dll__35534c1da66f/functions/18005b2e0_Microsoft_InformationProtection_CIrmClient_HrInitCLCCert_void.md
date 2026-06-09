# Microsoft::InformationProtection::CIrmClient::HrInitCLCCert(void)

- ea: `0x18005b2e0`
- end: `0x18005b493`
- name: `?HrInitCLCCert@CIrmClient@InformationProtection@Microsoft@@AEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(Microsoft::InformationProtection::CIrmClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b0a0`

## callees

- `0x18001a680`
- `0x18005a9cc`
- `0x18005aadc`
- `0x18005af28`
- `0x18005b2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b3fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b3fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b39b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b39b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b44c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b44c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b457`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b465`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b465`

## pseudocode

```c
__int64 __fastcall Microsoft::InformationProtection::CIrmClient::HrInitCLCCert(
        Microsoft::InformationProtection::CIrmClient *this)
{
  __int128 v1; // rdi
  int Cert; // eax
  unsigned int v3; // ebx
  unsigned __int16 **v4; // r9
  int ServiceLocation; // eax
  PWSTR wszURL; // r14
  DRMHSESSION v7; // ecx
  HRESULT v8; // eax
  __int64 v9; // r8
  HANDLE ProcessHeap; // rax
  __int128 pvContext; // [rsp+40h] [rbp-58h] BYREF
  __int64 v13; // [rsp+50h] [rbp-48h]
  PWSTR v14; // [rsp+A0h] [rbp+8h] BYREF

  *(_QWORD *)&v1 = this;
  Microsoft::InformationProtection::DebugLog(
    (Microsoft::InformationProtection *)L"%S Entered",
    "Microsoft::InformationProtection::CIrmClient::HrInitCLCCert");
  v14 = 0;
  v13 = 0;
  pvContext = 0;
  if ( !*(_QWORD *)(v1 + 48) && *(_DWORD *)(v1 + 16) )
  {
    Cert = Microsoft::InformationProtection::CIrmClient::HrGetCert(
             (Microsoft::InformationProtection::CIrmClient *)v1,
             0x200u,
             (unsigned __int16 **)(v1 + 48));
    v3 = Cert;
    if ( Cert >= 0 )
    {
LABEL_19:
      Microsoft::InformationProtection::DebugLog(
        (Microsoft::InformationProtection *)L"%S Exited with hr = 0x%x",
        "Microsoft::InformationProtection::CIrmClient::HrInitCLCCert",
        v3);
      return v3;
    }
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmClient::HrInitCLCCert",
      255,
      (unsigned int)Cert);
    ServiceLocation = Microsoft::InformationProtection::HrFindServiceLocation(
                        *(_DWORD *)(v1 + 16),
                        8u,
                        (unsigned int)&v14,
                        v4);
    wszURL = v14;
    v3 = ServiceLocation;
    if ( ServiceLocation < 0 )
    {
LABEL_17:
      if ( wszURL )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, wszURL);
      }
      goto LABEL_19;
    }
    *((_QWORD *)&v1 + 1) = CreateEventW(0, 0, 0, 0);
    if ( !*((_QWORD *)&v1 + 1) )
    {
      v3 = -2147467259;
      goto LABEL_17;
    }
    v7 = *(_DWORD *)(v1 + 16);
    pvContext = v1;
    v8 = DRMAcquireLicense(v7, 0, 0, 0, 0, wszURL, &pvContext);
    v3 = v8;
    if ( v8 >= 0 )
    {
      if ( WaitForSingleObject(*((HANDLE *)&v1 + 1), 0xEA60u) )
      {
        v3 = -2147467259;
        goto LABEL_15;
      }
      v3 = v13;
      if ( (int)v13 < 0
        || (v8 = Microsoft::InformationProtection::CIrmClient::HrGetCert(
                   (Microsoft::InformationProtection::CIrmClient *)v1,
                   0x200u,
                   (unsigned __int16 **)(v1 + 48)),
            v3 = v8,
            v8 >= 0) )
      {
LABEL_15:
        if ( *((_QWORD *)&v1 + 1) != -1 )
          CloseHandle(*((HANDLE *)&v1 + 1));
        goto LABEL_17;
      }
      v9 = 291;
    }
    else
    {
      v9 = 277;
    }
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmClient::HrInitCLCCert",
      v9,
      (unsigned int)v8);
    goto LABEL_15;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18005b2e0  push    rbx
0x18005b2e2  push    rbp
0x18005b2e3  push    rsi
0x18005b2e4  push    rdi
0x18005b2e5  push    r12
0x18005b2e7  push    r14
0x18005b2e9  sub     rsp, 68h
0x18005b2ed  mov     rdi, rcx
0x18005b2f0  lea     r12, aMicrosoftInfor_21; "Microsoft::InformationProtection::CIrmC"...
0x18005b2f7  mov     rdx, r12; unsigned __int16 *
0x18005b2fa  lea     rcx, aSEntered; "%S Entered"
0x18005b301  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005b306  xor     eax, eax
0x18005b308  mov     [rsp+98h+arg_0], 0
0x18005b314  lea     rbp, [rdi+30h]
0x18005b318  mov     [rsp+98h+var_48], rax
0x18005b31d  xorps   xmm0, xmm0
0x18005b320  movups  [rsp+98h+var_58], xmm0
0x18005b325  cmp     [rbp+0], rax
0x18005b329  jnz     loc_18005B481
0x18005b32f  cmp     [rdi+10h], eax
0x18005b332  jz      loc_18005B481
0x18005b338  mov     r8, rbp; unsigned __int16 **
0x18005b33b  mov     edx, 200h; unsigned int
0x18005b340  mov     rcx, rdi; this
0x18005b343  call    ?HrGetCert@CIrmClient@InformationProtection@Microsoft@@AEAAJKPEAPEAG@Z; Microsoft::InformationProtection::CIrmClient::HrGetCert(ulong,ushort * *)
0x18005b348  mov     ebx, eax
0x18005b34a  test    eax, eax
0x18005b34c  jns     loc_18005B46B
0x18005b352  mov     r9d, eax
0x18005b355  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005b35c  mov     r8d, 0FFh
0x18005b362  mov     rdx, r12; unsigned __int16 *
0x18005b365  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005b36a  mov     ecx, [rdi+10h]; hClient
0x18005b36d  lea     r8, [rsp+98h+arg_0]; unsigned int
0x18005b375  mov     edx, 8; uServiceType
0x18005b37a  call    ?HrFindServiceLocation@InformationProtection@Microsoft@@YAJKIPEAPEAG@Z; Microsoft::InformationProtection::HrFindServiceLocation(ulong,uint,ushort * *)
0x18005b37f  mov     r14, [rsp+98h+arg_0]
0x18005b387  mov     ebx, eax
0x18005b389  test    eax, eax
0x18005b38b  js      loc_18005B452
0x18005b391  xor     r9d, r9d; lpName
0x18005b394  xor     r8d, r8d; bInitialState
0x18005b397  xor     edx, edx; bManualReset
0x18005b399  xor     ecx, ecx; lpEventAttributes
0x18005b39b  call    cs:__imp_CreateEventW
0x18005b3a1  mov     rsi, rax
0x18005b3a4  test    rax, rax
0x18005b3a7  jnz     short loc_18005B3B3
0x18005b3a9  mov     ebx, 80004005h
0x18005b3ae  jmp     loc_18005B452
0x18005b3b3  mov     ecx, [rdi+10h]; hSession
0x18005b3b6  lea     rax, [rsp+98h+var_58]
0x18005b3bb  mov     [rsp+98h+pvContext], rax; pvContext
0x18005b3c0  xor     r9d, r9d; wszRequestedRights
0x18005b3c3  mov     [rsp+98h+wszURL], r14; wszURL
0x18005b3c8  xor     r8d, r8d; wszGroupIdentityCredential
0x18005b3cb  xor     edx, edx; uFlags
0x18005b3cd  mov     [rsp+98h+wszCustomData], 0; wszCustomData
0x18005b3d6  mov     qword ptr [rsp+98h+var_58], rdi
0x18005b3db  mov     qword ptr [rsp+98h+var_58+8], rsi
0x18005b3e0  call    DRMAcquireLicense
0x18005b3e5  mov     ebx, eax
0x18005b3e7  test    eax, eax
0x18005b3e9  jns     short loc_18005B3F3
0x18005b3eb  mov     r8d, 115h
0x18005b3f1  jmp     short loc_18005B431
0x18005b3f3  mov     edx, 0EA60h; dwMilliseconds
0x18005b3f8  mov     rcx, rsi; hHandle
0x18005b3fb  call    cs:__imp_WaitForSingleObject
0x18005b401  test    eax, eax
0x18005b403  jz      short loc_18005B40C
0x18005b405  mov     ebx, 80004005h
0x18005b40a  jmp     short loc_18005B443
0x18005b40c  mov     rbx, [rsp+98h+var_48]
0x18005b411  test    ebx, ebx
0x18005b413  js      short loc_18005B443
0x18005b415  mov     r8, rbp; unsigned __int16 **
0x18005b418  mov     edx, 200h; unsigned int
0x18005b41d  mov     rcx, rdi; this
0x18005b420  call    ?HrGetCert@CIrmClient@InformationProtection@Microsoft@@AEAAJKPEAPEAG@Z; Microsoft::InformationProtection::CIrmClient::HrGetCert(ulong,ushort * *)
0x18005b425  mov     ebx, eax
0x18005b427  test    eax, eax
0x18005b429  jns     short loc_18005B443
0x18005b42b  mov     r8d, 123h
0x18005b431  mov     r9d, eax
0x18005b434  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005b43b  mov     rdx, r12; unsigned __int16 *
0x18005b43e  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005b443  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005b447  jz      short loc_18005B452
0x18005b449  mov     rcx, rsi; hObject
0x18005b44c  call    cs:__imp_CloseHandle
0x18005b452  test    r14, r14
0x18005b455  jz      short loc_18005B46B
0x18005b457  call    cs:__imp_GetProcessHeap
0x18005b45d  mov     r8, r14; lpMem
0x18005b460  xor     edx, edx; dwFlags
0x18005b462  mov     rcx, rax; hHeap
0x18005b465  call    cs:__imp_HeapFree
0x18005b46b  mov     r8d, ebx
0x18005b46e  lea     rcx, aSExitedWithHr0; "%S Exited with hr = 0x%x"
0x18005b475  mov     rdx, r12; unsigned __int16 *
0x18005b478  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005b47d  mov     eax, ebx
0x18005b47f  jmp     short loc_18005B486
0x18005b481  mov     eax, 8000FFFFh
0x18005b486  add     rsp, 68h
0x18005b48a  pop     r14
0x18005b48c  pop     r12
0x18005b48e  pop     rdi
0x18005b48f  pop     rsi
0x18005b490  pop     rbp
0x18005b491  pop     rbx
0x18005b492  retn
```
