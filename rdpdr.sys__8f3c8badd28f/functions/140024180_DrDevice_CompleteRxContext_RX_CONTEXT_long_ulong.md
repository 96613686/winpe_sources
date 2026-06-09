# DrDevice::CompleteRxContext(_RX_CONTEXT *,long,ulong)

- ea: `0x140024180`
- end: `0x1400242a9`
- name: `?CompleteRxContext@DrDevice@@KAXPEAU_RX_CONTEXT@@JK@Z`
- size: `297`
- prototype: `void __fastcall(PRX_CONTEXT RxContext, int, unsigned int)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140011870`
- `0x14001f310`
- `0x14001f480`
- `0x140023030`
- `0x140023500`
- `0x140024020`
- `0x140027190`
- `0x14002d0c0`

## callees

- `0x14000324c`
- `0x140024180`
- `0x14002ac20`
- `0x14002be3c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002420b`
- `ntoskrnl!KeSetEvent` at `0x14002420b`
- `rdbss!RxLowIoCompletion` at `0x1400241d4`
- `rdbss!RxLowIoCompletion` at `0x1400241d4`

## pseudocode

```c
void __fastcall DrDevice::CompleteRxContext(PRX_CONTEXT RxContext, NTSTATUS a2, unsigned int a3)
{
  bool v3; // zf
  char RealDevice; // al
  PIRP CurrentIrp; // rax
  struct _FILE_OBJECT *FileObject; // rcx
  PIRP v9; // rax
  struct _FILE_OBJECT *v10; // rcx

  v3 = (*((_BYTE *)&RxContext->9 + 122) & 1) == 0;
  RxContext->InformationToReturn = a3;
  RxContext->StoredStatus = a2;
  if ( v3 && LOBYTE(RxContext->RealDevice) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    RealDevice = (char)RxContext->RealDevice;
    if ( RealDevice )
    {
      if ( RealDevice == 2 )
      {
        CurrentIrp = RxContext->CurrentIrp;
        if ( CurrentIrp )
        {
          FileObject = CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject;
          if ( FileObject )
            DrRemoveOpenHandle(FileObject);
        }
      }
    }
    else if ( !a2 )
    {
      v9 = RxContext->CurrentIrp;
      if ( v9 )
      {
        v10 = v9->Tail.Overlay.CurrentStackLocation->FileObject;
        if ( v10 )
          DrAddOpenHandle(v10);
      }
    }
    RxLowIoCompletion(RxContext);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    KeSetEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, 0, 0);
  }
}

```

## disassembly

```asm
0x140024180  mov     [rsp+arg_0], rbx
0x140024185  push    rdi
0x140024186  sub     rsp, 20h
0x14002418a  test    byte ptr [rcx+20Ah], 1
0x140024191  mov     edi, edx
0x140024193  mov     eax, r8d
0x140024196  mov     rbx, rcx
0x140024199  mov     [rcx+0B8h], rax
0x1400241a0  mov     [rcx+0B0h], edx
0x1400241a6  jnz     short loc_1400241EC
0x1400241a8  cmp     byte ptr [rcx+20h], 0
0x1400241ac  jz      short loc_1400241EC
0x1400241ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400241b5  lea     rax, WPP_GLOBAL_Control
0x1400241bc  cmp     rcx, rax
0x1400241bf  jnz     short loc_140024219
0x1400241c1  movzx   eax, byte ptr [rbx+20h]
0x1400241c5  test    al, al
0x1400241c7  jz      loc_140024276
0x1400241cd  cmp     al, 2
0x1400241cf  jz      short loc_140024236
0x1400241d1  mov     rcx, rbx; RxContext
0x1400241d4  call    cs:__imp_RxLowIoCompletion
0x1400241db  nop     dword ptr [rax+rax+00h]
0x1400241e0  mov     rbx, [rsp+28h+arg_0]
0x1400241e5  add     rsp, 20h
0x1400241e9  pop     rdi
0x1400241ea  retn
0x1400241ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400241f3  lea     rax, WPP_GLOBAL_Control
0x1400241fa  cmp     rcx, rax
0x1400241fd  jnz     short loc_140024259
0x1400241ff  lea     rcx, [rbx+180h]; Event
0x140024206  xor     r8d, r8d; Wait
0x140024209  xor     edx, edx; Increment
0x14002420b  call    cs:__imp_KeSetEvent
0x140024212  nop     dword ptr [rax+rax+00h]
0x140024217  jmp     short loc_1400241E0
0x140024219  cmp     byte ptr [rcx+29h], 5
0x14002421d  jb      short loc_1400241C1
0x14002421f  mov     rcx, [rcx+18h]
0x140024223  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002422a  mov     edx, 43h ; 'C'
0x14002422f  call    WPP_SF_
0x140024234  jmp     short loc_1400241C1
0x140024236  mov     rax, [rbx+28h]
0x14002423a  test    rax, rax
0x14002423d  jz      short loc_1400241D1
0x14002423f  mov     rax, [rax+0B8h]
0x140024246  mov     rcx, [rax+30h]; struct _FILE_OBJECT *
0x14002424a  test    rcx, rcx
0x14002424d  jz      short loc_1400241D1
0x14002424f  call    ?DrRemoveOpenHandle@@YAXPEAU_FILE_OBJECT@@@Z; DrRemoveOpenHandle(_FILE_OBJECT *)
0x140024254  jmp     loc_1400241D1
0x140024259  cmp     byte ptr [rcx+29h], 5
0x14002425d  jb      short loc_1400241FF
0x14002425f  mov     rcx, [rcx+18h]
0x140024263  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002426a  mov     edx, 42h ; 'B'
0x14002426f  call    WPP_SF_
0x140024274  jmp     short loc_1400241FF
0x140024276  test    edi, edi
0x140024278  jnz     loc_1400241D1
0x14002427e  mov     rax, [rbx+28h]
0x140024282  test    rax, rax
0x140024285  jz      loc_1400241D1
0x14002428b  mov     rax, [rax+0B8h]
0x140024292  mov     rcx, [rax+30h]; struct _FILE_OBJECT *
0x140024296  test    rcx, rcx
0x140024299  jz      loc_1400241D1
0x14002429f  call    ?DrAddOpenHandle@@YAXPEAU_FILE_OBJECT@@@Z; DrAddOpenHandle(_FILE_OBJECT *)
0x1400242a4  jmp     loc_1400241D1
```
