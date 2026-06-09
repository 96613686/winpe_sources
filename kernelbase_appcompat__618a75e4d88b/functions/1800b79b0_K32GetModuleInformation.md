# K32GetModuleInformation

- ea: `0x1800b79b0`
- end: `0x1800b7c50`
- name: `K32GetModuleInformation`
- size: `672`
- prototype: `BOOL __stdcall(HANDLE hProcess, HMODULE hModule, LPMODULEINFO lpmodinfo, DWORD cb)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18001cd34`
- `0x18004b9d0`
- `0x1800b79b0`
- `0x1800b7c58`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b7b9c`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7c34`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7b9c`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7c34`
- `ntdll!NtQueryInformationProcess` at `0x1800b7a43`
- `ntdll!NtQueryInformationProcess` at `0x1800b7a43`
- `ntdll!NtReadVirtualMemory` at `0x1800b7a88`
- `ntdll!NtReadVirtualMemory` at `0x1800b7ace`
- `ntdll!NtReadVirtualMemory` at `0x1800b7b1d`
- `ntdll!NtReadVirtualMemory` at `0x1800b7c02`
- `ntdll!NtReadVirtualMemory` at `0x1800b7a88`
- `ntdll!NtReadVirtualMemory` at `0x1800b7ace`
- `ntdll!NtReadVirtualMemory` at `0x1800b7b1d`
- `ntdll!NtReadVirtualMemory` at `0x1800b7c02`

## pseudocode

```c
BOOL __stdcall K32GetModuleInformation(HANDLE hProcess, HMODULE hModule, LPMODULEINFO lpmodinfo, DWORD cb)
{
  int InformationProcess; // eax
  __int64 v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rax
  ULONG v14; // ecx
  ULONG_PTR NumberOfBytesRead; // [rsp+30h] [rbp-138h] BYREF
  HMODULE v17; // [rsp+38h] [rbp-130h] BYREF
  __int64 v18; // [rsp+40h] [rbp-128h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-120h] BYREF
  __int128 v20; // [rsp+50h] [rbp-118h]
  _OWORD ProcessInformation[3]; // [rsp+68h] [rbp-100h] BYREF
  _BYTE v22[16]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-B8h]
  HMODULE v24; // [rsp+D0h] [rbp-98h]
  void *v25; // [rsp+D8h] [rbp-90h]
  int v26; // [rsp+E0h] [rbp-88h]
  __int16 v27; // [rsp+10Ch] [rbp-5Ch]

  memset_0(v22, 0, 0x88u);
  v20 = 0;
  if ( cb < 0x18 )
  {
    v14 = 122;
  }
  else
  {
    v17 = hModule;
    memset(ProcessInformation, 0, 44);
    Buffer = 0;
    v18 = 0;
    InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess < 0 )
    {
      v14 = RtlNtStatusToDosError(InformationProcess);
    }
    else
    {
      v9 = *((_QWORD *)&ProcessInformation[0] + 1);
      if ( !v17 )
      {
        NumberOfBytesRead = 0;
        v10 = NtReadVirtualMemory(
                hProcess,
                (PVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 16LL),
                &v17,
                8u,
                &NumberOfBytesRead);
        if ( v10 < 0 )
          goto LABEL_16;
      }
      NumberOfBytesRead = 0;
      v10 = NtReadVirtualMemory(hProcess, (PVOID)(v9 + 24), &Buffer, 8u, &NumberOfBytesRead);
      if ( v10 < 0 )
        goto LABEL_16;
      if ( Buffer )
      {
        v11 = Buffer + 32;
        NumberOfBytesRead = 0;
        v10 = NtReadVirtualMemory(hProcess, (PVOID)(Buffer + 32), &v18, 8u, &NumberOfBytesRead);
        if ( v10 >= 0 )
        {
          v12 = 0;
          v13 = v18;
          while ( v13 != v11 )
          {
            NumberOfBytesRead = 0;
            v10 = NtReadVirtualMemory(hProcess, (PVOID)(v13 - 16), v22, 0x88u, &NumberOfBytesRead);
            if ( v10 < 0 )
              goto LABEL_16;
            if ( v24 == v17 )
            {
              if ( !v27 )
                return 0;
              goto LABEL_14;
            }
            v13 = v23;
            v18 = v23;
            if ( (unsigned int)++v12 > 0x2710 )
              goto LABEL_12;
          }
          if ( (unsigned int)Wow64FindModuleEx(hProcess) )
          {
LABEL_14:
            *(_QWORD *)&v20 = hModule;
            DWORD2(v20) = v26;
            *(_OWORD *)&lpmodinfo->lpBaseOfDll = v20;
            lpmodinfo->EntryPoint = v25;
            return 1;
          }
          return 0;
        }
LABEL_16:
        BaseSetLastNTError((unsigned int)v10);
        return 0;
      }
LABEL_12:
      v14 = 6;
    }
  }
  SetLastError_0(v14);
  return 0;
}

```

## disassembly

```asm
0x1800b79b0  mov     [rsp+arg_18], rbx; GetModuleInformation
0x1800b79b5  push    rsi
0x1800b79b6  push    rdi
0x1800b79b7  push    r12
0x1800b79b9  push    r14
0x1800b79bb  push    r15
0x1800b79bd  sub     rsp, 140h
0x1800b79c4  mov     rax, cs:__security_cookie
0x1800b79cb  xor     rax, rsp
0x1800b79ce  mov     [rsp+168h+var_38], rax
0x1800b79d6  mov     ebx, r9d
0x1800b79d9  mov     r14, r8
0x1800b79dc  mov     r15, rdx
0x1800b79df  mov     rsi, rcx
0x1800b79e2  xor     edx, edx; Val
0x1800b79e4  mov     r8d, 88h; Size
0x1800b79ea  lea     rcx, [rsp+168h+var_C8]; void *
0x1800b79f2  call    memset_0
0x1800b79f7  xorps   xmm0, xmm0
0x1800b79fa  xor     eax, eax
0x1800b79fc  movups  [rsp+168h+var_118], xmm0
0x1800b7a01  cmp     ebx, 18h
0x1800b7a04  jb      loc_1800B7C49
0x1800b7a0a  mov     [rsp+168h+var_130], r15
0x1800b7a0f  movups  [rsp+168h+ProcessInformation], xmm0
0x1800b7a14  movups  xmmword ptr [rsp+168h+var_F0], xmm0
0x1800b7a19  movups  xmmword ptr [rsp+168h+var_F0+0Ch], xmm0
0x1800b7a21  xor     r12d, r12d
0x1800b7a24  mov     [rsp+168h+Buffer], r12
0x1800b7a29  mov     [rsp+168h+var_128], r12
0x1800b7a2e  mov     [rsp+168h+ReturnLength], r12; ReturnLength
0x1800b7a33  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800b7a39  lea     r8, [rsp+168h+ProcessInformation]; ProcessInformation
0x1800b7a3e  xor     edx, edx; ProcessInformationClass
0x1800b7a40  mov     rcx, rsi; ProcessHandle
0x1800b7a43  call    cs:__imp_NtQueryInformationProcess
0x1800b7a4a  nop     dword ptr [rax+rax+00h]
0x1800b7a4f  test    eax, eax
0x1800b7a51  js      loc_1800B7C32
0x1800b7a57  mov     rbx, qword ptr [rsp+168h+ProcessInformation+8]
0x1800b7a5c  cmp     [rsp+168h+var_130], r12
0x1800b7a61  jz      loc_1800B7BE1
0x1800b7a67  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800b7a6c  lea     rdx, [rbx+18h]; BaseAddress
0x1800b7a70  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800b7a75  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800b7a7a  mov     r9d, 8; NumberOfBytesToRead
0x1800b7a80  lea     r8, [rsp+168h+Buffer]; Buffer
0x1800b7a85  mov     rcx, rsi; ProcessHandle
0x1800b7a88  call    cs:__imp_NtReadVirtualMemory
0x1800b7a8f  nop     dword ptr [rax+rax+00h]
0x1800b7a94  test    eax, eax
0x1800b7a96  js      loc_1800B7C16
0x1800b7a9c  mov     rdi, [rsp+168h+Buffer]
0x1800b7aa1  test    rdi, rdi
0x1800b7aa4  jz      loc_1800B7B57
0x1800b7aaa  add     rdi, 20h ; ' '
0x1800b7aae  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800b7ab3  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800b7ab8  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800b7abd  mov     r9d, 8; NumberOfBytesToRead
0x1800b7ac3  lea     r8, [rsp+168h+var_128]; Buffer
0x1800b7ac8  mov     rdx, rdi; BaseAddress
0x1800b7acb  mov     rcx, rsi; ProcessHandle
0x1800b7ace  call    cs:__imp_NtReadVirtualMemory
0x1800b7ad5  nop     dword ptr [rax+rax+00h]
0x1800b7ada  test    eax, eax
0x1800b7adc  js      loc_1800B7C16
0x1800b7ae2  mov     ebx, r12d
0x1800b7ae5  mov     rdx, [rsp+168h+var_130]
0x1800b7aea  mov     rax, [rsp+168h+var_128]
0x1800b7aef  nop
0x1800b7af0  lea     r8, [rsp+168h+var_C8]; Buffer
0x1800b7af8  mov     rcx, rsi; ProcessHandle
0x1800b7afb  cmp     rax, rdi
0x1800b7afe  jz      loc_1800B7C21
0x1800b7b04  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800b7b09  lea     rdx, [rax-10h]; BaseAddress
0x1800b7b0d  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800b7b12  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800b7b17  mov     r9d, 88h; NumberOfBytesToRead
0x1800b7b1d  call    cs:__imp_NtReadVirtualMemory
0x1800b7b24  nop     dword ptr [rax+rax+00h]
0x1800b7b29  test    eax, eax
0x1800b7b2b  js      loc_1800B7C16
0x1800b7b31  mov     rdx, [rsp+168h+var_130]
0x1800b7b36  cmp     [rsp+168h+var_98], rdx
0x1800b7b3e  jz      short loc_1800B7B61
0x1800b7b40  mov     rax, [rsp+168h+var_B8]
0x1800b7b48  mov     [rsp+168h+var_128], rax
0x1800b7b4d  inc     ebx
0x1800b7b4f  cmp     ebx, 2710h
0x1800b7b55  jbe     short loc_1800B7AF0
0x1800b7b57  mov     ecx, 6
0x1800b7b5c  jmp     loc_1800B7C42
0x1800b7b61  cmp     [rsp+168h+var_5C], r12w
0x1800b7b6a  jz      loc_1800B7C2E
0x1800b7b70  mov     qword ptr [rsp+168h+var_118], r15
0x1800b7b75  mov     eax, [rsp+168h+var_88]
0x1800b7b7c  mov     dword ptr [rsp+168h+var_118+8], eax
0x1800b7b80  movups  xmm0, [rsp+168h+var_118]
0x1800b7b85  movups  xmmword ptr [r14], xmm0
0x1800b7b89  movsd   xmm1, [rsp+168h+var_90]
0x1800b7b92  movsd   qword ptr [r14+10h], xmm1
0x1800b7b98  jmp     short loc_1800B7BB3
0x1800b7b9a  mov     ecx, eax; Status
0x1800b7b9c  call    cs:__imp_RtlNtStatusToDosError
0x1800b7ba3  nop     dword ptr [rax+rax+00h]
0x1800b7ba8  mov     ecx, eax; dwErrCode
0x1800b7baa  call    SetLastError_0
0x1800b7baf  xor     eax, eax
0x1800b7bb1  jmp     short loc_1800B7BB8
0x1800b7bb3  mov     eax, 1
0x1800b7bb8  mov     rcx, [rsp+168h+var_38]
0x1800b7bc0  xor     rcx, rsp; StackCookie
0x1800b7bc3  call    __security_check_cookie
0x1800b7bc8  mov     rbx, [rsp+168h+arg_18]
0x1800b7bd0  add     rsp, 140h
0x1800b7bd7  pop     r15
0x1800b7bd9  pop     r14
0x1800b7bdb  pop     r12
0x1800b7bdd  pop     rdi
0x1800b7bde  pop     rsi
0x1800b7bdf  retn
0x1800b7be1  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800b7be6  lea     rdx, [rbx+10h]; BaseAddress
0x1800b7bea  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800b7bef  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800b7bf4  mov     r9d, 8; NumberOfBytesToRead
0x1800b7bfa  lea     r8, [rsp+168h+var_130]; Buffer
0x1800b7bff  mov     rcx, rsi; ProcessHandle
0x1800b7c02  call    cs:__imp_NtReadVirtualMemory
0x1800b7c09  nop     dword ptr [rax+rax+00h]
0x1800b7c0e  test    eax, eax
0x1800b7c10  jns     loc_1800B7A67
0x1800b7c16  mov     ecx, eax
0x1800b7c18  call    BaseSetLastNTError
0x1800b7c1d  xor     eax, eax
0x1800b7c1f  jmp     short loc_1800B7BB8
0x1800b7c21  call    Wow64FindModuleEx
0x1800b7c26  test    eax, eax
0x1800b7c28  jnz     loc_1800B7B70
0x1800b7c2e  xor     eax, eax
0x1800b7c30  jmp     short loc_1800B7BB8
0x1800b7c32  mov     ecx, eax; Status
0x1800b7c34  call    cs:__imp_RtlNtStatusToDosError
0x1800b7c3b  nop     dword ptr [rax+rax+00h]
0x1800b7c40  mov     ecx, eax; dwErrCode
0x1800b7c42  call    SetLastError_0
0x1800b7c47  jmp     short loc_1800B7C2E
0x1800b7c49  mov     ecx, 7Ah ; 'z'
0x1800b7c4e  jmp     short loc_1800B7C42
```
