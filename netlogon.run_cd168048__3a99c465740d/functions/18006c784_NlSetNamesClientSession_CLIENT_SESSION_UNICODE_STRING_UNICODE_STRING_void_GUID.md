# NlSetNamesClientSession(_CLIENT_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *)

- ea: `0x18006c784`
- end: `0x18006cbbd`
- name: `?NlSetNamesClientSession@@YAHPEAU_CLIENT_SESSION@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@@Z`
- size: `1081`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *Src, struct _GUID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006891c`
- `0x18006f6b0`
- `0x180075b60`

## callees

- `0x180003250`
- `0x1800037f0`
- `0x180007518`
- `0x18000c130`
- `0x18000dd00`
- `0x18000e910`
- `0x180040928`
- `0x1800409c4`
- `0x180040f18`
- `0x18006c784`
- `0x180089328`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006ca9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006ca9f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006ca7f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006ca7f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006ca65`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006ca65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c858`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c827`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18006cb12`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18006cb12`
- `ntdll!RtlEqualDomainName` at `0x18006c89b`
- `ntdll!RtlEqualDomainName` at `0x18006c89b`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18006c91f`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18006c91f`
- `ntdll!RtlEqualSid` at `0x18006c810`
- `ntdll!RtlEqualSid` at `0x18006c810`
- `ntdll!RtlInitUnicodeString` at `0x18006cb30`
- `ntdll!RtlInitUnicodeString` at `0x18006cb30`
- `ntdll!RtlLengthSid` at `0x18006c846`
- `ntdll!RtlLengthSid` at `0x18006c846`
- `netutils!NetApiBufferFree` at `0x18006cab6`
- `netutils!NetApiBufferFree` at `0x18006cab6`

## string_xrefs

- `0x18006c7c6`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`

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
  __int64 v18; // r8
  _BYTE *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  char *v22; // rax
  DWORD nSize; // [rsp+30h] [rbp-78h] BYREF
  _BYTE Srca[40]; // [rsp+38h] [rbp-70h] BYREF

  nSize = 16;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x1F3u,
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
      v19 = *(_BYTE **)(*((_QWORD *)a1 + 34) + 144LL);
      if ( !v19 )
      {
        NlPrintCsRoutine(0x100u, a1, L"NlSetNameClientSession: NT 5 DNS trust with no DnsDomainName.\n");
        return 0;
      }
      goto LABEL_47;
    }
    if ( *((_DWORD *)a1 + 70) == 4 )
    {
      v18 = *((_QWORD *)a1 + 34) + 72LL;
      goto LABEL_46;
    }
    if ( (unsigned int)(*((_DWORD *)a1 + 70) - 6) > 1 )
      return 0;
  }
  v18 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
LABEL_46:
  _o_wcscpy_s(Srca, 17, v18);
  _o_wcscat_s(Srca, 17, L"$");
  v19 = Srca;
LABEL_47:
  v20 = *((_QWORD *)a1 + 25);
  if ( v20 )
  {
    if ( (unsigned int)_o__wcsicmp(v20, v19) )
    {
      NetApiBufferFree(*((LPVOID *)a1 + 25));
      *((_QWORD *)a1 + 25) = 0;
    }
  }
  if ( *((_QWORD *)a1 + 25) )
    return 1;
  v21 = NetpAllocWStrFromWStr(v19);
  *((_QWORD *)a1 + 25) = v21;
  if ( !v21 )
    return 0;
  if ( (*((_DWORD *)a1 + 73) & 0x40000) == 0 )
    return 1;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, (LPWSTR)a1 + 112, &nSize) )
    return 0;
  RtlInitUnicodeString((PUNICODE_STRING)a1 + 13, (PCWSTR)a1 + 112);
  v22 = NetpCreateUtf8StrFromWStr((LPCWCH)a1 + 112, 0, 0);
  *((_QWORD *)a1 + 32) = v22;
  return v22 != 0;
}

```

## disassembly

```asm
0x18006c784  push    rbx
0x18006c786  push    rbp
0x18006c787  push    rsi
0x18006c788  push    rdi
0x18006c789  push    r14
0x18006c78b  push    r15
0x18006c78d  sub     rsp, 78h
0x18006c791  mov     rax, cs:__security_cookie
0x18006c798  xor     rax, rsp
0x18006c79b  mov     [rsp+0A8h+var_48], rax
0x18006c7a0  xor     r15d, r15d
0x18006c7a3  mov     [rsp+0A8h+nSize], 10h
0x18006c7ab  mov     rdi, r9
0x18006c7ae  mov     r14, r8
0x18006c7b1  mov     rsi, rdx
0x18006c7b4  mov     rbx, rcx
0x18006c7b7  cmp     [rcx+148h], r15d
0x18006c7be  ja      short loc_18006C7D9
0x18006c7c0  mov     r8d, 1F3h; unsigned int
0x18006c7c6  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006c7cd  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006c7d4  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006c7d9  mov     rcx, [rsp+0A8h+arg_20]
0x18006c7e1  test    rcx, rcx
0x18006c7e4  jz      short loc_18006C7F8
0x18006c7e6  movups  xmm0, xmmword ptr [rcx]
0x18006c7e9  lea     rax, [rbx+60h]
0x18006c7ed  mov     [rbx+0B0h], rax
0x18006c7f4  movdqu  xmmword ptr [rax], xmm0
0x18006c7f8  test    rdi, rdi
0x18006c7fb  jz      loc_18006C882
0x18006c801  mov     rcx, [rbx+108h]; Sid1
0x18006c808  test    rcx, rcx
0x18006c80b  jz      short loc_18006C83A
0x18006c80d  mov     rdx, rdi; Sid2
0x18006c810  call    cs:__imp_RtlEqualSid
0x18006c817  nop     dword ptr [rax+rax+00h]
0x18006c81c  test    al, al
0x18006c81e  jnz     short loc_18006C83A
0x18006c820  mov     rcx, [rbx+108h]; hMem
0x18006c827  call    cs:__imp_LocalFree
0x18006c82e  nop     dword ptr [rax+rax+00h]
0x18006c833  mov     [rbx+108h], r15
0x18006c83a  cmp     [rbx+108h], r15
0x18006c841  jnz     short loc_18006C882
0x18006c843  mov     rcx, rdi; Sid
0x18006c846  call    cs:__imp_RtlLengthSid
0x18006c84d  nop     dword ptr [rax+rax+00h]
0x18006c852  mov     edx, eax; uBytes
0x18006c854  xor     ecx, ecx; uFlags
0x18006c856  mov     ebp, eax
0x18006c858  call    cs:__imp_LocalAlloc
0x18006c85f  nop     dword ptr [rax+rax+00h]
0x18006c864  mov     [rbx+108h], rax
0x18006c86b  test    rax, rax
0x18006c86e  jz      loc_18006C947
0x18006c874  mov     r8d, ebp; Size
0x18006c877  mov     rdx, rdi; Src
0x18006c87a  mov     rcx, rax; void *
0x18006c87d  call    memcpy_0
0x18006c882  test    rsi, rsi
0x18006c885  jz      loc_18006C958
0x18006c88b  lea     rdi, [rbx+70h]
0x18006c88f  cmp     [rdi], r15w
0x18006c893  jz      short loc_18006C8DB
0x18006c895  mov     rdx, rsi; DomainName2
0x18006c898  mov     rcx, rdi; DomainName1
0x18006c89b  call    cs:__imp_RtlEqualDomainName
0x18006c8a2  nop     dword ptr [rax+rax+00h]
0x18006c8a7  test    al, al
0x18006c8a9  jnz     short loc_18006C8D5
0x18006c8ab  mov     rax, [rbx+78h]
0x18006c8af  cmp     [rbx+0B8h], rax
0x18006c8b6  jnz     short loc_18006C8BF
0x18006c8b8  mov     [rbx+0B8h], r15
0x18006c8bf  mov     rcx, rdi; struct _UNICODE_STRING *
0x18006c8c2  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x18006c8c7  mov     [rbx+90h], r15d
0x18006c8ce  mov     [rbx+80h], r15b
0x18006c8d5  cmp     [rdi], r15w
0x18006c8d9  jnz     short loc_18006C958
0x18006c8db  mov     rdx, rdi; struct _UNICODE_STRING *
0x18006c8de  mov     rcx, rsi; struct _UNICODE_STRING *
0x18006c8e1  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006c8e6  test    al, al
0x18006c8e8  jz      short loc_18006C947
0x18006c8ea  cmp     [rbx+0B8h], r15
0x18006c8f1  jnz     short loc_18006C8FE
0x18006c8f3  mov     rax, [rbx+78h]
0x18006c8f7  mov     [rbx+0B8h], rax
0x18006c8fe  movzx   eax, word ptr [rsi]
0x18006c901  lea     rdi, [rbx+90h]
0x18006c908  mov     r9, [rsi+8]; UnicodeString
0x18006c90c  lea     rcx, [rbx+80h]; OemString
0x18006c913  mov     r8, rdi; ResultSize
0x18006c916  mov     [rsp+0A8h+UnicodeSize], eax; UnicodeSize
0x18006c91a  mov     edx, 0Fh; OemSize
0x18006c91f  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x18006c926  nop     dword ptr [rax+rax+00h]
0x18006c92b  test    eax, eax
0x18006c92d  jns     short loc_18006C94E
0x18006c92f  mov     r8, [rsi+8]
0x18006c933  lea     rdx, aWsUnableToConv; "%ws: Unable to convert Domain name to O"...
0x18006c93a  mov     r9d, eax
0x18006c93d  mov     ecx, 100h; unsigned int
0x18006c942  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006c947  xor     eax, eax
0x18006c949  jmp     loc_18006CBA2
0x18006c94e  mov     eax, [rdi]
0x18006c950  mov     [rax+rbx+80h], r15b
0x18006c958  test    r14, r14
0x18006c95b  jz      loc_18006CA13
0x18006c961  lea     rdi, [rbx+98h]
0x18006c968  cmp     [rdi], r15w
0x18006c96c  jz      short loc_18006C9BA
0x18006c96e  mov     rdx, r14; struct _UNICODE_STRING *
0x18006c971  mov     rcx, rdi; struct _UNICODE_STRING *
0x18006c974  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006c979  test    eax, eax
0x18006c97b  jnz     short loc_18006C9B4
0x18006c97d  mov     rax, [rbx+0A0h]
0x18006c984  cmp     [rbx+0B8h], rax
0x18006c98b  jnz     short loc_18006C994
0x18006c98d  mov     [rbx+0B8h], r15
0x18006c994  mov     rcx, rdi; struct _UNICODE_STRING *
0x18006c997  call    ?NlFreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; NlFreeUnicodeString(_UNICODE_STRING *)
0x18006c99c  mov     rcx, [rbx+0A8h]
0x18006c9a3  test    rcx, rcx
0x18006c9a6  jz      short loc_18006C9B4
0x18006c9a8  call    NetpMemoryFree
0x18006c9ad  mov     [rbx+0A8h], r15
0x18006c9b4  cmp     [rdi], r15w
0x18006c9b8  jnz     short loc_18006CA13
0x18006c9ba  mov     rdx, rdi; struct _UNICODE_STRING *
0x18006c9bd  mov     rcx, r14; struct _UNICODE_STRING *
0x18006c9c0  call    ?NlDuplicateUnicodeString@@YAEPEAU_UNICODE_STRING@@0@Z; NlDuplicateUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006c9c5  test    al, al
0x18006c9c7  jz      loc_18006C947
0x18006c9cd  cmp     [rbx+0B8h], r15
0x18006c9d4  jnz     short loc_18006C9E4
0x18006c9d6  mov     rax, [rbx+0A0h]
0x18006c9dd  mov     [rbx+0B8h], rax
0x18006c9e4  mov     rcx, [rbx+0A0h]; lpWideCharStr
0x18006c9eb  test    rcx, rcx
0x18006c9ee  jnz     short loc_18006C9F9
0x18006c9f0  mov     [rbx+0A8h], r15
0x18006c9f7  jmp     short loc_18006CA13
0x18006c9f9  xor     r8d, r8d; int
0x18006c9fc  xor     edx, edx; lpMultiByteStr
0x18006c9fe  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18006ca03  mov     [rbx+0A8h], rax
0x18006ca0a  test    rax, rax
0x18006ca0d  jz      loc_18006C947
0x18006ca13  test    byte ptr [rbx+124h], 10h
0x18006ca1a  jz      loc_18006CB9D
0x18006ca20  mov     ecx, [rbx+118h]
0x18006ca26  sub     ecx, 2
0x18006ca29  jz      short loc_18006CA4B
0x18006ca2b  sub     ecx, 1
0x18006ca2e  jz      loc_18006CB6D
0x18006ca34  sub     ecx, 1
0x18006ca37  jz      loc_18006CB5D
0x18006ca3d  sub     ecx, 2
0x18006ca40  jz      short loc_18006CA4B
0x18006ca42  cmp     ecx, 1
0x18006ca45  jnz     loc_18006C947
0x18006ca4b  mov     r8, [rbx+110h]
0x18006ca52  mov     r8, [r8+108h]
0x18006ca59  mov     edi, 11h
0x18006ca5e  lea     rcx, [rsp+0A8h+Src]
0x18006ca63  mov     edx, edi
0x18006ca65  call    cs:__imp__o_wcscpy_s
0x18006ca6c  nop     dword ptr [rax+rax+00h]
0x18006ca71  lea     r8, asc_1800ACA94; "$"
0x18006ca78  mov     edx, edi
0x18006ca7a  lea     rcx, [rsp+0A8h+Src]
0x18006ca7f  call    cs:__imp__o_wcscat_s
0x18006ca86  nop     dword ptr [rax+rax+00h]
0x18006ca8b  lea     rdi, [rsp+0A8h+Src]
0x18006ca90  mov     rcx, [rbx+0C8h]
0x18006ca97  test    rcx, rcx
0x18006ca9a  jz      short loc_18006CAC9
0x18006ca9c  mov     rdx, rdi
0x18006ca9f  call    cs:__imp__o__wcsicmp
0x18006caa6  nop     dword ptr [rax+rax+00h]
0x18006caab  test    eax, eax
0x18006caad  jz      short loc_18006CAC9
0x18006caaf  mov     rcx, [rbx+0C8h]; Buffer
0x18006cab6  call    cs:__imp_NetApiBufferFree
0x18006cabd  nop     dword ptr [rax+rax+00h]
0x18006cac2  mov     [rbx+0C8h], r15
0x18006cac9  cmp     [rbx+0C8h], r15
0x18006cad0  jnz     loc_18006CB9D
0x18006cad6  mov     rcx, rdi; Src
0x18006cad9  call    NetpAllocWStrFromWStr
0x18006cade  mov     [rbx+0C8h], rax
0x18006cae5  test    rax, rax
0x18006cae8  jz      loc_18006C947
0x18006caee  test    dword ptr [rbx+124h], 40000h
0x18006caf8  jz      loc_18006CB9D
0x18006cafe  lea     rdi, [rbx+0E0h]
0x18006cb05  mov     ecx, 4; NameType
0x18006cb0a  mov     rdx, rdi; lpBuffer
0x18006cb0d  lea     r8, [rsp+0A8h+nSize]; nSize
0x18006cb12  call    cs:__imp_GetComputerNameExW
0x18006cb19  nop     dword ptr [rax+rax+00h]
0x18006cb1e  test    eax, eax
0x18006cb20  jz      loc_18006C947
0x18006cb26  lea     rcx, [rbx+0D0h]; DestinationString
0x18006cb2d  mov     rdx, rdi; SourceString
0x18006cb30  call    cs:__imp_RtlInitUnicodeString
0x18006cb37  nop     dword ptr [rax+rax+00h]
0x18006cb3c  xor     r8d, r8d; int
0x18006cb3f  xor     edx, edx; lpMultiByteStr
0x18006cb41  mov     rcx, rdi; lpWideCharStr
0x18006cb44  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18006cb49  test    rax, rax
0x18006cb4c  mov     [rbx+100h], rax
0x18006cb53  mov     ecx, r15d
0x18006cb56  setnz   cl
0x18006cb59  mov     eax, ecx
0x18006cb5b  jmp     short loc_18006CBA2
0x18006cb5d  mov     r8, [rbx+110h]
0x18006cb64  add     r8, 48h ; 'H'
0x18006cb68  jmp     loc_18006CA59
0x18006cb6d  mov     rax, [rbx+110h]
0x18006cb74  mov     rdi, [rax+90h]
0x18006cb7b  test    rdi, rdi
0x18006cb7e  jnz     loc_18006CA90
0x18006cb84  lea     r8, aNlsetnameclien; "NlSetNameClientSession: NT 5 DNS trust "...
0x18006cb8b  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18006cb8e  mov     ecx, 100h; unsigned int
0x18006cb93  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006cb98  jmp     loc_18006C947
0x18006cb9d  mov     eax, 1
0x18006cba2  mov     rcx, [rsp+0A8h+var_48]
0x18006cba7  xor     rcx, rsp; StackCookie
0x18006cbaa  call    __security_check_cookie
0x18006cbaf  add     rsp, 78h
0x18006cbb3  pop     r15
0x18006cbb5  pop     r14
0x18006cbb7  pop     rdi
0x18006cbb8  pop     rsi
0x18006cbb9  pop     rbp
0x18006cbba  pop     rbx
0x18006cbbb  retn
```
