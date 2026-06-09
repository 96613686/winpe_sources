# MRxSmbFsdDispatch

- ea: `0x14008dd50`
- end: `0x14008deff`
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
- `0x14008dd50`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ddca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008de9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ddca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008de9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008dd9d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008dd9d`
- `ntoskrnl!IofCompleteRequest` at `0x14008de37`
- `ntoskrnl!IofCompleteRequest` at `0x14008de37`
- `rdbss!RxFsdDispatch` at `0x14008dde5`
- `rdbss!RxFsdDispatch` at `0x14008dde5`
- `rdbss!RxAttemptTurboIo` at `0x14008de85`
- `rdbss!RxAttemptTurboIo` at `0x14008de85`

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
0x14008dd50  mov     [rsp+arg_10], rbp
0x14008dd55  mov     [rsp+arg_18], rsi
0x14008dd5a  push    rdi
0x14008dd5b  sub     rsp, 30h
0x14008dd5f  mov     rdi, [rdx+0B8h]
0x14008dd66  mov     rsi, rdx
0x14008dd69  mov     rbp, rcx
0x14008dd6c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008dd73  lea     rax, WPP_GLOBAL_Control
0x14008dd7a  cmp     rcx, rax
0x14008dd7d  jz      short loc_14008DD8A
0x14008dd7f  mov     eax, [rcx+2Ch]
0x14008dd82  test    al, 2
0x14008dd84  jnz     loc_14008DED3
0x14008dd8a  cmp     byte ptr [rdi], 17h
0x14008dd8d  jz      loc_14008DEBA
0x14008dd93  mov     [rsp+38h+arg_0], rbx
0x14008dd98  mov     [rsp+38h+arg_8], r14
0x14008dd9d  call    cs:__imp_KeEnterCriticalRegion
0x14008dda4  nop     dword ptr [rax+rax+00h]
0x14008dda9  movzx   eax, byte ptr [rdi]
0x14008ddac  cmp     al, 1Bh
0x14008ddae  jz      short loc_14008DE10
0x14008ddb0  mov     rcx, [rdi+30h]
0x14008ddb4  xor     ebx, ebx
0x14008ddb6  mov     r14b, 1
0x14008ddb9  test    rcx, rcx
0x14008ddbc  jz      short loc_14008DDCA
0x14008ddbe  cmp     al, 3
0x14008ddc0  jz      loc_14008DEAF
0x14008ddc6  cmp     al, 4
0x14008ddc8  jz      short loc_14008DE45
0x14008ddca  call    cs:__imp_KeLeaveCriticalRegion
0x14008ddd1  nop     dword ptr [rax+rax+00h]
0x14008ddd6  test    ebx, ebx
0x14008ddd8  jnz     short loc_14008DE1F
0x14008ddda  test    r14b, r14b
0x14008dddd  jz      short loc_14008DE27
0x14008dddf  mov     rdx, rsi; Irp
0x14008dde2  mov     rcx, rbp; RxDeviceObject
0x14008dde5  call    cs:__imp_RxFsdDispatch
0x14008ddec  nop     dword ptr [rax+rax+00h]
0x14008ddf1  mov     ebx, eax
0x14008ddf3  mov     r14, [rsp+38h+arg_8]
0x14008ddf8  mov     eax, ebx
0x14008ddfa  mov     rbx, [rsp+38h+arg_0]
0x14008ddff  mov     rbp, [rsp+38h+arg_10]
0x14008de04  mov     rsi, [rsp+38h+arg_18]
0x14008de09  add     rsp, 30h
0x14008de0d  pop     rdi
0x14008de0e  retn
0x14008de10  xor     r14b, r14b
0x14008de13  mov     rcx, rsi
0x14008de16  call    MRxSmbProcessPnpIrp
0x14008de1b  mov     ebx, eax
0x14008de1d  jmp     short loc_14008DDCA
0x14008de1f  cmp     ebx, 103h
0x14008de25  jz      short loc_14008DDF3
0x14008de27  xor     edx, edx; PriorityBoost
0x14008de29  mov     [rsi+30h], ebx
0x14008de2c  mov     rcx, rsi; Irp
0x14008de2f  mov     qword ptr [rsi+38h], 0
0x14008de37  call    cs:__imp_IofCompleteRequest
0x14008de3e  nop     dword ptr [rax+rax+00h]
0x14008de43  jmp     short loc_14008DDF3
0x14008de45  cmp     dword ptr [rdi+8], 10000h
0x14008de4c  ja      loc_14008DDCA
0x14008de52  cmp     [rdi+1], bl
0x14008de55  jnz     loc_14008DDCA
0x14008de5b  mov     eax, [rsi+10h]
0x14008de5e  test    r14b, al
0x14008de61  jz      loc_14008DDCA
0x14008de67  mov     rax, [rcx+20h]
0x14008de6b  test    rax, rax
0x14008de6e  jz      loc_14008DDCA
0x14008de74  mov     ecx, 0EC30h
0x14008de79  cmp     cx, [rax]
0x14008de7c  jnz     loc_14008DDCA
0x14008de82  mov     rcx, rsi
0x14008de85  call    cs:__imp_RxAttemptTurboIo
0x14008de8c  nop     dword ptr [rax+rax+00h]
0x14008de91  mov     ebx, eax
0x14008de93  cmp     eax, 103h
0x14008de98  jz      loc_14008DDCA
0x14008de9e  call    cs:__imp_KeLeaveCriticalRegion
0x14008dea5  nop     dword ptr [rax+rax+00h]
0x14008deaa  jmp     loc_14008DDDF
0x14008deaf  cmp     dword ptr [rdi+8], 10000h
0x14008deb6  jbe     short loc_14008DE52
0x14008deb8  jmp     short loc_14008DE9E
0x14008deba  mov     rdx, rsi
0x14008debd  call    MRxSmbProcessSystemControlIrp
0x14008dec2  mov     rbp, [rsp+38h+arg_10]
0x14008dec7  mov     rsi, [rsp+38h+arg_18]
0x14008decc  add     rsp, 30h
0x14008ded0  pop     rdi
0x14008ded1  retn
0x14008ded3  cmp     byte ptr [rcx+29h], 4
0x14008ded7  jb      loc_14008DD8A
0x14008dedd  mov     rcx, [rcx+18h]
0x14008dee1  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14008dee8  mov     edx, 32h ; '2'
0x14008deed  mov     [rsp+38h+var_18], rsi
0x14008def2  mov     r9, rbp
0x14008def5  call    WPP_SF_qq
0x14008defa  jmp     loc_14008DD8A
```
