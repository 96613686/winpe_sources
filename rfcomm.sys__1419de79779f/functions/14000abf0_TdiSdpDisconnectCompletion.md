# TdiSdpDisconnectCompletion

- ea: `0x14000abf0`
- end: `0x14000ac8e`
- name: `TdiSdpDisconnectCompletion`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000abf0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ac49`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ac49`

## pseudocode

```c
void __fastcall TdiSdpDisconnectCompletion(__int64 a1, int a2)
{
  int v3; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      109,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), TdiServiceClassIdCallback, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      15,
      110,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
}

```

## disassembly

```asm
0x14000abf0  mov     [rsp+arg_0], rbx
0x14000abf5  mov     [rsp+arg_8], rbp
0x14000abfa  push    rdi
0x14000abfb  sub     rsp, 30h
0x14000abff  mov     rbx, rcx
0x14000ac02  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000ac09  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000ac10  lea     rbp, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000ac17  jz      short loc_14000AC38
0x14000ac19  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac20  mov     r9d, 6Dh ; 'm'
0x14000ac26  mov     [rsp+38h+var_18], rbp
0x14000ac2b  mov     rcx, [rcx+40h]
0x14000ac2f  lea     r8d, [r9-5Eh]
0x14000ac33  call    WPP_RECORDER_SF_
0x14000ac38  lea     rcx, [rbx+28h]; RemoveLock
0x14000ac3c  mov     r8d, 20h ; ' '; RemlockSize
0x14000ac42  lea     rdx, TdiServiceClassIdCallback; Tag
0x14000ac49  call    cs:__imp_IoReleaseRemoveLockEx
0x14000ac50  nop     dword ptr [rax+rax+00h]
0x14000ac55  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000ac5c  jz      short loc_14000AC7D
0x14000ac5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac65  mov     r9d, 6Eh ; 'n'
0x14000ac6b  mov     [rsp+38h+var_18], rbp
0x14000ac70  mov     rcx, [rcx+40h]
0x14000ac74  lea     r8d, [r9-5Fh]
0x14000ac78  call    WPP_RECORDER_SF_
0x14000ac7d  mov     rbx, [rsp+38h+arg_0]
0x14000ac82  mov     rbp, [rsp+38h+arg_8]
0x14000ac87  add     rsp, 30h
0x14000ac8b  pop     rdi
0x14000ac8c  retn
```
