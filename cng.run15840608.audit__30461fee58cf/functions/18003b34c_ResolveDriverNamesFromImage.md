# _ResolveDriverNamesFromImage

- ea: `0x18003b34c`
- end: `0x18003b922`
- name: `_ResolveDriverNamesFromImage`
- size: `1494`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003b174`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18003b34c`
- `0x180048b98`
- `0x18009d820`
- `0x18009da40`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18003b5dc`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b5dc`
- `ntoskrnl!ZwClose` at `0x18003b693`
- `ntoskrnl!ZwClose` at `0x18003b8a4`
- `ntoskrnl!ZwClose` at `0x18003b8d3`
- `ntoskrnl!ZwClose` at `0x18003b693`
- `ntoskrnl!ZwClose` at `0x18003b8a4`
- `ntoskrnl!ZwClose` at `0x18003b8d3`
- `ntoskrnl!ZwOpenKey` at `0x18003b42c`
- `ntoskrnl!ZwOpenKey` at `0x18003b597`
- `ntoskrnl!ZwOpenKey` at `0x18003b42c`
- `ntoskrnl!ZwOpenKey` at `0x18003b597`
- `ntoskrnl!ZwEnumerateKey` at `0x18003b4df`
- `ntoskrnl!ZwEnumerateKey` at `0x18003b4df`

## string_xrefs

- `0x18003b465`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b4a2`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b39a`: `ImagePath`
- `0x18003b383`: `\Registry\Machine\System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall ResolveDriverNamesFromImage(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v3; // rdi
  unsigned int *v4; // rsi
  NTSTATUS v7; // ebx
  int v8; // r8d
  int v9; // edx
  ULONG Length; // ecx
  ULONG v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int16 v17; // ax
  unsigned __int16 v18; // ax
  void *v19; // rax
  __int16 v20; // ax
  unsigned __int16 v21; // ax
  void *v22; // rax
  void *v23; // rcx
  void *v24; // rcx
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v27; // [rsp+44h] [rbp-BCh]
  ULONG v28; // [rsp+48h] [rbp-B8h]
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v30; // [rsp+58h] [rbp-A8h]
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v37; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING ValueName; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-28h]
  _BYTE KeyValueInformation[528]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE KeyInformation[544]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v40 = a1;
  *(&ObjectAttributes.Length + 1) = 0;
  Src = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services";
  v3 = KeyInformation;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ValueName.Buffer = L"ImagePath";
  v4 = (unsigned int *)KeyValueInformation;
  KeyHandle = 0;
  v36 = 0;
  Handle = 0;
  v32 = 6815846;
  *(_QWORD *)&ValueName.Length = 1310738;
  ResultLength = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( a2 )
    *(_QWORD *)(a2 + 8) = 0;
  if ( a3 )
    *(_QWORD *)(a3 + 8) = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v32;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    Length = 536;
    v30 = 528;
    v11 = 0;
    v28 = 536;
    while ( 1 )
    {
      v27 = v11;
      if ( v11 >= 0x10000 )
        break;
      if ( v3 )
      {
        while ( 1 )
        {
          v12 = ZwEnumerateKey(KeyHandle, v11, KeyBasicInformation, v3, Length, &ResultLength);
          v7 = v12;
          if ( v12 != -1073741789 && v12 != -2147483643 )
            break;
          if ( v3 != (_WORD *)KeyInformation )
            MSCryptFree(v3);
          v28 = (ResultLength + 255) & 0xFFFFFF00;
          v3 = (_WORD *)MSCryptAlloc(v28);
          if ( !v3 )
          {
            v15 = 656;
            goto LABEL_49;
          }
          v11 = v27;
          Length = v28;
        }
      }
      if ( v7 < 0 )
      {
        if ( v7 != -2147483622 )
          goto LABEL_51;
        v7 = -1073741275;
        v15 = 668;
        v16 = 3221226021LL;
        goto LABEL_50;
      }
      WORD1(v34) = v3[6];
      LOWORD(v34) = WORD1(v34);
      ObjectAttributes.Length = 48;
      v35 = v3 + 8;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v34;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      if ( v7 >= 0 )
      {
        if ( v4 )
        {
          while ( 1 )
          {
            v13 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, v4, v30, &ResultLength);
            v7 = v13;
            if ( v13 != -1073741789 && v13 != -2147483643 )
              break;
            if ( v4 != (unsigned int *)KeyValueInformation )
              MSCryptFree(v4);
            v30 = (ResultLength + 255) & 0xFFFFFF00;
            v4 = (unsigned int *)MSCryptAlloc(v30);
            if ( !v4 )
            {
              v7 = -1073741670;
              DebugTraceError(
                3221225626LL,
                "sResult",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                733);
              goto LABEL_33;
            }
          }
        }
        if ( v7 >= 0 )
        {
          v14 = v4[2];
          if ( (unsigned int)v14 > 2 )
          {
            while ( !*(_WORD *)((char *)v4 + v14 + 10) )
            {
              v14 = (unsigned int)(v14 - 2);
              v4[2] = v14;
            }
            WORD1(v36) = *((_WORD *)v4 + 4);
            LOWORD(v36) = WORD1(v36);
            v37 = v4 + 3;
            if ( (unsigned int)IsImagePath(&v36, v40) )
              goto LABEL_40;
          }
        }
LABEL_33:
        ZwClose(Handle);
        Handle = 0;
      }
      Length = v28;
      v11 = v27 + 1;
    }
    if ( v11 == 0x10000 )
    {
      v7 = -1073741275;
      DebugTraceError(3221226021LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 773);
    }
    else
    {
LABEL_40:
      if ( v7 >= 0 )
      {
        if ( a2 )
        {
          v17 = v32 + v34 + 2;
          *(_WORD *)a2 = v17;
          v18 = (v17 + 7) & 0xFFF8;
          *(_WORD *)(a2 + 2) = v18;
          v19 = (void *)MSCryptAlloc(v18);
          *(_QWORD *)(a2 + 8) = v19;
          if ( !v19 )
          {
            v7 = -1073741670;
            DebugTraceError(3221225626LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 792);
            goto LABEL_52;
          }
          memmove(v19, Src, (unsigned __int16)v32);
          *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * ((unsigned __int64)(unsigned __int16)v32 >> 1)) = 92;
          memmove(
            (void *)(*(_QWORD *)(a2 + 8) + 2 * (((unsigned __int64)(unsigned __int16)v32 >> 1) + 1)),
            v3 + 8,
            *((unsigned int *)v3 + 3));
        }
        if ( a3 )
        {
          v20 = v34 + 16;
          *(_WORD *)a3 = v34 + 16;
          v21 = (v20 + 7) & 0xFFF8;
          *(_WORD *)(a3 + 2) = v21;
          v22 = (void *)MSCryptAlloc(v21);
          *(_QWORD *)(a3 + 8) = v22;
          if ( !v22 )
          {
            v15 = 816;
LABEL_49:
            v7 = -1073741670;
            v16 = 3221225626LL;
            goto LABEL_50;
          }
          memmove(v22, L"\\Device", 0xEu);
          *(_WORD *)(*(_QWORD *)(a3 + 8) + 14LL) = 92;
          memmove((void *)(*(_QWORD *)(a3 + 8) + 16LL), v3 + 8, *((unsigned int *)v3 + 3));
        }
        v7 = 0;
        goto LABEL_61;
      }
    }
    v15 = 778;
    v16 = (unsigned int)v7;
LABEL_50:
    DebugTraceError(v16, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v15);
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v9 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v9 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        v8,
        (unsigned int)"sResult",
        v7,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        104);
  }
LABEL_51:
  if ( a2 )
  {
LABEL_52:
    v23 = *(void **)(a2 + 8);
    if ( v23 )
    {
      MSCryptFree(v23);
      *(_QWORD *)(a2 + 8) = 0;
    }
    *(_DWORD *)a2 = 0;
  }
  if ( a3 )
  {
    v24 = *(void **)(a3 + 8);
    if ( v24 )
    {
      MSCryptFree(v24);
      *(_QWORD *)(a3 + 8) = 0;
    }
    *(_DWORD *)a3 = 0;
  }
LABEL_61:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v3 && v3 != (_WORD *)KeyInformation )
    MSCryptFree(v3);
  if ( Handle )
    ZwClose(Handle);
  if ( v4 && v4 != (unsigned int *)KeyValueInformation )
    MSCryptFree(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003b34c  mov     [rsp-8+arg_18], rbx
0x18003b351  push    rbp
0x18003b352  push    rsi
0x18003b353  push    rdi
0x18003b354  push    r12
0x18003b356  push    r13
0x18003b358  push    r14
0x18003b35a  push    r15
0x18003b35c  lea     rbp, [rsp-420h]
0x18003b364  sub     rsp, 520h
0x18003b36b  mov     rax, cs:__security_cookie
0x18003b372  xor     rax, rsp
0x18003b375  mov     [rbp+450h+var_40], rax
0x18003b37c  xor     r12d, r12d
0x18003b37f  mov     [rbp+450h+var_478], rcx
0x18003b383  lea     rax, aRegistryMachin_15; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003b38a  mov     dword ptr [rbp+450h+ObjectAttributes+4], r12d
0x18003b38e  mov     [rsp+550h+Src], rax
0x18003b393  lea     rdi, [rbp+450h+KeyInformation]
0x18003b39a  lea     rax, aImagepath; "ImagePath"
0x18003b3a1  mov     dword ptr [rbp+450h+ObjectAttributes+1Ch], r12d
0x18003b3a5  mov     [rbp+450h+ValueName.Buffer], rax
0x18003b3a9  lea     rsi, [rbp+450h+KeyValueInformation]
0x18003b3ad  xor     eax, eax
0x18003b3af  mov     [rsp+550h+KeyHandle], r12
0x18003b3b4  mov     [rbp+450h+var_4C4], eax
0x18003b3b7  mov     r14, r8
0x18003b3ba  mov     [rbp-78h], r12
0x18003b3be  mov     r15, rdx
0x18003b3c1  mov     [rsp+550h+Handle], r12
0x18003b3c6  mov     [rsp+550h+var_4E8], 680066h
0x18003b3cf  mov     qword ptr [rbp+450h+ValueName.Length], 140012h
0x18003b3d7  mov     [rsp+550h+var_510], r12d
0x18003b3dc  mov     [rbp+450h+var_4C0], r12
0x18003b3e0  mov     [rsp+550h+var_4D8], r12
0x18003b3e5  mov     [rbp+450h+var_4D0], r12
0x18003b3e9  test    rdx, rdx
0x18003b3ec  jz      short loc_18003B3F2
0x18003b3ee  mov     [rdx+8], r12
0x18003b3f2  test    r14, r14
0x18003b3f5  jz      short loc_18003B3FB
0x18003b3f7  mov     [r8+8], r12
0x18003b3fb  lea     rax, [rsp+550h+var_4E8]
0x18003b400  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x18003b407  xorps   xmm0, xmm0
0x18003b40a  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18003b40e  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x18003b412  mov     [rbp+450h+ObjectAttributes.RootDirectory], r12
0x18003b416  mov     edx, 20019h; DesiredAccess
0x18003b41b  mov     [rbp+450h+ObjectAttributes.Attributes], 240h
0x18003b422  lea     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18003b427  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003b42c  call    cs:__imp_ZwOpenKey
0x18003b433  nop     dword ptr [rax+rax+00h]
0x18003b438  mov     ebx, eax
0x18003b43a  test    eax, eax
0x18003b43c  jns     short loc_18003B48E
0x18003b43e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b445  lea     rax, WPP_GLOBAL_Control
0x18003b44c  cmp     rcx, rax
0x18003b44f  jz      loc_18003B816
0x18003b455  mov     edx, [rcx+2Ch]
0x18003b458  test    dl, 1
0x18003b45b  jz      loc_18003B816
0x18003b461  mov     rcx, [rcx+18h]
0x18003b465  lea     r12, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b46c  mov     [rsp+550h+var_520], 268h
0x18003b474  lea     r9, aSresult; "sResult"
0x18003b47b  mov     [rsp+550h+ResultLength], r12
0x18003b480  mov     [rsp+550h+Length], ebx
0x18003b484  call    WPP_SF_sDsd
0x18003b489  jmp     loc_18003B813
0x18003b48e  mov     ecx, 218h
0x18003b493  mov     [rsp+550h+var_4F8], 210h
0x18003b49b  mov     eax, r12d
0x18003b49e  mov     [rsp+550h+var_508], ecx
0x18003b4a2  lea     r12, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b4a9  lea     r13, aSresult; "sResult"
0x18003b4b0  mov     [rsp+550h+var_50C], eax
0x18003b4b4  cmp     eax, 10000h
0x18003b4b9  jnb     loc_18003B6E3
0x18003b4bf  test    rdi, rdi
0x18003b4c2  jz      short loc_18003B543
0x18003b4c4  lea     rdx, [rsp+550h+var_510]
0x18003b4c9  mov     r9, rdi; KeyInformation
0x18003b4cc  mov     [rsp+550h+ResultLength], rdx; ResultLength
0x18003b4d1  xor     r8d, r8d; KeyInformationClass
0x18003b4d4  mov     [rsp+550h+Length], ecx; Length
0x18003b4d8  mov     edx, eax; Index
0x18003b4da  mov     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18003b4df  call    cs:__imp_ZwEnumerateKey
0x18003b4e6  nop     dword ptr [rax+rax+00h]
0x18003b4eb  mov     ebx, eax
0x18003b4ed  cmp     eax, 0C0000023h
0x18003b4f2  jz      short loc_18003B500
0x18003b4f4  cmp     eax, 80000005h
0x18003b4f9  jnz     short loc_18003B543
0x18003b4fb  test    rdi, rdi
0x18003b4fe  jz      short loc_18003B514
0x18003b500  lea     rax, [rbp+450h+KeyInformation]
0x18003b507  cmp     rdi, rax
0x18003b50a  jz      short loc_18003B514
0x18003b50c  mov     rcx, rdi; P
0x18003b50f  call    MSCryptFree
0x18003b514  mov     eax, [rsp+550h+var_510]
0x18003b518  add     eax, 0FFh
0x18003b51d  and     eax, 0FFFFFF00h
0x18003b522  mov     ecx, eax
0x18003b524  mov     [rsp+550h+var_508], eax
0x18003b528  call    MSCryptAlloc
0x18003b52d  mov     rdi, rax
0x18003b530  test    rax, rax
0x18003b533  jz      loc_18003B6B7
0x18003b539  mov     eax, [rsp+550h+var_50C]
0x18003b53d  mov     ecx, [rsp+550h+var_508]
0x18003b541  jmp     short loc_18003B4C4
0x18003b543  test    ebx, ebx
0x18003b545  js      loc_18003B6C2
0x18003b54b  movzx   eax, word ptr [rdi+0Ch]
0x18003b54f  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x18003b553  mov     word ptr [rsp+550h+var_4D8+2], ax
0x18003b558  lea     rcx, [rsp+550h+Handle]; KeyHandle
0x18003b55d  mov     word ptr [rsp+550h+var_4D8], ax
0x18003b562  xorps   xmm0, xmm0
0x18003b565  lea     rax, [rdi+10h]
0x18003b569  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x18003b570  mov     [rbp+450h+var_4D0], rax
0x18003b574  mov     edx, 20019h; DesiredAccess
0x18003b579  mov     rax, [rsp+550h+KeyHandle]
0x18003b57e  mov     [rbp+450h+ObjectAttributes.RootDirectory], rax
0x18003b582  lea     rax, [rsp+550h+var_4D8]
0x18003b587  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18003b58b  mov     [rbp+450h+ObjectAttributes.Attributes], 240h
0x18003b592  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003b597  call    cs:__imp_ZwOpenKey
0x18003b59e  nop     dword ptr [rax+rax+00h]
0x18003b5a3  xor     edx, edx
0x18003b5a5  mov     ebx, eax
0x18003b5a7  test    eax, eax
0x18003b5a9  js      loc_18003B6A8
0x18003b5af  test    rsi, rsi
0x18003b5b2  jz      loc_18003B64E
0x18003b5b8  mov     rcx, [rsp+550h+Handle]; KeyHandle
0x18003b5bd  lea     rax, [rsp+550h+var_510]
0x18003b5c2  mov     [rsp+550h+ResultLength], rax; ResultLength
0x18003b5c7  lea     rdx, [rbp+450h+ValueName]; ValueName
0x18003b5cb  mov     eax, [rsp+550h+var_4F8]
0x18003b5cf  mov     r9, rsi; KeyValueInformation
0x18003b5d2  mov     r8d, 2; KeyValueInformationClass
0x18003b5d8  mov     [rsp+550h+Length], eax; Length
0x18003b5dc  call    cs:__imp_ZwQueryValueKey
0x18003b5e3  nop     dword ptr [rax+rax+00h]
0x18003b5e8  mov     ebx, eax
0x18003b5ea  cmp     eax, 0C0000023h
0x18003b5ef  jz      short loc_18003B5FD
0x18003b5f1  cmp     eax, 80000005h
0x18003b5f6  jnz     short loc_18003B64C
0x18003b5f8  test    rsi, rsi
0x18003b5fb  jz      short loc_18003B60E
0x18003b5fd  lea     rax, [rbp+450h+KeyValueInformation]
0x18003b601  cmp     rsi, rax
0x18003b604  jz      short loc_18003B60E
0x18003b606  mov     rcx, rsi; P
0x18003b609  call    MSCryptFree
0x18003b60e  mov     eax, [rsp+550h+var_510]
0x18003b612  add     eax, 0FFh
0x18003b617  and     eax, 0FFFFFF00h
0x18003b61c  mov     ecx, eax
0x18003b61e  mov     [rsp+550h+var_4F8], eax
0x18003b622  call    MSCryptAlloc
0x18003b627  mov     rsi, rax
0x18003b62a  test    rax, rax
0x18003b62d  jnz     short loc_18003B5B8
0x18003b62f  mov     r9d, 2DDh
0x18003b635  mov     r8, r12
0x18003b638  mov     rdx, r13
0x18003b63b  mov     ecx, 0C000009Ah
0x18003b640  mov     ebx, 0C000009Ah
0x18003b645  call    DebugTraceError
0x18003b64a  jmp     short loc_18003B68E
0x18003b64c  xor     edx, edx
0x18003b64e  test    ebx, ebx
0x18003b650  js      short loc_18003B68E
0x18003b652  mov     ecx, [rsi+8]
0x18003b655  cmp     ecx, 2
0x18003b658  ja      short loc_18003B662
0x18003b65a  jmp     short loc_18003B68E
0x18003b65c  add     ecx, 0FFFFFFFEh
0x18003b65f  mov     [rsi+8], ecx
0x18003b662  cmp     [rcx+rsi+0Ah], dx
0x18003b667  jz      short loc_18003B65C
0x18003b669  movzx   eax, word ptr [rsi+8]
0x18003b66d  lea     rcx, [rbp+450h+var_4C8]
0x18003b671  mov     rdx, [rbp+450h+var_478]
0x18003b675  mov     [rbp+450h+var_4C6], ax
0x18003b679  mov     [rbp+450h+var_4C8], ax
0x18003b67d  lea     rax, [rsi+0Ch]
0x18003b681  mov     [rbp+450h+var_4C0], rax
0x18003b685  call    _IsImagePath
0x18003b68a  test    eax, eax
0x18003b68c  jnz     short loc_18003B702
0x18003b68e  mov     rcx, [rsp+550h+Handle]; Handle
0x18003b693  call    cs:__imp_ZwClose
0x18003b69a  nop     dword ptr [rax+rax+00h]
0x18003b69f  mov     [rsp+550h+Handle], 0
0x18003b6a8  mov     eax, [rsp+550h+var_50C]
0x18003b6ac  mov     ecx, [rsp+550h+var_508]
0x18003b6b0  inc     eax
0x18003b6b2  jmp     loc_18003B4B0
0x18003b6b7  mov     r9d, 290h
0x18003b6bd  jmp     loc_18003B7FE
0x18003b6c2  cmp     ebx, 8000001Ah
0x18003b6c8  jnz     loc_18003B813
0x18003b6ce  mov     ebx, 0C0000225h
0x18003b6d3  mov     r9d, 29Ch
0x18003b6d9  mov     ecx, 0C0000225h
0x18003b6de  jmp     loc_18003B808
0x18003b6e3  jnz     short loc_18003B702
0x18003b6e5  mov     r9d, 305h
0x18003b6eb  mov     r8, r12
0x18003b6ee  mov     rdx, r13
0x18003b6f1  mov     ecx, 0C0000225h
0x18003b6f6  mov     ebx, 0C0000225h
0x18003b6fb  call    DebugTraceError
0x18003b700  jmp     short loc_18003B706
0x18003b702  test    ebx, ebx
0x18003b704  jns     short loc_18003B713
0x18003b706  mov     r9d, 30Ah
0x18003b70c  mov     ecx, ebx
0x18003b70e  jmp     loc_18003B808
0x18003b713  mov     ecx, 0FFF8h
0x18003b718  test    r15, r15
0x18003b71b  jz      loc_18003B7BD
0x18003b721  movzx   eax, word ptr [rsp+550h+var_4D8]
0x18003b726  add     ax, 2
0x18003b72a  add     ax, word ptr [rsp+550h+var_4E8]
0x18003b72f  mov     [r15], ax
0x18003b733  add     ax, 7
0x18003b737  and     ax, cx
0x18003b73a  movzx   ecx, ax
0x18003b73d  mov     [r15+2], cx
0x18003b742  call    MSCryptAlloc
0x18003b747  mov     [r15+8], rax
0x18003b74b  test    rax, rax
0x18003b74e  jnz     short loc_18003B773
0x18003b750  mov     r9d, 318h
0x18003b756  mov     r8, r12
0x18003b759  mov     rdx, r13
0x18003b75c  mov     ecx, 0C000009Ah
0x18003b761  mov     ebx, 0C000009Ah
0x18003b766  call    DebugTraceError
0x18003b76b  xor     r12d, r12d
0x18003b76e  jmp     loc_18003B81B
0x18003b773  movzx   r8d, word ptr [rsp+550h+var_4E8]; Size
0x18003b779  mov     rcx, rax; void *
0x18003b77c  mov     rdx, [rsp+550h+Src]; Src
0x18003b781  call    memmove
0x18003b786  movzx   ecx, word ptr [rsp+550h+var_4E8]
0x18003b78b  lea     rdx, [rdi+10h]; Src
0x18003b78f  mov     rax, [r15+8]
0x18003b793  shr     rcx, 1
0x18003b796  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18003b79c  movzx   ecx, word ptr [rsp+550h+var_4E8]
0x18003b7a1  mov     rax, [r15+8]
0x18003b7a5  mov     r8d, [rdi+0Ch]; Size
0x18003b7a9  shr     rcx, 1
0x18003b7ac  inc     rcx
0x18003b7af  lea     rcx, [rax+rcx*2]; void *
0x18003b7b3  call    memmove
0x18003b7b8  mov     ecx, 0FFF8h
0x18003b7bd  test    r14, r14
0x18003b7c0  jz      loc_18003B894
0x18003b7c6  movzx   eax, word ptr [rsp+550h+var_4D8]
0x18003b7cb  mov     edx, 0Eh
0x18003b7d0  add     dx, 2
0x18003b7d4  add     ax, dx
0x18003b7d7  mov     [r14], ax
0x18003b7db  add     ax, 7
0x18003b7df  and     ax, cx
0x18003b7e2  movzx   ecx, ax
0x18003b7e5  mov     [r14+2], cx
0x18003b7ea  call    MSCryptAlloc
0x18003b7ef  mov     [r14+8], rax
0x18003b7f3  test    rax, rax
0x18003b7f6  jnz     short loc_18003B854
0x18003b7f8  mov     r9d, 330h
0x18003b7fe  mov     ebx, 0C000009Ah
0x18003b803  mov     ecx, 0C000009Ah
0x18003b808  mov     r8, r12
0x18003b80b  mov     rdx, r13
0x18003b80e  call    DebugTraceError
0x18003b813  xor     r12d, r12d
0x18003b816  test    r15, r15
0x18003b819  jz      short loc_18003B834
0x18003b81b  mov     rcx, [r15+8]; P
0x18003b81f  test    rcx, rcx
0x18003b822  jz      short loc_18003B82D
0x18003b824  call    MSCryptFree
0x18003b829  mov     [r15+8], r12
0x18003b82d  mov     dword ptr [r15], 0
  ... truncated ...
```
