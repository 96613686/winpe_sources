# GetVolumePathNameInternalW

- ea: `0x180050eb0`
- end: `0x180051840`
- name: `GetVolumePathNameInternalW`
- size: `2448`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180050ca0`
- `0x180050eb0`

## callees

- `0x18004b9d0`
- `0x180050eb0`
- `0x1800520d0`
- `0x180052890`
- `0x180052e40`
- `0x180073120`
- `0x1801369c9`
- `0x180194eb9`
- `0x180194ec5`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800515c3`
- `ntdll!RtlFreeUnicodeString` at `0x1800515c3`
- `ntdll!RtlInitUnicodeString` at `0x180050ffe`
- `ntdll!RtlInitUnicodeString` at `0x1800512b8`
- `ntdll!RtlInitUnicodeString` at `0x1800513b1`
- `ntdll!RtlInitUnicodeString` at `0x1800514ba`
- `ntdll!RtlInitUnicodeString` at `0x180051535`
- `ntdll!RtlInitUnicodeString` at `0x18005154c`
- `ntdll!RtlInitUnicodeString` at `0x180050ffe`
- `ntdll!RtlInitUnicodeString` at `0x1800512b8`
- `ntdll!RtlInitUnicodeString` at `0x1800513b1`
- `ntdll!RtlInitUnicodeString` at `0x1800514ba`
- `ntdll!RtlInitUnicodeString` at `0x180051535`
- `ntdll!RtlInitUnicodeString` at `0x18005154c`
- `ntdll!_wcsicmp` at `0x1800510f0`
- `ntdll!_wcsicmp` at `0x180051108`
- `ntdll!_wcsicmp` at `0x1800510f0`
- `ntdll!_wcsicmp` at `0x180051108`
- `ntdll!RtlSetLastWin32Error` at `0x180051365`
- `ntdll!RtlSetLastWin32Error` at `0x18005151b`
- `ntdll!RtlSetLastWin32Error` at `0x180051576`
- `ntdll!RtlSetLastWin32Error` at `0x1800516ab`
- `ntdll!RtlSetLastWin32Error` at `0x180051713`
- `ntdll!RtlSetLastWin32Error` at `0x1800517c8`
- `ntdll!RtlSetLastWin32Error` at `0x1800517f9`
- `ntdll!RtlSetLastWin32Error` at `0x180051365`
- `ntdll!RtlSetLastWin32Error` at `0x18005151b`
- `ntdll!RtlSetLastWin32Error` at `0x180051576`
- `ntdll!RtlSetLastWin32Error` at `0x1800516ab`
- `ntdll!RtlSetLastWin32Error` at `0x180051713`
- `ntdll!RtlSetLastWin32Error` at `0x1800517c8`
- `ntdll!RtlSetLastWin32Error` at `0x1800517f9`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800510b1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800510b1`
- `ntdll!RtlFreeHeap` at `0x1800511d2`
- `ntdll!RtlFreeHeap` at `0x180051247`
- `ntdll!RtlFreeHeap` at `0x180051331`
- `ntdll!RtlFreeHeap` at `0x180051354`
- `ntdll!RtlFreeHeap` at `0x180051460`
- `ntdll!RtlFreeHeap` at `0x180051503`
- `ntdll!RtlFreeHeap` at `0x180051668`
- `ntdll!RtlFreeHeap` at `0x1800517b7`
- `ntdll!RtlFreeHeap` at `0x18005181e`
- `ntdll!RtlFreeHeap` at `0x1800511d2`
- `ntdll!RtlFreeHeap` at `0x180051247`
- `ntdll!RtlFreeHeap` at `0x180051331`
- `ntdll!RtlFreeHeap` at `0x180051354`
- `ntdll!RtlFreeHeap` at `0x180051460`
- `ntdll!RtlFreeHeap` at `0x180051503`
- `ntdll!RtlFreeHeap` at `0x180051668`
- `ntdll!RtlFreeHeap` at `0x1800517b7`
- `ntdll!RtlFreeHeap` at `0x18005181e`
- `ntdll!RtlGetFullPathName_UEx` at `0x180050f34`
- `ntdll!RtlGetFullPathName_UEx` at `0x180050fcb`
- `ntdll!RtlGetFullPathName_UEx` at `0x180050f34`
- `ntdll!RtlGetFullPathName_UEx` at `0x180050fcb`
- `ntdll!RtlAllocateHeap` at `0x180050f8c`
- `ntdll!RtlAllocateHeap` at `0x180051061`
- `ntdll!RtlAllocateHeap` at `0x1800515f6`
- `ntdll!RtlAllocateHeap` at `0x180050f8c`
- `ntdll!RtlAllocateHeap` at `0x180051061`
- `ntdll!RtlAllocateHeap` at `0x1800515f6`

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
0x180050eb0  push    rbp
0x180050eb2  push    rdi
0x180050eb3  push    r13
0x180050eb5  push    r14
0x180050eb7  lea     rbp, [rsp-3Fh]
0x180050ebc  sub     rsp, 0C8h
0x180050ec3  mov     rax, cs:__security_cookie
0x180050eca  xor     rax, rsp
0x180050ecd  mov     [rbp+57h+var_48], rax
0x180050ed1  xor     r14d, r14d
0x180050ed4  mov     [rbp+57h+var_90], ecx
0x180050ed7  mov     [rbp+57h+FilePart], r14
0x180050edb  mov     eax, r9d
0x180050ede  mov     [rbp+57h+var_A8], eax
0x180050ee1  xorps   xmm0, xmm0
0x180050ee4  xorps   xmm1, xmm1
0x180050ee7  mov     r13, r8
0x180050eea  mov     rdi, rdx
0x180050eed  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180050ef1  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x180050ef5  cmp     ecx, 40h ; '@'
0x180050ef8  jnb     loc_180051516
0x180050efe  test    rdx, rdx
0x180050f01  jz      loc_18005170E
0x180050f07  test    r8, r8
0x180050f0a  jz      loc_18005170E
0x180050f10  test    eax, eax
0x180050f12  jz      loc_18005170E
0x180050f18  mov     [r8], r14w
0x180050f1c  lea     rax, [rbp+57h+var_B0]
0x180050f20  xor     r8d, r8d; Buffer
0x180050f23  mov     [rsp+0E0h+InputPathType], rax; InputPathType
0x180050f28  xor     r9d, r9d; FilePart
0x180050f2b  mov     [rbp+57h+var_B0], r14d
0x180050f2f  xor     edx, edx; BufferLength
0x180050f31  mov     rcx, rdi; FileName
0x180050f34  call    cs:__imp_RtlGetFullPathName_UEx
0x180050f3b  nop     dword ptr [rax+rax+00h]
0x180050f40  test    eax, eax
0x180050f42  jns     short loc_180050F4B
0x180050f44  mov     ecx, eax
0x180050f46  call    BaseSetLastNTError
0x180050f4b  mov     eax, [rbp+57h+var_B0]
0x180050f4e  shr     eax, 1
0x180050f50  jz      loc_180051527
0x180050f56  mov     rcx, gs:60h
0x180050f5f  mov     edx, cs:KernelBaseGlobalData; Flags
0x180050f65  mov     [rsp+0E0h+var_20], rbx
0x180050f6d  mov     [rsp+0E0h+var_28], rsi
0x180050f75  lea     esi, [rax+0Ah]
0x180050f78  mov     rcx, [rcx+30h]; HeapHandle
0x180050f7c  mov     ebx, esi
0x180050f7e  add     rbx, rbx
0x180050f81  mov     [rsp+0E0h+var_30], r12
0x180050f89  mov     r8, rbx; Size
0x180050f8c  call    cs:__imp_RtlAllocateHeap
0x180050f93  nop     dword ptr [rax+rax+00h]
0x180050f98  mov     r12, rax
0x180050f9b  test    rax, rax
0x180050f9e  jz      loc_1800517F4
0x180050fa4  mov     r8, rbx; Size
0x180050fa7  xor     edx, edx; Val
0x180050fa9  mov     rcx, rax; void *
0x180050fac  call    memset_0
0x180050fb1  lea     rax, [rbp+57h+var_B0]
0x180050fb5  mov     [rbp+57h+var_B0], r14d
0x180050fb9  lea     edx, [rsi+rsi]; BufferLength
0x180050fbc  mov     [rsp+0E0h+InputPathType], rax; InputPathType
0x180050fc1  lea     r9, [rbp+57h+FilePart]; FilePart
0x180050fc5  mov     r8, r12; Buffer
0x180050fc8  mov     rcx, rdi; FileName
0x180050fcb  call    cs:__imp_RtlGetFullPathName_UEx
0x180050fd2  nop     dword ptr [rax+rax+00h]
0x180050fd7  test    eax, eax
0x180050fd9  jns     short loc_180050FE2
0x180050fdb  mov     ecx, eax
0x180050fdd  call    BaseSetLastNTError
0x180050fe2  test    [rbp+57h+var_B0], 0FFFFFFFEh
0x180050fe9  jz      loc_18005180C
0x180050fef  mov     rdx, r12; SourceString
0x180050ff2  mov     [rsp+0E0h+var_38], r15
0x180050ffa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180050ffe  call    cs:__imp_RtlInitUnicodeString
0x180051005  nop     dword ptr [rax+rax+00h]
0x18005100a  movzx   ecx, [rbp+57h+DestinationString.Length]
0x18005100e  mov     ebx, 5Ch ; '\'
0x180051013  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x180051017  mov     eax, ecx
0x180051019  shr     rax, 1
0x18005101c  cmp     [rdx+rax*2-2], bx
0x180051021  jz      short loc_180051048
0x180051023  add     cx, 2
0x180051027  movzx   eax, cx
0x18005102a  mov     [rbp+57h+DestinationString.Length], ax
0x18005102e  mov     ecx, eax
0x180051030  shr     rcx, 1
0x180051033  mov     [rdx+rcx*2-2], bx
0x180051038  movzx   edx, [rbp+57h+DestinationString.Length]
0x18005103c  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180051040  shr     rdx, 1
0x180051043  mov     [rax+rdx*2], r14w
0x180051048  mov     rcx, gs:60h
0x180051051  mov     r8d, 4000h; Size
0x180051057  mov     edx, cs:KernelBaseGlobalData; Flags
0x18005105d  mov     rcx, [rcx+30h]; HeapHandle
0x180051061  call    cs:__imp_RtlAllocateHeap
0x180051068  nop     dword ptr [rax+rax+00h]
0x18005106d  xor     edx, edx; Val
0x18005106f  mov     r15, rax
0x180051072  test    rax, rax
0x180051075  jz      loc_180051344
0x18005107b  mov     r8d, 4000h; Size
0x180051081  mov     rcx, rax; void *
0x180051084  call    memset_0
0x180051089  mov     [rbp+57h+FilePart], r14
0x18005108d  mov     esi, r14d
0x180051090  mov     [rbp+57h+var_B0], r14d
0x180051094  mov     rdi, [rbp+57h+DestinationString.Buffer]
0x180051098  lea     rcx, [rbp+57h+UnicodeString]; DestinationString
0x18005109c  mov     eax, 1
0x1800510a1  xorps   xmm0, xmm0
0x1800510a4  mov     rdx, rdi; SourceString
0x1800510a7  mov     [rbp+57h+var_AC], eax
0x1800510aa  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1800510ae  mov     r14d, eax
0x1800510b1  call    cs:__imp_RtlInitUnicodeStringEx
0x1800510b8  nop     dword ptr [rax+rax+00h]
0x1800510bd  test    eax, eax
0x1800510bf  js      loc_1800517D9
0x1800510c5  movzx   ecx, [rbp+57h+UnicodeString.Length]
0x1800510c9  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x1800510cd  shr     rcx, 1
0x1800510d0  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800510d6  jnz     loc_1800517E5
0x1800510dc  mov     rcx, rdi; lpRootPathName
0x1800510df  call    GetDriveTypeW
0x1800510e4  lea     rdx, asc_18029DF04; "\\\\"
0x1800510eb  mov     rcx, rdi; String1
0x1800510ee  mov     ebx, eax
0x1800510f0  call    cs:__imp__wcsicmp
0x1800510f7  nop     dword ptr [rax+rax+00h]
0x1800510fc  lea     rdx, aUnc_2; "\\\\?\\UNC\\"
0x180051103  mov     rcx, rdi; String1
0x180051106  mov     esi, eax
0x180051108  call    cs:__imp__wcsicmp
0x18005110f  nop     dword ptr [rax+rax+00h]
0x180051114  cmp     ebx, 4
0x180051117  jz      loc_180051679
0x18005111d  movzx   eax, [rbp+57h+UnicodeString.Length]
0x180051121  cmp     ax, 6
0x180051125  jz      loc_1800512E8
0x18005112b  cmp     ax, 0Eh
0x18005112f  jz      loc_1800513C2
0x180051135  mov     r8d, 2000h
0x18005113b  mov     rdx, r15
0x18005113e  mov     rcx, rdi
0x180051141  call    GetVolumeNameForRoot
0x180051146  test    eax, eax
0x180051148  jnz     loc_1800512DE
0x18005114e  lea     r9, [rbp+57h+var_AC]
0x180051152  mov     r8d, 2000h; cchFilePath
0x180051158  mov     rdx, r15; void *
0x18005115b  mov     rcx, rdi; lpFileName
0x18005115e  call    BasepGetVolumeNameFromReparsePoint
0x180051163  test    eax, eax
0x180051165  jnz     loc_1800512C9
0x18005116b  mov     r14d, [rbp+57h+var_AC]
0x18005116f  test    r14d, r14d
0x180051172  jz      loc_18005137E
0x180051178  mov     esi, [rbp+57h+var_B0]
0x18005117b  mov     edi, 1
0x180051180  cmp     word ptr [r15], 0
0x180051185  jnz     loc_180051425
0x18005118b  test    r14d, r14d
0x18005118e  jz      loc_18005139A
0x180051194  movzx   eax, [rbp+57h+DestinationString.Length]
0x180051198  cmp     eax, 2
0x18005119b  jbe     short loc_1800511C0
0x18005119d  shr     eax, 1
0x18005119f  sub     eax, 2
0x1800511a2  jz      short loc_1800511C0
0x1800511a4  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x1800511a8  nop     dword ptr [rax+rax+00000000h]
0x1800511b0  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1800511b5  jz      loc_180051290
0x1800511bb  add     eax, 0FFFFFFFFh
0x1800511be  jnz     short loc_1800511B0
0x1800511c0  mov     rcx, gs:60h
0x1800511c9  mov     r8, r15; P
0x1800511cc  xor     edx, edx; Flags
0x1800511ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800511d2  call    cs:__imp_RtlFreeHeap
0x1800511d9  nop     dword ptr [rax+rax+00h]
0x1800511de  test    r14d, r14d
0x1800511e1  jz      loc_180051314
0x1800511e7  movzx   edx, [rbp+57h+DestinationString.Length]
0x1800511eb  xor     ebx, ebx
0x1800511ed  mov     r10d, [rbp+57h+var_A8]
0x1800511f1  cmp     edx, 2
0x1800511f4  jb      short loc_180051208
0x1800511f6  mov     ebx, edx
0x1800511f8  shr     ebx, 1
0x1800511fa  jz      short loc_180051208
0x1800511fc  lea     eax, [rbx+1]
0x1800511ff  cmp     eax, r10d
0x180051202  ja      loc_18005176F
0x180051208  movzx   r8d, dx; Size
0x18005120c  mov     ecx, r10d
0x18005120f  add     rcx, rcx
0x180051212  lea     rax, [r8+2]
0x180051216  cmp     rcx, rax
0x180051219  jb      loc_1800517A5
0x18005121f  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x180051223  mov     rcx, r13; void *
0x180051226  call    memcpy_0
0x18005122b  xor     ecx, ecx
0x18005122d  mov     edx, ebx
0x18005122f  mov     r8, r12; P
0x180051232  mov     [r13+rdx*2+0], cx
0x180051238  xor     edx, edx; Flags
0x18005123a  mov     rcx, gs:60h
0x180051243  mov     rcx, [rcx+30h]; HeapHandle
0x180051247  call    cs:__imp_RtlFreeHeap
0x18005124e  nop     dword ptr [rax+rax+00h]
0x180051253  mov     eax, edi
0x180051255  mov     r15, [rsp+0E0h+var_38]
0x18005125d  mov     rsi, [rsp+0E0h+var_28]
0x180051265  mov     rbx, [rsp+0E0h+var_20]
0x18005126d  mov     r12, [rsp+0E0h+var_30]
0x180051275  mov     rcx, [rbp+57h+var_48]
0x180051279  xor     rcx, rsp; StackCookie
0x18005127c  call    __security_check_cookie
0x180051281  add     rsp, 0C8h
0x180051288  pop     r14
0x18005128a  pop     r13
0x18005128c  pop     rdi
0x18005128d  pop     rbp
0x18005128e  retn
0x180051290  lea     ecx, [rax+1]
0x180051293  add     rcx, rcx
0x180051296  test    r14d, r14d
0x180051299  jz      loc_180051373
0x18005129f  add     rcx, rdx
0x1800512a2  mov     [rbp+57h+FilePart], rcx
0x1800512a6  xor     eax, eax
0x1800512a8  movzx   esi, word ptr [rcx]
0x1800512ab  mov     [rbp+57h+var_B0], esi
0x1800512ae  mov     [rcx], ax
0x1800512b1  mov     rdx, r12; SourceString
0x1800512b4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800512b8  call    cs:__imp_RtlInitUnicodeString
0x1800512bf  nop     dword ptr [rax+rax+00h]
0x1800512c4  jmp     loc_180051094
0x1800512c9  mov     r8d, 2000h
0x1800512cf  mov     rdx, r15
0x1800512d2  mov     rcx, r15
0x1800512d5  call    GetVolumeNameForRoot
0x1800512da  mov     r14d, [rbp+57h+var_AC]
0x1800512de  mov     edi, 1
0x1800512e3  jmp     loc_1800511C0
0x1800512e8  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x1800512ec  cmp     word ptr [rax+2], 3Ah ; ':'
0x1800512f1  jnz     loc_180051135
0x1800512f7  mov     r8d, 2000h
0x1800512fd  mov     rdx, r15
0x180051300  mov     rcx, rdi
0x180051303  call    GetVolumeNameForRoot
0x180051308  test    eax, eax
0x18005130a  jnz     short loc_1800512DE
0x18005130c  xor     r14d, r14d
0x18005130f  jmp     loc_18019AB0E
0x180051314  cmp     [rbp+57h+FilePart], 0
0x180051319  jnz     loc_1800511E7
0x18005131f  mov     rcx, gs:60h
0x180051328  mov     r8, r12; P
0x18005132b  xor     edx, edx; Flags
0x18005132d  mov     rcx, [rcx+30h]; HeapHandle
0x180051331  call    cs:__imp_RtlFreeHeap
0x180051338  nop     dword ptr [rax+rax+00h]
0x18005133d  xor     eax, eax
0x18005133f  jmp     loc_180051255
0x180051344  mov     r8, r12; P
0x180051347  mov     rcx, gs:60h
0x180051350  mov     rcx, [rcx+30h]; HeapHandle
0x180051354  call    cs:__imp_RtlFreeHeap
0x18005135b  nop     dword ptr [rax+rax+00h]
0x180051360  mov     ecx, 8; LastError
0x180051365  call    cs:__imp_RtlSetLastWin32Error
0x18005136c  nop     dword ptr [rax+rax+00h]
0x180051371  jmp     short loc_18005133D
0x180051373  xor     eax, eax
0x180051375  mov     [rcx+rdx], ax
0x180051379  jmp     loc_1800512B1
0x18005137e  mov     eax, gs:68h
0x180051386  mov     edi, 1
0x18005138b  mov     esi, [rbp+57h+var_B0]
0x18005138e  cmp     eax, 5
0x180051391  cmovz   r14d, edi
0x180051395  jmp     loc_180051180
0x18005139a  mov     rax, [rbp+57h+FilePart]
  ... truncated ...
```
