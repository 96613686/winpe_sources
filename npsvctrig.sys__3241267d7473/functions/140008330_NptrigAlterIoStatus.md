# NptrigAlterIoStatus

- ea: `0x140008330`
- end: `0x14000838c`
- name: `NptrigAlterIoStatus`
- size: `92`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA Data, NTSTATUS, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140008520`
- `0x140008a80`
- `0x140008ed0`
- `0x140009da0`
- `0x140009fa0`

## callees

- `0x140001220`
- `0x140008330`

## import_xrefs

- `FLTMGR!FltSetCallbackDataDirty` at `0x140008374`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140008374`

## pseudocode

```c
void __fastcall NptrigAlterIoStatus(PFLT_CALLBACK_DATA Data, NTSTATUS a2, __int64 a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 10, a3, Data, a2);
  Data->IoStatus.Status = a2;
  FltSetCallbackDataDirty(Data);
}

```

## disassembly

```asm
0x140008330  mov     [rsp+arg_0], rbx
0x140008335  push    rdi
0x140008336  sub     rsp, 30h
0x14000833a  mov     edi, edx
0x14000833c  mov     rbx, rcx
0x14000833f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008346  lea     rax, WPP_GLOBAL_Control
0x14000834d  cmp     rcx, rax
0x140008350  jz      short loc_14000836E
0x140008352  mov     eax, [rcx+2Ch]
0x140008355  test    al, 4
0x140008357  jz      short loc_14000836E
0x140008359  mov     rcx, [rcx+18h]
0x14000835d  mov     edx, 0Ah
0x140008362  mov     r9, rbx
0x140008365  mov     [rsp+38h+var_18], edi
0x140008369  call    WPP_SF_qd
0x14000836e  mov     rcx, rbx; Data
0x140008371  mov     [rbx+18h], edi
0x140008374  call    cs:__imp_FltSetCallbackDataDirty
0x14000837b  nop     dword ptr [rax+rax+00h]
0x140008380  mov     rbx, [rsp+38h+arg_0]
0x140008385  add     rsp, 30h
0x140008389  pop     rdi
0x14000838a  retn
```
