# CscIssueQueryInfoToRdr

- ea: `0x14001bc58`
- end: `0x14001bd40`
- name: `CscIssueQueryInfoToRdr`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bd48`

## callees

- `0x140018930`
- `0x14001bc58`
- `0x14002f0f0`

## import_xrefs

- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001bcf3`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001bcf3`
- `rdbss!RxCreateRxContext` at `0x14001bc7b`
- `rdbss!RxCreateRxContext` at `0x14001bc7b`

## pseudocode

```c
__int64 __fastcall CscIssueQueryInfoToRdr(__int64 a1, ULONG a2, RXVBO a3, int a4)
{
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v9; // rbx
  unsigned int v10; // edi
  __int64 (__fastcall *v11)(struct _RX_CONTEXT *); // rax

  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  v9 = RxContext;
  if ( RxContext )
  {
    RxContext->LowIoContext.ParamsFor.ReadWrite.ByteOffset = a3;
    *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = a4;
    RxContext->LowIoContext.ParamsFor.Locks.Flags = a2;
    LOWORD(RxContext->RealDevice) = 5;
    RxContext->pFcb = *(PMRX_FCB *)(a1 + 56);
    RxContext->pFobx = *(PMRX_FOBX *)(a1 + 64);
    RxContext->pRelevantSrvOpen = *(PMRX_SRV_OPEN *)(a1 + 72);
    v11 = *(__int64 (__fastcall **)(struct _RX_CONTEXT *))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 200LL);
    if ( v11 )
      v10 = v11(v9);
    else
      v10 = -1073741822;
    RxDereferenceAndDeleteRxContext_Real(v9);
  }
  else
  {
    v10 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x14001bc58  push    rbx
0x14001bc5a  push    rbp
0x14001bc5b  push    rsi
0x14001bc5c  push    rdi
0x14001bc5d  push    r14
0x14001bc5f  sub     rsp, 20h
0x14001bc63  mov     r14d, edx
0x14001bc66  mov     rbp, r8
0x14001bc69  mov     rdx, [rcx+50h]; RxDeviceObject
0x14001bc6d  mov     rdi, rcx
0x14001bc70  xor     ecx, ecx; Irp
0x14001bc72  mov     r8d, 2; InitialContextFlags
0x14001bc78  mov     esi, r9d
0x14001bc7b  call    cs:__imp_RxCreateRxContext
0x14001bc82  nop     dword ptr [rax+rax+00h]
0x14001bc87  mov     rbx, rax
0x14001bc8a  test    rax, rax
0x14001bc8d  jnz     short loc_14001BC96
0x14001bc8f  mov     edi, 0C000009Ah
0x14001bc94  jmp     short loc_14001BCFF
0x14001bc96  mov     [rax+1C8h], rbp
0x14001bc9d  mov     [rax+1D8h], esi
0x14001bca3  mov     [rax+1C0h], r14d
0x14001bcaa  mov     word ptr [rax+20h], 5
0x14001bcb0  mov     rax, [rdi+38h]
0x14001bcb4  mov     [rbx+38h], rax
0x14001bcb8  mov     rax, [rdi+40h]
0x14001bcbc  mov     [rbx+40h], rax
0x14001bcc0  mov     rax, [rdi+48h]
0x14001bcc4  mov     [rbx+48h], rax
0x14001bcc8  mov     rax, [rdi+50h]
0x14001bccc  mov     rcx, [rax+160h]
0x14001bcd3  mov     rax, [rcx+0C8h]
0x14001bcda  test    rax, rax
0x14001bcdd  jnz     short loc_14001BCE6
0x14001bcdf  mov     edi, 0C0000002h
0x14001bce4  jmp     short loc_14001BCF0
0x14001bce6  mov     rcx, rbx
0x14001bce9  call    _guard_dispatch_icall
0x14001bcee  mov     edi, eax
0x14001bcf0  mov     rcx, rbx; RxContext
0x14001bcf3  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14001bcfa  nop     dword ptr [rax+rax+00h]
0x14001bcff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd06  lea     rax, WPP_GLOBAL_Control
0x14001bd0d  cmp     rcx, rax
0x14001bd10  jz      short loc_14001BD32
0x14001bd12  mov     edx, [rcx+2Ch]
0x14001bd15  test    dl, 20h
0x14001bd18  jz      short loc_14001BD32
0x14001bd1a  mov     rcx, [rcx+18h]
0x14001bd1e  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14001bd25  mov     edx, 1Fh
0x14001bd2a  mov     r9d, edi
0x14001bd2d  call    WPP_SF_d
0x14001bd32  mov     eax, edi
0x14001bd34  add     rsp, 20h
0x14001bd38  pop     r14
0x14001bd3a  pop     rdi
0x14001bd3b  pop     rsi
0x14001bd3c  pop     rbp
0x14001bd3d  pop     rbx
0x14001bd3e  retn
```
