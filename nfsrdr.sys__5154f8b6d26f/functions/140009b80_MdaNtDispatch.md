# MdaNtDispatch

- ea: `0x140009b80`
- end: `0x140009dbf`
- name: `MdaNtDispatch`
- size: `575`
- prototype: `__int64 __fastcall(PRDBSS_DEVICE_OBJECT RxDeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009b80`
- `0x1400159cc`
- `0x1400159fc`
- `0x140022c5c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140009c27`
- `ntoskrnl!IofCompleteRequest` at `0x140009c9f`
- `ntoskrnl!IofCompleteRequest` at `0x140009cf2`
- `ntoskrnl!IofCompleteRequest` at `0x140009c27`
- `ntoskrnl!IofCompleteRequest` at `0x140009c9f`
- `ntoskrnl!IofCompleteRequest` at `0x140009cf2`
- `rdbss!RxFsdDispatch` at `0x140009c03`
- `rdbss!RxFsdDispatch` at `0x140009d5d`
- `rdbss!RxFsdDispatch` at `0x140009c03`
- `rdbss!RxFsdDispatch` at `0x140009d5d`

## pseudocode

```c
__int64 __fastcall MdaNtDispatch(PRDBSS_DEVICE_OBJECT RxDeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int v5; // esi
  char v6; // r14
  volatile signed __int32 *v7; // rdi
  NTSTATUS v8; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( (HIDWORD(RxDeviceObject[1].DispatcherContext.pTearDownEvent) & 8) == 0 )
  {
    v7 = (volatile signed __int32 *)&RxDeviceObject[1].RxNetNameTableInDeviceObject.MemberQueue.Blink + 1;
    _InterlockedIncrement((volatile signed __int32 *)&RxDeviceObject[1].RxNetNameTableInDeviceObject.MemberQueue.Blink + 1);
    if ( (_InterlockedCompareExchange(
            (volatile signed __int32 *)&RxDeviceObject[1].DispatcherContext.pTearDownEvent + 1,
            0,
            0)
        & 8) != 0 )
    {
      v6 = 1;
      goto LABEL_12;
    }
    Irp->IoStatus.Information = 0;
    if ( CurrentStackLocation->MajorFunction == 14 )
    {
      v8 = MdaDeviceControl(RxDeviceObject, Irp);
      v5 = v8;
      if ( v8 != -1073741822 )
      {
        Irp->IoStatus.Status = v8;
        if ( v8 == 259 )
          Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        else
          IofCompleteRequest(Irp, 0);
        v7 = (volatile signed __int32 *)&RxDeviceObject[1].RxNetNameTableInDeviceObject.MemberQueue.Blink + 1;
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_29:
        v5 = RxFsdDispatch(RxDeviceObject, Irp);
LABEL_30:
        _InterlockedDecrement(v7);
        goto LABEL_31;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
    goto LABEL_29;
  }
  if ( ((CurrentStackLocation->MajorFunction - 2) & 0xEF) == 0 )
  {
    if ( CurrentStackLocation->FileObject->FileName.Length )
    {
      Irp->IoStatus.Information = 0;
      v5 = -1073741823;
      Irp->IoStatus.Status = -1073741823;
      IofCompleteRequest(Irp, 0);
    }
    else
    {
      v5 = RxFsdDispatch(RxDeviceObject, Irp);
    }
    goto LABEL_31;
  }
  v6 = 0;
  v7 = (volatile signed __int32 *)&RxDeviceObject[1].RxNetNameTableInDeviceObject.MemberQueue.Blink + 1;
LABEL_12:
  v5 = -1073741823;
  Irp->IoStatus.Information = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
  Irp->IoStatus.Status = -1073741823;
  IofCompleteRequest(Irp, 0);
  if ( v6 )
    goto LABEL_30;
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x140009b80  sub     rsp, 38h
0x140009b84  mov     [rsp+38h+arg_0], rbx
0x140009b89  mov     rbx, rdx
0x140009b8c  mov     [rsp+38h+arg_8], rbp
0x140009b91  mov     rbp, rcx
0x140009b94  mov     [rsp+38h+var_18], r15
0x140009b99  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ba0  lea     r15, WPP_GLOBAL_Control
0x140009ba7  cmp     rcx, r15
0x140009baa  jz      short loc_140009BC8
0x140009bac  mov     eax, [rcx+2Ch]
0x140009baf  test    al, 8
0x140009bb1  jz      short loc_140009BC8
0x140009bb3  mov     rcx, [rcx+18h]
0x140009bb7  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140009bbe  mov     edx, 1Bh
0x140009bc3  call    WPP_SF_
0x140009bc8  mov     eax, [rbp+90Ch]
0x140009bce  mov     rdx, [rbx+0B8h]
0x140009bd5  mov     [rsp+38h+arg_10], rsi
0x140009bda  mov     [rsp+38h+var_8], rdi
0x140009bdf  mov     [rsp+38h+var_10], r14
0x140009be4  test    al, 8
0x140009be6  jz      short loc_140009C46
0x140009be8  movzx   eax, byte ptr [rdx]
0x140009beb  sub     al, 2
0x140009bed  test    al, 0EFh
0x140009bef  jnz     short loc_140009C38
0x140009bf1  mov     rax, [rdx+30h]
0x140009bf5  xor     ecx, ecx
0x140009bf7  cmp     cx, [rax+58h]
0x140009bfb  jnz     short loc_140009C16
0x140009bfd  mov     rdx, rbx; Irp
0x140009c00  mov     rcx, rbp; RxDeviceObject
0x140009c03  call    cs:__imp_RxFsdDispatch
0x140009c0a  nop     dword ptr [rax+rax+00h]
0x140009c0f  mov     esi, eax
0x140009c11  jmp     loc_140009D6E
0x140009c16  mov     [rbx+38h], rcx
0x140009c1a  mov     esi, 0C0000001h
0x140009c1f  mov     rcx, rbx; Irp
0x140009c22  mov     [rbx+30h], esi
0x140009c25  xor     edx, edx; PriorityBoost
0x140009c27  call    cs:__imp_IofCompleteRequest
0x140009c2e  nop     dword ptr [rax+rax+00h]
0x140009c33  jmp     loc_140009D6E
0x140009c38  xor     r14b, r14b
0x140009c3b  lea     rdi, [rbp+92Ch]
0x140009c42  xor     ecx, ecx
0x140009c44  jmp     short loc_140009C63
0x140009c46  lea     rdi, [rbp+92Ch]
0x140009c4d  lock inc dword ptr [rdi]
0x140009c50  xor     ecx, ecx
0x140009c52  xor     eax, eax
0x140009c54  lock cmpxchg [rbp+90Ch], ecx
0x140009c5c  test    al, 8
0x140009c5e  jz      short loc_140009CB9
0x140009c60  mov     r14b, 1
0x140009c63  mov     esi, 0C0000001h
0x140009c68  mov     [rbx+38h], rcx
0x140009c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c73  cmp     rcx, r15
0x140009c76  jz      short loc_140009C97
0x140009c78  mov     eax, [rcx+2Ch]
0x140009c7b  test    al, 1
0x140009c7d  jz      short loc_140009C97
0x140009c7f  mov     rcx, [rcx+18h]
0x140009c83  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140009c8a  mov     edx, 1Ch
0x140009c8f  mov     r9d, esi
0x140009c92  call    WPP_SF_d
0x140009c97  xor     edx, edx; PriorityBoost
0x140009c99  mov     [rbx+30h], esi
0x140009c9c  mov     rcx, rbx; Irp
0x140009c9f  call    cs:__imp_IofCompleteRequest
0x140009ca6  nop     dword ptr [rax+rax+00h]
0x140009cab  test    r14b, r14b
0x140009cae  jz      loc_140009D6E
0x140009cb4  jmp     loc_140009D6B
0x140009cb9  mov     [rbx+38h], rcx
0x140009cbd  cmp     byte ptr [rdx], 0Eh
0x140009cc0  jnz     short loc_140009D2F
0x140009cc2  mov     rdx, rbx
0x140009cc5  mov     rcx, rbp
0x140009cc8  call    MdaDeviceControl
0x140009ccd  mov     esi, eax
0x140009ccf  cmp     eax, 0C0000002h
0x140009cd4  jz      short loc_140009D07
0x140009cd6  mov     [rbx+30h], eax
0x140009cd9  cmp     eax, 103h
0x140009cde  jnz     short loc_140009CED
0x140009ce0  mov     rax, [rbx+0B8h]
0x140009ce7  or      byte ptr [rax+3], 1
0x140009ceb  jmp     short loc_140009CFE
0x140009ced  xor     edx, edx; PriorityBoost
0x140009cef  mov     rcx, rbx; Irp
0x140009cf2  call    cs:__imp_IofCompleteRequest
0x140009cf9  nop     dword ptr [rax+rax+00h]
0x140009cfe  lea     rdi, [rbp+92Ch]
0x140009d05  jmp     short loc_140009D6B
0x140009d07  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d0e  cmp     rcx, r15
0x140009d11  jz      short loc_140009D57
0x140009d13  mov     eax, [rcx+2Ch]
0x140009d16  test    al, 2
0x140009d18  jz      short loc_140009D2F
0x140009d1a  mov     rcx, [rcx+18h]
0x140009d1e  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140009d25  mov     edx, 1Dh
0x140009d2a  call    WPP_SF_
0x140009d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d36  cmp     rcx, r15
0x140009d39  jz      short loc_140009D57
0x140009d3b  mov     eax, [rcx+2Ch]
0x140009d3e  test    al, 8
0x140009d40  jz      short loc_140009D57
0x140009d42  mov     rcx, [rcx+18h]
0x140009d46  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140009d4d  mov     edx, 1Eh
0x140009d52  call    WPP_SF_
0x140009d57  mov     rdx, rbx; Irp
0x140009d5a  mov     rcx, rbp; RxDeviceObject
0x140009d5d  call    cs:__imp_RxFsdDispatch
0x140009d64  nop     dword ptr [rax+rax+00h]
0x140009d69  mov     esi, eax
0x140009d6b  lock dec dword ptr [rdi]
0x140009d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d75  mov     r14, [rsp+38h+var_10]
0x140009d7a  cmp     rcx, r15
0x140009d7d  mov     r15, [rsp+38h+var_18]
0x140009d82  mov     rdi, [rsp+38h+var_8]
0x140009d87  mov     rbp, [rsp+38h+arg_8]
0x140009d8c  mov     rbx, [rsp+38h+arg_0]
0x140009d91  jz      short loc_140009DB2
0x140009d93  mov     eax, [rcx+2Ch]
0x140009d96  test    al, 8
0x140009d98  jz      short loc_140009DB2
0x140009d9a  mov     rcx, [rcx+18h]
0x140009d9e  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140009da5  mov     edx, 1Fh
0x140009daa  mov     r9d, esi
0x140009dad  call    WPP_SF_d
0x140009db2  mov     eax, esi
0x140009db4  mov     rsi, [rsp+38h+arg_10]
0x140009db9  add     rsp, 38h
0x140009dbd  retn
```
