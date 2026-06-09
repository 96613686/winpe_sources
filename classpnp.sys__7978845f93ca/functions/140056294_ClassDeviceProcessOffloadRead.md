# ClassDeviceProcessOffloadRead

- ea: `0x140056294`
- end: `0x14005665d`
- name: `ClassDeviceProcessOffloadRead`
- size: `969`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140001008`
- `0x14001fc38`
- `0x14002001c`
- `0x140022668`
- `0x140023e3c`
- `0x14002689c`
- `0x140026f28`
- `0x140027870`
- `0x14003e430`
- `0x140056294`
- `0x140059cb4`
- `0x14005c054`
- `0x14005c3d8`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140056328`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056328`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140056517`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140056517`

## pseudocode

```c
__int64 __fastcall ClassDeviceProcessOffloadRead(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v5; // ebx
  unsigned int v6; // r9d
  unsigned int *MasterIrp; // rcx
  unsigned int v8; // r8d
  _QWORD *DeviceExtension; // r15
  unsigned int v10; // r8d
  unsigned int Length; // r8d
  __int64 v12; // rbx
  unsigned int v13; // edx
  __int64 *v14; // r14
  unsigned int v15; // ecx
  unsigned int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+40h] [rbp-49h] BYREF
  __int64 v21; // [rsp+48h] [rbp-41h] BYREF
  __int128 v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23[10]; // [rsp+60h] [rbp-29h] BYREF

  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      220,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      DeviceObject,
      Irp);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v22 = *(_OWORD *)&Irp->Type;
  v5 = ClasspValidateOffloadSupported(DeviceObject, Irp);
  if ( v5 < 0 )
    goto LABEL_46;
  if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 221, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
    }
    v5 = -1073741496;
    goto LABEL_46;
  }
  if ( Irp->RequestorMode )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 222, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
    }
    v5 = -1073741790;
    goto LABEL_46;
  }
  v5 = ClasspValidateOffloadInputParameters(DeviceObject, Irp);
  if ( v5 < 0 )
  {
LABEL_46:
    ClasspCompleteOffloadRequest(DeviceObject, Irp);
    goto LABEL_47;
  }
  MasterIrp = (unsigned int *)Irp->AssociatedIrp.MasterIrp;
  v8 = MasterIrp[4];
  if ( v8 < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        223,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        v8,
        16);
    }
LABEL_24:
    v5 = -1073741811;
    goto LABEL_46;
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  v10 = *(_DWORD *)(DeviceExtension[144] + 136LL);
  if ( v10 )
  {
    v6 = *(unsigned int *)((char *)MasterIrp + MasterIrp[3] + 4);
    if ( v6 > v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          224,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          DeviceObject,
          v6,
          v10);
      }
      goto LABEL_24;
    }
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 0x218 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        225,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        Length);
    }
    v5 = -1073741789;
    goto LABEL_46;
  }
  v12 = 0;
  v13 = MasterIrp[6];
  v14 = (__int64 *)((char *)MasterIrp + MasterIrp[5]);
  v15 = 0;
  v16 = v13 >> 4;
  if ( v16 )
  {
    do
    {
      v17 = v15++;
      v12 += v14[2 * v17 + 1];
    }
    while ( v15 < v16 );
  }
  if ( ClassPnPETWEnabled
    && (int)IoGetActivityIdIrp(Irp, &v22) >= 0
    && ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 8) != 0 )
  {
    McTemplateK0qptix_EtwWriteTransfer(
      v15,
      (unsigned int)EventCopyOffloadReadRequest,
      (unsigned int)&v22,
      *((_DWORD *)DeviceExtension + 147),
      (char)Irp,
      0,
      *v14,
      v12);
  }
  if ( (unsigned int)dword_14004D060 > 5 )
  {
    v18 = DeviceExtension[146];
    v23[5] = 16;
    v23[4] = v18 + 4;
    v20 = *v14;
    v23[6] = (__int64)&v20;
    v23[8] = (__int64)&v21;
    v23[7] = 8;
    v21 = v12;
    v23[9] = 8;
    tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140048725, Length, v6, 5u, (__int64)v23);
  }
  v5 = ClasspServicePopulateTokenTransferRequest(DeviceObject, Irp);
  if ( v5 != 259 )
    goto LABEL_46;
LABEL_47:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      226,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      DeviceObject,
      Irp,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140056294  mov     [rsp-8+arg_10], rbx
0x140056299  push    rbp
0x14005629a  push    rsi
0x14005629b  push    rdi
0x14005629c  push    r14
0x14005629e  push    r15
0x1400562a0  lea     rbp, [rsp-37h]
0x1400562a5  sub     rsp, 0C0h
0x1400562ac  mov     rax, cs:__security_cookie
0x1400562b3  xor     rax, rsp
0x1400562b6  mov     [rbp+57h+var_30], rax
0x1400562ba  xorps   xmm0, xmm0
0x1400562bd  mov     rsi, rdx
0x1400562c0  movups  [rbp+57h+var_90], xmm0
0x1400562c4  mov     rdi, rcx
0x1400562c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400562ce  lea     rax, WPP_GLOBAL_Control
0x1400562d5  cmp     rcx, rax
0x1400562d8  jz      short loc_140056304
0x1400562da  mov     eax, [rcx+2Ch]
0x1400562dd  test    al, 10h
0x1400562df  jz      short loc_140056304
0x1400562e1  cmp     byte ptr [rcx+29h], 5
0x1400562e5  jb      short loc_140056304
0x1400562e7  mov     rcx, [rcx+18h]
0x1400562eb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400562f2  mov     edx, 0DCh
0x1400562f7  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x1400562fc  mov     r9, rdi
0x1400562ff  call    WPP_SF_qq
0x140056304  movups  xmm0, xmmword ptr [rsi]
0x140056307  mov     r14, [rsi+0B8h]
0x14005630e  mov     rdx, rsi
0x140056311  mov     rcx, rdi
0x140056314  movdqu  [rbp+57h+var_90], xmm0
0x140056319  call    ClasspValidateOffloadSupported
0x14005631e  mov     ebx, eax
0x140056320  test    eax, eax
0x140056322  js      loc_1400565E8
0x140056328  call    cs:__imp_KeGetCurrentIrql
0x14005632f  nop     dword ptr [rax+rax+00h]
0x140056334  mov     r15b, 2
0x140056337  cmp     al, r15b
0x14005633a  jb      short loc_14005637E
0x14005633c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056343  lea     r14, WPP_GLOBAL_Control
0x14005634a  cmp     rcx, r14
0x14005634d  jz      short loc_140056374
0x14005634f  mov     eax, [rcx+2Ch]
0x140056352  test    al, 10h
0x140056354  jz      short loc_140056374
0x140056356  cmp     [rcx+29h], r15b
0x14005635a  jb      short loc_140056374
0x14005635c  mov     rcx, [rcx+18h]
0x140056360  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140056367  mov     edx, 0DDh
0x14005636c  mov     r9, rdi
0x14005636f  call    WPP_SF_q
0x140056374  mov     ebx, 0C0000148h
0x140056379  jmp     loc_1400565EF
0x14005637e  cmp     byte ptr [rsi+40h], 0
0x140056382  jz      short loc_1400563C6
0x140056384  mov     rcx, cs:WPP_GLOBAL_Control
0x14005638b  lea     r14, WPP_GLOBAL_Control
0x140056392  cmp     rcx, r14
0x140056395  jz      short loc_1400563BC
0x140056397  mov     eax, [rcx+2Ch]
0x14005639a  test    al, 10h
0x14005639c  jz      short loc_1400563BC
0x14005639e  cmp     [rcx+29h], r15b
0x1400563a2  jb      short loc_1400563BC
0x1400563a4  mov     rcx, [rcx+18h]
0x1400563a8  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400563af  mov     edx, 0DEh
0x1400563b4  mov     r9, rdi
0x1400563b7  call    WPP_SF_q
0x1400563bc  mov     ebx, 0C0000022h
0x1400563c1  jmp     loc_1400565EF
0x1400563c6  mov     rdx, rsi
0x1400563c9  mov     rcx, rdi
0x1400563cc  call    ClasspValidateOffloadInputParameters
0x1400563d1  mov     ebx, eax
0x1400563d3  test    eax, eax
0x1400563d5  js      loc_1400565E8
0x1400563db  mov     rcx, [rsi+18h]
0x1400563df  mov     r8d, [rcx+10h]
0x1400563e3  cmp     r8d, 10h
0x1400563e7  jnb     short loc_140056438
0x1400563e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400563f0  lea     r14, WPP_GLOBAL_Control
0x1400563f7  cmp     rcx, r14
0x1400563fa  jz      short loc_14005642E
0x1400563fc  mov     eax, [rcx+2Ch]
0x1400563ff  test    al, 10h
0x140056401  jz      short loc_14005642E
0x140056403  cmp     [rcx+29h], r15b
0x140056407  jb      short loc_14005642E
0x140056409  mov     dword ptr [rsp+0E0h+var_B8], 10h
0x140056411  mov     edx, 0DFh
0x140056416  mov     [rsp+0E0h+var_C0], r8d
0x14005641b  mov     rcx, [rcx+18h]
0x14005641f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140056426  mov     r9, rdi
0x140056429  call    WPP_SF_qDD
0x14005642e  mov     ebx, 0C000000Dh
0x140056433  jmp     loc_1400565EF
0x140056438  mov     r15, [rdi+40h]
0x14005643c  mov     rax, [r15+480h]
0x140056443  mov     r8d, [rax+88h]
0x14005644a  test    r8d, r8d
0x14005644d  jz      short loc_14005648D
0x14005644f  mov     eax, [rcx+0Ch]
0x140056452  mov     r9d, [rax+rcx+4]
0x140056457  cmp     r9d, r8d
0x14005645a  jbe     short loc_14005648D
0x14005645c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056463  lea     r14, WPP_GLOBAL_Control
0x14005646a  cmp     rcx, r14
0x14005646d  jz      short loc_14005642E
0x14005646f  mov     eax, [rcx+2Ch]
0x140056472  test    al, 10h
0x140056474  jz      short loc_14005642E
0x140056476  cmp     byte ptr [rcx+29h], 2
0x14005647a  jb      short loc_14005642E
0x14005647c  mov     dword ptr [rsp+0E0h+var_B8], r8d
0x140056481  mov     edx, 0E0h
0x140056486  mov     [rsp+0E0h+var_C0], r9d
0x14005648b  jmp     short loc_14005641B
0x14005648d  mov     r8d, [r14+8]
0x140056491  cmp     r8d, 218h
0x140056498  jnb     short loc_1400564E1
0x14005649a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400564a1  lea     r14, WPP_GLOBAL_Control
0x1400564a8  cmp     rcx, r14
0x1400564ab  jz      short loc_1400564D7
0x1400564ad  mov     eax, [rcx+2Ch]
0x1400564b0  test    al, 10h
0x1400564b2  jz      short loc_1400564D7
0x1400564b4  cmp     byte ptr [rcx+29h], 2
0x1400564b8  jb      short loc_1400564D7
0x1400564ba  mov     rcx, [rcx+18h]
0x1400564be  mov     edx, 0E1h
0x1400564c3  mov     [rsp+0E0h+var_C0], r8d
0x1400564c8  mov     r9, rdi
0x1400564cb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400564d2  call    WPP_SF_qD
0x1400564d7  mov     ebx, 0C0000023h
0x1400564dc  jmp     loc_1400565EF
0x1400564e1  mov     r14d, [rcx+14h]
0x1400564e5  xor     ebx, ebx
0x1400564e7  mov     edx, [rcx+18h]
0x1400564ea  add     r14, rcx
0x1400564ed  xor     ecx, ecx
0x1400564ef  shr     edx, 4
0x1400564f2  test    edx, edx
0x1400564f4  jz      short loc_140056507
0x1400564f6  mov     eax, ecx
0x1400564f8  inc     ecx
0x1400564fa  shl     rax, 4
0x1400564fe  add     rbx, [rax+r14+8]
0x140056503  cmp     ecx, edx
0x140056505  jb      short loc_1400564F6
0x140056507  cmp     cs:ClassPnPETWEnabled, 0
0x14005650e  jz      short loc_140056561
0x140056510  lea     rdx, [rbp+57h+var_90]
0x140056514  mov     rcx, rsi
0x140056517  call    cs:__imp_IoGetActivityIdIrp
0x14005651e  nop     dword ptr [rax+rax+00h]
0x140056523  test    eax, eax
0x140056525  js      short loc_140056561
0x140056527  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 8
0x14005652e  jz      short loc_140056561
0x140056530  mov     rax, [r14]
0x140056533  lea     r8, [rbp+57h+var_90]
0x140056537  mov     r9d, [r15+24Ch]
0x14005653e  lea     rdx, EventCopyOffloadReadRequest
0x140056545  mov     [rsp+0E0h+var_A8], rbx
0x14005654a  mov     [rsp+0E0h+var_B0], rax
0x14005654f  mov     dword ptr [rsp+0E0h+var_B8], 0
0x140056557  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x14005655c  call    McTemplateK0qptix_EtwWriteTransfer
0x140056561  mov     eax, cs:dword_14004D060
0x140056567  cmp     eax, 5
0x14005656a  jbe     short loc_1400565CB
0x14005656c  mov     rax, [r15+490h]
0x140056573  lea     rdx, byte_140048725; int
0x14005657a  add     rax, 4
0x14005657e  mov     [rbp+57h+var_58], 10h
0x140056586  mov     [rbp+57h+var_60], rax
0x14005658a  mov     rax, [r14]
0x14005658d  mov     [rbp+57h+var_A0], rax
0x140056591  lea     rax, [rbp+57h+var_A0]
0x140056595  mov     [rbp+57h+var_50], rax
0x140056599  lea     rax, [rbp+57h+var_98]
0x14005659d  mov     [rbp+57h+var_40], rax
0x1400565a1  lea     rax, [rbp+57h+var_80]
0x1400565a5  mov     [rsp+0E0h+var_B8], rax; __int64
0x1400565aa  mov     [rsp+0E0h+var_C0], 5; ULONG
0x1400565b2  mov     [rbp+57h+var_48], 8
0x1400565ba  mov     [rbp+57h+var_98], rbx
0x1400565be  mov     [rbp+57h+var_38], 8
0x1400565c6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400565cb  mov     rdx, rsi
0x1400565ce  mov     rcx, rdi
0x1400565d1  call    ClasspServicePopulateTokenTransferRequest
0x1400565d6  lea     r14, WPP_GLOBAL_Control
0x1400565dd  mov     ebx, eax
0x1400565df  cmp     eax, 103h
0x1400565e4  jz      short loc_1400565FD
0x1400565e6  jmp     short loc_1400565EF
0x1400565e8  lea     r14, WPP_GLOBAL_Control
0x1400565ef  mov     r8d, ebx
0x1400565f2  mov     rdx, rsi; Irp
0x1400565f5  mov     rcx, rdi; DeviceObject
0x1400565f8  call    ClasspCompleteOffloadRequest
0x1400565fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140056604  cmp     rcx, r14
0x140056607  jz      short loc_140056637
0x140056609  mov     eax, [rcx+2Ch]
0x14005660c  test    al, 10h
0x14005660e  jz      short loc_140056637
0x140056610  cmp     byte ptr [rcx+29h], 5
0x140056614  jb      short loc_140056637
0x140056616  mov     rcx, [rcx+18h]
0x14005661a  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140056621  mov     edx, 0E2h
0x140056626  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x14005662a  mov     r9, rdi
0x14005662d  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x140056632  call    WPP_SF_qqD
0x140056637  mov     eax, ebx
0x140056639  mov     rcx, [rbp+57h+var_30]
0x14005663d  xor     rcx, rsp; StackCookie
0x140056640  call    __security_check_cookie
0x140056645  mov     rbx, [rsp+0E0h+arg_10]
0x14005664d  add     rsp, 0C0h
0x140056654  pop     r15
0x140056656  pop     r14
0x140056658  pop     rdi
0x140056659  pop     rsi
0x14005665a  pop     rbp
0x14005665b  retn
```
