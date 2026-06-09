# RxImpersonateLinkedToken

- ea: `0x1400221f4`
- end: `0x14002251c`
- name: `RxImpersonateLinkedToken`
- size: `808`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001ed50`
- `0x14001efc0`

## callees

- `0x1400221f4`
- `0x140025c20`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400224c0`
- `ntoskrnl!ZwClose` at `0x1400224d5`
- `ntoskrnl!ZwClose` at `0x1400224ea`
- `ntoskrnl!ZwClose` at `0x1400224c0`
- `ntoskrnl!ZwClose` at `0x1400224d5`
- `ntoskrnl!ZwClose` at `0x1400224ea`
- `ntoskrnl!RtlCopyLuid` at `0x14002231e`
- `ntoskrnl!RtlCopyLuid` at `0x140022368`
- `ntoskrnl!RtlCopyLuid` at `0x1400223ba`
- `ntoskrnl!RtlCopyLuid` at `0x140022470`
- `ntoskrnl!RtlCopyLuid` at `0x14002231e`
- `ntoskrnl!RtlCopyLuid` at `0x140022368`
- `ntoskrnl!RtlCopyLuid` at `0x1400223ba`
- `ntoskrnl!RtlCopyLuid` at `0x140022470`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14002229b`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14002229b`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400222cd`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400222cd`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022301`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022345`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022396`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022457`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022301`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022345`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022396`
- `ntoskrnl!ZwQueryInformationToken` at `0x140022457`
- `ntoskrnl!ZwDuplicateToken` at `0x14002242a`
- `ntoskrnl!ZwDuplicateToken` at `0x14002242a`
- `ntoskrnl!ZwSetInformationThread` at `0x140022491`
- `ntoskrnl!ZwSetInformationThread` at `0x140022491`

## pseudocode

```c
__int64 __fastcall RxImpersonateLinkedToken(void **a1, struct _LUID *a2, struct _LUID *a3)
{
  char *v4; // rcx
  char v7; // di
  NTSTATUS v8; // eax
  NTSTATUS v9; // ebx
  NTSTATUS v10; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-79h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-71h] BYREF
  int v14; // [rsp+40h] [rbp-69h] BYREF
  HANDLE ThreadInformation; // [rsp+48h] [rbp-61h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+50h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-51h] BYREF
  __int64 v18; // [rsp+88h] [rbp-21h] BYREF
  int v19; // [rsp+90h] [rbp-19h]
  _OWORD TokenInformation[3]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+1Fh]

  Handle = 0;
  v21 = 0;
  ReturnLength = 0;
  v4 = (char *)*a1;
  v18 = 0;
  v19 = 0;
  ExistingTokenHandle = 0;
  ThreadInformation = 0;
  v14 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, 0x200u, &Handle);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( v8 != -1073741700 )
        goto LABEL_20;
      v7 = 0;
      v9 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &Handle);
      if ( v9 < 0 )
        goto LABEL_20;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
    Handle = v4;
  }
  v9 = ZwQueryInformationToken(Handle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  if ( v9 >= 0 )
  {
    RtlCopyLuid(a2, (PLUID)TokenInformation + 1);
    v9 = ZwQueryInformationToken(Handle, TokenElevationType, &v14, 4u, &ReturnLength);
    if ( v9 >= 0 )
    {
      if ( v14 == 1 )
      {
        RtlCopyLuid(a3, (PLUID)TokenInformation + 1);
        v9 = 0;
        goto LABEL_20;
      }
      v10 = ZwQueryInformationToken(Handle, TokenLinkedToken, &ExistingTokenHandle, 8u, &ReturnLength);
      v9 = v10;
      if ( v10 >= 0 )
      {
        LOWORD(v19) = 1;
        v18 = 0x20000000CLL;
        ObjectAttributes.SecurityQualityOfService = &v18;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 512;
        ObjectAttributes.ObjectName = 0;
        ObjectAttributes.SecurityDescriptor = 0;
        v9 = ZwDuplicateToken(ExistingTokenHandle, 0xCu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation);
        if ( v9 < 0 )
          goto LABEL_20;
        v9 = ZwQueryInformationToken(ThreadInformation, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
        if ( v9 < 0 )
          goto LABEL_20;
        RtlCopyLuid(a3, (PLUID)TokenInformation + 1);
        v9 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      }
      else
      {
        if ( v10 != -1073741729 )
          goto LABEL_20;
        RtlCopyLuid(a3, (PLUID)TokenInformation + 1);
        v7 = 0;
        v9 = 0;
      }
      if ( v9 >= 0 && v7 )
      {
        *a1 = Handle;
        Handle = 0;
      }
    }
  }
LABEL_20:
  if ( Handle )
    ZwClose(Handle);
  if ( ThreadInformation )
    ZwClose(ThreadInformation);
  if ( ExistingTokenHandle )
    ZwClose(ExistingTokenHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400221f4  mov     [rsp-8+arg_18], rbx
0x1400221f9  push    rbp
0x1400221fa  push    rsi
0x1400221fb  push    rdi
0x1400221fc  push    r14
0x1400221fe  push    r15
0x140022200  lea     rbp, [rsp-37h]
0x140022205  sub     rsp, 0E0h
0x14002220c  mov     rax, cs:__security_cookie
0x140022213  xor     rax, rsp
0x140022216  mov     [rbp+57h+var_30], rax
0x14002221a  xor     eax, eax
0x14002221c  mov     [rbp+57h+Handle], 0
0x140022224  xorps   xmm0, xmm0
0x140022227  mov     [rbp+57h+var_38], rax
0x14002222b  mov     r14, rcx
0x14002222e  mov     [rbp+57h+ReturnLength], eax
0x140022231  mov     rcx, [rcx]
0x140022234  mov     rsi, r8
0x140022237  mov     [rbp+57h+var_78], rax
0x14002223b  mov     r15, rdx
0x14002223e  mov     [rbp+57h+var_70], eax
0x140022241  mov     edi, 200h
0x140022246  mov     [rbp+57h+ExistingTokenHandle], rax
0x14002224a  lea     rax, [rcx-1]
0x14002224e  mov     [rbp+57h+ThreadInformation], 0
0x140022256  mov     [rbp+57h+var_C0], 0
0x14002225d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140022261  movups  [rbp+57h+TokenInformation], xmm0
0x140022265  movups  [rbp+57h+var_58], xmm0
0x140022269  movups  [rbp+57h+var_48], xmm0
0x14002226d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140022271  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140022275  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140022279  ja      short loc_140022284
0x14002227b  xor     dil, dil
0x14002227e  mov     [rbp+57h+Handle], rcx
0x140022282  jmp     short loc_1400222E6
0x140022284  xor     r8d, r8d; OpenAsSelf
0x140022287  lea     rax, [rbp+57h+Handle]
0x14002228b  mov     r9d, edi; HandleAttributes
0x14002228e  mov     [rsp+100h+TokenHandle], rax; TokenHandle
0x140022293  lea     edx, [r8+8]; DesiredAccess
0x140022297  lea     rcx, [r8-2]; ThreadHandle
0x14002229b  call    cs:__imp_ZwOpenThreadTokenEx
0x1400222a2  nop     dword ptr [rax+rax+00h]
0x1400222a7  mov     ebx, eax
0x1400222a9  test    eax, eax
0x1400222ab  js      short loc_1400222B2
0x1400222ad  mov     dil, 1
0x1400222b0  jmp     short loc_1400222E6
0x1400222b2  cmp     eax, 0C000007Ch
0x1400222b7  jnz     loc_1400224B7
0x1400222bd  lea     r9, [rbp+57h+Handle]; TokenHandle
0x1400222c1  mov     r8d, edi; HandleAttributes
0x1400222c4  mov     edx, 8; DesiredAccess
0x1400222c9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400222cd  call    cs:__imp_ZwOpenProcessTokenEx
0x1400222d4  nop     dword ptr [rax+rax+00h]
0x1400222d9  xor     dil, dil
0x1400222dc  mov     ebx, eax
0x1400222de  test    eax, eax
0x1400222e0  js      loc_1400224B7
0x1400222e6  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x1400222ea  lea     rax, [rbp+57h+ReturnLength]
0x1400222ee  mov     r9d, 38h ; '8'; TokenInformationLength
0x1400222f4  mov     [rsp+100h+TokenHandle], rax; ReturnLength
0x1400222f9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1400222fd  lea     edx, [r9-2Eh]; TokenInformationClass
0x140022301  call    cs:__imp_ZwQueryInformationToken
0x140022308  nop     dword ptr [rax+rax+00h]
0x14002230d  mov     ebx, eax
0x14002230f  test    eax, eax
0x140022311  js      loc_1400224B7
0x140022317  lea     rdx, [rbp+57h+TokenInformation+8]; SourceLuid
0x14002231b  mov     rcx, r15; DestinationLuid
0x14002231e  call    cs:__imp_RtlCopyLuid
0x140022325  nop     dword ptr [rax+rax+00h]
0x14002232a  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x14002232e  lea     rax, [rbp+57h+ReturnLength]
0x140022332  mov     r9d, 4; TokenInformationLength
0x140022338  mov     [rsp+100h+TokenHandle], rax; ReturnLength
0x14002233d  lea     r8, [rbp+57h+var_C0]; TokenInformation
0x140022341  lea     edx, [r9+0Eh]; TokenInformationClass
0x140022345  call    cs:__imp_ZwQueryInformationToken
0x14002234c  nop     dword ptr [rax+rax+00h]
0x140022351  mov     ebx, eax
0x140022353  test    eax, eax
0x140022355  js      loc_1400224B7
0x14002235b  cmp     [rbp+57h+var_C0], 1
0x14002235f  jnz     short loc_14002237B
0x140022361  lea     rdx, [rbp+57h+TokenInformation+8]; SourceLuid
0x140022365  mov     rcx, rsi; DestinationLuid
0x140022368  call    cs:__imp_RtlCopyLuid
0x14002236f  nop     dword ptr [rax+rax+00h]
0x140022374  xor     ebx, ebx
0x140022376  jmp     loc_1400224B7
0x14002237b  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x14002237f  lea     rax, [rbp+57h+ReturnLength]
0x140022383  mov     r9d, 8; TokenInformationLength
0x140022389  mov     [rsp+100h+TokenHandle], rax; ReturnLength
0x14002238e  lea     r8, [rbp+57h+ExistingTokenHandle]; TokenInformation
0x140022392  lea     edx, [r9+0Bh]; TokenInformationClass
0x140022396  call    cs:__imp_ZwQueryInformationToken
0x14002239d  nop     dword ptr [rax+rax+00h]
0x1400223a2  mov     ebx, eax
0x1400223a4  test    eax, eax
0x1400223a6  jns     short loc_1400223D0
0x1400223a8  cmp     eax, 0C000005Fh
0x1400223ad  jnz     loc_1400224B7
0x1400223b3  lea     rdx, [rbp+57h+TokenInformation+8]; SourceLuid
0x1400223b7  mov     rcx, rsi; DestinationLuid
0x1400223ba  call    cs:__imp_RtlCopyLuid
0x1400223c1  nop     dword ptr [rax+rax+00h]
0x1400223c6  xor     dil, dil
0x1400223c9  xor     ebx, ebx
0x1400223cb  jmp     loc_14002249F
0x1400223d0  mov     edx, 0Ch; DesiredAccess
0x1400223d5  mov     word ptr [rbp+57h+var_70], 1
0x1400223db  lea     rax, [rbp+57h+var_78]
0x1400223df  mov     dword ptr [rbp+57h+var_78], edx
0x1400223e2  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x1400223e6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400223ea  lea     rax, [rbp+57h+ThreadInformation]
0x1400223ee  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400223f5  lea     ecx, [rdx-0Ah]
0x1400223f8  mov     [rsp+100h+NewTokenHandle], rax; NewTokenHandle
0x1400223fd  mov     dword ptr [rbp+57h+var_78+4], ecx
0x140022400  xor     r9d, r9d; EffectiveOnly
0x140022403  mov     dword ptr [rsp+100h+TokenHandle], ecx; TokenType
0x140022407  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14002240b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140022413  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14002241a  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140022422  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x14002242a  call    cs:__imp_ZwDuplicateToken
0x140022431  nop     dword ptr [rax+rax+00h]
0x140022436  mov     ebx, eax
0x140022438  test    eax, eax
0x14002243a  js      short loc_1400224B7
0x14002243c  mov     rcx, [rbp+57h+ThreadInformation]; TokenHandle
0x140022440  lea     rax, [rbp+57h+ReturnLength]
0x140022444  mov     r9d, 38h ; '8'; TokenInformationLength
0x14002244a  mov     [rsp+100h+TokenHandle], rax; ReturnLength
0x14002244f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140022453  lea     edx, [r9-2Eh]; TokenInformationClass
0x140022457  call    cs:__imp_ZwQueryInformationToken
0x14002245e  nop     dword ptr [rax+rax+00h]
0x140022463  mov     ebx, eax
0x140022465  test    eax, eax
0x140022467  js      short loc_1400224B7
0x140022469  lea     rdx, [rbp+57h+TokenInformation+8]; SourceLuid
0x14002246d  mov     rcx, rsi; DestinationLuid
0x140022470  call    cs:__imp_RtlCopyLuid
0x140022477  nop     dword ptr [rax+rax+00h]
0x14002247c  mov     r9d, 8; ThreadInformationLength
0x140022482  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x140022486  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002248d  lea     edx, [r9-3]; ThreadInformationClass
0x140022491  call    cs:__imp_ZwSetInformationThread
0x140022498  nop     dword ptr [rax+rax+00h]
0x14002249d  mov     ebx, eax
0x14002249f  test    ebx, ebx
0x1400224a1  js      short loc_1400224B7
0x1400224a3  test    dil, dil
0x1400224a6  jz      short loc_1400224B7
0x1400224a8  mov     rax, [rbp+57h+Handle]
0x1400224ac  mov     [r14], rax
0x1400224af  mov     [rbp+57h+Handle], 0
0x1400224b7  mov     rcx, [rbp+57h+Handle]; Handle
0x1400224bb  test    rcx, rcx
0x1400224be  jz      short loc_1400224CC
0x1400224c0  call    cs:__imp_ZwClose
0x1400224c7  nop     dword ptr [rax+rax+00h]
0x1400224cc  mov     rcx, [rbp+57h+ThreadInformation]; Handle
0x1400224d0  test    rcx, rcx
0x1400224d3  jz      short loc_1400224E1
0x1400224d5  call    cs:__imp_ZwClose
0x1400224dc  nop     dword ptr [rax+rax+00h]
0x1400224e1  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x1400224e5  test    rcx, rcx
0x1400224e8  jz      short loc_1400224F6
0x1400224ea  call    cs:__imp_ZwClose
0x1400224f1  nop     dword ptr [rax+rax+00h]
0x1400224f6  mov     eax, ebx
0x1400224f8  mov     rcx, [rbp+57h+var_30]
0x1400224fc  xor     rcx, rsp; StackCookie
0x1400224ff  call    __security_check_cookie
0x140022504  mov     rbx, [rsp+100h+arg_18]
0x14002250c  add     rsp, 0E0h
0x140022513  pop     r15
0x140022515  pop     r14
0x140022517  pop     rdi
0x140022518  pop     rsi
0x140022519  pop     rbp
0x14002251a  retn
```
