# MidlSwDeviceCreationInfoToDasDeviceCreationInfo(_SW_DEVICE_CREATE_INFO const *,_DAS_SW_DEVICE_CREATE_INFO * *)

- ea: `0x14001a208`
- end: `0x14001a3a2`
- name: `?MidlSwDeviceCreationInfoToDasDeviceCreationInfo@@YAJPEBU_SW_DEVICE_CREATE_INFO@@PEAPEAU_DAS_SW_DEVICE_CREATE_INFO@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(const struct _SW_DEVICE_CREATE_INFO *, struct _DAS_SW_DEVICE_CREATE_INFO **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ef44`

## callees

- `0x1400020d0`
- `0x140009060`
- `0x140019db0`
- `0x140019f38`
- `0x14001a0e0`
- `0x14001a208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a34a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14001a340`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14001a340`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a38c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a38c`

## pseudocode

```c
__int64 __fastcall MidlSwDeviceCreationInfoToDasDeviceCreationInfo(
        const struct _SW_DEVICE_CREATE_INFO *a1,
        struct _DAS_SW_DEVICE_CREATE_INFO **a2)
{
  void *v4; // rax
  void *v5; // rdi
  int v6; // ebx
  _OWORD *v7; // rax
  unsigned __int8 *v8; // rcx
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rcx
  const unsigned __int16 *v11; // rcx
  const unsigned __int16 *v12; // rcx
  void *v13; // rcx
  signed int LastError; // eax
  ULONG StringSecurityDescriptorLen; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+68h] [rbp+20h] BYREF

  StringSecurityDescriptor = 0;
  StringSecurityDescriptorLen = 0;
  v4 = (void *)DAF_user_alloc(88);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    goto LABEL_24;
  }
  memset_0(v4, 0, 0x58u);
  *((_DWORD *)v5 + 14) = *((_DWORD *)a1 + 10);
  *(_DWORD *)v5 = 88;
  if ( *((_QWORD *)a1 + 4) )
  {
    v7 = (_OWORD *)DAF_user_alloc(16);
    *((_QWORD *)v5 + 6) = v7;
    if ( !v7 )
    {
      v6 = -2147024882;
      goto LABEL_22;
    }
    *v7 = *(_OWORD *)*((_QWORD *)a1 + 4);
  }
  v8 = (unsigned __int8 *)*((_QWORD *)a1 + 6);
  v6 = 0;
  if ( v8 )
  {
    v6 = MidlCopyString(v8, (unsigned __int8 **)v5 + 8);
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v9 = (unsigned __int8 *)*((_QWORD *)a1 + 7);
  if ( v9 )
  {
    v6 = MidlCopyString(v9, (unsigned __int8 **)v5 + 9);
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v10 = (unsigned __int8 *)*((_QWORD *)a1 + 1);
  if ( v10 )
  {
    v6 = MidlCopyString(v10, (unsigned __int8 **)v5 + 1);
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v11 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
  if ( v11 )
  {
    v6 = MidlMultiSzToStringArray(v11, (unsigned int *)v5 + 8, (unsigned __int16 ***)v5 + 5);
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v12 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
  if ( v12 )
  {
    v6 = MidlMultiSzToStringArray(v12, (unsigned int *)v5 + 4, (unsigned __int16 ***)v5 + 3);
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v13 = (void *)*((_QWORD *)a1 + 8);
  if ( v13 )
  {
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
            v13,
            1u,
            0x1Fu,
            &StringSecurityDescriptor,
            &StringSecurityDescriptorLen) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    v6 = MidlCopyString((unsigned __int8 *)StringSecurityDescriptor, (unsigned __int8 **)v5 + 10);
    if ( v6 < 0 )
    {
LABEL_22:
      MidlFreeDasDeviceCreationInfo((struct _DAS_SW_DEVICE_CREATE_INFO *)v5);
      goto LABEL_24;
    }
  }
  *a2 = (struct _DAS_SW_DEVICE_CREATE_INFO *)v5;
LABEL_24:
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001a208  mov     [rsp+arg_0], rbx
0x14001a20d  push    rsi
0x14001a20e  push    rdi
0x14001a20f  push    r14
0x14001a211  sub     rsp, 30h
0x14001a215  mov     rsi, rcx
0x14001a218  mov     [rsp+48h+StringSecurityDescriptor], 0
0x14001a221  mov     ebx, 58h ; 'X'
0x14001a226  mov     [rsp+48h+arg_10], 0
0x14001a22e  mov     ecx, ebx
0x14001a230  mov     r14, rdx
0x14001a233  call    DAF_user_alloc
0x14001a238  mov     rdi, rax
0x14001a23b  test    rax, rax
0x14001a23e  jnz     short loc_14001A24A
0x14001a240  mov     ebx, 8007000Eh
0x14001a245  jmp     loc_14001A382
0x14001a24a  mov     r8, rbx; Size
0x14001a24d  xor     edx, edx; Val
0x14001a24f  mov     rcx, rdi; void *
0x14001a252  call    memset_0
0x14001a257  mov     eax, [rsi+28h]
0x14001a25a  mov     [rdi+38h], eax
0x14001a25d  mov     [rdi], ebx
0x14001a25f  cmp     qword ptr [rsi+20h], 0
0x14001a264  jz      short loc_14001A291
0x14001a266  mov     ecx, 10h
0x14001a26b  call    DAF_user_alloc
0x14001a270  mov     [rdi+30h], rax
0x14001a274  mov     rcx, rax
0x14001a277  test    rax, rax
0x14001a27a  jnz     short loc_14001A286
0x14001a27c  mov     ebx, 8007000Eh
0x14001a281  jmp     loc_14001A375
0x14001a286  mov     rax, [rsi+20h]
0x14001a28a  movups  xmm0, xmmword ptr [rax]
0x14001a28d  movdqu  xmmword ptr [rcx], xmm0
0x14001a291  mov     rcx, [rsi+30h]; unsigned __int16 *
0x14001a295  xor     ebx, ebx
0x14001a297  test    rcx, rcx
0x14001a29a  jz      short loc_14001A2AF
0x14001a29c  lea     rdx, [rdi+40h]; unsigned __int16 **
0x14001a2a0  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14001a2a5  mov     ebx, eax
0x14001a2a7  test    eax, eax
0x14001a2a9  js      loc_14001A375
0x14001a2af  mov     rcx, [rsi+38h]; unsigned __int16 *
0x14001a2b3  test    rcx, rcx
0x14001a2b6  jz      short loc_14001A2CB
0x14001a2b8  lea     rdx, [rdi+48h]; unsigned __int16 **
0x14001a2bc  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14001a2c1  mov     ebx, eax
0x14001a2c3  test    eax, eax
0x14001a2c5  js      loc_14001A375
0x14001a2cb  mov     rcx, [rsi+8]; unsigned __int16 *
0x14001a2cf  test    rcx, rcx
0x14001a2d2  jz      short loc_14001A2E7
0x14001a2d4  lea     rdx, [rdi+8]; unsigned __int16 **
0x14001a2d8  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14001a2dd  mov     ebx, eax
0x14001a2df  test    eax, eax
0x14001a2e1  js      loc_14001A375
0x14001a2e7  mov     rcx, [rsi+18h]; unsigned __int16 *
0x14001a2eb  test    rcx, rcx
0x14001a2ee  jz      short loc_14001A303
0x14001a2f0  lea     r8, [rdi+28h]; unsigned __int16 ***
0x14001a2f4  lea     rdx, [rdi+20h]; unsigned int *
0x14001a2f8  call    ?MidlMultiSzToStringArray@@YAJPEBGPEAKPEAPEAPEAG@Z; MidlMultiSzToStringArray(ushort const *,ulong *,ushort * * *)
0x14001a2fd  mov     ebx, eax
0x14001a2ff  test    eax, eax
0x14001a301  js      short loc_14001A375
0x14001a303  mov     rcx, [rsi+10h]; unsigned __int16 *
0x14001a307  test    rcx, rcx
0x14001a30a  jz      short loc_14001A31F
0x14001a30c  lea     r8, [rdi+18h]; unsigned __int16 ***
0x14001a310  lea     rdx, [rdi+10h]; unsigned int *
0x14001a314  call    ?MidlMultiSzToStringArray@@YAJPEBGPEAKPEAPEAPEAG@Z; MidlMultiSzToStringArray(ushort const *,ulong *,ushort * * *)
0x14001a319  mov     ebx, eax
0x14001a31b  test    eax, eax
0x14001a31d  js      short loc_14001A375
0x14001a31f  mov     rcx, [rsi+40h]; SecurityDescriptor
0x14001a323  test    rcx, rcx
0x14001a326  jz      short loc_14001A37F
0x14001a328  mov     edx, 1; RequestedStringSDRevision
0x14001a32d  lea     rax, [rsp+48h+arg_10]
0x14001a332  lea     r9, [rsp+48h+StringSecurityDescriptor]; StringSecurityDescriptor
0x14001a337  mov     [rsp+48h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x14001a33c  lea     r8d, [rdx+1Eh]; SecurityInformation
0x14001a340  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x14001a346  test    eax, eax
0x14001a348  jnz     short loc_14001A361
0x14001a34a  call    cs:__imp_GetLastError
0x14001a350  mov     ebx, eax
0x14001a352  test    eax, eax
0x14001a354  jle     short loc_14001A375
0x14001a356  movzx   ebx, ax
0x14001a359  or      ebx, 80070000h
0x14001a35f  jmp     short loc_14001A375
0x14001a361  mov     rcx, [rsp+48h+StringSecurityDescriptor]; unsigned __int16 *
0x14001a366  lea     rdx, [rdi+50h]; unsigned __int16 **
0x14001a36a  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14001a36f  mov     ebx, eax
0x14001a371  test    eax, eax
0x14001a373  jns     short loc_14001A37F
0x14001a375  mov     rcx, rdi; struct _DAS_SW_DEVICE_CREATE_INFO *
0x14001a378  call    ?MidlFreeDasDeviceCreationInfo@@YAXPEAU_DAS_SW_DEVICE_CREATE_INFO@@@Z; MidlFreeDasDeviceCreationInfo(_DAS_SW_DEVICE_CREATE_INFO *)
0x14001a37d  jmp     short loc_14001A382
0x14001a37f  mov     [r14], rdi
0x14001a382  mov     rcx, [rsp+48h+StringSecurityDescriptor]; hMem
0x14001a387  test    rcx, rcx
0x14001a38a  jz      short loc_14001A392
0x14001a38c  call    cs:__imp_LocalFree
0x14001a392  mov     eax, ebx
0x14001a394  mov     rbx, [rsp+48h+arg_0]
0x14001a399  add     rsp, 30h
0x14001a39d  pop     r14
0x14001a39f  pop     rdi
0x14001a3a0  pop     rsi
0x14001a3a1  retn
```
