# MupGetRequiredHardeningCapabilitiesFromIrp

- ea: `0x1400022d0`
- end: `0x14000238d`
- name: `MupGetRequiredHardeningCapabilitiesFromIrp`
- size: `189`
- prototype: `NTSTATUS __fastcall(IRP *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001cf8`

## callees

- `0x1400022d0`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000231c`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000231c`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1400022ee`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1400022ee`

## pseudocode

```c
NTSTATUS __fastcall MupGetRequiredHardeningCapabilitiesFromIrp(IRP *a1, int *a2)
{
  NTSTATUS result; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // edx
  PVOID EcpContext; // [rsp+40h] [rbp+18h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+48h] [rbp+20h] BYREF

  ExtraCreateParameter = 0;
  EcpContext = 0;
  result = IoGetIrpExtraCreateParameter(a1, &ExtraCreateParameter);
  if ( result )
    return -1073741595;
  if ( !ExtraCreateParameter )
    goto LABEL_7;
  EcpContext = 0;
  result = FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_NETWORK_OPEN_CONTEXT, &EcpContext, 0);
  if ( result == -1073741275 )
  {
    *a2 = 0;
    return 0;
  }
  if ( !result )
  {
LABEL_7:
    if ( EcpContext )
    {
      v4 = *((_DWORD *)EcpContext + 2);
      if ( v4 == 3 )
      {
        v5 = 6;
      }
      else if ( v4 == 2 || (v5 = 0, v4 == 4) )
      {
        v5 = 2;
      }
      v6 = v5 | 1;
      if ( (*((_DWORD *)EcpContext + 3) & 8) == 0 )
        v6 = v5;
      *a2 = v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400022d0  mov     [rsp+arg_0], rbx
0x1400022d5  push    rdi
0x1400022d6  sub     rsp, 20h
0x1400022da  mov     rbx, rdx
0x1400022dd  xor     edi, edi
0x1400022df  lea     rdx, [rsp+28h+ExtraCreateParameter]; ExtraCreateParameter
0x1400022e4  mov     [rsp+28h+ExtraCreateParameter], rdi
0x1400022e9  mov     [rsp+28h+EcpContext], rdi
0x1400022ee  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1400022f5  nop     dword ptr [rax+rax+00h]
0x1400022fa  test    eax, eax
0x1400022fc  jnz     short loc_140002376
0x1400022fe  mov     rcx, [rsp+28h+ExtraCreateParameter]; EcpList
0x140002303  test    rcx, rcx
0x140002306  jz      short loc_140002343
0x140002308  xor     r9d, r9d; EcpContextSize
0x14000230b  mov     [rsp+28h+EcpContext], rdi
0x140002310  lea     r8, [rsp+28h+EcpContext]; EcpContext
0x140002315  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14000231c  call    cs:__imp_FsRtlFindExtraCreateParameter
0x140002323  nop     dword ptr [rax+rax+00h]
0x140002328  cmp     eax, 0C0000225h
0x14000232d  jnz     short loc_14000233F
0x14000232f  mov     [rbx], edi
0x140002331  mov     eax, edi
0x140002333  mov     rbx, [rsp+28h+arg_0]
0x140002338  add     rsp, 20h
0x14000233c  pop     rdi
0x14000233d  retn
0x14000233f  test    eax, eax
0x140002341  jnz     short loc_140002333
0x140002343  mov     rdx, [rsp+28h+EcpContext]
0x140002348  test    rdx, rdx
0x14000234b  jz      short loc_140002333
0x14000234d  mov     ecx, [rdx+8]
0x140002350  cmp     ecx, 3
0x140002353  jz      short loc_14000237D
0x140002355  cmp     ecx, 2
0x140002358  jz      short loc_140002385
0x14000235a  mov     r8d, edi
0x14000235d  cmp     ecx, 4
0x140002360  jz      short loc_140002385
0x140002362  mov     ecx, [rdx+0Ch]
0x140002365  mov     edx, r8d
0x140002368  or      edx, 1
0x14000236b  test    cl, 8
0x14000236e  cmovz   edx, r8d
0x140002372  mov     [rbx], edx
0x140002374  jmp     short loc_140002333
0x140002376  mov     eax, 0C00000E5h
0x14000237b  jmp     short loc_140002333
0x14000237d  mov     r8d, 6
0x140002383  jmp     short loc_140002362
0x140002385  mov     r8d, 2
0x14000238b  jmp     short loc_140002362
```
