# OneXGetTokenInformation

- ea: `0x180031584`
- end: `0x180031678`
- name: `OneXGetTokenInformation`
- size: `244`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003184c`

## callees

- `0x180031584`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031638`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800315d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003162e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800315d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003162e`
- `MobileNetworking!FreeMemory` at `0x180031656`
- `MobileNetworking!FreeMemory` at `0x180031656`
- `MobileNetworking!AllocateMemory` at `0x180031602`
- `MobileNetworking!AllocateMemory` at `0x180031602`

## string_xrefs

- `0x1800315f0`: `OneXGetTokenInformation`
- `0x18003164a`: `OneXGetTokenInformation`

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
0x180031584  mov     rax, rsp
0x180031587  mov     [rax+18h], rbx
0x18003158b  mov     [rax+20h], rsi
0x18003158f  push    rdi
0x180031590  sub     rsp, 30h
0x180031594  mov     dword ptr [rax+8], 0
0x18003159b  mov     rdi, rdx
0x18003159e  mov     qword ptr [rax+10h], 0
0x1800315a6  mov     rsi, rcx
0x1800315a9  mov     qword ptr [rdx], 0
0x1800315b0  test    rcx, rcx
0x1800315b3  jnz     short loc_1800315BD
0x1800315b5  lea     ebx, [rcx+6]
0x1800315b8  jmp     loc_180031644
0x1800315bd  xor     r9d, r9d; TokenInformationLength
0x1800315c0  lea     rax, [rsp+38h+TokenInformationLength]
0x1800315c5  xor     r8d, r8d; TokenInformation
0x1800315c8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800315cd  lea     edx, [r9+1]; TokenInformationClass
0x1800315d1  call    cs:__imp_GetTokenInformation
0x1800315d7  test    eax, eax
0x1800315d9  jnz     short loc_180031610
0x1800315db  call    cs:__imp_GetLastError
0x1800315e1  mov     ebx, eax
0x1800315e3  cmp     eax, 7Ah ; 'z'
0x1800315e6  jz      short loc_1800315EC
0x1800315e8  test    eax, eax
0x1800315ea  jnz     short loc_180031644
0x1800315ec  mov     ecx, [rsp+38h+TokenInformationLength]
0x1800315f0  lea     r8, aOnexgettokenin; "OneXGetTokenInformation"
0x1800315f7  mov     r9d, 3B5h
0x1800315fd  lea     rdx, [rsp+38h+TokenInformation]
0x180031602  call    cs:__imp_AllocateMemory
0x180031608  mov     ebx, eax
0x18003160a  test    eax, eax
0x18003160c  jnz     short loc_180031644
0x18003160e  jmp     short loc_180031612
0x180031610  xor     ebx, ebx
0x180031612  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180031617  lea     rax, [rsp+38h+TokenInformationLength]
0x18003161c  mov     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180031621  mov     edx, 1; TokenInformationClass
0x180031626  mov     rcx, rsi; TokenHandle
0x180031629  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003162e  call    cs:__imp_GetTokenInformation
0x180031634  test    eax, eax
0x180031636  jnz     short loc_18003165E
0x180031638  call    cs:__imp_GetLastError
0x18003163e  mov     ebx, eax
0x180031640  test    eax, eax
0x180031642  jz      short loc_18003165E
0x180031644  mov     r8d, 3C5h
0x18003164a  lea     rdx, aOnexgettokenin; "OneXGetTokenInformation"
0x180031651  lea     rcx, [rsp+38h+TokenInformation]
0x180031656  call    cs:__imp_FreeMemory
0x18003165c  jmp     short loc_180031666
0x18003165e  mov     rax, [rsp+38h+TokenInformation]
0x180031663  mov     [rdi], rax
0x180031666  mov     rsi, [rsp+38h+arg_18]
0x18003166b  mov     eax, ebx
0x18003166d  mov     rbx, [rsp+38h+arg_10]
0x180031672  add     rsp, 30h
0x180031676  pop     rdi
0x180031677  retn
```
