# GetUserSidStringFromToken

- ea: `0x18001ba78`
- end: `0x18001bbf4`
- name: `GetUserSidStringFromToken`
- size: `380`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b804`

## callees

- `0x180009220`
- `0x180009590`
- `0x18001b0fc`
- `0x18001ba78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bad4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bac0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bb18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bac0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bb18`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001bb2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001bb2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bbd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bbd9`

## pseudocode

```c
__int64 __fastcall GetUserSidStringFromToken(HANDLE TokenHandle, wil::details **a2)
{
  PSID *v5; // r14
  signed int LastError; // eax
  void *v7; // rdx
  signed int v8; // ebx
  LPWSTR v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  StringSid = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
  {
    v5 = 0;
    goto LABEL_5;
  }
  v5 = (PSID *)DAF_user_alloc(TokenInformationLength);
  if ( !GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength)
    || !ConvertSidToStringSidW(*v5, &StringSid) )
  {
LABEL_5:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  v9 = StringSid;
  if ( !StringSid )
  {
    v8 = -2147024809;
    goto LABEL_20;
  }
  v10 = 184;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v7 = (void *)(184 - v10);
  v8 = v10 == 0 ? 0x80070057 : 0;
  v11 = (184 - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
  {
LABEL_20:
    if ( *a2 )
    {
      wil::details::FreeProcessHeap(*a2, v7);
      *a2 = 0;
    }
    goto LABEL_22;
  }
  v12 = (unsigned __int16 *)DAF_user_alloc(2 * v11 + 2);
  *a2 = (wil::details *)v12;
  if ( !v12 )
  {
    v8 = -2147024882;
    goto LABEL_20;
  }
  v8 = StringCchCopyW(v12, v11 + 1, StringSid);
LABEL_17:
  if ( v8 < 0 )
    goto LABEL_20;
LABEL_22:
  if ( v5 )
    wil::details::FreeProcessHeap((wil::details *)v5, v7);
  if ( StringSid )
    LocalFree(StringSid);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ba78  mov     rax, rsp
0x18001ba7b  mov     [rax+8], rbx
0x18001ba7f  mov     [rax+20h], rbp
0x18001ba83  push    rsi
0x18001ba84  push    rdi
0x18001ba85  push    r14
0x18001ba87  sub     rsp, 30h
0x18001ba8b  xor     ebp, ebp
0x18001ba8d  mov     rdi, rdx
0x18001ba90  mov     [rax+10h], ebp
0x18001ba93  mov     rbx, rcx
0x18001ba96  mov     [rax+18h], rbp
0x18001ba9a  test    rdx, rdx
0x18001ba9d  jnz     short loc_18001BAA9
0x18001ba9f  mov     eax, 80004003h
0x18001baa4  jmp     loc_18001BBE1
0x18001baa9  xor     r9d, r9d; TokenInformationLength
0x18001baac  mov     [rdx], rbp
0x18001baaf  lea     rax, [rsp+48h+TokenInformationLength]
0x18001bab4  xor     r8d, r8d; TokenInformation
0x18001bab7  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001babc  lea     edx, [r9+1]; TokenInformationClass
0x18001bac0  call    cs:__imp_GetTokenInformation
0x18001bac6  call    cs:__imp_GetLastError
0x18001bacc  cmp     eax, 7Ah ; 'z'
0x18001bacf  jz      short loc_18001BAF2
0x18001bad1  mov     r14, rbp
0x18001bad4  call    cs:__imp_GetLastError
0x18001bada  mov     ebx, eax
0x18001badc  test    eax, eax
0x18001bade  jle     loc_18001BBA7
0x18001bae4  movzx   ebx, ax
0x18001bae7  or      ebx, 80070000h
0x18001baed  jmp     loc_18001BBA7
0x18001baf2  mov     ecx, [rsp+48h+TokenInformationLength]
0x18001baf6  call    DAF_user_alloc
0x18001bafb  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18001bb00  mov     r14, rax
0x18001bb03  lea     rax, [rsp+48h+TokenInformationLength]
0x18001bb08  mov     r8, r14; TokenInformation
0x18001bb0b  mov     edx, 1; TokenInformationClass
0x18001bb10  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001bb15  mov     rcx, rbx; TokenHandle
0x18001bb18  call    cs:__imp_GetTokenInformation
0x18001bb1e  test    eax, eax
0x18001bb20  jz      short loc_18001BAD4
0x18001bb22  mov     rcx, [r14]; Sid
0x18001bb25  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18001bb2a  call    cs:__imp_ConvertSidToStringSidW
0x18001bb30  test    eax, eax
0x18001bb32  jz      short loc_18001BAD4
0x18001bb34  mov     rax, [rsp+48h+StringSid]
0x18001bb39  test    rax, rax
0x18001bb3c  jz      short loc_18001BBAD
0x18001bb3e  mov     edx, 0B8h
0x18001bb43  mov     ecx, edx
0x18001bb45  cmp     [rax], bp
0x18001bb48  jz      short loc_18001BB54
0x18001bb4a  add     rax, 2
0x18001bb4e  sub     rcx, 1
0x18001bb52  jnz     short loc_18001BB45
0x18001bb54  mov     rax, rcx
0x18001bb57  neg     rax
0x18001bb5a  mov     rax, rcx
0x18001bb5d  sbb     ebx, ebx
0x18001bb5f  sub     rdx, rcx
0x18001bb62  not     ebx
0x18001bb64  and     ebx, 80070057h
0x18001bb6a  neg     rax
0x18001bb6d  sbb     rsi, rsi
0x18001bb70  and     rsi, rdx
0x18001bb73  test    rcx, rcx
0x18001bb76  jz      short loc_18001BBB2
0x18001bb78  lea     rcx, ds:2[rsi*2]
0x18001bb80  call    DAF_user_alloc
0x18001bb85  mov     [rdi], rax
0x18001bb88  test    rax, rax
0x18001bb8b  jnz     short loc_18001BB94
0x18001bb8d  mov     ebx, 8007000Eh
0x18001bb92  jmp     short loc_18001BBB2
0x18001bb94  mov     r8, [rsp+48h+StringSid]; unsigned __int16 *
0x18001bb99  lea     rdx, [rsi+1]; unsigned __int64
0x18001bb9d  mov     rcx, rax; unsigned __int16 *
0x18001bba0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001bba5  mov     ebx, eax
0x18001bba7  test    ebx, ebx
0x18001bba9  js      short loc_18001BBB2
0x18001bbab  jmp     short loc_18001BBC2
0x18001bbad  mov     ebx, 80070057h
0x18001bbb2  mov     rcx, [rdi]; this
0x18001bbb5  test    rcx, rcx
0x18001bbb8  jz      short loc_18001BBC2
0x18001bbba  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001bbbf  mov     [rdi], rbp
0x18001bbc2  test    r14, r14
0x18001bbc5  jz      short loc_18001BBCF
0x18001bbc7  mov     rcx, r14; this
0x18001bbca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001bbcf  mov     rcx, [rsp+48h+StringSid]; hMem
0x18001bbd4  test    rcx, rcx
0x18001bbd7  jz      short loc_18001BBDF
0x18001bbd9  call    cs:__imp_LocalFree
0x18001bbdf  mov     eax, ebx
0x18001bbe1  mov     rbx, [rsp+48h+arg_0]
0x18001bbe6  mov     rbp, [rsp+48h+arg_18]
0x18001bbeb  add     rsp, 30h
0x18001bbef  pop     r14
0x18001bbf1  pop     rdi
0x18001bbf2  pop     rsi
0x18001bbf3  retn
```
