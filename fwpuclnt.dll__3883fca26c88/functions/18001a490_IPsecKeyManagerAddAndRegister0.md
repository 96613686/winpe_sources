# IPsecKeyManagerAddAndRegister0

- ea: `0x18001a490`
- end: `0x18001a66a`
- name: `IPsecKeyManagerAddAndRegister0`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002008`
- `0x180002a14`
- `0x180002af8`
- `0x1800034e0`
- `0x180004540`
- `0x180011500`
- `0x18001a490`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001a5ad`
- `RPCRT4!UuidCreate` at `0x18001a5ad`
- `RPCRT4!NdrClientCall3` at `0x18001a60a`
- `RPCRT4!NdrClientCall3` at `0x18001a60a`

## string_xrefs

- `0x18001a5bd`: `UuidCreate`

## pseudocode

```c
__int64 __fastcall IPsecKeyManagerAddAndRegister0(_QWORD *a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // r15
  __int64 v10; // r8
  const char *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 Dispatcher; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int Pointer; // eax
  LPCRITICAL_SECTION lpCriticalSection[11]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+8h] BYREF

  v4 = 0;
  v5 = 0;
  v20 = 0;
  lpCriticalSection[0] = 0;
  if ( !a1 || !a2 || !a4 || !*(_QWORD *)(a3 + 40) )
    goto LABEL_2;
  v12 = *(_QWORD *)(a3 + 32);
  if ( (*(_BYTE *)(a2 + 32) & 1) != 0 )
  {
    if ( !v12 || !*(_QWORD *)(a3 + 24) )
    {
LABEL_2:
      v10 = 2150760476LL;
      v11 = "IPsecKeyManagerAddAndRegister0";
LABEL_23:
      v13 = WfpReportSysErrorAsWinError(a1, v11, v10);
LABEL_24:
      Dispatcher = v13;
      if ( !v13 )
        return WfpErrorToFwpErr(Dispatcher);
      goto LABEL_25;
    }
  }
  else if ( v12 || *(_QWORD *)(a3 + 24) )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, "IPsecKeyManagerAddAndRegister0", 3221225659LL);
    goto LABEL_24;
  }
  Dispatcher = FwppSessionGetDispatcher(a1, lpCriticalSection);
  if ( Dispatcher )
    return WfpErrorToFwpErr(Dispatcher);
  v5 = lpCriticalSection[0];
  v15 = FwppDispatcherSubscribe(lpCriticalSection[0], (__int64)&v20);
  v4 = v20;
  Dispatcher = v15;
  if ( !v15 )
  {
    *(_OWORD *)(v20 + 64) = *(_OWORD *)a2;
    *(_OWORD *)(v4 + 80) = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(v4 + 96) = *(_QWORD *)(a2 + 32);
    v16 = *(_QWORD *)(v4 + 64);
    if ( !v16 )
      v16 = *(_QWORD *)(v4 + 72);
    if ( v16 || (Pointer = UuidCreate((UUID *)(v4 + 64))) == 0 )
    {
      *(_OWORD *)(v4 + 104) = *(_OWORD *)a3;
      *(_OWORD *)(v4 + 120) = *(_OWORD *)(a3 + 16);
      *(_OWORD *)(v4 + 136) = *(_OWORD *)(a3 + 32);
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0xA8u,
                                0,
                                *a1,
                                a1[1],
                                v4 + 64,
                                *(_QWORD *)(v4 + 24)).Pointer;
      if ( !Pointer )
      {
        *a4 = v4;
        return WfpErrorToFwpErr(Dispatcher);
      }
      v11 = "FwppProxyKeyManagerAdd";
    }
    else
    {
      v11 = "UuidCreate";
    }
    v10 = Pointer;
    goto LABEL_23;
  }
LABEL_25:
  if ( v4 )
    FwppDispatcherUnsubscribe(v5);
  return WfpErrorToFwpErr(Dispatcher);
}

```

## disassembly

```asm
0x18001a490  mov     rax, rsp
0x18001a493  push    rbx
0x18001a494  push    rbp
0x18001a495  push    rsi
0x18001a496  push    rdi
0x18001a497  push    r12
0x18001a499  push    r13
0x18001a49b  push    r14
0x18001a49d  push    r15
0x18001a49f  sub     rsp, 58h
0x18001a4a3  xor     edi, edi
0x18001a4a5  xor     r15d, r15d
0x18001a4a8  mov     [rax+8], rdi
0x18001a4ac  mov     r12, r9
0x18001a4af  mov     [rax-58h], r15
0x18001a4b3  mov     rsi, r8
0x18001a4b6  mov     rbp, rdx
0x18001a4b9  mov     r13, rcx
0x18001a4bc  test    rcx, rcx
0x18001a4bf  jnz     short loc_18001A4D3
0x18001a4c1  mov     r8d, 8032001Ch
0x18001a4c7  lea     rdx, aIpseckeymanage_7; "IPsecKeyManagerAddAndRegister0"
0x18001a4ce  jmp     loc_18001A624
0x18001a4d3  test    rbp, rbp
0x18001a4d6  jz      short loc_18001A4C1
0x18001a4d8  test    r12, r12
0x18001a4db  jz      short loc_18001A4C1
0x18001a4dd  cmp     [r8+28h], rdi
0x18001a4e1  jz      short loc_18001A4C1
0x18001a4e3  test    byte ptr [rdx+20h], 1
0x18001a4e7  mov     rax, [r8+20h]
0x18001a4eb  jz      short loc_18001A4FA
0x18001a4ed  test    rax, rax
0x18001a4f0  jz      short loc_18001A4C1
0x18001a4f2  cmp     [r8+18h], rdi
0x18001a4f6  jnz     short loc_18001A51C
0x18001a4f8  jmp     short loc_18001A4C1
0x18001a4fa  test    rax, rax
0x18001a4fd  jz      short loc_18001A516
0x18001a4ff  mov     r8d, 0C00000BBh
0x18001a505  lea     rdx, aIpseckeymanage_7; "IPsecKeyManagerAddAndRegister0"
0x18001a50c  call    WfpReportSysErrorAsNtStatus
0x18001a511  jmp     loc_18001A629
0x18001a516  cmp     [r8+18h], rdi
0x18001a51a  jnz     short loc_18001A4FF
0x18001a51c  lea     rdx, [rsp+98h+lpCriticalSection]
0x18001a521  call    FwppSessionGetDispatcher
0x18001a526  mov     rbx, rax
0x18001a529  test    rax, rax
0x18001a52c  jnz     loc_18001A64C
0x18001a532  mov     r15, [rsp+98h+lpCriticalSection]
0x18001a537  lea     rax, [rsp+98h+arg_0]
0x18001a53f  mov     rcx, r15; lpCriticalSection
0x18001a542  mov     [rsp+98h+var_78], rax; __int64
0x18001a547  lea     r9d, [rbx+58h]
0x18001a54b  xor     r8d, r8d
0x18001a54e  lea     rdx, FwppKeyManagerCallback
0x18001a555  call    FwppDispatcherSubscribe
0x18001a55a  mov     rdi, [rsp+98h+arg_0]
0x18001a562  mov     rbx, rax
0x18001a565  test    rax, rax
0x18001a568  jnz     loc_18001A631
0x18001a56e  movups  xmm0, xmmword ptr [rbp+0]
0x18001a572  lea     r14, [rdi+40h]
0x18001a576  movups  xmmword ptr [r14], xmm0
0x18001a57a  movups  xmm1, xmmword ptr [rbp+10h]
0x18001a57e  movups  xmmword ptr [r14+10h], xmm1
0x18001a583  movsd   xmm0, qword ptr [rbp+20h]
0x18001a588  movsd   qword ptr [r14+20h], xmm0
0x18001a58e  mov     rax, [r14]
0x18001a591  sub     rax, cs:qword_180073BC0
0x18001a598  jnz     short loc_18001A5A5
0x18001a59a  mov     rax, [r14+8]
0x18001a59e  sub     rax, cs:qword_180073BC8
0x18001a5a5  test    rax, rax
0x18001a5a8  jnz     short loc_18001A5C6
0x18001a5aa  mov     rcx, r14; Uuid
0x18001a5ad  call    cs:__imp_UuidCreate
0x18001a5b4  nop     dword ptr [rax+rax+00h]
0x18001a5b9  test    eax, eax
0x18001a5bb  jz      short loc_18001A5C6
0x18001a5bd  lea     rdx, aUuidcreate_0; "UuidCreate"
0x18001a5c4  jmp     short loc_18001A621
0x18001a5c6  movups  xmm0, xmmword ptr [rsi]
0x18001a5c9  xor     r8d, r8d; pReturnValue
0x18001a5cc  lea     rcx, pProxyInfo; pProxyInfo
0x18001a5d3  mov     edx, 0A8h; nProcNum
0x18001a5d8  movups  xmmword ptr [r14+28h], xmm0
0x18001a5dd  movups  xmm1, xmmword ptr [rsi+10h]
0x18001a5e1  movups  xmmword ptr [r14+38h], xmm1
0x18001a5e6  movups  xmm0, xmmword ptr [rsi+20h]
0x18001a5ea  movups  xmmword ptr [r14+48h], xmm0
0x18001a5ef  mov     rax, [rdi+18h]
0x18001a5f3  mov     r9, [r13+0]
0x18001a5f7  mov     [rsp+98h+var_68], rax
0x18001a5fc  mov     rax, [r13+8]
0x18001a600  mov     [rsp+98h+var_70], r14
0x18001a605  mov     [rsp+98h+var_78], rax
0x18001a60a  call    cs:__imp_NdrClientCall3
0x18001a611  nop     dword ptr [rax+rax+00h]
0x18001a616  test    eax, eax
0x18001a618  jz      short loc_18001A664
0x18001a61a  lea     rdx, aFwppproxykeyma; "FwppProxyKeyManagerAdd"
0x18001a621  mov     r8d, eax
0x18001a624  call    WfpReportSysErrorAsWinError
0x18001a629  mov     rbx, rax
0x18001a62c  test    rax, rax
0x18001a62f  jz      short loc_18001A64C
0x18001a631  test    rdi, rdi
0x18001a634  jz      short loc_18001A64C
0x18001a636  mov     r8d, 1
0x18001a63c  lea     rdx, [rsp+98h+arg_0]
0x18001a644  mov     rcx, r15; lpCriticalSection
0x18001a647  call    FwppDispatcherUnsubscribe
0x18001a64c  mov     rcx, rbx
0x18001a64f  add     rsp, 58h
0x18001a653  pop     r15
0x18001a655  pop     r14
0x18001a657  pop     r13
0x18001a659  pop     r12
0x18001a65b  pop     rdi
0x18001a65c  pop     rsi
0x18001a65d  pop     rbp
0x18001a65e  pop     rbx
0x18001a65f  jmp     WfpErrorToFwpErr
0x18001a664  mov     [r12], rdi
0x18001a668  jmp     short loc_18001A64C
```
