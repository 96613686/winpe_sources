# LUAGetUserType

- ea: `0x14001737c`
- end: `0x14001747b`
- name: `LUAGetUserType`
- size: `255`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000791c`

## callees

- `0x14001737c`
- `0x140017484`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x1400173d3`
- `ntdll!NtOpenProcessToken` at `0x1400173d3`
- `ntdll!NtQueryInformationToken` at `0x14001743d`
- `ntdll!NtQueryInformationToken` at `0x14001743d`
- `ntdll!NtClose` at `0x140017466`
- `ntdll!NtClose` at `0x140017466`
- `ntdll!NtOpenThreadToken` at `0x1400173ba`
- `ntdll!NtOpenThreadToken` at `0x1400173ba`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(__int64 a1, int *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rsi
  int v5; // ecx
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation_4; // [rsp+54h] [rbp+24h]
  ULONG ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation_4 = HIDWORD(a1);
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v3 == -1073741700 )
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v3 >= 0 )
  {
    v4 = TokenHandle;
    v3 = LUAIsElevatedToken(TokenHandle);
    if ( v3 >= 0 )
    {
      *a2 = TokenInformation ? 0 : 2 - (ReturnLength != 0);
      TokenInformation = 0;
      ReturnLength = 4;
      v3 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength);
      if ( v3 >= 0 )
      {
        if ( TokenInformation )
        {
          v5 = *a2;
          if ( (unsigned int)(*a2 - 16) > 2 )
            v5 += 16;
          *a2 = v5;
        }
      }
    }
    if ( v4 )
      NtClose(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001737c  mov     [rsp-18h+arg_8], rbx
0x140017381  mov     [rsp-18h+TokenInformation], rcx
0x140017386  push    rbp
0x140017387  push    rsi
0x140017388  push    rdi
0x140017389  mov     rbp, rsp
0x14001738c  sub     rsp, 30h
0x140017390  xor     r8d, r8d; OpenAsSelf
0x140017393  mov     [rbp+TokenHandle], 0
0x14001739b  mov     rdi, rdx
0x14001739e  mov     dword ptr [rbp+TokenInformation], 0
0x1400173a5  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400173a9  mov     [rbp+arg_10], 0
0x1400173b0  lea     esi, [r8+8]
0x1400173b4  mov     edx, esi; DesiredAccess
0x1400173b6  lea     rcx, [r8-2]; ThreadHandle
0x1400173ba  call    cs:__imp_NtOpenThreadToken
0x1400173c0  mov     ebx, eax
0x1400173c2  cmp     eax, 0C000007Ch
0x1400173c7  jnz     short loc_1400173DB
0x1400173c9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400173cd  mov     edx, esi; DesiredAccess
0x1400173cf  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400173d3  call    cs:__imp_NtOpenProcessToken
0x1400173d9  mov     ebx, eax
0x1400173db  test    ebx, ebx
0x1400173dd  js      loc_14001746C
0x1400173e3  mov     rsi, [rbp+TokenHandle]
0x1400173e7  lea     r8, [rbp+arg_10]
0x1400173eb  mov     rcx, rsi; TokenHandle
0x1400173ee  lea     rdx, [rbp+TokenInformation]
0x1400173f2  call    LUAIsElevatedToken
0x1400173f7  mov     ebx, eax
0x1400173f9  test    eax, eax
0x1400173fb  js      short loc_14001745E
0x1400173fd  cmp     dword ptr [rbp+TokenInformation], 0
0x140017401  jz      short loc_14001740B
0x140017403  mov     dword ptr [rdi], 0
0x140017409  jmp     short loc_140017417
0x14001740b  mov     eax, [rbp+arg_10]
0x14001740e  neg     eax
0x140017410  sbb     ecx, ecx
0x140017412  add     ecx, 2
0x140017415  mov     [rdi], ecx
0x140017417  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14001741b  lea     rax, [rbp+arg_10]
0x14001741f  mov     r9d, 4; TokenInformationLength
0x140017425  mov     dword ptr [rbp+TokenInformation], 0
0x14001742c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140017430  mov     [rbp+arg_10], r9d
0x140017434  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140017439  lea     edx, [r9+16h]; TokenInformationClass
0x14001743d  call    cs:__imp_NtQueryInformationToken
0x140017443  mov     ebx, eax
0x140017445  test    eax, eax
0x140017447  js      short loc_14001745E
0x140017449  cmp     dword ptr [rbp+TokenInformation], 0
0x14001744d  jz      short loc_14001745E
0x14001744f  mov     ecx, [rdi]
0x140017451  lea     eax, [rcx-10h]
0x140017454  cmp     eax, 2
0x140017457  jbe     short loc_14001745C
0x140017459  add     ecx, 10h
0x14001745c  mov     [rdi], ecx
0x14001745e  test    rsi, rsi
0x140017461  jz      short loc_14001746C
0x140017463  mov     rcx, rsi; Handle
0x140017466  call    cs:__imp_NtClose
0x14001746c  mov     eax, ebx
0x14001746e  mov     rbx, [rsp+30h+arg_8]
0x140017473  add     rsp, 30h
0x140017477  pop     rdi
0x140017478  pop     rsi
0x140017479  pop     rbp
0x14001747a  retn
```
