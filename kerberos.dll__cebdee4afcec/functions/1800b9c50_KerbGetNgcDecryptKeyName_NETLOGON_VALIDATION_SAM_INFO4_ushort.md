# KerbGetNgcDecryptKeyName(_NETLOGON_VALIDATION_SAM_INFO4 *,ushort * *)

- ea: `0x1800b9c50`
- end: `0x1800b9dc7`
- name: `?KerbGetNgcDecryptKeyName@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAG@Z`
- size: `375`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b8908`

## callees

- `0x1800069a0`
- `0x18008b70c`
- `0x1800b9b20`
- `0x1800b9c50`
- `0x1800dd634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b9d7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b9d8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b9d7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b9d8d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b9ccf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b9ccf`
- `cryptngc!NgcGetLogonDecryptionKeyName` at `0x1800b9d3b`
- `cryptngc!NgcGetLogonDecryptionKeyName` at `0x1800b9d3b`
- `cryptngc!NgcFreeEnumState` at `0x1800b9da9`
- `cryptngc!NgcFreeEnumState` at `0x1800b9da9`

## string_xrefs

- `0x1800b9ca1`: `Get UserSid fail : 0x%x\n`
- `0x1800b9cee`: `ConvertSidToStringSid: 0x%x\n`

## pseudocode

```c
__int64 __fastcall KerbGetNgcDecryptKeyName(struct _NETLOGON_VALIDATION_SAM_INFO4 *a1, unsigned __int16 **a2)
{
  ULONG v3; // edx
  void *v4; // rcx
  void *DomainRelativeSid; // rax
  void *v6; // rdi
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  signed int LastError; // eax
  int NgcContainerInfo; // eax
  int LogonDecryptionKeyName; // eax
  unsigned int v13; // eax
  void *v15; // [rsp+30h] [rbp-10h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int16 *v17; // [rsp+70h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+38h] BYREF

  hMem = 0;
  v3 = *((_DWORD *)a1 + 37);
  v4 = (void *)*((_QWORD *)a1 + 28);
  v15 = 0;
  v17 = 0;
  StringSid = 0;
  DomainRelativeSid = KerbMakeDomainRelativeSid(v4, v3);
  v6 = DomainRelativeSid;
  if ( DomainRelativeSid )
  {
    if ( ConvertSidToStringSidW(DomainRelativeSid, &StringSid) )
    {
      NgcContainerInfo = KerbGetNgcContainerInfo(StringSid, (struct _NGC_CONTAINER_ENUM_INFO **)&hMem, &v15);
      v7 = NgcContainerInfo;
      if ( NgcContainerInfo < 0 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetNgcDecryptKeyName",
          7777,
          "KerbGetNgcContainerInfo fails, no logon containers found: 0x%x\n",
          NgcContainerInfo);
        goto LABEL_16;
      }
      LogonDecryptionKeyName = NgcGetLogonDecryptionKeyName(
                                 StringSid,
                                 *((_QWORD *)hMem + 4),
                                 *((_QWORD *)hMem + 5),
                                 &v17);
      if ( LogonDecryptionKeyName >= 0 )
      {
        *a2 = v17;
        v17 = 0;
        goto LABEL_16;
      }
      v7 = (unsigned __int16)LogonDecryptionKeyName;
      v8 = "NgcGetLogonDecryptionKeyName: 0x%x\n";
      v9 = 7791;
      v13 = (unsigned __int16)LogonDecryptionKeyName | 0xC0070000;
      if ( v7 )
        v7 = v13;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0xC0070000;
      v8 = "ConvertSidToStringSid: 0x%x\n";
      v9 = 7769;
    }
  }
  else
  {
    v7 = -1073740759;
    v8 = "Get UserSid fail : 0x%x\n";
    v9 = 7761;
  }
  KerbTracerT::Log(1, "KerbGetNgcDecryptKeyName", v9, v8, v7);
LABEL_16:
  if ( hMem )
    LocalFree(hMem);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    KerbFree(v6);
  if ( v15 )
    NgcFreeEnumState();
  KerbFree(v17);
  return v7;
}

```

## disassembly

```asm
0x1800b9c50  mov     [rsp-18h+arg_8], rbx
0x1800b9c55  push    rbp
0x1800b9c56  push    rsi
0x1800b9c57  push    rdi
0x1800b9c58  mov     rbp, rsp
0x1800b9c5b  sub     rsp, 40h
0x1800b9c5f  mov     rsi, rdx
0x1800b9c62  mov     [rbp+hMem], 0
0x1800b9c6a  mov     edx, [rcx+94h]; unsigned int
0x1800b9c70  mov     rcx, [rcx+0E0h]; SourceSid
0x1800b9c77  mov     [rbp+var_10], 0
0x1800b9c7f  mov     [rbp+arg_10], 0
0x1800b9c87  mov     [rbp+StringSid], 0
0x1800b9c8f  call    ?KerbMakeDomainRelativeSid@@YAPEAXPEAXK@Z; KerbMakeDomainRelativeSid(void *,ulong)
0x1800b9c94  mov     rdi, rax
0x1800b9c97  test    rax, rax
0x1800b9c9a  jnz     short loc_1800B9CC8
0x1800b9c9c  mov     ebx, 0C0000429h
0x1800b9ca1  lea     r9, aGetUsersidFail; "Get UserSid fail : 0x%x\n"
0x1800b9ca8  mov     r8d, 1E51h
0x1800b9cae  mov     [rsp+40h+var_20], ebx
0x1800b9cb2  lea     rdx, aKerbgetngcdecr; "KerbGetNgcDecryptKeyName"
0x1800b9cb9  mov     ecx, 1
0x1800b9cbe  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9cc3  jmp     loc_1800B9D75
0x1800b9cc8  lea     rdx, [rbp+StringSid]; StringSid
0x1800b9ccc  mov     rcx, rdi; Sid
0x1800b9ccf  call    cs:__imp_ConvertSidToStringSidW
0x1800b9cd5  test    eax, eax
0x1800b9cd7  jnz     short loc_1800B9CFD
0x1800b9cd9  call    cs:__imp_GetLastError
0x1800b9cdf  mov     ebx, eax
0x1800b9ce1  test    eax, eax
0x1800b9ce3  jle     short loc_1800B9CEE
0x1800b9ce5  movzx   ebx, ax
0x1800b9ce8  or      ebx, 0C0070000h
0x1800b9cee  lea     r9, aConvertsidtost_0; "ConvertSidToStringSid: 0x%x\n"
0x1800b9cf5  mov     r8d, 1E59h
0x1800b9cfb  jmp     short loc_1800B9CAE
0x1800b9cfd  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x1800b9d01  lea     r8, [rbp+var_10]; void **
0x1800b9d05  lea     rdx, [rbp+hMem]; struct _NGC_CONTAINER_ENUM_INFO **
0x1800b9d09  call    ?KerbGetNgcContainerInfo@@YAJPEAGPEAPEAU_NGC_CONTAINER_ENUM_INFO@@PEAPEAX@Z; KerbGetNgcContainerInfo(ushort *,_NGC_CONTAINER_ENUM_INFO * *,void * *)
0x1800b9d0e  mov     ebx, eax
0x1800b9d10  test    eax, eax
0x1800b9d12  jns     short loc_1800B9D27
0x1800b9d14  mov     [rsp+40h+var_20], eax
0x1800b9d18  lea     r9, aKerbgetngccont; "KerbGetNgcContainerInfo fails, no logon"...
0x1800b9d1f  mov     r8d, 1E61h
0x1800b9d25  jmp     short loc_1800B9CB2
0x1800b9d27  mov     rdx, [rbp+hMem]
0x1800b9d2b  lea     r9, [rbp+arg_10]
0x1800b9d2f  mov     rcx, [rbp+StringSid]
0x1800b9d33  mov     r8, [rdx+28h]
0x1800b9d37  mov     rdx, [rdx+20h]
0x1800b9d3b  call    cs:__imp_NgcGetLogonDecryptionKeyName
0x1800b9d41  test    eax, eax
0x1800b9d43  jns     short loc_1800B9D66
0x1800b9d45  movzx   ebx, ax
0x1800b9d48  lea     r9, aNgcgetlogondec_0; "NgcGetLogonDecryptionKeyName: 0x%x\n"
0x1800b9d4f  mov     eax, ebx
0x1800b9d51  mov     r8d, 1E6Fh
0x1800b9d57  or      eax, 0C0070000h
0x1800b9d5c  test    ebx, ebx
0x1800b9d5e  cmovnz  ebx, eax
0x1800b9d61  jmp     loc_1800B9CAE
0x1800b9d66  mov     rax, [rbp+arg_10]
0x1800b9d6a  mov     [rsi], rax
0x1800b9d6d  mov     [rbp+arg_10], 0
0x1800b9d75  mov     rcx, [rbp+hMem]; hMem
0x1800b9d79  test    rcx, rcx
0x1800b9d7c  jz      short loc_1800B9D84
0x1800b9d7e  call    cs:__imp_LocalFree
0x1800b9d84  mov     rcx, [rbp+StringSid]; hMem
0x1800b9d88  test    rcx, rcx
0x1800b9d8b  jz      short loc_1800B9D93
0x1800b9d8d  call    cs:__imp_LocalFree
0x1800b9d93  test    rdi, rdi
0x1800b9d96  jz      short loc_1800B9DA0
0x1800b9d98  mov     rcx, rdi
0x1800b9d9b  call    KerbFree
0x1800b9da0  mov     rcx, [rbp+var_10]
0x1800b9da4  test    rcx, rcx
0x1800b9da7  jz      short loc_1800B9DAF
0x1800b9da9  call    cs:__imp_NgcFreeEnumState
0x1800b9daf  mov     rcx, [rbp+arg_10]
0x1800b9db3  call    KerbFree
0x1800b9db8  mov     eax, ebx
0x1800b9dba  mov     rbx, [rsp+40h+arg_8]
0x1800b9dbf  add     rsp, 40h
0x1800b9dc3  pop     rdi
0x1800b9dc4  pop     rsi
0x1800b9dc5  pop     rbp
0x1800b9dc6  retn
```
