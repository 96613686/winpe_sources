# MFGetGRL

- ea: `0x180080d1c`
- end: `0x1800810ad`
- name: `MFGetGRL`
- size: `913`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18007fbd4`
- `0x1800a55e4`

## callees

- `0x18002bef6`
- `0x18002bf20`
- `0x180080b5c`
- `0x180080c98`
- `0x180080d1c`
- `0x1800810d8`
- `0x180081154`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180080dac`
- `ntoskrnl!RtlInitUnicodeString` at `0x180080dac`
- `ntoskrnl!ExAllocatePool2` at `0x180080e33`
- `ntoskrnl!ExAllocatePool2` at `0x180080e63`
- `ntoskrnl!ExAllocatePool2` at `0x180080f37`
- `ntoskrnl!ExAllocatePool2` at `0x180080fbf`
- `ntoskrnl!ExAllocatePool2` at `0x180080e33`
- `ntoskrnl!ExAllocatePool2` at `0x180080e63`
- `ntoskrnl!ExAllocatePool2` at `0x180080f37`
- `ntoskrnl!ExAllocatePool2` at `0x180080fbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180081060`
- `ntoskrnl!ExFreePoolWithTag` at `0x180081076`
- `ntoskrnl!ExFreePoolWithTag` at `0x180081060`
- `ntoskrnl!ExFreePoolWithTag` at `0x180081076`
- `ntoskrnl!ZwOpenFile` at `0x180080dfb`
- `ntoskrnl!ZwOpenFile` at `0x180080dfb`
- `ntoskrnl!ZwClose` at `0x180080ffb`
- `ntoskrnl!ZwClose` at `0x180081033`
- `ntoskrnl!ZwClose` at `0x180080ffb`
- `ntoskrnl!ZwClose` at `0x180081033`

## pseudocode

```c
__int64 __fastcall MFGetGRL(void ***a1, __int64 a2)
{
  WCHAR *v2; // r15
  _DWORD *v3; // r14
  int GRLFileName; // eax
  NTSTATUS v7; // ebx
  void **Pool2; // rax
  void *v9; // rdx
  void *v10; // rbx
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // rdx
  ULONG v16; // edi
  void **v17; // rbx
  void *v18; // rdx
  ULONG v19; // r8d
  void *FileHandle; // [rsp+30h] [rbp-49h] BYREF
  PCWSTR SourceString; // [rsp+38h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  __int64 v26; // [rsp+90h] [rbp+17h] BYREF
  char v27; // [rsp+98h] [rbp+1Fh]

  v2 = 0;
  FileHandle = 0;
  v3 = 0;
  SourceString = 0;
  v26 = 0;
  v27 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !a1 || !a2 )
  {
    v7 = -1073741811;
    goto LABEL_32;
  }
  GRLFileName = GetGRLFileName(&SourceString);
  v2 = (WCHAR *)SourceString;
  v7 = GRLFileName;
  if ( GRLFileName >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 1u, 0x860u);
    if ( v7 >= 0 )
    {
      if ( !FileHandle )
      {
        v7 = -1073741823;
        goto LABEL_36;
      }
      Pool2 = (void **)ExAllocatePool2(256, 16, 1196575819);
      *a1 = Pool2;
      if ( !Pool2 )
        goto LABEL_8;
      *Pool2 = (void *)ExAllocatePool2(256, 88, 1196575819);
      v9 = **a1;
      if ( !v9 )
        goto LABEL_8;
      v7 = ReadFromFile(FileHandle, v9, 0x58u, 0);
      if ( v7 < 0 )
        goto LABEL_32;
      v10 = **a1;
      if ( wcsncmp_0((const wchar_t *)v10, L"MSGRL", 5u) )
        goto LABEL_12;
      if ( *((_WORD *)v10 + 6) > 1u )
      {
        v7 = -1072860821;
        goto LABEL_32;
      }
      if ( !*((_WORD *)v10 + 6) )
      {
        v7 = -1072860833;
        goto LABEL_32;
      }
      v11 = *((_DWORD *)v10 + 14);
      if ( v11 >= 0x58 )
      {
        v12 = *((_DWORD *)v10 + 10);
        v13 = v12 + *((_DWORD *)v10 + 11);
        if ( v13 >= v12 )
        {
          v14 = v13 + *((_DWORD *)v10 + 12);
          if ( v14 >= v13 )
          {
            v15 = v14 + *((_DWORD *)v10 + 13);
            if ( (unsigned int)v15 >= v14 )
            {
              v16 = 20 * v15;
              if ( (unsigned __int64)(20 * v15) <= 0xFFFFFFFF && v16 <= 0x100000 && v16 == v11 - 88 )
              {
                v17 = *a1;
                v17[1] = (void *)ExAllocatePool2(258, v16, 1196575819);
                v18 = (*a1)[1];
                if ( !v18 )
                  goto LABEL_8;
                v7 = ReadFromFile(FileHandle, v18, v16, 0);
                if ( v7 < 0 )
                  goto LABEL_32;
                v26 = 0;
                v27 = 0;
                v7 = ReadFromFile(FileHandle, &v26, 8u, (unsigned int *)**a1 + 20);
                if ( v7 < 0 )
                  goto LABEL_32;
                if ( HIDWORD(v26) <= 0xFFFF8 )
                {
                  v3 = (_DWORD *)ExAllocatePool2(258, HIDWORD(v26) + 8LL, 1196575819);
                  if ( v3 )
                  {
                    *v3 = v26;
                    v19 = HIDWORD(v26);
                    v3[1] = HIDWORD(v26);
                    v7 = ReadFromFile(FileHandle, v3 + 2, v19, 0);
                    ZwClose(FileHandle);
                    FileHandle = 0;
                    if ( v7 < 0 )
                    {
LABEL_36:
                      if ( *a1 )
                        MFFreeGRL(a1);
                      goto LABEL_38;
                    }
                    v7 = VerifyCoreSignature(*a1, v3, a2);
                    goto LABEL_32;
                  }
LABEL_8:
                  v7 = -1073741801;
                  goto LABEL_32;
                }
              }
            }
          }
        }
      }
LABEL_12:
      v7 = -1072860822;
    }
  }
LABEL_32:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v7 < 0 && a1 )
    goto LABEL_36;
LABEL_38:
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180080d1c  mov     [rsp-8+arg_10], rbx
0x180080d21  mov     [rsp-8+arg_18], rsi
0x180080d26  push    rbp
0x180080d27  push    rdi
0x180080d28  push    r12
0x180080d2a  push    r14
0x180080d2c  push    r15
0x180080d2e  lea     rbp, [rsp-37h]
0x180080d33  sub     rsp, 0B0h
0x180080d3a  mov     rax, cs:__security_cookie
0x180080d41  xor     rax, rsp
0x180080d44  mov     [rbp+57h+var_30], rax
0x180080d48  xorps   xmm0, xmm0
0x180080d4b  xor     eax, eax
0x180080d4d  xor     r15d, r15d
0x180080d50  mov     [rbp+57h+FileHandle], rax
0x180080d54  xor     r14d, r14d
0x180080d57  mov     [rbp+57h+SourceString], r15
0x180080d5b  mov     [rbp+57h+var_40], rax
0x180080d5f  mov     r12, rdx
0x180080d62  mov     [rbp+57h+var_38], al
0x180080d65  mov     rsi, rcx
0x180080d68  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180080d6c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180080d70  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180080d74  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180080d78  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180080d7c  test    rcx, rcx
0x180080d7f  jz      loc_180081025
0x180080d85  test    rdx, rdx
0x180080d88  jz      loc_180081025
0x180080d8e  lea     rcx, [rbp+57h+SourceString]
0x180080d92  call    GetGRLFileName
0x180080d97  mov     r15, [rbp+57h+SourceString]
0x180080d9b  mov     ebx, eax
0x180080d9d  test    eax, eax
0x180080d9f  js      loc_18008102A
0x180080da5  mov     rdx, r15; SourceString
0x180080da8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180080dac  call    cs:__imp_RtlInitUnicodeString
0x180080db3  nop     dword ptr [rax+rax+00h]
0x180080db8  lea     rax, [rbp+57h+DestinationString]
0x180080dbc  mov     [rsp+0D0h+OpenOptions], 860h; OpenOptions
0x180080dc4  xorps   xmm0, xmm0
0x180080dc7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180080dcb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180080dcf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180080dd6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180080dda  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180080dde  mov     edx, 80000000h; DesiredAccess
0x180080de3  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180080dea  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180080dee  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x180080df6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180080dfb  call    cs:__imp_ZwOpenFile
0x180080e02  nop     dword ptr [rax+rax+00h]
0x180080e07  mov     ebx, eax
0x180080e09  test    eax, eax
0x180080e0b  js      loc_18008102A
0x180080e11  cmp     [rbp+57h+FileHandle], r14
0x180080e15  jnz     short loc_180080E21
0x180080e17  mov     ebx, 0C0000001h
0x180080e1c  jmp     loc_180081048
0x180080e21  mov     edi, 47524C4Bh
0x180080e26  mov     edx, 10h
0x180080e2b  mov     r8d, edi
0x180080e2e  mov     ecx, 100h
0x180080e33  call    cs:__imp_ExAllocatePool2
0x180080e3a  nop     dword ptr [rax+rax+00h]
0x180080e3f  mov     [rsi], rax
0x180080e42  mov     rbx, rax
0x180080e45  test    rax, rax
0x180080e48  jnz     short loc_180080E54
0x180080e4a  mov     ebx, 0C0000017h
0x180080e4f  jmp     loc_18008102A
0x180080e54  mov     r8d, edi
0x180080e57  mov     ecx, 100h
0x180080e5c  mov     edi, 58h ; 'X'
0x180080e61  mov     edx, edi
0x180080e63  call    cs:__imp_ExAllocatePool2
0x180080e6a  nop     dword ptr [rax+rax+00h]
0x180080e6f  mov     [rbx], rax
0x180080e72  mov     rax, [rsi]
0x180080e75  mov     rdx, [rax]
0x180080e78  test    rdx, rdx
0x180080e7b  jz      short loc_180080E4A
0x180080e7d  mov     rcx, [rbp+57h+FileHandle]
0x180080e81  xor     r9d, r9d
0x180080e84  mov     r8d, edi
0x180080e87  call    ReadFromFile
0x180080e8c  mov     ebx, eax
0x180080e8e  test    eax, eax
0x180080e90  js      loc_18008102A
0x180080e96  mov     rax, [rsi]
0x180080e99  lea     r8d, [rdi-53h]; MaxCount
0x180080e9d  lea     rdx, aMsgrl; "MSGRL"
0x180080ea4  mov     rbx, [rax]
0x180080ea7  mov     rcx, rbx; Str1
0x180080eaa  call    wcsncmp_0
0x180080eaf  test    eax, eax
0x180080eb1  jz      short loc_180080EBD
0x180080eb3  mov     ebx, 0C00D716Ah
0x180080eb8  jmp     loc_18008102A
0x180080ebd  mov     ecx, 1
0x180080ec2  cmp     cx, [rbx+0Ch]
0x180080ec6  jnb     short loc_180080ED2
0x180080ec8  mov     ebx, 0C00D716Bh
0x180080ecd  jmp     loc_18008102A
0x180080ed2  jbe     short loc_180080EDE
0x180080ed4  mov     ebx, 0C00D715Fh
0x180080ed9  jmp     loc_18008102A
0x180080ede  mov     r8d, [rbx+38h]
0x180080ee2  cmp     r8d, edi
0x180080ee5  jb      short loc_180080EB3
0x180080ee7  mov     ecx, [rbx+28h]
0x180080eea  mov     edx, [rbx+2Ch]
0x180080eed  add     edx, ecx
0x180080eef  cmp     edx, ecx
0x180080ef1  jb      short loc_180080EB3
0x180080ef3  mov     ecx, [rbx+30h]
0x180080ef6  add     ecx, edx
0x180080ef8  cmp     ecx, edx
0x180080efa  jb      short loc_180080EB3
0x180080efc  mov     edx, [rbx+34h]
0x180080eff  add     edx, ecx
0x180080f01  cmp     edx, ecx
0x180080f03  jb      short loc_180080EB3
0x180080f05  lea     rdi, [rdx+rdx*4]
0x180080f09  mov     eax, 0FFFFFFFFh
0x180080f0e  shl     rdi, 2
0x180080f12  cmp     rdi, rax
0x180080f15  ja      short loc_180080EB3
0x180080f17  cmp     edi, 100000h
0x180080f1d  ja      short loc_180080EB3
0x180080f1f  lea     eax, [r8-58h]
0x180080f23  cmp     edi, eax
0x180080f25  jnz     short loc_180080EB3
0x180080f27  mov     rbx, [rsi]
0x180080f2a  mov     ecx, 102h
0x180080f2f  mov     edx, edi
0x180080f31  mov     r8d, 47524C4Bh
0x180080f37  call    cs:__imp_ExAllocatePool2
0x180080f3e  nop     dword ptr [rax+rax+00h]
0x180080f43  mov     [rbx+8], rax
0x180080f47  mov     rax, [rsi]
0x180080f4a  mov     rdx, [rax+8]
0x180080f4e  test    rdx, rdx
0x180080f51  jz      loc_180080E4A
0x180080f57  mov     rcx, [rbp+57h+FileHandle]
0x180080f5b  xor     r9d, r9d
0x180080f5e  mov     r8d, edi
0x180080f61  call    ReadFromFile
0x180080f66  mov     ebx, eax
0x180080f68  test    eax, eax
0x180080f6a  js      loc_18008102A
0x180080f70  mov     rcx, [rbp+57h+FileHandle]
0x180080f74  lea     rdx, [rbp+57h+var_40]
0x180080f78  xor     eax, eax
0x180080f7a  mov     r8d, 8
0x180080f80  mov     [rbp+57h+var_40], rax
0x180080f84  mov     [rbp+57h+var_38], al
0x180080f87  mov     rax, [rsi]
0x180080f8a  mov     r9, [rax]
0x180080f8d  add     r9, 50h ; 'P'
0x180080f91  call    ReadFromFile
0x180080f96  mov     ebx, eax
0x180080f98  test    eax, eax
0x180080f9a  js      loc_18008102A
0x180080fa0  cmp     dword ptr [rbp+57h+var_40+4], 0FFFF8h
0x180080fa7  ja      loc_180080EB3
0x180080fad  mov     edx, dword ptr [rbp+57h+var_40+4]
0x180080fb0  mov     ecx, 102h
0x180080fb5  add     rdx, 8
0x180080fb9  mov     r8d, 47524C4Bh
0x180080fbf  call    cs:__imp_ExAllocatePool2
0x180080fc6  nop     dword ptr [rax+rax+00h]
0x180080fcb  mov     r14, rax
0x180080fce  test    rax, rax
0x180080fd1  jz      loc_180080E4A
0x180080fd7  mov     eax, dword ptr [rbp+57h+var_40]
0x180080fda  lea     rdx, [r14+8]
0x180080fde  mov     [r14], eax
0x180080fe1  xor     r9d, r9d
0x180080fe4  mov     r8d, dword ptr [rbp+57h+var_40+4]
0x180080fe8  mov     [r14+4], r8d
0x180080fec  mov     rcx, [rbp+57h+FileHandle]
0x180080ff0  call    ReadFromFile
0x180080ff5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180080ff9  mov     ebx, eax
0x180080ffb  call    cs:__imp_ZwClose
0x180081002  nop     dword ptr [rax+rax+00h]
0x180081007  mov     [rbp+57h+FileHandle], 0
0x18008100f  test    ebx, ebx
0x180081011  js      short loc_180081048
0x180081013  mov     rcx, [rsi]
0x180081016  mov     r8, r12
0x180081019  mov     rdx, r14
0x18008101c  call    VerifyCoreSignature
0x180081021  mov     ebx, eax
0x180081023  jmp     short loc_18008102A
0x180081025  mov     ebx, 0C000000Dh
0x18008102a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18008102e  test    rcx, rcx
0x180081031  jz      short loc_18008103F
0x180081033  call    cs:__imp_ZwClose
0x18008103a  nop     dword ptr [rax+rax+00h]
0x18008103f  test    ebx, ebx
0x180081041  jns     short loc_180081056
0x180081043  test    rsi, rsi
0x180081046  jz      short loc_180081056
0x180081048  cmp     qword ptr [rsi], 0
0x18008104c  jz      short loc_180081056
0x18008104e  mov     rcx, rsi
0x180081051  call    MFFreeGRL
0x180081056  test    r15, r15
0x180081059  jz      short loc_18008106C
0x18008105b  xor     edx, edx; Tag
0x18008105d  mov     rcx, r15; P
0x180081060  call    cs:__imp_ExFreePoolWithTag
0x180081067  nop     dword ptr [rax+rax+00h]
0x18008106c  test    r14, r14
0x18008106f  jz      short loc_180081082
0x180081071  xor     edx, edx; Tag
0x180081073  mov     rcx, r14; P
0x180081076  call    cs:__imp_ExFreePoolWithTag
0x18008107d  nop     dword ptr [rax+rax+00h]
0x180081082  mov     eax, ebx
0x180081084  mov     rcx, [rbp+57h+var_30]
0x180081088  xor     rcx, rsp; StackCookie
0x18008108b  call    __security_check_cookie
0x180081090  lea     r11, [rsp+0D0h+var_20]
0x180081098  mov     rbx, [r11+40h]
0x18008109c  mov     rsi, [r11+48h]
0x1800810a0  mov     rsp, r11
0x1800810a3  pop     r15
0x1800810a5  pop     r14
0x1800810a7  pop     r12
0x1800810a9  pop     rdi
0x1800810aa  pop     rbp
0x1800810ab  retn
```
