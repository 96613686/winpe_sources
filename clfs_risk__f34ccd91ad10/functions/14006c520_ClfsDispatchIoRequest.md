# ClfsDispatchIoRequest

- ea: `0x14006c520`
- end: `0x14006c73f`
- name: `ClfsDispatchIoRequest`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400726d0`

## callees

- `0x14000ed64`
- `0x140017f20`
- `0x14006c520`
- `0x14006c748`
- `0x14006c874`
- `0x14006cf88`
- `0x14006ddb0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c562`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c562`
- `ntoskrnl!IofCompleteRequest` at `0x14006c642`
- `ntoskrnl!IofCompleteRequest` at `0x14006c642`

## pseudocode

```c
__int64 __fastcall ClfsDispatchIoRequest(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  CClfsRequest *v4; // rdi
  UCHAR MajorFunction; // dl
  CClfsRequest *v6; // rax
  int v7; // ebx

  v4 = 0;
  MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
  if ( MajorFunction == 18 )
  {
    v7 = CClfsRequest::Cleanup(Irp);
    if ( v7 < 0
      && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        30,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDispatchIoRequest",
        60,
        v7);
    }
  }
  else if ( MajorFunction == 2 )
  {
    v7 = CClfsRequest::Close(Irp);
    if ( v7 < 0
      && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        31,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDispatchIoRequest",
        71,
        v7);
    }
  }
  else
  {
    v6 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
    if ( v6 )
      v4 = CClfsRequest::CClfsRequest(v6);
    else
      v4 = 0;
    if ( v4 )
    {
      (**(void (__fastcall ***)(CClfsRequest *))v4)(v4);
      v7 = CClfsRequest::Dispatch(v4, Irp, a1);
      if ( v7 < 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          33,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsDispatchIoRequest",
          121,
          v7);
      }
    }
    else
    {
      v7 = -1073741670;
      Irp->IoStatus.Status = -1073741670;
      Irp->IoStatus.Information = 0;
      IofCompleteRequest(Irp, 0);
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          32,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsDispatchIoRequest",
          95,
          154);
      }
    }
  }
  if ( v4 )
    (*(void (__fastcall **)(CClfsRequest *))(*(_QWORD *)v4 + 8LL))(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14006c520  mov     rax, rsp
0x14006c523  mov     [rax+8], rbx
0x14006c527  mov     [rax+18h], rsi
0x14006c52b  mov     [rax+10h], rdx
0x14006c52f  push    rdi
0x14006c530  sub     rsp, 40h
0x14006c534  mov     rsi, rdx
0x14006c537  mov     rbx, rcx
0x14006c53a  xor     edi, edi
0x14006c53c  mov     [rax-10h], rdi
0x14006c540  mov     rax, [rdx+0B8h]
0x14006c547  mov     dl, [rax]
0x14006c549  cmp     dl, 12h
0x14006c54c  jz      loc_14006C6D4
0x14006c552  cmp     dl, 2
0x14006c555  jz      loc_14006C690
0x14006c55b  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14006c562  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006c569  nop     dword ptr [rax+rax+00h]
0x14006c56e  test    rax, rax
0x14006c571  jz      loc_14006C689
0x14006c577  mov     rcx, rax; this
0x14006c57a  call    ??0CClfsRequest@@QEAA@XZ; CClfsRequest::CClfsRequest(void)
0x14006c57f  mov     rdi, rax
0x14006c582  mov     [rsp+48h+var_10], rdi
0x14006c587  test    rdi, rdi
0x14006c58a  jz      loc_14006C629
0x14006c590  mov     rax, [rdi]
0x14006c593  mov     rax, [rax]
0x14006c596  mov     rcx, rdi
0x14006c599  call    _guard_dispatch_icall
0x14006c59e  nop
0x14006c59f  mov     r8, rbx; struct _DEVICE_OBJECT *
0x14006c5a2  mov     rdx, rsi; Irp
0x14006c5a5  mov     rcx, rdi; this
0x14006c5a8  call    ?Dispatch@CClfsRequest@@QEAAJPEAU_IRP@@PEAU_DEVICE_OBJECT@@@Z; CClfsRequest::Dispatch(_IRP *,_DEVICE_OBJECT *)
0x14006c5ad  mov     ebx, eax
0x14006c5af  mov     [rsp+48h+var_18], eax
0x14006c5b3  jmp     short loc_14006C5D0
0x14006c5b5  mov     ebx, eax
0x14006c5b7  mov     [rsp+48h+var_18], eax
0x14006c5bb  mov     rax, [rsp+48h+arg_8]
0x14006c5c0  mov     qword ptr [rax+38h], 0
0x14006c5c8  mov     [rax+30h], ebx
0x14006c5cb  mov     rdi, [rsp+48h+var_10]
0x14006c5d0  test    ebx, ebx
0x14006c5d2  jns     loc_14006C718
0x14006c5d8  lea     rax, WPP_GLOBAL_Control
0x14006c5df  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c5e6  cmp     rcx, rax
0x14006c5e9  jz      loc_14006C718
0x14006c5ef  mov     eax, [rcx+2Ch]
0x14006c5f2  bt      eax, 1Ah
0x14006c5f6  jnb     loc_14006C718
0x14006c5fc  mov     edx, 21h ; '!'
0x14006c601  mov     [rsp+48h+var_20], ebx
0x14006c605  mov     [rsp+48h+var_28], 279h
0x14006c60d  lea     r9, aClfsdispatchio; "ClfsDispatchIoRequest"
0x14006c614  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006c61b  mov     rcx, [rcx+18h]
0x14006c61f  call    WPP_SF_slD
0x14006c624  jmp     loc_14006C718
0x14006c629  mov     ebx, 0C000009Ah
0x14006c62e  mov     [rsp+48h+var_18], ebx
0x14006c632  mov     [rsi+30h], ebx
0x14006c635  mov     qword ptr [rsi+38h], 0
0x14006c63d  xor     edx, edx; PriorityBoost
0x14006c63f  mov     rcx, rsi; Irp
0x14006c642  call    cs:__imp_IofCompleteRequest
0x14006c649  nop     dword ptr [rax+rax+00h]
0x14006c64e  lea     rax, WPP_GLOBAL_Control
0x14006c655  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c65c  cmp     rcx, rax
0x14006c65f  jz      loc_14006C718
0x14006c665  mov     eax, [rcx+2Ch]
0x14006c668  bt      eax, 1Ah
0x14006c66c  jnb     loc_14006C718
0x14006c672  mov     edx, 20h ; ' '
0x14006c677  mov     [rsp+48h+var_20], 0C000009Ah
0x14006c67f  mov     [rsp+48h+var_28], 25Fh
0x14006c687  jmp     short loc_14006C60D
0x14006c689  xor     edi, edi
0x14006c68b  jmp     loc_14006C582
0x14006c690  mov     rcx, rsi; Irp
0x14006c693  call    ?Close@CClfsRequest@@SAJPEAU_IRP@@@Z; CClfsRequest::Close(_IRP *)
0x14006c698  mov     ebx, eax
0x14006c69a  mov     [rsp+48h+var_18], eax
0x14006c69e  test    eax, eax
0x14006c6a0  jns     short loc_14006C718
0x14006c6a2  lea     rax, WPP_GLOBAL_Control
0x14006c6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c6b0  cmp     rcx, rax
0x14006c6b3  jz      short loc_14006C718
0x14006c6b5  mov     eax, [rcx+2Ch]
0x14006c6b8  bt      eax, 1Ah
0x14006c6bc  jnb     short loc_14006C718
0x14006c6be  mov     edx, 1Fh
0x14006c6c3  mov     [rsp+48h+var_20], ebx
0x14006c6c7  mov     [rsp+48h+var_28], 247h
0x14006c6cf  jmp     loc_14006C60D
0x14006c6d4  mov     rcx, rsi; Irp
0x14006c6d7  call    ?Cleanup@CClfsRequest@@SAJPEAU_IRP@@@Z; CClfsRequest::Cleanup(_IRP *)
0x14006c6dc  mov     ebx, eax
0x14006c6de  mov     [rsp+48h+var_18], eax
0x14006c6e2  test    eax, eax
0x14006c6e4  jns     short loc_14006C718
0x14006c6e6  lea     rax, WPP_GLOBAL_Control
0x14006c6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c6f4  cmp     rcx, rax
0x14006c6f7  jz      short loc_14006C718
0x14006c6f9  test    dword ptr [rcx+2Ch], 4000000h
0x14006c700  jz      short loc_14006C718
0x14006c702  mov     edx, 1Eh
0x14006c707  mov     [rsp+48h+var_20], ebx
0x14006c70b  mov     [rsp+48h+var_28], 23Ch
0x14006c713  jmp     loc_14006C60D
0x14006c718  test    rdi, rdi
0x14006c71b  jz      short loc_14006C72C
0x14006c71d  mov     rax, [rdi]
0x14006c720  mov     rax, [rax+8]
0x14006c724  mov     rcx, rdi
0x14006c727  call    _guard_dispatch_icall
0x14006c72c  mov     eax, ebx
0x14006c72e  mov     rbx, [rsp+48h+arg_0]
0x14006c733  mov     rsi, [rsp+48h+arg_10]
0x14006c738  add     rsp, 40h
0x14006c73c  pop     rdi
0x14006c73d  retn
0x14007b72a  push    rbp
0x14007b72c  sub     rsp, 30h
0x14007b730  mov     rbp, rdx
0x14007b733  mov     rcx, [rbp+38h]
0x14007b737  test    rcx, rcx
0x14007b73a  jz      short loc_14007B750
0x14007b73c  mov     rax, [rcx]
0x14007b73f  mov     rax, [rax+8]
0x14007b743  call    _guard_dispatch_icall
0x14007b748  mov     qword ptr [rbp+38h], 0
0x14007b750  add     rsp, 30h
0x14007b754  pop     rbp
0x14007b755  retn
```
