# EnumProcessModulesInternal

- ea: `0x1800bc190`
- end: `0x1800bc3f7`
- name: `EnumProcessModulesInternal`
- size: `615`
- prototype: `__int64 __usercall@<rax>(HANDLE ProcessHandle@<rcx>, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800bbca0`
- `0x1800bc170`

## callees

- `0x18001cd34`
- `0x18004b9d0`
- `0x1800bc190`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800bc330`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc378`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc3d2`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc3e7`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc330`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc378`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc3d2`
- `ntdll!RtlNtStatusToDosError` at `0x1800bc3e7`
- `ntdll!NtQueryInformationProcess` at `0x1800bc1ea`
- `ntdll!NtQueryInformationProcess` at `0x1800bc1ea`
- `ntdll!NtReadVirtualMemory` at `0x1800bc22d`
- `ntdll!NtReadVirtualMemory` at `0x1800bc26a`
- `ntdll!NtReadVirtualMemory` at `0x1800bc2d6`
- `ntdll!NtReadVirtualMemory` at `0x1800bc22d`
- `ntdll!NtReadVirtualMemory` at `0x1800bc26a`
- `ntdll!NtReadVirtualMemory` at `0x1800bc2d6`

## pseudocode

```c
__int64 __fastcall EnumProcessModulesInternal(HANDLE ProcessHandle, __int64 a2, unsigned int a3, _DWORD *a4, int a5)
{
  unsigned int v8; // ebx
  int InformationProcess; // eax
  NTSTATUS v10; // eax
  __int64 v11; // r15
  unsigned int v12; // r14d
  __int64 v14; // rdi
  ULONG v16; // ecx
  ULONG_PTR NumberOfBytesRead; // [rsp+30h] [rbp-1B8h] BYREF
  __int64 v18; // [rsp+38h] [rbp-1B0h] BYREF
  __int64 Buffer; // [rsp+40h] [rbp-1A8h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+48h] [rbp-1A0h] BYREF
  _BYTE v21[16]; // [rsp+80h] [rbp-168h] BYREF
  __int64 v22; // [rsp+90h] [rbp-158h]
  __int64 v23; // [rsp+B0h] [rbp-138h]
  __int16 v24; // [rsp+ECh] [rbp-FCh]
  int v25; // [rsp+18Ch] [rbp-5Ch]

  memset(ProcessInformation, 0, 44);
  v8 = 0;
  Buffer = 0;
  v18 = 0;
  InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
  {
    v16 = RtlNtStatusToDosError(InformationProcess);
LABEL_21:
    SetLastError_0(v16);
    return 0;
  }
  if ( !*((_QWORD *)&ProcessInformation[0] + 1) )
  {
    v16 = RtlNtStatusToDosError(-2147483635);
    goto LABEL_21;
  }
  NumberOfBytesRead = 0;
  v10 = NtReadVirtualMemory(
          ProcessHandle,
          (PVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 24LL),
          &Buffer,
          8u,
          &NumberOfBytesRead);
  if ( v10 >= 0 )
  {
    v11 = Buffer + 32;
    NumberOfBytesRead = 0;
    v10 = NtReadVirtualMemory(ProcessHandle, (PVOID)(Buffer + 32), &v18, 8u, &NumberOfBytesRead);
    if ( v10 >= 0 )
    {
      v12 = a3 >> 3;
      v14 = v18;
      while ( 1 )
      {
        if ( v14 == v11 )
        {
          *a4 = 8 * v8;
          return 1;
        }
        memset_0(v21, 0, 0x138u);
        NumberOfBytesRead = 0;
        v10 = NtReadVirtualMemory(ProcessHandle, (PVOID)(v14 - 16), v21, 0x138u, &NumberOfBytesRead);
        if ( v10 < 0 )
          break;
        if ( a5 && v23 && v24 && v25 != 9 )
        {
          if ( v8 < v12 )
            *(_QWORD *)(a2 + 8LL * v8) = v23;
          if ( ++v8 > 0x2710 )
          {
            v16 = 6;
            goto LABEL_21;
          }
        }
        else
        {
          a5 = 1;
        }
        v14 = v22;
        v18 = v22;
      }
    }
  }
  BaseSetLastNTError((unsigned int)v10);
  return 0;
}

```

## disassembly

```asm
0x1800bc190  mov     [rsp+arg_0], rbx
0x1800bc195  mov     [rsp+arg_8], rsi
0x1800bc19a  mov     [rsp+arg_18], r9
0x1800bc19f  push    rdi
0x1800bc1a0  push    r12
0x1800bc1a2  push    r13
0x1800bc1a4  push    r14
0x1800bc1a6  push    r15
0x1800bc1a8  sub     rsp, 1C0h
0x1800bc1af  mov     r14d, r8d
0x1800bc1b2  mov     r13, rdx
0x1800bc1b5  mov     r12, rcx
0x1800bc1b8  xor     eax, eax
0x1800bc1ba  xorps   xmm0, xmm0
0x1800bc1bd  movups  [rsp+1E8h+ProcessInformation], xmm0
0x1800bc1c2  movups  xmmword ptr [rsp+1E8h+var_190], xmm0
0x1800bc1c7  movups  xmmword ptr [rsp+1E8h+var_190+0Ch], xmm0
0x1800bc1cc  xor     ebx, ebx
0x1800bc1ce  mov     [rsp+1E8h+Buffer], rbx
0x1800bc1d3  mov     [rsp+1E8h+var_1B0], rbx
0x1800bc1d8  mov     [rsp+1E8h+ReturnLength], rbx; ReturnLength
0x1800bc1dd  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800bc1e3  lea     r8, [rsp+1E8h+ProcessInformation]; ProcessInformation
0x1800bc1e8  xor     edx, edx; ProcessInformationClass
0x1800bc1ea  call    cs:__imp_NtQueryInformationProcess
0x1800bc1f1  nop     dword ptr [rax+rax+00h]
0x1800bc1f6  test    eax, eax
0x1800bc1f8  js      loc_1800BC3D0
0x1800bc1fe  mov     rdx, qword ptr [rsp+1E8h+ProcessInformation+8]
0x1800bc203  test    rdx, rdx
0x1800bc206  jz      loc_1800BC3E2
0x1800bc20c  mov     [rsp+1E8h+NumberOfBytesRead], rbx
0x1800bc211  add     rdx, 18h; BaseAddress
0x1800bc215  lea     rax, [rsp+1E8h+NumberOfBytesRead]
0x1800bc21a  mov     [rsp+1E8h+ReturnLength], rax; NumberOfBytesRead
0x1800bc21f  mov     r9d, 8; NumberOfBytesToRead
0x1800bc225  lea     r8, [rsp+1E8h+Buffer]; Buffer
0x1800bc22a  mov     rcx, r12; ProcessHandle
0x1800bc22d  call    cs:__imp_NtReadVirtualMemory
0x1800bc234  nop     dword ptr [rax+rax+00h]
0x1800bc239  test    eax, eax
0x1800bc23b  js      loc_1800BC3B9
0x1800bc241  mov     r15, [rsp+1E8h+Buffer]
0x1800bc246  add     r15, 20h ; ' '
0x1800bc24a  mov     [rsp+1E8h+NumberOfBytesRead], rbx
0x1800bc24f  lea     rax, [rsp+1E8h+NumberOfBytesRead]
0x1800bc254  mov     [rsp+1E8h+ReturnLength], rax; NumberOfBytesRead
0x1800bc259  mov     r9d, 8; NumberOfBytesToRead
0x1800bc25f  lea     r8, [rsp+1E8h+var_1B0]; Buffer
0x1800bc264  mov     rdx, r15; BaseAddress
0x1800bc267  mov     rcx, r12; ProcessHandle
0x1800bc26a  call    cs:__imp_NtReadVirtualMemory
0x1800bc271  nop     dword ptr [rax+rax+00h]
0x1800bc276  test    eax, eax
0x1800bc278  js      loc_1800BC3B9
0x1800bc27e  shr     r14d, 3
0x1800bc282  mov     esi, [rsp+1E8h+arg_20]
0x1800bc289  mov     rdi, [rsp+1E8h+var_1B0]
0x1800bc28e  xchg    ax, ax
0x1800bc290  cmp     rdi, r15
0x1800bc293  jz      loc_1800BC363
0x1800bc299  xor     edx, edx; Val
0x1800bc29b  mov     r8d, 138h; Size
0x1800bc2a1  lea     rcx, [rsp+1E8h+var_168]; void *
0x1800bc2a9  call    memset_0
0x1800bc2ae  mov     [rsp+1E8h+NumberOfBytesRead], 0
0x1800bc2b7  lea     rdx, [rdi-10h]; BaseAddress
0x1800bc2bb  lea     rax, [rsp+1E8h+NumberOfBytesRead]
0x1800bc2c0  mov     [rsp+1E8h+ReturnLength], rax; NumberOfBytesRead
0x1800bc2c5  mov     r9d, 138h; NumberOfBytesToRead
0x1800bc2cb  lea     r8, [rsp+1E8h+var_168]; Buffer
0x1800bc2d3  mov     rcx, r12; ProcessHandle
0x1800bc2d6  call    cs:__imp_NtReadVirtualMemory
0x1800bc2dd  nop     dword ptr [rax+rax+00h]
0x1800bc2e2  test    eax, eax
0x1800bc2e4  js      loc_1800BC3B9
0x1800bc2ea  test    esi, esi
0x1800bc2ec  jz      loc_1800BC3B2
0x1800bc2f2  mov     rcx, [rsp+1E8h+var_138]
0x1800bc2fa  test    rcx, rcx
0x1800bc2fd  jz      loc_1800BC3B2
0x1800bc303  cmp     [rsp+1E8h+var_FC], 0
0x1800bc30c  jz      loc_1800BC3B2
0x1800bc312  cmp     [rsp+1E8h+var_5C], 9
0x1800bc31a  jz      loc_1800BC3B2
0x1800bc320  cmp     ebx, r14d
0x1800bc323  jnb     short loc_1800BC347
0x1800bc325  mov     eax, ebx
0x1800bc327  mov     [r13+rax*8+0], rcx
0x1800bc32c  jmp     short loc_1800BC347
0x1800bc32e  mov     ecx, eax; Status
0x1800bc330  call    cs:__imp_RtlNtStatusToDosError
0x1800bc337  nop     dword ptr [rax+rax+00h]
0x1800bc33c  mov     ecx, eax; dwErrCode
0x1800bc33e  call    SetLastError_0
0x1800bc343  xor     eax, eax
0x1800bc345  jmp     short loc_1800BC394
0x1800bc347  inc     ebx
0x1800bc349  cmp     ebx, 2710h
0x1800bc34f  ja      short loc_1800BC3C4
0x1800bc351  mov     rdi, [rsp+1E8h+var_158]
0x1800bc359  mov     [rsp+1E8h+var_1B0], rdi
0x1800bc35e  jmp     loc_1800BC290
0x1800bc363  lea     ebx, ds:0[rbx*8]
0x1800bc36a  mov     rcx, [rsp+1E8h+arg_18]
0x1800bc372  mov     [rcx], ebx
0x1800bc374  jmp     short loc_1800BC38F
0x1800bc376  mov     ecx, eax; Status
0x1800bc378  call    cs:__imp_RtlNtStatusToDosError
0x1800bc37f  nop     dword ptr [rax+rax+00h]
0x1800bc384  mov     ecx, eax; dwErrCode
0x1800bc386  call    SetLastError_0
0x1800bc38b  xor     eax, eax
0x1800bc38d  jmp     short loc_1800BC394
0x1800bc38f  mov     eax, 1
0x1800bc394  lea     r11, [rsp+1E8h+var_28]
0x1800bc39c  mov     rbx, [r11+30h]
0x1800bc3a0  mov     rsi, [r11+38h]
0x1800bc3a4  mov     rsp, r11
0x1800bc3a7  pop     r15
0x1800bc3a9  pop     r14
0x1800bc3ab  pop     r13
0x1800bc3ad  pop     r12
0x1800bc3af  pop     rdi
0x1800bc3b0  retn
0x1800bc3b2  mov     esi, 1
0x1800bc3b7  jmp     short loc_1800BC351
0x1800bc3b9  mov     ecx, eax
0x1800bc3bb  call    BaseSetLastNTError
0x1800bc3c0  xor     eax, eax
0x1800bc3c2  jmp     short loc_1800BC394
0x1800bc3c4  mov     ecx, 6; dwErrCode
0x1800bc3c9  call    SetLastError_0
0x1800bc3ce  jmp     short loc_1800BC3C0
0x1800bc3d0  mov     ecx, eax; Status
0x1800bc3d2  call    cs:__imp_RtlNtStatusToDosError
0x1800bc3d9  nop     dword ptr [rax+rax+00h]
0x1800bc3de  mov     ecx, eax
0x1800bc3e0  jmp     short loc_1800BC3C9
0x1800bc3e2  mov     ecx, 8000000Dh; Status
0x1800bc3e7  call    cs:__imp_RtlNtStatusToDosError
0x1800bc3ee  nop     dword ptr [rax+rax+00h]
0x1800bc3f3  mov     ecx, eax
0x1800bc3f5  jmp     short loc_1800BC3C9
```
