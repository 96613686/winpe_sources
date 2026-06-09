# ProcessDirectoryPolicyPollState

- ea: `0x18002cf74`
- end: `0x18002d2e3`
- name: `ProcessDirectoryPolicyPollState`
- size: `879`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180003de0`
- `0x18000adac`

## callees

- `0x180007160`
- `0x180008280`
- `0x18000acb4`
- `0x18000cb1c`
- `0x18000e078`
- `0x18000e510`
- `0x18000f638`
- `0x18002bb44`
- `0x18002c1ec`
- `0x18002c448`
- `0x18002cf74`
- `0x18002d8c4`
- `0x180035714`
- `0x180036f00`
- `0x18003c2d4`
- `0x180042e20`

## pseudocode

```c
__int64 __fastcall ProcessDirectoryPolicyPollState(__int64 a1)
{
  bool v2; // zf
  LPVOID *v3; // rdi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // r12d
  unsigned int v13; // eax
  unsigned int v14; // eax
  LPVOID v16; // r15
  int updated; // eax
  LPVOID *v18; // rcx
  int v19; // r13d
  _DWORD *v20; // rcx
  unsigned int v21; // edi
  __int64 v22; // rdx
  void *v23; // rcx
  DWORD v24; // ebx
  int v25; // [rsp+90h] [rbp+48h] BYREF
  DWORD dwMessageId; // [rsp+98h] [rbp+50h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+58h] BYREF
  LPVOID v28; // [rsp+A8h] [rbp+60h] BYREF

  v2 = *(_DWORD *)a1 == 3;
  v3 = 0;
  v25 = 0;
  lpMem = 0;
  v28 = 0;
  dwMessageId = 0;
  if ( !v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v5 = 91;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  if ( (unsigned int)GetDirectoryIncarnationNumber(*(_QWORD *)(a1 + 8), &v25) )
  {
    v8 = MigrateFromDSToCache(a1);
    v9 = v8;
    if ( !v8 )
      return 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_38;
    v11 = 93;
    goto LABEL_36;
  }
  v12 = v25;
  if ( v25 == *(_DWORD *)(a1 + 24) )
  {
    AuditEventOld(v7, v6, 0x4BAD0008u, 0, 0, 1u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v5 = 94;
LABEL_17:
    WPP_SF_(v4[2], v5, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  if ( (unsigned int)LoadDirectoryPolicy(*(_QWORD *)(a1 + 8), &lpMem) )
  {
    v13 = MigrateFromDSToCache(a1);
    v9 = v13;
    if ( !v13 )
      return 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v3 = (LPVOID *)lpMem;
LABEL_41:
      if ( v3 )
        FreeIpsecPolicyObject(v3);
      if ( v28 )
        FreeIpsecPolicyData(v28);
      return v9;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
      v3 = (LPVOID *)lpMem;
LABEL_38:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
        WPP_SF_d(v10[2], 100, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v9);
      goto LABEL_41;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v13);
    v3 = (LPVOID *)lpMem;
LABEL_37:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  v3 = (LPVOID *)lpMem;
  v14 = ProcessNFAs(lpMem, 1, &dwMessageId, &v28);
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v14);
    v8 = MigrateFromDSToCache(a1);
    v9 = v8;
    if ( !v8 )
    {
      if ( v3 )
        FreeIpsecPolicyObject(v3);
      return 0;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_38;
    v11 = 98;
LABEL_36:
    WPP_SF_d(v10[2], v11, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v8);
    goto LABEL_37;
  }
  v16 = v28;
  updated = UpdatePolicyInformation(*(_QWORD *)(a1 + 40), v28, 3);
  v18 = *(LPVOID **)(a1 + 32);
  v19 = updated;
  if ( v18 )
    FreeIpsecPolicyObject(v18);
  v20 = *(_DWORD **)(a1 + 40);
  if ( v20 )
    FreeIpsecPolicyData(v20);
  DeleteRegistryCache();
  CacheDirectorytoRegistry((__int64)v3);
  *(_QWORD *)(a1 + 32) = v3;
  *(_QWORD *)(a1 + 40) = v16;
  *(_DWORD *)(a1 + 16) = *((_DWORD *)v16 + 4);
  *(_DWORD *)(a1 + 24) = v12;
  if ( v19 || !gbUpdatedAuthMethods )
  {
    NotifyIpsecPolicyChange();
    v24 = dwMessageId;
    v21 = 0;
    if ( dwMessageId )
    {
      AuditIPSecPolicyErrorEventOld((__int64)v23, v22, 0x4BAD0007u, *((unsigned __int16 **)v16 + 6), dwMessageId);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v24);
    }
    AuditEventOld((__int64)v23, v22, 0x4BAD0009u, 0, 0, 1u);
  }
  else
  {
    return (unsigned int)OnPolicyChanged(a1);
  }
  return v21;
}

```

## disassembly

```asm
0x18002cf74  push    rbp
0x18002cf76  push    rbx
0x18002cf77  push    rsi
0x18002cf78  push    rdi
0x18002cf79  push    r12
0x18002cf7b  push    r13
0x18002cf7d  push    r14
0x18002cf7f  push    r15
0x18002cf81  mov     rbp, rsp
0x18002cf84  sub     rsp, 48h
0x18002cf88  xor     r15d, r15d
0x18002cf8b  mov     rbx, rcx
0x18002cf8e  cmp     dword ptr [rcx], 3
0x18002cf91  mov     edi, r15d
0x18002cf94  mov     [rbp+arg_0], r15d
0x18002cf98  mov     [rbp+lpMem], r15
0x18002cf9c  mov     [rbp+arg_18], r15
0x18002cfa0  mov     [rbp+arg_8], r15d
0x18002cfa4  jz      short loc_18002CFD7
0x18002cfa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfad  lea     rsi, WPP_GLOBAL_Control
0x18002cfb4  cmp     rcx, rsi
0x18002cfb7  jz      loc_18002D1FB
0x18002cfbd  test    byte ptr [rcx+1Ch], 4
0x18002cfc1  jz      loc_18002D1FB
0x18002cfc7  lea     edx, [r15+5Bh]
0x18002cfcb  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cfd2  jmp     loc_18002D096
0x18002cfd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfde  lea     rsi, WPP_GLOBAL_Control
0x18002cfe5  lea     r14, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cfec  cmp     rcx, rsi
0x18002cfef  jz      short loc_18002D008
0x18002cff1  test    byte ptr [rcx+1Ch], 4
0x18002cff5  jz      short loc_18002D008
0x18002cff7  mov     rcx, [rcx+10h]
0x18002cffb  mov     edx, 5Ch ; '\'
0x18002d000  mov     r8, r14
0x18002d003  call    WPP_SF_
0x18002d008  mov     rcx, [rbx+8]; int
0x18002d00c  lea     rdx, [rbp+arg_0]
0x18002d010  call    GetDirectoryIncarnationNumber
0x18002d015  test    eax, eax
0x18002d017  jz      short loc_18002D04F
0x18002d019  mov     rcx, rbx
0x18002d01c  call    MigrateFromDSToCache
0x18002d021  mov     ebx, eax
0x18002d023  test    eax, eax
0x18002d025  jz      loc_18002D1FB
0x18002d02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d032  cmp     rcx, rsi
0x18002d035  jz      loc_18002D1E7
0x18002d03b  test    byte ptr [rcx+1Ch], 10h
0x18002d03f  jz      loc_18002D1AD
0x18002d045  mov     edx, 5Dh ; ']'
0x18002d04a  jmp     loc_18002D197
0x18002d04f  mov     r12d, [rbp+arg_0]
0x18002d053  cmp     r12d, [rbx+18h]
0x18002d057  jnz     short loc_18002D0A4
0x18002d059  mov     [rsp+48h+var_20], 1
0x18002d061  xor     r9d, r9d
0x18002d064  mov     r8d, 4BAD0008h
0x18002d06a  mov     [rsp+48h+dwMessageId], r15d
0x18002d06f  call    AuditEventOld
0x18002d074  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d07b  cmp     rcx, rsi
0x18002d07e  jz      loc_18002D1FB
0x18002d084  test    byte ptr [rcx+1Ch], 4
0x18002d088  jz      loc_18002D1FB
0x18002d08e  mov     edx, 5Eh ; '^'
0x18002d093  mov     r8, r14
0x18002d096  mov     rcx, [rcx+10h]
0x18002d09a  call    WPP_SF_
0x18002d09f  jmp     loc_18002D1FB
0x18002d0a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0ab  cmp     rcx, rsi
0x18002d0ae  jz      short loc_18002D0C7
0x18002d0b0  test    byte ptr [rcx+1Ch], 4
0x18002d0b4  jz      short loc_18002D0C7
0x18002d0b6  mov     rcx, [rcx+10h]
0x18002d0ba  mov     edx, 5Fh ; '_'
0x18002d0bf  mov     r8, r14
0x18002d0c2  call    WPP_SF_
0x18002d0c7  mov     rcx, [rbx+8]; int
0x18002d0cb  lea     rdx, [rbp+lpMem]
0x18002d0cf  call    LoadDirectoryPolicy
0x18002d0d4  test    eax, eax
0x18002d0d6  jz      short loc_18002D12B
0x18002d0d8  mov     rcx, rbx
0x18002d0db  call    MigrateFromDSToCache
0x18002d0e0  mov     ebx, eax
0x18002d0e2  test    eax, eax
0x18002d0e4  jz      loc_18002D1FB
0x18002d0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0f1  cmp     rcx, rsi
0x18002d0f4  jz      short loc_18002D122
0x18002d0f6  test    byte ptr [rcx+1Ch], 10h
0x18002d0fa  jz      short loc_18002D119
0x18002d0fc  mov     rcx, [rcx+10h]
0x18002d100  mov     edx, 60h ; '`'
0x18002d105  mov     r9d, eax
0x18002d108  mov     r8, r14
0x18002d10b  call    WPP_SF_d
0x18002d110  mov     rdi, [rbp+lpMem]
0x18002d114  jmp     loc_18002D1A6
0x18002d119  mov     rdi, [rbp+lpMem]
0x18002d11d  jmp     loc_18002D1AD
0x18002d122  mov     rdi, [rbp+lpMem]
0x18002d126  jmp     loc_18002D1CC
0x18002d12b  mov     rdi, [rbp+lpMem]
0x18002d12f  lea     r9, [rbp+arg_18]
0x18002d133  mov     rcx, rdi
0x18002d136  lea     r8, [rbp+arg_8]
0x18002d13a  mov     edx, 1
0x18002d13f  call    ProcessNFAs
0x18002d144  test    eax, eax
0x18002d146  jz      loc_18002D202
0x18002d14c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d153  cmp     rcx, rsi
0x18002d156  jz      short loc_18002D172
0x18002d158  test    byte ptr [rcx+1Ch], 10h
0x18002d15c  jz      short loc_18002D172
0x18002d15e  mov     rcx, [rcx+10h]
0x18002d162  mov     edx, 61h ; 'a'
0x18002d167  mov     r9d, eax
0x18002d16a  mov     r8, r14
0x18002d16d  call    WPP_SF_d
0x18002d172  mov     rcx, rbx
0x18002d175  call    MigrateFromDSToCache
0x18002d17a  mov     ebx, eax
0x18002d17c  test    eax, eax
0x18002d17e  jz      short loc_18002D1EE
0x18002d180  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d187  cmp     rcx, rsi
0x18002d18a  jz      short loc_18002D1CC
0x18002d18c  test    byte ptr [rcx+1Ch], 10h
0x18002d190  jz      short loc_18002D1AD
0x18002d192  mov     edx, 62h ; 'b'
0x18002d197  mov     rcx, [rcx+10h]
0x18002d19b  mov     r9d, eax
0x18002d19e  mov     r8, r14
0x18002d1a1  call    WPP_SF_d
0x18002d1a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1ad  cmp     rcx, rsi
0x18002d1b0  jz      short loc_18002D1CC
0x18002d1b2  test    byte ptr [rcx+1Ch], 10h
0x18002d1b6  jz      short loc_18002D1CC
0x18002d1b8  mov     rcx, [rcx+10h]
0x18002d1bc  mov     edx, 64h ; 'd'
0x18002d1c1  mov     r9d, ebx
0x18002d1c4  mov     r8, r14
0x18002d1c7  call    WPP_SF_d
0x18002d1cc  test    rdi, rdi
0x18002d1cf  jz      short loc_18002D1D9
0x18002d1d1  mov     rcx, rdi; lpMem
0x18002d1d4  call    FreeIpsecPolicyObject
0x18002d1d9  mov     rcx, [rbp+arg_18]; lpMem
0x18002d1dd  test    rcx, rcx
0x18002d1e0  jz      short loc_18002D1E7
0x18002d1e2  call    FreeIpsecPolicyData
0x18002d1e7  mov     eax, ebx
0x18002d1e9  jmp     loc_18002D2D2
0x18002d1ee  test    rdi, rdi
0x18002d1f1  jz      short loc_18002D1FB
0x18002d1f3  mov     rcx, rdi; lpMem
0x18002d1f6  call    FreeIpsecPolicyObject
0x18002d1fb  xor     eax, eax
0x18002d1fd  jmp     loc_18002D2D2
0x18002d202  mov     r15, [rbp+arg_18]
0x18002d206  mov     r8d, 3
0x18002d20c  mov     rcx, [rbx+28h]
0x18002d210  mov     rdx, r15
0x18002d213  call    UpdatePolicyInformation
0x18002d218  mov     rcx, [rbx+20h]; lpMem
0x18002d21c  mov     r13d, eax
0x18002d21f  test    rcx, rcx
0x18002d222  jz      short loc_18002D229
0x18002d224  call    FreeIpsecPolicyObject
0x18002d229  mov     rcx, [rbx+28h]; lpMem
0x18002d22d  test    rcx, rcx
0x18002d230  jz      short loc_18002D237
0x18002d232  call    FreeIpsecPolicyData
0x18002d237  call    DeleteRegistryCache
0x18002d23c  mov     rcx, rdi
0x18002d23f  call    CacheDirectorytoRegistry
0x18002d244  mov     [rbx+20h], rdi
0x18002d248  mov     [rbx+28h], r15
0x18002d24c  mov     eax, [r15+10h]
0x18002d250  mov     [rbx+10h], eax
0x18002d253  mov     [rbx+18h], r12d
0x18002d257  test    r13d, r13d
0x18002d25a  jnz     short loc_18002D271
0x18002d25c  cmp     cs:gbUpdatedAuthMethods, r13d
0x18002d263  jz      short loc_18002D271
0x18002d265  mov     rcx, rbx
0x18002d268  call    OnPolicyChanged
0x18002d26d  mov     edi, eax
0x18002d26f  jmp     short loc_18002D2D0
0x18002d271  call    NotifyIpsecPolicyChange
0x18002d276  mov     ebx, [rbp+arg_8]
0x18002d279  xor     edi, edi
0x18002d27b  test    ebx, ebx
0x18002d27d  jz      short loc_18002D2B6
0x18002d27f  mov     r9, [r15+30h]; int
0x18002d283  mov     r8d, 4BAD0007h; int
0x18002d289  mov     [rsp+48h+dwMessageId], ebx; dwMessageId
0x18002d28d  call    AuditIPSecPolicyErrorEventOld
0x18002d292  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d299  cmp     rcx, rsi
0x18002d29c  jz      short loc_18002D2B6
0x18002d29e  test    byte ptr [rcx+1Ch], 8
0x18002d2a2  jz      short loc_18002D2B6
0x18002d2a4  mov     rcx, [rcx+10h]
0x18002d2a8  lea     edx, [rdi+63h]
0x18002d2ab  mov     r9d, ebx
0x18002d2ae  mov     r8, r14
0x18002d2b1  call    WPP_SF_d
0x18002d2b6  mov     [rsp+48h+var_20], 1
0x18002d2be  xor     r9d, r9d
0x18002d2c1  mov     r8d, 4BAD0009h
0x18002d2c7  mov     [rsp+48h+dwMessageId], edi
0x18002d2cb  call    AuditEventOld
0x18002d2d0  mov     eax, edi
0x18002d2d2  add     rsp, 48h
0x18002d2d6  pop     r15
0x18002d2d8  pop     r14
0x18002d2da  pop     r13
0x18002d2dc  pop     r12
0x18002d2de  pop     rdi
0x18002d2df  pop     rsi
0x18002d2e0  pop     rbx
0x18002d2e1  pop     rbp
0x18002d2e2  retn
```
