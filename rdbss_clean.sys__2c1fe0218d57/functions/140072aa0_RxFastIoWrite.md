# RxFastIoWrite

- ea: `0x140072aa0`
- end: `0x140072d10`
- name: `RxFastIoWrite`
- size: `624`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, ULONG Length@<r8d>, int, PVOID, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14000ba60`
- `0x140016900`
- `0x140017280`
- `0x140017310`
- `0x14001cca0`
- `0x14001d190`
- `0x140072aa0`
- `0x140072d20`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140072b39`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140072b39`

## pseudocode

```c
char __fastcall RxFastIoWrite(
        PFILE_OBJECT FileObject,
        LARGE_INTEGER FileOffset,
        __int64 Length,
        BOOLEAN a4,
        int a5,
        PVOID Buffer,
        unsigned int *a7,
        __int64 a8)
{
  ULONG v9; // edi
  int v12; // edx
  int v13; // r8d
  int Timer_high; // edx
  char v15; // di
  int v16; // r8d
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-78h]
  __int128 Irp; // [rsp+50h] [rbp-48h] BYREF
  __m128i si128; // [rsp+60h] [rbp-38h]
  PIRP TopLevelIrp; // [rsp+70h] [rbp-28h]

  Irp = 0;
  TopLevelIrp = 0;
  si128 = 0;
  v9 = Length;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqiD(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      Length,
      FileObject,
      FileObject->FsContext,
      *(_QWORD *)FileOffset.QuadPart,
      Length);
  }
  if ( (*(_DWORD *)(*((_QWORD *)FileObject->FsContext2 + 4) + 72LL) & 2) != 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      return 0;
    }
    v19 = 15;
    goto LABEL_26;
  }
  if ( !RxIsThisTheTopLevelIrp(0) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      return 0;
    }
    v19 = 16;
LABEL_26:
    WPP_SF_(v18->AttachedDevice, v19, &WPP_1b57de22b73d3f557c58b461499d9993_Traceguids);
    return 0;
  }
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 4) != 0 )
  {
    LOWORD(v20) = FileObject->FileName.Length >> 1;
    McTemplateK0phzr1h_EtwWriteTransfer(
      (unsigned __int16)v20,
      v12,
      v13,
      (_DWORD)FileObject,
      v20,
      (__int64)FileObject->FileName.Buffer);
  }
  TopLevelIrp = IoGetTopLevelIrp();
  *((_QWORD *)&Irp + 1) = a8;
  *(_QWORD *)&Irp = 1280604242;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v15 = RxFastCopyWrite(FileObject, FileOffset, v9, a4, a5, Buffer, a7, a8, (PIRP)&Irp);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_1b57de22b73d3f557c58b461499d9993_Traceguids, *a7, a7[2]);
    }
  }
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 4) != 0 )
    McTemplateK0phzr1hq_EtwWriteTransfer(
      FileObject->FileName.Length >> 1,
      Timer_high,
      v16,
      (_DWORD)FileObject,
      FileObject->FileName.Length >> 1,
      (__int64)FileObject->FileName.Buffer,
      4,
      v15);
  return v15;
}

```

## disassembly

```asm
0x140072aa0  mov     [rsp+arg_10], rbx
0x140072aa5  mov     [rsp+arg_18], rbp
0x140072aaa  push    rsi
0x140072aab  push    rdi
0x140072aac  push    r15
0x140072aae  sub     rsp, 80h
0x140072ab5  xorps   xmm0, xmm0
0x140072ab8  xor     eax, eax
0x140072aba  movups  [rsp+98h+var_48], xmm0
0x140072abf  mov     [rsp+98h+var_28], rax
0x140072ac4  movzx   ebp, r9b
0x140072ac8  movups  [rsp+98h+var_38], xmm0
0x140072acd  mov     edi, r8d
0x140072ad0  mov     rsi, rdx
0x140072ad3  mov     rbx, rcx
0x140072ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x140072add  lea     r15, WPP_GLOBAL_Control
0x140072ae4  cmp     rcx, r15
0x140072ae7  jz      short loc_140072AF4
0x140072ae9  mov     eax, [rcx+2Ch]
0x140072aec  test    al, 10h
0x140072aee  jnz     loc_140072C6D
0x140072af4  mov     rax, [rbx+20h]
0x140072af8  mov     rcx, [rax+20h]
0x140072afc  mov     eax, [rcx+48h]
0x140072aff  test    al, 2
0x140072b01  jnz     loc_140072CA2
0x140072b07  xor     ecx, ecx; Irp
0x140072b09  call    RxIsThisTheTopLevelIrp
0x140072b0e  test    al, al
0x140072b10  jz      loc_140072C31
0x140072b16  mov     [rsp+98h+arg_0], r12
0x140072b1e  mov     r12d, 4
0x140072b24  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, r12b
0x140072b2b  mov     [rsp+98h+arg_8], r14
0x140072b33  jnz     loc_140072C45
0x140072b39  call    cs:__imp_IoGetTopLevelIrp
0x140072b40  nop     dword ptr [rax+rax+00h]
0x140072b45  mov     rcx, [rsp+98h+arg_38]
0x140072b4d  movzx   r9d, bpl
0x140072b51  movdqa  xmm0, cs:__xmm@00000000000000040000000000000000
0x140072b59  mov     r8d, edi; Length
0x140072b5c  mov     r14, [rsp+98h+arg_30]
0x140072b64  mov     rdx, rsi; FileOffset
0x140072b67  mov     [rsp+98h+var_28], rax
0x140072b6c  lea     rax, [rsp+98h+var_48]
0x140072b71  mov     [rsp+98h+Irp], rax; Irp
0x140072b76  mov     rax, [rsp+98h+arg_28]
0x140072b7e  mov     [rsp+98h+var_60], rcx; __int64
0x140072b83  mov     [rsp+98h+var_68], r14; __int64
0x140072b88  mov     [rsp+98h+Buffer], rax; Buffer
0x140072b8d  mov     eax, [rsp+98h+arg_20]
0x140072b94  mov     qword ptr [rsp+98h+var_48+8], rcx
0x140072b99  mov     rcx, rbx; FileObject
0x140072b9c  mov     [rsp+98h+var_78], eax; int
0x140072ba0  mov     qword ptr [rsp+98h+var_48], 4C547852h
0x140072ba9  movdqu  [rsp+98h+var_38], xmm0
0x140072baf  call    RxFastCopyWrite
0x140072bb4  movzx   edi, al
0x140072bb7  test    al, al
0x140072bb9  jnz     short loc_140072BF5
0x140072bbb  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, r12b
0x140072bc2  mov     r14, [rsp+98h+arg_8]
0x140072bca  jnz     loc_140072CE4
0x140072bd0  mov     r12, [rsp+98h+arg_0]
0x140072bd8  movzx   eax, dil
0x140072bdc  lea     r11, [rsp+98h+var_18]
0x140072be4  mov     rbx, [r11+30h]
0x140072be8  mov     rbp, [r11+38h]
0x140072bec  mov     rsp, r11
0x140072bef  pop     r15
0x140072bf1  pop     rdi
0x140072bf2  pop     rsi
0x140072bf3  retn
0x140072bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x140072bfc  cmp     rcx, r15
0x140072bff  jz      short loc_140072BBB
0x140072c01  mov     edx, [rcx+2Ch]
0x140072c04  test    dl, 10h
0x140072c07  jz      short loc_140072BBB
0x140072c09  cmp     byte ptr [rcx+29h], 2
0x140072c0d  jb      short loc_140072BBB
0x140072c0f  mov     eax, [r14+8]
0x140072c13  lea     r8, WPP_1b57de22b73d3f557c58b461499d9993_Traceguids
0x140072c1a  mov     r9d, [r14]
0x140072c1d  mov     edx, 11h
0x140072c22  mov     rcx, [rcx+18h]
0x140072c26  mov     [rsp+98h+var_78], eax
0x140072c2a  call    WPP_SF_Dd
0x140072c2f  jmp     short loc_140072BBB
0x140072c31  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c38  cmp     rcx, r15
0x140072c3b  jnz     loc_140072CC5
0x140072c41  xor     al, al
0x140072c43  jmp     short loc_140072BDC
0x140072c45  movzx   ecx, word ptr [rbx+58h]
0x140072c49  mov     r9, rbx
0x140072c4c  mov     rax, [rbx+60h]
0x140072c50  shr     cx, 1
0x140072c53  mov     word ptr [rsp+98h+var_68], r12w
0x140072c59  mov     [rsp+98h+Buffer], rax
0x140072c5e  mov     word ptr [rsp+98h+var_78], cx
0x140072c63  call    McTemplateK0phzr1h_EtwWriteTransfer
0x140072c68  jmp     loc_140072B39
0x140072c6d  cmp     byte ptr [rcx+29h], 2
0x140072c71  jb      loc_140072AF4
0x140072c77  mov     rax, [rsi]
0x140072c7a  mov     edx, 0Eh
0x140072c7f  mov     rcx, [rcx+18h]
0x140072c83  mov     r9, rbx
0x140072c86  mov     dword ptr [rsp+98h+var_68], edi
0x140072c8a  mov     [rsp+98h+Buffer], rax
0x140072c8f  mov     rax, [rbx+18h]
0x140072c93  mov     qword ptr [rsp+98h+var_78], rax
0x140072c98  call    WPP_SF_qqiD
0x140072c9d  jmp     loc_140072AF4
0x140072ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ca9  cmp     rcx, r15
0x140072cac  jz      short loc_140072C41
0x140072cae  mov     eax, [rcx+2Ch]
0x140072cb1  test    al, 10h
0x140072cb3  jz      short loc_140072C41
0x140072cb5  cmp     byte ptr [rcx+29h], 4
0x140072cb9  jb      short loc_140072C41
0x140072cbb  mov     edx, 0Fh
0x140072cc0  jmp     loc_14007F8C0
0x140072cc5  mov     eax, [rcx+2Ch]
0x140072cc8  test    al, 10h
0x140072cca  jz      loc_140072C41
0x140072cd0  cmp     byte ptr [rcx+29h], 4
0x140072cd4  jb      loc_140072C41
0x140072cda  mov     edx, 10h
0x140072cdf  jmp     loc_14007F8C0
0x140072ce4  movzx   ecx, word ptr [rbx+58h]
0x140072ce8  mov     r9, rbx
0x140072ceb  mov     rax, [rbx+60h]
0x140072cef  mov     dword ptr [rsp+98h+var_60], edi
0x140072cf3  shr     cx, 1
0x140072cf6  mov     word ptr [rsp+98h+var_68], r12w
0x140072cfc  mov     [rsp+98h+Buffer], rax
0x140072d01  mov     word ptr [rsp+98h+var_78], cx
0x140072d06  call    McTemplateK0phzr1hq_EtwWriteTransfer
0x140072d0b  jmp     loc_140072BD0
0x14007f8c0  mov     rcx, [rcx+18h]
0x14007f8c4  lea     r8, WPP_1b57de22b73d3f557c58b461499d9993_Traceguids
0x14007f8cb  call    WPP_SF_
0x14007f8d0  nop
0x14007f8d1  jmp     loc_140072C41
```
