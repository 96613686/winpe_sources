# DfsAddMachineAce

- ea: `0x14005a010`
- end: `0x14005a2a8`
- name: `DfsAddMachineAce`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140032efc`

## callees

- `0x140001526`
- `0x140001532`
- `0x14000aed8`
- `0x140059608`
- `0x140059f80`
- `0x14005a010`
- `0x14005a2b0`
- `0x14005a870`

## import_xrefs

- `ntdll!RtlDnsHostNameToComputerName` at `0x14005a0da`
- `ntdll!RtlDnsHostNameToComputerName` at `0x14005a0da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a248`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a25d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a248`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a25d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005a271`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14005a12f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14005a12f`

## pseudocode

```c
__int64 __fastcall DfsAddMachineAce(LDAP *a1, const WCHAR *a2, WCHAR *a3, WCHAR *a4, unsigned int a5)
{
  PSID v5; // r14
  WCHAR *v6; // rsi
  unsigned int ObjStringSD; // ebx
  __int64 v9; // rbx
  __int64 v10; // rdi
  wchar_t *v11; // rax
  wchar_t *v12; // r12
  STRSAFE_LPCWSTR v13; // r8
  int v14; // eax
  HLOCAL v15; // r15
  __int64 v16; // rcx
  LPWSTR v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rbx
  unsigned __int16 *v22; // rax
  LPWSTR StringSid; // [rsp+58h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  PSID Sid; // [rsp+68h] [rbp-11h]
  STRSAFE_LPWSTR pszDest; // [rsp+70h] [rbp-9h]
  struct _UNICODE_STRING ComputerName; // [rsp+78h] [rbp-1h] BYREF
  struct _UNICODE_STRING DnsHostName; // [rsp+88h] [rbp+Fh] BYREF

  Sid = 0;
  hMem = 0;
  StringSid = 0;
  v5 = 0;
  v6 = 0;
  DnsHostName = 0;
  ComputerName = 0;
  ObjStringSD = DfsGetObjStringSD(a1, a3, &hMem);
  if ( !ObjStringSD )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = (wchar_t *)malloc_0((unsigned int)(2 * v10 + 4));
    pszDest = v11;
    if ( v11 )
    {
      ComputerName.MaximumLength = 2 * v10 + 4;
      DnsHostName.Length = 2 * v10;
      ComputerName.Buffer = v11;
      DnsHostName.MaximumLength = 2 * v10 + 2;
      ComputerName.Length = 0;
      DnsHostName.Buffer = a4;
      RtlDnsHostNameToComputerName(&ComputerName, &DnsHostName, 0);
      v12 = pszDest;
      ComputerName.Buffer[(unsigned __int64)ComputerName.Length >> 1] = 0;
      StringCbCatW(v12, (unsigned int)(2 * v10 + 4), v13);
      v14 = DfsFindSid(a2, v12);
      v5 = Sid;
      if ( v14 == 1 && ConvertSidToStringSidW(Sid, &StringSid) )
      {
        v15 = hMem;
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)hMem + v16) );
        v17 = StringSid;
        if ( a5 < 2 )
        {
          do
            ++v9;
          while ( StringSid[v9] );
          v21 = v16 + v9 + 13;
        }
        else
        {
          v18 = -1;
          do
            ++v18;
          while ( StringSid[v18] );
          v19 = -1;
          do
            ++v19;
          while ( StringSid[v19] );
          v20 = v16 + v19;
          do
            ++v9;
          while ( StringSid[v9] );
          v21 = v18 + v20 + v9 + 49;
        }
        v22 = (unsigned __int16 *)malloc_0(2 * v21);
        v6 = v22;
        if ( v22 )
        {
          if ( a5 < 2 )
            StringCchPrintfW(v22, v21, L"%s%s%s)", v15, L"(A;;RPWP;;;", v17);
          else
            StringCchPrintfW(
              v22,
              v21,
              L"%s%s%s)%s%s)%s%s)",
              v15,
              L"(A;;CCDC;;;",
              v17,
              L"(A;CIIONP;CCDCDT;;;",
              v17,
              L"(A;CIIO;RPWP;;;",
              v17);
          ObjStringSD = DfsAddAce(a1, a3, v6);
        }
        else
        {
          ObjStringSD = 8;
        }
      }
      else
      {
        ObjStringSD = 4312;
      }
      free_0(v12);
    }
    else
    {
      ObjStringSD = 14;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v5 )
    LocalFree(v5);
  if ( v6 )
    free_0(v6);
  return ObjStringSD;
}

```

## disassembly

```asm
0x14005a010  mov     rax, rsp
0x14005a013  mov     [rax+20h], rbx
0x14005a017  mov     [rax+18h], r8
0x14005a01b  mov     [rax+10h], rdx
0x14005a01f  mov     [rax+8], rcx
0x14005a023  push    rbp
0x14005a024  push    rsi
0x14005a025  push    rdi
0x14005a026  push    r12
0x14005a028  push    r13
0x14005a02a  push    r14
0x14005a02c  push    r15
0x14005a02e  lea     rbp, [rax-57h]
0x14005a032  sub     rsp, 90h
0x14005a039  xor     r15d, r15d
0x14005a03c  mov     rdx, r8
0x14005a03f  xorps   xmm0, xmm0
0x14005a042  mov     [rbp+4Fh+Sid], r15
0x14005a046  xorps   xmm1, xmm1
0x14005a049  mov     [rbp+4Fh+hMem], r15
0x14005a04d  lea     r8, [rbp+4Fh+hMem]
0x14005a051  mov     [rbp+4Fh+StringSid], r15
0x14005a055  mov     r14d, r15d
0x14005a058  mov     esi, r15d
0x14005a05b  movups  xmmword ptr [rbp+4Fh+DnsHostName.Length], xmm0
0x14005a05f  mov     r13, r9
0x14005a062  movups  xmmword ptr [rbp+4Fh+ComputerName.Length], xmm1
0x14005a066  call    DfsGetObjStringSD
0x14005a06b  mov     ebx, eax
0x14005a06d  test    eax, eax
0x14005a06f  jnz     loc_14005A23F
0x14005a075  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14005a079  mov     rdi, rbx
0x14005a07c  inc     rdi
0x14005a07f  cmp     [r13+rdi*2+0], r15w
0x14005a085  jnz     short loc_14005A07C
0x14005a087  lea     r15d, ds:4[rdi*2]
0x14005a08f  mov     ecx, r15d; Size
0x14005a092  mov     r12d, r15d
0x14005a095  call    malloc_0
0x14005a09a  mov     [rbp+4Fh+pszDest], rax
0x14005a09e  test    rax, rax
0x14005a0a1  jnz     short loc_14005A0AB
0x14005a0a3  lea     ebx, [rax+0Eh]
0x14005a0a6  jmp     loc_14005A23F
0x14005a0ab  add     di, di
0x14005a0ae  mov     [rbp+4Fh+ComputerName.MaximumLength], r15w
0x14005a0b3  mov     [rbp+4Fh+DnsHostName.Length], di
0x14005a0b7  lea     rdx, [rbp+4Fh+DnsHostName]; DnsHostName
0x14005a0bb  add     di, 2
0x14005a0bf  mov     [rbp+4Fh+ComputerName.Buffer], rax
0x14005a0c3  xor     r15d, r15d
0x14005a0c6  mov     [rbp+4Fh+DnsHostName.MaximumLength], di
0x14005a0ca  xor     r8d, r8d; AllocateComputerNameString
0x14005a0cd  mov     [rbp+4Fh+ComputerName.Length], r15w
0x14005a0d2  lea     rcx, [rbp+4Fh+ComputerName]; ComputerName
0x14005a0d6  mov     [rbp+4Fh+DnsHostName.Buffer], r13
0x14005a0da  call    cs:__imp_RtlDnsHostNameToComputerName
0x14005a0e1  nop     dword ptr [rax+rax+00h]
0x14005a0e6  movzx   ecx, [rbp+4Fh+ComputerName.Length]
0x14005a0ea  mov     rdx, r12; cbDest
0x14005a0ed  mov     rax, [rbp+4Fh+ComputerName.Buffer]
0x14005a0f1  mov     r12, [rbp+4Fh+pszDest]
0x14005a0f5  shr     rcx, 1
0x14005a0f8  mov     [rax+rcx*2], r15w
0x14005a0fd  mov     rcx, r12; pszDest
0x14005a100  call    StringCbCatW
0x14005a105  mov     rcx, [rbp+4Fh+lpSystemName]; lpSystemName
0x14005a109  lea     r8, [rbp+4Fh+Sid]
0x14005a10d  mov     rdx, r12; lpAccountName
0x14005a110  call    DfsFindSid
0x14005a115  mov     r14, [rbp+4Fh+Sid]
0x14005a119  cmp     eax, 1
0x14005a11c  jz      short loc_14005A128
0x14005a11e  mov     ebx, 10D8h
0x14005a123  jmp     loc_14005A237
0x14005a128  lea     rdx, [rbp+4Fh+StringSid]; StringSid
0x14005a12c  mov     rcx, r14; Sid
0x14005a12f  call    cs:__imp_ConvertSidToStringSidW
0x14005a136  nop     dword ptr [rax+rax+00h]
0x14005a13b  cmp     eax, 1
0x14005a13e  jnz     short loc_14005A11E
0x14005a140  mov     r15, [rbp+4Fh+hMem]
0x14005a144  mov     rcx, rbx
0x14005a147  xor     r13d, r13d
0x14005a14a  inc     rcx
0x14005a14d  cmp     [r15+rcx*2], r13w
0x14005a152  jnz     short loc_14005A14A
0x14005a154  cmp     [rbp+4Fh+arg_20], 2
0x14005a158  mov     rdi, [rbp+4Fh+StringSid]
0x14005a15c  jb      short loc_14005A191
0x14005a15e  mov     rdx, rbx
0x14005a161  inc     rdx
0x14005a164  cmp     [rdi+rdx*2], r13w
0x14005a169  jnz     short loc_14005A161
0x14005a16b  mov     rax, rbx
0x14005a16e  inc     rax
0x14005a171  cmp     [rdi+rax*2], r13w
0x14005a176  jnz     short loc_14005A16E
0x14005a178  add     rax, rcx
0x14005a17b  inc     rbx
0x14005a17e  cmp     [rdi+rbx*2], r13w
0x14005a183  jnz     short loc_14005A17B
0x14005a185  add     rax, rdx
0x14005a188  add     rbx, 31h ; '1'
0x14005a18c  add     rbx, rax
0x14005a18f  jmp     short loc_14005A1A2
0x14005a191  inc     rbx
0x14005a194  cmp     [rdi+rbx*2], r13w
0x14005a199  jnz     short loc_14005A191
0x14005a19b  add     rbx, 0Dh
0x14005a19f  add     rbx, rcx
0x14005a1a2  lea     rcx, [rbx+rbx]; Size
0x14005a1a6  call    malloc_0
0x14005a1ab  mov     rsi, rax
0x14005a1ae  test    rax, rax
0x14005a1b1  jnz     short loc_14005A1B8
0x14005a1b3  lea     ebx, [rax+8]
0x14005a1b6  jmp     short loc_14005A237
0x14005a1b8  cmp     [rbp+4Fh+arg_20], 2
0x14005a1bc  mov     r9, r15
0x14005a1bf  mov     rdx, rbx; unsigned __int64
0x14005a1c2  mov     rcx, rsi; unsigned __int16 *
0x14005a1c5  jb      short loc_14005A208
0x14005a1c7  mov     [rsp+48h], rdi
0x14005a1cc  lea     rax, aACiioRpwp; "(A;CIIO;RPWP;;;"
0x14005a1d3  mov     [rsp+0C0h+var_80], rax
0x14005a1d8  lea     r8, aSSSSSSS; "%s%s%s)%s%s)%s%s)"
0x14005a1df  mov     [rsp+0C0h+var_88], rdi
0x14005a1e4  lea     rax, aACiionpCcdcdt; "(A;CIIONP;CCDCDT;;;"
0x14005a1eb  mov     [rsp+0C0h+var_90], rax
0x14005a1f0  lea     rax, aACcdc; "(A;;CCDC;;;"
0x14005a1f7  mov     [rsp+0C0h+var_98], rdi
0x14005a1fc  mov     [rsp+0C0h+var_A0], rax
0x14005a201  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a206  jmp     short loc_14005A225
0x14005a208  lea     rax, aARpwp; "(A;;RPWP;;;"
0x14005a20f  mov     [rsp+0C0h+var_98], rdi
0x14005a214  lea     r8, aSSS; "%s%s%s)"
0x14005a21b  mov     [rsp+0C0h+var_A0], rax
0x14005a220  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005a225  mov     rdx, [rbp+4Fh+dn]; dn
0x14005a229  mov     r8, rsi; StringSecurityDescriptor
0x14005a22c  mov     rcx, [rbp+4Fh+ld]; ld
0x14005a230  call    DfsAddAce
0x14005a235  mov     ebx, eax
0x14005a237  mov     rcx, r12; Block
0x14005a23a  call    free_0
0x14005a23f  mov     rcx, [rbp+4Fh+hMem]; hMem
0x14005a243  test    rcx, rcx
0x14005a246  jz      short loc_14005A254
0x14005a248  call    cs:__imp_LocalFree
0x14005a24f  nop     dword ptr [rax+rax+00h]
0x14005a254  mov     rcx, [rbp+4Fh+StringSid]; hMem
0x14005a258  test    rcx, rcx
0x14005a25b  jz      short loc_14005A269
0x14005a25d  call    cs:__imp_LocalFree
0x14005a264  nop     dword ptr [rax+rax+00h]
0x14005a269  test    r14, r14
0x14005a26c  jz      short loc_14005A27D
0x14005a26e  mov     rcx, r14; hMem
0x14005a271  call    cs:__imp_LocalFree
0x14005a278  nop     dword ptr [rax+rax+00h]
0x14005a27d  test    rsi, rsi
0x14005a280  jz      short loc_14005A28A
0x14005a282  mov     rcx, rsi; Block
0x14005a285  call    free_0
0x14005a28a  mov     eax, ebx
0x14005a28c  mov     rbx, [rsp+0C0h+arg_18]
0x14005a294  add     rsp, 90h
0x14005a29b  pop     r15
0x14005a29d  pop     r14
0x14005a29f  pop     r13
0x14005a2a1  pop     r12
0x14005a2a3  pop     rdi
0x14005a2a4  pop     rsi
0x14005a2a5  pop     rbp
0x14005a2a6  retn
```
