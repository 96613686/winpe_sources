# CIdentitySec::GetSidFromThreadOrProcess(CNtSid &)

- ea: `0x18008ec08`
- end: `0x18008edb6`
- name: `?GetSidFromThreadOrProcess@CIdentitySec@@AEAAJAEAVCNtSid@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(CIdentitySec *__hidden this, struct CNtSid *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f600`

## callees

- `0x180037120`
- `0x18008ec08`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008ec89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008ec89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008ec50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008ec50`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008ec98`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008ec98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008ec38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008ec38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ed8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ed8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ec5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ec6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008eca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ecd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ec5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ec6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008eca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ecd9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008eccf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008eccf`
- `wbemcomn!GetMemLogObject` at `0x18008ed2e`
- `wbemcomn!GetMemLogObject` at `0x18008ed2e`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18008ed24`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18008ed83`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18008ed24`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18008ed83`
- `wbemcomn!??4CNtSid@@QEAAAEAV0@AEBV0@@Z` at `0x18008ed0d`
- `wbemcomn!??4CNtSid@@QEAAAEAV0@AEBV0@@Z` at `0x18008ed0d`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18008ecff`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18008ecff`
- `wbemcomn!?IsValid@CNtSid@@QEAAHXZ` at `0x18008ed16`
- `wbemcomn!?IsValid@CNtSid@@QEAAHXZ` at `0x18008ed16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ed3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ed3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall CIdentitySec::GetSidFromThreadOrProcess(CIdentitySec *this, struct CNtSid *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v7; // rbx
  signed int v8; // eax
  unsigned int v9; // edi
  CMemoryLog *MemLogObject; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp-49h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-39h] BYREF
  HANDLE v14; // [rsp+50h] [rbp-29h]
  void *TokenInformation; // [rsp+60h] [rbp-19h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1309 && LastError != 1008 )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      GetLastError();
  }
  v7 = TokenHandle;
  v14 = TokenHandle;
  ReturnLength = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
  {
    CNtSid::CNtSid((CNtSid *)v13, TokenInformation);
    CNtSid::operator=(a2, v13);
    if ( CNtSid::IsValid(a2) )
    {
      CNtSid::~CNtSid((CNtSid *)v13);
      v9 = 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      v9 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids, 2147749894LL);
      }
      CNtSid::~CNtSid((CNtSid *)v13);
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  CloseHandle(v7);
  return v9;
}

```

## disassembly

```asm
0x18008ec08  mov     [rsp-8+arg_0], rbx
0x18008ec0d  mov     [rsp-8+arg_10], rdi
0x18008ec12  push    rbp
0x18008ec13  lea     rbp, [rsp-57h]
0x18008ec18  sub     rsp, 0D0h
0x18008ec1f  mov     rax, cs:__security_cookie
0x18008ec26  xor     rax, rsp
0x18008ec29  mov     [rbp+57h+var_10], rax
0x18008ec2d  mov     rdi, rdx
0x18008ec30  mov     [rbp+57h+TokenHandle], 0
0x18008ec38  call    cs:__imp_GetCurrentThread
0x18008ec3e  mov     rcx, rax; ThreadHandle
0x18008ec41  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18008ec45  mov     ebx, 8
0x18008ec4a  lea     r8d, [rbx-7]; OpenAsSelf
0x18008ec4e  mov     edx, ebx; DesiredAccess
0x18008ec50  call    cs:__imp_OpenThreadToken
0x18008ec56  test    eax, eax
0x18008ec58  jnz     short loc_18008ECA8
0x18008ec5a  call    cs:__imp_GetLastError
0x18008ec60  cmp     eax, 51Dh
0x18008ec65  jz      short loc_18008EC89
0x18008ec67  cmp     eax, 3F0h
0x18008ec6c  jz      short loc_18008EC89
0x18008ec6e  call    cs:__imp_GetLastError
0x18008ec74  test    eax, eax
0x18008ec76  jle     loc_18008ED95
0x18008ec7c  movzx   eax, ax
0x18008ec7f  or      eax, 80070000h
0x18008ec84  jmp     loc_18008ED95
0x18008ec89  call    cs:__imp_GetCurrentProcess
0x18008ec8f  mov     rcx, rax; ProcessHandle
0x18008ec92  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18008ec96  mov     edx, ebx; DesiredAccess
0x18008ec98  call    cs:__imp_OpenProcessToken
0x18008ec9e  test    eax, eax
0x18008eca0  jnz     short loc_18008ECA8
0x18008eca2  call    cs:__imp_GetLastError
0x18008eca8  mov     rbx, [rbp+57h+TokenHandle]
0x18008ecac  mov     [rbp+57h+var_80], rbx
0x18008ecb0  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18008ecb6  mov     [rbp+57h+var_98], r9d
0x18008ecba  lea     rax, [rbp+57h+var_98]
0x18008ecbe  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18008ecc3  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18008ecc7  lea     edx, [r9-57h]; TokenInformationClass
0x18008eccb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18008eccf  call    cs:__imp_GetTokenInformation
0x18008ecd5  test    eax, eax
0x18008ecd7  jnz     short loc_18008ECF7
0x18008ecd9  call    cs:__imp_GetLastError
0x18008ecdf  mov     edi, eax
0x18008ece1  test    eax, eax
0x18008ece3  jle     loc_18008ED8A
0x18008ece9  movzx   edi, ax
0x18008ecec  or      edi, 80070000h
0x18008ecf2  jmp     loc_18008ED8A
0x18008ecf7  mov     rdx, [rbp+57h+TokenInformation]
0x18008ecfb  lea     rcx, [rbp+57h+var_90]
0x18008ecff  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18008ed05  nop
0x18008ed06  lea     rdx, [rbp+57h+var_90]
0x18008ed0a  mov     rcx, rdi
0x18008ed0d  call    cs:__imp_??4CNtSid@@QEAAAEAV0@AEBV0@@Z; CNtSid::operator=(CNtSid const &)
0x18008ed13  mov     rcx, rdi
0x18008ed16  call    cs:__imp_?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18008ed1c  test    eax, eax
0x18008ed1e  jz      short loc_18008ED2E
0x18008ed20  lea     rcx, [rbp+57h+var_90]
0x18008ed24  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18008ed2a  xor     edi, edi
0x18008ed2c  jmp     short loc_18008ED8A
0x18008ed2e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008ed34  mov     edi, 80041006h
0x18008ed39  mov     edx, edi
0x18008ed3b  mov     rcx, rax
0x18008ed3e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008ed44  lea     rax, WPP_GLOBAL_Control
0x18008ed4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ed52  cmp     rcx, rax
0x18008ed55  jz      short loc_18008ED7F
0x18008ed57  test    byte ptr [rcx+1Ch], 1
0x18008ed5b  jz      short loc_18008ED7F
0x18008ed5d  cmp     byte ptr [rcx+19h], 2
0x18008ed61  jb      short loc_18008ED7F
0x18008ed63  mov     edx, 21h ; '!'
0x18008ed68  mov     r9d, 80041006h
0x18008ed6e  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008ed75  mov     rcx, [rcx+10h]
0x18008ed79  call    WPP_SF_d
0x18008ed7e  nop
0x18008ed7f  lea     rcx, [rbp+57h+var_90]
0x18008ed83  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18008ed89  nop
0x18008ed8a  mov     rcx, rbx; hObject
0x18008ed8d  call    cs:__imp_CloseHandle
0x18008ed93  mov     eax, edi
0x18008ed95  mov     rcx, [rbp+57h+var_10]
0x18008ed99  xor     rcx, rsp; StackCookie
0x18008ed9c  call    __security_check_cookie
0x18008eda1  lea     r11, [rsp+0D0h+var_s0]
0x18008eda9  mov     rbx, [r11+10h]
0x18008edad  mov     rdi, [r11+20h]
0x18008edb1  mov     rsp, r11
0x18008edb4  pop     rbp
0x18008edb5  retn
```
