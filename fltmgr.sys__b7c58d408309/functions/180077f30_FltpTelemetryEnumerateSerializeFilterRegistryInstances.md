# FltpTelemetryEnumerateSerializeFilterRegistryInstances

- ea: `0x180077f30`
- end: `0x1800783fc`
- name: `FltpTelemetryEnumerateSerializeFilterRegistryInstances`
- size: `1228`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING DestinationString, _WORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180055154`

## callees

- `0x180009f20`
- `0x18001e410`
- `0x18001e610`
- `0x180077f30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180078095`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800781d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007838d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800783a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180078095`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800781d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007838d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800783a6`
- `ntoskrnl!ExAllocatePool2` at `0x180077f9b`
- `ntoskrnl!ExAllocatePool2` at `0x180077fcf`
- `ntoskrnl!ExAllocatePool2` at `0x1800780b3`
- `ntoskrnl!ExAllocatePool2` at `0x1800781f2`
- `ntoskrnl!ExAllocatePool2` at `0x180077f9b`
- `ntoskrnl!ExAllocatePool2` at `0x180077fcf`
- `ntoskrnl!ExAllocatePool2` at `0x1800780b3`
- `ntoskrnl!ExAllocatePool2` at `0x1800781f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078138`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078186`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078138`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078186`
- `ntoskrnl!ZwClose` at `0x1800783e3`
- `ntoskrnl!ZwClose` at `0x1800783e3`
- `ntoskrnl!ZwOpenKey` at `0x180078117`
- `ntoskrnl!ZwOpenKey` at `0x180078117`
- `ntoskrnl!ZwQueryValueKey` at `0x180078162`
- `ntoskrnl!ZwQueryValueKey` at `0x1800781b0`
- `ntoskrnl!ZwQueryValueKey` at `0x180078162`
- `ntoskrnl!ZwQueryValueKey` at `0x1800781b0`
- `ntoskrnl!ZwEnumerateKey` at `0x180078034`
- `ntoskrnl!ZwEnumerateKey` at `0x180078034`

## pseudocode

```c
__int64 __fastcall FltpTelemetryEnumerateSerializeFilterRegistryInstances(
        HANDLE KeyHandle,
        PUNICODE_STRING DestinationString,
        _WORD *a3)
{
  ULONG Length; // r15d
  _WORD *Pool2; // r14
  NTSTATUS v7; // esi
  __int64 v8; // rbx
  ULONG v9; // edi
  ULONG v10; // eax
  NTSTATUS v11; // esi
  unsigned int v12; // esi
  NTSTATUS v13; // eax
  __int16 v14; // cx
  unsigned int v15; // ecx
  NTSTATUS v16; // edi
  PULONG ResultLength; // [rsp+30h] [rbp-81h]
  __int16 v19; // [rsp+48h] [rbp-69h]
  ULONG v20; // [rsp+4Ch] [rbp-65h] BYREF
  ULONG i; // [rsp+50h] [rbp-61h]
  NTSTATUS v22; // [rsp+54h] [rbp-5Dh]
  void *KeyHandlea; // [rsp+58h] [rbp-59h] BYREF
  UNICODE_STRING v24; // [rsp+60h] [rbp-51h] BYREF
  __int128 v25; // [rsp+70h] [rbp-41h] BYREF
  UNICODE_STRING DestinationStringa; // [rsp+80h] [rbp-31h] BYREF
  __int128 v27; // [rsp+90h] [rbp-21h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-11h] BYREF
  char v30; // [rsp+130h] [rbp+7Fh]

  Length = 80;
  v20 = 0;
  KeyHandlea = 0;
  DestinationStringa = 0;
  v27 = 0;
  memset(&ObjectAttributes, 0, 44);
  v25 = 0;
  v24 = 0;
  Pool2 = (_WORD *)ExAllocatePool2(256, 80, 1920224582);
  if ( !Pool2 )
  {
    v7 = -1073741670;
    goto LABEL_38;
  }
  v8 = ExAllocatePool2(256, 80, 1920224582);
  if ( v8 )
  {
    v9 = 80;
    v22 = RtlUnicodeStringCatString(DestinationString, "[");
    v19 = 2;
    v10 = 0;
    v30 = 0;
LABEL_6:
    for ( i = v10; ; v10 = i )
    {
      v11 = ZwEnumerateKey(KeyHandle, v10, KeyBasicInformation, Pool2, Length, &v20);
      if ( (int)FltpDbgStatus(v11) >= 0 )
      {
        LOWORD(v25) = Pool2[6];
        WORD1(v25) = v25;
        ObjectAttributes.Length = 48;
        *((_QWORD *)&v25 + 1) = Pool2 + 8;
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v25;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v7 = ZwOpenKey(&KeyHandlea, 0x20019u, &ObjectAttributes);
        if ( v7 < 0 )
          goto LABEL_34;
        RtlInitUnicodeString(&DestinationStringa, L"FLAGS");
        v7 = ZwQueryValueKey(KeyHandlea, &DestinationStringa, KeyValuePartialInformation, (PVOID)v8, v9, &v20);
        if ( v7 < 0 )
          goto LABEL_34;
        v12 = *(_DWORD *)(v8 + 12);
        RtlInitUnicodeString(&DestinationStringa, L"ALTITUDE");
        while ( 1 )
        {
          v13 = ZwQueryValueKey(KeyHandlea, &DestinationStringa, KeyValuePartialInformation, (PVOID)v8, v9, &v20);
          if ( v13 >= 0 )
            break;
          if ( v13 == -1073741789 || v13 == -2147483643 )
          {
            ExFreePoolWithTag((PVOID)v8, 0x72744D46u);
            v9 = v20;
            v8 = ExAllocatePool2(256, v20, 1920224582);
            if ( !v8 )
            {
              v10 = i + 1;
              goto LABEL_6;
            }
          }
        }
        if ( v30 )
        {
          if ( (int)FltpDbgStatus(v22) >= 0 )
            v22 = RtlUnicodeStringCatString(DestinationString, L",");
          v14 = v19 + 2;
        }
        else
        {
          v14 = v19;
          v30 = 1;
        }
        v19 = *(_WORD *)(v8 + 8) + 32 + v14;
        if ( (int)FltpDbgStatus(v22) >= 0 )
        {
          v15 = DestinationString->Length;
          LOWORD(v27) = *(_WORD *)(v8 + 8) - 2;
          WORD1(v27) = v27;
          *((_QWORD *)&v27 + 1) = v8 + 12;
          v24.Buffer = (wchar_t *)((char *)DestinationString->Buffer + v15);
          v24.Length = 0;
          LODWORD(ResultLength) = 8;
          v24.MaximumLength = DestinationString->MaximumLength - v15;
          v22 = RtlUnicodeStringPrintfEx(&v24, 0, 0x1100u, L"[\"%wZ\",\"0x%0*X\"]", &v27, ResultLength, v12);
          if ( (int)FltpDbgStatus(v22) >= 0 )
            DestinationString->Length += v24.Length;
        }
        v10 = i + 1;
        goto LABEL_6;
      }
      if ( v11 != -2147483643 && v11 != -1073741789 )
        break;
      ExFreePoolWithTag(Pool2, 0x72744D46u);
      Length = v20;
      Pool2 = (_WORD *)ExAllocatePool2(256, v20, 1920224582);
      if ( !Pool2 )
        break;
    }
    v16 = v22;
    if ( (int)FltpDbgStatus(v22) >= 0 )
      v16 = RtlUnicodeStringCatString(DestinationString, L"]");
    if ( a3 )
      *a3 = v19 + 2;
    FltpDbgStatus(v16);
    v7 = v16;
LABEL_34:
    if ( !Pool2 )
      goto LABEL_36;
  }
  else
  {
    v7 = -1073741670;
  }
  ExFreePoolWithTag(Pool2, 0x72744D46u);
LABEL_36:
  if ( v8 )
    ExFreePoolWithTag((PVOID)v8, 0x72744D46u);
LABEL_38:
  if ( KeyHandlea )
    ZwClose(KeyHandlea);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180077f30  mov     rax, rsp
0x180077f33  mov     [rax+18h], r8
0x180077f37  push    rbp
0x180077f38  push    rsi
0x180077f39  lea     rbp, [rax-5Fh]
0x180077f3d  sub     rsp, 0F8h
0x180077f44  xorps   xmm0, xmm0
0x180077f47  mov     [rax-20h], r12
0x180077f4b  mov     [rax-28h], r13
0x180077f4f  mov     r12, rcx
0x180077f52  mov     [rax-30h], r14
0x180077f56  mov     r13, rdx
0x180077f59  mov     [rax-38h], r15
0x180077f5d  xorps   xmm1, xmm1
0x180077f60  xor     esi, esi
0x180077f62  mov     r15d, 50h ; 'P'
0x180077f68  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180077f6c  mov     edx, r15d
0x180077f6f  mov     [rbp+57h+var_BC], esi
0x180077f72  xor     eax, eax
0x180077f74  mov     [rbp+57h+KeyHandle], rsi
0x180077f78  mov     r8d, 72744D46h
0x180077f7e  mov     ecx, 100h
0x180077f83  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180077f87  movups  [rbp+57h+var_78], xmm1
0x180077f8b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180077f8f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180077f93  movups  [rbp+57h+var_98], xmm0
0x180077f97  movups  xmmword ptr [rbp+57h+var_A8.Length], xmm0
0x180077f9b  call    cs:__imp_ExAllocatePool2
0x180077fa2  nop     dword ptr [rax+rax+00h]
0x180077fa7  mov     r14, rax
0x180077faa  test    rax, rax
0x180077fad  jnz     short loc_180077FB9
0x180077faf  mov     esi, 0C000009Ah
0x180077fb4  jmp     loc_1800783BA
0x180077fb9  mov     r8d, 72744D46h
0x180077fbf  mov     [rsp+100h+arg_0], rbx
0x180077fc7  mov     rdx, r15
0x180077fca  mov     ecx, 100h
0x180077fcf  call    cs:__imp_ExAllocatePool2
0x180077fd6  nop     dword ptr [rax+rax+00h]
0x180077fdb  mov     rbx, rax
0x180077fde  test    rax, rax
0x180077fe1  jnz     short loc_180077FED
0x180077fe3  mov     esi, 0C000009Ah
0x180077fe8  jmp     loc_180078385
0x180077fed  mov     [rsp+0F0h], rdi
0x180077ff5  lea     rdx, FltpTelemetryArrayStart; "["
0x180077ffc  mov     rcx, r13; DestinationString
0x180077fff  mov     edi, r15d
0x180078002  call    RtlUnicodeStringCatString
0x180078007  mov     [rbp+57h+var_B4], eax
0x18007800a  mov     eax, 2
0x18007800f  mov     [rbp+57h+var_C0], ax
0x180078013  mov     eax, esi
0x180078015  mov     [rbp+57h+arg_18], al
0x180078018  mov     [rbp+57h+var_B8], eax
0x18007801b  lea     rcx, [rbp+57h+var_BC]
0x18007801f  mov     r9, r14; KeyInformation
0x180078022  mov     [rsp+100h+ResultLength], rcx; ResultLength
0x180078027  xor     r8d, r8d; KeyInformationClass
0x18007802a  mov     rcx, r12; KeyHandle
0x18007802d  mov     [rsp+100h+Length], r15d; Length
0x180078032  mov     edx, eax; Index
0x180078034  call    cs:__imp_ZwEnumerateKey
0x18007803b  nop     dword ptr [rax+rax+00h]
0x180078040  mov     qword ptr [rsp+30h], 0
0x180078049  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180078050  mov     ecx, eax
0x180078052  mov     dword ptr [rsp+100h+ResultLength], 80000005h
0x18007805a  mov     r9d, 8000001Ah
0x180078060  mov     [rsp+100h+Length], 0C0000023h
0x180078068  mov     r8d, 541h
0x18007806e  mov     esi, eax
0x180078070  call    FltpDbgStatus
0x180078075  test    eax, eax
0x180078077  jns     short loc_1800780D3
0x180078079  cmp     esi, 80000005h
0x18007807f  jz      short loc_18007808D
0x180078081  cmp     esi, 0C0000023h
0x180078087  jnz     loc_18007831C
0x18007808d  mov     edx, 72744D46h; Tag
0x180078092  mov     rcx, r14; P
0x180078095  call    cs:__imp_ExFreePoolWithTag
0x18007809c  nop     dword ptr [rax+rax+00h]
0x1800780a1  mov     r15d, [rbp+57h+var_BC]
0x1800780a5  mov     ecx, 100h
0x1800780aa  mov     edx, r15d
0x1800780ad  mov     r8d, 72744D46h
0x1800780b3  call    cs:__imp_ExAllocatePool2
0x1800780ba  nop     dword ptr [rax+rax+00h]
0x1800780bf  mov     r14, rax
0x1800780c2  test    rax, rax
0x1800780c5  jz      loc_18007831C
0x1800780cb  mov     eax, [rbp+57h+var_B8]
0x1800780ce  jmp     loc_18007801B
0x1800780d3  movzx   eax, word ptr [r14+0Ch]
0x1800780d8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800780dc  mov     word ptr [rbp+57h+var_98], ax
0x1800780e0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800780e4  mov     word ptr [rbp+57h+var_98+2], ax
0x1800780e8  xorps   xmm0, xmm0
0x1800780eb  lea     rax, [r14+10h]
0x1800780ef  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800780f6  mov     qword ptr [rbp+57h+var_98+8], rax
0x1800780fa  mov     edx, 20019h; DesiredAccess
0x1800780ff  lea     rax, [rbp+57h+var_98]
0x180078103  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180078107  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007810b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180078112  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180078117  call    cs:__imp_ZwOpenKey
0x18007811e  nop     dword ptr [rax+rax+00h]
0x180078123  mov     esi, eax
0x180078125  test    eax, eax
0x180078127  js      loc_180078378
0x18007812d  lea     rdx, FltpRegFlagsValueName; "FLAGS"
0x180078134  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180078138  call    cs:__imp_RtlInitUnicodeString
0x18007813f  nop     dword ptr [rax+rax+00h]
0x180078144  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180078148  lea     rax, [rbp+57h+var_BC]
0x18007814c  mov     [rsp+100h+ResultLength], rax; ResultLength
0x180078151  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180078155  mov     r9, rbx; KeyValueInformation
0x180078158  mov     [rsp+100h+Length], edi; Length
0x18007815c  mov     r8d, 2; KeyValueInformationClass
0x180078162  call    cs:__imp_ZwQueryValueKey
0x180078169  nop     dword ptr [rax+rax+00h]
0x18007816e  mov     esi, eax
0x180078170  test    eax, eax
0x180078172  js      loc_180078378
0x180078178  mov     esi, [rbx+0Ch]
0x18007817b  lea     rdx, FltpRegAltitudeValueName; "ALTITUDE"
0x180078182  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180078186  call    cs:__imp_RtlInitUnicodeString
0x18007818d  nop     dword ptr [rax+rax+00h]
0x180078192  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180078196  lea     rax, [rbp+57h+var_BC]
0x18007819a  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18007819f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800781a3  mov     r9, rbx; KeyValueInformation
0x1800781a6  mov     [rsp+100h+Length], edi; Length
0x1800781aa  mov     r8d, 2; KeyValueInformationClass
0x1800781b0  call    cs:__imp_ZwQueryValueKey
0x1800781b7  nop     dword ptr [rax+rax+00h]
0x1800781bc  test    eax, eax
0x1800781be  jns     short loc_180078210
0x1800781c0  cmp     eax, 0C0000023h
0x1800781c5  jz      short loc_1800781CE
0x1800781c7  cmp     eax, 80000005h
0x1800781cc  jnz     short loc_180078192
0x1800781ce  mov     edx, 72744D46h; Tag
0x1800781d3  mov     rcx, rbx; P
0x1800781d6  call    cs:__imp_ExFreePoolWithTag
0x1800781dd  nop     dword ptr [rax+rax+00h]
0x1800781e2  mov     edi, [rbp+57h+var_BC]
0x1800781e5  mov     ecx, 100h
0x1800781ea  mov     edx, edi
0x1800781ec  mov     r8d, 72744D46h
0x1800781f2  call    cs:__imp_ExAllocatePool2
0x1800781f9  nop     dword ptr [rax+rax+00h]
0x1800781fe  mov     rbx, rax
0x180078201  test    rax, rax
0x180078204  jnz     short loc_180078192
0x180078206  mov     eax, [rbp+57h+var_B8]
0x180078209  inc     eax
0x18007820b  jmp     loc_180078018
0x180078210  cmp     [rbp+57h+arg_18], 0
0x180078214  jz      short loc_18007824E
0x180078216  mov     ecx, [rbp+57h+var_B4]
0x180078219  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180078220  xor     r9d, r9d
0x180078223  mov     r8d, 5E9h
0x180078229  call    FltpDbgStatus
0x18007822e  test    eax, eax
0x180078230  js      short loc_180078244
0x180078232  lea     rdx, FltpTelemetryArrayElementSeparator; ","
0x180078239  mov     rcx, r13; DestinationString
0x18007823c  call    RtlUnicodeStringCatString
0x180078241  mov     [rbp+57h+var_B4], eax
0x180078244  movzx   ecx, [rbp+57h+var_C0]
0x180078248  add     cx, 2
0x18007824c  jmp     short loc_180078256
0x18007824e  movzx   ecx, [rbp+57h+var_C0]
0x180078252  mov     [rbp+57h+arg_18], 1
0x180078256  movzx   eax, word ptr [rbx+8]
0x18007825a  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180078261  add     ax, 20h ; ' '
0x180078265  xor     r9d, r9d
0x180078268  add     cx, ax
0x18007826b  mov     r8d, 608h
0x180078271  mov     [rbp+57h+var_C0], cx
0x180078275  mov     ecx, [rbp+57h+var_B4]
0x180078278  call    FltpDbgStatus
0x18007827d  test    eax, eax
0x18007827f  js      loc_180078312
0x180078285  movzx   eax, word ptr [rbx+8]
0x180078289  lea     r9, FltpTelemetryInstanceInfoFormat; "[\"%wZ\",\"0x%0*X\"]"
0x180078290  movzx   ecx, word ptr [r13+0]
0x180078295  sub     ax, 2
0x180078299  mov     word ptr [rbp+57h+var_78], ax
0x18007829d  xor     edx, edx; RemainingString
0x18007829f  mov     word ptr [rbp+57h+var_78+2], ax
0x1800782a3  mov     r8d, 1100h; dwFlags
0x1800782a9  lea     rax, [rbx+0Ch]
0x1800782ad  mov     [rsp+30h], esi
0x1800782b1  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800782b5  mov     eax, ecx
0x1800782b7  add     rax, [r13+8]
0x1800782bb  mov     [rbp+57h+var_A8.Buffer], rax
0x1800782bf  xor     eax, eax
0x1800782c1  mov     [rbp+57h+var_A8.Length], ax
0x1800782c5  movzx   eax, word ptr [r13+2]
0x1800782ca  sub     ax, cx
0x1800782cd  mov     dword ptr [rsp+100h+ResultLength], 8
0x1800782d5  mov     [rbp+57h+var_A8.MaximumLength], ax
0x1800782d9  lea     rcx, [rbp+57h+var_A8]; DestinationString
0x1800782dd  lea     rax, [rbp+57h+var_78]
0x1800782e1  mov     qword ptr [rsp+100h+Length], rax
0x1800782e6  call    RtlUnicodeStringPrintfEx
0x1800782eb  xor     r9d, r9d
0x1800782ee  mov     [rbp+57h+var_B4], eax
0x1800782f1  mov     r8d, 619h
0x1800782f7  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800782fe  mov     ecx, eax
0x180078300  call    FltpDbgStatus
0x180078305  test    eax, eax
0x180078307  js      short loc_180078312
0x180078309  movzx   eax, [rbp+57h+var_A8.Length]
0x18007830d  add     [r13+0], ax
0x180078312  mov     eax, [rbp+57h+var_B8]
0x180078315  inc     eax
0x180078317  jmp     loc_180078018
0x18007831c  mov     edi, [rbp+57h+var_B4]
0x18007831f  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180078326  mov     ecx, edi
0x180078328  mov     r8d, 628h
0x18007832e  xor     r9d, r9d
0x180078331  call    FltpDbgStatus
0x180078336  test    eax, eax
0x180078338  js      short loc_18007834B
0x18007833a  lea     rdx, FltpTelemetryArrayEnd; "]"
0x180078341  mov     rcx, r13; DestinationString
0x180078344  call    RtlUnicodeStringCatString
0x180078349  mov     edi, eax
0x18007834b  mov     rax, [rbp+57h+arg_10]
0x18007834f  test    rax, rax
0x180078352  jz      short loc_18007835F
0x180078354  movzx   ecx, [rbp+57h+var_C0]
0x180078358  add     cx, 2
0x18007835c  mov     [rax], cx
0x18007835f  mov     r8d, 63Ch
0x180078365  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x18007836c  xor     r9d, r9d
0x18007836f  mov     ecx, edi
0x180078371  call    FltpDbgStatus
0x180078376  mov     esi, edi
0x180078378  mov     rdi, [rsp+0F0h]
0x180078380  test    r14, r14
0x180078383  jz      short loc_180078399
0x180078385  mov     edx, 72744D46h; Tag
0x18007838a  mov     rcx, r14; P
0x18007838d  call    cs:__imp_ExFreePoolWithTag
0x180078394  nop     dword ptr [rax+rax+00h]
0x180078399  test    rbx, rbx
0x18007839c  jz      short loc_1800783B2
0x18007839e  mov     edx, 72744D46h; Tag
0x1800783a3  mov     rcx, rbx; P
0x1800783a6  call    cs:__imp_ExFreePoolWithTag
0x1800783ad  nop     dword ptr [rax+rax+00h]
0x1800783b2  mov     rbx, [rsp+100h+arg_0]
0x1800783ba  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800783be  mov     r15, [rsp+100h+var_30]
0x1800783c6  mov     r14, [rsp+100h+var_28]
0x1800783ce  mov     r13, [rsp+100h+var_20]
0x1800783d6  mov     r12, [rsp+100h+var_18]
0x1800783de  test    rcx, rcx
0x1800783e1  jz      short loc_1800783EF
0x1800783e3  call    cs:__imp_ZwClose
0x1800783ea  nop     dword ptr [rax+rax+00h]
0x1800783ef  mov     eax, esi
0x1800783f1  add     rsp, 0F8h
0x1800783f8  pop     rsi
0x1800783f9  pop     rbp
0x1800783fa  retn
```
