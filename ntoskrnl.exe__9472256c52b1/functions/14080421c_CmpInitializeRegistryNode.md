# CmpInitializeRegistryNode

- ea: `0x14080421c`
- end: `0x140804596`
- name: `CmpInitializeRegistryNode`
- size: `890`
- prototype: `NTSTATUS __fastcall(__int64, void *, HANDLE *, int, int, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1407fe0fc`
- `0x140c929bc`

## callees

- `0x140403380`
- `0x140439450`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x1406f6f80`
- `0x14080421c`
- `0x14092e000`
- `0x14092fdd0`
- `0x14094b120`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140804488`: `Configuration Data`
- `0x1408043c1`: `Component Information`

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
  v10 = (UNICODE_STRING *)&CmTypeName[2 * *v6];
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
      RtlIntegerToChar(v13, 0xAu, 12, SourceString);
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
0x14080421c  mov     [rsp-8+arg_18], rbx
0x140804221  push    rbp
0x140804222  push    rsi
0x140804223  push    rdi
0x140804224  push    r12
0x140804226  push    r13
0x140804228  push    r14
0x14080422a  push    r15
0x14080422c  lea     rbp, [rsp-0Fh]
0x140804231  sub     rsp, 0F0h
0x140804238  mov     rax, cs:__security_cookie
0x14080423f  xor     rax, rsp
0x140804242  mov     [rbp+3Fh+var_38], rax
0x140804246  mov     rsi, [rbp+3Fh+arg_28]
0x14080424a  lea     rbx, [rcx+1Ch]
0x14080424e  xor     r12d, r12d
0x140804251  xorps   xmm0, xmm0
0x140804254  xorps   xmm1, xmm1
0x140804257  mov     r15d, r9d
0x14080425a  mov     r14, r8
0x14080425d  mov     rdi, rcx
0x140804260  mov     dword ptr [rbp+3Fh+ObjectAttributes+4], r12d
0x140804264  mov     dword ptr [rbp+3Fh+ObjectAttributes+1Ch], r12d
0x140804268  movups  xmmword ptr [rsp+120h+var_C0.Length], xmm0
0x14080426d  mov     [rsp+120h+KeyHandle], r12
0x140804272  movups  xmmword ptr [rsp+120h+ValueName.Length], xmm1
0x140804277  mov     [rsp+120h+var_D8], r12d
0x14080427c  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm0
0x140804280  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x140804284  cmp     [rcx+18h], r12d
0x140804288  jnz     short loc_14080428D
0x14080428a  mov     [rbx], r12d
0x14080428d  movsxd  rax, dword ptr [rbx]
0x140804290  lea     rcx, CmTypeName
0x140804297  shl     rax, 4
0x14080429b  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14080429f  add     rax, rcx
0x1408042a2  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rdx
0x1408042a6  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x1408042aa  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1408042af  lea     rax, [rsp+120h+var_D8]
0x1408042b4  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1408042bb  mov     [rsp+120h+Disposition], rax; Disposition
0x1408042c0  xor     r9d, r9d; TitleIndex
0x1408042c3  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x1408042c8  mov     edx, 2001Fh; DesiredAccess
0x1408042cd  mov     [rsp+120h+Class], r12; Class
0x1408042d2  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1408042d9  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1408042de  call    ZwCreateKey
0x1408042e3  test    eax, eax
0x1408042e5  js      loc_14080456E
0x1408042eb  mov     r13d, 1
0x1408042f1  cmp     [rdi+18h], r12d
0x1408042f5  jz      loc_1408043C1
0x1408042fb  movsxd  rax, dword ptr [rbx]
0x1408042fe  cmp     eax, 2Ah ; '*'
0x140804301  jnb     short loc_140804314
0x140804303  movzx   edx, word ptr [rsi+rax*2]
0x140804307  mov     rcx, rax
0x14080430a  lea     eax, [rdx+r13]
0x14080430e  mov     [rsi+rcx*2], ax
0x140804312  jmp     short loc_140804317
0x140804314  mov     edx, r12d
0x140804317  movzx   ecx, dx
0x14080431a  lea     r9, [rbp+3Fh+SourceString]
0x14080431e  mov     edx, 0Ah
0x140804323  lea     r8d, [rdx+2]
0x140804327  call    RtlIntegerToChar
0x14080432c  lea     rdx, [rbp+3Fh+SourceString]; SourceString
0x140804330  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140804334  call    RtlInitAnsiString
0x140804339  lea     rax, [rbp+3Fh+var_50]
0x14080433d  mov     dword ptr [rsp+120h+var_C0.Length], 180000h
0x140804345  xor     r8d, r8d; AllocateDestinationString
0x140804348  mov     [rbp+3Fh+var_C0.Buffer], rax
0x14080434c  lea     rdx, [rbp+3Fh+DestinationString]; SourceString
0x140804350  lea     rcx, [rsp+120h+var_C0]; DestinationString
0x140804355  call    RtlAnsiStringToUnicodeString
0x14080435a  mov     rbx, [rsp+120h+KeyHandle]
0x14080435f  lea     rax, [rsp+120h+var_C0]
0x140804364  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140804368  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14080436c  lea     rax, [rsp+120h+var_D8]
0x140804371  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140804378  mov     [rsp+120h+Disposition], rax; Disposition
0x14080437d  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140804382  xorps   xmm0, xmm0
0x140804385  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x14080438a  xor     r9d, r9d; TitleIndex
0x14080438d  mov     [rsp+120h+Class], r12; Class
0x140804392  mov     edx, 2001Fh; DesiredAccess
0x140804397  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x14080439b  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1408043a2  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1408043a7  call    ZwCreateKey
0x1408043ac  mov     rcx, rbx; Handle
0x1408043af  mov     esi, eax
0x1408043b1  call    ZwClose
0x1408043b6  test    esi, esi
0x1408043b8  jns     short loc_1408043C1
0x1408043ba  mov     eax, esi
0x1408043bc  jmp     loc_14080456E
0x1408043c1  lea     rdx, aComponentInfor; "Component Information"
0x1408043c8  lea     rcx, [rsp+120h+ValueName]; DestinationString
0x1408043cd  call    RtlInitUnicodeString
0x1408043d2  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1408043d7  lea     rax, [rdi+20h]
0x1408043db  mov     [rsp+120h+CreateOptions], 10h; DataSize
0x1408043e3  lea     rdx, [rsp+120h+ValueName]; ValueName
0x1408043e8  mov     r9d, 3; Type
0x1408043ee  mov     [rsp+120h+Class], rax; Data
0x1408043f3  xor     r8d, r8d; TitleIndex
0x1408043f6  call    ZwSetValueKey
0x1408043fb  mov     ebx, eax
0x1408043fd  test    eax, eax
0x1408043ff  jns     short loc_140804412
0x140804401  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140804406  call    ZwClose
0x14080440b  mov     eax, ebx
0x14080440d  jmp     loc_14080456E
0x140804412  cmp     [rdi+34h], r12d
0x140804416  jz      short loc_140804488
0x140804418  lea     rdx, aIdentifier; "Identifier"
0x14080441f  lea     rcx, [rsp+120h+ValueName]; DestinationString
0x140804424  call    RtlInitUnicodeString
0x140804429  mov     rdx, [rdi+38h]; SourceString
0x14080442d  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140804431  call    RtlInitAnsiString
0x140804436  mov     r8b, r13b; AllocateDestinationString
0x140804439  lea     rdx, [rbp+3Fh+DestinationString]; SourceString
0x14080443d  lea     rcx, [rbp+3Fh+UnicodeString]; DestinationString
0x140804441  call    RtlAnsiStringToUnicodeString
0x140804446  mov     ebx, eax
0x140804448  test    eax, eax
0x14080444a  js      short loc_140804401
0x14080444c  movzx   eax, [rbp+3Fh+UnicodeString.Length]
0x140804450  lea     rdx, [rsp+120h+ValueName]; ValueName
0x140804455  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x14080445a  add     eax, 2
0x14080445d  mov     [rsp+120h+CreateOptions], eax; DataSize
0x140804461  mov     r9d, r13d; Type
0x140804464  mov     rax, [rbp+3Fh+UnicodeString.Buffer]
0x140804468  xor     r8d, r8d; TitleIndex
0x14080446b  mov     [rsp+120h+Class], rax; Data
0x140804470  call    ZwSetValueKey
0x140804475  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x140804479  mov     ebx, eax
0x14080447b  call    RtlFreeAnsiString
0x140804480  test    ebx, ebx
0x140804482  js      loc_140804401
0x140804488  lea     rdx, aConfigurationD; "Configuration Data"
0x14080448f  mov     ebx, r12d
0x140804492  lea     rcx, [rsp+120h+ValueName]; DestinationString
0x140804497  call    RtlInitUnicodeString
0x14080449c  mov     rdx, [rdi+40h]; Src
0x1408044a0  test    rdx, rdx
0x1408044a3  jz      short loc_140804513
0x1408044a5  mov     eax, [rdi+30h]
0x1408044a8  lea     ebx, [rax+8]
0x1408044ab  cmp     ebx, cs:CmpConfigurationAreaSize
0x1408044b1  jbe     short loc_140804500
0x1408044b3  mov     edx, ebx
0x1408044b5  mov     ecx, 100h
0x1408044ba  mov     r8d, 20204D43h
0x1408044c0  call    ExAllocatePool2
0x1408044c5  mov     rsi, rax
0x1408044c8  test    rax, rax
0x1408044cb  jz      short loc_1408044F6
0x1408044cd  mov     rcx, cs:CmpConfigurationData; P
0x1408044d4  xor     edx, edx; Tag
0x1408044d6  mov     cs:CmpConfigurationAreaSize, ebx
0x1408044dc  call    ExFreePoolWithTag
0x1408044e1  mov     r8d, [rdi+30h]
0x1408044e5  lea     rcx, [rsi+8]
0x1408044e9  mov     rdx, [rdi+40h]
0x1408044ed  mov     cs:CmpConfigurationData, rsi
0x1408044f4  jmp     short loc_14080450E
0x1408044f6  mov     [rdi+30h], r12d
0x1408044fa  mov     [rdi+40h], r12
0x1408044fe  jmp     short loc_140804513
0x140804500  mov     rcx, cs:CmpConfigurationData
0x140804507  mov     r8, rax; Size
0x14080450a  add     rcx, 8; void *
0x14080450e  call    memmove
0x140804513  cmp     [rdi+40h], r12
0x140804517  jnz     short loc_140804529
0x140804519  mov     rcx, cs:CmpConfigurationData
0x140804520  mov     ebx, 10h
0x140804525  mov     [rcx+8], r12
0x140804529  mov     rcx, cs:CmpConfigurationData
0x140804530  lea     rdx, [rsp+120h+ValueName]; ValueName
0x140804535  mov     eax, [rbp+3Fh+arg_20]
0x140804538  mov     r9d, 9; Type
0x14080453e  mov     [rsp+120h+CreateOptions], ebx; DataSize
0x140804542  xor     r8d, r8d; TitleIndex
0x140804545  mov     [rsp+120h+Class], rcx; Data
0x14080454a  mov     [rcx], r15d
0x14080454d  mov     [rcx+4], eax
0x140804550  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140804555  call    ZwSetValueKey
0x14080455a  mov     ebx, eax
0x14080455c  test    eax, eax
0x14080455e  js      loc_140804401
0x140804564  mov     rax, [rsp+120h+KeyHandle]
0x140804569  mov     [r14], rax
0x14080456c  xor     eax, eax
0x14080456e  mov     rcx, [rbp+3Fh+var_38]
0x140804572  xor     rcx, rsp; StackCookie
0x140804575  call    __security_check_cookie
0x14080457a  mov     rbx, [rsp+120h+arg_18]
0x140804582  add     rsp, 0F0h
0x140804589  pop     r15
0x14080458b  pop     r14
0x14080458d  pop     r13
0x14080458f  pop     r12
0x140804591  pop     rdi
0x140804592  pop     rsi
0x140804593  pop     rbp
0x140804594  retn
```
