# BeforeKeyRotation::SetPreferredBackupKeyGuid(ulong,_GUID *)

- ea: `0x180035134`
- end: `0x180035215`
- name: `?SetPreferredBackupKeyGuid@BeforeKeyRotation@@YAHKPEAU_GUID@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, WCHAR *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800354c8`

## callees

- `0x180007f10`
- `0x180032898`
- `0x180035134`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035162`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035162`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800351d2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800351d2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800351c0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800351c0`

## string_xrefs

- `0x1800351e8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::SetPreferredBackupKeyGuid(BeforeKeyRotation *this, WCHAR *a2, struct _GUID *a3)
{
  DWORD v4; // ecx
  unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rcx
  NTSTATUS v8; // eax
  NTSTATUS v9; // ebx
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+20h] [rbp-20h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+30h] [rbp-10h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+58h] [rbp+18h] BYREF

  PolicyHandle = 0;
  KeyName = 0;
  PrivateData = 0;
  if ( !a2 )
  {
    v4 = 87;
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  v6 = L"G$BCKUPKEY_P";
  if ( (_DWORD)this != 1 )
    v6 = L"G$BCKUPKEY_PREFERRED";
  InitLsaString((struct _UNICODE_STRING *)&KeyName, v6);
  PrivateData.Buffer = a2;
  *(_DWORD *)&PrivateData.Length = 1048592;
  v8 = OpenPolicy(v7, 0x20u, &PolicyHandle);
  if ( v8 < 0 )
  {
    v4 = v8;
    goto LABEL_3;
  }
  v9 = LsaStorePrivateData(PolicyHandle, &KeyName, &PrivateData);
  LsaClose(PolicyHandle);
  if ( v9 < 0 )
  {
    DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 5061);
    v4 = v9;
    goto LABEL_3;
  }
  return 1;
}

```

## disassembly

```asm
0x180035134  mov     [rsp-8+arg_0], rbx
0x180035139  push    rbp
0x18003513a  mov     rbp, rsp
0x18003513d  sub     rsp, 40h
0x180035141  mov     [rbp+PolicyHandle], 0
0x180035149  xorps   xmm0, xmm0
0x18003514c  xorps   xmm1, xmm1
0x18003514f  mov     rbx, rdx
0x180035152  movups  xmmword ptr [rbp+KeyName.Length], xmm0
0x180035156  movups  xmmword ptr [rbp+PrivateData.Length], xmm1
0x18003515a  test    rdx, rdx
0x18003515d  jnz     short loc_180035175
0x18003515f  lea     ecx, [rdx+57h]; dwErrCode
0x180035162  call    cs:__imp_SetLastError
0x180035169  nop     dword ptr [rax+rax+00h]
0x18003516e  xor     eax, eax
0x180035170  jmp     loc_180035209
0x180035175  cmp     ecx, 1
0x180035178  lea     rax, aGBckupkeyPrefe; "G$BCKUPKEY_PREFERRED"
0x18003517f  lea     rdx, aGBckupkeyP; "G$BCKUPKEY_P"
0x180035186  cmovnz  rdx, rax; unsigned __int16 *
0x18003518a  lea     rcx, [rbp+KeyName]; struct _UNICODE_STRING *
0x18003518e  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180035193  lea     r8, [rbp+PolicyHandle]; void **
0x180035197  mov     [rbp+PrivateData.Buffer], rbx
0x18003519b  mov     edx, 20h ; ' '; unsigned int
0x1800351a0  mov     dword ptr [rbp+PrivateData.Length], 100010h
0x1800351a7  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x1800351ac  test    eax, eax
0x1800351ae  jns     short loc_1800351B4
0x1800351b0  mov     ecx, eax
0x1800351b2  jmp     short loc_180035162
0x1800351b4  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800351b8  lea     r8, [rbp+PrivateData]; PrivateData
0x1800351bc  lea     rdx, [rbp+KeyName]; KeyName
0x1800351c0  call    cs:__imp_LsaStorePrivateData
0x1800351c7  nop     dword ptr [rax+rax+00h]
0x1800351cc  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800351d0  mov     ebx, eax
0x1800351d2  call    cs:__imp_LsaClose
0x1800351d9  nop     dword ptr [rax+rax+00h]
0x1800351de  test    ebx, ebx
0x1800351e0  jns     short loc_180035204
0x1800351e2  mov     r9d, 13C5h
0x1800351e8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800351ef  lea     rdx, aStatus; "Status"
0x1800351f6  mov     ecx, ebx
0x1800351f8  call    DebugTraceError
0x1800351fd  mov     ecx, ebx
0x1800351ff  jmp     loc_180035162
0x180035204  mov     eax, 1
0x180035209  mov     rbx, [rsp+40h+arg_0]
0x18003520e  add     rsp, 40h
0x180035212  pop     rbp
0x180035213  retn
```
