# RxFastIoRead

- ea: `0x140062e70`
- end: `0x140063080`
- name: `RxFastIoRead`
- size: `528`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, int, PVOID, PIO_STATUS_BLOCK, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000ba60`
- `0x140016900`
- `0x140017310`
- `0x14001cca0`
- `0x14001d190`
- `0x140062e70`
- `0x140063090`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140062ef6`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140062ef6`

## pseudocode

```c
char __fastcall RxFastIoRead(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        __int64 a3,
        BOOLEAN a4,
        int a5,
        PVOID a6,
        PIO_STATUS_BLOCK a7,
        __int64 a8)
{
  unsigned int v9; // ebx
  int v12; // edx
  int v13; // r8d
  int Timer_high; // edx
  char v15; // bl
  int v16; // r8d
  int v18; // [rsp+20h] [rbp-78h]
  __int64 v19; // [rsp+38h] [rbp-60h]
  __int128 Irp; // [rsp+50h] [rbp-48h] BYREF
  __m128i si128; // [rsp+60h] [rbp-38h]
  PIRP TopLevelIrp; // [rsp+70h] [rbp-28h]

  Irp = 0;
  TopLevelIrp = 0;
  si128 = 0;
  v9 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqiD(WPP_GLOBAL_Control->AttachedDevice, 12, a3, FileObject, FileObject->FsContext, FileOffset->QuadPart, a3);
  }
  if ( !RxIsThisTheTopLevelIrp(0) )
    return 0;
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 4) != 0 )
  {
    LOWORD(v18) = FileObject->FileName.Length >> 1;
    McTemplateK0phzr1h_EtwWriteTransfer(
      (unsigned __int16)v18,
      v12,
      v13,
      (_DWORD)FileObject,
      v18,
      (__int64)FileObject->FileName.Buffer);
  }
  TopLevelIrp = IoGetTopLevelIrp();
  *((_QWORD *)&Irp + 1) = a8;
  *(_QWORD *)&Irp = 1280604242;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v15 = RxFastCopyRead(FileObject, FileOffset, v9, a4, a5, a6, a7, v19, (PIRP)&Irp);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_1b57de22b73d3f557c58b461499d9993_Traceguids,
          (unsigned int)a7->Status,
          a7->Information);
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
      3,
      v15);
  return v15;
}

```

## disassembly

```asm
0x140062e70  mov     [rsp+arg_10], rbx
0x140062e75  mov     [rsp+arg_18], rbp
0x140062e7a  push    rsi
0x140062e7b  push    rdi
0x140062e7c  push    r15
0x140062e7e  sub     rsp, 80h
0x140062e85  xorps   xmm0, xmm0
0x140062e88  xor     eax, eax
0x140062e8a  movups  [rsp+98h+var_48], xmm0
0x140062e8f  mov     [rsp+98h+var_28], rax
0x140062e94  movzx   esi, r9b
0x140062e98  movups  [rsp+98h+var_38], xmm0
0x140062e9d  mov     ebx, r8d
0x140062ea0  mov     rdi, rdx
0x140062ea3  mov     rbp, rcx
0x140062ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x140062ead  lea     r15, WPP_GLOBAL_Control
0x140062eb4  cmp     rcx, r15
0x140062eb7  jz      short loc_140062EC4
0x140062eb9  mov     eax, [rcx+2Ch]
0x140062ebc  test    al, 10h
0x140062ebe  jnz     loc_140062FF0
0x140062ec4  xor     ecx, ecx; Irp
0x140062ec6  call    RxIsThisTheTopLevelIrp
0x140062ecb  test    al, al
0x140062ecd  jz      loc_140062FC4
0x140062ed3  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 4
0x140062eda  mov     [rsp+98h+arg_0], r12
0x140062ee2  mov     r12d, 3
0x140062ee8  mov     [rsp+98h+arg_8], r14
0x140062ef0  jnz     loc_140062FC8
0x140062ef6  call    cs:__imp_IoGetTopLevelIrp
0x140062efd  nop     dword ptr [rax+rax+00h]
0x140062f02  mov     rcx, [rsp+98h+arg_38]
0x140062f0a  movzx   r9d, sil
0x140062f0e  movdqa  xmm0, cs:__xmm@00000000000000040000000000000000
0x140062f16  mov     r8d, ebx
0x140062f19  mov     r14, [rsp+98h+arg_30]
0x140062f21  mov     rdx, rdi; FileOffset
0x140062f24  mov     [rsp+98h+var_28], rax
0x140062f29  lea     rax, [rsp+98h+var_48]
0x140062f2e  mov     [rsp+98h+Irp], rax; Irp
0x140062f33  mov     rax, [rsp+98h+arg_28]
0x140062f3b  mov     [rsp+98h+var_68], r14; PIO_STATUS_BLOCK
0x140062f40  mov     [rsp+98h+var_70], rax; PVOID
0x140062f45  mov     eax, [rsp+98h+arg_20]
0x140062f4c  mov     qword ptr [rsp+98h+var_48+8], rcx
0x140062f51  mov     rcx, rbp; FileObject
0x140062f54  mov     [rsp+98h+var_78], eax; int
0x140062f58  mov     qword ptr [rsp+98h+var_48], 4C547852h
0x140062f61  movdqu  [rsp+98h+var_38], xmm0
0x140062f67  call    RxFastCopyRead
0x140062f6c  movzx   ebx, al
0x140062f6f  test    al, al
0x140062f71  jz      short loc_140062F8B
0x140062f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f7a  cmp     rcx, r15
0x140062f7d  jz      short loc_140062F8B
0x140062f7f  mov     edx, [rcx+2Ch]
0x140062f82  test    dl, 10h
0x140062f85  jnz     loc_140063025
0x140062f8b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 4
0x140062f92  mov     r14, [rsp+98h+arg_8]
0x140062f9a  jnz     loc_140063054
0x140062fa0  mov     r12, [rsp+98h+arg_0]
0x140062fa8  movzx   eax, bl
0x140062fab  lea     r11, [rsp+98h+var_18]
0x140062fb3  mov     rbx, [r11+30h]
0x140062fb7  mov     rbp, [r11+38h]
0x140062fbb  mov     rsp, r11
0x140062fbe  pop     r15
0x140062fc0  pop     rdi
0x140062fc1  pop     rsi
0x140062fc2  retn
0x140062fc4  xor     al, al
0x140062fc6  jmp     short loc_140062FAB
0x140062fc8  movzx   ecx, word ptr [rbp+58h]
0x140062fcc  mov     r9, rbp
0x140062fcf  mov     rax, [rbp+60h]
0x140062fd3  shr     cx, 1
0x140062fd6  mov     word ptr [rsp+98h+var_68], r12w
0x140062fdc  mov     [rsp+98h+var_70], rax
0x140062fe1  mov     word ptr [rsp+98h+var_78], cx
0x140062fe6  call    McTemplateK0phzr1h_EtwWriteTransfer
0x140062feb  jmp     loc_140062EF6
0x140062ff0  cmp     byte ptr [rcx+29h], 2
0x140062ff4  jb      loc_140062EC4
0x140062ffa  mov     rax, [rdi]
0x140062ffd  mov     edx, 0Ch
0x140063002  mov     rcx, [rcx+18h]
0x140063006  mov     r9, rbp
0x140063009  mov     dword ptr [rsp+98h+var_68], ebx
0x14006300d  mov     [rsp+98h+var_70], rax
0x140063012  mov     rax, [rbp+18h]
0x140063016  mov     qword ptr [rsp+98h+var_78], rax
0x14006301b  call    WPP_SF_qqiD
0x140063020  jmp     loc_140062EC4
0x140063025  cmp     byte ptr [rcx+29h], 2
0x140063029  jb      loc_140062F8B
0x14006302f  mov     eax, [r14+8]
0x140063033  lea     r8, WPP_1b57de22b73d3f557c58b461499d9993_Traceguids
0x14006303a  mov     r9d, [r14]
0x14006303d  mov     edx, 0Dh
0x140063042  mov     rcx, [rcx+18h]
0x140063046  mov     [rsp+98h+var_78], eax
0x14006304a  call    WPP_SF_Dd
0x14006304f  jmp     loc_140062F8B
0x140063054  movzx   ecx, word ptr [rbp+58h]
0x140063058  mov     r9, rbp
0x14006305b  mov     rax, [rbp+60h]
0x14006305f  mov     dword ptr [rsp+98h+var_60], ebx
0x140063063  shr     cx, 1
0x140063066  mov     word ptr [rsp+98h+var_68], r12w
0x14006306c  mov     [rsp+98h+var_70], rax
0x140063071  mov     word ptr [rsp+98h+var_78], cx
0x140063076  call    McTemplateK0phzr1hq_EtwWriteTransfer
0x14006307b  jmp     loc_140062FA0
```
