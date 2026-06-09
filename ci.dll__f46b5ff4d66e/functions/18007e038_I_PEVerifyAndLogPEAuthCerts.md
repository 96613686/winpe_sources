# I_PEVerifyAndLogPEAuthCerts

- ea: `0x18007e038`
- end: `0x18007e1b9`
- name: `I_PEVerifyAndLogPEAuthCerts`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007e1c0`
- `0x18007eefc`

## callees

- `0x18002bef0`
- `0x18007e038`
- `0x18007ee50`
- `0x180096fdc`
- `0x1800a452c`
- `0x1800e32ac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007e076`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e076`

## string_xrefs

- `0x18007e05b`: `\SystemRoot\System32\Drivers\PEAuth.sys`

## pseudocode

```c
void I_PEVerifyAndLogPEAuthCerts()
{
  int v0; // ebx
  int v1; // ebx
  __int64 v2; // rcx
  int v3; // ebx
  int v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-9h] BYREF
  __int128 v6; // [rsp+40h] [rbp+7h] BYREF
  __int128 v7; // [rsp+50h] [rbp+17h]
  __int128 v8; // [rsp+60h] [rbp+27h]
  _BYTE v9[24]; // [rsp+70h] [rbp+37h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SystemRoot\\System32\\Drivers\\PEAuth.sys");
  if ( qword_180048EC0 )
  {
    v0 = I_PEVerifyCertificates(qword_180048EC0, (unsigned int)dword_180048EC8, v9, &v6);
    if ( v0 )
    {
      v1 = v0 | 0x20000;
      if ( (g_PEAuthConfigOptions & 1) != 0 )
        I_PEWriteComponentLoadExEvents(v1, SDWORD2(v6), &DestinationString.Length, 1);
      I_PEUpdateHashCache(g_rgEmptyHash, (__int64)v9, &DestinationString, v1, 1, 0);
    }
    v2 = qword_180048ED0;
    if ( qword_180048ED0 )
    {
      if ( (_DWORD)v6 )
      {
        I_MincryptFreeChainInfo(v7);
        v2 = qword_180048ED0;
        v6 = 0;
        v7 = 0;
        v8 = 0;
      }
      v3 = I_PEVerifyCertificates(v2, (unsigned int)dword_180048ECC, v9, &v6);
      if ( v3 )
      {
        v4 = v3 | 0x40000;
        if ( (g_PEAuthConfigOptions & 1) != 0 )
          I_PEWriteComponentLoadExEvents(v4, SDWORD2(v6), &DestinationString.Length, 1);
        I_PEUpdateHashCache(g_rgEmptyHash, (__int64)v9, &DestinationString, v4, 1, 0);
      }
    }
  }
  if ( (_DWORD)v6 )
    I_MincryptFreeChainInfo(v7);
}

```

## disassembly

```asm
0x18007e038  mov     [rsp-8+arg_0], rbx
0x18007e03d  push    rbp
0x18007e03e  lea     rbp, [rsp-57h]
0x18007e043  sub     rsp, 90h
0x18007e04a  mov     rax, cs:__security_cookie
0x18007e051  xor     rax, rsp
0x18007e054  mov     [rbp+57h+var_8], rax
0x18007e058  xorps   xmm0, xmm0
0x18007e05b  lea     rdx, aSystemrootSyst_5; "\\SystemRoot\\System32\\Drivers\\PEAuth"...
0x18007e062  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007e066  movups  [rbp+57h+var_50], xmm0
0x18007e06a  movups  [rbp+57h+var_40], xmm0
0x18007e06e  movups  [rbp+57h+var_30], xmm0
0x18007e072  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007e076  call    cs:__imp_RtlInitUnicodeString
0x18007e07d  nop     dword ptr [rax+rax+00h]
0x18007e082  mov     rcx, cs:qword_180048EC0
0x18007e089  test    rcx, rcx
0x18007e08c  jz      loc_18007E18C
0x18007e092  mov     edx, cs:dword_180048EC8
0x18007e098  lea     r9, [rbp+57h+var_50]
0x18007e09c  lea     r8, [rbp+57h+var_20]
0x18007e0a0  call    I_PEVerifyCertificates
0x18007e0a5  mov     ebx, eax
0x18007e0a7  test    eax, eax
0x18007e0a9  jz      short loc_18007E0F5
0x18007e0ab  mov     ecx, cs:g_PEAuthConfigOptions
0x18007e0b1  bts     ebx, 11h
0x18007e0b5  test    cl, 1
0x18007e0b8  jz      short loc_18007E0CE
0x18007e0ba  mov     edx, dword ptr [rbp+57h+var_50+8]
0x18007e0bd  lea     r8, [rbp+57h+DestinationString]
0x18007e0c1  mov     r9d, 1
0x18007e0c7  mov     ecx, ebx
0x18007e0c9  call    I_PEWriteComponentLoadExEvents
0x18007e0ce  mov     [rsp+90h+var_68], 0; int
0x18007e0d6  lea     r8, [rbp+57h+DestinationString]
0x18007e0da  mov     r9d, ebx
0x18007e0dd  mov     [rsp+90h+var_70], 1; int
0x18007e0e5  lea     rdx, [rbp+57h+var_20]
0x18007e0e9  lea     rcx, g_rgEmptyHash; Source2
0x18007e0f0  call    I_PEUpdateHashCache
0x18007e0f5  mov     rcx, cs:qword_180048ED0
0x18007e0fc  test    rcx, rcx
0x18007e0ff  jz      loc_18007E18C
0x18007e105  cmp     dword ptr [rbp+57h+var_50], 0
0x18007e109  jz      short loc_18007E12A
0x18007e10b  mov     rcx, qword ptr [rbp+57h+var_40]
0x18007e10f  call    I_MincryptFreeChainInfo
0x18007e114  mov     rcx, cs:qword_180048ED0
0x18007e11b  xorps   xmm0, xmm0
0x18007e11e  movups  [rbp+57h+var_50], xmm0
0x18007e122  movups  [rbp+57h+var_40], xmm0
0x18007e126  movups  [rbp+57h+var_30], xmm0
0x18007e12a  mov     edx, cs:dword_180048ECC
0x18007e130  lea     r9, [rbp+57h+var_50]
0x18007e134  lea     r8, [rbp+57h+var_20]
0x18007e138  call    I_PEVerifyCertificates
0x18007e13d  mov     ebx, eax
0x18007e13f  test    eax, eax
0x18007e141  jz      short loc_18007E18C
0x18007e143  mov     eax, cs:g_PEAuthConfigOptions
0x18007e149  bts     ebx, 12h
0x18007e14d  test    al, 1
0x18007e14f  jz      short loc_18007E165
0x18007e151  mov     edx, dword ptr [rbp+57h+var_50+8]
0x18007e154  lea     r8, [rbp+57h+DestinationString]
0x18007e158  mov     r9d, 1
0x18007e15e  mov     ecx, ebx
0x18007e160  call    I_PEWriteComponentLoadExEvents
0x18007e165  mov     [rsp+90h+var_68], 0; int
0x18007e16d  lea     r8, [rbp+57h+DestinationString]
0x18007e171  mov     r9d, ebx
0x18007e174  mov     [rsp+90h+var_70], 1; int
0x18007e17c  lea     rdx, [rbp+57h+var_20]
0x18007e180  lea     rcx, g_rgEmptyHash; Source2
0x18007e187  call    I_PEUpdateHashCache
0x18007e18c  cmp     dword ptr [rbp+57h+var_50], 0
0x18007e190  jz      short loc_18007E19B
0x18007e192  mov     rcx, qword ptr [rbp+57h+var_40]
0x18007e196  call    I_MincryptFreeChainInfo
0x18007e19b  mov     rcx, [rbp+57h+var_8]
0x18007e19f  xor     rcx, rsp; StackCookie
0x18007e1a2  call    __security_check_cookie
0x18007e1a7  mov     rbx, [rsp+90h+arg_0]
0x18007e1af  add     rsp, 90h
0x18007e1b6  pop     rbp
0x18007e1b7  retn
```
