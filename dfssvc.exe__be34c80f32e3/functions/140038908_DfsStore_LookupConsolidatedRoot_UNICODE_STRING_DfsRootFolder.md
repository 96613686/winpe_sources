# DfsStore::LookupConsolidatedRoot(_UNICODE_STRING *,DfsRootFolder * *)

- ea: `0x140038908`
- end: `0x140038ab5`
- name: `?LookupConsolidatedRoot@DfsStore@@QEAAKPEAU_UNICODE_STRING@@PEAPEAVDfsRootFolder@@@Z`
- size: `429`
- prototype: `unsigned int(DfsStore *__hidden this, struct _UNICODE_STRING *, struct DfsRootFolder **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c664`

## callees

- `0x14000fca8`
- `0x14001e6d4`
- `0x140038908`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1400389f8`
- `ntdll!RtlCompareUnicodeString` at `0x1400389f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140038975`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140038975`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140038a30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140038a30`

## pseudocode

```c
__int64 __fastcall DfsStore::LookupConsolidatedRoot(
        DfsStore *this,
        struct _UNICODE_STRING *a2,
        struct DfsRootFolder **a3)
{
  __int64 v6; // rbx
  unsigned int v7; // ebp
  unsigned int *v8; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 17, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids, a2);
  }
  AcquireSRWLockShared((PSRWLOCK)this + 2);
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  v6 = *((_QWORD *)this + 7);
  v7 = 1168;
  if ( v6 )
  {
    v8 = pWppControl;
    do
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && v8
        && (v8[7] & 0x20) != 0
        && *((_BYTE *)v8 + 25) >= 3u )
      {
        WPP_SF_Z(*((_QWORD *)v8 + 2), 18, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids, v6 + 296);
        v8 = pWppControl;
      }
      if ( **(_WORD **)(v6 + 304) == 35 )
      {
        if ( !RtlCompareUnicodeString(a2, (PCUNICODE_STRING)(v6 + 296), 1u) )
        {
          v7 = 0;
          _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
          *a3 = (struct DfsRootFolder *)v6;
          break;
        }
        v8 = pWppControl;
      }
      v6 = *(_QWORD *)(v6 + 472);
    }
    while ( v6 != *((_QWORD *)this + 7) );
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 6);
  ReleaseSRWLockShared((PSRWLOCK)this + 2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (v7 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_ZqD(
      *((_QWORD *)pWppControl + 2),
      19,
      (unsigned int)WPP_417794ce451139ef3a777c1a55d669e5_Traceguids,
      (_DWORD)a2,
      v6,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140038908  mov     rax, rsp
0x14003890b  mov     [rax+8], rbx
0x14003890f  mov     [rax+10h], rbp
0x140038913  mov     [rax+18h], rsi
0x140038917  mov     [rax+20h], rdi
0x14003891b  push    r12
0x14003891d  push    r14
0x14003891f  push    r15
0x140038921  sub     rsp, 30h
0x140038925  mov     r12, r8
0x140038928  mov     r15, rdx
0x14003892b  mov     rdi, rcx
0x14003892e  lea     rax, WPP_GLOBAL_Control
0x140038935  mov     esi, 20h ; ' '
0x14003893a  cmp     cs:WPP_GLOBAL_Control, rax
0x140038941  jz      short loc_140038971
0x140038943  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003894a  test    rcx, rcx
0x14003894d  jz      short loc_140038971
0x14003894f  test    [rcx+1Ch], sil
0x140038953  jz      short loc_140038971
0x140038955  cmp     byte ptr [rcx+19h], 3
0x140038959  jb      short loc_140038971
0x14003895b  mov     rcx, [rcx+10h]
0x14003895f  lea     edx, [rsi-0Fh]
0x140038962  mov     r9, r15
0x140038965  lea     r8, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids
0x14003896c  call    WPP_SF_Z
0x140038971  lea     rcx, [rdi+10h]; SRWLock
0x140038975  call    cs:__imp_AcquireSRWLockShared
0x14003897c  nop     dword ptr [rax+rax+00h]
0x140038981  lock inc dword ptr [rdi+18h]
0x140038985  mov     rbx, [rdi+38h]
0x140038989  mov     ebp, 490h
0x14003898e  test    rbx, rbx
0x140038991  jz      loc_140038A28
0x140038997  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003899e  lea     r14, [rbx+128h]
0x1400389a5  lea     rax, WPP_GLOBAL_Control
0x1400389ac  cmp     cs:WPP_GLOBAL_Control, rax
0x1400389b3  jz      short loc_1400389E5
0x1400389b5  test    rcx, rcx
0x1400389b8  jz      short loc_1400389E5
0x1400389ba  test    [rcx+1Ch], sil
0x1400389be  jz      short loc_1400389E5
0x1400389c0  cmp     byte ptr [rcx+19h], 3
0x1400389c4  jb      short loc_1400389E5
0x1400389c6  mov     rcx, [rcx+10h]
0x1400389ca  lea     r8, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids
0x1400389d1  mov     edx, 12h
0x1400389d6  mov     r9, r14
0x1400389d9  call    WPP_SF_Z
0x1400389de  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400389e5  mov     rax, [r14+8]
0x1400389e9  cmp     word ptr [rax], 23h ; '#'
0x1400389ed  jnz     short loc_140038A0F
0x1400389ef  mov     r8b, 1; CaseInsensitive
0x1400389f2  mov     rdx, r14; String2
0x1400389f5  mov     rcx, r15; String1
0x1400389f8  call    cs:__imp_RtlCompareUnicodeString
0x1400389ff  nop     dword ptr [rax+rax+00h]
0x140038a04  test    eax, eax
0x140038a06  jz      short loc_140038A1E
0x140038a08  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038a0f  mov     rbx, [rbx+1D8h]
0x140038a16  cmp     rbx, [rdi+38h]
0x140038a1a  jnz     short loc_14003899E
0x140038a1c  jmp     short loc_140038A28
0x140038a1e  xor     ebp, ebp
0x140038a20  lock inc dword ptr [rbx+8]
0x140038a24  mov     [r12], rbx
0x140038a28  lock dec dword ptr [rdi+18h]
0x140038a2c  lea     rcx, [rdi+10h]; SRWLock
0x140038a30  call    cs:__imp_ReleaseSRWLockShared
0x140038a37  nop     dword ptr [rax+rax+00h]
0x140038a3c  lea     rax, WPP_GLOBAL_Control
0x140038a43  cmp     cs:WPP_GLOBAL_Control, rax
0x140038a4a  jz      short loc_140038A93
0x140038a4c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140038a53  test    rcx, rcx
0x140038a56  jz      short loc_140038A93
0x140038a58  mov     eax, ebp
0x140038a5a  neg     eax
0x140038a5c  sbb     edx, edx
0x140038a5e  and     edx, 0FFFFFFECh
0x140038a61  add     edx, 1Fh
0x140038a64  bts     esi, edx
0x140038a67  test    [rcx+1Ch], esi
0x140038a6a  jz      short loc_140038A93
0x140038a6c  cmp     byte ptr [rcx+19h], 3
0x140038a70  jb      short loc_140038A93
0x140038a72  mov     rcx, [rcx+10h]
0x140038a76  lea     r8, WPP_417794ce451139ef3a777c1a55d669e5_Traceguids
0x140038a7d  mov     edx, 13h
0x140038a82  mov     [rsp+48h+var_20], ebp
0x140038a86  mov     r9, r15
0x140038a89  mov     [rsp+48h+var_28], rbx
0x140038a8e  call    WPP_SF_ZqD
0x140038a93  mov     rbx, [rsp+48h+arg_0]
0x140038a98  mov     eax, ebp
0x140038a9a  mov     rbp, [rsp+48h+arg_8]
0x140038a9f  mov     rsi, [rsp+48h+arg_10]
0x140038aa4  mov     rdi, [rsp+48h+arg_18]
0x140038aa9  add     rsp, 30h
0x140038aad  pop     r15
0x140038aaf  pop     r14
0x140038ab1  pop     r12
0x140038ab3  retn
```
