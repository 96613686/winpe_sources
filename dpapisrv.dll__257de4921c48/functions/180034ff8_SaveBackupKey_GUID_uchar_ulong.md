# SaveBackupKey(_GUID *,uchar *,ulong)

- ea: `0x180034ff8`
- end: `0x18003512d`
- name: `?SaveBackupKey@@YAHPEAU_GUID@@PEAEK@Z`
- size: `309`
- prototype: `__int64 __fastcall(struct _GUID *, WCHAR *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800310e0`
- `0x1800313c8`
- `0x180031674`

## callees

- `0x180007f10`
- `0x18000dcb0`
- `0x18001d810`
- `0x180032898`
- `0x180034ff8`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035107`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035107`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800350e3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800350e3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800350d1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800350d1`

## string_xrefs

- `0x1800350ac`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall SaveBackupKey(struct _GUID *a1, WCHAR *a2, unsigned int a3)
{
  USHORT v3; // bx
  unsigned __int16 *v5; // rcx
  NTSTATUS v6; // ebx
  __int64 v7; // r9
  DWORD v8; // ecx
  LSA_HANDLE PolicyHandle; // [rsp+20h] [rbp-69h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+28h] [rbp-61h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 v13[8]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v14; // [rsp+60h] [rbp-29h] BYREF

  PolicyHandle = 0;
  v3 = a3;
  KeyName = 0;
  PrivateData = 0;
  if ( a1
    && a2
    && a3 <= 0xFFFF
    && (*(_OWORD *)v13 = *(_OWORD *)L"G$BCKUPKEY_",
        v14 = *(_QWORD *)L"EY_",
        !(unsigned int)MyGuidToStringW(a1, (char *)&v14 + 6)) )
  {
    InitLsaString((struct _UNICODE_STRING *)&KeyName, v13);
    PrivateData.Buffer = a2;
    PrivateData.Length = v3;
    PrivateData.MaximumLength = v3;
    v6 = OpenPolicy(v5, 0x20u, &PolicyHandle);
    if ( v6 >= 0 )
    {
      v6 = LsaStorePrivateData(PolicyHandle, &KeyName, &PrivateData);
      LsaClose(PolicyHandle);
      if ( v6 >= 0 )
        return 1;
      v7 = 2602;
    }
    else
    {
      v7 = 2587;
    }
    DebugTraceError((unsigned int)v6, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v7);
    v8 = v6;
  }
  else
  {
    v8 = 87;
  }
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x180034ff8  push    rbp
0x180034ffa  push    rbx
0x180034ffb  push    rdi
0x180034ffc  lea     rbp, [rsp-47h]
0x180035001  sub     rsp, 0D0h
0x180035008  mov     rax, cs:__security_cookie
0x18003500f  xor     rax, rsp
0x180035012  mov     [rbp+57h+var_20], rax
0x180035016  mov     [rbp+57h+PolicyHandle], 0
0x18003501e  xorps   xmm0, xmm0
0x180035021  xorps   xmm1, xmm1
0x180035024  mov     ebx, r8d
0x180035027  mov     rdi, rdx
0x18003502a  movups  xmmword ptr [rbp+57h+KeyName.Length], xmm0
0x18003502e  movups  xmmword ptr [rbp+57h+PrivateData.Length], xmm1
0x180035032  test    rcx, rcx
0x180035035  jz      loc_180035102
0x18003503b  test    rdx, rdx
0x18003503e  jz      loc_180035102
0x180035044  cmp     ebx, 0FFFFh
0x18003504a  ja      loc_180035102
0x180035050  movups  xmm0, xmmword ptr cs:aGBckupkey; "G$BCKUPKEY_"
0x180035057  lea     rdx, [rbp+57h+var_7A]
0x18003505b  movsd   xmm1, qword ptr cs:aGBckupkey+10h; "EY_"
0x180035063  movaps  xmmword ptr [rbp+57h+var_90], xmm0
0x180035067  movsd   qword ptr [rbp-29h], xmm1
0x18003506c  call    MyGuidToStringW
0x180035071  test    eax, eax
0x180035073  jnz     loc_180035102
0x180035079  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18003507d  lea     rcx, [rbp+57h+KeyName]; struct _UNICODE_STRING *
0x180035081  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180035086  lea     r8, [rbp+57h+PolicyHandle]; void **
0x18003508a  mov     [rbp+57h+PrivateData.Buffer], rdi
0x18003508e  mov     edx, 20h ; ' '; unsigned int
0x180035093  mov     [rbp+57h+PrivateData.Length], bx
0x180035097  mov     [rbp+57h+PrivateData.MaximumLength], bx
0x18003509b  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x1800350a0  mov     ebx, eax
0x1800350a2  test    eax, eax
0x1800350a4  jns     short loc_1800350C5
0x1800350a6  mov     r9d, 0A1Bh
0x1800350ac  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800350b3  mov     ecx, ebx
0x1800350b5  lea     rdx, aStatus; "Status"
0x1800350bc  call    DebugTraceError
0x1800350c1  mov     ecx, ebx
0x1800350c3  jmp     short loc_180035107
0x1800350c5  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800350c9  lea     r8, [rbp+57h+PrivateData]; PrivateData
0x1800350cd  lea     rdx, [rbp+57h+KeyName]; KeyName
0x1800350d1  call    cs:__imp_LsaStorePrivateData
0x1800350d8  nop     dword ptr [rax+rax+00h]
0x1800350dd  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1800350e1  mov     ebx, eax
0x1800350e3  call    cs:__imp_LsaClose
0x1800350ea  nop     dword ptr [rax+rax+00h]
0x1800350ef  test    ebx, ebx
0x1800350f1  jns     short loc_1800350FB
0x1800350f3  mov     r9d, 0A2Ah
0x1800350f9  jmp     short loc_1800350AC
0x1800350fb  mov     eax, 1
0x180035100  jmp     short loc_180035115
0x180035102  mov     ecx, 57h ; 'W'; dwErrCode
0x180035107  call    cs:__imp_SetLastError
0x18003510e  nop     dword ptr [rax+rax+00h]
0x180035113  xor     eax, eax
0x180035115  mov     rcx, [rbp+57h+var_20]
0x180035119  xor     rcx, rsp; StackCookie
0x18003511c  call    __security_check_cookie
0x180035121  add     rsp, 0D0h
0x180035128  pop     rdi
0x180035129  pop     rbx
0x18003512a  pop     rbp
0x18003512b  retn
```
