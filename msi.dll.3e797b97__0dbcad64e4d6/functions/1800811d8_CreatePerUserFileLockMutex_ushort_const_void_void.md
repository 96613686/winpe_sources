# CreatePerUserFileLockMutex(ushort const *,void *,void * &)

- ea: `0x1800811d8`
- end: `0x180081533`
- name: `?CreatePerUserFileLockMutex@@YAKPEBGPEAXAEAPEAX@Z`
- size: `859`
- prototype: `unsigned int(const unsigned __int16 *, void *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801c8bd8`

## callees

- `0x180010ac0`
- `0x18001386c`
- `0x1800811d8`
- `0x1800817f8`
- `0x180092280`
- `0x1800924b8`
- `0x180122110`
- `0x18015c794`
- `0x180175f88`
- `0x1801b7920`
- `0x1801b79a0`
- `0x1801b79dc`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x1800813d0`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800813d0`
- `KERNEL32!CreateMutexW` at `0x180081474`
- `KERNEL32!CreateMutexW` at `0x180081474`
- `KERNEL32!GetLastError` at `0x18008125d`
- `KERNEL32!GetLastError` at `0x1800813e0`
- `KERNEL32!GetLastError` at `0x1800814ab`
- `KERNEL32!GetLastError` at `0x18008125d`
- `KERNEL32!GetLastError` at `0x1800813e0`
- `KERNEL32!GetLastError` at `0x1800814ab`
- `KERNEL32!GlobalFree` at `0x18008149a`
- `KERNEL32!GlobalFree` at `0x1800814cb`
- `KERNEL32!GlobalFree` at `0x18008149a`
- `KERNEL32!GlobalFree` at `0x1800814cb`
- `KERNEL32!GetFileTime` at `0x18008124d`
- `KERNEL32!GetFileTime` at `0x18008124d`

## string_xrefs

- `0x180081217`: `Global\MSILOG_`

## pseudocode

```c
signed int __fastcall CreatePerUserFileLockMutex(const unsigned __int16 *a1, void *a2, void **a3)
{
  signed int result; // eax
  const unsigned __int16 *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rbx
  unsigned int v10; // ecx
  __int64 v11; // r8
  WCHAR *v12; // rax
  __int64 v13; // r9
  unsigned __int64 v14; // rdx
  WCHAR v15; // ax
  unsigned __int64 v16; // rdx
  CSIDAccess *v17; // rdi
  __int64 v18; // rsi
  PSID *pSid; // rax
  DWORD LastError; // esi
  CSIDAccess *v21; // rdi
  int CurrentUserSID; // edi
  void *v23; // r8
  struct _SECURITY_ATTRIBUTES *v24; // rax
  HANDLE MutexW; // rax
  struct _FILETIME CreationTime; // [rsp+60h] [rbp-A0h] BYREF
  PSID v27[2]; // [rsp+68h] [rbp-98h] BYREF
  int v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[16]; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+90h] [rbp-70h]
  _BYTE v31[32]; // [rsp+98h] [rbp-68h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  HGLOBAL hMem; // [rsp+C0h] [rbp-40h] BYREF
  int v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+CCh] [rbp-34h]
  _BYTE v36[80]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Name[14]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v38; // [rsp+13Ch] [rbp+3Ch] BYREF
  _BYTE v39[498]; // [rsp+13Eh] [rbp+3Eh] BYREF

  *a3 = 0;
  wcscpy(Name, L"GlobalMSILOG_");
  memset_0(v39, 0, 0x1EAu);
  CreationTime = 0;
  if ( !GetFileTime(a2, &CreationTime, 0, 0) )
    return GetLastError();
  result = StringCchPrintfW(&v38, 0xF6u, L"%08x%x", CreationTime.dwLowDateTime, CreationTime.dwHighDateTime);
  if ( result < 0 )
    return result;
  if ( !a1 )
    return -2147024809;
  v7 = a1;
  v8 = 0x7FFF;
  v9 = 2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v10 = v8 == 0 ? 0x80070057 : 0;
  v11 = (0x7FFF - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    return v10;
  v12 = Name;
  v13 = 260;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v13;
  }
  while ( v13 );
  result = v13 == 0 ? 0x80070057 : 0;
  v14 = (260 - v13) & -(__int64)(v13 != 0);
  if ( v13 )
  {
    while ( v11 && v14 < 0x103 )
    {
      if ( a1[--v11] == 92 )
        v15 = 95;
      else
        v15 = a1[v11];
      Name[v14++] = v15;
    }
    v16 = v14;
    if ( v16 >= 260 )
      _report_rangecheckfailure(-v13);
    Name[v16] = 0;
    v17 = (CSIDAccess *)v27;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    v18 = 2;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    do
    {
      CSIDAccess::CSIDAccess(v17);
      v17 = (CSIDAccess *)((char *)v17 + 24);
      --v18;
    }
    while ( v18 );
    pSid = (PSID *)CSIDPointer::operator&(v27);
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, pSid) )
    {
      LastError = GetLastError();
      v21 = (CSIDAccess *)v31;
      do
      {
        v21 = (CSIDAccess *)((char *)v21 - 24);
        CSIDAccess::~CSIDAccess(v21);
        --v9;
      }
      while ( v9 );
      return LastError;
    }
    v34 = 72;
    hMem = v36;
    v35 = 72;
    CurrentUserSID = GetCurrentUserSID((__int64)&hMem);
    if ( !CurrentUserSID )
    {
      CSIDPointer::operator=(v29, hMem);
      v29[8] = 0;
      v28 = 0x10000000;
      v30 = 0x10000000;
      CSecurityDescription::CSecurityDescription((CSecurityDescription *)v31, 0, v23, v27, 2);
      v24 = CSecurityDescription::SecurityAttributes((CSecurityDescription *)v31);
      MutexW = CreateMutexW(v24, 0, Name);
      *a3 = MutexW;
      if ( MutexW )
      {
        CSecurityDescription::~CSecurityDescription((CSecurityDescription *)v31);
        if ( v34 > 72 )
          GlobalFree(hMem);
        CurrentUserSID = 0;
LABEL_35:
        v34 = 72;
        hMem = v36;
        `vector destructor iterator'(v27, 0x18u, 2u, (void (*)(void *))CSIDAccess::~CSIDAccess);
        return CurrentUserSID;
      }
      CurrentUserSID = GetLastError();
      CSecurityDescription::~CSecurityDescription((CSecurityDescription *)v31);
    }
    if ( v34 > 72 )
      GlobalFree(hMem);
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x1800811d8  mov     [rsp-8+arg_0], rbx
0x1800811dd  push    rbp
0x1800811de  push    rsi
0x1800811df  push    rdi
0x1800811e0  push    r14
0x1800811e2  push    r15
0x1800811e4  lea     rbp, [rsp-240h]
0x1800811ec  sub     rsp, 340h
0x1800811f3  mov     rax, cs:__security_cookie
0x1800811fa  xor     rax, rsp
0x1800811fd  mov     [rbp+260h+var_30], rax
0x180081204  mov     r14, r8
0x180081207  mov     rbx, rdx
0x18008120a  mov     rdi, rcx
0x18008120d  xor     r15d, r15d
0x180081210  mov     [r8], r15
0x180081213  lea     rcx, [rbp+260h+var_222]; void *
0x180081217  movups  xmm0, xmmword ptr cs:aGlobalMsilog; "Global\\MSILOG_"
0x18008121e  xor     edx, edx; Val
0x180081220  mov     r8d, 1EAh; Size
0x180081226  movups  xmm1, xmmword ptr cs:aGlobalMsilog+0Eh; "MSILOG_"
0x18008122d  movaps  xmmword ptr [rbp+260h+Name], xmm0
0x180081231  movups  xmmword ptr [rbp+260h+Name+0Eh], xmm1
0x180081235  call    memset_0
0x18008123a  xor     r9d, r9d; lpLastWriteTime
0x18008123d  mov     qword ptr [rsp+360h+CreationTime.dwLowDateTime], r15
0x180081242  xor     r8d, r8d; lpLastAccessTime
0x180081245  lea     rdx, [rsp+360h+CreationTime]; lpCreationTime
0x18008124a  mov     rcx, rbx; hFile
0x18008124d  call    cs:__imp_GetFileTime
0x180081254  nop     dword ptr [rax+rax+00h]
0x180081259  test    eax, eax
0x18008125b  jnz     short loc_18008126E
0x18008125d  call    cs:__imp_GetLastError
0x180081264  nop     dword ptr [rax+rax+00h]
0x180081269  jmp     loc_18008150C
0x18008126e  mov     eax, [rsp+360h+CreationTime.dwHighDateTime]
0x180081272  lea     r8, a08xX; "%08x%x"
0x180081279  mov     r9d, [rsp+360h+CreationTime.dwLowDateTime]
0x18008127e  lea     rcx, [rbp+260h+var_224]; unsigned __int16 *
0x180081282  mov     edx, 0F6h; unsigned __int64
0x180081287  mov     [rsp+360h+nSubAuthority2], eax
0x18008128b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180081290  test    eax, eax
0x180081292  js      loc_18008150C
0x180081298  test    rdi, rdi
0x18008129b  jz      loc_180081505
0x1800812a1  mov     r9d, 7FFFh
0x1800812a7  mov     rax, rdi
0x1800812aa  mov     edx, r9d
0x1800812ad  mov     ebx, 2
0x1800812b2  cmp     [rax], r15w
0x1800812b6  jz      short loc_1800812C1
0x1800812b8  add     rax, rbx
0x1800812bb  sub     rdx, 1
0x1800812bf  jnz     short loc_1800812B2
0x1800812c1  mov     rax, rdx
0x1800812c4  mov     r10d, 80070057h
0x1800812ca  neg     rax
0x1800812cd  mov     rax, rdx
0x1800812d0  sbb     ecx, ecx
0x1800812d2  sub     r9, rdx
0x1800812d5  not     ecx
0x1800812d7  and     ecx, r10d
0x1800812da  neg     rax
0x1800812dd  sbb     r8, r8
0x1800812e0  and     r8, r9
0x1800812e3  test    rdx, rdx
0x1800812e6  jz      loc_18008150A
0x1800812ec  mov     r11d, 104h
0x1800812f2  lea     rax, [rbp+260h+Name]
0x1800812f6  mov     r9d, r11d
0x1800812f9  cmp     [rax], r15w
0x1800812fd  jz      short loc_180081308
0x1800812ff  add     rax, rbx
0x180081302  sub     r9, 1
0x180081306  jnz     short loc_1800812F9
0x180081308  mov     rax, r9
0x18008130b  mov     rcx, r9
0x18008130e  neg     rax
0x180081311  sbb     eax, eax
0x180081313  sub     r11, r9
0x180081316  not     eax
0x180081318  and     eax, r10d
0x18008131b  neg     rcx
0x18008131e  sbb     rdx, rdx
0x180081321  and     rdx, r11
0x180081324  test    r9, r9
0x180081327  jz      loc_18008150C
0x18008132d  jmp     short loc_180081357
0x18008132f  cmp     rdx, 103h
0x180081336  jnb     short loc_18008135C
0x180081338  dec     r8
0x18008133b  cmp     word ptr [rdi+r8*2], 5Ch ; '\'
0x180081341  jnz     short loc_18008134A
0x180081343  mov     eax, 5Fh ; '_'
0x180081348  jmp     short loc_18008134F
0x18008134a  movzx   eax, word ptr [rdi+r8*2]
0x18008134f  mov     [rbp+rdx*2+260h+Name], ax
0x180081354  inc     rdx
0x180081357  test    r8, r8
0x18008135a  jnz     short loc_18008132F
0x18008135c  add     rdx, rdx
0x18008135f  cmp     rdx, 208h
0x180081366  jnb     loc_1800814FF
0x18008136c  mov     [rbp+rdx+260h+Name], r15w
0x180081372  lea     rdi, [rsp+360h+var_2F8]
0x180081377  mov     dword ptr [rbp+260h+pIdentifierAuthority.Value], r15d
0x18008137b  mov     rsi, rbx
0x18008137e  mov     word ptr [rbp+260h+pIdentifierAuthority.Value+4], 500h
0x180081384  mov     rcx, rdi; this
0x180081387  call    ??0CSIDAccess@@QEAA@XZ; CSIDAccess::CSIDAccess(void)
0x18008138c  add     rdi, 18h
0x180081390  sub     rsi, 1
0x180081394  jnz     short loc_180081384
0x180081396  lea     rcx, [rsp+360h+var_2F8]
0x18008139b  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x1800813a0  mov     [rsp+360h+pSid], rax; pSid
0x1800813a5  lea     r8d, [rsi+12h]; nSubAuthority0
0x1800813a9  mov     [rsp+360h+nSubAuthority7], r15d; nSubAuthority7
0x1800813ae  lea     rcx, [rbp+260h+pIdentifierAuthority]; pIdentifierAuthority
0x1800813b2  mov     [rsp+360h+nSubAuthority6], r15d; nSubAuthority6
0x1800813b7  xor     r9d, r9d; nSubAuthority1
0x1800813ba  mov     [rsp+360h+nSubAuthority5], r15d; nSubAuthority5
0x1800813bf  mov     dl, 1; nSubAuthorityCount
0x1800813c1  mov     [rsp+360h+nSubAuthority4], r15d; nSubAuthority4
0x1800813c6  mov     [rsp+360h+nSubAuthority3], r15d; nSubAuthority3
0x1800813cb  mov     [rsp+360h+nSubAuthority2], r15d; nSubAuthority2
0x1800813d0  call    cs:__imp_AllocateAndInitializeSid
0x1800813d7  nop     dword ptr [rax+rax+00h]
0x1800813dc  test    eax, eax
0x1800813de  jnz     short loc_18008140B
0x1800813e0  call    cs:__imp_GetLastError
0x1800813e7  nop     dword ptr [rax+rax+00h]
0x1800813ec  mov     esi, eax
0x1800813ee  lea     rdi, [rbp+260h+var_2C8]
0x1800813f2  sub     rdi, 18h
0x1800813f6  mov     rcx, rdi; this
0x1800813f9  call    ??1CSIDAccess@@QEAA@XZ; CSIDAccess::~CSIDAccess(void)
0x1800813fe  sub     rbx, 1
0x180081402  jnz     short loc_1800813F2
0x180081404  mov     eax, esi
0x180081406  jmp     loc_18008150C
0x18008140b  mov     esi, 48h ; 'H'
0x180081410  lea     rax, [rbp+260h+var_290]
0x180081414  lea     rcx, [rbp+260h+hMem]
0x180081418  mov     [rbp+260h+var_298], esi
0x18008141b  mov     [rbp+260h+hMem], rax
0x18008141f  mov     [rbp+260h+var_294], esi
0x180081422  call    ?GetCurrentUserSID@@YAKAEAV?$CAPITempBufferRef@E@@@Z; GetCurrentUserSID(CAPITempBufferRef<uchar> &)
0x180081427  mov     edi, eax
0x180081429  test    eax, eax
0x18008142b  jnz     loc_1800814C2
0x180081431  mov     rdx, [rbp+260h+hMem]
0x180081435  lea     rcx, [rbp+260h+var_2E0]
0x180081439  call    ??4CSIDPointer@@QEAAAEAV0@PEAU_SID@@@Z; CSIDPointer::operator=(_SID *)
0x18008143e  mov     eax, 10000000h
0x180081443  mov     [rbp+260h+var_2D8], r15b
0x180081447  lea     r9, [rsp+360h+var_2F8]; struct CSIDAccess *
0x18008144c  mov     [rsp+360h+var_2E8], eax
0x180081450  xor     edx, edx; void *
0x180081452  mov     [rbp+260h+var_2D0], eax
0x180081455  lea     rcx, [rbp+260h+var_2C8]; this
0x180081459  mov     [rsp+360h+nSubAuthority2], ebx; int
0x18008145d  call    ??0CSecurityDescription@@QEAA@PEAX0PEAUCSIDAccess@@H@Z; CSecurityDescription::CSecurityDescription(void *,void *,CSIDAccess *,int)
0x180081462  lea     rcx, [rbp+260h+var_2C8]; this
0x180081466  call    ?SecurityAttributes@CSecurityDescription@@QEAAQEAU_SECURITY_ATTRIBUTES@@XZ; CSecurityDescription::SecurityAttributes(void)
0x18008146b  mov     rcx, rax; lpMutexAttributes
0x18008146e  lea     r8, [rbp+260h+Name]; lpName
0x180081472  xor     edx, edx; bInitialOwner
0x180081474  call    cs:__imp_CreateMutexW
0x18008147b  nop     dword ptr [rax+rax+00h]
0x180081480  mov     [r14], rax
0x180081483  test    rax, rax
0x180081486  jz      short loc_1800814AB
0x180081488  lea     rcx, [rbp+260h+var_2C8]; this
0x18008148c  call    ??1CSecurityDescription@@QEAA@XZ; CSecurityDescription::~CSecurityDescription(void)
0x180081491  cmp     [rbp+260h+var_298], esi
0x180081494  jle     short loc_1800814A6
0x180081496  mov     rcx, [rbp+260h+hMem]; hMem
0x18008149a  call    cs:__imp_GlobalFree
0x1800814a1  nop     dword ptr [rax+rax+00h]
0x1800814a6  mov     edi, r15d
0x1800814a9  jmp     short loc_1800814D7
0x1800814ab  call    cs:__imp_GetLastError
0x1800814b2  nop     dword ptr [rax+rax+00h]
0x1800814b7  lea     rcx, [rbp+260h+var_2C8]; this
0x1800814bb  mov     edi, eax
0x1800814bd  call    ??1CSecurityDescription@@QEAA@XZ; CSecurityDescription::~CSecurityDescription(void)
0x1800814c2  cmp     [rbp+260h+var_298], esi
0x1800814c5  jle     short loc_1800814D7
0x1800814c7  mov     rcx, [rbp+260h+hMem]; hMem
0x1800814cb  call    cs:__imp_GlobalFree
0x1800814d2  nop     dword ptr [rax+rax+00h]
0x1800814d7  lea     rax, [rbp+260h+var_290]
0x1800814db  mov     [rbp+260h+var_298], esi
0x1800814de  lea     r9, ??1CSIDAccess@@QEAA@XZ; void (*)(void *)
0x1800814e5  mov     [rbp+260h+hMem], rax
0x1800814e9  mov     r8, rbx; unsigned __int64
0x1800814ec  lea     rcx, [rsp+360h+var_2F8]; void *
0x1800814f1  mov     edx, 18h; unsigned __int64
0x1800814f6  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800814fb  mov     eax, edi
0x1800814fd  jmp     short loc_18008150C
0x1800814ff  call    __report_rangecheckfailure
0x180081505  mov     ecx, 80070057h
0x18008150a  mov     eax, ecx
0x18008150c  mov     rcx, [rbp+260h+var_30]
0x180081513  xor     rcx, rsp; StackCookie
0x180081516  call    __security_check_cookie
0x18008151b  mov     rbx, [rsp+360h+arg_0]
0x180081523  add     rsp, 340h
0x18008152a  pop     r15
0x18008152c  pop     r14
0x18008152e  pop     rdi
0x18008152f  pop     rsi
0x180081530  pop     rbp
0x180081531  retn
```
