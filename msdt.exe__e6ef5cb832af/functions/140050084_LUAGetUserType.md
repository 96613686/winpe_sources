# LUAGetUserType

- ea: `0x140050084`
- end: `0x14005019c`
- name: `LUAGetUserType`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140018b5c`
- `0x1400468d0`

## callees

- `0x140050084`
- `0x1400501a4`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x1400500e1`
- `ntdll!NtOpenProcessToken` at `0x1400500e1`
- `ntdll!NtQueryInformationToken` at `0x140050151`
- `ntdll!NtQueryInformationToken` at `0x140050151`
- `ntdll!NtClose` at `0x140050180`
- `ntdll!NtClose` at `0x140050180`
- `ntdll!NtOpenThreadToken` at `0x1400500c2`
- `ntdll!NtOpenThreadToken` at `0x1400500c2`

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
0x140050084  mov     [rsp-18h+arg_8], rbx
0x140050089  mov     [rsp-18h+TokenInformation], rcx
0x14005008e  push    rbp
0x14005008f  push    rsi
0x140050090  push    rdi
0x140050091  mov     rbp, rsp
0x140050094  sub     rsp, 30h
0x140050098  xor     r8d, r8d; OpenAsSelf
0x14005009b  mov     [rbp+TokenHandle], 0
0x1400500a3  mov     rdi, rdx
0x1400500a6  mov     dword ptr [rbp+TokenInformation], 0
0x1400500ad  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400500b1  mov     [rbp+arg_10], 0
0x1400500b8  lea     esi, [r8+8]
0x1400500bc  mov     edx, esi; DesiredAccess
0x1400500be  lea     rcx, [r8-2]; ThreadHandle
0x1400500c2  call    cs:__imp_NtOpenThreadToken
0x1400500c9  nop     dword ptr [rax+rax+00h]
0x1400500ce  mov     ebx, eax
0x1400500d0  cmp     eax, 0C000007Ch
0x1400500d5  jnz     short loc_1400500EF
0x1400500d7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400500db  mov     edx, esi; DesiredAccess
0x1400500dd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400500e1  call    cs:__imp_NtOpenProcessToken
0x1400500e8  nop     dword ptr [rax+rax+00h]
0x1400500ed  mov     ebx, eax
0x1400500ef  test    ebx, ebx
0x1400500f1  js      loc_14005018C
0x1400500f7  mov     rsi, [rbp+TokenHandle]
0x1400500fb  lea     r8, [rbp+arg_10]
0x1400500ff  mov     rcx, rsi; TokenHandle
0x140050102  lea     rdx, [rbp+TokenInformation]
0x140050106  call    LUAIsElevatedToken
0x14005010b  mov     ebx, eax
0x14005010d  test    eax, eax
0x14005010f  js      short loc_140050178
0x140050111  cmp     dword ptr [rbp+TokenInformation], 0
0x140050115  jz      short loc_14005011F
0x140050117  mov     dword ptr [rdi], 0
0x14005011d  jmp     short loc_14005012B
0x14005011f  mov     eax, [rbp+arg_10]
0x140050122  neg     eax
0x140050124  sbb     ecx, ecx
0x140050126  add     ecx, 2
0x140050129  mov     [rdi], ecx
0x14005012b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14005012f  lea     rax, [rbp+arg_10]
0x140050133  mov     r9d, 4; TokenInformationLength
0x140050139  mov     dword ptr [rbp+TokenInformation], 0
0x140050140  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140050144  mov     [rbp+arg_10], r9d
0x140050148  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14005014d  lea     edx, [r9+16h]; TokenInformationClass
0x140050151  call    cs:__imp_NtQueryInformationToken
0x140050158  nop     dword ptr [rax+rax+00h]
0x14005015d  mov     ebx, eax
0x14005015f  test    eax, eax
0x140050161  js      short loc_140050178
0x140050163  cmp     dword ptr [rbp+TokenInformation], 0
0x140050167  jz      short loc_140050178
0x140050169  mov     ecx, [rdi]
0x14005016b  lea     eax, [rcx-10h]
0x14005016e  cmp     eax, 2
0x140050171  jbe     short loc_140050176
0x140050173  add     ecx, 10h
0x140050176  mov     [rdi], ecx
0x140050178  test    rsi, rsi
0x14005017b  jz      short loc_14005018C
0x14005017d  mov     rcx, rsi; Handle
0x140050180  call    cs:__imp_NtClose
0x140050187  nop     dword ptr [rax+rax+00h]
0x14005018c  mov     eax, ebx
0x14005018e  mov     rbx, [rsp+30h+arg_8]
0x140050193  add     rsp, 30h
0x140050197  pop     rdi
0x140050198  pop     rsi
0x140050199  pop     rbp
0x14005019a  retn
```
