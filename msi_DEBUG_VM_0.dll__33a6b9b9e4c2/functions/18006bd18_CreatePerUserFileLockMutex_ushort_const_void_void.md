# CreatePerUserFileLockMutex(ushort const *,void *,void * &)

- ea: `0x18006bd18`
- end: `0x18006c03e`
- name: `?CreatePerUserFileLockMutex@@YAKPEBGPEAXAEAPEAX@Z`
- size: `806`
- prototype: `unsigned int(const unsigned __int16 *, void *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801c0700`

## callees

- `0x180022120`
- `0x1800252a8`
- `0x18006bd18`
- `0x18006c044`
- `0x18006c0cc`
- `0x18006c17c`
- `0x180121310`
- `0x180156d80`
- `0x18016fde8`
- `0x1801afce0`
- `0x1801afd60`
- `0x1801afd94`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x18006bf04`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18006bf04`
- `KERNEL32!CreateMutexW` at `0x18006bf98`
- `KERNEL32!CreateMutexW` at `0x18006bf98`
- `KERNEL32!GetLastError` at `0x18006bd97`
- `KERNEL32!GetLastError` at `0x18006bf0e`
- `KERNEL32!GetLastError` at `0x18006bfc3`
- `KERNEL32!GetLastError` at `0x18006bd97`
- `KERNEL32!GetLastError` at `0x18006bf0e`
- `KERNEL32!GetLastError` at `0x18006bfc3`
- `KERNEL32!GlobalFree` at `0x18006bfb8`
- `KERNEL32!GlobalFree` at `0x18006bfdd`
- `KERNEL32!GlobalFree` at `0x18006bfb8`
- `KERNEL32!GlobalFree` at `0x18006bfdd`
- `KERNEL32!GetFileTime` at `0x18006bd8d`
- `KERNEL32!GetFileTime` at `0x18006bd8d`

## string_xrefs

- `0x18006bd57`: `Global\MSILOG_`

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
0x18006bd18  mov     [rsp-8+arg_0], rbx
0x18006bd1d  push    rbp
0x18006bd1e  push    rsi
0x18006bd1f  push    rdi
0x18006bd20  push    r14
0x18006bd22  push    r15
0x18006bd24  lea     rbp, [rsp-240h]
0x18006bd2c  sub     rsp, 340h
0x18006bd33  mov     rax, cs:__security_cookie
0x18006bd3a  xor     rax, rsp
0x18006bd3d  mov     [rbp+260h+var_30], rax
0x18006bd44  mov     r14, r8
0x18006bd47  mov     rbx, rdx
0x18006bd4a  mov     rdi, rcx
0x18006bd4d  xor     r15d, r15d
0x18006bd50  mov     [r8], r15
0x18006bd53  lea     rcx, [rbp+260h+var_222]; void *
0x18006bd57  movups  xmm0, xmmword ptr cs:aGlobalMsilog; "Global\\MSILOG_"
0x18006bd5e  xor     edx, edx; Val
0x18006bd60  mov     r8d, 1EAh; Size
0x18006bd66  movups  xmm1, xmmword ptr cs:aGlobalMsilog+0Eh; "MSILOG_"
0x18006bd6d  movaps  xmmword ptr [rbp+260h+Name], xmm0
0x18006bd71  movups  xmmword ptr [rbp+260h+Name+0Eh], xmm1
0x18006bd75  call    memset_0
0x18006bd7a  xor     r9d, r9d; lpLastWriteTime
0x18006bd7d  mov     qword ptr [rsp+360h+CreationTime.dwLowDateTime], r15
0x18006bd82  xor     r8d, r8d; lpLastAccessTime
0x18006bd85  lea     rdx, [rsp+360h+CreationTime]; lpCreationTime
0x18006bd8a  mov     rcx, rbx; hFile
0x18006bd8d  call    cs:__imp_GetFileTime
0x18006bd93  test    eax, eax
0x18006bd95  jnz     short loc_18006BDA2
0x18006bd97  call    cs:__imp_GetLastError
0x18006bd9d  jmp     loc_18006C018
0x18006bda2  mov     eax, [rsp+360h+CreationTime.dwHighDateTime]
0x18006bda6  lea     r8, a08xX; "%08x%x"
0x18006bdad  mov     r9d, [rsp+360h+CreationTime.dwLowDateTime]
0x18006bdb2  lea     rcx, [rbp+260h+var_224]; unsigned __int16 *
0x18006bdb6  mov     edx, 0F6h; unsigned __int64
0x18006bdbb  mov     [rsp+360h+nSubAuthority2], eax
0x18006bdbf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bdc4  test    eax, eax
0x18006bdc6  js      loc_18006C018
0x18006bdcc  test    rdi, rdi
0x18006bdcf  jz      loc_18006C011
0x18006bdd5  mov     r9d, 7FFFh
0x18006bddb  mov     rax, rdi
0x18006bdde  mov     edx, r9d
0x18006bde1  mov     ebx, 2
0x18006bde6  cmp     [rax], r15w
0x18006bdea  jz      short loc_18006BDF5
0x18006bdec  add     rax, rbx
0x18006bdef  sub     rdx, 1
0x18006bdf3  jnz     short loc_18006BDE6
0x18006bdf5  mov     rax, rdx
0x18006bdf8  mov     r10d, 80070057h
0x18006bdfe  neg     rax
0x18006be01  mov     rax, rdx
0x18006be04  sbb     ecx, ecx
0x18006be06  sub     r9, rdx
0x18006be09  not     ecx
0x18006be0b  and     ecx, r10d
0x18006be0e  neg     rax
0x18006be11  sbb     r8, r8
0x18006be14  and     r8, r9
0x18006be17  test    rdx, rdx
0x18006be1a  jz      loc_18006C016
0x18006be20  mov     r11d, 104h
0x18006be26  lea     rax, [rbp+260h+Name]
0x18006be2a  mov     r9d, r11d
0x18006be2d  cmp     [rax], r15w
0x18006be31  jz      short loc_18006BE3C
0x18006be33  add     rax, rbx
0x18006be36  sub     r9, 1
0x18006be3a  jnz     short loc_18006BE2D
0x18006be3c  mov     rax, r9
0x18006be3f  mov     rcx, r9
0x18006be42  neg     rax
0x18006be45  sbb     eax, eax
0x18006be47  sub     r11, r9
0x18006be4a  not     eax
0x18006be4c  and     eax, r10d
0x18006be4f  neg     rcx
0x18006be52  sbb     rdx, rdx
0x18006be55  and     rdx, r11
0x18006be58  test    r9, r9
0x18006be5b  jz      loc_18006C018
0x18006be61  jmp     short loc_18006BE8B
0x18006be63  cmp     rdx, 103h
0x18006be6a  jnb     short loc_18006BE90
0x18006be6c  dec     r8
0x18006be6f  cmp     word ptr [rdi+r8*2], 5Ch ; '\'
0x18006be75  jnz     short loc_18006BE7E
0x18006be77  mov     eax, 5Fh ; '_'
0x18006be7c  jmp     short loc_18006BE83
0x18006be7e  movzx   eax, word ptr [rdi+r8*2]
0x18006be83  mov     [rbp+rdx*2+260h+Name], ax
0x18006be88  inc     rdx
0x18006be8b  test    r8, r8
0x18006be8e  jnz     short loc_18006BE63
0x18006be90  add     rdx, rdx
0x18006be93  cmp     rdx, 208h
0x18006be9a  jnb     loc_18006C00B
0x18006bea0  mov     [rbp+rdx+260h+Name], r15w
0x18006bea6  lea     rdi, [rsp+360h+var_2F8]
0x18006beab  mov     dword ptr [rbp+260h+pIdentifierAuthority.Value], r15d
0x18006beaf  mov     rsi, rbx
0x18006beb2  mov     word ptr [rbp+260h+pIdentifierAuthority.Value+4], 500h
0x18006beb8  mov     rcx, rdi; this
0x18006bebb  call    ??0CSIDAccess@@QEAA@XZ; CSIDAccess::CSIDAccess(void)
0x18006bec0  add     rdi, 18h
0x18006bec4  sub     rsi, 1
0x18006bec8  jnz     short loc_18006BEB8
0x18006beca  lea     rcx, [rsp+360h+var_2F8]
0x18006becf  call    ??ICSIDPointer@@QEAAPEAPEAU_SID@@XZ; CSIDPointer::operator&(void)
0x18006bed4  mov     [rsp+360h+pSid], rax; pSid
0x18006bed9  lea     r8d, [rsi+12h]; nSubAuthority0
0x18006bedd  mov     [rsp+360h+nSubAuthority7], r15d; nSubAuthority7
0x18006bee2  lea     rcx, [rbp+260h+pIdentifierAuthority]; pIdentifierAuthority
0x18006bee6  mov     [rsp+360h+nSubAuthority6], r15d; nSubAuthority6
0x18006beeb  xor     r9d, r9d; nSubAuthority1
0x18006beee  mov     [rsp+360h+nSubAuthority5], r15d; nSubAuthority5
0x18006bef3  mov     dl, 1; nSubAuthorityCount
0x18006bef5  mov     [rsp+360h+nSubAuthority4], r15d; nSubAuthority4
0x18006befa  mov     [rsp+360h+nSubAuthority3], r15d; nSubAuthority3
0x18006beff  mov     [rsp+360h+nSubAuthority2], r15d; nSubAuthority2
0x18006bf04  call    cs:__imp_AllocateAndInitializeSid
0x18006bf0a  test    eax, eax
0x18006bf0c  jnz     short loc_18006BF33
0x18006bf0e  call    cs:__imp_GetLastError
0x18006bf14  mov     esi, eax
0x18006bf16  lea     rdi, [rbp+260h+var_2C8]
0x18006bf1a  sub     rdi, 18h
0x18006bf1e  mov     rcx, rdi; this
0x18006bf21  call    ??1CSIDAccess@@QEAA@XZ; CSIDAccess::~CSIDAccess(void)
0x18006bf26  sub     rbx, 1
0x18006bf2a  jnz     short loc_18006BF1A
0x18006bf2c  mov     eax, esi
0x18006bf2e  jmp     loc_18006C018
0x18006bf33  mov     esi, 48h ; 'H'
0x18006bf38  lea     rax, [rbp+260h+var_290]
0x18006bf3c  lea     rcx, [rbp+260h+hMem]
0x18006bf40  mov     [rbp+260h+var_298], esi
0x18006bf43  mov     [rbp+260h+hMem], rax
0x18006bf47  mov     [rbp+260h+var_294], esi
0x18006bf4a  call    ?GetCurrentUserSID@@YAKAEAV?$CAPITempBufferRef@E@@@Z; GetCurrentUserSID(CAPITempBufferRef<uchar> &)
0x18006bf4f  mov     edi, eax
0x18006bf51  test    eax, eax
0x18006bf53  jnz     short loc_18006BFD4
0x18006bf55  mov     rdx, [rbp+260h+hMem]
0x18006bf59  lea     rcx, [rbp+260h+var_2E0]
0x18006bf5d  call    ??4CSIDPointer@@QEAAAEAV0@PEAU_SID@@@Z; CSIDPointer::operator=(_SID *)
0x18006bf62  mov     eax, 10000000h
0x18006bf67  mov     [rbp+260h+var_2D8], r15b
0x18006bf6b  lea     r9, [rsp+360h+var_2F8]; struct CSIDAccess *
0x18006bf70  mov     [rsp+360h+var_2E8], eax
0x18006bf74  xor     edx, edx; void *
0x18006bf76  mov     [rbp+260h+var_2D0], eax
0x18006bf79  lea     rcx, [rbp+260h+var_2C8]; this
0x18006bf7d  mov     [rsp+360h+nSubAuthority2], ebx; int
0x18006bf81  call    ??0CSecurityDescription@@QEAA@PEAX0PEAUCSIDAccess@@H@Z; CSecurityDescription::CSecurityDescription(void *,void *,CSIDAccess *,int)
0x18006bf86  lea     rcx, [rbp+260h+var_2C8]; this
0x18006bf8a  call    ?SecurityAttributes@CSecurityDescription@@QEAAQEAU_SECURITY_ATTRIBUTES@@XZ; CSecurityDescription::SecurityAttributes(void)
0x18006bf8f  mov     rcx, rax; lpMutexAttributes
0x18006bf92  lea     r8, [rbp+260h+Name]; lpName
0x18006bf96  xor     edx, edx; bInitialOwner
0x18006bf98  call    cs:__imp_CreateMutexW
0x18006bf9e  mov     [r14], rax
0x18006bfa1  test    rax, rax
0x18006bfa4  jz      short loc_18006BFC3
0x18006bfa6  lea     rcx, [rbp+260h+var_2C8]; this
0x18006bfaa  call    ??1CSecurityDescription@@QEAA@XZ; CSecurityDescription::~CSecurityDescription(void)
0x18006bfaf  cmp     [rbp+260h+var_298], esi
0x18006bfb2  jle     short loc_18006BFBE
0x18006bfb4  mov     rcx, [rbp+260h+hMem]; hMem
0x18006bfb8  call    cs:__imp_GlobalFree
0x18006bfbe  mov     edi, r15d
0x18006bfc1  jmp     short loc_18006BFE3
0x18006bfc3  call    cs:__imp_GetLastError
0x18006bfc9  lea     rcx, [rbp+260h+var_2C8]; this
0x18006bfcd  mov     edi, eax
0x18006bfcf  call    ??1CSecurityDescription@@QEAA@XZ; CSecurityDescription::~CSecurityDescription(void)
0x18006bfd4  cmp     [rbp+260h+var_298], esi
0x18006bfd7  jle     short loc_18006BFE3
0x18006bfd9  mov     rcx, [rbp+260h+hMem]; hMem
0x18006bfdd  call    cs:__imp_GlobalFree
0x18006bfe3  lea     rax, [rbp+260h+var_290]
0x18006bfe7  mov     [rbp+260h+var_298], esi
0x18006bfea  lea     r9, ??1CSIDAccess@@QEAA@XZ; void (*)(void *)
0x18006bff1  mov     [rbp+260h+hMem], rax
0x18006bff5  mov     r8, rbx; unsigned __int64
0x18006bff8  lea     rcx, [rsp+360h+var_2F8]; void *
0x18006bffd  mov     edx, 18h; unsigned __int64
0x18006c002  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18006c007  mov     eax, edi
0x18006c009  jmp     short loc_18006C018
0x18006c00b  call    __report_rangecheckfailure
0x18006c011  mov     ecx, 80070057h
0x18006c016  mov     eax, ecx
0x18006c018  mov     rcx, [rbp+260h+var_30]
0x18006c01f  xor     rcx, rsp; StackCookie
0x18006c022  call    __security_check_cookie
0x18006c027  mov     rbx, [rsp+360h+arg_0]
0x18006c02f  add     rsp, 340h
0x18006c036  pop     r15
0x18006c038  pop     r14
0x18006c03a  pop     rdi
0x18006c03b  pop     rsi
0x18006c03c  pop     rbp
0x18006c03d  retn
```
