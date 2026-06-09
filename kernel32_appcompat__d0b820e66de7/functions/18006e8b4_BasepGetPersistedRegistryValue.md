# BasepGetPersistedRegistryValue

- ea: `0x18006e8b4`
- end: `0x18006ea6c`
- name: `BasepGetPersistedRegistryValue`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x18005e990`

## callees

- `0x180035a3c`
- `0x18006e8b4`
- `0x18008278d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006e9ad`
- `ntdll!RtlNtStatusToDosError` at `0x18006e9ad`
- `ntdll!RtlGetPersistedStateLocation` at `0x18006e929`
- `ntdll!RtlGetPersistedStateLocation` at `0x18006e99b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18006e929`
- `ntdll!RtlGetPersistedStateLocation` at `0x18006e99b`
- `ntdll!RtlFreeHeap` at `0x18006ea3e`
- `ntdll!RtlFreeHeap` at `0x18006ea3e`
- `ntdll!RtlAllocateHeap` at `0x18006e950`
- `ntdll!RtlAllocateHeap` at `0x18006e950`

## string_xrefs

- `0x18006e8fc`: `TargetNtPath`
- `0x18006e994`: `TargetNtPath`
- `0x18006e8f0`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x18006e97a`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x18006e9f2`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`

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
0x18006e8b4  push    rbp
0x18006e8b6  push    rbx
0x18006e8b7  push    rsi
0x18006e8b8  push    rdi
0x18006e8b9  push    r14
0x18006e8bb  push    r15
0x18006e8bd  lea     rbp, [rsp-178h]
0x18006e8c5  sub     rsp, 278h
0x18006e8cc  mov     rax, cs:__security_cookie
0x18006e8d3  xor     rax, rsp
0x18006e8d6  mov     [rbp+1A0h+var_40], rax
0x18006e8dd  mov     r15, [rbp+1A0h+arg_28]
0x18006e8e4  lea     rax, [rsp+2A0h+Size]
0x18006e8e9  mov     r14, [rbp+1A0h+arg_30]
0x18006e8f0  lea     r8, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006e8f7  mov     [rsp+2A0h+var_270], rax
0x18006e8fc  lea     rdx, aTargetntpath; "TargetNtPath"
0x18006e903  lea     rax, [rsp+2A0h+var_250]
0x18006e908  mov     [rsp+2A0h+var_278], 20Ah
0x18006e910  xor     r9d, r9d
0x18006e913  mov     [rsp+2A0h+var_280], rax
0x18006e918  lea     rcx, aFilesystem; "FileSystem"
0x18006e91f  mov     dword ptr [rsp+2A0h+Size], 0
0x18006e927  xor     edi, edi
0x18006e929  call    cs:__imp_RtlGetPersistedStateLocation
0x18006e930  nop     dword ptr [rax+rax+00h]
0x18006e935  cmp     eax, 80000005h
0x18006e93a  jnz     short loc_18006E9A7
0x18006e93c  mov     rcx, gs:60h
0x18006e945  xor     edx, edx; Flags
0x18006e947  mov     r8d, dword ptr [rsp+2A0h+Size]; Size
0x18006e94c  mov     rcx, [rcx+30h]; HeapHandle
0x18006e950  call    cs:__imp_RtlAllocateHeap
0x18006e957  nop     dword ptr [rax+rax+00h]
0x18006e95c  mov     rdi, rax
0x18006e95f  test    rax, rax
0x18006e962  jnz     short loc_18006E96C
0x18006e964  lea     ebx, [rax+8]
0x18006e967  jmp     loc_18006EA4A
0x18006e96c  mov     eax, dword ptr [rsp+2A0h+Size]
0x18006e970  lea     rcx, [rsp+2A0h+Size]
0x18006e975  mov     [rsp+2A0h+var_270], rcx
0x18006e97a  lea     r8, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006e981  mov     [rsp+2A0h+var_278], eax
0x18006e985  lea     rcx, aFilesystem; "FileSystem"
0x18006e98c  xor     r9d, r9d
0x18006e98f  mov     [rsp+2A0h+var_280], rdi
0x18006e994  lea     rdx, aTargetntpath; "TargetNtPath"
0x18006e99b  call    cs:__imp_RtlGetPersistedStateLocation
0x18006e9a2  nop     dword ptr [rax+rax+00h]
0x18006e9a7  test    eax, eax
0x18006e9a9  jns     short loc_18006E9BD
0x18006e9ab  mov     ecx, eax; Status
0x18006e9ad  call    cs:__imp_RtlNtStatusToDosError
0x18006e9b4  nop     dword ptr [rax+rax+00h]
0x18006e9b9  mov     ebx, eax
0x18006e9bb  jmp     short loc_18006EA27
0x18006e9bd  mov     eax, [r14]
0x18006e9c0  lea     rsi, [rsp+2A0h+var_250]
0x18006e9c5  mov     dword ptr [rsp+2A0h+Size+4], eax
0x18006e9c9  test    rdi, rdi
0x18006e9cc  lea     rax, [rsp+2A0h+Size+4]
0x18006e9d1  mov     r9, r15
0x18006e9d4  cmovnz  rsi, rdi
0x18006e9d8  mov     [rsp+2A0h+var_280], rax; __int64
0x18006e9dd  mov     rcx, rsi; SourceString
0x18006e9e0  call    BasepRegGetValue
0x18006e9e5  mov     ebx, eax
0x18006e9e7  add     eax, 0FFFFFFFEh
0x18006e9ea  cmp     eax, 1
0x18006e9ed  ja      short loc_18006EA20
0x18006e9ef  mov     rdx, rsi; String2
0x18006e9f2  lea     rcx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006e9f9  call    wcscmp_0
0x18006e9fe  test    eax, eax
0x18006ea00  jz      short loc_18006EA20
0x18006ea02  mov     eax, [r14]
0x18006ea05  mov     r9, r15
0x18006ea08  mov     dword ptr [rsp+2A0h+Size+4], eax
0x18006ea0c  mov     rcx, rsi; SourceString
0x18006ea0f  lea     rax, [rsp+2A0h+Size+4]
0x18006ea14  mov     [rsp+2A0h+var_280], rax; __int64
0x18006ea19  call    BasepRegGetValue
0x18006ea1e  mov     ebx, eax
0x18006ea20  mov     eax, dword ptr [rsp+2A0h+Size+4]
0x18006ea24  mov     [r14], eax
0x18006ea27  test    rdi, rdi
0x18006ea2a  jz      short loc_18006EA4A
0x18006ea2c  mov     rcx, gs:60h
0x18006ea35  mov     r8, rdi; P
0x18006ea38  xor     edx, edx; Flags
0x18006ea3a  mov     rcx, [rcx+30h]; HeapHandle
0x18006ea3e  call    cs:__imp_RtlFreeHeap
0x18006ea45  nop     dword ptr [rax+rax+00h]
0x18006ea4a  mov     eax, ebx
0x18006ea4c  mov     rcx, [rbp+1A0h+var_40]
0x18006ea53  xor     rcx, rsp; StackCookie
0x18006ea56  call    __security_check_cookie
0x18006ea5b  add     rsp, 278h
0x18006ea62  pop     r15
0x18006ea64  pop     r14
0x18006ea66  pop     rdi
0x18006ea67  pop     rsi
0x18006ea68  pop     rbx
0x18006ea69  pop     rbp
0x18006ea6a  retn
```
