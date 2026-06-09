# WcpFilterLoadWithPrivilege

- ea: `0x1800ad88c`
- end: `0x1800ad9f2`
- name: `WcpFilterLoadWithPrivilege`
- size: `358`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ad510`

## callees

- `0x1800acf90`
- `0x1800ad88c`
- `0x1800ae0cc`
- `0x1800ae2f8`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1800ad9ca`
- `ntdll!NtSetInformationThread` at `0x1800ad9ca`
- `ntdll!RtlImpersonateSelf` at `0x1800ad912`
- `ntdll!RtlImpersonateSelf` at `0x1800ad912`
- `ntdll!NtClose` at `0x1800ad99f`
- `ntdll!NtClose` at `0x1800ad99f`
- `ntdll!NtOpenThreadToken` at `0x1800ad8e8`
- `ntdll!NtOpenThreadToken` at `0x1800ad934`
- `ntdll!NtOpenThreadToken` at `0x1800ad8e8`
- `ntdll!NtOpenThreadToken` at `0x1800ad934`

## pseudocode

```c
__int64 __fastcall WcpFilterLoadWithPrivilege(void *Src)
{
  int v1; // edi
  int v3; // eax
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  TokenHandle = (void *)-1LL;
  LODWORD(ThreadInformation) = 0;
  v3 = NtFilterLoad(Src);
  v4 = v3;
  if ( v3 < 0 && (v3 == -2147023582 || v3 == (unsigned int)FilterHResultFromNtStatus(3221225569LL)) )
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle);
    if ( v5
      && (v5 != -1073741700
       || (v5 = RtlImpersonateSelf(SecurityImpersonation), v5 < 0)
       || (v1 = 1, (v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle)) != 0)) )
    {
      v4 = FilterHResultFromNtStatus((unsigned int)v5);
    }
    else
    {
      v6 = WcpSetPrivilege(TokenHandle, 10, 1, &ThreadInformation);
      if ( v6 )
        v7 = FilterHResultFromNtStatus(v6);
      else
        v7 = NtFilterLoad(Src);
      v4 = v7;
      if ( !v1 && (_DWORD)ThreadInformation && (unsigned int)WcpSetPrivilege(TokenHandle, 10, 0, 0) )
        goto LABEL_19;
    }
  }
  if ( TokenHandle != (void *)-1LL )
    NtClose(TokenHandle);
  if ( v1 )
  {
    ThreadInformation = 0;
    if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) )
LABEL_19:
      __fastfail(7u);
  }
  return v4;
}

```

## disassembly

```asm
0x1800ad88c  mov     [rsp+arg_0], rbx
0x1800ad891  push    rsi
0x1800ad892  push    rdi
0x1800ad893  push    r15
0x1800ad895  sub     rsp, 20h
0x1800ad899  xor     edi, edi
0x1800ad89b  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800ad8a4  mov     dword ptr [rsp+38h+ThreadInformation], edi
0x1800ad8a8  mov     rsi, rcx
0x1800ad8ab  call    NtFilterLoad
0x1800ad8b0  lea     r15, [rdi-2]
0x1800ad8b4  mov     ebx, eax
0x1800ad8b6  test    eax, eax
0x1800ad8b8  jns     loc_1800AD994
0x1800ad8be  cmp     eax, 80070522h
0x1800ad8c3  jz      short loc_1800AD8D7
0x1800ad8c5  mov     ecx, 0C0000061h
0x1800ad8ca  call    FilterHResultFromNtStatus
0x1800ad8cf  cmp     ebx, eax
0x1800ad8d1  jnz     loc_1800AD994
0x1800ad8d7  xor     r8d, r8d; OpenAsSelf
0x1800ad8da  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800ad8df  mov     rcx, r15; ThreadHandle
0x1800ad8e2  lea     ebx, [r8+28h]
0x1800ad8e6  mov     edx, ebx; DesiredAccess
0x1800ad8e8  call    cs:__imp_NtOpenThreadToken
0x1800ad8ef  nop     dword ptr [rax+rax+00h]
0x1800ad8f4  test    eax, eax
0x1800ad8f6  jz      short loc_1800AD944
0x1800ad8f8  cmp     eax, 0C000007Ch
0x1800ad8fd  jz      short loc_1800AD90D
0x1800ad8ff  mov     ecx, eax
0x1800ad901  call    FilterHResultFromNtStatus
0x1800ad906  mov     ebx, eax
0x1800ad908  jmp     loc_1800AD994
0x1800ad90d  mov     ecx, 2; ImpersonationLevel
0x1800ad912  call    cs:__imp_RtlImpersonateSelf
0x1800ad919  nop     dword ptr [rax+rax+00h]
0x1800ad91e  test    eax, eax
0x1800ad920  js      short loc_1800AD8FF
0x1800ad922  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800ad927  xor     r8d, r8d; OpenAsSelf
0x1800ad92a  mov     edx, ebx; DesiredAccess
0x1800ad92c  mov     rcx, r15; ThreadHandle
0x1800ad92f  mov     edi, 1
0x1800ad934  call    cs:__imp_NtOpenThreadToken
0x1800ad93b  nop     dword ptr [rax+rax+00h]
0x1800ad940  test    eax, eax
0x1800ad942  jnz     short loc_1800AD8FF
0x1800ad944  mov     rcx, [rsp+38h+TokenHandle]
0x1800ad949  lea     r9, [rsp+38h+ThreadInformation]
0x1800ad94e  mov     edx, 0Ah
0x1800ad953  lea     r8d, [rdx-9]
0x1800ad957  call    WcpSetPrivilege
0x1800ad95c  test    eax, eax
0x1800ad95e  jz      short loc_1800AD969
0x1800ad960  mov     ecx, eax
0x1800ad962  call    FilterHResultFromNtStatus
0x1800ad967  jmp     short loc_1800AD971
0x1800ad969  mov     rcx, rsi; Src
0x1800ad96c  call    NtFilterLoad
0x1800ad971  mov     ebx, eax
0x1800ad973  test    edi, edi
0x1800ad975  jnz     short loc_1800AD994
0x1800ad977  cmp     dword ptr [rsp+38h+ThreadInformation], edi
0x1800ad97b  jz      short loc_1800AD994
0x1800ad97d  mov     rcx, [rsp+38h+TokenHandle]
0x1800ad982  lea     edx, [rdi+0Ah]
0x1800ad985  xor     r9d, r9d
0x1800ad988  xor     r8d, r8d
0x1800ad98b  call    WcpSetPrivilege
0x1800ad990  test    eax, eax
0x1800ad992  jnz     short loc_1800AD9DA
0x1800ad994  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x1800ad999  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ad99d  jz      short loc_1800AD9AB
0x1800ad99f  call    cs:__imp_NtClose
0x1800ad9a6  nop     dword ptr [rax+rax+00h]
0x1800ad9ab  test    edi, edi
0x1800ad9ad  jz      short loc_1800AD9E1
0x1800ad9af  mov     r9d, 8; ThreadInformationLength
0x1800ad9b5  mov     [rsp+38h+ThreadInformation], 0
0x1800ad9be  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800ad9c3  mov     rcx, r15; ThreadHandle
0x1800ad9c6  lea     edx, [r9-3]; ThreadInformationClass
0x1800ad9ca  call    cs:__imp_NtSetInformationThread
0x1800ad9d1  nop     dword ptr [rax+rax+00h]
0x1800ad9d6  test    eax, eax
0x1800ad9d8  jz      short loc_1800AD9E1
0x1800ad9da  mov     ecx, 7
0x1800ad9df  int     29h; Win8: RtlFailFast(ecx)
0x1800ad9e1  mov     eax, ebx
0x1800ad9e3  mov     rbx, [rsp+38h+arg_0]
0x1800ad9e8  add     rsp, 20h
0x1800ad9ec  pop     r15
0x1800ad9ee  pop     rdi
0x1800ad9ef  pop     rsi
0x1800ad9f0  retn
```
