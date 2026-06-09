# CProxy::CreateRemoteCursor(_DEVICE_OBJECT *,ulong,ulong)

- ea: `0x14001b9e0`
- end: `0x14001bb6e`
- name: `?CreateRemoteCursor@CProxy@@UEAAJPEAU_DEVICE_OBJECT@@KK@Z`
- size: `398`
- prototype: `int(CProxy *__hidden this, struct _DEVICE_OBJECT *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400057f4`

## callees

- `0x140001c04`
- `0x14000b7bc`
- `0x14000c914`
- `0x14000cb4c`
- `0x140019e5c`
- `0x14001b9e0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001bb0b`
- `ntoskrnl!IofCompleteRequest` at `0x14001bb50`
- `ntoskrnl!IofCompleteRequest` at `0x14001bb0b`
- `ntoskrnl!IofCompleteRequest` at `0x14001bb50`

## pseudocode

```c
__int64 __fastcall CProxy::CreateRemoteCursor(CProxy ***this, struct _DEVICE_OBJECT *a2, int a3, unsigned int a4)
{
  struct _IRP *TaggedRequest; // rax
  IRP *v8; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  unsigned int v11; // esi
  unsigned int v12; // edi
  struct CCursor *v13; // rax
  struct CCursor *v14; // r8
  CProxy **v15; // rdx
  CProxy *v16; // rax
  _DWORD *p_Type; // rax
  _QWORD v18[9]; // [rsp+30h] [rbp-48h] BYREF

  TaggedRequest = CQueueBase::GetTaggedRequest((CQueueBase *)this, a4);
  v8 = TaggedRequest;
  if ( !TaggedRequest )
    return 3221226021LL;
  CurrentStackLocation = TaggedRequest->Tail.Overlay.CurrentStackLocation;
  v18[0] = 0;
  v11 = CCursor::Create(v18, CurrentStackLocation->FileObject, a2, this);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_qDD(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids);
    }
    v13 = CCursor::Validate(a2, v11);
    v14 = v13;
    v15 = this[10];
    if ( *v15 != (CProxy *)(this + 9) )
      __fastfail(3u);
    v16 = (struct CCursor *)((char *)v13 + 16);
    *((_QWORD *)v16 + 1) = v15;
    *(_QWORD *)v16 = this + 9;
    *v15 = v16;
    this[10] = (CProxy **)v16;
    *((_DWORD *)v14 + 14) = a3;
    p_Type = &v8->AssociatedIrp.MasterIrp->Type;
    if ( p_Type && CurrentStackLocation->Parameters.Read.Length >= 4 )
    {
      *p_Type = v11;
      v8->IoStatus.Information = 4;
      v8->IoStatus.Status = 0;
      IofCompleteRequest(v8, 0);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 16, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids);
    }
    v12 = -1073741808;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids);
    }
    v12 = -1073741670;
  }
  v8->IoStatus.Status = v12;
  IofCompleteRequest(v8, 0);
  return v12;
}

```

## disassembly

```asm
0x14001b9e0  push    rbx
0x14001b9e2  push    rbp
0x14001b9e3  push    rsi
0x14001b9e4  push    rdi
0x14001b9e5  push    r12
0x14001b9e7  push    r14
0x14001b9e9  push    r15
0x14001b9eb  sub     rsp, 40h
0x14001b9ef  mov     r15, rdx
0x14001b9f2  mov     r12d, r8d
0x14001b9f5  mov     edx, r9d; unsigned int
0x14001b9f8  mov     rbp, rcx
0x14001b9fb  call    ?GetTaggedRequest@CQueueBase@@IEAAPEAU_IRP@@K@Z; CQueueBase::GetTaggedRequest(ulong)
0x14001ba00  mov     rbx, rax
0x14001ba03  test    rax, rax
0x14001ba06  jnz     short loc_14001BA12
0x14001ba08  mov     eax, 0C0000225h
0x14001ba0d  jmp     loc_14001BB5E
0x14001ba12  mov     r14, [rax+0B8h]
0x14001ba19  lea     rcx, [rsp+78h+var_48]
0x14001ba1e  mov     r9, rbp
0x14001ba21  mov     [rsp+78h+var_48], 0
0x14001ba2a  mov     r8, r15
0x14001ba2d  mov     rdx, [r14+30h]
0x14001ba31  call    ?Create@CCursor@@SAKAEBV?$CAVLTree1@VCPacket@@_KVCGetLookupId@1@V?$Less@_K@@$0EI@@@PEBU_FILE_OBJECT@@PEAU_DEVICE_OBJECT@@PEAVCUserQueue@@@Z; CCursor::Create(CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72> const &,_FILE_OBJECT const *,_DEVICE_OBJECT *,CUserQueue *)
0x14001ba36  mov     esi, eax
0x14001ba38  test    eax, eax
0x14001ba3a  jnz     short loc_14001BA73
0x14001ba3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba43  lea     rdi, WPP_GLOBAL_Control
0x14001ba4a  cmp     rcx, rdi
0x14001ba4d  jz      short loc_14001BA69
0x14001ba4f  mov     eax, [rcx+6Ch]
0x14001ba52  test    al, 1
0x14001ba54  jz      short loc_14001BA69
0x14001ba56  mov     rcx, [rcx+58h]
0x14001ba5a  lea     edx, [rsi+0Eh]
0x14001ba5d  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x14001ba64  call    WPP_SF_
0x14001ba69  mov     edi, 0C000009Ah
0x14001ba6e  jmp     loc_14001BB48
0x14001ba73  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba7a  lea     rdi, WPP_GLOBAL_Control
0x14001ba81  cmp     rcx, rdi
0x14001ba84  jz      short loc_14001BAAE
0x14001ba86  mov     eax, [rcx+6Ch]
0x14001ba89  test    al, 4
0x14001ba8b  jz      short loc_14001BAAE
0x14001ba8d  mov     rcx, [rcx+58h]
0x14001ba91  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x14001ba98  mov     edx, 0Fh
0x14001ba9d  mov     [rsp+78h+var_50], r12d
0x14001baa2  mov     r9, rbx
0x14001baa5  mov     [rsp+78h+var_58], esi
0x14001baa9  call    WPP_SF_qDD
0x14001baae  mov     edx, esi; unsigned int
0x14001bab0  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14001bab3  call    ?Validate@CCursor@@SAPEAV1@PEAU_DEVICE_OBJECT@@K@Z; CCursor::Validate(_DEVICE_OBJECT *,ulong)
0x14001bab8  lea     rcx, [rbp+48h]
0x14001babc  mov     r8, rax
0x14001babf  mov     rdx, [rcx+8]
0x14001bac3  cmp     [rdx], rcx
0x14001bac6  jz      short loc_14001BACF
0x14001bac8  mov     ecx, 3
0x14001bacd  int     29h; Win8: RtlFailFast(ecx)
0x14001bacf  add     rax, 10h
0x14001bad3  mov     [rax+8], rdx
0x14001bad7  mov     [rax], rcx
0x14001bada  mov     [rdx], rax
0x14001badd  mov     [rcx+8], rax
0x14001bae1  mov     [r8+38h], r12d
0x14001bae5  mov     rax, [rbx+18h]
0x14001bae9  test    rax, rax
0x14001baec  jz      short loc_14001BB1B
0x14001baee  cmp     dword ptr [r14+8], 4
0x14001baf3  jb      short loc_14001BB1B
0x14001baf5  mov     [rax], esi
0x14001baf7  xor     edx, edx; PriorityBoost
0x14001baf9  mov     rcx, rbx; Irp
0x14001bafc  mov     qword ptr [rbx+38h], 4
0x14001bb04  mov     dword ptr [rbx+30h], 0
0x14001bb0b  call    cs:__imp_IofCompleteRequest
0x14001bb12  nop     dword ptr [rax+rax+00h]
0x14001bb17  xor     eax, eax
0x14001bb19  jmp     short loc_14001BB5E
0x14001bb1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb22  cmp     rcx, rdi
0x14001bb25  jz      short loc_14001BB43
0x14001bb27  mov     eax, [rcx+6Ch]
0x14001bb2a  test    al, 1
0x14001bb2c  jz      short loc_14001BB43
0x14001bb2e  mov     rcx, [rcx+58h]
0x14001bb32  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x14001bb39  mov     edx, 10h
0x14001bb3e  call    WPP_SF_
0x14001bb43  mov     edi, 0C0000010h
0x14001bb48  xor     edx, edx; PriorityBoost
0x14001bb4a  mov     [rbx+30h], edi
0x14001bb4d  mov     rcx, rbx; Irp
0x14001bb50  call    cs:__imp_IofCompleteRequest
0x14001bb57  nop     dword ptr [rax+rax+00h]
0x14001bb5c  mov     eax, edi
0x14001bb5e  add     rsp, 40h
0x14001bb62  pop     r15
0x14001bb64  pop     r14
0x14001bb66  pop     r12
0x14001bb68  pop     rdi
0x14001bb69  pop     rsi
0x14001bb6a  pop     rbp
0x14001bb6b  pop     rbx
0x14001bb6c  retn
```
