# CldiStreamInsertIntoCancelSafeQueue

- ea: `0x1400419e8`
- end: `0x140041c5e`
- name: `CldiStreamInsertIntoCancelSafeQueue`
- size: `630`
- prototype: `__int64 __fastcall(void *, struct _FLT_CALLBACK_DATA *, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003fcb0`
- `0x140040090`
- `0x140082ba0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000d868`
- `0x1400419e8`
- `0x1400812d4`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140041a21`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140041a21`
- `FLTMGR!FltCbdqInsertIo` at `0x140041ac0`
- `FLTMGR!FltCbdqInsertIo` at `0x140041ac0`
- `FLTMGR!FltIsIoCanceled` at `0x140041b15`
- `FLTMGR!FltIsIoCanceled` at `0x140041b15`

## pseudocode

```c
__int64 __fastcall CldiStreamInsertIntoCancelSafeQueue(void *a1, struct _FLT_CALLBACK_DATA *a2, __int64 a3, _QWORD *a4)
{
  unsigned int v4; // esi
  _OWORD *v8; // rax
  volatile signed __int32 *v9; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rax
  PDEVICE_OBJECT p_QueueLinks; // rcx

  v4 = 0;
  if ( !a2 || (a2->Flags & 1) == 0 )
  {
    p_QueueLinks = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4);
    }
    if ( a2 && !a2->QueueContext[1] )
    {
      p_QueueLinks = (PDEVICE_OBJECT)&a2->QueueLinks;
      a2->QueueContext[1] = a1;
      a2->QueueLinks.Blink = &a2->QueueLinks;
      a2->QueueLinks.Flink = &a2->QueueLinks;
    }
    goto LABEL_31;
  }
  if ( a2->QueueContext[1] )
  {
    if ( FltIsIoCanceled(a2) )
    {
      v4 = -1073741536;
      HsmDbgBreakOnStatus(3221225760LL);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return v4;
      }
      v11 = 15;
LABEL_19:
      WPP_SF_qqqd(v10->AttachedDevice, v11, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4, v4);
      return v4;
    }
    v12 = (volatile signed __int32 *)a2->QueueContext[1];
    a4[12] = v12;
    _InterlockedIncrement(v12 + 8);
    p_QueueLinks = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4);
    }
LABEL_31:
    CldiStreamCdqINSERT_IO(p_QueueLinks, a2, a4);
    return v4;
  }
  v8 = ExAllocateFromPagedLookasideList(&stru_140028880);
  if ( !v8 )
  {
    v4 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v4;
    }
    v11 = 13;
    goto LABEL_19;
  }
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  a2->QueueContext[1] = v8;
  *(_QWORD *)v8 = a2;
  a2->QueueLinks.Blink = &a2->QueueLinks;
  a2->QueueLinks.Flink = &a2->QueueLinks;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4);
  }
  v9 = (volatile signed __int32 *)a2->QueueContext[1];
  a4[12] = v9;
  _InterlockedIncrement(v9 + 8);
  FltCbdqInsertIo(
    (PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) + 144LL),
    a2,
    (PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT)(a4[12] + 8LL),
    a4);
  return v4;
}

```

## disassembly

```asm
0x1400419e8  push    rbx
0x1400419ea  push    rsi
0x1400419eb  push    rdi
0x1400419ec  push    r14
0x1400419ee  sub     rsp, 48h
0x1400419f2  xor     esi, esi
0x1400419f4  mov     rdi, r9
0x1400419f7  mov     rbx, rdx
0x1400419fa  mov     r14, rcx
0x1400419fd  test    rdx, rdx
0x140041a00  jz      loc_140041BE8
0x140041a06  mov     eax, [rdx]
0x140041a08  test    al, 1
0x140041a0a  jz      loc_140041BE8
0x140041a10  cmp     [rdx+48h], rsi
0x140041a14  jnz     loc_140041B12
0x140041a1a  lea     rcx, stru_140028880; Lookaside
0x140041a21  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140041a28  nop     dword ptr [rax+rax+00h]
0x140041a2d  test    rax, rax
0x140041a30  jz      loc_140041AD1
0x140041a36  xorps   xmm0, xmm0
0x140041a39  movups  xmmword ptr [rax], xmm0
0x140041a3c  movups  xmmword ptr [rax+10h], xmm0
0x140041a40  movups  xmmword ptr [rax+20h], xmm0
0x140041a44  mov     [rbx+48h], rax
0x140041a48  mov     [rax], rbx
0x140041a4b  lea     rax, [rbx+30h]
0x140041a4f  mov     [rax+8], rax
0x140041a53  mov     [rax], rax
0x140041a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140041a5d  lea     rax, WPP_GLOBAL_Control
0x140041a64  cmp     rcx, rax
0x140041a67  jz      short loc_140041A98
0x140041a69  test    dword ptr [rcx+2Ch], 100h
0x140041a70  jz      short loc_140041A98
0x140041a72  cmp     byte ptr [rcx+29h], 4
0x140041a76  jb      short loc_140041A98
0x140041a78  mov     rcx, [rcx+18h]
0x140041a7c  lea     edx, [rsi+0Eh]
0x140041a7f  mov     [rsp+68h+var_40], rdi
0x140041a84  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041a8b  mov     r9, rbx
0x140041a8e  mov     [rsp+68h+var_48], r14
0x140041a93  call    WPP_SF_qqq
0x140041a98  mov     rax, [rbx+48h]
0x140041a9c  mov     [rdi+60h], rax
0x140041aa0  lock inc dword ptr [rax+20h]
0x140041aa4  mov     rax, [r14]
0x140041aa7  mov     r9, rdi; InsertContext
0x140041aaa  mov     r8, [rdi+60h]
0x140041aae  mov     rdx, rbx; Cbd
0x140041ab1  add     r8, 8; Context
0x140041ab5  mov     rcx, [rax+8]
0x140041ab9  add     rcx, 90h; Cbdq
0x140041ac0  call    cs:__imp_FltCbdqInsertIo
0x140041ac7  nop     dword ptr [rax+rax+00h]
0x140041acc  jmp     loc_140041C51
0x140041ad1  mov     esi, 0C000009Ah
0x140041ad6  mov     ecx, esi
0x140041ad8  call    HsmDbgBreakOnStatus
0x140041add  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ae4  lea     rax, WPP_GLOBAL_Control
0x140041aeb  cmp     rcx, rax
0x140041aee  jz      loc_140041C51
0x140041af4  test    dword ptr [rcx+2Ch], 100h
0x140041afb  jz      loc_140041C51
0x140041b01  cmp     byte ptr [rcx+29h], 2
0x140041b05  jb      loc_140041C51
0x140041b0b  mov     edx, 0Dh
0x140041b10  jmp     short loc_140041B64
0x140041b12  mov     rcx, rbx; CallbackData
0x140041b15  call    cs:__imp_FltIsIoCanceled
0x140041b1c  nop     dword ptr [rax+rax+00h]
0x140041b21  test    al, al
0x140041b23  jz      short loc_140041B8A
0x140041b25  mov     esi, 0C0000120h
0x140041b2a  mov     ecx, esi
0x140041b2c  call    HsmDbgBreakOnStatus
0x140041b31  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b38  lea     rax, WPP_GLOBAL_Control
0x140041b3f  cmp     rcx, rax
0x140041b42  jz      loc_140041C51
0x140041b48  test    dword ptr [rcx+2Ch], 100h
0x140041b4f  jz      loc_140041C51
0x140041b55  cmp     byte ptr [rcx+29h], 2
0x140041b59  jb      loc_140041C51
0x140041b5f  mov     edx, 0Fh
0x140041b64  mov     rcx, [rcx+18h]
0x140041b68  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041b6f  mov     [rsp+68h+var_38], esi
0x140041b73  mov     r9, rbx
0x140041b76  mov     [rsp+68h+var_40], rdi
0x140041b7b  mov     [rsp+68h+var_48], r14
0x140041b80  call    WPP_SF_qqqd
0x140041b85  jmp     loc_140041C51
0x140041b8a  mov     rax, [rbx+48h]
0x140041b8e  mov     [rdi+60h], rax
0x140041b92  lock inc dword ptr [rax+20h]
0x140041b96  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b9d  lea     rax, WPP_GLOBAL_Control
0x140041ba4  cmp     rcx, rax
0x140041ba7  jz      loc_140041C46
0x140041bad  test    dword ptr [rcx+2Ch], 100h
0x140041bb4  jz      loc_140041C46
0x140041bba  cmp     byte ptr [rcx+29h], 4
0x140041bbe  jb      loc_140041C46
0x140041bc4  mov     rcx, [rcx+18h]
0x140041bc8  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041bcf  mov     edx, 10h
0x140041bd4  mov     [rsp+68h+var_40], rdi
0x140041bd9  mov     r9, rbx
0x140041bdc  mov     [rsp+68h+var_48], r14
0x140041be1  call    WPP_SF_qqq
0x140041be6  jmp     short loc_140041C46
0x140041be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140041bef  lea     rax, WPP_GLOBAL_Control
0x140041bf6  cmp     rcx, rax
0x140041bf9  jz      short loc_140041C2C
0x140041bfb  test    dword ptr [rcx+2Ch], 100h
0x140041c02  jz      short loc_140041C2C
0x140041c04  cmp     byte ptr [rcx+29h], 4
0x140041c08  jb      short loc_140041C2C
0x140041c0a  mov     rcx, [rcx+18h]
0x140041c0e  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041c15  mov     edx, 11h
0x140041c1a  mov     [rsp+68h+var_40], rdi
0x140041c1f  mov     r9, rbx
0x140041c22  mov     [rsp+68h+var_48], r14
0x140041c27  call    WPP_SF_qqq
0x140041c2c  test    rbx, rbx
0x140041c2f  jz      short loc_140041C46
0x140041c31  cmp     [rbx+48h], rsi
0x140041c35  jnz     short loc_140041C46
0x140041c37  lea     rcx, [rbx+30h]
0x140041c3b  mov     [rbx+48h], r14
0x140041c3f  mov     [rcx+8], rcx
0x140041c43  mov     [rcx], rcx
0x140041c46  mov     r8, rdi
0x140041c49  mov     rdx, rbx
0x140041c4c  call    CldiStreamCdqINSERT_IO
0x140041c51  mov     eax, esi
0x140041c53  add     rsp, 48h
0x140041c57  pop     r14
0x140041c59  pop     rdi
0x140041c5a  pop     rsi
0x140041c5b  pop     rbx
0x140041c5c  retn
```
