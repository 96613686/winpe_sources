# Pku2uLoadDH(void)

- ea: `0x180030be0`
- end: `0x180030de8`
- name: `?Pku2uLoadDH@@YAHXZ`
- size: `520`
- prototype: `int(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800302f0`
- `0x1800370d0`

## callees

- `0x1800160e0`
- `0x180023cb8`
- `0x180023ce0`
- `0x18003087c`
- `0x180030be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030dcf`
- `ntdll!RtlInitializeCriticalSection` at `0x180030d54`
- `ntdll!RtlInitializeCriticalSection` at `0x180030d54`
- `ntdll!NtSetInformationThread` at `0x180030c77`
- `ntdll!NtSetInformationThread` at `0x180030dc4`
- `ntdll!NtSetInformationThread` at `0x180030c77`
- `ntdll!NtSetInformationThread` at `0x180030dc4`
- `ntdll!NtOpenThreadToken` at `0x180030c2b`
- `ntdll!NtOpenThreadToken` at `0x180030c2b`
- `CRYPTSP!CryptAcquireContextW` at `0x180030c9f`
- `CRYPTSP!CryptAcquireContextW` at `0x180030c9f`

## pseudocode

```c
__int64 Pku2uLoadDH(void)
{
  BOOL v1; // edi
  NTSTATUS v2; // ecx
  void *v3; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  ThreadInformation = 0;
  if ( Pku2uGlobalWellknownDomainParamtersLockInitialized )
    return 1;
  v1 = 0;
  v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073741700 )
  {
    if ( v2 == -1073741700 )
    {
      v3 = 0;
      TokenHandle = 0;
    }
    else
    {
      v3 = TokenHandle;
    }
    if ( !v3
      || NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0 )
    {
      if ( CryptAcquireContextW(&Pku2uGlobalCSPProvider, 0, 0, 0xDu, 0xF0000040) )
      {
        if ( (unsigned int)KerbUnpackData(&Pku2uGlobalEncodedMODPDHOID, 0xCu, 0xDu, &Pku2uGlobalEmpheralDHAlg) )
        {
          SetLastError(0x5AAu);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids);
        }
        else if ( RtlInitializeCriticalSection(&Pku2uGlobalWellknownDomainParamtersLock) >= 0 )
        {
          Pku2uGlobalWellknownDomainParamtersLockInitialized = 1;
          v1 = Pku2uInitDHWellknowDomainParametersDefaults() != 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids);
          SetLastError(0x5AAu);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids, LastError);
      }
    }
  }
  if ( TokenHandle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    CloseHandle(TokenHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x180030be0  mov     rax, rsp
0x180030be3  mov     [rax+18h], rbx
0x180030be7  mov     [rax+20h], rdi
0x180030beb  push    r15
0x180030bed  sub     rsp, 30h
0x180030bf1  cmp     cs:?Pku2uGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int Pku2uGlobalWellknownDomainParamtersLockInitialized
0x180030bf8  mov     qword ptr [rax+8], 0
0x180030c00  mov     qword ptr [rax+10h], 0
0x180030c08  jz      short loc_180030C14
0x180030c0a  mov     eax, 1
0x180030c0f  jmp     loc_180030DD7
0x180030c14  xor     edi, edi
0x180030c16  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180030c1b  lea     ebx, [rdi+1]
0x180030c1e  lea     r15, [rdi-2]
0x180030c22  mov     r8b, bl; OpenAsSelf
0x180030c25  mov     rcx, r15; ThreadHandle
0x180030c28  lea     edx, [rdi+0Ch]; DesiredAccess
0x180030c2b  call    cs:__imp_NtOpenThreadToken
0x180030c31  mov     edx, 80000000h
0x180030c36  mov     r8d, 0C000007Ch
0x180030c3c  mov     ecx, eax
0x180030c3e  add     eax, edx
0x180030c40  test    edx, eax
0x180030c42  jnz     short loc_180030C4D
0x180030c44  cmp     ecx, r8d
0x180030c47  jnz     loc_180030DAA
0x180030c4d  cmp     ecx, r8d
0x180030c50  jnz     short loc_180030C5B
0x180030c52  xor     eax, eax
0x180030c54  mov     [rsp+38h+TokenHandle], rax
0x180030c59  jmp     short loc_180030C60
0x180030c5b  mov     rax, [rsp+38h+TokenHandle]
0x180030c60  test    rax, rax
0x180030c63  jz      short loc_180030C85
0x180030c65  mov     r9d, 8; ThreadInformationLength
0x180030c6b  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180030c70  mov     rcx, r15; ThreadHandle
0x180030c73  lea     edx, [r9-3]; ThreadInformationClass
0x180030c77  call    cs:__imp_NtSetInformationThread
0x180030c7d  test    eax, eax
0x180030c7f  js      loc_180030DAA
0x180030c85  mov     r9d, 0Dh; dwProvType
0x180030c8b  mov     [rsp+38h+dwFlags], 0F0000040h; dwFlags
0x180030c93  xor     r8d, r8d; szProvider
0x180030c96  lea     rcx, ?Pku2uGlobalCSPProvider@@3_KA; phProv
0x180030c9d  xor     edx, edx; szContainer
0x180030c9f  call    cs:__imp_CryptAcquireContextW
0x180030ca5  test    eax, eax
0x180030ca7  jnz     short loc_180030CF3
0x180030ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cb0  lea     rax, WPP_GLOBAL_Control
0x180030cb7  cmp     rcx, rax
0x180030cba  jz      loc_180030DAA
0x180030cc0  test    [rcx+1Ch], bl
0x180030cc3  jz      loc_180030DAA
0x180030cc9  call    cs:__imp_GetLastError
0x180030ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cd6  lea     r8, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids
0x180030cdd  mov     edx, 0Ah
0x180030ce2  mov     r9d, eax
0x180030ce5  mov     rcx, [rcx+10h]
0x180030ce9  call    WPP_SF_d
0x180030cee  jmp     loc_180030DAA
0x180030cf3  mov     edx, 0Ch; unsigned int
0x180030cf8  lea     r9, ?Pku2uGlobalEmpheralDHAlg@@3PEAUKERB_ALGORITHM_IDENTIFIER@@EA; void **
0x180030cff  lea     rcx, ?Pku2uGlobalEncodedMODPDHOID@@3PAEA; unsigned __int8 *
0x180030d06  lea     r8d, [rdx+1]; unsigned int
0x180030d0a  call    ?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z; KerbUnpackData(uchar *,ulong,ulong,void * *)
0x180030d0f  test    eax, eax
0x180030d11  jz      short loc_180030D4D
0x180030d13  mov     ecx, 5AAh; dwErrCode
0x180030d18  call    cs:__imp_SetLastError
0x180030d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d25  lea     rax, WPP_GLOBAL_Control
0x180030d2c  cmp     rcx, rax
0x180030d2f  jz      short loc_180030DAA
0x180030d31  test    [rcx+1Ch], bl
0x180030d34  jz      short loc_180030DAA
0x180030d36  mov     rcx, [rcx+10h]
0x180030d3a  lea     r8, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids
0x180030d41  mov     edx, 0Bh
0x180030d46  call    WPP_SF_
0x180030d4b  jmp     short loc_180030DAA
0x180030d4d  lea     rcx, ?Pku2uGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180030d54  call    cs:__imp_RtlInitializeCriticalSection
0x180030d5a  test    eax, eax
0x180030d5c  jns     short loc_180030D98
0x180030d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d65  lea     rax, WPP_GLOBAL_Control
0x180030d6c  cmp     rcx, rax
0x180030d6f  jz      short loc_180030D8B
0x180030d71  test    [rcx+1Ch], bl
0x180030d74  jz      short loc_180030D8B
0x180030d76  mov     rcx, [rcx+10h]
0x180030d7a  lea     r8, WPP_ab3076db16bc34eed0dc663a0a4f0cac_Traceguids
0x180030d81  mov     edx, 0Ch
0x180030d86  call    WPP_SF_
0x180030d8b  mov     ecx, 5AAh; dwErrCode
0x180030d90  call    cs:__imp_SetLastError
0x180030d96  jmp     short loc_180030DAA
0x180030d98  mov     cs:?Pku2uGlobalWellknownDomainParamtersLockInitialized@@3HA, ebx; int Pku2uGlobalWellknownDomainParamtersLockInitialized
0x180030d9e  call    ?Pku2uInitDHWellknowDomainParametersDefaults@@YAHXZ; Pku2uInitDHWellknowDomainParametersDefaults(void)
0x180030da3  test    eax, eax
0x180030da5  mov     edi, eax
0x180030da7  cmovnz  edi, ebx
0x180030daa  cmp     [rsp+38h+TokenHandle], 0
0x180030db0  jz      short loc_180030DD5
0x180030db2  mov     r9d, 8; ThreadInformationLength
0x180030db8  lea     r8, [rsp+38h+TokenHandle]; ThreadInformation
0x180030dbd  mov     rcx, r15; ThreadHandle
0x180030dc0  lea     edx, [r9-3]; ThreadInformationClass
0x180030dc4  call    cs:__imp_NtSetInformationThread
0x180030dca  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180030dcf  call    cs:__imp_CloseHandle
0x180030dd5  mov     eax, edi
0x180030dd7  mov     rbx, [rsp+38h+arg_10]
0x180030ddc  mov     rdi, [rsp+38h+arg_18]
0x180030de1  add     rsp, 30h
0x180030de5  pop     r15
0x180030de7  retn
```
