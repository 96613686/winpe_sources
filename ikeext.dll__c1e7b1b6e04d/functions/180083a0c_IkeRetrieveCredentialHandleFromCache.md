# IkeRetrieveCredentialHandleFromCache

- ea: `0x180083a0c`
- end: `0x180083fc9`
- name: `IkeRetrieveCredentialHandleFromCache`
- size: `1469`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18002f9e4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d594`
- `0x18004d60c`
- `0x180050850`
- `0x18005bc40`
- `0x18007dde4`
- `0x18008081c`
- `0x180080d3c`
- `0x180083a0c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180083d25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180083d25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083c1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083c1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083a71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083a71`

## string_xrefs

- `0x180083af8`: `Looking for credentials in cache`
- `0x180083a3e`: `IkeRetrieveCredentialHandleFromCache`
- `0x180083c26`: `IkeRetrieveCredentialHandleFromCache`
- `0x180083c32`: `IkeRetrieveCredentialHandleFromCache`
- `0x180083ce2`: `Found credentials in the cache, logging cache entry`
- `0x180083be5`: `Did not find credentials in the cache`
- `0x180083ea5`: `Cached entry credentials are expired, removing`
- `0x180083dcf`: `Cached entry is expired, removing`
- `0x180083f2b`: `Moving cached entry to front`

## pseudocode

```c
__int64 __fastcall IkeRetrieveCredentialHandleFromCache(unsigned int a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v12; // rcx
  int TlsMmLuid; // eax
  __int64 v14; // rcx
  const WCHAR *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 CredCacheEntry; // r15
  __int64 v20; // rsi
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  const WCHAR *v26; // rax
  __int64 v27; // r8
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  const WCHAR *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  const WCHAR *v43; // rax
  __int64 v44; // r8
  __int64 v45; // r9
  char *v46; // rdx
  const char *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rdi
  __int64 v50; // rbx
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rcx
  const WCHAR *v54; // rax
  __int64 v55; // rdi
  __int64 v56; // rbx
  __int64 v57; // rcx
  int v58; // eax
  __int64 v59; // rcx
  const WCHAR *v60; // rax
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rax
  _QWORD *v64; // rcx
  _QWORD *p_OwningThread; // rax
  LPCRITICAL_SECTION *OwningThread; // rcx
  __int64 v67; // [rsp+30h] [rbp-69h] BYREF
  __int64 v68; // [rsp+38h] [rbp-61h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v70[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v71; // [rsp+70h] [rbp-29h]
  __int64 v72; // [rsp+78h] [rbp-21h]
  _BYTE v73[16]; // [rsp+80h] [rbp-19h] BYREF
  const char *v74; // [rsp+90h] [rbp-9h]
  __int64 v75; // [rsp+98h] [rbp-1h]

  v67 = 0;
  SystemTimeAsFileTime = 0;
  TraceLogHelper("IkeRetrieveCredentialHandleFromCache", 1);
  *a4 = 0;
  v8 = *(_QWORD *)(*(_QWORD *)(a3 + 104) + 56LL);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3488));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v9);
    TlsMmLuid = IkeGetTlsMmLuid(v12);
    WPP_SF_iS(v10, 82, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v68 = IkeGetTlsMmLuid(v9);
    v71 = &v68;
    v72 = 8;
    v15 = (const WCHAR *)IkeGetTlsPeerAddr(v14);
    tlgCreate1Sz_wchar_t((__int64)v73, v15);
    v75 = 33;
    v74 = "Looking for credentials in cache";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_180154C59,
      v16,
      v17,
      5,
      (__int64)v70);
  }
  CredCacheEntry = IkeGetCredCacheEntry(a1, *(unsigned int *)(a2 + 72), v8, &v67);
  if ( !CredCacheEntry )
  {
    v20 = v67;
    if ( !v67 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v22 = IkeGetTlsPeerAddr(v18);
        v24 = IkeGetTlsMmLuid(v23);
        WPP_SF_iS(v21, 83, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v24, v22);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v68 = IkeGetTlsMmLuid(v18);
        v71 = &v68;
        v72 = 8;
        v26 = (const WCHAR *)IkeGetTlsPeerAddr(v25);
        tlgCreate1Sz_wchar_t((__int64)v73, v26);
        v75 = 38;
        v74 = "Did not find credentials in the cache";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)byte_180154C1B,
          v27,
          (__int64)"Did not find credentials in the cache",
          5,
          (__int64)v70);
      }
      goto LABEL_15;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v29 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v30 = IkeGetTlsPeerAddr(v18);
      v32 = IkeGetTlsMmLuid(v31);
      WPP_SF_iS(v29, 84, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v32, v30);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v68 = IkeGetTlsMmLuid(v18);
      v71 = &v68;
      v72 = 8;
      v34 = (const WCHAR *)IkeGetTlsPeerAddr(v33);
      tlgCreate1Sz_wchar_t((__int64)v73, v34);
      v75 = 52;
      v74 = "Found credentials in the cache, logging cache entry";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_180154B61,
        v35,
        v36,
        5,
        (__int64)v70);
    }
    IkeLogCredCacheEntry(v20);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v37 = 72000000000LL;
    if ( *(unsigned __int64 *)&SystemTimeAsFileTime > *(_QWORD *)(v20 + 56) + 72000000000LL )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v38 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v39 = IkeGetTlsPeerAddr(72000000000LL);
        v41 = IkeGetTlsMmLuid(v40);
        WPP_SF_iS(v38, 85, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v41, v39);
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_30;
      v68 = IkeGetTlsMmLuid(v37);
      v71 = &v68;
      v72 = 8;
      v43 = (const WCHAR *)IkeGetTlsPeerAddr(v42);
      tlgCreate1Sz_wchar_t((__int64)v73, v43);
      v46 = byte_180154B23;
      v75 = 34;
      v47 = "Cached entry is expired, removing";
LABEL_29:
      v74 = v47;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)v46,
        v44,
        v45,
        5,
        (__int64)v70);
LABEL_30:
      IkeRemoveCredCacheEntry(v20);
      IkeDerefCacheEntry(v20);
      goto LABEL_15;
    }
    if ( (unsigned int)IkeIsCachedCredExpired(v20) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v49 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v50 = IkeGetTlsPeerAddr(v48);
        v52 = IkeGetTlsMmLuid(v51);
        WPP_SF_iS(v49, 86, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v52, v50);
      }
      if ( (unsigned int)dword_180173278 <= 4 )
        goto LABEL_30;
      v68 = IkeGetTlsMmLuid(v48);
      v71 = &v68;
      v72 = 8;
      v54 = (const WCHAR *)IkeGetTlsPeerAddr(v53);
      tlgCreate1Sz_wchar_t((__int64)v73, v54);
      v46 = byte_180154BDD;
      v75 = 47;
      v47 = "Cached entry credentials are expired, removing";
      goto LABEL_29;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v55 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v56 = IkeGetTlsPeerAddr(v48);
      v58 = IkeGetTlsMmLuid(v57);
      WPP_SF_iS(v55, 87, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v58, v56);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v68 = IkeGetTlsMmLuid(v48);
      v71 = &v68;
      v72 = 8;
      v60 = (const WCHAR *)IkeGetTlsPeerAddr(v59);
      tlgCreate1Sz_wchar_t((__int64)v73, v60);
      v75 = 29;
      v74 = "Moving cached entry to front";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&byte_180154B9F,
        v61,
        v62,
        5,
        (__int64)v70);
    }
    v63 = *(_QWORD *)v20;
    if ( *(_QWORD *)(*(_QWORD *)v20 + 8LL) != v20
      || (v64 = *(_QWORD **)(v20 + 8), *v64 != v20)
      || (*v64 = v63,
          *(_QWORD *)(v63 + 8) = v64,
          p_OwningThread = &gIkeExtGlobals[88].OwningThread,
          OwningThread = (LPCRITICAL_SECTION *)gIkeExtGlobals[88].OwningThread,
          OwningThread[1] != (LPCRITICAL_SECTION)&gIkeExtGlobals[88].OwningThread) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)v20 = OwningThread;
    *(_QWORD *)(v20 + 8) = p_OwningThread;
    OwningThread[1] = (LPCRITICAL_SECTION)v20;
    *p_OwningThread = v20;
    *(_OWORD *)(a3 + 8) = *(_OWORD *)(v20 + 72);
    *(_QWORD *)(a3 + 48) = *(_QWORD *)(v20 + 88);
    *(_QWORD *)(a3 + 112) = v20;
    *a4 = 1;
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3488));
  TraceLogHelper("IkeRetrieveCredentialHandleFromCache", 0);
  return IkeReturnError(CredCacheEntry, "IkeRetrieveCredentialHandleFromCache");
}

```

## disassembly

```asm
0x180083a0c  push    rbp
0x180083a0e  push    rbx
0x180083a0f  push    rsi
0x180083a10  push    rdi
0x180083a11  push    r12
0x180083a13  push    r13
0x180083a15  push    r14
0x180083a17  push    r15
0x180083a19  lea     rbp, [rsp-1Fh]
0x180083a1e  sub     rsp, 0B8h
0x180083a25  mov     rax, cs:__security_cookie
0x180083a2c  xor     rax, rsp
0x180083a2f  mov     [rbp+57h+var_50], rax
0x180083a33  xor     ebx, ebx
0x180083a35  mov     r15, rdx
0x180083a38  mov     esi, ecx
0x180083a3a  mov     [rbp+57h+var_C0], rbx
0x180083a3e  lea     rcx, aIkeretrievecre; "IkeRetrieveCredentialHandleFromCache"
0x180083a45  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180083a49  mov     r13, r9
0x180083a4c  mov     r14, r8
0x180083a4f  lea     edx, [rbx+1]
0x180083a52  call    TraceLogHelper
0x180083a57  mov     [r13+0], ebx
0x180083a5b  mov     rax, [r14+68h]
0x180083a5f  mov     rcx, cs:gIkeExtGlobals
0x180083a66  add     rcx, 0DA0h; lpCriticalSection
0x180083a6d  mov     r12, [rax+38h]
0x180083a71  call    cs:__imp_EnterCriticalSection
0x180083a77  mov     rdi, cs:WPP_GLOBAL_Control
0x180083a7e  lea     rax, WPP_GLOBAL_Control
0x180083a85  cmp     rdi, rax
0x180083a88  jz      short loc_180083AC3
0x180083a8a  cmp     byte ptr [rdi+19h], 4
0x180083a8e  jb      short loc_180083AC3
0x180083a90  test    byte ptr [rdi+1Ch], 10h
0x180083a94  jz      short loc_180083AC3
0x180083a96  mov     rdi, [rdi+10h]
0x180083a9a  call    IkeGetTlsPeerAddr
0x180083a9f  mov     rbx, rax
0x180083aa2  call    IkeGetTlsMmLuid
0x180083aa7  mov     r9, rax
0x180083aaa  mov     [rsp+0F0h+var_D0], rbx
0x180083aaf  mov     edx, 52h ; 'R'
0x180083ab4  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083abb  mov     rcx, rdi
0x180083abe  call    WPP_SF_iS
0x180083ac3  mov     eax, cs:dword_180173278
0x180083ac9  cmp     eax, 4
0x180083acc  jbe     short loc_180083B2F
0x180083ace  call    IkeGetTlsMmLuid
0x180083ad3  mov     [rbp+57h+var_B8], rax
0x180083ad7  lea     rax, [rbp+57h+var_B8]
0x180083adb  mov     [rbp+57h+var_80], rax
0x180083adf  mov     [rbp+57h+var_78], 8
0x180083ae7  call    IkeGetTlsPeerAddr
0x180083aec  mov     rdx, rax
0x180083aef  lea     rcx, [rbp+57h+var_70]
0x180083af3  call    _tlgCreate1Sz_wchar_t
0x180083af8  lea     rcx, aLookingForCred; "Looking for credentials in cache"
0x180083aff  mov     [rbp+57h+var_58], 21h ; '!'
0x180083b07  lea     rax, [rbp+57h+var_A0]
0x180083b0b  mov     [rbp+57h+var_60], rcx
0x180083b0f  mov     [rsp+0F0h+var_C8], rax
0x180083b14  lea     rcx, dword_180173278
0x180083b1b  lea     rdx, byte_180154C59
0x180083b22  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083b2a  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083b2f  mov     edx, [r15+48h]
0x180083b33  lea     r9, [rbp+57h+var_C0]
0x180083b37  mov     r8, r12
0x180083b3a  mov     ecx, esi
0x180083b3c  call    IkeGetCredCacheEntry
0x180083b41  mov     r15, rax
0x180083b44  test    rax, rax
0x180083b47  jnz     loc_180083C10
0x180083b4d  mov     rsi, [rbp+57h+var_C0]
0x180083b51  test    rsi, rsi
0x180083b54  jnz     loc_180083C61
0x180083b5a  mov     rdi, cs:WPP_GLOBAL_Control
0x180083b61  lea     rax, WPP_GLOBAL_Control
0x180083b68  cmp     rdi, rax
0x180083b6b  jz      short loc_180083BA4
0x180083b6d  cmp     byte ptr [rdi+19h], 4
0x180083b71  jb      short loc_180083BA4
0x180083b73  test    byte ptr [rdi+1Ch], 10h
0x180083b77  jz      short loc_180083BA4
0x180083b79  mov     rdi, [rdi+10h]
0x180083b7d  call    IkeGetTlsPeerAddr
0x180083b82  mov     rbx, rax
0x180083b85  call    IkeGetTlsMmLuid
0x180083b8a  mov     r9, rax
0x180083b8d  mov     [rsp+0F0h+var_D0], rbx
0x180083b92  lea     edx, [rsi+53h]
0x180083b95  mov     rcx, rdi
0x180083b98  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083b9f  call    WPP_SF_iS
0x180083ba4  mov     eax, cs:dword_180173278
0x180083baa  cmp     eax, 4
0x180083bad  jbe     short loc_180083C10
0x180083baf  call    IkeGetTlsMmLuid
0x180083bb4  mov     [rbp+57h+var_B8], rax
0x180083bb8  lea     rax, [rbp+57h+var_B8]
0x180083bbc  mov     [rbp+57h+var_80], rax
0x180083bc0  mov     [rbp+57h+var_78], 8
0x180083bc8  call    IkeGetTlsPeerAddr
0x180083bcd  mov     rdx, rax
0x180083bd0  lea     rcx, [rbp+57h+var_70]
0x180083bd4  call    _tlgCreate1Sz_wchar_t
0x180083bd9  lea     rax, [rbp+57h+var_A0]
0x180083bdd  mov     [rbp+57h+var_58], 26h ; '&'
0x180083be5  lea     r9, aDidNotFindCred; "Did not find credentials in the cache"
0x180083bec  mov     [rsp+0F0h+var_C8], rax
0x180083bf1  lea     rdx, byte_180154C1B
0x180083bf8  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083c00  lea     rcx, dword_180173278
0x180083c07  mov     [rbp+57h+var_60], r9
0x180083c0b  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083c10  mov     rcx, cs:gIkeExtGlobals
0x180083c17  add     rcx, 0DA0h; lpCriticalSection
0x180083c1e  call    cs:__imp_LeaveCriticalSection
0x180083c24  xor     edx, edx
0x180083c26  lea     rcx, aIkeretrievecre; "IkeRetrieveCredentialHandleFromCache"
0x180083c2d  call    TraceLogHelper
0x180083c32  lea     rdx, aIkeretrievecre; "IkeRetrieveCredentialHandleFromCache"
0x180083c39  mov     rcx, r15
0x180083c3c  call    IkeReturnError
0x180083c41  mov     rcx, [rbp+57h+var_50]
0x180083c45  xor     rcx, rsp; StackCookie
0x180083c48  call    __security_check_cookie
0x180083c4d  add     rsp, 0B8h
0x180083c54  pop     r15
0x180083c56  pop     r14
0x180083c58  pop     r13
0x180083c5a  pop     r12
0x180083c5c  pop     rdi
0x180083c5d  pop     rsi
0x180083c5e  pop     rbx
0x180083c5f  pop     rbp
0x180083c60  retn
0x180083c61  mov     rdi, cs:WPP_GLOBAL_Control
0x180083c68  lea     r12, WPP_GLOBAL_Control
0x180083c6f  cmp     rdi, r12
0x180083c72  jz      short loc_180083CAD
0x180083c74  cmp     byte ptr [rdi+19h], 4
0x180083c78  jb      short loc_180083CAD
0x180083c7a  test    byte ptr [rdi+1Ch], 10h
0x180083c7e  jz      short loc_180083CAD
0x180083c80  mov     rdi, [rdi+10h]
0x180083c84  call    IkeGetTlsPeerAddr
0x180083c89  mov     rbx, rax
0x180083c8c  call    IkeGetTlsMmLuid
0x180083c91  mov     r9, rax
0x180083c94  mov     [rsp+0F0h+var_D0], rbx
0x180083c99  mov     edx, 54h ; 'T'
0x180083c9e  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083ca5  mov     rcx, rdi
0x180083ca8  call    WPP_SF_iS
0x180083cad  mov     eax, cs:dword_180173278
0x180083cb3  cmp     eax, 4
0x180083cb6  jbe     short loc_180083D19
0x180083cb8  call    IkeGetTlsMmLuid
0x180083cbd  mov     [rbp+57h+var_B8], rax
0x180083cc1  lea     rax, [rbp+57h+var_B8]
0x180083cc5  mov     [rbp+57h+var_80], rax
0x180083cc9  mov     [rbp+57h+var_78], 8
0x180083cd1  call    IkeGetTlsPeerAddr
0x180083cd6  mov     rdx, rax
0x180083cd9  lea     rcx, [rbp+57h+var_70]
0x180083cdd  call    _tlgCreate1Sz_wchar_t
0x180083ce2  lea     rcx, aFoundCredentia; "Found credentials in the cache, logging"...
0x180083ce9  mov     [rbp+57h+var_58], 34h ; '4'
0x180083cf1  lea     rax, [rbp+57h+var_A0]
0x180083cf5  mov     [rbp+57h+var_60], rcx
0x180083cf9  mov     [rsp+0F0h+var_C8], rax
0x180083cfe  lea     rcx, dword_180173278
0x180083d05  lea     rdx, byte_180154B61
0x180083d0c  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083d14  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083d19  mov     rcx, rsi
0x180083d1c  call    IkeLogCredCacheEntry
0x180083d21  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180083d25  call    cs:__imp_GetSystemTimeAsFileTime
0x180083d2b  mov     rax, [rsi+38h]
0x180083d2f  mov     rcx, 10C388D000h
0x180083d39  add     rax, rcx
0x180083d3c  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180083d40  jbe     loc_180083E0C
0x180083d46  mov     rdi, cs:WPP_GLOBAL_Control
0x180083d4d  cmp     rdi, r12
0x180083d50  jz      short loc_180083D8B
0x180083d52  cmp     byte ptr [rdi+19h], 4
0x180083d56  jb      short loc_180083D8B
0x180083d58  test    byte ptr [rdi+1Ch], 10h
0x180083d5c  jz      short loc_180083D8B
0x180083d5e  mov     rdi, [rdi+10h]
0x180083d62  call    IkeGetTlsPeerAddr
0x180083d67  mov     rbx, rax
0x180083d6a  call    IkeGetTlsMmLuid
0x180083d6f  mov     r9, rax
0x180083d72  mov     [rsp+0F0h+var_D0], rbx
0x180083d77  mov     edx, 55h ; 'U'
0x180083d7c  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083d83  mov     rcx, rdi
0x180083d86  call    WPP_SF_iS
0x180083d8b  mov     eax, cs:dword_180173278
0x180083d91  cmp     eax, 4
0x180083d94  jbe     short loc_180083DF7
0x180083d96  call    IkeGetTlsMmLuid
0x180083d9b  mov     [rbp+57h+var_B8], rax
0x180083d9f  lea     rax, [rbp+57h+var_B8]
0x180083da3  mov     [rbp+57h+var_80], rax
0x180083da7  mov     [rbp+57h+var_78], 8
0x180083daf  call    IkeGetTlsPeerAddr
0x180083db4  mov     rdx, rax
0x180083db7  lea     rcx, [rbp+57h+var_70]
0x180083dbb  call    _tlgCreate1Sz_wchar_t
0x180083dc0  lea     rdx, byte_180154B23
0x180083dc7  mov     [rbp+57h+var_58], 22h ; '"'
0x180083dcf  lea     rcx, aCachedEntryIsE; "Cached entry is expired, removing"
0x180083dd6  lea     rax, [rbp+57h+var_A0]
0x180083dda  mov     [rbp+57h+var_60], rcx
0x180083dde  mov     [rsp+0F0h+var_C8], rax
0x180083de3  lea     rcx, dword_180173278
0x180083dea  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180083df2  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083df7  mov     rcx, rsi
0x180083dfa  call    IkeRemoveCredCacheEntry
0x180083dff  mov     rcx, rsi
0x180083e02  call    IkeDerefCacheEntry
0x180083e07  jmp     loc_180083C10
0x180083e0c  mov     rcx, rsi
0x180083e0f  call    IkeIsCachedCredExpired
0x180083e14  test    eax, eax
0x180083e16  jz      loc_180083EB1
0x180083e1c  mov     rdi, cs:WPP_GLOBAL_Control
0x180083e23  cmp     rdi, r12
0x180083e26  jz      short loc_180083E61
0x180083e28  cmp     byte ptr [rdi+19h], 4
0x180083e2c  jb      short loc_180083E61
0x180083e2e  test    byte ptr [rdi+1Ch], 10h
0x180083e32  jz      short loc_180083E61
0x180083e34  mov     rdi, [rdi+10h]
0x180083e38  call    IkeGetTlsPeerAddr
0x180083e3d  mov     rbx, rax
0x180083e40  call    IkeGetTlsMmLuid
0x180083e45  mov     r9, rax
0x180083e48  mov     [rsp+0F0h+var_D0], rbx
0x180083e4d  mov     edx, 56h ; 'V'
0x180083e52  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083e59  mov     rcx, rdi
0x180083e5c  call    WPP_SF_iS
0x180083e61  mov     eax, cs:dword_180173278
0x180083e67  cmp     eax, 4
0x180083e6a  jbe     short loc_180083DF7
0x180083e6c  call    IkeGetTlsMmLuid
0x180083e71  mov     [rbp+57h+var_B8], rax
0x180083e75  lea     rax, [rbp+57h+var_B8]
0x180083e79  mov     [rbp+57h+var_80], rax
0x180083e7d  mov     [rbp+57h+var_78], 8
0x180083e85  call    IkeGetTlsPeerAddr
0x180083e8a  mov     rdx, rax
0x180083e8d  lea     rcx, [rbp+57h+var_70]
0x180083e91  call    _tlgCreate1Sz_wchar_t
0x180083e96  lea     rdx, byte_180154BDD
0x180083e9d  mov     [rbp+57h+var_58], 2Fh ; '/'
0x180083ea5  lea     rcx, aCachedEntryCre; "Cached entry credentials are expired, r"...
0x180083eac  jmp     loc_180083DD6
0x180083eb1  mov     rdi, cs:WPP_GLOBAL_Control
0x180083eb8  cmp     rdi, r12
0x180083ebb  jz      short loc_180083EF6
0x180083ebd  cmp     byte ptr [rdi+19h], 4
0x180083ec1  jb      short loc_180083EF6
0x180083ec3  test    byte ptr [rdi+1Ch], 10h
0x180083ec7  jz      short loc_180083EF6
0x180083ec9  mov     rdi, [rdi+10h]
0x180083ecd  call    IkeGetTlsPeerAddr
0x180083ed2  mov     rbx, rax
0x180083ed5  call    IkeGetTlsMmLuid
0x180083eda  mov     r9, rax
0x180083edd  mov     [rsp+0F0h+var_D0], rbx
0x180083ee2  mov     edx, 57h ; 'W'
0x180083ee7  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083eee  mov     rcx, rdi
0x180083ef1  call    WPP_SF_iS
0x180083ef6  mov     eax, cs:dword_180173278
0x180083efc  cmp     eax, 4
0x180083eff  jbe     short loc_180083F62
0x180083f01  call    IkeGetTlsMmLuid
0x180083f06  mov     [rbp+57h+var_B8], rax
0x180083f0a  lea     rax, [rbp+57h+var_B8]
0x180083f0e  mov     [rbp+57h+var_80], rax
0x180083f12  mov     [rbp+57h+var_78], 8
0x180083f1a  call    IkeGetTlsPeerAddr
0x180083f1f  mov     rdx, rax
0x180083f22  lea     rcx, [rbp+57h+var_70]
0x180083f26  call    _tlgCreate1Sz_wchar_t
0x180083f2b  lea     rcx, aMovingCachedEn; "Moving cached entry to front"
0x180083f32  mov     [rbp+57h+var_58], 1Dh
0x180083f3a  lea     rax, [rbp+57h+var_A0]
  ... truncated ...
```
