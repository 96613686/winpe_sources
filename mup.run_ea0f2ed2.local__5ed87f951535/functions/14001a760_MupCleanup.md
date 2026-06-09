# MupCleanup

- ea: `0x14001a760`
- end: `0x14001a8ca`
- name: `MupCleanup`
- size: `362`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, ULONG_PTR BugCheckParameter2)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x140002700`
- `0x1400029b0`
- `0x14001a760`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001bb60`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001a897`
- `ntoskrnl!KeBugCheckEx` at `0x14001a897`
- `ntoskrnl!IofCompleteRequest` at `0x14001a852`
- `ntoskrnl!IofCompleteRequest` at `0x14001a852`

## pseudocode

```c
__int64 __fastcall MupCleanup(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG_PTR FileObject; // rbp
  ULONG_PTR FileContext; // rdi
  __int64 SiloFromFileObject; // rax
  unsigned int ContainerContextFromSilo; // ebx
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      FileObject,
      BugCheckParameter2);
  }
  FileContext = MupFindFileContext(FileObject);
  if ( FileContext )
  {
    SiloFromFileObject = MupGetSiloFromFileObject(BugCheckParameter2->Tail.Overlay.CurrentStackLocation->FileObject);
    ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v10);
    if ( !ContainerContextFromSilo )
    {
      ContainerContextFromSilo = MupCreateIrpContext(FileContext, v10, (ULONG_PTR)BugCheckParameter2, 1, (__int64 **)&P);
      if ( !ContainerContextFromSilo )
        ContainerContextFromSilo = MupStateMachine(P);
    }
  }
  else
  {
    if ( *(FSRTL_ADVANCED_FCB_HEADER **)(FileObject + 24) != &g_MupAdvancedFcbHeader )
      KeBugCheckEx(0x103u, 1u, (ULONG_PTR)BugCheckParameter2, FileObject, BugCheckParameter4);
    BugCheckParameter2->IoStatus.Status = 0;
    ContainerContextFromSilo = 0;
    IofCompleteRequest(BugCheckParameter2, 2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      FileObject,
      BugCheckParameter2,
      ContainerContextFromSilo);
  }
  return ContainerContextFromSilo;
}

```

## disassembly

```asm
0x14001a760  mov     [rsp+arg_0], rbx
0x14001a765  push    rbp
0x14001a766  push    rsi
0x14001a767  push    rdi
0x14001a768  push    r14
0x14001a76a  push    r15
0x14001a76c  sub     rsp, 30h
0x14001a770  mov     rax, [rdx+0B8h]
0x14001a777  xor     r15d, r15d
0x14001a77a  mov     rsi, rdx
0x14001a77d  mov     [rsp+58h+P], r15
0x14001a782  mov     rbx, rcx
0x14001a785  mov     rbp, [rax+30h]
0x14001a789  mov     [rsp+58h+arg_8], r15
0x14001a78e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a795  lea     r14, WPP_GLOBAL_Control
0x14001a79c  cmp     rcx, r14
0x14001a79f  jz      short loc_14001A7AE
0x14001a7a1  test    dword ptr [rcx+2Ch], 2000000h
0x14001a7a8  jnz     loc_14001A860
0x14001a7ae  mov     rcx, rbp
0x14001a7b1  call    MupFindFileContext
0x14001a7b6  mov     rdi, rax
0x14001a7b9  test    rax, rax
0x14001a7bc  jz      short loc_14001A839
0x14001a7be  mov     rcx, [rsi+0B8h]
0x14001a7c5  mov     rcx, [rcx+30h]
0x14001a7c9  call    MupGetSiloFromFileObject
0x14001a7ce  mov     rcx, rax
0x14001a7d1  lea     rdx, [rsp+58h+arg_8]
0x14001a7d6  call    MupGetContainerContextFromSilo
0x14001a7db  mov     ebx, eax
0x14001a7dd  test    eax, eax
0x14001a7df  jnz     short loc_14001A810
0x14001a7e1  mov     rdx, [rsp+58h+arg_8]
0x14001a7e6  lea     rax, [rsp+58h+P]
0x14001a7eb  mov     r9b, 1
0x14001a7ee  mov     [rsp+58h+BugCheckParameter4], rax; __int64
0x14001a7f3  mov     r8, rsi
0x14001a7f6  mov     rcx, rdi; BugCheckParameter4
0x14001a7f9  call    MupCreateIrpContext
0x14001a7fe  mov     ebx, eax
0x14001a800  test    eax, eax
0x14001a802  jnz     short loc_14001A810
0x14001a804  mov     rcx, [rsp+58h+P]; P
0x14001a809  call    MupStateMachine
0x14001a80e  mov     ebx, eax
0x14001a810  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a817  cmp     rcx, r14
0x14001a81a  jz      short loc_14001A825
0x14001a81c  test    dword ptr [rcx+2Ch], 2000000h
0x14001a823  jnz     short loc_14001A8A4
0x14001a825  mov     eax, ebx
0x14001a827  mov     rbx, [rsp+58h+arg_0]
0x14001a82c  add     rsp, 30h
0x14001a830  pop     r15
0x14001a832  pop     r14
0x14001a834  pop     rdi
0x14001a835  pop     rsi
0x14001a836  pop     rbp
0x14001a837  retn
0x14001a839  lea     rax, g_MupAdvancedFcbHeader
0x14001a840  cmp     [rbp+18h], rax
0x14001a844  jnz     short loc_14001A882
0x14001a846  mov     dl, 2; PriorityBoost
0x14001a848  mov     [rsi+30h], r15d
0x14001a84c  mov     rcx, rsi; Irp
0x14001a84f  mov     ebx, r15d
0x14001a852  call    cs:__imp_IofCompleteRequest
0x14001a859  nop     dword ptr [rax+rax+00h]
0x14001a85e  jmp     short loc_14001A810
0x14001a860  mov     rcx, [rcx+18h]
0x14001a864  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a86b  mov     edx, 10h
0x14001a870  mov     [rsp+58h+BugCheckParameter4], rsi
0x14001a875  mov     r9, rbp
0x14001a878  call    WPP_SF_qq
0x14001a87d  jmp     loc_14001A7AE
0x14001a882  mov     r9, rbp; BugCheckParameter3
0x14001a885  mov     [rsp+58h+BugCheckParameter4], rbx; BugCheckParameter4
0x14001a88a  mov     r8, rsi; BugCheckParameter2
0x14001a88d  mov     edx, 1; BugCheckParameter1
0x14001a892  mov     ecx, 103h; BugCheckCode
0x14001a897  call    cs:__imp_KeBugCheckEx
0x14001a8a4  mov     rcx, [rcx+18h]
0x14001a8a8  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a8af  mov     edx, 11h
0x14001a8b4  mov     [rsp+58h+var_30], ebx
0x14001a8b8  mov     r9, rbp
0x14001a8bb  mov     [rsp+58h+BugCheckParameter4], rsi
0x14001a8c0  call    WPP_SF_qqD
0x14001a8c5  jmp     loc_14001A825
```
