# DsRolepClearLsaSecretAutoLogonPassword

- ea: `0x180013b1c`
- end: `0x180013c47`
- name: `DsRolepClearLsaSecretAutoLogonPassword`
- size: `299`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013c50`

## callees

- `0x180013b1c`

## import_xrefs

- `LSASRV!LsarOpenPolicy` at `0x180013b63`
- `LSASRV!LsarOpenPolicy` at `0x180013b63`
- `LSASRV!LsarStorePrivateData` at `0x180013ba0`
- `LSASRV!LsarStorePrivateData` at `0x180013bd5`
- `LSASRV!LsarStorePrivateData` at `0x180013c05`
- `LSASRV!LsarStorePrivateData` at `0x180013ba0`
- `LSASRV!LsarStorePrivateData` at `0x180013bd5`
- `LSASRV!LsarStorePrivateData` at `0x180013c05`
- `LSASRV!LsarRetrievePrivateData` at `0x180013bb8`
- `LSASRV!LsarRetrievePrivateData` at `0x180013bb8`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180013c11`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180013c11`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180013c22`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180013c22`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013c31`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013c31`

## pseudocode

```c
__int64 DsRolepClearLsaSecretAutoLogonPassword()
{
  NTSTATUS v0; // eax
  ULONG v1; // ebx
  __int64 v2; // r8
  _BYTE *v3; // rdx
  int v5; // [rsp+20h] [rbp-50h] BYREF
  const WCHAR *v6; // [rsp+28h] [rbp-48h]
  int v7; // [rsp+30h] [rbp-40h] BYREF
  const WCHAR *v8; // [rsp+38h] [rbp-38h]
  _OWORD v9[3]; // [rsp+40h] [rbp-30h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+80h] [rbp+10h] BYREF
  PVOID Buffer; // [rsp+88h] [rbp+18h] BYREF

  ObjectHandle = 0;
  Buffer = 0;
  memset(v9, 0, sizeof(v9));
  v0 = ((__int64 (__fastcall *)(_QWORD, _OWORD *, __int64, LSA_HANDLE *, _QWORD, _QWORD, _QWORD, _QWORD))LsarOpenPolicy)(
         0,
         v9,
         131110,
         &ObjectHandle,
         0,
         0,
         0,
         0);
  if ( v0 < 0 )
    goto LABEL_9;
  v6 = L"DefaultPassword";
  v5 = 2097182;
  v8 = L"DcpromoOld_DefaultPassword";
  v7 = 3538996;
  v0 = LsarStorePrivateData(ObjectHandle, &v5, 0);
  if ( v0 < 0 )
    goto LABEL_9;
  v1 = 0;
  v0 = LsarRetrievePrivateData(ObjectHandle, &v7, &Buffer);
  if ( v0 != -1073741772 )
  {
    if ( v0 < 0 )
      goto LABEL_9;
    v0 = LsarStorePrivateData(ObjectHandle, &v5, Buffer);
    v2 = *(unsigned int *)Buffer;
    v3 = (_BYTE *)*((_QWORD *)Buffer + 1);
    if ( *(_DWORD *)Buffer )
    {
      do
      {
        *v3++ = 0;
        --v2;
      }
      while ( v2 );
    }
    if ( v0 < 0 || (v0 = LsarStorePrivateData(ObjectHandle, &v7, 0), v0 < 0) )
LABEL_9:
      v1 = LsaNtStatusToWinError(v0);
  }
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  return v1;
}

```

## disassembly

```asm
0x180013b1c  mov     [rsp-8+arg_10], rbx
0x180013b21  push    rbp
0x180013b22  mov     rbp, rsp
0x180013b25  sub     rsp, 70h
0x180013b29  xorps   xmm0, xmm0
0x180013b2c  mov     [rbp+ObjectHandle], 0
0x180013b34  xorps   xmm1, xmm1
0x180013b37  mov     [rbp+Buffer], 0
0x180013b3f  lea     r9, [rbp+ObjectHandle]
0x180013b43  mov     r8d, 20026h
0x180013b49  lea     rdx, [rbp+var_30]
0x180013b4d  xor     ecx, ecx
0x180013b4f  movups  [rbp+var_50], xmm0
0x180013b53  movups  [rbp+var_40], xmm1
0x180013b57  movups  [rbp+var_30], xmm0
0x180013b5b  movups  [rbp+var_20], xmm0
0x180013b5f  movups  [rbp+var_10], xmm0
0x180013b63  call    cs:__imp_LsarOpenPolicy
0x180013b69  test    eax, eax
0x180013b6b  js      loc_180013C0F
0x180013b71  mov     rcx, [rbp+ObjectHandle]
0x180013b75  lea     rax, aDefaultpasswor; "DefaultPassword"
0x180013b7c  mov     qword ptr [rbp+var_50+8], rax
0x180013b80  lea     rdx, [rbp+var_50]
0x180013b84  lea     rax, aDcpromooldDefa_0; "DcpromoOld_DefaultPassword"
0x180013b8b  mov     dword ptr [rbp+var_50], 20001Eh
0x180013b92  xor     r8d, r8d
0x180013b95  mov     qword ptr [rbp+var_40+8], rax
0x180013b99  mov     dword ptr [rbp+var_40], 360034h
0x180013ba0  call    cs:__imp_LsarStorePrivateData
0x180013ba6  test    eax, eax
0x180013ba8  js      short loc_180013C0F
0x180013baa  mov     rcx, [rbp+ObjectHandle]
0x180013bae  lea     r8, [rbp+Buffer]
0x180013bb2  lea     rdx, [rbp+var_40]
0x180013bb6  xor     ebx, ebx
0x180013bb8  call    cs:__imp_LsarRetrievePrivateData
0x180013bbe  cmp     eax, 0C0000034h
0x180013bc3  jz      short loc_180013C19
0x180013bc5  test    eax, eax
0x180013bc7  js      short loc_180013C0F
0x180013bc9  mov     r8, [rbp+Buffer]
0x180013bcd  lea     rdx, [rbp+var_50]
0x180013bd1  mov     rcx, [rbp+ObjectHandle]
0x180013bd5  call    cs:__imp_LsarStorePrivateData
0x180013bdb  mov     rcx, [rbp+Buffer]
0x180013bdf  mov     r8d, [rcx]
0x180013be2  mov     rdx, [rcx+8]
0x180013be6  test    r8, r8
0x180013be9  jz      short loc_180013BF6
0x180013beb  mov     [rdx], bl
0x180013bed  inc     rdx
0x180013bf0  sub     r8, 1
0x180013bf4  jnz     short loc_180013BEB
0x180013bf6  test    eax, eax
0x180013bf8  js      short loc_180013C0F
0x180013bfa  mov     rcx, [rbp+ObjectHandle]
0x180013bfe  lea     rdx, [rbp+var_40]
0x180013c02  xor     r8d, r8d
0x180013c05  call    cs:__imp_LsarStorePrivateData
0x180013c0b  test    eax, eax
0x180013c0d  jns     short loc_180013C19
0x180013c0f  mov     ecx, eax; Status
0x180013c11  call    cs:__imp_LsaNtStatusToWinError
0x180013c17  mov     ebx, eax
0x180013c19  mov     rcx, [rbp+ObjectHandle]; ObjectHandle
0x180013c1d  test    rcx, rcx
0x180013c20  jz      short loc_180013C28
0x180013c22  call    cs:__imp_LsaClose
0x180013c28  mov     rcx, [rbp+Buffer]; Buffer
0x180013c2c  test    rcx, rcx
0x180013c2f  jz      short loc_180013C37
0x180013c31  call    cs:__imp_LsaFreeMemory
0x180013c37  mov     eax, ebx
0x180013c39  mov     rbx, [rsp+70h+arg_10]
0x180013c41  add     rsp, 70h
0x180013c45  pop     rbp
0x180013c46  retn
```
