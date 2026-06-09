# HsmiFileCacheIrpClose

- ea: `0x14001bf10`
- end: `0x14001c039`
- name: `HsmiFileCacheIrpClose`
- size: `297`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x14000c12c`
- `0x14000d868`
- `0x14000d95c`
- `0x14001be38`
- `0x14001bf10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001bfef`
- `ntoskrnl!IofCompleteRequest` at `0x14001bfef`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheIrpClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v4; // ebx
  PFILE_OBJECT FileObject; // rdi
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  v4 = 0;
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
    v4 = HsmiFileCacheValidateFileObject(FileObject, 0, &P);
    HsmDbgBreakOnStatus(v4);
    if ( v4 >= 0 )
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
        v4);
    }
  }
  a2->IoStatus.Status = v4;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001bf10  push    rbx
0x14001bf12  push    rsi
0x14001bf13  push    rdi
0x14001bf14  push    r12
0x14001bf16  sub     rsp, 38h
0x14001bf1a  mov     rax, [rdx+0B8h]
0x14001bf21  mov     rsi, rdx
0x14001bf24  mov     r9, rcx
0x14001bf27  mov     [rsp+58h+P], 0
0x14001bf30  xor     ebx, ebx
0x14001bf32  mov     rdi, [rax+30h]
0x14001bf36  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf3d  lea     r12, WPP_GLOBAL_Control
0x14001bf44  cmp     rcx, r12
0x14001bf47  jz      short loc_14001BF73
0x14001bf49  mov     eax, [rcx+2Ch]
0x14001bf4c  test    al, 8
0x14001bf4e  jz      short loc_14001BF73
0x14001bf50  cmp     byte ptr [rcx+29h], 5
0x14001bf54  jb      short loc_14001BF73
0x14001bf56  mov     rcx, [rcx+18h]
0x14001bf5a  lea     edx, [rbx+6Ah]
0x14001bf5d  mov     [rsp+58h+var_30], rdi
0x14001bf62  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bf69  mov     [rsp+58h+var_38], rsi
0x14001bf6e  call    WPP_SF_qqq
0x14001bf73  cmp     [rdi+18h], rbx
0x14001bf77  jz      short loc_14001BFDF
0x14001bf79  lea     r8, [rsp+58h+P]
0x14001bf7e  xor     edx, edx
0x14001bf80  mov     rcx, rdi
0x14001bf83  call    HsmiFileCacheValidateFileObject
0x14001bf88  mov     ecx, eax
0x14001bf8a  mov     ebx, eax
0x14001bf8c  call    HsmDbgBreakOnStatus
0x14001bf91  test    ebx, ebx
0x14001bf93  jns     short loc_14001BFCD
0x14001bf95  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf9c  cmp     rcx, r12
0x14001bf9f  jz      short loc_14001BFDF
0x14001bfa1  mov     edx, [rcx+2Ch]
0x14001bfa4  test    dl, 8
0x14001bfa7  jz      short loc_14001BFDF
0x14001bfa9  cmp     byte ptr [rcx+29h], 2
0x14001bfad  jb      short loc_14001BFDF
0x14001bfaf  mov     rcx, [rcx+18h]
0x14001bfb3  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bfba  mov     edx, 6Bh ; 'k'
0x14001bfbf  mov     dword ptr [rsp+58h+var_38], ebx
0x14001bfc3  mov     r9, rdi
0x14001bfc6  call    WPP_SF_qd
0x14001bfcb  jmp     short loc_14001BFDF
0x14001bfcd  mov     rcx, [rsp+58h+P]; P
0x14001bfd2  call    HsmiFileCacheFreeStreamControlBlock
0x14001bfd7  mov     qword ptr [rdi+18h], 0
0x14001bfdf  xor     edx, edx; PriorityBoost
0x14001bfe1  mov     [rsi+30h], ebx
0x14001bfe4  mov     rcx, rsi; Irp
0x14001bfe7  mov     qword ptr [rsi+38h], 0
0x14001bfef  call    cs:__imp_IofCompleteRequest
0x14001bff6  nop     dword ptr [rax+rax+00h]
0x14001bffb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c002  cmp     rcx, r12
0x14001c005  jz      short loc_14001C02C
0x14001c007  mov     eax, [rcx+2Ch]
0x14001c00a  test    al, 8
0x14001c00c  jz      short loc_14001C02C
0x14001c00e  cmp     byte ptr [rcx+29h], 5
0x14001c012  jb      short loc_14001C02C
0x14001c014  mov     rcx, [rcx+18h]
0x14001c018  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c01f  mov     edx, 6Ch ; 'l'
0x14001c024  mov     r9d, ebx
0x14001c027  call    WPP_SF_d
0x14001c02c  mov     eax, ebx
0x14001c02e  add     rsp, 38h
0x14001c032  pop     r12
0x14001c034  pop     rdi
0x14001c035  pop     rsi
0x14001c036  pop     rbx
0x14001c037  retn
```
