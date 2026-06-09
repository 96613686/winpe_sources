# DsRolepInstallDs

- ea: `0x180017890`
- end: `0x180017c08`
- name: `DsRolepInstallDs`
- size: `888`
- prototype: `__int64 __fastcall(PCWSTR pName2, __int64, __int64, __int64, LPCWSTR pszPath, __int64, __int64, __int64, unsigned __int16 *, __int64, __int64, _WORD *, STRSAFE_LPCWSTR pszSrc, __int64, __int64, __int64, int, char, __int64, __int64, __int64, __int64, int, __int64, int, int, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180016374`
- `0x180016538`
- `0x180017890`
- `0x18001ec08`
- `0x18001ee88`
- `0x18001f5b0`
- `0x180020dbc`
- `0x180020e50`
- `0x18002c01e`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180017af6`
- `DNSAPI!DnsNameCompare_W` at `0x180017af6`
- `NTDSETUP!NtdsInstall` at `0x180017bb5`
- `NTDSETUP!NtdsInstall` at `0x180017bb5`

## string_xrefs

- `0x180017b85`: `Calling NtdsInstall for %ws\n`
- `0x180017bc5`: `NtdsInstall for %ws returned %lu\n`
- `0x180017be1`: `DsRolepInstallDs returned %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepInstallDs(
        PCWSTR pName2,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPCWSTR pszPath,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned __int16 *a9,
        __int64 a10,
        __int64 a11,
        _WORD *a12,
        STRSAFE_LPCWSTR pszSrc,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        int a17,
        char a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        int a23,
        __int64 a24,
        int a25,
        int a26,
        int a27,
        __int64 a28,
        __int64 a29,
        __int64 a30)
{
  int v34; // ecx
  int v35; // eax
  int v36; // r9d
  _WORD *v37; // r8
  unsigned int AuthIdentForCreds; // ebx
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+38h] [rbp-C8h]
  int v42; // [rsp+44h] [rbp-BCh]
  LPCWSTR v43; // [rsp+48h] [rbp-B8h]
  __int64 v44; // [rsp+50h] [rbp-B0h]
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h]
  int v47; // [rsp+68h] [rbp-98h]
  __int64 v48; // [rsp+70h] [rbp-90h]
  PCWSTR v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h]
  _WORD *v52; // [rsp+90h] [rbp-70h]
  __int64 v53; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v54)(STRSAFE_LPCWSTR); // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v56)(STRSAFE_LPCWSTR); // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v57)(); // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  HANDLE v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+D8h] [rbp-28h]
  __int64 v61; // [rsp+E0h] [rbp-20h]
  int v62; // [rsp+E8h] [rbp-18h]
  __int64 v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+160h] [rbp+60h]
  __int64 v65; // [rsp+168h] [rbp+68h]
  int v66; // [rsp+170h] [rbp+70h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  int v68; // [rsp+180h] [rbp+80h]
  int v69; // [rsp+188h] [rbp+88h]
  int v70; // [rsp+18Ch] [rbp+8Ch]

  memset_0(&v40, 0, 0x160u);
  if ( a18 )
    v34 = 4;
  else
    v34 = (a11 != 0) + 1;
  v40 = v34;
  if ( (a17 & 4) != 0 )
  {
    v34 |= 8u;
    v40 = v34;
  }
  if ( (a17 & 8) != 0 )
  {
    v34 |= 0x10u;
    v40 = v34;
  }
  if ( (a17 & 0x20) != 0 )
  {
    v34 |= 0x20u;
    v40 = v34;
  }
  if ( (a17 & 0x10) != 0 )
  {
    v34 |= 0x80u;
    v40 = v34;
  }
  if ( (a17 & 0x800) != 0 )
  {
    v34 |= 0x100u;
    v40 = v34;
  }
  if ( (a17 & 0x4000) != 0 )
  {
    v34 |= 0x200u;
    v40 = v34;
  }
  if ( (a17 & 0x8000) != 0 )
  {
    v34 |= 0x400u;
    v40 = v34;
  }
  v35 = v42;
  if ( (a17 & 0x20000) != 0 )
    v35 = 1;
  v42 = v35;
  if ( (a17 & 0x800000) != 0 )
  {
    v34 |= 0x4000u;
    v40 = v34;
  }
  v36 = a17 & 0x40000;
  if ( (a17 & 0x40000) != 0 )
  {
    v34 |= 0x800u;
    v40 = v34;
  }
  if ( (a17 & 0x80000) != 0 )
  {
    v34 |= 0x1000u;
    v40 = v34;
  }
  if ( (a17 & 0x400000) != 0 )
    v40 = v34 | 0x2000;
  v37 = a12;
  if ( a12 && *a12 == 92 )
    v37 = a12 + 2;
  v44 = a6;
  v45 = a8;
  v46 = *((_QWORD *)a9 + 1);
  v47 = *a9;
  v54 = DsRolepStringUpdateCallback;
  v57 = DsRolepOperationResultFlagsCallBack;
  v55 = a10;
  v56 = DsRolepStringErrorUpdateCallback;
  v58 = a19;
  v59 = NewTokenHandle;
  v60 = a15;
  v61 = a16;
  v63 = a20;
  v70 = a26;
  v69 = a27;
  v43 = pszPath;
  v41 = a7;
  v48 = a4;
  v49 = pName2;
  v50 = a2;
  v51 = a3;
  v52 = v37;
  v62 = a17;
  if ( v36 )
  {
    v64 = a21;
    v65 = a22;
    v66 = a23;
    v67 = a24;
    v68 = a25;
  }
  if ( !a7 || v36 || DnsNameCompare_W(*(PCWSTR *)(a7 + 32), pName2) )
  {
    AuthIdentForCreds = DsRolepCreateAuthIdentForCreds(pszSrc);
    if ( !AuthIdentForCreds )
    {
      v53 = 0;
      if ( v41 || (a17 & 0x800000) != 0 || (AuthIdentForCreds = DsRolepCopyDsDitFiles(pszPath)) == 0 )
      {
        DsRolepSetCurrentOperationStatus(28678, 0, 0);
        DsRolepLogPrintRoutine(8, "Calling NtdsInstall for %ws\n", pName2);
        DsRolepSetAndClearLog();
        AuthIdentForCreds = NtdsInstall(&v40, a28, a29, a30);
        DsRolepSetAndClearLog();
        DsRolepLogPrintRoutine(8, "NtdsInstall for %ws returned %lu\n", pName2, AuthIdentForCreds);
      }
      DsRolepFreeAuthIdentForCreds(0);
    }
    DsRolepLogPrintRoutine(4, "DsRolepInstallDs returned %lu\n", AuthIdentForCreds);
  }
  else
  {
    AuthIdentForCreds = 1399;
    DsRolepSetFailureMessage(1399, 3221254707LL, v49, *(_QWORD *)(a7 + 32), 0);
  }
  return AuthIdentForCreds;
}

```

## disassembly

```asm
0x180017890  push    rbp
0x180017892  push    rbx
0x180017893  push    rsi
0x180017894  push    rdi
0x180017895  push    r12
0x180017897  push    r13
0x180017899  push    r14
0x18001789b  push    r15
0x18001789d  lea     rbp, [rsp-98h]
0x1800178a5  sub     rsp, 198h
0x1800178ac  mov     r12, r8
0x1800178af  mov     [rbp+0D0h+P], 0
0x1800178ba  mov     r13, rdx
0x1800178bd  mov     r15, rcx
0x1800178c0  xor     edx, edx; Val
0x1800178c2  lea     rcx, [rsp+1D0h+var_1A0]; void *
0x1800178c7  mov     r8d, 160h; Size
0x1800178cd  mov     rdi, r9
0x1800178d0  call    memset_0
0x1800178d5  cmp     [rbp+0D0h+arg_88], 0
0x1800178dc  mov     r9d, 1
0x1800178e2  jnz     short loc_1800178F4
0x1800178e4  neg     [rbp+0D0h+arg_50]
0x1800178eb  sbb     ecx, ecx
0x1800178ed  neg     ecx
0x1800178ef  add     ecx, r9d
0x1800178f2  jmp     short loc_1800178F9
0x1800178f4  mov     ecx, 4
0x1800178f9  mov     edx, [rbp+0D0h+arg_80]
0x1800178ff  mov     [rsp+1D0h+var_1A0], ecx
0x180017903  test    dl, 4
0x180017906  jz      short loc_18001790F
0x180017908  or      ecx, 8
0x18001790b  mov     [rsp+1D0h+var_1A0], ecx
0x18001790f  test    dl, 8
0x180017912  jz      short loc_18001791B
0x180017914  or      ecx, 10h
0x180017917  mov     [rsp+1D0h+var_1A0], ecx
0x18001791b  test    dl, 20h
0x18001791e  jz      short loc_180017927
0x180017920  or      ecx, 20h
0x180017923  mov     [rsp+1D0h+var_1A0], ecx
0x180017927  test    dl, 10h
0x18001792a  jz      short loc_180017934
0x18001792c  bts     ecx, 7
0x180017930  mov     [rsp+1D0h+var_1A0], ecx
0x180017934  mov     r10d, 800h
0x18001793a  test    r10d, edx
0x18001793d  jz      short loc_180017947
0x18001793f  bts     ecx, 8
0x180017943  mov     [rsp+1D0h+var_1A0], ecx
0x180017947  mov     r8d, 4000h
0x18001794d  test    r8d, edx
0x180017950  jz      short loc_18001795A
0x180017952  bts     ecx, 9
0x180017956  mov     [rsp+1D0h+var_1A0], ecx
0x18001795a  bt      edx, 0Fh
0x18001795e  jnb     short loc_180017968
0x180017960  bts     ecx, 0Ah
0x180017964  mov     [rsp+1D0h+var_1A0], ecx
0x180017968  mov     eax, [rsp+1D0h+var_18C]
0x18001796c  bt      edx, 11h
0x180017970  mov     esi, edx
0x180017972  cmovb   eax, r9d
0x180017976  mov     [rsp+1D0h+var_18C], eax
0x18001797a  and     esi, 800000h
0x180017980  jz      short loc_180017989
0x180017982  or      ecx, r8d
0x180017985  mov     [rsp+1D0h+var_1A0], ecx
0x180017989  mov     r9d, edx
0x18001798c  and     r9d, 40000h
0x180017993  jz      short loc_18001799C
0x180017995  or      ecx, r10d
0x180017998  mov     [rsp+1D0h+var_1A0], ecx
0x18001799c  bt      edx, 13h
0x1800179a0  jnb     short loc_1800179AA
0x1800179a2  bts     ecx, 0Ch
0x1800179a6  mov     [rsp+1D0h+var_1A0], ecx
0x1800179aa  bt      edx, 16h
0x1800179ae  jnb     short loc_1800179B8
0x1800179b0  bts     ecx, 0Dh
0x1800179b4  mov     [rsp+1D0h+var_1A0], ecx
0x1800179b8  mov     r8, [rbp+0D0h+arg_58]
0x1800179bf  test    r8, r8
0x1800179c2  jz      short loc_1800179CF
0x1800179c4  cmp     word ptr [r8], 5Ch ; '\'
0x1800179c9  jnz     short loc_1800179CF
0x1800179cb  add     r8, 4
0x1800179cf  mov     rax, [rbp+0D0h+arg_28]
0x1800179d6  mov     rcx, [rbp+0D0h+arg_40]
0x1800179dd  mov     r14, [rbp+0D0h+pszPath]
0x1800179e4  mov     rbx, [rbp+0D0h+arg_30]
0x1800179eb  mov     [rsp+1D0h+var_180], rax
0x1800179f0  mov     rax, [rbp+0D0h+arg_38]
0x1800179f7  mov     [rsp+1D0h+var_178], rax
0x1800179fc  mov     rax, [rcx+8]
0x180017a00  mov     [rsp+1D0h+var_170], rax
0x180017a05  movzx   eax, word ptr [rcx]
0x180017a08  mov     [rsp+1D0h+var_168], eax
0x180017a0c  lea     rax, DsRolepStringUpdateCallback
0x180017a13  mov     [rbp+0D0h+var_128], rax
0x180017a17  lea     rax, DsRolepOperationResultFlagsCallBack
0x180017a1e  mov     [rbp+0D0h+var_110], rax
0x180017a22  mov     rax, [rbp+0D0h+arg_48]
0x180017a29  mov     [rbp+0D0h+var_120], rax
0x180017a2d  lea     rax, DsRolepStringErrorUpdateCallback
0x180017a34  mov     [rbp+0D0h+var_118], rax
0x180017a38  mov     rax, [rbp+0D0h+arg_90]
0x180017a3f  mov     [rbp+0D0h+var_108], rax
0x180017a43  mov     rax, cs:NewTokenHandle
0x180017a4a  mov     [rbp+0D0h+var_100], rax
0x180017a4e  mov     rax, [rbp+0D0h+arg_70]
0x180017a55  mov     [rbp+0D0h+var_F8], rax
0x180017a59  mov     rax, [rbp+0D0h+arg_78]
0x180017a60  mov     [rbp+0D0h+var_F0], rax
0x180017a64  mov     rax, [rbp+0D0h+arg_98]
0x180017a6b  mov     [rbp+0D0h+var_E0], rax
0x180017a6f  mov     eax, [rbp+0D0h+arg_C8]
0x180017a75  mov     [rbp+0D0h+var_44], eax
0x180017a7b  mov     eax, [rbp+0D0h+arg_D0]
0x180017a81  mov     [rbp+0D0h+var_48], eax
0x180017a87  mov     [rsp+1D0h+var_188], r14
0x180017a8c  mov     [rsp+1D0h+var_198], rbx
0x180017a91  mov     [rsp+1D0h+var_160], rdi
0x180017a96  mov     [rsp+1D0h+var_158], r15
0x180017a9b  mov     [rbp+0D0h+var_150], r13
0x180017a9f  mov     [rbp+0D0h+var_148], r12
0x180017aa3  mov     [rbp+0D0h+var_140], r8
0x180017aa7  mov     [rbp+0D0h+var_E8], edx
0x180017aaa  test    r9d, r9d
0x180017aad  jz      short loc_180017AE5
0x180017aaf  mov     rax, [rbp+0D0h+arg_A0]
0x180017ab6  mov     [rbp+0D0h+var_70], rax
0x180017aba  mov     rax, [rbp+0D0h+arg_A8]
0x180017ac1  mov     [rbp+0D0h+var_68], rax
0x180017ac5  mov     eax, [rbp+0D0h+arg_B0]
0x180017acb  mov     [rbp+0D0h+var_60], eax
0x180017ace  mov     rax, [rbp+0D0h+arg_B8]
0x180017ad5  mov     [rbp+0D0h+var_58], rax
0x180017ad9  mov     eax, [rbp+0D0h+arg_C0]
0x180017adf  mov     [rbp+0D0h+var_50], eax
0x180017ae5  test    rbx, rbx
0x180017ae8  jz      short loc_180017B28
0x180017aea  test    r9d, r9d
0x180017aed  jnz     short loc_180017B28
0x180017aef  mov     rcx, [rbx+20h]; pName1
0x180017af3  mov     rdx, r15; pName2
0x180017af6  call    cs:__imp_DnsNameCompare_W
0x180017afc  test    eax, eax
0x180017afe  jnz     short loc_180017B28
0x180017b00  mov     r9, [rbx+20h]
0x180017b04  mov     edx, 0C0007233h
0x180017b09  mov     r8, [rsp+1D0h+var_158]
0x180017b0e  mov     ebx, 577h
0x180017b13  mov     ecx, ebx
0x180017b15  mov     [rsp+1D0h+var_1B0], 0
0x180017b1e  call    DsRolepSetFailureMessage
0x180017b23  jmp     loc_180017BF2
0x180017b28  mov     rdx, [rbp+0D0h+arg_68]
0x180017b2f  lea     r8, [rbp+0D0h+P]
0x180017b36  mov     rcx, [rbp+0D0h+pszSrc]; pszSrc
0x180017b3d  call    DsRolepCreateAuthIdentForCreds
0x180017b42  mov     ebx, eax
0x180017b44  test    eax, eax
0x180017b46  jnz     loc_180017BDE
0x180017b4c  cmp     [rsp+1D0h+var_198], 0
0x180017b52  mov     rdi, [rbp+0D0h+P]
0x180017b59  mov     [rbp+0D0h+var_130], rdi
0x180017b5d  jnz     short loc_180017B71
0x180017b5f  test    esi, esi
0x180017b61  jnz     short loc_180017B71
0x180017b63  mov     rcx, r14; pszPath
0x180017b66  call    DsRolepCopyDsDitFiles
0x180017b6b  mov     ebx, eax
0x180017b6d  test    eax, eax
0x180017b6f  jnz     short loc_180017BD6
0x180017b71  xor     r8d, r8d
0x180017b74  xor     edx, edx
0x180017b76  mov     ecx, 7006h
0x180017b7b  call    DsRolepSetCurrentOperationStatus
0x180017b80  mov     esi, 8
0x180017b85  lea     rdx, aCallingNtdsins; "Calling NtdsInstall for %ws\n"
0x180017b8c  mov     ecx, esi
0x180017b8e  mov     r8, r15
0x180017b91  call    DsRolepLogPrintRoutine
0x180017b96  call    DsRolepSetAndClearLog
0x180017b9b  mov     r9, [rbp+0D0h+arg_E8]
0x180017ba2  lea     rcx, [rsp+1D0h+var_1A0]
0x180017ba7  mov     r8, [rbp+0D0h+arg_E0]
0x180017bae  mov     rdx, [rbp+0D0h+arg_D8]
0x180017bb5  call    cs:__imp_NtdsInstall
0x180017bbb  mov     ebx, eax
0x180017bbd  call    DsRolepSetAndClearLog
0x180017bc2  mov     r9d, ebx
0x180017bc5  lea     rdx, aNtdsinstallFor; "NtdsInstall for %ws returned %lu\n"
0x180017bcc  mov     r8, r15
0x180017bcf  mov     ecx, esi
0x180017bd1  call    DsRolepLogPrintRoutine
0x180017bd6  mov     rcx, rdi; P
0x180017bd9  call    DsRolepFreeAuthIdentForCreds
0x180017bde  mov     r8d, ebx
0x180017be1  lea     rdx, aDsrolepinstall; "DsRolepInstallDs returned %lu\n"
0x180017be8  mov     ecx, 4
0x180017bed  call    DsRolepLogPrintRoutine
0x180017bf2  mov     eax, ebx
0x180017bf4  add     rsp, 198h
0x180017bfb  pop     r15
0x180017bfd  pop     r14
0x180017bff  pop     r13
0x180017c01  pop     r12
0x180017c03  pop     rdi
0x180017c04  pop     rsi
0x180017c05  pop     rbx
0x180017c06  pop     rbp
0x180017c07  retn
```
