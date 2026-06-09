# GetVolumePathNameInternalW

- ea: `0x1800464e0`
- end: `0x180046db5`
- name: `GetVolumePathNameInternalW`
- size: `2261`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800462f0`
- `0x1800464e0`

## callees

- `0x1800134a0`
- `0x1800464e0`
- `0x180047580`
- `0x180047c90`
- `0x1800481f0`
- `0x18006e590`
- `0x18012d119`
- `0x180188eb9`
- `0x180188ec5`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180046b6e`
- `ntdll!RtlFreeUnicodeString` at `0x180046b6e`
- `ntdll!RtlInitUnicodeString` at `0x18004661c`
- `ntdll!RtlInitUnicodeString` at `0x1800468ab`
- `ntdll!RtlInitUnicodeString` at `0x18004698c`
- `ntdll!RtlInitUnicodeString` at `0x180046a89`
- `ntdll!RtlInitUnicodeString` at `0x180046af2`
- `ntdll!RtlInitUnicodeString` at `0x180046b03`
- `ntdll!RtlInitUnicodeString` at `0x18004661c`
- `ntdll!RtlInitUnicodeString` at `0x1800468ab`
- `ntdll!RtlInitUnicodeString` at `0x18004698c`
- `ntdll!RtlInitUnicodeString` at `0x180046a89`
- `ntdll!RtlInitUnicodeString` at `0x180046af2`
- `ntdll!RtlInitUnicodeString` at `0x180046b03`
- `ntdll!_wcsicmp` at `0x1800466fc`
- `ntdll!_wcsicmp` at `0x18004670e`
- `ntdll!_wcsicmp` at `0x1800466fc`
- `ntdll!_wcsicmp` at `0x18004670e`
- `ntdll!RtlSetLastWin32Error` at `0x180046946`
- `ntdll!RtlSetLastWin32Error` at `0x180046ade`
- `ntdll!RtlSetLastWin32Error` at `0x180046b27`
- `ntdll!RtlSetLastWin32Error` at `0x180046c44`
- `ntdll!RtlSetLastWin32Error` at `0x180046ca6`
- `ntdll!RtlSetLastWin32Error` at `0x180046d4f`
- `ntdll!RtlSetLastWin32Error` at `0x180046d7a`
- `ntdll!RtlSetLastWin32Error` at `0x180046946`
- `ntdll!RtlSetLastWin32Error` at `0x180046ade`
- `ntdll!RtlSetLastWin32Error` at `0x180046b27`
- `ntdll!RtlSetLastWin32Error` at `0x180046c44`
- `ntdll!RtlSetLastWin32Error` at `0x180046ca6`
- `ntdll!RtlSetLastWin32Error` at `0x180046d4f`
- `ntdll!RtlSetLastWin32Error` at `0x180046d7a`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800466c3`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800466c3`
- `ntdll!RtlFreeHeap` at `0x1800467d2`
- `ntdll!RtlFreeHeap` at `0x180046841`
- `ntdll!RtlFreeHeap` at `0x18004691e`
- `ntdll!RtlFreeHeap` at `0x18004693b`
- `ntdll!RtlFreeHeap` at `0x180046a35`
- `ntdll!RtlFreeHeap` at `0x180046acc`
- `ntdll!RtlFreeHeap` at `0x180046c07`
- `ntdll!RtlFreeHeap` at `0x180046d44`
- `ntdll!RtlFreeHeap` at `0x180046d99`
- `ntdll!RtlFreeHeap` at `0x1800467d2`
- `ntdll!RtlFreeHeap` at `0x180046841`
- `ntdll!RtlFreeHeap` at `0x18004691e`
- `ntdll!RtlFreeHeap` at `0x18004693b`
- `ntdll!RtlFreeHeap` at `0x180046a35`
- `ntdll!RtlFreeHeap` at `0x180046acc`
- `ntdll!RtlFreeHeap` at `0x180046c07`
- `ntdll!RtlFreeHeap` at `0x180046d44`
- `ntdll!RtlFreeHeap` at `0x180046d99`
- `ntdll!RtlGetFullPathName_UEx` at `0x180046564`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800465ef`
- `ntdll!RtlGetFullPathName_UEx` at `0x180046564`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800465ef`
- `ntdll!RtlAllocateHeap` at `0x1800465b6`
- `ntdll!RtlAllocateHeap` at `0x180046679`
- `ntdll!RtlAllocateHeap` at `0x180046b9b`
- `ntdll!RtlAllocateHeap` at `0x1800465b6`
- `ntdll!RtlAllocateHeap` at `0x180046679`
- `ntdll!RtlAllocateHeap` at `0x180046b9b`

## pseudocode

```c
__int64 __fastcall GetVolumePathNameInternalW(unsigned int a1, WCHAR *a2, _WORD *a3, unsigned int a4)
{
  NTSTATUS FullPathName_UEx; // eax
  unsigned int v7; // eax
  unsigned int v8; // esi
  SIZE_T v9; // rbx
  WCHAR *Heap; // rax
  WCHAR *v11; // r12
  NTSTATUS v12; // eax
  USHORT Length; // cx
  _WORD *v14; // rax
  _WORD *v15; // r15
  WCHAR v16; // si
  PWSTR Buffer; // rdi
  BOOL v18; // r14d
  NTSTATUS inited; // eax
  UINT DriveTypeW; // ebx
  int v21; // esi
  int v22; // eax
  __int64 v23; // rax
  bool v24; // zf
  USHORT v25; // dx
  unsigned int v26; // ebx
  unsigned int v27; // r10d
  __int64 v29; // rcx
  WCHAR *v30; // r8
  WCHAR v31; // cx
  WCHAR v32; // ax
  WCHAR v33; // cx
  unsigned int VolumePathNameInternalW; // ebx
  unsigned int v35; // ebx
  SIZE_T v36; // r8
  UINT v37; // ebx
  _WORD *v38; // rax
  _WORD *v39; // rdi
  __int64 v40; // r9
  WCHAR v41; // cx
  WCHAR v42; // ax
  __int64 v43; // r8
  RTL_PATH_TYPE InputPathType; // [rsp+30h] [rbp-59h] BYREF
  int v45; // [rsp+34h] [rbp-55h]
  unsigned int v46; // [rsp+38h] [rbp-51h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v48; // [rsp+50h] [rbp-39h]
  PWSTR FilePart; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING v51; // [rsp+70h] [rbp-19h] BYREF
  WCHAR v52; // [rsp+80h] [rbp-9h] BYREF
  int v53; // [rsp+82h] [rbp-7h]
  __int16 v54; // [rsp+86h] [rbp-3h]

  v48 = a1;
  FilePart = 0;
  v46 = a4;
  DestinationString = 0;
  v51 = 0;
  if ( a1 >= 0x40 )
  {
    RtlSetLastWin32Error(0xA1u);
    return 0;
  }
  if ( !a2 || !a3 || !a4 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  *a3 = 0;
  InputPathType = RtlPathTypeUnknown;
  FullPathName_UEx = RtlGetFullPathName_UEx(a2, 0, 0, 0, &InputPathType);
  if ( FullPathName_UEx < 0 )
    BaseSetLastNTError((unsigned int)FullPathName_UEx);
  v7 = (unsigned int)InputPathType >> 1;
  if ( !((unsigned int)InputPathType >> 1) )
    return 0;
  v8 = v7 + 10;
  v9 = 2LL * (v7 + 10);
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v9);
  v11 = Heap;
  if ( !Heap )
  {
    RtlSetLastWin32Error(8u);
    return 0;
  }
  memset_0(Heap, 0, v9);
  InputPathType = RtlPathTypeUnknown;
  v12 = RtlGetFullPathName_UEx(a2, 2 * v8, v11, &FilePart, &InputPathType);
  if ( v12 < 0 )
    BaseSetLastNTError((unsigned int)v12);
  if ( (InputPathType & 0xFFFFFFFE) == 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, v11);
  Length = DestinationString.Length;
  if ( DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92 )
  {
    DestinationString.Length += 2;
    DestinationString.Buffer[((unsigned __int64)(unsigned __int16)(Length + 2) >> 1) - 1] = 92;
    DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
  }
  v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
  v15 = v14;
  if ( !v14 )
  {
    v30 = v11;
    goto LABEL_51;
  }
  memset_0(v14, 0, 0x4000u);
  FilePart = 0;
  v16 = 0;
  InputPathType = RtlPathTypeUnknown;
  while ( 1 )
  {
    Buffer = DestinationString.Buffer;
    v45 = 1;
    UnicodeString = 0;
    v18 = 1;
    inited = RtlInitUnicodeStringEx(&UnicodeString, DestinationString.Buffer);
    if ( inited < 0 )
    {
      BaseSetLastNTError((unsigned int)inited);
      goto LABEL_26;
    }
    if ( UnicodeString.Buffer[((unsigned __int64)UnicodeString.Length >> 1) - 1] != 92 )
    {
      BaseSetLastNTError(3221225523LL);
      goto LABEL_26;
    }
    DriveTypeW = GetDriveTypeW(Buffer);
    v21 = _wcsicmp(Buffer, L"\\\\");
    v22 = _wcsicmp(Buffer, L"\\\\?\\UNC\\");
    if ( DriveTypeW == 4 && v21 && v22 )
    {
      if ( (unsigned int)BasepGetVolumeNameFromReparsePoint(Buffer, v15, 0x2000u) )
        goto LABEL_42;
      RtlSetLastWin32Error(0x57u);
      v18 = v45;
      goto LABEL_113;
    }
    if ( UnicodeString.Length == 6 )
    {
      if ( UnicodeString.Buffer[1] != 58 )
        break;
      if ( (unsigned int)GetVolumeNameForRoot(Buffer, (__int64)v15, 0x2000u) )
        goto LABEL_32;
      goto LABEL_46;
    }
    if ( UnicodeString.Length != 14 )
      break;
    if ( *UnicodeString.Buffer != 92 )
      break;
    if ( UnicodeString.Buffer[1] != 92 )
      break;
    v31 = UnicodeString.Buffer[2];
    if ( v31 != 46 && v31 != 63 )
      break;
    if ( UnicodeString.Buffer[3] != 92 || UnicodeString.Buffer[5] != 58 )
      break;
    if ( (unsigned int)GetVolumeNameForRoot(Buffer + 4, (__int64)v15, 0x2000u) )
      goto LABEL_32;
LABEL_46:
    v18 = 0;
LABEL_113:
    *v15 = 0;
LABEL_24:
    v16 = InputPathType;
    if ( !v18 )
      v18 = NtCurrentTeb()->LastErrorValue == 5;
LABEL_26:
    if ( !*v15 )
      goto LABEL_27;
    v32 = *v11;
    if ( *v11 == 92 && v11[1] == 92 )
    {
      v41 = v11[2];
      if ( v41 != 63 && v41 != 46 )
        goto LABEL_27;
      if ( v11[3] != 92 || v11[5] != 58 )
        goto LABEL_27;
    }
    v33 = v11[1];
    if ( v33 != 58 )
    {
      if ( v32 == 92 && v33 == 92 )
      {
        v42 = v11[2];
        if ( (v42 == 63 || v42 == 46) && v11[3] == 92 && v11[5] == 58 )
        {
          v32 = v11[4];
          goto LABEL_80;
        }
      }
LABEL_67:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
      if ( *v15 == 92 && v15[1] == 63 && v15[2] == 63 && v15[3] == 92 )
      {
        if ( v15[4] && v15[5] == 58 )
        {
          RtlInitUnicodeString(&DestinationString, v15);
          memmove_0(v15, v15 + 4, DestinationString.Length - 6LL);
        }
        else
        {
          v15[1] = 92;
        }
        VolumePathNameInternalW = GetVolumePathNameInternalW(v48 + 1, v15, a3, v46);
        goto LABEL_75;
      }
      RtlInitUnicodeString(&DestinationString, v15);
      RtlInitUnicodeString(&v51, L"\\\\?\\GLOBALROOT");
      v35 = DestinationString.Length + v51.Length;
      v36 = (unsigned __int16)(DestinationString.Length + v51.Length + 2);
      if ( (unsigned int)v36 < v35 || (unsigned __int16)v36 < (unsigned __int16)v35 )
      {
        RtlSetLastWin32Error(0x6Fu);
        return 0;
      }
      v38 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v36);
      v39 = v38;
      if ( v38 )
      {
        memcpy_0(v38, v51.Buffer, v51.Length);
        memcpy_0((char *)v39 + v51.Length, DestinationString.Buffer, DestinationString.Length);
        v40 = v46;
        v39[(unsigned __int64)(unsigned __int16)v35 >> 1] = 0;
        VolumePathNameInternalW = GetVolumePathNameInternalW(v48 + 1, v39, a3, v40);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v39);
LABEL_75:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        return VolumePathNameInternalW;
      }
      v30 = v15;
LABEL_51:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
      RtlSetLastWin32Error(8u);
      return 0;
    }
LABEL_80:
    v52 = v32;
    v53 = 6029370;
    v54 = 0;
    UnicodeString = 0;
    if ( !(unsigned int)Basep8BitStringToDynamicUnicodeString(&UnicodeString, &v52) )
      goto LABEL_67;
    v37 = GetDriveTypeW(UnicodeString.Buffer);
    RtlFreeUnicodeString(&UnicodeString);
    if ( v37 != 4 )
      goto LABEL_67;
LABEL_27:
    if ( !v18 && FilePart )
    {
      *FilePart = v16;
      RtlInitUnicodeString(&DestinationString, v11);
      goto LABEL_32;
    }
    if ( DestinationString.Length <= 2u )
      goto LABEL_32;
    v23 = (DestinationString.Length >> 1) - 2;
    if ( DestinationString.Length >> 1 == 2 )
      goto LABEL_32;
    while ( DestinationString.Buffer[v23] != 92 )
    {
      v24 = (_DWORD)v23 == 1;
      v23 = (unsigned int)(v23 - 1);
      if ( v24 )
        goto LABEL_32;
    }
    v29 = (unsigned int)(v23 + 1);
    if ( v18 )
    {
      FilePart = &DestinationString.Buffer[v29];
      v16 = DestinationString.Buffer[(unsigned int)(v23 + 1)];
      InputPathType = v16;
      *FilePart = 0;
    }
    else
    {
      DestinationString.Buffer[v29] = 0;
    }
    RtlInitUnicodeString(&DestinationString, v11);
  }
  if ( (unsigned int)GetVolumeNameForRoot(Buffer, (__int64)v15, 0x2000u) )
    goto LABEL_32;
  if ( !(unsigned int)BasepGetVolumeNameFromReparsePoint(Buffer, v15, 0x2000u) )
  {
    v18 = v45;
    goto LABEL_24;
  }
  GetVolumeNameForRoot(v15, (__int64)v15, 0x2000u);
LABEL_42:
  v18 = v45;
LABEL_32:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( v18 || FilePart )
  {
    v25 = DestinationString.Length;
    v26 = 0;
    v27 = v46;
    if ( DestinationString.Length >= 2u )
    {
      v26 = DestinationString.Length >> 1;
      if ( v26 )
      {
        if ( v26 + 1 > v46 )
        {
          v43 = v26 - 1;
          if ( DestinationString.Buffer[v43] == 92 )
          {
            --v26;
            DestinationString.Buffer[v43] = 0;
            v25 = DestinationString.Length - 2;
            DestinationString.Length -= 2;
          }
        }
      }
    }
    if ( 2 * (unsigned __int64)v27 >= (unsigned __int64)v25 + 2 )
    {
      memcpy_0(a3, DestinationString.Buffer, v25);
      a3[v26] = 0;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
      return 1;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    RtlSetLastWin32Error(0xCEu);
  }
  else
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x1800464e0  push    rbp
0x1800464e2  push    rdi
0x1800464e3  push    r13
0x1800464e5  push    r14
0x1800464e7  lea     rbp, [rsp-3Fh]
0x1800464ec  sub     rsp, 0C8h
0x1800464f3  mov     rax, cs:__security_cookie
0x1800464fa  xor     rax, rsp
0x1800464fd  mov     [rbp+57h+var_48], rax
0x180046501  xor     r14d, r14d
0x180046504  mov     [rbp+57h+var_90], ecx
0x180046507  mov     [rbp+57h+FilePart], r14
0x18004650b  mov     eax, r9d
0x18004650e  mov     [rbp+57h+var_A8], eax
0x180046511  xorps   xmm0, xmm0
0x180046514  xorps   xmm1, xmm1
0x180046517  mov     r13, r8
0x18004651a  mov     rdi, rdx
0x18004651d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180046521  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x180046525  cmp     ecx, 40h ; '@'
0x180046528  jnb     loc_180046AD9
0x18004652e  test    rdx, rdx
0x180046531  jz      loc_180046CA1
0x180046537  test    r8, r8
0x18004653a  jz      loc_180046CA1
0x180046540  test    eax, eax
0x180046542  jz      loc_180046CA1
0x180046548  mov     [r8], r14w
0x18004654c  lea     rax, [rbp+57h+var_B0]
0x180046550  xor     r8d, r8d; Buffer
0x180046553  mov     [rsp+0E0h+InputPathType], rax; InputPathType
0x180046558  xor     r9d, r9d; FilePart
0x18004655b  mov     [rbp+57h+var_B0], r14d
0x18004655f  xor     edx, edx; BufferLength
0x180046561  mov     rcx, rdi; FileName
0x180046564  call    cs:__imp_RtlGetFullPathName_UEx
0x18004656a  test    eax, eax
0x18004656c  jns     short loc_180046575
0x18004656e  mov     ecx, eax
0x180046570  call    BaseSetLastNTError
0x180046575  mov     eax, [rbp+57h+var_B0]
0x180046578  shr     eax, 1
0x18004657a  jz      loc_180046AE4
0x180046580  mov     rcx, gs:60h
0x180046589  mov     edx, cs:KernelBaseGlobalData; Flags
0x18004658f  mov     [rsp+0E0h+var_20], rbx
0x180046597  mov     [rsp+0E0h+var_28], rsi
0x18004659f  lea     esi, [rax+0Ah]
0x1800465a2  mov     rcx, [rcx+30h]; HeapHandle
0x1800465a6  mov     ebx, esi
0x1800465a8  add     rbx, rbx
0x1800465ab  mov     [rsp+0E0h+var_30], r12
0x1800465b3  mov     r8, rbx; Size
0x1800465b6  call    cs:__imp_RtlAllocateHeap
0x1800465bc  mov     r12, rax
0x1800465bf  test    rax, rax
0x1800465c2  jz      loc_180046D75
0x1800465c8  mov     r8, rbx; Size
0x1800465cb  xor     edx, edx; Val
0x1800465cd  mov     rcx, rax; void *
0x1800465d0  call    memset_0
0x1800465d5  lea     rax, [rbp+57h+var_B0]
0x1800465d9  mov     [rbp+57h+var_B0], r14d
0x1800465dd  lea     edx, [rsi+rsi]; BufferLength
0x1800465e0  mov     [rsp+0E0h+InputPathType], rax; InputPathType
0x1800465e5  lea     r9, [rbp+57h+FilePart]; FilePart
0x1800465e9  mov     r8, r12; Buffer
0x1800465ec  mov     rcx, rdi; FileName
0x1800465ef  call    cs:__imp_RtlGetFullPathName_UEx
0x1800465f5  test    eax, eax
0x1800465f7  jns     short loc_180046600
0x1800465f9  mov     ecx, eax
0x1800465fb  call    BaseSetLastNTError
0x180046600  test    [rbp+57h+var_B0], 0FFFFFFFEh
0x180046607  jz      loc_180046D87
0x18004660d  mov     rdx, r12; SourceString
0x180046610  mov     [rsp+0E0h+var_38], r15
0x180046618  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004661c  call    cs:__imp_RtlInitUnicodeString
0x180046622  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180046626  mov     ebx, 5Ch ; '\'
0x18004662b  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x18004662f  mov     eax, ecx
0x180046631  shr     rax, 1
0x180046634  cmp     [rdx+rax*2-2], bx
0x180046639  jz      short loc_180046660
0x18004663b  add     cx, 2
0x18004663f  movzx   eax, cx
0x180046642  mov     [rbp+57h+DestinationString.Length], ax
0x180046646  mov     ecx, eax
0x180046648  shr     rcx, 1
0x18004664b  mov     [rdx+rcx*2-2], bx
0x180046650  movzx   edx, [rbp+57h+DestinationString.Length]
0x180046654  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180046658  shr     rdx, 1
0x18004665b  mov     [rax+rdx*2], r14w
0x180046660  mov     rcx, gs:60h
0x180046669  mov     r8d, 4000h; Size
0x18004666f  mov     edx, cs:KernelBaseGlobalData; Flags
0x180046675  mov     rcx, [rcx+30h]; HeapHandle
0x180046679  call    cs:__imp_RtlAllocateHeap
0x18004667f  xor     edx, edx; Val
0x180046681  mov     r15, rax
0x180046684  test    rax, rax
0x180046687  jz      loc_18004692B
0x18004668d  mov     r8d, 4000h; Size
0x180046693  mov     rcx, rax; void *
0x180046696  call    memset_0
0x18004669b  mov     [rbp+57h+FilePart], r14
0x18004669f  mov     esi, r14d
0x1800466a2  mov     [rbp+57h+var_B0], r14d
0x1800466a6  mov     rdi, [rbp+57h+DestinationString.Buffer]
0x1800466aa  lea     rcx, [rbp+57h+UnicodeString]; DestinationString
0x1800466ae  mov     eax, 1
0x1800466b3  xorps   xmm0, xmm0
0x1800466b6  mov     rdx, rdi; SourceString
0x1800466b9  mov     [rbp+57h+var_AC], eax
0x1800466bc  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1800466c0  mov     r14d, eax
0x1800466c3  call    cs:__imp_RtlInitUnicodeStringEx
0x1800466c9  test    eax, eax
0x1800466cb  js      loc_180046D5A
0x1800466d1  movzx   ecx, [rbp+57h+UnicodeString.Length]
0x1800466d5  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x1800466d9  shr     rcx, 1
0x1800466dc  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800466e2  jnz     loc_180046D66
0x1800466e8  mov     rcx, rdi; lpRootPathName
0x1800466eb  call    GetDriveTypeW
0x1800466f0  lea     rdx, asc_180290A74; "\\\\"
0x1800466f7  mov     rcx, rdi; String1
0x1800466fa  mov     ebx, eax
0x1800466fc  call    cs:__imp__wcsicmp
0x180046702  lea     rdx, aUnc_2; "\\\\?\\UNC\\"
0x180046709  mov     rcx, rdi; String1
0x18004670c  mov     esi, eax
0x18004670e  call    cs:__imp__wcsicmp
0x180046714  cmp     ebx, 4
0x180046717  jz      loc_180046C12
0x18004671d  movzx   eax, [rbp+57h+UnicodeString.Length]
0x180046721  cmp     ax, 6
0x180046725  jz      loc_1800468D5
0x18004672b  cmp     ax, 0Eh
0x18004672f  jz      loc_180046997
0x180046735  mov     r8d, 2000h
0x18004673b  mov     rdx, r15
0x18004673e  mov     rcx, rdi
0x180046741  call    GetVolumeNameForRoot
0x180046746  test    eax, eax
0x180046748  jnz     loc_1800468CB
0x18004674e  lea     r9, [rbp+57h+var_AC]
0x180046752  mov     r8d, 2000h; cchFilePath
0x180046758  mov     rdx, r15; void *
0x18004675b  mov     rcx, rdi; lpFileName
0x18004675e  call    BasepGetVolumeNameFromReparsePoint
0x180046763  test    eax, eax
0x180046765  jnz     loc_1800468B6
0x18004676b  mov     r14d, [rbp+57h+var_AC]
0x18004676f  test    r14d, r14d
0x180046772  jz      loc_180046959
0x180046778  mov     esi, [rbp+57h+var_B0]
0x18004677b  mov     edi, 1
0x180046780  cmp     word ptr [r15], 0
0x180046785  jnz     loc_1800469FA
0x18004678b  test    r14d, r14d
0x18004678e  jz      loc_180046975
0x180046794  movzx   eax, [rbp+57h+DestinationString.Length]
0x180046798  cmp     eax, 2
0x18004679b  jbe     short loc_1800467C0
0x18004679d  shr     eax, 1
0x18004679f  sub     eax, 2
0x1800467a2  jz      short loc_1800467C0
0x1800467a4  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x1800467a8  nop     dword ptr [rax+rax+00000000h]
0x1800467b0  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1800467b5  jz      loc_180046883
0x1800467bb  add     eax, 0FFFFFFFFh
0x1800467be  jnz     short loc_1800467B0
0x1800467c0  mov     rcx, gs:60h
0x1800467c9  mov     r8, r15; P
0x1800467cc  xor     edx, edx; Flags
0x1800467ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800467d2  call    cs:__imp_RtlFreeHeap
0x1800467d8  test    r14d, r14d
0x1800467db  jz      loc_180046901
0x1800467e1  movzx   edx, [rbp+57h+DestinationString.Length]
0x1800467e5  xor     ebx, ebx
0x1800467e7  mov     r10d, [rbp+57h+var_A8]
0x1800467eb  cmp     edx, 2
0x1800467ee  jb      short loc_180046802
0x1800467f0  mov     ebx, edx
0x1800467f2  shr     ebx, 1
0x1800467f4  jz      short loc_180046802
0x1800467f6  lea     eax, [rbx+1]
0x1800467f9  cmp     eax, r10d
0x1800467fc  ja      loc_180046CFC
0x180046802  movzx   r8d, dx; Size
0x180046806  mov     ecx, r10d
0x180046809  add     rcx, rcx
0x18004680c  lea     rax, [r8+2]
0x180046810  cmp     rcx, rax
0x180046813  jb      loc_180046D32
0x180046819  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x18004681d  mov     rcx, r13; void *
0x180046820  call    memcpy_0
0x180046825  xor     ecx, ecx
0x180046827  mov     edx, ebx
0x180046829  mov     r8, r12; P
0x18004682c  mov     [r13+rdx*2+0], cx
0x180046832  xor     edx, edx; Flags
0x180046834  mov     rcx, gs:60h
0x18004683d  mov     rcx, [rcx+30h]; HeapHandle
0x180046841  call    cs:__imp_RtlFreeHeap
0x180046847  mov     eax, edi
0x180046849  mov     r15, [rsp+0E0h+var_38]
0x180046851  mov     rsi, [rsp+0E0h+var_28]
0x180046859  mov     rbx, [rsp+0E0h+var_20]
0x180046861  mov     r12, [rsp+0E0h+var_30]
0x180046869  mov     rcx, [rbp+57h+var_48]
0x18004686d  xor     rcx, rsp; StackCookie
0x180046870  call    __security_check_cookie
0x180046875  add     rsp, 0C8h
0x18004687c  pop     r14
0x18004687e  pop     r13
0x180046880  pop     rdi
0x180046881  pop     rbp
0x180046882  retn
0x180046883  lea     ecx, [rax+1]
0x180046886  add     rcx, rcx
0x180046889  test    r14d, r14d
0x18004688c  jz      loc_18004694E
0x180046892  add     rcx, rdx
0x180046895  mov     [rbp+57h+FilePart], rcx
0x180046899  xor     eax, eax
0x18004689b  movzx   esi, word ptr [rcx]
0x18004689e  mov     [rbp+57h+var_B0], esi
0x1800468a1  mov     [rcx], ax
0x1800468a4  mov     rdx, r12; SourceString
0x1800468a7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800468ab  call    cs:__imp_RtlInitUnicodeString
0x1800468b1  jmp     loc_1800466A6
0x1800468b6  mov     r8d, 2000h
0x1800468bc  mov     rdx, r15
0x1800468bf  mov     rcx, r15
0x1800468c2  call    GetVolumeNameForRoot
0x1800468c7  mov     r14d, [rbp+57h+var_AC]
0x1800468cb  mov     edi, 1
0x1800468d0  jmp     loc_1800467C0
0x1800468d5  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x1800468d9  cmp     word ptr [rax+2], 3Ah ; ':'
0x1800468de  jnz     loc_180046735
0x1800468e4  mov     r8d, 2000h
0x1800468ea  mov     rdx, r15
0x1800468ed  mov     rcx, rdi
0x1800468f0  call    GetVolumeNameForRoot
0x1800468f5  test    eax, eax
0x1800468f7  jnz     short loc_1800468CB
0x1800468f9  xor     r14d, r14d
0x1800468fc  jmp     loc_18018F2BE
0x180046901  cmp     [rbp+57h+FilePart], 0
0x180046906  jnz     loc_1800467E1
0x18004690c  mov     rcx, gs:60h
0x180046915  mov     r8, r12; P
0x180046918  xor     edx, edx; Flags
0x18004691a  mov     rcx, [rcx+30h]; HeapHandle
0x18004691e  call    cs:__imp_RtlFreeHeap
0x180046924  xor     eax, eax
0x180046926  jmp     loc_180046849
0x18004692b  mov     r8, r12; P
0x18004692e  mov     rcx, gs:60h
0x180046937  mov     rcx, [rcx+30h]; HeapHandle
0x18004693b  call    cs:__imp_RtlFreeHeap
0x180046941  mov     ecx, 8; LastError
0x180046946  call    cs:__imp_RtlSetLastWin32Error
0x18004694c  jmp     short loc_180046924
0x18004694e  xor     eax, eax
0x180046950  mov     [rcx+rdx], ax
0x180046954  jmp     loc_1800468A4
0x180046959  mov     eax, gs:68h
0x180046961  mov     edi, 1
0x180046966  mov     esi, [rbp+57h+var_B0]
0x180046969  cmp     eax, 5
0x18004696c  cmovz   r14d, edi
0x180046970  jmp     loc_180046780
0x180046975  mov     rax, [rbp+57h+FilePart]
0x180046979  test    rax, rax
0x18004697c  jz      loc_180046794
0x180046982  mov     rdx, r12; SourceString
0x180046985  mov     [rax], si
0x180046988  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004698c  call    cs:__imp_RtlInitUnicodeString
0x180046992  jmp     loc_1800467C0
0x180046997  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x18004699b  cmp     word ptr [rax], 5Ch ; '\'
0x18004699f  jnz     loc_180046735
0x1800469a5  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800469aa  jnz     loc_180046735
0x1800469b0  movzx   ecx, word ptr [rax+4]
0x1800469b4  cmp     cx, 2Eh ; '.'
  ... truncated ...
```
