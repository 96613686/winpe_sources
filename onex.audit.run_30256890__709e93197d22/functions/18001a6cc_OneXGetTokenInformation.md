# OneXGetTokenInformation

- ea: `0x18001a6cc`
- end: `0x18001a7c0`
- name: `OneXGetTokenInformation`
- size: `244`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002470`
- `0x180011310`
- `0x18001c840`
- `0x18001e290`
- `0x180029668`

## callees

- `0x18001a6cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a780`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a719`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a776`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a719`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a776`
- `MobileNetworking!AllocateMemory` at `0x18001a74a`
- `MobileNetworking!AllocateMemory` at `0x18001a74a`
- `MobileNetworking!FreeMemory` at `0x18001a79e`
- `MobileNetworking!FreeMemory` at `0x18001a79e`

## string_xrefs

- `0x18001a738`: `OneXGetTokenInformation`
- `0x18001a792`: `OneXGetTokenInformation`

## pseudocode

```c
__int64 __fastcall OneXGetTokenInformation(HANDLE TokenHandle, LPVOID *a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  LPVOID TokenInformation; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  TokenInformation = 0;
  *a2 = 0;
  if ( TokenHandle )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError != 122 && LastError )
        goto LABEL_11;
      v4 = AllocateMemory(TokenInformationLength, &TokenInformation, "OneXGetTokenInformation", 949);
      if ( v4 )
        goto LABEL_11;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength)
      || (v4 = GetLastError()) == 0 )
    {
      *a2 = TokenInformation;
      return v4;
    }
  }
  else
  {
    v4 = 6;
  }
LABEL_11:
  FreeMemory(&TokenInformation, "OneXGetTokenInformation", 965);
  return v4;
}

```

## disassembly

```asm
0x18001a6cc  mov     rax, rsp
0x18001a6cf  mov     [rax+18h], rbx
0x18001a6d3  mov     [rax+20h], rsi
0x18001a6d7  push    rdi
0x18001a6d8  sub     rsp, 30h
0x18001a6dc  mov     dword ptr [rax+8], 0
0x18001a6e3  mov     rdi, rdx
0x18001a6e6  mov     qword ptr [rax+10h], 0
0x18001a6ee  mov     rsi, rcx
0x18001a6f1  mov     qword ptr [rdx], 0
0x18001a6f8  test    rcx, rcx
0x18001a6fb  jnz     short loc_18001A705
0x18001a6fd  lea     ebx, [rcx+6]
0x18001a700  jmp     loc_18001A78C
0x18001a705  xor     r9d, r9d; TokenInformationLength
0x18001a708  lea     rax, [rsp+38h+TokenInformationLength]
0x18001a70d  xor     r8d, r8d; TokenInformation
0x18001a710  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001a715  lea     edx, [r9+1]; TokenInformationClass
0x18001a719  call    cs:__imp_GetTokenInformation
0x18001a71f  test    eax, eax
0x18001a721  jnz     short loc_18001A758
0x18001a723  call    cs:__imp_GetLastError
0x18001a729  mov     ebx, eax
0x18001a72b  cmp     eax, 7Ah ; 'z'
0x18001a72e  jz      short loc_18001A734
0x18001a730  test    eax, eax
0x18001a732  jnz     short loc_18001A78C
0x18001a734  mov     ecx, [rsp+38h+TokenInformationLength]
0x18001a738  lea     r8, aOnexgettokenin; "OneXGetTokenInformation"
0x18001a73f  mov     r9d, 3B5h
0x18001a745  lea     rdx, [rsp+38h+TokenInformation]
0x18001a74a  call    cs:__imp_AllocateMemory
0x18001a750  mov     ebx, eax
0x18001a752  test    eax, eax
0x18001a754  jz      short loc_18001A75A
0x18001a756  jmp     short loc_18001A78C
0x18001a758  xor     ebx, ebx
0x18001a75a  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001a75f  lea     rax, [rsp+38h+TokenInformationLength]
0x18001a764  mov     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18001a769  mov     edx, 1; TokenInformationClass
0x18001a76e  mov     rcx, rsi; TokenHandle
0x18001a771  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001a776  call    cs:__imp_GetTokenInformation
0x18001a77c  test    eax, eax
0x18001a77e  jnz     short loc_18001A7A6
0x18001a780  call    cs:__imp_GetLastError
0x18001a786  mov     ebx, eax
0x18001a788  test    eax, eax
0x18001a78a  jz      short loc_18001A7A6
0x18001a78c  mov     r8d, 3C5h
0x18001a792  lea     rdx, aOnexgettokenin; "OneXGetTokenInformation"
0x18001a799  lea     rcx, [rsp+38h+TokenInformation]
0x18001a79e  call    cs:__imp_FreeMemory
0x18001a7a4  jmp     short loc_18001A7AE
0x18001a7a6  mov     rax, [rsp+38h+TokenInformation]
0x18001a7ab  mov     [rdi], rax
0x18001a7ae  mov     rsi, [rsp+38h+arg_18]
0x18001a7b3  mov     eax, ebx
0x18001a7b5  mov     rbx, [rsp+38h+arg_10]
0x18001a7ba  add     rsp, 30h
0x18001a7be  pop     rdi
0x18001a7bf  retn
```
