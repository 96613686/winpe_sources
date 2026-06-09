# EnumProcessModulesInternal

- ea: `0x1800b0dc0`
- end: `0x1800b0ff8`
- name: `EnumProcessModulesInternal`
- size: `568`
- prototype: `__int64 __usercall@<rax>(HANDLE ProcessHandle@<rcx>, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800b0900`
- `0x1800b0da0`

## callees

- `0x1800134a0`
- `0x180037714`
- `0x1800b0dc0`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b0f4a`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0f8c`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0fdf`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0fee`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0f4a`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0f8c`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0fdf`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0fee`
- `ntdll!NtQueryInformationProcess` at `0x1800b0e1a`
- `ntdll!NtQueryInformationProcess` at `0x1800b0e1a`
- `ntdll!NtReadVirtualMemory` at `0x1800b0e57`
- `ntdll!NtReadVirtualMemory` at `0x1800b0e8e`
- `ntdll!NtReadVirtualMemory` at `0x1800b0ef6`
- `ntdll!NtReadVirtualMemory` at `0x1800b0e57`
- `ntdll!NtReadVirtualMemory` at `0x1800b0e8e`
- `ntdll!NtReadVirtualMemory` at `0x1800b0ef6`

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
0x1800b0dc0  mov     [rsp+arg_0], rbx
0x1800b0dc5  mov     [rsp+arg_8], rsi
0x1800b0dca  mov     [rsp+arg_18], r9
0x1800b0dcf  push    rdi
0x1800b0dd0  push    r12
0x1800b0dd2  push    r13
0x1800b0dd4  push    r14
0x1800b0dd6  push    r15
0x1800b0dd8  sub     rsp, 1C0h
0x1800b0ddf  mov     r14d, r8d
0x1800b0de2  mov     r13, rdx
0x1800b0de5  mov     r12, rcx
0x1800b0de8  xor     eax, eax
0x1800b0dea  xorps   xmm0, xmm0
0x1800b0ded  movups  [rsp+1E8h+ProcessInformation], xmm0
0x1800b0df2  movups  xmmword ptr [rsp+1E8h+var_190], xmm0
0x1800b0df7  movups  xmmword ptr [rsp+1E8h+var_190+0Ch], xmm0
0x1800b0dfc  xor     ebx, ebx
0x1800b0dfe  mov     [rsp+1E8h+Buffer], rbx
0x1800b0e03  mov     [rsp+1E8h+var_1B0], rbx
0x1800b0e08  mov     [rsp+1E8h+ReturnLength], rbx; ReturnLength
0x1800b0e0d  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800b0e13  lea     r8, [rsp+1E8h+ProcessInformation]; ProcessInformation
0x1800b0e18  xor     edx, edx; ProcessInformationClass
0x1800b0e1a  call    cs:__imp_NtQueryInformationProcess
0x1800b0e20  test    eax, eax
0x1800b0e22  js      loc_1800B0FDD
0x1800b0e28  mov     rdx, qword ptr [rsp+1E8h+ProcessInformation+8]
0x1800b0e2d  test    rdx, rdx
0x1800b0e30  jz      loc_1800B0FE9
0x1800b0e36  mov     [rsp+1E8h+NumberOfBytesRead], rbx
0x1800b0e3b  add     rdx, 18h; BaseAddress
0x1800b0e3f  lea     rax, [rsp+1E8h+NumberOfBytesRead]
0x1800b0e44  mov     [rsp+1E8h+ReturnLength], rax; NumberOfBytesRead
0x1800b0e49  mov     r9d, 8; NumberOfBytesToRead
0x1800b0e4f  lea     r8, [rsp+1E8h+Buffer]; Buffer
0x1800b0e54  mov     rcx, r12; ProcessHandle
0x1800b0e57  call    cs:__imp_NtReadVirtualMemory
0x1800b0e5d  test    eax, eax
0x1800b0e5f  js      loc_1800B0FC6
0x1800b0e65  mov     r15, [rsp+1E8h+Buffer]
0x1800b0e6a  add     r15, 20h ; ' '
0x1800b0e6e  mov     [rsp+1E8h+NumberOfBytesRead], rbx
0x1800b0e73  lea     rax, [rsp+1E8h+NumberOfBytesRead]
0x1800b0e78  mov     [rsp+1E8h+ReturnLength], rax; NumberOfBytesRead
0x1800b0e7d  mov     r9d, 8; NumberOfBytesToRead
0x1800b0e83  lea     r8, [rsp+1E8h+var_1B0]; Buffer
0x1800b0e88  mov     rdx, r15; BaseAddress
0x1800b0e8b  mov     rcx, r12; ProcessHandle
0x1800b0e8e  call    cs:__imp_NtReadVirtualMemory
0x1800b0e94  test    eax, eax
0x1800b0e96  js      loc_1800B0FC6
0x1800b0e9c  shr     r14d, 3
0x1800b0ea0  mov     esi, [rsp+1E8h+arg_20]
0x1800b0ea7  mov     rdi, [rsp+1E8h+var_1B0]
0x1800b0eac  nop     dword ptr [rax+00h]
0x1800b0eb0  cmp     rdi, r15
0x1800b0eb3  jz      loc_1800B0F77
0x1800b0eb9  xor     edx, edx; Val
0x1800b0ebb  mov     r8d, 138h; Size
0x1800b0ec1  lea     rcx, [rsp+1E8h+var_168]; void *
0x1800b0ec9  call    memset_0
0x1800b0ece  mov     [rsp+1E8h+NumberOfBytesRead], 0
0x1800b0ed7  lea     rdx, [rdi-10h]; BaseAddress
0x1800b0edb  lea     rax, [rsp+1E8h+NumberOfBytesRead]
0x1800b0ee0  mov     [rsp+1E8h+ReturnLength], rax; NumberOfBytesRead
0x1800b0ee5  mov     r9d, 138h; NumberOfBytesToRead
0x1800b0eeb  lea     r8, [rsp+1E8h+var_168]; Buffer
0x1800b0ef3  mov     rcx, r12; ProcessHandle
0x1800b0ef6  call    cs:__imp_NtReadVirtualMemory
0x1800b0efc  test    eax, eax
0x1800b0efe  js      loc_1800B0FC6
0x1800b0f04  test    esi, esi
0x1800b0f06  jz      loc_1800B0FBF
0x1800b0f0c  mov     rcx, [rsp+1E8h+var_138]
0x1800b0f14  test    rcx, rcx
0x1800b0f17  jz      loc_1800B0FBF
0x1800b0f1d  cmp     [rsp+1E8h+var_FC], 0
0x1800b0f26  jz      loc_1800B0FBF
0x1800b0f2c  cmp     [rsp+1E8h+var_5C], 9
0x1800b0f34  jz      loc_1800B0FBF
0x1800b0f3a  cmp     ebx, r14d
0x1800b0f3d  jnb     short loc_1800B0F5B
0x1800b0f3f  mov     eax, ebx
0x1800b0f41  mov     [r13+rax*8+0], rcx
0x1800b0f46  jmp     short loc_1800B0F5B
0x1800b0f48  mov     ecx, eax; Status
0x1800b0f4a  call    cs:__imp_RtlNtStatusToDosError
0x1800b0f50  mov     ecx, eax; dwErrCode
0x1800b0f52  call    SetLastError_0
0x1800b0f57  xor     eax, eax
0x1800b0f59  jmp     short loc_1800B0FA2
0x1800b0f5b  inc     ebx
0x1800b0f5d  cmp     ebx, 2710h
0x1800b0f63  ja      short loc_1800B0FD1
0x1800b0f65  mov     rdi, [rsp+1E8h+var_158]
0x1800b0f6d  mov     [rsp+1E8h+var_1B0], rdi
0x1800b0f72  jmp     loc_1800B0EB0
0x1800b0f77  lea     ebx, ds:0[rbx*8]
0x1800b0f7e  mov     rcx, [rsp+1E8h+arg_18]
0x1800b0f86  mov     [rcx], ebx
0x1800b0f88  jmp     short loc_1800B0F9D
0x1800b0f8a  mov     ecx, eax; Status
0x1800b0f8c  call    cs:__imp_RtlNtStatusToDosError
0x1800b0f92  mov     ecx, eax; dwErrCode
0x1800b0f94  call    SetLastError_0
0x1800b0f99  xor     eax, eax
0x1800b0f9b  jmp     short loc_1800B0FA2
0x1800b0f9d  mov     eax, 1
0x1800b0fa2  lea     r11, [rsp+1E8h+var_28]
0x1800b0faa  mov     rbx, [r11+30h]
0x1800b0fae  mov     rsi, [r11+38h]
0x1800b0fb2  mov     rsp, r11
0x1800b0fb5  pop     r15
0x1800b0fb7  pop     r14
0x1800b0fb9  pop     r13
0x1800b0fbb  pop     r12
0x1800b0fbd  pop     rdi
0x1800b0fbe  retn
0x1800b0fbf  mov     esi, 1
0x1800b0fc4  jmp     short loc_1800B0F65
0x1800b0fc6  mov     ecx, eax
0x1800b0fc8  call    BaseSetLastNTError
0x1800b0fcd  xor     eax, eax
0x1800b0fcf  jmp     short loc_1800B0FA2
0x1800b0fd1  mov     ecx, 6; dwErrCode
0x1800b0fd6  call    SetLastError_0
0x1800b0fdb  jmp     short loc_1800B0FCD
0x1800b0fdd  mov     ecx, eax; Status
0x1800b0fdf  call    cs:__imp_RtlNtStatusToDosError
0x1800b0fe5  mov     ecx, eax
0x1800b0fe7  jmp     short loc_1800B0FD6
0x1800b0fe9  mov     ecx, 8000000Dh; Status
0x1800b0fee  call    cs:__imp_RtlNtStatusToDosError
0x1800b0ff4  mov     ecx, eax
0x1800b0ff6  jmp     short loc_1800B0FD6
```
