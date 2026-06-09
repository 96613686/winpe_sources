# DeleteQMPolicy

- ea: `0x180018a94`
- end: `0x180018c98`
- name: `DeleteQMPolicy`
- size: `516`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004840`
- `0x180011290`
- `0x180028a8c`
- `0x180028b2c`

## callees

- `0x18000e510`
- `0x1800189fc`
- `0x180018a94`
- `0x180018ee4`
- `0x180019d80`
- `0x180019df8`
- `0x180019e74`
- `0x180044ea4`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ad3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c3f`

## pseudocode

```c
__int64 __fastcall DeleteQMPolicy(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 v4; // rcx
  __int64 QMPolicy; // rax
  _QWORD *v6; // rdi
  unsigned int v7; // ebp
  _QWORD *v8; // rcx
  _QWORD *v9; // rcx
  int v11; // eax
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF

  v12 = 0;
  if ( !a3 || !*a3 )
    return 87;
  EnterCriticalSection(&gcSPDSection);
  QMPolicy = FindQMPolicy(v4, a3);
  v6 = (_QWORD *)QMPolicy;
  if ( !QMPolicy )
  {
    v7 = 13001;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids, 13001);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
        WPP_SF_SD(v8[2], 51, (unsigned int)WPP_b879685112533572aee45ba5e3c29dd7_Traceguids, (_DWORD)a3, 201);
    }
LABEL_17:
    LeaveCriticalSection(&gcSPDSection);
    return v7;
  }
  v12 = *(_OWORD *)QMPolicy;
  if ( *(_DWORD *)(QMPolicy + 24) )
  {
    v7 = 13002;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids, 13002);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
        WPP_SF_S_guid_D(
          v9[2],
          50,
          (unsigned int)WPP_b879685112533572aee45ba5e3c29dd7_Traceguids,
          v6[2],
          (__int64)v6,
          13002,
          v12);
    }
    goto LABEL_17;
  }
  v11 = LipsApiIpsecPolicyDelete(QMPolicy);
  if ( v11 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_S_guid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)WPP_b879685112533572aee45ba5e3c29dd7_Traceguids,
      (_DWORD)a3,
      (__int64)&v12,
      v11);
  DeleteIniQMPolicy(v6);
  LeaveCriticalSection(&gcSPDSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_b879685112533572aee45ba5e3c29dd7_Traceguids,
      (_DWORD)a3,
      (__int64)&v12);
  return 0;
}

```

## disassembly

```asm
0x180018a94  push    rbx
0x180018a96  push    rbp
0x180018a97  push    rsi
0x180018a98  push    rdi
0x180018a99  sub     rsp, 58h
0x180018a9d  mov     rax, cs:__security_cookie
0x180018aa4  xor     rax, rsp
0x180018aa7  mov     [rsp+78h+var_38], rax
0x180018aac  xor     ebp, ebp
0x180018aae  xorps   xmm0, xmm0
0x180018ab1  mov     rsi, r8
0x180018ab4  movups  [rsp+78h+var_48], xmm0
0x180018ab9  test    r8, r8
0x180018abc  jz      loc_180018C7D
0x180018ac2  cmp     [r8], bp
0x180018ac6  jz      loc_180018C7D
0x180018acc  lea     rcx, gcSPDSection; lpCriticalSection
0x180018ad3  call    cs:__imp_EnterCriticalSection
0x180018ad9  mov     rdx, rsi
0x180018adc  call    FindQMPolicy
0x180018ae1  mov     rdi, rax
0x180018ae4  test    rax, rax
0x180018ae7  jnz     short loc_180018B59
0x180018ae9  mov     ebp, 32C9h
0x180018aee  mov     rcx, cs:WPP_GLOBAL_Control
0x180018af5  lea     rbx, WPP_GLOBAL_Control
0x180018afc  cmp     rcx, rbx
0x180018aff  jz      loc_180018BD1
0x180018b05  test    byte ptr [rcx+1Ch], 10h
0x180018b09  jz      short loc_180018B28
0x180018b0b  mov     rcx, [rcx+10h]
0x180018b0f  lea     edx, [rax+2Eh]
0x180018b12  mov     r9d, ebp
0x180018b15  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x180018b1c  call    WPP_SF_d
0x180018b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b28  cmp     rcx, rbx
0x180018b2b  jz      loc_180018BD1
0x180018b31  test    byte ptr [rcx+1Ch], 10h
0x180018b35  jz      loc_180018BD1
0x180018b3b  mov     rcx, [rcx+10h]
0x180018b3f  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x180018b46  mov     edx, 33h ; '3'
0x180018b4b  mov     dword ptr [rsp+78h+var_58], ebp
0x180018b4f  mov     r9, rsi
0x180018b52  call    WPP_SF_SD
0x180018b57  jmp     short loc_180018BD1
0x180018b59  movups  xmm0, xmmword ptr [rax]
0x180018b5c  movdqu  [rsp+78h+var_48], xmm0
0x180018b62  cmp     [rax+18h], ebp
0x180018b65  jz      short loc_180018BE5
0x180018b67  mov     ebp, 32CAh
0x180018b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b73  lea     rbx, WPP_GLOBAL_Control
0x180018b7a  cmp     rcx, rbx
0x180018b7d  jz      short loc_180018BD1
0x180018b7f  test    byte ptr [rcx+1Ch], 10h
0x180018b83  jz      short loc_180018BA4
0x180018b85  mov     rcx, [rcx+10h]
0x180018b89  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x180018b90  mov     edx, 2Fh ; '/'
0x180018b95  mov     r9d, ebp
0x180018b98  call    WPP_SF_d
0x180018b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ba4  cmp     rcx, rbx
0x180018ba7  jz      short loc_180018BD1
0x180018ba9  test    byte ptr [rcx+1Ch], 10h
0x180018bad  jz      short loc_180018BD1
0x180018baf  mov     r9, [rdi+10h]
0x180018bb3  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x180018bba  mov     rcx, [rcx+10h]
0x180018bbe  mov     edx, 32h ; '2'
0x180018bc3  mov     [rsp+78h+var_50], ebp
0x180018bc7  mov     [rsp+78h+var_58], rdi
0x180018bcc  call    WPP_SF_S_guid_D
0x180018bd1  lea     rcx, gcSPDSection; lpCriticalSection
0x180018bd8  call    cs:__imp_LeaveCriticalSection
0x180018bde  mov     eax, ebp
0x180018be0  jmp     loc_180018C82
0x180018be5  mov     rcx, rdi
0x180018be8  call    LipsApiIpsecPolicyDelete
0x180018bed  lea     rbx, WPP_GLOBAL_Control
0x180018bf4  test    eax, eax
0x180018bf6  jz      short loc_180018C30
0x180018bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bff  cmp     rcx, rbx
0x180018c02  jz      short loc_180018C30
0x180018c04  test    byte ptr [rcx+1Ch], 10h
0x180018c08  jz      short loc_180018C30
0x180018c0a  mov     rcx, [rcx+10h]
0x180018c0e  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x180018c15  mov     [rsp+78h+var_50], eax
0x180018c19  mov     edx, 30h ; '0'
0x180018c1e  lea     rax, [rsp+78h+var_48]
0x180018c23  mov     r9, rsi
0x180018c26  mov     [rsp+78h+var_58], rax
0x180018c2b  call    WPP_SF_S_guid_D
0x180018c30  mov     rcx, rdi; lpMem
0x180018c33  call    DeleteIniQMPolicy
0x180018c38  lea     rcx, gcSPDSection; lpCriticalSection
0x180018c3f  call    cs:__imp_LeaveCriticalSection
0x180018c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c4c  cmp     rcx, rbx
0x180018c4f  jz      short loc_180018C79
0x180018c51  test    byte ptr [rcx+1Ch], 4
0x180018c55  jz      short loc_180018C79
0x180018c57  mov     rcx, [rcx+10h]
0x180018c5b  lea     rax, [rsp+78h+var_48]
0x180018c60  mov     edx, 31h ; '1'
0x180018c65  mov     [rsp+78h+var_58], rax
0x180018c6a  mov     r9, rsi
0x180018c6d  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x180018c74  call    WPP_SF_S_guid_
0x180018c79  xor     eax, eax
0x180018c7b  jmp     short loc_180018C82
0x180018c7d  mov     eax, 57h ; 'W'
0x180018c82  mov     rcx, [rsp+78h+var_38]
0x180018c87  xor     rcx, rsp; StackCookie
0x180018c8a  call    __security_check_cookie
0x180018c8f  add     rsp, 58h
0x180018c93  pop     rdi
0x180018c94  pop     rsi
0x180018c95  pop     rbp
0x180018c96  pop     rbx
0x180018c97  retn
```
