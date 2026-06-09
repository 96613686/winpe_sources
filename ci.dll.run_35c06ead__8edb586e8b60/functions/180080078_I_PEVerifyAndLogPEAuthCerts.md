# I_PEVerifyAndLogPEAuthCerts

- ea: `0x180080078`
- end: `0x1800801f9`
- name: `I_PEVerifyAndLogPEAuthCerts`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180080200`
- `0x180080f3c`

## callees

- `0x18002c0d0`
- `0x180080078`
- `0x180080e90`
- `0x18008eddc`
- `0x1800a57b0`
- `0x1800e3270`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800800b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800800b6`

## string_xrefs

- `0x18008009b`: `\SystemRoot\System32\Drivers\PEAuth.sys`

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
  if ( qword_180049EC8 )
  {
    v0 = I_PEVerifyCertificates(qword_180049EC8, (unsigned int)dword_180049ED4, v9, &v6);
    if ( v0 )
    {
      v1 = v0 | 0x20000;
      if ( (g_PEAuthConfigOptions & 1) != 0 )
        I_PEWriteComponentLoadExEvents(v1, SDWORD2(v6), &DestinationString.Length, 1);
      I_PEUpdateHashCache(g_rgEmptyHash, (__int64)v9, &DestinationString, v1, 1, 0);
    }
    v2 = qword_180049ED8;
    if ( qword_180049ED8 )
    {
      if ( (_DWORD)v6 )
      {
        I_MincryptFreeChainInfo(v7);
        v2 = qword_180049ED8;
        v6 = 0;
        v7 = 0;
        v8 = 0;
      }
      v3 = I_PEVerifyCertificates(v2, (unsigned int)dword_180049ED0, v9, &v6);
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
0x180080078  mov     [rsp-8+arg_0], rbx
0x18008007d  push    rbp
0x18008007e  lea     rbp, [rsp-57h]
0x180080083  sub     rsp, 90h
0x18008008a  mov     rax, cs:__security_cookie
0x180080091  xor     rax, rsp
0x180080094  mov     [rbp+57h+var_8], rax
0x180080098  xorps   xmm0, xmm0
0x18008009b  lea     rdx, aSystemrootSyst_5; "\\SystemRoot\\System32\\Drivers\\PEAuth"...
0x1800800a2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800800a6  movups  [rbp+57h+var_50], xmm0
0x1800800aa  movups  [rbp+57h+var_40], xmm0
0x1800800ae  movups  [rbp+57h+var_30], xmm0
0x1800800b2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800800b6  call    cs:__imp_RtlInitUnicodeString
0x1800800bd  nop     dword ptr [rax+rax+00h]
0x1800800c2  mov     rcx, cs:qword_180049EC8
0x1800800c9  test    rcx, rcx
0x1800800cc  jz      loc_1800801CC
0x1800800d2  mov     edx, cs:dword_180049ED4
0x1800800d8  lea     r9, [rbp+57h+var_50]
0x1800800dc  lea     r8, [rbp+57h+var_20]
0x1800800e0  call    I_PEVerifyCertificates
0x1800800e5  mov     ebx, eax
0x1800800e7  test    eax, eax
0x1800800e9  jz      short loc_180080135
0x1800800eb  mov     ecx, cs:g_PEAuthConfigOptions
0x1800800f1  bts     ebx, 11h
0x1800800f5  test    cl, 1
0x1800800f8  jz      short loc_18008010E
0x1800800fa  mov     edx, dword ptr [rbp+57h+var_50+8]
0x1800800fd  lea     r8, [rbp+57h+DestinationString]
0x180080101  mov     r9d, 1
0x180080107  mov     ecx, ebx
0x180080109  call    I_PEWriteComponentLoadExEvents
0x18008010e  mov     [rsp+90h+var_68], 0; int
0x180080116  lea     r8, [rbp+57h+DestinationString]
0x18008011a  mov     r9d, ebx
0x18008011d  mov     [rsp+90h+var_70], 1; int
0x180080125  lea     rdx, [rbp+57h+var_20]
0x180080129  lea     rcx, g_rgEmptyHash; Source2
0x180080130  call    I_PEUpdateHashCache
0x180080135  mov     rcx, cs:qword_180049ED8
0x18008013c  test    rcx, rcx
0x18008013f  jz      loc_1800801CC
0x180080145  cmp     dword ptr [rbp+57h+var_50], 0
0x180080149  jz      short loc_18008016A
0x18008014b  mov     rcx, qword ptr [rbp+57h+var_40]
0x18008014f  call    I_MincryptFreeChainInfo
0x180080154  mov     rcx, cs:qword_180049ED8
0x18008015b  xorps   xmm0, xmm0
0x18008015e  movups  [rbp+57h+var_50], xmm0
0x180080162  movups  [rbp+57h+var_40], xmm0
0x180080166  movups  [rbp+57h+var_30], xmm0
0x18008016a  mov     edx, cs:dword_180049ED0
0x180080170  lea     r9, [rbp+57h+var_50]
0x180080174  lea     r8, [rbp+57h+var_20]
0x180080178  call    I_PEVerifyCertificates
0x18008017d  mov     ebx, eax
0x18008017f  test    eax, eax
0x180080181  jz      short loc_1800801CC
0x180080183  mov     eax, cs:g_PEAuthConfigOptions
0x180080189  bts     ebx, 12h
0x18008018d  test    al, 1
0x18008018f  jz      short loc_1800801A5
0x180080191  mov     edx, dword ptr [rbp+57h+var_50+8]
0x180080194  lea     r8, [rbp+57h+DestinationString]
0x180080198  mov     r9d, 1
0x18008019e  mov     ecx, ebx
0x1800801a0  call    I_PEWriteComponentLoadExEvents
0x1800801a5  mov     [rsp+90h+var_68], 0; int
0x1800801ad  lea     r8, [rbp+57h+DestinationString]
0x1800801b1  mov     r9d, ebx
0x1800801b4  mov     [rsp+90h+var_70], 1; int
0x1800801bc  lea     rdx, [rbp+57h+var_20]
0x1800801c0  lea     rcx, g_rgEmptyHash; Source2
0x1800801c7  call    I_PEUpdateHashCache
0x1800801cc  cmp     dword ptr [rbp+57h+var_50], 0
0x1800801d0  jz      short loc_1800801DB
0x1800801d2  mov     rcx, qword ptr [rbp+57h+var_40]
0x1800801d6  call    I_MincryptFreeChainInfo
0x1800801db  mov     rcx, [rbp+57h+var_8]
0x1800801df  xor     rcx, rsp; StackCookie
0x1800801e2  call    __security_check_cookie
0x1800801e7  mov     rbx, [rsp+90h+arg_0]
0x1800801ef  add     rsp, 90h
0x1800801f6  pop     rbp
0x1800801f7  retn
```
