# CLocalConfigProvider::_Init(void)

- ea: `0x1800e93d8`
- end: `0x1800e957b`
- name: `?_Init@CLocalConfigProvider@@AEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e8b88`
- `0x1800e8d10`

## callees

- `0x18009b290`
- `0x1800a1ea4`
- `0x1800e93d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e94ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e94ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e943b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e94c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e943b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e94c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e954f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e954f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e9404`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e9404`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800e94a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800e94a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e9433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e94b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e9433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e94b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800e9506`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800e9506`

## string_xrefs

- `0x1800e952d`: `Initialized registry provider, path = %s`
- `0x1800e953a`: `CLocalConfigProvider::_Init`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocalConfigProvider::_Init(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r15
  HKEY *phkResult; // r14
  HKEY Ptr; // rsi
  DWORD LastError; // ebx
  const CHAR *v6; // rbx
  const CHAR *v7; // rdi
  struct CPersistenceLocation *v8; // rax
  LSTATUS Key; // eax
  DWORD v10; // ebx
  const CHAR *v11; // rdi
  struct CPersistenceLocation *v12; // rax
  signed int v13; // edi
  const char *v14; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = this + 16;
  AcquireSRWLockExclusive(this + 16);
  try
  {
    phkResult = (HKEY *)&this[17];
    Ptr = (HKEY)this[17].Ptr;
    if ( LOBYTE(this[11].Ptr) )
    {
      if ( Ptr )
      {
        LastError = GetLastError();
        RegCloseKey(Ptr);
        SetLastError(LastError);
      }
      *phkResult = 0;
      v6 = (const CHAR *)&this[12];
      v7 = v6;
      if ( *((_QWORD *)v6 + 3) > 0xFu )
        v7 = *(const CHAR **)v6;
      v8 = CPersistenceLocation::Instance();
      Key = RegCreateKeyExA(
              (HKEY)(-(__int64)(*((_BYTE *)v8 + 160) != 0) - 2147483645),
              v7,
              0,
              0,
              0,
              3u,
              0,
              phkResult,
              0);
    }
    else
    {
      if ( Ptr )
      {
        v10 = GetLastError();
        RegCloseKey(Ptr);
        SetLastError(v10);
      }
      *phkResult = 0;
      v6 = (const CHAR *)&this[12];
      v11 = v6;
      if ( *((_QWORD *)v6 + 3) > 0xFu )
        v11 = *(const CHAR **)v6;
      v12 = CPersistenceLocation::Instance();
      Key = RegOpenKeyExA((HKEY)(-(__int64)(*((_BYTE *)v12 + 160) != 0) - 2147483645), v11, 0, 3u, phkResult);
    }
    v13 = (unsigned __int16)Key | 0x80070000;
    if ( Key <= 0 )
      v13 = Key;
    if ( v13 >= 0 )
    {
      if ( *((_QWORD *)v6 + 3) > 0xFu )
        v6 = *(const CHAR **)v6;
      LogMessage(5u, "CLocalConfigProvider::_Init", 0xBAu, "Initialized registry provider, path = %s", v6);
    }
    ReleaseSRWLockExclusive(v2);
    result = (unsigned int)v13;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC0,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\LocalConfigProvider.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800e93d8  mov     rax, rsp
0x1800e93db  mov     [rax+10h], rbx
0x1800e93df  mov     [rax+18h], rsi
0x1800e93e3  push    rdi
0x1800e93e4  push    r14
0x1800e93e6  push    r15
0x1800e93e8  sub     rsp, 70h
0x1800e93ec  mov     rdi, rcx
0x1800e93ef  xorps   xmm0, xmm0
0x1800e93f2  movups  xmmword ptr [rax-30h], xmm0
0x1800e93f6  lea     r15, [rcx+80h]
0x1800e93fd  mov     [rax-30h], r15
0x1800e9401  mov     rcx, r15; SRWLock
0x1800e9404  call    cs:__imp_AcquireSRWLockExclusive
0x1800e940a  mov     [rsp+88h+var_28], 1
0x1800e940f  lea     r14, [rdi+88h]
0x1800e9416  mov     rsi, [r14]
0x1800e9419  cmp     byte ptr [rdi+58h], 0
0x1800e941d  jz      loc_1800E94A8
0x1800e9423  test    rsi, rsi
0x1800e9426  jz      short loc_1800E9441
0x1800e9428  call    cs:__imp_GetLastError
0x1800e942e  mov     ebx, eax
0x1800e9430  mov     rcx, rsi; hKey
0x1800e9433  call    cs:__imp_RegCloseKey
0x1800e9439  mov     ecx, ebx; dwErrCode
0x1800e943b  call    cs:__imp_SetLastError
0x1800e9441  mov     qword ptr [r14], 0
0x1800e9448  lea     rbx, [rdi+60h]
0x1800e944c  mov     rdi, rbx
0x1800e944f  cmp     qword ptr [rbx+18h], 0Fh
0x1800e9454  jbe     short loc_1800E9459
0x1800e9456  mov     rdi, [rbx]
0x1800e9459  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800e945e  mov     al, [rax+0A0h]
0x1800e9464  neg     al
0x1800e9466  sbb     rcx, rcx
0x1800e9469  add     rcx, 0FFFFFFFF80000003h; hKey
0x1800e9470  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800e9479  mov     [rsp+88h+phkResult], r14; phkResult
0x1800e947e  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800e9487  mov     [rsp+88h+samDesired], 3; samDesired
0x1800e948f  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800e9497  xor     r9d, r9d; lpClass
0x1800e949a  xor     r8d, r8d; Reserved
0x1800e949d  mov     rdx, rdi; lpSubKey
0x1800e94a0  call    cs:__imp_RegCreateKeyExA
0x1800e94a6  jmp     short loc_1800E950C
0x1800e94a8  test    rsi, rsi
0x1800e94ab  jz      short loc_1800E94C6
0x1800e94ad  call    cs:__imp_GetLastError
0x1800e94b3  mov     ebx, eax
0x1800e94b5  mov     rcx, rsi; hKey
0x1800e94b8  call    cs:__imp_RegCloseKey
0x1800e94be  mov     ecx, ebx; dwErrCode
0x1800e94c0  call    cs:__imp_SetLastError
0x1800e94c6  mov     qword ptr [r14], 0
0x1800e94cd  lea     rbx, [rdi+60h]
0x1800e94d1  mov     rdi, rbx
0x1800e94d4  cmp     qword ptr [rbx+18h], 0Fh
0x1800e94d9  jbe     short loc_1800E94DE
0x1800e94db  mov     rdi, [rbx]
0x1800e94de  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800e94e3  mov     al, [rax+0A0h]
0x1800e94e9  neg     al
0x1800e94eb  sbb     rcx, rcx
0x1800e94ee  add     rcx, 0FFFFFFFF80000003h; hKey
0x1800e94f5  mov     qword ptr [rsp+88h+dwOptions], r14; phkResult
0x1800e94fa  mov     r9d, 3; samDesired
0x1800e9500  xor     r8d, r8d; ulOptions
0x1800e9503  mov     rdx, rdi; lpSubKey
0x1800e9506  call    cs:__imp_RegOpenKeyExA
0x1800e950c  movzx   edi, ax
0x1800e950f  or      edi, 80070000h
0x1800e9515  test    eax, eax
0x1800e9517  cmovle  edi, eax
0x1800e951a  test    edi, edi
0x1800e951c  js      short loc_1800E954C
0x1800e951e  cmp     qword ptr [rbx+18h], 0Fh
0x1800e9523  jbe     short loc_1800E9528
0x1800e9525  mov     rbx, [rbx]
0x1800e9528  mov     qword ptr [rsp+88h+dwOptions], rbx
0x1800e952d  lea     r9, aInitializedReg; "Initialized registry provider, path = %"...
0x1800e9534  mov     r8d, 0BAh; unsigned int
0x1800e953a  lea     rdx, aClocalconfigpr; "CLocalConfigProvider::_Init"
0x1800e9541  mov     ecx, 5; unsigned __int8
0x1800e9546  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800e954b  nop
0x1800e954c  mov     rcx, r15; SRWLock
0x1800e954f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e9555  mov     eax, edi
0x1800e9557  jmp     short loc_1800E9564
0x1800e9559  mov     eax, 8007000Eh
0x1800e955e  jmp     short loc_1800E9564
0x1800e9560  mov     eax, [rsp+88h+var_38]
0x1800e9564  lea     r11, [rsp+88h+var_18]
0x1800e9569  mov     rbx, [r11+28h]
0x1800e956d  mov     rsi, [r11+30h]
0x1800e9571  mov     rsp, r11
0x1800e9574  pop     r15
0x1800e9576  pop     r14
0x1800e9578  pop     rdi
0x1800e9579  retn
```
