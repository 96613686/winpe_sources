# CdpCreateProcess

- ea: `0x14000d6b0`
- end: `0x14000d91c`
- name: `CdpCreateProcess`
- size: `620`
- prototype: `__int64 __fastcall(PEX_RUNDOWN_REF RunRef)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ce70`

## callees

- `0x1400014d0`
- `0x140001900`
- `0x14000d6b0`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x14000d732`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000d732`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000d723`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000d723`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000d8ba`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14000d8ba`
- `ntoskrnl!ZwSetInformationProcess` at `0x14000d851`
- `ntoskrnl!ZwSetInformationProcess` at `0x14000d8f6`
- `ntoskrnl!ZwSetInformationProcess` at `0x14000d851`
- `ntoskrnl!ZwSetInformationProcess` at `0x14000d8f6`
- `ntoskrnl!ObCloseHandle` at `0x14000d86c`
- `ntoskrnl!ObCloseHandle` at `0x14000d86c`
- `ntoskrnl!__imp_ZwCreateUserProcess` at `0x14000d825`
- `ntoskrnl!__imp_ZwCreateUserProcess` at `0x14000d825`

## string_xrefs

- `0x14000d77c`: `\SystemRoot\System32\Conhost.exe`

## pseudocode

```c
NTSTATUS __fastcall CdpCreateProcess(PEX_RUNDOWN_REF RunRef, __int64 a2, __int64 a3)
{
  __int64 CurrentProcess; // rax
  int v7; // eax
  int v8; // ebx
  NTSTATUS result; // eax
  int ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h]
  __int128 v12; // [rsp+70h] [rbp-90h]
  _OWORD v13[15]; // [rsp+80h] [rbp-80h] BYREF

  memset(&v13[2], 0, 0x58u);
  memset(&v13[8], 0, 0x68u);
  memset(v13, 0, 28);
  ProcessInformation = 0;
  Handle = 0;
  v12 = 0;
  CurrentProcess = PsGetCurrentProcess();
  if ( PsGetProcessWow64Process(CurrentProcess)
    && ((result = ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDebugFlags, &ProcessInformation, 4u, 0),
         result < 0)
     || ProcessInformation == 1
     && (ProcessInformation = 0,
         result = ZwSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDebugFlags, &ProcessInformation, 4u),
         ProcessInformation = 1,
         result < 0)) )
  {
    RunRef->Count = 0;
  }
  else
  {
    memset((char *)&v13[2] + 8, 0, 0x50u);
    *(_QWORD *)&v13[2] = 88;
    *(_QWORD *)&v13[10] = 0;
    *(_QWORD *)&v13[12] = 0;
    *(_QWORD *)&v13[14] = 0;
    *(_QWORD *)&v13[8] = 104;
    *((_QWORD *)&v13[9] + 1) = L"\\SystemRoot\\System32\\Conhost.exe";
    *((_QWORD *)&v13[8] + 1) = 131077;
    *(_QWORD *)&v13[9] = 64;
    *((_QWORD *)&v13[10] + 1) = 393218;
    *((_QWORD *)&v13[11] + 1) = a2;
    *(_QWORD *)&v13[11] = 8;
    *((_QWORD *)&v13[12] + 1) = 393216;
    *((_QWORD *)&v13[13] + 1) = a3;
    *(_QWORD *)&v13[13] = 8;
    LODWORD(v12) = 48;
    *((_QWORD *)&v12 + 1) = 0;
    DWORD2(v13[0]) = 512;
    *(_QWORD *)&v13[0] = 0;
    v13[1] = 0;
    LOBYTE(v7) = ZwCreateUserProcess(RunRef);
    v8 = v7;
    if ( ProcessInformation == 1 )
      ZwSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDebugFlags, &ProcessInformation, 4u);
    if ( v8 < 0 )
      RunRef->Count = 0;
    else
      ObCloseHandle(Handle, 0);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x14000d6b0  mov     [rsp-8+arg_8], rbx
0x14000d6b5  push    rbp
0x14000d6b6  push    rsi
0x14000d6b7  push    rdi
0x14000d6b8  push    r14
0x14000d6ba  push    r15
0x14000d6bc  lea     rbp, [rsp-80h]
0x14000d6c1  sub     rsp, 180h
0x14000d6c8  mov     rax, cs:__security_cookie
0x14000d6cf  xor     rax, rsp
0x14000d6d2  mov     [rbp+0A0h+var_30], rax
0x14000d6d6  mov     rbx, r8
0x14000d6d9  mov     rsi, rdx
0x14000d6dc  mov     rdi, rcx
0x14000d6df  xor     edx, edx; Val
0x14000d6e1  mov     r8d, 58h ; 'X'; Size
0x14000d6e7  lea     rcx, [rbp+0A0h+var_100]; void *
0x14000d6eb  mov     r14, r9
0x14000d6ee  call    memset
0x14000d6f3  xor     edx, edx; Val
0x14000d6f5  lea     rcx, [rbp+0A0h+var_A0]; void *
0x14000d6f9  mov     r8d, 68h ; 'h'; Size
0x14000d6ff  call    memset
0x14000d704  xorps   xmm0, xmm0
0x14000d707  xor     r15d, r15d
0x14000d70a  movups  [rbp+0A0h+var_120], xmm0
0x14000d70e  xor     eax, eax
0x14000d710  mov     [rsp+1A0h+ProcessInformation], r15d
0x14000d715  movups  [rbp+0A0h+var_120+0Ch], xmm0
0x14000d719  mov     [rsp+1A0h+Handle], r15
0x14000d71e  movups  [rsp+1A0h+var_130], xmm0
0x14000d723  call    cs:__imp_PsGetCurrentProcess
0x14000d72a  nop     dword ptr [rax+rax+00h]
0x14000d72f  mov     rcx, rax
0x14000d732  call    cs:__imp_PsGetProcessWow64Process
0x14000d739  nop     dword ptr [rax+rax+00h]
0x14000d73e  test    rax, rax
0x14000d741  jnz     loc_14000D89E
0x14000d747  xor     edx, edx; Val
0x14000d749  lea     rcx, [rbp+0A0h+var_F8]; void *
0x14000d74d  mov     r8d, 50h ; 'P'; Size
0x14000d753  call    memset
0x14000d758  xor     eax, eax
0x14000d75a  mov     [rbp+0A0h+var_100], 58h ; 'X'
0x14000d762  mov     [rbp+0A0h+var_80], rax
0x14000d766  lea     rdx, [rsp+1A0h+Handle]
0x14000d76b  mov     [rbp+0A0h+var_60], rax
0x14000d76f  mov     r9d, 2000000h
0x14000d775  mov     [rbp+0A0h+var_40], rax
0x14000d779  xorps   xmm0, xmm0
0x14000d77c  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\Conhost.exe"
0x14000d783  mov     [rbp+0A0h+var_A0], 68h ; 'h'
0x14000d78b  mov     [rbp+0A0h+var_88], rax
0x14000d78f  mov     r8d, r9d
0x14000d792  lea     rax, [rbp+0A0h+var_A0]
0x14000d796  mov     [rbp+0A0h+var_98], 20005h
0x14000d79e  mov     [rsp+1A0h+var_150], rax
0x14000d7a3  mov     rcx, rdi; RunRef
0x14000d7a6  lea     rax, [rbp+0A0h+var_100]
0x14000d7aa  mov     [rbp+0A0h+var_90], 40h ; '@'
0x14000d7b2  mov     [rsp+1A0h+var_158], rax
0x14000d7b7  lea     rax, [rsp+1A0h+var_130]
0x14000d7bc  mov     [rsp+1A0h+var_160], r14
0x14000d7c1  mov     [rsp+1A0h+var_168], 1
0x14000d7c9  mov     [rsp+1A0h+var_170], 8000h
0x14000d7d1  mov     [rsp+1A0h+var_178], rax
0x14000d7d6  lea     rax, [rsp+1A0h+var_130]
0x14000d7db  mov     [rsp+1A0h+ReturnLength], rax
0x14000d7e0  mov     [rbp+0A0h+var_78], 60002h
0x14000d7e8  mov     [rbp+0A0h+var_68], rsi
0x14000d7ec  mov     [rbp+0A0h+var_70], 8
0x14000d7f4  mov     [rbp+0A0h+var_58], 60000h
0x14000d7fc  mov     [rbp+0A0h+var_48], rbx
0x14000d800  mov     [rbp+0A0h+var_50], 8
0x14000d808  mov     dword ptr [rsp+1A0h+var_130], 30h ; '0'
0x14000d810  mov     qword ptr [rsp+1A0h+var_130+8], r15
0x14000d815  mov     dword ptr [rbp+0A0h+var_120+8], 200h
0x14000d81c  mov     qword ptr [rbp+0A0h+var_120], r15
0x14000d820  movdqu  [rbp+0A0h+var_110], xmm0
0x14000d825  call    cs:__imp_ZwCreateUserProcess
0x14000d82c  nop     dword ptr [rax+rax+00h]
0x14000d831  cmp     [rsp+1A0h+ProcessInformation], 1
0x14000d836  mov     ebx, eax
0x14000d838  jnz     short loc_14000D85D
0x14000d83a  mov     r9d, 4; ProcessInformationLength
0x14000d840  lea     r8, [rsp+1A0h+ProcessInformation]; ProcessInformation
0x14000d845  mov     edx, 1Fh; ProcessInformationClass
0x14000d84a  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000d851  call    cs:__imp_ZwSetInformationProcess
0x14000d858  nop     dword ptr [rax+rax+00h]
0x14000d85d  test    ebx, ebx
0x14000d85f  js      loc_14000D914
0x14000d865  mov     rcx, [rsp+1A0h+Handle]; Handle
0x14000d86a  xor     edx, edx; PreviousMode
0x14000d86c  call    cs:__imp_ObCloseHandle
0x14000d873  nop     dword ptr [rax+rax+00h]
0x14000d878  mov     eax, ebx
0x14000d87a  mov     rcx, [rbp+0A0h+var_30]
0x14000d87e  xor     rcx, rsp; StackCookie
0x14000d881  call    __security_check_cookie
0x14000d886  mov     rbx, [rsp+1A0h+arg_8]
0x14000d88e  add     rsp, 180h
0x14000d895  pop     r15
0x14000d897  pop     r14
0x14000d899  pop     rdi
0x14000d89a  pop     rsi
0x14000d89b  pop     rbp
0x14000d89c  retn
0x14000d89e  mov     r9d, 4; ProcessInformationLength
0x14000d8a4  mov     [rsp+1A0h+ReturnLength], r15; ReturnLength
0x14000d8a9  lea     r8, [rsp+1A0h+ProcessInformation]; ProcessInformation
0x14000d8ae  mov     edx, 1Fh; ProcessInformationClass
0x14000d8b3  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000d8ba  call    cs:__imp_ZwQueryInformationProcess
0x14000d8c1  nop     dword ptr [rax+rax+00h]
0x14000d8c6  test    eax, eax
0x14000d8c8  jns     short loc_14000D8CF
0x14000d8ca  mov     [rdi], r15
0x14000d8cd  jmp     short loc_14000D87A
0x14000d8cf  cmp     [rsp+1A0h+ProcessInformation], 1
0x14000d8d4  jnz     loc_14000D747
0x14000d8da  mov     r9d, 4; ProcessInformationLength
0x14000d8e0  mov     [rsp+1A0h+ProcessInformation], r15d
0x14000d8e5  lea     r8, [rsp+1A0h+ProcessInformation]; ProcessInformation
0x14000d8ea  mov     edx, 1Fh; ProcessInformationClass
0x14000d8ef  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000d8f6  call    cs:__imp_ZwSetInformationProcess
0x14000d8fd  nop     dword ptr [rax+rax+00h]
0x14000d902  mov     [rsp+1A0h+ProcessInformation], 1
0x14000d90a  test    eax, eax
0x14000d90c  jns     loc_14000D747
0x14000d912  jmp     short loc_14000D8CA
0x14000d914  mov     [rdi], r15
0x14000d917  jmp     loc_14000D878
```
