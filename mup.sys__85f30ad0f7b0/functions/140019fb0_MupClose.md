# MupClose

- ea: `0x140019fb0`
- end: `0x14001a11f`
- name: `MupClose`
- size: `367`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, ULONG_PTR BugCheckParameter2)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x1400025ac`
- `0x140002614`
- `0x140002754`
- `0x1400122f0`
- `0x140019fb0`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001bbb0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001a0cd`
- `ntoskrnl!KeBugCheckEx` at `0x14001a0cd`
- `ntoskrnl!IofCompleteRequest` at `0x14001a0aa`
- `ntoskrnl!IofCompleteRequest` at `0x14001a0aa`

## pseudocode

```c
__int64 __fastcall MupClose(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG_PTR FileObject; // rsi
  ULONG_PTR FileContext; // rbx
  __int64 SiloFromFileObject; // rax
  unsigned __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, FileObject);
  }
  FileContext = MupFindFileContext(FileObject);
  if ( FileContext )
  {
    SiloFromFileObject = MupGetSiloFromFileObject(BugCheckParameter2->Tail.Overlay.CurrentStackLocation->FileObject);
    MupGetContainerContextFromSilo(SiloFromFileObject, &v11);
    MupCreateIrpContext(FileContext, v11, (ULONG_PTR)BugCheckParameter2, 1, (__int64 **)&P);
    v9 = MupStateMachine((unsigned __int64)P, v8);
  }
  else
  {
    if ( *(FSRTL_ADVANCED_FCB_HEADER **)(FileObject + 24) != &g_MupAdvancedFcbHeader )
      KeBugCheckEx(0x103u, 1u, (ULONG_PTR)BugCheckParameter2, FileObject, BugCheckParameter4);
    MupiUpdateMupDeviceOpenCount(0);
    if ( *(_QWORD *)(FileObject + 32) )
      MupDeregisterUncProvider();
    BugCheckParameter2->IoStatus.Status = 0;
    v9 = 0;
    IofCompleteRequest(BugCheckParameter2, 2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, FileObject, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140019fb0  mov     [rsp+arg_0], rbx
0x140019fb5  push    rbp
0x140019fb6  push    rsi
0x140019fb7  push    rdi
0x140019fb8  push    r14
0x140019fba  push    r15
0x140019fbc  sub     rsp, 30h
0x140019fc0  mov     rax, [rdx+0B8h]
0x140019fc7  xor     r15d, r15d
0x140019fca  mov     rdi, rdx
0x140019fcd  mov     [rsp+58h+P], r15
0x140019fd2  mov     rbp, rcx
0x140019fd5  mov     rsi, [rax+30h]
0x140019fd9  mov     [rsp+58h+arg_8], r15
0x140019fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140019fe5  lea     r14, WPP_GLOBAL_Control
0x140019fec  cmp     rcx, r14
0x140019fef  jz      short loc_140019FFE
0x140019ff1  test    dword ptr [rcx+2Ch], 2000000h
0x140019ff8  jnz     loc_14001A0DA
0x140019ffe  mov     rcx, rsi
0x14001a001  call    MupFindFileContext
0x14001a006  mov     rbx, rax
0x14001a009  test    rax, rax
0x14001a00c  jz      short loc_14001A081
0x14001a00e  mov     rcx, [rdi+0B8h]
0x14001a015  mov     rcx, [rcx+30h]
0x14001a019  call    MupGetSiloFromFileObject
0x14001a01e  mov     rcx, rax
0x14001a021  lea     rdx, [rsp+58h+arg_8]
0x14001a026  call    MupGetContainerContextFromSilo
0x14001a02b  mov     rdx, [rsp+58h+arg_8]
0x14001a030  lea     rax, [rsp+58h+P]
0x14001a035  mov     r9b, 1
0x14001a038  mov     [rsp+58h+BugCheckParameter4], rax; __int64
0x14001a03d  mov     r8, rdi
0x14001a040  mov     rcx, rbx; BugCheckParameter4
0x14001a043  call    MupCreateIrpContext
0x14001a048  mov     rcx, [rsp+58h+P]; P
0x14001a04d  call    MupStateMachine
0x14001a052  mov     ebx, eax
0x14001a054  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a05b  cmp     rcx, r14
0x14001a05e  jz      short loc_14001A06D
0x14001a060  test    dword ptr [rcx+2Ch], 2000000h
0x14001a067  jnz     loc_14001A0FE
0x14001a06d  mov     eax, ebx
0x14001a06f  mov     rbx, [rsp+58h+arg_0]
0x14001a074  add     rsp, 30h
0x14001a078  pop     r15
0x14001a07a  pop     r14
0x14001a07c  pop     rdi
0x14001a07d  pop     rsi
0x14001a07e  pop     rbp
0x14001a07f  retn
0x14001a081  lea     rax, g_MupAdvancedFcbHeader
0x14001a088  cmp     [rsi+18h], rax
0x14001a08c  jnz     short loc_14001A0B8
0x14001a08e  xor     ecx, ecx
0x14001a090  call    MupiUpdateMupDeviceOpenCount
0x14001a095  mov     rcx, [rsi+20h]
0x14001a099  test    rcx, rcx
0x14001a09c  jnz     short loc_14001A0F7
0x14001a09e  mov     dl, 2; PriorityBoost
0x14001a0a0  mov     [rdi+30h], r15d
0x14001a0a4  mov     rcx, rdi; Irp
0x14001a0a7  mov     ebx, r15d
0x14001a0aa  call    cs:__imp_IofCompleteRequest
0x14001a0b1  nop     dword ptr [rax+rax+00h]
0x14001a0b6  jmp     short loc_14001A054
0x14001a0b8  mov     r9, rsi; BugCheckParameter3
0x14001a0bb  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x14001a0c0  mov     r8, rdi; BugCheckParameter2
0x14001a0c3  mov     edx, 1; BugCheckParameter1
0x14001a0c8  mov     ecx, 103h; BugCheckCode
0x14001a0cd  call    cs:__imp_KeBugCheckEx
0x14001a0da  mov     rcx, [rcx+18h]
0x14001a0de  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a0e5  mov     edx, 12h
0x14001a0ea  mov     r9, rsi
0x14001a0ed  call    WPP_SF_q
0x14001a0f2  jmp     loc_140019FFE
0x14001a0f7  call    MupDeregisterUncProvider
0x14001a0fc  jmp     short loc_14001A09E
0x14001a0fe  mov     rcx, [rcx+18h]
0x14001a102  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a109  mov     edx, 13h
0x14001a10e  mov     dword ptr [rsp+58h+BugCheckParameter4], ebx
0x14001a112  mov     r9, rsi
0x14001a115  call    WPP_SF_qD
0x14001a11a  jmp     loc_14001A06D
```
