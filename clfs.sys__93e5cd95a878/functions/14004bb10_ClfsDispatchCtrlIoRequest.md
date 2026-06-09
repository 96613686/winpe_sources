# ClfsDispatchCtrlIoRequest

- ea: `0x14004bb10`
- end: `0x14004bbb3`
- name: `ClfsDispatchCtrlIoRequest`
- size: `163`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400726d0`

## callees

- `0x14000ed64`
- `0x140040ba8`
- `0x14004bb10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14004bb99`
- `ntoskrnl!IofCompleteRequest` at `0x140080537`
- `ntoskrnl!IofCompleteRequest` at `0x14004bb99`
- `ntoskrnl!IofCompleteRequest` at `0x140080537`

## pseudocode

```c
__int64 __fastcall ClfsDispatchCtrlIoRequest(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  int v3; // ebx
  int v5; // [rsp+28h] [rbp-20h]
  int v6; // [rsp+30h] [rbp-18h]

  v3 = CClfsRequest::DispatchCntrl(a2, a1);
  v6 = v3;
  if ( v3 < 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    v5 = v3;
    WPP_SF_slD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      34,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsDispatchCtrlIoRequest",
      208,
      v5,
      v6);
  }
  IofCompleteRequest(a2, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14004bb10  mov     [rsp+arg_0], rbx
0x14004bb15  mov     [rsp+arg_8], rdx
0x14004bb1a  push    rdi
0x14004bb1b  sub     rsp, 40h
0x14004bb1f  mov     rdi, rdx
0x14004bb22  mov     rdx, rcx; struct _DEVICE_OBJECT *
0x14004bb25  mov     rcx, rdi; struct _IRP *
0x14004bb28  call    ?DispatchCntrl@CClfsRequest@@SAJPEAU_IRP@@PEAU_DEVICE_OBJECT@@@Z; CClfsRequest::DispatchCntrl(_IRP *,_DEVICE_OBJECT *)
0x14004bb2d  mov     ebx, eax
0x14004bb2f  mov     [rsp+48h+var_18], eax
0x14004bb33  jmp     short loc_14004BB4B
0x14004bb35  mov     ebx, eax
0x14004bb37  mov     [rsp+48h+var_18], eax
0x14004bb3b  mov     rdi, [rsp+48h+arg_8]
0x14004bb40  mov     qword ptr [rdi+38h], 0
0x14004bb48  mov     [rdi+30h], eax
0x14004bb4b  test    ebx, ebx
0x14004bb4d  jns     short loc_14004BB94
0x14004bb4f  lea     rax, WPP_GLOBAL_Control
0x14004bb56  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bb5d  cmp     rcx, rax
0x14004bb60  jz      short loc_14004BB94
0x14004bb62  mov     eax, [rcx+2Ch]
0x14004bb65  bt      eax, 1Ah
0x14004bb69  jnb     short loc_14004BB94
0x14004bb6b  mov     edx, 22h ; '"'
0x14004bb70  mov     [rsp+48h+var_20], ebx
0x14004bb74  mov     [rsp+48h+var_28], 2D0h
0x14004bb7c  lea     r9, aClfsdispatchct; "ClfsDispatchCtrlIoRequest"
0x14004bb83  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004bb8a  mov     rcx, [rcx+18h]
0x14004bb8e  call    WPP_SF_slD
0x14004bb93  nop
0x14004bb94  xor     edx, edx; PriorityBoost
0x14004bb96  mov     rcx, rdi; Irp
0x14004bb99  call    cs:__imp_IofCompleteRequest
0x14004bba0  nop     dword ptr [rax+rax+00h]
0x14004bba5  mov     eax, ebx
0x14004bba7  mov     rbx, [rsp+48h+arg_0]
0x14004bbac  add     rsp, 40h
0x14004bbb0  pop     rdi
0x14004bbb1  retn
0x140080528  push    rbp
0x14008052a  sub     rsp, 30h
0x14008052e  mov     rbp, rdx
0x140080531  xor     edx, edx; PriorityBoost
0x140080533  mov     rcx, [rbp+58h]; Irp
0x140080537  call    cs:__imp_IofCompleteRequest
0x14008053e  nop     dword ptr [rax+rax+00h]
0x140080543  nop
0x140080544  add     rsp, 30h
0x140080548  pop     rbp
0x140080549  retn
```
