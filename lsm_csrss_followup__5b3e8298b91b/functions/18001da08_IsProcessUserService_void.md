# IsProcessUserService(void *)

- ea: `0x18001da08`
- end: `0x18001db29`
- name: `?IsProcessUserService@@YAHPEAX@Z`
- size: `289`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d640`

## callees

- `0x1800074c0`
- `0x18001da08`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18001daf2`
- `ntdll!RtlCompareUnicodeString` at `0x18001daf2`
- `ntdll!NtQueryInformationToken` at `0x18001da8d`
- `ntdll!NtQueryInformationToken` at `0x18001dace`
- `ntdll!NtQueryInformationToken` at `0x18001da8d`
- `ntdll!NtQueryInformationToken` at `0x18001dace`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001da4c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001da4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001da33`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001da33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001daaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001daaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001db08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001db08`

## string_xrefs

- `0x18001da41`: `WIN://SCMUserService`
- `0x18001db16`: `IsProcessUserService: OpenProcessToken for process handle %x failed `

## pseudocode

```c
__int64 __fastcall IsProcessUserService(void *a1)
{
  unsigned int v1; // esi
  int v2; // ebx
  _QWORD *v4; // rbx
  __int64 i; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+30h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v2 = (int)a1;
  TokenInformationLength = 0;
  DestinationString = 0;
  if ( OpenProcessToken(a1, 8u, &TokenHandle) )
  {
    if ( !RtlInitUnicodeStringEx(&DestinationString, L"WIN://SCMUserService")
      && NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength) == -1073741789 )
    {
      if ( TokenInformationLength )
      {
        v4 = LocalAlloc(0x40u, 16LL * TokenInformationLength);
        if ( v4 )
        {
          if ( NtQueryInformationToken(
                 TokenHandle,
                 TokenSecurityAttributes,
                 v4,
                 TokenInformationLength,
                 &TokenInformationLength) >= 0 )
          {
            for ( i = 0; (unsigned int)i < *((_DWORD *)v4 + 1); i = (unsigned int)(i + 1) )
            {
              if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v4[1] + 40 * i), 1u) )
              {
                v1 = 1;
                break;
              }
            }
          }
          LocalFree(v4);
        }
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "IsProcessUserService: OpenProcessToken for process handle %x failed ", v2);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18001da08  mov     [rsp-18h+arg_0], rbx
0x18001da0d  push    rbp
0x18001da0e  push    rsi
0x18001da0f  push    rdi
0x18001da10  mov     rbp, rsp
0x18001da13  sub     rsp, 40h
0x18001da17  xor     esi, esi
0x18001da19  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001da1d  xorps   xmm0, xmm0
0x18001da20  mov     [rbp+TokenHandle], rsi
0x18001da24  mov     rbx, rcx
0x18001da27  mov     [rbp+TokenInformationLength], esi
0x18001da2a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001da2e  lea     edi, [rsi+8]
0x18001da31  mov     edx, edi; DesiredAccess
0x18001da33  call    cs:__imp_OpenProcessToken
0x18001da39  test    eax, eax
0x18001da3b  jz      loc_18001DB13
0x18001da41  lea     rdx, aWinScmuserserv; "WIN://SCMUserService"
0x18001da48  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001da4c  call    cs:__imp_RtlInitUnicodeStringEx
0x18001da52  test    eax, eax
0x18001da54  jz      short loc_18001DA74
0x18001da56  mov     rcx, [rbp+TokenHandle]; hObject
0x18001da5a  test    rcx, rcx
0x18001da5d  jz      short loc_18001DA65
0x18001da5f  call    cs:__imp_CloseHandle
0x18001da65  mov     rbx, [rsp+40h+arg_0]
0x18001da6a  mov     eax, esi
0x18001da6c  add     rsp, 40h
0x18001da70  pop     rdi
0x18001da71  pop     rsi
0x18001da72  pop     rbp
0x18001da73  retn
0x18001da74  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001da78  lea     rax, [rbp+TokenInformationLength]
0x18001da7c  xor     r9d, r9d; TokenInformationLength
0x18001da7f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001da84  xor     r8d, r8d; TokenInformation
0x18001da87  lea     edi, [r9+27h]
0x18001da8b  mov     edx, edi; TokenInformationClass
0x18001da8d  call    cs:__imp_NtQueryInformationToken
0x18001da93  cmp     eax, 0C0000023h
0x18001da98  jnz     short loc_18001DA56
0x18001da9a  mov     eax, [rbp+TokenInformationLength]
0x18001da9d  test    eax, eax
0x18001da9f  jz      short loc_18001DA56
0x18001daa1  mov     edx, eax
0x18001daa3  lea     ecx, [rdi+19h]; uFlags
0x18001daa6  shl     rdx, 4; uBytes
0x18001daaa  call    cs:__imp_LocalAlloc
0x18001dab0  mov     rbx, rax
0x18001dab3  test    rax, rax
0x18001dab6  jz      short loc_18001DA56
0x18001dab8  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001dabc  lea     rax, [rbp+TokenInformationLength]
0x18001dac0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001dac4  mov     r8, rbx; TokenInformation
0x18001dac7  mov     edx, edi; TokenInformationClass
0x18001dac9  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001dace  call    cs:__imp_NtQueryInformationToken
0x18001dad4  test    eax, eax
0x18001dad6  js      short loc_18001DB05
0x18001dad8  xor     edi, edi
0x18001dada  cmp     edi, [rbx+4]
0x18001dadd  jnb     short loc_18001DB05
0x18001dadf  mov     rax, [rbx+8]
0x18001dae3  lea     rcx, [rdi+rdi*4]
0x18001dae7  mov     r8b, 1; CaseInsensitive
0x18001daea  lea     rdx, [rax+rcx*8]; String2
0x18001daee  lea     rcx, [rbp+DestinationString]; String1
0x18001daf2  call    cs:__imp_RtlCompareUnicodeString
0x18001daf8  test    eax, eax
0x18001dafa  jz      short loc_18001DB00
0x18001dafc  inc     edi
0x18001dafe  jmp     short loc_18001DADA
0x18001db00  mov     esi, 1
0x18001db05  mov     rcx, rbx; hMem
0x18001db08  call    cs:__imp_LocalFree
0x18001db0e  jmp     loc_18001DA56
0x18001db13  mov     r8, rbx
0x18001db16  lea     rdx, aIsprocessusers; "IsProcessUserService: OpenProcessToken "...
0x18001db1d  mov     ecx, edi; int
0x18001db1f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001db24  jmp     loc_18001DA56
```
