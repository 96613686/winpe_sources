# DiskReadWriteVerification

- ea: `0x140001010`
- end: `0x140001145`
- name: `DiskReadWriteVerification`
- size: `309`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140001010`
- `0x1400041c0`

## import_xrefs

- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400010eb`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400010eb`

## pseudocode

```c
__int64 __fastcall DiskReadWriteVerification(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r10
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v6; // r8
  int v7; // r11d
  int v8; // r9d
  __int64 QuadPart; // rdx
  unsigned int v10; // ebx
  __int64 result; // rax
  int v12; // ebp

  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v6 = DeviceExtension[3];
  v7 = CurrentStackLocation->Parameters.Read.Length & (*(_DWORD *)(v6 + 572) - 1);
  v8 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & (*(_DWORD *)(v6 + 572) - 1);
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  if ( QuadPart > DeviceExtension[18] || QuadPart < 0 || v7 || v8 )
  {
    v10 = 0;
  }
  else
  {
    v10 = 0;
    if ( (unsigned __int64)CurrentStackLocation->Parameters.Read.Length <= DeviceExtension[18]
                                                                         - CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart )
      goto LABEL_6;
  }
  v12 = *(_DWORD *)(DeviceExtension[12] + 4LL);
  if ( v12 >= 0 )
  {
    if ( v7 || v8 )
      v10 = -1073741811;
  }
  else
  {
    v10 = *(_DWORD *)(DeviceExtension[12] + 4LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 14, v6, (unsigned int)v12);
    }
    if ( (unsigned int)(v12 + 1073741662) <= 1
      || (unsigned int)(v12 + 1073741806) <= 2
      || v12 == -2147483626
      || v12 == -1073741643 )
    {
      if ( Irp->Tail.Overlay.Thread )
        IoSetHardErrorOrVerifyDevice(Irp, DeviceObject);
    }
  }
LABEL_6:
  result = v10;
  Irp->IoStatus.Status = v10;
  return result;
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_8], rbx
0x140001015  mov     [rsp+arg_10], rsi
0x14000101a  push    rdi
0x14000101b  sub     rsp, 20h
0x14000101f  mov     r10, [rcx+40h]
0x140001023  mov     rsi, rcx
0x140001026  mov     rax, [rdx+0B8h]
0x14000102d  mov     rdi, rdx
0x140001030  mov     r8, [r10+18h]
0x140001034  mov     r11d, [r8+23Ch]
0x14000103b  mov     r8, [r10+18h]
0x14000103f  dec     r11d
0x140001042  and     r11d, [rax+8]
0x140001046  mov     r9d, [r8+23Ch]
0x14000104d  mov     rcx, [r10+90h]
0x140001054  dec     r9d
0x140001057  and     r9d, [rax+18h]
0x14000105b  mov     rdx, [rax+18h]
0x14000105f  cmp     rdx, rcx
0x140001062  jg      short loc_14000109E
0x140001064  test    rdx, rdx
0x140001067  js      short loc_14000109E
0x140001069  test    r11d, r11d
0x14000106c  jnz     short loc_14000109E
0x14000106e  test    r9d, r9d
0x140001071  jnz     short loc_14000109E
0x140001073  mov     rdx, [r10+90h]
0x14000107a  xor     ebx, ebx
0x14000107c  sub     rdx, [rax+18h]
0x140001080  mov     ecx, [rax+8]
0x140001083  cmp     rcx, rdx
0x140001086  ja      short loc_1400010A0
0x140001088  mov     rsi, [rsp+28h+arg_10]
0x14000108d  mov     eax, ebx
0x14000108f  mov     [rdi+30h], ebx
0x140001092  mov     rbx, [rsp+28h+arg_8]
0x140001097  add     rsp, 20h
0x14000109b  pop     rdi
0x14000109c  retn
0x14000109e  xor     ebx, ebx
0x1400010a0  mov     rax, [r10+60h]
0x1400010a4  mov     [rsp+28h+arg_0], rbp
0x1400010a9  mov     ebp, [rax+4]
0x1400010ac  test    ebp, ebp
0x1400010ae  jns     loc_140001134
0x1400010b4  mov     ebx, ebp
0x1400010b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400010bd  lea     rax, WPP_GLOBAL_Control
0x1400010c4  cmp     rcx, rax
0x1400010c7  jz      short loc_1400010D0
0x1400010c9  mov     eax, [rcx+2Ch]
0x1400010cc  test    al, 8
0x1400010ce  jnz     short loc_1400010FE
0x1400010d0  lea     eax, [rbp+3FFFFF5Eh]
0x1400010d6  cmp     eax, 1
0x1400010d9  ja      short loc_140001117
0x1400010db  cmp     qword ptr [rdi+98h], 0
0x1400010e3  jz      short loc_1400010F7
0x1400010e5  mov     rdx, rsi; DeviceObject
0x1400010e8  mov     rcx, rdi; Irp
0x1400010eb  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x1400010f2  nop     dword ptr [rax+rax+00h]
0x1400010f7  mov     rbp, [rsp+28h+arg_0]
0x1400010fc  jmp     short loc_140001088
0x1400010fe  cmp     byte ptr [rcx+29h], 3
0x140001102  jb      short loc_1400010D0
0x140001104  mov     rcx, [rcx+18h]
0x140001108  mov     edx, 0Eh
0x14000110d  mov     r9d, ebp
0x140001110  call    WPP_SF_L
0x140001115  jmp     short loc_1400010D0
0x140001117  lea     eax, [rbp+3FFFFFEEh]
0x14000111d  cmp     eax, 2
0x140001120  jbe     short loc_1400010DB
0x140001122  cmp     ebp, 80000016h
0x140001128  jz      short loc_1400010DB
0x14000112a  cmp     ebp, 0C00000B5h
0x140001130  jnz     short loc_1400010F7
0x140001132  jmp     short loc_1400010DB
0x140001134  test    r11d, r11d
0x140001137  jnz     short loc_14000113E
0x140001139  test    r9d, r9d
0x14000113c  jz      short loc_1400010F7
0x14000113e  mov     ebx, 0C000000Dh
0x140001143  jmp     short loc_1400010F7
```
