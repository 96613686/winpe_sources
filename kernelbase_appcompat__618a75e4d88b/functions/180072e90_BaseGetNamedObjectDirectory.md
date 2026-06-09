# BaseGetNamedObjectDirectory

- ea: `0x180072e90`
- end: `0x180073055`
- name: `BaseGetNamedObjectDirectory`
- size: `453`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004b490`
- `0x18004bc10`
- `0x18004be40`
- `0x180070a70`
- `0x180071920`
- `0x180071c10`
- `0x180072550`
- `0x1800726c0`
- `0x180072878`
- `0x180072be0`
- `0x180072d80`
- `0x1800b3ca0`
- `0x1800c1d60`
- `0x180110530`

## callees

- `0x180072e90`
- `0x1800731a0`

## import_xrefs

- `ntdll!NtClose` at `0x180072f88`
- `ntdll!NtClose` at `0x180072f9e`
- `ntdll!NtClose` at `0x180073044`
- `ntdll!NtClose` at `0x180072f88`
- `ntdll!NtClose` at `0x180072f9e`
- `ntdll!NtClose` at `0x180073044`
- `ntdll!NtOpenProcessToken` at `0x180072f10`
- `ntdll!NtOpenProcessToken` at `0x180072f10`
- `ntdll!NtOpenThreadToken` at `0x180072fca`
- `ntdll!NtOpenThreadToken` at `0x180072fca`
- `ntdll!NtSetInformationThread` at `0x180072ff8`
- `ntdll!NtSetInformationThread` at `0x180073033`
- `ntdll!NtSetInformationThread` at `0x180072ff8`
- `ntdll!NtSetInformationThread` at `0x180073033`

## pseudocode

```c
__int64 __fastcall BaseGetNamedObjectDirectory(_QWORD *a1)
{
  int v3; // esi
  int NamedObjectDirectoryForToken; // edi
  HANDLE v5; // rcx
  HANDLE v6; // [rsp+60h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  __int64 ThreadInformation; // [rsp+78h] [rbp+20h] BYREF

  ThreadInformation = 0;
  if ( !a1 )
    return 3221225485LL;
  if ( BaseNamedObjectDirectory )
  {
    *a1 = BaseNamedObjectDirectory;
    return 0;
  }
  *a1 = 0;
  Handle = 0;
  TokenHandle = 0;
  v6 = 0;
  v3 = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
    goto LABEL_6;
  NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v6);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    ThreadInformation = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     &ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      v3 = 1;
LABEL_6:
      NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
      if ( NamedObjectDirectoryForToken >= 0 )
      {
        NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
        if ( NamedObjectDirectoryForToken >= 0 )
        {
          if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
            Handle = 0;
          *a1 = BaseNamedObjectDirectory;
        }
      }
    }
  }
  v5 = v6;
  if ( v6 )
  {
    if ( v3 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v6, 8u);
      v5 = v6;
    }
    NtClose(v5);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)NamedObjectDirectoryForToken;
}

```

## disassembly

```asm
0x180072e90  push    rbx
0x180072e92  push    rbp
0x180072e93  sub     rsp, 48h
0x180072e97  xor     ebp, ebp
0x180072e99  mov     rbx, rcx
0x180072e9c  mov     [rsp+58h+ThreadInformation], rbp
0x180072ea1  test    rcx, rcx
0x180072ea4  jz      short loc_180072EBF
0x180072ea6  mov     rax, cs:BaseNamedObjectDirectory
0x180072ead  test    rax, rax
0x180072eb0  jz      short loc_180072ECC
0x180072eb2  mov     [rcx], rax
0x180072eb5  xor     eax, eax
0x180072eb7  add     rsp, 48h
0x180072ebb  pop     rbp
0x180072ebc  pop     rbx
0x180072ebd  retn
0x180072ebf  mov     eax, 0C000000Dh
0x180072ec4  add     rsp, 48h
0x180072ec8  pop     rbp
0x180072ec9  pop     rbx
0x180072eca  retn
0x180072ecc  mov     [rcx], rbp
0x180072ecf  mov     [rsp+58h+Handle], rbp
0x180072ed4  mov     [rsp+58h+TokenHandle], rbp
0x180072ed9  mov     [rsp+58h+arg_0], rbp
0x180072ede  mov     rax, gs:30h
0x180072ee7  mov     [rsp+58h+var_18], rsi
0x180072eec  mov     esi, ebp
0x180072eee  mov     [rsp+58h+var_20], rdi
0x180072ef3  cmp     [rax+179Ch], ebp
0x180072ef9  jnz     loc_180072FB6
0x180072eff  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180072f04  mov     edx, 8; DesiredAccess
0x180072f09  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180072f10  call    cs:__imp_NtOpenProcessToken
0x180072f17  nop     dword ptr [rax+rax+00h]
0x180072f1c  mov     edi, eax
0x180072f1e  test    eax, eax
0x180072f20  js      short loc_180072F6B
0x180072f22  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180072f27  lea     rax, [rsp+58h+Handle]
0x180072f2c  xor     edx, edx
0x180072f2e  mov     [rsp+58h+var_38], rax; __int64
0x180072f33  mov     r9d, 0Fh
0x180072f39  mov     r8d, 1
0x180072f3f  call    BasepGetNamedObjectDirectoryForToken
0x180072f44  mov     edi, eax
0x180072f46  test    eax, eax
0x180072f48  js      short loc_180072F6B
0x180072f4a  mov     rcx, [rsp+58h+Handle]
0x180072f4f  xor     eax, eax
0x180072f51  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x180072f5a  jnz     short loc_180072F61
0x180072f5c  mov     [rsp+58h+Handle], rbp
0x180072f61  mov     rax, cs:BaseNamedObjectDirectory
0x180072f68  mov     [rbx], rax
0x180072f6b  mov     rcx, [rsp+58h+arg_0]
0x180072f70  test    rcx, rcx
0x180072f73  jnz     loc_180073018
0x180072f79  mov     rcx, [rsp+58h+TokenHandle]; Handle
0x180072f7e  mov     rsi, [rsp+58h+var_18]
0x180072f83  test    rcx, rcx
0x180072f86  jz      short loc_180072F94
0x180072f88  call    cs:__imp_NtClose
0x180072f8f  nop     dword ptr [rax+rax+00h]
0x180072f94  mov     rcx, [rsp+58h+Handle]; Handle
0x180072f99  test    rcx, rcx
0x180072f9c  jz      short loc_180072FAA
0x180072f9e  call    cs:__imp_NtClose
0x180072fa5  nop     dword ptr [rax+rax+00h]
0x180072faa  mov     eax, edi
0x180072fac  mov     rdi, [rsp+58h+var_20]
0x180072fb1  jmp     loc_180072EB7
0x180072fb6  lea     r9, [rsp+58h+arg_0]; TokenHandle
0x180072fbb  mov     r8b, 1; OpenAsSelf
0x180072fbe  mov     edx, 4; DesiredAccess
0x180072fc3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180072fca  call    cs:__imp_NtOpenThreadToken
0x180072fd1  nop     dword ptr [rax+rax+00h]
0x180072fd6  mov     edi, eax
0x180072fd8  test    eax, eax
0x180072fda  js      short loc_180072F6B
0x180072fdc  mov     r9d, 8; ThreadInformationLength
0x180072fe2  mov     [rsp+58h+ThreadInformation], rbp
0x180072fe7  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x180072fec  mov     edx, 5; ThreadInformationClass
0x180072ff1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180072ff8  call    cs:__imp_NtSetInformationThread
0x180072fff  nop     dword ptr [rax+rax+00h]
0x180073004  mov     edi, eax
0x180073006  test    eax, eax
0x180073008  js      loc_180072F6B
0x18007300e  mov     esi, 1
0x180073013  jmp     loc_180072EFF
0x180073018  test    esi, esi
0x18007301a  jz      short loc_180073044
0x18007301c  mov     r9d, 8; ThreadInformationLength
0x180073022  lea     r8, [rsp+58h+arg_0]; ThreadInformation
0x180073027  mov     edx, 5; ThreadInformationClass
0x18007302c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180073033  call    cs:__imp_NtSetInformationThread
0x18007303a  nop     dword ptr [rax+rax+00h]
0x18007303f  mov     rcx, [rsp+58h+arg_0]; Handle
0x180073044  call    cs:__imp_NtClose
0x18007304b  nop     dword ptr [rax+rax+00h]
0x180073050  jmp     loc_180072F79
```
