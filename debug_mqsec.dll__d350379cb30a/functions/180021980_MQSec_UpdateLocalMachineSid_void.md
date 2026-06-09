# MQSec_UpdateLocalMachineSid(void *)

- ea: `0x180021980`
- end: `0x180021b29`
- name: `?MQSec_UpdateLocalMachineSid@@YAXPEAX@Z`
- size: `425`
- prototype: `void __fastcall(PSID pSourceSid)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800049ac`
- `0x18000b95c`
- `0x1800139dc`
- `0x18001722c`
- `0x180020680`
- `0x180021980`

## import_xrefs

- `msvcrt!free` at `0x180021a93`
- `msvcrt!free` at `0x180021b0b`
- `msvcrt!free` at `0x180021a93`
- `msvcrt!free` at `0x180021b0b`
- `ADVAPI32!CopySid` at `0x180021a2a`
- `ADVAPI32!CopySid` at `0x180021a2a`
- `ADVAPI32!EqualSid` at `0x1800219b3`
- `ADVAPI32!EqualSid` at `0x1800219b3`
- `ADVAPI32!GetLengthSid` at `0x180021a0b`
- `ADVAPI32!GetLengthSid` at `0x180021a0b`
- `KERNEL32!LeaveCriticalSection` at `0x1800219fc`
- `KERNEL32!LeaveCriticalSection` at `0x180021a9d`
- `KERNEL32!LeaveCriticalSection` at `0x180021b15`
- `KERNEL32!LeaveCriticalSection` at `0x1800219fc`
- `KERNEL32!LeaveCriticalSection` at `0x180021a9d`
- `KERNEL32!LeaveCriticalSection` at `0x180021b15`
- `KERNEL32!GetLastError` at `0x180021a34`
- `KERNEL32!GetLastError` at `0x180021a71`
- `KERNEL32!GetLastError` at `0x180021a34`
- `KERNEL32!GetLastError` at `0x180021a71`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall MQSec_UpdateLocalMachineSid(PSID pSourceSid)
{
  DWORD LengthSid; // esi
  void *v3; // rbx
  __int64 LastError; // r9
  DWORD v5; // eax

  CCriticalSection::Lock((CCriticalSection *)&stru_180042DC0);
  if ( g_pLocalMachineSid && EqualSid(pSourceSid, g_pLocalMachineSid) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
    LeaveCriticalSection(&stru_180042DC0);
  }
  else
  {
    LengthSid = GetLengthSid(pSourceSid);
    v3 = MmAllocate(LengthSid);
    if ( CopySid(LengthSid, v3, pSourceSid) )
    {
      g_pOldLocalMachineSidAutoFree = g_pLocalMachineSid;
      g_pLocalMachineSid = v3;
      LODWORD(g_dwLocalMachineSidLen) = LengthSid;
      byte_180043174 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
      free(0);
      LeaveCriticalSection(&stru_180042DC0);
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 28, &WPP_efe327766876393cacc144e0c735893e_Traceguids, LastError);
      v5 = GetLastError();
      if ( v5 )
        LogMsgNTStatus(v5, (wchar_t *)L"acssctrl/acssinit", 0x5Bu);
      free(v3);
      LeaveCriticalSection(&stru_180042DC0);
    }
  }
}

```

## disassembly

```asm
0x180021980  mov     [rsp+arg_0], rbx
0x180021985  push    rbp
0x180021986  push    rsi
0x180021987  push    rdi
0x180021988  sub     rsp, 20h
0x18002198c  mov     rdi, rcx
0x18002198f  lea     rbp, stru_180042DC0
0x180021996  mov     [rsp+38h+arg_10], rbp
0x18002199b  mov     rcx, rbp; this
0x18002199e  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800219a3  nop
0x1800219a4  mov     rdx, cs:?g_pLocalMachineSid@@3PEAXEA; pSid2
0x1800219ab  test    rdx, rdx
0x1800219ae  jz      short loc_180021A08
0x1800219b0  mov     rcx, rdi; pSid1
0x1800219b3  call    cs:__imp_EqualSid
0x1800219b9  test    eax, eax
0x1800219bb  jz      short loc_180021A08
0x1800219bd  lea     rax, WPP_GLOBAL_Control
0x1800219c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219cb  cmp     rcx, rax
0x1800219ce  jz      short loc_1800219F9
0x1800219d0  test    byte ptr [rcx+10Ch], 4
0x1800219d7  jz      short loc_1800219F9
0x1800219d9  mov     edx, 1Bh
0x1800219de  mov     r9, cs:?g_pLocalMachineSid@@3PEAXEA; void * g_pLocalMachineSid
0x1800219e5  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x1800219ec  mov     rcx, [rcx+100h]; LoggerHandle
0x1800219f3  call    WPP_SF__sid_
0x1800219f8  nop
0x1800219f9  mov     rcx, rbp; lpCriticalSection
0x1800219fc  call    cs:__imp_LeaveCriticalSection
0x180021a02  nop
0x180021a03  jmp     loc_180021B1C
0x180021a08  mov     rcx, rdi; pSid
0x180021a0b  call    cs:__imp_GetLengthSid
0x180021a11  mov     esi, eax
0x180021a13  mov     ecx, eax; unsigned __int64
0x180021a15  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180021a1a  mov     rbx, rax
0x180021a1d  mov     [rsp+38h+arg_8], rax
0x180021a22  mov     r8, rdi; pSourceSid
0x180021a25  mov     rdx, rax; pDestinationSid
0x180021a28  mov     ecx, esi; nDestinationSidLength
0x180021a2a  call    cs:__imp_CopySid
0x180021a30  test    eax, eax
0x180021a32  jnz     short loc_180021AA6
0x180021a34  call    cs:__imp_GetLastError
0x180021a3a  mov     r9d, eax
0x180021a3d  lea     rax, WPP_GLOBAL_Control
0x180021a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a4b  cmp     rcx, rax
0x180021a4e  jz      short loc_180021A71
0x180021a50  test    byte ptr [rcx+10Ch], 1
0x180021a57  jz      short loc_180021A71
0x180021a59  mov     edx, 1Ch
0x180021a5e  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180021a65  mov     rcx, [rcx+100h]
0x180021a6c  call    WPP_SF_d
0x180021a71  call    cs:__imp_GetLastError
0x180021a77  test    eax, eax
0x180021a79  jz      short loc_180021A90
0x180021a7b  mov     r8d, 5Bh ; '['; unsigned __int16
0x180021a81  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x180021a88  mov     ecx, eax; int
0x180021a8a  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180021a8f  nop
0x180021a90  mov     rcx, rbx; Block
0x180021a93  call    cs:__imp_free
0x180021a99  nop
0x180021a9a  mov     rcx, rbp; lpCriticalSection
0x180021a9d  call    cs:__imp_LeaveCriticalSection
0x180021aa3  nop
0x180021aa4  jmp     short loc_180021B1C
0x180021aa6  mov     rax, cs:?g_pLocalMachineSid@@3PEAXEA; void * g_pLocalMachineSid
0x180021aad  mov     cs:?g_pOldLocalMachineSidAutoFree@@3V?$AP@E@@A, rax; AP<uchar> g_pOldLocalMachineSidAutoFree
0x180021ab4  mov     [rsp+38h+arg_8], 0
0x180021abd  mov     cs:?g_pLocalMachineSid@@3PEAXEA, rbx; void * g_pLocalMachineSid
0x180021ac4  mov     cs:?g_dwLocalMachineSidLen@@3KA, esi; ulong g_dwLocalMachineSidLen
0x180021aca  mov     cs:byte_180043174, 1
0x180021ad1  lea     rax, WPP_GLOBAL_Control
0x180021ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021adf  cmp     rcx, rax
0x180021ae2  jz      short loc_180021B09
0x180021ae4  test    byte ptr [rcx+10Ch], 4
0x180021aeb  jz      short loc_180021B09
0x180021aed  mov     edx, 1Dh
0x180021af2  mov     r9, rbx
0x180021af5  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180021afc  mov     rcx, [rcx+100h]; LoggerHandle
0x180021b03  call    WPP_SF__sid_
0x180021b08  nop
0x180021b09  xor     ecx, ecx; Block
0x180021b0b  call    cs:__imp_free
0x180021b11  nop
0x180021b12  mov     rcx, rbp; lpCriticalSection
0x180021b15  call    cs:__imp_LeaveCriticalSection
0x180021b1b  nop
0x180021b1c  mov     rbx, [rsp+38h+arg_0]
0x180021b21  add     rsp, 20h
0x180021b25  pop     rdi
0x180021b26  pop     rsi
0x180021b27  pop     rbp
0x180021b28  retn
```
