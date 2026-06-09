# BasepMoveFileDelayed

- ea: `0x1801006c0`
- end: `0x180100a47`
- name: `BasepMoveFileDelayed`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f6f80`

## callees

- `0x18006fd7c`
- `0x1801006c0`
- `0x180100a50`
- `0x180100b5c`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18010074c`
- `ntdll!RtlInitUnicodeString` at `0x18010077b`
- `ntdll!RtlInitUnicodeString` at `0x18010074c`
- `ntdll!RtlInitUnicodeString` at `0x18010077b`
- `ntdll!NtWaitForSingleObject` at `0x1801008b5`
- `ntdll!NtWaitForSingleObject` at `0x1801008b5`
- `ntdll!NtReleaseMutant` at `0x1801008ec`
- `ntdll!NtReleaseMutant` at `0x1801008ec`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180100730`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180100730`
- `ntdll!NtCreateKeyTransacted` at `0x18010095a`
- `ntdll!NtCreateKeyTransacted` at `0x180100997`
- `ntdll!NtCreateKeyTransacted` at `0x18010095a`
- `ntdll!NtCreateKeyTransacted` at `0x180100997`
- `ntdll!NtCreateKey` at `0x1801007d3`
- `ntdll!NtCreateKey` at `0x1801009f7`
- `ntdll!NtCreateKey` at `0x1801007d3`
- `ntdll!NtCreateKey` at `0x1801009f7`
- `ntdll!NtClose` at `0x180100901`
- `ntdll!NtClose` at `0x18010092d`
- `ntdll!NtClose` at `0x180100901`
- `ntdll!NtClose` at `0x18010092d`
- `ntdll!RtlFreeHeap` at `0x180100922`
- `ntdll!RtlFreeHeap` at `0x180100a14`
- `ntdll!RtlFreeHeap` at `0x180100a3c`
- `ntdll!RtlFreeHeap` at `0x180100922`
- `ntdll!RtlFreeHeap` at `0x180100a14`
- `ntdll!RtlFreeHeap` at `0x180100a3c`
- `ntdll!RtlAllocateHeap` at `0x180100834`
- `ntdll!RtlAllocateHeap` at `0x1801009c9`
- `ntdll!RtlAllocateHeap` at `0x180100834`
- `ntdll!RtlAllocateHeap` at `0x1801009c9`

## string_xrefs

- `0x18010075e`: `PendingFileRenameOperations%d`
- `0x18010073a`: `\REGISTRY\MACHINE\OSDATA\Session Manager`
- `0x180100745`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager`
- `0x18010093a`: `PendingFileRenameOperations`

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
0x1801006c0  mov     [rsp-8+arg_18], rbx
0x1801006c5  push    rbp
0x1801006c6  push    rsi
0x1801006c7  push    rdi
0x1801006c8  push    r12
0x1801006ca  push    r13
0x1801006cc  push    r14
0x1801006ce  push    r15
0x1801006d0  lea     rbp, [rsp-40h]
0x1801006d5  sub     rsp, 140h
0x1801006dc  mov     rax, cs:__security_cookie
0x1801006e3  xor     rax, rsp
0x1801006e6  mov     [rbp+70h+var_40], rax
0x1801006ea  mov     rdi, [rbp+70h+arg_20]
0x1801006f1  xorps   xmm0, xmm0
0x1801006f4  xor     r14d, r14d
0x1801006f7  mov     [rsp+170h+var_120], r9d
0x1801006fc  xorps   xmm1, xmm1
0x1801006ff  mov     [rsp+170h+KeyHandle], r14
0x180100704  movups  xmmword ptr [rsp+170h+ObjectAttributes.ObjectName], xmm0
0x180100709  xor     eax, eax
0x18010070b  mov     dword ptr [rsp+170h+Size], r14d
0x180100710  movups  xmmword ptr [rsp+170h+ObjectAttributes+1Ch], xmm0
0x180100715  mov     ebx, r8d
0x180100718  mov     [rsp+170h+Handle], r14
0x18010071d  mov     r13, rdx
0x180100720  mov     r15, rcx
0x180100723  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x180100728  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18010072c  movups  xmmword ptr [rbp+70h+ValueName.Length], xmm1
0x180100730  call    cs:__imp_RtlIsStateSeparationEnabled
0x180100736  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x18010073a  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\OSDATA\\Session Ma"...
0x180100741  test    al, al
0x180100743  jnz     short loc_18010074C
0x180100745  lea     rdx, aRegistryMachin_37; "\\Registry\\Machine\\System\\CurrentCon"...
0x18010074c  call    cs:__imp_RtlInitUnicodeString
0x180100752  cmp     ebx, 1
0x180100755  jz      loc_18010093A
0x18010075b  mov     r9d, ebx
0x18010075e  lea     r8, aPendingfileren; "PendingFileRenameOperations%d"
0x180100765  mov     edx, 40h ; '@'
0x18010076a  lea     rcx, [rbp+70h+SourceString]
0x18010076e  call    RtlStringCchPrintfW
0x180100773  lea     rdx, [rbp+70h+SourceString]; SourceString
0x180100777  lea     rcx, [rbp+70h+ValueName]; DestinationString
0x18010077b  call    cs:__imp_RtlInitUnicodeString
0x180100781  xor     r9d, r9d; TitleIndex
0x180100784  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x18010078c  mov     [rsp+170h+ObjectAttributes.RootDirectory], r14
0x180100791  lea     rax, [rbp+70h+DestinationString]
0x180100795  mov     [rsp+170h+ObjectAttributes.Attributes], 0C0h
0x18010079d  xorps   xmm0, xmm0
0x1801007a0  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1801007a5  mov     ebx, 0C0000000h
0x1801007aa  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1801007af  mov     edx, ebx; DesiredAccess
0x1801007b1  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1801007b6  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801007bb  test    rdi, rdi
0x1801007be  jnz     loc_180100946
0x1801007c4  mov     [rsp+170h+Disposition], r14; Disposition
0x1801007c9  mov     [rsp+170h+CreateOptions], r14d; CreateOptions
0x1801007ce  mov     [rsp+170h+Class], r14; Class
0x1801007d3  call    cs:__imp_NtCreateKey
0x1801007d9  cmp     eax, 0C0000022h
0x1801007de  jz      loc_18010096C
0x1801007e4  test    eax, eax
0x1801007e6  jns     short loc_18010080F
0x1801007e8  mov     rcx, [rbp+70h+var_40]
0x1801007ec  xor     rcx, rsp; StackCookie
0x1801007ef  call    __security_check_cookie
0x1801007f4  mov     rbx, [rsp+170h+arg_18]
0x1801007fc  add     rsp, 140h
0x180100803  pop     r15
0x180100805  pop     r14
0x180100807  pop     r13
0x180100809  pop     r12
0x18010080b  pop     rdi
0x18010080c  pop     rsi
0x18010080d  pop     rbp
0x18010080e  retn
0x18010080f  movzx   ecx, word ptr [r15]
0x180100813  movzx   r12d, word ptr [r13+0]
0x180100818  add     ecx, 6
0x18010081b  mov     edx, cs:KernelBaseGlobalData; Flags
0x180100821  add     r12d, ecx
0x180100824  mov     rcx, gs:60h
0x18010082d  mov     r8d, r12d; Size
0x180100830  mov     rcx, [rcx+30h]; HeapHandle
0x180100834  call    cs:__imp_RtlAllocateHeap
0x18010083a  mov     rsi, rax
0x18010083d  test    rax, rax
0x180100840  jz      loc_180100965
0x180100846  movzx   r8d, word ptr [r15]; Size
0x18010084a  mov     rcx, rax; void *
0x18010084d  mov     rdx, [r15+8]; Src
0x180100851  mov     rdi, r14
0x180100854  call    memcpy_0
0x180100859  movzx   eax, word ptr [r15]
0x18010085d  xor     r15d, r15d
0x180100860  mov     [rax+rsi], r15w
0x180100865  lea     rbx, [rax+2]
0x180100869  movzx   r8d, word ptr [r13+0]; Size
0x18010086e  add     rbx, rsi
0x180100871  mov     rdx, [r13+8]; Src
0x180100875  mov     rcx, rbx; void *
0x180100878  call    memcpy_0
0x18010087d  movzx   eax, word ptr [r13+0]
0x180100882  lea     rcx, [rax+rbx]
0x180100886  mov     [rax+rbx], r15b
0x18010088a  mov     [rcx+1], r15w
0x18010088f  mov     [rcx+3], r15b
0x180100893  lea     rcx, [rsp+170h+Handle]
0x180100898  call    BasepOpenPendingRenameMutex
0x18010089d  mov     ebx, eax
0x18010089f  test    eax, eax
0x1801008a1  js      short loc_180100910
0x1801008a3  mov     r15, [rsp+170h+Handle]
0x1801008a8  mov     r13d, [rsp+170h+var_120]
0x1801008ad  xor     r8d, r8d; Timeout
0x1801008b0  xor     edx, edx; Alertable
0x1801008b2  mov     rcx, r15; Handle
0x1801008b5  call    cs:__imp_NtWaitForSingleObject
0x1801008bb  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1801008c0  lea     r8, [rsp+170h+Size]; ResultLength
0x1801008c5  mov     [rsp+170h+var_138], r13d; int
0x1801008ca  lea     rdx, [rbp+70h+ValueName]; ValueName
0x1801008ce  mov     dword ptr [rsp+170h+Disposition], r12d; Size
0x1801008d3  mov     r9, rdi
0x1801008d6  mov     qword ptr [rsp+170h+CreateOptions], rsi; Src
0x1801008db  mov     dword ptr [rsp+170h+Class], r14d; ULONG
0x1801008e0  call    BasepRegistryAppendString
0x1801008e5  xor     edx, edx; ReleaseCount
0x1801008e7  mov     rcx, r15; MutantHandle
0x1801008ea  mov     ebx, eax
0x1801008ec  call    cs:__imp_NtReleaseMutant
0x1801008f2  cmp     ebx, 0C0000023h
0x1801008f8  jz      loc_1801009A2
0x1801008fe  mov     rcx, r15; Handle
0x180100901  call    cs:__imp_NtClose
0x180100907  test    rdi, rdi
0x18010090a  jnz     loc_180100A2A
0x180100910  mov     rcx, gs:60h
0x180100919  mov     r8, rsi; P
0x18010091c  xor     edx, edx; Flags
0x18010091e  mov     rcx, [rcx+30h]; HeapHandle
0x180100922  call    cs:__imp_RtlFreeHeap
0x180100928  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x18010092d  call    cs:__imp_NtClose
0x180100933  mov     eax, ebx
0x180100935  jmp     loc_1801007E8
0x18010093a  lea     rdx, aPendingfileren_0; "PendingFileRenameOperations"
0x180100941  jmp     loc_180100777
0x180100946  mov     qword ptr [rsp+170h+var_138], r14
0x18010094b  mov     [rsp+170h+Disposition], rdi
0x180100950  mov     [rsp+170h+CreateOptions], r14d
0x180100955  mov     [rsp+170h+Class], r14
0x18010095a  call    cs:__imp_NtCreateKeyTransacted
0x180100960  jmp     loc_1801007D9
0x180100965  mov     ebx, 0C000009Ah
0x18010096a  jmp     short loc_180100928
0x18010096c  xor     r9d, r9d; TitleIndex
0x18010096f  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180100974  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180100979  mov     edx, ebx; DesiredAccess
0x18010097b  test    rdi, rdi
0x18010097e  jz      short loc_1801009E5
0x180100980  mov     qword ptr [rsp+170h+var_138], r14
0x180100985  mov     [rsp+170h+Disposition], rdi
0x18010098a  mov     [rsp+170h+CreateOptions], 4
0x180100992  mov     [rsp+170h+Class], r14
0x180100997  call    cs:__imp_NtCreateKeyTransacted
0x18010099d  jmp     loc_1801007E4
0x1801009a2  mov     eax, dword ptr [rsp+170h+Size]
0x1801009a6  cmp     eax, r14d
0x1801009a9  jbe     short loc_180100A20
0x1801009ab  test    rdi, rdi
0x1801009ae  jnz     short loc_180100A02
0x1801009b0  mov     rcx, gs:60h
0x1801009b9  mov     edx, cs:KernelBaseGlobalData; Flags
0x1801009bf  mov     r8d, eax; Size
0x1801009c2  mov     r14d, eax
0x1801009c5  mov     rcx, [rcx+30h]; HeapHandle
0x1801009c9  call    cs:__imp_RtlAllocateHeap
0x1801009cf  mov     rdi, rax
0x1801009d2  test    rax, rax
0x1801009d5  jnz     loc_1801008AD
0x1801009db  mov     ebx, 0C000009Ah
0x1801009e0  jmp     loc_1801008FE
0x1801009e5  mov     [rsp+170h+Disposition], r14; Disposition
0x1801009ea  mov     [rsp+170h+CreateOptions], 4; CreateOptions
0x1801009f2  mov     [rsp+170h+Class], r14; Class
0x1801009f7  call    cs:__imp_NtCreateKey
0x1801009fd  jmp     loc_1801007E4
0x180100a02  mov     rcx, gs:60h
0x180100a0b  mov     r8, rdi; P
0x180100a0e  xor     edx, edx; Flags
0x180100a10  mov     rcx, [rcx+30h]; HeapHandle
0x180100a14  call    cs:__imp_RtlFreeHeap
0x180100a1a  mov     eax, dword ptr [rsp+170h+Size]
0x180100a1e  jmp     short loc_1801009B0
0x180100a20  mov     ebx, 0C0000001h
0x180100a25  jmp     loc_1801008FE
0x180100a2a  mov     rcx, gs:60h
0x180100a33  mov     r8, rdi; P
0x180100a36  xor     edx, edx; Flags
0x180100a38  mov     rcx, [rcx+30h]; HeapHandle
0x180100a3c  call    cs:__imp_RtlFreeHeap
0x180100a42  jmp     loc_180100910
```
