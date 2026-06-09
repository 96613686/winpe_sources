# K32GetModuleFileNameExW

- ea: `0x1800b7540`
- end: `0x1800b79a9`
- name: `K32GetModuleFileNameExW`
- size: `1129`
- prototype: `DWORD __stdcall(HANDLE hProcess, HMODULE hModule, LPWSTR lpFilename, DWORD nSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800b74a0`

## callees

- `0x18001cd34`
- `0x18004b9d0`
- `0x1800b7540`
- `0x1800b7c58`
- `0x1801369c9`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b78aa`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7947`
- `ntdll!RtlNtStatusToDosError` at `0x1800b798f`
- `ntdll!RtlNtStatusToDosError` at `0x1800b78aa`
- `ntdll!RtlNtStatusToDosError` at `0x1800b7947`
- `ntdll!RtlNtStatusToDosError` at `0x1800b798f`
- `ntdll!NtQueryInformationProcess` at `0x1800b75e1`
- `ntdll!NtQueryInformationProcess` at `0x1800b77f5`
- `ntdll!NtQueryInformationProcess` at `0x1800b7979`
- `ntdll!NtQueryInformationProcess` at `0x1800b75e1`
- `ntdll!NtQueryInformationProcess` at `0x1800b77f5`
- `ntdll!NtQueryInformationProcess` at `0x1800b7979`
- `ntdll!RtlFreeHeap` at `0x1800b7854`
- `ntdll!RtlFreeHeap` at `0x1800b78cf`
- `ntdll!RtlFreeHeap` at `0x1800b78f2`
- `ntdll!RtlFreeHeap` at `0x1800b7854`
- `ntdll!RtlFreeHeap` at `0x1800b78cf`
- `ntdll!RtlFreeHeap` at `0x1800b78f2`
- `ntdll!NtReadVirtualMemory` at `0x1800b7626`
- `ntdll!NtReadVirtualMemory` at `0x1800b766c`
- `ntdll!NtReadVirtualMemory` at `0x1800b76b9`
- `ntdll!NtReadVirtualMemory` at `0x1800b7729`
- `ntdll!NtReadVirtualMemory` at `0x1800b7888`
- `ntdll!NtReadVirtualMemory` at `0x1800b7626`
- `ntdll!NtReadVirtualMemory` at `0x1800b766c`
- `ntdll!NtReadVirtualMemory` at `0x1800b76b9`
- `ntdll!NtReadVirtualMemory` at `0x1800b7729`
- `ntdll!NtReadVirtualMemory` at `0x1800b7888`
- `ntdll!RtlAllocateHeap` at `0x1800b77bf`
- `ntdll!RtlAllocateHeap` at `0x1800b7912`
- `ntdll!RtlAllocateHeap` at `0x1800b77bf`
- `ntdll!RtlAllocateHeap` at `0x1800b7912`

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
0x1800b7540  mov     r11, rsp; GetModuleFileNameExW
0x1800b7543  push    rbp
0x1800b7544  push    rbx
0x1800b7545  push    r12
0x1800b7547  push    r14
0x1800b7549  lea     rbp, [r11-58h]
0x1800b754d  sub     rsp, 138h
0x1800b7554  mov     rax, cs:__security_cookie
0x1800b755b  xor     rax, rsp
0x1800b755e  mov     [rbp+50h+var_40], rax
0x1800b7562  mov     r12, r8
0x1800b7565  mov     rbx, rdx
0x1800b7568  mov     r14, rcx
0x1800b756b  test    r9d, r9d
0x1800b756e  jz      loc_1800B798A
0x1800b7574  mov     [r11-28h], rsi
0x1800b7578  mov     [r11-30h], rdi
0x1800b757c  mov     [r11-38h], r15
0x1800b7580  mov     r15d, 7FFFh
0x1800b7586  cmp     r9d, r15d
0x1800b7589  cmovbe  r15d, r9d
0x1800b758d  xor     edx, edx; Val
0x1800b758f  test    rbx, rbx
0x1800b7592  jz      loc_1800B77A3
0x1800b7598  mov     r8d, 88h; Size
0x1800b759e  lea     rcx, [rbp+50h+var_D0]; void *
0x1800b75a2  call    memset_0
0x1800b75a7  xorps   xmm0, xmm0
0x1800b75aa  mov     qword ptr [rsp+150h+ReturnLength], rbx
0x1800b75af  xor     esi, esi
0x1800b75b1  lea     r8, [rsp+150h+ProcessInformation+8]; ProcessInformation
0x1800b75b6  movups  xmmword ptr [rsp+150h+var_F8+8], xmm0
0x1800b75bb  xor     eax, eax
0x1800b75bd  mov     qword ptr [rsp+150h+ProcessInformation], rsi
0x1800b75c2  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800b75c8  mov     [rsp+150h+Buffer], rsi
0x1800b75cd  xor     edx, edx; ProcessInformationClass
0x1800b75cf  mov     [rsp+20h], rsi; ReturnLength
0x1800b75d4  mov     rcx, r14; ProcessHandle
0x1800b75d7  movups  xmmword ptr [rsp+150h+var_F8+14h], xmm0
0x1800b75dc  movups  [rsp+150h+ProcessInformation+8], xmm0
0x1800b75e1  call    cs:__imp_NtQueryInformationProcess
0x1800b75e8  nop     dword ptr [rax+rax+00h]
0x1800b75ed  test    eax, eax
0x1800b75ef  js      loc_1800B7945
0x1800b75f5  mov     rbx, qword ptr [rsp+150h+var_F8]
0x1800b75fa  cmp     qword ptr [rsp+150h+ReturnLength], rsi
0x1800b75ff  jz      loc_1800B7867
0x1800b7605  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800b760a  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800b760f  lea     rdx, [rbx+18h]; BaseAddress
0x1800b7613  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800b7618  mov     r9d, 8; NumberOfBytesToRead
0x1800b761e  lea     r8, [rsp+150h+ProcessInformation]; Buffer
0x1800b7623  mov     rcx, r14; ProcessHandle
0x1800b7626  call    cs:__imp_NtReadVirtualMemory
0x1800b762d  nop     dword ptr [rax+rax+00h]
0x1800b7632  test    eax, eax
0x1800b7634  js      loc_1800B789C
0x1800b763a  mov     rdi, qword ptr [rsp+150h+ProcessInformation]
0x1800b763f  test    rdi, rdi
0x1800b7642  jz      loc_1800B76EB
0x1800b7648  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800b764d  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800b7652  add     rdi, 20h ; ' '
0x1800b7656  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800b765b  mov     rdx, rdi; BaseAddress
0x1800b765e  lea     r8, [rsp+150h+Buffer]; Buffer
0x1800b7663  mov     r9d, 8; NumberOfBytesToRead
0x1800b7669  mov     rcx, r14; ProcessHandle
0x1800b766c  call    cs:__imp_NtReadVirtualMemory
0x1800b7673  nop     dword ptr [rax+rax+00h]
0x1800b7678  test    eax, eax
0x1800b767a  js      loc_1800B789C
0x1800b7680  mov     rdx, qword ptr [rsp+150h+ReturnLength]
0x1800b7685  mov     ebx, esi
0x1800b7687  mov     rax, [rsp+150h+Buffer]
0x1800b768c  nop     dword ptr [rax+00h]
0x1800b7690  lea     r8, [rbp+50h+var_D0]; Buffer
0x1800b7694  mov     rcx, r14; ProcessHandle
0x1800b7697  cmp     rax, rdi
0x1800b769a  jz      loc_1800B7765
0x1800b76a0  lea     rdx, [rax-10h]; BaseAddress
0x1800b76a4  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800b76a9  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800b76ae  mov     r9d, 88h; NumberOfBytesToRead
0x1800b76b4  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800b76b9  call    cs:__imp_NtReadVirtualMemory
0x1800b76c0  nop     dword ptr [rax+rax+00h]
0x1800b76c5  test    eax, eax
0x1800b76c7  js      loc_1800B789C
0x1800b76cd  mov     rdx, qword ptr [rsp+150h+ReturnLength]
0x1800b76d2  cmp     [rbp+50h+var_A0], rdx
0x1800b76d6  jz      short loc_1800B76F5
0x1800b76d8  mov     rax, [rbp+50h+var_C0]
0x1800b76dc  inc     ebx
0x1800b76de  mov     [rsp+150h+Buffer], rax
0x1800b76e3  cmp     ebx, 2710h
0x1800b76e9  jbe     short loc_1800B7690
0x1800b76eb  mov     ecx, 6
0x1800b76f0  jmp     loc_1800B792B
0x1800b76f5  cmp     [rbp+50h+var_64], si
0x1800b76f9  jz      short loc_1800B776E
0x1800b76fb  movzx   ecx, [rbp+50h+var_88]
0x1800b76ff  lea     edi, [r15+r15]
0x1800b7703  mov     rdx, [rbp+50h+BaseAddress]; BaseAddress
0x1800b7707  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800b770c  add     ecx, 2
0x1800b770f  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800b7714  cmp     edi, ecx
0x1800b7716  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800b771b  mov     ebx, edi
0x1800b771d  mov     r8, r12; Buffer
0x1800b7720  cmovnb  ebx, ecx
0x1800b7723  mov     rcx, r14; ProcessHandle
0x1800b7726  mov     r9d, ebx; NumberOfBytesToRead
0x1800b7729  call    cs:__imp_NtReadVirtualMemory
0x1800b7730  nop     dword ptr [rax+rax+00h]
0x1800b7735  test    eax, eax
0x1800b7737  js      loc_1800B789C
0x1800b773d  movzx   eax, [rbp+50h+var_88]
0x1800b7741  add     rax, 2
0x1800b7745  cmp     rbx, rax
0x1800b7748  jnz     short loc_1800B774D
0x1800b774a  add     ebx, 0FFFFFFFEh
0x1800b774d  cmp     ebx, edi
0x1800b774f  jnb     loc_1800B7935
0x1800b7755  mov     eax, ebx
0x1800b7757  shr     rax, 1
0x1800b775a  mov     [r12+rax*2], si
0x1800b775f  shr     ebx, 1
0x1800b7761  mov     eax, ebx
0x1800b7763  jmp     short loc_1800B7770
0x1800b7765  call    Wow64FindModuleEx
0x1800b776a  test    eax, eax
0x1800b776c  jnz     short loc_1800B76FB
0x1800b776e  xor     eax, eax
0x1800b7770  mov     rdi, [rsp+150h+var_28]
0x1800b7778  mov     rsi, [rsp+130h]
0x1800b7780  mov     r15, [rsp+150h+var_30]
0x1800b7788  mov     rcx, [rbp+50h+var_40]
0x1800b778c  xor     rcx, rsp; StackCookie
0x1800b778f  call    __security_check_cookie
0x1800b7794  add     rsp, 138h
0x1800b779b  pop     r14
0x1800b779d  pop     r12
0x1800b779f  pop     rbx
0x1800b77a0  pop     rbp
0x1800b77a1  retn
0x1800b77a3  lea     eax, [r15+r15]
0x1800b77a7  mov     [rsp+150h+ReturnLength], eax
0x1800b77ab  mov     rcx, gs:60h
0x1800b77b4  mov     r8d, eax
0x1800b77b7  add     r8, 10h; Size
0x1800b77bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800b77bf  call    cs:__imp_RtlAllocateHeap
0x1800b77c6  nop     dword ptr [rax+rax+00h]
0x1800b77cb  mov     rdi, rax
0x1800b77ce  test    rax, rax
0x1800b77d1  jz      loc_1800B7926
0x1800b77d7  mov     r9d, [rsp+150h+ReturnLength]
0x1800b77dc  lea     rax, [rsp+150h+ReturnLength]
0x1800b77e1  add     r9d, 10h; ProcessInformationLength
0x1800b77e5  mov     [rsp+20h], rax; ReturnLength
0x1800b77ea  mov     r8, rdi; ProcessInformation
0x1800b77ed  mov     edx, 2Bh ; '+'; ProcessInformationClass
0x1800b77f2  mov     rcx, r14; ProcessHandle
0x1800b77f5  call    cs:__imp_NtQueryInformationProcess
0x1800b77fc  nop     dword ptr [rax+rax+00h]
0x1800b7801  cmp     eax, 0C0000004h
0x1800b7806  jz      loc_1800B78E0
0x1800b780c  test    eax, eax
0x1800b780e  js      loc_1800B78A8
0x1800b7814  movzx   ebx, word ptr [rdi]
0x1800b7817  shr     ebx, 1
0x1800b7819  cmp     ebx, r15d
0x1800b781c  jb      short loc_1800B7822
0x1800b781e  lea     ebx, [r15-1]
0x1800b7822  mov     r14d, ebx
0x1800b7825  add     r14, r14
0x1800b7828  test    ebx, ebx
0x1800b782a  jz      short loc_1800B783B
0x1800b782c  mov     rdx, [rdi+8]; Src
0x1800b7830  mov     r8, r14; Size
0x1800b7833  mov     rcx, r12; void *
0x1800b7836  call    memcpy_0
0x1800b783b  xor     esi, esi
0x1800b783d  mov     r8, rdi; P
0x1800b7840  mov     [r12+r14], si
0x1800b7845  xor     edx, edx; Flags
0x1800b7847  mov     rcx, gs:60h
0x1800b7850  mov     rcx, [rcx+30h]; HeapHandle
0x1800b7854  call    cs:__imp_RtlFreeHeap
0x1800b785b  nop     dword ptr [rax+rax+00h]
0x1800b7860  mov     eax, ebx
0x1800b7862  jmp     loc_1800B7770
0x1800b7867  lea     rax, [rsp+150h+NumberOfBytesRead]
0x1800b786c  mov     [rsp+150h+NumberOfBytesRead], rsi
0x1800b7871  lea     rdx, [rbx+10h]; BaseAddress
0x1800b7875  mov     [rsp+20h], rax; NumberOfBytesRead
0x1800b787a  mov     r9d, 8; NumberOfBytesToRead
0x1800b7880  lea     r8, [rsp+150h+ReturnLength]; Buffer
0x1800b7885  mov     rcx, r14; ProcessHandle
0x1800b7888  call    cs:__imp_NtReadVirtualMemory
0x1800b788f  nop     dword ptr [rax+rax+00h]
0x1800b7894  test    eax, eax
0x1800b7896  jns     loc_1800B7605
0x1800b789c  mov     ecx, eax
0x1800b789e  call    BaseSetLastNTError
0x1800b78a3  jmp     loc_1800B776E
0x1800b78a8  mov     ecx, eax; Status
0x1800b78aa  call    cs:__imp_RtlNtStatusToDosError
0x1800b78b1  nop     dword ptr [rax+rax+00h]
0x1800b78b6  mov     ecx, eax; dwErrCode
0x1800b78b8  call    SetLastError_0
0x1800b78bd  mov     rcx, gs:60h
0x1800b78c6  mov     r8, rdi; P
0x1800b78c9  xor     edx, edx; Flags
0x1800b78cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800b78cf  call    cs:__imp_RtlFreeHeap
0x1800b78d6  nop     dword ptr [rax+rax+00h]
0x1800b78db  jmp     loc_1800B776E
0x1800b78e0  mov     rcx, gs:60h
0x1800b78e9  mov     r8, rdi; P
0x1800b78ec  xor     edx, edx; Flags
0x1800b78ee  mov     rcx, [rcx+30h]; HeapHandle
0x1800b78f2  call    cs:__imp_RtlFreeHeap
0x1800b78f9  nop     dword ptr [rax+rax+00h]
0x1800b78fe  mov     rcx, gs:60h
0x1800b7907  xor     edx, edx; Flags
0x1800b7909  mov     r8d, [rsp+150h+ReturnLength]; Size
0x1800b790e  mov     rcx, [rcx+30h]; HeapHandle
0x1800b7912  call    cs:__imp_RtlAllocateHeap
0x1800b7919  nop     dword ptr [rax+rax+00h]
0x1800b791e  mov     rdi, rax
0x1800b7921  test    rax, rax
0x1800b7924  jnz     short loc_1800B795F
0x1800b7926  mov     ecx, 8; dwErrCode
0x1800b792b  call    SetLastError_0
0x1800b7930  jmp     loc_1800B776E
0x1800b7935  mov     ecx, edi
0x1800b7937  shr     rcx, 1
0x1800b793a  mov     [r12+rcx*2-2], si
0x1800b7940  jmp     loc_1800B775F
0x1800b7945  mov     ecx, eax; Status
0x1800b7947  call    cs:__imp_RtlNtStatusToDosError
0x1800b794e  nop     dword ptr [rax+rax+00h]
0x1800b7953  mov     ecx, eax; dwErrCode
0x1800b7955  call    SetLastError_0
0x1800b795a  jmp     loc_1800B776E
0x1800b795f  mov     r9d, [rsp+150h+ReturnLength]; ProcessInformationLength
0x1800b7964  lea     rax, [rsp+150h+ReturnLength]
0x1800b7969  mov     r8, rdi; ProcessInformation
0x1800b796c  mov     [rsp+20h], rax; ReturnLength
0x1800b7971  mov     edx, 2Bh ; '+'; ProcessInformationClass
0x1800b7976  mov     rcx, r14; ProcessHandle
0x1800b7979  call    cs:__imp_NtQueryInformationProcess
0x1800b7980  nop     dword ptr [rax+rax+00h]
0x1800b7985  jmp     loc_1800B780C
0x1800b798a  mov     ecx, 0C0000023h; Status
0x1800b798f  call    cs:__imp_RtlNtStatusToDosError
0x1800b7996  nop     dword ptr [rax+rax+00h]
0x1800b799b  mov     ecx, eax; dwErrCode
0x1800b799d  call    SetLastError_0
0x1800b79a2  xor     eax, eax
0x1800b79a4  jmp     loc_1800B7788
```
