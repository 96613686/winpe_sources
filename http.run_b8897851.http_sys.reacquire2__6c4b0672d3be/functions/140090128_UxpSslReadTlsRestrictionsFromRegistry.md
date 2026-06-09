# UxpSslReadTlsRestrictionsFromRegistry

- ea: `0x140090128`
- end: `0x1400903c7`
- name: `UxpSslReadTlsRestrictionsFromRegistry`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008ef04`

## callees

- `0x140090128`
- `0x140090810`
- `0x14009def0`
- `0x140167840`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14009023b`
- `ntoskrnl!ZwOpenKey` at `0x14009023b`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ab0f`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ad2d`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ab0f`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ad2d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017ac53`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017aefe`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017ac53`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017aefe`
- `ntoskrnl!ZwClose` at `0x140090334`
- `ntoskrnl!ZwClose` at `0x140090348`
- `ntoskrnl!ZwClose` at `0x14009035c`
- `ntoskrnl!ZwClose` at `0x140090370`
- `ntoskrnl!ZwClose` at `0x140090384`
- `ntoskrnl!ZwClose` at `0x140090398`
- `ntoskrnl!ZwClose` at `0x14017aca9`
- `ntoskrnl!ZwClose` at `0x14017af55`
- `ntoskrnl!ZwClose` at `0x14017af7e`
- `ntoskrnl!ZwClose` at `0x14017afa2`
- `ntoskrnl!ZwClose` at `0x14017afc9`
- `ntoskrnl!ZwClose` at `0x14017b012`
- `ntoskrnl!ZwClose` at `0x140090334`
- `ntoskrnl!ZwClose` at `0x140090348`
- `ntoskrnl!ZwClose` at `0x14009035c`
- `ntoskrnl!ZwClose` at `0x140090370`
- `ntoskrnl!ZwClose` at `0x140090384`
- `ntoskrnl!ZwClose` at `0x140090398`
- `ntoskrnl!ZwClose` at `0x14017aca9`
- `ntoskrnl!ZwClose` at `0x14017af55`
- `ntoskrnl!ZwClose` at `0x14017af7e`
- `ntoskrnl!ZwClose` at `0x14017afa2`
- `ntoskrnl!ZwClose` at `0x14017afc9`
- `ntoskrnl!ZwClose` at `0x14017b012`
- `ntoskrnl!ExAllocatePool3` at `0x1400901a2`
- `ntoskrnl!ExAllocatePool3` at `0x1400901da`
- `ntoskrnl!ExAllocatePool3` at `0x1400901a2`
- `ntoskrnl!ExAllocatePool3` at `0x1400901da`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090260`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009027a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090260`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009027a`

## string_xrefs

- `0x14017abc5`: `DisabledProtocols`

## pseudocode

```c
__int64 __fastcall UxpSslReadTlsRestrictionsFromRegistry(void *a1, __int64 a2)
{
  void *v2; // rdi
  HANDLE v3; // rsi
  HANDLE v4; // r13
  HANDLE v5; // r15
  HANDLE v6; // r14
  HANDLE v7; // r12
  NTSTATUS v9; // eax
  int RegistryKeyValue; // ebx
  _WORD *v12; // r12
  NTSTATUS v13; // eax
  ULONG *v14; // r12
  ULONG v15; // r12d
  int v16; // eax
  NTSTATUS v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  _WORD *v20; // r12
  NTSTATUS v21; // eax
  __int64 v22; // r12
  void *v23; // rax
  ULONG v24; // r12d
  NTSTATUS v25; // eax
  unsigned int v26; // eax
  NTSTATUS v27; // eax
  void *v28; // [rsp+30h] [rbp-79h]
  HANDLE v29; // [rsp+40h] [rbp-69h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  PVOID P; // [rsp+50h] [rbp-59h]
  HANDLE v32; // [rsp+58h] [rbp-51h] BYREF
  ULONG *v33; // [rsp+60h] [rbp-49h]
  HANDLE v34; // [rsp+68h] [rbp-41h] BYREF
  HANDLE v35; // [rsp+70h] [rbp-39h] BYREF
  PVOID Pool3; // [rsp+78h] [rbp-31h]
  void *KeyHandle; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v38[2]; // [rsp+88h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-11h] BYREF
  ULONG Index; // [rsp+120h] [rbp+77h]
  ULONG ResultLength; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = 0;
  ResultLength = 0;
  v3 = 0;
  v32 = 0;
  v4 = 0;
  Handle = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v34 = 0;
  v7 = 0;
  v29 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1041, 36, WPP_b370fe665b8033233cc44e642047166f_Traceguids, a1, a2);
  P = (PVOID)ExAllocatePool3(258, 544, 1146252373, UxLowPriorityPool, 1);
  if ( P )
  {
    Pool3 = (PVOID)ExAllocatePool3(258, 21056, 1381264469, UxLowPriorityPool, 1);
    if ( Pool3 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      v38[1] = L"TlsRestrictions";
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v38;
      v38[0] = 1966110;
      KeyHandle = 0;
      ObjectAttributes.RootDirectory = a1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      RegistryKeyValue = v9;
      if ( v9 >= 0 )
      {
        v2 = KeyHandle;
        KeyHandle = 0;
        while ( 1 )
        {
          Index = (unsigned int)v7;
          if ( (unsigned int)v7 >= 4 )
            break;
          v12 = P;
          v13 = ZwEnumerateKey(v2, Index, KeyBasicInformation, P, 0x220u, &ResultLength);
          RegistryKeyValue = v13;
          if ( v13 == -2147483622 )
          {
            LODWORD(v7) = Index;
            break;
          }
          if ( v13 < 0 )
            goto LABEL_27;
          RegistryKeyValue = UxOpenKey(v2, (__int64)(v12 + 8), v12[6], 0x20019u, 0, &v32);
          if ( RegistryKeyValue < 0 )
          {
            v3 = v32;
            goto LABEL_27;
          }
          v14 = (ULONG *)((char *)Pool3 + 5264 * Index);
          v33 = v14;
          v3 = v32;
          RegistryKeyValue = UxReadRegistryKeyValue(v32, 0, 0, v14 + 1315, 4u);
          if ( RegistryKeyValue < 0 )
            goto LABEL_27;
          v28 = v14 + 129;
          v15 = 0;
          RegistryKeyValue = UxReadRegistryKeyValue(v3, 0, 0, v28, 4u);
          if ( RegistryKeyValue < 0 )
            goto LABEL_27;
          v16 = UxOpenKey(v3, (__int64)L"AlpnIds", 14, 0x20019u, 0, &Handle);
          v4 = Handle;
          RegistryKeyValue = v16;
          if ( v16 < 0 )
            goto LABEL_27;
          while ( v15 < 8 )
          {
            v17 = ZwEnumerateValueKey(v4, v15, KeyValueFullInformation, P, 0x220u, &ResultLength);
            RegistryKeyValue = v17;
            if ( v17 == -2147483622 )
              break;
            if ( v17 < 0 )
              goto LABEL_27;
            v18 = *((_DWORD *)P + 3);
            if ( v18 > 0x40 )
              v18 = 64;
            memmove(&v33[16 * (unsigned __int64)v15++ + 1], (char *)P + *((unsigned int *)P + 2), v18);
          }
          RegistryKeyValue = ZwClose(v4);
          if ( RegistryKeyValue < 0 )
            goto LABEL_27;
          v4 = 0;
          Handle = 0;
          *v33 = v15;
          v19 = UxOpenKey(v3, (__int64)L"CryptoSettings", 28, 0x20019u, 0, &v35);
          v5 = v35;
          RegistryKeyValue = v19;
          if ( v19 < 0 )
            goto LABEL_27;
          while ( (unsigned int)v4 < 8 )
          {
            v20 = P;
            v21 = ZwEnumerateKey(v5, (ULONG)v4, KeyBasicInformation, P, 0x220u, &ResultLength);
            RegistryKeyValue = v21;
            if ( v21 == -2147483622 )
              break;
            if ( v21 < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxOpenKey(v5, (__int64)(v20 + 8), v20[6], 0x20019u, 0, &v34);
            if ( RegistryKeyValue < 0 )
            {
              v6 = v34;
              goto LABEL_66;
            }
            v22 = (__int64)&v33[148 * (unsigned int)v4 + 131];
            v6 = v34;
            v32 = (HANDLE)v22;
            RegistryKeyValue = UxReadRegistryKeyValue(v34, 0, 0, (void *)v22, 4u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxReadRegistryKeyValue(v6, 0, 0, (void *)(v22 + 584), 4u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxReadRegistryKeyValue(v6, 0, 0, (void *)(v22 + 588), 4u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            v23 = (void *)(v22 + 4);
            v24 = 0;
            RegistryKeyValue = UxReadRegistryKeyValue(v6, 0, 0, v23, 0x40u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxOpenKey(v6, (__int64)L"ChainingModes", 26, 0x20019u, 0, &v29);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            while ( v24 < 8 )
            {
              v25 = ZwEnumerateValueKey(v29, v24, KeyValueFullInformation, P, 0x220u, &ResultLength);
              RegistryKeyValue = v25;
              if ( v25 == -2147483622 )
                break;
              if ( v25 < 0 )
                goto LABEL_66;
              v26 = *((_DWORD *)P + 3);
              if ( v26 > 0x40 )
                v26 = 64;
              memmove((char *)v32 + 64 * (unsigned __int64)v24++ + 72, (char *)P + *((unsigned int *)P + 2), v26);
            }
            RegistryKeyValue = ZwClose(v29);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            v29 = 0;
            *((_DWORD *)v32 + 17) = v24;
            RegistryKeyValue = ZwClose(v6);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            v6 = 0;
            v34 = 0;
            LODWORD(v4) = (_DWORD)v4 + 1;
          }
          RegistryKeyValue = ZwClose(v5);
          if ( RegistryKeyValue < 0 )
          {
LABEL_66:
            v4 = Handle;
            goto LABEL_27;
          }
          v5 = 0;
          v35 = 0;
          v33[130] = (unsigned int)v4;
          v27 = ZwClose(v3);
          v4 = Handle;
          RegistryKeyValue = v27;
          if ( v27 < 0 )
            goto LABEL_27;
          v3 = 0;
          v32 = 0;
          LODWORD(v7) = Index + 1;
        }
        RegistryKeyValue = ZwClose(v2);
        if ( RegistryKeyValue >= 0 )
        {
          v2 = 0;
          if ( (_DWORD)v7 )
          {
            *(_QWORD *)(a2 + 8) = Pool3;
            Pool3 = 0;
          }
          *(_DWORD *)a2 = (_DWORD)v7;
        }
LABEL_27:
        v7 = v29;
      }
      else if ( v9 == -1073741772 )
      {
        RegistryKeyValue = 0;
      }
    }
    else
    {
      RegistryKeyValue = -1073741670;
    }
    ExFreePoolWithTag(P, 0);
    if ( Pool3 )
      ExFreePoolWithTag(Pool3, 0);
    if ( v2 )
      ZwClose(v2);
    if ( v3 )
      ZwClose(v3);
    if ( v4 )
      ZwClose(v4);
    if ( v5 )
      ZwClose(v5);
    if ( v6 )
      ZwClose(v6);
    if ( v7 )
      ZwClose(v7);
  }
  else
  {
    RegistryKeyValue = -1073741670;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 37, WPP_b370fe665b8033233cc44e642047166f_Traceguids, (unsigned int)RegistryKeyValue);
  return (unsigned int)RegistryKeyValue;
}

```

## disassembly

```asm
0x140090128  mov     [rsp-8+arg_0], rbx
0x14009012d  mov     [rsp-8+arg_8], rdx
0x140090132  push    rbp
0x140090133  push    rsi
0x140090134  push    rdi
0x140090135  push    r12
0x140090137  push    r13
0x140090139  push    r14
0x14009013b  push    r15
0x14009013d  lea     rbp, [rsp-27h]
0x140090142  sub     rsp, 0D0h
0x140090149  xor     edi, edi
0x14009014b  mov     r8, rdx
0x14009014e  mov     [rbp+57h+arg_18], edi
0x140090151  mov     esi, edi
0x140090153  mov     [rbp+57h+var_A8], rdi
0x140090157  mov     r13d, edi
0x14009015a  mov     [rbp+57h+Handle], rdi
0x14009015e  mov     r15d, edi
0x140090161  mov     [rbp+57h+var_90], rdi
0x140090165  mov     r14d, edi
0x140090168  mov     [rbp+57h+var_98], rdi
0x14009016c  mov     r12d, edi
0x14009016f  mov     [rbp+57h+var_C0], rdi
0x140090173  mov     rbx, rcx
0x140090176  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14009017d  jnz     loc_140090307
0x140090183  lea     r9, UxLowPriorityPool
0x14009018a  mov     [rsp+100h+Length], 1
0x140090192  mov     edx, 220h
0x140090197  mov     ecx, 102h
0x14009019c  mov     r8d, 44526C55h
0x1400901a2  call    cs:__imp_ExAllocatePool3
0x1400901a9  nop     dword ptr [rax+rax+00h]
0x1400901ae  mov     [rbp+57h+P], rax
0x1400901b2  test    rax, rax
0x1400901b5  jz      loc_14009032A
0x1400901bb  lea     r9, UxLowPriorityPool
0x1400901c2  mov     [rsp+100h+Length], 1
0x1400901ca  mov     edx, 5240h
0x1400901cf  mov     ecx, 102h
0x1400901d4  mov     r8d, 52546C55h
0x1400901da  call    cs:__imp_ExAllocatePool3
0x1400901e1  nop     dword ptr [rax+rax+00h]
0x1400901e6  mov     [rbp+57h+var_88], rax
0x1400901ea  test    rax, rax
0x1400901ed  jz      loc_1400902F4
0x1400901f3  lea     rax, aTlsrestriction; "TlsRestrictions"
0x1400901fa  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140090202  mov     [rbp+57h+var_70], rax
0x140090206  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009020a  lea     rax, [rbp+57h+var_78]
0x14009020e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140090216  xorps   xmm0, xmm0
0x140090219  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14009021d  mov     edx, 20019h; DesiredAccess
0x140090222  mov     [rbp+57h+var_78], 1E001Eh
0x14009022a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009022e  mov     [rbp+57h+KeyHandle], rdi
0x140090232  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140090236  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009023b  call    cs:__imp_ZwOpenKey
0x140090242  nop     dword ptr [rax+rax+00h]
0x140090247  mov     ebx, eax
0x140090249  test    eax, eax
0x14009024b  jns     loc_1400902E7
0x140090251  cmp     eax, 0C0000034h
0x140090256  jnz     short loc_14009025A
0x140090258  mov     ebx, edi
0x14009025a  mov     rcx, [rbp+57h+P]; P
0x14009025e  xor     edx, edx; Tag
0x140090260  call    cs:__imp_ExFreePoolWithTag
0x140090267  nop     dword ptr [rax+rax+00h]
0x14009026c  mov     rax, [rbp+57h+var_88]
0x140090270  test    rax, rax
0x140090273  jz      short loc_140090286
0x140090275  xor     edx, edx; Tag
0x140090277  mov     rcx, rax; P
0x14009027a  call    cs:__imp_ExFreePoolWithTag
0x140090281  nop     dword ptr [rax+rax+00h]
0x140090286  test    rdi, rdi
0x140090289  jnz     loc_140090331
0x14009028f  test    rsi, rsi
0x140090292  jnz     loc_140090345
0x140090298  test    r13, r13
0x14009029b  jnz     loc_140090359
0x1400902a1  test    r15, r15
0x1400902a4  jnz     loc_14009036D
0x1400902aa  test    r14, r14
0x1400902ad  jnz     loc_140090381
0x1400902b3  test    r12, r12
0x1400902b6  jnz     loc_140090395
0x1400902bc  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400902c3  jnz     loc_1400903A9
0x1400902c9  mov     eax, ebx
0x1400902cb  mov     rbx, [rsp+100h+arg_0]
0x1400902d3  add     rsp, 0D0h
0x1400902da  pop     r15
0x1400902dc  pop     r14
0x1400902de  pop     r13
0x1400902e0  pop     r12
0x1400902e2  pop     rdi
0x1400902e3  pop     rsi
0x1400902e4  pop     rbp
0x1400902e5  retn
0x1400902e7  mov     rdi, [rbp+57h+KeyHandle]
0x1400902eb  mov     [rbp+57h+KeyHandle], rsi
0x1400902ef  jmp     loc_14017AAE0
0x1400902f4  mov     ebx, 0C000009Ah
0x1400902f9  jmp     loc_14009025A
0x1400902fe  mov     r12, [rbp+57h+var_C0]
0x140090302  jmp     loc_14009025A
0x140090307  mov     qword ptr [rsp+100h+Length], r8
0x14009030c  mov     edx, 24h ; '$'
0x140090311  lea     r8, WPP_b370fe665b8033233cc44e642047166f_Traceguids
0x140090318  mov     ecx, 411h
0x14009031d  mov     r9, rbx
0x140090320  call    WPP_SF_qq
0x140090325  jmp     loc_140090183
0x14009032a  mov     ebx, 0C000009Ah
0x14009032f  jmp     short loc_1400902BC
0x140090331  mov     rcx, rdi; Handle
0x140090334  call    cs:__imp_ZwClose
0x14009033b  nop     dword ptr [rax+rax+00h]
0x140090340  jmp     loc_14009028F
0x140090345  mov     rcx, rsi; Handle
0x140090348  call    cs:__imp_ZwClose
0x14009034f  nop     dword ptr [rax+rax+00h]
0x140090354  jmp     loc_140090298
0x140090359  mov     rcx, r13; Handle
0x14009035c  call    cs:__imp_ZwClose
0x140090363  nop     dword ptr [rax+rax+00h]
0x140090368  jmp     loc_1400902A1
0x14009036d  mov     rcx, r15; Handle
0x140090370  call    cs:__imp_ZwClose
0x140090377  nop     dword ptr [rax+rax+00h]
0x14009037c  jmp     loc_1400902AA
0x140090381  mov     rcx, r14; Handle
0x140090384  call    cs:__imp_ZwClose
0x14009038b  nop     dword ptr [rax+rax+00h]
0x140090390  jmp     loc_1400902B3
0x140090395  mov     rcx, r12; Handle
0x140090398  call    cs:__imp_ZwClose
0x14009039f  nop     dword ptr [rax+rax+00h]
0x1400903a4  jmp     loc_1400902BC
0x1400903a9  mov     edx, 25h ; '%'
0x1400903ae  lea     r8, WPP_b370fe665b8033233cc44e642047166f_Traceguids
0x1400903b5  mov     ecx, 411h
0x1400903ba  mov     r9d, ebx
0x1400903bd  call    WPP_SF_d
0x1400903c2  jmp     loc_1400902C9
0x14017aae0  mov     [rbp+57h+Index], r12d
0x14017aae4  cmp     r12d, 4
0x14017aae8  jnb     loc_14017B00F
0x14017aaee  mov     r12, [rbp+57h+P]
0x14017aaf2  lea     rax, [rbp+57h+arg_18]
0x14017aaf6  mov     edx, [rbp+57h+Index]; Index
0x14017aaf9  mov     r9, r12; KeyInformation
0x14017aafc  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14017ab01  xor     r8d, r8d; KeyInformationClass
0x14017ab04  mov     rcx, rdi; KeyHandle
0x14017ab07  mov     [rsp+100h+Length], 220h; Length
0x14017ab0f  call    cs:__imp_ZwEnumerateKey
0x14017ab16  nop     dword ptr [rax+rax+00h]
0x14017ab1b  mov     ebx, eax
0x14017ab1d  cmp     eax, 8000001Ah
0x14017ab22  jz      loc_14017B00B
0x14017ab28  test    eax, eax
0x14017ab2a  js      loc_1400902FE
0x14017ab30  movzx   r8d, word ptr [r12+0Ch]
0x14017ab36  lea     rcx, [rbp+57h+var_A8]
0x14017ab3a  mov     [rsp+100h+ResultLength], rcx
0x14017ab3f  lea     rdx, [r12+10h]
0x14017ab44  xor     esi, esi
0x14017ab46  mov     rcx, rdi
0x14017ab49  mov     r9d, 20019h
0x14017ab4f  mov     byte ptr [rsp+100h+Length], sil
0x14017ab54  call    UxOpenKey
0x14017ab59  mov     ebx, eax
0x14017ab5b  test    eax, eax
0x14017ab5d  js      loc_14017B002
0x14017ab63  mov     eax, [rbp+57h+Index]
0x14017ab66  lea     r8d, [rsi+4]
0x14017ab6a  mov     [rsp+100h+var_C8], r8d; ULONG
0x14017ab6f  lea     rdx, aFlags; "Flags"
0x14017ab76  imul    r12, rax, 1490h
0x14017ab7d  xor     r9d, r9d
0x14017ab80  add     r12, [rbp+57h+var_88]
0x14017ab84  mov     [rbp+57h+var_A0], r12
0x14017ab88  lea     rax, [r12+148Ch]
0x14017ab90  mov     [rsp+100h+var_D0], rax; void *
0x14017ab95  mov     dword ptr [rsp+100h+ResultLength], esi; int
0x14017ab99  mov     qword ptr [rsp+100h+Length], rsi; Src
0x14017ab9e  mov     rsi, [rbp+57h+var_A8]
0x14017aba2  mov     rcx, rsi; KeyHandle
0x14017aba5  call    UxReadRegistryKeyValue
0x14017abaa  mov     ebx, eax
0x14017abac  test    eax, eax
0x14017abae  js      loc_1400902FE
0x14017abb4  mov     ecx, 4
0x14017abb9  lea     rax, [r12+204h]
0x14017abc1  mov     [rsp+100h+var_C8], ecx; ULONG
0x14017abc5  lea     rdx, aDisabledprotoc; "DisabledProtocols"
0x14017abcc  mov     [rsp+100h+var_D0], rax; void *
0x14017abd1  xor     r12d, r12d
0x14017abd4  mov     r8d, ecx
0x14017abd7  mov     dword ptr [rsp+100h+ResultLength], r12d; int
0x14017abdc  xor     r9d, r9d
0x14017abdf  mov     qword ptr [rsp+100h+Length], r12; Src
0x14017abe4  mov     rcx, rsi; KeyHandle
0x14017abe7  call    UxReadRegistryKeyValue
0x14017abec  mov     ebx, eax
0x14017abee  test    eax, eax
0x14017abf0  js      loc_1400902FE
0x14017abf6  lea     rax, [rbp+57h+Handle]
0x14017abfa  mov     r9d, 20019h
0x14017ac00  mov     [rsp+100h+ResultLength], rax
0x14017ac05  lea     r8d, [r12+0Eh]
0x14017ac0a  lea     rdx, aAlpnids; "AlpnIds"
0x14017ac11  mov     byte ptr [rsp+100h+Length], r12b
0x14017ac16  mov     rcx, rsi
0x14017ac19  call    UxOpenKey
0x14017ac1e  mov     r13, [rbp+57h+Handle]
0x14017ac22  mov     ebx, eax
0x14017ac24  test    eax, eax
0x14017ac26  js      loc_1400902FE
0x14017ac2c  cmp     r12d, 8
0x14017ac30  jnb     short loc_14017ACA6
0x14017ac32  mov     r9, [rbp+57h+P]; KeyValueInformation
0x14017ac36  lea     rax, [rbp+57h+arg_18]
0x14017ac3a  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14017ac3f  mov     r8d, 1; KeyValueInformationClass
0x14017ac45  mov     edx, r12d; Index
0x14017ac48  mov     [rsp+100h+Length], 220h; Length
0x14017ac50  mov     rcx, r13; KeyHandle
0x14017ac53  call    cs:__imp_ZwEnumerateValueKey
0x14017ac5a  nop     dword ptr [rax+rax+00h]
0x14017ac5f  mov     ebx, eax
0x14017ac61  cmp     eax, 8000001Ah
0x14017ac66  jz      short loc_14017ACA6
0x14017ac68  test    eax, eax
0x14017ac6a  js      loc_1400902FE
0x14017ac70  mov     rcx, [rbp+57h+P]
0x14017ac74  mov     edx, 40h ; '@'
0x14017ac79  mov     eax, [rcx+0Ch]
0x14017ac7c  cmp     eax, edx
0x14017ac7e  cmova   eax, edx
0x14017ac81  mov     edx, [rcx+8]
0x14017ac84  add     rdx, rcx; Src
0x14017ac87  mov     r8d, eax; Size
0x14017ac8a  mov     rcx, [rbp+57h+var_A0]
0x14017ac8e  add     rcx, 4
0x14017ac92  mov     eax, r12d
0x14017ac95  shl     rax, 6
0x14017ac99  add     rcx, rax; void *
0x14017ac9c  call    memmove
0x14017aca1  inc     r12d
0x14017aca4  jmp     short loc_14017AC2C
0x14017aca6  mov     rcx, r13; Handle
0x14017aca9  call    cs:__imp_ZwClose
0x14017acb0  nop     dword ptr [rax+rax+00h]
0x14017acb5  mov     ebx, eax
0x14017acb7  test    eax, eax
0x14017acb9  js      loc_1400902FE
0x14017acbf  mov     rax, [rbp+57h+var_A0]
0x14017acc3  lea     rdx, aCryptosettings; "CryptoSettings"
0x14017acca  xor     r13d, r13d
0x14017accd  mov     r9d, 20019h
0x14017acd3  mov     rcx, rsi
0x14017acd6  mov     [rbp+57h+Handle], r13
0x14017acda  mov     [rax], r12d
0x14017acdd  lea     rax, [rbp+57h+var_90]
0x14017ace1  mov     [rsp+100h+ResultLength], rax
0x14017ace6  lea     r8d, [r13+1Ch]
0x14017acea  mov     byte ptr [rsp+100h+Length], r13b
0x14017acef  call    UxOpenKey
0x14017acf4  mov     r15, [rbp+57h+var_90]
0x14017acf8  mov     ebx, eax
0x14017acfa  test    eax, eax
0x14017acfc  js      loc_1400902FE
0x14017ad02  cmp     r13d, 8
0x14017ad06  jnb     loc_14017AF9F
0x14017ad0c  mov     r12, [rbp+57h+P]
0x14017ad10  lea     rax, [rbp+57h+arg_18]
0x14017ad14  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14017ad19  mov     r9, r12; KeyInformation
0x14017ad1c  xor     r8d, r8d; KeyInformationClass
0x14017ad1f  mov     [rsp+100h+Length], 220h; Length
0x14017ad27  mov     edx, r13d; Index
0x14017ad2a  mov     rcx, r15; KeyHandle
0x14017ad2d  call    cs:__imp_ZwEnumerateKey
0x14017ad34  nop     dword ptr [rax+rax+00h]
0x14017ad39  mov     ebx, eax
0x14017ad3b  cmp     eax, 8000001Ah
0x14017ad40  jz      loc_14017AF9F
0x14017ad46  test    eax, eax
0x14017ad48  js      loc_14017AFF9
0x14017ad4e  movzx   r8d, word ptr [r12+0Ch]
0x14017ad54  lea     rax, [rbp+57h+var_98]
0x14017ad58  mov     [rsp+100h+ResultLength], rax
  ... truncated ...
```
