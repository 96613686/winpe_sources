# MupSetInformationFile

- ea: `0x14001cff0`
- end: `0x14001d208`
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
- `0x14001ba90`
- `0x14001bb30`
- `0x14001bb60`
- `0x14001cff0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001d170`
- `ntoskrnl!KeBugCheckEx` at `0x14001d1fb`
- `ntoskrnl!KeBugCheckEx` at `0x14001d170`
- `ntoskrnl!KeBugCheckEx` at `0x14001d1fb`
- `ntoskrnl!IofCompleteRequest` at `0x14001d0d4`
- `ntoskrnl!IofCompleteRequest` at `0x14001d0d4`

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
  ULONG_PTR QuadPart; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  v16 = 0;
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
  v13 = MupFindFileContext(QuadPart);
  if ( !v13 )
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
  v14 = *(_QWORD *)(FileContext + 168);
  if ( v14 )
  {
    v15 = *(_QWORD *)(v13 + 168);
    if ( v15 )
    {
      if ( *(_QWORD *)(v14 + 168) != *(_QWORD *)(v15 + 168) )
      {
        IrpContext = -1073741612;
        goto LABEL_10;
      }
    }
  }
LABEL_5:
  SiloFromFileObject = MupGetSiloFromFileObject(BugCheckParameter2->Tail.Overlay.CurrentStackLocation->FileObject);
  ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v16);
  P = 0;
  IrpContext = ContainerContextFromSilo;
  if ( ContainerContextFromSilo )
    goto LABEL_10;
  IrpContext = MupCreateIrpContext(FileContext, v16, (ULONG_PTR)BugCheckParameter2, 0, (__int64 **)&P);
  if ( IrpContext )
    goto LABEL_10;
  IrpContext = MupStateMachine(P);
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
0x14001cff0  mov     [rsp+arg_0], rbx
0x14001cff5  push    rbp
0x14001cff6  push    rsi
0x14001cff7  push    rdi
0x14001cff8  push    r12
0x14001cffa  push    r14
0x14001cffc  sub     rsp, 30h
0x14001d000  mov     rbx, [rdx+0B8h]
0x14001d007  mov     rdi, rdx
0x14001d00a  mov     [rsp+58h+arg_8], 0
0x14001d013  mov     r14, rcx
0x14001d016  mov     rsi, [rbx+30h]
0x14001d01a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d021  lea     r12, WPP_GLOBAL_Control
0x14001d028  cmp     rcx, r12
0x14001d02b  jnz     loc_14001D100
0x14001d031  mov     rcx, rsi
0x14001d034  call    MupFindFileContext
0x14001d039  mov     rbp, rax
0x14001d03c  test    rax, rax
0x14001d03f  jz      short loc_14001D0B6
0x14001d041  mov     ecx, [rbx+10h]
0x14001d044  lea     eax, [rcx-0Ah]
0x14001d047  cmp     eax, 1
0x14001d04a  jbe     loc_14001D17D
0x14001d050  cmp     ecx, 1Fh
0x14001d053  jz      loc_14001D17D
0x14001d059  mov     rcx, [rdi+0B8h]
0x14001d060  mov     rcx, [rcx+30h]
0x14001d064  call    MupGetSiloFromFileObject
0x14001d069  mov     rcx, rax
0x14001d06c  lea     rdx, [rsp+58h+arg_8]
0x14001d071  call    MupGetContainerContextFromSilo
0x14001d076  mov     [rsp+58h+P], 0
0x14001d07f  mov     ebx, eax
0x14001d081  test    eax, eax
0x14001d083  jnz     short loc_14001D0CC
0x14001d085  mov     rdx, [rsp+58h+arg_8]
0x14001d08a  lea     rax, [rsp+58h+P]
0x14001d08f  xor     r9d, r9d
0x14001d092  mov     [rsp+58h+BugCheckParameter4], rax; __int64
0x14001d097  mov     r8, rdi
0x14001d09a  mov     rcx, rbp; BugCheckParameter4
0x14001d09d  call    MupCreateIrpContext
0x14001d0a2  mov     ebx, eax
0x14001d0a4  test    eax, eax
0x14001d0a6  jnz     short loc_14001D0CC
0x14001d0a8  mov     rcx, [rsp+58h+P]; P
0x14001d0ad  call    MupStateMachine
0x14001d0b2  mov     ebx, eax
0x14001d0b4  jmp     short loc_14001D0E0
0x14001d0b6  lea     rax, g_MupAdvancedFcbHeader
0x14001d0bd  cmp     [rsi+18h], rax
0x14001d0c1  jnz     loc_14001D15B
0x14001d0c7  mov     ebx, 0C0000010h
0x14001d0cc  mov     dl, 2; PriorityBoost
0x14001d0ce  mov     [rdi+30h], ebx
0x14001d0d1  mov     rcx, rdi; Irp
0x14001d0d4  call    cs:__imp_IofCompleteRequest
0x14001d0db  nop     dword ptr [rax+rax+00h]
0x14001d0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0e7  cmp     rcx, r12
0x14001d0ea  jnz     short loc_14001D12F
0x14001d0ec  mov     eax, ebx
0x14001d0ee  mov     rbx, [rsp+58h+arg_0]
0x14001d0f3  add     rsp, 30h
0x14001d0f7  pop     r14
0x14001d0f9  pop     r12
0x14001d0fb  pop     rdi
0x14001d0fc  pop     rsi
0x14001d0fd  pop     rbp
0x14001d0fe  retn
0x14001d100  test    dword ptr [rcx+2Ch], 4000000h
0x14001d107  jz      loc_14001D031
0x14001d10d  mov     rcx, [rcx+18h]
0x14001d111  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001d118  mov     edx, 0Ch
0x14001d11d  mov     [rsp+58h+BugCheckParameter4], rdi
0x14001d122  mov     r9, rsi
0x14001d125  call    WPP_SF_qq
0x14001d12a  jmp     loc_14001D031
0x14001d12f  test    dword ptr [rcx+2Ch], 4000000h
0x14001d136  jz      short loc_14001D0EC
0x14001d138  mov     rcx, [rcx+18h]
0x14001d13c  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001d143  mov     edx, 0Dh
0x14001d148  mov     [rsp+58h+var_30], ebx
0x14001d14c  mov     r9, rsi
0x14001d14f  mov     [rsp+58h+BugCheckParameter4], rdi
0x14001d154  call    WPP_SF_qqD
0x14001d159  jmp     short loc_14001D0EC
0x14001d15b  mov     r9, rsi; BugCheckParameter3
0x14001d15e  mov     [rsp+58h+BugCheckParameter4], r14; BugCheckParameter4
0x14001d163  mov     r8, rdi; BugCheckParameter2
0x14001d166  mov     edx, 1; BugCheckParameter1
0x14001d16b  mov     ecx, 103h; BugCheckCode
0x14001d170  call    cs:__imp_KeBugCheckEx
0x14001d17d  mov     rbx, [rbx+18h]
0x14001d181  test    rbx, rbx
0x14001d184  jz      loc_14001D059
0x14001d18a  mov     rcx, rbx
0x14001d18d  call    MupFindFileContext
0x14001d192  test    rax, rax
0x14001d195  jz      short loc_14001D1D5
0x14001d197  mov     rcx, [rbp+0A8h]
0x14001d19e  test    rcx, rcx
0x14001d1a1  jz      loc_14001D059
0x14001d1a7  mov     rax, [rax+0A8h]
0x14001d1ae  test    rax, rax
0x14001d1b1  jz      loc_14001D059
0x14001d1b7  mov     rax, [rax+0A8h]
0x14001d1be  cmp     [rcx+0A8h], rax
0x14001d1c5  jz      loc_14001D059
0x14001d1cb  mov     ebx, 0C00000D4h
0x14001d1d0  jmp     loc_14001D0CC
0x14001d1d5  lea     rax, g_MupAdvancedFcbHeader
0x14001d1dc  cmp     [rbx+18h], rax
0x14001d1e0  jz      loc_14001D0C7
0x14001d1e6  mov     r9, rbx; BugCheckParameter3
0x14001d1e9  mov     [rsp+58h+BugCheckParameter4], r14; BugCheckParameter4
0x14001d1ee  mov     r8, rdi; BugCheckParameter2
0x14001d1f1  mov     edx, 1; BugCheckParameter1
0x14001d1f6  mov     ecx, 103h; BugCheckCode
0x14001d1fb  call    cs:__imp_KeBugCheckEx
```
