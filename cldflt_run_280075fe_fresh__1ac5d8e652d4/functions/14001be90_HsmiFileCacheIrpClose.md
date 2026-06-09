# HsmiFileCacheIrpClose

- ea: `0x14001be90`
- end: `0x14001bfb9`
- name: `HsmiFileCacheIrpClose`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x14000c12c`
- `0x14000d868`
- `0x14000d95c`
- `0x14001bdb8`
- `0x14001be90`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001bf6f`
- `ntoskrnl!IofCompleteRequest` at `0x14001bf6f`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheIrpClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v4; // r9
  unsigned int v5; // ebx
  PFILE_OBJECT FileObject; // rdi
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = a1;
  P = 0;
  v5 = 0;
  FileObject = CurrentStackLocation->FileObject;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      106,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      a1,
      a2,
      FileObject);
  }
  if ( FileObject->FsContext )
  {
    v5 = HsmiFileCacheValidateFileObject(FileObject, 0, &P, v4);
    HsmDbgBreakOnStatus(v5);
    if ( (v5 & 0x80000000) == 0 )
    {
      HsmiFileCacheFreeStreamControlBlock((char *)P);
      FileObject->FsContext = 0;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        107,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        FileObject,
        v5);
    }
  }
  a2->IoStatus.Status = v5;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x14001be90  push    rbx
0x14001be92  push    rsi
0x14001be93  push    rdi
0x14001be94  push    r12
0x14001be96  sub     rsp, 38h
0x14001be9a  mov     rax, [rdx+0B8h]
0x14001bea1  mov     rsi, rdx
0x14001bea4  mov     r9, rcx
0x14001bea7  mov     [rsp+58h+P], 0
0x14001beb0  xor     ebx, ebx
0x14001beb2  mov     rdi, [rax+30h]
0x14001beb6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bebd  lea     r12, WPP_GLOBAL_Control
0x14001bec4  cmp     rcx, r12
0x14001bec7  jz      short loc_14001BEF3
0x14001bec9  mov     eax, [rcx+2Ch]
0x14001becc  test    al, 8
0x14001bece  jz      short loc_14001BEF3
0x14001bed0  cmp     byte ptr [rcx+29h], 5
0x14001bed4  jb      short loc_14001BEF3
0x14001bed6  mov     rcx, [rcx+18h]
0x14001beda  lea     edx, [rbx+6Ah]
0x14001bedd  mov     [rsp+58h+var_30], rdi
0x14001bee2  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bee9  mov     [rsp+58h+var_38], rsi
0x14001beee  call    WPP_SF_qqq
0x14001bef3  cmp     [rdi+18h], rbx
0x14001bef7  jz      short loc_14001BF5F
0x14001bef9  lea     r8, [rsp+58h+P]
0x14001befe  xor     edx, edx
0x14001bf00  mov     rcx, rdi
0x14001bf03  call    HsmiFileCacheValidateFileObject
0x14001bf08  mov     ecx, eax
0x14001bf0a  mov     ebx, eax
0x14001bf0c  call    HsmDbgBreakOnStatus
0x14001bf11  test    ebx, ebx
0x14001bf13  jns     short loc_14001BF4D
0x14001bf15  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf1c  cmp     rcx, r12
0x14001bf1f  jz      short loc_14001BF5F
0x14001bf21  mov     edx, [rcx+2Ch]
0x14001bf24  test    dl, 8
0x14001bf27  jz      short loc_14001BF5F
0x14001bf29  cmp     byte ptr [rcx+29h], 2
0x14001bf2d  jb      short loc_14001BF5F
0x14001bf2f  mov     rcx, [rcx+18h]
0x14001bf33  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bf3a  mov     edx, 6Bh ; 'k'
0x14001bf3f  mov     dword ptr [rsp+58h+var_38], ebx
0x14001bf43  mov     r9, rdi
0x14001bf46  call    WPP_SF_qd
0x14001bf4b  jmp     short loc_14001BF5F
0x14001bf4d  mov     rcx, [rsp+58h+P]; P
0x14001bf52  call    HsmiFileCacheFreeStreamControlBlock
0x14001bf57  mov     qword ptr [rdi+18h], 0
0x14001bf5f  xor     edx, edx; PriorityBoost
0x14001bf61  mov     [rsi+30h], ebx
0x14001bf64  mov     rcx, rsi; Irp
0x14001bf67  mov     qword ptr [rsi+38h], 0
0x14001bf6f  call    cs:__imp_IofCompleteRequest
0x14001bf76  nop     dword ptr [rax+rax+00h]
0x14001bf7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf82  cmp     rcx, r12
0x14001bf85  jz      short loc_14001BFAC
0x14001bf87  mov     eax, [rcx+2Ch]
0x14001bf8a  test    al, 8
0x14001bf8c  jz      short loc_14001BFAC
0x14001bf8e  cmp     byte ptr [rcx+29h], 5
0x14001bf92  jb      short loc_14001BFAC
0x14001bf94  mov     rcx, [rcx+18h]
0x14001bf98  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bf9f  mov     edx, 6Ch ; 'l'
0x14001bfa4  mov     r9d, ebx
0x14001bfa7  call    WPP_SF_d
0x14001bfac  mov     eax, ebx
0x14001bfae  add     rsp, 38h
0x14001bfb2  pop     r12
0x14001bfb4  pop     rdi
0x14001bfb5  pop     rsi
0x14001bfb6  pop     rbx
0x14001bfb7  retn
```
