# BeforeKeyRotation::GetPreferredBackupKeyGuid(ulong,_GUID *)

- ea: `0x180032474`
- end: `0x1800325af`
- name: `?GetPreferredBackupKeyGuid@BeforeKeyRotation@@YAHKPEAU_GUID@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, _OWORD *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800354c8`

## callees

- `0x180007f10`
- `0x180032474`
- `0x180032898`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032534`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032534`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032590`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800324fe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800324fe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032563`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032563`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800324ec`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800324ec`

## string_xrefs

- `0x180032579`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::GetPreferredBackupKeyGuid(BeforeKeyRotation *this, _OWORD *a2, struct _GUID *a3)
{
  unsigned __int16 *v4; // rdx
  unsigned __int16 *v5; // rcx
  int v6; // eax
  DWORD v7; // ecx
  NTSTATUS v8; // ebx
  PLSA_UNICODE_STRING v9; // rcx
  unsigned int v10; // ebx
  __int64 Length; // r8
  _BYTE *Buffer; // rdx
  struct _LSA_UNICODE_STRING KeyName; // [rsp+20h] [rbp-10h] BYREF
  PLSA_UNICODE_STRING PrivateData; // [rsp+48h] [rbp+18h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+50h] [rbp+20h] BYREF

  PolicyHandle = 0;
  PrivateData = 0;
  KeyName = 0;
  if ( !a2 )
    return 0;
  v4 = L"G$BCKUPKEY_P";
  if ( (_DWORD)this != 1 )
    v4 = L"G$BCKUPKEY_PREFERRED";
  InitLsaString((struct _UNICODE_STRING *)&KeyName, v4);
  v6 = OpenPolicy(v5, 4u, &PolicyHandle);
  if ( v6 < 0 )
  {
    v7 = v6;
LABEL_16:
    SetLastError(v7);
    return 0;
  }
  v8 = LsaRetrievePrivateData(PolicyHandle, &KeyName, &PrivateData);
  LsaClose(PolicyHandle);
  if ( v8 < 0 || (v9 = PrivateData) == 0 )
  {
    DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 4986);
    v7 = v8;
    goto LABEL_16;
  }
  if ( PrivateData->Length == 16 )
  {
    v10 = 1;
    *a2 = *(_OWORD *)PrivateData->Buffer;
  }
  else
  {
    SetLastError(0x57u);
    v9 = PrivateData;
    v10 = 0;
  }
  Length = v9->Length;
  Buffer = v9->Buffer;
  if ( v9->Length )
  {
    do
    {
      *Buffer++ = 0;
      --Length;
    }
    while ( Length );
    v9 = PrivateData;
  }
  LsaFreeMemory(v9);
  return v10;
}

```

## disassembly

```asm
0x180032474  mov     [rsp-8+arg_0], rbx
0x180032479  mov     [rsp-8+arg_18], rdi
0x18003247e  push    rbp
0x18003247f  mov     rbp, rsp
0x180032482  sub     rsp, 30h
0x180032486  mov     [rbp+PolicyHandle], 0
0x18003248e  xorps   xmm0, xmm0
0x180032491  mov     [rbp+PrivateData], 0
0x180032499  mov     rdi, rdx
0x18003249c  movups  xmmword ptr [rbp+KeyName.Length], xmm0
0x1800324a0  test    rdx, rdx
0x1800324a3  jz      loc_18003259C
0x1800324a9  cmp     ecx, 1
0x1800324ac  lea     rax, aGBckupkeyPrefe; "G$BCKUPKEY_PREFERRED"
0x1800324b3  lea     rdx, aGBckupkeyP; "G$BCKUPKEY_P"
0x1800324ba  cmovnz  rdx, rax; unsigned __int16 *
0x1800324be  lea     rcx, [rbp+KeyName]; struct _UNICODE_STRING *
0x1800324c2  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x1800324c7  lea     r8, [rbp+PolicyHandle]; void **
0x1800324cb  mov     edx, 4; unsigned int
0x1800324d0  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x1800324d5  test    eax, eax
0x1800324d7  jns     short loc_1800324E0
0x1800324d9  mov     ecx, eax
0x1800324db  jmp     loc_180032590
0x1800324e0  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800324e4  lea     r8, [rbp+PrivateData]; PrivateData
0x1800324e8  lea     rdx, [rbp+KeyName]; KeyName
0x1800324ec  call    cs:__imp_LsaRetrievePrivateData
0x1800324f3  nop     dword ptr [rax+rax+00h]
0x1800324f8  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800324fc  mov     ebx, eax
0x1800324fe  call    cs:__imp_LsaClose
0x180032505  nop     dword ptr [rax+rax+00h]
0x18003250a  test    ebx, ebx
0x18003250c  js      short loc_180032573
0x18003250e  mov     rcx, [rbp+PrivateData]
0x180032512  test    rcx, rcx
0x180032515  jz      short loc_180032573
0x180032517  cmp     word ptr [rcx], 10h
0x18003251b  jnz     short loc_18003252F
0x18003251d  mov     rax, [rcx+8]
0x180032521  mov     ebx, 1
0x180032526  movups  xmm0, xmmword ptr [rax]
0x180032529  movdqu  xmmword ptr [rdi], xmm0
0x18003252d  jmp     short loc_180032546
0x18003252f  mov     ecx, 57h ; 'W'; dwErrCode
0x180032534  call    cs:__imp_SetLastError
0x18003253b  nop     dword ptr [rax+rax+00h]
0x180032540  mov     rcx, [rbp+PrivateData]
0x180032544  xor     ebx, ebx
0x180032546  movzx   r8d, word ptr [rcx]
0x18003254a  mov     rdx, [rcx+8]
0x18003254e  test    r8, r8
0x180032551  jz      short loc_180032563
0x180032553  mov     byte ptr [rdx], 0
0x180032556  inc     rdx
0x180032559  sub     r8, 1
0x18003255d  jnz     short loc_180032553
0x18003255f  mov     rcx, [rbp+PrivateData]; Buffer
0x180032563  call    cs:__imp_LsaFreeMemory
0x18003256a  nop     dword ptr [rax+rax+00h]
0x18003256f  mov     eax, ebx
0x180032571  jmp     short loc_18003259E
0x180032573  mov     r9d, 137Ah
0x180032579  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032580  lea     rdx, aStatus; "Status"
0x180032587  mov     ecx, ebx
0x180032589  call    DebugTraceError
0x18003258e  mov     ecx, ebx; dwErrCode
0x180032590  call    cs:__imp_SetLastError
0x180032597  nop     dword ptr [rax+rax+00h]
0x18003259c  xor     eax, eax
0x18003259e  mov     rbx, [rsp+30h+arg_0]
0x1800325a3  mov     rdi, [rsp+30h+arg_18]
0x1800325a8  add     rsp, 30h
0x1800325ac  pop     rbp
0x1800325ad  retn
```
