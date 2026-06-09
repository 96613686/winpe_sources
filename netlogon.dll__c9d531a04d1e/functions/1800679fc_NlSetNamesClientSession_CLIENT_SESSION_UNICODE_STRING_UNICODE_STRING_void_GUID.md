# NlSetNamesClientSession(_CLIENT_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *)

- ea: `0x1800679fc`
- end: `0x180067de8`
- name: `?NlSetNamesClientSession@@YAHPEAU_CLIENT_SESSION@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *Src, struct _GUID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180063f6c`
- `0x18006a694`
- `0x18007070c`

## callees

- `0x180003170`
- `0x180003670`
- `0x180007278`
- `0x18000ba1c`
- `0x18000d710`
- `0x18000e270`
- `0x18003e208`
- `0x18003e294`
- `0x18003e71c`
- `0x1800679fc`
- `0x180083180`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180067ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180067ce3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180067cc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180067cc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067cb5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067cb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067aba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067a95`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180067d4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180067d4a`
- `ntdll!RtlEqualDomainName` at `0x180067af7`
- `ntdll!RtlEqualDomainName` at `0x180067af7`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x180067b75`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x180067b75`
- `ntdll!RtlEqualSid` at `0x180067a84`
- `ntdll!RtlEqualSid` at `0x180067a84`
- `ntdll!RtlInitUnicodeString` at `0x180067d62`
- `ntdll!RtlInitUnicodeString` at `0x180067d62`
- `ntdll!RtlLengthSid` at `0x180067aae`
- `ntdll!RtlLengthSid` at `0x180067aae`
- `netutils!NetApiBufferFree` at `0x180067cf4`
- `netutils!NetApiBufferFree` at `0x180067cf4`

## string_xrefs

- `0x180067a3e`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`

## pseudocode

```c
_BOOL8 __fastcall NlSetNamesClientSession(
        struct _CLIENT_SESSION *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        char *Src,
        struct _GUID *a5)
{
  __int128 v9; // xmm0
  void *v10; // rcx
  SIZE_T v11; // rbp
  HLOCAL v12; // rax
  NTSTATUS v13; // eax
  __int64 v15; // rcx
  const WCHAR *v16; // rcx
  char *Utf8StrFromWStr; // rax
  _BYTE *v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rax
  char *v21; // rax
  DWORD nSize; // [rsp+30h] [rbp-78h] BYREF
  _BYTE Srca[40]; // [rsp+38h] [rbp-70h] BYREF

  nSize = 16;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      499,
      Src);
  if ( a5 )
  {
    v9 = (__int128)*a5;
    *((_QWORD *)a1 + 22) = (char *)a1 + 96;
    *((_OWORD *)a1 + 6) = v9;
  }
  if ( Src )
  {
    v10 = (void *)*((_QWORD *)a1 + 33);
    if ( v10 && !RtlEqualSid(v10, Src) )
    {
      LocalFree(*((HLOCAL *)a1 + 33));
      *((_QWORD *)a1 + 33) = 0;
    }
    if ( !*((_QWORD *)a1 + 33) )
    {
      v11 = RtlLengthSid(Src);
      v12 = LocalAlloc(0, v11);
      *((_QWORD *)a1 + 33) = v12;
      if ( !v12 )
        return 0;
      memcpy_0(v12, Src, (unsigned int)v11);
    }
  }
  if ( !a2 )
    goto LABEL_26;
  if ( *((_WORD *)a1 + 56) )
  {
    if ( !RtlEqualDomainName((PUNICODE_STRING)a1 + 7, a2) )
    {
      if ( *((_QWORD *)a1 + 23) == *((_QWORD *)a1 + 15) )
        *((_QWORD *)a1 + 23) = 0;
      NlFreeUnicodeString((struct _UNICODE_STRING *)a1 + 7);
      *((_DWORD *)a1 + 36) = 0;
      *((_BYTE *)a1 + 128) = 0;
    }
    if ( *((_WORD *)a1 + 56) )
      goto LABEL_26;
  }
  if ( !NlDuplicateUnicodeString(a2, (struct _UNICODE_STRING *)a1 + 7) )
    return 0;
  if ( !*((_QWORD *)a1 + 23) )
    *((_QWORD *)a1 + 23) = *((_QWORD *)a1 + 15);
  v13 = RtlUpcaseUnicodeToOemN((PCHAR)a1 + 128, 0xFu, (PULONG)a1 + 36, a2->Buffer, a2->Length);
  if ( v13 < 0 )
  {
    NlPrintRoutine(0x100u, L"%ws: Unable to convert Domain name to OEM 0x%lx\n", a2->Buffer, (unsigned int)v13);
    return 0;
  }
  *((_BYTE *)a1 + *((unsigned int *)a1 + 36) + 128) = 0;
LABEL_26:
  if ( a3 )
  {
    if ( !*((_WORD *)a1 + 76) )
      goto LABEL_34;
    if ( !(unsigned int)NlEqualDnsNameU((struct _UNICODE_STRING *)((char *)a1 + 152), a3) )
    {
      if ( *((_QWORD *)a1 + 23) == *((_QWORD *)a1 + 20) )
        *((_QWORD *)a1 + 23) = 0;
      NlFreeUnicodeString((struct _UNICODE_STRING *)((char *)a1 + 152));
      v15 = *((_QWORD *)a1 + 21);
      if ( v15 )
      {
        NetpMemoryFree(v15);
        *((_QWORD *)a1 + 21) = 0;
      }
    }
    if ( !*((_WORD *)a1 + 76) )
    {
LABEL_34:
      if ( !NlDuplicateUnicodeString(a3, (struct _UNICODE_STRING *)((char *)a1 + 152)) )
        return 0;
      if ( !*((_QWORD *)a1 + 23) )
        *((_QWORD *)a1 + 23) = *((_QWORD *)a1 + 20);
      v16 = (const WCHAR *)*((_QWORD *)a1 + 20);
      if ( v16 )
      {
        Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(v16, 0, 0);
        *((_QWORD *)a1 + 21) = Utf8StrFromWStr;
        if ( !Utf8StrFromWStr )
          return 0;
      }
      else
      {
        *((_QWORD *)a1 + 21) = 0;
      }
    }
  }
  if ( (*((_BYTE *)a1 + 292) & 0x10) == 0 )
    return 1;
  if ( *((_DWORD *)a1 + 70) != 2 )
  {
    if ( *((_DWORD *)a1 + 70) == 3 )
    {
      v18 = *(_BYTE **)(*((_QWORD *)a1 + 34) + 144LL);
      if ( !v18 )
      {
        NlPrintCsRoutine(0x100u, a1, L"NlSetNameClientSession: NT 5 DNS trust with no DnsDomainName.\n");
        return 0;
      }
      goto LABEL_46;
    }
    if ( *((_DWORD *)a1 + 70) != 4 && (unsigned int)(*((_DWORD *)a1 + 70) - 6) > 1 )
      return 0;
  }
  _o_wcscpy_s(Srca, 17);
  _o_wcscat_s(Srca, 17, L"$");
  v18 = Srca;
LABEL_46:
  v19 = *((_QWORD *)a1 + 25);
  if ( v19 )
  {
    if ( (unsigned int)_o__wcsicmp(v19) )
    {
      NetApiBufferFree(*((LPVOID *)a1 + 25));
      *((_QWORD *)a1 + 25) = 0;
    }
  }
  if ( *((_QWORD *)a1 + 25) )
    return 1;
  v20 = NetpAllocWStrFromWStr(v18);
  *((_QWORD *)a1 + 25) = v20;
  if ( !v20 )
    return 0;
  if ( (*((_DWORD *)a1 + 73) & 0x40000) == 0 )
    return 1;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, (LPWSTR)a1 + 112, &nSize) )
    return 0;
  RtlInitUnicodeString((PUNICODE_STRING)a1 + 13, (PCWSTR)a1 + 112);
  v21 = NetpCreateUtf8StrFromWStr((LPCWCH)a1 + 112, 0, 0);
  *((_QWORD *)a1 + 32) = v21;
  return v21 != 0;
}

```

## disassembly

```asm
0x1800679fc  push    rbx
0x1800679fe  push    rbp
0x1800679ff  push    rsi
0x180067a00  push    rdi
0x180067a01  push    r14
0x180067a03  push    r15
0x180067a05  sub     rsp, 78h
0x180067a09  mov     rax, cs:__security_cookie
0x180067a10  xor     rax, rsp
0x180067a13  mov     [rsp+0A8h+var_48], rax
0x180067a18  xor     r15d, r15d
0x180067a1b  mov     [rsp+0A8h+nSize], 10h
0x180067a23  mov     rdi, r9
0x180067a26  mov     r14, r8
0x180067a29  mov     rsi, rdx
0x180067a2c  mov     rbx, rcx
0x180067a2f  cmp     [rcx+148h], r15d
0x180067a36  ja      short loc_180067A51
0x180067a38  mov     r8d, 1F3h; unsigned int
0x180067a3e  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180067a45  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180067a4c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067a51  mov     rcx, [rsp+0A8h+arg_20]
0x180067a59  test    rcx, rcx
0x180067a5c  jz      short loc_180067A70
0x180067a5e  movups  xmm0, xmmword ptr [rcx]
0x180067a61  lea     rax, [rbx+60h]
0x180067a65  mov     [rbx+0B0h], rax
0x180067a6c  movdqu  xmmword ptr [rax], xmm0
0x180067a70  test    rdi, rdi
0x180067a73  jz      short loc_180067ADE
0x180067a75  mov     rcx, [rbx+108h]; Sid1
0x180067a7c  test    rcx, rcx
0x180067a7f  jz      short loc_180067AA2
0x180067a81  mov     rdx, rdi; Sid2
0x180067a84  call    cs:__imp_RtlEqualSid
0x180067a8a  test    al, al
0x180067a8c  jnz     short loc_180067AA2
0x180067a8e  mov     rcx, [rbx+108h]; hMem
0x180067a95  call    cs:__imp_LocalFree
0x180067a9b  mov     [rbx+108h], r15
0x180067aa2  cmp     [rbx+108h], r15
0x180067aa9  jnz     short loc_180067ADE
0x180067aab  mov     rcx, rdi; Sid
0x180067aae  call    cs:__imp_RtlLengthSid
0x180067ab4  mov     edx, eax; uBytes
0x180067ab6  xor     ecx, ecx; uFlags
0x180067ab8  mov     ebp, eax
0x180067aba  call    cs:__imp_LocalAlloc
0x180067ac0  mov     [rbx+108h], rax
0x180067ac7  test    rax, rax
0x180067aca  jz      loc_180067B97
0x180067ad0  mov     r8d, ebp; Size
0x180067ad3  mov     rdx, rdi; Src
0x180067ad6  mov     rcx, rax; void *
0x180067ad9  call    memcpy_0
0x180067ade  test    rsi, rsi
0x180067ae1  jz      loc_180067BA8
0x180067ae7  lea     rdi, [rbx+70h]
0x180067aeb  cmp     [rdi], r15w
0x180067aef  jz      short loc_180067B31
0x180067af1  mov     rdx, rsi; DomainName2
0x180067af4  mov     rcx, rdi; DomainName1
0x180067af7  call    cs:__imp_RtlEqualDomainName
0x180067afd  test    al, al
0x180067aff  jnz     short loc_180067B2B
0x180067b01  mov     rax, [rbx+78h]
0x180067b05  cmp     [rbx+0B8h], rax
0x180067b0c  jnz     short loc_180067B15
0x180067b0e  mov     [rbx+0B8h], r15
0x180067b15  mov     rcx, rdi; struct _UNICODE_STRING *
0x180067b18  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x180067b1d  mov     [rbx+90h], r15d
0x180067b24  mov     [rbx+80h], r15b
0x180067b2b  cmp     [rdi], r15w
0x180067b2f  jnz     short loc_180067BA8
0x180067b31  mov     rdx, rdi; struct _UNICODE_STRING *
0x180067b34  mov     rcx, rsi; struct _UNICODE_STRING *
0x180067b37  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180067b3c  test    al, al
0x180067b3e  jz      short loc_180067B97
0x180067b40  cmp     [rbx+0B8h], r15
0x180067b47  jnz     short loc_180067B54
0x180067b49  mov     rax, [rbx+78h]
0x180067b4d  mov     [rbx+0B8h], rax
0x180067b54  movzx   eax, word ptr [rsi]
0x180067b57  lea     rdi, [rbx+90h]
0x180067b5e  mov     r9, [rsi+8]; UnicodeString
0x180067b62  lea     rcx, [rbx+80h]; OemString
0x180067b69  mov     r8, rdi; ResultSize
0x180067b6c  mov     [rsp+0A8h+UnicodeSize], eax; UnicodeSize
0x180067b70  mov     edx, 0Fh; OemSize
0x180067b75  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x180067b7b  test    eax, eax
0x180067b7d  jns     short loc_180067B9E
0x180067b7f  mov     r8, [rsi+8]
0x180067b83  lea     rdx, aWsUnableToConv; "%ws: Unable to convert Domain name to O"...
0x180067b8a  mov     r9d, eax
0x180067b8d  mov     ecx, 100h; unsigned int
0x180067b92  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067b97  xor     eax, eax
0x180067b99  jmp     loc_180067DCE
0x180067b9e  mov     eax, [rdi]
0x180067ba0  mov     [rax+rbx+80h], r15b
0x180067ba8  test    r14, r14
0x180067bab  jz      loc_180067C63
0x180067bb1  lea     rdi, [rbx+98h]
0x180067bb8  cmp     [rdi], r15w
0x180067bbc  jz      short loc_180067C0A
0x180067bbe  mov     rdx, r14; struct _UNICODE_STRING *
0x180067bc1  mov     rcx, rdi; struct _UNICODE_STRING *
0x180067bc4  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x180067bc9  test    eax, eax
0x180067bcb  jnz     short loc_180067C04
0x180067bcd  mov     rax, [rbx+0A0h]
0x180067bd4  cmp     [rbx+0B8h], rax
0x180067bdb  jnz     short loc_180067BE4
0x180067bdd  mov     [rbx+0B8h], r15
0x180067be4  mov     rcx, rdi; struct _UNICODE_STRING *
0x180067be7  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x180067bec  mov     rcx, [rbx+0A8h]
0x180067bf3  test    rcx, rcx
0x180067bf6  jz      short loc_180067C04
0x180067bf8  call    NetpMemoryFree
0x180067bfd  mov     [rbx+0A8h], r15
0x180067c04  cmp     [rdi], r15w
0x180067c08  jnz     short loc_180067C63
0x180067c0a  mov     rdx, rdi; struct _UNICODE_STRING *
0x180067c0d  mov     rcx, r14; struct _UNICODE_STRING *
0x180067c10  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180067c15  test    al, al
0x180067c17  jz      loc_180067B97
0x180067c1d  cmp     [rbx+0B8h], r15
0x180067c24  jnz     short loc_180067C34
0x180067c26  mov     rax, [rbx+0A0h]
0x180067c2d  mov     [rbx+0B8h], rax
0x180067c34  mov     rcx, [rbx+0A0h]; lpWideCharStr
0x180067c3b  test    rcx, rcx
0x180067c3e  jnz     short loc_180067C49
0x180067c40  mov     [rbx+0A8h], r15
0x180067c47  jmp     short loc_180067C63
0x180067c49  xor     r8d, r8d; int
0x180067c4c  xor     edx, edx; lpMultiByteStr
0x180067c4e  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180067c53  mov     [rbx+0A8h], rax
0x180067c5a  test    rax, rax
0x180067c5d  jz      loc_180067B97
0x180067c63  test    byte ptr [rbx+124h], 10h
0x180067c6a  jz      loc_180067DC9
0x180067c70  mov     ecx, [rbx+118h]
0x180067c76  sub     ecx, 2
0x180067c79  jz      short loc_180067C9B
0x180067c7b  sub     ecx, 1
0x180067c7e  jz      loc_180067D99
0x180067c84  sub     ecx, 1
0x180067c87  jz      loc_180067D89
0x180067c8d  sub     ecx, 2
0x180067c90  jz      short loc_180067C9B
0x180067c92  cmp     ecx, 1
0x180067c95  jnz     loc_180067B97
0x180067c9b  mov     r8, [rbx+110h]
0x180067ca2  mov     r8, [r8+108h]
0x180067ca9  mov     edi, 11h
0x180067cae  lea     rcx, [rsp+0A8h+Src]
0x180067cb3  mov     edx, edi
0x180067cb5  call    cs:__imp__o_wcscpy_s
0x180067cbb  lea     r8, asc_1800A5A84; "$"
0x180067cc2  mov     edx, edi
0x180067cc4  lea     rcx, [rsp+0A8h+Src]
0x180067cc9  call    cs:__imp__o_wcscat_s
0x180067ccf  lea     rdi, [rsp+0A8h+Src]
0x180067cd4  mov     rcx, [rbx+0C8h]
0x180067cdb  test    rcx, rcx
0x180067cde  jz      short loc_180067D01
0x180067ce0  mov     rdx, rdi
0x180067ce3  call    cs:__imp__o__wcsicmp
0x180067ce9  test    eax, eax
0x180067ceb  jz      short loc_180067D01
0x180067ced  mov     rcx, [rbx+0C8h]; Buffer
0x180067cf4  call    cs:__imp_NetApiBufferFree
0x180067cfa  mov     [rbx+0C8h], r15
0x180067d01  cmp     [rbx+0C8h], r15
0x180067d08  jnz     loc_180067DC9
0x180067d0e  mov     rcx, rdi; Src
0x180067d11  call    NetpAllocWStrFromWStr
0x180067d16  mov     [rbx+0C8h], rax
0x180067d1d  test    rax, rax
0x180067d20  jz      loc_180067B97
0x180067d26  test    dword ptr [rbx+124h], 40000h
0x180067d30  jz      loc_180067DC9
0x180067d36  lea     rdi, [rbx+0E0h]
0x180067d3d  mov     ecx, 4; NameType
0x180067d42  mov     rdx, rdi; lpBuffer
0x180067d45  lea     r8, [rsp+0A8h+nSize]; nSize
0x180067d4a  call    cs:__imp_GetComputerNameExW
0x180067d50  test    eax, eax
0x180067d52  jz      loc_180067B97
0x180067d58  lea     rcx, [rbx+0D0h]; DestinationString
0x180067d5f  mov     rdx, rdi; SourceString
0x180067d62  call    cs:__imp_RtlInitUnicodeString
0x180067d68  xor     r8d, r8d; int
0x180067d6b  xor     edx, edx; lpMultiByteStr
0x180067d6d  mov     rcx, rdi; lpWideCharStr
0x180067d70  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180067d75  test    rax, rax
0x180067d78  mov     [rbx+100h], rax
0x180067d7f  mov     ecx, r15d
0x180067d82  setnz   cl
0x180067d85  mov     eax, ecx
0x180067d87  jmp     short loc_180067DCE
0x180067d89  mov     r8, [rbx+110h]
0x180067d90  add     r8, 48h ; 'H'
0x180067d94  jmp     loc_180067CA9
0x180067d99  mov     rax, [rbx+110h]
0x180067da0  mov     rdi, [rax+90h]
0x180067da7  test    rdi, rdi
0x180067daa  jnz     loc_180067CD4
0x180067db0  lea     r8, aNlsetnameclien; "NlSetNameClientSession: NT 5 DNS trust "...
0x180067db7  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180067dba  mov     ecx, 100h; unsigned int
0x180067dbf  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180067dc4  jmp     loc_180067B97
0x180067dc9  mov     eax, 1
0x180067dce  mov     rcx, [rsp+0A8h+var_48]
0x180067dd3  xor     rcx, rsp; StackCookie
0x180067dd6  call    __security_check_cookie
0x180067ddb  add     rsp, 78h
0x180067ddf  pop     r15
0x180067de1  pop     r14
0x180067de3  pop     rdi
0x180067de4  pop     rsi
0x180067de5  pop     rbp
0x180067de6  pop     rbx
0x180067de7  retn
```
