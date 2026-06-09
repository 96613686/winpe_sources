# MRxSmbSetFileAttributes

- ea: `0x14003b4c8`
- end: `0x14003b8cc`
- name: `MRxSmbSetFileAttributes`
- size: `1028`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14002e3c0`
- `0x14003a5f0`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x140039dc4`
- `0x14003b4c8`
- `0x14003b8d4`
- `0x140043228`
- `0x14004442c`
- `0x140044624`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`
- `0x14004ab38`
- `0x14004b1b0`
- `0x1400507a0`
- `0x1400526e4`

## pseudocode

```c
__int64 __fastcall MRxSmbSetFileAttributes(_QWORD *pContext, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  int v8; // esi
  __int64 v9; // r15
  __int64 *v10; // r14
  __int64 v11; // rbx
  bool v12; // zf
  char v13; // al
  unsigned int started; // ebx
  _QWORD *v15; // rcx
  unsigned __int16 v16; // r15
  unsigned int v17; // eax
  __int64 v18; // r8
  __int64 v20; // [rsp+20h] [rbp-A9h]
  __int64 v21; // [rsp+20h] [rbp-A9h]
  _WORD v22[2]; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int16 v23; // [rsp+64h] [rbp-65h] BYREF
  unsigned __int16 v24; // [rsp+68h] [rbp-61h] BYREF
  __int64 v25; // [rsp+70h] [rbp-59h]
  int v26; // [rsp+78h] [rbp-51h]
  int v27; // [rsp+7Ch] [rbp-4Dh]
  int v28; // [rsp+80h] [rbp-49h]
  int v29; // [rsp+84h] [rbp-45h]
  int v30; // [rsp+88h] [rbp-41h]
  int v31; // [rsp+8Ch] [rbp-3Dh]
  unsigned int v32; // [rsp+90h] [rbp-39h] BYREF
  _QWORD *v33; // [rsp+98h] [rbp-31h]
  __int64 v34; // [rsp+A0h] [rbp-29h]
  __int64 v35; // [rsp+A8h] [rbp-21h]
  _QWORD v36[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-9h]
  __int64 v38; // [rsp+C8h] [rbp-1h]
  int v39; // [rsp+D0h] [rbp+7h]
  int v40; // [rsp+D4h] [rbp+Bh]
  unsigned __int16 v41; // [rsp+130h] [rbp+67h] BYREF
  unsigned __int16 v42; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned int v43; // [rsp+140h] [rbp+77h]
  unsigned __int16 v44; // [rsp+148h] [rbp+7Fh] BYREF

  v43 = a3;
  v3 = *(_QWORD *)(a2 + 64);
  v34 = 0;
  v5 = *(_QWORD *)(a2 + 56);
  v6 = 0;
  v25 = 0;
  v35 = v5;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
    v6 = 0;
  }
  if ( v3 && (v6 = *(_QWORD *)(v3 + 32), (v25 = v6) != 0) )
  {
    v11 = *(_QWORD *)(v6 + 48);
    v34 = v11;
  }
  else
  {
    v11 = 0;
  }
  v12 = *(_BYTE *)(a2 + 32) == 6;
  v26 = 0;
  v41 = 0;
  v27 = 0;
  v42 = 0;
  v28 = 0;
  v44 = 0;
  v29 = 0;
  v22[0] = 0;
  v30 = 0;
  v23 = 0;
  v31 = 0;
  v24 = 0;
  if ( v12 )
  {
    v9 = pContext[70];
    v13 = 0;
    v8 = *(_DWORD *)(v9 + 32);
    v10 = (__int64 *)(v9 + 16);
    if ( *(_QWORD *)(v9 + 16) )
    {
      if ( !(unsigned __int8)MRxSmbTimeToSecondsSince1970(v9 + 16, pContext[10] + 400LL, &v32)
        || !(unsigned __int8)MRxSmbConvertTimeToSmbTime(v9 + 16, pContext, &v41, &v42) )
      {
        goto LABEL_11;
      }
      v13 = 1;
      v26 = v41;
      v27 = v42;
    }
    v15 = (_QWORD *)(v9 + 8);
    v33 = (_QWORD *)(v9 + 8);
    if ( *(_QWORD *)(v9 + 8) )
    {
      if ( !(unsigned __int8)MRxSmbConvertTimeToSmbTime(v15, pContext, &v44, v22) )
        goto LABEL_11;
      v13 = 1;
      v28 = v44;
      v29 = v22[0];
      v15 = v33;
    }
    if ( !*(_QWORD *)v9 )
    {
      if ( !v13 && !v8 )
      {
LABEL_22:
        started = 0;
        goto LABEL_49;
      }
      v6 = v25;
      goto LABEL_25;
    }
    if ( (unsigned __int8)MRxSmbConvertTimeToSmbTime(v9, pContext, &v23, &v24) )
    {
      v15 = v33;
      v30 = v23;
      v31 = v24;
      v6 = v25;
      goto LABEL_25;
    }
LABEL_11:
    started = -1073741811;
    goto LABEL_49;
  }
  v15 = 0;
LABEL_25:
  if ( v11
    && !v8
    && *(_BYTE *)(a2 + 32) == 6
    && (*(_DWORD *)(v6 + 72) & 0x100000) == 0
    && (*v10 || *v15 || *(_QWORD *)v9) )
  {
    started = MRxSmbStartSMBCommand((__int64)(pContext + 111), 1, 34, 17, v20, 0x10000u);
    if ( started )
      goto LABEL_49;
    LODWORD(v21) = (unsigned __int16)v30;
    MRxSmbStuffSMB(
      pContext + 111,
      "0wwwwwwwB!",
      *(unsigned __int16 *)(v34 + 8),
      (unsigned __int16)v31,
      v21,
      (unsigned __int16)v29);
    v16 = v43;
  }
  else
  {
    started = MRxSmbStartSMBCommand((__int64)(pContext + 111), 1, 9, 19, v20, 0x10000u);
    if ( started )
      goto LABEL_49;
    v16 = v43;
    MRxSmbStuffSMB(pContext + 111, "0wdwwwwwB4!", v43, v32, 0, 0);
  }
  v17 = SmbPseOrdinaryExchange(pContext);
  started = v17;
  if ( !v17 )
  {
    if ( *(_BYTE *)(a2 + 32) != 6 )
      v8 = MRxSmbMapSmbAttributes(v16);
    v40 = 0;
    v18 = 0;
    v38 = 0;
    v36[0] = 0;
    v37 = 0;
    v36[1] = 0;
    if ( v10 )
    {
      if ( *v10 )
        v18 = *v10;
      v37 = v18;
    }
    v39 = v8;
    MRxSmbUpdateBasicFileInfoCacheAll(a2, (__int64)v36);
    MRxSmbInvalidateFullDirectoryCacheParent(a2, 1);
    MRxSmbUpdateStandardFileInfoCache(a2, 0, v8 & 0x10);
    MRxSmbInvalidateFileNotFoundCache(a2);
    MRxSmbInvalidateFullDirectoryCacheParent(a2, 0);
    goto LABEL_22;
  }
  if ( v17 == -1073741772 || v17 == -1073741766 )
    MRxSmbCacheFileNotFound(a2);
  else
    MRxSmbInvalidateFileNotFoundCache(a2);
  MRxSmbInvalidateFileInfoCache(a2);
LABEL_49:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x14003b4c8  mov     [rsp-8+arg_10], r8d
0x14003b4cd  push    rbp
0x14003b4ce  push    rbx
0x14003b4cf  push    rsi
0x14003b4d0  push    rdi
0x14003b4d1  push    r12
0x14003b4d3  push    r13
0x14003b4d5  push    r14
0x14003b4d7  push    r15
0x14003b4d9  lea     rbp, [rsp-1Fh]
0x14003b4de  sub     rsp, 0E8h
0x14003b4e5  mov     rbx, [rdx+40h]
0x14003b4e9  xor     r12d, r12d
0x14003b4ec  mov     r13, rcx
0x14003b4ef  mov     [rbp+57h+var_80], r12
0x14003b4f3  mov     rcx, [rdx+38h]
0x14003b4f7  mov     eax, r12d
0x14003b4fa  mov     [rbp+57h+var_B0], rax
0x14003b4fe  mov     rdi, rdx
0x14003b501  mov     [rbp+57h+var_78], rcx
0x14003b505  mov     esi, r12d
0x14003b508  mov     [rbp+57h+var_90], r12d
0x14003b50c  mov     r15d, r12d
0x14003b50f  mov     r14d, r12d
0x14003b512  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b519  lea     rdx, WPP_GLOBAL_Control
0x14003b520  cmp     rcx, rdx
0x14003b523  jz      short loc_14003B54A
0x14003b525  test    dword ptr [rcx+2Ch], 400h
0x14003b52c  jz      short loc_14003B54A
0x14003b52e  mov     rcx, [rcx+18h]
0x14003b532  lea     edx, [r12+13h]
0x14003b537  mov     r9, r13
0x14003b53a  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003b541  call    WPP_SF_q
0x14003b546  mov     eax, esi
0x14003b548  jmp     short $+2
0x14003b54a  test    rbx, rbx
0x14003b54d  jz      short loc_14003B566
0x14003b54f  mov     rax, [rbx+20h]
0x14003b553  mov     [rbp+57h+var_B0], rax
0x14003b557  test    rax, rax
0x14003b55a  jz      short loc_14003B566
0x14003b55c  mov     rbx, [rax+30h]
0x14003b560  mov     [rbp+57h+var_80], rbx
0x14003b564  jmp     short loc_14003B569
0x14003b566  mov     rbx, rsi
0x14003b569  cmp     byte ptr [rdi+20h], 6
0x14003b56d  mov     edx, r12d
0x14003b570  mov     [rbp+57h+var_A8], edx
0x14003b573  mov     [rbp+57h+arg_0], dx
0x14003b577  mov     [rbp+57h+var_A4], edx
0x14003b57a  mov     [rbp+57h+arg_8], dx
0x14003b57e  mov     [rbp+57h+var_A0], edx
0x14003b581  mov     [rbp+57h+arg_18], dx
0x14003b585  mov     [rbp+57h+var_9C], edx
0x14003b588  mov     [rbp+57h+var_C0], dx
0x14003b58c  mov     [rbp+57h+var_98], r12d
0x14003b590  mov     [rbp+57h+var_BC], r12w
0x14003b595  mov     [rbp+57h+var_94], r12d
0x14003b599  mov     [rbp+57h+var_B8], r12w
0x14003b59e  jnz     loc_14003B68A
0x14003b5a4  mov     r15, [r13+230h]
0x14003b5ab  mov     al, r12b
0x14003b5ae  mov     esi, [r15+20h]
0x14003b5b2  lea     r14, [r15+10h]
0x14003b5b6  cmp     [r14], r12
0x14003b5b9  jz      short loc_14003B607
0x14003b5bb  mov     rdx, [r13+50h]
0x14003b5bf  lea     r8, [rbp+57h+var_90]
0x14003b5c3  add     rdx, 190h
0x14003b5ca  mov     rcx, r14
0x14003b5cd  call    MRxSmbTimeToSecondsSince1970
0x14003b5d2  test    al, al
0x14003b5d4  jnz     short loc_14003B5E0
0x14003b5d6  mov     ebx, 0C000000Dh
0x14003b5db  jmp     loc_14003B87D
0x14003b5e0  lea     r9, [rbp+57h+arg_8]
0x14003b5e4  mov     rdx, r13
0x14003b5e7  lea     r8, [rbp+57h+arg_0]
0x14003b5eb  mov     rcx, r14
0x14003b5ee  call    MRxSmbConvertTimeToSmbTime
0x14003b5f3  test    al, al
0x14003b5f5  jz      short loc_14003B5D6
0x14003b5f7  movzx   ecx, [rbp+57h+arg_0]
0x14003b5fb  mov     al, 1
0x14003b5fd  mov     [rbp+57h+var_A8], ecx
0x14003b600  movzx   ecx, [rbp+57h+arg_8]
0x14003b604  mov     [rbp+57h+var_A4], ecx
0x14003b607  lea     rcx, [r15+8]
0x14003b60b  mov     [rbp+57h+var_88], rcx
0x14003b60f  cmp     [rcx], r12
0x14003b612  jz      short loc_14003B63C
0x14003b614  lea     r9, [rbp+57h+var_C0]
0x14003b618  mov     rdx, r13
0x14003b61b  lea     r8, [rbp+57h+arg_18]
0x14003b61f  call    MRxSmbConvertTimeToSmbTime
0x14003b624  test    al, al
0x14003b626  jz      short loc_14003B5D6
0x14003b628  movzx   ecx, [rbp+57h+arg_18]
0x14003b62c  mov     al, 1
0x14003b62e  mov     [rbp+57h+var_A0], ecx
0x14003b631  movzx   ecx, [rbp+57h+var_C0]
0x14003b635  mov     [rbp+57h+var_9C], ecx
0x14003b638  mov     rcx, [rbp+57h+var_88]
0x14003b63c  cmp     [r15], r12
0x14003b63f  jz      short loc_14003B674
0x14003b641  lea     r9, [rbp+57h+var_B8]
0x14003b645  mov     rdx, r13
0x14003b648  lea     r8, [rbp+57h+var_BC]
0x14003b64c  mov     rcx, r15
0x14003b64f  call    MRxSmbConvertTimeToSmbTime
0x14003b654  test    al, al
0x14003b656  jz      loc_14003B5D6
0x14003b65c  movzx   eax, [rbp+57h+var_BC]
0x14003b660  mov     rcx, [rbp+57h+var_88]
0x14003b664  mov     [rbp+57h+var_98], eax
0x14003b667  movzx   eax, [rbp+57h+var_B8]
0x14003b66b  mov     [rbp+57h+var_94], eax
0x14003b66e  mov     rax, [rbp+57h+var_B0]
0x14003b672  jmp     short loc_14003B68D
0x14003b674  test    al, al
0x14003b676  jnz     short loc_14003B684
0x14003b678  test    esi, esi
0x14003b67a  jnz     short loc_14003B684
0x14003b67c  mov     ebx, r12d
0x14003b67f  jmp     loc_14003B87D
0x14003b684  mov     rax, [rbp+57h+var_B0]
0x14003b688  jmp     short loc_14003B68D
0x14003b68a  mov     rcx, rdx
0x14003b68d  xor     edx, edx
0x14003b68f  lea     r12, [r13+378h]
0x14003b696  test    rbx, rbx
0x14003b699  jz      loc_14003B756
0x14003b69f  test    esi, esi
0x14003b6a1  jnz     loc_14003B756
0x14003b6a7  cmp     byte ptr [rdi+20h], 6
0x14003b6ab  jnz     loc_14003B756
0x14003b6b1  test    dword ptr [rax+48h], 100000h
0x14003b6b8  jnz     loc_14003B756
0x14003b6be  cmp     [r14], rdx
0x14003b6c1  jnz     short loc_14003B6D1
0x14003b6c3  cmp     [rcx], rdx
0x14003b6c6  jnz     short loc_14003B6D1
0x14003b6c8  cmp     [r15], rdx
0x14003b6cb  jz      loc_14003B756
0x14003b6d1  mov     r9d, 11h
0x14003b6d7  mov     dword ptr [rsp+120h+var_F8], 10000h
0x14003b6df  mov     r8b, 22h ; '"'
0x14003b6e2  mov     rcx, r12
0x14003b6e5  lea     edx, [r9-10h]
0x14003b6e9  call    MRxSmbStartSMBCommand
0x14003b6ee  mov     ebx, eax
0x14003b6f0  test    eax, eax
0x14003b6f2  jnz     loc_14003B87D
0x14003b6f8  mov     rcx, [rbp+57h+var_80]
0x14003b6fc  movzx   eax, word ptr [rbp+57h+var_A8]
0x14003b700  movzx   edx, word ptr [rbp+57h+var_A4]
0x14003b704  movzx   r10d, word ptr [rbp+57h+var_A0]
0x14003b709  movzx   r11d, word ptr [rbp+57h+var_9C]
0x14003b70e  movzx   r8d, word ptr [rcx+8]
0x14003b713  mov     rcx, r12
0x14003b716  movzx   ebx, word ptr [rbp+57h+var_98]
0x14003b71a  movzx   r9d, word ptr [rbp+57h+var_94]
0x14003b71f  mov     [rsp+120h+var_D8], 0
0x14003b728  mov     dword ptr [rsp+120h+var_E0], eax
0x14003b72c  mov     dword ptr [rsp+120h+var_E8], edx
0x14003b730  lea     rdx, a0wwwwwwwb; "0wwwwwwwB!"
0x14003b737  mov     dword ptr [rsp+120h+var_F0], r10d
0x14003b73c  mov     dword ptr [rsp+120h+var_F8], r11d
0x14003b741  mov     dword ptr [rsp+120h+var_100], ebx
0x14003b745  call    MRxSmbStuffSMB
0x14003b74a  mov     r15d, [rbp+57h+arg_10]
0x14003b74e  mov     r8d, 1Bh
0x14003b754  jmp     short loc_14003B7C5
0x14003b756  mov     r9d, 13h
0x14003b75c  mov     dword ptr [rsp+120h+var_F8], 10000h
0x14003b764  mov     r8b, 9
0x14003b767  mov     rcx, r12
0x14003b76a  lea     edx, [r9-12h]
0x14003b76e  call    MRxSmbStartSMBCommand
0x14003b773  xor     ecx, ecx
0x14003b775  mov     ebx, eax
0x14003b777  test    eax, eax
0x14003b779  jnz     loc_14003B87D
0x14003b77f  mov     rax, [rbp+57h+var_78]
0x14003b783  lea     rdx, a0wdwwwwwb4; "0wdwwwwwB4!"
0x14003b78a  mov     r15d, [rbp+57h+arg_10]
0x14003b78e  add     rax, 168h
0x14003b794  mov     r9d, [rbp+57h+var_90]
0x14003b798  mov     r8d, r15d
0x14003b79b  mov     [rsp+120h+var_D8], rax
0x14003b7a0  mov     [rsp+120h+var_E0], rcx
0x14003b7a5  mov     [rsp+120h+var_E8], rcx
0x14003b7aa  mov     [rsp+120h+var_F0], rcx
0x14003b7af  mov     [rsp+120h+var_F8], rcx
0x14003b7b4  mov     [rsp+120h+var_100], rcx
0x14003b7b9  mov     rcx, r12
0x14003b7bc  call    MRxSmbStuffSMB
0x14003b7c1  lea     r8d, [rbx+1Ah]
0x14003b7c5  mov     rdx, rdi
0x14003b7c8  mov     rcx, r13; pContext
0x14003b7cb  call    SmbPseOrdinaryExchange
0x14003b7d0  xor     r12d, r12d
0x14003b7d3  mov     ebx, eax
0x14003b7d5  test    eax, eax
0x14003b7d7  jnz     short loc_14003B855
0x14003b7d9  cmp     byte ptr [rdi+20h], 6
0x14003b7dd  jz      short loc_14003B7EA
0x14003b7df  movzx   ecx, r15w
0x14003b7e3  call    MRxSmbMapSmbAttributes
0x14003b7e8  mov     esi, eax
0x14003b7ea  mov     [rbp+57h+var_4C], r12d
0x14003b7ee  mov     r8, r12
0x14003b7f1  mov     [rbp+57h+var_58], r12
0x14003b7f5  mov     [rbp+57h+var_70], r12
0x14003b7f9  mov     [rbp+57h+var_60], r12
0x14003b7fd  mov     [rbp+57h+var_68], r12
0x14003b801  test    r14, r14
0x14003b804  jz      short loc_14003B814
0x14003b806  mov     rcx, [r14]
0x14003b809  test    rcx, rcx
0x14003b80c  cmovnz  r8, rcx
0x14003b810  mov     [rbp+57h+var_60], r8
0x14003b814  lea     rdx, [rbp+57h+var_70]
0x14003b818  mov     [rbp+57h+var_50], esi
0x14003b81b  mov     rcx, rdi
0x14003b81e  call    MRxSmbUpdateBasicFileInfoCacheAll
0x14003b823  mov     dl, 1
0x14003b825  mov     rcx, rdi
0x14003b828  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14003b82d  and     sil, 10h
0x14003b831  xor     edx, edx
0x14003b833  mov     r8b, sil
0x14003b836  mov     rcx, rdi
0x14003b839  call    MRxSmbUpdateStandardFileInfoCache
0x14003b83e  mov     rcx, rdi
0x14003b841  call    MRxSmbInvalidateFileNotFoundCache
0x14003b846  xor     edx, edx
0x14003b848  mov     rcx, rdi
0x14003b84b  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14003b850  jmp     loc_14003B67C
0x14003b855  cmp     eax, 0C0000034h
0x14003b85a  jz      short loc_14003B86D
0x14003b85c  cmp     eax, 0C000003Ah
0x14003b861  jz      short loc_14003B86D
0x14003b863  mov     rcx, rdi
0x14003b866  call    MRxSmbInvalidateFileNotFoundCache
0x14003b86b  jmp     short loc_14003B875
0x14003b86d  mov     rcx, rdi
0x14003b870  call    MRxSmbCacheFileNotFound
0x14003b875  mov     rcx, rdi
0x14003b878  call    MRxSmbInvalidateFileInfoCache
0x14003b87d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b884  lea     rax, WPP_GLOBAL_Control
0x14003b88b  cmp     rcx, rax
0x14003b88e  jz      short loc_14003B8B5
0x14003b890  test    dword ptr [rcx+2Ch], 400h
0x14003b897  jz      short loc_14003B8B5
0x14003b899  mov     rcx, [rcx+18h]
0x14003b89d  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003b8a4  mov     edx, 14h
0x14003b8a9  mov     dword ptr [rsp+120h+var_100], ebx
0x14003b8ad  mov     r9, r13
0x14003b8b0  call    WPP_SF_qD
0x14003b8b5  mov     eax, ebx
0x14003b8b7  add     rsp, 0E8h
0x14003b8be  pop     r15
0x14003b8c0  pop     r14
0x14003b8c2  pop     r13
0x14003b8c4  pop     r12
0x14003b8c6  pop     rdi
0x14003b8c7  pop     rsi
0x14003b8c8  pop     rbx
0x14003b8c9  pop     rbp
0x14003b8ca  retn
```
