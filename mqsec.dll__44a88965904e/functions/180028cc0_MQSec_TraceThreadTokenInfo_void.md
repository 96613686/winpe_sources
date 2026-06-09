# MQSec_TraceThreadTokenInfo(void)

- ea: `0x180028cc0`
- end: `0x180028d71`
- name: `?MQSec_TraceThreadTokenInfo@@YAXXZ`
- size: `177`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18001f5c0`

## callees

- `0x1800041cc`
- `0x1800049ac`
- `0x180028cc0`
- `0x180028d78`
- `0x180028e84`
- `0x180028fdc`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x180028cf8`
- `ADVAPI32!OpenThreadToken` at `0x180028cf8`
- `KERNEL32!GetCurrentThread` at `0x180028ce1`
- `KERNEL32!GetCurrentThread` at `0x180028ce1`
- `KERNEL32!GetLastError` at `0x180028d02`
- `KERNEL32!GetLastError` at `0x180028d02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void MQSec_TraceThreadTokenInfo(void)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      try
      {
        TraceTokenTypeInfo(TokenHandle);
        TraceTokenImpLevelInfo(TokenHandle);
        TraceTokenSidInfo(TokenHandle);
      }
      catch ( exception )
      {
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 35, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, LastError);
    }
    CHandle::~CHandle((CHandle *)&TokenHandle);
  }
}

```

## disassembly

```asm
0x180028cc0  sub     rsp, 28h
0x180028cc4  mov     rax, cs:WPP_GLOBAL_Control
0x180028ccb  test    byte ptr [rax+10Ch], 4
0x180028cd2  jz      loc_180028D6C
0x180028cd8  mov     [rsp+28h+TokenHandle], 0
0x180028ce1  call    cs:__imp_GetCurrentThread
0x180028ce7  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180028cec  mov     edx, 8; DesiredAccess
0x180028cf1  lea     r8d, [rdx-7]; OpenAsSelf
0x180028cf5  mov     rcx, rax; ThreadHandle
0x180028cf8  call    cs:__imp_OpenThreadToken
0x180028cfe  test    eax, eax
0x180028d00  jnz     short loc_180028D41
0x180028d02  call    cs:__imp_GetLastError
0x180028d08  lea     rdx, WPP_GLOBAL_Control
0x180028d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d16  cmp     rcx, rdx
0x180028d19  jz      short loc_180028D62
0x180028d1b  test    byte ptr [rcx+10Ch], 1
0x180028d22  jz      short loc_180028D62
0x180028d24  mov     edx, 23h ; '#'
0x180028d29  mov     r9d, eax
0x180028d2c  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028d33  mov     rcx, [rcx+100h]
0x180028d3a  call    WPP_SF_d
0x180028d3f  jmp     short loc_180028D62
0x180028d41  mov     rcx, [rsp+28h+TokenHandle]
0x180028d46  call    TraceTokenTypeInfo
0x180028d4b  mov     rcx, [rsp+28h+TokenHandle]
0x180028d50  call    TraceTokenImpLevelInfo
0x180028d55  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180028d5a  call    TraceTokenSidInfo
0x180028d5f  nop
0x180028d60  jmp     short $+2
0x180028d62  lea     rcx, [rsp+28h+TokenHandle]; this
0x180028d67  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180028d6c  add     rsp, 28h
0x180028d70  retn
```
