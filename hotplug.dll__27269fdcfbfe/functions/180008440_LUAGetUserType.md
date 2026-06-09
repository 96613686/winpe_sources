# LUAGetUserType

- ea: `0x180008440`
- end: `0x18000853f`
- name: `LUAGetUserType`
- size: `255`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800073b0`

## callees

- `0x180008440`
- `0x180008548`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18000847e`
- `ntdll!NtOpenThreadToken` at `0x18000847e`
- `ntdll!NtQueryInformationToken` at `0x180008501`
- `ntdll!NtQueryInformationToken` at `0x180008501`
- `ntdll!NtOpenProcessToken` at `0x180008497`
- `ntdll!NtOpenProcessToken` at `0x180008497`
- `ntdll!NtClose` at `0x18000852a`
- `ntdll!NtClose` at `0x18000852a`

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
0x180008440  mov     [rsp-18h+arg_8], rbx
0x180008445  mov     [rsp-18h+TokenInformation], rcx
0x18000844a  push    rbp
0x18000844b  push    rsi
0x18000844c  push    rdi
0x18000844d  mov     rbp, rsp
0x180008450  sub     rsp, 30h
0x180008454  xor     r8d, r8d; OpenAsSelf
0x180008457  mov     [rbp+TokenHandle], 0
0x18000845f  mov     rdi, rdx
0x180008462  mov     dword ptr [rbp+TokenInformation], 0
0x180008469  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000846d  mov     [rbp+arg_10], 0
0x180008474  lea     esi, [r8+8]
0x180008478  mov     edx, esi; DesiredAccess
0x18000847a  lea     rcx, [r8-2]; ThreadHandle
0x18000847e  call    cs:__imp_NtOpenThreadToken
0x180008484  mov     ebx, eax
0x180008486  cmp     eax, 0C000007Ch
0x18000848b  jnz     short loc_18000849F
0x18000848d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180008491  mov     edx, esi; DesiredAccess
0x180008493  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180008497  call    cs:__imp_NtOpenProcessToken
0x18000849d  mov     ebx, eax
0x18000849f  test    ebx, ebx
0x1800084a1  js      loc_180008530
0x1800084a7  mov     rsi, [rbp+TokenHandle]
0x1800084ab  lea     r8, [rbp+arg_10]
0x1800084af  mov     rcx, rsi; TokenHandle
0x1800084b2  lea     rdx, [rbp+TokenInformation]
0x1800084b6  call    LUAIsElevatedToken
0x1800084bb  mov     ebx, eax
0x1800084bd  test    eax, eax
0x1800084bf  js      short loc_180008522
0x1800084c1  cmp     dword ptr [rbp+TokenInformation], 0
0x1800084c5  jz      short loc_1800084CF
0x1800084c7  mov     dword ptr [rdi], 0
0x1800084cd  jmp     short loc_1800084DB
0x1800084cf  mov     eax, [rbp+arg_10]
0x1800084d2  neg     eax
0x1800084d4  sbb     ecx, ecx
0x1800084d6  add     ecx, 2
0x1800084d9  mov     [rdi], ecx
0x1800084db  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800084df  lea     rax, [rbp+arg_10]
0x1800084e3  mov     r9d, 4; TokenInformationLength
0x1800084e9  mov     dword ptr [rbp+TokenInformation], 0
0x1800084f0  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800084f4  mov     [rbp+arg_10], r9d
0x1800084f8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800084fd  lea     edx, [r9+16h]; TokenInformationClass
0x180008501  call    cs:__imp_NtQueryInformationToken
0x180008507  mov     ebx, eax
0x180008509  test    eax, eax
0x18000850b  js      short loc_180008522
0x18000850d  cmp     dword ptr [rbp+TokenInformation], 0
0x180008511  jz      short loc_180008522
0x180008513  mov     ecx, [rdi]
0x180008515  lea     eax, [rcx-10h]
0x180008518  cmp     eax, 2
0x18000851b  jbe     short loc_180008520
0x18000851d  add     ecx, 10h
0x180008520  mov     [rdi], ecx
0x180008522  test    rsi, rsi
0x180008525  jz      short loc_180008530
0x180008527  mov     rcx, rsi; Handle
0x18000852a  call    cs:__imp_NtClose
0x180008530  mov     eax, ebx
0x180008532  mov     rbx, [rsp+30h+arg_8]
0x180008537  add     rsp, 30h
0x18000853b  pop     rdi
0x18000853c  pop     rsi
0x18000853d  pop     rbp
0x18000853e  retn
```
