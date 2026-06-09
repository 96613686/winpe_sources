# ReadBackupKeyFromLsaSecret(_GUID const *,uchar * *,ulong *)

- ea: `0x180032a9c`
- end: `0x180032cae`
- name: `?ReadBackupKeyFromLsaSecret@@YAHPEBU_GUID@@PEAPEAEPEAK@Z`
- size: `530`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032084`
- `0x180032cb4`

## callees

- `0x180001184`
- `0x180007f10`
- `0x18000dcb0`
- `0x18001467c`
- `0x18001d810`
- `0x180032898`
- `0x180032a9c`
- `0x1800367a4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032c19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032c80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032c19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032c80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032bac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032bac`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180032b86`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180032b86`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032c07`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032c07`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x180032b74`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x180032b74`

## string_xrefs

- `0x180032b4c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall ReadBackupKeyFromLsaSecret(const struct _GUID *a1, unsigned __int8 **a2, unsigned int *a3)
{
  DWORD v5; // ecx
  unsigned __int16 *v6; // rcx
  NTSTATUS v7; // ebx
  __int64 v8; // r9
  unsigned __int8 *v9; // rax
  PLSA_UNICODE_STRING v10; // rdx
  unsigned int v11; // edi
  PLSA_UNICODE_STRING v12; // rcx
  __int64 Length; // rdx
  PWSTR Buffer; // rax
  __int64 v16; // r9
  PLSA_UNICODE_STRING PrivateData; // [rsp+30h] [rbp-69h] BYREF
  NTSTATUS v18; // [rsp+38h] [rbp-61h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+40h] [rbp-59h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 v21[8]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v22; // [rsp+70h] [rbp-29h] BYREF

  PolicyHandle = 0;
  PrivateData = 0;
  KeyName = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = 87;
    goto LABEL_25;
  }
  *(_OWORD *)v21 = *(_OWORD *)L"G$BCKUPKEY_";
  v22 = *(_QWORD *)L"EY_";
  if ( (unsigned int)MyGuidToStringW(a1, (char *)&v22 + 6) )
  {
    v5 = 2;
LABEL_25:
    SetLastError(v5);
    return 0;
  }
  InitLsaString((struct _UNICODE_STRING *)&KeyName, v21);
  v7 = OpenPolicy(v6, 4u, &PolicyHandle);
  if ( v7 < 0 )
  {
    v8 = 2158;
LABEL_8:
    DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v8);
    v5 = v7;
    goto LABEL_25;
  }
  v7 = LsaRetrievePrivateData(PolicyHandle, &KeyName, &PrivateData);
  LsaClose(PolicyHandle);
  if ( v7 < 0 || !PrivateData )
  {
    if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
    {
      v18 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18004C260,
        (int)word_18004520A,
        0,
        v16,
        (__int64)&v18);
    }
    v8 = 2180;
    goto LABEL_8;
  }
  v9 = (unsigned __int8 *)LocalAlloc(0, PrivateData->Length);
  *a2 = v9;
  if ( v9 )
  {
    v10 = PrivateData;
    *a3 = PrivateData->Length;
    memcpy_0(*a2, v10->Buffer, v10->Length);
    v11 = 1;
  }
  else
  {
    v7 = 8;
    v11 = 0;
  }
  v12 = PrivateData;
  Length = PrivateData->Length;
  Buffer = PrivateData->Buffer;
  if ( PrivateData->Length )
  {
    do
    {
      *(_BYTE *)Buffer = 0;
      Buffer = (PWSTR)((char *)Buffer + 1);
      --Length;
    }
    while ( Length );
    v12 = PrivateData;
  }
  LsaFreeMemory(v12);
  if ( !v11 )
    SetLastError(v7);
  return v11;
}

```

## disassembly

```asm
0x180032a9c  mov     [rsp-8+arg_18], rbx
0x180032aa1  push    rbp
0x180032aa2  push    rsi
0x180032aa3  push    rdi
0x180032aa4  lea     rbp, [rsp-47h]
0x180032aa9  sub     rsp, 0E0h
0x180032ab0  mov     rax, cs:__security_cookie
0x180032ab7  xor     rax, rsp
0x180032aba  mov     [rbp+57h+var_20], rax
0x180032abe  mov     [rbp+57h+PolicyHandle], 0
0x180032ac6  xorps   xmm0, xmm0
0x180032ac9  mov     [rbp+57h+PrivateData], 0
0x180032ad1  mov     rsi, r8
0x180032ad4  mov     rdi, rdx
0x180032ad7  movups  xmmword ptr [rbp+57h+KeyName.Length], xmm0
0x180032adb  test    rcx, rcx
0x180032ade  jz      loc_180032C7B
0x180032ae4  test    rdx, rdx
0x180032ae7  jz      loc_180032C7B
0x180032aed  test    r8, r8
0x180032af0  jz      loc_180032C7B
0x180032af6  movups  xmm0, xmmword ptr cs:aGBckupkey; "G$BCKUPKEY_"
0x180032afd  lea     rdx, [rbp+57h+var_7A]
0x180032b01  movsd   xmm1, qword ptr cs:aGBckupkey+10h; "EY_"
0x180032b09  movaps  xmmword ptr [rbp+57h+var_90], xmm0
0x180032b0d  movsd   qword ptr [rbp-29h], xmm1
0x180032b12  call    MyGuidToStringW
0x180032b17  test    eax, eax
0x180032b19  jz      short loc_180032B25
0x180032b1b  mov     ecx, 2
0x180032b20  jmp     loc_180032C80
0x180032b25  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180032b29  lea     rcx, [rbp+57h+KeyName]; struct _UNICODE_STRING *
0x180032b2d  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180032b32  lea     r8, [rbp+57h+PolicyHandle]; void **
0x180032b36  mov     edx, 4; unsigned int
0x180032b3b  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x180032b40  mov     ebx, eax
0x180032b42  test    eax, eax
0x180032b44  jns     short loc_180032B68
0x180032b46  mov     r9d, 86Eh
0x180032b4c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032b53  mov     ecx, ebx
0x180032b55  lea     rdx, aStatus; "Status"
0x180032b5c  call    DebugTraceError
0x180032b61  mov     ecx, ebx
0x180032b63  jmp     loc_180032C80
0x180032b68  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180032b6c  lea     r8, [rbp+57h+PrivateData]; PrivateData
0x180032b70  lea     rdx, [rbp+57h+KeyName]; KeyName
0x180032b74  call    cs:__imp_LsaRetrievePrivateData
0x180032b7b  nop     dword ptr [rax+rax+00h]
0x180032b80  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180032b84  mov     ebx, eax
0x180032b86  call    cs:__imp_LsaClose
0x180032b8d  nop     dword ptr [rax+rax+00h]
0x180032b92  test    ebx, ebx
0x180032b94  js      loc_180032C29
0x180032b9a  mov     rax, [rbp+57h+PrivateData]
0x180032b9e  test    rax, rax
0x180032ba1  jz      loc_180032C29
0x180032ba7  movzx   edx, word ptr [rax]; uBytes
0x180032baa  xor     ecx, ecx; uFlags
0x180032bac  call    cs:__imp_LocalAlloc
0x180032bb3  nop     dword ptr [rax+rax+00h]
0x180032bb8  mov     [rdi], rax
0x180032bbb  test    rax, rax
0x180032bbe  jz      short loc_180032BE0
0x180032bc0  mov     rdx, [rbp+57h+PrivateData]
0x180032bc4  movzx   eax, word ptr [rdx]
0x180032bc7  mov     [rsi], eax
0x180032bc9  movzx   r8d, word ptr [rdx]; Size
0x180032bcd  mov     rdx, [rdx+8]; Src
0x180032bd1  mov     rcx, [rdi]; void *
0x180032bd4  call    memcpy_0
0x180032bd9  mov     edi, 1
0x180032bde  jmp     short loc_180032BE7
0x180032be0  mov     ebx, 8
0x180032be5  xor     edi, edi
0x180032be7  mov     rcx, [rbp+57h+PrivateData]
0x180032beb  movzx   edx, word ptr [rcx]
0x180032bee  mov     rax, [rcx+8]
0x180032bf2  test    rdx, rdx
0x180032bf5  jz      short loc_180032C07
0x180032bf7  mov     byte ptr [rax], 0
0x180032bfa  inc     rax
0x180032bfd  sub     rdx, 1
0x180032c01  jnz     short loc_180032BF7
0x180032c03  mov     rcx, [rbp+57h+PrivateData]; Buffer
0x180032c07  call    cs:__imp_LsaFreeMemory
0x180032c0e  nop     dword ptr [rax+rax+00h]
0x180032c13  test    edi, edi
0x180032c15  jnz     short loc_180032C25
0x180032c17  mov     ecx, ebx; dwErrCode
0x180032c19  call    cs:__imp_SetLastError
0x180032c20  nop     dword ptr [rax+rax+00h]
0x180032c25  mov     eax, edi
0x180032c27  jmp     short loc_180032C8E
0x180032c29  mov     eax, cs:dword_18004C260
0x180032c2f  cmp     eax, 5
0x180032c32  jbe     short loc_180032C70
0x180032c34  mov     rdx, 400000000000h
0x180032c3e  lea     rcx, dword_18004C260
0x180032c45  call    _tlgKeywordOn
0x180032c4a  test    al, al
0x180032c4c  jz      short loc_180032C70
0x180032c4e  lea     rax, [rbp+57h+var_B8]
0x180032c52  mov     [rbp+57h+var_B8], ebx
0x180032c55  xor     r8d, r8d
0x180032c58  mov     [rsp+0F0h+var_D0], rax
0x180032c5d  lea     rdx, word_18004520A
0x180032c64  lea     rcx, dword_18004C260
0x180032c6b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180032c70  mov     r9d, 884h
0x180032c76  jmp     loc_180032B4C
0x180032c7b  mov     ecx, 57h ; 'W'; dwErrCode
0x180032c80  call    cs:__imp_SetLastError
0x180032c87  nop     dword ptr [rax+rax+00h]
0x180032c8c  xor     eax, eax
0x180032c8e  mov     rcx, [rbp+57h+var_20]
0x180032c92  xor     rcx, rsp; StackCookie
0x180032c95  call    __security_check_cookie
0x180032c9a  mov     rbx, [rsp+0F0h+arg_18]
0x180032ca2  add     rsp, 0E0h
0x180032ca9  pop     rdi
0x180032caa  pop     rsi
0x180032cab  pop     rbp
0x180032cac  retn
```
