# DfscRestartCreateViaReparse

- ea: `0x140012858`
- end: `0x140012928`
- name: `DfscRestartCreateViaReparse`
- size: `208`
- prototype: `NTSTATUS __fastcall(IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140021140`

## callees

- `0x140012858`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140012878`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140012878`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1400128ab`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1400128ab`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1400128f5`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1400128f5`
- `MUP!MupSurrogateRestoreFileNameInFileObject` at `0x140012904`
- `MUP!MupSurrogateRestoreFileNameInFileObject` at `0x140012904`

## pseudocode

```c
NTSTATUS __fastcall DfscRestartCreateViaReparse(IRP *a1)
{
  NTSTATUS result; // eax
  int v3; // eax
  PVOID v4; // rcx
  PVOID EcpContext; // [rsp+38h] [rbp+10h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+40h] [rbp+18h] BYREF

  ExtraCreateParameter = 0;
  EcpContext = 0;
  if ( IoGetIrpExtraCreateParameter(a1, &ExtraCreateParameter) )
    return -1073741595;
  if ( !ExtraCreateParameter
    || (result = FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_NETWORK_OPEN_CONTEXT, &EcpContext, 0)) == 0
    || result == -1073741275 )
  {
    if ( EcpContext )
    {
      v3 = 1;
      if ( (*((_DWORD *)EcpContext + 2) & 0xFFFFFFFB) != 0 )
        v3 = *((_DWORD *)EcpContext + 2);
      *((_DWORD *)EcpContext + 5) = v3;
      v4 = EcpContext;
      if ( (*((_DWORD *)EcpContext + 3) & 8) != 0 )
      {
        *((_DWORD *)EcpContext + 6) |= 8u;
        v4 = EcpContext;
      }
      FsRtlAcknowledgeEcp(v4);
    }
    result = MupSurrogateRestoreFileNameInFileObject(a1);
    if ( !result )
    {
      result = 260;
      a1->IoStatus.Information = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012858  push    rbx
0x14001285a  sub     rsp, 20h
0x14001285e  lea     rdx, [rsp+28h+ExtraCreateParameter]; ExtraCreateParameter
0x140012863  mov     [rsp+28h+ExtraCreateParameter], 0
0x14001286c  mov     rbx, rcx
0x14001286f  mov     [rsp+28h+EcpContext], 0
0x140012878  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14001287f  nop     dword ptr [rax+rax+00h]
0x140012884  test    eax, eax
0x140012886  jz      short loc_140012892
0x140012888  mov     eax, 0C00000E5h
0x14001288d  jmp     loc_140012921
0x140012892  mov     rcx, [rsp+28h+ExtraCreateParameter]; EcpList
0x140012897  test    rcx, rcx
0x14001289a  jz      short loc_1400128C2
0x14001289c  xor     r9d, r9d; EcpContextSize
0x14001289f  lea     r8, [rsp+28h+EcpContext]; EcpContext
0x1400128a4  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x1400128ab  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1400128b2  nop     dword ptr [rax+rax+00h]
0x1400128b7  test    eax, eax
0x1400128b9  jz      short loc_1400128C2
0x1400128bb  cmp     eax, 0C0000225h
0x1400128c0  jnz     short loc_140012921
0x1400128c2  mov     rdx, [rsp+28h+EcpContext]
0x1400128c7  test    rdx, rdx
0x1400128ca  jz      short loc_140012901
0x1400128cc  mov     ecx, [rdx+8]
0x1400128cf  mov     eax, 1
0x1400128d4  test    ecx, 0FFFFFFFBh
0x1400128da  cmovnz  eax, ecx
0x1400128dd  mov     [rdx+14h], eax
0x1400128e0  mov     rcx, [rsp+28h+EcpContext]
0x1400128e5  mov     eax, [rcx+0Ch]
0x1400128e8  test    al, 8
0x1400128ea  jz      short loc_1400128F5
0x1400128ec  or      dword ptr [rcx+18h], 8
0x1400128f0  mov     rcx, [rsp+28h+EcpContext]; EcpContext
0x1400128f5  call    cs:__imp_FsRtlAcknowledgeEcp
0x1400128fc  nop     dword ptr [rax+rax+00h]
0x140012901  mov     rcx, rbx
0x140012904  call    cs:__imp_MupSurrogateRestoreFileNameInFileObject
0x14001290b  nop     dword ptr [rax+rax+00h]
0x140012910  test    eax, eax
0x140012912  jnz     short loc_140012921
0x140012914  mov     eax, 104h
0x140012919  mov     qword ptr [rbx+38h], 0
0x140012921  add     rsp, 20h
0x140012925  pop     rbx
0x140012926  retn
```
