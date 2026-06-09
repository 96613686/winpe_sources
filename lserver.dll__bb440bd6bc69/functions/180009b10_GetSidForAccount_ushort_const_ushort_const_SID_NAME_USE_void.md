# GetSidForAccount(ushort const *,ushort const *,_SID_NAME_USE *,void * *)

- ea: `0x180009b10`
- end: `0x180009d71`
- name: `?GetSidForAccount@@YAJPEBG0PEAW4_SID_NAME_USE@@PEAPEAX@Z`
- size: `609`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, enum _SID_NAME_USE *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000a048`

## callees

- `0x180006cbc`
- `0x180006cf0`
- `0x180009b10`
- `0x18000a2b4`
- `0x18001aea4`
- `0x18001af24`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d27`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d3b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d4e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d27`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d3b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d4e`
- `ADVAPI32!LookupAccountNameW` at `0x180009b69`
- `ADVAPI32!LookupAccountNameW` at `0x180009cbd`
- `ADVAPI32!LookupAccountNameW` at `0x180009b69`
- `ADVAPI32!LookupAccountNameW` at `0x180009cbd`

## string_xrefs

- `0x180009bb7`: `GetSidForAccount`
- `0x180009c10`: `GetSidForAccount`
- `0x180009c7a`: `GetSidForAccount`
- `0x180009cf6`: `GetSidForAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetSidForAccount(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        enum _SID_NAME_USE *a3,
        void **a4)
{
  int Error; // edi
  void *v8; // rbx
  void *v9; // rax
  LPWSTR ReferencedDomainName[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+40h] BYREF
  int v13; // [rsp+94h] [rbp+44h]
  DWORD cbSid; // [rsp+98h] [rbp+48h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A0h] [rbp+50h] BYREF
  void *v16; // [rsp+A8h] [rbp+58h] BYREF

  v13 = HIDWORD(a1);
  *a4 = 0;
  *a3 = SidTypeUnknown;
  Error = 0;
  ReferencedDomainName[1] = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  LookupAccountNameW(0, a2, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
  if ( !cbSid || !cchReferencedDomainName )
  {
    Error = -2147024894;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"GetSidForAccount",
        cbSid,
        cchReferencedDomainName);
  }
  v8 = 0;
  v16 = 0;
  if ( Error >= 0 )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&v16, cbSid) )
    {
      Error = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"GetSidForAccount",
          cbSid);
    }
    v8 = v16;
  }
  ReferencedDomainName[0] = 0;
  if ( Error >= 0 )
  {
    if ( (unsigned __int8)ATL::CAutoVectorPtr<unsigned short>::Allocate(ReferencedDomainName, cchReferencedDomainName) )
    {
      if ( LookupAccountNameW(0, a2, v8, &cbSid, ReferencedDomainName[0], &cchReferencedDomainName, &peUse) )
        goto LABEL_22;
      Error = HResultFromLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"GetSidForAccount",
          Error);
      if ( Error >= 0 )
      {
LABEL_22:
        v9 = v8;
        v8 = 0;
        v16 = 0;
        *a4 = v9;
        *a3 = peUse;
      }
    }
    else
    {
      Error = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"GetSidForAccount",
          cchReferencedDomainName);
    }
  }
  operator delete[](ReferencedDomainName[0]);
  ReferencedDomainName[0] = 0;
  operator delete[](v8);
  v16 = 0;
  operator delete[](0);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180009b10  mov     r11, rsp
0x180009b13  mov     [r11+8], rcx
0x180009b17  push    rbp
0x180009b18  push    rbx
0x180009b19  push    rsi
0x180009b1a  push    rdi
0x180009b1b  push    r13
0x180009b1d  push    r14
0x180009b1f  push    r15
0x180009b21  mov     rbp, rsp
0x180009b24  sub     rsp, 50h
0x180009b28  mov     rsi, r9
0x180009b2b  mov     r14, r8
0x180009b2e  mov     r15, rdx
0x180009b31  and     qword ptr [r9], 0
0x180009b35  mov     eax, 8
0x180009b3a  mov     [r8], eax
0x180009b3d  xor     edi, edi
0x180009b3f  and     [rbp+var_8], rdi
0x180009b43  and     [rbp+cbSid], edi
0x180009b46  and     [rbp+arg_0], edi
0x180009b49  mov     [rbp+arg_10], eax
0x180009b4c  lea     rax, [rbp+arg_10]
0x180009b50  mov     [r11-58h], rax
0x180009b54  lea     rax, [rbp+arg_0]
0x180009b58  mov     [r11-60h], rax
0x180009b5c  and     [r11-68h], rdi
0x180009b60  lea     r9, [rbp+cbSid]; cbSid
0x180009b64  xor     r8d, r8d; Sid
0x180009b67  xor     ecx, ecx; lpSystemName
0x180009b69  call    cs:__imp_LookupAccountNameW
0x180009b70  nop     dword ptr [rax+rax+00h]
0x180009b75  mov     r13d, 1000h
0x180009b7b  lea     rdx, WPP_GLOBAL_Control
0x180009b82  mov     eax, [rbp+arg_0]
0x180009b85  mov     r8d, [rbp+cbSid]
0x180009b89  test    r8d, r8d
0x180009b8c  jz      short loc_180009B92
0x180009b8e  test    eax, eax
0x180009b90  jnz     short loc_180009BCE
0x180009b92  mov     edi, 80070002h
0x180009b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b9e  cmp     rcx, rdx
0x180009ba1  jz      short loc_180009BCE
0x180009ba3  test    [rcx+1Ch], r13d
0x180009ba7  jz      short loc_180009BCE
0x180009ba9  mov     edx, 0Dh
0x180009bae  mov     dword ptr [rsp+50h+cchReferencedDomainName], eax
0x180009bb2  mov     dword ptr [rsp+50h+ReferencedDomainName], r8d
0x180009bb7  lea     r9, aGetsidforaccou; "GetSidForAccount"
0x180009bbe  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180009bc5  mov     rcx, [rcx+10h]
0x180009bc9  call    WPP_SF_SDD
0x180009bce  xor     ebx, ebx
0x180009bd0  mov     [rbp+arg_18], rbx
0x180009bd4  test    edi, edi
0x180009bd6  js      short loc_180009C2B
0x180009bd8  mov     edx, [rbp+cbSid]
0x180009bdb  lea     rcx, [rbp+arg_18]
0x180009bdf  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x180009be4  test    al, al
0x180009be6  jnz     short loc_180009C27
0x180009be8  mov     edi, 8007000Eh
0x180009bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bf4  lea     rax, WPP_GLOBAL_Control
0x180009bfb  cmp     rcx, rax
0x180009bfe  jz      short loc_180009C27
0x180009c00  test    [rcx+1Ch], r13d
0x180009c04  jz      short loc_180009C27
0x180009c06  lea     edx, [rbx+0Eh]
0x180009c09  mov     eax, [rbp+cbSid]
0x180009c0c  mov     dword ptr [rsp+50h+ReferencedDomainName], eax
0x180009c10  lea     r9, aGetsidforaccou; "GetSidForAccount"
0x180009c17  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180009c1e  mov     rcx, [rcx+10h]
0x180009c22  call    WPP_SF_SD
0x180009c27  mov     rbx, [rbp+arg_18]
0x180009c2b  and     [rbp+var_10], 0
0x180009c30  test    edi, edi
0x180009c32  js      loc_180009D23
0x180009c38  mov     edx, [rbp+arg_0]
0x180009c3b  lea     rcx, [rbp+var_10]
0x180009c3f  call    ?Allocate@?$CAutoVectorPtr@G@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ushort>::Allocate(unsigned __int64)
0x180009c44  test    al, al
0x180009c46  jnz     short loc_180009C96
0x180009c48  mov     edi, 8007000Eh
0x180009c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c54  lea     rax, WPP_GLOBAL_Control
0x180009c5b  cmp     rcx, rax
0x180009c5e  jz      loc_180009D23
0x180009c64  test    [rcx+1Ch], r13d
0x180009c68  jz      loc_180009D23
0x180009c6e  mov     edx, 0Fh
0x180009c73  mov     eax, [rbp+arg_0]
0x180009c76  mov     dword ptr [rsp+50h+ReferencedDomainName], eax
0x180009c7a  lea     r9, aGetsidforaccou; "GetSidForAccount"
0x180009c81  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180009c88  mov     rcx, [rcx+10h]
0x180009c8c  call    WPP_SF_SD
0x180009c91  jmp     loc_180009D23
0x180009c96  lea     rax, [rbp+arg_10]
0x180009c9a  mov     [rsp+50h+peUse], rax; peUse
0x180009c9f  lea     rax, [rbp+arg_0]
0x180009ca3  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180009ca8  mov     rax, [rbp+var_10]
0x180009cac  mov     [rsp+50h+ReferencedDomainName], rax; ReferencedDomainName
0x180009cb1  lea     r9, [rbp+cbSid]; cbSid
0x180009cb5  mov     r8, rbx; Sid
0x180009cb8  mov     rdx, r15; lpAccountName
0x180009cbb  xor     ecx, ecx; lpSystemName
0x180009cbd  call    cs:__imp_LookupAccountNameW
0x180009cc4  nop     dword ptr [rax+rax+00h]
0x180009cc9  test    eax, eax
0x180009ccb  jnz     short loc_180009D11
0x180009ccd  call    ?HResultFromLastError@@YAJXZ; HResultFromLastError(void)
0x180009cd2  mov     edi, eax
0x180009cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cdb  lea     rax, WPP_GLOBAL_Control
0x180009ce2  cmp     rcx, rax
0x180009ce5  jz      short loc_180009D0D
0x180009ce7  test    [rcx+1Ch], r13d
0x180009ceb  jz      short loc_180009D0D
0x180009ced  mov     edx, 10h
0x180009cf2  mov     dword ptr [rsp+50h+ReferencedDomainName], edi
0x180009cf6  lea     r9, aGetsidforaccou; "GetSidForAccount"
0x180009cfd  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180009d04  mov     rcx, [rcx+10h]
0x180009d08  call    WPP_SF_SD
0x180009d0d  test    edi, edi
0x180009d0f  js      short loc_180009D23
0x180009d11  mov     rax, rbx
0x180009d14  xor     ebx, ebx
0x180009d16  mov     [rbp+arg_18], rbx
0x180009d1a  mov     [rsi], rax
0x180009d1d  mov     eax, [rbp+arg_10]
0x180009d20  mov     [r14], eax
0x180009d23  mov     rcx, [rbp+var_10]
0x180009d27  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009d2e  nop     dword ptr [rax+rax+00h]
0x180009d33  and     [rbp+var_10], 0
0x180009d38  mov     rcx, rbx
0x180009d3b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009d42  nop     dword ptr [rax+rax+00h]
0x180009d47  and     [rbp+arg_18], 0
0x180009d4c  xor     ecx, ecx
0x180009d4e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009d55  nop     dword ptr [rax+rax+00h]
0x180009d5a  and     [rbp+var_8], 0
0x180009d5f  mov     eax, edi
0x180009d61  add     rsp, 50h
0x180009d65  pop     r15
0x180009d67  pop     r14
0x180009d69  pop     r13
0x180009d6b  pop     rdi
0x180009d6c  pop     rsi
0x180009d6d  pop     rbx
0x180009d6e  pop     rbp
0x180009d6f  retn
```
