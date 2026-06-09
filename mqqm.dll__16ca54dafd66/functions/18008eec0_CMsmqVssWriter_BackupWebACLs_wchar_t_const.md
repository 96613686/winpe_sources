# CMsmqVssWriter::BackupWebACLs(wchar_t const *)

- ea: `0x18008eec0`
- end: `0x18008f334`
- name: `?BackupWebACLs@CMsmqVssWriter@@AEAAJPEB_W@Z`
- size: `1140`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800921e0`

## callees

- `0x18000bb04`
- `0x180012ea8`
- `0x18002c61c`
- `0x18008eec0`
- `0x180090140`
- `0x180092030`
- `0x1800944c8`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18008ef17`
- `msvcrt!free` at `0x18008ef89`
- `msvcrt!free` at `0x18008eff6`
- `msvcrt!free` at `0x18008f000`
- `msvcrt!free` at `0x18008f018`
- `msvcrt!free` at `0x18008f0af`
- `msvcrt!free` at `0x18008f0b9`
- `msvcrt!free` at `0x18008f0c3`
- `msvcrt!free` at `0x18008f113`
- `msvcrt!free` at `0x18008f11d`
- `msvcrt!free` at `0x18008f127`
- `msvcrt!free` at `0x18008f172`
- `msvcrt!free` at `0x18008f17c`
- `msvcrt!free` at `0x18008f186`
- `msvcrt!free` at `0x18008f200`
- `msvcrt!free` at `0x18008f20a`
- `msvcrt!free` at `0x18008f214`
- `msvcrt!free` at `0x18008f281`
- `msvcrt!free` at `0x18008f28b`
- `msvcrt!free` at `0x18008f295`
- `msvcrt!free` at `0x18008f2d9`
- `msvcrt!free` at `0x18008f2e3`
- `msvcrt!free` at `0x18008f2ed`
- `msvcrt!free` at `0x18008f306`
- `msvcrt!free` at `0x18008f310`
- `msvcrt!free` at `0x18008f31a`
- `msvcrt!free` at `0x18008ef17`
- `msvcrt!free` at `0x18008ef89`
- `msvcrt!free` at `0x18008eff6`
- `msvcrt!free` at `0x18008f000`
- `msvcrt!free` at `0x18008f018`
- `msvcrt!free` at `0x18008f0af`
- `msvcrt!free` at `0x18008f0b9`
- `msvcrt!free` at `0x18008f0c3`
- `msvcrt!free` at `0x18008f113`
- `msvcrt!free` at `0x18008f11d`
- `msvcrt!free` at `0x18008f127`
- `msvcrt!free` at `0x18008f172`
- `msvcrt!free` at `0x18008f17c`
- `msvcrt!free` at `0x18008f186`
- `msvcrt!free` at `0x18008f200`
- `msvcrt!free` at `0x18008f20a`
- `msvcrt!free` at `0x18008f214`
- `msvcrt!free` at `0x18008f281`
- `msvcrt!free` at `0x18008f28b`
- `msvcrt!free` at `0x18008f295`
- `msvcrt!free` at `0x18008f2d9`
- `msvcrt!free` at `0x18008f2e3`
- `msvcrt!free` at `0x18008f2ed`
- `msvcrt!free` at `0x18008f306`
- `msvcrt!free` at `0x18008f310`
- `msvcrt!free` at `0x18008f31a`
- `ADVAPI32!GetFileSecurityW` at `0x18008ef3f`
- `ADVAPI32!GetFileSecurityW` at `0x18008efbb`
- `ADVAPI32!GetFileSecurityW` at `0x18008ef3f`
- `ADVAPI32!GetFileSecurityW` at `0x18008efbb`
- `KERNEL32!GetLastError` at `0x18008ef4d`
- `KERNEL32!GetLastError` at `0x18008ef58`
- `KERNEL32!GetLastError` at `0x18008efc5`
- `KERNEL32!GetLastError` at `0x18008f1c0`
- `KERNEL32!GetLastError` at `0x18008f241`
- `KERNEL32!GetLastError` at `0x18008ef4d`
- `KERNEL32!GetLastError` at `0x18008ef58`
- `KERNEL32!GetLastError` at `0x18008efc5`
- `KERNEL32!GetLastError` at `0x18008f1c0`
- `KERNEL32!GetLastError` at `0x18008f241`
- `KERNEL32!WriteFile` at `0x18008f1b6`
- `KERNEL32!WriteFile` at `0x18008f237`
- `KERNEL32!WriteFile` at `0x18008f1b6`
- `KERNEL32!WriteFile` at `0x18008f237`

## string_xrefs

- `0x18008ef05`: `writer/mqwriter`
- `0x18008ef77`: `writer/mqwriter`
- `0x18008efe4`: `writer/mqwriter`
- `0x18008f09c`: `writer/mqwriter`
- `0x18008f0f7`: `writer/mqwriter`
- `0x18008f156`: `writer/mqwriter`
- `0x18008f1e3`: `writer/mqwriter`
- `0x18008f264`: `writer/mqwriter`
- `0x18008f2bd`: `writer/mqwriter`
- `0x18008f0da`: `msmqwebacl.bkp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMsmqVssWriter::BackupWebACLs(CMsmqVssWriter *this, wchar_t *a2)
{
  void *v2; // rbx
  CMsmqVssWriter *v3; // rcx
  unsigned int v4; // r8d
  int HttpPhysicalDirectory; // eax
  unsigned int v6; // edi
  signed int LastError; // eax
  DWORD v9; // eax
  unsigned __int8 *v10; // rdi
  signed int v11; // eax
  signed int v12; // esi
  DWORD v13; // r14d
  CMsmqVssWriter *v14; // rcx
  void *v15; // rsi
  wchar_t *v16; // r13
  DWORD i; // r15d
  int v18; // eax
  unsigned int v19; // r12d
  int v20; // eax
  CMsmqVssWriter *v21; // rcx
  signed int v22; // r14d
  HANDLE v23; // r14
  int v24; // eax
  unsigned int v25; // r15d
  signed int v26; // eax
  CMsmqVssWriter *v27; // rcx
  signed int v28; // eax
  int v29; // eax
  HANDLE hFile[5]; // [rsp+30h] [rbp-28h] BYREF
  CMsmqVssWriter *Buffer; // [rsp+A0h] [rbp+48h] BYREF
  wchar_t *v32; // [rsp+A8h] [rbp+50h]
  DWORD nLengthNeeded; // [rsp+B0h] [rbp+58h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+60h] BYREF

  v32 = a2;
  Buffer = this;
  v2 = MmAllocate(0x20Au);
  hFile[1] = v2;
  HttpPhysicalDirectory = CMsmqVssWriter::GetHttpPhysicalDirectory(v3, (wchar_t *)v2, v4);
  v6 = HttpPhysicalDirectory;
  if ( HttpPhysicalDirectory < 0 )
  {
    LogMsgHR(HttpPhysicalDirectory, (wchar_t *)L"writer/mqwriter", 0xDFCu);
    free(v2);
    return v6;
  }
  nLengthNeeded = 0;
  if ( GetFileSecurityW((LPCWSTR)v2, 4u, 0, 0, &nLengthNeeded) )
  {
    v9 = nLengthNeeded;
    if ( !nLengthNeeded )
    {
      free(v2);
      return 0;
    }
  }
  else
  {
    if ( GetLastError() != 122 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (v6 & 0x80000000) != 0 )
        LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", 0xE10u);
      free(v2);
      return v6;
    }
    v9 = nLengthNeeded;
  }
  v10 = (unsigned __int8 *)MmAllocate(v9);
  hFile[2] = v10;
  if ( GetFileSecurityW((LPCWSTR)v2, 4u, v10, nLengthNeeded, &nLengthNeeded) )
  {
    v13 = 2 * nLengthNeeded + 1;
    v15 = MmAllocate(saturated_mul(v13, 2u));
    hFile[3] = v15;
    v16 = (wchar_t *)v15;
    for ( i = 0; i < nLengthNeeded && v13; ++i )
    {
      v18 = StringCchPrintfW(v16, v13, L"%02x", v10[i]);
      v19 = v18;
      if ( v18 < 0 )
      {
        LogMsgHR(v18, (wchar_t *)L"writer/mqwriter", 0xE38u);
        free(v15);
        free(v10);
        free(v2);
        return v19;
      }
      v16 += 2;
      v13 -= 2;
    }
    hFile[0] = 0;
    v20 = CMsmqVssWriter::PrepareBackupFile(v14, v32, L"msmqwebacl.bkp", hFile);
    v22 = v20;
    if ( v20 < 0 )
    {
      LogMsgHR(v20, (wchar_t *)L"writer/mqwriter", 0xE4Cu);
      CHandle::~CHandle((CHandle *)hFile);
      free(v15);
      free(v10);
      free(v2);
      return (unsigned int)v22;
    }
    v23 = hFile[0];
    v24 = CMsmqVssWriter::WriteStringToFile(v21, hFile[0], L"https");
    v25 = v24;
    if ( v24 < 0 )
    {
      LogMsgHR(v24, (wchar_t *)L"writer/mqwriter", 0xE60u);
      CHandle::~CHandle((CHandle *)hFile);
      free(v15);
      free(v10);
      free(v2);
      return v25;
    }
    NumberOfBytesWritten = 0;
    LOWORD(Buffer) = 61;
    if ( !WriteFile(v23, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      v26 = GetLastError();
      v22 = v26;
      if ( v26 > 0 )
        v22 = (unsigned __int16)v26 | 0x80070000;
      if ( v22 < 0 )
        LogMsgHR(v22, (wchar_t *)L"writer/mqwriter", 0xE74u);
LABEL_36:
      CHandle::~CHandle((CHandle *)hFile);
      free(v15);
      free(v10);
      free(v2);
      return (unsigned int)v22;
    }
    if ( !WriteFile(v23, v15, 4 * nLengthNeeded, &NumberOfBytesWritten, 0) )
    {
      v28 = GetLastError();
      v22 = v28;
      if ( v28 > 0 )
        v22 = (unsigned __int16)v28 | 0x80070000;
      if ( v22 < 0 )
        LogMsgHR(v22, (wchar_t *)L"writer/mqwriter", 0xE88u);
      goto LABEL_36;
    }
    v29 = CMsmqVssWriter::WriteStringToFile(v27, v23, L"\r\n");
    v22 = v29;
    if ( v29 < 0 )
    {
      LogMsgHR(v29, (wchar_t *)L"writer/mqwriter", 0xE9Cu);
      CHandle::~CHandle((CHandle *)hFile);
      free(v15);
      free(v10);
      free(v2);
      return (unsigned int)v22;
    }
    CHandle::~CHandle((CHandle *)hFile);
    free(v15);
    free(v10);
    free(v2);
    return 0;
  }
  v11 = GetLastError();
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 < 0 )
    LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0xE24u);
  free(v10);
  free(v2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18008eec0  mov     [rsp-40h+arg_8], rdx
0x18008eec5  mov     [rsp-40h+Buffer], rcx
0x18008eeca  push    rbp
0x18008eecb  push    rbx
0x18008eecc  push    rsi
0x18008eecd  push    rdi
0x18008eece  push    r12
0x18008eed0  push    r13
0x18008eed2  push    r14
0x18008eed4  push    r15
0x18008eed6  mov     rbp, rsp
0x18008eed9  sub     rsp, 58h
0x18008eedd  mov     ecx, 20Ah; unsigned __int64
0x18008eee2  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008eee7  mov     rbx, rax
0x18008eeea  mov     [rbp+var_20], rax
0x18008eeee  mov     rdx, rax; wchar_t *
0x18008eef1  call    ?GetHttpPhysicalDirectory@CMsmqVssWriter@@AEAAJPEA_WK@Z; CMsmqVssWriter::GetHttpPhysicalDirectory(wchar_t *,ulong)
0x18008eef6  mov     edi, eax
0x18008eef8  xor     r12d, r12d
0x18008eefb  test    eax, eax
0x18008eefd  jns     short loc_18008EF25
0x18008eeff  mov     r8d, 0DFCh; unsigned __int16
0x18008ef05  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ef0c  mov     ecx, eax; int
0x18008ef0e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ef13  nop
0x18008ef14  mov     rcx, rbx; Block
0x18008ef17  call    cs:__imp_free
0x18008ef1d  nop
0x18008ef1e  mov     eax, edi
0x18008ef20  jmp     loc_18008F323
0x18008ef25  mov     [rbp+nLengthNeeded], r12d
0x18008ef29  lea     rax, [rbp+nLengthNeeded]
0x18008ef2d  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18008ef32  xor     r9d, r9d; nLength
0x18008ef35  xor     r8d, r8d; pSecurityDescriptor
0x18008ef38  lea     edx, [r9+4]; RequestedInformation
0x18008ef3c  mov     rcx, rbx; lpFileName
0x18008ef3f  call    cs:__imp_GetFileSecurityW
0x18008ef45  test    eax, eax
0x18008ef47  jnz     loc_18008F00E
0x18008ef4d  call    cs:__imp_GetLastError
0x18008ef53  cmp     eax, 7Ah ; 'z'
0x18008ef56  jz      short loc_18008EF92
0x18008ef58  call    cs:__imp_GetLastError
0x18008ef5e  mov     edi, eax
0x18008ef60  test    eax, eax
0x18008ef62  jle     short loc_18008EF6D
0x18008ef64  movzx   edi, ax
0x18008ef67  or      edi, 80070000h
0x18008ef6d  test    edi, edi
0x18008ef6f  jns     short loc_18008EF86
0x18008ef71  mov     r8d, 0E10h; unsigned __int16
0x18008ef77  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ef7e  mov     ecx, edi; int
0x18008ef80  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ef85  nop
0x18008ef86  mov     rcx, rbx; Block
0x18008ef89  call    cs:__imp_free
0x18008ef8f  nop
0x18008ef90  jmp     short loc_18008EF1E
0x18008ef92  mov     eax, [rbp+nLengthNeeded]
0x18008ef95  mov     ecx, eax; unsigned __int64
0x18008ef97  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008ef9c  mov     rdi, rax
0x18008ef9f  mov     [rbp+var_18], rax
0x18008efa3  lea     rax, [rbp+nLengthNeeded]
0x18008efa7  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18008efac  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18008efb0  mov     r8, rdi; pSecurityDescriptor
0x18008efb3  mov     edx, 4; RequestedInformation
0x18008efb8  mov     rcx, rbx; lpFileName
0x18008efbb  call    cs:__imp_GetFileSecurityW
0x18008efc1  test    eax, eax
0x18008efc3  jnz     short loc_18008F024
0x18008efc5  call    cs:__imp_GetLastError
0x18008efcb  mov     esi, eax
0x18008efcd  test    eax, eax
0x18008efcf  jle     short loc_18008EFDA
0x18008efd1  movzx   esi, ax
0x18008efd4  or      esi, 80070000h
0x18008efda  test    esi, esi
0x18008efdc  jns     short loc_18008EFF3
0x18008efde  mov     r8d, 0E24h; unsigned __int16
0x18008efe4  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008efeb  mov     ecx, esi; int
0x18008efed  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008eff2  nop
0x18008eff3  mov     rcx, rdi; Block
0x18008eff6  call    cs:__imp_free
0x18008effc  nop
0x18008effd  mov     rcx, rbx; Block
0x18008f000  call    cs:__imp_free
0x18008f006  nop
0x18008f007  mov     eax, esi
0x18008f009  jmp     loc_18008F323
0x18008f00e  mov     eax, [rbp+nLengthNeeded]
0x18008f011  test    eax, eax
0x18008f013  jnz     short loc_18008EF95
0x18008f015  mov     rcx, rbx; Block
0x18008f018  call    cs:__imp_free
0x18008f01e  nop
0x18008f01f  jmp     loc_18008F321
0x18008f024  mov     eax, [rbp+nLengthNeeded]
0x18008f027  lea     r14d, ds:1[rax*2]
0x18008f02f  mov     ecx, r14d
0x18008f032  mov     eax, 2
0x18008f037  mul     rcx
0x18008f03a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008f041  cmovb   rax, rcx
0x18008f045  mov     rcx, rax; unsigned __int64
0x18008f048  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008f04d  mov     rsi, rax
0x18008f050  mov     [rbp+var_10], rax
0x18008f054  mov     r13, rax
0x18008f057  mov     r15d, r12d
0x18008f05a  cmp     r15d, [rbp+nLengthNeeded]
0x18008f05e  jnb     short loc_18008F0D2
0x18008f060  test    r14d, r14d
0x18008f063  jz      short loc_18008F0D2
0x18008f065  mov     eax, r15d
0x18008f068  movzx   r9d, byte ptr [rax+rdi]
0x18008f06d  mov     edx, r14d; unsigned __int64
0x18008f070  lea     r8, a02x; "%02x"
0x18008f077  mov     rcx, r13; wchar_t *
0x18008f07a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008f07f  mov     r12d, eax
0x18008f082  test    eax, eax
0x18008f084  js      short loc_18008F096
0x18008f086  add     r13, 4
0x18008f08a  add     r14d, 0FFFFFFFEh
0x18008f08e  inc     r15d
0x18008f091  xor     r12d, r12d
0x18008f094  jmp     short loc_18008F05A
0x18008f096  mov     r8d, 0E38h; unsigned __int16
0x18008f09c  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f0a3  mov     ecx, r12d; int
0x18008f0a6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f0ab  nop
0x18008f0ac  mov     rcx, rsi; Block
0x18008f0af  call    cs:__imp_free
0x18008f0b5  nop
0x18008f0b6  mov     rcx, rdi; Block
0x18008f0b9  call    cs:__imp_free
0x18008f0bf  nop
0x18008f0c0  mov     rcx, rbx; Block
0x18008f0c3  call    cs:__imp_free
0x18008f0c9  nop
0x18008f0ca  mov     eax, r12d
0x18008f0cd  jmp     loc_18008F323
0x18008f0d2  mov     [rbp+hFile], r12
0x18008f0d6  lea     r9, [rbp+hFile]; void **
0x18008f0da  lea     r8, aMsmqwebaclBkp; "msmqwebacl.bkp"
0x18008f0e1  mov     rdx, [rbp+arg_8]; wchar_t *
0x18008f0e5  call    ?PrepareBackupFile@CMsmqVssWriter@@AEAAJPEB_W0PEAPEAX@Z; CMsmqVssWriter::PrepareBackupFile(wchar_t const *,wchar_t const *,void * *)
0x18008f0ea  mov     r14d, eax
0x18008f0ed  test    eax, eax
0x18008f0ef  jns     short loc_18008F136
0x18008f0f1  mov     r8d, 0E4Ch; unsigned __int16
0x18008f0f7  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f0fe  mov     ecx, eax; int
0x18008f100  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f105  nop
0x18008f106  lea     rcx, [rbp+hFile]; this
0x18008f10a  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18008f10f  nop
0x18008f110  mov     rcx, rsi; Block
0x18008f113  call    cs:__imp_free
0x18008f119  nop
0x18008f11a  mov     rcx, rdi; Block
0x18008f11d  call    cs:__imp_free
0x18008f123  nop
0x18008f124  mov     rcx, rbx; Block
0x18008f127  call    cs:__imp_free
0x18008f12d  nop
0x18008f12e  mov     eax, r14d
0x18008f131  jmp     loc_18008F323
0x18008f136  lea     r8, aHttps_0; "https"
0x18008f13d  mov     r14, [rbp+hFile]
0x18008f141  mov     rdx, r14; void *
0x18008f144  call    ?WriteStringToFile@CMsmqVssWriter@@AEAAJPEAXPEB_W@Z; CMsmqVssWriter::WriteStringToFile(void *,wchar_t const *)
0x18008f149  mov     r15d, eax
0x18008f14c  test    eax, eax
0x18008f14e  jns     short loc_18008F195
0x18008f150  mov     r8d, 0E60h; unsigned __int16
0x18008f156  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f15d  mov     ecx, eax; int
0x18008f15f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f164  nop
0x18008f165  lea     rcx, [rbp+hFile]; this
0x18008f169  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18008f16e  nop
0x18008f16f  mov     rcx, rsi; Block
0x18008f172  call    cs:__imp_free
0x18008f178  nop
0x18008f179  mov     rcx, rdi; Block
0x18008f17c  call    cs:__imp_free
0x18008f182  nop
0x18008f183  mov     rcx, rbx; Block
0x18008f186  call    cs:__imp_free
0x18008f18c  nop
0x18008f18d  mov     eax, r15d
0x18008f190  jmp     loc_18008F323
0x18008f195  mov     [rbp+NumberOfBytesWritten], r12d
0x18008f199  mov     eax, 3Dh ; '='
0x18008f19e  mov     word ptr [rbp+Buffer], ax
0x18008f1a2  mov     [rsp+58h+lpnLengthNeeded], r12; lpOverlapped
0x18008f1a7  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008f1ab  lea     r8d, [rax-3Bh]; nNumberOfBytesToWrite
0x18008f1af  lea     rdx, [rbp+Buffer]; lpBuffer
0x18008f1b3  mov     rcx, r14; hFile
0x18008f1b6  call    cs:__imp_WriteFile
0x18008f1bc  test    eax, eax
0x18008f1be  jnz     short loc_18008F220
0x18008f1c0  call    cs:__imp_GetLastError
0x18008f1c6  mov     r14d, eax
0x18008f1c9  test    eax, eax
0x18008f1cb  jle     short loc_18008F1D8
0x18008f1cd  movzx   r14d, ax
0x18008f1d1  or      r14d, 80070000h
0x18008f1d8  test    r14d, r14d
0x18008f1db  jns     short loc_18008F1F3
0x18008f1dd  mov     r8d, 0E74h; unsigned __int16
0x18008f1e3  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f1ea  mov     ecx, r14d; int
0x18008f1ed  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f1f2  nop
0x18008f1f3  lea     rcx, [rbp+hFile]; this
0x18008f1f7  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18008f1fc  nop
0x18008f1fd  mov     rcx, rsi; Block
0x18008f200  call    cs:__imp_free
0x18008f206  nop
0x18008f207  mov     rcx, rdi; Block
0x18008f20a  call    cs:__imp_free
0x18008f210  nop
0x18008f211  mov     rcx, rbx; Block
0x18008f214  call    cs:__imp_free
0x18008f21a  nop
0x18008f21b  jmp     loc_18008F12E
0x18008f220  mov     r8d, [rbp+nLengthNeeded]
0x18008f224  shl     r8d, 2; nNumberOfBytesToWrite
0x18008f228  mov     [rsp+58h+lpnLengthNeeded], r12; lpOverlapped
0x18008f22d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008f231  mov     rdx, rsi; lpBuffer
0x18008f234  mov     rcx, r14; hFile
0x18008f237  call    cs:__imp_WriteFile
0x18008f23d  test    eax, eax
0x18008f23f  jnz     short loc_18008F2A1
0x18008f241  call    cs:__imp_GetLastError
0x18008f247  mov     r14d, eax
0x18008f24a  test    eax, eax
0x18008f24c  jle     short loc_18008F259
0x18008f24e  movzx   r14d, ax
0x18008f252  or      r14d, 80070000h
0x18008f259  test    r14d, r14d
0x18008f25c  jns     short loc_18008F274
0x18008f25e  mov     r8d, 0E88h; unsigned __int16
0x18008f264  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f26b  mov     ecx, r14d; int
0x18008f26e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f273  nop
0x18008f274  lea     rcx, [rbp+hFile]; this
0x18008f278  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18008f27d  nop
0x18008f27e  mov     rcx, rsi; Block
0x18008f281  call    cs:__imp_free
0x18008f287  nop
0x18008f288  mov     rcx, rdi; Block
0x18008f28b  call    cs:__imp_free
0x18008f291  nop
0x18008f292  mov     rcx, rbx; Block
0x18008f295  call    cs:__imp_free
0x18008f29b  nop
0x18008f29c  jmp     loc_18008F12E
0x18008f2a1  lea     r8, asc_18010500C; "\r\n"
0x18008f2a8  mov     rdx, r14; void *
0x18008f2ab  call    ?WriteStringToFile@CMsmqVssWriter@@AEAAJPEAXPEB_W@Z; CMsmqVssWriter::WriteStringToFile(void *,wchar_t const *)
0x18008f2b0  mov     r14d, eax
0x18008f2b3  test    eax, eax
0x18008f2b5  jns     short loc_18008F2F9
0x18008f2b7  mov     r8d, 0E9Ch; unsigned __int16
0x18008f2bd  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f2c4  mov     ecx, eax; int
0x18008f2c6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f2cb  nop
0x18008f2cc  lea     rcx, [rbp+hFile]; this
0x18008f2d0  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18008f2d5  nop
0x18008f2d6  mov     rcx, rsi; Block
0x18008f2d9  call    cs:__imp_free
0x18008f2df  nop
0x18008f2e0  mov     rcx, rdi; Block
0x18008f2e3  call    cs:__imp_free
0x18008f2e9  nop
0x18008f2ea  mov     rcx, rbx; Block
0x18008f2ed  call    cs:__imp_free
0x18008f2f3  nop
0x18008f2f4  jmp     loc_18008F12E
  ... truncated ...
```
