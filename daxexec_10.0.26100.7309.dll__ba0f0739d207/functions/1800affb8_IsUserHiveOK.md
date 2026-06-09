# IsUserHiveOK

- ea: `0x1800affb8`
- end: `0x1800b01af`
- name: `IsUserHiveOK`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008e820`

## callees

- `0x1800afeec`
- `0x1800afefc`
- `0x1800affb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b00c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b00c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b0001`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b00b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b0001`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b00b1`

## string_xrefs

- `0x1800b006a`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800b0107`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800b018b`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800b0058`: `IsElevatedToken`
- `0x1800b00f5`: `GetTokenElevationType`
- `0x1800b0172`: `COM will not use the per-user hive in this process.This can cause activation of per-user classes from Elevated and Accessibilty appsto fail with REGDB_E_CLASSNOTREG.`

## pseudocode

```c
__int64 __fastcall IsUserHiveOK(__int64 a1, int *a2)
{
  int v3; // esi
  void *v4; // rcx
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-18h]
  int v11; // [rsp+80h] [rbp+38h] BYREF
  int v12; // [rsp+84h] [rbp+3Ch]
  DWORD TokenInformation; // [rsp+88h] [rbp+40h] BYREF
  int v14; // [rsp+90h] [rbp+48h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+50h] BYREF

  v12 = HIDWORD(a1);
  *a2 = 0;
  v11 = 0;
  v14 = 0;
  v3 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( !TokenInformation )
    {
LABEL_21:
      v6 = IsUIAccessToken(v4, &v14);
      if ( (v6 & 0x80000000) != 0 )
        return v6;
      v8 = v14 == 0;
      *a2 = v8;
      goto LABEL_23;
    }
    v3 = 1;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( dword_180106038 )
      ComTraceMessage(
        v6,
        "onecore\\com\\published\\comutils\\reghelp.cxx",
        "IsElevatedToken",
        127,
        0,
        L"%!HRESULT!",
        v6);
    if ( (v6 & 0x80000000) != 0 )
      return v6;
  }
  if ( !v3 )
    goto LABEL_21;
  TokenInformation = 0;
  v11 = 1;
  v6 = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenElevationType, &v11, 4u, &TokenInformation) )
  {
    v7 = GetLastError();
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( dword_180106038 )
    {
      LODWORD(v10) = v6;
      ComTraceMessage(
        v6,
        "onecore\\com\\published\\comutils\\reghelp.cxx",
        "GetTokenElevationType",
        174,
        0,
        L"%!HRESULT!",
        v10);
    }
  }
  if ( (v6 & 0x80000000) == 0 )
  {
    if ( v11 == 2 )
    {
      *a2 = 0;
LABEL_24:
      if ( !byte_1801085A0 )
      {
        byte_1801085A0 = 1;
        if ( dword_180106038 )
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\published\\comutils\\reghelp.cxx",
            "IsUserHiveOK",
            249,
            1,
            L"COM will not use the per-user hive in this process.This can cause activation of per-user classes from Elevat"
             "ed and Accessibilty appsto fail with REGDB_E_CLASSNOTREG.");
      }
      return v6;
    }
    if ( v11 == 1 )
    {
      *a2 = 1;
      v8 = 1;
    }
    else
    {
      v8 = *a2;
    }
LABEL_23:
    if ( v8 )
      return v6;
    goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x1800affb8  mov     [rsp-30h+arg_0], rcx
0x1800affbd  push    rbp
0x1800affbe  push    rbx
0x1800affbf  push    rsi
0x1800affc0  push    rdi
0x1800affc1  push    r14
0x1800affc3  push    r15
0x1800affc5  mov     rbp, rsp
0x1800affc8  sub     rsp, 48h
0x1800affcc  xor     r14d, r14d
0x1800affcf  lea     rax, [rbp+arg_18]
0x1800affd3  mov     rdi, rdx
0x1800affd6  mov     [rdx], r14d
0x1800affd9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800affdd  mov     dword ptr [rbp+arg_0], r14d
0x1800affe1  mov     [rbp+arg_10], r14d
0x1800affe5  mov     esi, r14d
0x1800affe8  lea     r9d, [r14+4]; TokenInformationLength
0x1800affec  mov     [rbp+arg_18], r14d
0x1800afff0  lea     edx, [r14+14h]; TokenInformationClass
0x1800afff4  mov     [rbp+TokenInformation], r14d
0x1800afff8  lea     rcx, [r14-4]; TokenHandle
0x1800afffc  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800b0001  call    cs:__imp_GetTokenInformation
0x1800b0008  nop     dword ptr [rax+rax+00h]
0x1800b000d  lea     r15d, [r14+1]
0x1800b0011  test    eax, eax
0x1800b0013  jz      short loc_1800B0024
0x1800b0015  cmp     [rbp+TokenInformation], r14d
0x1800b0019  jz      loc_1800B013A
0x1800b001f  mov     esi, r15d
0x1800b0022  jmp     short loc_1800B0080
0x1800b0024  call    cs:__imp_GetLastError
0x1800b002b  nop     dword ptr [rax+rax+00h]
0x1800b0030  mov     ebx, eax
0x1800b0032  test    eax, eax
0x1800b0034  jle     short loc_1800B003F
0x1800b0036  movzx   ebx, ax
0x1800b0039  or      ebx, 80070000h
0x1800b003f  cmp     cs:dword_180106038, r14d
0x1800b0046  jbe     short loc_1800B0078
0x1800b0048  mov     dword ptr [rsp+48h+var_18], ebx
0x1800b004c  lea     rax, aHresult; "%!HRESULT!"
0x1800b0053  mov     [rsp+48h+var_20], rax
0x1800b0058  lea     r8, aIselevatedtoke; "IsElevatedToken"
0x1800b005f  mov     r9d, 7Fh
0x1800b0065  mov     dword ptr [rsp+48h+ReturnLength], r14d
0x1800b006a  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800b0071  mov     ecx, ebx
0x1800b0073  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800b0078  test    ebx, ebx
0x1800b007a  js      loc_1800B019F
0x1800b0080  test    esi, esi
0x1800b0082  jz      loc_1800B013A
0x1800b0088  mov     r9d, 4; TokenInformationLength
0x1800b008e  mov     [rbp+TokenInformation], r14d
0x1800b0092  lea     rax, [rbp+TokenInformation]
0x1800b0096  mov     dword ptr [rbp+arg_0], r15d
0x1800b009a  lea     r8, [rbp+arg_0]; TokenInformation
0x1800b009e  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800b00a3  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800b00aa  mov     ebx, r14d
0x1800b00ad  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800b00b1  call    cs:__imp_GetTokenInformation
0x1800b00b8  nop     dword ptr [rax+rax+00h]
0x1800b00bd  test    eax, eax
0x1800b00bf  jnz     short loc_1800B0115
0x1800b00c1  call    cs:__imp_GetLastError
0x1800b00c8  nop     dword ptr [rax+rax+00h]
0x1800b00cd  mov     ebx, eax
0x1800b00cf  test    eax, eax
0x1800b00d1  jle     short loc_1800B00DC
0x1800b00d3  movzx   ebx, ax
0x1800b00d6  or      ebx, 80070000h
0x1800b00dc  cmp     cs:dword_180106038, r14d
0x1800b00e3  jbe     short loc_1800B0115
0x1800b00e5  mov     dword ptr [rsp+48h+var_18], ebx
0x1800b00e9  lea     rax, aHresult; "%!HRESULT!"
0x1800b00f0  mov     [rsp+48h+var_20], rax
0x1800b00f5  lea     r8, aGettokenelevat; "GetTokenElevationType"
0x1800b00fc  mov     r9d, 0AEh
0x1800b0102  mov     dword ptr [rsp+48h+ReturnLength], r14d
0x1800b0107  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800b010e  mov     ecx, ebx
0x1800b0110  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800b0115  test    ebx, ebx
0x1800b0117  js      loc_1800B019F
0x1800b011d  cmp     dword ptr [rbp+arg_0], 2
0x1800b0121  jnz     short loc_1800B0128
0x1800b0123  mov     [rdi], r14d
0x1800b0126  jmp     short loc_1800B0159
0x1800b0128  cmp     dword ptr [rbp+arg_0], r15d
0x1800b012c  jnz     short loc_1800B0136
0x1800b012e  mov     [rdi], r15d
0x1800b0131  mov     eax, r15d
0x1800b0134  jmp     short loc_1800B0155
0x1800b0136  mov     eax, [rdi]
0x1800b0138  jmp     short loc_1800B0155
0x1800b013a  lea     rdx, [rbp+arg_10]; int *
0x1800b013e  call    ?IsUIAccessToken@@YAJPEAXPEAH@Z; IsUIAccessToken(void *,int *)
0x1800b0143  mov     ebx, eax
0x1800b0145  test    eax, eax
0x1800b0147  js      short loc_1800B019F
0x1800b0149  cmp     [rbp+arg_10], r14d
0x1800b014d  mov     eax, r14d
0x1800b0150  setz    al
0x1800b0153  mov     [rdi], eax
0x1800b0155  test    eax, eax
0x1800b0157  jnz     short loc_1800B019F
0x1800b0159  cmp     cs:byte_1801085A0, r14b
0x1800b0160  jnz     short loc_1800B019F
0x1800b0162  cmp     cs:dword_180106038, r14d
0x1800b0169  mov     cs:byte_1801085A0, r15b
0x1800b0170  jbe     short loc_1800B019F
0x1800b0172  lea     rax, aComWillNotUseT; "COM will not use the per-user hive in t"...
0x1800b0179  mov     r9d, 0F9h
0x1800b017f  mov     [rsp+48h+var_20], rax
0x1800b0184  lea     r8, aIsuserhiveok; "IsUserHiveOK"
0x1800b018b  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800b0192  mov     dword ptr [rsp+48h+ReturnLength], r15d
0x1800b0197  or      ecx, 0FFFFFFFFh
0x1800b019a  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800b019f  mov     eax, ebx
0x1800b01a1  add     rsp, 48h
0x1800b01a5  pop     r15
0x1800b01a7  pop     r14
0x1800b01a9  pop     rdi
0x1800b01aa  pop     rsi
0x1800b01ab  pop     rbx
0x1800b01ac  pop     rbp
0x1800b01ad  retn
```
