# GetSecuritySID(WELL_KNOWN_SID_TYPE,void * &)

- ea: `0x180082c6c`
- end: `0x180082d8f`
- name: `?GetSecuritySID@@YA_NW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z`
- size: `291`
- prototype: `bool __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082dc8`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180082c6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d46`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082d24`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082d24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082cc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082cc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082d6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082d6e`

## pseudocode

```c
char __fastcall GetSecuritySID(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  HLOCAL v4; // rax
  DWORD LastError; // eax
  DWORD v7; // eax
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
  }
  if ( !*a2 )
  {
    cbSid = 68;
    v4 = LocalAlloc(0, 0x44u);
    *a2 = v4;
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, LastError);
      }
      return 0;
    }
    if ( !CreateWellKnownSid(WellKnownSidType, 0, v4, &cbSid) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, v7);
      }
      LocalFree(*a2);
      *a2 = 0;
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180082c6c  mov     [rsp+arg_0], rbx
0x180082c71  mov     [rsp+arg_10], rbp
0x180082c76  push    rdi
0x180082c77  sub     rsp, 20h
0x180082c7b  mov     rbx, rdx
0x180082c7e  mov     edi, ecx
0x180082c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c87  lea     rbp, WPP_GLOBAL_Control
0x180082c8e  cmp     rcx, rbp
0x180082c91  jz      short loc_180082CB4
0x180082c93  test    byte ptr [rcx+1Ch], 1
0x180082c97  jz      short loc_180082CB4
0x180082c99  cmp     byte ptr [rcx+19h], 6
0x180082c9d  jb      short loc_180082CB4
0x180082c9f  mov     rcx, [rcx+10h]
0x180082ca3  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082caa  mov     edx, 0Dh
0x180082caf  call    WPP_SF_
0x180082cb4  cmp     qword ptr [rbx], 0
0x180082cb8  jnz     loc_180082D7D
0x180082cbe  mov     edx, 44h ; 'D'; uBytes
0x180082cc3  xor     ecx, ecx; uFlags
0x180082cc5  mov     [rsp+28h+cbSid], edx
0x180082cc9  call    cs:__imp_LocalAlloc
0x180082ccf  mov     [rbx], rax
0x180082cd2  test    rax, rax
0x180082cd5  jnz     short loc_180082D18
0x180082cd7  mov     rax, cs:WPP_GLOBAL_Control
0x180082cde  cmp     rax, rbp
0x180082ce1  jz      short loc_180082D14
0x180082ce3  test    byte ptr [rax+1Ch], 1
0x180082ce7  jz      short loc_180082D14
0x180082ce9  cmp     byte ptr [rax+19h], 2
0x180082ced  jb      short loc_180082D14
0x180082cef  call    cs:__imp_GetLastError
0x180082cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180082cfc  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082d03  mov     edx, 0Eh
0x180082d08  mov     r9d, eax
0x180082d0b  mov     rcx, [rcx+10h]
0x180082d0f  call    WPP_SF_d
0x180082d14  xor     al, al
0x180082d16  jmp     short loc_180082D7F
0x180082d18  lea     r9, [rsp+28h+cbSid]; cbSid
0x180082d1d  mov     r8, rax; pSid
0x180082d20  xor     edx, edx; DomainSid
0x180082d22  mov     ecx, edi; WellKnownSidType
0x180082d24  call    cs:__imp_CreateWellKnownSid
0x180082d2a  test    eax, eax
0x180082d2c  jnz     short loc_180082D7D
0x180082d2e  mov     rax, cs:WPP_GLOBAL_Control
0x180082d35  cmp     rax, rbp
0x180082d38  jz      short loc_180082D6B
0x180082d3a  test    byte ptr [rax+1Ch], 1
0x180082d3e  jz      short loc_180082D6B
0x180082d40  cmp     byte ptr [rax+19h], 2
0x180082d44  jb      short loc_180082D6B
0x180082d46  call    cs:__imp_GetLastError
0x180082d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082d53  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082d5a  mov     edx, 0Fh
0x180082d5f  mov     r9d, eax
0x180082d62  mov     rcx, [rcx+10h]
0x180082d66  call    WPP_SF_d
0x180082d6b  mov     rcx, [rbx]; hMem
0x180082d6e  call    cs:__imp_LocalFree
0x180082d74  mov     qword ptr [rbx], 0
0x180082d7b  jmp     short loc_180082D14
0x180082d7d  mov     al, 1
0x180082d7f  mov     rbx, [rsp+28h+arg_0]
0x180082d84  mov     rbp, [rsp+28h+arg_10]
0x180082d89  add     rsp, 20h
0x180082d8d  pop     rdi
0x180082d8e  retn
```
