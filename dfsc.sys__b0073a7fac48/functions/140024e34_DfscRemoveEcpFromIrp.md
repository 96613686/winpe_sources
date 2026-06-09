# DfscRemoveEcpFromIrp

- ea: `0x140024e34`
- end: `0x140024eac`
- name: `DfscRemoveEcpFromIrp`
- size: `120`
- prototype: `NTSTATUS __fastcall(IRP *, const GUID *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d9b0`
- `0x140020e10`
- `0x1400239b0`

## callees

- `0x140024e34`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140024e54`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140024e54`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x140024e79`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x140024e79`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140024e90`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140024e90`

## pseudocode

```c
NTSTATUS __fastcall DfscRemoveEcpFromIrp(IRP *a1, const GUID *a2)
{
  NTSTATUS result; // eax
  NTSTATUS v4; // ebx
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+40h] [rbp+18h] BYREF
  PVOID EcpContext; // [rsp+48h] [rbp+20h] BYREF

  EcpContext = 0;
  ExtraCreateParameter = 0;
  result = IoGetIrpExtraCreateParameter(a1, &ExtraCreateParameter);
  if ( !result )
  {
    if ( ExtraCreateParameter )
    {
      v4 = FsRtlRemoveExtraCreateParameter(ExtraCreateParameter, a2, &EcpContext, 0);
      if ( !v4 )
        FsRtlFreeExtraCreateParameter(EcpContext);
      return v4;
    }
    else
    {
      return -1073741275;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140024e34  push    rbx
0x140024e36  sub     rsp, 20h
0x140024e3a  mov     rbx, rdx
0x140024e3d  mov     [rsp+28h+EcpContext], 0
0x140024e46  lea     rdx, [rsp+28h+ExtraCreateParameter]; ExtraCreateParameter
0x140024e4b  mov     [rsp+28h+ExtraCreateParameter], 0
0x140024e54  call    cs:__imp_IoGetIrpExtraCreateParameter
0x140024e5b  nop     dword ptr [rax+rax+00h]
0x140024e60  test    eax, eax
0x140024e62  jnz     short loc_140024E9E
0x140024e64  mov     rcx, [rsp+28h+ExtraCreateParameter]; EcpList
0x140024e69  test    rcx, rcx
0x140024e6c  jz      short loc_140024EA5
0x140024e6e  xor     r9d, r9d; EcpContextSize
0x140024e71  lea     r8, [rsp+28h+EcpContext]; EcpContext
0x140024e76  mov     rdx, rbx; EcpType
0x140024e79  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x140024e80  nop     dword ptr [rax+rax+00h]
0x140024e85  mov     ebx, eax
0x140024e87  test    eax, eax
0x140024e89  jnz     short loc_140024E9C
0x140024e8b  mov     rcx, [rsp+28h+EcpContext]; EcpContext
0x140024e90  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140024e97  nop     dword ptr [rax+rax+00h]
0x140024e9c  mov     eax, ebx
0x140024e9e  add     rsp, 20h
0x140024ea2  pop     rbx
0x140024ea3  retn
0x140024ea5  mov     eax, 0C0000225h
0x140024eaa  jmp     short loc_140024E9E
```
