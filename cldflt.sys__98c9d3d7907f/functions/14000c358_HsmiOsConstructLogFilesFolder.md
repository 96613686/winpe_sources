# HsmiOsConstructLogFilesFolder

- ea: `0x14000c358`
- end: `0x14000c6ef`
- name: `HsmiOsConstructLogFilesFolder`
- size: `919`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PUNICODE_STRING)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400131fc`

## callees

- `0x14000c358`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c491`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c4a5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c4c3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c4d7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c61b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c62f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c643`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c669`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c67b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c68f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c491`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c4a5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c4c3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c4d7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c61b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c62f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c643`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c669`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c67b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c68f`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14000c52e`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14000c52e`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14000c3a5`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14000c3a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c46f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c46f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c427`
- `ntoskrnl!ExAllocatePool2` at `0x14000c453`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5b3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5e5`
- `ntoskrnl!ExAllocatePool2` at `0x14000c427`
- `ntoskrnl!ExAllocatePool2` at `0x14000c453`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5b3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5e5`

## string_xrefs

- `0x14000c4e8`: `\System32\LogFiles\CloudFiles\`

## pseudocode

```c
__int64 __fastcall HsmiOsConstructLogFilesFolder(PUNICODE_STRING Destination, PUNICODE_STRING a2)
{
  WCHAR *Pool2; // r12
  unsigned int v5; // ebx
  WCHAR *v6; // r15
  WCHAR *v7; // rcx
  struct _UNICODE_STRING *v8; // rcx
  const WCHAR *NtSystemRoot; // rax
  const WCHAR *v10; // r12
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  WCHAR *v13; // r13
  WCHAR *v14; // r15
  unsigned int v15; // ecx
  unsigned int v16; // eax
  unsigned __int64 v18; // [rsp+20h] [rbp-E0h]
  WCHAR v19[12]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v20[16]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v21[4]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Source[28]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR v23[40]; // [rsp+E0h] [rbp-20h] BYREF

  wcscpy(v19, L"CldFlt0.etl");
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    wcscpy(Source, L"\\DriverData\\CloudFiles\\");
    wcscpy(v23, L"\\\\?\\GLOBALROOT\\DriverData\\CldFiles\\");
    Pool2 = (WCHAR *)ExAllocatePool2(256, 72, 1934979912);
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    v6 = (WCHAR *)ExAllocatePool2(256, 100, 1934979912);
    if ( !v6 )
    {
      v7 = Pool2;
LABEL_6:
      ExFreePoolWithTag(v7, 0x73557348u);
      return (unsigned int)-1073741670;
    }
    a2->Buffer = Pool2;
    *(_DWORD *)&a2->Length = 4718592;
    v5 = 0;
    RtlAppendUnicodeToString(a2, Source);
    RtlAppendUnicodeToString(a2, v19);
    Destination->Buffer = v6;
    *(_DWORD *)&Destination->Length = 6553600;
    RtlAppendUnicodeToString(Destination, v23);
    v8 = Destination;
    goto LABEL_8;
  }
  wcscpy((wchar_t *)v21, L"\\System32\\LogFiles\\ClodFiles\\");
  wcscpy(v20, L"\\Devices\\");
  NtSystemRoot = (const WCHAR *)RtlGetNtSystemRoot();
  v10 = NtSystemRoot;
  if ( NtSystemRoot )
  {
    v11 = 0x7FFF;
    do
    {
      if ( !*NtSystemRoot )
        break;
      ++NtSystemRoot;
      --v11;
    }
    while ( v11 );
    v5 = v11 == 0 ? 0xC000000D : 0;
    if ( v11 )
    {
      v12 = (2 * (0x7FFF - v11)) & -(__int64)(v11 != 0);
      if ( v12 >= 0xFFA9 )
        return (unsigned int)-1073741675;
      v18 = v12 + 86;
      v13 = (WCHAR *)ExAllocatePool2(256, v12 + 86, 1934979912);
      if ( !v13 )
        return (unsigned int)-1073741670;
      v14 = (WCHAR *)ExAllocatePool2(256, v18 + 26, 1934979912);
      if ( !v14 )
      {
        v7 = v13;
        goto LABEL_6;
      }
      Destination->Buffer = v13;
      Destination->Length = 0;
      Destination->MaximumLength = v18;
      RtlAppendUnicodeToString(Destination, v10);
      RtlAppendUnicodeToString(Destination, (PCWSTR)v21);
      RtlAppendUnicodeToString(Destination, v19);
      a2->Buffer = v14;
      a2->Length = 0;
      a2->MaximumLength = v18 + 26;
      RtlAppendUnicodeToString(a2, v20);
      RtlAppendUnicodeToString(a2, v10);
      RtlAppendUnicodeToString(a2, (PCWSTR)v21);
      v8 = a2;
LABEL_8:
      RtlAppendUnicodeToString(v8, v19);
      return v5;
    }
    v15 = v11 == 0 ? 0xC000000D : 0;
  }
  else
  {
    v15 = -1073741811;
    v5 = -1073741811;
  }
  if ( v15 == -1073741811 )
  {
    v16 = v5;
    if ( v10 )
      return (unsigned int)-1073741675;
    return v16;
  }
  return v5;
}

```

## disassembly

```asm
0x14000c358  mov     [rsp-8+arg_10], rbx
0x14000c35d  mov     [rsp-8+arg_18], rsi
0x14000c362  push    rbp
0x14000c363  push    r12
0x14000c365  push    r13
0x14000c367  push    r14
0x14000c369  push    r15
0x14000c36b  lea     rbp, [rsp-40h]
0x14000c370  sub     rsp, 140h
0x14000c377  mov     rax, cs:__security_cookie
0x14000c37e  xor     rax, rsp
0x14000c381  mov     [rbp+60h+var_30], rax
0x14000c385  movups  xmm0, xmmword ptr cs:aCldflt0Etl; "CldFlt0.etl"
0x14000c38c  mov     rsi, rdx
0x14000c38f  mov     r14, rcx
0x14000c392  movsd   xmm1, qword ptr cs:aCldflt0Etl+10h; "etl"
0x14000c39a  movups  xmmword ptr [rsp+160h+var_130], xmm0
0x14000c39f  movsd   [rsp+160h+var_120], xmm1
0x14000c3a5  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000c3ac  nop     dword ptr [rax+rax+00h]
0x14000c3b1  xor     r13d, r13d
0x14000c3b4  test    al, al
0x14000c3b6  jz      loc_14000C4E8
0x14000c3bc  movups  xmm0, xmmword ptr cs:aDriverdataClou; "\\DriverData\\CloudFiles\\"
0x14000c3c3  mov     r15d, 100h
0x14000c3c9  lea     edx, [r13+48h]
0x14000c3cd  movups  xmm1, xmmword ptr cs:aDriverdataClou+10h; "ata\\CloudFiles\\"
0x14000c3d4  mov     r8d, 73557348h
0x14000c3da  mov     ecx, r15d
0x14000c3dd  movups  xmmword ptr [rbp+60h+Source], xmm0
0x14000c3e1  movups  xmm0, xmmword ptr cs:aDriverdataClou+20h; "dFiles\\"
0x14000c3e8  movups  [rbp+60h+var_A8], xmm1
0x14000c3ec  movaps  xmm1, xmmword ptr cs:aGlobalrootDriv; "\\\\?\\GLOBALROOT\\DriverData\\CloudFil"...
0x14000c3f3  movaps  xmmword ptr [rbp+60h+var_80], xmm1
0x14000c3f7  movaps  xmm1, xmmword ptr cs:aGlobalrootDriv+20h; "riverData\\CloudFiles\\"
0x14000c3fe  movups  [rbp+60h+var_98], xmm0
0x14000c402  movaps  xmm0, xmmword ptr cs:aGlobalrootDriv+10h; "ALROOT\\DriverData\\CloudFiles\\"
0x14000c409  movaps  [rbp+60h+var_60], xmm1
0x14000c40d  movups  xmm1, xmmword ptr cs:aGlobalrootDriv+3Ch; "dFiles\\"
0x14000c414  movaps  xmmword ptr [rbp-10h], xmm0
0x14000c418  movaps  xmm0, xmmword ptr cs:aGlobalrootDriv+30h; "a\\CloudFiles\\"
0x14000c41f  movaps  [rbp+60h+var_50], xmm0
0x14000c423  movups  [rbp+60h+var_50+0Ch], xmm1
0x14000c427  call    cs:__imp_ExAllocatePool2
0x14000c42e  nop     dword ptr [rax+rax+00h]
0x14000c433  mov     r12, rax
0x14000c436  test    rax, rax
0x14000c439  jnz     short loc_14000C445
0x14000c43b  mov     ebx, 0C000009Ah
0x14000c440  jmp     loc_14000C6C3
0x14000c445  mov     edx, 64h ; 'd'
0x14000c44a  mov     r8d, 73557348h
0x14000c450  mov     rcx, r15
0x14000c453  call    cs:__imp_ExAllocatePool2
0x14000c45a  nop     dword ptr [rax+rax+00h]
0x14000c45f  mov     r15, rax
0x14000c462  test    rax, rax
0x14000c465  jnz     short loc_14000C47D
0x14000c467  mov     rcx, r12; P
0x14000c46a  mov     edx, 73557348h; Tag
0x14000c46f  call    cs:__imp_ExFreePoolWithTag
0x14000c476  nop     dword ptr [rax+rax+00h]
0x14000c47b  jmp     short loc_14000C43B
0x14000c47d  lea     rdx, [rbp+60h+Source]; Source
0x14000c481  mov     [rsi+8], r12
0x14000c485  mov     rcx, rsi; Destination
0x14000c488  mov     dword ptr [rsi], 480000h
0x14000c48e  mov     ebx, r13d
0x14000c491  call    cs:__imp_RtlAppendUnicodeToString
0x14000c498  nop     dword ptr [rax+rax+00h]
0x14000c49d  lea     rdx, [rsp+160h+var_130]; Source
0x14000c4a2  mov     rcx, rsi; Destination
0x14000c4a5  call    cs:__imp_RtlAppendUnicodeToString
0x14000c4ac  nop     dword ptr [rax+rax+00h]
0x14000c4b1  lea     rdx, [rbp+60h+var_80]; Source
0x14000c4b5  mov     [r14+8], r15
0x14000c4b9  mov     rcx, r14; Destination
0x14000c4bc  mov     dword ptr [r14], 640000h
0x14000c4c3  call    cs:__imp_RtlAppendUnicodeToString
0x14000c4ca  nop     dword ptr [rax+rax+00h]
0x14000c4cf  mov     rcx, r14; Destination
0x14000c4d2  lea     rdx, [rsp+160h+var_130]; Source
0x14000c4d7  call    cs:__imp_RtlAppendUnicodeToString
0x14000c4de  nop     dword ptr [rax+rax+00h]
0x14000c4e3  jmp     loc_14000C6C3
0x14000c4e8  movups  xmm0, xmmword ptr cs:aSystem32Logfil; "\\System32\\LogFiles\\CloudFiles\\"
0x14000c4ef  movups  xmm1, xmmword ptr cs:aSystem32Logfil+10h; "2\\LogFiles\\CloudFiles\\"
0x14000c4f6  movups  xmmword ptr [rsp+160h+var_F8], xmm0
0x14000c4fb  movups  xmm0, xmmword ptr cs:aSystem32Logfil+20h; "es\\CloudFiles\\"
0x14000c502  movups  xmmword ptr [rsp+160h+var_F8+10h], xmm1
0x14000c507  movups  xmm1, xmmword ptr cs:aSystem32Logfil+2Eh; "dFiles\\"
0x14000c50e  movups  [rbp+60h+var_D8], xmm0
0x14000c512  movups  xmm0, xmmword ptr cs:aDosdevices; "\\DosDevices\\"
0x14000c519  movups  [rbp+60h+var_D8+0Eh], xmm1
0x14000c51d  movups  xmm1, xmmword ptr cs:aDosdevices+0Ah; "evices\\"
0x14000c524  movups  xmmword ptr [rsp+160h+var_118], xmm0
0x14000c529  movups  xmmword ptr [rsp+160h+var_118+0Ah], xmm1
0x14000c52e  call    cs:__imp_RtlGetNtSystemRoot
0x14000c535  nop     dword ptr [rax+rax+00h]
0x14000c53a  mov     r12, rax
0x14000c53d  test    rax, rax
0x14000c540  jz      loc_14000C6A7
0x14000c546  mov     edx, 7FFFh
0x14000c54b  mov     ecx, edx
0x14000c54d  cmp     [rax], r13w
0x14000c551  jz      short loc_14000C55D
0x14000c553  add     rax, 2
0x14000c557  sub     rcx, 1
0x14000c55b  jnz     short loc_14000C54D
0x14000c55d  mov     rax, rcx
0x14000c560  neg     rax
0x14000c563  mov     eax, 0C000000Dh
0x14000c568  sbb     ebx, ebx
0x14000c56a  not     ebx
0x14000c56c  and     ebx, eax
0x14000c56e  test    rcx, rcx
0x14000c571  jz      loc_14000C6A3
0x14000c577  sub     rdx, rcx
0x14000c57a  add     rdx, rdx
0x14000c57d  neg     rcx
0x14000c580  sbb     rax, rax
0x14000c583  and     rax, rdx
0x14000c586  cmp     rax, 0FFA9h
0x14000c58c  jb      short loc_14000C598
0x14000c58e  mov     ebx, 0C0000095h
0x14000c593  jmp     loc_14000C6C3
0x14000c598  add     rax, 56h ; 'V'
0x14000c59c  mov     r15d, 100h
0x14000c5a2  mov     rdx, rax
0x14000c5a5  mov     [rsp+160h+var_140], rax
0x14000c5aa  mov     ecx, r15d
0x14000c5ad  mov     r8d, 73557348h
0x14000c5b3  call    cs:__imp_ExAllocatePool2
0x14000c5ba  nop     dword ptr [rax+rax+00h]
0x14000c5bf  mov     r13, rax
0x14000c5c2  test    rax, rax
0x14000c5c5  jz      loc_14000C43B
0x14000c5cb  mov     rax, [rsp+160h+var_140]
0x14000c5d0  mov     r8d, 73557348h
0x14000c5d6  add     rax, 1Ah
0x14000c5da  mov     ecx, r15d
0x14000c5dd  mov     rdx, rax
0x14000c5e0  mov     [rsp+160h+var_138], rax
0x14000c5e5  call    cs:__imp_ExAllocatePool2
0x14000c5ec  nop     dword ptr [rax+rax+00h]
0x14000c5f1  mov     r15, rax
0x14000c5f4  test    rax, rax
0x14000c5f7  jnz     short loc_14000C601
0x14000c5f9  mov     rcx, r13
0x14000c5fc  jmp     loc_14000C46A
0x14000c601  xor     eax, eax
0x14000c603  mov     [r14+8], r13
0x14000c607  mov     [r14], ax
0x14000c60b  mov     rdx, r12; Source
0x14000c60e  mov     rax, [rsp+160h+var_140]
0x14000c613  mov     rcx, r14; Destination
0x14000c616  mov     [r14+2], ax
0x14000c61b  call    cs:__imp_RtlAppendUnicodeToString
0x14000c622  nop     dword ptr [rax+rax+00h]
0x14000c627  lea     rdx, [rsp+160h+var_F8]; Source
0x14000c62c  mov     rcx, r14; Destination
0x14000c62f  call    cs:__imp_RtlAppendUnicodeToString
0x14000c636  nop     dword ptr [rax+rax+00h]
0x14000c63b  lea     rdx, [rsp+160h+var_130]; Source
0x14000c640  mov     rcx, r14; Destination
0x14000c643  call    cs:__imp_RtlAppendUnicodeToString
0x14000c64a  nop     dword ptr [rax+rax+00h]
0x14000c64f  xor     eax, eax
0x14000c651  mov     [rsi+8], r15
0x14000c655  mov     [rsi], ax
0x14000c658  lea     rdx, [rsp+160h+var_118]; Source
0x14000c65d  mov     rax, [rsp+160h+var_138]
0x14000c662  mov     rcx, rsi; Destination
0x14000c665  mov     [rsi+2], ax
0x14000c669  call    cs:__imp_RtlAppendUnicodeToString
0x14000c670  nop     dword ptr [rax+rax+00h]
0x14000c675  mov     rdx, r12; Source
0x14000c678  mov     rcx, rsi; Destination
0x14000c67b  call    cs:__imp_RtlAppendUnicodeToString
0x14000c682  nop     dword ptr [rax+rax+00h]
0x14000c687  lea     rdx, [rsp+160h+var_F8]; Source
0x14000c68c  mov     rcx, rsi; Destination
0x14000c68f  call    cs:__imp_RtlAppendUnicodeToString
0x14000c696  nop     dword ptr [rax+rax+00h]
0x14000c69b  mov     rcx, rsi
0x14000c69e  jmp     loc_14000C4D2
0x14000c6a3  mov     ecx, ebx
0x14000c6a5  jmp     short loc_14000C6B0
0x14000c6a7  mov     eax, 0C000000Dh
0x14000c6ac  mov     ecx, eax
0x14000c6ae  mov     ebx, eax
0x14000c6b0  cmp     ecx, eax
0x14000c6b2  jnz     short loc_14000C6C3
0x14000c6b4  mov     eax, ebx
0x14000c6b6  test    r12, r12
0x14000c6b9  mov     ebx, 0C0000095h
0x14000c6be  cmovnz  eax, ebx
0x14000c6c1  mov     ebx, eax
0x14000c6c3  mov     eax, ebx
0x14000c6c5  mov     rcx, [rbp+60h+var_30]
0x14000c6c9  xor     rcx, rsp; StackCookie
0x14000c6cc  call    __security_check_cookie
0x14000c6d1  lea     r11, [rsp+160h+var_20]
0x14000c6d9  mov     rbx, [r11+40h]
0x14000c6dd  mov     rsi, [r11+48h]
0x14000c6e1  mov     rsp, r11
0x14000c6e4  pop     r15
0x14000c6e6  pop     r14
0x14000c6e8  pop     r13
0x14000c6ea  pop     r12
0x14000c6ec  pop     rbp
0x14000c6ed  retn
```
