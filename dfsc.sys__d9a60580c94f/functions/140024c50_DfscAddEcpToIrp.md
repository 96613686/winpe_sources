# DfscAddEcpToIrp

- ea: `0x140024c50`
- end: `0x140024dad`
- name: `DfscAddEcpToIrp`
- size: `349`
- prototype: `__int64 __fastcall(PIRP Irp, LPCGUID EcpType, ULONG SizeOfContext)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400239b0`

## callees

- `0x140024c50`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140024d02`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140024d02`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140024cdd`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140024cdd`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140024d4f`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140024d4f`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140024d35`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140024d35`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140024c87`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140024c87`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140024cac`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140024cac`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140024d9a`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140024d9a`
- `ntoskrnl!IoSetIrpExtraCreateParameter` at `0x140024d1a`
- `ntoskrnl!IoSetIrpExtraCreateParameter` at `0x140024d1a`

## pseudocode

```c
NTSTATUS __fastcall DfscAddEcpToIrp(PIRP Irp, LPCGUID EcpType, ULONG SizeOfContext, PVOID *a4)
{
  NTSTATUS result; // eax
  struct _ECP_LIST *v9; // rcx
  NTSTATUS Parameter; // eax
  NTSTATUS v11; // ebx
  NTSTATUS v12; // ebx
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+50h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+68h] [rbp+20h] BYREF

  ExtraCreateParameter = 0;
  EcpContext = 0;
  *a4 = 0;
  if ( (Irp->Flags & 0x80u) == 0 )
    return -1073741808;
  result = IoGetIrpExtraCreateParameter(Irp, &ExtraCreateParameter);
  if ( !result )
  {
    v9 = ExtraCreateParameter;
    if ( !ExtraCreateParameter )
    {
      result = FsRtlAllocateExtraCreateParameterList(0, &ExtraCreateParameter);
      if ( result )
        return result;
      Parameter = IoSetIrpExtraCreateParameter(Irp, ExtraCreateParameter);
      v9 = ExtraCreateParameter;
      v11 = Parameter;
      if ( Parameter )
      {
        FsRtlFreeExtraCreateParameterList(ExtraCreateParameter);
        return v11;
      }
    }
    if ( FsRtlFindExtraCreateParameter(v9, EcpType, &EcpContext, 0) )
    {
      result = FsRtlAllocateExtraCreateParameter(EcpType, SizeOfContext, 0, 0, 0x48436644u, &EcpContext);
      if ( !result )
      {
        v12 = FsRtlInsertExtraCreateParameter(ExtraCreateParameter, EcpContext);
        if ( v12 )
        {
          FsRtlFreeExtraCreateParameter(EcpContext);
          return v12;
        }
        else
        {
          *a4 = EcpContext;
          return 0;
        }
      }
    }
    else
    {
      *a4 = EcpContext;
      return 0x40000000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140024c50  mov     [rsp+arg_8], rbx
0x140024c55  push    rbp
0x140024c56  push    rsi
0x140024c57  push    rdi
0x140024c58  sub     rsp, 30h
0x140024c5c  xor     eax, eax
0x140024c5e  mov     rsi, r9
0x140024c61  mov     [rsp+48h+ExtraCreateParameter], rax
0x140024c66  mov     ebp, r8d
0x140024c69  mov     [rsp+48h+EcpContext], rax
0x140024c6e  mov     rdi, rdx
0x140024c71  mov     [r9], rax
0x140024c74  mov     rbx, rcx
0x140024c77  mov     eax, [rcx+10h]
0x140024c7a  test    al, al
0x140024c7c  jns     loc_140024D8B
0x140024c82  lea     rdx, [rsp+48h+ExtraCreateParameter]; ExtraCreateParameter
0x140024c87  call    cs:__imp_IoGetIrpExtraCreateParameter
0x140024c8e  nop     dword ptr [rax+rax+00h]
0x140024c93  test    eax, eax
0x140024c95  jnz     short loc_140024CED
0x140024c97  mov     rcx, [rsp+48h+ExtraCreateParameter]; EcpList
0x140024c9c  test    rcx, rcx
0x140024c9f  jz      short loc_140024CFB
0x140024ca1  xor     r9d, r9d; EcpContextSize
0x140024ca4  lea     r8, [rsp+48h+EcpContext]; EcpContext
0x140024ca9  mov     rdx, rdi; EcpType
0x140024cac  call    cs:__imp_FsRtlFindExtraCreateParameter
0x140024cb3  nop     dword ptr [rax+rax+00h]
0x140024cb8  test    eax, eax
0x140024cba  jz      loc_140024D79
0x140024cc0  lea     rax, [rsp+48h+EcpContext]
0x140024cc5  xor     r9d, r9d; CleanupCallback
0x140024cc8  mov     [rsp+48h+var_20], rax; EcpContext
0x140024ccd  xor     r8d, r8d; Flags
0x140024cd0  mov     edx, ebp; SizeOfContext
0x140024cd2  mov     [rsp+48h+PoolTag], 48436644h; PoolTag
0x140024cda  mov     rcx, rdi; EcpType
0x140024cdd  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140024ce4  nop     dword ptr [rax+rax+00h]
0x140024ce9  test    eax, eax
0x140024ceb  jz      short loc_140024D45
0x140024ced  mov     rbx, [rsp+48h+arg_8]
0x140024cf2  add     rsp, 30h
0x140024cf6  pop     rdi
0x140024cf7  pop     rsi
0x140024cf8  pop     rbp
0x140024cf9  retn
0x140024cfb  lea     rdx, [rsp+48h+ExtraCreateParameter]; EcpList
0x140024d00  xor     ecx, ecx; Flags
0x140024d02  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140024d09  nop     dword ptr [rax+rax+00h]
0x140024d0e  test    eax, eax
0x140024d10  jnz     short loc_140024CED
0x140024d12  mov     rdx, [rsp+48h+ExtraCreateParameter]; ExtraCreateParameter
0x140024d17  mov     rcx, rbx; Irp
0x140024d1a  call    cs:__imp_IoSetIrpExtraCreateParameter
0x140024d21  nop     dword ptr [rax+rax+00h]
0x140024d26  mov     rcx, [rsp+48h+ExtraCreateParameter]; EcpList
0x140024d2b  mov     ebx, eax
0x140024d2d  test    eax, eax
0x140024d2f  jz      loc_140024CA1
0x140024d35  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140024d3c  nop     dword ptr [rax+rax+00h]
0x140024d41  mov     eax, ebx
0x140024d43  jmp     short loc_140024CED
0x140024d45  mov     rdx, [rsp+48h+EcpContext]; EcpContext
0x140024d4a  mov     rcx, [rsp+48h+ExtraCreateParameter]; EcpList
0x140024d4f  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140024d56  nop     dword ptr [rax+rax+00h]
0x140024d5b  mov     ebx, eax
0x140024d5d  test    eax, eax
0x140024d5f  jnz     short loc_140024D95
0x140024d61  mov     rax, [rsp+48h+EcpContext]
0x140024d66  mov     [rsi], rax
0x140024d69  mov     eax, ebx
0x140024d6b  mov     rbx, [rsp+48h+arg_8]
0x140024d70  add     rsp, 30h
0x140024d74  pop     rdi
0x140024d75  pop     rsi
0x140024d76  pop     rbp
0x140024d77  retn
0x140024d79  mov     rax, [rsp+48h+EcpContext]
0x140024d7e  mov     [rsi], rax
0x140024d81  mov     eax, 40000000h
0x140024d86  jmp     loc_140024CED
0x140024d8b  mov     eax, 0C0000010h
0x140024d90  jmp     loc_140024CED
0x140024d95  mov     rcx, [rsp+48h+EcpContext]; EcpContext
0x140024d9a  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140024da1  nop     dword ptr [rax+rax+00h]
0x140024da6  mov     eax, ebx
0x140024da8  jmp     loc_140024CED
```
