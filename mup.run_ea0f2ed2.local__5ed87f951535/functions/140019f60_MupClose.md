# MupClose

- ea: `0x140019f60`
- end: `0x14001a0cf`
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
- `0x1400122a0`
- `0x140019f60`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001bb60`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001a07d`
- `ntoskrnl!KeBugCheckEx` at `0x14001a07d`
- `ntoskrnl!IofCompleteRequest` at `0x14001a05a`
- `ntoskrnl!IofCompleteRequest` at `0x14001a05a`

## pseudocode

```c
__int64 __fastcall MupClose(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG_PTR FileObject; // rsi
  ULONG_PTR FileContext; // rbx
  __int64 SiloFromFileObject; // rax
  unsigned int v8; // ebx
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, FileObject);
  }
  FileContext = MupFindFileContext(FileObject);
  if ( FileContext )
  {
    SiloFromFileObject = MupGetSiloFromFileObject(BugCheckParameter2->Tail.Overlay.CurrentStackLocation->FileObject);
    MupGetContainerContextFromSilo(SiloFromFileObject, &v10);
    MupCreateIrpContext(FileContext, v10, (ULONG_PTR)BugCheckParameter2, 1, (__int64 **)&P);
    v8 = MupStateMachine(P);
  }
  else
  {
    if ( *(FSRTL_ADVANCED_FCB_HEADER **)(FileObject + 24) != &g_MupAdvancedFcbHeader )
      KeBugCheckEx(0x103u, 1u, (ULONG_PTR)BugCheckParameter2, FileObject, BugCheckParameter4);
    MupiUpdateMupDeviceOpenCount(0);
    if ( *(_QWORD *)(FileObject + 32) )
      MupDeregisterUncProvider();
    BugCheckParameter2->IoStatus.Status = 0;
    v8 = 0;
    IofCompleteRequest(BugCheckParameter2, 2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, FileObject, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140019f60  mov     [rsp+arg_0], rbx
0x140019f65  push    rbp
0x140019f66  push    rsi
0x140019f67  push    rdi
0x140019f68  push    r14
0x140019f6a  push    r15
0x140019f6c  sub     rsp, 30h
0x140019f70  mov     rax, [rdx+0B8h]
0x140019f77  xor     r15d, r15d
0x140019f7a  mov     rdi, rdx
0x140019f7d  mov     [rsp+58h+P], r15
0x140019f82  mov     rbp, rcx
0x140019f85  mov     rsi, [rax+30h]
0x140019f89  mov     [rsp+58h+arg_8], r15
0x140019f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f95  lea     r14, WPP_GLOBAL_Control
0x140019f9c  cmp     rcx, r14
0x140019f9f  jz      short loc_140019FAE
0x140019fa1  test    dword ptr [rcx+2Ch], 2000000h
0x140019fa8  jnz     loc_14001A08A
0x140019fae  mov     rcx, rsi
0x140019fb1  call    MupFindFileContext
0x140019fb6  mov     rbx, rax
0x140019fb9  test    rax, rax
0x140019fbc  jz      short loc_14001A031
0x140019fbe  mov     rcx, [rdi+0B8h]
0x140019fc5  mov     rcx, [rcx+30h]
0x140019fc9  call    MupGetSiloFromFileObject
0x140019fce  mov     rcx, rax
0x140019fd1  lea     rdx, [rsp+58h+arg_8]
0x140019fd6  call    MupGetContainerContextFromSilo
0x140019fdb  mov     rdx, [rsp+58h+arg_8]
0x140019fe0  lea     rax, [rsp+58h+P]
0x140019fe5  mov     r9b, 1
0x140019fe8  mov     [rsp+58h+BugCheckParameter4], rax; __int64
0x140019fed  mov     r8, rdi
0x140019ff0  mov     rcx, rbx; BugCheckParameter4
0x140019ff3  call    MupCreateIrpContext
0x140019ff8  mov     rcx, [rsp+58h+P]; P
0x140019ffd  call    MupStateMachine
0x14001a002  mov     ebx, eax
0x14001a004  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a00b  cmp     rcx, r14
0x14001a00e  jz      short loc_14001A01D
0x14001a010  test    dword ptr [rcx+2Ch], 2000000h
0x14001a017  jnz     loc_14001A0AE
0x14001a01d  mov     eax, ebx
0x14001a01f  mov     rbx, [rsp+58h+arg_0]
0x14001a024  add     rsp, 30h
0x14001a028  pop     r15
0x14001a02a  pop     r14
0x14001a02c  pop     rdi
0x14001a02d  pop     rsi
0x14001a02e  pop     rbp
0x14001a02f  retn
0x14001a031  lea     rax, g_MupAdvancedFcbHeader
0x14001a038  cmp     [rsi+18h], rax
0x14001a03c  jnz     short loc_14001A068
0x14001a03e  xor     ecx, ecx
0x14001a040  call    MupiUpdateMupDeviceOpenCount
0x14001a045  mov     rcx, [rsi+20h]
0x14001a049  test    rcx, rcx
0x14001a04c  jnz     short loc_14001A0A7
0x14001a04e  mov     dl, 2; PriorityBoost
0x14001a050  mov     [rdi+30h], r15d
0x14001a054  mov     rcx, rdi; Irp
0x14001a057  mov     ebx, r15d
0x14001a05a  call    cs:__imp_IofCompleteRequest
0x14001a061  nop     dword ptr [rax+rax+00h]
0x14001a066  jmp     short loc_14001A004
0x14001a068  mov     r9, rsi; BugCheckParameter3
0x14001a06b  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x14001a070  mov     r8, rdi; BugCheckParameter2
0x14001a073  mov     edx, 1; BugCheckParameter1
0x14001a078  mov     ecx, 103h; BugCheckCode
0x14001a07d  call    cs:__imp_KeBugCheckEx
0x14001a08a  mov     rcx, [rcx+18h]
0x14001a08e  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a095  mov     edx, 12h
0x14001a09a  mov     r9, rsi
0x14001a09d  call    WPP_SF_q
0x14001a0a2  jmp     loc_140019FAE
0x14001a0a7  call    MupDeregisterUncProvider
0x14001a0ac  jmp     short loc_14001A04E
0x14001a0ae  mov     rcx, [rcx+18h]
0x14001a0b2  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a0b9  mov     edx, 13h
0x14001a0be  mov     dword ptr [rsp+58h+BugCheckParameter4], ebx
0x14001a0c2  mov     r9, rsi
0x14001a0c5  call    WPP_SF_qD
0x14001a0ca  jmp     loc_14001A01D
```
