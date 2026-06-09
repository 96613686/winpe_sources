# DsRolepSaveUpgradePasswordForAutoLogonAsLsaSecret

- ea: `0x180014344`
- end: `0x18001451c`
- name: `DsRolepSaveUpgradePasswordForAutoLogonAsLsaSecret`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014524`

## callees

- `0x180014344`
- `0x180027ea4`
- `0x180027f68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800144ea`
- `LSASRV!LsarOpenPolicy` at `0x18001439e`
- `LSASRV!LsarOpenPolicy` at `0x18001439e`
- `LSASRV!LsarStorePrivateData` at `0x1800143fc`
- `LSASRV!LsarStorePrivateData` at `0x18001442d`
- `LSASRV!LsarStorePrivateData` at `0x18001449d`
- `LSASRV!LsarStorePrivateData` at `0x1800143fc`
- `LSASRV!LsarStorePrivateData` at `0x18001442d`
- `LSASRV!LsarStorePrivateData` at `0x18001449d`
- `LSASRV!LsarRetrievePrivateData` at `0x1800143df`
- `LSASRV!LsarRetrievePrivateData` at `0x1800143df`
- `LSASRV!LsapCrServerGetSessionKey` at `0x180014463`
- `LSASRV!LsapCrServerGetSessionKey` at `0x180014463`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800144ca`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800144ca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800144db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800144db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800144f9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800144f9`

## pseudocode

```c
__int64 __fastcall DsRolepSaveUpgradePasswordForAutoLogonAsLsaSecret(__int64 a1)
{
  unsigned int *v2; // rbx
  int SessionKey; // eax
  NTSTATUS v4; // ecx
  __int64 v5; // r8
  _BYTE *v6; // rdx
  __int64 v7; // rax
  ULONG v8; // edi
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // esi
  _BYTE *v13; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-39h] BYREF
  int v16; // [rsp+28h] [rbp-31h] BYREF
  const WCHAR *v17; // [rsp+30h] [rbp-29h]
  int v18; // [rsp+38h] [rbp-21h] BYREF
  const WCHAR *v19; // [rsp+40h] [rbp-19h]
  _DWORD v20[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v21; // [rsp+50h] [rbp-9h]
  _OWORD v22[5]; // [rsp+58h] [rbp-1h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+C8h] [rbp+6Fh] BYREF
  PVOID Buffer; // [rsp+D0h] [rbp+77h] BYREF
  unsigned int *v25; // [rsp+D8h] [rbp+7Fh] BYREF

  ObjectHandle = 0;
  Buffer = 0;
  v2 = 0;
  v25 = 0;
  memset(v22, 0, 48);
  SessionKey = ((__int64 (__fastcall *)(_QWORD, _OWORD *, __int64, LSA_HANDLE *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))LsarOpenPolicy)(
                 0,
                 v22,
                 131110,
                 &ObjectHandle,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0);
  if ( SessionKey < 0 )
    goto LABEL_2;
  v17 = L"DefaultPassword";
  v16 = 2097182;
  v19 = L"DcpromoOld_DefaultPassword";
  v18 = 3538996;
  SessionKey = LsarRetrievePrivateData(ObjectHandle, &v16, &Buffer);
  if ( SessionKey != -1073741772 )
  {
    if ( SessionKey < 0 )
      goto LABEL_2;
    SessionKey = LsarStorePrivateData(ObjectHandle, &v18, Buffer);
    v5 = *(unsigned int *)Buffer;
    v6 = (_BYTE *)*((_QWORD *)Buffer + 1);
    if ( *(_DWORD *)Buffer )
    {
      do
      {
        *v6++ = 0;
        --v5;
      }
      while ( v5 );
    }
    if ( SessionKey < 0 )
      goto LABEL_2;
    SessionKey = LsarStorePrivateData(ObjectHandle, &v16, 0);
    if ( SessionKey < 0 )
      goto LABEL_2;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  v21 = a1;
  v20[0] = 2 * (unsigned __int16)v7;
  v20[1] = v20[0] + 2;
  SessionKey = LsapCrServerGetSessionKey(ObjectHandle, &hMem);
  if ( SessionKey < 0 )
  {
LABEL_2:
    v4 = SessionKey;
LABEL_18:
    v8 = LsaNtStatusToWinError(v4);
    goto LABEL_19;
  }
  v8 = 0;
  v9 = LsapCrEncryptValue(v20, hMem, &v25);
  v2 = v25;
  if ( v9 >= 0 && v25 )
  {
    v10 = LsarStorePrivateData(ObjectHandle, &v16, v25);
    v11 = *v2;
    v12 = v10;
    v13 = (_BYTE *)*((_QWORD *)v2 + 1);
    if ( *v2 )
    {
      do
      {
        *v13++ = 0;
        --v11;
      }
      while ( v11 );
    }
    LsapCrFreeMemoryValue(v2);
    if ( v12 < 0 )
    {
      v4 = v12;
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  if ( hMem )
    LocalFree(hMem);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( v2 )
    LsapCrFreeMemoryValue(v2);
  return v8;
}

```

## disassembly

```asm
0x180014344  push    rbp
0x180014346  push    rbx
0x180014347  push    rsi
0x180014348  push    rdi
0x180014349  push    r14
0x18001434b  lea     rbp, [rsp-37h]
0x180014350  sub     rsp, 90h
0x180014357  xorps   xmm1, xmm1
0x18001435a  lea     r9, [rbp+57h+ObjectHandle]
0x18001435e  xor     r14d, r14d
0x180014361  lea     rdx, [rbp+57h+var_58]
0x180014365  xorps   xmm0, xmm0
0x180014368  mov     [rbp+57h+ObjectHandle], r14
0x18001436c  mov     rdi, rcx
0x18001436f  mov     [rbp+57h+Buffer], r14
0x180014373  mov     ebx, r14d
0x180014376  mov     [rbp+57h+hMem], r14
0x18001437a  mov     r8d, 20026h
0x180014380  mov     [rbp+57h+arg_18], rbx
0x180014384  xor     ecx, ecx
0x180014386  movups  [rbp+57h+var_88], xmm0
0x18001438a  movups  [rbp+57h+var_78], xmm1
0x18001438e  movups  [rbp+57h+var_68], xmm0
0x180014392  movups  [rbp+57h+var_58], xmm1
0x180014396  movups  [rbp+57h+var_48], xmm1
0x18001439a  movups  [rbp+57h+var_38], xmm1
0x18001439e  call    cs:__imp_LsarOpenPolicy
0x1800143a4  test    eax, eax
0x1800143a6  jns     short loc_1800143AF
0x1800143a8  mov     ecx, eax
0x1800143aa  jmp     loc_1800144CA
0x1800143af  mov     rcx, [rbp+57h+ObjectHandle]
0x1800143b3  lea     rax, aDefaultpasswor; "DefaultPassword"
0x1800143ba  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800143be  lea     r8, [rbp+57h+Buffer]
0x1800143c2  lea     rax, aDcpromooldDefa_0; "DcpromoOld_DefaultPassword"
0x1800143c9  mov     dword ptr [rbp+57h+var_88], 20001Eh
0x1800143d0  lea     rdx, [rbp+57h+var_88]
0x1800143d4  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800143d8  mov     dword ptr [rbp+57h+var_78], 360034h
0x1800143df  call    cs:__imp_LsarRetrievePrivateData
0x1800143e5  cmp     eax, 0C0000034h
0x1800143ea  jz      short loc_18001443B
0x1800143ec  test    eax, eax
0x1800143ee  js      short loc_1800143A8
0x1800143f0  mov     r8, [rbp+57h+Buffer]
0x1800143f4  lea     rdx, [rbp+57h+var_78]
0x1800143f8  mov     rcx, [rbp+57h+ObjectHandle]
0x1800143fc  call    cs:__imp_LsarStorePrivateData
0x180014402  mov     rcx, [rbp+57h+Buffer]
0x180014406  mov     r8d, [rcx]
0x180014409  mov     rdx, [rcx+8]
0x18001440d  test    r8, r8
0x180014410  jz      short loc_18001441E
0x180014412  mov     [rdx], r14b
0x180014415  inc     rdx
0x180014418  sub     r8, 1
0x18001441c  jnz     short loc_180014412
0x18001441e  test    eax, eax
0x180014420  js      short loc_1800143A8
0x180014422  mov     rcx, [rbp+57h+ObjectHandle]
0x180014426  lea     rdx, [rbp+57h+var_88]
0x18001442a  xor     r8d, r8d
0x18001442d  call    cs:__imp_LsarStorePrivateData
0x180014433  test    eax, eax
0x180014435  js      loc_1800143A8
0x18001443b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001443f  inc     rax
0x180014442  cmp     [rdi+rax*2], r14w
0x180014447  jnz     short loc_18001443F
0x180014449  mov     rcx, [rbp+57h+ObjectHandle]
0x18001444d  lea     rdx, [rbp+57h+hMem]
0x180014451  movzx   eax, ax
0x180014454  add     eax, eax
0x180014456  mov     qword ptr [rbp+57h+var_68+8], rdi
0x18001445a  mov     dword ptr [rbp+57h+var_68], eax
0x18001445d  add     eax, 2
0x180014460  mov     dword ptr [rbp+57h+var_68+4], eax
0x180014463  call    cs:__imp_LsapCrServerGetSessionKey
0x180014469  test    eax, eax
0x18001446b  js      loc_1800143A8
0x180014471  mov     rdx, [rbp+57h+hMem]
0x180014475  lea     r8, [rbp+57h+arg_18]
0x180014479  lea     rcx, [rbp+57h+var_68]
0x18001447d  mov     edi, r14d
0x180014480  call    LsapCrEncryptValue
0x180014485  mov     rbx, [rbp+57h+arg_18]
0x180014489  test    eax, eax
0x18001448b  js      short loc_1800144D2
0x18001448d  test    rbx, rbx
0x180014490  jz      short loc_1800144D2
0x180014492  mov     rcx, [rbp+57h+ObjectHandle]
0x180014496  lea     rdx, [rbp+57h+var_88]
0x18001449a  mov     r8, rbx
0x18001449d  call    cs:__imp_LsarStorePrivateData
0x1800144a3  mov     edx, [rbx]
0x1800144a5  mov     esi, eax
0x1800144a7  mov     rcx, [rbx+8]
0x1800144ab  test    rdx, rdx
0x1800144ae  jz      short loc_1800144BC
0x1800144b0  mov     [rcx], r14b
0x1800144b3  inc     rcx
0x1800144b6  sub     rdx, 1
0x1800144ba  jnz     short loc_1800144B0
0x1800144bc  mov     rcx, rbx
0x1800144bf  call    LsapCrFreeMemoryValue
0x1800144c4  test    esi, esi
0x1800144c6  jns     short loc_1800144D2
0x1800144c8  mov     ecx, esi; Status
0x1800144ca  call    cs:__imp_LsaNtStatusToWinError
0x1800144d0  mov     edi, eax
0x1800144d2  mov     rcx, [rbp+57h+ObjectHandle]; ObjectHandle
0x1800144d6  test    rcx, rcx
0x1800144d9  jz      short loc_1800144E1
0x1800144db  call    cs:__imp_LsaClose
0x1800144e1  mov     rcx, [rbp+57h+hMem]; hMem
0x1800144e5  test    rcx, rcx
0x1800144e8  jz      short loc_1800144F0
0x1800144ea  call    cs:__imp_LocalFree
0x1800144f0  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800144f4  test    rcx, rcx
0x1800144f7  jz      short loc_1800144FF
0x1800144f9  call    cs:__imp_LsaFreeMemory
0x1800144ff  test    rbx, rbx
0x180014502  jz      short loc_18001450C
0x180014504  mov     rcx, rbx
0x180014507  call    LsapCrFreeMemoryValue
0x18001450c  mov     eax, edi
0x18001450e  add     rsp, 90h
0x180014515  pop     r14
0x180014517  pop     rdi
0x180014518  pop     rsi
0x180014519  pop     rbx
0x18001451a  pop     rbp
0x18001451b  retn
```
