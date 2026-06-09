# GetSecuritySID(WELL_KNOWN_SID_TYPE,void * &)

- ea: `0x1800893d0`
- end: `0x180089512`
- name: `?GetSecuritySID@@YA_NW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z`
- size: `322`
- prototype: `bool __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180089548`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800893d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800894bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800894bc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180089494`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180089494`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008942d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008942d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800894ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800894ea`

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
0x1800893d0  mov     [rsp+arg_0], rbx
0x1800893d5  mov     [rsp+arg_10], rbp
0x1800893da  push    rdi
0x1800893db  sub     rsp, 20h
0x1800893df  mov     rbx, rdx
0x1800893e2  mov     edi, ecx
0x1800893e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800893eb  lea     rbp, WPP_GLOBAL_Control
0x1800893f2  cmp     rcx, rbp
0x1800893f5  jz      short loc_180089418
0x1800893f7  test    byte ptr [rcx+1Ch], 1
0x1800893fb  jz      short loc_180089418
0x1800893fd  cmp     byte ptr [rcx+19h], 6
0x180089401  jb      short loc_180089418
0x180089403  mov     rcx, [rcx+10h]
0x180089407  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x18008940e  mov     edx, 0Dh
0x180089413  call    WPP_SF_
0x180089418  cmp     qword ptr [rbx], 0
0x18008941c  jnz     loc_1800894FF
0x180089422  mov     edx, 44h ; 'D'; uBytes
0x180089427  xor     ecx, ecx; uFlags
0x180089429  mov     [rsp+28h+cbSid], edx
0x18008942d  call    cs:__imp_LocalAlloc
0x180089434  nop     dword ptr [rax+rax+00h]
0x180089439  mov     [rbx], rax
0x18008943c  test    rax, rax
0x18008943f  jnz     short loc_180089488
0x180089441  mov     rax, cs:WPP_GLOBAL_Control
0x180089448  cmp     rax, rbp
0x18008944b  jz      short loc_180089484
0x18008944d  test    byte ptr [rax+1Ch], 1
0x180089451  jz      short loc_180089484
0x180089453  cmp     byte ptr [rax+19h], 2
0x180089457  jb      short loc_180089484
0x180089459  call    cs:__imp_GetLastError
0x180089460  nop     dword ptr [rax+rax+00h]
0x180089465  mov     rcx, cs:WPP_GLOBAL_Control
0x18008946c  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180089473  mov     edx, 0Eh
0x180089478  mov     r9d, eax
0x18008947b  mov     rcx, [rcx+10h]
0x18008947f  call    WPP_SF_d
0x180089484  xor     al, al
0x180089486  jmp     short loc_180089501
0x180089488  lea     r9, [rsp+28h+cbSid]; cbSid
0x18008948d  mov     r8, rax; pSid
0x180089490  xor     edx, edx; DomainSid
0x180089492  mov     ecx, edi; WellKnownSidType
0x180089494  call    cs:__imp_CreateWellKnownSid
0x18008949b  nop     dword ptr [rax+rax+00h]
0x1800894a0  test    eax, eax
0x1800894a2  jnz     short loc_1800894FF
0x1800894a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800894ab  cmp     rax, rbp
0x1800894ae  jz      short loc_1800894E7
0x1800894b0  test    byte ptr [rax+1Ch], 1
0x1800894b4  jz      short loc_1800894E7
0x1800894b6  cmp     byte ptr [rax+19h], 2
0x1800894ba  jb      short loc_1800894E7
0x1800894bc  call    cs:__imp_GetLastError
0x1800894c3  nop     dword ptr [rax+rax+00h]
0x1800894c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800894cf  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800894d6  mov     edx, 0Fh
0x1800894db  mov     r9d, eax
0x1800894de  mov     rcx, [rcx+10h]
0x1800894e2  call    WPP_SF_d
0x1800894e7  mov     rcx, [rbx]; hMem
0x1800894ea  call    cs:__imp_LocalFree
0x1800894f1  nop     dword ptr [rax+rax+00h]
0x1800894f6  mov     qword ptr [rbx], 0
0x1800894fd  jmp     short loc_180089484
0x1800894ff  mov     al, 1
0x180089501  mov     rbx, [rsp+28h+arg_0]
0x180089506  mov     rbp, [rsp+28h+arg_10]
0x18008950b  add     rsp, 20h
0x18008950f  pop     rdi
0x180089510  retn
```
