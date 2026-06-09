# NbtReadRegistry

- ea: `0x1400493c4`
- end: `0x140049b96`
- name: `NbtReadRegistry`
- size: `2002`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, _QWORD *)`
- caller_count: `4`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140027200`
- `0x1400471c0`
- `0x140048ac0`
- `0x140053828`

## callees

- `0x140028040`
- `0x1400400a4`
- `0x140040294`
- `0x140042330`
- `0x1400491a0`
- `0x1400493c4`
- `0x140049ba0`
- `0x140049d20`
- `0x14004abd4`
- `0x14004b384`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140049807`
- `ntoskrnl!ZwClose` at `0x140049817`
- `ntoskrnl!ZwClose` at `0x140049827`
- `ntoskrnl!ZwClose` at `0x140049919`
- `ntoskrnl!ZwClose` at `0x140049929`
- `ntoskrnl!ZwClose` at `0x140049939`
- `ntoskrnl!ZwClose` at `0x140049807`
- `ntoskrnl!ZwClose` at `0x140049817`
- `ntoskrnl!ZwClose` at `0x140049827`
- `ntoskrnl!ZwClose` at `0x140049919`
- `ntoskrnl!ZwClose` at `0x140049929`
- `ntoskrnl!ZwClose` at `0x140049939`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049492`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049503`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049782`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400497d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049492`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049503`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049782`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400497d3`
- `ntoskrnl!ZwCreateKey` at `0x140049458`
- `ntoskrnl!ZwCreateKey` at `0x140049458`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140049799`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400497ea`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140049799`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400497ea`
- `ntoskrnl!ZwOpenKey` at `0x1400494c9`
- `ntoskrnl!ZwOpenKey` at `0x14004953a`
- `ntoskrnl!ZwOpenKey` at `0x1400494c9`
- `ntoskrnl!ZwOpenKey` at `0x14004953a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400497b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004987e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004988f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049961`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400497b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004987e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004988f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049961`
- `ntoskrnl!ExAllocatePool2` at `0x140049563`
- `ntoskrnl!ExAllocatePool2` at `0x140049585`
- `ntoskrnl!ExAllocatePool2` at `0x140049563`
- `ntoskrnl!ExAllocatePool2` at `0x140049585`

## string_xrefs

- `0x140049472`: `Linkage`

## pseudocode

```c
__int64 __fastcall NbtReadRegistry(__int64 *a1, __int64 *a2, _QWORD *a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  void *v8; // rbx
  NTSTATUS v9; // ebx
  void *v10; // rbx
  NTSTATUS v11; // ebx
  __int64 Pool2; // rbx
  __int64 v13; // rsi
  int LinkageInformation; // eax
  unsigned int v15; // edi
  bool v16; // r14
  int v17; // eax
  __int16 v18; // cx
  int NameServerAddresses; // eax
  unsigned int i; // ecx
  unsigned __int64 v21; // rax
  __int16 v22; // ax
  __int64 result; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  __int16 v26; // ax
  HANDLE v27; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-69h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES v30; // [rsp+70h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v32; // [rsp+120h] [rbp+67h] BYREF
  ULONG Disposition; // [rsp+128h] [rbp+6Fh] BYREF
  void *KeyHandle; // [rsp+130h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+138h] [rbp+7Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a1 = 0;
  *a2 = 0;
  ObjectAttributes.ObjectName = &stru_1400394D0;
  *a3 = 0;
  v27 = 0;
  Handle = 0;
  KeyHandle = 0;
  Disposition = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  String1 = 0;
  LODWORD(v32) = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (xmmword_140038420 & 2) != 0 )
      WPP_SF_d(1025, 10, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, (unsigned int)v6);
    NbtLogEvent(3221229772LL, v7, 276);
  }
  else
  {
    v8 = KeyHandle;
    DestinationString = 0;
    memset(&v30, 0, 44);
    RtlInitUnicodeString(&DestinationString, L"Linkage");
    v30.Length = 48;
    v30.ObjectName = &DestinationString;
    v30.RootDirectory = v8;
    v30.Attributes = 576;
    *(_OWORD *)&v30.SecurityDescriptor = 0;
    v9 = ZwOpenKey(&v27, 0x20019u, &v30);
    if ( v9 < 0 )
    {
      if ( (xmmword_140038420 & 2) != 0 )
        WPP_SF_d(1025, 20, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, v7);
      NbtLogEvent(3221229785LL, (unsigned int)v9, 288);
    }
    else
    {
      v10 = KeyHandle;
      DestinationString = 0;
      memset(&v30, 0, 44);
      RtlInitUnicodeString(&DestinationString, L"Parameters");
      v30.Length = 48;
      v30.ObjectName = &DestinationString;
      v30.RootDirectory = v10;
      v30.Attributes = 576;
      *(_OWORD *)&v30.SecurityDescriptor = 0;
      v11 = ZwOpenKey(&Handle, 0x20019u, &v30);
      if ( v11 < 0 )
      {
        if ( (xmmword_140038420 & 2) != 0 )
          WPP_SF_d(1025, 19, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, v7);
        NbtLogEvent(3221229773LL, (unsigned int)v11, 281);
      }
      else
      {
        Pool2 = ExAllocatePool2(64, 2072, 892494414);
        if ( Pool2 )
        {
          v13 = ExAllocatePool2(64, 2072, 909271630);
          if ( v13 )
          {
            ReadParameters(&NbtConfig, Handle);
            ReadSmbDeviceInfo(KeyHandle);
            *(_QWORD *)v13 = 0;
            *(_QWORD *)Pool2 = 0;
            LinkageInformation = NbtReadLinkageInformation(L"Bind", v27, (__int64)&v32);
            v15 = LinkageInformation;
            v16 = 1;
            if ( LinkageInformation < 0 )
            {
              if ( (xmmword_140038420 & 2) != 0 )
                WPP_SF_d(1025, 11, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, (unsigned int)LinkageInformation);
              v24 = 277;
              v25 = 3221229786LL;
            }
            else
            {
              if ( (xmmword_140038420 & 8) != 0 )
                WPP_SF_S(1027, 12, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, *(_QWORD *)(Pool2 + 16));
              word_140039508 = v32;
              LODWORD(v32) = 0;
              v17 = NbtReadLinkageInformation(L"Export", v27, (__int64)&v32);
              v15 = v17;
              if ( v17 >= 0 )
              {
                v18 = v32;
                if ( (unsigned __int16)word_140039508 > (unsigned int)v32 )
                  word_140039508 = v32;
                else
                  v18 = word_140039508;
                if ( !v18 && (byte_140038418 & 8) != 0 )
                  WPP_SF_(771, 13, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids);
                if ( !word_140039508 )
                  goto LABEL_24;
                if ( (xmmword_140038420 & 8) != 0 )
                  WPP_SF_S(1027, 15, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, *(_QWORD *)(v13 + 16));
                NameServerAddresses = ReadNameServerAddresses(KeyHandle, Pool2, (unsigned __int16)word_140039508, a3);
                v15 = NameServerAddresses;
                if ( NameServerAddresses >= 0 )
                {
                  if ( (NodeType & 0x1001) != 0 )
                  {
                    for ( i = 0; i < (unsigned __int16)word_140039508; ++i )
                    {
                      v21 = (unsigned __int64)i << 6;
                      if ( *(_DWORD *)(v21 + *a3) != 2130706432 || *(_DWORD *)(v21 + *a3 + 4) != 2130706432 )
                      {
                        NodeType = NodeType & 0x10 | 8;
                        break;
                      }
                    }
                  }
LABEL_24:
                  if ( word_140039508 )
                    goto LABEL_25;
                  goto LABEL_40;
                }
                if ( (NodeType & 1) == 0 )
                  NbtLogEvent(3221229778LL, (unsigned int)NameServerAddresses, 280);
                if ( (xmmword_140038420 & 2) != 0 )
                  WPP_SF_d(1025, 16, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, v15);
LABEL_40:
                if ( *(_QWORD *)Pool2 )
                  ExFreePoolWithTag(*(PVOID *)Pool2, 0);
                ExFreePoolWithTag((PVOID)Pool2, 0);
                if ( *(_QWORD *)v13 )
                  ExFreePoolWithTag(*(PVOID *)v13, 0);
                ExFreePoolWithTag((PVOID)v13, 0);
                v13 = 0;
                word_140039508 = 0;
                Pool2 = 0;
                v15 = 0;
LABEL_25:
                v22 = NodeType & 0xEFFF;
                NodeType = v22;
                if ( (v22 & 1) != 0 && (v22 & 0x10) != 0 )
                {
                  v22 &= ~0x10u;
                  NodeType = v22;
                }
                word_1400395DE = 14;
                if ( (v22 & 0xF) == 1 )
                {
                  word_140039626 = 0;
                }
                else
                {
                  switch ( v22 & 0xF )
                  {
                    case 2:
                      v26 = 0x2000;
                      break;
                    case 4:
                      v26 = 0x4000;
                      break;
                    case 8:
                      v26 = 24576;
                      break;
                    default:
                      goto LABEL_30;
                  }
                  word_140039626 = v26;
                }
LABEL_30:
                if ( (int)ReadElement(Handle, L"TransportBindName", &String1) < 0 )
                {
LABEL_35:
                  StreamsStack = v16;
                  ZwClose(Handle);
                  ZwClose(v27);
                  ZwClose(KeyHandle);
                  result = v15;
                  *a2 = v13;
                  *a1 = Pool2;
                  return result;
                }
                DestinationString = 0;
                if ( qword_1400394E0 )
                {
                  RtlInitUnicodeString(&DestinationString, (PCWSTR)qword_1400394E0);
                  if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
                  {
                    ExFreePoolWithTag(String1.Buffer, 0);
                    String1 = DestinationString;
LABEL_34:
                    RtlInitUnicodeString(&DestinationString, L"\\Device\\Streams\\");
                    v16 = RtlCompareUnicodeString(&String1, &DestinationString, 1u) == 0;
                    goto LABEL_35;
                  }
                  ExFreePoolWithTag(qword_1400394E0, 0);
                }
                qword_1400394E0 = String1.Buffer;
                goto LABEL_34;
              }
              if ( (xmmword_140038420 & 2) != 0 )
                WPP_SF_d(1025, 14, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, (unsigned int)v17);
              v24 = 278;
              v25 = 3221229787LL;
            }
            NbtLogEvent(v25, v15, v24);
            goto LABEL_40;
          }
          if ( (xmmword_140038420 & 2) != 0 )
            WPP_SF_(1025, 17, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids);
          ExFreePoolWithTag((PVOID)Pool2, 0);
        }
        else if ( (xmmword_140038420 & 2) != 0 )
        {
          WPP_SF_(1025, 18, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids);
        }
        ZwClose(Handle);
      }
      ZwClose(v27);
    }
    ZwClose(KeyHandle);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400493c4  push    rbp
0x1400493c6  push    rbx
0x1400493c7  push    rsi
0x1400493c8  push    rdi
0x1400493c9  push    r12
0x1400493cb  push    r13
0x1400493cd  push    r14
0x1400493cf  push    r15
0x1400493d1  lea     rbp, [rsp-1Fh]
0x1400493d6  sub     rsp, 0D8h
0x1400493dd  xor     r14d, r14d
0x1400493e0  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400493e8  xorps   xmm0, xmm0
0x1400493eb  mov     [rcx], r14
0x1400493ee  lea     rax, stru_1400394D0
0x1400493f5  mov     [rdx], r14
0x1400493f8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400493fc  mov     r15, r8
0x1400493ff  lea     rax, [rbp+57h+arg_8]
0x140049403  mov     [r8], r14
0x140049406  mov     [rsp+110h+Disposition], rax; Disposition
0x14004940b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004940f  mov     r12, rdx
0x140049412  mov     [rsp+110h+CreateOptions], r14d; CreateOptions
0x140049417  mov     r13, rcx
0x14004941a  mov     [rsp+110h+Class], r14; Class
0x14004941f  xor     r9d, r9d; TitleIndex
0x140049422  mov     [rbp+57h+var_D0], r14
0x140049426  mov     edx, 20019h; DesiredAccess
0x14004942b  mov     [rbp+57h+Handle], r14
0x14004942f  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140049433  mov     [rbp+57h+KeyHandle], r14
0x140049437  mov     [rbp+57h+arg_8], r14d
0x14004943b  lea     esi, [r14+30h]
0x14004943f  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140049447  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x14004944b  mov     dword ptr [rbp+57h+arg_0], r14d
0x14004944f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x140049453  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140049458  call    cs:__imp_ZwCreateKey
0x14004945f  nop     dword ptr [rax+rax+00h]
0x140049464  mov     edi, eax
0x140049466  test    eax, eax
0x140049468  js      loc_140049987
0x14004946e  mov     rbx, [rbp+57h+KeyHandle]
0x140049472  lea     rdx, aLinkage; "Linkage"
0x140049479  xorps   xmm0, xmm0
0x14004947c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140049480  movups  xmmword ptr [rbp+57h+var_A0.ObjectName], xmm0
0x140049484  xor     eax, eax
0x140049486  movups  xmmword ptr [rbp+57h+var_A0+1Ch], xmm0
0x14004948a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004948e  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x140049492  call    cs:__imp_RtlInitUnicodeString
0x140049499  nop     dword ptr [rax+rax+00h]
0x14004949e  lea     rax, [rbp+57h+DestinationString]
0x1400494a2  mov     [rbp+57h+var_A0.Length], esi
0x1400494a5  xorps   xmm0, xmm0
0x1400494a8  mov     [rbp+57h+var_A0.ObjectName], rax
0x1400494ac  lea     r8, [rbp+57h+var_A0]; ObjectAttributes
0x1400494b0  mov     [rbp+57h+var_A0.RootDirectory], rbx
0x1400494b4  mov     edx, 20019h; DesiredAccess
0x1400494b9  mov     [rbp+57h+var_A0.Attributes], 240h
0x1400494c0  lea     rcx, [rbp+57h+var_D0]; KeyHandle
0x1400494c4  movdqu  xmmword ptr [rbp+57h+var_A0.SecurityDescriptor], xmm0
0x1400494c9  call    cs:__imp_ZwOpenKey
0x1400494d0  nop     dword ptr [rax+rax+00h]
0x1400494d5  mov     ebx, eax
0x1400494d7  test    eax, eax
0x1400494d9  js      loc_140049B5D
0x1400494df  mov     rbx, [rbp+57h+KeyHandle]
0x1400494e3  lea     rdx, aParameters; "Parameters"
0x1400494ea  xorps   xmm0, xmm0
0x1400494ed  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400494f1  movups  xmmword ptr [rbp+57h+var_A0.ObjectName], xmm0
0x1400494f5  xor     eax, eax
0x1400494f7  movups  xmmword ptr [rbp+57h+var_A0+1Ch], xmm0
0x1400494fb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400494ff  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x140049503  call    cs:__imp_RtlInitUnicodeString
0x14004950a  nop     dword ptr [rax+rax+00h]
0x14004950f  lea     rax, [rbp+57h+DestinationString]
0x140049513  mov     [rbp+57h+var_A0.Length], esi
0x140049516  xorps   xmm0, xmm0
0x140049519  mov     [rbp+57h+var_A0.ObjectName], rax
0x14004951d  lea     r8, [rbp+57h+var_A0]; ObjectAttributes
0x140049521  mov     [rbp+57h+var_A0.RootDirectory], rbx
0x140049525  mov     edx, 20019h; DesiredAccess
0x14004952a  mov     [rbp+57h+var_A0.Attributes], 240h
0x140049531  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140049535  movdqu  xmmword ptr [rbp+57h+var_A0.SecurityDescriptor], xmm0
0x14004953a  call    cs:__imp_ZwOpenKey
0x140049541  nop     dword ptr [rax+rax+00h]
0x140049546  mov     ebx, eax
0x140049548  test    eax, eax
0x14004954a  js      loc_140049B24
0x140049550  mov     edi, 818h
0x140049555  lea     esi, [r14+40h]
0x140049559  mov     edx, edi
0x14004955b  mov     ecx, esi
0x14004955d  mov     r8d, 3532624Eh
0x140049563  call    cs:__imp_ExAllocatePool2
0x14004956a  nop     dword ptr [rax+rax+00h]
0x14004956f  mov     rbx, rax
0x140049572  test    rax, rax
0x140049575  jz      loc_140049908
0x14004957b  mov     r8d, 3632624Eh
0x140049581  mov     edx, edi
0x140049583  mov     ecx, esi
0x140049585  call    cs:__imp_ExAllocatePool2
0x14004958c  nop     dword ptr [rax+rax+00h]
0x140049591  mov     rsi, rax
0x140049594  test    rax, rax
0x140049597  jz      loc_14004994F
0x14004959d  mov     rdx, [rbp+57h+Handle]
0x1400495a1  lea     rcx, NbtConfig
0x1400495a8  call    ReadParameters
0x1400495ad  mov     rcx, [rbp+57h+KeyHandle]
0x1400495b1  call    ReadSmbDeviceInfo
0x1400495b6  mov     [rsi], r14
0x1400495b9  lea     rax, [rbp+57h+arg_0]
0x1400495bd  mov     [rbx], r14
0x1400495c0  lea     rcx, aBind; "Bind"
0x1400495c7  mov     rdx, [rbp+57h+var_D0]; KeyHandle
0x1400495cb  mov     r9, rbx
0x1400495ce  mov     [rsp+110h+Class], rax; __int64
0x1400495d3  call    NbtReadLinkageInformation
0x1400495d8  mov     edi, eax
0x1400495da  mov     r14d, 1
0x1400495e0  test    eax, eax
0x1400495e2  js      loc_140049852
0x1400495e8  test    byte ptr cs:xmmword_140038420, 8
0x1400495ef  jnz     loc_1400499DB
0x1400495f5  movzx   eax, word ptr [rbp+57h+arg_0]
0x1400495f9  lea     rcx, aExport; "Export"
0x140049600  mov     rdx, [rbp+57h+var_D0]; KeyHandle
0x140049604  mov     r9, rsi
0x140049607  mov     cs:word_140039508, ax
0x14004960e  lea     rax, [rbp+57h+arg_0]
0x140049612  mov     [rsp+110h+Class], rax; __int64
0x140049617  mov     dword ptr [rbp+57h+arg_0], 0
0x14004961e  call    NbtReadLinkageInformation
0x140049623  xor     r8d, r8d
0x140049626  mov     edi, eax
0x140049628  test    eax, eax
0x14004962a  js      loc_140049A96
0x140049630  movzx   edx, cs:word_140039508
0x140049637  mov     ecx, dword ptr [rbp+57h+arg_0]
0x14004963a  cmp     edx, ecx
0x14004963c  ja      loc_1400499FA
0x140049642  movzx   ecx, dx
0x140049645  mov     cs:word_140039508, dx
0x14004964c  test    cx, cx
0x14004964f  jz      loc_140049A06
0x140049655  cmp     cs:word_140039508, r8w
0x14004965d  jz      loc_1400496E5
0x140049663  test    byte ptr cs:xmmword_140038420, 8
0x14004966a  jnz     loc_140049A31
0x140049670  movzx   r8d, cs:word_140039508
0x140049678  mov     r9, r15
0x14004967b  mov     rcx, [rbp+57h+KeyHandle]
0x14004967f  mov     rdx, rbx
0x140049682  call    ReadNameServerAddresses
0x140049687  xor     edx, edx
0x140049689  mov     edi, eax
0x14004968b  test    eax, eax
0x14004968d  js      loc_140049A50
0x140049693  mov     ecx, 1001h
0x140049698  test    cs:NodeType, cx
0x14004969f  jz      short loc_1400496E5
0x1400496a1  mov     ecx, edx
0x1400496a3  mov     r8d, 7F000000h
0x1400496a9  movzx   eax, cs:word_140039508
0x1400496b0  cmp     ecx, eax
0x1400496b2  jnb     short loc_1400496E5
0x1400496b4  mov     rdx, [r15]
0x1400496b7  mov     eax, ecx
0x1400496b9  shl     rax, 6
0x1400496bd  cmp     [rax+rdx], r8d
0x1400496c1  jnz     short loc_1400496CF
0x1400496c3  cmp     [rax+rdx+4], r8d
0x1400496c8  jnz     short loc_1400496CF
0x1400496ca  add     ecx, r14d
0x1400496cd  jmp     short loc_1400496A9
0x1400496cf  movzx   eax, cs:NodeType
0x1400496d6  and     ax, 10h
0x1400496da  or      ax, 8
0x1400496de  mov     cs:NodeType, ax
0x1400496e5  xor     r15d, r15d
0x1400496e8  cmp     r15w, cs:word_140039508
0x1400496f0  jz      loc_140049874
0x1400496f6  movzx   eax, cs:NodeType
0x1400496fd  mov     ecx, 0EFFFh
0x140049702  and     ax, cx
0x140049705  mov     cs:NodeType, ax
0x14004970c  test    r14b, al
0x14004970f  jnz     loc_140049AC8
0x140049715  mov     ecx, 0Eh
0x14004971a  mov     cs:word_1400395DE, cx
0x140049721  movzx   ecx, ax
0x140049724  and     ecx, 0Fh
0x140049727  sub     ecx, r14d
0x14004972a  jz      loc_1400498D8
0x140049730  sub     ecx, r14d
0x140049733  jz      loc_140049AE4
0x140049739  sub     ecx, 2
0x14004973c  jz      loc_140049980
0x140049742  cmp     ecx, 4
0x140049745  jz      loc_14004996F
0x14004974b  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14004974f  lea     r8, [rbp+57h+String1]; ValueName
0x140049753  lea     rdx, aTransportbindn; "TransportBindName"
0x14004975a  call    ReadElement
0x14004975f  test    eax, eax
0x140049761  js      loc_1400497FC
0x140049767  mov     rdx, cs:qword_1400394E0; SourceString
0x14004976e  xorps   xmm0, xmm0
0x140049771  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140049775  test    rdx, rdx
0x140049778  jz      loc_1400498F8
0x14004977e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140049782  call    cs:__imp_RtlInitUnicodeString
0x140049789  nop     dword ptr [rax+rax+00h]
0x14004978e  mov     r8b, r14b; CaseInSensitive
0x140049791  lea     rdx, [rbp+57h+DestinationString]; String2
0x140049795  lea     rcx, [rbp+57h+String1]; String1
0x140049799  call    cs:__imp_RtlCompareUnicodeString
0x1400497a0  nop     dword ptr [rax+rax+00h]
0x1400497a5  xor     edx, edx; Tag
0x1400497a7  test    eax, eax
0x1400497a9  jnz     loc_1400498E5
0x1400497af  mov     rcx, [rbp+57h+String1.Buffer]; P
0x1400497b3  call    cs:__imp_ExFreePoolWithTag
0x1400497ba  nop     dword ptr [rax+rax+00h]
0x1400497bf  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1400497c3  movdqa  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1400497c8  lea     rdx, aDeviceStreams; "\\Device\\Streams\\"
0x1400497cf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400497d3  call    cs:__imp_RtlInitUnicodeString
0x1400497da  nop     dword ptr [rax+rax+00h]
0x1400497df  mov     r8b, r14b; CaseInSensitive
0x1400497e2  lea     rdx, [rbp+57h+DestinationString]; String2
0x1400497e6  lea     rcx, [rbp+57h+String1]; String1
0x1400497ea  call    cs:__imp_RtlCompareUnicodeString
0x1400497f1  nop     dword ptr [rax+rax+00h]
0x1400497f6  test    eax, eax
0x1400497f8  setz    r14b
0x1400497fc  mov     rcx, [rbp+57h+Handle]; Handle
0x140049800  mov     cs:StreamsStack, r14b
0x140049807  call    cs:__imp_ZwClose
0x14004980e  nop     dword ptr [rax+rax+00h]
0x140049813  mov     rcx, [rbp+57h+var_D0]; Handle
0x140049817  call    cs:__imp_ZwClose
0x14004981e  nop     dword ptr [rax+rax+00h]
0x140049823  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140049827  call    cs:__imp_ZwClose
0x14004982e  nop     dword ptr [rax+rax+00h]
0x140049833  mov     eax, edi
0x140049835  mov     [r12], rsi
0x140049839  mov     [r13+0], rbx
0x14004983d  add     rsp, 0D8h
0x140049844  pop     r15
0x140049846  pop     r14
0x140049848  pop     r13
0x14004984a  pop     r12
0x14004984c  pop     rdi
0x14004984d  pop     rsi
0x14004984e  pop     rbx
0x14004984f  pop     rbp
0x140049850  retn
0x140049852  test    byte ptr cs:xmmword_140038420, 2
0x140049859  jnz     loc_1400499BD
0x14004985f  mov     r8d, 115h
0x140049865  mov     ecx, 0C00010DAh
0x14004986a  mov     edx, edi
0x14004986c  call    NbtLogEvent
0x140049871  xor     r15d, r15d
0x140049874  mov     rcx, [rbx]; P
0x140049877  test    rcx, rcx
0x14004987a  jz      short loc_14004988A
0x14004987c  xor     edx, edx; Tag
0x14004987e  call    cs:__imp_ExFreePoolWithTag
0x140049885  nop     dword ptr [rax+rax+00h]
0x14004988a  xor     edx, edx; Tag
0x14004988c  mov     rcx, rbx; P
0x14004988f  call    cs:__imp_ExFreePoolWithTag
0x140049896  nop     dword ptr [rax+rax+00h]
0x14004989b  mov     rcx, [rsi]; P
0x14004989e  test    rcx, rcx
0x1400498a1  jz      short loc_1400498B1
0x1400498a3  xor     edx, edx; Tag
0x1400498a5  call    cs:__imp_ExFreePoolWithTag
0x1400498ac  nop     dword ptr [rax+rax+00h]
0x1400498b1  xor     edx, edx; Tag
0x1400498b3  mov     rcx, rsi; P
0x1400498b6  call    cs:__imp_ExFreePoolWithTag
0x1400498bd  nop     dword ptr [rax+rax+00h]
0x1400498c2  mov     rsi, r15
0x1400498c5  mov     cs:word_140039508, r15w
0x1400498cd  mov     rbx, r15
  ... truncated ...
```
