# FltpTelemetryEnumerateSerializeFilterRegistryInstances

- ea: `0x180077fe0`
- end: `0x1800784ac`
- name: `FltpTelemetryEnumerateSerializeFilterRegistryInstances`
- size: `1228`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180055154`

## callees

- `0x180009f20`
- `0x18001e410`
- `0x18001e610`
- `0x180077fe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180078145`
- `ntoskrnl!ExFreePoolWithTag` at `0x180078286`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007843d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180078456`
- `ntoskrnl!ExFreePoolWithTag` at `0x180078145`
- `ntoskrnl!ExFreePoolWithTag` at `0x180078286`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007843d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180078456`
- `ntoskrnl!ExAllocatePool2` at `0x18007804b`
- `ntoskrnl!ExAllocatePool2` at `0x18007807f`
- `ntoskrnl!ExAllocatePool2` at `0x180078163`
- `ntoskrnl!ExAllocatePool2` at `0x1800782a2`
- `ntoskrnl!ExAllocatePool2` at `0x18007804b`
- `ntoskrnl!ExAllocatePool2` at `0x18007807f`
- `ntoskrnl!ExAllocatePool2` at `0x180078163`
- `ntoskrnl!ExAllocatePool2` at `0x1800782a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800781e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078236`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800781e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078236`
- `ntoskrnl!ZwClose` at `0x180078493`
- `ntoskrnl!ZwClose` at `0x180078493`
- `ntoskrnl!ZwOpenKey` at `0x1800781c7`
- `ntoskrnl!ZwOpenKey` at `0x1800781c7`
- `ntoskrnl!ZwQueryValueKey` at `0x180078212`
- `ntoskrnl!ZwQueryValueKey` at `0x180078260`
- `ntoskrnl!ZwQueryValueKey` at `0x180078212`
- `ntoskrnl!ZwQueryValueKey` at `0x180078260`
- `ntoskrnl!ZwEnumerateKey` at `0x1800780e4`
- `ntoskrnl!ZwEnumerateKey` at `0x1800780e4`

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
  unsigned int v11; // esi
  unsigned int v12; // esi
  NTSTATUS v13; // eax
  __int16 v14; // cx
  unsigned int v15; // ecx
  unsigned int v16; // edi
  PULONG ResultLength; // [rsp+30h] [rbp-81h]
  __int16 v19; // [rsp+48h] [rbp-69h]
  ULONG v20; // [rsp+4Ch] [rbp-65h] BYREF
  ULONG i; // [rsp+50h] [rbp-61h]
  unsigned int v22; // [rsp+54h] [rbp-5Dh]
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
      if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 1348, 2147483674LL) >= 0 )
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
          if ( (int)FltpDbgStatus(v22, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 1516, 0) >= 0 )
            v22 = RtlUnicodeStringCatString(DestinationString, L",");
          v14 = v19 + 2;
        }
        else
        {
          v14 = v19;
          v30 = 1;
        }
        v19 = *(_WORD *)(v8 + 8) + 32 + v14;
        if ( (int)FltpDbgStatus(v22, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 1547, 0) >= 0 )
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
          if ( (int)FltpDbgStatus(v22, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 1564, 0) >= 0 )
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
    if ( (int)FltpDbgStatus(v22, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 1579, 0) >= 0 )
      v16 = RtlUnicodeStringCatString(DestinationString, L"]");
    if ( a3 )
      *a3 = v19 + 2;
    FltpDbgStatus(v16, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 1599, 0);
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
0x180077fe0  mov     rax, rsp
0x180077fe3  mov     [rax+18h], r8
0x180077fe7  push    rbp
0x180077fe8  push    rsi
0x180077fe9  lea     rbp, [rax-5Fh]
0x180077fed  sub     rsp, 0F8h
0x180077ff4  xorps   xmm0, xmm0
0x180077ff7  mov     [rax-20h], r12
0x180077ffb  mov     [rax-28h], r13
0x180077fff  mov     r12, rcx
0x180078002  mov     [rax-30h], r14
0x180078006  mov     r13, rdx
0x180078009  mov     [rax-38h], r15
0x18007800d  xorps   xmm1, xmm1
0x180078010  xor     esi, esi
0x180078012  mov     r15d, 50h ; 'P'
0x180078018  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18007801c  mov     edx, r15d
0x18007801f  mov     [rbp+57h+var_BC], esi
0x180078022  xor     eax, eax
0x180078024  mov     [rbp+57h+KeyHandle], rsi
0x180078028  mov     r8d, 72744D46h
0x18007802e  mov     ecx, 100h
0x180078033  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180078037  movups  [rbp+57h+var_78], xmm1
0x18007803b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007803f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180078043  movups  [rbp+57h+var_98], xmm0
0x180078047  movups  xmmword ptr [rbp+57h+var_A8.Length], xmm0
0x18007804b  call    cs:__imp_ExAllocatePool2
0x180078052  nop     dword ptr [rax+rax+00h]
0x180078057  mov     r14, rax
0x18007805a  test    rax, rax
0x18007805d  jnz     short loc_180078069
0x18007805f  mov     esi, 0C000009Ah
0x180078064  jmp     loc_18007846A
0x180078069  mov     r8d, 72744D46h
0x18007806f  mov     [rsp+100h+arg_0], rbx
0x180078077  mov     rdx, r15
0x18007807a  mov     ecx, 100h
0x18007807f  call    cs:__imp_ExAllocatePool2
0x180078086  nop     dword ptr [rax+rax+00h]
0x18007808b  mov     rbx, rax
0x18007808e  test    rax, rax
0x180078091  jnz     short loc_18007809D
0x180078093  mov     esi, 0C000009Ah
0x180078098  jmp     loc_180078435
0x18007809d  mov     [rsp+0F0h], rdi
0x1800780a5  lea     rdx, FltpTelemetryArrayStart; "["
0x1800780ac  mov     rcx, r13; DestinationString
0x1800780af  mov     edi, r15d
0x1800780b2  call    RtlUnicodeStringCatString
0x1800780b7  mov     [rbp+57h+var_B4], eax
0x1800780ba  mov     eax, 2
0x1800780bf  mov     [rbp+57h+var_C0], ax
0x1800780c3  mov     eax, esi
0x1800780c5  mov     [rbp+57h+arg_18], al
0x1800780c8  mov     [rbp+57h+var_B8], eax
0x1800780cb  lea     rcx, [rbp+57h+var_BC]
0x1800780cf  mov     r9, r14; KeyInformation
0x1800780d2  mov     [rsp+100h+ResultLength], rcx; ResultLength
0x1800780d7  xor     r8d, r8d; KeyInformationClass
0x1800780da  mov     rcx, r12; KeyHandle
0x1800780dd  mov     [rsp+100h+Length], r15d; Length
0x1800780e2  mov     edx, eax; Index
0x1800780e4  call    cs:__imp_ZwEnumerateKey
0x1800780eb  nop     dword ptr [rax+rax+00h]
0x1800780f0  mov     qword ptr [rsp+30h], 0
0x1800780f9  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180078100  mov     ecx, eax
0x180078102  mov     dword ptr [rsp+100h+ResultLength], 80000005h
0x18007810a  mov     r9d, 8000001Ah
0x180078110  mov     [rsp+100h+Length], 0C0000023h
0x180078118  mov     r8d, 544h
0x18007811e  mov     esi, eax
0x180078120  call    FltpDbgStatus
0x180078125  test    eax, eax
0x180078127  jns     short loc_180078183
0x180078129  cmp     esi, 80000005h
0x18007812f  jz      short loc_18007813D
0x180078131  cmp     esi, 0C0000023h
0x180078137  jnz     loc_1800783CC
0x18007813d  mov     edx, 72744D46h; Tag
0x180078142  mov     rcx, r14; P
0x180078145  call    cs:__imp_ExFreePoolWithTag
0x18007814c  nop     dword ptr [rax+rax+00h]
0x180078151  mov     r15d, [rbp+57h+var_BC]
0x180078155  mov     ecx, 100h
0x18007815a  mov     edx, r15d
0x18007815d  mov     r8d, 72744D46h
0x180078163  call    cs:__imp_ExAllocatePool2
0x18007816a  nop     dword ptr [rax+rax+00h]
0x18007816f  mov     r14, rax
0x180078172  test    rax, rax
0x180078175  jz      loc_1800783CC
0x18007817b  mov     eax, [rbp+57h+var_B8]
0x18007817e  jmp     loc_1800780CB
0x180078183  movzx   eax, word ptr [r14+0Ch]
0x180078188  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007818c  mov     word ptr [rbp+57h+var_98], ax
0x180078190  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180078194  mov     word ptr [rbp+57h+var_98+2], ax
0x180078198  xorps   xmm0, xmm0
0x18007819b  lea     rax, [r14+10h]
0x18007819f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800781a6  mov     qword ptr [rbp+57h+var_98+8], rax
0x1800781aa  mov     edx, 20019h; DesiredAccess
0x1800781af  lea     rax, [rbp+57h+var_98]
0x1800781b3  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1800781b7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800781bb  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800781c2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800781c7  call    cs:__imp_ZwOpenKey
0x1800781ce  nop     dword ptr [rax+rax+00h]
0x1800781d3  mov     esi, eax
0x1800781d5  test    eax, eax
0x1800781d7  js      loc_180078428
0x1800781dd  lea     rdx, FltpRegFlagsValueName; "FLAGS"
0x1800781e4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800781e8  call    cs:__imp_RtlInitUnicodeString
0x1800781ef  nop     dword ptr [rax+rax+00h]
0x1800781f4  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800781f8  lea     rax, [rbp+57h+var_BC]
0x1800781fc  mov     [rsp+100h+ResultLength], rax; ResultLength
0x180078201  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180078205  mov     r9, rbx; KeyValueInformation
0x180078208  mov     [rsp+100h+Length], edi; Length
0x18007820c  mov     r8d, 2; KeyValueInformationClass
0x180078212  call    cs:__imp_ZwQueryValueKey
0x180078219  nop     dword ptr [rax+rax+00h]
0x18007821e  mov     esi, eax
0x180078220  test    eax, eax
0x180078222  js      loc_180078428
0x180078228  mov     esi, [rbx+0Ch]
0x18007822b  lea     rdx, FltpRegAltitudeValueName; "ALTITUDE"
0x180078232  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180078236  call    cs:__imp_RtlInitUnicodeString
0x18007823d  nop     dword ptr [rax+rax+00h]
0x180078242  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180078246  lea     rax, [rbp+57h+var_BC]
0x18007824a  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18007824f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180078253  mov     r9, rbx; KeyValueInformation
0x180078256  mov     [rsp+100h+Length], edi; Length
0x18007825a  mov     r8d, 2; KeyValueInformationClass
0x180078260  call    cs:__imp_ZwQueryValueKey
0x180078267  nop     dword ptr [rax+rax+00h]
0x18007826c  test    eax, eax
0x18007826e  jns     short loc_1800782C0
0x180078270  cmp     eax, 0C0000023h
0x180078275  jz      short loc_18007827E
0x180078277  cmp     eax, 80000005h
0x18007827c  jnz     short loc_180078242
0x18007827e  mov     edx, 72744D46h; Tag
0x180078283  mov     rcx, rbx; P
0x180078286  call    cs:__imp_ExFreePoolWithTag
0x18007828d  nop     dword ptr [rax+rax+00h]
0x180078292  mov     edi, [rbp+57h+var_BC]
0x180078295  mov     ecx, 100h
0x18007829a  mov     edx, edi
0x18007829c  mov     r8d, 72744D46h
0x1800782a2  call    cs:__imp_ExAllocatePool2
0x1800782a9  nop     dword ptr [rax+rax+00h]
0x1800782ae  mov     rbx, rax
0x1800782b1  test    rax, rax
0x1800782b4  jnz     short loc_180078242
0x1800782b6  mov     eax, [rbp+57h+var_B8]
0x1800782b9  inc     eax
0x1800782bb  jmp     loc_1800780C8
0x1800782c0  cmp     [rbp+57h+arg_18], 0
0x1800782c4  jz      short loc_1800782FE
0x1800782c6  mov     ecx, [rbp+57h+var_B4]
0x1800782c9  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800782d0  xor     r9d, r9d
0x1800782d3  mov     r8d, 5ECh
0x1800782d9  call    FltpDbgStatus
0x1800782de  test    eax, eax
0x1800782e0  js      short loc_1800782F4
0x1800782e2  lea     rdx, FltpTelemetryArrayElementSeparator; ","
0x1800782e9  mov     rcx, r13; DestinationString
0x1800782ec  call    RtlUnicodeStringCatString
0x1800782f1  mov     [rbp+57h+var_B4], eax
0x1800782f4  movzx   ecx, [rbp+57h+var_C0]
0x1800782f8  add     cx, 2
0x1800782fc  jmp     short loc_180078306
0x1800782fe  movzx   ecx, [rbp+57h+var_C0]
0x180078302  mov     [rbp+57h+arg_18], 1
0x180078306  movzx   eax, word ptr [rbx+8]
0x18007830a  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180078311  add     ax, 20h ; ' '
0x180078315  xor     r9d, r9d
0x180078318  add     cx, ax
0x18007831b  mov     r8d, 60Bh
0x180078321  mov     [rbp+57h+var_C0], cx
0x180078325  mov     ecx, [rbp+57h+var_B4]
0x180078328  call    FltpDbgStatus
0x18007832d  test    eax, eax
0x18007832f  js      loc_1800783C2
0x180078335  movzx   eax, word ptr [rbx+8]
0x180078339  lea     r9, FltpTelemetryInstanceInfoFormat; "[\"%wZ\",\"0x%0*X\"]"
0x180078340  movzx   ecx, word ptr [r13+0]
0x180078345  sub     ax, 2
0x180078349  mov     word ptr [rbp+57h+var_78], ax
0x18007834d  xor     edx, edx; RemainingString
0x18007834f  mov     word ptr [rbp+57h+var_78+2], ax
0x180078353  mov     r8d, 1100h; dwFlags
0x180078359  lea     rax, [rbx+0Ch]
0x18007835d  mov     [rsp+30h], esi
0x180078361  mov     qword ptr [rbp+57h+var_78+8], rax
0x180078365  mov     eax, ecx
0x180078367  add     rax, [r13+8]
0x18007836b  mov     [rbp+57h+var_A8.Buffer], rax
0x18007836f  xor     eax, eax
0x180078371  mov     [rbp+57h+var_A8.Length], ax
0x180078375  movzx   eax, word ptr [r13+2]
0x18007837a  sub     ax, cx
0x18007837d  mov     dword ptr [rsp+100h+ResultLength], 8
0x180078385  mov     [rbp+57h+var_A8.MaximumLength], ax
0x180078389  lea     rcx, [rbp+57h+var_A8]; DestinationString
0x18007838d  lea     rax, [rbp+57h+var_78]
0x180078391  mov     qword ptr [rsp+100h+Length], rax
0x180078396  call    RtlUnicodeStringPrintfEx
0x18007839b  xor     r9d, r9d
0x18007839e  mov     [rbp+57h+var_B4], eax
0x1800783a1  mov     r8d, 61Ch
0x1800783a7  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800783ae  mov     ecx, eax
0x1800783b0  call    FltpDbgStatus
0x1800783b5  test    eax, eax
0x1800783b7  js      short loc_1800783C2
0x1800783b9  movzx   eax, [rbp+57h+var_A8.Length]
0x1800783bd  add     [r13+0], ax
0x1800783c2  mov     eax, [rbp+57h+var_B8]
0x1800783c5  inc     eax
0x1800783c7  jmp     loc_1800780C8
0x1800783cc  mov     edi, [rbp+57h+var_B4]
0x1800783cf  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800783d6  mov     ecx, edi
0x1800783d8  mov     r8d, 62Bh
0x1800783de  xor     r9d, r9d
0x1800783e1  call    FltpDbgStatus
0x1800783e6  test    eax, eax
0x1800783e8  js      short loc_1800783FB
0x1800783ea  lea     rdx, FltpTelemetryArrayEnd; "]"
0x1800783f1  mov     rcx, r13; DestinationString
0x1800783f4  call    RtlUnicodeStringCatString
0x1800783f9  mov     edi, eax
0x1800783fb  mov     rax, [rbp+57h+arg_10]
0x1800783ff  test    rax, rax
0x180078402  jz      short loc_18007840F
0x180078404  movzx   ecx, [rbp+57h+var_C0]
0x180078408  add     cx, 2
0x18007840c  mov     [rax], cx
0x18007840f  mov     r8d, 63Fh
0x180078415  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x18007841c  xor     r9d, r9d
0x18007841f  mov     ecx, edi
0x180078421  call    FltpDbgStatus
0x180078426  mov     esi, edi
0x180078428  mov     rdi, [rsp+0F0h]
0x180078430  test    r14, r14
0x180078433  jz      short loc_180078449
0x180078435  mov     edx, 72744D46h; Tag
0x18007843a  mov     rcx, r14; P
0x18007843d  call    cs:__imp_ExFreePoolWithTag
0x180078444  nop     dword ptr [rax+rax+00h]
0x180078449  test    rbx, rbx
0x18007844c  jz      short loc_180078462
0x18007844e  mov     edx, 72744D46h; Tag
0x180078453  mov     rcx, rbx; P
0x180078456  call    cs:__imp_ExFreePoolWithTag
0x18007845d  nop     dword ptr [rax+rax+00h]
0x180078462  mov     rbx, [rsp+100h+arg_0]
0x18007846a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18007846e  mov     r15, [rsp+100h+var_30]
0x180078476  mov     r14, [rsp+100h+var_28]
0x18007847e  mov     r13, [rsp+100h+var_20]
0x180078486  mov     r12, [rsp+100h+var_18]
0x18007848e  test    rcx, rcx
0x180078491  jz      short loc_18007849F
0x180078493  call    cs:__imp_ZwClose
0x18007849a  nop     dword ptr [rax+rax+00h]
0x18007849f  mov     eax, esi
0x1800784a1  add     rsp, 0F8h
0x1800784a8  pop     rsi
0x1800784a9  pop     rbp
0x1800784aa  retn
```
