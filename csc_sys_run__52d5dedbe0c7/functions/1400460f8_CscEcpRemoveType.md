# CscEcpRemoveType

- ea: `0x1400460f8`
- end: `0x140046222`
- name: `CscEcpRemoveType`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400460c4`

## callees

- `0x1400190ec`
- `0x1400460f8`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400461ff`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400461ff`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x1400461b8`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x1400461b8`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140046123`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140046123`

## pseudocode

```c
__int64 __fastcall CscEcpRemoveType(IRP *a1, __int64 a2)
{
  NTSTATUS IrpExtraCreateParameter; // ebx
  int v4; // esi
  struct _ECP_LIST *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rdx
  PECP_LIST EcpList; // [rsp+30h] [rbp-28h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+20h] BYREF

  EcpList = 0;
  EcpContext = 0;
  IrpExtraCreateParameter = IoGetIrpExtraCreateParameter(a1, &EcpList);
  if ( IrpExtraCreateParameter >= 0 )
  {
    v6 = EcpList;
    if ( EcpList )
    {
      v4 = 0;
      v7 = 0;
      while ( 1 )
      {
        v8 = *(int *)(a2 + 4 * v7);
        EcpContext = 0;
        IrpExtraCreateParameter = FsRtlRemoveExtraCreateParameter(v6, (LPCGUID)off_140031000[v8], &EcpContext, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_f74abd63425539499d784964bfbadaaa_Traceguids,
            *(unsigned int *)(a2 + 4 * v7),
            IrpExtraCreateParameter);
        }
        if ( !IrpExtraCreateParameter )
          FsRtlFreeExtraCreateParameter(EcpContext);
        if ( ++v7 == 3 )
          break;
        v6 = EcpList;
      }
    }
    else
    {
      v4 = 688;
    }
  }
  else
  {
    v4 = 681;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      WPP_f74abd63425539499d784964bfbadaaa_Traceguids,
      (unsigned int)IrpExtraCreateParameter,
      v4);
  return (unsigned int)IrpExtraCreateParameter;
}

```

## disassembly

```asm
0x1400460f8  mov     rax, rsp
0x1400460fb  mov     [rax+8], rbx
0x1400460ff  mov     [rax+10h], rsi
0x140046103  push    rdi
0x140046104  push    r14
0x140046106  push    r15
0x140046108  sub     rsp, 40h
0x14004610c  mov     r14, rdx
0x14004610f  mov     qword ptr [rax-28h], 0
0x140046117  lea     rdx, [rax-28h]; ExtraCreateParameter
0x14004611b  mov     qword ptr [rax+20h], 0
0x140046123  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14004612a  nop     dword ptr [rax+rax+00h]
0x14004612f  lea     r15, WPP_GLOBAL_Control
0x140046136  mov     ebx, eax
0x140046138  test    eax, eax
0x14004613a  jns     short loc_140046187
0x14004613c  mov     esi, 2A9h
0x140046141  mov     rcx, cs:WPP_GLOBAL_Control
0x140046148  cmp     rcx, r15
0x14004614b  jz      short loc_140046170
0x14004614d  mov     eax, [rcx+2Ch]
0x140046150  test    al, 20h
0x140046152  jz      short loc_140046170
0x140046154  mov     rcx, [rcx+18h]
0x140046158  lea     r8, WPP_f74abd63425539499d784964bfbadaaa_Traceguids
0x14004615f  mov     edx, 11h
0x140046164  mov     [rsp+58h+var_38], esi
0x140046168  mov     r9d, ebx
0x14004616b  call    WPP_SF_Dd
0x140046170  mov     rsi, [rsp+58h+arg_8]
0x140046175  mov     eax, ebx
0x140046177  mov     rbx, [rsp+58h+arg_0]
0x14004617c  add     rsp, 40h
0x140046180  pop     r15
0x140046182  pop     r14
0x140046184  pop     rdi
0x140046185  retn
0x140046187  mov     rcx, [rsp+58h+EcpList]; EcpList
0x14004618c  test    rcx, rcx
0x14004618f  jnz     short loc_140046198
0x140046191  mov     esi, 2B0h
0x140046196  jmp     short loc_140046141
0x140046198  xor     esi, esi
0x14004619a  xor     edi, edi
0x14004619c  movsxd  rdx, dword ptr [r14+rdi*4]
0x1400461a0  lea     rax, off_140031000
0x1400461a7  xor     r9d, r9d; EcpContextSize
0x1400461aa  mov     [rsp+58h+EcpContext], rsi
0x1400461af  lea     r8, [rsp+58h+EcpContext]; EcpContext
0x1400461b4  mov     rdx, [rax+rdx*8]; EcpType
0x1400461b8  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x1400461bf  nop     dword ptr [rax+rax+00h]
0x1400461c4  mov     ebx, eax
0x1400461c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400461cd  cmp     rcx, r15
0x1400461d0  jz      short loc_1400461F6
0x1400461d2  mov     eax, [rcx+2Ch]
0x1400461d5  test    al, 20h
0x1400461d7  jz      short loc_1400461F6
0x1400461d9  mov     r9d, [r14+rdi*4]
0x1400461dd  lea     r8, WPP_f74abd63425539499d784964bfbadaaa_Traceguids
0x1400461e4  mov     rcx, [rcx+18h]
0x1400461e8  mov     edx, 10h
0x1400461ed  mov     [rsp+58h+var_38], ebx
0x1400461f1  call    WPP_SF_Dd
0x1400461f6  test    ebx, ebx
0x1400461f8  jnz     short loc_14004620B
0x1400461fa  mov     rcx, [rsp+58h+EcpContext]; EcpContext
0x1400461ff  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140046206  nop     dword ptr [rax+rax+00h]
0x14004620b  inc     rdi
0x14004620e  cmp     rdi, 3
0x140046212  jz      loc_140046141
0x140046218  mov     rcx, [rsp+58h+EcpList]
0x14004621d  jmp     loc_14004619C
```
