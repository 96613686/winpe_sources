# MRxSmbCoreDeleteForSupercedeOrClose

- ea: `0x14003a204`
- end: `0x14003a38d`
- name: `MRxSmbCoreDeleteForSupercedeOrClose`
- size: `393`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002e3c0`
- `0x14003a5f0`
- `0x140052c00`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x140010aec`
- `0x14003a204`
- `0x140043228`
- `0x140043c5c`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`
- `0x14004ab38`
- `0x14004b1b0`

## pseudocode

```c
__int64 __fastcall MRxSmbCoreDeleteForSupercedeOrClose(char *pContext, __int64 a2, char a3)
{
  __int64 v6; // rcx
  _DWORD *v7; // r14
  char *v8; // rcx
  unsigned int started; // ebx
  __int64 v10; // r9
  int v11; // edx
  int v12; // r8d
  __int64 v14; // [rsp+20h] [rbp-78h]
  __int64 v15; // [rsp+20h] [rbp-78h]
  __int64 v16; // [rsp+20h] [rbp-78h]
  int v17; // [rsp+28h] [rbp-70h]
  int v18; // [rsp+28h] [rbp-70h]

  v6 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL);
  if ( v6 )
    v7 = *(_DWORD **)(v6 + 48);
  else
    v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
  v8 = pContext + 888;
  if ( a3 )
  {
    started = MRxSmbStartSMBCommand((__int64)v8, 1, 1, 3, v14, 0x10000u);
    if ( started )
      goto LABEL_17;
    MRxSmbStuffSMB(pContext + 888, "0B4!", *((_QWORD *)pContext + 108), v10, v16, v18);
  }
  else
  {
    started = MRxSmbStartSMBCommand((__int64)v8, 1, 6, 5, v14, 0x10000u);
    if ( started )
      goto LABEL_17;
    MRxSmbStuffSMB(pContext + 888, "0wB4!", 6, *((_QWORD *)pContext + 108), v15, v17);
  }
  started = SmbPseOrdinaryExchange(pContext);
  if ( started )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return started;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_DZ(WPP_GLOBAL_Control->AttachedDevice, v11, v12, started, *((_QWORD *)pContext + 108));
  }
  else
  {
    MRxSmbInvalidateFileInfoCache(a2);
    MRxSmbInvalidateFullDirectoryCacheParent(a2, 0);
    MRxSmbInvalidateInternalFileInfoCache(a2);
    MRxSmbCacheFileNotFound(a2);
    *v7 |= 0x100u;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x14003a204  push    rbx
0x14003a206  push    rbp
0x14003a207  push    rsi
0x14003a208  push    rdi
0x14003a209  push    r14
0x14003a20b  push    r15
0x14003a20d  sub     rsp, 68h
0x14003a211  mov     rax, [rdx+40h]
0x14003a215  mov     rdi, rcx
0x14003a218  mov     bl, r8b
0x14003a21b  mov     rsi, rdx
0x14003a21e  mov     rcx, [rax+20h]
0x14003a222  test    rcx, rcx
0x14003a225  jnz     short loc_14003A22C
0x14003a227  xor     r14d, r14d
0x14003a22a  jmp     short loc_14003A230
0x14003a22c  mov     r14, [rcx+30h]
0x14003a230  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a237  lea     r15, WPP_GLOBAL_Control
0x14003a23e  cmp     rcx, r15
0x14003a241  jz      short loc_14003A264
0x14003a243  test    dword ptr [rcx+2Ch], 400h
0x14003a24a  jz      short loc_14003A264
0x14003a24c  mov     rcx, [rcx+18h]
0x14003a250  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a257  mov     edx, 0Ch
0x14003a25c  mov     r9, rdi
0x14003a25f  call    WPP_SF_q
0x14003a264  mov     [rsp+98h+var_70], 10000h
0x14003a26c  lea     rbp, [rdi+378h]
0x14003a273  mov     rcx, rbp
0x14003a276  mov     edx, 1
0x14003a27b  test    bl, bl
0x14003a27d  jnz     short loc_14003A2B1
0x14003a27f  lea     r9d, [rdx+4]
0x14003a283  mov     r8b, 6
0x14003a286  call    MRxSmbStartSMBCommand
0x14003a28b  mov     ebx, eax
0x14003a28d  test    eax, eax
0x14003a28f  jnz     loc_14003A34C
0x14003a295  mov     r9, [rdi+360h]
0x14003a29c  lea     r8d, [rax+6]
0x14003a2a0  lea     rdx, a0wb4; "0wB4!"
0x14003a2a7  mov     rcx, rbp
0x14003a2aa  call    MRxSmbStuffSMB
0x14003a2af  jmp     short loc_14003A2DF
0x14003a2b1  mov     r9d, 3
0x14003a2b7  mov     r8b, 1
0x14003a2ba  call    MRxSmbStartSMBCommand
0x14003a2bf  mov     ebx, eax
0x14003a2c1  test    eax, eax
0x14003a2c3  jnz     loc_14003A34C
0x14003a2c9  mov     r8, [rdi+360h]
0x14003a2d0  lea     rdx, a0b4; "0B4!"
0x14003a2d7  mov     rcx, rbp
0x14003a2da  call    MRxSmbStuffSMB
0x14003a2df  mov     r8d, 16h
0x14003a2e5  mov     rdx, rsi
0x14003a2e8  mov     rcx, rdi; pContext
0x14003a2eb  call    SmbPseOrdinaryExchange
0x14003a2f0  mov     ebx, eax
0x14003a2f2  test    eax, eax
0x14003a2f4  jnz     short loc_14003A31F
0x14003a2f6  mov     rcx, rsi
0x14003a2f9  call    MRxSmbInvalidateFileInfoCache
0x14003a2fe  xor     edx, edx
0x14003a300  mov     rcx, rsi
0x14003a303  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14003a308  mov     rcx, rsi
0x14003a30b  call    MRxSmbInvalidateInternalFileInfoCache
0x14003a310  mov     rcx, rsi
0x14003a313  call    MRxSmbCacheFileNotFound
0x14003a318  bts     dword ptr [r14], 8
0x14003a31d  jmp     short loc_14003A34C
0x14003a31f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a326  cmp     rcx, r15
0x14003a329  jz      short loc_14003A37D
0x14003a32b  test    dword ptr [rcx+2Ch], 200h
0x14003a332  jz      short loc_14003A34C
0x14003a334  mov     rax, [rdi+360h]
0x14003a33b  mov     r9d, ebx
0x14003a33e  mov     rcx, [rcx+18h]
0x14003a342  mov     [rsp+98h+var_78], rax
0x14003a347  call    WPP_SF_DZ
0x14003a34c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a353  cmp     rcx, r15
0x14003a356  jz      short loc_14003A37D
0x14003a358  test    dword ptr [rcx+2Ch], 400h
0x14003a35f  jz      short loc_14003A37D
0x14003a361  mov     rcx, [rcx+18h]
0x14003a365  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a36c  mov     edx, 0Eh
0x14003a371  mov     dword ptr [rsp+98h+var_78], ebx
0x14003a375  mov     r9, rdi
0x14003a378  call    WPP_SF_qD
0x14003a37d  mov     eax, ebx
0x14003a37f  add     rsp, 68h
0x14003a383  pop     r15
0x14003a385  pop     r14
0x14003a387  pop     rdi
0x14003a388  pop     rsi
0x14003a389  pop     rbp
0x14003a38a  pop     rbx
0x14003a38b  retn
```
