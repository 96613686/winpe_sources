# _ResolveDriverNamesFromImage

- ea: `0x1800453dc`
- end: `0x1800459b2`
- name: `_ResolveDriverNamesFromImage`
- size: `1494`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180045204`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x1800453dc`
- `0x180052c88`
- `0x1800a4260`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18004566c`
- `ntoskrnl!ZwQueryValueKey` at `0x18004566c`
- `ntoskrnl!ZwClose` at `0x180045723`
- `ntoskrnl!ZwClose` at `0x180045934`
- `ntoskrnl!ZwClose` at `0x180045963`
- `ntoskrnl!ZwClose` at `0x180045723`
- `ntoskrnl!ZwClose` at `0x180045934`
- `ntoskrnl!ZwClose` at `0x180045963`
- `ntoskrnl!ZwOpenKey` at `0x1800454bc`
- `ntoskrnl!ZwOpenKey` at `0x180045627`
- `ntoskrnl!ZwOpenKey` at `0x1800454bc`
- `ntoskrnl!ZwOpenKey` at `0x180045627`
- `ntoskrnl!ZwEnumerateKey` at `0x18004556f`
- `ntoskrnl!ZwEnumerateKey` at `0x18004556f`

## string_xrefs

- `0x1800454f5`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180045532`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18004542a`: `ImagePath`
- `0x180045413`: `\Registry\Machine\System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall ResolveDriverNamesFromImage(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v3; // rdi
  unsigned int *v4; // rsi
  __int64 v7; // rdx
  NTSTATUS v8; // ebx
  int v9; // r8d
  int v10; // edx
  ULONG Length; // ecx
  ULONG v12; // eax
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rcx
  __int16 v21; // ax
  unsigned __int16 v22; // ax
  void *v23; // rax
  __int16 v24; // ax
  unsigned __int16 v25; // ax
  void *v26; // rax
  void *v27; // rcx
  void *v28; // rcx
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v31; // [rsp+44h] [rbp-BCh]
  ULONG v32; // [rsp+48h] [rbp-B8h]
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v34; // [rsp+58h] [rbp-A8h]
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v41; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING ValueName; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  _BYTE KeyValueInformation[528]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE KeyInformation[544]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v44 = a1;
  *(&ObjectAttributes.Length + 1) = 0;
  Src = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services";
  v3 = KeyInformation;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ValueName.Buffer = L"ImagePath";
  v4 = (unsigned int *)KeyValueInformation;
  KeyHandle = 0;
  v40 = 0;
  Handle = 0;
  v36 = 6815846;
  *(_QWORD *)&ValueName.Length = 1310738;
  ResultLength = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  if ( a2 )
    *(_QWORD *)(a2 + 8) = 0;
  if ( a3 )
    *(_QWORD *)(a3 + 8) = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v36;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    Length = 536;
    v34 = 528;
    v12 = 0;
    v32 = 536;
    while ( 1 )
    {
      v31 = v12;
      if ( v12 >= 0x10000 )
        break;
      if ( v3 )
      {
        while ( 1 )
        {
          v13 = ZwEnumerateKey(KeyHandle, v12, KeyBasicInformation, v3, Length, &ResultLength);
          v8 = v13;
          if ( v13 != -1073741789 && v13 != -2147483643 )
            break;
          if ( v3 != (_WORD *)KeyInformation )
            MSCryptFree(v3);
          v32 = (ResultLength + 255) & 0xFFFFFF00;
          v3 = (_WORD *)MSCryptAlloc(v32, v14);
          if ( !v3 )
          {
            v19 = 656;
            goto LABEL_49;
          }
          v12 = v31;
          Length = v32;
        }
      }
      if ( v8 < 0 )
      {
        if ( v8 != -2147483622 )
          goto LABEL_51;
        v8 = -1073741275;
        v19 = 668;
        v20 = 3221226021LL;
        goto LABEL_50;
      }
      WORD1(v38) = v3[6];
      LOWORD(v38) = WORD1(v38);
      ObjectAttributes.Length = 48;
      v39 = v3 + 8;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v38;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      v7 = 0;
      v8 = v15;
      if ( v15 >= 0 )
      {
        if ( v4 )
        {
          while ( 1 )
          {
            v16 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, v4, v34, &ResultLength);
            v8 = v16;
            if ( v16 != -1073741789 && v16 != -2147483643 )
              break;
            if ( v4 != (unsigned int *)KeyValueInformation )
              MSCryptFree(v4);
            v34 = (ResultLength + 255) & 0xFFFFFF00;
            v4 = (unsigned int *)MSCryptAlloc(v34, v17);
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
          v18 = v4[2];
          if ( (unsigned int)v18 > 2 )
          {
            while ( !*(_WORD *)((char *)v4 + v18 + 10) )
            {
              v18 = (unsigned int)(v18 - 2);
              v4[2] = v18;
            }
            WORD1(v40) = *((_WORD *)v4 + 4);
            LOWORD(v40) = WORD1(v40);
            v41 = v4 + 3;
            if ( (unsigned int)IsImagePath(&v40, v44) )
              goto LABEL_40;
          }
        }
LABEL_33:
        ZwClose(Handle);
        Handle = 0;
      }
      Length = v32;
      v12 = v31 + 1;
    }
    if ( v12 == 0x10000 )
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
          v21 = v36 + v38 + 2;
          *(_WORD *)a2 = v21;
          v22 = (v21 + 7) & 0xFFF8;
          *(_WORD *)(a2 + 2) = v22;
          v23 = (void *)MSCryptAlloc(v22, v7);
          *(_QWORD *)(a2 + 8) = v23;
          if ( !v23 )
          {
            v8 = -1073741670;
            DebugTraceError(3221225626LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 792);
            goto LABEL_52;
          }
          memmove(v23, Src, (unsigned __int16)v36);
          *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * ((unsigned __int64)(unsigned __int16)v36 >> 1)) = 92;
          memmove(
            (void *)(*(_QWORD *)(a2 + 8) + 2 * (((unsigned __int64)(unsigned __int16)v36 >> 1) + 1)),
            v3 + 8,
            *((unsigned int *)v3 + 3));
        }
        if ( a3 )
        {
          v24 = v38 + 16;
          *(_WORD *)a3 = v38 + 16;
          v25 = (v24 + 7) & 0xFFF8;
          *(_WORD *)(a3 + 2) = v25;
          v26 = (void *)MSCryptAlloc(v25, 16);
          *(_QWORD *)(a3 + 8) = v26;
          if ( !v26 )
          {
            v19 = 816;
LABEL_49:
            v8 = -1073741670;
            v20 = 3221225626LL;
            goto LABEL_50;
          }
          memmove(v26, L"\\Device", 0xEu);
          *(_WORD *)(*(_QWORD *)(a3 + 8) + 14LL) = 92;
          memmove((void *)(*(_QWORD *)(a3 + 8) + 16LL), v3 + 8, *((unsigned int *)v3 + 3));
        }
        v8 = 0;
        goto LABEL_61;
      }
    }
    v19 = 778;
    v20 = (unsigned int)v8;
LABEL_50:
    DebugTraceError(v20, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v19);
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v10 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v10 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v10,
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
    v27 = *(void **)(a2 + 8);
    if ( v27 )
    {
      MSCryptFree(v27);
      *(_QWORD *)(a2 + 8) = 0;
    }
    *(_DWORD *)a2 = 0;
  }
  if ( a3 )
  {
    v28 = *(void **)(a3 + 8);
    if ( v28 )
    {
      MSCryptFree(v28);
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
0x1800453dc  mov     [rsp-8+arg_18], rbx
0x1800453e1  push    rbp
0x1800453e2  push    rsi
0x1800453e3  push    rdi
0x1800453e4  push    r12
0x1800453e6  push    r13
0x1800453e8  push    r14
0x1800453ea  push    r15
0x1800453ec  lea     rbp, [rsp-420h]
0x1800453f4  sub     rsp, 520h
0x1800453fb  mov     rax, cs:__security_cookie
0x180045402  xor     rax, rsp
0x180045405  mov     [rbp+450h+var_40], rax
0x18004540c  xor     r12d, r12d
0x18004540f  mov     [rbp+450h+var_478], rcx
0x180045413  lea     rax, aRegistryMachin_15; "\\Registry\\Machine\\System\\CurrentCon"...
0x18004541a  mov     dword ptr [rbp+450h+ObjectAttributes+4], r12d
0x18004541e  mov     [rsp+550h+Src], rax
0x180045423  lea     rdi, [rbp+450h+KeyInformation]
0x18004542a  lea     rax, aImagepath; "ImagePath"
0x180045431  mov     dword ptr [rbp+450h+ObjectAttributes+1Ch], r12d
0x180045435  mov     [rbp+450h+ValueName.Buffer], rax
0x180045439  lea     rsi, [rbp+450h+KeyValueInformation]
0x18004543d  xor     eax, eax
0x18004543f  mov     [rsp+550h+KeyHandle], r12
0x180045444  mov     [rbp+450h+var_4C4], eax
0x180045447  mov     r14, r8
0x18004544a  mov     [rbp-78h], r12
0x18004544e  mov     r15, rdx
0x180045451  mov     [rsp+550h+Handle], r12
0x180045456  mov     [rsp+550h+var_4E8], 680066h
0x18004545f  mov     qword ptr [rbp+450h+ValueName.Length], 140012h
0x180045467  mov     [rsp+550h+var_510], r12d
0x18004546c  mov     [rbp+450h+var_4C0], r12
0x180045470  mov     [rsp+550h+var_4D8], r12
0x180045475  mov     [rbp+450h+var_4D0], r12
0x180045479  test    rdx, rdx
0x18004547c  jz      short loc_180045482
0x18004547e  mov     [rdx+8], r12
0x180045482  test    r14, r14
0x180045485  jz      short loc_18004548B
0x180045487  mov     [r8+8], r12
0x18004548b  lea     rax, [rsp+550h+var_4E8]
0x180045490  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x180045497  xorps   xmm0, xmm0
0x18004549a  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18004549e  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x1800454a2  mov     [rbp+450h+ObjectAttributes.RootDirectory], r12
0x1800454a6  mov     edx, 20019h; DesiredAccess
0x1800454ab  mov     [rbp+450h+ObjectAttributes.Attributes], 240h
0x1800454b2  lea     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x1800454b7  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800454bc  call    cs:__imp_ZwOpenKey
0x1800454c3  nop     dword ptr [rax+rax+00h]
0x1800454c8  mov     ebx, eax
0x1800454ca  test    eax, eax
0x1800454cc  jns     short loc_18004551E
0x1800454ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800454d5  lea     rax, WPP_GLOBAL_Control
0x1800454dc  cmp     rcx, rax
0x1800454df  jz      loc_1800458A6
0x1800454e5  mov     edx, [rcx+2Ch]
0x1800454e8  test    dl, 1
0x1800454eb  jz      loc_1800458A6
0x1800454f1  mov     rcx, [rcx+18h]
0x1800454f5  lea     r12, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800454fc  mov     [rsp+550h+var_520], 268h
0x180045504  lea     r9, aSresult; "sResult"
0x18004550b  mov     [rsp+550h+ResultLength], r12
0x180045510  mov     [rsp+550h+Length], ebx
0x180045514  call    WPP_SF_sDsd
0x180045519  jmp     loc_1800458A3
0x18004551e  mov     ecx, 218h
0x180045523  mov     [rsp+550h+var_4F8], 210h
0x18004552b  mov     eax, r12d
0x18004552e  mov     [rsp+550h+var_508], ecx
0x180045532  lea     r12, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045539  lea     r13, aSresult; "sResult"
0x180045540  mov     [rsp+550h+var_50C], eax
0x180045544  cmp     eax, 10000h
0x180045549  jnb     loc_180045773
0x18004554f  test    rdi, rdi
0x180045552  jz      short loc_1800455D3
0x180045554  lea     rdx, [rsp+550h+var_510]
0x180045559  mov     r9, rdi; KeyInformation
0x18004555c  mov     [rsp+550h+ResultLength], rdx; ResultLength
0x180045561  xor     r8d, r8d; KeyInformationClass
0x180045564  mov     [rsp+550h+Length], ecx; Length
0x180045568  mov     edx, eax; Index
0x18004556a  mov     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18004556f  call    cs:__imp_ZwEnumerateKey
0x180045576  nop     dword ptr [rax+rax+00h]
0x18004557b  mov     ebx, eax
0x18004557d  cmp     eax, 0C0000023h
0x180045582  jz      short loc_180045590
0x180045584  cmp     eax, 80000005h
0x180045589  jnz     short loc_1800455D3
0x18004558b  test    rdi, rdi
0x18004558e  jz      short loc_1800455A4
0x180045590  lea     rax, [rbp+450h+KeyInformation]
0x180045597  cmp     rdi, rax
0x18004559a  jz      short loc_1800455A4
0x18004559c  mov     rcx, rdi; P
0x18004559f  call    MSCryptFree
0x1800455a4  mov     eax, [rsp+550h+var_510]
0x1800455a8  add     eax, 0FFh
0x1800455ad  and     eax, 0FFFFFF00h
0x1800455b2  mov     ecx, eax
0x1800455b4  mov     [rsp+550h+var_508], eax
0x1800455b8  call    MSCryptAlloc
0x1800455bd  mov     rdi, rax
0x1800455c0  test    rax, rax
0x1800455c3  jz      loc_180045747
0x1800455c9  mov     eax, [rsp+550h+var_50C]
0x1800455cd  mov     ecx, [rsp+550h+var_508]
0x1800455d1  jmp     short loc_180045554
0x1800455d3  test    ebx, ebx
0x1800455d5  js      loc_180045752
0x1800455db  movzx   eax, word ptr [rdi+0Ch]
0x1800455df  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x1800455e3  mov     word ptr [rsp+550h+var_4D8+2], ax
0x1800455e8  lea     rcx, [rsp+550h+Handle]; KeyHandle
0x1800455ed  mov     word ptr [rsp+550h+var_4D8], ax
0x1800455f2  xorps   xmm0, xmm0
0x1800455f5  lea     rax, [rdi+10h]
0x1800455f9  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x180045600  mov     [rbp+450h+var_4D0], rax
0x180045604  mov     edx, 20019h; DesiredAccess
0x180045609  mov     rax, [rsp+550h+KeyHandle]
0x18004560e  mov     [rbp+450h+ObjectAttributes.RootDirectory], rax
0x180045612  lea     rax, [rsp+550h+var_4D8]
0x180045617  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18004561b  mov     [rbp+450h+ObjectAttributes.Attributes], 240h
0x180045622  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x180045627  call    cs:__imp_ZwOpenKey
0x18004562e  nop     dword ptr [rax+rax+00h]
0x180045633  xor     edx, edx
0x180045635  mov     ebx, eax
0x180045637  test    eax, eax
0x180045639  js      loc_180045738
0x18004563f  test    rsi, rsi
0x180045642  jz      loc_1800456DE
0x180045648  mov     rcx, [rsp+550h+Handle]; KeyHandle
0x18004564d  lea     rax, [rsp+550h+var_510]
0x180045652  mov     [rsp+550h+ResultLength], rax; ResultLength
0x180045657  lea     rdx, [rbp+450h+ValueName]; ValueName
0x18004565b  mov     eax, [rsp+550h+var_4F8]
0x18004565f  mov     r9, rsi; KeyValueInformation
0x180045662  mov     r8d, 2; KeyValueInformationClass
0x180045668  mov     [rsp+550h+Length], eax; Length
0x18004566c  call    cs:__imp_ZwQueryValueKey
0x180045673  nop     dword ptr [rax+rax+00h]
0x180045678  mov     ebx, eax
0x18004567a  cmp     eax, 0C0000023h
0x18004567f  jz      short loc_18004568D
0x180045681  cmp     eax, 80000005h
0x180045686  jnz     short loc_1800456DC
0x180045688  test    rsi, rsi
0x18004568b  jz      short loc_18004569E
0x18004568d  lea     rax, [rbp+450h+KeyValueInformation]
0x180045691  cmp     rsi, rax
0x180045694  jz      short loc_18004569E
0x180045696  mov     rcx, rsi; P
0x180045699  call    MSCryptFree
0x18004569e  mov     eax, [rsp+550h+var_510]
0x1800456a2  add     eax, 0FFh
0x1800456a7  and     eax, 0FFFFFF00h
0x1800456ac  mov     ecx, eax
0x1800456ae  mov     [rsp+550h+var_4F8], eax
0x1800456b2  call    MSCryptAlloc
0x1800456b7  mov     rsi, rax
0x1800456ba  test    rax, rax
0x1800456bd  jnz     short loc_180045648
0x1800456bf  mov     r9d, 2DDh
0x1800456c5  mov     r8, r12
0x1800456c8  mov     rdx, r13
0x1800456cb  mov     ecx, 0C000009Ah
0x1800456d0  mov     ebx, 0C000009Ah
0x1800456d5  call    DebugTraceError
0x1800456da  jmp     short loc_18004571E
0x1800456dc  xor     edx, edx
0x1800456de  test    ebx, ebx
0x1800456e0  js      short loc_18004571E
0x1800456e2  mov     ecx, [rsi+8]
0x1800456e5  cmp     ecx, 2
0x1800456e8  ja      short loc_1800456F2
0x1800456ea  jmp     short loc_18004571E
0x1800456ec  add     ecx, 0FFFFFFFEh
0x1800456ef  mov     [rsi+8], ecx
0x1800456f2  cmp     [rcx+rsi+0Ah], dx
0x1800456f7  jz      short loc_1800456EC
0x1800456f9  movzx   eax, word ptr [rsi+8]
0x1800456fd  lea     rcx, [rbp+450h+var_4C8]
0x180045701  mov     rdx, [rbp+450h+var_478]
0x180045705  mov     [rbp+450h+var_4C6], ax
0x180045709  mov     [rbp+450h+var_4C8], ax
0x18004570d  lea     rax, [rsi+0Ch]
0x180045711  mov     [rbp+450h+var_4C0], rax
0x180045715  call    _IsImagePath
0x18004571a  test    eax, eax
0x18004571c  jnz     short loc_180045792
0x18004571e  mov     rcx, [rsp+550h+Handle]; Handle
0x180045723  call    cs:__imp_ZwClose
0x18004572a  nop     dword ptr [rax+rax+00h]
0x18004572f  mov     [rsp+550h+Handle], 0
0x180045738  mov     eax, [rsp+550h+var_50C]
0x18004573c  mov     ecx, [rsp+550h+var_508]
0x180045740  inc     eax
0x180045742  jmp     loc_180045540
0x180045747  mov     r9d, 290h
0x18004574d  jmp     loc_18004588E
0x180045752  cmp     ebx, 8000001Ah
0x180045758  jnz     loc_1800458A3
0x18004575e  mov     ebx, 0C0000225h
0x180045763  mov     r9d, 29Ch
0x180045769  mov     ecx, 0C0000225h
0x18004576e  jmp     loc_180045898
0x180045773  jnz     short loc_180045792
0x180045775  mov     r9d, 305h
0x18004577b  mov     r8, r12
0x18004577e  mov     rdx, r13
0x180045781  mov     ecx, 0C0000225h
0x180045786  mov     ebx, 0C0000225h
0x18004578b  call    DebugTraceError
0x180045790  jmp     short loc_180045796
0x180045792  test    ebx, ebx
0x180045794  jns     short loc_1800457A3
0x180045796  mov     r9d, 30Ah
0x18004579c  mov     ecx, ebx
0x18004579e  jmp     loc_180045898
0x1800457a3  mov     ecx, 0FFF8h
0x1800457a8  test    r15, r15
0x1800457ab  jz      loc_18004584D
0x1800457b1  movzx   eax, word ptr [rsp+550h+var_4D8]
0x1800457b6  add     ax, 2
0x1800457ba  add     ax, word ptr [rsp+550h+var_4E8]
0x1800457bf  mov     [r15], ax
0x1800457c3  add     ax, 7
0x1800457c7  and     ax, cx
0x1800457ca  movzx   ecx, ax
0x1800457cd  mov     [r15+2], cx
0x1800457d2  call    MSCryptAlloc
0x1800457d7  mov     [r15+8], rax
0x1800457db  test    rax, rax
0x1800457de  jnz     short loc_180045803
0x1800457e0  mov     r9d, 318h
0x1800457e6  mov     r8, r12
0x1800457e9  mov     rdx, r13
0x1800457ec  mov     ecx, 0C000009Ah
0x1800457f1  mov     ebx, 0C000009Ah
0x1800457f6  call    DebugTraceError
0x1800457fb  xor     r12d, r12d
0x1800457fe  jmp     loc_1800458AB
0x180045803  movzx   r8d, word ptr [rsp+550h+var_4E8]; Size
0x180045809  mov     rcx, rax; void *
0x18004580c  mov     rdx, [rsp+550h+Src]; Src
0x180045811  call    memmove
0x180045816  movzx   ecx, word ptr [rsp+550h+var_4E8]
0x18004581b  lea     rdx, [rdi+10h]; Src
0x18004581f  mov     rax, [r15+8]
0x180045823  shr     rcx, 1
0x180045826  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18004582c  movzx   ecx, word ptr [rsp+550h+var_4E8]
0x180045831  mov     rax, [r15+8]
0x180045835  mov     r8d, [rdi+0Ch]; Size
0x180045839  shr     rcx, 1
0x18004583c  inc     rcx
0x18004583f  lea     rcx, [rax+rcx*2]; void *
0x180045843  call    memmove
0x180045848  mov     ecx, 0FFF8h
0x18004584d  test    r14, r14
0x180045850  jz      loc_180045924
0x180045856  movzx   eax, word ptr [rsp+550h+var_4D8]
0x18004585b  mov     edx, 0Eh
0x180045860  add     dx, 2
0x180045864  add     ax, dx
0x180045867  mov     [r14], ax
0x18004586b  add     ax, 7
0x18004586f  and     ax, cx
0x180045872  movzx   ecx, ax
0x180045875  mov     [r14+2], cx
0x18004587a  call    MSCryptAlloc
0x18004587f  mov     [r14+8], rax
0x180045883  test    rax, rax
0x180045886  jnz     short loc_1800458E4
0x180045888  mov     r9d, 330h
0x18004588e  mov     ebx, 0C000009Ah
0x180045893  mov     ecx, 0C000009Ah
0x180045898  mov     r8, r12
0x18004589b  mov     rdx, r13
0x18004589e  call    DebugTraceError
0x1800458a3  xor     r12d, r12d
0x1800458a6  test    r15, r15
0x1800458a9  jz      short loc_1800458C4
0x1800458ab  mov     rcx, [r15+8]; P
0x1800458af  test    rcx, rcx
0x1800458b2  jz      short loc_1800458BD
0x1800458b4  call    MSCryptFree
0x1800458b9  mov     [r15+8], r12
0x1800458bd  mov     dword ptr [r15], 0
  ... truncated ...
```
