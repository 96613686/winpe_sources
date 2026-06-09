# CscDriverOpenItemWithDispositionEx

- ea: `0x180002db0`
- end: `0x18000363e`
- name: `CscDriverOpenItemWithDispositionEx`
- size: `2190`
- prototype: `__int64 __usercall@<rax>(PHANDLE FileHandle@<rcx>, int, ULONG, int, int)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002080`
- `0x180002820`
- `0x180002cd0`
- `0x1800060c0`
- `0x1800091d4`

## callees

- `0x180002db0`
- `0x180003650`
- `0x1800036b0`
- `0x180003e90`
- `0x180008ccc`
- `0x180008eb0`
- `0x180009050`
- `0x1800090c0`
- `0x180009490`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003008`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003031`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003008`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003031`
- `ntdll!NtClose` at `0x1800033c2`
- `ntdll!NtClose` at `0x1800033c2`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000310e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000314b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800031a8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800031e6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003279`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800032bd`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800033df`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800033f3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003408`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000310e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000314b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800031a8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800031e6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003279`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800032bd`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800033df`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800033f3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003408`
- `ntdll!RtlPrefixUnicodeString` at `0x1800034af`
- `ntdll!RtlPrefixUnicodeString` at `0x1800034af`
- `ntdll!NtCreateFile` at `0x180003339`
- `ntdll!NtCreateFile` at `0x180003339`

## pseudocode

```c
__int64 __fastcall CscDriverOpenItemWithDispositionEx(
        PHANDLE FileHandle,
        __int64 a2,
        const UNICODE_STRING *a3,
        int a4,
        int a5,
        ULONG ShareAccess,
        int a7,
        int a8)
{
  UNICODE_STRING v8; // xmm1
  int v12; // ecx
  ULONG CreateOptions; // r12d
  int v14; // r14d
  USHORT Length; // cx
  WCHAR *Buffer; // r8
  unsigned int i; // r9d
  unsigned int v18; // ebx
  NTSTATUS appended; // edi
  int v20; // r15d
  _QWORD *v21; // rcx
  HLOCAL v22; // rbx
  HLOCAL v23; // rbx
  void *v25; // rax
  NTSTATUS v26; // eax
  void *v27; // rcx
  const UNICODE_STRING *v28; // rdi
  HLOCAL v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING v30; // [rsp+70h] [rbp-90h] BYREF
  UNICODE_STRING v31; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem[2]; // [rsp+90h] [rbp-70h] BYREF
  int v33; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING Source; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING v35; // [rsp+B8h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v38; // [rsp+108h] [rbp+8h] BYREF
  int v39; // [rsp+118h] [rbp+18h]
  _DWORD EaBuffer[2]; // [rsp+120h] [rbp+20h] BYREF
  char v41[13]; // [rsp+128h] [rbp+28h] BYREF
  int v42; // [rsp+135h] [rbp+35h]

  v8 = *a3;
  *(_QWORD *)&Source.Length = 655368;
  *(_QWORD *)&v35.Length = 1572886;
  v31 = v8;
  Source.Buffer = L"\\.\\.";
  v35.Buffer = L"\\Device\\Csc";
  *(_OWORD *)v29 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_OWORD *)hMem = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qqZDDDD(*((_QWORD *)WPP_GLOBAL_Control + 7), a2, (_DWORD)a3, (_DWORD)FileHandle);
  }
  if ( FileHandle )
    *FileHandle = 0;
  v12 = a8 | 0x20;
  if ( (a4 & 0x10) != 0 )
    v12 = a8;
  CreateOptions = v12 | 1;
  if ( (a4 & 0x20) == 0 )
    CreateOptions = v12;
  if ( (a4 & 0x40) != 0 )
    CreateOptions |= 0x40u;
  v14 = (2 * (a4 & 2)) | 8;
  if ( (a4 & 4) == 0 )
    v14 = 2 * (a4 & 2);
  if ( (a4 & 8) != 0 )
    v14 |= 0x10u;
  if ( (a4 & 0x80u) != 0 )
    v14 |= 0x20u;
  if ( (a4 & 0x80000) != 0 )
    v14 |= 0x40000u;
  if ( (a4 & 0x100) != 0 )
    v14 |= 0x40u;
  if ( (a4 & 0x200) != 0 )
    v14 |= 0x80u;
  if ( (a4 & 0x400) != 0 )
    v14 |= 0x100u;
  if ( (a4 & 0x800) != 0 )
    v14 |= 0x200u;
  if ( (a4 & 0x1000) != 0 )
    v14 |= 0x400u;
  if ( (a4 & 0x2000) != 0 )
    v14 |= 0x800u;
  if ( (a4 & 0x4000) != 0 )
    v14 |= 0x2000u;
  if ( (a4 & 0x8000) != 0 )
    v14 |= 0x4000u;
  if ( (a4 & 0x10000) != 0 )
    v14 |= 0x8000u;
  if ( (a4 & 0x20000) != 0 )
    v14 |= 0x10000u;
  if ( (a4 & 0x40000) != 0 )
    v14 |= 0x20000u;
  if ( (a4 & 0x100000) != 0 )
    v14 |= 0x80000u;
  EaBuffer[0] = 0;
  EaBuffer[1] = 265216;
  strcpy(v41, "$RxCscFlags$");
  v42 = v14;
  if ( (a4 & 1) != 0 )
  {
    Length = v31.Length;
    Buffer = v31.Buffer;
    if ( v31.Length >= 2u && *v31.Buffer == 92 )
    {
      Buffer = v31.Buffer + 1;
      Length = v31.Length - 2;
      goto LABEL_46;
    }
    goto LABEL_47;
  }
  v18 = 0;
  v31 = *a3;
  while ( 1 )
  {
    if ( v18 >= 4 )
    {
      appended = -1073741811;
      v20 = 886;
LABEL_55:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    v28 = &::Source + v18;
    if ( RtlPrefixUnicodeString(v28, a3, 1u) )
      break;
    ++v18;
  }
  Buffer = &v31.Buffer[(unsigned __int64)v28->Length >> 1];
  Length = v31.Length - v28->Length;
LABEL_46:
  v31.MaximumLength = Length;
  v31.Length = Length;
  v31.Buffer = Buffer;
LABEL_47:
  if ( Length )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= Length >> 1 )
        goto LABEL_67;
      if ( Buffer[i] == 92 )
        break;
    }
    *(_QWORD *)&v30.Length = 262146;
    WORD1(v29[0]) = ::Source.Length + Length + 2;
    v30.Buffer = L"\\";
    LOWORD(v29[0]) = 0;
    v29[1] = (HLOCAL)CscDriverpAllocate(WORD1(v29[0]));
    if ( v29[1] )
    {
      appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)v29, &::Source);
      if ( v31.Length >= 2u )
      {
        if ( ::Source.Buffer[((unsigned __int64)::Source.Length >> 1) - 1] != *v30.Buffer && *v31.Buffer != *v30.Buffer )
          RtlAppendUnicodeStringToString((PUNICODE_STRING)v29, &v30);
        appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)v29, &v31);
      }
      if ( appended >= 0 )
        goto LABEL_93;
    }
    else
    {
      appended = -1073741670;
    }
    if ( v29[1] )
    {
      CscDriverpFree(v29[1]);
      v29[1] = 0;
    }
    LODWORD(v29[0]) = 0;
    v20 = 971;
    goto LABEL_55;
  }
LABEL_67:
  *(_QWORD *)&v30.Length = 262146;
  v30.Buffer = L"\\";
  LOWORD(hMem[0]) = 0;
  WORD1(hMem[0]) = Source.Length + Length + 2;
  hMem[1] = (HLOCAL)CscDriverpAllocate(WORD1(hMem[0]));
  if ( !hMem[1] )
  {
    appended = -1073741670;
LABEL_108:
    if ( hMem[1] )
    {
      CscDriverpFree(hMem[1]);
      hMem[1] = 0;
    }
    LODWORD(hMem[0]) = 0;
    v20 = 934;
    goto LABEL_55;
  }
  appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)hMem, &Source);
  if ( v31.Length >= 2u )
  {
    if ( Source.Buffer[((unsigned __int64)Source.Length >> 1) - 1] != *v30.Buffer && *v31.Buffer != *v30.Buffer )
      RtlAppendUnicodeStringToString((PUNICODE_STRING)hMem, &v30);
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)hMem, &v31);
  }
  if ( appended < 0 )
    goto LABEL_108;
  *(_QWORD *)&v30.Length = 262146;
  LOWORD(v29[0]) = 0;
  v30.Buffer = L"\\";
  WORD1(v29[0]) = v35.Length + LOWORD(hMem[0]) + 2;
  v29[1] = (HLOCAL)CscDriverpAllocate(WORD1(v29[0]));
  if ( !v29[1] )
  {
    appended = -1073741670;
LABEL_112:
    if ( v29[1] )
    {
      CscDriverpFree(v29[1]);
      v29[1] = 0;
    }
    LODWORD(v29[0]) = 0;
    v20 = 946;
    goto LABEL_55;
  }
  appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)v29, &v35);
  if ( LOWORD(hMem[0]) >= 2u )
  {
    if ( v35.Buffer[((unsigned __int64)v35.Length >> 1) - 1] != *v30.Buffer && *(_WORD *)hMem[1] != *v30.Buffer )
      RtlAppendUnicodeStringToString((PUNICODE_STRING)v29, &v30);
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)v29, (PCUNICODE_STRING)hMem);
  }
  if ( appended < 0 )
    goto LABEL_112;
LABEL_93:
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v29;
  ObjectAttributes.Length = 48;
  v20 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v26 = NtCreateFile(
          FileHandle,
          a5 | 0x100000,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          ShareAccess,
          1u,
          CreateOptions,
          EaBuffer,
          0x1Cu);
  appended = v26;
  if ( (v14 & 0x4002C) == 0 )
    goto LABEL_55;
  if ( v26 != -1073741605 )
  {
    if ( v26 >= 0 )
    {
      v27 = *FileHandle;
      v39 = 0;
      v33 = 0;
      v38 = 0;
      *(_QWORD *)&v30.Length = 8;
      if ( (int)CscDriverpFsControlEx(v27, a2, &v33, &v30, 8u, &v38, 0x14u) >= 0 && (v14 & 8) != 0 && (_DWORD)v38 != 2 )
      {
        NtClose(*FileHandle);
        *FileHandle = 0;
        appended = -1073740768;
      }
    }
    goto LABEL_55;
  }
  appended = -1073741766;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, a3, 3221225691LL, -1073741766);
    goto LABEL_55;
  }
LABEL_56:
  v22 = hMem[1];
  if ( hMem[1] )
  {
    LocalFree(hMem[1]);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, a3, v22);
      v21 = WPP_GLOBAL_Control;
    }
  }
  v23 = v29[1];
  if ( v29[1] )
  {
    LocalFree(v29[1]);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, a3, v23);
        v21 = WPP_GLOBAL_Control;
      }
      goto LABEL_62;
    }
  }
  else
  {
LABEL_62:
    if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 17) & 0x400) != 0 && *((_BYTE *)v21 + 65) >= 4u )
    {
      if ( FileHandle )
        v25 = *FileHandle;
      else
        v25 = 0;
      WPP_SF_qqDD(v21[7], a2, a3, FileHandle, v25, appended, v20);
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180002db0  mov     [rsp-8+arg_8], rbx
0x180002db5  push    rbp
0x180002db6  push    rsi
0x180002db7  push    rdi
0x180002db8  push    r12
0x180002dba  push    r13
0x180002dbc  push    r14
0x180002dbe  push    r15
0x180002dc0  lea     rbp, [rsp-50h]
0x180002dc5  sub     rsp, 150h
0x180002dcc  mov     rax, cs:__security_cookie
0x180002dd3  xor     rax, rsp
0x180002dd6  mov     [rbp+80h+var_40], rax
0x180002dda  movups  xmm1, xmmword ptr [r8]
0x180002dde  mov     qword ptr [rbp+80h+Source.Length], 0A0008h
0x180002de6  xor     eax, eax
0x180002de8  xorps   xmm0, xmm0
0x180002deb  mov     qword ptr [rbp+80h+var_C8.Length], 180016h
0x180002df3  lea     rax, asc_18000B650; "\\.\\."
0x180002dfa  mov     ebx, r9d
0x180002dfd  movups  xmmword ptr [rbp+80h+var_100.Length], xmm1
0x180002e01  mov     [rbp+80h+Source.Buffer], rax
0x180002e05  lea     rax, aDeviceCsc; "\\Device\\Csc"
0x180002e0c  xorps   xmm1, xmm1
0x180002e0f  mov     [rbp+80h+var_C8.Buffer], rax
0x180002e13  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x180002e17  mov     r15, r8
0x180002e1a  mov     rsi, rcx
0x180002e1d  movups  xmmword ptr [rsp+180h+var_120], xmm1
0x180002e22  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x180002e26  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x180002e2a  movups  xmmword ptr [rbp+80h+IoStatusBlock], xmm0
0x180002e2e  movups  xmmword ptr [rbp+80h+hMem], xmm0
0x180002e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e39  lea     rax, WPP_GLOBAL_Control
0x180002e40  mov     edi, [rbp+80h+arg_38]
0x180002e46  mov     r13d, [rbp+80h+arg_20]
0x180002e4d  cmp     rcx, rax
0x180002e50  jnz     loc_18000307F
0x180002e56  xor     r10d, r10d
0x180002e59  test    rsi, rsi
0x180002e5c  jz      short loc_180002E61
0x180002e5e  mov     [rsi], r10
0x180002e61  mov     ecx, edi
0x180002e63  or      ecx, 20h
0x180002e66  test    bl, 10h
0x180002e69  cmovnz  ecx, edi
0x180002e6c  mov     r12d, ecx
0x180002e6f  or      r12d, 1
0x180002e73  test    bl, 20h
0x180002e76  cmovz   r12d, ecx
0x180002e7a  mov     ecx, ebx
0x180002e7c  mov     eax, r12d
0x180002e7f  or      eax, 40h
0x180002e82  test    bl, 40h
0x180002e85  cmovnz  r12d, eax
0x180002e89  and     ecx, 2
0x180002e8c  add     ecx, ecx
0x180002e8e  mov     r14d, ecx
0x180002e91  or      r14d, 8
0x180002e95  test    bl, 4
0x180002e98  cmovz   r14d, ecx
0x180002e9c  mov     eax, r14d
0x180002e9f  or      eax, 10h
0x180002ea2  test    bl, 8
0x180002ea5  cmovnz  r14d, eax
0x180002ea9  test    bl, bl
0x180002eab  js      loc_180003413
0x180002eb1  bt      ebx, 13h
0x180002eb5  jb      loc_18000341C
0x180002ebb  bt      ebx, 8
0x180002ebf  jb      loc_180003426
0x180002ec5  bt      ebx, 9
0x180002ec9  jb      loc_18000342F
0x180002ecf  bt      ebx, 0Ah
0x180002ed3  jb      loc_180003439
0x180002ed9  bt      ebx, 0Bh
0x180002edd  jb      loc_180003443
0x180002ee3  bt      ebx, 0Ch
0x180002ee7  jb      loc_18000344D
0x180002eed  bt      ebx, 0Dh
0x180002ef1  jb      loc_180003457
0x180002ef7  bt      ebx, 0Eh
0x180002efb  jb      loc_180003461
0x180002f01  bt      ebx, 0Fh
0x180002f05  jb      loc_18000346B
0x180002f0b  bt      ebx, 10h
0x180002f0f  jb      loc_180003475
0x180002f15  bt      ebx, 11h
0x180002f19  jb      loc_18000347F
0x180002f1f  bt      ebx, 12h
0x180002f23  jb      loc_180003489
0x180002f29  bt      ebx, 14h
0x180002f2d  jb      loc_180003493
0x180002f33  mov     eax, dword ptr cs:aRxcscflags+8; "ags$"
0x180002f39  lea     rcx, Source
0x180002f40  movsd   xmm0, qword ptr cs:aRxcscflags; "$RxCscFlags$"
0x180002f48  mov     edi, 5Ch ; '\'
0x180002f4d  mov     dword ptr [rbp+80h+var_58+8], eax
0x180002f50  movzx   eax, byte ptr cs:aRxcscflags+0Ch; ""
0x180002f57  mov     [rbp+80h+var_58+0Ch], al
0x180002f5a  mov     [rbp+80h+var_60], r10d
0x180002f5e  mov     [rbp+80h+var_5C], 40C00h
0x180002f65  movsd   qword ptr [rbp+80h+var_58], xmm0
0x180002f6a  mov     [rbp+80h+var_4B], r14d
0x180002f6e  test    bl, 1
0x180002f71  jz      short loc_180002FCF
0x180002f73  movzx   ecx, [rbp+80h+var_100.Length]
0x180002f77  mov     r8, [rbp+80h+var_100.Buffer]
0x180002f7b  cmp     cx, 2
0x180002f7f  jb      short loc_180002F9F
0x180002f81  cmp     di, [r8]
0x180002f85  jnz     short loc_180002F9F
0x180002f87  add     r8, 2
0x180002f8b  mov     eax, 0FFFEh
0x180002f90  add     cx, ax
0x180002f93  mov     [rbp+80h+var_100.MaximumLength], cx
0x180002f97  mov     [rbp+80h+var_100.Length], cx
0x180002f9b  mov     [rbp+80h+var_100.Buffer], r8
0x180002f9f  cmp     r10w, cx
0x180002fa3  jz      loc_1800030C3
0x180002fa9  mov     r9d, r10d
0x180002fac  movzx   edx, cx
0x180002faf  mov     eax, edx
0x180002fb1  shr     eax, 1
0x180002fb3  cmp     r9d, eax
0x180002fb6  jnb     loc_1800030C3
0x180002fbc  mov     eax, r9d
0x180002fbf  cmp     di, [r8+rax*2]
0x180002fc4  jz      loc_180003223
0x180002fca  inc     r9d
0x180002fcd  jmp     short loc_180002FAC
0x180002fcf  movups  xmm0, xmmword ptr [r15]
0x180002fd3  mov     ebx, r10d
0x180002fd6  movups  xmmword ptr [rbp+80h+var_100.Length], xmm0
0x180002fda  cmp     ebx, 4
0x180002fdd  jb      loc_18000349D
0x180002fe3  mov     edi, 0C000000Dh
0x180002fe8  mov     r15d, 376h
0x180002fee  lea     r14, WPP_GLOBAL_Control
0x180002ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ffc  mov     rbx, [rbp+80h+hMem+8]
0x180003000  test    rbx, rbx
0x180003003  jz      short loc_180003024
0x180003005  mov     rcx, rbx; hMem
0x180003008  call    cs:__imp_LocalFree
0x18000300e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003015  cmp     rcx, r14
0x180003018  jz      short loc_180003024
0x18000301a  test    byte ptr [rcx+44h], 40h
0x18000301e  jnz     loc_1800035CF
0x180003024  mov     rbx, [rsp+180h+var_120+8]
0x180003029  test    rbx, rbx
0x18000302c  jz      short loc_18000304D
0x18000302e  mov     rcx, rbx; hMem
0x180003031  call    cs:__imp_LocalFree
0x180003037  mov     rcx, cs:WPP_GLOBAL_Control
0x18000303e  cmp     rcx, r14
0x180003041  jz      short loc_180003056
0x180003043  test    byte ptr [rcx+44h], 40h
0x180003047  jnz     loc_1800035F6
0x18000304d  cmp     rcx, r14
0x180003050  jnz     loc_1800031FB
0x180003056  mov     eax, edi
0x180003058  mov     rcx, [rbp+80h+var_40]
0x18000305c  xor     rcx, rsp; StackCookie
0x18000305f  call    __security_check_cookie
0x180003064  mov     rbx, [rsp+180h+arg_8]
0x18000306c  add     rsp, 150h
0x180003073  pop     r15
0x180003075  pop     r14
0x180003077  pop     r13
0x180003079  pop     r12
0x18000307b  pop     rdi
0x18000307c  pop     rsi
0x18000307d  pop     rbp
0x18000307e  retn
0x18000307f  test    dword ptr [rcx+44h], 400h
0x180003086  jz      loc_180002E56
0x18000308c  cmp     byte ptr [rcx+41h], 4
0x180003090  jb      loc_180002E56
0x180003096  mov     eax, [rbp+80h+arg_28]
0x18000309c  mov     r9, rsi
0x18000309f  mov     rcx, [rcx+38h]
0x1800030a3  mov     dword ptr [rsp+180h+EaBuffer], edi
0x1800030a7  mov     [rsp+180h+CreateOptions], eax
0x1800030ab  mov     [rsp+180h+CreateDisposition], r13d
0x1800030b0  mov     [rsp+180h+ShareAccess], ebx
0x1800030b4  mov     qword ptr [rsp+180h+FileAttributes], r15
0x1800030b9  call    WPP_SF_qqZDDDD
0x1800030be  jmp     loc_180002E56
0x1800030c3  mov     ebx, 2
0x1800030c8  mov     qword ptr [rsp+180h+var_110.Length], 40002h
0x1800030d1  lea     r15, asc_18000B65C; "\\"
0x1800030d8  mov     [rbp+80h+hMem+8], r10
0x1800030dc  mov     [rsp+180h+var_110.Buffer], r15
0x1800030e1  mov     word ptr [rbp+80h+hMem], r10w
0x1800030e6  lea     eax, [rcx+rbx]
0x1800030e9  add     ax, [rbp+80h+Source.Length]
0x1800030ed  movzx   ecx, ax; uBytes
0x1800030f0  mov     word ptr [rbp+80h+hMem+2], cx
0x1800030f4  call    CscDriverpAllocate
0x1800030f9  mov     [rbp+80h+hMem+8], rax
0x1800030fd  test    rax, rax
0x180003100  jz      loc_18000351D
0x180003106  lea     rdx, [rbp+80h+Source]; Source
0x18000310a  lea     rcx, [rbp+80h+hMem]; Destination
0x18000310e  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003114  mov     edi, eax
0x180003116  cmp     bx, [rbp+80h+var_100.Length]
0x18000311a  ja      short loc_180003153
0x18000311c  mov     rax, [rsp+180h+var_110.Buffer]
0x180003121  movzx   ecx, [rbp+80h+Source.Length]
0x180003125  shr     rcx, 1
0x180003128  movzx   edx, word ptr [rax]
0x18000312b  mov     rax, [rbp+80h+Source.Buffer]
0x18000312f  cmp     [rax+rcx*2-2], dx
0x180003134  jz      short loc_180003143
0x180003136  mov     rax, [rbp+80h+var_100.Buffer]
0x18000313a  cmp     [rax], dx
0x18000313d  jnz     loc_1800033EA
0x180003143  lea     rdx, [rbp+80h+var_100]; Source
0x180003147  lea     rcx, [rbp+80h+hMem]; Destination
0x18000314b  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003151  mov     edi, eax
0x180003153  test    edi, edi
0x180003155  js      loc_180003522
0x18000315b  xor     eax, eax
0x18000315d  mov     qword ptr [rsp+180h+var_110.Length], 40002h
0x180003166  mov     word ptr [rsp+180h+var_120], ax
0x18000316b  movzx   eax, word ptr [rbp+80h+hMem]
0x18000316f  add     ax, bx
0x180003172  mov     [rsp+180h+var_110.Buffer], r15
0x180003177  add     ax, [rbp+80h+var_C8.Length]
0x18000317b  movzx   ecx, ax; uBytes
0x18000317e  mov     word ptr [rsp+180h+var_120+2], cx
0x180003183  mov     [rsp+180h+var_120+8], 0
0x18000318c  call    CscDriverpAllocate
0x180003191  mov     [rsp+180h+var_120+8], rax
0x180003196  test    rax, rax
0x180003199  jz      loc_18000354C
0x18000319f  lea     rdx, [rbp+80h+var_C8]; Source
0x1800031a3  lea     rcx, [rsp+180h+var_120]; Destination
0x1800031a8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800031ae  mov     edi, eax
0x1800031b0  cmp     bx, word ptr [rbp+80h+hMem]
0x1800031b4  ja      short loc_1800031EE
0x1800031b6  mov     rax, [rsp+180h+var_110.Buffer]
0x1800031bb  movzx   ecx, [rbp+80h+var_C8.Length]
0x1800031bf  shr     rcx, 1
0x1800031c2  movzx   edx, word ptr [rax]
0x1800031c5  mov     rax, [rbp+80h+var_C8.Buffer]
0x1800031c9  cmp     [rax+rcx*2-2], dx
0x1800031ce  jz      short loc_1800031DD
0x1800031d0  mov     rax, [rbp+80h+hMem+8]
0x1800031d4  cmp     [rax], dx
0x1800031d7  jnz     loc_1800033FE
0x1800031dd  lea     rdx, [rbp+80h+hMem]; Source
0x1800031e1  lea     rcx, [rsp+180h+var_120]; Destination
0x1800031e6  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800031ec  mov     edi, eax
0x1800031ee  test    edi, edi
0x1800031f0  js      loc_180003551
0x1800031f6  jmp     loc_1800032CD
0x1800031fb  test    dword ptr [rcx+44h], 400h
0x180003202  jz      loc_180003056
0x180003208  cmp     byte ptr [rcx+41h], 4
0x18000320c  jb      loc_180003056
0x180003212  test    rsi, rsi
0x180003215  jz      loc_18000361D
0x18000321b  mov     rax, [rsi]
0x18000321e  jmp     loc_18000361F
0x180003223  mov     ebx, 2
0x180003228  mov     qword ptr [rsp+180h+var_110.Length], 40002h
0x180003231  add     dx, bx
0x180003234  mov     [rsp+180h+var_120+8], r10
0x180003239  add     dx, cs:Source.Length
0x180003240  lea     r15, asc_18000B65C; "\\"
0x180003247  movzx   ecx, dx; uBytes
0x18000324a  mov     word ptr [rsp+180h+var_120+2], cx
0x18000324f  mov     [rsp+180h+var_110.Buffer], r15
0x180003254  mov     word ptr [rsp+180h+var_120], r10w
0x18000325a  call    CscDriverpAllocate
0x18000325f  mov     [rsp+180h+var_120+8], rax
0x180003264  test    rax, rax
0x180003267  jz      loc_1800034EB
0x18000326d  lea     rdx, Source; Source
0x180003274  lea     rcx, [rsp+180h+var_120]; Destination
0x180003279  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000327f  mov     edi, eax
0x180003281  cmp     bx, [rbp+80h+var_100.Length]
0x180003285  ja      short loc_1800032C5
0x180003287  mov     rax, [rsp+180h+var_110.Buffer]
0x18000328c  movzx   ecx, cs:Source.Length
0x180003293  shr     rcx, 1
0x180003296  movzx   edx, word ptr [rax]
0x180003299  mov     rax, cs:Source.Buffer
0x1800032a0  cmp     [rax+rcx*2-2], dx
0x1800032a5  jz      short loc_1800032B4
0x1800032a7  mov     rax, [rbp+80h+var_100.Buffer]
  ... truncated ...
```
