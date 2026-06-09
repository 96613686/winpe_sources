# MQSec_IsUnAuthenticatedUser(int *)

- ea: `0x180028b30`
- end: `0x180028cb9`
- name: `?MQSec_IsUnAuthenticatedUser@@YAJPEAH@Z`
- size: `393`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180004074`
- `0x18000c39c`
- `0x180017430`
- `0x180028214`
- `0x180028250`
- `0x1800287c0`
- `0x180028ab0`
- `0x180028b30`

## import_xrefs

- `msvcrt!free` at `0x180028ba5`
- `msvcrt!free` at `0x180028c58`
- `msvcrt!free` at `0x180028c9d`
- `msvcrt!free` at `0x180028ba5`
- `msvcrt!free` at `0x180028c58`
- `msvcrt!free` at `0x180028c9d`
- `ADVAPI32!EqualSid` at `0x180028c82`
- `ADVAPI32!EqualSid` at `0x180028c82`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MQSec_IsUnAuthenticatedUser(int *a1)
{
  int v2; // ebx
  int ThreadUserSid; // edi
  unsigned int v5; // eax
  void *v6; // rdi
  _BYTE v7[24]; // [rsp+60h] [rbp-20h] BYREF
  int v8; // [rsp+78h] [rbp-8h]
  __int16 v9; // [rsp+A8h] [rbp+28h] BYREF
  int v10; // [rsp+B0h] [rbp+30h] BYREF
  void *Block; // [rsp+B8h] [rbp+38h] BYREF

  Block = 0;
  v2 = 1;
  CImpersonate::CImpersonate((CImpersonate *)v7, 1, 1);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 37, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids);
    CImpersonate::~CImpersonate((CImpersonate *)v7);
    free(0);
    return 3222143012LL;
  }
  else
  {
    ThreadUserSid = MQSec_GetThreadUserSid(1, &Block, 0, 1);
    if ( ThreadUserSid >= 0 )
    {
      v6 = Block;
      if ( !MQSec_IsGuestSid(Block) && (!g_pAnonymSid || !EqualSid(g_pAnonymSid, v6)) )
        v2 = 0;
      *a1 = v2;
      CImpersonate::~CImpersonate((CImpersonate *)v7);
      free(v6);
      return 0;
    }
    else
    {
      v9 = 160;
      v10 = ThreadUserSid;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v5 = mqwcslen(L"acssctrl/imprsont");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v5 + 1),
          L"acssctrl/imprsont",
          2,
          &v9,
          4,
          &v10,
          0,
          0);
      }
      CImpersonate::~CImpersonate((CImpersonate *)v7);
      free(Block);
      return (unsigned int)ThreadUserSid;
    }
  }
}

```

## disassembly

```asm
0x180028b30  mov     [rsp-18h+arg_0], rbx
0x180028b35  push    rbp
0x180028b36  push    rsi
0x180028b37  push    rdi
0x180028b38  mov     rbp, rsp
0x180028b3b  sub     rsp, 80h
0x180028b42  mov     rsi, rcx
0x180028b45  mov     [rbp+Block], 0
0x180028b4d  mov     ebx, 1
0x180028b52  mov     r8d, ebx; int
0x180028b55  mov     edx, ebx; int
0x180028b57  lea     rcx, [rbp+var_20]; this
0x180028b5b  call    ??0CImpersonate@@QEAA@HH@Z; CImpersonate::CImpersonate(int,int)
0x180028b60  nop
0x180028b61  cmp     [rbp+var_8], 0
0x180028b65  jz      short loc_180028BB6
0x180028b67  lea     rax, WPP_GLOBAL_Control
0x180028b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b75  cmp     rcx, rax
0x180028b78  jz      short loc_180028B99
0x180028b7a  test    [rcx+10Ch], bl
0x180028b80  jz      short loc_180028B99
0x180028b82  lea     edx, [rbx+24h]
0x180028b85  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028b8c  mov     rcx, [rcx+100h]
0x180028b93  call    WPP_SF_
0x180028b98  nop
0x180028b99  lea     rcx, [rbp+var_20]; this
0x180028b9d  call    ??1CImpersonate@@UEAA@XZ; CImpersonate::~CImpersonate(void)
0x180028ba2  nop
0x180028ba3  xor     ecx, ecx; Block
0x180028ba5  call    cs:__imp_free
0x180028bab  nop
0x180028bac  mov     eax, 0C00E0024h
0x180028bb1  jmp     loc_180028CA6
0x180028bb6  mov     r9d, ebx; int
0x180028bb9  xor     r8d, r8d; unsigned int *
0x180028bbc  lea     rdx, [rbp+Block]; void **
0x180028bc0  mov     ecx, ebx; int
0x180028bc2  call    ?MQSec_GetThreadUserSid@@YAJHPEAPEAXPEAKH@Z; MQSec_GetThreadUserSid(int,void * *,ulong *,int)
0x180028bc7  mov     edi, eax
0x180028bc9  test    eax, eax
0x180028bcb  jns     loc_180028C63
0x180028bd1  mov     eax, 0A0h
0x180028bd6  mov     [rbp+arg_8], ax
0x180028bda  mov     [rbp+arg_10], edi
0x180028bdd  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180028be5  jz      short loc_180028C4A
0x180028be7  lea     rsi, aAcssctrlImprso; "acssctrl/imprsont"
0x180028bee  mov     rcx, rsi; wchar_t *
0x180028bf1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180028bf6  lea     r9d, [rbx+rax]
0x180028bfa  add     r9, r9
0x180028bfd  mov     [rsp+80h+var_30], 0
0x180028c06  mov     [rsp+80h+var_38], 0
0x180028c0f  lea     rax, [rbp+arg_10]
0x180028c13  mov     [rsp+80h+var_40], rax
0x180028c18  mov     [rsp+80h+var_48], 4
0x180028c21  lea     rax, [rbp+arg_8]
0x180028c25  mov     [rsp+80h+var_50], rax
0x180028c2a  mov     [rsp+80h+var_58], 2
0x180028c33  mov     [rsp+80h+var_60], rsi
0x180028c38  mov     r8d, ebx
0x180028c3b  mov     edx, ebx
0x180028c3d  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180028c44  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180028c49  nop
0x180028c4a  lea     rcx, [rbp+var_20]; this
0x180028c4e  call    ??1CImpersonate@@UEAA@XZ; CImpersonate::~CImpersonate(void)
0x180028c53  nop
0x180028c54  mov     rcx, [rbp+Block]; Block
0x180028c58  call    cs:__imp_free
0x180028c5e  nop
0x180028c5f  mov     eax, edi
0x180028c61  jmp     short loc_180028CA6
0x180028c63  mov     rdi, [rbp+Block]
0x180028c67  mov     rcx, rdi; pSid2
0x180028c6a  call    ?MQSec_IsGuestSid@@YAHPEAX@Z; MQSec_IsGuestSid(void *)
0x180028c6f  test    eax, eax
0x180028c71  jnz     short loc_180028C8E
0x180028c73  mov     rcx, cs:?g_pAnonymSid@@3PEAXEA; pSid1
0x180028c7a  test    rcx, rcx
0x180028c7d  jz      short loc_180028C8C
0x180028c7f  mov     rdx, rdi; pSid2
0x180028c82  call    cs:__imp_EqualSid
0x180028c88  test    eax, eax
0x180028c8a  jnz     short loc_180028C8E
0x180028c8c  xor     ebx, ebx
0x180028c8e  mov     [rsi], ebx
0x180028c90  lea     rcx, [rbp+var_20]; this
0x180028c94  call    ??1CImpersonate@@UEAA@XZ; CImpersonate::~CImpersonate(void)
0x180028c99  nop
0x180028c9a  mov     rcx, rdi; Block
0x180028c9d  call    cs:__imp_free
0x180028ca3  nop
0x180028ca4  xor     eax, eax
0x180028ca6  mov     rbx, [rsp+80h+arg_0]
0x180028cae  add     rsp, 80h
0x180028cb5  pop     rdi
0x180028cb6  pop     rsi
0x180028cb7  pop     rbp
0x180028cb8  retn
```
