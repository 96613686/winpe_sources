# MupCleanup

- ea: `0x14001a7b0`
- end: `0x14001a91a`
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
- `0x14001a7b0`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001bbb0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001a8e7`
- `ntoskrnl!KeBugCheckEx` at `0x14001a8e7`
- `ntoskrnl!IofCompleteRequest` at `0x14001a8a2`
- `ntoskrnl!IofCompleteRequest` at `0x14001a8a2`

## pseudocode

```c
__int64 __fastcall MupCleanup(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG_PTR FileObject; // rbp
  ULONG_PTR FileContext; // rdi
  __int64 SiloFromFileObject; // rax
  unsigned int ContainerContextFromSilo; // ebx
  unsigned __int64 v9; // rdx
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  v11 = 0;
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
    ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v11);
    if ( !ContainerContextFromSilo )
    {
      ContainerContextFromSilo = MupCreateIrpContext(FileContext, v11, (ULONG_PTR)BugCheckParameter2, 1, (__int64 **)&P);
      if ( !ContainerContextFromSilo )
        ContainerContextFromSilo = MupStateMachine((unsigned __int64)P, v9);
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
0x14001a7b0  mov     [rsp+arg_0], rbx
0x14001a7b5  push    rbp
0x14001a7b6  push    rsi
0x14001a7b7  push    rdi
0x14001a7b8  push    r14
0x14001a7ba  push    r15
0x14001a7bc  sub     rsp, 30h
0x14001a7c0  mov     rax, [rdx+0B8h]
0x14001a7c7  xor     r15d, r15d
0x14001a7ca  mov     rsi, rdx
0x14001a7cd  mov     [rsp+58h+P], r15
0x14001a7d2  mov     rbx, rcx
0x14001a7d5  mov     rbp, [rax+30h]
0x14001a7d9  mov     [rsp+58h+arg_8], r15
0x14001a7de  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7e5  lea     r14, WPP_GLOBAL_Control
0x14001a7ec  cmp     rcx, r14
0x14001a7ef  jz      short loc_14001A7FE
0x14001a7f1  test    dword ptr [rcx+2Ch], 2000000h
0x14001a7f8  jnz     loc_14001A8B0
0x14001a7fe  mov     rcx, rbp
0x14001a801  call    MupFindFileContext
0x14001a806  mov     rdi, rax
0x14001a809  test    rax, rax
0x14001a80c  jz      short loc_14001A889
0x14001a80e  mov     rcx, [rsi+0B8h]
0x14001a815  mov     rcx, [rcx+30h]
0x14001a819  call    MupGetSiloFromFileObject
0x14001a81e  mov     rcx, rax
0x14001a821  lea     rdx, [rsp+58h+arg_8]
0x14001a826  call    MupGetContainerContextFromSilo
0x14001a82b  mov     ebx, eax
0x14001a82d  test    eax, eax
0x14001a82f  jnz     short loc_14001A860
0x14001a831  mov     rdx, [rsp+58h+arg_8]
0x14001a836  lea     rax, [rsp+58h+P]
0x14001a83b  mov     r9b, 1
0x14001a83e  mov     [rsp+58h+BugCheckParameter4], rax; __int64
0x14001a843  mov     r8, rsi
0x14001a846  mov     rcx, rdi; BugCheckParameter4
0x14001a849  call    MupCreateIrpContext
0x14001a84e  mov     ebx, eax
0x14001a850  test    eax, eax
0x14001a852  jnz     short loc_14001A860
0x14001a854  mov     rcx, [rsp+58h+P]; P
0x14001a859  call    MupStateMachine
0x14001a85e  mov     ebx, eax
0x14001a860  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a867  cmp     rcx, r14
0x14001a86a  jz      short loc_14001A875
0x14001a86c  test    dword ptr [rcx+2Ch], 2000000h
0x14001a873  jnz     short loc_14001A8F4
0x14001a875  mov     eax, ebx
0x14001a877  mov     rbx, [rsp+58h+arg_0]
0x14001a87c  add     rsp, 30h
0x14001a880  pop     r15
0x14001a882  pop     r14
0x14001a884  pop     rdi
0x14001a885  pop     rsi
0x14001a886  pop     rbp
0x14001a887  retn
0x14001a889  lea     rax, g_MupAdvancedFcbHeader
0x14001a890  cmp     [rbp+18h], rax
0x14001a894  jnz     short loc_14001A8D2
0x14001a896  mov     dl, 2; PriorityBoost
0x14001a898  mov     [rsi+30h], r15d
0x14001a89c  mov     rcx, rsi; Irp
0x14001a89f  mov     ebx, r15d
0x14001a8a2  call    cs:__imp_IofCompleteRequest
0x14001a8a9  nop     dword ptr [rax+rax+00h]
0x14001a8ae  jmp     short loc_14001A860
0x14001a8b0  mov     rcx, [rcx+18h]
0x14001a8b4  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a8bb  mov     edx, 10h
0x14001a8c0  mov     [rsp+58h+BugCheckParameter4], rsi
0x14001a8c5  mov     r9, rbp
0x14001a8c8  call    WPP_SF_qq
0x14001a8cd  jmp     loc_14001A7FE
0x14001a8d2  mov     r9, rbp; BugCheckParameter3
0x14001a8d5  mov     [rsp+58h+BugCheckParameter4], rbx; BugCheckParameter4
0x14001a8da  mov     r8, rsi; BugCheckParameter2
0x14001a8dd  mov     edx, 1; BugCheckParameter1
0x14001a8e2  mov     ecx, 103h; BugCheckCode
0x14001a8e7  call    cs:__imp_KeBugCheckEx
0x14001a8f4  mov     rcx, [rcx+18h]
0x14001a8f8  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a8ff  mov     edx, 11h
0x14001a904  mov     [rsp+58h+var_30], ebx
0x14001a908  mov     r9, rbp
0x14001a90b  mov     [rsp+58h+BugCheckParameter4], rsi
0x14001a910  call    WPP_SF_qqD
0x14001a915  jmp     loc_14001A875
```
