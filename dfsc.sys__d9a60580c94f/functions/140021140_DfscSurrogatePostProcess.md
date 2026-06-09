# DfscSurrogatePostProcess

- ea: `0x140021140`
- end: `0x1400212f0`
- name: `DfscSurrogatePostProcess`
- size: `432`
- prototype: `__int64 __fastcall(IRP **)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x1400025f4`
- `0x140012858`
- `0x140021140`
- `0x140021300`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140021179`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140021179`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1400211a7`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1400211a7`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x1400211dd`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x140021289`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x1400211dd`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x140021289`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400211f2`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14002129e`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400211f2`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14002129e`
- `MUP!MupSurrogatePurgeNegativeCacheEntry` at `0x140021253`
- `MUP!MupSurrogatePurgeNegativeCacheEntry` at `0x140021253`

## pseudocode

```c
__int64 __fastcall DfscSurrogatePostProcess(IRP **a1)
{
  IRP *v1; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  UCHAR MajorFunction; // al
  unsigned int v5; // edi
  PVOID EcpContext; // [rsp+40h] [rbp+8h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+48h] [rbp+10h] BYREF

  v1 = *a1;
  CurrentStackLocation = (*a1)->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction <= 1u )
  {
LABEL_2:
    ExtraCreateParameter = 0;
    EcpContext = 0;
    if ( !IoGetIrpExtraCreateParameter(v1, &ExtraCreateParameter) )
    {
      if ( ExtraCreateParameter )
      {
        EcpContext = 0;
        if ( !FsRtlFindExtraCreateParameter(ExtraCreateParameter, &DFSC_DFS_SHARE_CHECK_ECP_GUID, &EcpContext, 0) )
        {
          if ( v1->IoStatus.Status == -1073741788 )
          {
            MupSurrogatePurgeNegativeCacheEntry(a1, &CurrentStackLocation->FileObject->FileName);
            v5 = DfscRestartCreateViaReparse(v1);
            if ( v5 != 260 )
            {
              EcpContext = 0;
              if ( !FsRtlRemoveExtraCreateParameter(
                      ExtraCreateParameter,
                      &DFSC_DFS_SHARE_CHECK_ECP_GUID,
                      &EcpContext,
                      0) )
                FsRtlFreeExtraCreateParameter(EcpContext);
              v5 = -1073741802;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v1);
            }
            return v5;
          }
          EcpContext = 0;
          if ( !FsRtlRemoveExtraCreateParameter(ExtraCreateParameter, &DFSC_DFS_SHARE_CHECK_ECP_GUID, &EcpContext, 0) )
            FsRtlFreeExtraCreateParameter(EcpContext);
        }
      }
    }
    return (unsigned int)-1073741802;
  }
  if ( MajorFunction == 2 )
  {
    DfscSurrogateClose();
    return 3221225494LL;
  }
  else
  {
    if ( MajorFunction == 19 )
      goto LABEL_2;
    return 3221225494LL;
  }
}

```

## disassembly

```asm
0x140021140  push    rbx
0x140021142  push    rsi
0x140021143  push    rdi
0x140021144  sub     rsp, 20h
0x140021148  mov     rbx, [rcx]
0x14002114b  mov     rdi, rcx
0x14002114e  mov     rsi, [rbx+0B8h]
0x140021155  movzx   eax, byte ptr [rsi]
0x140021158  cmp     al, 1
0x14002115a  jnz     loc_140021213
0x140021160  mov     [rsp+38h+arg_10], rbp
0x140021165  lea     rdx, [rsp+38h+ExtraCreateParameter]; ExtraCreateParameter
0x14002116a  xor     ebp, ebp
0x14002116c  mov     rcx, rbx; Irp
0x14002116f  mov     [rsp+38h+ExtraCreateParameter], rbp
0x140021174  mov     [rsp+38h+EcpContext], rbp
0x140021179  call    cs:__imp_IoGetIrpExtraCreateParameter
0x140021180  nop     dword ptr [rax+rax+00h]
0x140021185  test    eax, eax
0x140021187  jnz     short loc_1400211FE
0x140021189  mov     rcx, [rsp+38h+ExtraCreateParameter]; EcpList
0x14002118e  test    rcx, rcx
0x140021191  jz      short loc_1400211FE
0x140021193  xor     r9d, r9d; EcpContextSize
0x140021196  mov     [rsp+38h+EcpContext], rbp
0x14002119b  lea     r8, [rsp+38h+EcpContext]; EcpContext
0x1400211a0  lea     rdx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x1400211a7  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1400211ae  nop     dword ptr [rax+rax+00h]
0x1400211b3  test    eax, eax
0x1400211b5  jnz     short loc_1400211FE
0x1400211b7  cmp     dword ptr [rbx+30h], 0C0000024h
0x1400211be  jz      loc_140021248
0x1400211c4  mov     rcx, [rsp+38h+ExtraCreateParameter]; EcpList
0x1400211c9  lea     r8, [rsp+38h+EcpContext]; EcpContext
0x1400211ce  xor     r9d, r9d; EcpContextSize
0x1400211d1  mov     [rsp+38h+EcpContext], rbp
0x1400211d6  lea     rdx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x1400211dd  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x1400211e4  nop     dword ptr [rax+rax+00h]
0x1400211e9  test    eax, eax
0x1400211eb  jnz     short loc_1400211FE
0x1400211ed  mov     rcx, [rsp+38h+EcpContext]; EcpContext
0x1400211f2  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400211f9  nop     dword ptr [rax+rax+00h]
0x1400211fe  mov     edi, 0C0000016h
0x140021203  mov     rbp, [rsp+38h+arg_10]
0x140021208  mov     eax, edi
0x14002120a  add     rsp, 20h
0x14002120e  pop     rdi
0x14002120f  pop     rsi
0x140021210  pop     rbx
0x140021211  retn
0x140021213  test    al, al
0x140021215  jz      loc_140021160
0x14002121b  cmp     al, 2
0x14002121d  jz      short loc_140021235
0x14002121f  cmp     al, 13h
0x140021221  jz      loc_140021160
0x140021227  mov     eax, 0C0000016h
0x14002122c  add     rsp, 20h
0x140021230  pop     rdi
0x140021231  pop     rsi
0x140021232  pop     rbx
0x140021233  retn
0x140021235  call    DfscSurrogateClose
0x14002123a  mov     eax, 0C0000016h
0x14002123f  add     rsp, 20h
0x140021243  pop     rdi
0x140021244  pop     rsi
0x140021245  pop     rbx
0x140021246  retn
0x140021248  mov     rdx, [rsi+30h]
0x14002124c  mov     rcx, rdi
0x14002124f  add     rdx, 58h ; 'X'
0x140021253  call    cs:__imp_MupSurrogatePurgeNegativeCacheEntry
0x14002125a  nop     dword ptr [rax+rax+00h]
0x14002125f  mov     rcx, rbx
0x140021262  call    DfscRestartCreateViaReparse
0x140021267  mov     edi, eax
0x140021269  cmp     eax, 104h
0x14002126e  jz      short loc_1400212AF
0x140021270  mov     rcx, [rsp+38h+ExtraCreateParameter]; EcpList
0x140021275  lea     r8, [rsp+38h+EcpContext]; EcpContext
0x14002127a  xor     r9d, r9d; EcpContextSize
0x14002127d  mov     [rsp+38h+EcpContext], rbp
0x140021282  lea     rdx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x140021289  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x140021290  nop     dword ptr [rax+rax+00h]
0x140021295  test    eax, eax
0x140021297  jnz     short loc_1400212AA
0x140021299  mov     rcx, [rsp+38h+EcpContext]; EcpContext
0x14002129e  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400212a5  nop     dword ptr [rax+rax+00h]
0x1400212aa  mov     edi, 0C0000016h
0x1400212af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212b6  lea     rax, WPP_GLOBAL_Control
0x1400212bd  cmp     rcx, rax
0x1400212c0  jz      loc_140021203
0x1400212c6  test    dword ptr [rcx+2Ch], 400000h
0x1400212cd  jz      loc_140021203
0x1400212d3  mov     rcx, [rcx+18h]
0x1400212d7  lea     r8, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids
0x1400212de  mov     edx, 16h
0x1400212e3  mov     r9, rbx
0x1400212e6  call    WPP_SF_q
0x1400212eb  jmp     loc_140021203
```
