# CflApi::SerializeTempUserAccountCredential

- ea: `0x180020040`
- end: `0x180020370`
- name: `CflApi::SerializeTempUserAccountCredential`
- size: `816`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020a54`

## callees

- `0x180002ef8`
- `0x1800067a4`
- `0x1800067c4`
- `0x180010700`
- `0x180011130`
- `0x1800132a8`
- `0x18001332c`
- `0x18001afc8`
- `0x18001f8e4`
- `0x180020040`
- `0x18002d89c`
- `0x18002dac8`
- `0x18002db94`
- `0x18002ddb8`
- `0x18002dffc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020092`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180020084`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180020101`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180020084`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180020101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002025f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002025f`

## string_xrefs

- `0x1800200c5`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020111`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020145`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18002029d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020330`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020348`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18002031c`: `Expected GetComputerNameExW to fail with ERROR_MORE_DATA (actual error: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CflApi::SerializeTempUserAccountCredential(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        LPWSTR *a3,
        _DWORD *a4)
{
  LPWSTR v8; // rdi
  DWORD LastError; // ebx
  int v10; // eax
  int NegoAuthPackageId; // ebx
  LPWSTR v12; // rsi
  const char *v13; // r9
  unsigned __int16 *v14; // r14
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int16 *i; // rax
  const void *v18; // rsi
  size_t v19; // r14
  int v20; // eax
  LPWSTR v21; // rbx
  int v23; // [rsp+20h] [rbp-B9h]
  char *v24; // [rsp+28h] [rbp-B1h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-A9h] BYREF
  DWORD nSize[2]; // [rsp+38h] [rbp-A1h] BYREF
  LPWSTR v27; // [rsp+40h] [rbp-99h]
  void *Src[2]; // [rsp+58h] [rbp-81h] BYREF
  struct _UNICODE_STRING v29; // [rsp+70h] [rbp-69h] BYREF
  __int128 v30; // [rsp+80h] [rbp-59h] BYREF
  _OWORD v31[2]; // [rsp+90h] [rbp-49h] BYREF
  _KERB_INTERACTIVE_UNLOCK_LOGON v32; // [rsp+B0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  *a3 = 0;
  *a4 = 0;
  v8 = 0;
  v27 = 0;
  nSize[0] = 0;
  LastError = 0;
  if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, 0, nSize) || (LastError = GetLastError(), LastError != 234) )
  {
    LODWORD(v24) = LastError;
    NegoAuthPackageId = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x563,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Expected GetComputerNameExW to fail with ERROR_MORE_DATA (actual error: %d)",
      v24);
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x539,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)NegoAuthPackageId,
      v23);
    return (unsigned int)NegoAuthPackageId;
  }
  lpBuffer = 0;
  v10 = CflApiNew::AllocBuffer_unsigned_short_(nSize[0], &lpBuffer);
  NegoAuthPackageId = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x565,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v10,
      v23);
    if ( lpBuffer )
      CflFreeBuffer(lpBuffer);
    goto LABEL_37;
  }
  v12 = lpBuffer;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, lpBuffer, nSize) )
  {
    NegoAuthPackageId = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x566,
                          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                          v13);
    if ( v12 )
      CflFreeBuffer(v12);
    if ( NegoAuthPackageId < 0 )
      goto LABEL_37;
    goto LABEL_10;
  }
  v8 = v12;
  v27 = v12;
  if ( !v12 || !a2 )
  {
LABEL_10:
    NegoAuthPackageId = -2147467261;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x545,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)NegoAuthPackageId,
      v23);
LABEL_31:
    if ( v8 )
      CflFreeBuffer(v8);
    return (unsigned int)NegoAuthPackageId;
  }
  *(_OWORD *)Src = 0;
  lpBuffer = 0;
  NegoAuthPackageId = CredProtectAlloc(a2, &lpBuffer);
  v14 = lpBuffer;
  if ( NegoAuthPackageId >= 0 )
  {
    memset_0(&v29, 0, 0x40u);
    NegoAuthPackageId = UnicodeStringStringHijack(v12, (struct _UNICODE_STRING *)&v29.Buffer);
    if ( NegoAuthPackageId >= 0 )
    {
      NegoAuthPackageId = UnicodeStringStringHijack(a1, (struct _UNICODE_STRING *)((char *)&v30 + 8));
      if ( NegoAuthPackageId >= 0 )
      {
        NegoAuthPackageId = UnicodeStringStringHijack(v14, (struct _UNICODE_STRING *)((char *)v31 + 8));
        if ( NegoAuthPackageId >= 0 )
        {
          *(_DWORD *)&v29.Length = 2;
          *(struct _UNICODE_STRING *)&v32.Logon.MessageType = v29;
          *(_OWORD *)&v32.Logon.LogonDomainName.Buffer = v30;
          *(_OWORD *)&v32.Logon.UserName.Buffer = v31[0];
          *(_OWORD *)&v32.Logon.Password.Buffer = v31[1];
          NegoAuthPackageId = KerbInteractiveUnlockLogonPack(&v32, (unsigned __int8 **)&Src[1], (unsigned int *)Src + 1);
          if ( NegoAuthPackageId >= 0 )
          {
            nSize[0] = 0;
            NegoAuthPackageId = GetNegoAuthPackageId(nSize);
          }
        }
      }
    }
    if ( v14 )
    {
      if ( *v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        v16 = 2 * v15;
        for ( i = v14; v16; --v16 )
        {
          *(_BYTE *)i = 0;
          i = (unsigned __int16 *)((char *)i + 1);
        }
      }
    }
  }
  CoTaskMemFree(v14);
  if ( NegoAuthPackageId < 0 )
    goto LABEL_11;
  v18 = Src[1];
  *(void **)nSize = Src[1];
  v19 = HIDWORD(Src[0]);
  lpBuffer = 0;
  v20 = CflApiNew::AllocBuffer_unsigned_char_(HIDWORD(Src[0]));
  NegoAuthPackageId = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54C,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v20,
      v23);
    if ( lpBuffer )
      CflSecureFreeBuffer(lpBuffer);
    wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>(nSize);
    goto LABEL_31;
  }
  v21 = lpBuffer;
  memcpy_0(lpBuffer, v18, v19);
  *a3 = v21;
  *a4 = v19;
  wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>(nSize);
  if ( v8 )
    CflFreeBuffer(v8);
  return 0;
}

```

## disassembly

```asm
0x180020040  push    rbp
0x180020042  push    rbx
0x180020043  push    rsi
0x180020044  push    rdi
0x180020045  push    r12
0x180020047  push    r13
0x180020049  push    r14
0x18002004b  push    r15
0x18002004d  lea     rbp, [rsp-1Fh]
0x180020052  sub     rsp, 0F8h
0x180020059  mov     r13, r9
0x18002005c  mov     r12, r8
0x18002005f  mov     r14, rdx
0x180020062  mov     r15, rcx
0x180020065  xor     esi, esi
0x180020067  mov     [r8], rsi
0x18002006a  mov     [r9], esi
0x18002006d  mov     edi, esi
0x18002006f  mov     [rsp+130h+var_F0], rsi
0x180020074  mov     [rsp+130h+nSize], esi
0x180020078  mov     ebx, esi
0x18002007a  lea     r8, [rsp+130h+nSize]; nSize
0x18002007f  xor     edx, edx; lpBuffer
0x180020081  lea     ecx, [rsi+4]; NameType
0x180020084  call    cs:__imp_GetComputerNameExW
0x18002008a  test    eax, eax
0x18002008c  jnz     loc_180020314
0x180020092  call    cs:__imp_GetLastError
0x180020098  mov     ebx, eax
0x18002009a  cmp     eax, 0EAh
0x18002009f  jnz     loc_180020314
0x1800200a5  mov     [rsp+130h+lpBuffer], rsi
0x1800200aa  mov     ecx, [rsp+130h+nSize]
0x1800200ae  lea     rdx, [rsp+130h+lpBuffer]
0x1800200b3  call    CflApiNew__AllocBuffer_unsigned_short_
0x1800200b8  mov     ebx, eax
0x1800200ba  test    eax, eax
0x1800200bc  jns     short loc_1800200EF
0x1800200be  mov     rcx, [rbp+5Fh]; this
0x1800200c2  mov     r9d, eax; char *
0x1800200c5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800200cc  mov     edx, 565h; void *
0x1800200d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200d6  nop
0x1800200d7  mov     rcx, [rsp+130h+lpBuffer]; hMem
0x1800200dc  test    rcx, rcx
0x1800200df  jz      loc_180020341
0x1800200e5  call    CflFreeBuffer
0x1800200ea  jmp     loc_180020341
0x1800200ef  lea     r8, [rsp+130h+nSize]; nSize
0x1800200f4  mov     rsi, [rsp+130h+lpBuffer]
0x1800200f9  mov     rdx, rsi; lpBuffer
0x1800200fc  mov     ecx, 4; NameType
0x180020101  call    cs:__imp_GetComputerNameExW
0x180020107  xor     ecx, ecx
0x180020109  test    eax, eax
0x18002010b  jnz     short loc_18002015B
0x18002010d  mov     rcx, [rbp+5Fh]; this
0x180020111  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180020118  mov     edx, 566h; void *
0x18002011d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020122  mov     ebx, eax
0x180020124  test    rsi, rsi
0x180020127  jz      short loc_180020131
0x180020129  mov     rcx, rsi; hMem
0x18002012c  call    CflFreeBuffer
0x180020131  test    ebx, ebx
0x180020133  js      loc_180020341
0x180020139  mov     ebx, 80004003h
0x18002013e  mov     rcx, [rbp+5Fh]; this
0x180020142  mov     r9d, ebx; char *
0x180020145  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002014c  mov     edx, 545h; void *
0x180020151  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020156  jmp     loc_1800202CA
0x18002015b  mov     rdi, rsi
0x18002015e  mov     [rsp+130h+var_F0], rsi
0x180020163  test    rsi, rsi
0x180020166  jz      short loc_180020139
0x180020168  test    r14, r14
0x18002016b  jz      short loc_180020139
0x18002016d  xorps   xmm0, xmm0
0x180020170  movups  xmmword ptr [rsp+130h+Src], xmm0
0x180020175  mov     [rsp+130h+lpBuffer], rcx
0x18002017a  lea     rdx, [rsp+130h+lpBuffer]; unsigned __int16 **
0x18002017f  mov     rcx, r14; unsigned __int16 *
0x180020182  call    ?CredProtectAlloc@@YAJPEBGPEAPEAG@Z; CredProtectAlloc(ushort const *,ushort * *)
0x180020187  mov     ebx, eax
0x180020189  mov     r14, [rsp+130h+lpBuffer]
0x18002018e  test    eax, eax
0x180020190  js      loc_18002025C
0x180020196  xor     edx, edx; Val
0x180020198  lea     r8d, [rdx+40h]; Size
0x18002019c  lea     rcx, [rbp+57h+var_C0]; void *
0x1800201a0  call    memset_0
0x1800201a5  lea     rdx, [rbp+57h+var_C0.Buffer]; struct _UNICODE_STRING *
0x1800201a9  mov     rcx, rsi; unsigned __int16 *
0x1800201ac  call    ?UnicodeStringStringHijack@@YAJPEBGPEAU_UNICODE_STRING@@@Z; UnicodeStringStringHijack(ushort const *,_UNICODE_STRING *)
0x1800201b1  mov     ebx, eax
0x1800201b3  xor     esi, esi
0x1800201b5  test    eax, eax
0x1800201b7  js      short loc_18002022B
0x1800201b9  lea     rdx, [rbp+57h+var_A8]; struct _UNICODE_STRING *
0x1800201bd  mov     rcx, r15; unsigned __int16 *
0x1800201c0  call    ?UnicodeStringStringHijack@@YAJPEBGPEAU_UNICODE_STRING@@@Z; UnicodeStringStringHijack(ushort const *,_UNICODE_STRING *)
0x1800201c5  mov     ebx, eax
0x1800201c7  test    eax, eax
0x1800201c9  js      short loc_18002022B
0x1800201cb  lea     rdx, [rbp+57h+var_98]; struct _UNICODE_STRING *
0x1800201cf  mov     rcx, r14; unsigned __int16 *
0x1800201d2  call    ?UnicodeStringStringHijack@@YAJPEBGPEAU_UNICODE_STRING@@@Z; UnicodeStringStringHijack(ushort const *,_UNICODE_STRING *)
0x1800201d7  mov     ebx, eax
0x1800201d9  test    eax, eax
0x1800201db  js      short loc_18002022B
0x1800201dd  mov     dword ptr [rbp+57h+var_C0.Length], 2
0x1800201e4  movaps  xmm0, xmmword ptr [rbp+57h+var_C0.Length]
0x1800201e8  movaps  xmmword ptr [rbp+57h+var_80.Logon.MessageType], xmm0
0x1800201ec  movaps  xmm1, xmmword ptr [rbp-59h]
0x1800201f0  movaps  xmmword ptr [rbp+57h+var_80.Logon.LogonDomainName.Buffer], xmm1
0x1800201f4  movaps  xmm0, xmmword ptr [rbp-49h]
0x1800201f8  movaps  xmmword ptr [rbp+57h+var_80.Logon.UserName.Buffer], xmm0
0x1800201fc  movaps  xmm1, xmmword ptr [rbp+57h+var_98.Buffer]
0x180020200  movaps  xmmword ptr [rbp+57h+var_80.Logon.Password.Buffer], xmm1
0x180020204  lea     r8, [rbp+57h+Src+4]; unsigned int *
0x180020208  lea     rdx, [rbp+57h+Src+8]; unsigned __int8 **
0x18002020c  lea     rcx, [rbp+57h+var_80]; struct _KERB_INTERACTIVE_UNLOCK_LOGON *
0x180020210  call    ?KerbInteractiveUnlockLogonPack@@YAJAEBU_KERB_INTERACTIVE_UNLOCK_LOGON@@PEAPEAEPEAK@Z; KerbInteractiveUnlockLogonPack(_KERB_INTERACTIVE_UNLOCK_LOGON const &,uchar * *,ulong *)
0x180020215  mov     ebx, eax
0x180020217  test    eax, eax
0x180020219  js      short loc_18002022B
0x18002021b  mov     [rsp+130h+nSize], esi
0x18002021f  lea     rcx, [rsp+130h+nSize]; unsigned int *
0x180020224  call    ?GetNegoAuthPackageId@@YAJPEAK@Z; GetNegoAuthPackageId(ulong *)
0x180020229  mov     ebx, eax
0x18002022b  test    r14, r14
0x18002022e  jz      short loc_18002025C
0x180020230  cmp     [r14], si
0x180020234  jz      short loc_18002025C
0x180020236  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002023a  inc     rax
0x18002023d  cmp     [r14+rax*2], si
0x180020242  jnz     short loc_18002023A
0x180020244  lea     rcx, [rax+rax]
0x180020248  mov     rax, r14
0x18002024b  test    rcx, rcx
0x18002024e  jz      short loc_18002025C
0x180020250  mov     [rax], sil
0x180020253  inc     rax
0x180020256  sub     rcx, 1
0x18002025a  jnz     short loc_180020250
0x18002025c  mov     rcx, r14; pv
0x18002025f  call    cs:__imp_CoTaskMemFree
0x180020265  test    ebx, ebx
0x180020267  js      loc_18002013E
0x18002026d  mov     rsi, [rbp+57h+Src+8]
0x180020271  mov     qword ptr [rsp+130h+nSize], rsi
0x180020276  mov     r14d, dword ptr [rbp+57h+Src+4]
0x18002027a  mov     [rsp+130h+lpBuffer], 0
0x180020283  lea     rdx, [rsp+130h+lpBuffer]
0x180020288  mov     ecx, r14d; uBytes
0x18002028b  call    CflApiNew__AllocBuffer_unsigned_char_
0x180020290  mov     ebx, eax
0x180020292  test    eax, eax
0x180020294  jns     short loc_1800202DD
0x180020296  mov     rcx, [rbp+5Fh]; this
0x18002029a  mov     r9d, eax; char *
0x18002029d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800202a4  mov     edx, 54Ch; void *
0x1800202a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800202ae  nop
0x1800202af  mov     rcx, [rsp+130h+lpBuffer]; hMem
0x1800202b4  test    rcx, rcx
0x1800202b7  jz      short loc_1800202BF
0x1800202b9  call    CflSecureFreeBuffer
0x1800202be  nop
0x1800202bf  lea     rcx, [rsp+130h+nSize]
0x1800202c4  call    ??1?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>::~unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>(void)
0x1800202c9  nop
0x1800202ca  test    rdi, rdi
0x1800202cd  jz      loc_18002035A
0x1800202d3  mov     rcx, rdi; hMem
0x1800202d6  call    CflFreeBuffer
0x1800202db  jmp     short loc_18002035A
0x1800202dd  mov     r8, r14; Size
0x1800202e0  mov     rdx, rsi; Src
0x1800202e3  mov     rbx, [rsp+130h+lpBuffer]
0x1800202e8  mov     rcx, rbx; void *
0x1800202eb  call    memcpy_0
0x1800202f0  mov     [r12], rbx
0x1800202f4  mov     [r13+0], r14d
0x1800202f8  lea     rcx, [rsp+130h+nSize]
0x1800202fd  call    ??1?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>::~unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>(void)
0x180020302  nop
0x180020303  test    rdi, rdi
0x180020306  jz      short loc_180020310
0x180020308  mov     rcx, rdi; hMem
0x18002030b  call    CflFreeBuffer
0x180020310  xor     eax, eax
0x180020312  jmp     short loc_18002035C
0x180020314  mov     rcx, [rbp+5Fh]; this
0x180020318  mov     dword ptr [rsp+130h+var_108], ebx; char *
0x18002031c  lea     rax, aExpectedGetcom; "Expected GetComputerNameExW to fail wit"...
0x180020323  mov     qword ptr [rsp+130h+var_110], rax; int
0x180020328  mov     ebx, 8000FFFFh
0x18002032d  mov     r9d, ebx; char *
0x180020330  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180020337  mov     edx, 563h; void *
0x18002033c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020341  mov     rcx, [rbp+5Fh]; this
0x180020345  mov     r9d, ebx; char *
0x180020348  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002034f  mov     edx, 539h; void *
0x180020354  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020359  nop
0x18002035a  mov     eax, ebx
0x18002035c  add     rsp, 0F8h
0x180020363  pop     r15
0x180020365  pop     r14
0x180020367  pop     r13
0x180020369  pop     r12
0x18002036b  pop     rdi
0x18002036c  pop     rsi
0x18002036d  pop     rbx
0x18002036e  pop     rbp
0x18002036f  retn
```
