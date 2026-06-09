# DrSession::SendCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140027d50`
- end: `0x140027f1b`
- name: `?SendCompletionRoutine@DrSession@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `459`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001660`
- `0x14000324c`
- `0x14000327c`
- `0x140006560`
- `0x1400111d0`
- `0x140027d50`
- `0x14002a100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140027e10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027f0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027e10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027f0a`
- `ntoskrnl!IoFreeIrp` at `0x140027dd5`
- `ntoskrnl!IoFreeIrp` at `0x140027dd5`

## pseudocode

```c
__int64 __fastcall DrSession::SendCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, unsigned int *a3)
{
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, IO_STATUS_BLOCK *); // rcx
  DrSession *v6; // rbp
  int v7; // eax
  void *v8; // rcx
  RefCount *v9; // rcx
  __int64 (__fastcall *v11)(_QWORD, IO_STATUS_BLOCK *); // rax

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        56,
        WPP_5c887063686c325024567ba4647d07cf_Traceguids,
        (unsigned int)a2->IoStatus.Status);
    v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, IO_STATUS_BLOCK *))*((_QWORD *)a3 + 5);
    v6 = (DrSession *)*((_QWORD *)a3 + 2);
    if ( v5 )
    {
      v7 = (**v5)(v5, *((_QWORD *)a3 + 4), &a2->IoStatus);
    }
    else
    {
      v11 = (__int64 (__fastcall *)(_QWORD, IO_STATUS_BLOCK *))*((_QWORD *)a3 + 6);
      if ( !v11 )
        goto LABEL_6;
      v7 = v11(*((_QWORD *)a3 + 4), &a2->IoStatus);
    }
    if ( (v7 & 0xC0000000) == 0xC0000000 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
      DrSession::ChannelIoFailed(v6);
      goto LABEL_7;
    }
LABEL_6:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
LABEL_7:
    IoFreeIrp(a2);
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_5c887063686c325024567ba4647d07cf_Traceguids, *a3);
  DrSession::SendCompletion(*((DrSession **)a3 + 2), (struct tagWriteContext *)a3, (struct _IO_STATUS_BLOCK *)a3);
LABEL_8:
  v8 = (void *)*((_QWORD *)a3 + 3);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  v9 = (RefCount *)*((_QWORD *)a3 + 2);
  if ( v9 )
    RefCount::Release(v9);
  ExFreePoolWithTag(a3, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140027d50  push    rbx
0x140027d52  sub     rsp, 20h
0x140027d56  mov     [rsp+28h+arg_8], rsi
0x140027d5b  mov     rbx, r8
0x140027d5e  mov     [rsp+28h+arg_10], rdi
0x140027d63  mov     rdi, rdx
0x140027d66  test    rdx, rdx
0x140027d69  jz      loc_140027EC3
0x140027d6f  mov     [rsp+28h+arg_0], rbp
0x140027d74  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d7b  lea     rsi, WPP_GLOBAL_Control
0x140027d82  cmp     rcx, rsi
0x140027d85  jnz     loc_140027E28
0x140027d8b  mov     rcx, [rbx+28h]
0x140027d8f  lea     rdx, [rdi+30h]
0x140027d93  mov     rbp, [rbx+10h]
0x140027d97  test    rcx, rcx
0x140027d9a  jz      loc_140027E50
0x140027da0  mov     rax, [rcx]
0x140027da3  mov     r8, rdx
0x140027da6  mov     rdx, [rbx+20h]
0x140027daa  mov     rax, [rax]
0x140027dad  call    _guard_dispatch_icall
0x140027db2  and     eax, 0C0000000h
0x140027db7  cmp     eax, 0C0000000h
0x140027dbc  jz      loc_140027E6B
0x140027dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140027dc9  cmp     rcx, rsi
0x140027dcc  jnz     loc_140027E9F
0x140027dd2  mov     rcx, rdi; Irp
0x140027dd5  call    cs:__imp_IoFreeIrp
0x140027ddc  nop     dword ptr [rax+rax+00h]
0x140027de1  mov     rbp, [rsp+28h+arg_0]
0x140027de6  mov     rcx, [rbx+18h]; P
0x140027dea  mov     rdi, [rsp+28h+arg_10]
0x140027def  mov     rsi, [rsp+28h+arg_8]
0x140027df4  test    rcx, rcx
0x140027df7  jnz     loc_140027F08
0x140027dfd  mov     rcx, [rbx+10h]; this
0x140027e01  test    rcx, rcx
0x140027e04  jz      short loc_140027E0B
0x140027e06  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140027e0b  xor     edx, edx; Tag
0x140027e0d  mov     rcx, rbx; P
0x140027e10  call    cs:__imp_ExFreePoolWithTag
0x140027e17  nop     dword ptr [rax+rax+00h]
0x140027e1c  mov     eax, 0C0000016h
0x140027e21  add     rsp, 20h
0x140027e25  pop     rbx
0x140027e26  retn
0x140027e28  cmp     byte ptr [rcx+29h], 4
0x140027e2c  jb      loc_140027D8B
0x140027e32  mov     r9d, [rdi+30h]
0x140027e36  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140027e3d  mov     rcx, [rcx+18h]
0x140027e41  mov     edx, 38h ; '8'
0x140027e46  call    WPP_SF_d
0x140027e4b  jmp     loc_140027D8B
0x140027e50  mov     rax, [rbx+30h]
0x140027e54  test    rax, rax
0x140027e57  jz      loc_140027DC2
0x140027e5d  mov     rcx, [rbx+20h]
0x140027e61  call    _guard_dispatch_icall
0x140027e66  jmp     loc_140027DB2
0x140027e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027e72  cmp     rcx, rsi
0x140027e75  jz      short loc_140027E92
0x140027e77  cmp     byte ptr [rcx+29h], 4
0x140027e7b  jb      short loc_140027E92
0x140027e7d  mov     rcx, [rcx+18h]
0x140027e81  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140027e88  mov     edx, 3Bh ; ';'
0x140027e8d  call    WPP_SF_
0x140027e92  mov     rcx, rbp; this
0x140027e95  call    ?ChannelIoFailed@DrSession@@AEAAXXZ; DrSession::ChannelIoFailed(void)
0x140027e9a  jmp     loc_140027DD2
0x140027e9f  cmp     byte ptr [rcx+29h], 4
0x140027ea3  jb      loc_140027DD2
0x140027ea9  mov     rcx, [rcx+18h]
0x140027ead  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140027eb4  mov     edx, 3Ah ; ':'
0x140027eb9  call    WPP_SF_
0x140027ebe  jmp     loc_140027DD2
0x140027ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140027eca  lea     rsi, WPP_GLOBAL_Control
0x140027ed1  cmp     rcx, rsi
0x140027ed4  jz      short loc_140027EF4
0x140027ed6  cmp     byte ptr [rcx+29h], 4
0x140027eda  jb      short loc_140027EF4
0x140027edc  mov     r9d, [r8]
0x140027edf  mov     edx, 39h ; '9'
0x140027ee4  mov     rcx, [rcx+18h]
0x140027ee8  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140027eef  call    WPP_SF_d
0x140027ef4  mov     rcx, [rbx+10h]; this
0x140027ef8  mov     r8, rbx; struct _IO_STATUS_BLOCK *
0x140027efb  mov     rdx, rbx; struct tagWriteContext *
0x140027efe  call    ?SendCompletion@DrSession@@AEAAXPEAUtagWriteContext@@PEAU_IO_STATUS_BLOCK@@@Z; DrSession::SendCompletion(tagWriteContext *,_IO_STATUS_BLOCK *)
0x140027f03  jmp     loc_140027DE6
0x140027f08  xor     edx, edx; Tag
0x140027f0a  call    cs:__imp_ExFreePoolWithTag
0x140027f11  nop     dword ptr [rax+rax+00h]
0x140027f16  jmp     loc_140027DFD
```
