# BasepMoveFileDelayed

- ea: `0x180075848`
- end: `0x180075c37`
- name: `BasepMoveFileDelayed`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180100030`

## callees

- `0x180074ac8`
- `0x180075848`
- `0x180075c40`
- `0x180075d58`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800758da`
- `ntdll!RtlInitUnicodeString` at `0x18007590f`
- `ntdll!RtlInitUnicodeString` at `0x1800758da`
- `ntdll!RtlInitUnicodeString` at `0x18007590f`
- `ntdll!NtWaitForSingleObject` at `0x180075a5c`
- `ntdll!NtWaitForSingleObject` at `0x180075a5c`
- `ntdll!NtReleaseMutant` at `0x180075a99`
- `ntdll!NtReleaseMutant` at `0x180075a99`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800758b8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800758b8`
- `ntdll!NtCreateKeyTransacted` at `0x180075b1f`
- `ntdll!NtCreateKeyTransacted` at `0x180075b62`
- `ntdll!NtCreateKeyTransacted` at `0x180075b1f`
- `ntdll!NtCreateKeyTransacted` at `0x180075b62`
- `ntdll!NtCreateKey` at `0x18007596d`
- `ntdll!NtCreateKey` at `0x180075bd2`
- `ntdll!NtCreateKey` at `0x18007596d`
- `ntdll!NtCreateKey` at `0x180075bd2`
- `ntdll!NtClose` at `0x180075ab4`
- `ntdll!NtClose` at `0x180075aec`
- `ntdll!NtClose` at `0x180075ab4`
- `ntdll!NtClose` at `0x180075aec`
- `ntdll!RtlFreeHeap` at `0x180075adb`
- `ntdll!RtlFreeHeap` at `0x180075bf5`
- `ntdll!RtlFreeHeap` at `0x180075c26`
- `ntdll!RtlFreeHeap` at `0x180075adb`
- `ntdll!RtlFreeHeap` at `0x180075bf5`
- `ntdll!RtlFreeHeap` at `0x180075c26`
- `ntdll!RtlAllocateHeap` at `0x1800759d5`
- `ntdll!RtlAllocateHeap` at `0x180075b9e`
- `ntdll!RtlAllocateHeap` at `0x1800759d5`
- `ntdll!RtlAllocateHeap` at `0x180075b9e`

## string_xrefs

- `0x1800758f2`: `PendingFileRenameOperations%d`
- `0x1800758c8`: `\REGISTRY\MACHINE\OSDATA\Session Manager`
- `0x1800758d3`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager`
- `0x180075aff`: `PendingFileRenameOperations`

## pseudocode

```c
NTSTATUS __fastcall BasepMoveFileDelayed(const void **a1, const void **a2, unsigned int a3, int a4, __int64 a5)
{
  ULONG v5; // r14d
  char IsStateSeparationEnabled; // al
  const WCHAR *v10; // rdx
  WCHAR *v11; // rdx
  NTSTATUS result; // eax
  unsigned int v13; // r12d
  char *Heap; // rax
  char *v15; // rsi
  PVOID v16; // rdi
  __int64 v17; // rax
  char *v18; // rbx
  char *v19; // rcx
  int appended; // ebx
  HANDLE v21; // r15
  int v22; // r13d
  ULONG v23; // eax
  PULONG Disposition; // [rsp+30h] [rbp-D0h]
  SIZE_T Size; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h]
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[64]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = 0;
  v27 = a4;
  KeyHandle = 0;
  LODWORD(Size) = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v10 = L"\\REGISTRY\\MACHINE\\OSDATA\\Session Manager";
  if ( !IsStateSeparationEnabled )
    v10 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager";
  RtlInitUnicodeString(&DestinationString, v10);
  if ( a3 == 1 )
  {
    v11 = L"PendingFileRenameOperations";
  }
  else
  {
    RtlStringCchPrintfW(SourceString, 64, L"PendingFileRenameOperations%d", a3);
    v11 = SourceString;
  }
  RtlInitUnicodeString(&ValueName, v11);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 192;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a5 )
    result = NtCreateKeyTransacted(&KeyHandle, 3221225472LL, &ObjectAttributes, 0, 0, 0, a5, 0);
  else
    result = NtCreateKey(&KeyHandle, 0xC0000000, &ObjectAttributes, 0, 0, 0, 0);
  if ( result == -1073741790 )
  {
    if ( a5 )
      result = NtCreateKeyTransacted(&KeyHandle, 3221225472LL, &ObjectAttributes, 0, 0, 4, a5, 0);
    else
      result = NtCreateKey(&KeyHandle, 0xC0000000, &ObjectAttributes, 0, 0, 4u, 0);
  }
  if ( result >= 0 )
  {
    v13 = *(unsigned __int16 *)a1 + 6 + *(unsigned __int16 *)a2;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v13);
    v15 = Heap;
    if ( Heap )
    {
      v16 = 0;
      memcpy_0(Heap, a1[1], *(unsigned __int16 *)a1);
      v17 = *(unsigned __int16 *)a1;
      *(_WORD *)&v15[v17] = 0;
      v18 = &v15[v17 + 2];
      memcpy_0(v18, a2[1], *(unsigned __int16 *)a2);
      v19 = &v18[*(unsigned __int16 *)a2];
      *v19 = 0;
      *(_WORD *)(v19 + 1) = 0;
      v19[3] = 0;
      appended = BasepOpenPendingRenameMutex(&Handle);
      if ( appended >= 0 )
      {
        v21 = Handle;
        v22 = v27;
        while ( 1 )
        {
          NtWaitForSingleObject(v21, 0, 0);
          LODWORD(Disposition) = v13;
          appended = BasepRegistryAppendString(KeyHandle, &ValueName, (PULONG)&Size, v5, v15, (size_t)Disposition, v22);
          NtReleaseMutant(v21, 0);
          if ( appended != -1073741789 )
            break;
          v23 = Size;
          if ( (unsigned int)Size <= v5 )
          {
            appended = -1073741823;
            break;
          }
          if ( v16 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
            v23 = Size;
          }
          v5 = v23;
          v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v23);
          if ( !v16 )
          {
            appended = -1073741670;
            break;
          }
        }
        NtClose(v21);
        if ( v16 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    }
    else
    {
      appended = -1073741670;
    }
    NtClose(KeyHandle);
    return appended;
  }
  return result;
}

```

## disassembly

```asm
0x180075848  mov     [rsp-8+arg_18], rbx
0x18007584d  push    rbp
0x18007584e  push    rsi
0x18007584f  push    rdi
0x180075850  push    r12
0x180075852  push    r13
0x180075854  push    r14
0x180075856  push    r15
0x180075858  lea     rbp, [rsp-40h]
0x18007585d  sub     rsp, 140h
0x180075864  mov     rax, cs:__security_cookie
0x18007586b  xor     rax, rsp
0x18007586e  mov     [rbp+70h+var_40], rax
0x180075872  mov     rdi, [rbp+70h+arg_20]
0x180075879  xorps   xmm0, xmm0
0x18007587c  xor     r14d, r14d
0x18007587f  mov     [rsp+170h+var_120], r9d
0x180075884  xorps   xmm1, xmm1
0x180075887  mov     [rsp+170h+KeyHandle], r14
0x18007588c  movups  xmmword ptr [rsp+170h+ObjectAttributes.ObjectName], xmm0
0x180075891  xor     eax, eax
0x180075893  mov     dword ptr [rsp+170h+Size], r14d
0x180075898  movups  xmmword ptr [rsp+170h+ObjectAttributes+1Ch], xmm0
0x18007589d  mov     ebx, r8d
0x1800758a0  mov     [rsp+170h+Handle], r14
0x1800758a5  mov     r13, rdx
0x1800758a8  mov     r15, rcx
0x1800758ab  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x1800758b0  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1800758b4  movups  xmmword ptr [rbp+70h+ValueName.Length], xmm1
0x1800758b8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800758bf  nop     dword ptr [rax+rax+00h]
0x1800758c4  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800758c8  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\OSDATA\\Session Ma"...
0x1800758cf  test    al, al
0x1800758d1  jnz     short loc_1800758DA
0x1800758d3  lea     rdx, aRegistryMachin_37; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800758da  call    cs:__imp_RtlInitUnicodeString
0x1800758e1  nop     dword ptr [rax+rax+00h]
0x1800758e6  cmp     ebx, 1
0x1800758e9  jz      loc_180075AFF
0x1800758ef  mov     r9d, ebx
0x1800758f2  lea     r8, aPendingfileren; "PendingFileRenameOperations%d"
0x1800758f9  mov     edx, 40h ; '@'
0x1800758fe  lea     rcx, [rbp+70h+SourceString]
0x180075902  call    RtlStringCchPrintfW
0x180075907  lea     rdx, [rbp+70h+SourceString]; SourceString
0x18007590b  lea     rcx, [rbp+70h+ValueName]; DestinationString
0x18007590f  call    cs:__imp_RtlInitUnicodeString
0x180075916  nop     dword ptr [rax+rax+00h]
0x18007591b  xor     r9d, r9d; TitleIndex
0x18007591e  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x180075926  mov     [rsp+170h+ObjectAttributes.RootDirectory], r14
0x18007592b  lea     rax, [rbp+70h+DestinationString]
0x18007592f  mov     [rsp+170h+ObjectAttributes.Attributes], 0C0h
0x180075937  xorps   xmm0, xmm0
0x18007593a  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x18007593f  mov     ebx, 0C0000000h
0x180075944  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180075949  mov     edx, ebx; DesiredAccess
0x18007594b  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180075950  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x180075955  test    rdi, rdi
0x180075958  jnz     loc_180075B0B
0x18007595e  mov     [rsp+170h+Disposition], r14; Disposition
0x180075963  mov     [rsp+170h+CreateOptions], r14d; CreateOptions
0x180075968  mov     [rsp+170h+Class], r14; Class
0x18007596d  call    cs:__imp_NtCreateKey
0x180075974  nop     dword ptr [rax+rax+00h]
0x180075979  cmp     eax, 0C0000022h
0x18007597e  jz      loc_180075B37
0x180075984  test    eax, eax
0x180075986  jns     short loc_1800759B0
0x180075988  mov     rcx, [rbp+70h+var_40]
0x18007598c  xor     rcx, rsp; StackCookie
0x18007598f  call    __security_check_cookie
0x180075994  mov     rbx, [rsp+170h+arg_18]
0x18007599c  add     rsp, 140h
0x1800759a3  pop     r15
0x1800759a5  pop     r14
0x1800759a7  pop     r13
0x1800759a9  pop     r12
0x1800759ab  pop     rdi
0x1800759ac  pop     rsi
0x1800759ad  pop     rbp
0x1800759ae  retn
0x1800759b0  movzx   ecx, word ptr [r15]
0x1800759b4  movzx   r12d, word ptr [r13+0]
0x1800759b9  add     ecx, 6
0x1800759bc  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800759c2  add     r12d, ecx
0x1800759c5  mov     rcx, gs:60h
0x1800759ce  mov     r8d, r12d; Size
0x1800759d1  mov     rcx, [rcx+30h]; HeapHandle
0x1800759d5  call    cs:__imp_RtlAllocateHeap
0x1800759dc  nop     dword ptr [rax+rax+00h]
0x1800759e1  mov     rsi, rax
0x1800759e4  test    rax, rax
0x1800759e7  jz      loc_180075B30
0x1800759ed  movzx   r8d, word ptr [r15]; Size
0x1800759f1  mov     rcx, rax; void *
0x1800759f4  mov     rdx, [r15+8]; Src
0x1800759f8  mov     rdi, r14
0x1800759fb  call    memcpy_0
0x180075a00  movzx   eax, word ptr [r15]
0x180075a04  xor     r15d, r15d
0x180075a07  mov     [rax+rsi], r15w
0x180075a0c  lea     rbx, [rax+2]
0x180075a10  movzx   r8d, word ptr [r13+0]; Size
0x180075a15  add     rbx, rsi
0x180075a18  mov     rdx, [r13+8]; Src
0x180075a1c  mov     rcx, rbx; void *
0x180075a1f  call    memcpy_0
0x180075a24  movzx   eax, word ptr [r13+0]
0x180075a29  lea     rcx, [rax+rbx]
0x180075a2d  mov     [rax+rbx], r15b
0x180075a31  mov     [rcx+1], r15w
0x180075a36  mov     [rcx+3], r15b
0x180075a3a  lea     rcx, [rsp+170h+Handle]
0x180075a3f  call    BasepOpenPendingRenameMutex
0x180075a44  mov     ebx, eax
0x180075a46  test    eax, eax
0x180075a48  js      short loc_180075AC9
0x180075a4a  mov     r15, [rsp+170h+Handle]
0x180075a4f  mov     r13d, [rsp+170h+var_120]
0x180075a54  xor     r8d, r8d; Timeout
0x180075a57  xor     edx, edx; Alertable
0x180075a59  mov     rcx, r15; Handle
0x180075a5c  call    cs:__imp_NtWaitForSingleObject
0x180075a63  nop     dword ptr [rax+rax+00h]
0x180075a68  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180075a6d  lea     r8, [rsp+170h+Size]; ResultLength
0x180075a72  mov     [rsp+170h+var_138], r13d; int
0x180075a77  lea     rdx, [rbp+70h+ValueName]; ValueName
0x180075a7b  mov     dword ptr [rsp+170h+Disposition], r12d; Size
0x180075a80  mov     r9, rdi
0x180075a83  mov     qword ptr [rsp+170h+CreateOptions], rsi; Src
0x180075a88  mov     dword ptr [rsp+170h+Class], r14d; ULONG
0x180075a8d  call    BasepRegistryAppendString
0x180075a92  xor     edx, edx; ReleaseCount
0x180075a94  mov     rcx, r15; MutantHandle
0x180075a97  mov     ebx, eax
0x180075a99  call    cs:__imp_NtReleaseMutant
0x180075aa0  nop     dword ptr [rax+rax+00h]
0x180075aa5  cmp     ebx, 0C0000023h
0x180075aab  jz      loc_180075B73
0x180075ab1  mov     rcx, r15; Handle
0x180075ab4  call    cs:__imp_NtClose
0x180075abb  nop     dword ptr [rax+rax+00h]
0x180075ac0  test    rdi, rdi
0x180075ac3  jnz     loc_180075C14
0x180075ac9  mov     rcx, gs:60h
0x180075ad2  mov     r8, rsi; P
0x180075ad5  xor     edx, edx; Flags
0x180075ad7  mov     rcx, [rcx+30h]; HeapHandle
0x180075adb  call    cs:__imp_RtlFreeHeap
0x180075ae2  nop     dword ptr [rax+rax+00h]
0x180075ae7  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x180075aec  call    cs:__imp_NtClose
0x180075af3  nop     dword ptr [rax+rax+00h]
0x180075af8  mov     eax, ebx
0x180075afa  jmp     loc_180075988
0x180075aff  lea     rdx, aPendingfileren_0; "PendingFileRenameOperations"
0x180075b06  jmp     loc_18007590B
0x180075b0b  mov     qword ptr [rsp+170h+var_138], r14
0x180075b10  mov     [rsp+170h+Disposition], rdi
0x180075b15  mov     [rsp+170h+CreateOptions], r14d
0x180075b1a  mov     [rsp+170h+Class], r14
0x180075b1f  call    cs:__imp_NtCreateKeyTransacted
0x180075b26  nop     dword ptr [rax+rax+00h]
0x180075b2b  jmp     loc_180075979
0x180075b30  mov     ebx, 0C000009Ah
0x180075b35  jmp     short loc_180075AE7
0x180075b37  xor     r9d, r9d; TitleIndex
0x180075b3a  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180075b3f  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180075b44  mov     edx, ebx; DesiredAccess
0x180075b46  test    rdi, rdi
0x180075b49  jz      short loc_180075BC0
0x180075b4b  mov     qword ptr [rsp+170h+var_138], r14
0x180075b50  mov     [rsp+170h+Disposition], rdi
0x180075b55  mov     [rsp+170h+CreateOptions], 4
0x180075b5d  mov     [rsp+170h+Class], r14
0x180075b62  call    cs:__imp_NtCreateKeyTransacted
0x180075b69  nop     dword ptr [rax+rax+00h]
0x180075b6e  jmp     loc_180075984
0x180075b73  mov     eax, dword ptr [rsp+170h+Size]
0x180075b77  cmp     eax, r14d
0x180075b7a  jbe     loc_180075C0A
0x180075b80  test    rdi, rdi
0x180075b83  jnz     short loc_180075BE3
0x180075b85  mov     rcx, gs:60h
0x180075b8e  mov     edx, cs:KernelBaseGlobalData; Flags
0x180075b94  mov     r8d, eax; Size
0x180075b97  mov     r14d, eax
0x180075b9a  mov     rcx, [rcx+30h]; HeapHandle
0x180075b9e  call    cs:__imp_RtlAllocateHeap
0x180075ba5  nop     dword ptr [rax+rax+00h]
0x180075baa  mov     rdi, rax
0x180075bad  test    rax, rax
0x180075bb0  jnz     loc_180075A54
0x180075bb6  mov     ebx, 0C000009Ah
0x180075bbb  jmp     loc_180075AB1
0x180075bc0  mov     [rsp+170h+Disposition], r14; Disposition
0x180075bc5  mov     [rsp+170h+CreateOptions], 4; CreateOptions
0x180075bcd  mov     [rsp+170h+Class], r14; Class
0x180075bd2  call    cs:__imp_NtCreateKey
0x180075bd9  nop     dword ptr [rax+rax+00h]
0x180075bde  jmp     loc_180075984
0x180075be3  mov     rcx, gs:60h
0x180075bec  mov     r8, rdi; P
0x180075bef  xor     edx, edx; Flags
0x180075bf1  mov     rcx, [rcx+30h]; HeapHandle
0x180075bf5  call    cs:__imp_RtlFreeHeap
0x180075bfc  nop     dword ptr [rax+rax+00h]
0x180075c01  mov     eax, dword ptr [rsp+170h+Size]
0x180075c05  jmp     loc_180075B85
0x180075c0a  mov     ebx, 0C0000001h
0x180075c0f  jmp     loc_180075AB1
0x180075c14  mov     rcx, gs:60h
0x180075c1d  mov     r8, rdi; P
0x180075c20  xor     edx, edx; Flags
0x180075c22  mov     rcx, [rcx+30h]; HeapHandle
0x180075c26  call    cs:__imp_RtlFreeHeap
0x180075c2d  nop     dword ptr [rax+rax+00h]
0x180075c32  jmp     loc_180075AC9
```
