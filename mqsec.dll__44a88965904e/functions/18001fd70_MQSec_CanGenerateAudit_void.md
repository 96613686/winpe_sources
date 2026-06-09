# MQSec_CanGenerateAudit(void)

- ea: `0x18001fd70`
- end: `0x18002004a`
- name: `?MQSec_CanGenerateAudit@@YAHXZ`
- size: `730`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002036c`

## callees

- `0x1800041cc`
- `0x1800049ac`
- `0x1800049ec`
- `0x18001353c`
- `0x18001722c`
- `0x18001fd70`
- `0x180029fb8`

## import_xrefs

- `msvcrt!free` at `0x18001ff83`
- `msvcrt!free` at `0x18001fff6`
- `msvcrt!free` at `0x18001ff83`
- `msvcrt!free` at `0x18001fff6`
- `ADVAPI32!GetTokenInformation` at `0x18001fecb`
- `ADVAPI32!GetTokenInformation` at `0x18001ff43`
- `ADVAPI32!GetTokenInformation` at `0x18001fecb`
- `ADVAPI32!GetTokenInformation` at `0x18001ff43`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001fe5c`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18001fe5c`
- `ADVAPI32!OpenProcessToken` at `0x18001fdb6`
- `ADVAPI32!OpenProcessToken` at `0x18001fdb6`
- `KERNEL32!GetCurrentProcess` at `0x18001fda6`
- `KERNEL32!GetCurrentProcess` at `0x18001fda6`
- `KERNEL32!GetLastError` at `0x18001fdf7`
- `KERNEL32!GetLastError` at `0x18001fe66`
- `KERNEL32!GetLastError` at `0x18001fed1`
- `KERNEL32!GetLastError` at `0x18001fedc`
- `KERNEL32!GetLastError` at `0x18001ff4d`
- `KERNEL32!GetLastError` at `0x18001fdf7`
- `KERNEL32!GetLastError` at `0x18001fe66`
- `KERNEL32!GetLastError` at `0x18001fed1`
- `KERNEL32!GetLastError` at `0x18001fedc`
- `KERNEL32!GetLastError` at `0x18001ff4d`

## string_xrefs

- `0x18001fdd4`: `SeAuditPrivilege`
- `0x18001fe53`: `SeAuditPrivilege`
- `0x18001fe92`: `SeAuditPrivilege`
- `0x18001ffdc`: `SeAuditPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 MQSec_CanGenerateAudit(void)
{
  HANDLE CurrentProcess; // rax
  int v2; // eax
  PVOID *v3; // rcx
  DWORD LastError; // eax
  char v5; // al
  DWORD v6; // eax
  _DWORD *v7; // rbx
  DWORD v8; // eax
  __int64 i; // rdx
  unsigned int v10; // ebx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  struct _LUID Luid; // [rsp+70h] [rbp+40h] BYREF
  _DWORD *v14; // [rsp+78h] [rbp+48h]

  if ( dword_180043168 )
    return (unsigned int)dword_180043164;
  dword_180043168 = 1;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v2 = SetSpecificPrivilegeInAccessToken(TokenHandle, L"SeAuditPrivilege", 1, 0);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( v2 >= 0 )
      dword_180043164 = 1;
  }
  else
  {
    LastError = GetLastError();
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, LastError);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !dword_180043164 )
    goto LABEL_32;
  dword_180043164 = 0;
  Luid = 0;
  if ( LookupPrivilegeValueW(0, L"SeAuditPrivilege", &Luid) )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength);
    if ( GetLastError() != 122 )
    {
      v6 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 19, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, v6);
      goto LABEL_35;
    }
    v7 = MmAllocate(TokenInformationLength);
    v14 = v7;
    if ( !GetTokenInformation(TokenHandle, TokenPrivileges, v7, TokenInformationLength, &TokenInformationLength) )
    {
      v8 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 20, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, v8);
      free(v7);
      goto LABEL_35;
    }
    for ( i = 0; (unsigned int)i < *v7; i = (unsigned int)(i + 1) )
    {
      if ( v7[3 * i + 1] == Luid.LowPart && v7[3 * i + 2] == Luid.HighPart )
      {
        dword_180043164 = (v7[3 * i + 3] >> 1) & 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 32));
        break;
      }
    }
    free(v7);
    v3 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 268) & 4) != 0 )
      WPP_SF_d(v3[32], 22, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, (unsigned int)dword_180043164);
    goto LABEL_35;
  }
  v5 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 32), v5);
LABEL_35:
  v10 = dword_180043164;
  CHandle::~CHandle((CHandle *)&TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x18001fd70  push    rbp
0x18001fd72  push    rbx
0x18001fd73  push    rsi
0x18001fd74  push    r14
0x18001fd76  push    r15
0x18001fd78  mov     rbp, rsp
0x18001fd7b  sub     rsp, 30h
0x18001fd7f  cmp     cs:dword_180043168, 0
0x18001fd86  jz      short loc_18001FD93
0x18001fd88  mov     eax, cs:dword_180043164
0x18001fd8e  jmp     loc_18002003E
0x18001fd93  mov     esi, 1
0x18001fd98  mov     cs:dword_180043168, esi
0x18001fd9e  mov     [rbp+TokenHandle], 0
0x18001fda6  call    cs:__imp_GetCurrentProcess
0x18001fdac  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001fdb0  lea     edx, [rsi+27h]; DesiredAccess
0x18001fdb3  mov     rcx, rax; ProcessHandle
0x18001fdb6  call    cs:__imp_OpenProcessToken
0x18001fdbc  lea     r15, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001fdc3  lea     r14, WPP_GLOBAL_Control
0x18001fdca  test    eax, eax
0x18001fdcc  jz      short loc_18001FDF7
0x18001fdce  xor     r9d, r9d; int *
0x18001fdd1  mov     r8d, esi; int
0x18001fdd4  lea     rdx, aSeauditprivile; "SeAuditPrivilege"
0x18001fddb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001fddf  call    ?SetSpecificPrivilegeInAccessToken@@YAJPEAXPEB_WHPEAH@Z; SetSpecificPrivilegeInAccessToken(void *,wchar_t const *,int,int *)
0x18001fde4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdeb  test    eax, eax
0x18001fded  js      short loc_18001FE30
0x18001fdef  mov     cs:dword_180043164, esi
0x18001fdf5  jmp     short loc_18001FE30
0x18001fdf7  call    cs:__imp_GetLastError
0x18001fdfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe04  cmp     rcx, r14
0x18001fe07  jz      short loc_18001FE30
0x18001fe09  test    [rcx+10Ch], sil
0x18001fe10  jz      short loc_18001FE30
0x18001fe12  mov     edx, 11h
0x18001fe17  mov     r9d, eax
0x18001fe1a  mov     r8, r15
0x18001fe1d  mov     rcx, [rcx+100h]
0x18001fe24  call    WPP_SF_d
0x18001fe29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe30  cmp     cs:dword_180043164, 0
0x18001fe37  jz      loc_180020004
0x18001fe3d  mov     cs:dword_180043164, 0
0x18001fe47  mov     qword ptr [rbp+Luid.LowPart], 0
0x18001fe4f  lea     r8, [rbp+Luid]; lpLuid
0x18001fe53  lea     rdx, aSeauditprivile; "SeAuditPrivilege"
0x18001fe5a  xor     ecx, ecx; lpSystemName
0x18001fe5c  call    cs:__imp_LookupPrivilegeValueW
0x18001fe62  test    eax, eax
0x18001fe64  jnz     short loc_18001FEAD
0x18001fe66  call    cs:__imp_GetLastError
0x18001fe6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe73  cmp     rcx, r14
0x18001fe76  jz      loc_18002002D
0x18001fe7c  test    [rcx+10Ch], sil
0x18001fe83  jz      loc_18002002D
0x18001fe89  mov     edx, 12h
0x18001fe8e  mov     dword ptr [rsp+30h+ReturnLength], eax; char
0x18001fe92  lea     r9, aSeauditprivile; "SeAuditPrivilege"
0x18001fe99  mov     r8, r15
0x18001fe9c  mov     rcx, [rcx+100h]; LoggerHandle
0x18001fea3  call    WPP_SF_Sd
0x18001fea8  jmp     loc_18002002D
0x18001fead  mov     [rbp+TokenInformationLength], 0
0x18001feb4  lea     rax, [rbp+TokenInformationLength]
0x18001feb8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001febd  xor     r9d, r9d; TokenInformationLength
0x18001fec0  xor     r8d, r8d; TokenInformation
0x18001fec3  lea     edx, [r9+3]; TokenInformationClass
0x18001fec7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001fecb  call    cs:__imp_GetTokenInformation
0x18001fed1  call    cs:__imp_GetLastError
0x18001fed7  cmp     eax, 7Ah ; 'z'
0x18001feda  jz      short loc_18001FF1B
0x18001fedc  call    cs:__imp_GetLastError
0x18001fee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fee9  cmp     rcx, r14
0x18001feec  jz      loc_18002002D
0x18001fef2  test    [rcx+10Ch], sil
0x18001fef9  jz      loc_18002002D
0x18001feff  mov     edx, 13h
0x18001ff04  mov     r9d, eax
0x18001ff07  mov     r8, r15
0x18001ff0a  mov     rcx, [rcx+100h]
0x18001ff11  call    WPP_SF_d
0x18001ff16  jmp     loc_18002002D
0x18001ff1b  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18001ff1e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001ff23  mov     rbx, rax
0x18001ff26  mov     [rbp+arg_18], rax
0x18001ff2a  lea     rax, [rbp+TokenInformationLength]
0x18001ff2e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001ff33  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001ff37  mov     r8, rbx; TokenInformation
0x18001ff3a  mov     edx, 3; TokenInformationClass
0x18001ff3f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ff43  call    cs:__imp_GetTokenInformation
0x18001ff49  test    eax, eax
0x18001ff4b  jnz     short loc_18001FF8F
0x18001ff4d  call    cs:__imp_GetLastError
0x18001ff53  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff5a  cmp     rcx, r14
0x18001ff5d  jz      short loc_18001FF80
0x18001ff5f  test    [rcx+10Ch], sil
0x18001ff66  jz      short loc_18001FF80
0x18001ff68  mov     edx, 14h
0x18001ff6d  mov     r9d, eax
0x18001ff70  mov     r8, r15
0x18001ff73  mov     rcx, [rcx+100h]
0x18001ff7a  call    WPP_SF_d
0x18001ff7f  nop
0x18001ff80  mov     rcx, rbx; Block
0x18001ff83  call    cs:__imp_free
0x18001ff89  nop
0x18001ff8a  jmp     loc_18002002D
0x18001ff8f  xor     edx, edx
0x18001ff91  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18001ff95  mov     r9d, [rbp+Luid.HighPart]
0x18001ff99  cmp     edx, [rbx]
0x18001ff9b  jnb     short loc_18001FFF3
0x18001ff9d  lea     r8, [rdx+rdx*2]
0x18001ffa1  cmp     [rbx+r8*4+4], eax
0x18001ffa6  jnz     short loc_18001FFAF
0x18001ffa8  cmp     [rbx+r8*4+8], r9d
0x18001ffad  jz      short loc_18001FFB3
0x18001ffaf  add     edx, esi
0x18001ffb1  jmp     short loc_18001FF99
0x18001ffb3  mov     eax, [rbx+r8*4+0Ch]
0x18001ffb8  shr     eax, 1
0x18001ffba  and     eax, esi
0x18001ffbc  mov     cs:dword_180043164, eax
0x18001ffc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffc9  cmp     rcx, r14
0x18001ffcc  jz      short loc_18001FFF3
0x18001ffce  test    byte ptr [rcx+10Ch], 4
0x18001ffd5  jz      short loc_18001FFF3
0x18001ffd7  mov     edx, 15h
0x18001ffdc  lea     r9, aSeauditprivile; "SeAuditPrivilege"
0x18001ffe3  mov     r8, r15
0x18001ffe6  mov     rcx, [rcx+100h]; LoggerHandle
0x18001ffed  call    WPP_SF_S
0x18001fff2  nop
0x18001fff3  mov     rcx, rbx; Block
0x18001fff6  call    cs:__imp_free
0x18001fffc  nop
0x18001fffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180020004  cmp     rcx, r14
0x180020007  jz      short loc_18002002D
0x180020009  test    byte ptr [rcx+10Ch], 4
0x180020010  jz      short loc_18002002D
0x180020012  mov     edx, 16h
0x180020017  mov     r9d, cs:dword_180043164
0x18002001e  mov     r8, r15
0x180020021  mov     rcx, [rcx+100h]
0x180020028  call    WPP_SF_d
0x18002002d  mov     ebx, cs:dword_180043164
0x180020033  lea     rcx, [rbp+TokenHandle]; this
0x180020037  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18002003c  mov     eax, ebx
0x18002003e  add     rsp, 30h
0x180020042  pop     r15
0x180020044  pop     r14
0x180020046  pop     rsi
0x180020047  pop     rbx
0x180020048  pop     rbp
0x180020049  retn
```
