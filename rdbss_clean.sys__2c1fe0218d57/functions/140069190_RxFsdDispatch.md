# RxFsdDispatch

- ea: `0x140069190`
- end: `0x140069274`
- name: `RxFsdDispatch`
- size: `228`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT RxDeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140014600`
- `0x140014ca0`
- `0x140015290`
- `0x140069190`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14007e799`
- `ntoskrnl!IofCompleteRequest` at `0x14007e799`

## pseudocode

```c
NTSTATUS __stdcall RxFsdDispatch(PRDBSS_DEVICE_OBJECT RxDeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int16 MajorFunction; // ax
  __int64 FileObject; // r10
  __int64 v6; // rdx
  char v7; // di
  __int64 (__fastcall **v8)(PRX_CONTEXT, PIRP); // rax
  NTSTATUS result; // eax
  NTSTATUS v10; // r9d

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( (_BYTE)MajorFunction == 23 )
    return RxSystemControl(RxDeviceObject);
  if ( (_BYTE)MajorFunction == 19 || (_BYTE)MajorFunction == 1 )
  {
    v10 = -1073741773;
  }
  else
  {
    FileObject = (__int64)CurrentStackLocation->FileObject;
    if ( !(_BYTE)MajorFunction )
    {
      v7 = 1;
      goto LABEL_16;
    }
    if ( FileObject )
    {
      v6 = *(_QWORD *)(FileObject + 24);
      if ( v6 )
      {
        v7 = 0;
        if ( (*(_WORD *)v6 & 0xFFF0) == 0xEC20 )
        {
          v8 = *(__int64 (__fastcall ***)(PRX_CONTEXT, PIRP))(v6 + 384);
          if ( v8 )
          {
LABEL_9:
            result = RxFsdCommonDispatch((__int64)v8, (__int64)Irp, FileObject, RxDeviceObject);
            if ( v7 )
            {
              if ( result == -2147483603 )
                return 260;
            }
            return result;
          }
        }
LABEL_16:
        v8 = &RxFsdDispatchVector;
        goto LABEL_9;
      }
    }
    v10 = -1073741808;
  }
  CurrentStackLocation->Control |= 1u;
  Irp->IoStatus.Status = v10;
  Irp->IoStatus.Information = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqhDD(WPP_GLOBAL_Control->AttachedDevice, 13, CurrentStackLocation, RxDeviceObject, Irp, MajorFunction, v10);
  }
  IofCompleteRequest(Irp, 0);
  return 259;
}

```

## disassembly

```asm
0x140069190  push    rbx
0x140069192  sub     rsp, 40h
0x140069196  mov     r8, [rdx+0B8h]
0x14006919d  mov     rbx, rdx
0x1400691a0  movzx   eax, byte ptr [r8]
0x1400691a4  cmp     al, 17h
0x1400691a6  jz      loc_14006922D
0x1400691ac  mov     [rsp+48h+arg_0], rdi
0x1400691b1  cmp     al, 13h
0x1400691b3  jz      loc_14006925E
0x1400691b9  cmp     al, 1
0x1400691bb  jz      loc_14006925E
0x1400691c1  mov     r10, [r8+30h]
0x1400691c5  test    al, al
0x1400691c7  jz      loc_140069252
0x1400691cd  test    r10, r10
0x1400691d0  jz      loc_140069269
0x1400691d6  mov     rdx, [r10+18h]
0x1400691da  test    rdx, rdx
0x1400691dd  jz      loc_140069269
0x1400691e3  movzx   eax, word ptr [rdx]
0x1400691e6  mov     r8d, 0FFF0h
0x1400691ec  and     ax, r8w
0x1400691f0  xor     dil, dil
0x1400691f3  mov     r8d, 0EC20h
0x1400691f9  cmp     ax, r8w
0x1400691fd  jnz     short loc_140069255
0x1400691ff  mov     rax, [rdx+180h]
0x140069206  test    rax, rax
0x140069209  jz      short loc_140069255
0x14006920b  mov     r9, rcx
0x14006920e  mov     r8, r10
0x140069211  mov     rcx, rax
0x140069214  mov     rdx, rbx
0x140069217  call    RxFsdCommonDispatch
0x14006921c  test    dil, dil
0x14006921f  jnz     short loc_140069239
0x140069221  mov     rdi, [rsp+48h+arg_0]
0x140069226  add     rsp, 40h
0x14006922a  pop     rbx
0x14006922b  retn
0x14006922d  call    RxSystemControl
0x140069232  add     rsp, 40h
0x140069236  pop     rbx
0x140069237  retn
0x140069239  mov     rdi, [rsp+48h+arg_0]
0x14006923e  cmp     eax, 8000002Dh
0x140069243  mov     ecx, 104h
0x140069248  cmovz   eax, ecx
0x14006924b  add     rsp, 40h
0x14006924f  pop     rbx
0x140069250  retn
0x140069252  mov     dil, 1
0x140069255  lea     rax, RxFsdDispatchVector
0x14006925c  jmp     short loc_14006920B
0x14006925e  mov     r9d, 0C0000033h
0x140069264  jmp     loc_14007E740
0x140069269  mov     r9d, 0C0000010h
0x14006926f  jmp     loc_14007E740
0x14007e740  or      byte ptr [r8+3], 1
0x14007e745  mov     [rbx+30h], r9d
0x14007e749  mov     qword ptr [rbx+38h], 0
0x14007e751  mov     r10, cs:WPP_GLOBAL_Control
0x14007e758  lea     rdx, WPP_GLOBAL_Control
0x14007e75f  cmp     r10, rdx
0x14007e762  jz      short loc_14007E794
0x14007e764  mov     edx, [r10+2Ch]
0x14007e768  test    dl, 4
0x14007e76b  jz      short loc_14007E794
0x14007e76d  cmp     byte ptr [r10+29h], 2
0x14007e772  jb      short loc_14007E794
0x14007e774  mov     [rsp+48h+var_18], r9d
0x14007e779  mov     edx, 0Dh
0x14007e77e  mov     r9, rcx
0x14007e781  mov     [rsp+48h+var_20], ax
0x14007e786  mov     rcx, [r10+18h]
0x14007e78a  mov     [rsp+48h+var_28], rbx
0x14007e78f  call    WPP_SF_qqhDD
0x14007e794  xor     edx, edx; PriorityBoost
0x14007e796  mov     rcx, rbx; Irp
0x14007e799  call    cs:__imp_IofCompleteRequest
0x14007e7a0  nop     dword ptr [rax+rax+00h]
0x14007e7a5  mov     eax, 103h
0x14007e7aa  jmp     loc_140069221
```
