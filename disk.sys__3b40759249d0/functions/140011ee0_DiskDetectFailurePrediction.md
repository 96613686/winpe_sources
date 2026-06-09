# DiskDetectFailurePrediction

- ea: `0x140011ee0`
- end: `0x1400120db`
- name: `DiskDetectFailurePrediction`
- size: `507`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e510`

## callees

- `0x1400028b0`
- `0x1400046c8`
- `0x1400055dc`
- `0x140005bf0`
- `0x140006000`
- `0x140011ee0`
- `0x1400120f0`
- `0x1400125d0`
- `0x140014520`

## import_xrefs

- `CLASSPNP!ClassNotifyFailurePredicted` at `0x14001208e`
- `CLASSPNP!ClassNotifyFailurePredicted` at `0x14001208e`

## pseudocode

```c
__int64 __fastcall DiskDetectFailurePrediction(struct _FUNCTIONAL_DEVICE_EXTENSION *a1, _DWORD *a2, char a3)
{
  UCHAR *DriverData; // rbp
  int v7; // ebx
  const char *v8; // rax
  BOOLEAN v9; // zf
  __int64 v11; // [rsp+48h] [rbp-240h]
  UCHAR Buffer[528]; // [rsp+50h] [rbp-238h] BYREF

  DriverData = (UCHAR *)a1->CommonExtension.DriverData;
  memset(Buffer, 0, 0x204u);
  v11 = 0;
  *a2 = 0;
  if ( a3 )
    DiskGetIdentifyInfo((int)a1);
  v7 = DiskSendFailurePredictIoctl((__int64)a1, Buffer);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v8 = "does";
    if ( v7 < 0 )
      v8 = "does not";
    WPP_SF_qs(WPP_GLOBAL_Control->AttachedDevice, 32, (_DWORD)WPP_GLOBAL_Control, a1->DeviceObject, (__int64)v8);
  }
  if ( v7 < 0 )
  {
    *a2 = 0;
    DiskInfoExceptionCheck((__int64)a1);
    return 0;
  }
  else
  {
    *a2 = 1;
    DriverData[22] = 1;
    if ( *(_DWORD *)Buffer )
    {
      v9 = a1->FailurePredicted == 0;
      *(_DWORD *)Buffer = 512;
      ClassNotifyFailurePredicted(a1, Buffer, 0x204u, v9, 0x11u, DriverData[13], DriverData[14], DriverData[15]);
      a1->FailurePredicted = 1;
    }
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140011ee0  mov     [rsp+arg_10], rbx
0x140011ee5  mov     [rsp+arg_18], rbp
0x140011eea  push    rsi
0x140011eeb  push    rdi
0x140011eec  push    r14
0x140011eee  sub     rsp, 270h
0x140011ef5  mov     rax, cs:__security_cookie
0x140011efc  xor     rax, rsp
0x140011eff  mov     [rsp+288h+var_28], rax
0x140011f07  mov     rbp, [rcx+60h]
0x140011f0b  movzx   ebx, r8b
0x140011f0f  mov     rsi, rdx
0x140011f12  mov     [rsp+288h+var_248], 0
0x140011f17  mov     rdi, rcx
0x140011f1a  xor     edx, edx; Val
0x140011f1c  mov     r8d, 204h; Size
0x140011f22  lea     rcx, [rsp+288h+Buffer]; void *
0x140011f27  call    memset
0x140011f2c  xor     r14d, r14d
0x140011f2f  mov     [rsp+288h+var_240], r14
0x140011f34  mov     [rsi], r14d
0x140011f37  test    bl, bl
0x140011f39  jz      loc_140011FDB
0x140011f3f  lea     rdx, [rsp+288h+var_248]
0x140011f44  mov     rcx, rdi; int
0x140011f47  call    DiskGetIdentifyInfo
0x140011f4c  cmp     [rsp+288h+var_248], r14b
0x140011f51  jz      loc_140011FDB
0x140011f57  mov     rcx, rdi
0x140011f5a  call    DiskEnableSmart
0x140011f5f  mov     ebx, eax
0x140011f61  test    eax, eax
0x140011f63  js      short loc_140011FD4
0x140011f65  mov     dword ptr [rsi], 2
0x140011f6b  lea     rdx, [rsp+288h+var_240]
0x140011f70  mov     rcx, rdi
0x140011f73  mov     byte ptr [rbp+16h], 1
0x140011f77  call    DiskReadFailurePredictStatus
0x140011f7c  mov     ebx, eax
0x140011f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f85  lea     rax, WPP_GLOBAL_Control
0x140011f8c  cmp     rcx, rax
0x140011f8f  jz      short loc_140011FC9
0x140011f91  mov     eax, [rcx+2Ch]
0x140011f94  test    al, 40h
0x140011f96  jz      short loc_140011FC9
0x140011f98  cmp     byte ptr [rcx+29h], 4
0x140011f9c  jb      short loc_140011FC9
0x140011f9e  mov     r9, [rdi+8]
0x140011fa2  lea     rdx, aDoesNot; "does not"
0x140011fa9  mov     rcx, [rcx+18h]
0x140011fad  lea     rax, aDoes; "does"
0x140011fb4  test    ebx, ebx
0x140011fb6  cmovs   rax, rdx
0x140011fba  mov     edx, 1Fh
0x140011fbf  mov     qword ptr [rsp+288h+UniqueErrorValue], rax
0x140011fc4  call    WPP_SF_qs
0x140011fc9  test    ebx, ebx
0x140011fcb  jns     short loc_140011FD4
0x140011fcd  mov     [rsi], r14d
0x140011fd0  mov     [rbp+16h], r14b
0x140011fd4  mov     eax, ebx
0x140011fd6  jmp     loc_1400120B2
0x140011fdb  lea     rdx, [rsp+288h+Buffer]
0x140011fe0  mov     rcx, rdi
0x140011fe3  call    DiskSendFailurePredictIoctl
0x140011fe8  mov     ebx, eax
0x140011fea  mov     r8, cs:WPP_GLOBAL_Control
0x140011ff1  lea     rax, WPP_GLOBAL_Control
0x140011ff8  cmp     r8, rax
0x140011ffb  jz      short loc_140012038
0x140011ffd  mov     ecx, [r8+2Ch]
0x140012001  test    cl, 40h
0x140012004  jz      short loc_140012038
0x140012006  cmp     byte ptr [r8+29h], 4
0x14001200b  jb      short loc_140012038
0x14001200d  mov     r9, [rdi+8]
0x140012011  lea     rdx, aDoesNot; "does not"
0x140012018  mov     rcx, [r8+18h]
0x14001201c  lea     rax, aDoes; "does"
0x140012023  test    ebx, ebx
0x140012025  cmovs   rax, rdx
0x140012029  mov     edx, 20h ; ' '
0x14001202e  mov     qword ptr [rsp+288h+UniqueErrorValue], rax
0x140012033  call    WPP_SF_qs
0x140012038  test    ebx, ebx
0x14001203a  js      short loc_1400120A5
0x14001203c  mov     dword ptr [rsi], 1
0x140012042  mov     byte ptr [rbp+16h], 1
0x140012046  cmp     dword ptr [rsp+288h+Buffer], r14d
0x14001204b  jz      short loc_1400120A1
0x14001204d  cmp     [rdi+333h], r14b
0x140012054  lea     rdx, [rsp+288h+Buffer]; Buffer
0x140012059  mov     dword ptr [rsp+288h+Buffer], 200h
0x140012061  mov     r8d, 204h; BufferSize
0x140012067  movzx   eax, byte ptr [rbp+0Fh]
0x14001206b  setz    r9b; LogError
0x14001206f  mov     [rsp+288h+Lun], al; Lun
0x140012073  mov     rcx, rdi; FdoExtension
0x140012076  movzx   eax, byte ptr [rbp+0Eh]
0x14001207a  mov     [rsp+288h+TargetId], al; TargetId
0x14001207e  movzx   eax, byte ptr [rbp+0Dh]
0x140012082  mov     [rsp+288h+PathId], al; PathId
0x140012086  mov     [rsp+288h+UniqueErrorValue], 11h; UniqueErrorValue
0x14001208e  call    cs:__imp_ClassNotifyFailurePredicted
0x140012095  nop     dword ptr [rax+rax+00h]
0x14001209a  mov     byte ptr [rdi+333h], 1
0x1400120a1  mov     eax, ebx
0x1400120a3  jmp     short loc_1400120B2
0x1400120a5  mov     rcx, rdi
0x1400120a8  mov     [rsi], r14d
0x1400120ab  call    DiskInfoExceptionCheck
0x1400120b0  xor     eax, eax
0x1400120b2  mov     rcx, [rsp+288h+var_28]
0x1400120ba  xor     rcx, rsp; StackCookie
0x1400120bd  call    __security_check_cookie
0x1400120c2  lea     r11, [rsp+288h+var_18]
0x1400120ca  mov     rbx, [r11+30h]
0x1400120ce  mov     rbp, [r11+38h]
0x1400120d2  mov     rsp, r11
0x1400120d5  pop     r14
0x1400120d7  pop     rdi
0x1400120d8  pop     rsi
0x1400120d9  retn
```
