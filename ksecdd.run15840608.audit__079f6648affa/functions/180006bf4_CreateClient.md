# CreateClient

- ea: `0x180006bf4`
- end: `0x180006d7d`
- name: `CreateClient`
- size: `393`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a68`
- `0x18000bf50`
- `0x180026fb8`

## callees

- `0x1800011d0`
- `0x180006bf4`
- `0x180007ba8`
- `0x180007bd8`
- `0x18000c548`
- `0x180021b68`

## import_xrefs

- `ntoskrnl!PsGetProcessSecurityPort` at `0x180006c72`
- `ntoskrnl!PsGetProcessSecurityPort` at `0x180006c72`
- `ntoskrnl!PsGetCurrentProcess` at `0x180006c27`
- `ntoskrnl!PsGetCurrentProcess` at `0x180006c63`
- `ntoskrnl!PsGetCurrentProcess` at `0x180006c27`
- `ntoskrnl!PsGetCurrentProcess` at `0x180006c63`
- `ntoskrnl!PsGetThreadProcessId` at `0x180006c48`
- `ntoskrnl!PsGetThreadProcessId` at `0x180006c48`
- `ntoskrnl!PsGetProcessId` at `0x180006c36`
- `ntoskrnl!PsGetProcessId` at `0x180006c36`
- `ntoskrnl!ZwClose` at `0x180006cfb`
- `ntoskrnl!ZwClose` at `0x180006cfb`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180006ce8`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180006ce8`

## pseudocode

```c
__int64 __fastcall CreateClient(char a1, char a2)
{
  struct _KTHREAD *CurrentThread; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  HANDLE ProcessId; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  NTSTATUS v11; // ebx
  HANDLE Handle; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+18h] BYREF
  int v14; // [rsp+68h] [rbp+20h] BYREF

  Handle = 0;
  v14 = 0;
  v13 = 0;
  CurrentThread = KeGetCurrentThread();
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  ProcessId = PsGetProcessId(CurrentProcess);
  if ( ProcessId != PsGetThreadProcessId(CurrentThread) )
    return 3221225506LL;
  v8 = PsGetCurrentProcess();
  if ( PsGetProcessSecurityPort(v8) == 1 )
    return 3221225738LL;
  if ( !a2 )
  {
    v10 = OpenSyncEvent(&Handle);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          10,
          WPP_7e7d36d9cd2235de6bfe72b52195bde7_Traceguids,
          (unsigned int)v10);
      return 2148074244LL;
    }
    v11 = ZwWaitForSingleObject(Handle, 0, 0);
    ZwClose(Handle);
    if ( v11 < 0 )
      return 2148074244LL;
  }
  if ( (int)KsecCreateRpcConnection((unsigned __int64)"KSecDD" & -(__int64)(a1 != 0), v9, &v13, &v14) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, WPP_7e7d36d9cd2235de6bfe72b52195bde7_Traceguids);
    return 2148074244LL;
  }
  InitializePackages(v13);
  return 0;
}

```

## disassembly

```asm
0x180006bf4  mov     rax, rsp
0x180006bf7  mov     [rax+8], rbx
0x180006bfb  push    rbp
0x180006bfc  push    rsi
0x180006bfd  push    rdi
0x180006bfe  sub     rsp, 30h
0x180006c02  mov     qword ptr [rax-28h], 0
0x180006c0a  mov     sil, dl
0x180006c0d  mov     dword ptr [rax+20h], 0
0x180006c14  mov     bpl, cl
0x180006c17  mov     dword ptr [rax+18h], 0
0x180006c1e  mov     rdi, gs:188h
0x180006c27  call    cs:__imp_PsGetCurrentProcess
0x180006c2e  nop     dword ptr [rax+rax+00h]
0x180006c33  mov     rcx, rax; Process
0x180006c36  call    cs:__imp_PsGetProcessId
0x180006c3d  nop     dword ptr [rax+rax+00h]
0x180006c42  mov     rcx, rdi; Thread
0x180006c45  mov     rbx, rax
0x180006c48  call    cs:__imp_PsGetThreadProcessId
0x180006c4f  nop     dword ptr [rax+rax+00h]
0x180006c54  cmp     rbx, rax
0x180006c57  jz      short loc_180006C63
0x180006c59  mov     eax, 0C0000022h
0x180006c5e  jmp     loc_180006D6F
0x180006c63  call    cs:__imp_PsGetCurrentProcess
0x180006c6a  nop     dword ptr [rax+rax+00h]
0x180006c6f  mov     rcx, rax
0x180006c72  call    cs:__imp_PsGetProcessSecurityPort
0x180006c79  nop     dword ptr [rax+rax+00h]
0x180006c7e  cmp     rax, 1
0x180006c82  jnz     short loc_180006C8E
0x180006c84  mov     eax, 0C000010Ah
0x180006c89  jmp     loc_180006D6F
0x180006c8e  test    sil, sil
0x180006c91  jnz     short loc_180006D0B
0x180006c93  lea     rcx, [rsp+48h+Handle]; EventHandle
0x180006c98  call    OpenSyncEvent
0x180006c9d  test    eax, eax
0x180006c9f  jns     short loc_180006CDE
0x180006ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ca8  lea     rdx, WPP_GLOBAL_Control
0x180006caf  cmp     rcx, rdx
0x180006cb2  jz      loc_180006D5D
0x180006cb8  mov     edx, [rcx+2Ch]
0x180006cbb  test    dl, 1
0x180006cbe  jz      loc_180006D5D
0x180006cc4  mov     rcx, [rcx+18h]
0x180006cc8  lea     r8, WPP_7e7d36d9cd2235de6bfe72b52195bde7_Traceguids
0x180006ccf  mov     edx, 0Ah
0x180006cd4  mov     r9d, eax
0x180006cd7  call    WPP_SF_D
0x180006cdc  jmp     short loc_180006D5D
0x180006cde  mov     rcx, [rsp+48h+Handle]; Handle
0x180006ce3  xor     r8d, r8d; Timeout
0x180006ce6  xor     edx, edx; Alertable
0x180006ce8  call    cs:__imp_ZwWaitForSingleObject
0x180006cef  nop     dword ptr [rax+rax+00h]
0x180006cf4  mov     rcx, [rsp+48h+Handle]; Handle
0x180006cf9  mov     ebx, eax
0x180006cfb  call    cs:__imp_ZwClose
0x180006d02  nop     dword ptr [rax+rax+00h]
0x180006d07  test    ebx, ebx
0x180006d09  js      short loc_180006D5D
0x180006d0b  lea     rax, aKsecdd; "KSecDD"
0x180006d12  neg     bpl
0x180006d15  lea     r9, [rsp+48h+arg_18]
0x180006d1a  sbb     rcx, rcx
0x180006d1d  lea     r8, [rsp+48h+arg_10]
0x180006d22  and     rcx, rax
0x180006d25  call    KsecCreateRpcConnection
0x180006d2a  test    eax, eax
0x180006d2c  jns     short loc_180006D64
0x180006d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d35  lea     rdx, WPP_GLOBAL_Control
0x180006d3c  cmp     rcx, rdx
0x180006d3f  jz      short loc_180006D5D
0x180006d41  mov     eax, [rcx+2Ch]
0x180006d44  test    al, 1
0x180006d46  jz      short loc_180006D5D
0x180006d48  mov     rcx, [rcx+18h]
0x180006d4c  lea     r8, WPP_7e7d36d9cd2235de6bfe72b52195bde7_Traceguids
0x180006d53  mov     edx, 0Bh
0x180006d58  call    WPP_SF_
0x180006d5d  mov     eax, 80090304h
0x180006d62  jmp     short loc_180006D6F
0x180006d64  mov     ecx, [rsp+48h+arg_10]
0x180006d68  call    InitializePackages
0x180006d6d  xor     eax, eax
0x180006d6f  mov     rbx, [rsp+48h+arg_0]
0x180006d74  add     rsp, 30h
0x180006d78  pop     rdi
0x180006d79  pop     rsi
0x180006d7a  pop     rbp
0x180006d7b  retn
```
