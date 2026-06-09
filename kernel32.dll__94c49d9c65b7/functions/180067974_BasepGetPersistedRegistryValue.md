# BasepGetPersistedRegistryValue

- ea: `0x180067974`
- end: `0x180067b0d`
- name: `BasepGetPersistedRegistryValue`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180059260`

## callees

- `0x18003379c`
- `0x180067974`
- `0x18007a80d`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180067a5b`
- `ntdll!RtlNtStatusToDosError` at `0x180067a5b`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800679e9`
- `ntdll!RtlGetPersistedStateLocation` at `0x180067a4f`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800679e9`
- `ntdll!RtlGetPersistedStateLocation` at `0x180067a4f`
- `ntdll!RtlFreeHeap` at `0x180067ae6`
- `ntdll!RtlFreeHeap` at `0x180067ae6`
- `ntdll!RtlAllocateHeap` at `0x180067a0a`
- `ntdll!RtlAllocateHeap` at `0x180067a0a`

## string_xrefs

- `0x1800679bc`: `TargetNtPath`
- `0x180067a48`: `TargetNtPath`
- `0x1800679b0`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x180067a2e`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x180067a9a`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`

## pseudocode

```c
__int64 __fastcall BasepGetPersistedRegistryValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _DWORD *a7)
{
  WCHAR *Heap; // rdi
  NTSTATUS PersistedStateLocation; // eax
  ULONG Value; // ebx
  const WCHAR *v10; // rsi
  unsigned int Size; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD Size_4[3]; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v14[528]; // [rsp+50h] [rbp-B0h] BYREF

  Size = 0;
  Heap = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"FileSystem",
                             L"TargetNtPath",
                             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem",
                             0,
                             v14,
                             522,
                             &Size);
  if ( PersistedStateLocation == -2147483643 )
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
    if ( !Heap )
      return 8;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"FileSystem",
                               L"TargetNtPath",
                               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem",
                               0,
                               Heap,
                               Size,
                               &Size);
  }
  if ( PersistedStateLocation >= 0 )
  {
    v10 = (const WCHAR *)v14;
    Size_4[0] = *a7;
    if ( Heap )
      v10 = Heap;
    Value = BasepRegGetValue(v10, (__int64)Size_4);
    if ( Value - 2 <= 1 && wcscmp_0(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem", v10) )
    {
      Size_4[0] = *a7;
      Value = BasepRegGetValue(v10, (__int64)Size_4);
    }
    *a7 = Size_4[0];
  }
  else
  {
    Value = RtlNtStatusToDosError(PersistedStateLocation);
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return Value;
}

```

## disassembly

```asm
0x180067974  push    rbp
0x180067976  push    rbx
0x180067977  push    rsi
0x180067978  push    rdi
0x180067979  push    r14
0x18006797b  push    r15
0x18006797d  lea     rbp, [rsp-178h]
0x180067985  sub     rsp, 278h
0x18006798c  mov     rax, cs:__security_cookie
0x180067993  xor     rax, rsp
0x180067996  mov     [rbp+1A0h+var_40], rax
0x18006799d  mov     r15, [rbp+1A0h+arg_28]
0x1800679a4  lea     rax, [rsp+2A0h+Size]
0x1800679a9  mov     r14, [rbp+1A0h+arg_30]
0x1800679b0  lea     r8, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800679b7  mov     [rsp+2A0h+var_270], rax
0x1800679bc  lea     rdx, aTargetntpath; "TargetNtPath"
0x1800679c3  lea     rax, [rsp+2A0h+var_250]
0x1800679c8  mov     [rsp+2A0h+var_278], 20Ah
0x1800679d0  xor     r9d, r9d
0x1800679d3  mov     [rsp+2A0h+var_280], rax
0x1800679d8  lea     rcx, aFilesystem; "FileSystem"
0x1800679df  mov     dword ptr [rsp+2A0h+Size], 0
0x1800679e7  xor     edi, edi
0x1800679e9  call    cs:__imp_RtlGetPersistedStateLocation
0x1800679ef  cmp     eax, 80000005h
0x1800679f4  jnz     short loc_180067A55
0x1800679f6  mov     rcx, gs:60h
0x1800679ff  xor     edx, edx; Flags
0x180067a01  mov     r8d, dword ptr [rsp+2A0h+Size]; Size
0x180067a06  mov     rcx, [rcx+30h]; HeapHandle
0x180067a0a  call    cs:__imp_RtlAllocateHeap
0x180067a10  mov     rdi, rax
0x180067a13  test    rax, rax
0x180067a16  jnz     short loc_180067A20
0x180067a18  lea     ebx, [rax+8]
0x180067a1b  jmp     loc_180067AEC
0x180067a20  mov     eax, dword ptr [rsp+2A0h+Size]
0x180067a24  lea     rcx, [rsp+2A0h+Size]
0x180067a29  mov     [rsp+2A0h+var_270], rcx
0x180067a2e  lea     r8, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x180067a35  mov     [rsp+2A0h+var_278], eax
0x180067a39  lea     rcx, aFilesystem; "FileSystem"
0x180067a40  xor     r9d, r9d
0x180067a43  mov     [rsp+2A0h+var_280], rdi
0x180067a48  lea     rdx, aTargetntpath; "TargetNtPath"
0x180067a4f  call    cs:__imp_RtlGetPersistedStateLocation
0x180067a55  test    eax, eax
0x180067a57  jns     short loc_180067A65
0x180067a59  mov     ecx, eax; Status
0x180067a5b  call    cs:__imp_RtlNtStatusToDosError
0x180067a61  mov     ebx, eax
0x180067a63  jmp     short loc_180067ACF
0x180067a65  mov     eax, [r14]
0x180067a68  lea     rsi, [rsp+2A0h+var_250]
0x180067a6d  mov     dword ptr [rsp+2A0h+Size+4], eax
0x180067a71  test    rdi, rdi
0x180067a74  lea     rax, [rsp+2A0h+Size+4]
0x180067a79  mov     r9, r15
0x180067a7c  cmovnz  rsi, rdi
0x180067a80  mov     [rsp+2A0h+var_280], rax; __int64
0x180067a85  mov     rcx, rsi; SourceString
0x180067a88  call    BasepRegGetValue
0x180067a8d  mov     ebx, eax
0x180067a8f  add     eax, 0FFFFFFFEh
0x180067a92  cmp     eax, 1
0x180067a95  ja      short loc_180067AC8
0x180067a97  mov     rdx, rsi; String2
0x180067a9a  lea     rcx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x180067aa1  call    wcscmp_0
0x180067aa6  test    eax, eax
0x180067aa8  jz      short loc_180067AC8
0x180067aaa  mov     eax, [r14]
0x180067aad  mov     r9, r15
0x180067ab0  mov     dword ptr [rsp+2A0h+Size+4], eax
0x180067ab4  mov     rcx, rsi; SourceString
0x180067ab7  lea     rax, [rsp+2A0h+Size+4]
0x180067abc  mov     [rsp+2A0h+var_280], rax; __int64
0x180067ac1  call    BasepRegGetValue
0x180067ac6  mov     ebx, eax
0x180067ac8  mov     eax, dword ptr [rsp+2A0h+Size+4]
0x180067acc  mov     [r14], eax
0x180067acf  test    rdi, rdi
0x180067ad2  jz      short loc_180067AEC
0x180067ad4  mov     rcx, gs:60h
0x180067add  mov     r8, rdi; P
0x180067ae0  xor     edx, edx; Flags
0x180067ae2  mov     rcx, [rcx+30h]; HeapHandle
0x180067ae6  call    cs:__imp_RtlFreeHeap
0x180067aec  mov     eax, ebx
0x180067aee  mov     rcx, [rbp+1A0h+var_40]
0x180067af5  xor     rcx, rsp; StackCookie
0x180067af8  call    __security_check_cookie
0x180067afd  add     rsp, 278h
0x180067b04  pop     r15
0x180067b06  pop     r14
0x180067b08  pop     rdi
0x180067b09  pop     rsi
0x180067b0a  pop     rbx
0x180067b0b  pop     rbp
0x180067b0c  retn
```
