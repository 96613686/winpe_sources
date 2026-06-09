# K32GetModuleFileNameExW

- ea: `0x1800ad7c0`
- end: `0x1800adbca`
- name: `K32GetModuleFileNameExW`
- size: `1034`
- prototype: `DWORD __stdcall(HANDLE hProcess, HMODULE hModule, LPWSTR lpFilename, DWORD nSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800ad720`

## callees

- `0x1800134a0`
- `0x180037714`
- `0x1800ad7c0`
- `0x1800ade50`
- `0x18012d119`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800adaf5`
- `ntdll!RtlNtStatusToDosError` at `0x1800adb7a`
- `ntdll!RtlNtStatusToDosError` at `0x1800adbb6`
- `ntdll!RtlNtStatusToDosError` at `0x1800adaf5`
- `ntdll!RtlNtStatusToDosError` at `0x1800adb7a`
- `ntdll!RtlNtStatusToDosError` at `0x1800adbb6`
- `ntdll!NtQueryInformationProcess` at `0x1800ad861`
- `ntdll!NtQueryInformationProcess` at `0x1800ada52`
- `ntdll!NtQueryInformationProcess` at `0x1800adba6`
- `ntdll!NtQueryInformationProcess` at `0x1800ad861`
- `ntdll!NtQueryInformationProcess` at `0x1800ada52`
- `ntdll!NtQueryInformationProcess` at `0x1800adba6`
- `ntdll!RtlFreeHeap` at `0x1800adaab`
- `ntdll!RtlFreeHeap` at `0x1800adb14`
- `ntdll!RtlFreeHeap` at `0x1800adb31`
- `ntdll!RtlFreeHeap` at `0x1800adaab`
- `ntdll!RtlFreeHeap` at `0x1800adb14`
- `ntdll!RtlFreeHeap` at `0x1800adb31`
- `ntdll!NtReadVirtualMemory` at `0x1800ad8a0`
- `ntdll!NtReadVirtualMemory` at `0x1800ad8e0`
- `ntdll!NtReadVirtualMemory` at `0x1800ad929`
- `ntdll!NtReadVirtualMemory` at `0x1800ad993`
- `ntdll!NtReadVirtualMemory` at `0x1800adad9`
- `ntdll!NtReadVirtualMemory` at `0x1800ad8a0`
- `ntdll!NtReadVirtualMemory` at `0x1800ad8e0`
- `ntdll!NtReadVirtualMemory` at `0x1800ad929`
- `ntdll!NtReadVirtualMemory` at `0x1800ad993`
- `ntdll!NtReadVirtualMemory` at `0x1800adad9`
- `ntdll!RtlAllocateHeap` at `0x1800ada22`
- `ntdll!RtlAllocateHeap` at `0x1800adb4b`
- `ntdll!RtlAllocateHeap` at `0x1800ada22`
- `ntdll!RtlAllocateHeap` at `0x1800adb4b`

## pseudocode

```c
DWORD __stdcall K32GetModuleFileNameExW(HANDLE hProcess, HMODULE hModule, LPWSTR lpFilename, DWORD nSize)
{
  DWORD v7; // r15d
  int InformationProcess; // eax
  NTSTATUS v9; // eax
  __int64 v10; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rax
  DWORD v13; // ecx
  unsigned int v14; // edi
  unsigned int v15; // ecx
  __int64 v16; // rbx
  const void **Heap; // rdi
  int v19; // eax
  DWORD v20; // ebx
  ULONG v21; // eax
  ULONG v22; // eax
  ULONG v23; // eax
  ULONG ReturnLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  ULONG_PTR NumberOfBytesRead; // [rsp+40h] [rbp-C8h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-C0h] BYREF
  __int64 ProcessInformation; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD ProcessInformation_8[6]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v29[16]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v30; // [rsp+98h] [rbp-70h]
  __int64 v31; // [rsp+B8h] [rbp-50h]
  unsigned __int16 v32; // [rsp+D0h] [rbp-38h]
  PVOID BaseAddress; // [rsp+D8h] [rbp-30h]
  __int16 v34; // [rsp+F4h] [rbp-14h]

  if ( !nSize )
  {
    v23 = RtlNtStatusToDosError(-1073741789);
    SetLastError_0(v23);
    return 0;
  }
  v7 = 0x7FFF;
  if ( nSize <= 0x7FFF )
    v7 = nSize;
  if ( hModule )
  {
    memset_0(v29, 0, 0x88u);
    *(_QWORD *)ReturnLength = hModule;
    ProcessInformation = 0;
    Buffer = 0;
    memset(ProcessInformation_8, 0, 44);
    InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation_8, 0x30u, 0);
    if ( InformationProcess < 0 )
    {
      v22 = RtlNtStatusToDosError(InformationProcess);
      SetLastError_0(v22);
      return 0;
    }
    NumberOfBytesRead = 0;
    v9 = NtReadVirtualMemory(
           hProcess,
           (PVOID)(ProcessInformation_8[1] + 24LL),
           &ProcessInformation,
           8u,
           &NumberOfBytesRead);
    if ( v9 < 0 )
      goto LABEL_34;
    if ( ProcessInformation )
    {
      NumberOfBytesRead = 0;
      v10 = ProcessInformation + 32;
      v9 = NtReadVirtualMemory(hProcess, (PVOID)(ProcessInformation + 32), &Buffer, 8u, &NumberOfBytesRead);
      if ( v9 >= 0 )
      {
        v11 = 0;
        v12 = Buffer;
        while ( v12 != v10 )
        {
          NumberOfBytesRead = 0;
          v9 = NtReadVirtualMemory(hProcess, (PVOID)(v12 - 16), v29, 0x88u, &NumberOfBytesRead);
          if ( v9 < 0 )
            goto LABEL_34;
          if ( v31 == *(_QWORD *)ReturnLength )
          {
            if ( !v34 )
              return 0;
            goto LABEL_16;
          }
          v12 = v30;
          ++v11;
          Buffer = v30;
          if ( v11 > 0x2710 )
            goto LABEL_14;
        }
        if ( !(unsigned int)Wow64FindModuleEx(hProcess) )
          return 0;
LABEL_16:
        v14 = 2 * v7;
        v15 = v32 + 2;
        NumberOfBytesRead = 0;
        v16 = 2 * v7;
        if ( 2 * v7 >= v15 )
          v16 = v15;
        v9 = NtReadVirtualMemory(hProcess, BaseAddress, lpFilename, (unsigned int)v16, &NumberOfBytesRead);
        if ( v9 >= 0 )
        {
          if ( v16 == v32 + 2LL )
            LODWORD(v16) = v16 - 2;
          if ( (unsigned int)v16 >= v14 )
            lpFilename[((unsigned __int64)v14 >> 1) - 1] = 0;
          else
            lpFilename[(unsigned __int64)(unsigned int)v16 >> 1] = 0;
          return (unsigned int)v16 >> 1;
        }
      }
LABEL_34:
      BaseSetLastNTError((unsigned int)v9);
      return 0;
    }
LABEL_14:
    v13 = 6;
LABEL_38:
    SetLastError_0(v13);
    return 0;
  }
  ReturnLength[0] = 2 * v7;
  Heap = (const void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v7 + 16LL);
  if ( !Heap )
    goto LABEL_37;
  v19 = NtQueryInformationProcess(hProcess, ProcessImageFileNameWin32, Heap, ReturnLength[0] + 16, ReturnLength);
  if ( v19 != -1073741820 )
    goto LABEL_28;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  Heap = (const void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnLength[0]);
  if ( !Heap )
  {
LABEL_37:
    v13 = 8;
    goto LABEL_38;
  }
  v19 = NtQueryInformationProcess(hProcess, ProcessImageFileNameWin32, Heap, ReturnLength[0], ReturnLength);
LABEL_28:
  if ( v19 < 0 )
  {
    v21 = RtlNtStatusToDosError(v19);
    SetLastError_0(v21);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    return 0;
  }
  v20 = *(unsigned __int16 *)Heap >> 1;
  if ( v20 >= v7 )
    v20 = v7 - 1;
  if ( v20 )
    memcpy_0(lpFilename, Heap[1], 2LL * v20);
  lpFilename[v20] = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v20;
}

```

## disassembly

```asm
0x1800ad7c0  mov     r11, rsp; GetModuleFileNameExW
0x1800ad7c3  push    rbp
0x1800ad7c4  push    rbx
0x1800ad7c5  push    r12
0x1800ad7c7  push    r14
0x1800ad7c9  lea     rbp, [r11-58h]
0x1800ad7cd  sub     rsp, 138h
0x1800ad7d4  mov     rax, cs:__security_cookie
0x1800ad7db  xor     rax, rsp
0x1800ad7de  mov     [rbp+50h+var_40], rax
0x1800ad7e2  mov     r12, r8
0x1800ad7e5  mov     rbx, rdx
0x1800ad7e8  mov     r14, rcx
0x1800ad7eb  test    r9d, r9d
0x1800ad7ee  jz      loc_1800ADBB1
0x1800ad7f4  mov     [r11-28h], rsi
0x1800ad7f8  mov     [r11-30h], rdi
0x1800ad7fc  mov     [r11-38h], r15
0x1800ad800  mov     r15d, 7FFFh
0x1800ad806  cmp     r9d, r15d
0x1800ad809  cmovbe  r15d, r9d
0x1800ad80d  xor     edx, edx; Val
0x1800ad80f  test    rbx, rbx
0x1800ad812  jz      loc_1800ADA06
0x1800ad818  mov     r8d, 88h; Size
0x1800ad81e  lea     rcx, [rbp+50h+var_D0]; void *
0x1800ad822  call    memset_0
0x1800ad827  xorps   xmm0, xmm0
0x1800ad82a  mov     qword ptr [rsp+150h+ReturnLength], rbx
0x1800ad82f  xor     esi, esi
0x1800ad831  lea     r8, [rsp+150h+ProcessInformation+8]; ProcessInformation
0x1800ad836  movups  xmmword ptr [rsp+150h+var_F8+8], xmm0
0x1800ad83b  xor     eax, eax
0x1800ad83d  mov     qword ptr [rsp+150h+ProcessInformation], rsi
0x1800ad842  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800ad848  mov     [rsp+150h+Buffer], rsi
0x1800ad84d  xor     edx, edx; ProcessInformationClass
0x1800ad84f  mov     [rsp+20h], rsi; ReturnLength
0x1800ad854  mov     rcx, r14; ProcessHandle
0x1800ad857  movups  xmmword ptr [rsp+150h+var_F8+14h], xmm0
0x1800ad85c  movups  [rsp+150h+ProcessInformation+8], xmm0
0x1800ad861  call    cs:__imp_NtQueryInformationProcess
0x1800ad867  test    eax, eax
0x1800ad869  js      loc_1800ADB78
0x1800ad86f  mov     rbx, qword ptr [rsp+150h+var_F8]
0x1800ad874  cmp     qword ptr [rsp+150h+ReturnLength], rsi
0x1800ad879  jz      loc_1800ADAB8
0x1800ad87f  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800ad884  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800ad889  lea     rdx, [rbx+18h]; BaseAddress
0x1800ad88d  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800ad892  mov     r9d, 8; NumberOfBytesToRead
0x1800ad898  lea     r8, [rsp+150h+ProcessInformation]; Buffer
0x1800ad89d  mov     rcx, r14; ProcessHandle
0x1800ad8a0  call    cs:__imp_NtReadVirtualMemory
0x1800ad8a6  test    eax, eax
0x1800ad8a8  js      loc_1800ADAE7
0x1800ad8ae  mov     rdi, qword ptr [rsp+150h+ProcessInformation]
0x1800ad8b3  test    rdi, rdi
0x1800ad8b6  jz      loc_1800AD955
0x1800ad8bc  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800ad8c1  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800ad8c6  add     rdi, 20h ; ' '
0x1800ad8ca  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800ad8cf  mov     rdx, rdi; BaseAddress
0x1800ad8d2  lea     r8, [rsp+150h+Buffer]; Buffer
0x1800ad8d7  mov     r9d, 8; NumberOfBytesToRead
0x1800ad8dd  mov     rcx, r14; ProcessHandle
0x1800ad8e0  call    cs:__imp_NtReadVirtualMemory
0x1800ad8e6  test    eax, eax
0x1800ad8e8  js      loc_1800ADAE7
0x1800ad8ee  mov     rdx, qword ptr [rsp+150h+ReturnLength]
0x1800ad8f3  mov     ebx, esi
0x1800ad8f5  mov     rax, [rsp+150h+Buffer]
0x1800ad8fa  nop     word ptr [rax+rax+00h]
0x1800ad900  lea     r8, [rbp+50h+var_D0]; Buffer
0x1800ad904  mov     rcx, r14; ProcessHandle
0x1800ad907  cmp     rax, rdi
0x1800ad90a  jz      loc_1800AD9C9
0x1800ad910  lea     rdx, [rax-10h]; BaseAddress
0x1800ad914  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800ad919  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800ad91e  mov     r9d, 88h; NumberOfBytesToRead
0x1800ad924  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800ad929  call    cs:__imp_NtReadVirtualMemory
0x1800ad92f  test    eax, eax
0x1800ad931  js      loc_1800ADAE7
0x1800ad937  mov     rdx, qword ptr [rsp+150h+ReturnLength]
0x1800ad93c  cmp     [rbp+50h+var_A0], rdx
0x1800ad940  jz      short loc_1800AD95F
0x1800ad942  mov     rax, [rbp+50h+var_C0]
0x1800ad946  inc     ebx
0x1800ad948  mov     [rsp+150h+Buffer], rax
0x1800ad94d  cmp     ebx, 2710h
0x1800ad953  jbe     short loc_1800AD900
0x1800ad955  mov     ecx, 6
0x1800ad95a  jmp     loc_1800ADB5E
0x1800ad95f  cmp     [rbp+50h+var_64], si
0x1800ad963  jz      short loc_1800AD9D2
0x1800ad965  movzx   ecx, [rbp+50h+var_88]
0x1800ad969  lea     edi, [r15+r15]
0x1800ad96d  mov     rdx, [rbp+50h+BaseAddress]; BaseAddress
0x1800ad971  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800ad976  add     ecx, 2
0x1800ad979  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800ad97e  cmp     edi, ecx
0x1800ad980  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800ad985  mov     ebx, edi
0x1800ad987  mov     r8, r12; Buffer
0x1800ad98a  cmovnb  ebx, ecx
0x1800ad98d  mov     rcx, r14; ProcessHandle
0x1800ad990  mov     r9d, ebx; NumberOfBytesToRead
0x1800ad993  call    cs:__imp_NtReadVirtualMemory
0x1800ad999  test    eax, eax
0x1800ad99b  js      loc_1800ADAE7
0x1800ad9a1  movzx   eax, [rbp+50h+var_88]
0x1800ad9a5  add     rax, 2
0x1800ad9a9  cmp     rbx, rax
0x1800ad9ac  jnz     short loc_1800AD9B1
0x1800ad9ae  add     ebx, 0FFFFFFFEh
0x1800ad9b1  cmp     ebx, edi
0x1800ad9b3  jnb     loc_1800ADB68
0x1800ad9b9  mov     eax, ebx
0x1800ad9bb  shr     rax, 1
0x1800ad9be  mov     [r12+rax*2], si
0x1800ad9c3  shr     ebx, 1
0x1800ad9c5  mov     eax, ebx
0x1800ad9c7  jmp     short loc_1800AD9D4
0x1800ad9c9  call    Wow64FindModuleEx
0x1800ad9ce  test    eax, eax
0x1800ad9d0  jnz     short loc_1800AD965
0x1800ad9d2  xor     eax, eax
0x1800ad9d4  mov     rdi, [rsp+150h+var_28]
0x1800ad9dc  mov     rsi, [rsp+130h]
0x1800ad9e4  mov     r15, [rsp+150h+var_30]
0x1800ad9ec  mov     rcx, [rbp+50h+var_40]
0x1800ad9f0  xor     rcx, rsp; StackCookie
0x1800ad9f3  call    __security_check_cookie
0x1800ad9f8  add     rsp, 138h
0x1800ad9ff  pop     r14
0x1800ada01  pop     r12
0x1800ada03  pop     rbx
0x1800ada04  pop     rbp
0x1800ada05  retn
0x1800ada06  lea     eax, [r15+r15]
0x1800ada0a  mov     [rsp+150h+ReturnLength], eax
0x1800ada0e  mov     rcx, gs:60h
0x1800ada17  mov     r8d, eax
0x1800ada1a  add     r8, 10h; Size
0x1800ada1e  mov     rcx, [rcx+30h]; HeapHandle
0x1800ada22  call    cs:__imp_RtlAllocateHeap
0x1800ada28  mov     rdi, rax
0x1800ada2b  test    rax, rax
0x1800ada2e  jz      loc_1800ADB59
0x1800ada34  mov     r9d, [rsp+150h+ReturnLength]
0x1800ada39  lea     rax, [rsp+150h+ReturnLength]
0x1800ada3e  add     r9d, 10h; ProcessInformationLength
0x1800ada42  mov     [rsp+20h], rax; ReturnLength
0x1800ada47  mov     r8, rdi; ProcessInformation
0x1800ada4a  mov     edx, 2Bh ; '+'; ProcessInformationClass
0x1800ada4f  mov     rcx, r14; ProcessHandle
0x1800ada52  call    cs:__imp_NtQueryInformationProcess
0x1800ada58  cmp     eax, 0C0000004h
0x1800ada5d  jz      loc_1800ADB1F
0x1800ada63  test    eax, eax
0x1800ada65  js      loc_1800ADAF3
0x1800ada6b  movzx   ebx, word ptr [rdi]
0x1800ada6e  shr     ebx, 1
0x1800ada70  cmp     ebx, r15d
0x1800ada73  jb      short loc_1800ADA79
0x1800ada75  lea     ebx, [r15-1]
0x1800ada79  mov     r14d, ebx
0x1800ada7c  add     r14, r14
0x1800ada7f  test    ebx, ebx
0x1800ada81  jz      short loc_1800ADA92
0x1800ada83  mov     rdx, [rdi+8]; Src
0x1800ada87  mov     r8, r14; Size
0x1800ada8a  mov     rcx, r12; void *
0x1800ada8d  call    memcpy_0
0x1800ada92  xor     esi, esi
0x1800ada94  mov     r8, rdi; P
0x1800ada97  mov     [r12+r14], si
0x1800ada9c  xor     edx, edx; Flags
0x1800ada9e  mov     rcx, gs:60h
0x1800adaa7  mov     rcx, [rcx+30h]; HeapHandle
0x1800adaab  call    cs:__imp_RtlFreeHeap
0x1800adab1  mov     eax, ebx
0x1800adab3  jmp     loc_1800AD9D4
0x1800adab8  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800adabd  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800adac2  lea     rdx, [rbx+10h]; BaseAddress
0x1800adac6  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800adacb  mov     r9d, 8; NumberOfBytesToRead
0x1800adad1  lea     r8, [rsp+150h+ReturnLength]; Buffer
0x1800adad6  mov     rcx, r14; ProcessHandle
0x1800adad9  call    cs:__imp_NtReadVirtualMemory
0x1800adadf  test    eax, eax
0x1800adae1  jns     loc_1800AD87F
0x1800adae7  mov     ecx, eax
0x1800adae9  call    BaseSetLastNTError
0x1800adaee  jmp     loc_1800AD9D2
0x1800adaf3  mov     ecx, eax; Status
0x1800adaf5  call    cs:__imp_RtlNtStatusToDosError
0x1800adafb  mov     ecx, eax; dwErrCode
0x1800adafd  call    SetLastError_0
0x1800adb02  mov     rcx, gs:60h
0x1800adb0b  mov     r8, rdi; P
0x1800adb0e  xor     edx, edx; Flags
0x1800adb10  mov     rcx, [rcx+30h]; HeapHandle
0x1800adb14  call    cs:__imp_RtlFreeHeap
0x1800adb1a  jmp     loc_1800AD9D2
0x1800adb1f  mov     rcx, gs:60h
0x1800adb28  mov     r8, rdi; P
0x1800adb2b  xor     edx, edx; Flags
0x1800adb2d  mov     rcx, [rcx+30h]; HeapHandle
0x1800adb31  call    cs:__imp_RtlFreeHeap
0x1800adb37  mov     rcx, gs:60h
0x1800adb40  xor     edx, edx; Flags
0x1800adb42  mov     r8d, [rsp+150h+ReturnLength]; Size
0x1800adb47  mov     rcx, [rcx+30h]; HeapHandle
0x1800adb4b  call    cs:__imp_RtlAllocateHeap
0x1800adb51  mov     rdi, rax
0x1800adb54  test    rax, rax
0x1800adb57  jnz     short loc_1800ADB8C
0x1800adb59  mov     ecx, 8; dwErrCode
0x1800adb5e  call    SetLastError_0
0x1800adb63  jmp     loc_1800AD9D2
0x1800adb68  mov     ecx, edi
0x1800adb6a  shr     rcx, 1
0x1800adb6d  mov     [r12+rcx*2-2], si
0x1800adb73  jmp     loc_1800AD9C3
0x1800adb78  mov     ecx, eax; Status
0x1800adb7a  call    cs:__imp_RtlNtStatusToDosError
0x1800adb80  mov     ecx, eax; dwErrCode
0x1800adb82  call    SetLastError_0
0x1800adb87  jmp     loc_1800AD9D2
0x1800adb8c  mov     r9d, [rsp+150h+ReturnLength]; ProcessInformationLength
0x1800adb91  lea     rax, [rsp+150h+ReturnLength]
0x1800adb96  mov     r8, rdi; ProcessInformation
0x1800adb99  mov     [rsp+20h], rax; ReturnLength
0x1800adb9e  mov     edx, 2Bh ; '+'; ProcessInformationClass
0x1800adba3  mov     rcx, r14; ProcessHandle
0x1800adba6  call    cs:__imp_NtQueryInformationProcess
0x1800adbac  jmp     loc_1800ADA63
0x1800adbb1  mov     ecx, 0C0000023h; Status
0x1800adbb6  call    cs:__imp_RtlNtStatusToDosError
0x1800adbbc  mov     ecx, eax; dwErrCode
0x1800adbbe  call    SetLastError_0
0x1800adbc3  xor     eax, eax
0x1800adbc5  jmp     loc_1800AD9EC
```
