# MFGetGRL

- ea: `0x18007f6f0`
- end: `0x18007fa81`
- name: `MFGetGRL`
- size: `913`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18007e5a8`
- `0x1800a3fb4`

## callees

- `0x18002bec6`
- `0x18002bef0`
- `0x18007f530`
- `0x18007f66c`
- `0x18007f6f0`
- `0x18007faac`
- `0x18007fb28`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007f780`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007f780`
- `ntoskrnl!ExAllocatePool2` at `0x18007f807`
- `ntoskrnl!ExAllocatePool2` at `0x18007f837`
- `ntoskrnl!ExAllocatePool2` at `0x18007f90b`
- `ntoskrnl!ExAllocatePool2` at `0x18007f993`
- `ntoskrnl!ExAllocatePool2` at `0x18007f807`
- `ntoskrnl!ExAllocatePool2` at `0x18007f837`
- `ntoskrnl!ExAllocatePool2` at `0x18007f90b`
- `ntoskrnl!ExAllocatePool2` at `0x18007f993`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007fa34`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007fa4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007fa34`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007fa4a`
- `ntoskrnl!ZwOpenFile` at `0x18007f7cf`
- `ntoskrnl!ZwOpenFile` at `0x18007f7cf`
- `ntoskrnl!ZwClose` at `0x18007f9cf`
- `ntoskrnl!ZwClose` at `0x18007fa07`
- `ntoskrnl!ZwClose` at `0x18007f9cf`
- `ntoskrnl!ZwClose` at `0x18007fa07`

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
0x18007f6f0  mov     [rsp-8+arg_10], rbx
0x18007f6f5  mov     [rsp-8+arg_18], rsi
0x18007f6fa  push    rbp
0x18007f6fb  push    rdi
0x18007f6fc  push    r12
0x18007f6fe  push    r14
0x18007f700  push    r15
0x18007f702  lea     rbp, [rsp-37h]
0x18007f707  sub     rsp, 0B0h
0x18007f70e  mov     rax, cs:__security_cookie
0x18007f715  xor     rax, rsp
0x18007f718  mov     [rbp+57h+var_30], rax
0x18007f71c  xorps   xmm0, xmm0
0x18007f71f  xor     eax, eax
0x18007f721  xor     r15d, r15d
0x18007f724  mov     [rbp+57h+FileHandle], rax
0x18007f728  xor     r14d, r14d
0x18007f72b  mov     [rbp+57h+SourceString], r15
0x18007f72f  mov     [rbp+57h+var_40], rax
0x18007f733  mov     r12, rdx
0x18007f736  mov     [rbp+57h+var_38], al
0x18007f739  mov     rsi, rcx
0x18007f73c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18007f740  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18007f744  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007f748  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007f74c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007f750  test    rcx, rcx
0x18007f753  jz      loc_18007F9F9
0x18007f759  test    rdx, rdx
0x18007f75c  jz      loc_18007F9F9
0x18007f762  lea     rcx, [rbp+57h+SourceString]
0x18007f766  call    GetGRLFileName
0x18007f76b  mov     r15, [rbp+57h+SourceString]
0x18007f76f  mov     ebx, eax
0x18007f771  test    eax, eax
0x18007f773  js      loc_18007F9FE
0x18007f779  mov     rdx, r15; SourceString
0x18007f77c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007f780  call    cs:__imp_RtlInitUnicodeString
0x18007f787  nop     dword ptr [rax+rax+00h]
0x18007f78c  lea     rax, [rbp+57h+DestinationString]
0x18007f790  mov     [rsp+0D0h+OpenOptions], 860h; OpenOptions
0x18007f798  xorps   xmm0, xmm0
0x18007f79b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007f79f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007f7a3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007f7aa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007f7ae  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18007f7b2  mov     edx, 80000000h; DesiredAccess
0x18007f7b7  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007f7be  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18007f7c2  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x18007f7ca  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007f7cf  call    cs:__imp_ZwOpenFile
0x18007f7d6  nop     dword ptr [rax+rax+00h]
0x18007f7db  mov     ebx, eax
0x18007f7dd  test    eax, eax
0x18007f7df  js      loc_18007F9FE
0x18007f7e5  cmp     [rbp+57h+FileHandle], r14
0x18007f7e9  jnz     short loc_18007F7F5
0x18007f7eb  mov     ebx, 0C0000001h
0x18007f7f0  jmp     loc_18007FA1C
0x18007f7f5  mov     edi, 47524C4Bh
0x18007f7fa  mov     edx, 10h
0x18007f7ff  mov     r8d, edi
0x18007f802  mov     ecx, 100h
0x18007f807  call    cs:__imp_ExAllocatePool2
0x18007f80e  nop     dword ptr [rax+rax+00h]
0x18007f813  mov     [rsi], rax
0x18007f816  mov     rbx, rax
0x18007f819  test    rax, rax
0x18007f81c  jnz     short loc_18007F828
0x18007f81e  mov     ebx, 0C0000017h
0x18007f823  jmp     loc_18007F9FE
0x18007f828  mov     r8d, edi
0x18007f82b  mov     ecx, 100h
0x18007f830  mov     edi, 58h ; 'X'
0x18007f835  mov     edx, edi
0x18007f837  call    cs:__imp_ExAllocatePool2
0x18007f83e  nop     dword ptr [rax+rax+00h]
0x18007f843  mov     [rbx], rax
0x18007f846  mov     rax, [rsi]
0x18007f849  mov     rdx, [rax]
0x18007f84c  test    rdx, rdx
0x18007f84f  jz      short loc_18007F81E
0x18007f851  mov     rcx, [rbp+57h+FileHandle]
0x18007f855  xor     r9d, r9d
0x18007f858  mov     r8d, edi
0x18007f85b  call    ReadFromFile
0x18007f860  mov     ebx, eax
0x18007f862  test    eax, eax
0x18007f864  js      loc_18007F9FE
0x18007f86a  mov     rax, [rsi]
0x18007f86d  lea     r8d, [rdi-53h]; MaxCount
0x18007f871  lea     rdx, aMsgrl; "MSGRL"
0x18007f878  mov     rbx, [rax]
0x18007f87b  mov     rcx, rbx; Str1
0x18007f87e  call    wcsncmp_0
0x18007f883  test    eax, eax
0x18007f885  jz      short loc_18007F891
0x18007f887  mov     ebx, 0C00D716Ah
0x18007f88c  jmp     loc_18007F9FE
0x18007f891  mov     ecx, 1
0x18007f896  cmp     cx, [rbx+0Ch]
0x18007f89a  jnb     short loc_18007F8A6
0x18007f89c  mov     ebx, 0C00D716Bh
0x18007f8a1  jmp     loc_18007F9FE
0x18007f8a6  jbe     short loc_18007F8B2
0x18007f8a8  mov     ebx, 0C00D715Fh
0x18007f8ad  jmp     loc_18007F9FE
0x18007f8b2  mov     r8d, [rbx+38h]
0x18007f8b6  cmp     r8d, edi
0x18007f8b9  jb      short loc_18007F887
0x18007f8bb  mov     ecx, [rbx+28h]
0x18007f8be  mov     edx, [rbx+2Ch]
0x18007f8c1  add     edx, ecx
0x18007f8c3  cmp     edx, ecx
0x18007f8c5  jb      short loc_18007F887
0x18007f8c7  mov     ecx, [rbx+30h]
0x18007f8ca  add     ecx, edx
0x18007f8cc  cmp     ecx, edx
0x18007f8ce  jb      short loc_18007F887
0x18007f8d0  mov     edx, [rbx+34h]
0x18007f8d3  add     edx, ecx
0x18007f8d5  cmp     edx, ecx
0x18007f8d7  jb      short loc_18007F887
0x18007f8d9  lea     rdi, [rdx+rdx*4]
0x18007f8dd  mov     eax, 0FFFFFFFFh
0x18007f8e2  shl     rdi, 2
0x18007f8e6  cmp     rdi, rax
0x18007f8e9  ja      short loc_18007F887
0x18007f8eb  cmp     edi, 100000h
0x18007f8f1  ja      short loc_18007F887
0x18007f8f3  lea     eax, [r8-58h]
0x18007f8f7  cmp     edi, eax
0x18007f8f9  jnz     short loc_18007F887
0x18007f8fb  mov     rbx, [rsi]
0x18007f8fe  mov     ecx, 102h
0x18007f903  mov     edx, edi
0x18007f905  mov     r8d, 47524C4Bh
0x18007f90b  call    cs:__imp_ExAllocatePool2
0x18007f912  nop     dword ptr [rax+rax+00h]
0x18007f917  mov     [rbx+8], rax
0x18007f91b  mov     rax, [rsi]
0x18007f91e  mov     rdx, [rax+8]
0x18007f922  test    rdx, rdx
0x18007f925  jz      loc_18007F81E
0x18007f92b  mov     rcx, [rbp+57h+FileHandle]
0x18007f92f  xor     r9d, r9d
0x18007f932  mov     r8d, edi
0x18007f935  call    ReadFromFile
0x18007f93a  mov     ebx, eax
0x18007f93c  test    eax, eax
0x18007f93e  js      loc_18007F9FE
0x18007f944  mov     rcx, [rbp+57h+FileHandle]
0x18007f948  lea     rdx, [rbp+57h+var_40]
0x18007f94c  xor     eax, eax
0x18007f94e  mov     r8d, 8
0x18007f954  mov     [rbp+57h+var_40], rax
0x18007f958  mov     [rbp+57h+var_38], al
0x18007f95b  mov     rax, [rsi]
0x18007f95e  mov     r9, [rax]
0x18007f961  add     r9, 50h ; 'P'
0x18007f965  call    ReadFromFile
0x18007f96a  mov     ebx, eax
0x18007f96c  test    eax, eax
0x18007f96e  js      loc_18007F9FE
0x18007f974  cmp     dword ptr [rbp+57h+var_40+4], 0FFFF8h
0x18007f97b  ja      loc_18007F887
0x18007f981  mov     edx, dword ptr [rbp+57h+var_40+4]
0x18007f984  mov     ecx, 102h
0x18007f989  add     rdx, 8
0x18007f98d  mov     r8d, 47524C4Bh
0x18007f993  call    cs:__imp_ExAllocatePool2
0x18007f99a  nop     dword ptr [rax+rax+00h]
0x18007f99f  mov     r14, rax
0x18007f9a2  test    rax, rax
0x18007f9a5  jz      loc_18007F81E
0x18007f9ab  mov     eax, dword ptr [rbp+57h+var_40]
0x18007f9ae  lea     rdx, [r14+8]
0x18007f9b2  mov     [r14], eax
0x18007f9b5  xor     r9d, r9d
0x18007f9b8  mov     r8d, dword ptr [rbp+57h+var_40+4]
0x18007f9bc  mov     [r14+4], r8d
0x18007f9c0  mov     rcx, [rbp+57h+FileHandle]
0x18007f9c4  call    ReadFromFile
0x18007f9c9  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007f9cd  mov     ebx, eax
0x18007f9cf  call    cs:__imp_ZwClose
0x18007f9d6  nop     dword ptr [rax+rax+00h]
0x18007f9db  mov     [rbp+57h+FileHandle], 0
0x18007f9e3  test    ebx, ebx
0x18007f9e5  js      short loc_18007FA1C
0x18007f9e7  mov     rcx, [rsi]
0x18007f9ea  mov     r8, r12
0x18007f9ed  mov     rdx, r14
0x18007f9f0  call    VerifyCoreSignature
0x18007f9f5  mov     ebx, eax
0x18007f9f7  jmp     short loc_18007F9FE
0x18007f9f9  mov     ebx, 0C000000Dh
0x18007f9fe  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18007fa02  test    rcx, rcx
0x18007fa05  jz      short loc_18007FA13
0x18007fa07  call    cs:__imp_ZwClose
0x18007fa0e  nop     dword ptr [rax+rax+00h]
0x18007fa13  test    ebx, ebx
0x18007fa15  jns     short loc_18007FA2A
0x18007fa17  test    rsi, rsi
0x18007fa1a  jz      short loc_18007FA2A
0x18007fa1c  cmp     qword ptr [rsi], 0
0x18007fa20  jz      short loc_18007FA2A
0x18007fa22  mov     rcx, rsi
0x18007fa25  call    MFFreeGRL
0x18007fa2a  test    r15, r15
0x18007fa2d  jz      short loc_18007FA40
0x18007fa2f  xor     edx, edx; Tag
0x18007fa31  mov     rcx, r15; P
0x18007fa34  call    cs:__imp_ExFreePoolWithTag
0x18007fa3b  nop     dword ptr [rax+rax+00h]
0x18007fa40  test    r14, r14
0x18007fa43  jz      short loc_18007FA56
0x18007fa45  xor     edx, edx; Tag
0x18007fa47  mov     rcx, r14; P
0x18007fa4a  call    cs:__imp_ExFreePoolWithTag
0x18007fa51  nop     dword ptr [rax+rax+00h]
0x18007fa56  mov     eax, ebx
0x18007fa58  mov     rcx, [rbp+57h+var_30]
0x18007fa5c  xor     rcx, rsp; StackCookie
0x18007fa5f  call    __security_check_cookie
0x18007fa64  lea     r11, [rsp+0D0h+var_20]
0x18007fa6c  mov     rbx, [r11+40h]
0x18007fa70  mov     rsi, [r11+48h]
0x18007fa74  mov     rsp, r11
0x18007fa77  pop     r15
0x18007fa79  pop     r14
0x18007fa7b  pop     r12
0x18007fa7d  pop     rdi
0x18007fa7e  pop     rbp
0x18007fa7f  retn
```
