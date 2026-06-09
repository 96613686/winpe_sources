# I_PEVerifyAndLogPEAuthCerts

- ea: `0x18007f664`
- end: `0x18007f7e5`
- name: `I_PEVerifyAndLogPEAuthCerts`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007f7ec`
- `0x180080528`

## callees

- `0x18002bf20`
- `0x18007f664`
- `0x18008047c`
- `0x18009860c`
- `0x1800a5b5c`
- `0x1800e32a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007f6a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007f6a2`

## string_xrefs

- `0x18007f687`: `\SystemRoot\System32\Drivers\PEAuth.sys`

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
  if ( qword_180049EB0 )
  {
    v0 = I_PEVerifyCertificates(qword_180049EB0, (unsigned int)dword_180049EBC, v9, &v6);
    if ( v0 )
    {
      v1 = v0 | 0x20000;
      if ( (g_PEAuthConfigOptions & 1) != 0 )
        I_PEWriteComponentLoadExEvents(v1, SDWORD2(v6), &DestinationString.Length, 1);
      I_PEUpdateHashCache(g_rgEmptyHash, (__int64)v9, &DestinationString, v1, 1, 0);
    }
    v2 = qword_180049EC0;
    if ( qword_180049EC0 )
    {
      if ( (_DWORD)v6 )
      {
        I_MincryptFreeChainInfo(v7);
        v2 = qword_180049EC0;
        v6 = 0;
        v7 = 0;
        v8 = 0;
      }
      v3 = I_PEVerifyCertificates(v2, (unsigned int)dword_180049EB8, v9, &v6);
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
0x18007f664  mov     [rsp-8+arg_0], rbx
0x18007f669  push    rbp
0x18007f66a  lea     rbp, [rsp-57h]
0x18007f66f  sub     rsp, 90h
0x18007f676  mov     rax, cs:__security_cookie
0x18007f67d  xor     rax, rsp
0x18007f680  mov     [rbp+57h+var_8], rax
0x18007f684  xorps   xmm0, xmm0
0x18007f687  lea     rdx, aSystemrootSyst_5; "\\SystemRoot\\System32\\Drivers\\PEAuth"...
0x18007f68e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007f692  movups  [rbp+57h+var_50], xmm0
0x18007f696  movups  [rbp+57h+var_40], xmm0
0x18007f69a  movups  [rbp+57h+var_30], xmm0
0x18007f69e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007f6a2  call    cs:__imp_RtlInitUnicodeString
0x18007f6a9  nop     dword ptr [rax+rax+00h]
0x18007f6ae  mov     rcx, cs:qword_180049EB0
0x18007f6b5  test    rcx, rcx
0x18007f6b8  jz      loc_18007F7B8
0x18007f6be  mov     edx, cs:dword_180049EBC
0x18007f6c4  lea     r9, [rbp+57h+var_50]
0x18007f6c8  lea     r8, [rbp+57h+var_20]
0x18007f6cc  call    I_PEVerifyCertificates
0x18007f6d1  mov     ebx, eax
0x18007f6d3  test    eax, eax
0x18007f6d5  jz      short loc_18007F721
0x18007f6d7  mov     ecx, cs:g_PEAuthConfigOptions
0x18007f6dd  bts     ebx, 11h
0x18007f6e1  test    cl, 1
0x18007f6e4  jz      short loc_18007F6FA
0x18007f6e6  mov     edx, dword ptr [rbp+57h+var_50+8]
0x18007f6e9  lea     r8, [rbp+57h+DestinationString]
0x18007f6ed  mov     r9d, 1
0x18007f6f3  mov     ecx, ebx
0x18007f6f5  call    I_PEWriteComponentLoadExEvents
0x18007f6fa  mov     [rsp+90h+var_68], 0; int
0x18007f702  lea     r8, [rbp+57h+DestinationString]
0x18007f706  mov     r9d, ebx
0x18007f709  mov     [rsp+90h+var_70], 1; int
0x18007f711  lea     rdx, [rbp+57h+var_20]
0x18007f715  lea     rcx, g_rgEmptyHash; Source2
0x18007f71c  call    I_PEUpdateHashCache
0x18007f721  mov     rcx, cs:qword_180049EC0
0x18007f728  test    rcx, rcx
0x18007f72b  jz      loc_18007F7B8
0x18007f731  cmp     dword ptr [rbp+57h+var_50], 0
0x18007f735  jz      short loc_18007F756
0x18007f737  mov     rcx, qword ptr [rbp+57h+var_40]
0x18007f73b  call    I_MincryptFreeChainInfo
0x18007f740  mov     rcx, cs:qword_180049EC0
0x18007f747  xorps   xmm0, xmm0
0x18007f74a  movups  [rbp+57h+var_50], xmm0
0x18007f74e  movups  [rbp+57h+var_40], xmm0
0x18007f752  movups  [rbp+57h+var_30], xmm0
0x18007f756  mov     edx, cs:dword_180049EB8
0x18007f75c  lea     r9, [rbp+57h+var_50]
0x18007f760  lea     r8, [rbp+57h+var_20]
0x18007f764  call    I_PEVerifyCertificates
0x18007f769  mov     ebx, eax
0x18007f76b  test    eax, eax
0x18007f76d  jz      short loc_18007F7B8
0x18007f76f  mov     eax, cs:g_PEAuthConfigOptions
0x18007f775  bts     ebx, 12h
0x18007f779  test    al, 1
0x18007f77b  jz      short loc_18007F791
0x18007f77d  mov     edx, dword ptr [rbp+57h+var_50+8]
0x18007f780  lea     r8, [rbp+57h+DestinationString]
0x18007f784  mov     r9d, 1
0x18007f78a  mov     ecx, ebx
0x18007f78c  call    I_PEWriteComponentLoadExEvents
0x18007f791  mov     [rsp+90h+var_68], 0; int
0x18007f799  lea     r8, [rbp+57h+DestinationString]
0x18007f79d  mov     r9d, ebx
0x18007f7a0  mov     [rsp+90h+var_70], 1; int
0x18007f7a8  lea     rdx, [rbp+57h+var_20]
0x18007f7ac  lea     rcx, g_rgEmptyHash; Source2
0x18007f7b3  call    I_PEUpdateHashCache
0x18007f7b8  cmp     dword ptr [rbp+57h+var_50], 0
0x18007f7bc  jz      short loc_18007F7C7
0x18007f7be  mov     rcx, qword ptr [rbp+57h+var_40]
0x18007f7c2  call    I_MincryptFreeChainInfo
0x18007f7c7  mov     rcx, [rbp+57h+var_8]
0x18007f7cb  xor     rcx, rsp; StackCookie
0x18007f7ce  call    __security_check_cookie
0x18007f7d3  mov     rbx, [rsp+90h+arg_0]
0x18007f7db  add     rsp, 90h
0x18007f7e2  pop     rbp
0x18007f7e3  retn
```
