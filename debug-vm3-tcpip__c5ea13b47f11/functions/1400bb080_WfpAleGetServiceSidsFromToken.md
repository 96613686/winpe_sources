# WfpAleGetServiceSidsFromToken

- ea: `0x1400bb080`
- end: `0x1400bb4a8`
- name: `WfpAleGetServiceSidsFromToken`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400bac20`

## callees

- `0x1400541c0`
- `0x14008b220`
- `0x1400ba9d4`
- `0x1400bb080`
- `0x1400ddb90`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb33d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400bb33d`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb2c8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb31f`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb2c8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400bb31f`
- `ntoskrnl!RtlValidSid` at `0x1400bb148`
- `ntoskrnl!RtlValidSid` at `0x1400bb20c`
- `ntoskrnl!RtlValidSid` at `0x1400bb148`
- `ntoskrnl!RtlValidSid` at `0x1400bb20c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb0c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb0c1`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb15b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb21f`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb15b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400bb21f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb171`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb235`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb171`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400bb235`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb2a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb2a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb0e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb1b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb0e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb1b4`

## string_xrefs

- `0x1400bb251`: `RtlConvertSidToUnicodeString`

## pseudocode

```c
__int64 __fastcall WfpAleGetServiceSidsFromToken(__int64 a1)
{
  struct _UNICODE_STRING *v2; // r13
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rcx
  int v6; // r12d
  int v7; // r15d
  unsigned __int16 v8; // r14
  __int64 v9; // rcx
  unsigned int i; // ebx
  void *v11; // rdi
  __int64 v12; // rcx
  unsigned int j; // ebx
  void *v14; // rdi
  __int64 v15; // r8
  const char *v16; // rdx
  unsigned int v18; // eax
  int Length; // eax
  unsigned int appended; // eax
  unsigned int v21; // eax
  __int64 v22; // rax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-38h] BYREF

  v2 = (struct _UNICODE_STRING *)(a1 + 208);
  Destination = 0;
  UnicodeString = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 208), 0);
  v3 = *(_QWORD *)(a1 + 224);
  v4 = 0;
  UnicodeString.Buffer = (PWSTR)ExAllocatePool2(64, 130, 1400073281);
  if ( !UnicodeString.Buffer )
  {
    v22 = WfpReportSysErrorAsNtStatus(v5, "ExAllocatePool2", 3221225495LL);
    v4 = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpPoolAllocNonPaged",
          v22);
        goto LABEL_21;
      }
    }
  }
  if ( v4 )
    goto LABEL_21;
  v6 = 1;
  v7 = 1;
  v8 = 0;
  memset(UnicodeString.Buffer, 0, 0x82u);
  UnicodeString.MaximumLength = 130;
  for ( i = 0; i < *(_DWORD *)v3; ++i )
  {
    v11 = *(void **)(*(_QWORD *)(v3 + 8) + 16LL * i);
    if ( RtlValidSid(v11) && *RtlSubAuthorityCountSid(v11) && *RtlSubAuthoritySid(v11, 0) == 80 )
    {
      v18 = RtlConvertSidToUnicodeString(&UnicodeString, v11, 0);
      if ( v18 )
      {
LABEL_19:
        v15 = v18;
        v16 = "RtlConvertSidToUnicodeString";
        goto LABEL_20;
      }
      Length = UnicodeString.Length;
      LOWORD(Length) = v8 + UnicodeString.Length;
      if ( (unsigned __int16)(v8 + UnicodeString.Length) < v8 )
        goto LABEL_35;
      if ( v7 )
      {
        v8 += UnicodeString.Length;
        UnicodeString.Length = 0;
        v7 = 0;
      }
      else
      {
        v9 = (unsigned int)(Length + 2);
        if ( (unsigned __int16)(Length + 2) < (unsigned __int16)Length )
          goto LABEL_35;
        v8 = Length + 2;
        UnicodeString.Length = 0;
        v7 = 0;
      }
    }
  }
  if ( !v8 )
    goto LABEL_21;
  if ( (unsigned __int16)(v8 + 2) < v8 )
  {
LABEL_35:
    v15 = 3221225621LL;
    v16 = "RtlUShortAdd";
    goto LABEL_20;
  }
  v4 = 0;
  Destination.Buffer = (PWSTR)ExAllocatePool2(64, (unsigned __int16)(v8 + 2), 1400073281);
  if ( !Destination.Buffer )
  {
    v4 = WfpReportSysErrorAsNtStatus(v12, "ExAllocatePool2", 3221225495LL);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpPoolAllocNonPaged",
          v4);
        goto LABEL_21;
      }
    }
  }
  if ( v4 )
    goto LABEL_21;
  memset(Destination.Buffer, 0, (unsigned __int16)(v8 + 2));
  Destination.MaximumLength = v8 + 2;
  Destination.Length = 0;
  for ( j = 0; ; ++j )
  {
    if ( j >= *(_DWORD *)v3 )
    {
      *v2 = Destination;
      goto LABEL_34;
    }
    v14 = *(void **)(*(_QWORD *)(v3 + 8) + 16LL * j);
    if ( !RtlValidSid(v14) || !*RtlSubAuthorityCountSid(v14) || *RtlSubAuthoritySid(v14, 0) != 80 )
      continue;
    if ( !v6 )
    {
      v21 = RtlUnicodeStringCatString(&Destination, L",");
      if ( v21 )
        break;
    }
    v18 = RtlConvertSidToUnicodeString(&UnicodeString, v14, 0);
    if ( v18 )
      goto LABEL_19;
    appended = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
    v9 = 0;
    UnicodeString.Length = 0;
    if ( appended )
    {
      v15 = appended;
      v16 = "RtlAppendUnicodeStringToString";
      goto LABEL_20;
    }
    v6 = 0;
  }
  v15 = v21;
  v16 = "RtlUnicodeStringCatString";
LABEL_20:
  v4 = WfpReportSysErrorAsNtStatus(v9, v16, v15);
LABEL_21:
  if ( Destination.Buffer )
  {
    WfpNamedPoolFree(0x53736C41u);
LABEL_34:
    Destination.Buffer = 0;
  }
  if ( UnicodeString.Buffer )
    ExFreePoolWithTag(UnicodeString.Buffer, 0x53736C41u);
  return v4;
}

```

## disassembly

```asm
0x1400bb080  mov     rax, rsp
0x1400bb083  push    rbp
0x1400bb084  sub     rsp, 70h
0x1400bb088  mov     [rax+8], rbx
0x1400bb08c  xorps   xmm0, xmm0
0x1400bb08f  mov     [rax+10h], rsi
0x1400bb093  mov     rbx, rcx
0x1400bb096  mov     [rax+18h], rdi
0x1400bb09a  xorps   xmm1, xmm1
0x1400bb09d  mov     [rax-10h], r12
0x1400bb0a1  xor     edx, edx; SourceString
0x1400bb0a3  mov     [rax-18h], r13
0x1400bb0a7  lea     r13, [rcx+0D0h]
0x1400bb0ae  mov     [rax-20h], r14
0x1400bb0b2  mov     rcx, r13; DestinationString
0x1400bb0b5  mov     [rax-28h], r15
0x1400bb0b9  movups  xmmword ptr [rax-48h], xmm0
0x1400bb0bd  movups  xmmword ptr [rax-38h], xmm1
0x1400bb0c1  call    cs:__imp_RtlInitUnicodeString
0x1400bb0c8  nop     dword ptr [rax+rax+00h]
0x1400bb0cd  mov     rsi, [rbx+0E0h]
0x1400bb0d4  mov     r8d, 53736C41h
0x1400bb0da  mov     ebx, 82h
0x1400bb0df  mov     ecx, 40h ; '@'
0x1400bb0e4  mov     edx, ebx
0x1400bb0e6  xor     ebp, ebp
0x1400bb0e8  call    cs:__imp_ExAllocatePool2
0x1400bb0ef  nop     dword ptr [rax+rax+00h]
0x1400bb0f4  mov     [rsp+78h+UnicodeString.Buffer], rax
0x1400bb0f9  lea     rdi, WPP_GLOBAL_Control
0x1400bb100  test    rax, rax
0x1400bb103  jz      loc_1400BB3D8
0x1400bb109  test    rbp, rbp
0x1400bb10c  jnz     loc_1400BB260
0x1400bb112  mov     rcx, [rsp+78h+UnicodeString.Buffer]; void *
0x1400bb117  mov     r12d, 1
0x1400bb11d  mov     r8, rbx; Size
0x1400bb120  xor     edx, edx; Val
0x1400bb122  mov     r15d, r12d
0x1400bb125  xor     r14d, r14d
0x1400bb128  call    memset
0x1400bb12d  mov     [rsp+78h+UnicodeString.MaximumLength], bx
0x1400bb132  xor     ebx, ebx
0x1400bb134  cmp     ebx, [rsi]
0x1400bb136  jnb     short loc_1400BB18A
0x1400bb138  mov     rax, [rsi+8]
0x1400bb13c  mov     ecx, ebx
0x1400bb13e  add     rcx, rcx
0x1400bb141  mov     rdi, [rax+rcx*8]
0x1400bb145  mov     rcx, rdi; Sid
0x1400bb148  call    cs:__imp_RtlValidSid
0x1400bb14f  nop     dword ptr [rax+rax+00h]
0x1400bb154  test    al, al
0x1400bb156  jz      short loc_1400BB186
0x1400bb158  mov     rcx, rdi; Sid
0x1400bb15b  call    cs:__imp_RtlSubAuthorityCountSid
0x1400bb162  nop     dword ptr [rax+rax+00h]
0x1400bb167  cmp     byte ptr [rax], 0
0x1400bb16a  jz      short loc_1400BB186
0x1400bb16c  xor     edx, edx; SubAuthority
0x1400bb16e  mov     rcx, rdi; Sid
0x1400bb171  call    cs:__imp_RtlSubAuthoritySid
0x1400bb178  nop     dword ptr [rax+rax+00h]
0x1400bb17d  cmp     dword ptr [rax], 50h ; 'P'
0x1400bb180  jz      loc_1400BB2BD
0x1400bb186  inc     ebx
0x1400bb188  jmp     short loc_1400BB134
0x1400bb18a  test    r14w, r14w
0x1400bb18e  jz      loc_1400BB260
0x1400bb194  lea     ebx, [r14+2]
0x1400bb198  cmp     bx, r14w
0x1400bb19c  jb      loc_1400BB374
0x1400bb1a2  movzx   edi, bx
0x1400bb1a5  mov     r8d, 53736C41h
0x1400bb1ab  mov     edx, edi
0x1400bb1ad  mov     ecx, 40h ; '@'
0x1400bb1b2  xor     ebp, ebp
0x1400bb1b4  call    cs:__imp_ExAllocatePool2
0x1400bb1bb  nop     dword ptr [rax+rax+00h]
0x1400bb1c0  mov     [rsp+78h+Destination.Buffer], rax
0x1400bb1c5  test    rax, rax
0x1400bb1c8  jz      loc_1400BB442
0x1400bb1ce  test    rbp, rbp
0x1400bb1d1  jnz     loc_1400BB260
0x1400bb1d7  mov     rcx, [rsp+78h+Destination.Buffer]; void *
0x1400bb1dc  mov     r8, rdi; Size
0x1400bb1df  xor     edx, edx; Val
0x1400bb1e1  call    memset
0x1400bb1e6  xor     eax, eax
0x1400bb1e8  mov     [rsp+78h+Destination.MaximumLength], bx
0x1400bb1ed  mov     [rsp+78h+Destination.Length], ax
0x1400bb1f2  xor     ebx, ebx
0x1400bb1f4  cmp     ebx, [rsi]
0x1400bb1f6  jnb     loc_1400BB35C
0x1400bb1fc  mov     rax, [rsi+8]
0x1400bb200  mov     ecx, ebx
0x1400bb202  add     rcx, rcx
0x1400bb205  mov     rdi, [rax+rcx*8]
0x1400bb209  mov     rcx, rdi; Sid
0x1400bb20c  call    cs:__imp_RtlValidSid
0x1400bb213  nop     dword ptr [rax+rax+00h]
0x1400bb218  test    al, al
0x1400bb21a  jz      short loc_1400BB24A
0x1400bb21c  mov     rcx, rdi; Sid
0x1400bb21f  call    cs:__imp_RtlSubAuthorityCountSid
0x1400bb226  nop     dword ptr [rax+rax+00h]
0x1400bb22b  cmp     byte ptr [rax], 0
0x1400bb22e  jz      short loc_1400BB24A
0x1400bb230  xor     edx, edx; SubAuthority
0x1400bb232  mov     rcx, rdi; Sid
0x1400bb235  call    cs:__imp_RtlSubAuthoritySid
0x1400bb23c  nop     dword ptr [rax+rax+00h]
0x1400bb241  cmp     dword ptr [rax], 50h ; 'P'
0x1400bb244  jz      loc_1400BB30B
0x1400bb24a  inc     ebx
0x1400bb24c  jmp     short loc_1400BB1F4
0x1400bb24e  mov     r8d, eax
0x1400bb251  lea     rdx, aRtlconvertsidt; "RtlConvertSidToUnicodeString"
0x1400bb258  call    WfpReportSysErrorAsNtStatus
0x1400bb25d  mov     rbp, rax
0x1400bb260  cmp     [rsp+78h+Destination.Buffer], 0
0x1400bb266  jnz     loc_1400BB494
0x1400bb26c  mov     rcx, [rsp+78h+UnicodeString.Buffer]; P
0x1400bb271  mov     r15, [rsp+78h+var_28]
0x1400bb276  mov     r14, [rsp+78h+var_20]
0x1400bb27b  mov     r13, [rsp+78h+var_18]
0x1400bb280  mov     r12, [rsp+78h+var_10]
0x1400bb285  mov     rdi, [rsp+78h+arg_10]
0x1400bb28d  mov     rsi, [rsp+78h+arg_8]
0x1400bb295  mov     rbx, [rsp+78h+arg_0]
0x1400bb29d  test    rcx, rcx
0x1400bb2a0  jz      short loc_1400BB2B3
0x1400bb2a2  mov     edx, 53736C41h; Tag
0x1400bb2a7  call    cs:__imp_ExFreePoolWithTag
0x1400bb2ae  nop     dword ptr [rax+rax+00h]
0x1400bb2b3  mov     rax, rbp
0x1400bb2b6  add     rsp, 70h
0x1400bb2ba  pop     rbp
0x1400bb2bb  retn
0x1400bb2bd  xor     r8d, r8d; AllocateDestinationString
0x1400bb2c0  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400bb2c5  mov     rdx, rdi; Sid
0x1400bb2c8  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400bb2cf  nop     dword ptr [rax+rax+00h]
0x1400bb2d4  test    eax, eax
0x1400bb2d6  jnz     loc_1400BB24E
0x1400bb2dc  movzx   eax, [rsp+78h+UnicodeString.Length]
0x1400bb2e1  add     ax, r14w
0x1400bb2e5  cmp     ax, r14w
0x1400bb2e9  jb      loc_1400BB374
0x1400bb2ef  test    r15d, r15d
0x1400bb2f2  jz      loc_1400BB395
0x1400bb2f8  movzx   r14d, ax
0x1400bb2fc  xor     eax, eax
0x1400bb2fe  mov     [rsp+78h+UnicodeString.Length], ax
0x1400bb303  xor     r15d, r15d
0x1400bb306  jmp     loc_1400BB186
0x1400bb30b  test    r12d, r12d
0x1400bb30e  jz      loc_1400BB3B0
0x1400bb314  xor     r8d, r8d; AllocateDestinationString
0x1400bb317  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x1400bb31c  mov     rdx, rdi; Sid
0x1400bb31f  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400bb326  nop     dword ptr [rax+rax+00h]
0x1400bb32b  test    eax, eax
0x1400bb32d  jnz     loc_1400BB24E
0x1400bb333  lea     rdx, [rsp+78h+UnicodeString]; Source
0x1400bb338  lea     rcx, [rsp+78h+Destination]; Destination
0x1400bb33d  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400bb344  nop     dword ptr [rax+rax+00h]
0x1400bb349  xor     ecx, ecx
0x1400bb34b  mov     [rsp+78h+UnicodeString.Length], cx
0x1400bb350  test    eax, eax
0x1400bb352  jnz     short loc_1400BB386
0x1400bb354  xor     r12d, r12d
0x1400bb357  jmp     loc_1400BB24A
0x1400bb35c  movups  xmm0, xmmword ptr [rsp+78h+Destination.Length]
0x1400bb361  movups  xmmword ptr [r13+0], xmm0
0x1400bb366  mov     [rsp+78h+Destination.Buffer], 0
0x1400bb36f  jmp     loc_1400BB26C
0x1400bb374  mov     r8d, 0C0000095h
0x1400bb37a  lea     rdx, aRtlushortadd; "RtlUShortAdd"
0x1400bb381  jmp     loc_1400BB258
0x1400bb386  mov     r8d, eax
0x1400bb389  lea     rdx, aRtlappendunico; "RtlAppendUnicodeStringToString"
0x1400bb390  jmp     loc_1400BB258
0x1400bb395  lea     ecx, [rax+2]
0x1400bb398  cmp     cx, ax
0x1400bb39b  jb      short loc_1400BB374
0x1400bb39d  xor     eax, eax
0x1400bb39f  movzx   r14d, cx
0x1400bb3a3  mov     [rsp+78h+UnicodeString.Length], ax
0x1400bb3a8  xor     r15d, r15d
0x1400bb3ab  jmp     loc_1400BB186
0x1400bb3b0  lea     rdx, pszSrc; ","
0x1400bb3b7  lea     rcx, [rsp+78h+Destination]; DestinationString
0x1400bb3bc  call    RtlUnicodeStringCatString
0x1400bb3c1  test    eax, eax
0x1400bb3c3  jz      loc_1400BB314
0x1400bb3c9  mov     r8d, eax
0x1400bb3cc  lea     rdx, aRtlunicodestri; "RtlUnicodeStringCatString"
0x1400bb3d3  jmp     loc_1400BB258
0x1400bb3d8  mov     r8d, 0C0000017h
0x1400bb3de  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x1400bb3e5  call    WfpReportSysErrorAsNtStatus
0x1400bb3ea  mov     rbp, rax
0x1400bb3ed  test    rax, rax
0x1400bb3f0  jz      loc_1400BB109
0x1400bb3f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb3fd  cmp     rcx, rdi
0x1400bb400  jz      loc_1400BB109
0x1400bb406  cmp     byte ptr [rcx+29h], 2
0x1400bb40a  jb      loc_1400BB109
0x1400bb410  test    dword ptr [rcx+2Ch], 1000h
0x1400bb417  jz      loc_1400BB109
0x1400bb41d  mov     [rsp+78h+var_58], eax
0x1400bb421  mov     rcx, [rcx+18h]
0x1400bb425  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x1400bb42c  mov     edx, 0Fh
0x1400bb431  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400bb438  call    WPP_SF_sd
0x1400bb43d  jmp     loc_1400BB260
0x1400bb442  mov     r8d, 0C0000017h
0x1400bb448  lea     rdx, aExallocatepool; "ExAllocatePool2"
0x1400bb44f  call    WfpReportSysErrorAsNtStatus
0x1400bb454  mov     rbp, rax
0x1400bb457  test    rax, rax
0x1400bb45a  jz      loc_1400BB1CE
0x1400bb460  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb467  lea     rax, WPP_GLOBAL_Control
0x1400bb46e  cmp     rcx, rax
0x1400bb471  jz      loc_1400BB1CE
0x1400bb477  cmp     byte ptr [rcx+29h], 2
0x1400bb47b  jb      loc_1400BB1CE
0x1400bb481  test    dword ptr [rcx+2Ch], 1000h
0x1400bb488  jz      loc_1400BB1CE
0x1400bb48e  mov     [rsp+78h+var_58], ebp
0x1400bb492  jmp     short loc_1400BB421
0x1400bb494  lea     rdx, [rsp+78h+Destination.Buffer]
0x1400bb499  mov     ecx, 53736C41h; Tag
0x1400bb49e  call    WfpNamedPoolFree
0x1400bb4a3  jmp     loc_1400BB366
```
