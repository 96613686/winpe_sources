# FltpManualDeviceAttachWorker

- ea: `0x1800778a0`
- end: `0x180077b7a`
- name: `FltpManualDeviceAttachWorker`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180051250`

## callees

- `0x180009f20`
- `0x180014c10`
- `0x1800247a0`
- `0x180067920`
- `0x1800778a0`
- `0x180078690`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180077a45`
- `ntoskrnl!ObfDereferenceObject` at `0x180077a75`
- `ntoskrnl!ObfDereferenceObject` at `0x180077a45`
- `ntoskrnl!ObfDereferenceObject` at `0x180077a75`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180077a29`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180077a29`
- `ntoskrnl!ExDeleteTimer` at `0x180077b20`
- `ntoskrnl!ExDeleteTimer` at `0x180077b20`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1800779dd`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1800779dd`
- `ntoskrnl!ExSetTimer` at `0x180077b03`
- `ntoskrnl!ExSetTimer` at `0x180077b03`

## pseudocode

```c
LONG_PTR __fastcall FltpManualDeviceAttachWorker(int a1)
{
  int v1; // esi
  char v2; // r15
  __int64 v3; // rbx
  char v4; // r14
  LONG_PTR result; // rax
  __int64 v6; // rbp
  unsigned __int64 v7; // r12
  unsigned int DeviceObjectPointer; // eax
  struct _DEVICE_OBJECT *DeviceAttachmentBaseRef; // rdi
  __int64 v10; // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+30h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp-50h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF

  v1 = a1;
  v2 = 0;
  FileObject = 0;
  DeviceObject = 0;
  v13 = 0;
  v3 = a1 & 1;
  if ( (a1 & 1) != 0 )
  {
    a1 = dword_18003E9EC;
    if ( dword_18003E9EC > 0 )
    {
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
        McTemplateU0spdd_EtwWriteTransfer(
          dword_18003E9EC,
          (unsigned int)FrameSup_c1763,
          (unsigned int)"FltpManualDeviceAttachWorker",
          v1,
          dword_18003E9EC,
          dword_18003E9E8);
      --dword_18003E9EC;
      v4 = 0;
LABEL_24:
      if ( dword_18003E9E8 <= 0 || v4 )
      {
        result = ExDeleteTimer(qword_18003E9C0, 0, 0, 0);
        qword_18003E9C0 = 0;
      }
      else
      {
        if ( v2 )
        {
          v10 = (unsigned int)dword_18003E9F0;
        }
        else
        {
          --dword_18003E9E8;
          v10 = (unsigned int)qword_18003E9F4;
        }
        *(_QWORD *)&v13 = 0;
        *((_QWORD *)&v13 + 1) = -1;
        result = ExSetTimer(qword_18003E9C0, -10000000 * v10, 0, &v13);
      }
      goto LABEL_31;
    }
  }
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      a1,
      (unsigned int)FrameSup_c1779,
      (unsigned int)"FltpManualDeviceAttachWorker",
      v1,
      dword_18003E9EC,
      dword_18003E9E8);
  result = (unsigned int)dword_18003E810;
  if ( dword_18003E810 )
  {
    v4 = 1;
    LODWORD(v6) = 0;
    if ( ManualDeviceAttachList[0] != -1 )
    {
      do
      {
        result = (unsigned int)v6;
        v7 = 24LL * (unsigned int)v6;
        if ( !ManualDeviceAttachList[v7 + 1] )
        {
          DeviceObjectPointer = IoGetDeviceObjectPointer(
                                  (PUNICODE_STRING)&a24[v7 / 2],
                                  0x80u,
                                  &FileObject,
                                  &DeviceObject);
          result = FltpDbgStatus(DeviceObjectPointer, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 1824, 0);
          if ( (int)result >= 0 )
          {
            if ( FltpFindFrameForDeviceStack(DeviceObject) )
            {
              DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceObject);
              FltpFsNotificationActual(DeviceAttachmentBaseRef);
              ObfDereferenceObject(DeviceAttachmentBaseRef);
              if ( ManualDeviceAttachList[v7] )
                ManualDeviceAttachList[v7 + 1] = 1;
              else
                v4 = 0;
              ManualDeviceAttachList[v7 + 2] = 0;
            }
            else
            {
              v4 = 0;
            }
            result = ObfDereferenceObject(FileObject);
          }
          else
          {
            v4 = 0;
            if ( ManualDeviceAttachList[v7 + 2] )
              v2 = 1;
          }
        }
        v6 = (unsigned int)(v6 + 1);
      }
      while ( ManualDeviceAttachList[24 * v6] != -1 );
    }
  }
  else
  {
    v4 = 0;
  }
  if ( v3 )
    goto LABEL_24;
LABEL_31:
  if ( (v1 & 2) != 0 )
  {
    result = HIDWORD(qword_18003E9F4);
    dword_18003E9EC = HIDWORD(qword_18003E9F4);
  }
  return result;
}

```

## disassembly

```asm
0x1800778a0  mov     r11, rsp
0x1800778a3  sub     rsp, 88h
0x1800778aa  mov     rax, cs:__security_cookie
0x1800778b1  xor     rax, rsp
0x1800778b4  mov     [rsp+88h+var_38], rax
0x1800778b9  mov     [r11+10h], rbx
0x1800778bd  xorps   xmm0, xmm0
0x1800778c0  mov     [r11+20h], rsi
0x1800778c4  mov     rbx, rcx
0x1800778c7  mov     [r11-18h], r13
0x1800778cb  mov     rsi, rcx
0x1800778ce  xor     r13d, r13d
0x1800778d1  mov     [r11-20h], r14
0x1800778d5  mov     [r11-28h], r15
0x1800778d9  xor     r15b, r15b
0x1800778dc  mov     [r11-50h], r13
0x1800778e0  mov     [r11-58h], r13
0x1800778e4  movups  [rsp+88h+var_48], xmm0
0x1800778e9  and     ebx, 1
0x1800778ec  jz      short loc_180077933
0x1800778ee  mov     ecx, cs:dword_18003E9EC
0x1800778f4  test    ecx, ecx
0x1800778f6  jle     short loc_180077933
0x1800778f8  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800778ff  jz      short loc_180077925
0x180077901  mov     eax, cs:dword_18003E9E8
0x180077907  lea     r8, aFltpmanualdevi; "FltpManualDeviceAttachWorker"
0x18007790e  mov     [rsp+88h+var_60], eax
0x180077912  lea     rdx, FrameSup_c1763
0x180077919  mov     r9, rsi
0x18007791c  mov     [rsp+88h+var_68], ecx
0x180077920  call    McTemplateU0spdd_EtwWriteTransfer
0x180077925  dec     cs:dword_18003E9EC
0x18007792b  xor     r14b, r14b
0x18007792e  jmp     loc_180077AB5
0x180077933  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x18007793a  jz      short loc_180077966
0x18007793c  mov     eax, cs:dword_18003E9E8
0x180077942  lea     r8, aFltpmanualdevi; "FltpManualDeviceAttachWorker"
0x180077949  mov     [rsp+88h+var_60], eax
0x18007794d  lea     rdx, FrameSup_c1779
0x180077954  mov     eax, cs:dword_18003E9EC
0x18007795a  mov     r9, rsi
0x18007795d  mov     [rsp+88h+var_68], eax
0x180077961  call    McTemplateU0spdd_EtwWriteTransfer
0x180077966  mov     eax, cs:dword_18003E810
0x18007796c  test    eax, eax
0x18007796e  jnz     short loc_180077978
0x180077970  xor     r14b, r14b
0x180077973  jmp     loc_180077AB0
0x180077978  cmp     cs:ManualDeviceAttachList, 0FFh
0x18007797f  mov     r14b, 1
0x180077982  mov     [rsp+88h+arg_10], rbp
0x18007798a  mov     ebp, r13d
0x18007798d  jz      loc_180077AA8
0x180077993  mov     [rsp+88h+var_8], rdi
0x18007799b  mov     r13d, 720h
0x1800779a1  mov     [rsp+88h+var_10], r12
0x1800779a6  lea     rdi, ManualDeviceAttachList
0x1800779ad  mov     eax, ebp
0x1800779af  lea     rcx, [rax+rax*2]
0x1800779b3  lea     r12, ds:0[rcx*8]
0x1800779bb  cmp     byte ptr [r12+rdi+1], 0
0x1800779c1  jnz     loc_180077A81
0x1800779c7  lea     rcx, [rdi+8]
0x1800779cb  mov     edx, 80h; DesiredAccess
0x1800779d0  add     rcx, r12; ObjectName
0x1800779d3  lea     r9, [rsp+88h+DeviceObject]; DeviceObject
0x1800779d8  lea     r8, [rsp+88h+FileObject]; FileObject
0x1800779dd  call    cs:__imp_IoGetDeviceObjectPointer
0x1800779e4  nop     dword ptr [rax+rax+00h]
0x1800779e9  xor     r9d, r9d
0x1800779ec  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x1800779f3  mov     ecx, eax
0x1800779f5  mov     r8d, r13d
0x1800779f8  call    FltpDbgStatus
0x1800779fd  test    eax, eax
0x1800779ff  jns     short loc_180077A10
0x180077a01  xor     r14b, r14b
0x180077a04  cmp     [r12+rdi+2], r14b
0x180077a09  jz      short loc_180077A81
0x180077a0b  mov     r15b, 1
0x180077a0e  jmp     short loc_180077A81
0x180077a10  mov     rcx, [rsp+88h+DeviceObject]; DeviceObject
0x180077a15  call    FltpFindFrameForDeviceStack
0x180077a1a  test    rax, rax
0x180077a1d  jnz     short loc_180077A24
0x180077a1f  xor     r14b, r14b
0x180077a22  jmp     short loc_180077A70
0x180077a24  mov     rcx, [rsp+88h+DeviceObject]; DeviceObject
0x180077a29  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x180077a30  nop     dword ptr [rax+rax+00h]
0x180077a35  mov     rcx, rax; TargetDevice
0x180077a38  mov     dl, 1
0x180077a3a  mov     rdi, rax
0x180077a3d  call    FltpFsNotificationActual
0x180077a42  mov     rcx, rdi; Object
0x180077a45  call    cs:__imp_ObfDereferenceObject
0x180077a4c  nop     dword ptr [rax+rax+00h]
0x180077a51  lea     rdi, ManualDeviceAttachList
0x180077a58  cmp     byte ptr [r12+rdi], 0
0x180077a5d  jz      short loc_180077A67
0x180077a5f  mov     byte ptr [r12+rdi+1], 1
0x180077a65  jmp     short loc_180077A6A
0x180077a67  xor     r14b, r14b
0x180077a6a  mov     byte ptr [r12+rdi+2], 0
0x180077a70  mov     rcx, [rsp+88h+FileObject]; Object
0x180077a75  call    cs:__imp_ObfDereferenceObject
0x180077a7c  nop     dword ptr [rax+rax+00h]
0x180077a81  inc     ebp
0x180077a83  lea     rcx, ds:0[rbp*2]
0x180077a8b  add     rcx, rbp
0x180077a8e  cmp     byte ptr [rdi+rcx*8], 0FFh
0x180077a92  jnz     loc_1800779AD
0x180077a98  mov     r12, [rsp+88h+var_10]
0x180077a9d  xor     r13d, r13d
0x180077aa0  mov     rdi, [rsp+88h+var_8]
0x180077aa8  mov     rbp, [rsp+88h+arg_10]
0x180077ab0  test    rbx, rbx
0x180077ab3  jz      short loc_180077B33
0x180077ab5  mov     eax, cs:dword_18003E9E8
0x180077abb  test    eax, eax
0x180077abd  jle     short loc_180077B11
0x180077abf  test    r14b, r14b
0x180077ac2  jnz     short loc_180077B11
0x180077ac4  test    r15b, r15b
0x180077ac7  jnz     short loc_180077AD9
0x180077ac9  dec     eax
0x180077acb  mov     cs:dword_18003E9E8, eax
0x180077ad1  mov     eax, dword ptr cs:qword_18003E9F4
0x180077ad7  jmp     short loc_180077ADF
0x180077ad9  mov     eax, cs:dword_18003E9F0
0x180077adf  mov     rcx, cs:qword_18003E9C0
0x180077ae6  lea     r9, [rsp+88h+var_48]
0x180077aeb  imul    rdx, rax, 0FFFFFFFFFF676980h
0x180077af2  xor     r8d, r8d
0x180077af5  mov     qword ptr [rsp+88h+var_48], r13
0x180077afa  mov     qword ptr [rsp+88h+var_48+8], 0FFFFFFFFFFFFFFFFh
0x180077b03  call    cs:__imp_ExSetTimer
0x180077b0a  nop     dword ptr [rax+rax+00h]
0x180077b0f  jmp     short loc_180077B33
0x180077b11  mov     rcx, cs:qword_18003E9C0
0x180077b18  xor     r9d, r9d
0x180077b1b  xor     r8d, r8d
0x180077b1e  xor     edx, edx
0x180077b20  call    cs:__imp_ExDeleteTimer
0x180077b27  nop     dword ptr [rax+rax+00h]
0x180077b2c  mov     cs:qword_18003E9C0, r13
0x180077b33  mov     r15, [rsp+88h+var_28]
0x180077b38  test    sil, 2
0x180077b3c  mov     rsi, [rsp+88h+arg_18]
0x180077b44  mov     r14, [rsp+88h+var_20]
0x180077b49  mov     r13, [rsp+88h+var_18]
0x180077b4e  mov     rbx, [rsp+88h+arg_8]
0x180077b56  jz      short loc_180077B64
0x180077b58  mov     eax, dword ptr cs:qword_18003E9F4+4
0x180077b5e  mov     cs:dword_18003E9EC, eax
0x180077b64  mov     rcx, [rsp+88h+var_38]
0x180077b69  xor     rcx, rsp; StackCookie
0x180077b6c  call    __security_check_cookie
0x180077b71  add     rsp, 88h
0x180077b78  retn
```
