# CompleteIRPWithDevMgmtEvent

- ea: `0x140004604`
- end: `0x1400046af`
- name: `CompleteIRPWithDevMgmtEvent`
- size: `171`
- prototype: `__int64 __fastcall(PIRP Irp, size_t Size, int, const void *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001f10`
- `0x1400027b0`

## callees

- `0x14000324c`
- `0x140004604`
- `0x140006560`
- `0x1400065c0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140004669`
- `ntoskrnl!IofCompleteRequest` at `0x140004669`

## pseudocode

```c
__int64 __fastcall CompleteIRPWithDevMgmtEvent(PIRP Irp, size_t Size, int a3, const void *a4, __int64 a5)
{
  size_t v6; // rdi
  struct _IRP *MasterIrp; // rax

  v6 = (unsigned int)Size;
  if ( a5 )
    (*(void (__fastcall **)(__int64, const void *))(*(_QWORD *)a5 + 88LL))(a5, a4);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  *(_DWORD *)&MasterIrp->Type = a3;
  *(_DWORD *)(&MasterIrp->Size + 1) = v6;
  if ( a4 && (_DWORD)v6 )
    memmove(&Irp->AssociatedIrp.MasterIrp->MdlAddress, a4, v6);
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = (unsigned int)(v6 + 8);
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140004604  push    rbx
0x140004606  push    rbp
0x140004607  push    rsi
0x140004608  push    rdi
0x140004609  sub     rsp, 28h
0x14000460d  mov     rbx, rcx
0x140004610  mov     edi, edx
0x140004612  mov     rcx, [rsp+48h+arg_20]
0x140004617  mov     rsi, r9
0x14000461a  mov     ebp, r8d
0x14000461d  test    rcx, rcx
0x140004620  jz      short loc_140004631
0x140004622  mov     rax, [rcx]
0x140004625  mov     rdx, r9
0x140004628  mov     rax, [rax+58h]
0x14000462c  call    _guard_dispatch_icall
0x140004631  mov     rax, [rbx+18h]
0x140004635  mov     [rax], ebp
0x140004637  mov     [rax+4], edi
0x14000463a  test    rsi, rsi
0x14000463d  jz      short loc_140004656
0x14000463f  test    edi, edi
0x140004641  jz      short loc_140004656
0x140004643  mov     rcx, [rbx+18h]
0x140004647  mov     r8, rdi; Size
0x14000464a  add     rcx, 8; void *
0x14000464e  mov     rdx, rsi; Src
0x140004651  call    memmove
0x140004656  lea     ecx, [rdi+8]
0x140004659  mov     dword ptr [rbx+30h], 0
0x140004660  mov     [rbx+38h], rcx
0x140004664  xor     edx, edx; PriorityBoost
0x140004666  mov     rcx, rbx; Irp
0x140004669  call    cs:__imp_IofCompleteRequest
0x140004670  nop     dword ptr [rax+rax+00h]
0x140004675  mov     rcx, cs:WPP_GLOBAL_Control
0x14000467c  lea     rax, WPP_GLOBAL_Control
0x140004683  cmp     rcx, rax
0x140004686  jz      short loc_1400046A3
0x140004688  cmp     byte ptr [rcx+29h], 4
0x14000468c  jb      short loc_1400046A3
0x14000468e  mov     rcx, [rcx+18h]
0x140004692  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x140004699  mov     edx, 1Eh
0x14000469e  call    WPP_SF_
0x1400046a3  xor     eax, eax
0x1400046a5  add     rsp, 28h
0x1400046a9  pop     rdi
0x1400046aa  pop     rsi
0x1400046ab  pop     rbp
0x1400046ac  pop     rbx
0x1400046ad  retn
```
