# MRxSmbFsdDispatch

- ea: `0x14008dda0`
- end: `0x14008df4f`
- name: `MRxSmbFsdDispatch`
- size: `431`
- prototype: `__int64 __fastcall(PRDBSS_DEVICE_OBJECT RxDeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400286a4`
- `0x140028ea4`
- `0x140038068`
- `0x14008dda0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008de1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008deee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008de1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008deee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008dded`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008dded`
- `ntoskrnl!IofCompleteRequest` at `0x14008de87`
- `ntoskrnl!IofCompleteRequest` at `0x14008de87`
- `rdbss!RxFsdDispatch` at `0x14008de35`
- `rdbss!RxFsdDispatch` at `0x14008de35`
- `rdbss!RxAttemptTurboIo` at `0x14008ded5`
- `rdbss!RxAttemptTurboIo` at `0x14008ded5`

## pseudocode

```c
__int64 __fastcall MRxSmbFsdDispatch(PRDBSS_DEVICE_OBJECT RxDeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PDEVICE_OBJECT v5; // rcx
  UCHAR MajorFunction; // al
  PFILE_OBJECT FileObject; // rcx
  unsigned int v8; // ebx
  char v9; // r14
  _WORD *FsContext2; // rax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
      RxDeviceObject,
      Irp);
  }
  if ( CurrentStackLocation->MajorFunction != 23 )
  {
    KeEnterCriticalRegion();
    MajorFunction = CurrentStackLocation->MajorFunction;
    if ( CurrentStackLocation->MajorFunction == 27 )
    {
      v9 = 0;
      v8 = MRxSmbProcessPnpIrp(Irp);
      goto LABEL_8;
    }
    FileObject = CurrentStackLocation->FileObject;
    v8 = 0;
    v9 = 1;
    if ( !FileObject )
      goto LABEL_8;
    if ( MajorFunction == 3 )
    {
      if ( CurrentStackLocation->Parameters.Read.Length > 0x10000 )
      {
LABEL_21:
        KeLeaveCriticalRegion();
        return (unsigned int)RxFsdDispatch(RxDeviceObject, Irp);
      }
    }
    else if ( MajorFunction != 4 || CurrentStackLocation->Parameters.Read.Length > 0x10000 )
    {
      goto LABEL_8;
    }
    if ( !CurrentStackLocation->MinorFunction && (Irp->Flags & 1) != 0 )
    {
      FsContext2 = FileObject->FsContext2;
      if ( FsContext2 )
      {
        if ( *FsContext2 == 0xEC30 )
        {
          v8 = RxAttemptTurboIo(Irp);
          if ( v8 != 259 )
            goto LABEL_21;
        }
      }
    }
LABEL_8:
    KeLeaveCriticalRegion();
    if ( v8 )
    {
      if ( v8 == 259 )
        return v8;
    }
    else if ( v9 )
    {
      return (unsigned int)RxFsdDispatch(RxDeviceObject, Irp);
    }
    Irp->IoStatus.Status = v8;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, 0);
    return v8;
  }
  return MRxSmbProcessSystemControlIrp(v5, Irp);
}

```

## disassembly

```asm
0x14008dda0  mov     [rsp+arg_10], rbp
0x14008dda5  mov     [rsp+arg_18], rsi
0x14008ddaa  push    rdi
0x14008ddab  sub     rsp, 30h
0x14008ddaf  mov     rdi, [rdx+0B8h]
0x14008ddb6  mov     rsi, rdx
0x14008ddb9  mov     rbp, rcx
0x14008ddbc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ddc3  lea     rax, WPP_GLOBAL_Control
0x14008ddca  cmp     rcx, rax
0x14008ddcd  jz      short loc_14008DDDA
0x14008ddcf  mov     eax, [rcx+2Ch]
0x14008ddd2  test    al, 2
0x14008ddd4  jnz     loc_14008DF23
0x14008ddda  cmp     byte ptr [rdi], 17h
0x14008dddd  jz      loc_14008DF0A
0x14008dde3  mov     [rsp+38h+arg_0], rbx
0x14008dde8  mov     [rsp+38h+arg_8], r14
0x14008dded  call    cs:__imp_KeEnterCriticalRegion
0x14008ddf4  nop     dword ptr [rax+rax+00h]
0x14008ddf9  movzx   eax, byte ptr [rdi]
0x14008ddfc  cmp     al, 1Bh
0x14008ddfe  jz      short loc_14008DE60
0x14008de00  mov     rcx, [rdi+30h]
0x14008de04  xor     ebx, ebx
0x14008de06  mov     r14b, 1
0x14008de09  test    rcx, rcx
0x14008de0c  jz      short loc_14008DE1A
0x14008de0e  cmp     al, 3
0x14008de10  jz      loc_14008DEFF
0x14008de16  cmp     al, 4
0x14008de18  jz      short loc_14008DE95
0x14008de1a  call    cs:__imp_KeLeaveCriticalRegion
0x14008de21  nop     dword ptr [rax+rax+00h]
0x14008de26  test    ebx, ebx
0x14008de28  jnz     short loc_14008DE6F
0x14008de2a  test    r14b, r14b
0x14008de2d  jz      short loc_14008DE77
0x14008de2f  mov     rdx, rsi; Irp
0x14008de32  mov     rcx, rbp; RxDeviceObject
0x14008de35  call    cs:__imp_RxFsdDispatch
0x14008de3c  nop     dword ptr [rax+rax+00h]
0x14008de41  mov     ebx, eax
0x14008de43  mov     r14, [rsp+38h+arg_8]
0x14008de48  mov     eax, ebx
0x14008de4a  mov     rbx, [rsp+38h+arg_0]
0x14008de4f  mov     rbp, [rsp+38h+arg_10]
0x14008de54  mov     rsi, [rsp+38h+arg_18]
0x14008de59  add     rsp, 30h
0x14008de5d  pop     rdi
0x14008de5e  retn
0x14008de60  xor     r14b, r14b
0x14008de63  mov     rcx, rsi
0x14008de66  call    MRxSmbProcessPnpIrp
0x14008de6b  mov     ebx, eax
0x14008de6d  jmp     short loc_14008DE1A
0x14008de6f  cmp     ebx, 103h
0x14008de75  jz      short loc_14008DE43
0x14008de77  xor     edx, edx; PriorityBoost
0x14008de79  mov     [rsi+30h], ebx
0x14008de7c  mov     rcx, rsi; Irp
0x14008de7f  mov     qword ptr [rsi+38h], 0
0x14008de87  call    cs:__imp_IofCompleteRequest
0x14008de8e  nop     dword ptr [rax+rax+00h]
0x14008de93  jmp     short loc_14008DE43
0x14008de95  cmp     dword ptr [rdi+8], 10000h
0x14008de9c  ja      loc_14008DE1A
0x14008dea2  cmp     [rdi+1], bl
0x14008dea5  jnz     loc_14008DE1A
0x14008deab  mov     eax, [rsi+10h]
0x14008deae  test    r14b, al
0x14008deb1  jz      loc_14008DE1A
0x14008deb7  mov     rax, [rcx+20h]
0x14008debb  test    rax, rax
0x14008debe  jz      loc_14008DE1A
0x14008dec4  mov     ecx, 0EC30h
0x14008dec9  cmp     cx, [rax]
0x14008decc  jnz     loc_14008DE1A
0x14008ded2  mov     rcx, rsi
0x14008ded5  call    cs:__imp_RxAttemptTurboIo
0x14008dedc  nop     dword ptr [rax+rax+00h]
0x14008dee1  mov     ebx, eax
0x14008dee3  cmp     eax, 103h
0x14008dee8  jz      loc_14008DE1A
0x14008deee  call    cs:__imp_KeLeaveCriticalRegion
0x14008def5  nop     dword ptr [rax+rax+00h]
0x14008defa  jmp     loc_14008DE2F
0x14008deff  cmp     dword ptr [rdi+8], 10000h
0x14008df06  jbe     short loc_14008DEA2
0x14008df08  jmp     short loc_14008DEEE
0x14008df0a  mov     rdx, rsi
0x14008df0d  call    MRxSmbProcessSystemControlIrp
0x14008df12  mov     rbp, [rsp+38h+arg_10]
0x14008df17  mov     rsi, [rsp+38h+arg_18]
0x14008df1c  add     rsp, 30h
0x14008df20  pop     rdi
0x14008df21  retn
0x14008df23  cmp     byte ptr [rcx+29h], 4
0x14008df27  jb      loc_14008DDDA
0x14008df2d  mov     rcx, [rcx+18h]
0x14008df31  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14008df38  mov     edx, 32h ; '2'
0x14008df3d  mov     [rsp+38h+var_18], rsi
0x14008df42  mov     r9, rbp
0x14008df45  call    WPP_SF_qq
0x14008df4a  jmp     loc_14008DDDA
```
