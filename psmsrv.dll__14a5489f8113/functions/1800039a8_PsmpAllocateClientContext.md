# PsmpAllocateClientContext

- ea: `0x1800039a8`
- end: `0x180003ae9`
- name: `PsmpAllocateClientContext`
- size: `321`
- prototype: `int __fastcall(void *, unsigned int, unsigned int *, __int64 *, void **, HANDLE *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180003970`
- `0x180019550`
- `0x180019810`
- `0x18002a5f0`

## callees

- `0x1800039a8`
- `0x180003af0`
- `0x18000436c`
- `0x18000438c`
- `0x1800043d8`
- `0x180019bfc`

## import_xrefs

- `ntdll!NtClose` at `0x180003abc`
- `ntdll!NtClose` at `0x180003abc`
- `ntdll!NtQueryInformationProcess` at `0x180003a1c`
- `ntdll!NtQueryInformationProcess` at `0x180003a1c`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800039ed`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800039ed`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800039f9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800039f9`

## pseudocode

```c
int __fastcall PsmpAllocateClientContext(
        void *a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 *a4,
        void **a5,
        HANDLE *a6)
{
  RPC_STATUS v10; // eax
  int result; // eax
  NTSTATUS InformationProcess; // edi
  __int64 Heap; // rax
  __int64 v14; // rbx
  void *ClientProcess; // [rsp+30h] [rbp-48h] BYREF
  _OWORD ProcessInformation[4]; // [rsp+38h] [rbp-40h] BYREF

  ClientProcess = 0;
  memset(ProcessInformation, 0, 44);
  v10 = I_RpcOpenClientProcess(a1, (a2 & 5) != 0 ? 1052736 : 1052672, &ClientProcess);
  if ( !v10 || (result = I_RpcMapWin32Status(v10), result >= 0) )
  {
    InformationProcess = NtQueryInformationProcess(ClientProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess >= 0 )
    {
      if ( (a2 & 2) != 0 )
        return PsmpAcquireClientAppContext(a4, a1, ProcessInformation[2], ClientProcess, a5, a6);
      Heap = PsmpAllocateHeap(120);
      v14 = Heap;
      if ( Heap )
      {
        PsmpInitializeClientContext(Heap, a2, LODWORD(ProcessInformation[2]), ClientProcess);
        ClientProcess = 0;
        if ( (a2 & 1) == 0 )
        {
          if ( (a2 & 4) != 0 )
          {
            *(_QWORD *)(v14 + 40) = v14 + 32;
            *(_QWORD *)(v14 + 32) = v14 + 32;
          }
          goto LABEL_10;
        }
        InformationProcess = PsmpAcquireManagerContext(*a3, v14);
        if ( InformationProcess >= 0 )
        {
LABEL_10:
          *a4 = v14;
          return 0;
        }
        *(_DWORD *)v14 = 0;
        PsmpDereferenceClientContext(v14);
      }
      else
      {
        InformationProcess = -1073741670;
      }
    }
    if ( ClientProcess )
      NtClose(ClientProcess);
    return InformationProcess;
  }
  return result;
}

```

## disassembly

```asm
0x1800039a8  push    rbp
0x1800039aa  push    rbx
0x1800039ab  push    rsi
0x1800039ac  push    rdi
0x1800039ad  push    r14
0x1800039af  push    r15
0x1800039b1  mov     rbp, rsp
0x1800039b4  sub     rsp, 78h
0x1800039b8  xor     eax, eax
0x1800039ba  mov     esi, edx
0x1800039bc  mov     [rbp+ClientProcess], rax
0x1800039c0  xorps   xmm0, xmm0
0x1800039c3  mov     eax, edx
0x1800039c5  mov     r15, r8
0x1800039c8  and     al, 5
0x1800039ca  lea     r8, [rbp+ClientProcess]; ClientProcess
0x1800039ce  neg     al
0x1800039d0  mov     r14, r9
0x1800039d3  movups  [rbp+var_30], xmm0
0x1800039d7  sbb     edx, edx
0x1800039d9  mov     rbx, rcx
0x1800039dc  and     edx, 40h
0x1800039df  add     edx, 101000h; DesiredAccess
0x1800039e5  movups  [rbp+ProcessInformation], xmm0
0x1800039e9  movups  [rbp+var_30+0Ch], xmm0
0x1800039ed  call    cs:__imp_I_RpcOpenClientProcess
0x1800039f3  test    eax, eax
0x1800039f5  jz      short loc_180003A03
0x1800039f7  mov     ecx, eax; Status
0x1800039f9  call    cs:__imp_I_RpcMapWin32Status
0x1800039ff  test    eax, eax
0x180003a01  js      short loc_180003A57
0x180003a03  mov     rcx, [rbp+ClientProcess]; ProcessHandle
0x180003a07  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x180003a0b  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180003a11  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x180003a1a  xor     edx, edx; ProcessInformationClass
0x180003a1c  call    cs:__imp_NtQueryInformationProcess
0x180003a22  mov     edi, eax
0x180003a24  test    eax, eax
0x180003a26  js      loc_180003AB3
0x180003a2c  test    sil, 2
0x180003a30  jz      short loc_180003A64
0x180003a32  mov     rax, [rbp+arg_28]
0x180003a36  mov     rdx, rbx
0x180003a39  mov     r9, [rbp+ClientProcess]
0x180003a3d  mov     rcx, r14
0x180003a40  mov     r8d, [rbp+var_20]
0x180003a44  mov     [rsp+78h+var_50], rax
0x180003a49  mov     rax, [rbp+arg_20]
0x180003a4d  mov     [rsp+78h+ReturnLength], rax
0x180003a52  call    PsmpAcquireClientAppContext
0x180003a57  add     rsp, 78h
0x180003a5b  pop     r15
0x180003a5d  pop     r14
0x180003a5f  pop     rdi
0x180003a60  pop     rsi
0x180003a61  pop     rbx
0x180003a62  pop     rbp
0x180003a63  retn
0x180003a64  mov     ecx, 78h ; 'x'
0x180003a69  call    PsmpAllocateHeap
0x180003a6e  mov     rbx, rax
0x180003a71  test    rax, rax
0x180003a74  jz      short loc_180003AAE
0x180003a76  mov     r9, [rbp+ClientProcess]
0x180003a7a  mov     edx, esi
0x180003a7c  mov     r8d, [rbp+var_20]
0x180003a80  mov     rcx, rax
0x180003a83  call    PsmpInitializeClientContext
0x180003a88  mov     [rbp+ClientProcess], 0
0x180003a90  test    sil, 1
0x180003a94  jz      short loc_180003AD6
0x180003a96  mov     ecx, [r15]
0x180003a99  mov     rdx, rbx
0x180003a9c  call    PsmpAcquireManagerContext
0x180003aa1  mov     edi, eax
0x180003aa3  test    eax, eax
0x180003aa5  js      short loc_180003AC6
0x180003aa7  mov     [r14], rbx
0x180003aaa  xor     eax, eax
0x180003aac  jmp     short loc_180003A57
0x180003aae  mov     edi, 0C000009Ah
0x180003ab3  mov     rcx, [rbp+ClientProcess]; Handle
0x180003ab7  test    rcx, rcx
0x180003aba  jz      short loc_180003AC2
0x180003abc  call    cs:__imp_NtClose
0x180003ac2  mov     eax, edi
0x180003ac4  jmp     short loc_180003A57
0x180003ac6  mov     rcx, rbx
0x180003ac9  mov     dword ptr [rbx], 0
0x180003acf  call    PsmpDereferenceClientContext
0x180003ad4  jmp     short loc_180003AB3
0x180003ad6  test    sil, 4
0x180003ada  jz      short loc_180003AA7
0x180003adc  lea     rax, [rbx+20h]
0x180003ae0  mov     [rax+8], rax
0x180003ae4  mov     [rax], rax
0x180003ae7  jmp     short loc_180003AA7
```
