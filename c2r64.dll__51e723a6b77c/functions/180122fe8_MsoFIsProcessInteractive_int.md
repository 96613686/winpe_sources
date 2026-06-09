# MsoFIsProcessInteractive(int *)

- ea: `0x180122fe8`
- end: `0x18012320d`
- name: `?MsoFIsProcessInteractive@@YAHPEAH@Z`
- size: `549`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180122d10`

## callees

- `0x1800264b4`
- `0x18003e690`
- `0x180052cd0`
- `0x18009ca08`
- `0x180122fe8`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1801230ad`
- `KERNEL32!GetCurrentProcess` at `0x1801230ad`
- `KERNEL32!GetLastError` at `0x180123105`
- `KERNEL32!GetLastError` at `0x180123105`
- `KERNEL32!CloseHandle` at `0x18012305d`
- `KERNEL32!CloseHandle` at `0x1801231f0`
- `KERNEL32!CloseHandle` at `0x18012305d`
- `KERNEL32!CloseHandle` at `0x1801231f0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801231d8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801231d8`
- `ADVAPI32!CreateWellKnownSid` at `0x180123171`
- `ADVAPI32!CreateWellKnownSid` at `0x180123171`
- `ADVAPI32!OpenProcessToken` at `0x1801230bf`
- `ADVAPI32!OpenProcessToken` at `0x1801230bf`
- `ADVAPI32!GetTokenInformation` at `0x1801230f4`
- `ADVAPI32!GetTokenInformation` at `0x180123153`
- `ADVAPI32!GetTokenInformation` at `0x1801230f4`
- `ADVAPI32!GetTokenInformation` at `0x180123153`
- `ADVAPI32!IsValidSid` at `0x18012319e`
- `ADVAPI32!IsValidSid` at `0x18012319e`
- `ADVAPI32!EqualSid` at `0x1801231b1`
- `ADVAPI32!EqualSid` at `0x1801231b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsoFIsProcessInteractive(int *a1)
{
  HANDLE CurrentProcess; // rax
  __int64 v4; // rcx
  unsigned __int8 v5; // di
  char v6; // al
  unsigned int *v7; // rbx
  __int64 v8; // rcx
  unsigned int v9; // r14d
  HANDLE v10; // rcx
  DWORD TokenInformationLength; // [rsp+38h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-31h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-29h] BYREF
  LPVOID TokenInformation; // [rsp+50h] [rbp-21h] BYREF
  _BYTE pSid[80]; // [rsp+58h] [rbp-19h] BYREF

  hObject = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  memset(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !a1 )
  {
    MsoShipAssertTagProc(1422280);
    return 0;
  }
  if ( vfHaveCachedInteractiveValue )
  {
    *a1 = vfIsProcessInteractive;
    return 1;
  }
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &hObject) )
  {
    if ( GetTokenInformation(hObject, TokenGroups, 0, 0, &TokenInformationLength) )
    {
      v4 = 1422282;
      goto LABEL_7;
    }
    if ( GetLastError() != 122 )
    {
      v4 = 1422283;
      goto LABEL_7;
    }
    v6 = Mso::MemoryPtr<_TOKEN_GROUPS,0>::AllocBytes(&TokenInformation, TokenInformationLength);
    v7 = (unsigned int *)TokenInformation;
    if ( v6 )
    {
      if ( GetTokenInformation(hObject, TokenGroups, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
        if ( CreateWellKnownSid(WinInteractiveSid, 0, pSid, &cbSid) )
        {
          v9 = 0;
          v5 = 1;
          while ( 1 )
          {
            if ( !v7 )
              CrashWithRecovery(0x1F31F70Cu, 0);
            if ( v9 >= *v7 )
              break;
            if ( IsValidSid(*(PSID *)&v7[4 * v9 + 2]) && EqualSid(pSid, *(PSID *)&v7[4 * v9 + 2]) )
            {
              *a1 = 1;
              break;
            }
            ++v9;
          }
          vfHaveCachedInteractiveValue = 1;
          vfIsProcessInteractive = *a1;
          goto LABEL_27;
        }
        v8 = 1422286;
      }
      else
      {
        v8 = 1422285;
      }
    }
    else
    {
      v8 = 1422284;
    }
    MsoShipAssertTagProc(v8);
    v5 = 0;
LABEL_27:
    if ( v7 )
      free(v7);
    goto LABEL_29;
  }
  v4 = 1422281;
LABEL_7:
  MsoShipAssertTagProc(v4);
  v5 = 0;
LABEL_29:
  v10 = hObject;
  if ( hObject )
  {
    hObject = 0;
    CloseHandle(v10);
  }
  return v5;
}

```

## disassembly

```asm
0x180122fe8  mov     rax, rsp
0x180122feb  mov     [rax+10h], rbx
0x180122fef  mov     [rax+18h], rsi
0x180122ff3  mov     [rax+20h], rdi
0x180122ff7  push    rbp
0x180122ff8  push    r14
0x180122ffa  push    r15
0x180122ffc  lea     rbp, [rax-5Fh]
0x180123000  sub     rsp, 0B0h
0x180123007  mov     rax, cs:__security_cookie
0x18012300e  xor     rax, rsp
0x180123011  mov     [rbp+57h+var_20], rax
0x180123015  mov     rsi, rcx
0x180123018  mov     [rbp+57h+hObject], 0
0x180123020  mov     [rbp+57h+TokenInformation], 0
0x180123028  mov     [rbp+57h+TokenInformationLength], 0
0x18012302f  mov     ebx, 44h ; 'D'
0x180123034  mov     r8d, ebx; Size
0x180123037  xor     edx, edx; Val
0x180123039  lea     rcx, [rbp+57h+pSid]; void *
0x18012303d  call    memset
0x180123042  mov     [rbp+57h+cbSid], ebx
0x180123045  test    rsi, rsi
0x180123048  jnz     short loc_18012308F
0x18012304a  mov     ecx, 15B3C8h
0x18012304f  call    MsoShipAssertTagProc
0x180123054  mov     rcx, [rbp+57h+hObject]; hObject
0x180123058  test    rcx, rcx
0x18012305b  jz      short loc_180123064
0x18012305d  call    cs:__imp_CloseHandle
0x180123063  nop
0x180123064  xor     eax, eax
0x180123066  mov     rcx, [rbp+57h+var_20]
0x18012306a  xor     rcx, rsp; StackCookie
0x18012306d  call    __security_check_cookie
0x180123072  lea     r11, [rsp+0C0h+var_10]
0x18012307a  mov     rbx, [r11+28h]
0x18012307e  mov     rsi, [r11+30h]
0x180123082  mov     rdi, [r11+38h]
0x180123086  mov     rsp, r11
0x180123089  pop     r15
0x18012308b  pop     r14
0x18012308d  pop     rbp
0x18012308e  retn
0x18012308f  cmp     cs:?vfHaveCachedInteractiveValue@@3HA, 0; int vfHaveCachedInteractiveValue
0x180123096  jz      short loc_1801230A7
0x180123098  mov     eax, cs:?vfIsProcessInteractive@@3HA; int vfIsProcessInteractive
0x18012309e  mov     [rsi], eax
0x1801230a0  mov     eax, 1
0x1801230a5  jmp     short loc_180123066
0x1801230a7  mov     dword ptr [rsi], 0
0x1801230ad  call    cs:__imp_GetCurrentProcess
0x1801230b3  lea     r8, [rbp+57h+hObject]; TokenHandle
0x1801230b7  mov     edx, 20008h; DesiredAccess
0x1801230bc  mov     rcx, rax; ProcessHandle
0x1801230bf  call    cs:__imp_OpenProcessToken
0x1801230c5  test    eax, eax
0x1801230c7  jnz     short loc_1801230DB
0x1801230c9  mov     ecx, 15B3C9h
0x1801230ce  call    MsoShipAssertTagProc
0x1801230d3  xor     dil, dil
0x1801230d6  jmp     loc_1801231DF
0x1801230db  lea     rax, [rbp+57h+TokenInformationLength]
0x1801230df  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1801230e4  xor     r9d, r9d; TokenInformationLength
0x1801230e7  xor     r8d, r8d; TokenInformation
0x1801230ea  lea     edi, [r9+2]
0x1801230ee  mov     edx, edi; TokenInformationClass
0x1801230f0  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x1801230f4  call    cs:__imp_GetTokenInformation
0x1801230fa  test    eax, eax
0x1801230fc  jz      short loc_180123105
0x1801230fe  mov     ecx, 15B3CAh
0x180123103  jmp     short loc_1801230CE
0x180123105  call    cs:__imp_GetLastError
0x18012310b  cmp     eax, 7Ah ; 'z'
0x18012310e  jz      short loc_180123117
0x180123110  mov     ecx, 15B3CBh
0x180123115  jmp     short loc_1801230CE
0x180123117  mov     edx, [rbp+57h+TokenInformationLength]
0x18012311a  lea     rcx, [rbp+57h+TokenInformation]
0x18012311e  call    ?AllocBytes@?$MemoryPtr@U_TOKEN_GROUPS@@$0A@@Mso@@QEAA_N_K@Z; Mso::MemoryPtr<_TOKEN_GROUPS,0>::AllocBytes(unsigned __int64)
0x180123123  mov     rbx, [rbp+57h+TokenInformation]
0x180123127  test    al, al
0x180123129  jnz     short loc_18012313D
0x18012312b  mov     ecx, 15B3CCh
0x180123130  call    MsoShipAssertTagProc
0x180123135  xor     dil, dil
0x180123138  jmp     loc_1801231D0
0x18012313d  lea     rax, [rbp+57h+TokenInformationLength]
0x180123141  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180123146  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18012314a  mov     r8, rbx; TokenInformation
0x18012314d  mov     edx, edi; TokenInformationClass
0x18012314f  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x180123153  call    cs:__imp_GetTokenInformation
0x180123159  test    eax, eax
0x18012315b  jnz     short loc_180123164
0x18012315d  mov     ecx, 15B3CDh
0x180123162  jmp     short loc_180123130
0x180123164  lea     r9, [rbp+57h+cbSid]; cbSid
0x180123168  lea     r8, [rbp+57h+pSid]; pSid
0x18012316c  xor     edx, edx; DomainSid
0x18012316e  lea     ecx, [rdx+0Bh]; WellKnownSidType
0x180123171  call    cs:__imp_CreateWellKnownSid
0x180123177  test    eax, eax
0x180123179  jnz     short loc_180123182
0x18012317b  mov     ecx, 15B3CEh
0x180123180  jmp     short loc_180123130
0x180123182  xor     r14d, r14d
0x180123185  lea     edi, [r14+1]
0x180123189  test    rbx, rbx
0x18012318c  jz      short loc_180123200
0x18012318e  cmp     r14d, [rbx]
0x180123191  jnb     short loc_1801231C2
0x180123193  mov     r15d, r14d
0x180123196  add     r15, r15
0x180123199  mov     rcx, [rbx+r15*8+8]; pSid
0x18012319e  call    cs:__imp_IsValidSid
0x1801231a4  test    eax, eax
0x1801231a6  jz      short loc_1801231BB
0x1801231a8  mov     rdx, [rbx+r15*8+8]; pSid2
0x1801231ad  lea     rcx, [rbp+57h+pSid]; pSid1
0x1801231b1  call    cs:__imp_EqualSid
0x1801231b7  test    eax, eax
0x1801231b9  jnz     short loc_1801231C0
0x1801231bb  add     r14d, edi
0x1801231be  jmp     short loc_180123189
0x1801231c0  mov     [rsi], edi
0x1801231c2  mov     cs:?vfHaveCachedInteractiveValue@@3HA, edi; int vfHaveCachedInteractiveValue
0x1801231c8  mov     eax, [rsi]
0x1801231ca  mov     cs:?vfIsProcessInteractive@@3HA, eax; int vfIsProcessInteractive
0x1801231d0  test    rbx, rbx
0x1801231d3  jz      short loc_1801231DF
0x1801231d5  mov     rcx, rbx; Block
0x1801231d8  call    cs:__imp_free
0x1801231de  nop
0x1801231df  mov     rcx, [rbp+57h+hObject]; hObject
0x1801231e3  test    rcx, rcx
0x1801231e6  jz      short loc_1801231F7
0x1801231e8  mov     [rbp+57h+hObject], 0
0x1801231f0  call    cs:__imp_CloseHandle
0x1801231f6  nop
0x1801231f7  movzx   eax, dil
0x1801231fb  jmp     loc_180123066
0x180123200  xor     edx, edx; struct CrashContext *
0x180123202  mov     ecx, 1F31F70Ch; unsigned int
0x180123207  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
