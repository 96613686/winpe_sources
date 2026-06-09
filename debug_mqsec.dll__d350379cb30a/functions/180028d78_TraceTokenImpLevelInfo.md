# TraceTokenImpLevelInfo

- ea: `0x180028d78`
- end: `0x180028e7e`
- name: `TraceTokenImpLevelInfo`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028cc0`

## callees

- `0x1800049ac`
- `0x18001353c`
- `0x180028d78`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180028da5`
- `ADVAPI32!GetTokenInformation` at `0x180028da5`
- `KERNEL32!GetLastError` at `0x180028daf`
- `KERNEL32!GetLastError` at `0x180028daf`

## pseudocode

```c
DWORD __fastcall TraceTokenImpLevelInfo(void *a1)
{
  DWORD result; // eax
  unsigned int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  ReturnLength = 0;
  TokenInformation = 0;
  result = GetTokenInformation(a1, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  if ( result )
  {
    if ( TokenInformation > 3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 32),
                 28,
                 &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids,
                 (int)TokenInformation);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    {
      return WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 32));
    }
  }
  else
  {
    result = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      return WPP_SF_d(
               *((_QWORD *)WPP_GLOBAL_Control + 32),
               26,
               &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids,
               result);
  }
  return result;
}

```

## disassembly

```asm
0x180028d78  sub     rsp, 38h
0x180028d7c  mov     r9d, 4; TokenInformationLength
0x180028d82  mov     [rsp+38h+arg_10], 0
0x180028d8a  lea     rax, [rsp+38h+arg_10]
0x180028d8f  mov     [rsp+38h+TokenInformation], 0
0x180028d97  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180028d9c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180028da1  lea     edx, [r9+5]; TokenInformationClass
0x180028da5  call    cs:__imp_GetTokenInformation
0x180028dab  test    eax, eax
0x180028dad  jnz     short loc_180028DF9
0x180028daf  call    cs:__imp_GetLastError
0x180028db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dbc  lea     rdx, WPP_GLOBAL_Control
0x180028dc3  cmp     rcx, rdx
0x180028dc6  jz      loc_180028E79
0x180028dcc  test    byte ptr [rcx+10Ch], 1
0x180028dd3  jz      loc_180028E79
0x180028dd9  mov     rcx, [rcx+100h]
0x180028de0  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028de7  mov     edx, 1Ah
0x180028dec  mov     r9d, eax
0x180028def  call    WPP_SF_d
0x180028df4  jmp     loc_180028E79
0x180028df9  movsxd  r9, [rsp+38h+TokenInformation]
0x180028dfe  cmp     r9d, 3
0x180028e02  ja      short loc_180028E45
0x180028e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e0b  lea     rdx, WPP_GLOBAL_Control
0x180028e12  cmp     rcx, rdx
0x180028e15  jz      short loc_180028E79
0x180028e17  test    byte ptr [rcx+10Ch], 4
0x180028e1e  jz      short loc_180028E79
0x180028e20  mov     rcx, [rcx+100h]; LoggerHandle
0x180028e27  lea     rax, off_180032830; "SecurityAnonymous"
0x180028e2e  mov     r9, [rax+r9*8]
0x180028e32  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028e39  mov     edx, 1Bh
0x180028e3e  call    WPP_SF_S
0x180028e43  jmp     short loc_180028E79
0x180028e45  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e4c  lea     rdx, WPP_GLOBAL_Control
0x180028e53  cmp     rcx, rdx
0x180028e56  jz      short loc_180028E79
0x180028e58  test    byte ptr [rcx+10Ch], 4
0x180028e5f  jz      short loc_180028E79
0x180028e61  mov     rcx, [rcx+100h]
0x180028e68  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028e6f  mov     edx, 1Ch
0x180028e74  call    WPP_SF_d
0x180028e79  add     rsp, 38h
0x180028e7d  retn
```
