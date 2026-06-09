# MdaNotifyCompleteIrp

- ea: `0x14002f744`
- end: `0x14002f94e`
- name: `MdaNotifyCompleteIrp`
- size: `522`
- prototype: `NTSTATUS __fastcall(PRX_CONTEXT RxContext, __int64, unsigned int, NTSTATUS)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002f954`
- `0x14002fa64`

## callees

- `0x1400159cc`
- `0x14002f744`
- `0x140030724`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f828`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f828`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f8c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f8c5`
- `rdbss!RxLowIoCompletion` at `0x14002f907`
- `rdbss!RxLowIoCompletion` at `0x14002f907`

## pseudocode

```c
NTSTATUS __fastcall MdaNotifyCompleteIrp(PRX_CONTEXT RxContext, __int64 a2, unsigned int a3, NTSTATUS a4)
{
  size_t v5; // rdi
  PIRP *p_CurrentIrp; // r14
  PIRP CurrentIrp; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  const void **v11; // r15
  const void *v12; // rdx
  void *MasterIrp; // rcx
  PMDL MdlAddress; // r10
  PVOID MappedSystemVa; // rax
  void *v16; // rcx
  NTSTATUS result; // eax

  v5 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  MdaNotifySetCancelRoutine(RxContext);
  if ( !a4 )
  {
    if ( (_DWORD)v5 )
    {
      p_CurrentIrp = &RxContext->CurrentIrp;
      CurrentIrp = RxContext->CurrentIrp;
      CurrentStackLocation = CurrentIrp->Tail.Overlay.CurrentStackLocation;
      if ( CurrentStackLocation->Parameters.Read.Length >= (unsigned int)v5 )
      {
        v11 = (const void **)(a2 + 600);
        v12 = *(const void **)(a2 + 600);
        if ( !v12 )
        {
LABEL_25:
          (*p_CurrentIrp)->IoStatus.Information = (unsigned int)v5;
          *(_QWORD *)(a2 + 608) = 0;
          goto LABEL_27;
        }
        if ( CurrentIrp->AssociatedIrp.MasterIrp )
        {
          MasterIrp = CurrentIrp->AssociatedIrp.MasterIrp;
        }
        else
        {
          MdlAddress = CurrentIrp->MdlAddress;
          if ( MdlAddress )
          {
            if ( (MdlAddress->MdlFlags & 5) != 0 )
              MappedSystemVa = MdlAddress->MappedSystemVa;
            else
              MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
            if ( !MappedSystemVa )
            {
              a4 = 268;
              LODWORD(v5) = 0;
              goto LABEL_21;
            }
            v12 = *v11;
            MasterIrp = MappedSystemVa;
          }
          else
          {
            if ( (CurrentStackLocation->Control & 1) != 0 )
            {
              CurrentIrp->Flags |= 0x70u;
              (*p_CurrentIrp)->AssociatedIrp.MasterIrp = (struct _IRP *)*v11;
LABEL_21:
              v16 = (void *)*v11;
              if ( *v11 != (*p_CurrentIrp)->AssociatedIrp.MasterIrp && v16 )
                ExFreePoolWithTag(v16, 0);
              *v11 = 0;
              *(_DWORD *)(a2 + 620) = 0;
              goto LABEL_25;
            }
            MasterIrp = CurrentIrp->UserBuffer;
          }
        }
        memmove(MasterIrp, v12, v5);
        goto LABEL_21;
      }
    }
    a4 = 268;
  }
LABEL_27:
  RxContext->StoredStatus = a4;
  result = RxLowIoCompletion(RxContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14002f744  mov     [rsp+arg_8], rdx
0x14002f749  mov     [rsp+arg_0], rcx
0x14002f74e  push    rbx
0x14002f74f  push    rsi
0x14002f750  push    rdi
0x14002f751  push    r12
0x14002f753  push    r13
0x14002f755  push    r14
0x14002f757  push    r15
0x14002f759  sub     rsp, 40h
0x14002f75d  mov     ebx, r9d
0x14002f760  mov     edi, r8d
0x14002f763  mov     r13, rdx
0x14002f766  mov     rsi, rcx
0x14002f769  lea     r12, WPP_GLOBAL_Control
0x14002f770  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f777  cmp     rcx, r12
0x14002f77a  jz      short loc_14002F79A
0x14002f77c  test    dword ptr [rcx+2Ch], 80000h
0x14002f783  jz      short loc_14002F79A
0x14002f785  mov     edx, 1Ch
0x14002f78a  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002f791  mov     rcx, [rcx+18h]
0x14002f795  call    WPP_SF_
0x14002f79a  mov     dl, 1
0x14002f79c  mov     rcx, rsi; RxContext
0x14002f79f  call    MdaNotifySetCancelRoutine
0x14002f7a4  test    ebx, ebx
0x14002f7a6  jnz     loc_14002F8FE
0x14002f7ac  test    edi, edi
0x14002f7ae  jz      loc_14002F8F9
0x14002f7b4  lea     r14, [rsi+28h]
0x14002f7b8  mov     [rsp+78h+var_48], r14
0x14002f7bd  mov     rcx, [r14]
0x14002f7c0  mov     rax, [rcx+0B8h]
0x14002f7c7  cmp     [rax+8], edi
0x14002f7ca  jb      loc_14002F8F9
0x14002f7d0  lea     r15, [r13+258h]
0x14002f7d7  mov     [rsp+78h+var_40], r15
0x14002f7dc  mov     rdx, [r15]; Src
0x14002f7df  test    rdx, rdx
0x14002f7e2  jz      loc_14002F8E3
0x14002f7e8  mov     r9, [rcx+18h]
0x14002f7ec  test    r9, r9
0x14002f7ef  jz      short loc_14002F7F6
0x14002f7f1  mov     rcx, r9
0x14002f7f4  jmp     short loc_14002F862
0x14002f7f6  mov     r10, [rcx+8]
0x14002f7fa  test    r10, r10
0x14002f7fd  jz      short loc_14002F858
0x14002f7ff  test    byte ptr [r10+0Ah], 5
0x14002f804  jz      short loc_14002F80C
0x14002f806  mov     rax, [r10+18h]
0x14002f80a  jmp     short loc_14002F834
0x14002f80c  mov     [rsp+78h+Priority], 40000010h; Priority
0x14002f814  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002f81c  xor     r9d, r9d; RequestedAddress
0x14002f81f  xor     edx, edx; AccessMode
0x14002f821  lea     r8d, [r9+1]; CacheType
0x14002f825  mov     rcx, r10; MemoryDescriptorList
0x14002f828  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f82f  nop     dword ptr [rax+rax+00h]
0x14002f834  test    rax, rax
0x14002f837  jz      short loc_14002F841
0x14002f839  mov     rdx, [r15]
0x14002f83c  mov     rcx, rax
0x14002f83f  jmp     short loc_14002F862
0x14002f841  mov     ebx, 10Ch
0x14002f846  mov     [rsp+78h+arg_18], ebx
0x14002f84d  xor     edi, edi
0x14002f84f  mov     [rsp+78h+arg_10], edi
0x14002f856  jmp     short loc_14002F87A
0x14002f858  test    byte ptr [rax+3], 1
0x14002f85c  jnz     short loc_14002F86C
0x14002f85e  mov     rcx, [rcx+70h]; void *
0x14002f862  mov     r8, rdi; Size
0x14002f865  call    memmove
0x14002f86a  jmp     short loc_14002F87A
0x14002f86c  or      dword ptr [rcx+10h], 70h
0x14002f870  mov     rcx, [r14]
0x14002f873  mov     rax, [r15]
0x14002f876  mov     [rcx+18h], rax
0x14002f87a  jmp     short loc_14002F8B2
0x14002f87c  mov     ebx, 10Ch
0x14002f881  mov     [rsp+78h+arg_18], ebx
0x14002f888  xor     edi, edi
0x14002f88a  mov     [rsp+78h+arg_10], edi
0x14002f891  lea     r12, WPP_GLOBAL_Control
0x14002f898  mov     r13, [rsp+78h+arg_8]
0x14002f8a0  mov     rsi, [rsp+78h+arg_0]
0x14002f8a8  mov     r14, [rsp+78h+var_48]
0x14002f8ad  mov     r15, [rsp+78h+var_40]
0x14002f8b2  mov     rcx, [r15]; P
0x14002f8b5  mov     rax, [r14]
0x14002f8b8  cmp     rcx, [rax+18h]
0x14002f8bc  jz      short loc_14002F8D1
0x14002f8be  test    rcx, rcx
0x14002f8c1  jz      short loc_14002F8D1
0x14002f8c3  xor     edx, edx; Tag
0x14002f8c5  call    cs:__imp_ExFreePoolWithTag
0x14002f8cc  nop     dword ptr [rax+rax+00h]
0x14002f8d1  mov     qword ptr [r15], 0
0x14002f8d8  mov     dword ptr [r13+26Ch], 0
0x14002f8e3  mov     ecx, edi
0x14002f8e5  mov     rax, [r14]
0x14002f8e8  mov     [rax+38h], rcx
0x14002f8ec  mov     qword ptr [r13+260h], 0
0x14002f8f7  jmp     short loc_14002F8FE
0x14002f8f9  mov     ebx, 10Ch
0x14002f8fe  mov     [rsi+0B0h], ebx
0x14002f904  mov     rcx, rsi; RxContext
0x14002f907  call    cs:__imp_RxLowIoCompletion
0x14002f90e  nop     dword ptr [rax+rax+00h]
0x14002f913  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f91a  cmp     rcx, r12
0x14002f91d  jz      short loc_14002F93D
0x14002f91f  test    dword ptr [rcx+2Ch], 80000h
0x14002f926  jz      short loc_14002F93D
0x14002f928  mov     edx, 1Dh
0x14002f92d  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14002f934  mov     rcx, [rcx+18h]
0x14002f938  call    WPP_SF_
0x14002f93d  add     rsp, 40h
0x14002f941  pop     r15
0x14002f943  pop     r14
0x14002f945  pop     r13
0x14002f947  pop     r12
0x14002f949  pop     rdi
0x14002f94a  pop     rsi
0x14002f94b  pop     rbx
0x14002f94c  retn
```
