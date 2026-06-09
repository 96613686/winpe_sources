# MupSetInformationFile

- ea: `0x14001d040`
- end: `0x14001d258`
- name: `MupSetInformationFile`
- size: `536`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, ULONG_PTR BugCheckParameter2)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x140002700`
- `0x1400029b0`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001bbb0`
- `0x14001d040`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001d1c0`
- `ntoskrnl!KeBugCheckEx` at `0x14001d24b`
- `ntoskrnl!KeBugCheckEx` at `0x14001d1c0`
- `ntoskrnl!KeBugCheckEx` at `0x14001d24b`
- `ntoskrnl!IofCompleteRequest` at `0x14001d124`
- `ntoskrnl!IofCompleteRequest` at `0x14001d124`

## pseudocode

```c
__int64 __fastcall MupSetInformationFile(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  ULONG_PTR FileObject; // rsi
  ULONG_PTR FileContext; // rbp
  ULONG Options; // ecx
  __int64 SiloFromFileObject; // rax
  unsigned int ContainerContextFromSilo; // eax
  unsigned int IrpContext; // ebx
  unsigned __int64 v11; // rdx
  ULONG_PTR QuadPart; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  v17 = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      FileObject,
      BugCheckParameter2);
  }
  FileContext = MupFindFileContext(FileObject);
  if ( !FileContext )
  {
    if ( *(FSRTL_ADVANCED_FCB_HEADER **)(FileObject + 24) != &g_MupAdvancedFcbHeader )
      KeBugCheckEx(0x103u, 1u, (ULONG_PTR)BugCheckParameter2, FileObject, BugCheckParameter4);
    goto LABEL_9;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options - 10 > 1 && Options != 31 )
    goto LABEL_5;
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  if ( !QuadPart )
    goto LABEL_5;
  v14 = MupFindFileContext(QuadPart);
  if ( !v14 )
  {
    if ( *(FSRTL_ADVANCED_FCB_HEADER **)(QuadPart + 24) != &g_MupAdvancedFcbHeader )
      KeBugCheckEx(0x103u, 1u, (ULONG_PTR)BugCheckParameter2, QuadPart, BugCheckParameter4);
LABEL_9:
    IrpContext = -1073741808;
LABEL_10:
    BugCheckParameter2->IoStatus.Status = IrpContext;
    IofCompleteRequest(BugCheckParameter2, 2);
    goto LABEL_11;
  }
  v15 = *(_QWORD *)(FileContext + 168);
  if ( v15 )
  {
    v16 = *(_QWORD *)(v14 + 168);
    if ( v16 )
    {
      if ( *(_QWORD *)(v15 + 168) != *(_QWORD *)(v16 + 168) )
      {
        IrpContext = -1073741612;
        goto LABEL_10;
      }
    }
  }
LABEL_5:
  SiloFromFileObject = MupGetSiloFromFileObject(BugCheckParameter2->Tail.Overlay.CurrentStackLocation->FileObject);
  ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v17);
  P = 0;
  IrpContext = ContainerContextFromSilo;
  if ( ContainerContextFromSilo )
    goto LABEL_10;
  IrpContext = MupCreateIrpContext(FileContext, v17, (ULONG_PTR)BugCheckParameter2, 0, (__int64 **)&P);
  if ( IrpContext )
    goto LABEL_10;
  IrpContext = MupStateMachine((unsigned __int64)P, v11);
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      FileObject,
      BugCheckParameter2,
      IrpContext);
  }
  return IrpContext;
}

```

## disassembly

```asm
0x14001d040  mov     [rsp+arg_0], rbx
0x14001d045  push    rbp
0x14001d046  push    rsi
0x14001d047  push    rdi
0x14001d048  push    r12
0x14001d04a  push    r14
0x14001d04c  sub     rsp, 30h
0x14001d050  mov     rbx, [rdx+0B8h]
0x14001d057  mov     rdi, rdx
0x14001d05a  mov     [rsp+58h+arg_8], 0
0x14001d063  mov     r14, rcx
0x14001d066  mov     rsi, [rbx+30h]
0x14001d06a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d071  lea     r12, WPP_GLOBAL_Control
0x14001d078  cmp     rcx, r12
0x14001d07b  jnz     loc_14001D150
0x14001d081  mov     rcx, rsi
0x14001d084  call    MupFindFileContext
0x14001d089  mov     rbp, rax
0x14001d08c  test    rax, rax
0x14001d08f  jz      short loc_14001D106
0x14001d091  mov     ecx, [rbx+10h]
0x14001d094  lea     eax, [rcx-0Ah]
0x14001d097  cmp     eax, 1
0x14001d09a  jbe     loc_14001D1CD
0x14001d0a0  cmp     ecx, 1Fh
0x14001d0a3  jz      loc_14001D1CD
0x14001d0a9  mov     rcx, [rdi+0B8h]
0x14001d0b0  mov     rcx, [rcx+30h]
0x14001d0b4  call    MupGetSiloFromFileObject
0x14001d0b9  mov     rcx, rax
0x14001d0bc  lea     rdx, [rsp+58h+arg_8]
0x14001d0c1  call    MupGetContainerContextFromSilo
0x14001d0c6  mov     [rsp+58h+P], 0
0x14001d0cf  mov     ebx, eax
0x14001d0d1  test    eax, eax
0x14001d0d3  jnz     short loc_14001D11C
0x14001d0d5  mov     rdx, [rsp+58h+arg_8]
0x14001d0da  lea     rax, [rsp+58h+P]
0x14001d0df  xor     r9d, r9d
0x14001d0e2  mov     [rsp+58h+BugCheckParameter4], rax; __int64
0x14001d0e7  mov     r8, rdi
0x14001d0ea  mov     rcx, rbp; BugCheckParameter4
0x14001d0ed  call    MupCreateIrpContext
0x14001d0f2  mov     ebx, eax
0x14001d0f4  test    eax, eax
0x14001d0f6  jnz     short loc_14001D11C
0x14001d0f8  mov     rcx, [rsp+58h+P]; P
0x14001d0fd  call    MupStateMachine
0x14001d102  mov     ebx, eax
0x14001d104  jmp     short loc_14001D130
0x14001d106  lea     rax, g_MupAdvancedFcbHeader
0x14001d10d  cmp     [rsi+18h], rax
0x14001d111  jnz     loc_14001D1AB
0x14001d117  mov     ebx, 0C0000010h
0x14001d11c  mov     dl, 2; PriorityBoost
0x14001d11e  mov     [rdi+30h], ebx
0x14001d121  mov     rcx, rdi; Irp
0x14001d124  call    cs:__imp_IofCompleteRequest
0x14001d12b  nop     dword ptr [rax+rax+00h]
0x14001d130  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d137  cmp     rcx, r12
0x14001d13a  jnz     short loc_14001D17F
0x14001d13c  mov     eax, ebx
0x14001d13e  mov     rbx, [rsp+58h+arg_0]
0x14001d143  add     rsp, 30h
0x14001d147  pop     r14
0x14001d149  pop     r12
0x14001d14b  pop     rdi
0x14001d14c  pop     rsi
0x14001d14d  pop     rbp
0x14001d14e  retn
0x14001d150  test    dword ptr [rcx+2Ch], 4000000h
0x14001d157  jz      loc_14001D081
0x14001d15d  mov     rcx, [rcx+18h]
0x14001d161  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001d168  mov     edx, 0Ch
0x14001d16d  mov     [rsp+58h+BugCheckParameter4], rdi
0x14001d172  mov     r9, rsi
0x14001d175  call    WPP_SF_qq
0x14001d17a  jmp     loc_14001D081
0x14001d17f  test    dword ptr [rcx+2Ch], 4000000h
0x14001d186  jz      short loc_14001D13C
0x14001d188  mov     rcx, [rcx+18h]
0x14001d18c  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001d193  mov     edx, 0Dh
0x14001d198  mov     [rsp+58h+var_30], ebx
0x14001d19c  mov     r9, rsi
0x14001d19f  mov     [rsp+58h+BugCheckParameter4], rdi
0x14001d1a4  call    WPP_SF_qqD
0x14001d1a9  jmp     short loc_14001D13C
0x14001d1ab  mov     r9, rsi; BugCheckParameter3
0x14001d1ae  mov     [rsp+58h+BugCheckParameter4], r14; BugCheckParameter4
0x14001d1b3  mov     r8, rdi; BugCheckParameter2
0x14001d1b6  mov     edx, 1; BugCheckParameter1
0x14001d1bb  mov     ecx, 103h; BugCheckCode
0x14001d1c0  call    cs:__imp_KeBugCheckEx
0x14001d1cd  mov     rbx, [rbx+18h]
0x14001d1d1  test    rbx, rbx
0x14001d1d4  jz      loc_14001D0A9
0x14001d1da  mov     rcx, rbx
0x14001d1dd  call    MupFindFileContext
0x14001d1e2  test    rax, rax
0x14001d1e5  jz      short loc_14001D225
0x14001d1e7  mov     rcx, [rbp+0A8h]
0x14001d1ee  test    rcx, rcx
0x14001d1f1  jz      loc_14001D0A9
0x14001d1f7  mov     rax, [rax+0A8h]
0x14001d1fe  test    rax, rax
0x14001d201  jz      loc_14001D0A9
0x14001d207  mov     rax, [rax+0A8h]
0x14001d20e  cmp     [rcx+0A8h], rax
0x14001d215  jz      loc_14001D0A9
0x14001d21b  mov     ebx, 0C00000D4h
0x14001d220  jmp     loc_14001D11C
0x14001d225  lea     rax, g_MupAdvancedFcbHeader
0x14001d22c  cmp     [rbx+18h], rax
0x14001d230  jz      loc_14001D117
0x14001d236  mov     r9, rbx; BugCheckParameter3
0x14001d239  mov     [rsp+58h+BugCheckParameter4], r14; BugCheckParameter4
0x14001d23e  mov     r8, rdi; BugCheckParameter2
0x14001d241  mov     edx, 1; BugCheckParameter1
0x14001d246  mov     ecx, 103h; BugCheckCode
0x14001d24b  call    cs:__imp_KeBugCheckEx
```
