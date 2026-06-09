# _ResolveDriverNamesFromImage

- ea: `0x18003be4c`
- end: `0x18003c422`
- name: `_ResolveDriverNamesFromImage`
- size: `1494`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003bc74`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18003be4c`
- `0x180049628`
- `0x18009f650`
- `0x18009f780`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18003c0dc`
- `ntoskrnl!ZwQueryValueKey` at `0x18003c0dc`
- `ntoskrnl!ZwClose` at `0x18003c193`
- `ntoskrnl!ZwClose` at `0x18003c3a4`
- `ntoskrnl!ZwClose` at `0x18003c3d3`
- `ntoskrnl!ZwClose` at `0x18003c193`
- `ntoskrnl!ZwClose` at `0x18003c3a4`
- `ntoskrnl!ZwClose` at `0x18003c3d3`
- `ntoskrnl!ZwOpenKey` at `0x18003bf2c`
- `ntoskrnl!ZwOpenKey` at `0x18003c097`
- `ntoskrnl!ZwOpenKey` at `0x18003bf2c`
- `ntoskrnl!ZwOpenKey` at `0x18003c097`
- `ntoskrnl!ZwEnumerateKey` at `0x18003bfdf`
- `ntoskrnl!ZwEnumerateKey` at `0x18003bfdf`

## string_xrefs

- `0x18003bf65`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003bfa2`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003be9a`: `ImagePath`
- `0x18003be83`: `\Registry\Machine\System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall ResolveDriverNamesFromImage(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v3; // rdi
  unsigned int *v4; // rsi
  __int64 v7; // rdx
  NTSTATUS v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edx
  ULONG Length; // ecx
  ULONG v13; // eax
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rcx
  __int16 v26; // ax
  unsigned __int16 v27; // ax
  void *v28; // rax
  __int16 v29; // ax
  unsigned __int16 v30; // ax
  void *v31; // rax
  void *v32; // rcx
  void *v33; // rcx
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v36; // [rsp+44h] [rbp-BCh]
  ULONG v37; // [rsp+48h] [rbp-B8h]
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v39; // [rsp+58h] [rbp-A8h]
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v46; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING ValueName; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h]
  _BYTE KeyValueInformation[528]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE KeyInformation[544]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v49 = a1;
  *(&ObjectAttributes.Length + 1) = 0;
  Src = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services";
  v3 = KeyInformation;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ValueName.Buffer = L"ImagePath";
  v4 = (unsigned int *)KeyValueInformation;
  KeyHandle = 0;
  v45 = 0;
  Handle = 0;
  v41 = 6815846;
  *(_QWORD *)&ValueName.Length = 1310738;
  ResultLength = 0;
  v46 = 0;
  v43 = 0;
  v44 = 0;
  if ( a2 )
    *(_QWORD *)(a2 + 8) = 0;
  if ( a3 )
    *(_QWORD *)(a3 + 8) = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v41;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    Length = 536;
    v39 = 528;
    v13 = 0;
    v37 = 536;
    while ( 1 )
    {
      v36 = v13;
      if ( v13 >= 0x10000 )
        break;
      if ( v3 )
      {
        while ( 1 )
        {
          v14 = ZwEnumerateKey(KeyHandle, v13, KeyBasicInformation, v3, Length, &ResultLength);
          v8 = v14;
          if ( v14 != -1073741789 && v14 != -2147483643 )
            break;
          if ( v3 != (_WORD *)KeyInformation )
            MSCryptFree(v3);
          v37 = (ResultLength + 255) & 0xFFFFFF00;
          v3 = (_WORD *)MSCryptAlloc(v37, v15, v16, v17);
          if ( !v3 )
          {
            v24 = 656;
            goto LABEL_49;
          }
          v13 = v36;
          Length = v37;
        }
      }
      if ( v8 < 0 )
      {
        if ( v8 != -2147483622 )
          goto LABEL_51;
        v8 = -1073741275;
        v24 = 668;
        v25 = 3221226021LL;
        goto LABEL_50;
      }
      WORD1(v43) = v3[6];
      LOWORD(v43) = WORD1(v43);
      ObjectAttributes.Length = 48;
      v44 = v3 + 8;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v43;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v18 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      v7 = 0;
      v8 = v18;
      if ( v18 >= 0 )
      {
        if ( v4 )
        {
          while ( 1 )
          {
            v19 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, v4, v39, &ResultLength);
            v8 = v19;
            if ( v19 != -1073741789 && v19 != -2147483643 )
              break;
            if ( v4 != (unsigned int *)KeyValueInformation )
              MSCryptFree(v4);
            v39 = (ResultLength + 255) & 0xFFFFFF00;
            v4 = (unsigned int *)MSCryptAlloc(v39, v20, v21, v22);
            if ( !v4 )
            {
              v8 = -1073741670;
              DebugTraceError(
                3221225626LL,
                "sResult",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                733);
              goto LABEL_33;
            }
          }
        }
        if ( v8 >= 0 )
        {
          v23 = v4[2];
          if ( (unsigned int)v23 > 2 )
          {
            while ( !*(_WORD *)((char *)v4 + v23 + 10) )
            {
              v23 = (unsigned int)(v23 - 2);
              v4[2] = v23;
            }
            WORD1(v45) = *((_WORD *)v4 + 4);
            LOWORD(v45) = WORD1(v45);
            v46 = v4 + 3;
            if ( (unsigned int)IsImagePath(&v45, v49) )
              goto LABEL_40;
          }
        }
LABEL_33:
        ZwClose(Handle);
        Handle = 0;
      }
      Length = v37;
      v13 = v36 + 1;
    }
    if ( v13 == 0x10000 )
    {
      v8 = -1073741275;
      DebugTraceError(3221226021LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 773);
    }
    else
    {
LABEL_40:
      if ( v8 >= 0 )
      {
        if ( a2 )
        {
          v26 = v41 + v43 + 2;
          *(_WORD *)a2 = v26;
          v27 = (v26 + 7) & 0xFFF8;
          *(_WORD *)(a2 + 2) = v27;
          v28 = (void *)MSCryptAlloc(v27, v7, v9, v10);
          *(_QWORD *)(a2 + 8) = v28;
          if ( !v28 )
          {
            v8 = -1073741670;
            DebugTraceError(3221225626LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 792);
            goto LABEL_52;
          }
          memmove(v28, Src, (unsigned __int16)v41);
          *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * ((unsigned __int64)(unsigned __int16)v41 >> 1)) = 92;
          memmove(
            (void *)(*(_QWORD *)(a2 + 8) + 2 * (((unsigned __int64)(unsigned __int16)v41 >> 1) + 1)),
            v3 + 8,
            *((unsigned int *)v3 + 3));
        }
        if ( a3 )
        {
          v29 = v43 + 16;
          *(_WORD *)a3 = v43 + 16;
          v30 = (v29 + 7) & 0xFFF8;
          *(_WORD *)(a3 + 2) = v30;
          v31 = (void *)MSCryptAlloc(v30, 16, v9, v10);
          *(_QWORD *)(a3 + 8) = v31;
          if ( !v31 )
          {
            v24 = 816;
LABEL_49:
            v8 = -1073741670;
            v25 = 3221225626LL;
            goto LABEL_50;
          }
          memmove(v31, L"\\Device", 0xEu);
          *(_WORD *)(*(_QWORD *)(a3 + 8) + 14LL) = 92;
          memmove((void *)(*(_QWORD *)(a3 + 8) + 16LL), v3 + 8, *((unsigned int *)v3 + 3));
        }
        v8 = 0;
        goto LABEL_61;
      }
    }
    v24 = 778;
    v25 = (unsigned int)v8;
LABEL_50:
    DebugTraceError(v25, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v24);
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v11 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v11 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v11,
        v9,
        (unsigned int)"sResult",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        104);
  }
LABEL_51:
  if ( a2 )
  {
LABEL_52:
    v32 = *(void **)(a2 + 8);
    if ( v32 )
    {
      MSCryptFree(v32);
      *(_QWORD *)(a2 + 8) = 0;
    }
    *(_DWORD *)a2 = 0;
  }
  if ( a3 )
  {
    v33 = *(void **)(a3 + 8);
    if ( v33 )
    {
      MSCryptFree(v33);
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
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003be4c  mov     [rsp-8+arg_18], rbx
0x18003be51  push    rbp
0x18003be52  push    rsi
0x18003be53  push    rdi
0x18003be54  push    r12
0x18003be56  push    r13
0x18003be58  push    r14
0x18003be5a  push    r15
0x18003be5c  lea     rbp, [rsp-420h]
0x18003be64  sub     rsp, 520h
0x18003be6b  mov     rax, cs:__security_cookie
0x18003be72  xor     rax, rsp
0x18003be75  mov     [rbp+450h+var_40], rax
0x18003be7c  xor     r12d, r12d
0x18003be7f  mov     [rbp+450h+var_478], rcx
0x18003be83  lea     rax, aRegistryMachin_15; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003be8a  mov     dword ptr [rbp+450h+ObjectAttributes+4], r12d
0x18003be8e  mov     [rsp+550h+Src], rax
0x18003be93  lea     rdi, [rbp+450h+KeyInformation]
0x18003be9a  lea     rax, aImagepath; "ImagePath"
0x18003bea1  mov     dword ptr [rbp+450h+ObjectAttributes+1Ch], r12d
0x18003bea5  mov     [rbp+450h+ValueName.Buffer], rax
0x18003bea9  lea     rsi, [rbp+450h+KeyValueInformation]
0x18003bead  xor     eax, eax
0x18003beaf  mov     [rsp+550h+KeyHandle], r12
0x18003beb4  mov     [rbp+450h+var_4C4], eax
0x18003beb7  mov     r14, r8
0x18003beba  mov     [rbp-78h], r12
0x18003bebe  mov     r15, rdx
0x18003bec1  mov     [rsp+550h+Handle], r12
0x18003bec6  mov     [rsp+550h+var_4E8], 680066h
0x18003becf  mov     qword ptr [rbp+450h+ValueName.Length], 140012h
0x18003bed7  mov     [rsp+550h+var_510], r12d
0x18003bedc  mov     [rbp+450h+var_4C0], r12
0x18003bee0  mov     [rsp+550h+var_4D8], r12
0x18003bee5  mov     [rbp+450h+var_4D0], r12
0x18003bee9  test    rdx, rdx
0x18003beec  jz      short loc_18003BEF2
0x18003beee  mov     [rdx+8], r12
0x18003bef2  test    r14, r14
0x18003bef5  jz      short loc_18003BEFB
0x18003bef7  mov     [r8+8], r12
0x18003befb  lea     rax, [rsp+550h+var_4E8]
0x18003bf00  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x18003bf07  xorps   xmm0, xmm0
0x18003bf0a  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18003bf0e  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x18003bf12  mov     [rbp+450h+ObjectAttributes.RootDirectory], r12
0x18003bf16  mov     edx, 20019h; DesiredAccess
0x18003bf1b  mov     [rbp+450h+ObjectAttributes.Attributes], 240h
0x18003bf22  lea     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18003bf27  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003bf2c  call    cs:__imp_ZwOpenKey
0x18003bf33  nop     dword ptr [rax+rax+00h]
0x18003bf38  mov     ebx, eax
0x18003bf3a  test    eax, eax
0x18003bf3c  jns     short loc_18003BF8E
0x18003bf3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf45  lea     rax, WPP_GLOBAL_Control
0x18003bf4c  cmp     rcx, rax
0x18003bf4f  jz      loc_18003C316
0x18003bf55  mov     edx, [rcx+2Ch]
0x18003bf58  test    dl, 1
0x18003bf5b  jz      loc_18003C316
0x18003bf61  mov     rcx, [rcx+18h]
0x18003bf65  lea     r12, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003bf6c  mov     [rsp+550h+var_520], 268h
0x18003bf74  lea     r9, aSresult; "sResult"
0x18003bf7b  mov     [rsp+550h+ResultLength], r12
0x18003bf80  mov     [rsp+550h+Length], ebx
0x18003bf84  call    WPP_SF_sDsd
0x18003bf89  jmp     loc_18003C313
0x18003bf8e  mov     ecx, 218h
0x18003bf93  mov     [rsp+550h+var_4F8], 210h
0x18003bf9b  mov     eax, r12d
0x18003bf9e  mov     [rsp+550h+var_508], ecx
0x18003bfa2  lea     r12, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003bfa9  lea     r13, aSresult; "sResult"
0x18003bfb0  mov     [rsp+550h+var_50C], eax
0x18003bfb4  cmp     eax, 10000h
0x18003bfb9  jnb     loc_18003C1E3
0x18003bfbf  test    rdi, rdi
0x18003bfc2  jz      short loc_18003C043
0x18003bfc4  lea     rdx, [rsp+550h+var_510]
0x18003bfc9  mov     r9, rdi; KeyInformation
0x18003bfcc  mov     [rsp+550h+ResultLength], rdx; ResultLength
0x18003bfd1  xor     r8d, r8d; KeyInformationClass
0x18003bfd4  mov     [rsp+550h+Length], ecx; Length
0x18003bfd8  mov     edx, eax; Index
0x18003bfda  mov     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18003bfdf  call    cs:__imp_ZwEnumerateKey
0x18003bfe6  nop     dword ptr [rax+rax+00h]
0x18003bfeb  mov     ebx, eax
0x18003bfed  cmp     eax, 0C0000023h
0x18003bff2  jz      short loc_18003C000
0x18003bff4  cmp     eax, 80000005h
0x18003bff9  jnz     short loc_18003C043
0x18003bffb  test    rdi, rdi
0x18003bffe  jz      short loc_18003C014
0x18003c000  lea     rax, [rbp+450h+KeyInformation]
0x18003c007  cmp     rdi, rax
0x18003c00a  jz      short loc_18003C014
0x18003c00c  mov     rcx, rdi; P
0x18003c00f  call    MSCryptFree
0x18003c014  mov     eax, [rsp+550h+var_510]
0x18003c018  add     eax, 0FFh
0x18003c01d  and     eax, 0FFFFFF00h
0x18003c022  mov     ecx, eax
0x18003c024  mov     [rsp+550h+var_508], eax
0x18003c028  call    MSCryptAlloc
0x18003c02d  mov     rdi, rax
0x18003c030  test    rax, rax
0x18003c033  jz      loc_18003C1B7
0x18003c039  mov     eax, [rsp+550h+var_50C]
0x18003c03d  mov     ecx, [rsp+550h+var_508]
0x18003c041  jmp     short loc_18003BFC4
0x18003c043  test    ebx, ebx
0x18003c045  js      loc_18003C1C2
0x18003c04b  movzx   eax, word ptr [rdi+0Ch]
0x18003c04f  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x18003c053  mov     word ptr [rsp+550h+var_4D8+2], ax
0x18003c058  lea     rcx, [rsp+550h+Handle]; KeyHandle
0x18003c05d  mov     word ptr [rsp+550h+var_4D8], ax
0x18003c062  xorps   xmm0, xmm0
0x18003c065  lea     rax, [rdi+10h]
0x18003c069  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x18003c070  mov     [rbp+450h+var_4D0], rax
0x18003c074  mov     edx, 20019h; DesiredAccess
0x18003c079  mov     rax, [rsp+550h+KeyHandle]
0x18003c07e  mov     [rbp+450h+ObjectAttributes.RootDirectory], rax
0x18003c082  lea     rax, [rsp+550h+var_4D8]
0x18003c087  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18003c08b  mov     [rbp+450h+ObjectAttributes.Attributes], 240h
0x18003c092  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c097  call    cs:__imp_ZwOpenKey
0x18003c09e  nop     dword ptr [rax+rax+00h]
0x18003c0a3  xor     edx, edx
0x18003c0a5  mov     ebx, eax
0x18003c0a7  test    eax, eax
0x18003c0a9  js      loc_18003C1A8
0x18003c0af  test    rsi, rsi
0x18003c0b2  jz      loc_18003C14E
0x18003c0b8  mov     rcx, [rsp+550h+Handle]; KeyHandle
0x18003c0bd  lea     rax, [rsp+550h+var_510]
0x18003c0c2  mov     [rsp+550h+ResultLength], rax; ResultLength
0x18003c0c7  lea     rdx, [rbp+450h+ValueName]; ValueName
0x18003c0cb  mov     eax, [rsp+550h+var_4F8]
0x18003c0cf  mov     r9, rsi; KeyValueInformation
0x18003c0d2  mov     r8d, 2; KeyValueInformationClass
0x18003c0d8  mov     [rsp+550h+Length], eax; Length
0x18003c0dc  call    cs:__imp_ZwQueryValueKey
0x18003c0e3  nop     dword ptr [rax+rax+00h]
0x18003c0e8  mov     ebx, eax
0x18003c0ea  cmp     eax, 0C0000023h
0x18003c0ef  jz      short loc_18003C0FD
0x18003c0f1  cmp     eax, 80000005h
0x18003c0f6  jnz     short loc_18003C14C
0x18003c0f8  test    rsi, rsi
0x18003c0fb  jz      short loc_18003C10E
0x18003c0fd  lea     rax, [rbp+450h+KeyValueInformation]
0x18003c101  cmp     rsi, rax
0x18003c104  jz      short loc_18003C10E
0x18003c106  mov     rcx, rsi; P
0x18003c109  call    MSCryptFree
0x18003c10e  mov     eax, [rsp+550h+var_510]
0x18003c112  add     eax, 0FFh
0x18003c117  and     eax, 0FFFFFF00h
0x18003c11c  mov     ecx, eax
0x18003c11e  mov     [rsp+550h+var_4F8], eax
0x18003c122  call    MSCryptAlloc
0x18003c127  mov     rsi, rax
0x18003c12a  test    rax, rax
0x18003c12d  jnz     short loc_18003C0B8
0x18003c12f  mov     r9d, 2DDh
0x18003c135  mov     r8, r12
0x18003c138  mov     rdx, r13
0x18003c13b  mov     ecx, 0C000009Ah
0x18003c140  mov     ebx, 0C000009Ah
0x18003c145  call    DebugTraceError
0x18003c14a  jmp     short loc_18003C18E
0x18003c14c  xor     edx, edx
0x18003c14e  test    ebx, ebx
0x18003c150  js      short loc_18003C18E
0x18003c152  mov     ecx, [rsi+8]
0x18003c155  cmp     ecx, 2
0x18003c158  ja      short loc_18003C162
0x18003c15a  jmp     short loc_18003C18E
0x18003c15c  add     ecx, 0FFFFFFFEh
0x18003c15f  mov     [rsi+8], ecx
0x18003c162  cmp     [rcx+rsi+0Ah], dx
0x18003c167  jz      short loc_18003C15C
0x18003c169  movzx   eax, word ptr [rsi+8]
0x18003c16d  lea     rcx, [rbp+450h+var_4C8]
0x18003c171  mov     rdx, [rbp+450h+var_478]
0x18003c175  mov     [rbp+450h+var_4C6], ax
0x18003c179  mov     [rbp+450h+var_4C8], ax
0x18003c17d  lea     rax, [rsi+0Ch]
0x18003c181  mov     [rbp+450h+var_4C0], rax
0x18003c185  call    _IsImagePath
0x18003c18a  test    eax, eax
0x18003c18c  jnz     short loc_18003C202
0x18003c18e  mov     rcx, [rsp+550h+Handle]; Handle
0x18003c193  call    cs:__imp_ZwClose
0x18003c19a  nop     dword ptr [rax+rax+00h]
0x18003c19f  mov     [rsp+550h+Handle], 0
0x18003c1a8  mov     eax, [rsp+550h+var_50C]
0x18003c1ac  mov     ecx, [rsp+550h+var_508]
0x18003c1b0  inc     eax
0x18003c1b2  jmp     loc_18003BFB0
0x18003c1b7  mov     r9d, 290h
0x18003c1bd  jmp     loc_18003C2FE
0x18003c1c2  cmp     ebx, 8000001Ah
0x18003c1c8  jnz     loc_18003C313
0x18003c1ce  mov     ebx, 0C0000225h
0x18003c1d3  mov     r9d, 29Ch
0x18003c1d9  mov     ecx, 0C0000225h
0x18003c1de  jmp     loc_18003C308
0x18003c1e3  jnz     short loc_18003C202
0x18003c1e5  mov     r9d, 305h
0x18003c1eb  mov     r8, r12
0x18003c1ee  mov     rdx, r13
0x18003c1f1  mov     ecx, 0C0000225h
0x18003c1f6  mov     ebx, 0C0000225h
0x18003c1fb  call    DebugTraceError
0x18003c200  jmp     short loc_18003C206
0x18003c202  test    ebx, ebx
0x18003c204  jns     short loc_18003C213
0x18003c206  mov     r9d, 30Ah
0x18003c20c  mov     ecx, ebx
0x18003c20e  jmp     loc_18003C308
0x18003c213  mov     ecx, 0FFF8h
0x18003c218  test    r15, r15
0x18003c21b  jz      loc_18003C2BD
0x18003c221  movzx   eax, word ptr [rsp+550h+var_4D8]
0x18003c226  add     ax, 2
0x18003c22a  add     ax, word ptr [rsp+550h+var_4E8]
0x18003c22f  mov     [r15], ax
0x18003c233  add     ax, 7
0x18003c237  and     ax, cx
0x18003c23a  movzx   ecx, ax
0x18003c23d  mov     [r15+2], cx
0x18003c242  call    MSCryptAlloc
0x18003c247  mov     [r15+8], rax
0x18003c24b  test    rax, rax
0x18003c24e  jnz     short loc_18003C273
0x18003c250  mov     r9d, 318h
0x18003c256  mov     r8, r12
0x18003c259  mov     rdx, r13
0x18003c25c  mov     ecx, 0C000009Ah
0x18003c261  mov     ebx, 0C000009Ah
0x18003c266  call    DebugTraceError
0x18003c26b  xor     r12d, r12d
0x18003c26e  jmp     loc_18003C31B
0x18003c273  movzx   r8d, word ptr [rsp+550h+var_4E8]; Size
0x18003c279  mov     rcx, rax; void *
0x18003c27c  mov     rdx, [rsp+550h+Src]; Src
0x18003c281  call    memmove
0x18003c286  movzx   ecx, word ptr [rsp+550h+var_4E8]
0x18003c28b  lea     rdx, [rdi+10h]; Src
0x18003c28f  mov     rax, [r15+8]
0x18003c293  shr     rcx, 1
0x18003c296  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18003c29c  movzx   ecx, word ptr [rsp+550h+var_4E8]
0x18003c2a1  mov     rax, [r15+8]
0x18003c2a5  mov     r8d, [rdi+0Ch]; Size
0x18003c2a9  shr     rcx, 1
0x18003c2ac  inc     rcx
0x18003c2af  lea     rcx, [rax+rcx*2]; void *
0x18003c2b3  call    memmove
0x18003c2b8  mov     ecx, 0FFF8h
0x18003c2bd  test    r14, r14
0x18003c2c0  jz      loc_18003C394
0x18003c2c6  movzx   eax, word ptr [rsp+550h+var_4D8]
0x18003c2cb  mov     edx, 0Eh
0x18003c2d0  add     dx, 2
0x18003c2d4  add     ax, dx
0x18003c2d7  mov     [r14], ax
0x18003c2db  add     ax, 7
0x18003c2df  and     ax, cx
0x18003c2e2  movzx   ecx, ax
0x18003c2e5  mov     [r14+2], cx
0x18003c2ea  call    MSCryptAlloc
0x18003c2ef  mov     [r14+8], rax
0x18003c2f3  test    rax, rax
0x18003c2f6  jnz     short loc_18003C354
0x18003c2f8  mov     r9d, 330h
0x18003c2fe  mov     ebx, 0C000009Ah
0x18003c303  mov     ecx, 0C000009Ah
0x18003c308  mov     r8, r12
0x18003c30b  mov     rdx, r13
0x18003c30e  call    DebugTraceError
0x18003c313  xor     r12d, r12d
0x18003c316  test    r15, r15
0x18003c319  jz      short loc_18003C334
0x18003c31b  mov     rcx, [r15+8]; P
0x18003c31f  test    rcx, rcx
0x18003c322  jz      short loc_18003C32D
0x18003c324  call    MSCryptFree
0x18003c329  mov     [r15+8], r12
0x18003c32d  mov     dword ptr [r15], 0
  ... truncated ...
```
