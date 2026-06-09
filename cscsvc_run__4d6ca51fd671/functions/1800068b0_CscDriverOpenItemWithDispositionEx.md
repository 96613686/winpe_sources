# CscDriverOpenItemWithDispositionEx

- ea: `0x1800068b0`
- end: `0x18000721b`
- name: `CscDriverOpenItemWithDispositionEx`
- size: `2411`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, void *, struct _UNICODE_STRING *, int, int, ULONG ShareAccess, ULONG CreateDisposition, int)`
- caller_count: `41`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001ad0`
- `0x180005030`
- `0x1800060a0`
- `0x1800074b0`
- `0x180007750`
- `0x180007a00`
- `0x180007b40`
- `0x180007e30`
- `0x18000801c`
- `0x180008310`
- `0x180008c00`
- `0x1800094c0`
- `0x18000a0d0`
- `0x18000a6f0`
- `0x180019c90`
- `0x18001b500`
- `0x18001bc74`
- `0x180024020`
- `0x18002a560`
- `0x18002a6dc`
- `0x180031d38`
- `0x180032e68`
- `0x18006c4dc`
- `0x18006c6ec`
- `0x18006c7a8`
- `0x18006cab4`
- `0x18006cc6c`
- `0x18006cd24`
- `0x18006ce00`
- `0x18006cf48`
- `0x18006d03c`
- `0x18006db00`
- `0x18006e144`
- `0x18006e6ec`
- `0x18006eb88`
- `0x18006f614`
- `0x18006f698`
- `0x180072f5c`
- `0x18007656c`
- `0x18007906c`
- `0x18008586c`

## callees

- `0x1800068b0`
- `0x180007280`
- `0x18000b580`
- `0x18000b8b0`
- `0x180039610`
- `0x18003e928`
- `0x18004af1c`
- `0x18004fef4`
- `0x1800715d8`
- `0x180071644`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x180006dfd`
- `ntdll!RtlPrefixUnicodeString` at `0x180006dfd`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006b41`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006b77`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006bd3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006c08`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006ef1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006f2e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000702b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000704b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000706c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006b41`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006b77`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006bd3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006c08`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006ef1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006f2e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000702b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000704b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000706c`
- `ntdll!NtClose` at `0x180006d84`
- `ntdll!NtClose` at `0x180006d84`
- `ntdll!NtCreateFile` at `0x180006c87`
- `ntdll!NtCreateFile` at `0x180006c87`
- `KERNEL32!LocalAlloc` at `0x180006b0c`
- `KERNEL32!LocalAlloc` at `0x180006ebb`
- `KERNEL32!LocalAlloc` at `0x180006b0c`
- `KERNEL32!LocalAlloc` at `0x180006ebb`
- `KERNEL32!LocalFree` at `0x180006cc0`
- `KERNEL32!LocalFree` at `0x180006cc0`

## pseudocode

```c
__int64 __fastcall CscDriverOpenItemWithDispositionEx(
        PHANDLE FileHandle,
        void *a2,
        struct _UNICODE_STRING *a3,
        int a4,
        int a5,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        int a8)
{
  UNICODE_STRING v8; // xmm1
  int v13; // ecx
  int v14; // edx
  ULONG v15; // ecx
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // edx
  int v31; // r13d
  ACCESS_MASK v32; // edi
  WCHAR *v33; // rbx
  CObjectMonitor *v34; // rcx
  NTSTATUS appended; // ebx
  int v36; // r14d
  NTSTATUS v37; // eax
  PWSTR v38; // rdi
  void *v40; // rcx
  void *v41; // rax
  unsigned int v42; // ebx
  UNICODE_STRING *v43; // r13
  USHORT Length; // r8
  WCHAR *Buffer; // r9
  unsigned int i; // eax
  WCHAR *v47; // rbx
  struct _UNICODE_STRING v48; // [rsp+60h] [rbp-A0h] BYREF
  SIZE_T v49; // [rsp+70h] [rbp-90h]
  UNICODE_STRING v50; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+88h] [rbp-78h] BYREF
  ULONG CreateOptions; // [rsp+98h] [rbp-68h]
  int v53; // [rsp+9Ch] [rbp-64h]
  UNICODE_STRING Source; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING v55; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  UNICODE_STRING v58; // [rsp+100h] [rbp+0h] BYREF
  int v59; // [rsp+110h] [rbp+10h]
  _DWORD EaBuffer[2]; // [rsp+118h] [rbp+18h] BYREF
  char v61[13]; // [rsp+120h] [rbp+20h] BYREF
  int v62; // [rsp+12Dh] [rbp+2Dh]

  v8 = *a3;
  *(_QWORD *)&Source.Length = 655368;
  *(_QWORD *)&v55.Length = 1572886;
  v50 = v8;
  Source.Buffer = L"\\.\\.";
  v55.Buffer = L"\\Device\\Csc";
  v48 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  Destination = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qqZDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)FileHandle,
      (char)a2,
      (__int64)a3,
      a4,
      a5,
      ShareAccess,
      a8);
  }
  if ( FileHandle )
    *FileHandle = 0;
  v13 = a8 | 0x20;
  if ( (a4 & 0x10) != 0 )
    v13 = a8;
  v14 = v13 | 1;
  if ( (a4 & 0x20) == 0 )
    v14 = v13;
  v15 = v14 | 0x40;
  if ( (a4 & 0x40) == 0 )
    v15 = v14;
  CreateOptions = v15;
  v16 = (2 * (a4 & 2)) | 8;
  if ( (a4 & 4) == 0 )
    v16 = 2 * (a4 & 2);
  v17 = v16 | 0x10;
  if ( (a4 & 8) == 0 )
    v17 = v16;
  v18 = v17 | 0x20;
  if ( (a4 & 0x80u) == 0 )
    v18 = v17;
  v19 = v18 | 0x40000;
  if ( (a4 & 0x80000) == 0 )
    v19 = v18;
  v20 = v19 | 0x40;
  if ( (a4 & 0x100) == 0 )
    v20 = v19;
  v21 = v20 | 0x80;
  if ( (a4 & 0x200) == 0 )
    v21 = v20;
  v22 = v21 | 0x100;
  if ( (a4 & 0x400) == 0 )
    v22 = v21;
  v23 = v22 | 0x200;
  if ( (a4 & 0x800) == 0 )
    v23 = v22;
  v24 = v23 | 0x400;
  if ( (a4 & 0x1000) == 0 )
    v24 = v23;
  v25 = v24 | 0x800;
  if ( (a4 & 0x2000) == 0 )
    v25 = v24;
  v26 = v25 | 0x2000;
  if ( (a4 & 0x4000) == 0 )
    v26 = v25;
  v27 = v26 | 0x4000;
  if ( (a4 & 0x8000) == 0 )
    v27 = v26;
  v28 = v27 | 0x8000;
  if ( (a4 & 0x10000) == 0 )
    v28 = v27;
  v29 = v28 | 0x10000;
  if ( (a4 & 0x20000) == 0 )
    v29 = v28;
  v30 = v29 | 0x20000;
  if ( (a4 & 0x40000) == 0 )
    v30 = v29;
  v31 = v30 | 0x80000;
  if ( (a4 & 0x100000) == 0 )
    v31 = v30;
  v53 = v31;
  EaBuffer[0] = 0;
  EaBuffer[1] = 265216;
  strcpy(v61, "$RxCscFlags$");
  v62 = v31;
  if ( !a2 )
  {
    if ( (a4 & 1) == 0 )
    {
      v42 = 0;
      v50 = *a3;
      while ( v42 < 4 )
      {
        v43 = &::Source + v42;
        if ( RtlPrefixUnicodeString(v43, a3, 1u) )
        {
          Length = v50.Length - v43->Length;
          Buffer = &v50.Buffer[(unsigned __int64)v43->Length >> 1];
          goto LABEL_83;
        }
        ++v42;
      }
      appended = -1073741811;
      v36 = 886;
      goto LABEL_60;
    }
    Length = v50.Length;
    Buffer = v50.Buffer;
    if ( v50.Length >= 2u && *v50.Buffer == 92 )
    {
      Buffer = v50.Buffer + 1;
      Length = v50.Length - 2;
LABEL_83:
      v50.MaximumLength = Length;
      v50.Length = Length;
      v50.Buffer = Buffer;
    }
    if ( Length )
    {
      for ( i = 0; i < Length >> 1; ++i )
      {
        if ( Buffer[i] == 92 )
        {
          *(_QWORD *)&v58.Length = 262146;
          v58.Buffer = (PWSTR)L"\\";
          v48.Buffer = 0;
          v48.Length = 0;
          v49 = (unsigned __int16)(::Source.Length + Length + 2);
          v48.MaximumLength = ::Source.Length + Length + 2;
          v47 = (WCHAR *)LocalAlloc(0, v49);
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              10,
              WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
              (unsigned int)v49,
              v47);
            v34 = WPP_GLOBAL_Control;
          }
          v48.Buffer = v47;
          if ( v47 )
          {
            appended = RtlAppendUnicodeStringToString(&v48, &::Source);
            if ( v50.Length >= 2u )
            {
              if ( ::Source.Buffer[((unsigned __int64)::Source.Length >> 1) - 1] != *v58.Buffer
                && *v50.Buffer != *v58.Buffer )
              {
                RtlAppendUnicodeStringToString(&v48, &v58);
              }
              appended = RtlAppendUnicodeStringToString(&v48, &v50);
            }
            if ( appended >= 0 )
            {
              v31 = v53;
              goto LABEL_44;
            }
            v34 = WPP_GLOBAL_Control;
          }
          else
          {
            appended = -1073741670;
          }
          if ( v48.Buffer )
          {
            CscDriverpFree(v48.Buffer);
            v34 = WPP_GLOBAL_Control;
            v48.Buffer = 0;
          }
          *(_DWORD *)&v48.Length = 0;
          v36 = 971;
          goto LABEL_61;
        }
      }
    }
    *(_QWORD *)&v58.Length = 262146;
    Destination.Buffer = 0;
    v58.Buffer = (PWSTR)L"\\";
    Destination.Length = 0;
    v49 = (unsigned __int16)(Source.Length + Length + 2);
    Destination.MaximumLength = Source.Length + Length + 2;
    v33 = (WCHAR *)LocalAlloc(0, v49);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        10,
        WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
        (unsigned int)v49,
        v33);
      v34 = WPP_GLOBAL_Control;
    }
    Destination.Buffer = v33;
    if ( v33 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( v50.Length >= 2u )
      {
        if ( Source.Buffer[((unsigned __int64)Source.Length >> 1) - 1] != *v58.Buffer && *v50.Buffer != *v58.Buffer )
          RtlAppendUnicodeStringToString(&Destination, &v58);
        appended = RtlAppendUnicodeStringToString(&Destination, &v50);
      }
      if ( appended >= 0 )
      {
        *(_QWORD *)&v58.Length = 262146;
        v48.Length = 0;
        v58.Buffer = (PWSTR)L"\\";
        v48.MaximumLength = v55.Length + Destination.Length + 2;
        v48.Buffer = (PWSTR)CscDriverpAllocate(v48.MaximumLength);
        if ( v48.Buffer )
        {
          appended = RtlAppendUnicodeStringToString(&v48, &v55);
          if ( Destination.Length >= 2u )
          {
            if ( v55.Buffer[((unsigned __int64)v55.Length >> 1) - 1] != *v58.Buffer
              && *Destination.Buffer != *v58.Buffer )
            {
              RtlAppendUnicodeStringToString(&v48, &v58);
            }
            appended = RtlAppendUnicodeStringToString(&v48, &Destination);
          }
          if ( appended >= 0 )
          {
            ObjectAttributes.Length = 48;
            v32 = a5 | 0x100000;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            goto LABEL_58;
          }
        }
        else
        {
          appended = -1073741670;
        }
        if ( v48.Buffer )
        {
          CscDriverpFree(v48.Buffer);
          v48.Buffer = 0;
        }
        *(_DWORD *)&v48.Length = 0;
        v36 = 946;
        goto LABEL_60;
      }
      v34 = WPP_GLOBAL_Control;
    }
    else
    {
      appended = -1073741670;
    }
    if ( Destination.Buffer )
    {
      CscDriverpFree(Destination.Buffer);
      v34 = WPP_GLOBAL_Control;
      Destination.Buffer = 0;
    }
    *(_DWORD *)&Destination.Length = 0;
    v36 = 934;
    goto LABEL_61;
  }
LABEL_44:
  v32 = a5 | 0x100000;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 64;
  if ( !a2 )
  {
LABEL_58:
    v31 = v53;
    ObjectAttributes.ObjectName = &v48;
    goto LABEL_59;
  }
  ObjectAttributes.ObjectName = a3;
LABEL_59:
  v36 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v37 = NtCreateFile(
          FileHandle,
          v32,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          ShareAccess,
          CreateDisposition,
          CreateOptions,
          EaBuffer,
          0x1Cu);
  appended = v37;
  if ( (v31 & 0x4002C) == 0 )
  {
LABEL_60:
    v34 = WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  if ( v37 != -1073741605 )
  {
    if ( v37 >= 0 )
    {
      v40 = *FileHandle;
      v59 = 0;
      v49 = 8;
      v58 = 0;
      CreateOptions = 0;
      if ( (int)CscDriverpFsControlEx(v40, 8u, &v58, 0x14u) >= 0 && (v31 & 8) != 0 && *(_DWORD *)&v58.Length != 2 )
      {
        NtClose(*FileHandle);
        *FileHandle = 0;
        appended = -1073740768;
      }
    }
    goto LABEL_60;
  }
  appended = -1073741766;
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      17,
      WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
      3221225691LL,
      -1073741766);
    v34 = WPP_GLOBAL_Control;
  }
LABEL_61:
  if ( Destination.Buffer )
  {
    CscDriverpFree(Destination.Buffer);
    v34 = WPP_GLOBAL_Control;
  }
  v38 = v48.Buffer;
  if ( v48.Buffer )
  {
    LocalFree(v48.Buffer);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
      return (unsigned int)appended;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, v38);
      v34 = WPP_GLOBAL_Control;
    }
  }
  if ( v34 != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)v34 + 17) & 0x400) != 0
    && *((_BYTE *)v34 + 65) >= 4u )
  {
    if ( FileHandle )
      v41 = *FileHandle;
    else
      v41 = 0;
    WPP_SF_qqDD(
      *((_QWORD *)v34 + 7),
      18,
      WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
      FileHandle,
      v41,
      appended,
      v36);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800068b0  mov     [rsp-8+arg_18], rbx
0x1800068b5  push    rbp
0x1800068b6  push    rsi
0x1800068b7  push    rdi
0x1800068b8  push    r12
0x1800068ba  push    r13
0x1800068bc  push    r14
0x1800068be  push    r15
0x1800068c0  lea     rbp, [rsp-40h]
0x1800068c5  sub     rsp, 140h
0x1800068cc  mov     rax, cs:__security_cookie
0x1800068d3  xor     rax, rsp
0x1800068d6  mov     [rbp+70h+var_38], rax
0x1800068da  movups  xmm1, xmmword ptr [r8]
0x1800068de  mov     qword ptr [rbp+70h+Source.Length], 0A0008h
0x1800068e6  xor     eax, eax
0x1800068e8  xorps   xmm0, xmm0
0x1800068eb  mov     qword ptr [rbp+70h+var_C0.Length], 180016h
0x1800068f3  lea     rax, asc_18008FC68; "\\.\\."
0x1800068fa  mov     ebx, r9d
0x1800068fd  movups  xmmword ptr [rsp+170h+var_F8.Length], xmm1
0x180006902  mov     [rbp+70h+Source.Buffer], rax
0x180006906  lea     rax, aDeviceCsc; "\\Device\\Csc"
0x18000690d  xorps   xmm1, xmm1
0x180006910  mov     [rbp+70h+var_C0.Buffer], rax
0x180006914  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x180006918  mov     r14, r8
0x18000691b  mov     r15, rdx
0x18000691e  movups  xmmword ptr [rsp+170h+var_110.Length], xmm1
0x180006923  mov     rsi, rcx
0x180006926  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x18000692a  movups  xmmword ptr [rbp+70h+ObjectAttributes+1Ch], xmm0
0x18000692e  movups  xmmword ptr [rbp+70h+IoStatusBlock], xmm0
0x180006932  movups  xmmword ptr [rbp+70h+Destination.Length], xmm0
0x180006936  mov     rcx, cs:WPP_GLOBAL_Control
0x18000693d  lea     rax, WPP_GLOBAL_Control
0x180006944  mov     r13d, [rbp+70h+arg_38]
0x18000694b  mov     r12d, [rbp+70h+arg_28]
0x180006952  mov     edi, [rbp+70h+arg_20]
0x180006958  cmp     rcx, rax
0x18000695b  jz      short loc_18000696A
0x18000695d  test    dword ptr [rcx+44h], 400h
0x180006964  jnz     loc_1800070D6
0x18000696a  xor     r10d, r10d
0x18000696d  test    rsi, rsi
0x180006970  jz      short loc_180006975
0x180006972  mov     [rsi], r10
0x180006975  mov     ecx, r13d
0x180006978  or      ecx, 20h
0x18000697b  test    bl, 10h
0x18000697e  cmovnz  ecx, r13d
0x180006982  mov     edx, ecx
0x180006984  or      edx, 1
0x180006987  test    bl, 20h
0x18000698a  cmovz   edx, ecx
0x18000698d  mov     ecx, edx
0x18000698f  or      ecx, 40h
0x180006992  test    bl, 40h
0x180006995  cmovz   ecx, edx
0x180006998  mov     [rbp+70h+var_D8], ecx
0x18000699b  mov     ecx, ebx
0x18000699d  and     ecx, 2
0x1800069a0  add     ecx, ecx
0x1800069a2  mov     edx, ecx
0x1800069a4  or      edx, 8
0x1800069a7  test    bl, 4
0x1800069aa  cmovz   edx, ecx
0x1800069ad  mov     ecx, edx
0x1800069af  or      ecx, 10h
0x1800069b2  test    bl, 8
0x1800069b5  cmovz   ecx, edx
0x1800069b8  mov     edx, ecx
0x1800069ba  or      edx, 20h
0x1800069bd  test    bl, 80h
0x1800069c0  cmovz   edx, ecx
0x1800069c3  mov     ecx, edx
0x1800069c5  bts     ecx, 12h
0x1800069c9  bt      ebx, 13h
0x1800069cd  cmovnb  ecx, edx
0x1800069d0  mov     edx, ecx
0x1800069d2  or      edx, 40h
0x1800069d5  bt      ebx, 8
0x1800069d9  cmovnb  edx, ecx
0x1800069dc  mov     ecx, edx
0x1800069de  bts     ecx, 7
0x1800069e2  bt      ebx, 9
0x1800069e6  cmovnb  ecx, edx
0x1800069e9  mov     edx, ecx
0x1800069eb  bts     edx, 8
0x1800069ef  bt      ebx, 0Ah
0x1800069f3  cmovnb  edx, ecx
0x1800069f6  mov     ecx, edx
0x1800069f8  bts     ecx, 9
0x1800069fc  bt      ebx, 0Bh
0x180006a00  cmovnb  ecx, edx
0x180006a03  mov     edx, ecx
0x180006a05  bts     edx, 0Ah
0x180006a09  bt      ebx, 0Ch
0x180006a0d  cmovnb  edx, ecx
0x180006a10  mov     ecx, edx
0x180006a12  bts     ecx, 0Bh
0x180006a16  bt      ebx, 0Dh
0x180006a1a  cmovnb  ecx, edx
0x180006a1d  mov     edx, ecx
0x180006a1f  bts     edx, 0Dh
0x180006a23  bt      ebx, 0Eh
0x180006a27  cmovnb  edx, ecx
0x180006a2a  mov     ecx, edx
0x180006a2c  bts     ecx, 0Eh
0x180006a30  bt      ebx, 0Fh
0x180006a34  cmovnb  ecx, edx
0x180006a37  mov     edx, ecx
0x180006a39  bts     edx, 0Fh
0x180006a3d  bt      ebx, 10h
0x180006a41  cmovnb  edx, ecx
0x180006a44  mov     ecx, edx
0x180006a46  bts     ecx, 10h
0x180006a4a  bt      ebx, 11h
0x180006a4e  cmovnb  ecx, edx
0x180006a51  mov     edx, ecx
0x180006a53  bts     edx, 11h
0x180006a57  bt      ebx, 12h
0x180006a5b  cmovnb  edx, ecx
0x180006a5e  mov     r13d, edx
0x180006a61  bts     r13d, 13h
0x180006a66  bt      ebx, 14h
0x180006a6a  cmovnb  r13d, edx
0x180006a6e  mov     [rbp+70h+var_D4], r13d
0x180006a72  mov     eax, dword ptr cs:aRxcscflags+8; "ags$"
0x180006a78  movsd   xmm0, qword ptr cs:aRxcscflags; "$RxCscFlags$"
0x180006a80  mov     dword ptr [rbp+70h+var_50+8], eax
0x180006a83  movzx   eax, byte ptr cs:aRxcscflags+0Ch; ""
0x180006a8a  mov     [rbp+70h+var_50+0Ch], al
0x180006a8d  mov     [rbp+70h+var_58], r10d
0x180006a91  mov     [rbp+70h+var_54], 40C00h
0x180006a98  movsd   qword ptr [rbp+70h+var_50], xmm0
0x180006a9d  mov     [rbp+70h+var_43], r13d
0x180006aa1  test    r15, r15
0x180006aa4  jz      loc_180006DBF
0x180006aaa  bts     edi, 14h
0x180006aae  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x180006ab5  mov     [rbp+70h+ObjectAttributes.RootDirectory], r15
0x180006ab9  mov     [rbp+70h+ObjectAttributes.Attributes], 40h ; '@'
0x180006ac0  test    r15, r15
0x180006ac3  jz      loc_180006C31
0x180006ac9  mov     [rbp+70h+ObjectAttributes.ObjectName], r14
0x180006acd  jmp     loc_180006C3E
0x180006ad2  mov     r13d, 2
0x180006ad8  mov     qword ptr [rbp+70h+var_70.Length], 40002h
0x180006ae0  lea     r14, Src; "\\"
0x180006ae7  mov     [rbp+70h+Destination.Buffer], r10
0x180006aeb  xor     ecx, ecx; uFlags
0x180006aed  mov     [rbp+70h+var_70.Buffer], r14
0x180006af1  mov     [rbp+70h+Destination.Length], r10w
0x180006af6  lea     eax, [r8+r13]
0x180006afa  add     ax, [rbp+70h+Source.Length]
0x180006afe  movzx   eax, ax
0x180006b01  mov     edx, eax; uBytes
0x180006b03  mov     [rsp+170h+var_100], rax
0x180006b08  mov     [rbp+70h+Destination.MaximumLength], ax
0x180006b0c  call    cs:__imp_LocalAlloc
0x180006b12  mov     rbx, rax
0x180006b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b1c  lea     rax, WPP_GLOBAL_Control
0x180006b23  cmp     rcx, rax
0x180006b26  jnz     loc_180006FB2
0x180006b2c  mov     [rbp+70h+Destination.Buffer], rbx
0x180006b30  test    rbx, rbx
0x180006b33  jz      loc_18000714F
0x180006b39  lea     rdx, [rbp+70h+Source]; Source
0x180006b3d  lea     rcx, [rbp+70h+Destination]; Destination
0x180006b41  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006b47  mov     ebx, eax
0x180006b49  cmp     r13w, [rsp+170h+var_F8.Length]
0x180006b4f  ja      short loc_180006B7F
0x180006b51  mov     rax, [rbp+70h+var_70.Buffer]
0x180006b55  movzx   ecx, [rbp+70h+Source.Length]
0x180006b59  shr     rcx, 1
0x180006b5c  movzx   edx, word ptr [rax]
0x180006b5f  mov     rax, [rbp+70h+Source.Buffer]
0x180006b63  cmp     [rax+rcx*2-2], dx
0x180006b68  jnz     loc_180007036
0x180006b6e  lea     rdx, [rsp+170h+var_F8]; Source
0x180006b73  lea     rcx, [rbp+70h+Destination]; Destination
0x180006b77  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006b7d  mov     ebx, eax
0x180006b7f  test    ebx, ebx
0x180006b81  js      loc_180007156
0x180006b87  xor     eax, eax
0x180006b89  mov     qword ptr [rbp+70h+var_70.Length], 40002h
0x180006b91  mov     [rsp+170h+var_110.Length], ax
0x180006b96  movzx   eax, [rbp+70h+Destination.Length]
0x180006b9a  add     ax, r13w
0x180006b9e  mov     [rbp+70h+var_70.Buffer], r14
0x180006ba2  add     ax, [rbp+70h+var_C0.Length]
0x180006ba6  movzx   ecx, ax; uBytes
0x180006ba9  mov     [rsp+170h+var_110.MaximumLength], cx
0x180006bae  mov     [rsp+170h+var_110.Buffer], 0
0x180006bb7  call    CscDriverpAllocate
0x180006bbc  mov     [rsp+170h+var_110.Buffer], rax
0x180006bc1  test    rax, rax
0x180006bc4  jz      loc_18000718E
0x180006bca  lea     rdx, [rbp+70h+var_C0]; Source
0x180006bce  lea     rcx, [rsp+170h+var_110]; Destination
0x180006bd3  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006bd9  mov     ebx, eax
0x180006bdb  cmp     r13w, [rbp+70h+Destination.Length]
0x180006be0  ja      short loc_180006C10
0x180006be2  mov     rax, [rbp+70h+var_70.Buffer]
0x180006be6  movzx   ecx, [rbp+70h+var_C0.Length]
0x180006bea  shr     rcx, 1
0x180006bed  movzx   edx, word ptr [rax]
0x180006bf0  mov     rax, [rbp+70h+var_C0.Buffer]
0x180006bf4  cmp     [rax+rcx*2-2], dx
0x180006bf9  jnz     loc_180007056
0x180006bff  lea     rdx, [rbp+70h+Destination]; Source
0x180006c03  lea     rcx, [rsp+170h+var_110]; Destination
0x180006c08  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006c0e  mov     ebx, eax
0x180006c10  test    ebx, ebx
0x180006c12  js      loc_180007193
0x180006c18  xor     r10d, r10d
0x180006c1b  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x180006c22  bts     edi, 14h
0x180006c26  mov     [rbp+70h+ObjectAttributes.RootDirectory], r15
0x180006c2a  mov     [rbp+70h+ObjectAttributes.Attributes], 40h ; '@'
0x180006c31  mov     r13d, [rbp+70h+var_D4]
0x180006c35  lea     rax, [rsp+170h+var_110]
0x180006c3a  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x180006c3e  mov     [rsp+170h+EaLength], 1Ch; EaLength
0x180006c46  lea     rax, [rbp+70h+var_58]
0x180006c4a  mov     [rsp+170h+EaBuffer], rax; EaBuffer
0x180006c4f  lea     r9, [rbp+70h+IoStatusBlock]; IoStatusBlock
0x180006c53  mov     eax, [rbp+70h+var_D8]
0x180006c56  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x180006c5a  mov     [rsp+170h+CreateOptions], eax; CreateOptions
0x180006c5e  xorps   xmm0, xmm0
0x180006c61  mov     eax, [rbp+70h+arg_30]
0x180006c67  mov     edx, edi; DesiredAccess
0x180006c69  mov     [rsp+170h+CreateDisposition], eax; CreateDisposition
0x180006c6d  mov     rcx, rsi; FileHandle
0x180006c70  mov     [rsp+170h+ShareAccess], r12d; ShareAccess
0x180006c75  mov     r14d, r10d
0x180006c78  mov     [rsp+170h+FileAttributes], r10d; FileAttributes
0x180006c7d  mov     [rsp+170h+AllocationSize], r10; AllocationSize
0x180006c82  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006c87  call    cs:__imp_NtCreateFile
0x180006c8d  mov     ebx, eax
0x180006c8f  test    r13d, 4002Ch
0x180006c96  jnz     short loc_180006D0E
0x180006c98  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c9f  lea     r15, WPP_GLOBAL_Control
0x180006ca6  mov     rax, [rbp+70h+Destination.Buffer]
0x180006caa  test    rax, rax
0x180006cad  jnz     loc_180007001
0x180006cb3  mov     rdi, [rsp+170h+var_110.Buffer]
0x180006cb8  test    rdi, rdi
0x180006cbb  jz      short loc_180006CDC
0x180006cbd  mov     rcx, rdi; hMem
0x180006cc0  call    cs:__imp_LocalFree
0x180006cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ccd  cmp     rcx, r15
0x180006cd0  jz      short loc_180006CE5
0x180006cd2  test    byte ptr [rcx+44h], 40h
0x180006cd6  jnz     loc_1800071C0
0x180006cdc  cmp     rcx, r15
0x180006cdf  jnz     loc_180006D97
0x180006ce5  mov     eax, ebx
0x180006ce7  mov     rcx, [rbp+70h+var_38]
0x180006ceb  xor     rcx, rsp; StackCookie
0x180006cee  call    __security_check_cookie
0x180006cf3  mov     rbx, [rsp+170h+arg_18]
0x180006cfb  add     rsp, 140h
0x180006d02  pop     r15
0x180006d04  pop     r14
0x180006d06  pop     r13
0x180006d08  pop     r12
0x180006d0a  pop     rdi
0x180006d0b  pop     rsi
0x180006d0c  pop     rbp
0x180006d0d  retn
0x180006d0e  cmp     eax, 0C00000DBh
0x180006d13  jz      loc_180007077
0x180006d19  test    eax, eax
0x180006d1b  js      loc_180006C98
0x180006d21  mov     rcx, [rsi]; FileHandle
0x180006d24  lea     r9, [rsp+170h+var_100]
0x180006d29  xor     eax, eax
0x180006d2b  mov     [rsp+170h+ShareAccess], 14h; ULONG
0x180006d33  mov     [rbp+70h+var_60], eax
0x180006d36  lea     r8, [rbp+70h+var_D8]
0x180006d3a  lea     rax, [rbp+70h+var_70]
0x180006d3e  mov     [rsp+170h+var_100], 8
0x180006d47  xorps   xmm0, xmm0
0x180006d4a  mov     qword ptr [rsp+170h+FileAttributes], rax; PVOID
0x180006d4f  xor     edi, edi
0x180006d51  mov     dword ptr [rsp+170h+AllocationSize], 8; ULONG
0x180006d59  movups  xmmword ptr [rbp+70h+var_70.Length], xmm0
0x180006d5d  mov     [rbp+70h+var_D8], edi
0x180006d60  call    CscDriverpFsControlEx
  ... truncated ...
```
