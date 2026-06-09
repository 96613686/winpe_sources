# IsProcessUserService(void *)

- ea: `0x18001f0f8`
- end: `0x18001f24a`
- name: `?IsProcessUserService@@YAHPEAX@Z`
- size: `338`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ecd0`

## callees

- `0x1800077a0`
- `0x18001f0f8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18001f207`
- `ntdll!RtlCompareUnicodeString` at `0x18001f207`
- `ntdll!NtQueryInformationToken` at `0x18001f190`
- `ntdll!NtQueryInformationToken` at `0x18001f1dd`
- `ntdll!NtQueryInformationToken` at `0x18001f190`
- `ntdll!NtQueryInformationToken` at `0x18001f1dd`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001f142`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001f142`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f123`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f15b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f15b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f1b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f1b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f223`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f223`

## string_xrefs

- `0x18001f137`: `WIN://SCMUserService`
- `0x18001f237`: `IsProcessUserService: OpenProcessToken for process handle %x failed `

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
0x18001f0f8  mov     [rsp-18h+arg_0], rbx
0x18001f0fd  push    rbp
0x18001f0fe  push    rsi
0x18001f0ff  push    rdi
0x18001f100  mov     rbp, rsp
0x18001f103  sub     rsp, 40h
0x18001f107  xor     esi, esi
0x18001f109  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001f10d  xorps   xmm0, xmm0
0x18001f110  mov     [rbp+TokenHandle], rsi
0x18001f114  mov     rbx, rcx
0x18001f117  mov     [rbp+TokenInformationLength], esi
0x18001f11a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001f11e  lea     edi, [rsi+8]
0x18001f121  mov     edx, edi; DesiredAccess
0x18001f123  call    cs:__imp_OpenProcessToken
0x18001f12a  nop     dword ptr [rax+rax+00h]
0x18001f12f  test    eax, eax
0x18001f131  jz      loc_18001F234
0x18001f137  lea     rdx, aWinScmuserserv; "WIN://SCMUserService"
0x18001f13e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001f142  call    cs:__imp_RtlInitUnicodeStringEx
0x18001f149  nop     dword ptr [rax+rax+00h]
0x18001f14e  test    eax, eax
0x18001f150  jz      short loc_18001F177
0x18001f152  mov     rcx, [rbp+TokenHandle]; hObject
0x18001f156  test    rcx, rcx
0x18001f159  jz      short loc_18001F167
0x18001f15b  call    cs:__imp_CloseHandle
0x18001f162  nop     dword ptr [rax+rax+00h]
0x18001f167  mov     rbx, [rsp+40h+arg_0]
0x18001f16c  mov     eax, esi
0x18001f16e  add     rsp, 40h
0x18001f172  pop     rdi
0x18001f173  pop     rsi
0x18001f174  pop     rbp
0x18001f175  retn
0x18001f177  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f17b  lea     rax, [rbp+TokenInformationLength]
0x18001f17f  xor     r9d, r9d; TokenInformationLength
0x18001f182  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001f187  xor     r8d, r8d; TokenInformation
0x18001f18a  lea     edi, [r9+27h]
0x18001f18e  mov     edx, edi; TokenInformationClass
0x18001f190  call    cs:__imp_NtQueryInformationToken
0x18001f197  nop     dword ptr [rax+rax+00h]
0x18001f19c  cmp     eax, 0C0000023h
0x18001f1a1  jnz     short loc_18001F152
0x18001f1a3  mov     eax, [rbp+TokenInformationLength]
0x18001f1a6  test    eax, eax
0x18001f1a8  jz      short loc_18001F152
0x18001f1aa  mov     edx, eax
0x18001f1ac  lea     ecx, [rdi+19h]; uFlags
0x18001f1af  shl     rdx, 4; uBytes
0x18001f1b3  call    cs:__imp_LocalAlloc
0x18001f1ba  nop     dword ptr [rax+rax+00h]
0x18001f1bf  mov     rbx, rax
0x18001f1c2  test    rax, rax
0x18001f1c5  jz      short loc_18001F152
0x18001f1c7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001f1cb  lea     rax, [rbp+TokenInformationLength]
0x18001f1cf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f1d3  mov     r8, rbx; TokenInformation
0x18001f1d6  mov     edx, edi; TokenInformationClass
0x18001f1d8  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001f1dd  call    cs:__imp_NtQueryInformationToken
0x18001f1e4  nop     dword ptr [rax+rax+00h]
0x18001f1e9  test    eax, eax
0x18001f1eb  js      short loc_18001F220
0x18001f1ed  xor     edi, edi
0x18001f1ef  cmp     edi, [rbx+4]
0x18001f1f2  jnb     short loc_18001F220
0x18001f1f4  mov     rax, [rbx+8]
0x18001f1f8  lea     rcx, [rdi+rdi*4]
0x18001f1fc  mov     r8b, 1; CaseInsensitive
0x18001f1ff  lea     rdx, [rax+rcx*8]; String2
0x18001f203  lea     rcx, [rbp+DestinationString]; String1
0x18001f207  call    cs:__imp_RtlCompareUnicodeString
0x18001f20e  nop     dword ptr [rax+rax+00h]
0x18001f213  test    eax, eax
0x18001f215  jz      short loc_18001F21B
0x18001f217  inc     edi
0x18001f219  jmp     short loc_18001F1EF
0x18001f21b  mov     esi, 1
0x18001f220  mov     rcx, rbx; hMem
0x18001f223  call    cs:__imp_LocalFree
0x18001f22a  nop     dword ptr [rax+rax+00h]
0x18001f22f  jmp     loc_18001F152
0x18001f234  mov     r8, rbx
0x18001f237  lea     rdx, aIsprocessusers; "IsProcessUserService: OpenProcessToken "...
0x18001f23e  mov     ecx, edi; int
0x18001f240  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f245  jmp     loc_18001F152
```
