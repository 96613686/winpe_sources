# CmpInitializeRegistryNode

- ea: `0x14080146c`
- end: `0x1408017e6`
- name: `CmpInitializeRegistryNode`
- size: `890`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1407fb2fc`
- `0x140c8fb38`

## callees

- `0x1403f2d50`
- `0x140421c80`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dac30`
- `0x1406db490`
- `0x1406f4480`
- `0x14080146c`
- `0x1408eeff0`
- `0x140935ee0`
- `0x140937cb0`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x140801611`: `Component Information`
- `0x1408016d8`: `Configuration Data`

## pseudocode

```c
NTSTATUS __fastcall CmpInitializeRegistryNode(__int64 a1, void *a2, HANDLE *a3, int a4, int a5, __int64 a6)
{
  int *v6; // rbx
  UNICODE_STRING *v10; // rax
  NTSTATUS result; // eax
  __int64 v12; // rax
  unsigned __int16 v13; // dx
  HANDLE v14; // rbx
  NTSTATUS v15; // esi
  NTSTATUS v16; // ebx
  ULONG v17; // ebx
  const void *v18; // rdx
  char *Pool2; // rsi
  size_t v20; // r8
  char *v21; // rcx
  _DWORD *v22; // rcx
  PUNICODE_STRING Class; // [rsp+20h] [rbp-C1h]
  HANDLE KeyHandle; // [rsp+40h] [rbp-A1h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-99h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-91h] BYREF
  UNICODE_STRING v27; // [rsp+60h] [rbp-81h] BYREF
  STRING DestinationString; // [rsp+70h] [rbp-71h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-61h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-51h] BYREF
  char SourceString[16]; // [rsp+C0h] [rbp-21h] BYREF
  char v32; // [rsp+D0h] [rbp-11h] BYREF

  v6 = (int *)(a1 + 28);
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v27 = 0;
  KeyHandle = 0;
  ValueName = 0;
  Disposition = 0;
  UnicodeString = 0;
  DestinationString = 0;
  if ( !*(_DWORD *)(a1 + 24) )
    *v6 = 0;
  v10 = (UNICODE_STRING *)((char *)&CmTypeName + 16 * *v6);
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = v10;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( result >= 0 )
  {
    if ( *(_DWORD *)(a1 + 24) )
    {
      v12 = *v6;
      if ( (unsigned int)v12 >= 0x2A )
      {
        v13 = 0;
      }
      else
      {
        v13 = *(_WORD *)(a6 + 2 * v12);
        *(_WORD *)(a6 + 2LL * *v6) = v13 + 1;
      }
      RtlIntegerToChar(v13, 10, 12, SourceString);
      RtlInitAnsiString(&DestinationString, SourceString);
      *(_DWORD *)&v27.Length = 1572864;
      v27.Buffer = (wchar_t *)&v32;
      RtlAnsiStringToUnicodeString(&v27, &DestinationString, 0);
      v14 = KeyHandle;
      ObjectAttributes.ObjectName = &v27;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
      ZwClose(v14);
      if ( v15 < 0 )
        return v15;
    }
    RtlInitUnicodeString(&ValueName, L"Component Information");
    v16 = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, (PVOID)(a1 + 32), 0x10u);
    if ( v16 < 0 )
      goto LABEL_11;
    if ( *(_DWORD *)(a1 + 52) )
    {
      RtlInitUnicodeString(&ValueName, L"Identifier");
      RtlInitAnsiString(&DestinationString, *(PCSZ *)(a1 + 56));
      v16 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
      if ( v16 < 0 )
        goto LABEL_11;
      v16 = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, UnicodeString.Buffer, UnicodeString.Length + 2);
      RtlFreeAnsiString(&UnicodeString);
      if ( v16 < 0 )
        goto LABEL_11;
    }
    v17 = 0;
    RtlInitUnicodeString(&ValueName, L"Configuration Data");
    v18 = *(const void **)(a1 + 64);
    if ( v18 )
    {
      v17 = *(_DWORD *)(a1 + 48) + 8;
      if ( v17 <= CmpConfigurationAreaSize )
      {
        v20 = *(unsigned int *)(a1 + 48);
        v21 = (char *)CmpConfigurationData + 8;
      }
      else
      {
        Pool2 = (char *)ExAllocatePool2(256, v17, 538987843);
        if ( !Pool2 )
        {
          *(_DWORD *)(a1 + 48) = 0;
          *(_QWORD *)(a1 + 64) = 0;
          goto LABEL_22;
        }
        CmpConfigurationAreaSize = v17;
        ExFreePoolWithTag(CmpConfigurationData, 0);
        v20 = *(unsigned int *)(a1 + 48);
        v21 = Pool2 + 8;
        v18 = *(const void **)(a1 + 64);
        CmpConfigurationData = Pool2;
      }
      memmove(v21, v18, v20);
    }
LABEL_22:
    if ( !*(_QWORD *)(a1 + 64) )
    {
      v17 = 16;
      *((_QWORD *)CmpConfigurationData + 1) = 0;
    }
    v22 = CmpConfigurationData;
    Class = (PUNICODE_STRING)CmpConfigurationData;
    *(_DWORD *)CmpConfigurationData = a4;
    v22[1] = a5;
    v16 = ZwSetValueKey(KeyHandle, &ValueName, 0, 9u, Class, v17);
    if ( v16 >= 0 )
    {
      *a3 = KeyHandle;
      return 0;
    }
LABEL_11:
    ZwClose(KeyHandle);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x14080146c  mov     [rsp-8+arg_18], rbx
0x140801471  push    rbp
0x140801472  push    rsi
0x140801473  push    rdi
0x140801474  push    r12
0x140801476  push    r13
0x140801478  push    r14
0x14080147a  push    r15
0x14080147c  lea     rbp, [rsp-0Fh]
0x140801481  sub     rsp, 0F0h
0x140801488  mov     rax, cs:__security_cookie
0x14080148f  xor     rax, rsp
0x140801492  mov     [rbp+3Fh+var_38], rax
0x140801496  mov     rsi, [rbp+3Fh+arg_28]
0x14080149a  lea     rbx, [rcx+1Ch]
0x14080149e  xor     r12d, r12d
0x1408014a1  xorps   xmm0, xmm0
0x1408014a4  xorps   xmm1, xmm1
0x1408014a7  mov     r15d, r9d
0x1408014aa  mov     r14, r8
0x1408014ad  mov     rdi, rcx
0x1408014b0  mov     dword ptr [rbp+3Fh+ObjectAttributes+4], r12d
0x1408014b4  mov     dword ptr [rbp+3Fh+ObjectAttributes+1Ch], r12d
0x1408014b8  movups  xmmword ptr [rsp+120h+var_C0.Length], xmm0
0x1408014bd  mov     [rsp+120h+KeyHandle], r12
0x1408014c2  movups  xmmword ptr [rsp+120h+ValueName.Length], xmm1
0x1408014c7  mov     [rsp+120h+var_D8], r12d
0x1408014cc  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm0
0x1408014d0  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x1408014d4  cmp     [rcx+18h], r12d
0x1408014d8  jnz     short loc_1408014DD
0x1408014da  mov     [rbx], r12d
0x1408014dd  movsxd  rax, dword ptr [rbx]
0x1408014e0  lea     rcx, CmTypeName
0x1408014e7  shl     rax, 4
0x1408014eb  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1408014ef  add     rax, rcx
0x1408014f2  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rdx
0x1408014f6  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x1408014fa  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1408014ff  lea     rax, [rsp+120h+var_D8]
0x140801504  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14080150b  mov     [rsp+120h+Disposition], rax; Disposition
0x140801510  xor     r9d, r9d; TitleIndex
0x140801513  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x140801518  mov     edx, 2001Fh; DesiredAccess
0x14080151d  mov     [rsp+120h+Class], r12; Class
0x140801522  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x140801529  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14080152e  call    ZwCreateKey
0x140801533  test    eax, eax
0x140801535  js      loc_1408017BE
0x14080153b  mov     r13d, 1
0x140801541  cmp     [rdi+18h], r12d
0x140801545  jz      loc_140801611
0x14080154b  movsxd  rax, dword ptr [rbx]
0x14080154e  cmp     eax, 2Ah ; '*'
0x140801551  jnb     short loc_140801564
0x140801553  movzx   edx, word ptr [rsi+rax*2]
0x140801557  mov     rcx, rax
0x14080155a  lea     eax, [rdx+r13]
0x14080155e  mov     [rsi+rcx*2], ax
0x140801562  jmp     short loc_140801567
0x140801564  mov     edx, r12d
0x140801567  movzx   ecx, dx
0x14080156a  lea     r9, [rbp+3Fh+SourceString]
0x14080156e  mov     edx, 0Ah
0x140801573  lea     r8d, [rdx+2]
0x140801577  call    RtlIntegerToChar
0x14080157c  lea     rdx, [rbp+3Fh+SourceString]; SourceString
0x140801580  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140801584  call    RtlInitAnsiString
0x140801589  lea     rax, [rbp+3Fh+var_50]
0x14080158d  mov     dword ptr [rsp+120h+var_C0.Length], 180000h
0x140801595  xor     r8d, r8d; AllocateDestinationString
0x140801598  mov     [rbp+3Fh+var_C0.Buffer], rax
0x14080159c  lea     rdx, [rbp+3Fh+DestinationString]; SourceString
0x1408015a0  lea     rcx, [rsp+120h+var_C0]; DestinationString
0x1408015a5  call    RtlAnsiStringToUnicodeString
0x1408015aa  mov     rbx, [rsp+120h+KeyHandle]
0x1408015af  lea     rax, [rsp+120h+var_C0]
0x1408015b4  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x1408015b8  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1408015bc  lea     rax, [rsp+120h+var_D8]
0x1408015c1  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1408015c8  mov     [rsp+120h+Disposition], rax; Disposition
0x1408015cd  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1408015d2  xorps   xmm0, xmm0
0x1408015d5  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x1408015da  xor     r9d, r9d; TitleIndex
0x1408015dd  mov     [rsp+120h+Class], r12; Class
0x1408015e2  mov     edx, 2001Fh; DesiredAccess
0x1408015e7  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x1408015eb  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1408015f2  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1408015f7  call    ZwCreateKey
0x1408015fc  mov     rcx, rbx; Handle
0x1408015ff  mov     esi, eax
0x140801601  call    ZwClose
0x140801606  test    esi, esi
0x140801608  jns     short loc_140801611
0x14080160a  mov     eax, esi
0x14080160c  jmp     loc_1408017BE
0x140801611  lea     rdx, aComponentInfor; "Component Information"
0x140801618  lea     rcx, [rsp+120h+ValueName]; DestinationString
0x14080161d  call    RtlInitUnicodeString
0x140801622  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140801627  lea     rax, [rdi+20h]
0x14080162b  mov     [rsp+120h+CreateOptions], 10h; DataSize
0x140801633  lea     rdx, [rsp+120h+ValueName]; ValueName
0x140801638  mov     r9d, 3; Type
0x14080163e  mov     [rsp+120h+Class], rax; Data
0x140801643  xor     r8d, r8d; TitleIndex
0x140801646  call    ZwSetValueKey
0x14080164b  mov     ebx, eax
0x14080164d  test    eax, eax
0x14080164f  jns     short loc_140801662
0x140801651  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140801656  call    ZwClose
0x14080165b  mov     eax, ebx
0x14080165d  jmp     loc_1408017BE
0x140801662  cmp     [rdi+34h], r12d
0x140801666  jz      short loc_1408016D8
0x140801668  lea     rdx, aIdentifier; "Identifier"
0x14080166f  lea     rcx, [rsp+120h+ValueName]; DestinationString
0x140801674  call    RtlInitUnicodeString
0x140801679  mov     rdx, [rdi+38h]; SourceString
0x14080167d  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140801681  call    RtlInitAnsiString
0x140801686  mov     r8b, r13b; AllocateDestinationString
0x140801689  lea     rdx, [rbp+3Fh+DestinationString]; SourceString
0x14080168d  lea     rcx, [rbp+3Fh+UnicodeString]; DestinationString
0x140801691  call    RtlAnsiStringToUnicodeString
0x140801696  mov     ebx, eax
0x140801698  test    eax, eax
0x14080169a  js      short loc_140801651
0x14080169c  movzx   eax, [rbp+3Fh+UnicodeString.Length]
0x1408016a0  lea     rdx, [rsp+120h+ValueName]; ValueName
0x1408016a5  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1408016aa  add     eax, 2
0x1408016ad  mov     [rsp+120h+CreateOptions], eax; DataSize
0x1408016b1  mov     r9d, r13d; Type
0x1408016b4  mov     rax, [rbp+3Fh+UnicodeString.Buffer]
0x1408016b8  xor     r8d, r8d; TitleIndex
0x1408016bb  mov     [rsp+120h+Class], rax; Data
0x1408016c0  call    ZwSetValueKey
0x1408016c5  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x1408016c9  mov     ebx, eax
0x1408016cb  call    RtlFreeAnsiString
0x1408016d0  test    ebx, ebx
0x1408016d2  js      loc_140801651
0x1408016d8  lea     rdx, aConfigurationD; "Configuration Data"
0x1408016df  mov     ebx, r12d
0x1408016e2  lea     rcx, [rsp+120h+ValueName]; DestinationString
0x1408016e7  call    RtlInitUnicodeString
0x1408016ec  mov     rdx, [rdi+40h]; Src
0x1408016f0  test    rdx, rdx
0x1408016f3  jz      short loc_140801763
0x1408016f5  mov     eax, [rdi+30h]
0x1408016f8  lea     ebx, [rax+8]
0x1408016fb  cmp     ebx, cs:CmpConfigurationAreaSize
0x140801701  jbe     short loc_140801750
0x140801703  mov     edx, ebx
0x140801705  mov     ecx, 100h
0x14080170a  mov     r8d, 20204D43h
0x140801710  call    ExAllocatePool2
0x140801715  mov     rsi, rax
0x140801718  test    rax, rax
0x14080171b  jz      short loc_140801746
0x14080171d  mov     rcx, cs:CmpConfigurationData; P
0x140801724  xor     edx, edx; Tag
0x140801726  mov     cs:CmpConfigurationAreaSize, ebx
0x14080172c  call    ExFreePoolWithTag
0x140801731  mov     r8d, [rdi+30h]
0x140801735  lea     rcx, [rsi+8]
0x140801739  mov     rdx, [rdi+40h]
0x14080173d  mov     cs:CmpConfigurationData, rsi
0x140801744  jmp     short loc_14080175E
0x140801746  mov     [rdi+30h], r12d
0x14080174a  mov     [rdi+40h], r12
0x14080174e  jmp     short loc_140801763
0x140801750  mov     rcx, cs:CmpConfigurationData
0x140801757  mov     r8, rax; Size
0x14080175a  add     rcx, 8; void *
0x14080175e  call    memmove
0x140801763  cmp     [rdi+40h], r12
0x140801767  jnz     short loc_140801779
0x140801769  mov     rcx, cs:CmpConfigurationData
0x140801770  mov     ebx, 10h
0x140801775  mov     [rcx+8], r12
0x140801779  mov     rcx, cs:CmpConfigurationData
0x140801780  lea     rdx, [rsp+120h+ValueName]; ValueName
0x140801785  mov     eax, [rbp+3Fh+arg_20]
0x140801788  mov     r9d, 9; Type
0x14080178e  mov     [rsp+120h+CreateOptions], ebx; DataSize
0x140801792  xor     r8d, r8d; TitleIndex
0x140801795  mov     [rsp+120h+Class], rcx; Data
0x14080179a  mov     [rcx], r15d
0x14080179d  mov     [rcx+4], eax
0x1408017a0  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1408017a5  call    ZwSetValueKey
0x1408017aa  mov     ebx, eax
0x1408017ac  test    eax, eax
0x1408017ae  js      loc_140801651
0x1408017b4  mov     rax, [rsp+120h+KeyHandle]
0x1408017b9  mov     [r14], rax
0x1408017bc  xor     eax, eax
0x1408017be  mov     rcx, [rbp+3Fh+var_38]
0x1408017c2  xor     rcx, rsp; StackCookie
0x1408017c5  call    __security_check_cookie
0x1408017ca  mov     rbx, [rsp+120h+arg_18]
0x1408017d2  add     rsp, 0F0h
0x1408017d9  pop     r15
0x1408017db  pop     r14
0x1408017dd  pop     r13
0x1408017df  pop     r12
0x1408017e1  pop     rdi
0x1408017e2  pop     rsi
0x1408017e3  pop     rbp
0x1408017e4  retn
```
