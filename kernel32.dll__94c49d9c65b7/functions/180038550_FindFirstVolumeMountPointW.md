# FindFirstVolumeMountPointW

- ea: `0x180038550`
- end: `0x18003876d`
- name: `FindFirstVolumeMountPointW`
- size: `541`
- prototype: `HANDLE __stdcall(LPCWSTR lpszRootPathName, LPWSTR lpszVolumeMountPoint, DWORD cchBufferLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18006c740`

## callees

- `0x18000f920`
- `0x180038550`
- `0x180038774`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18003858b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003858b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180038645`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180038645`
- `ntdll!RtlSetLastWin32Error` at `0x1800386e9`
- `ntdll!RtlSetLastWin32Error` at `0x180038756`
- `ntdll!RtlSetLastWin32Error` at `0x1800386e9`
- `ntdll!RtlSetLastWin32Error` at `0x180038756`
- `ntdll!RtlCopyUnicodeString` at `0x180038637`
- `ntdll!RtlCopyUnicodeString` at `0x180038637`
- `ntdll!RtlInitUnicodeString` at `0x1800385d5`
- `ntdll!RtlInitUnicodeString` at `0x1800385d5`
- `ntdll!RtlFreeHeap` at `0x18003869d`
- `ntdll!RtlFreeHeap` at `0x180038737`
- `ntdll!RtlFreeHeap` at `0x18003869d`
- `ntdll!RtlFreeHeap` at `0x180038737`
- `ntdll!RtlAllocateHeap` at `0x180038618`
- `ntdll!RtlAllocateHeap` at `0x1800386cf`
- `ntdll!RtlAllocateHeap` at `0x180038618`
- `ntdll!RtlAllocateHeap` at `0x1800386cf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800385fe`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800386b4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800385fe`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800386b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800386e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003871f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800386e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003871f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800385bb`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800385bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038681`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038681`

## string_xrefs

- `0x1800385ca`: `$Extend\$Reparse:$R:$INDEX_ALLOCATION`

## pseudocode

```c
HANDLE __stdcall FindFirstVolumeMountPointW(
        LPCWSTR lpszRootPathName,
        LPWSTR lpszVolumeMountPoint,
        DWORD cchBufferLength)
{
  NTSTATUS inited; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  ULONG *GlobalData; // rax
  ULONG v12; // ecx
  HANDLE FileW; // rsi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  ULONG *v19; // rax
  HANDLE *Heap; // rax
  HANDLE *v21; // rdi
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-18h] BYREF

  DestinationString = 0;
  Source = 0;
  Destination = 0;
  if ( !lpszRootPathName )
    goto LABEL_18;
  inited = RtlInitUnicodeStringEx(&DestinationString, lpszRootPathName);
  if ( inited >= 0 )
  {
    if ( DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92 )
      goto LABEL_17;
    if ( GetDriveTypeW(lpszRootPathName) != 4 )
    {
      RtlInitUnicodeString(&Source, L"$Extend\\$Reparse:$R:$INDEX_ALLOCATION");
      v10 = Source.Length + (unsigned int)DestinationString.Length + 2;
      if ( (unsigned int)v10 <= 0xFFFF )
      {
        Destination.MaximumLength = Source.Length + DestinationString.Length + 2;
        Destination.Length = 0;
        GlobalData = (ULONG *)KernelBaseGetGlobalData(Source.Length, v10, v8, v9);
        Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, Destination.MaximumLength);
        if ( Destination.Buffer )
        {
          RtlCopyUnicodeString(&Destination, &DestinationString);
          RtlAppendUnicodeStringToString(&Destination, &Source);
          Destination.Buffer[(unsigned __int64)Destination.Length >> 1] = 0;
          FileW = CreateFileW(Destination.Buffer, 0x80000000, 1u, 0, 3u, 0x2020000u, 0);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
          if ( FileW != (HANDLE)-1LL )
          {
            v19 = (ULONG *)KernelBaseGetGlobalData(v15, v14, v16, v17);
            Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v19, 0x18u);
            v21 = Heap;
            if ( Heap )
            {
              Heap[1] = 0;
              Heap[2] = 0;
              *Heap = FileW;
              if ( (unsigned int)FindNextVolumeMountPointHelper((__int64)Heap, lpszVolumeMountPoint, cchBufferLength, 1) )
                return v21;
              CloseHandle(*v21);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
            }
            else
            {
              CloseHandle(FileW);
              RtlSetLastWin32Error(8u);
            }
          }
          return (HANDLE)-1LL;
        }
        v12 = 8;
        goto LABEL_19;
      }
LABEL_17:
      v7 = 3221225523LL;
      goto LABEL_4;
    }
LABEL_18:
    v12 = 87;
LABEL_19:
    RtlSetLastWin32Error(v12);
    return (HANDLE)-1LL;
  }
  v7 = (unsigned int)inited;
LABEL_4:
  BaseSetLastNTError(v7);
  return (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180038550  push    rbp
0x180038552  push    rbx
0x180038553  push    rsi
0x180038554  push    rdi
0x180038555  push    r14
0x180038557  push    r15
0x180038559  mov     rbp, rsp
0x18003855c  sub     rsp, 78h
0x180038560  xorps   xmm0, xmm0
0x180038563  xorps   xmm1, xmm1
0x180038566  mov     r14d, r8d
0x180038569  mov     r15, rdx
0x18003856c  mov     rbx, rcx
0x18003856f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180038573  movups  xmmword ptr [rbp+Source.Length], xmm1
0x180038577  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18003857b  test    rcx, rcx
0x18003857e  jz      loc_180038751
0x180038584  mov     rdx, rcx; SourceString
0x180038587  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003858b  call    cs:__imp_RtlInitUnicodeStringEx
0x180038591  test    eax, eax
0x180038593  jns     short loc_1800385A1
0x180038595  mov     ecx, eax
0x180038597  call    BaseSetLastNTError
0x18003859c  jmp     loc_18003875C
0x1800385a1  movzx   ecx, [rbp+DestinationString.Length]
0x1800385a5  mov     rax, [rbp+DestinationString.Buffer]
0x1800385a9  shr     rcx, 1
0x1800385ac  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800385b2  jnz     loc_180038747
0x1800385b8  mov     rcx, rbx; lpRootPathName
0x1800385bb  call    cs:__imp_GetDriveTypeW
0x1800385c1  cmp     eax, 4
0x1800385c4  jz      loc_180038751
0x1800385ca  lea     rdx, aExtendReparseR; "$Extend\\$Reparse:$R:$INDEX_ALLOCATION"
0x1800385d1  lea     rcx, [rbp+Source]; DestinationString
0x1800385d5  call    cs:__imp_RtlInitUnicodeString
0x1800385db  movzx   edx, [rbp+DestinationString.Length]
0x1800385df  movzx   ecx, [rbp+Source.Length]
0x1800385e3  add     edx, 2
0x1800385e6  add     edx, ecx
0x1800385e8  cmp     edx, 0FFFFh
0x1800385ee  ja      loc_180038747
0x1800385f4  xor     eax, eax
0x1800385f6  mov     [rbp+Destination.MaximumLength], dx
0x1800385fa  mov     [rbp+Destination.Length], ax
0x1800385fe  call    cs:__imp_KernelBaseGetGlobalData
0x180038604  mov     rcx, gs:60h
0x18003860d  movzx   r8d, [rbp+Destination.MaximumLength]; Size
0x180038612  mov     edx, [rax]; Flags
0x180038614  mov     rcx, [rcx+30h]; HeapHandle
0x180038618  call    cs:__imp_RtlAllocateHeap
0x18003861e  mov     [rbp+Destination.Buffer], rax
0x180038622  test    rax, rax
0x180038625  jnz     short loc_18003862F
0x180038627  lea     ecx, [rax+8]
0x18003862a  jmp     loc_180038756
0x18003862f  lea     rdx, [rbp+DestinationString]; SourceString
0x180038633  lea     rcx, [rbp+Destination]; DestinationString
0x180038637  call    cs:__imp_RtlCopyUnicodeString
0x18003863d  lea     rdx, [rbp+Source]; Source
0x180038641  lea     rcx, [rbp+Destination]; Destination
0x180038645  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003864b  movzx   edx, [rbp+Destination.Length]
0x18003864f  xor     ecx, ecx
0x180038651  mov     rax, [rbp+Destination.Buffer]
0x180038655  xor     r9d, r9d; lpSecurityAttributes
0x180038658  mov     [rsp+78h+hTemplateFile], rcx; hTemplateFile
0x18003865d  shr     rdx, 1
0x180038660  lea     r8d, [rcx+1]; dwShareMode
0x180038664  mov     [rsp+78h+dwFlagsAndAttributes], 2020000h; dwFlagsAndAttributes
0x18003866c  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180038674  mov     [rax+rdx*2], cx
0x180038678  mov     edx, 80000000h; dwDesiredAccess
0x18003867d  mov     rcx, [rbp+Destination.Buffer]; lpFileName
0x180038681  call    cs:__imp_CreateFileW
0x180038687  mov     rcx, gs:60h
0x180038690  xor     edx, edx; Flags
0x180038692  mov     r8, [rbp+Destination.Buffer]; P
0x180038696  mov     rsi, rax
0x180038699  mov     rcx, [rcx+30h]; HeapHandle
0x18003869d  call    cs:__imp_RtlFreeHeap
0x1800386a3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800386a7  cmp     rsi, rbx
0x1800386aa  jnz     short loc_1800386B4
0x1800386ac  mov     rax, rbx
0x1800386af  jmp     loc_180038760
0x1800386b4  call    cs:__imp_KernelBaseGetGlobalData
0x1800386ba  mov     rcx, gs:60h
0x1800386c3  mov     r8d, 18h; Size
0x1800386c9  mov     edx, [rax]; Flags
0x1800386cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800386cf  call    cs:__imp_RtlAllocateHeap
0x1800386d5  mov     rdi, rax
0x1800386d8  test    rax, rax
0x1800386db  jnz     short loc_1800386F1
0x1800386dd  mov     rcx, rsi; hObject
0x1800386e0  call    cs:__imp_CloseHandle
0x1800386e6  lea     ecx, [rdi+8]; LastError
0x1800386e9  call    cs:__imp_RtlSetLastWin32Error
0x1800386ef  jmp     short loc_1800386AC
0x1800386f1  mov     qword ptr [rax+8], 0
0x1800386f9  mov     r9d, 1
0x1800386ff  mov     qword ptr [rax+10h], 0
0x180038707  mov     r8d, r14d
0x18003870a  mov     rdx, r15
0x18003870d  mov     [rax], rsi
0x180038710  mov     rcx, rdi
0x180038713  call    FindNextVolumeMountPointHelper
0x180038718  test    eax, eax
0x18003871a  jnz     short loc_180038742
0x18003871c  mov     rcx, [rdi]; hObject
0x18003871f  call    cs:__imp_CloseHandle
0x180038725  mov     rcx, gs:60h
0x18003872e  mov     r8, rdi; P
0x180038731  xor     edx, edx; Flags
0x180038733  mov     rcx, [rcx+30h]; HeapHandle
0x180038737  call    cs:__imp_RtlFreeHeap
0x18003873d  jmp     loc_1800386AC
0x180038742  mov     rax, rdi
0x180038745  jmp     short loc_180038760
0x180038747  mov     ecx, 0C0000033h
0x18003874c  jmp     loc_180038597
0x180038751  mov     ecx, 57h ; 'W'; LastError
0x180038756  call    cs:__imp_RtlSetLastWin32Error
0x18003875c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038760  add     rsp, 78h
0x180038764  pop     r15
0x180038766  pop     r14
0x180038768  pop     rdi
0x180038769  pop     rsi
0x18003876a  pop     rbx
0x18003876b  pop     rbp
0x18003876c  retn
```
