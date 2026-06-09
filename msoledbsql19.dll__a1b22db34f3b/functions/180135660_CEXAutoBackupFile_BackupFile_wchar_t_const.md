# CEXAutoBackupFile::BackupFile(wchar_t const *)

- ea: `0x180135660`
- end: `0x18013585a`
- name: `?BackupFile@CEXAutoBackupFile@@QEAAJPEB_W@Z`
- size: `506`
- prototype: `__int64 __fastcall(CEXAutoBackupFile *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800a2770`

## callees

- `0x180003d80`
- `0x180007050`
- `0x1800993b0`
- `0x180135660`
- `0x180135860`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801357aa`
- `KERNEL32!GetLastError` at `0x1801357aa`
- `KERNEL32!GetTempFileNameW` at `0x1801357a0`
- `KERNEL32!GetTempFileNameW` at `0x1801357a0`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x1801356dc`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x1801356dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEXAutoBackupFile::BackupFile(CEXAutoBackupFile *this, const wchar_t *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  unsigned __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  wchar_t *v10; // rcx
  signed int LastError; // eax
  signed int v12; // ecx
  wchar_t Drive[264]; // [rsp+50h] [rbp-648h] BYREF
  wchar_t PrefixString[256]; // [rsp+260h] [rbp-438h] BYREF
  wchar_t Dir[264]; // [rsp+460h] [rbp-238h] BYREF

  if ( *((_QWORD *)this + 2) && *((_QWORD *)this + 1) )
    return 2147500037LL;
  _wsplitpath_s(a2, Drive, 0x104u, Dir, 0x104u, PrefixString, 0x100u, 0, 0);
  result = StringCchCatW(Drive, 0x104u, Dir);
  if ( (int)result < 0 )
    goto LABEL_5;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 == -1 )
  {
    v8 = 0;
  }
  else
  {
    _mm_lfence();
    v7 = 2 * v6;
    if ( !is_mul_ok(v6, 2u) )
      v7 = -1;
    v8 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v7);
  }
  *((_QWORD *)this + 1) = v8;
  v9 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, 520);
  *((_QWORD *)this + 2) = v9;
  v10 = (wchar_t *)*((_QWORD *)this + 1);
  if ( !v10 || !v9 )
    goto LABEL_28;
  result = StringCchCopyW(v10, v6, a2);
  if ( (int)result < 0 )
  {
LABEL_5:
    _mm_lfence();
    return result;
  }
  if ( !GetTempFileNameW(Drive, PrefixString, 0, *((LPWSTR *)this + 2)) )
  {
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v12 = LastError;
    if ( v12 < 0 )
      goto LABEL_28;
  }
  if ( (int)CExFileOperation::FOCopyFile(this, *((LPCWSTR *)this + 1), *((const wchar_t **)this + 2), 0) < 0 )
  {
LABEL_28:
    if ( *((_QWORD *)this + 2) )
    {
      _mm_lfence();
      (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
      *((_QWORD *)this + 2) = 0;
    }
    if ( *((_QWORD *)this + 1) )
    {
      _mm_lfence();
      (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
      *((_QWORD *)this + 1) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180135660  mov     [rsp+arg_10], rbx
0x180135665  push    rbp
0x180135666  push    rsi
0x180135667  push    rdi
0x180135668  sub     rsp, 680h
0x18013566f  mov     rax, cs:__security_cookie
0x180135676  xor     rax, rsp
0x180135679  mov     [rsp+698h+var_28], rax
0x180135681  mov     rdi, rdx
0x180135684  mov     rbx, rcx
0x180135687  xor     ebp, ebp
0x180135689  cmp     [rcx+10h], rbp
0x18013568d  jz      short loc_18013569F
0x18013568f  cmp     [rcx+8], rbp
0x180135693  jz      short loc_18013569F
0x180135695  mov     eax, 80004005h
0x18013569a  jmp     loc_180135837
0x18013569f  mov     [rsp+698h+ExtCount], rbp; ExtCount
0x1801356a4  mov     [rsp+698h+Ext], rbp; Ext
0x1801356a9  mov     [rsp+698h+FilenameCount], 100h; FilenameCount
0x1801356b2  lea     rax, [rsp+698h+PrefixString]
0x1801356ba  mov     [rsp+698h+Filename], rax; Filename
0x1801356bf  mov     esi, 104h
0x1801356c4  mov     [rsp+698h+DirCount], rsi; DirCount
0x1801356c9  lea     r9, [rsp+698h+Dir]; Dir
0x1801356d1  mov     r8d, esi; DriveCount
0x1801356d4  lea     rdx, [rsp+698h+Drive]; Drive
0x1801356d9  mov     rcx, rdi; FullPath
0x1801356dc  call    cs:__imp__wsplitpath_s
0x1801356e2  lea     r8, [rsp+698h+Dir]; wchar_t *
0x1801356ea  mov     edx, esi; unsigned __int64
0x1801356ec  lea     rcx, [rsp+698h+Drive]; wchar_t *
0x1801356f1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1801356f6  test    eax, eax
0x1801356f8  jns     short loc_180135702
0x1801356fa  lfence
0x1801356fd  jmp     loc_180135837
0x180135702  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180135706  mov     rax, rcx
0x180135709  inc     rax
0x18013570c  cmp     [rdi+rax*2], bp
0x180135710  jnz     short loc_180135709
0x180135712  lea     rsi, [rax+1]
0x180135716  cmp     rax, rcx
0x180135719  jnb     short loc_180135746
0x18013571b  lfence
0x18013571e  mov     eax, 2
0x180135723  mul     rsi
0x180135726  mov     rdx, rax
0x180135729  cmovb   rdx, rcx
0x18013572d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135734  mov     rax, [rcx]
0x180135737  mov     rax, [rax+70h]
0x18013573b  call    cs:__guard_dispatch_icall_fptr
0x180135741  mov     rcx, rax
0x180135744  jmp     short loc_180135749
0x180135746  mov     rcx, rbp
0x180135749  mov     [rbx+8], rcx
0x18013574d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135754  mov     rax, [rcx]
0x180135757  mov     edx, 208h
0x18013575c  mov     rax, [rax+70h]
0x180135760  call    cs:__guard_dispatch_icall_fptr
0x180135766  nop
0x180135767  mov     [rbx+10h], rax
0x18013576b  mov     rcx, [rbx+8]; wchar_t *
0x18013576f  test    rcx, rcx
0x180135772  jz      short loc_1801357D9
0x180135774  test    rax, rax
0x180135777  jz      short loc_1801357D9
0x180135779  mov     r8, rdi; wchar_t *
0x18013577c  mov     rdx, rsi; unsigned __int64
0x18013577f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180135784  test    eax, eax
0x180135786  js      loc_1801356FA
0x18013578c  mov     r9, [rbx+10h]; lpTempFileName
0x180135790  xor     r8d, r8d; uUnique
0x180135793  lea     rdx, [rsp+698h+PrefixString]; lpPrefixString
0x18013579b  lea     rcx, [rsp+698h+Drive]; lpPathName
0x1801357a0  call    cs:__imp_GetTempFileNameW
0x1801357a6  test    eax, eax
0x1801357a8  jnz     short loc_1801357C2
0x1801357aa  call    cs:__imp_GetLastError
0x1801357b0  movzx   ecx, ax
0x1801357b3  or      ecx, 80070000h
0x1801357b9  test    eax, eax
0x1801357bb  cmovle  ecx, eax
0x1801357be  test    ecx, ecx
0x1801357c0  js      short loc_1801357D9
0x1801357c2  xor     r9d, r9d; bFailIfExists
0x1801357c5  mov     r8, [rbx+10h]; wchar_t *
0x1801357c9  mov     rdx, [rbx+8]; lpExistingFileName
0x1801357cd  mov     rcx, rbx; this
0x1801357d0  call    ?FOCopyFile@CExFileOperation@@QEAAJPEB_W0H@Z; CExFileOperation::FOCopyFile(wchar_t const *,wchar_t const *,int)
0x1801357d5  test    eax, eax
0x1801357d7  jns     short loc_180135835
0x1801357d9  cmp     [rbx+10h], rbp
0x1801357dd  jz      short loc_180135807
0x1801357df  lfence
0x1801357e2  mov     rdx, [rbx+10h]
0x1801357e6  test    rdx, rdx
0x1801357e9  jz      short loc_180135803
0x1801357eb  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1801357f2  mov     rax, [rcx]
0x1801357f5  mov     rax, [rax+80h]
0x1801357fc  call    cs:__guard_dispatch_icall_fptr
0x180135802  nop
0x180135803  mov     [rbx+10h], rbp
0x180135807  cmp     [rbx+8], rbp
0x18013580b  jz      short loc_180135835
0x18013580d  lfence
0x180135810  mov     rdx, [rbx+8]
0x180135814  test    rdx, rdx
0x180135817  jz      short loc_180135831
0x180135819  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135820  mov     rax, [rcx]
0x180135823  mov     rax, [rax+80h]
0x18013582a  call    cs:__guard_dispatch_icall_fptr
0x180135830  nop
0x180135831  mov     [rbx+8], rbp
0x180135835  xor     eax, eax
0x180135837  mov     rcx, [rsp+698h+var_28]
0x18013583f  xor     rcx, rsp; StackCookie
0x180135842  call    __security_check_cookie
0x180135847  mov     rbx, [rsp+698h+arg_10]
0x18013584f  add     rsp, 680h
0x180135856  pop     rdi
0x180135857  pop     rsi
0x180135858  pop     rbp
0x180135859  retn
```
