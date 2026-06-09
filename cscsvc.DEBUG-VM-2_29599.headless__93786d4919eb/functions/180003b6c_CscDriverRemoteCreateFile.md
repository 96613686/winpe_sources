# CscDriverRemoteCreateFile

- ea: `0x180003b6c`
- end: `0x18000420d`
- name: `CscDriverRemoteCreateFile`
- size: `1697`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003a00`
- `0x180004220`
- `0x1800355bc`
- `0x180045914`
- `0x18006c160`
- `0x18006c644`
- `0x18006e144`
- `0x1800731e0`

## callees

- `0x180003b6c`
- `0x18000b580`
- `0x18000b8b0`
- `0x180039610`
- `0x18005fa04`
- `0x18006d2d4`
- `0x180071754`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x180003e6e`
- `ntdll!RtlPrefixUnicodeString` at `0x180003e6e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003d54`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003dc0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003dff`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003e0d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f49`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f61`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f8a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000405e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000409d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800040ab`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003d54`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003dc0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003dff`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003e0d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f49`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f61`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003f8a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000405e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000409d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800040ab`
- `ntdll!NtQueryInformationFile` at `0x180003c86`
- `ntdll!NtQueryInformationFile` at `0x180003cf7`
- `ntdll!NtQueryInformationFile` at `0x180003c86`
- `ntdll!NtQueryInformationFile` at `0x180003cf7`
- `ntdll!NtCreateFile` at `0x180004165`
- `ntdll!NtCreateFile` at `0x180004165`

## pseudocode

```c
__int64 __fastcall CscDriverRemoteCreateFile(
        void **a1,
        void *a2,
        const UNICODE_STRING *a3,
        int a4,
        struct _IO_STATUS_BLOCK *a5,
        __int64 a6,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions)
{
  unsigned __int16 *p_FileInformation; // r13
  void **v11; // r15
  NTSTATUS appended; // ebx
  int v15; // esi
  SIZE_T v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned int v18; // ecx
  unsigned __int16 v19; // ax
  WCHAR *v20; // rax
  USHORT Length; // si
  PWSTR Buffer; // r15
  unsigned int i; // ebx
  unsigned __int64 v24; // rdx
  unsigned __int16 v25; // si
  unsigned __int16 v26; // di
  WCHAR *v27; // r15
  USHORT v28; // di
  WCHAR *v29; // rax
  struct _UNICODE_STRING v31; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING Source; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING v33; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+B0h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+D0h] [rbp-30h]
  PIO_STATUS_BLOCK v37; // [rsp+D8h] [rbp-28h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  __int64 FileInformation; // [rsp+110h] [rbp+10h] BYREF

  p_FileInformation = (unsigned __int16 *)&FileInformation;
  *(_QWORD *)&Destination.Length = a1;
  v11 = a1;
  v36 = a4;
  v37 = a5;
  FileInformation = 0;
  memset(&ObjectAttributes, 0, 44);
  v31 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qqZDqqiDDDDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      FileAttributes,
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)a1,
      (char)a2,
      (__int64)a3,
      a4,
      (char)a5);
  }
  *v11 = 0;
  if ( !a2 )
  {
    Length = a3->Length;
    Buffer = a3->Buffer;
    for ( i = 0; ; ++i )
    {
      if ( i >= 4 )
      {
        v11 = *(void ***)&Destination.Length;
        appended = -1073741585;
        goto LABEL_68;
      }
      if ( RtlPrefixUnicodeString(&::Source + i, a3, 1u) )
        break;
    }
    v24 = *(&::Source.Length + 8 * i);
    IoStatusBlock.Information = (ULONG_PTR)L"$NOCSC$";
    IoStatusBlock.Pointer = (PVOID)1048590;
    v25 = Length - v24;
    v33.Buffer = 0;
    *(_DWORD *)&v33.Length = 0;
    Source = 0;
    if ( v25 >= 2u )
    {
      if ( (unsigned int)v25 + 14 > 0xFFFF )
      {
        appended = -1073741675;
LABEL_49:
        if ( v33.Buffer )
        {
          CscDriverpFree(v33.Buffer);
          v33.Buffer = 0;
          v33.Length = 0;
        }
LABEL_64:
        v11 = *(void ***)&Destination.Length;
        goto LABEL_68;
      }
      v26 = 0;
      v27 = &Buffer[v24 >> 1];
      while ( v26 < (unsigned __int16)(v25 >> 1) )
      {
        if ( v27[v26] == 92 )
        {
          v33.MaximumLength = v25 + 14;
          v33.Buffer = (PWSTR)CscDriverpAllocate((unsigned __int16)(v25 + 14));
          if ( !v33.Buffer )
          {
            appended = -1073741670;
            goto LABEL_49;
          }
          v28 = 2 * v26;
          Source.Buffer = v27;
          Source.Length = v28;
          Source.MaximumLength = v28;
          appended = RtlAppendUnicodeStringToString(&v33, &Source);
          if ( appended < 0 )
            goto LABEL_49;
          appended = RtlAppendUnicodeStringToString(&v33, (PCUNICODE_STRING)&IoStatusBlock);
          if ( appended < 0 )
            goto LABEL_49;
          Source.Length = v25 - v28;
          Source.Buffer = &v27[v28 / 2u];
          Source.MaximumLength = v25 - v28;
          appended = RtlAppendUnicodeStringToString(&v33, &Source);
          if ( appended < 0 )
            goto LABEL_49;
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, &v33);
          }
          *(_QWORD *)&Source.Length = 262146;
          Source.Buffer = (PWSTR)L"\\";
          v31.Length = 0;
          v31.MaximumLength = ::Source.Length + v33.Length + 2;
          v29 = (WCHAR *)CscDriverpAllocate(v31.MaximumLength);
          v31.Buffer = v29;
          if ( v29 )
          {
            appended = RtlAppendUnicodeStringToString(&v31, &::Source);
            if ( v33.Length >= 2u )
            {
              if ( ::Source.Buffer[((unsigned __int64)::Source.Length >> 1) - 1] != *Source.Buffer
                && *v33.Buffer != *Source.Buffer )
              {
                RtlAppendUnicodeStringToString(&v31, &Source);
              }
              appended = RtlAppendUnicodeStringToString(&v31, &v33);
            }
            if ( appended >= 0 )
            {
              v11 = *(void ***)&Destination.Length;
              goto LABEL_66;
            }
            v29 = v31.Buffer;
          }
          else
          {
            appended = -1073741670;
          }
          if ( v29 )
          {
            CscDriverpFree(v29);
            v31.Buffer = 0;
          }
          *(_DWORD *)&v31.Length = 0;
          goto LABEL_64;
        }
        ++v26;
      }
    }
    appended = -1073741811;
    goto LABEL_49;
  }
  IoStatusBlock = 0;
  Destination = 0;
  appended = NtQueryInformationFile(a2, &IoStatusBlock, &FileInformation, 8u, FileNameInformation);
  if ( (int)(appended + 0x80000000) < 0 || appended == -2147483643 )
  {
    v15 = FileInformation;
    v16 = (unsigned int)FileInformation + a3->Length + 10LL;
    if ( v16 > 0xFFFE )
    {
      appended = -1073741675;
      goto LABEL_68;
    }
    v17 = (unsigned __int16 *)CscDriverpAllocate(v16);
    p_FileInformation = v17;
    if ( !v17 )
    {
      appended = -1073741670;
      goto LABEL_68;
    }
    IoStatusBlock = 0;
    appended = NtQueryInformationFile(a2, &IoStatusBlock, v17, v15 + 8, FileNameInformation);
    if ( appended >= 0 )
    {
      Destination.MaximumLength = a3->Length + v15;
      v18 = *p_FileInformation;
      v19 = *p_FileInformation;
      Destination.Buffer = p_FileInformation + 3;
      Destination.Length = v19 - 2;
      if ( p_FileInformation[((unsigned __int64)(unsigned __int16)(v19 - 2) >> 1) + 2] != 92 )
      {
        Destination.Length = v18;
        p_FileInformation[((unsigned __int64)v18 >> 1) + 2] = 92;
      }
      appended = RtlAppendUnicodeStringToString(&Destination, a3);
      if ( appended >= 0 )
      {
        *(_QWORD *)&Source.Length = 262146;
        Source.Buffer = (PWSTR)L"\\";
        v31.Length = 0;
        v31.MaximumLength = ::Source.Length + Destination.Length + 2;
        v20 = (WCHAR *)CscDriverpAllocate(v31.MaximumLength);
        v31.Buffer = v20;
        if ( v20 )
        {
          appended = RtlAppendUnicodeStringToString(&v31, &::Source);
          if ( Destination.Length >= 2u )
          {
            if ( ::Source.Buffer[((unsigned __int64)::Source.Length >> 1) - 1] != *Source.Buffer
              && *Destination.Buffer != *Source.Buffer )
            {
              RtlAppendUnicodeStringToString(&v31, &Source);
            }
            appended = RtlAppendUnicodeStringToString(&v31, &Destination);
          }
          if ( appended >= 0 )
          {
LABEL_66:
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            ObjectAttributes.ObjectName = &v31;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            appended = NtCreateFile(
                         v11,
                         v36 | 0x100000,
                         &ObjectAttributes,
                         v37,
                         0,
                         FileAttributes,
                         ShareAccess,
                         CreateDisposition,
                         CreateOptions,
                         0,
                         0);
            CscDriverpFree(v31.Buffer);
            goto LABEL_68;
          }
          v20 = v31.Buffer;
        }
        else
        {
          appended = -1073741670;
        }
        if ( v20 )
        {
          CscDriverpFree(v20);
          v31.Buffer = 0;
        }
        *(_DWORD *)&v31.Length = 0;
      }
    }
  }
LABEL_68:
  if ( v33.Buffer )
    CscDriverpFree(v33.Buffer);
  if ( p_FileInformation != (unsigned __int16 *)&FileInformation )
    CscDriverpFree(p_FileInformation);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      15,
      WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
      v11,
      *v11,
      appended);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180003b6c  push    rbp
0x180003b6e  push    rbx
0x180003b6f  push    rsi
0x180003b70  push    rdi
0x180003b71  push    r12
0x180003b73  push    r13
0x180003b75  push    r14
0x180003b77  push    r15
0x180003b79  lea     rbp, [rsp-28h]
0x180003b7e  sub     rsp, 128h
0x180003b85  mov     rax, cs:__security_cookie
0x180003b8c  xor     rax, rsp
0x180003b8f  mov     [rbp+60h+var_48], rax
0x180003b93  mov     rax, [rbp+60h+arg_20]
0x180003b9a  lea     r13, [rbp+60h+FileInformation]
0x180003b9e  xorps   xmm0, xmm0
0x180003ba1  mov     qword ptr [rbp+60h+Destination.Length], rcx
0x180003ba5  mov     r15, rcx
0x180003ba8  mov     [rbp+60h+var_90], r9d
0x180003bac  xor     ecx, ecx
0x180003bae  mov     [rbp+60h+var_88], rax
0x180003bb2  xorps   xmm1, xmm1
0x180003bb5  mov     [rbp+60h+FileInformation], rcx
0x180003bb9  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x180003bbd  mov     rdi, r8
0x180003bc0  mov     r14, rdx
0x180003bc3  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x180003bc7  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x180003bcb  movups  xmmword ptr [rbp+60h+var_E0.Length], xmm0
0x180003bcf  movups  xmmword ptr [rbp+60h+var_C0.Length], xmm1
0x180003bd3  lea     edx, [rcx+4]
0x180003bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bdd  lea     r8, WPP_GLOBAL_Control
0x180003be4  cmp     rcx, r8
0x180003be7  jz      short loc_180003C4D
0x180003be9  test    dword ptr [rcx+44h], 400h
0x180003bf0  jz      short loc_180003C4D
0x180003bf2  cmp     [rcx+41h], dl
0x180003bf5  jb      short loc_180003C4D
0x180003bf7  mov     edx, [rbp+60h+arg_48]
0x180003bfd  mov     rcx, [rcx+38h]
0x180003c01  mov     [rsp+160h+var_F8], edx
0x180003c05  mov     edx, [rbp+60h+arg_40]
0x180003c0b  mov     [rsp+160h+var_100], edx
0x180003c0f  mov     edx, [rbp+60h+arg_38]
0x180003c15  mov     [rsp+160h+var_108], edx
0x180003c19  mov     edx, [rbp+60h+arg_30]
0x180003c1f  mov     [rsp+160h+EaLength], edx
0x180003c23  mov     [rsp+160h+EaBuffer], 0
0x180003c2c  mov     qword ptr [rsp+160h+CreateDisposition], rax
0x180003c31  mov     [rsp+160h+ShareAccess], r9d
0x180003c36  mov     r9, r15
0x180003c39  mov     qword ptr [rsp+160h+FileAttributes], rdi
0x180003c3e  mov     qword ptr [rsp+160h+FileInformationClass], r14
0x180003c43  call    WPP_SF_qqZDqqiDDDDqD
0x180003c48  mov     edx, 4
0x180003c4d  mov     qword ptr [r15], 0
0x180003c54  test    r14, r14
0x180003c57  jz      loc_180003E40
0x180003c5d  mov     r12d, 9
0x180003c63  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x180003c67  xorps   xmm0, xmm0
0x180003c6a  mov     [rsp+160h+FileInformationClass], r12d; FileInformationClass
0x180003c6f  xorps   xmm1, xmm1
0x180003c72  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180003c76  mov     rcx, r14; FileHandle
0x180003c79  lea     r9d, [r12-1]; Length
0x180003c7e  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x180003c82  movups  xmmword ptr [rbp+60h+Destination.Length], xmm1
0x180003c86  call    cs:__imp_NtQueryInformationFile
0x180003c8c  mov     ebx, eax
0x180003c8e  mov     eax, 80000000h
0x180003c93  lea     ecx, [rbx+rax]
0x180003c96  test    eax, ecx
0x180003c98  jnz     short loc_180003CA6
0x180003c9a  cmp     ebx, 80000005h
0x180003ca0  jnz     loc_180004181
0x180003ca6  movzx   ecx, word ptr [rdi]
0x180003ca9  mov     esi, dword ptr [rbp+60h+FileInformation]
0x180003cac  add     rcx, 0Ah
0x180003cb0  add     rcx, rsi; uBytes
0x180003cb3  cmp     rcx, 0FFFEh
0x180003cba  jbe     short loc_180003CC6
0x180003cbc  mov     ebx, 0C0000095h
0x180003cc1  jmp     loc_180004181
0x180003cc6  call    CscDriverpAllocate
0x180003ccb  mov     r13, rax
0x180003cce  test    rax, rax
0x180003cd1  jnz     short loc_180003CDD
0x180003cd3  mov     ebx, 0C000009Ah
0x180003cd8  jmp     loc_180004181
0x180003cdd  xorps   xmm0, xmm0
0x180003ce0  mov     [rsp+160h+FileInformationClass], r12d; FileInformationClass
0x180003ce5  lea     r9d, [rsi+8]; Length
0x180003ce9  mov     r8, r13; FileInformation
0x180003cec  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180003cf0  mov     rcx, r14; FileHandle
0x180003cf3  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x180003cf7  call    cs:__imp_NtQueryInformationFile
0x180003cfd  mov     ebx, eax
0x180003cff  test    eax, eax
0x180003d01  js      loc_180004181
0x180003d07  add     si, [rdi]
0x180003d0a  lea     rdx, [r13+6]
0x180003d0e  mov     [rbp+60h+Destination.MaximumLength], si
0x180003d12  mov     r14d, 2
0x180003d18  movzx   ecx, word ptr [r13+0]
0x180003d1d  movzx   eax, cx
0x180003d20  mov     [rbp+60h+Destination.Buffer], rdx
0x180003d24  sub     ax, r14w
0x180003d28  mov     [rbp+60h+Destination.Length], ax
0x180003d2c  lea     r8d, [r14+5Ah]
0x180003d30  movzx   eax, ax
0x180003d33  shr     rax, 1
0x180003d36  cmp     [rdx+rax*2-2], r8w
0x180003d3c  jz      short loc_180003D4D
0x180003d3e  mov     eax, ecx
0x180003d40  mov     [rbp+60h+Destination.Length], cx
0x180003d44  shr     rax, 1
0x180003d47  mov     [rdx+rax*2-2], r8w
0x180003d4d  mov     rdx, rdi; Source
0x180003d50  lea     rcx, [rbp+60h+Destination]; Destination
0x180003d54  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003d5a  mov     ebx, eax
0x180003d5c  test    eax, eax
0x180003d5e  js      loc_180004181
0x180003d64  lea     rax, Src; "\\"
0x180003d6b  mov     qword ptr [rbp+60h+Source.Length], 40002h
0x180003d73  mov     [rbp+60h+Source.Buffer], rax
0x180003d77  mov     edi, 4
0x180003d7c  xor     eax, eax
0x180003d7e  mov     [rbp+60h+var_E0.Buffer], 0
0x180003d86  mov     [rbp+60h+var_E0.Length], ax
0x180003d8a  movzx   eax, r14w
0x180003d8e  add     ax, [rbp+60h+Destination.Length]
0x180003d92  add     ax, cs:Source.Length
0x180003d99  movzx   ecx, ax; uBytes
0x180003d9c  mov     [rbp+60h+var_E0.MaximumLength], cx
0x180003da0  call    CscDriverpAllocate
0x180003da5  mov     [rbp+60h+var_E0.Buffer], rax
0x180003da9  test    rax, rax
0x180003dac  jnz     short loc_180003DB5
0x180003dae  mov     ebx, 0C000009Ah
0x180003db3  jmp     short loc_180003E21
0x180003db5  lea     rdx, Source; Source
0x180003dbc  lea     rcx, [rbp+60h+var_E0]; Destination
0x180003dc0  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003dc6  mov     ebx, eax
0x180003dc8  cmp     r14w, [rbp+60h+Destination.Length]
0x180003dcd  ja      short loc_180003E15
0x180003dcf  mov     rax, [rbp+60h+Source.Buffer]
0x180003dd3  movzx   ecx, cs:Source.Length
0x180003dda  shr     rcx, 1
0x180003ddd  movzx   edx, word ptr [rax]
0x180003de0  mov     rax, cs:Source.Buffer
0x180003de7  cmp     [rax+rcx*2-2], dx
0x180003dec  jz      short loc_180003E05
0x180003dee  mov     rax, [rbp+60h+Destination.Buffer]
0x180003df2  cmp     [rax], dx
0x180003df5  jz      short loc_180003E05
0x180003df7  lea     rdx, [rbp+60h+Source]; Source
0x180003dfb  lea     rcx, [rbp+60h+var_E0]; Destination
0x180003dff  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003e05  lea     rdx, [rbp+60h+Destination]; Source
0x180003e09  lea     rcx, [rbp+60h+var_E0]; Destination
0x180003e0d  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003e13  mov     ebx, eax
0x180003e15  test    ebx, ebx
0x180003e17  jns     loc_1800040E4
0x180003e1d  mov     rax, [rbp+60h+var_E0.Buffer]
0x180003e21  test    rax, rax
0x180003e24  jz      short loc_180003E36
0x180003e26  mov     rcx, rax
0x180003e29  call    CscDriverpFree
0x180003e2e  mov     [rbp+60h+var_E0.Buffer], 0
0x180003e36  xor     eax, eax
0x180003e38  mov     dword ptr [rbp+60h+var_E0.Length], eax
0x180003e3b  jmp     loc_180004186
0x180003e40  movzx   esi, word ptr [rdi]
0x180003e43  lea     r12, Source
0x180003e4a  mov     r15, [rdi+8]
0x180003e4e  xor     ebx, ebx
0x180003e50  lea     ecx, [rbx+1]
0x180003e53  cmp     ebx, edx
0x180003e55  jnb     loc_180004178
0x180003e5b  mov     r8b, cl; CaseInsensitive
0x180003e5e  mov     r14d, ebx
0x180003e61  shl     r14, 4
0x180003e65  mov     rdx, rdi; String2
0x180003e68  add     r14, r12
0x180003e6b  mov     rcx, r14; String1
0x180003e6e  call    cs:__imp_RtlPrefixUnicodeString
0x180003e74  test    al, al
0x180003e76  jnz     short loc_180003E84
0x180003e78  mov     ecx, 1
0x180003e7d  add     ebx, ecx
0x180003e7f  lea     edx, [rcx+3]
0x180003e82  jmp     short loc_180003E53
0x180003e84  movzx   edx, word ptr [r14]
0x180003e88  lea     rax, aNocsc; "$NOCSC$"
0x180003e8f  mov     r9d, 0Eh
0x180003e95  mov     [rbp+60h+IoStatusBlock.Information], rax
0x180003e99  xor     eax, eax
0x180003e9b  mov     qword ptr [rbp+60h+IoStatusBlock], 10000Eh
0x180003ea3  sub     si, dx
0x180003ea6  mov     [rbp+60h+var_C0.Buffer], 0
0x180003eae  xorps   xmm0, xmm0
0x180003eb1  mov     dword ptr [rbp+60h+var_C0.Length], eax
0x180003eb4  lea     r14d, [r9-0Ch]
0x180003eb8  movups  xmmword ptr [rbp+60h+Source.Length], xmm0
0x180003ebc  cmp     si, r14w
0x180003ec0  jb      loc_180003FD6
0x180003ec6  movzx   ecx, si
0x180003ec9  add     ecx, r9d
0x180003ecc  cmp     ecx, 0FFFFh
0x180003ed2  jbe     short loc_180003EDE
0x180003ed4  mov     ebx, 0C0000095h
0x180003ed9  jmp     loc_180003FDB
0x180003ede  xor     edi, edi
0x180003ee0  mov     rax, rdx
0x180003ee3  shr     rax, 1
0x180003ee6  movzx   ecx, si
0x180003ee9  shr     cx, 1
0x180003eec  lea     edx, [rdi+1]
0x180003eef  lea     r15, [r15+rax*2]
0x180003ef3  lea     r8d, [rdi+5Ch]
0x180003ef7  cmp     di, cx
0x180003efa  jnb     loc_180003FD6
0x180003f00  movzx   eax, di
0x180003f03  cmp     r8w, [r15+rax*2]
0x180003f08  jz      short loc_180003F0F
0x180003f0a  add     di, dx
0x180003f0d  jmp     short loc_180003EF7
0x180003f0f  lea     eax, [r9+rsi]
0x180003f13  movzx   ecx, ax; uBytes
0x180003f16  mov     [rbp+60h+var_C0.MaximumLength], cx
0x180003f1a  call    CscDriverpAllocate
0x180003f1f  mov     [rbp+60h+var_C0.Buffer], rax
0x180003f23  test    rax, rax
0x180003f26  jnz     short loc_180003F32
0x180003f28  mov     ebx, 0C000009Ah
0x180003f2d  jmp     loc_180003FDB
0x180003f32  add     di, di
0x180003f35  mov     [rbp+60h+Source.Buffer], r15
0x180003f39  lea     rdx, [rbp+60h+Source]; Source
0x180003f3d  mov     [rbp+60h+Source.Length], di
0x180003f41  lea     rcx, [rbp+60h+var_C0]; Destination
0x180003f45  mov     [rbp+60h+Source.MaximumLength], di
0x180003f49  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003f4f  mov     ebx, eax
0x180003f51  test    eax, eax
0x180003f53  js      loc_180003FDB
0x180003f59  lea     rdx, [rbp+60h+IoStatusBlock]; Source
0x180003f5d  lea     rcx, [rbp+60h+var_C0]; Destination
0x180003f61  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003f67  mov     ebx, eax
0x180003f69  test    eax, eax
0x180003f6b  js      short loc_180003FDB
0x180003f6d  sub     si, di
0x180003f70  movzx   eax, di
0x180003f73  add     rax, r15
0x180003f76  mov     [rbp+60h+Source.Length], si
0x180003f7a  lea     rdx, [rbp+60h+Source]; Source
0x180003f7e  mov     [rbp+60h+Source.Buffer], rax
0x180003f82  lea     rcx, [rbp+60h+var_C0]; Destination
0x180003f86  mov     [rbp+60h+Source.MaximumLength], si
0x180003f8a  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003f90  mov     ebx, eax
0x180003f92  test    eax, eax
0x180003f94  js      short loc_180003FDB
0x180003f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f9d  lea     rsi, WPP_GLOBAL_Control
0x180003fa4  mov     edi, 4
0x180003fa9  cmp     rcx, rsi
0x180003fac  jz      short loc_18000400B
0x180003fae  test    dword ptr [rcx+44h], 400h
0x180003fb5  jz      short loc_18000400B
0x180003fb7  cmp     [rcx+41h], dil
0x180003fbb  jb      short loc_18000400B
0x180003fbd  mov     rcx, [rcx+38h]
0x180003fc1  lea     edx, [rdi+8]
0x180003fc4  lea     r9, [rbp+60h+var_C0]
0x180003fc8  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x180003fcf  call    WPP_SF_Z
0x180003fd4  jmp     short loc_18000400B
0x180003fd6  mov     ebx, 0C000000Dh
0x180003fdb  mov     rcx, [rbp+60h+var_C0.Buffer]
0x180003fdf  test    rcx, rcx
0x180003fe2  jz      short loc_180003FF7
0x180003fe4  call    CscDriverpFree
0x180003fe9  xor     eax, eax
0x180003feb  mov     [rbp+60h+var_C0.Buffer], 0
0x180003ff3  mov     [rbp+60h+var_C0.Length], ax
0x180003ff7  lea     rsi, WPP_GLOBAL_Control
0x180003ffe  mov     edi, 4
0x180004003  test    ebx, ebx
0x180004005  js      loc_1800040D5
0x18000400b  lea     rax, Src; "\\"
0x180004012  mov     qword ptr [rbp+60h+Source.Length], 40002h
0x18000401a  mov     [rbp+60h+Source.Buffer], rax
  ... truncated ...
```
