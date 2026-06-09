# IsLowIntegrityToken

- ea: `0x18012da30`
- end: `0x18012dc26`
- name: `IsLowIntegrityToken`
- size: `502`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18012d4b4`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x18012d594`
- `0x18012da30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012daab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012db1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012db64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012dba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012daab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012db1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012db64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012dba9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012da97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012db0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012da97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012db0f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012db50`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012db99`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012db50`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012db99`
- `ntdll!RtlEqualSid` at `0x18012dbd3`
- `ntdll!RtlEqualSid` at `0x18012dbd3`

## pseudocode

```c
__int64 __fastcall IsLowIntegrityToken(HANDLE TokenHandle, _BYTE *a2)
{
  signed int v2; // ebx
  DWORD LastError; // eax
  struct _RTL_BALANCED_NODE *v7; // r14
  struct _RTL_BALANCED_NODE *v8; // rdi
  DWORD v9; // eax
  void *v10; // rdx
  DWORD v11; // eax
  struct _RTL_BALANCED_NODE *v12; // rax
  void *v13; // rdx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  v2 = -2146892963;
  cbSid = 0;
  if ( !a2 )
    return (unsigned int)v2;
  *a2 = 0;
  v2 = TokenHandle == 0 ? 0x8009035D : 0;
  if ( !TokenHandle )
    return (unsigned int)v2;
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 && LastError != 24 )
    {
      if ( LastError )
        return ConvertWin32StatusToSecStatus(LastError, 2148074248LL);
      return 2148074288LL;
    }
    v7 = (struct _RTL_BALANCED_NODE *)LsapAllocate(TokenInformationLength);
    if ( !v7 )
      return 2148074240LL;
    v8 = 0;
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength)
      || (v9 = GetLastError(), v2 = ConvertWin32StatusToSecStatus(v9, 2148074248LL), v2 >= 0) )
    {
      if ( !CreateWellKnownSid(WinLowLabelSid, 0, 0, &cbSid) )
      {
        v11 = GetLastError();
        if ( v11 == 122 )
        {
          v12 = (struct _RTL_BALANCED_NODE *)LsapAllocate(cbSid);
          v8 = v12;
          if ( !v12 )
          {
            v2 = -2146893056;
            goto LABEL_25;
          }
          if ( CreateWellKnownSid(WinLowLabelSid, 0, v12, &cbSid) )
          {
LABEL_21:
            if ( v2 >= 0 && RtlEqualSid(v8, v7->Children[0]) )
              *a2 = 1;
            goto LABEL_25;
          }
          v11 = GetLastError();
LABEL_20:
          v2 = ConvertWin32StatusToSecStatus(v11, 2148074288LL);
          goto LABEL_21;
        }
        if ( v11 )
          goto LABEL_20;
      }
      v2 = -2146893008;
    }
LABEL_25:
    LsapSubProv_FreeRoutine(v7, v10);
    if ( v8 )
      LsapSubProv_FreeRoutine(v8, v13);
    return (unsigned int)v2;
  }
  return 2148074288LL;
}

```

## disassembly

```asm
0x18012da30  mov     rax, rsp
0x18012da33  mov     [rax+18h], rbx
0x18012da37  mov     [rax+20h], rsi
0x18012da3b  push    rdi
0x18012da3c  push    r14
0x18012da3e  push    r15
0x18012da40  sub     rsp, 30h
0x18012da44  mov     dword ptr [rax+8], 0
0x18012da4b  mov     ebx, 8009035Dh
0x18012da50  mov     dword ptr [rax+10h], 0
0x18012da57  mov     r15, rdx
0x18012da5a  mov     rax, rcx
0x18012da5d  mov     rsi, rcx
0x18012da60  neg     rax
0x18012da63  sbb     r8d, r8d
0x18012da66  not     r8d
0x18012da69  and     r8d, ebx
0x18012da6c  test    rdx, rdx
0x18012da6f  jz      short loc_18012DA7C
0x18012da71  mov     byte ptr [rdx], 0
0x18012da74  mov     ebx, r8d
0x18012da77  test    rcx, rcx
0x18012da7a  jnz     short loc_18012DA83
0x18012da7c  mov     eax, ebx
0x18012da7e  jmp     loc_18012DC11
0x18012da83  xor     r9d, r9d; TokenInformationLength
0x18012da86  lea     rax, [rsp+48h+TokenInformationLength]
0x18012da8b  xor     r8d, r8d; TokenInformation
0x18012da8e  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18012da93  lea     edx, [r9+19h]; TokenInformationClass
0x18012da97  call    cs:__imp_GetTokenInformation
0x18012da9e  nop     dword ptr [rax+rax+00h]
0x18012daa3  test    eax, eax
0x18012daa5  jnz     loc_18012DC0C
0x18012daab  call    cs:__imp_GetLastError
0x18012dab2  nop     dword ptr [rax+rax+00h]
0x18012dab7  cmp     eax, 7Ah ; 'z'
0x18012daba  jz      short loc_18012DADA
0x18012dabc  cmp     eax, 18h
0x18012dabf  jz      short loc_18012DADA
0x18012dac1  test    eax, eax
0x18012dac3  jz      loc_18012DC0C
0x18012dac9  mov     edx, 80090308h
0x18012dace  mov     ecx, eax
0x18012dad0  call    ConvertWin32StatusToSecStatus
0x18012dad5  jmp     loc_18012DC11
0x18012dada  mov     ecx, [rsp+48h+TokenInformationLength]
0x18012dade  call    LsapAllocate
0x18012dae3  mov     r14, rax
0x18012dae6  test    rax, rax
0x18012dae9  jnz     short loc_18012DAF5
0x18012daeb  mov     eax, 80090300h
0x18012daf0  jmp     loc_18012DC11
0x18012daf5  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18012dafa  lea     rax, [rsp+48h+TokenInformationLength]
0x18012daff  xor     edi, edi
0x18012db01  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18012db06  mov     r8, r14; TokenInformation
0x18012db09  mov     rcx, rsi; TokenHandle
0x18012db0c  lea     edx, [rdi+19h]; TokenInformationClass
0x18012db0f  call    cs:__imp_GetTokenInformation
0x18012db16  nop     dword ptr [rax+rax+00h]
0x18012db1b  test    eax, eax
0x18012db1d  jnz     short loc_18012DB41
0x18012db1f  call    cs:__imp_GetLastError
0x18012db26  nop     dword ptr [rax+rax+00h]
0x18012db2b  mov     ecx, eax
0x18012db2d  mov     edx, 80090308h
0x18012db32  call    ConvertWin32StatusToSecStatus
0x18012db37  mov     ebx, eax
0x18012db39  test    eax, eax
0x18012db3b  js      loc_18012DBEE
0x18012db41  xor     edx, edx; DomainSid
0x18012db43  lea     r9, [rsp+48h+cbSid]; cbSid
0x18012db48  xor     r8d, r8d; pSid
0x18012db4b  lea     esi, [rdx+42h]
0x18012db4e  mov     ecx, esi; WellKnownSidType
0x18012db50  call    cs:__imp_CreateWellKnownSid
0x18012db57  nop     dword ptr [rax+rax+00h]
0x18012db5c  test    eax, eax
0x18012db5e  jnz     loc_18012DBE9
0x18012db64  call    cs:__imp_GetLastError
0x18012db6b  nop     dword ptr [rax+rax+00h]
0x18012db70  cmp     eax, 7Ah ; 'z'
0x18012db73  jnz     short loc_18012DBB7
0x18012db75  mov     ecx, [rsp+48h+cbSid]
0x18012db79  call    LsapAllocate
0x18012db7e  mov     rdi, rax
0x18012db81  test    rax, rax
0x18012db84  jnz     short loc_18012DB8D
0x18012db86  mov     ebx, 80090300h
0x18012db8b  jmp     short loc_18012DBEE
0x18012db8d  lea     r9, [rsp+48h+cbSid]; cbSid
0x18012db92  mov     r8, rax; pSid
0x18012db95  xor     edx, edx; DomainSid
0x18012db97  mov     ecx, esi; WellKnownSidType
0x18012db99  call    cs:__imp_CreateWellKnownSid
0x18012dba0  nop     dword ptr [rax+rax+00h]
0x18012dba5  test    eax, eax
0x18012dba7  jnz     short loc_18012DBC9
0x18012dba9  call    cs:__imp_GetLastError
0x18012dbb0  nop     dword ptr [rax+rax+00h]
0x18012dbb5  jmp     short loc_18012DBBB
0x18012dbb7  test    eax, eax
0x18012dbb9  jz      short loc_18012DBE9
0x18012dbbb  mov     edx, 80090330h
0x18012dbc0  mov     ecx, eax
0x18012dbc2  call    ConvertWin32StatusToSecStatus
0x18012dbc7  mov     ebx, eax
0x18012dbc9  test    ebx, ebx
0x18012dbcb  js      short loc_18012DBEE
0x18012dbcd  mov     rdx, [r14]; Sid2
0x18012dbd0  mov     rcx, rdi; Sid1
0x18012dbd3  call    cs:__imp_RtlEqualSid
0x18012dbda  nop     dword ptr [rax+rax+00h]
0x18012dbdf  test    al, al
0x18012dbe1  jz      short loc_18012DBEE
0x18012dbe3  mov     byte ptr [r15], 1
0x18012dbe7  jmp     short loc_18012DBEE
0x18012dbe9  mov     ebx, 80090330h
0x18012dbee  mov     rcx, r14; struct _RTL_BALANCED_NODE *
0x18012dbf1  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18012dbf6  test    rdi, rdi
0x18012dbf9  jz      loc_18012DA7C
0x18012dbff  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18012dc02  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18012dc07  jmp     loc_18012DA7C
0x18012dc0c  mov     eax, 80090330h
0x18012dc11  mov     rbx, [rsp+48h+arg_10]
0x18012dc16  mov     rsi, [rsp+48h+arg_18]
0x18012dc1b  add     rsp, 30h
0x18012dc1f  pop     r15
0x18012dc21  pop     r14
0x18012dc23  pop     rdi
0x18012dc24  retn
```
