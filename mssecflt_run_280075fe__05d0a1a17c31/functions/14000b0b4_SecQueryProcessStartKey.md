# SecQueryProcessStartKey

- ea: `0x14000b0b4`
- end: `0x14000b1b6`
- name: `SecQueryProcessStartKey`
- size: `258`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b1c0`

## callees

- `0x140008880`
- `0x14000b0b4`
- `0x1400100b0`
- `0x140011650`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14000b120`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000b120`
- `ntoskrnl!ZwClose` at `0x14000b17d`
- `ntoskrnl!ZwClose` at `0x14000b17d`

## pseudocode

```c
__int64 __fastcall SecQueryProcessStartKey(PVOID Object, _QWORD *a2)
{
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  HANDLE ProcessHandle; // [rsp+40h] [rbp-88h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-80h] BYREF
  _QWORD ProcessInformation[12]; // [rsp+50h] [rbp-78h] BYREF

  ProcessHandle = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  ReturnLength = 0;
  v4 = ObOpenObjectByPointer(Object, 0x200u, 0, 0, 0, 0, &ProcessHandle);
  if ( v4 >= 0 )
  {
    v5 = ZwQueryInformationProcess_0(ProcessHandle, (PROCESSINFOCLASS)64, ProcessInformation, 0x60u, &ReturnLength);
    v4 = v5;
    if ( v5 >= 0 || v5 == -2147483643 && ReturnLength )
    {
      v4 = 0;
      *a2 = ProcessInformation[1];
    }
  }
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( v4 < 0 )
    SecIncrementGetProcessStartKeyFailureCount();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000b0b4  mov     [rsp+arg_10], rbx
0x14000b0b9  push    rdi
0x14000b0ba  sub     rsp, 0C0h
0x14000b0c1  mov     rax, cs:__security_cookie
0x14000b0c8  xor     rax, rsp
0x14000b0cb  mov     [rsp+0C8h+var_18], rax
0x14000b0d3  mov     rdi, rdx
0x14000b0d6  mov     [rsp+0C8h+ProcessHandle], 0
0x14000b0df  xor     edx, edx; Val
0x14000b0e1  mov     rbx, rcx
0x14000b0e4  lea     rcx, [rsp+0C8h+ProcessInformation]; void *
0x14000b0e9  lea     r8d, [rdx+60h]; Size
0x14000b0ed  call    memset
0x14000b0f2  lea     rax, [rsp+0C8h+ProcessHandle]
0x14000b0f7  mov     [rsp+0C8h+ReturnLength], 0
0x14000b0ff  mov     [rsp+0C8h+Handle], rax; Handle
0x14000b104  xor     r9d, r9d; DesiredAccess
0x14000b107  mov     [rsp+0C8h+AccessMode], 0; AccessMode
0x14000b10c  xor     r8d, r8d; PassedAccessState
0x14000b10f  mov     edx, 200h; HandleAttributes
0x14000b114  mov     [rsp+0C8h+ObjectType], 0; ObjectType
0x14000b11d  mov     rcx, rbx; Object
0x14000b120  call    cs:__imp_ObOpenObjectByPointer
0x14000b127  nop     dword ptr [rax+rax+00h]
0x14000b12c  mov     ebx, eax
0x14000b12e  test    eax, eax
0x14000b130  js      short loc_14000B173
0x14000b132  mov     rcx, [rsp+0C8h+ProcessHandle]; ProcessHandle
0x14000b137  lea     rax, [rsp+0C8h+ReturnLength]
0x14000b13c  mov     r9d, 60h ; '`'; ProcessInformationLength
0x14000b142  mov     [rsp+0C8h+ObjectType], rax; ReturnLength
0x14000b147  lea     r8, [rsp+0C8h+ProcessInformation]; ProcessInformation
0x14000b14c  lea     edx, [r9-20h]; ProcessInformationClass
0x14000b150  call    ZwQueryInformationProcess_0
0x14000b155  mov     ebx, eax
0x14000b157  test    eax, eax
0x14000b159  jns     short loc_14000B169
0x14000b15b  cmp     eax, 80000005h
0x14000b160  jnz     short loc_14000B173
0x14000b162  cmp     [rsp+0C8h+ReturnLength], 0
0x14000b167  jz      short loc_14000B173
0x14000b169  mov     rax, [rsp+0C8h+var_70]
0x14000b16e  xor     ebx, ebx
0x14000b170  mov     [rdi], rax
0x14000b173  mov     rcx, [rsp+0C8h+ProcessHandle]; Handle
0x14000b178  test    rcx, rcx
0x14000b17b  jz      short loc_14000B189
0x14000b17d  call    cs:__imp_ZwClose
0x14000b184  nop     dword ptr [rax+rax+00h]
0x14000b189  test    ebx, ebx
0x14000b18b  jns     short loc_14000B192
0x14000b18d  call    SecIncrementGetProcessStartKeyFailureCount
0x14000b192  mov     eax, ebx
0x14000b194  mov     rcx, [rsp+0C8h+var_18]
0x14000b19c  xor     rcx, rsp; StackCookie
0x14000b19f  call    __security_check_cookie
0x14000b1a4  mov     rbx, [rsp+0C8h+arg_10]
0x14000b1ac  add     rsp, 0C0h
0x14000b1b3  pop     rdi
0x14000b1b4  retn
```
