# MRxSmbRename

- ea: `0x14003c3f8`
- end: `0x14003c54a`
- name: `MRxSmbRename`
- size: `338`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x14002b980`
- `0x14002cc54`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14003c3f8`
- `0x140043228`
- `0x140043918`
- `0x1400439e0`
- `0x140043c5c`
- `0x140046120`
- `0x14004ab38`
- `0x14004b1b0`
- `0x14004d7f0`
- `0x14004dd50`

## pseudocode

```c
__int64 __fastcall MRxSmbRename(__int64 a1)
{
  int v1; // ebp
  __int64 v2; // rsi
  unsigned int OrdinaryExchange; // edi
  char v5; // dl
  __int64 v7; // [rsp+20h] [rbp-28h]
  PVOID pContext; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 448);
  v2 = *(_QWORD *)(a1 + 64);
  pContext = 0;
  while ( 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids);
    OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                         a1,
                         *(_QWORD *)(*(_QWORD *)(v2 + 32) + 40LL),
                         13,
                         (__int64)SmbPseExchangeStart_Rename,
                         v7,
                         (__int64 *)&pContext);
    if ( OrdinaryExchange )
      break;
    OrdinaryExchange = SmbCeInitiateExchange((unsigned __int8 *)pContext);
    SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)pContext);
    if ( OrdinaryExchange != -1069481983 )
    {
      if ( !OrdinaryExchange && v1 != 11 )
      {
        MRxSmbCacheFileNotFound(a1);
        MRxSmbInvalidateFileNotFoundCacheForRename(a1);
      }
      MRxSmbInvalidateFileInfoCache(a1);
      MRxSmbInvalidateInternalFileInfoCache(a1);
      MRxSmbInvalidateFullDirectoryCacheParent(a1, 0);
      MRxSmbInvalidateFullDirectoryCacheParentForRename(a1, v5);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids,
          OrdinaryExchange);
      }
      return OrdinaryExchange;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids);
  return OrdinaryExchange;
}

```

## disassembly

```asm
0x14003c3f8  mov     [rsp+arg_8], rbx
0x14003c3fd  mov     [rsp+arg_10], rbp
0x14003c402  push    rsi
0x14003c403  push    rdi
0x14003c404  push    r15
0x14003c406  sub     rsp, 30h
0x14003c40a  mov     ebp, [rcx+1C0h]
0x14003c410  lea     r15, WPP_GLOBAL_Control
0x14003c417  mov     rsi, [rcx+40h]
0x14003c41b  mov     rbx, rcx
0x14003c41e  mov     [rsp+48h+pContext], 0
0x14003c427  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c42e  cmp     rcx, r15
0x14003c431  jz      short loc_14003C451
0x14003c433  test    dword ptr [rcx+2Ch], 400h
0x14003c43a  jz      short loc_14003C451
0x14003c43c  mov     rcx, [rcx+18h]
0x14003c440  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c447  mov     edx, 0Ah
0x14003c44c  call    WPP_SF_
0x14003c451  mov     rdx, [rsi+20h]
0x14003c455  lea     rax, [rsp+48h+pContext]
0x14003c45a  lea     r9, SmbPseExchangeStart_Rename
0x14003c461  mov     [rsp+48h+var_20], rax
0x14003c466  mov     r8d, 0Dh
0x14003c46c  mov     rcx, rbx
0x14003c46f  mov     rdx, [rdx+28h]
0x14003c473  call    __SmbPseCreateOrdinaryExchange
0x14003c478  mov     edi, eax
0x14003c47a  test    eax, eax
0x14003c47c  jnz     loc_14003C50A
0x14003c482  mov     rcx, [rsp+48h+pContext]
0x14003c487  call    SmbCeInitiateExchange
0x14003c48c  mov     rcx, [rsp+48h+pContext]; pContext
0x14003c491  mov     edi, eax
0x14003c493  call    SmbPseFinalizeOrdinaryExchange
0x14003c498  cmp     edi, 0C0410001h
0x14003c49e  jz      short loc_14003C427
0x14003c4a0  test    edi, edi
0x14003c4a2  jnz     short loc_14003C4B9
0x14003c4a4  cmp     ebp, 0Bh
0x14003c4a7  jz      short loc_14003C4B9
0x14003c4a9  mov     rcx, rbx
0x14003c4ac  call    MRxSmbCacheFileNotFound
0x14003c4b1  mov     rcx, rbx
0x14003c4b4  call    MRxSmbInvalidateFileNotFoundCacheForRename
0x14003c4b9  mov     rcx, rbx
0x14003c4bc  call    MRxSmbInvalidateFileInfoCache
0x14003c4c1  mov     rcx, rbx
0x14003c4c4  call    MRxSmbInvalidateInternalFileInfoCache
0x14003c4c9  xor     edx, edx
0x14003c4cb  mov     rcx, rbx
0x14003c4ce  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14003c4d3  mov     rcx, rbx
0x14003c4d6  call    MRxSmbInvalidateFullDirectoryCacheParentForRename
0x14003c4db  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c4e2  cmp     rcx, r15
0x14003c4e5  jz      short loc_14003C534
0x14003c4e7  test    dword ptr [rcx+2Ch], 400h
0x14003c4ee  jz      short loc_14003C534
0x14003c4f0  mov     rcx, [rcx+18h]
0x14003c4f4  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c4fb  mov     edx, 0Ch
0x14003c500  mov     r9d, edi
0x14003c503  call    WPP_SF_d
0x14003c508  jmp     short loc_14003C534
0x14003c50a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c511  cmp     rcx, r15
0x14003c514  jz      short loc_14003C534
0x14003c516  test    dword ptr [rcx+2Ch], 400h
0x14003c51d  jz      short loc_14003C534
0x14003c51f  mov     rcx, [rcx+18h]
0x14003c523  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c52a  mov     edx, 0Bh
0x14003c52f  call    WPP_SF_
0x14003c534  mov     rbx, [rsp+48h+arg_8]
0x14003c539  mov     eax, edi
0x14003c53b  mov     rbp, [rsp+48h+arg_10]
0x14003c540  add     rsp, 30h
0x14003c544  pop     r15
0x14003c546  pop     rdi
0x14003c547  pop     rsi
0x14003c548  retn
```
