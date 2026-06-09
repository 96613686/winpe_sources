# InternalFindFirstFileExW

- ea: `0x180082860`
- end: `0x180082f75`
- name: `InternalFindFirstFileExW`
- size: `1813`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosName@<rcx>, int, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007fdc0`
- `0x1800815d0`
- `0x180081780`
- `0x180082020`
- `0x1800827e0`
- `0x180082820`
- `0x180084c70`

## callees

- `0x18004b9d0`
- `0x180082860`
- `0x1801369c9`
- `0x18018d188`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180082949`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180082949`
- `ntdll!RtlInitUnicodeString` at `0x18008291b`
- `ntdll!RtlInitUnicodeString` at `0x18008291b`
- `ntdll!RtlReleaseRelativeName` at `0x180082b46`
- `ntdll!RtlReleaseRelativeName` at `0x180082dba`
- `ntdll!RtlReleaseRelativeName` at `0x180082e0c`
- `ntdll!RtlReleaseRelativeName` at `0x18019daac`
- `ntdll!RtlReleaseRelativeName` at `0x180082b46`
- `ntdll!RtlReleaseRelativeName` at `0x180082dba`
- `ntdll!RtlReleaseRelativeName` at `0x180082e0c`
- `ntdll!RtlReleaseRelativeName` at `0x18019daac`
- `ntdll!NtOpenFile` at `0x180082a44`
- `ntdll!NtOpenFile` at `0x180082eb4`
- `ntdll!NtOpenFile` at `0x180082a44`
- `ntdll!NtOpenFile` at `0x180082eb4`
- `ntdll!RtlInitializeCriticalSection` at `0x180082c7c`
- `ntdll!RtlInitializeCriticalSection` at `0x180082c7c`
- `ntdll!RtlSetLastWin32Error` at `0x180082e4c`
- `ntdll!RtlSetLastWin32Error` at `0x180082e69`
- `ntdll!RtlSetLastWin32Error` at `0x180082f5d`
- `ntdll!RtlSetLastWin32Error` at `0x180082e4c`
- `ntdll!RtlSetLastWin32Error` at `0x180082e69`
- `ntdll!RtlSetLastWin32Error` at `0x180082f5d`
- `ntdll!RtlIsDosDeviceName_U` at `0x18008296e`
- `ntdll!RtlIsDosDeviceName_U` at `0x18008296e`
- `ntdll!NtClose` at `0x180082d97`
- `ntdll!NtClose` at `0x180082e3b`
- `ntdll!NtClose` at `0x180082f37`
- `ntdll!NtClose` at `0x180082d97`
- `ntdll!NtClose` at `0x180082e3b`
- `ntdll!NtClose` at `0x180082f37`
- `ntdll!RtlFreeHeap` at `0x180082b64`
- `ntdll!RtlFreeHeap` at `0x180082dd8`
- `ntdll!RtlFreeHeap` at `0x180082e2a`
- `ntdll!RtlFreeHeap` at `0x180082f26`
- `ntdll!RtlFreeHeap` at `0x18019daca`
- `ntdll!RtlFreeHeap` at `0x180082b64`
- `ntdll!RtlFreeHeap` at `0x180082dd8`
- `ntdll!RtlFreeHeap` at `0x180082e2a`
- `ntdll!RtlFreeHeap` at `0x180082f26`
- `ntdll!RtlFreeHeap` at `0x18019daca`
- `ntdll!RtlCompareMemory` at `0x180082d41`
- `ntdll!RtlCompareMemory` at `0x180082d41`
- `ntdll!NtQueryDirectoryFileEx` at `0x180082b34`
- `ntdll!NtQueryDirectoryFileEx` at `0x180082b34`
- `ntdll!RtlAllocateHeap` at `0x180082c49`
- `ntdll!RtlAllocateHeap` at `0x180082c49`

## pseudocode

```c
__int64 __fastcall InternalFindFirstFileExW(PCWSTR DosName, int a2, __int64 a3, int a4, int a5, int a6)
{
  bool v10; // r15
  PWSTR Buffer; // r13
  ULONG IsDosDeviceName_U; // eax
  unsigned __int64 v13; // rbx
  USHORT Length; // ax
  __int16 v15; // cx
  unsigned int v16; // edx
  bool v17; // di
  NTSTATUS v18; // eax
  NTSTATUS v19; // ebx
  unsigned int v20; // eax
  WCHAR *v21; // rdx
  unsigned __int8 *p_Src; // rdx
  int v23; // edi
  unsigned int v24; // eax
  bool v25; // cc
  unsigned __int64 v26; // rbx
  unsigned int v27; // ecx
  unsigned __int64 v28; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v29; // rdi
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  struct _RTL_CRITICAL_SECTION *v31; // rbx
  ULONG v33; // ecx
  ULONG v34; // ecx
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR PartName[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+88h] [rbp-78h] BYREF
  _WORD v40[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v41; // [rsp+ACh] [rbp-54h]
  char *v42; // [rsp+B0h] [rbp-50h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  char v45[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v46; // [rsp+108h] [rbp+8h]
  __int64 v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  int v49; // [rsp+128h] [rbp+28h]
  int v50; // [rsp+12Ch] [rbp+2Ch]
  int v51; // [rsp+138h] [rbp+38h]
  unsigned int v52; // [rsp+13Ch] [rbp+3Ch]
  int v53; // [rsp+140h] [rbp+40h]
  unsigned __int8 v54; // [rsp+144h] [rbp+44h] BYREF
  char v55[24]; // [rsp+146h] [rbp+46h] BYREF
  char Src; // [rsp+15Eh] [rbp+5Eh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)PartName = 0;
  NtName = 0;
  IoStatusBlock = 0;
  memset_0(v45, 0, 0x268u);
  v41 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  DestinationString = 0;
  if ( a2 < 2 && a4 < 2 && (a6 & 0xFFFFFFF8) == 0 )
  {
    RtlInitUnicodeString(&DestinationString, DosName);
    v10 = DestinationString.Length
       && DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] == 46;
    if ( !RtlDosPathNameToRelativeNtPathName_U(DosName, &NtName, &PartName[1], &RelativeName) )
    {
      RtlSetLastWin32Error(3u);
      return -1;
    }
    Buffer = NtName.Buffer;
    IsDosDeviceName_U = RtlIsDosDeviceName_U(DestinationString.Buffer);
    v13 = IsDosDeviceName_U;
    if ( IsDosDeviceName_U )
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      v40[0] = v13;
      v42 = (char *)DestinationString.Buffer + (v13 >> 16);
      v40[1] = v13;
      return BaseFindFirstDevice(v40, a3);
    }
    Length = NtName.Length;
    if ( PartName[1] )
      v15 = NtName.Length + LOWORD(NtName.Buffer) - LOWORD(PartName[1]);
    else
      v15 = 0;
    LOWORD(PartName[0]) = v15;
    WORD1(PartName[0]) = v15;
    if ( !RelativeName.RelativeName.Length || RelativeName.RelativeName.Buffer == PartName[1] )
    {
      RelativeName.ContainingDirectory = 0;
      if ( !PartName[1] )
        goto LABEL_14;
      Length = LOWORD(PartName[1]) - LOWORD(NtName.Buffer);
    }
    else
    {
      if ( !PartName[1] )
      {
LABEL_14:
        v16 = Length >> 1;
        v17 = v16 >= 2 && NtName.Buffer[v16 - 2] != 58 && NtName.Buffer[v16 - 1] == 92;
        ObjectAttributes.RootDirectory = RelativeName.ContainingDirectory;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = ((a6 & 1) == 0) << 6;
        ObjectAttributes.ObjectName = &NtName;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v18 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
        v19 = v18;
        if ( v17 && (v18 == -1073741565 || v18 == -1073741811) )
        {
          NtName.Length -= 2;
          v19 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
        }
        if ( v19 < 0 )
        {
          RtlReleaseRelativeName(&RelativeName);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
          if ( v19 == -1073741788 || v19 == -1073741772 )
          {
            BaseSetLastNTError(3221225530LL);
            return -1;
          }
          goto LABEL_60;
        }
        if ( !LOWORD(PartName[0]) )
        {
          RtlReleaseRelativeName(&RelativeName);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
          NtClose(FileHandle);
          v33 = 2;
          goto LABEL_64;
        }
        if ( LOWORD(PartName[0]) == 6 && RtlCompareMemory(PartName[1], L"*.*", 6u) == 6 )
        {
          LOWORD(PartName[0]) = 2;
LABEL_29:
          v19 = NtQueryDirectoryFileEx(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  v45,
                  616,
                  3 - (unsigned int)(a2 != 0),
                  2 * (a6 & 4 | 1u),
                  PartName);
          RtlReleaseRelativeName(&RelativeName);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
          if ( v19 >= 0 )
          {
            p_Src = &v54;
            v23 = v51;
            *(_QWORD *)(a3 + 4) = v46;
            *(_QWORD *)(a3 + 12) = v47;
            *(_QWORD *)(a3 + 20) = v48;
            *(_DWORD *)(a3 + 28) = v50;
            *(_DWORD *)(a3 + 32) = v49;
            v24 = v52;
            v25 = v52 <= 0x206;
            *(_DWORD *)a3 = v23;
            if ( !v25 )
              v24 = 518;
            v26 = v24;
            if ( !a2 )
              p_Src = (unsigned __int8 *)&Src;
            memcpy_0((void *)(a3 + 44), p_Src, v24);
            *(_WORD *)(a3 + 2 * (v26 >> 1) + 44) = 0;
            if ( a2 )
            {
              *(_WORD *)(a3 + 564) = 0;
            }
            else
            {
              if ( v54 > 0x1Au || (v27 = (char)v54, (unsigned int)(char)v54 >= 0x18) )
                v27 = 24;
              v28 = v27;
              memcpy_0((void *)(a3 + 564), v55, v27);
              *(_WORD *)(a3 + 2 * (v28 >> 1) + 564) = 0;
            }
            if ( (v23 & 0x400) != 0 )
              *(_DWORD *)(a3 + 36) = v53;
            v29 = (struct _RTL_CRITICAL_SECTION_DEBUG *)FileHandle;
            Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(
                                                     NtCurrentPeb()->ProcessHeap,
                                                     KernelBaseGlobalData + 786432,
                                                     0x50u);
            v31 = Heap;
            if ( Heap )
            {
              Heap->DebugInfo = v29;
              *(_QWORD *)&Heap->LockCount = 0;
              Heap->OwningThread = 0;
              Heap->LockSemaphore = 0;
              LODWORD(Heap->SpinCount) = a2;
              HIDWORD(Heap->SpinCount) = a6;
              if ( RtlInitializeCriticalSection(Heap + 1) >= 0 )
                return (__int64)v31;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v31);
            }
            NtClose(FileHandle);
            v33 = 8;
LABEL_64:
            RtlSetLastWin32Error(v33);
            return -1;
          }
          NtClose(FileHandle);
LABEL_60:
          BaseSetLastNTError((unsigned int)v19);
          return -1;
        }
        v20 = 0;
        v21 = (WCHAR *)PartName[1];
        if ( ((__int64)PartName[0] & 0xFFFE) == 0 )
        {
LABEL_28:
          if ( v10 && *(v21 - 1) == 42 )
            *(v21 - 1) = 60;
          goto LABEL_29;
        }
        while ( 1 )
        {
          if ( v20 && *v21 == 46 && *(v21 - 1) == 42 )
            *(v21 - 1) = 60;
          if ( *v21 == 63 )
            break;
          if ( *v21 == 42 )
            goto LABEL_45;
LABEL_27:
          ++v20;
          ++v21;
          if ( v20 >= LOWORD(PartName[0]) >> 1 )
            goto LABEL_28;
        }
        *v21 = 62;
LABEL_45:
        if ( v20 && *(v21 - 1) == 46 )
          *(v21 - 1) = 34;
        goto LABEL_27;
      }
      NtName.Buffer = RelativeName.RelativeName.Buffer;
      Length = LOWORD(PartName[1]) - LOWORD(RelativeName.RelativeName.Buffer);
    }
    NtName.MaximumLength = Length;
    NtName.Length = Length;
    goto LABEL_14;
  }
  v34 = 50;
  if ( a4 != 2 )
    v34 = 87;
  RtlSetLastWin32Error(v34);
  return -1;
}

```

## disassembly

```asm
0x180082860  push    rbp
0x180082862  push    rbx
0x180082863  push    rsi
0x180082864  push    rdi
0x180082865  push    r12
0x180082867  push    r14
0x180082869  lea     rbp, [rsp-288h]
0x180082871  sub     rsp, 388h
0x180082878  mov     rax, cs:__security_cookie
0x18008287f  xor     rax, rsp
0x180082882  mov     [rbp+2B0h+var_40], rax
0x180082889  xorps   xmm0, xmm0
0x18008288c  mov     rsi, r8
0x18008288f  mov     r12d, edx
0x180082892  mov     rbx, rcx
0x180082895  xorps   xmm1, xmm1
0x180082898  lea     rcx, [rbp+2B0h+var_2B0]; void *
0x18008289c  movups  xmmword ptr [rbp+2B0h+ObjectAttributes.ObjectName], xmm0
0x1800828a0  xor     r14d, r14d
0x1800828a3  xor     eax, eax
0x1800828a5  xor     edx, edx; Val
0x1800828a7  mov     [rsp+3B0h+FileHandle], r14
0x1800828ac  mov     r8d, 268h; Size
0x1800828b2  mov     edi, r9d
0x1800828b5  movups  xmmword ptr [rbp+2B0h+ObjectAttributes+1Ch], xmm0
0x1800828b9  movups  xmmword ptr [rbp+2B0h+ObjectAttributes.Length], xmm0
0x1800828bd  movups  xmmword ptr [rsp+3B0h+PartName], xmm0
0x1800828c2  movups  xmmword ptr [rsp+3B0h+NtName.Length], xmm1
0x1800828c7  movups  xmmword ptr [rbp+2B0h+IoStatusBlock], xmm0
0x1800828cb  call    memset_0
0x1800828d0  mov     [rbp+2B0h+var_304], r14d
0x1800828d4  xorps   xmm0, xmm0
0x1800828d7  movups  xmmword ptr [rbp+2B0h+RelativeName.RelativeName.Length], xmm0
0x1800828db  movups  xmmword ptr [rbp+2B0h+RelativeName.ContainingDirectory], xmm0
0x1800828df  movups  xmmword ptr [rsp+3B0h+DestinationString.Length], xmm0
0x1800828e4  cmp     r12d, 2
0x1800828e8  jge     loc_180082F4D
0x1800828ee  cmp     edi, 2
0x1800828f1  jge     loc_180082F4D
0x1800828f7  mov     r14d, [rbp+2B0h+arg_28]
0x1800828fe  test    r14d, 0FFFFFFF8h
0x180082905  jnz     loc_180082F4D
0x18008290b  mov     rdx, rbx; SourceString
0x18008290e  mov     [rsp+3B0h+var_30], r15
0x180082916  lea     rcx, [rsp+3B0h+DestinationString]; DestinationString
0x18008291b  call    cs:__imp_RtlInitUnicodeString
0x180082922  nop     dword ptr [rax+rax+00h]
0x180082927  movzx   eax, [rsp+3B0h+DestinationString.Length]
0x18008292c  test    ax, ax
0x18008292f  jnz     loc_180082CE6
0x180082935  xor     r15b, r15b
0x180082938  lea     r9, [rbp+2B0h+RelativeName]; RelativeName
0x18008293c  mov     rcx, rbx; DosName
0x18008293f  lea     r8, [rsp+3B0h+PartName+8]; PartName
0x180082944  lea     rdx, [rsp+3B0h+NtName]; NtName
0x180082949  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180082950  nop     dword ptr [rax+rax+00h]
0x180082955  test    al, al
0x180082957  jz      loc_180082E64
0x18008295d  mov     rcx, [rbp+2B0h+DestinationString.Buffer]; Name
0x180082961  mov     [rsp+3B0h+arg_8], r13
0x180082969  mov     r13, [rsp+3B0h+NtName.Buffer]
0x18008296e  call    cs:__imp_RtlIsDosDeviceName_U
0x180082975  nop     dword ptr [rax+rax+00h]
0x18008297a  mov     ebx, eax
0x18008297c  test    eax, eax
0x18008297e  jnz     loc_18019DAA8
0x180082984  mov     rdx, [rsp+3B0h+PartName+8]
0x180082989  movzx   r8d, word ptr [rsp+3B0h+PartName+8]
0x18008298f  movzx   r9d, word ptr [rsp+3B0h+NtName.Buffer]
0x180082995  movzx   eax, [rsp+3B0h+NtName.Length]
0x18008299a  test    rdx, rdx
0x18008299d  jz      loc_180082E81
0x1800829a3  movzx   ecx, r9w
0x1800829a7  sub     cx, r8w
0x1800829ab  add     cx, ax
0x1800829ae  cmp     [rbp+2B0h+RelativeName.RelativeName.Length], 0
0x1800829b3  mov     word ptr [rsp+3B0h+PartName], cx
0x1800829b8  mov     word ptr [rsp+3B0h+PartName+2], cx
0x1800829bd  jnz     loc_180082EC7
0x1800829c3  mov     [rbp+2B0h+RelativeName.ContainingDirectory], 0
0x1800829cb  test    rdx, rdx
0x1800829ce  jz      short loc_1800829E2
0x1800829d0  movzx   eax, r8w
0x1800829d4  sub     ax, r9w
0x1800829d8  mov     [rsp+3B0h+NtName.MaximumLength], ax
0x1800829dd  mov     [rsp+3B0h+NtName.Length], ax
0x1800829e2  movzx   edx, ax
0x1800829e5  shr     edx, 1
0x1800829e7  cmp     edx, 2
0x1800829ea  jnb     loc_180082D04
0x1800829f0  xor     dil, dil
0x1800829f3  mov     rax, [rbp+2B0h+RelativeName.ContainingDirectory]
0x1800829f7  lea     r9, [rbp+2B0h+IoStatusBlock]; IoStatusBlock
0x1800829fb  mov     [rbp+2B0h+ObjectAttributes.RootDirectory], rax
0x1800829ff  lea     r8, [rbp+2B0h+ObjectAttributes]; ObjectAttributes
0x180082a03  movzx   eax, r14b
0x180082a07  mov     [rsp+3B0h+OpenOptions], 4021h; OpenOptions
0x180082a0f  not     al
0x180082a11  mov     [rbp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x180082a18  and     eax, 1
0x180082a1b  mov     [rsp+3B0h+ShareAccess], 7; ShareAccess
0x180082a23  shl     eax, 6
0x180082a26  lea     rcx, [rsp+3B0h+FileHandle]; FileHandle
0x180082a2b  mov     [rbp+2B0h+ObjectAttributes.Attributes], eax
0x180082a2e  xorps   xmm0, xmm0
0x180082a31  lea     rax, [rsp+3B0h+NtName]
0x180082a36  mov     edx, 100001h; DesiredAccess
0x180082a3b  mov     [rbp+2B0h+ObjectAttributes.ObjectName], rax
0x180082a3f  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180082a44  call    cs:__imp_NtOpenFile
0x180082a4b  nop     dword ptr [rax+rax+00h]
0x180082a50  mov     ebx, eax
0x180082a52  test    dil, dil
0x180082a55  jz      short loc_180082A6D
0x180082a57  cmp     eax, 0C0000103h
0x180082a5c  jz      loc_180082E88
0x180082a62  cmp     eax, 0C000000Dh
0x180082a67  jz      loc_180082E88
0x180082a6d  test    ebx, ebx
0x180082a6f  js      loc_180082DB6
0x180082a75  cmp     word ptr [rsp+3B0h+PartName], 0
0x180082a7b  jz      loc_180082E08
0x180082a81  cmp     word ptr [rsp+3B0h+PartName], 6
0x180082a87  jz      loc_180082D2F
0x180082a8d  movzx   ecx, word ptr [rsp+3B0h+PartName]
0x180082a92  xor     eax, eax
0x180082a94  mov     rdx, [rsp+3B0h+PartName+8]
0x180082a99  mov     r10d, 3Ch ; '<'
0x180082a9f  test    ecx, 0FFFFFFFEh
0x180082aa5  jbe     short loc_180082ADD
0x180082aa7  test    eax, eax
0x180082aa9  jz      short loc_180082AB5
0x180082aab  cmp     word ptr [rdx], 2Eh ; '.'
0x180082aaf  jz      loc_180082D66
0x180082ab5  movzx   ecx, word ptr [rdx]
0x180082ab8  cmp     cx, 3Fh ; '?'
0x180082abc  jz      loc_180082CC3
0x180082ac2  cmp     cx, 2Ah ; '*'
0x180082ac6  jz      loc_180082CC8
0x180082acc  movzx   ecx, word ptr [rsp+3B0h+PartName]
0x180082ad1  inc     eax
0x180082ad3  shr     ecx, 1
0x180082ad5  add     rdx, 2
0x180082ad9  cmp     eax, ecx
0x180082adb  jb      short loc_180082AA7
0x180082add  test    r15b, r15b
0x180082ae0  jnz     loc_180082EFF
0x180082ae6  mov     edx, r14d
0x180082ae9  mov     eax, r12d
0x180082aec  and     edx, 4
0x180082aef  or      edx, 1
0x180082af2  add     edx, edx
0x180082af4  neg     eax
0x180082af6  lea     rax, [rsp+3B0h+PartName]
0x180082afb  mov     [rsp+3B0h+var_368], rax
0x180082b00  sbb     ecx, ecx
0x180082b02  mov     [rsp+3B0h+var_370], edx
0x180082b06  lea     rax, [rbp+2B0h+var_2B0]
0x180082b0a  add     ecx, 3
0x180082b0d  xor     r9d, r9d
0x180082b10  mov     [rsp+3B0h+var_378], ecx
0x180082b14  xor     r8d, r8d
0x180082b17  mov     rcx, [rsp+3B0h+FileHandle]
0x180082b1c  xor     edx, edx
0x180082b1e  mov     [rsp+3B0h+var_380], 268h
0x180082b26  mov     qword ptr [rsp+3B0h+OpenOptions], rax
0x180082b2b  lea     rax, [rbp+2B0h+IoStatusBlock]
0x180082b2f  mov     qword ptr [rsp+3B0h+ShareAccess], rax
0x180082b34  call    cs:__imp_NtQueryDirectoryFileEx
0x180082b3b  nop     dword ptr [rax+rax+00h]
0x180082b40  lea     rcx, [rbp+2B0h+RelativeName]; RelativeName
0x180082b44  mov     ebx, eax
0x180082b46  call    cs:__imp_RtlReleaseRelativeName
0x180082b4d  nop     dword ptr [rax+rax+00h]
0x180082b52  mov     rcx, gs:60h
0x180082b5b  mov     r8, r13; P
0x180082b5e  xor     edx, edx; Flags
0x180082b60  mov     rcx, [rcx+30h]; HeapHandle
0x180082b64  call    cs:__imp_RtlFreeHeap
0x180082b6b  nop     dword ptr [rax+rax+00h]
0x180082b70  test    ebx, ebx
0x180082b72  js      loc_180082D92
0x180082b78  mov     rax, [rbp+2B0h+var_2A8]
0x180082b7c  lea     rdx, [rbp+2B0h+var_26C]
0x180082b80  mov     rdi, [rbp+2B0h+var_278]
0x180082b84  mov     ecx, 206h
0x180082b89  mov     [rsi+4], rax
0x180082b8d  mov     rax, [rbp+2B0h+var_2A0]
0x180082b91  mov     [rsi+0Ch], rax
0x180082b95  mov     rax, [rbp+2B0h+var_298]
0x180082b99  mov     [rsi+14h], rax
0x180082b9d  mov     eax, [rbp+2B0h+var_284]
0x180082ba0  mov     [rsi+1Ch], eax
0x180082ba3  mov     eax, [rbp+2B0h+var_288]
0x180082ba6  mov     [rsi+20h], eax
0x180082ba9  mov     eax, dword ptr [rbp+2B0h+var_278+4]
0x180082bac  cmp     eax, ecx
0x180082bae  mov     [rsi], edi
0x180082bb0  cmova   eax, ecx
0x180082bb3  test    r12d, r12d
0x180082bb6  mov     ebx, eax
0x180082bb8  lea     rcx, [rsi+2Ch]; void *
0x180082bbc  lea     rax, [rbp+2B0h+Src]
0x180082bc0  mov     r8d, ebx; Size
0x180082bc3  cmovz   rdx, rax; Src
0x180082bc7  call    memcpy_0
0x180082bcc  shr     rbx, 1
0x180082bcf  xor     r15d, r15d
0x180082bd2  mov     [rsi+rbx*2+2Ch], r15w
0x180082bd8  test    r12d, r12d
0x180082bdb  jnz     loc_180082D7B
0x180082be1  movsx   eax, [rbp+2B0h+var_26C]
0x180082be5  cmp     al, 1Ah
0x180082be7  ja      loc_180082D88
0x180082bed  mov     ecx, eax
0x180082bef  cmp     eax, 18h
0x180082bf2  jnb     loc_180082D88
0x180082bf8  mov     ebx, ecx
0x180082bfa  lea     rdx, [rbp+2B0h+var_26A]; Src
0x180082bfe  mov     r8d, ebx; Size
0x180082c01  lea     rcx, [rsi+234h]; void *
0x180082c08  call    memcpy_0
0x180082c0d  shr     rbx, 1
0x180082c10  mov     [rsi+rbx*2+234h], r15w
0x180082c19  bt      edi, 0Ah
0x180082c1d  jnb     short loc_180082C25
0x180082c1f  mov     eax, [rbp+2B0h+var_270]
0x180082c22  mov     [rsi+24h], eax
0x180082c25  mov     rcx, gs:60h
0x180082c2e  mov     r8d, 50h ; 'P'; Size
0x180082c34  mov     edx, cs:KernelBaseGlobalData
0x180082c3a  mov     rdi, [rsp+3B0h+FileHandle]
0x180082c3f  add     edx, 0C0000h; Flags
0x180082c45  mov     rcx, [rcx+30h]; HeapHandle
0x180082c49  call    cs:__imp_RtlAllocateHeap
0x180082c50  nop     dword ptr [rax+rax+00h]
0x180082c55  mov     rbx, rax
0x180082c58  test    rax, rax
0x180082c5b  jz      loc_180082F32
0x180082c61  lea     rcx, [rax+28h]; CriticalSection
0x180082c65  mov     [rax], rdi
0x180082c68  mov     [rax+8], r15
0x180082c6c  mov     [rax+10h], r15
0x180082c70  mov     [rax+18h], r15
0x180082c74  mov     [rax+20h], r12d
0x180082c78  mov     [rax+24h], r14d
0x180082c7c  call    cs:__imp_RtlInitializeCriticalSection
0x180082c83  nop     dword ptr [rax+rax+00h]
0x180082c88  test    eax, eax
0x180082c8a  js      loc_180082F14
0x180082c90  mov     rax, rbx
0x180082c93  mov     r13, [rsp+3B0h+arg_8]
0x180082c9b  mov     r15, [rsp+3B0h+var_30]
0x180082ca3  mov     rcx, [rbp+2B0h+var_40]
0x180082caa  xor     rcx, rsp; StackCookie
0x180082cad  call    __security_check_cookie
0x180082cb2  add     rsp, 388h
0x180082cb9  pop     r14
0x180082cbb  pop     r12
0x180082cbd  pop     rdi
0x180082cbe  pop     rsi
0x180082cbf  pop     rbx
0x180082cc0  pop     rbp
0x180082cc1  retn
0x180082cc3  mov     word ptr [rdx], 3Eh ; '>'
0x180082cc8  test    eax, eax
0x180082cca  jz      loc_180082ACC
0x180082cd0  cmp     word ptr [rdx-2], 2Eh ; '.'
0x180082cd5  jnz     loc_180082ACC
0x180082cdb  mov     word ptr [rdx-2], 22h ; '"'
0x180082ce1  jmp     loc_180082ACC
0x180082ce6  mov     rcx, rax
0x180082ce9  mov     rax, [rbp+2B0h+DestinationString.Buffer]
0x180082ced  shr     rcx, 1
0x180082cf0  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x180082cf6  jnz     loc_180082935
0x180082cfc  mov     r15b, 1
0x180082cff  jmp     loc_180082938
0x180082d04  mov     r8, [rsp+3B0h+NtName.Buffer]
0x180082d09  lea     eax, [rdx-2]
0x180082d0c  cmp     word ptr [r8+rax*2], 3Ah ; ':'
0x180082d12  jz      loc_1800829F0
0x180082d18  lea     eax, [rdx-1]
0x180082d1b  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x180082d21  jnz     loc_1800829F0
0x180082d27  mov     dil, 1
0x180082d2a  jmp     loc_1800829F3
0x180082d2f  mov     rcx, [rsp+3B0h+PartName+8]; Source1
0x180082d34  lea     rdx, asc_1802A0390; "*.*"
0x180082d3b  mov     r8d, 6; Length
0x180082d41  call    cs:__imp_RtlCompareMemory
0x180082d48  nop     dword ptr [rax+rax+00h]
0x180082d4d  cmp     rax, 6
0x180082d51  jnz     loc_180082A8D
0x180082d57  mov     eax, 2
0x180082d5c  mov     word ptr [rsp+3B0h+PartName], ax
0x180082d61  jmp     loc_180082AE6
0x180082d66  cmp     word ptr [rdx-2], 2Ah ; '*'
0x180082d6b  jnz     loc_180082AB5
  ... truncated ...
```
