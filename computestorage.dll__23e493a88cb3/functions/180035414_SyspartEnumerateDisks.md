# SyspartEnumerateDisks

- ea: `0x180035414`
- end: `0x18003567c`
- name: `SyspartEnumerateDisks`
- size: `616`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030b4c`
- `0x180034598`

## callees

- `0x1800033d4`
- `0x180035358`
- `0x180035414`
- `0x180049010`

## import_xrefs

- `ntdll!NtQueryDirectoryObject` at `0x1800354e7`
- `ntdll!NtQueryDirectoryObject` at `0x1800354e7`
- `ntdll!RtlFreeHeap` at `0x18003550e`
- `ntdll!RtlFreeHeap` at `0x180035644`
- `ntdll!RtlFreeHeap` at `0x18003566b`
- `ntdll!RtlFreeHeap` at `0x18003550e`
- `ntdll!RtlFreeHeap` at `0x180035644`
- `ntdll!RtlFreeHeap` at `0x18003566b`
- `ntdll!NtClose` at `0x180035551`
- `ntdll!NtClose` at `0x18003557f`
- `ntdll!NtClose` at `0x180035551`
- `ntdll!NtClose` at `0x18003557f`
- `ntdll!RtlInitUnicodeString` at `0x180035465`
- `ntdll!RtlInitUnicodeString` at `0x180035465`
- `ntdll!RtlAllocateHeap` at `0x18003552f`
- `ntdll!RtlAllocateHeap` at `0x1800355ba`
- `ntdll!RtlAllocateHeap` at `0x18003552f`
- `ntdll!RtlAllocateHeap` at `0x1800355ba`
- `ntdll!NtOpenDirectoryObject` at `0x18003549f`
- `ntdll!NtOpenDirectoryObject` at `0x18003549f`

## pseudocode

```c
__int64 __fastcall SyspartEnumerateDisks(unsigned __int8 (__fastcall *a1)(wchar_t *, _QWORD, __int64), __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG v5; // esi
  SIZE_T i; // r8
  _WORD *Heap; // rdi
  wchar_t *v9; // r14
  wchar_t **v10; // rsi
  void *FileHandle; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  ULONG Context; // [rsp+E8h] [rbp+7Fh] BYREF

  Context = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenDirectoryObject(&FileHandle, 1u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    v5 = 4096;
    for ( i = 4096; ; i = v5 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, i);
      if ( !Heap )
      {
        v4 = -1073741801;
        goto LABEL_7;
      }
      Context = 0;
      v4 = NtQueryDirectoryObject(FileHandle, Heap, v5, 0, 1u, &Context, 0);
      if ( v4 != 261 )
        break;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v5 += 4096;
    }
    NtClose(FileHandle);
    FileHandle = 0;
    if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147483622 )
    {
      v9 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x6Au);
      if ( v9 )
      {
        v4 = 0;
        v10 = (wchar_t **)Heap;
        if ( *Heap )
        {
          do
          {
            if ( (unsigned __int8)SiIsValidDiskDevice(v10[1], v10[3]) )
            {
              swprintf_s(v9, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", 0, 0);
              if ( a1(v9, 0, a2) )
                break;
            }
            v10 += 4;
          }
          while ( *(_WORD *)v10 );
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      }
      else
      {
        v4 = -1073741801;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
LABEL_7:
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035414  mov     [rsp-8+arg_0], rbx
0x180035419  push    rbp
0x18003541a  push    rsi
0x18003541b  push    rdi
0x18003541c  push    r12
0x18003541e  push    r13
0x180035420  push    r14
0x180035422  push    r15
0x180035424  lea     rbp, [rsp-27h]
0x180035429  sub     rsp, 90h
0x180035430  xorps   xmm0, xmm0
0x180035433  xor     r13d, r13d
0x180035436  mov     r15, rdx
0x180035439  mov     [rbp+57h+arg_18], r13d
0x18003543d  mov     r12, rcx
0x180035440  mov     [rbp+57h+arg_10], r13d
0x180035444  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180035448  xor     eax, eax
0x18003544a  mov     [rbp+57h+FileHandle], r13
0x18003544e  lea     rdx, aDevice; "\\Device"
0x180035455  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180035459  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003545d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180035461  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180035465  call    cs:__imp_RtlInitUnicodeString
0x18003546c  nop     dword ptr [rax+rax+00h]
0x180035471  lea     rax, [rbp+57h+DestinationString]
0x180035475  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003547c  xorps   xmm0, xmm0
0x18003547f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180035483  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180035487  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18003548b  lea     edx, [r13+1]; DesiredAccess
0x18003548f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180035496  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003549a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003549f  call    cs:__imp_NtOpenDirectoryObject
0x1800354a6  nop     dword ptr [rax+rax+00h]
0x1800354ab  mov     ebx, eax
0x1800354ad  test    eax, eax
0x1800354af  js      loc_180035548
0x1800354b5  mov     r14d, 1000h
0x1800354bb  mov     esi, r14d
0x1800354be  mov     r8d, r14d
0x1800354c1  jmp     short loc_180035520
0x1800354c3  mov     rcx, [rbp+57h+FileHandle]; DirectoryHandle
0x1800354c7  lea     rax, [rbp+57h+arg_18]
0x1800354cb  mov     [rsp+0C0h+ReturnLength], r13; ReturnLength
0x1800354d0  xor     r9d, r9d; ReturnSingleEntry
0x1800354d3  mov     [rsp+0C0h+Context], rax; Context
0x1800354d8  mov     r8d, esi; BufferLength
0x1800354db  mov     rdx, rdi; Buffer
0x1800354de  mov     [rsp+0C0h+RestartScan], 1; RestartScan
0x1800354e3  mov     [rbp+57h+arg_18], r13d
0x1800354e7  call    cs:__imp_NtQueryDirectoryObject
0x1800354ee  nop     dword ptr [rax+rax+00h]
0x1800354f3  mov     ebx, eax
0x1800354f5  cmp     eax, 105h
0x1800354fa  jnz     short loc_18003557B
0x1800354fc  mov     rcx, gs:60h
0x180035505  mov     r8, rdi; P
0x180035508  xor     edx, edx; Flags
0x18003550a  mov     rcx, [rcx+30h]; HeapHandle
0x18003550e  call    cs:__imp_RtlFreeHeap
0x180035515  nop     dword ptr [rax+rax+00h]
0x18003551a  add     esi, r14d
0x18003551d  mov     r8d, esi; Size
0x180035520  mov     rcx, gs:60h
0x180035529  xor     edx, edx; Flags
0x18003552b  mov     rcx, [rcx+30h]; HeapHandle
0x18003552f  call    cs:__imp_RtlAllocateHeap
0x180035536  nop     dword ptr [rax+rax+00h]
0x18003553b  mov     rdi, rax
0x18003553e  test    rax, rax
0x180035541  jnz     short loc_1800354C3
0x180035543  mov     ebx, 0C0000017h
0x180035548  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18003554c  test    rcx, rcx
0x18003554f  jz      short loc_18003555D
0x180035551  call    cs:__imp_NtClose
0x180035558  nop     dword ptr [rax+rax+00h]
0x18003555d  mov     eax, ebx
0x18003555f  mov     rbx, [rsp+0C0h+arg_0]
0x180035567  add     rsp, 90h
0x18003556e  pop     r15
0x180035570  pop     r14
0x180035572  pop     r13
0x180035574  pop     r12
0x180035576  pop     rdi
0x180035577  pop     rsi
0x180035578  pop     rbp
0x180035579  retn
0x18003557b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18003557f  call    cs:__imp_NtClose
0x180035586  nop     dword ptr [rax+rax+00h]
0x18003558b  mov     ecx, 80000000h
0x180035590  mov     [rbp+57h+FileHandle], r13
0x180035594  lea     eax, [rbx+rcx]
0x180035597  test    ecx, eax
0x180035599  jnz     short loc_1800355A7
0x18003559b  cmp     ebx, 8000001Ah
0x1800355a1  jnz     loc_180035650
0x1800355a7  mov     rcx, gs:60h
0x1800355b0  xor     edx, edx; Flags
0x1800355b2  mov     rcx, [rcx+30h]; HeapHandle
0x1800355b6  lea     r8d, [rdx+6Ah]; Size
0x1800355ba  call    cs:__imp_RtlAllocateHeap
0x1800355c1  nop     dword ptr [rax+rax+00h]
0x1800355c6  mov     r14, rax
0x1800355c9  test    rax, rax
0x1800355cc  jnz     short loc_1800355D5
0x1800355ce  mov     ebx, 0C0000017h
0x1800355d3  jmp     short loc_180035650
0x1800355d5  mov     ebx, r13d
0x1800355d8  mov     rsi, rdi
0x1800355db  cmp     [rdi], r13w
0x1800355df  jz      short loc_180035632
0x1800355e1  mov     rdx, [rsi+18h]; wchar_t *
0x1800355e5  lea     r8, [rbp+57h+arg_10]
0x1800355e9  mov     rcx, [rsi+8]; String1
0x1800355ed  call    SiIsValidDiskDevice
0x1800355f2  test    al, al
0x1800355f4  jz      short loc_180035628
0x1800355f6  mov     r9d, [rbp+57h+arg_10]
0x1800355fa  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x180035601  mov     edx, 35h ; '5'; BufferCount
0x180035606  mov     qword ptr [rsp+0C0h+RestartScan], r13
0x18003560b  mov     rcx, r14; Buffer
0x18003560e  call    swprintf_s
0x180035613  mov     edx, [rbp+57h+arg_10]
0x180035616  mov     r8, r15
0x180035619  mov     rcx, r14
0x18003561c  mov     rax, r12
0x18003561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035624  test    al, al
0x180035626  jnz     short loc_180035632
0x180035628  add     rsi, 20h ; ' '
0x18003562c  cmp     [rsi], r13w
0x180035630  jnz     short loc_1800355E1
0x180035632  mov     rcx, gs:60h
0x18003563b  mov     r8, r14; P
0x18003563e  xor     edx, edx; Flags
0x180035640  mov     rcx, [rcx+30h]; HeapHandle
0x180035644  call    cs:__imp_RtlFreeHeap
0x18003564b  nop     dword ptr [rax+rax+00h]
0x180035650  test    rdi, rdi
0x180035653  jz      loc_180035548
0x180035659  mov     rcx, gs:60h
0x180035662  mov     r8, rdi; P
0x180035665  xor     edx, edx; Flags
0x180035667  mov     rcx, [rcx+30h]; HeapHandle
0x18003566b  call    cs:__imp_RtlFreeHeap
0x180035672  nop     dword ptr [rax+rax+00h]
0x180035677  jmp     loc_180035548
```
