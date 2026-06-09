# FatCommonSetVolumeInfo

- ea: `0x14004a7e8`
- end: `0x14004a8e6`
- name: `FatCommonSetVolumeInfo`
- size: `254`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400438e0`
- `0x14004a9b0`

## callees

- `0x140007408`
- `0x14002486c`
- `0x140038eb4`
- `0x14003d880`
- `0x1400466c8`
- `0x14004a1d4`
- `0x14004a7e8`
- `0x14004ab20`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14004a8d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ff22`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a8d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ff22`

## pseudocode

```c
__int64 __fastcall FatCommonSetVolumeInfo(PVOID Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  ULONG Options; // edi
  int v6; // eax
  __int64 v7; // r9
  PVOID v8; // rcx
  unsigned int v9; // edi
  struct _ERESOURCE *v11; // r14
  _QWORD v12[6]; // [rsp+28h] [rbp-30h] BYREF
  struct _ERESOURCE *v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v12[0] = 0;
  v14 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v6 = FatDecodeFileObject(CurrentStackLocation->FileObject, &v13, v12, &v14);
  v8 = Entry;
  if ( v6 != 4 )
  {
    v9 = -1073741790;
LABEL_3:
    FatCompleteRequest_Real(v8, Irp, v9, v7);
    return v9;
  }
  v11 = v13;
  if ( (unsigned __int8)FatAcquireExclusiveVcb_Real(Entry, v13, 0, v7) )
  {
    FatVerifyFcb(Entry, v11[2].SystemResourcesList.Flink);
    if ( Options == 2 )
      v9 = FatSetFsLabelInfo((int)Entry);
    else
      v9 = -1073741811;
    FatUnpinRepinnedBcbs((__int64)Entry);
    ExReleaseResourceLite(v11 + 5);
    v8 = Entry;
    goto LABEL_3;
  }
  return FatFsdPostRequest(Entry, Irp);
}

```

## disassembly

```asm
0x14004a7e8  mov     rax, rsp
0x14004a7eb  mov     [rax+10h], rdx
0x14004a7ef  mov     [rax+8], rcx
0x14004a7f3  push    rbx
0x14004a7f4  push    rsi
0x14004a7f5  push    rdi
0x14004a7f6  push    r14
0x14004a7f8  push    r15
0x14004a7fa  sub     rsp, 30h
0x14004a7fe  mov     rsi, rdx
0x14004a801  mov     rbx, rcx
0x14004a804  mov     qword ptr [rax+18h], 0
0x14004a80c  mov     qword ptr [rax-30h], 0
0x14004a814  mov     qword ptr [rax+20h], 0
0x14004a81c  mov     rcx, [rdx+0B8h]
0x14004a823  mov     edi, [rcx+10h]
0x14004a826  mov     r15, [rdx+18h]
0x14004a82a  lea     r9, [rax+20h]
0x14004a82e  lea     r8, [rax-30h]
0x14004a832  lea     rdx, [rax+18h]
0x14004a836  mov     rcx, [rcx+30h]
0x14004a83a  call    FatDecodeFileObject
0x14004a83f  mov     rcx, rbx; Entry
0x14004a842  cmp     eax, 4
0x14004a845  jz      short loc_14004A866
0x14004a847  mov     edi, 0C0000022h
0x14004a84c  mov     rdx, rsi; Irp
0x14004a84f  mov     r8d, edi
0x14004a852  call    FatCompleteRequest_Real
0x14004a857  mov     eax, edi
0x14004a859  add     rsp, 30h
0x14004a85d  pop     r15
0x14004a85f  pop     r14
0x14004a861  pop     rdi
0x14004a862  pop     rsi
0x14004a863  pop     rbx
0x14004a864  retn
0x14004a866  mov     [rsp+58h+var_38], 0
0x14004a86e  xor     r8d, r8d
0x14004a871  mov     r14, [rsp+58h+arg_10]
0x14004a876  mov     rdx, r14
0x14004a879  call    FatAcquireExclusiveVcb_Real
0x14004a87e  test    al, al
0x14004a880  jnz     short loc_14004A88F
0x14004a882  mov     rdx, rsi; Context2
0x14004a885  mov     rcx, rbx; Context1
0x14004a888  call    FatFsdPostRequest
0x14004a88d  jmp     short loc_14004A859
0x14004a88f  mov     rdx, [r14+0D0h]
0x14004a896  mov     rcx, rbx
0x14004a899  call    FatVerifyFcb
0x14004a89e  cmp     edi, 2
0x14004a8a1  jz      short loc_14004A8AE
0x14004a8a3  mov     edi, 0C000000Dh
0x14004a8a8  mov     [rsp+58h+var_38], edi
0x14004a8ac  jmp     short loc_14004A8C2
0x14004a8ae  mov     r8, r15
0x14004a8b1  mov     rdx, r14
0x14004a8b4  mov     rcx, rbx; int
0x14004a8b7  call    FatSetFsLabelInfo
0x14004a8bc  mov     edi, eax
0x14004a8be  mov     [rsp+58h+var_38], eax
0x14004a8c2  mov     rcx, rbx
0x14004a8c5  call    FatUnpinRepinnedBcbs
0x14004a8ca  nop
0x14004a8cb  lea     rcx, [r14+208h]; Resource
0x14004a8d2  call    cs:__imp_ExReleaseResourceLite
0x14004a8d9  nop     dword ptr [rax+rax+00h]
0x14004a8de  mov     rcx, rbx
0x14004a8e1  jmp     loc_14004A84C
0x14005ff0a  push    rbx
0x14005ff0c  push    rbp
0x14005ff0d  sub     rsp, 28h
0x14005ff11  mov     rbp, rdx
0x14005ff14  movzx   ebx, cl
0x14005ff17  mov     rcx, [rbp+70h]
0x14005ff1b  add     rcx, 208h; Resource
0x14005ff22  call    cs:__imp_ExReleaseResourceLite
0x14005ff29  nop     dword ptr [rax+rax+00h]
0x14005ff2e  mov     eax, ebx
0x14005ff30  test    bl, bl
0x14005ff32  jnz     short loc_14005FF46
0x14005ff34  mov     r8d, [rbp+20h]
0x14005ff38  mov     rdx, [rbp+68h]; Irp
0x14005ff3c  mov     rcx, [rbp+60h]; Entry
0x14005ff40  call    FatCompleteRequest_Real
0x14005ff45  nop
0x14005ff46  add     rsp, 28h
0x14005ff4a  pop     rbp
0x14005ff4b  pop     rbx
0x14005ff4c  retn
```
