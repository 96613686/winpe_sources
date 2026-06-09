# DiskPerformSmartCommand

- ea: `0x140012810`
- end: `0x140012b22`
- name: `DiskPerformSmartCommand`
- size: `786`
- prototype: `NTSTATUS __fastcall(__int64, int, char, char, char, char, char *Buffer, int *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400028b0`
- `0x140003410`
- `0x140004624`
- `0x140010e14`
- `0x140010f3c`
- `0x140011118`
- `0x1400120f0`
- `0x1400125d0`
- `0x1400126c0`

## callees

- `0x140005bf0`
- `0x140006000`
- `0x140012810`

## import_xrefs

- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14001295b`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14001295b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012a2e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012a2e`
- `ntoskrnl!KeFlushIoBuffers` at `0x1400129f6`
- `ntoskrnl!KeFlushIoBuffers` at `0x1400129f6`
- `ntoskrnl!KeInitializeEvent` at `0x140012910`
- `ntoskrnl!KeInitializeEvent` at `0x140012910`
- `ntoskrnl!IofCallDriver` at `0x140012a09`
- `ntoskrnl!IofCallDriver` at `0x140012a09`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140012aae`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140012aae`

## pseudocode

```c
NTSTATUS __fastcall DiskPerformSmartCommand(
        __int64 a1,
        int a2,
        char a3,
        char a4,
        char a5,
        char a6,
        char *Buffer,
        int *a8)
{
  int v12; // ecx
  __int64 v13; // r14
  ULONG v14; // r15d
  struct _DEVICE_OBJECT *v15; // rdx
  PIRP v16; // rax
  IRP *v17; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  int v19; // eax
  NTSTATUS result; // eax
  int v21; // eax
  union _LARGE_INTEGER StartingOffset; // [rsp+40h] [rbp-C0h] BYREF
  struct _KEVENT Event; // [rsp+48h] [rbp-B8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v25[11]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[18]; // [rsp+D0h] [rbp-30h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  memset(v25, 0, sizeof(v25));
  StartingOffset.QuadPart = 0;
  memset(v26, 0, sizeof(v26));
  v12 = *a8;
  if ( (unsigned int)*a8 < 0x1C )
    return -1073741789;
  v13 = *(_QWORD *)(a1 + 96);
  *(_DWORD *)Buffer = 28;
  *(_QWORD *)(Buffer + 4) = 0x4B53494449534353LL;
  *((_DWORD *)Buffer + 3) = *(_DWORD *)(a1 + 584);
  *((_DWORD *)Buffer + 6) = v12 - 28;
  *((_DWORD *)Buffer + 4) = a2;
  *((_DWORD *)Buffer + 7) = 33;
  Buffer[40] = *(_BYTE *)(v13 + 14);
  Buffer[33] = a5;
  Buffer[34] = a6;
  Buffer[32] = a4;
  *(_WORD *)(Buffer + 35) = -15793;
  Buffer[38] = a3;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v14 = *((_DWORD *)Buffer + 6) + *(_DWORD *)Buffer;
  v15 = *(struct _DEVICE_OBJECT **)(a1 + 16);
  StartingOffset.QuadPart = 1;
  v16 = IoBuildSynchronousFsdRequest(0xFu, v15, Buffer, v14, &StartingOffset, &Event, &IoStatusBlock);
  v17 = v16;
  if ( !v16 )
    return -1073741670;
  CurrentStackLocation = v16->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 271;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 528) + 30LL) == 1 )
  {
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v26;
    LOWORD(v26[0]) = 8;
    BYTE2(v26[0]) = 40;
    v26[1] = 0x153524258LL;
    v26[2] = 0x200000090LL;
    WORD2(v26[4]) = IoGetIoPriorityHint(v16);
    v21 = *(_DWORD *)(a1 + 592) | 0x100140;
    HIDWORD(v26[6]) = 128;
    LODWORD(v26[3]) = v21;
    HIWORD(v26[4]) = 32;
    LODWORD(v26[5]) = *((_DWORD *)Buffer + 3);
    LODWORD(v26[4]) = 255;
    v26[10] = v17;
    v26[8] = Buffer;
    HIDWORD(v26[7]) = v14;
    LOWORD(v26[16]) = 1;
    HIDWORD(v26[16]) = 4;
    LOWORD(v26[17]) = *(_WORD *)(v13 + 13);
    HIBYTE(v25[0]) = *(_BYTE *)(v13 + 15);
    BYTE2(v26[17]) = HIBYTE(v25[0]);
  }
  else
  {
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v25;
    *(_WORD *)((char *)v25 + 5) = *(_WORD *)(v13 + 13);
    HIBYTE(v25[0]) = *(_BYTE *)(v13 + 15);
    LOWORD(v25[0]) = 88;
    v19 = *(_DWORD *)(a1 + 592) | 0x100140;
    BYTE2(v25[0]) = 2;
    HIDWORD(v25[1]) = v19;
    HIDWORD(v25[2]) = *((_DWORD *)Buffer + 3);
    LOWORD(v25[1]) = 8447;
    v25[6] = v17;
    v25[3] = Buffer;
    LODWORD(v25[2]) = v14;
  }
  KeFlushIoBuffers(v17->MdlAddress, 0, 1);
  result = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 16), v17);
  if ( result == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    return IoStatusBlock.Status;
  }
  return result;
}

```

## disassembly

```asm
0x140012810  mov     [rsp-8+arg_10], rbx
0x140012815  mov     [rsp-8+arg_18], rsi
0x14001281a  push    rbp
0x14001281b  push    rdi
0x14001281c  push    r12
0x14001281e  push    r13
0x140012820  push    r15
0x140012822  lea     rbp, [rsp-70h]
0x140012827  sub     rsp, 170h
0x14001282e  mov     rax, cs:__security_cookie
0x140012835  xor     rax, rsp
0x140012838  mov     [rbp+90h+var_30], rax
0x14001283c  mov     rbx, [rbp+90h+Buffer]
0x140012843  xorps   xmm0, xmm0
0x140012846  movzx   r15d, r8b
0x14001284a  mov     r12d, edx
0x14001284d  mov     rdi, rcx
0x140012850  xor     eax, eax
0x140012852  xor     edx, edx; Val
0x140012854  mov     [rsp+190h+Event.Header.WaitListHead.Blink], rax
0x140012859  mov     r8d, 58h ; 'X'; Size
0x14001285f  lea     rcx, [rsp+190h+var_120]; void *
0x140012864  movups  xmmword ptr [rsp+190h+Event.Header], xmm0
0x140012869  movzx   esi, r9b
0x14001286d  movups  xmmword ptr [rsp+190h+var_130], xmm0
0x140012872  call    memset
0x140012877  xor     r13d, r13d
0x14001287a  lea     rcx, [rbp+90h+var_C0]; void *
0x14001287e  xor     edx, edx; Val
0x140012880  mov     qword ptr [rsp+190h+var_150], r13
0x140012885  mov     r8d, 90h; Size
0x14001288b  call    memset
0x140012890  mov     rax, [rbp+90h+arg_38]
0x140012897  mov     ecx, [rax]
0x140012899  cmp     ecx, 1Ch
0x14001289c  jb      loc_140012A6F
0x1400128a2  mov     rax, 4B53494449534353h
0x1400128ac  mov     [rsp+190h+arg_8], r14
0x1400128b4  mov     r14, [rdi+60h]
0x1400128b8  xor     r8d, r8d; State
0x1400128bb  mov     dword ptr [rbx], 1Ch
0x1400128c1  xor     edx, edx; Type
0x1400128c3  mov     [rbx+4], rax
0x1400128c7  mov     eax, [rdi+248h]
0x1400128cd  mov     [rbx+0Ch], eax
0x1400128d0  lea     eax, [rcx-1Ch]
0x1400128d3  mov     [rbx+18h], eax
0x1400128d6  lea     rcx, [rsp+190h+Event]; Event
0x1400128db  mov     [rbx+10h], r12d
0x1400128df  mov     dword ptr [rbx+1Ch], 21h ; '!'
0x1400128e6  movzx   eax, byte ptr [r14+0Eh]
0x1400128eb  mov     [rbx+28h], al
0x1400128ee  movzx   eax, [rbp+90h+arg_20]
0x1400128f5  mov     [rbx+21h], al
0x1400128f8  movzx   eax, [rbp+90h+arg_28]
0x1400128ff  mov     [rbx+22h], al
0x140012902  mov     [rbx+20h], sil
0x140012906  mov     word ptr [rbx+23h], 0C24Fh
0x14001290c  mov     [rbx+26h], r15b
0x140012910  call    cs:__imp_KeInitializeEvent
0x140012917  nop     dword ptr [rax+rax+00h]
0x14001291c  mov     r15d, [rbx]
0x14001291f  lea     rax, [rsp+190h+var_130]
0x140012924  add     r15d, [rbx+18h]
0x140012928  mov     r12d, 1
0x14001292e  mov     rdx, [rdi+10h]; DeviceObject
0x140012932  mov     r9d, r15d; Length
0x140012935  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x14001293a  mov     r8, rbx; Buffer
0x14001293d  lea     rax, [rsp+190h+Event]
0x140012942  mov     qword ptr [rsp+190h+var_150], r12
0x140012947  mov     [rsp+190h+var_168], rax; Event
0x14001294c  mov     ecx, 0Fh; MajorFunction
0x140012951  lea     rax, [rsp+190h+var_150]
0x140012956  mov     [rsp+190h+StartingOffset], rax; StartingOffset
0x14001295b  call    cs:__imp_IoBuildSynchronousFsdRequest
0x140012962  nop     dword ptr [rax+rax+00h]
0x140012967  mov     rsi, rax
0x14001296a  test    rax, rax
0x14001296d  jz      loc_140012A76
0x140012973  mov     rcx, [rax+0B8h]
0x14001297a  mov     word ptr [rcx-48h], 10Fh
0x140012980  mov     rax, [rdi+210h]
0x140012987  cmp     [rax+1Eh], r12b
0x14001298b  jz      loc_140012A7D
0x140012991  lea     rax, [rsp+190h+var_120]
0x140012996  mov     [rcx-40h], rax
0x14001299a  movzx   eax, byte ptr [r14+0Dh]
0x14001299f  mov     [rsp+190h+var_11B], al
0x1400129a3  movzx   eax, byte ptr [r14+0Eh]
0x1400129a8  mov     [rsp+190h+var_11A], al
0x1400129ac  movzx   eax, byte ptr [r14+0Fh]
0x1400129b1  mov     [rsp+190h+var_119], al
0x1400129b5  mov     eax, 58h ; 'X'
0x1400129ba  mov     [rsp+190h+var_120], ax
0x1400129bf  mov     eax, [rdi+250h]
0x1400129c5  or      eax, 100140h
0x1400129ca  mov     [rsp+190h+var_11E], 2
0x1400129cf  mov     [rsp+190h+var_114], eax
0x1400129d3  mov     eax, [rbx+0Ch]
0x1400129d6  mov     [rbp+90h+var_10C], eax
0x1400129d9  mov     [rsp+190h+var_118], 20FFh
0x1400129e0  mov     [rbp+90h+var_F0], rsi
0x1400129e4  mov     [rbp+90h+var_108], rbx
0x1400129e8  mov     [rbp+90h+var_110], r15d
0x1400129ec  mov     rcx, [rsi+8]
0x1400129f0  movzx   r8d, r12b
0x1400129f4  xor     edx, edx
0x1400129f6  call    cs:__imp_KeFlushIoBuffers
0x1400129fd  nop     dword ptr [rax+rax+00h]
0x140012a02  mov     rcx, [rdi+10h]; DeviceObject
0x140012a06  mov     rdx, rsi; Irp
0x140012a09  call    cs:__imp_IofCallDriver
0x140012a10  nop     dword ptr [rax+rax+00h]
0x140012a15  cmp     eax, 103h
0x140012a1a  jnz     short loc_140012A3E
0x140012a1c  xor     r9d, r9d; Alertable
0x140012a1f  mov     [rsp+190h+StartingOffset], r13; Timeout
0x140012a24  xor     r8d, r8d; WaitMode
0x140012a27  lea     rcx, [rsp+190h+Event]; Object
0x140012a2c  xor     edx, edx; WaitReason
0x140012a2e  call    cs:__imp_KeWaitForSingleObject
0x140012a35  nop     dword ptr [rax+rax+00h]
0x140012a3a  mov     eax, dword ptr [rsp+190h+var_130]
0x140012a3e  mov     r14, [rsp+190h+arg_8]
0x140012a46  mov     rcx, [rbp+90h+var_30]
0x140012a4a  xor     rcx, rsp; StackCookie
0x140012a4d  call    __security_check_cookie
0x140012a52  lea     r11, [rsp+190h+var_20]
0x140012a5a  mov     rbx, [r11+40h]
0x140012a5e  mov     rsi, [r11+48h]
0x140012a62  mov     rsp, r11
0x140012a65  pop     r15
0x140012a67  pop     r13
0x140012a69  pop     r12
0x140012a6b  pop     rdi
0x140012a6c  pop     rbp
0x140012a6d  retn
0x140012a6f  mov     eax, 0C0000023h
0x140012a74  jmp     short loc_140012A46
0x140012a76  mov     eax, 0C000009Ah
0x140012a7b  jmp     short loc_140012A3E
0x140012a7d  lea     rax, [rbp+90h+var_C0]
0x140012a81  mov     [rcx-40h], rax
0x140012a85  mov     eax, 8
0x140012a8a  mov     rcx, rsi; Irp
0x140012a8d  mov     [rbp+90h+var_C0], ax
0x140012a91  mov     [rbp+90h+var_BE], 28h ; '('
0x140012a95  mov     [rbp+90h+var_B8], 53524258h
0x140012a9c  mov     [rbp+90h+var_B4], r12d
0x140012aa0  mov     [rbp+90h+var_B0], 90h
0x140012aa7  mov     [rbp+90h+var_AC], 2
0x140012aae  call    cs:__imp_IoGetIoPriorityHint
0x140012ab5  nop     dword ptr [rax+rax+00h]
0x140012aba  mov     [rbp+90h+var_9C], ax
0x140012abe  mov     eax, [rdi+250h]
0x140012ac4  or      eax, 100140h
0x140012ac9  mov     [rbp+90h+var_8C], 80h
0x140012ad0  mov     [rbp+90h+var_A8], eax
0x140012ad3  mov     eax, 20h ; ' '
0x140012ad8  mov     [rbp+90h+var_9A], ax
0x140012adc  mov     eax, [rbx+0Ch]
0x140012adf  mov     [rbp+90h+var_98], eax
0x140012ae2  mov     [rbp+90h+var_A0], 0FFh
0x140012ae9  mov     [rbp+90h+var_70], rsi
0x140012aed  mov     [rbp+90h+var_80], rbx
0x140012af1  mov     [rbp+90h+var_84], r15d
0x140012af5  mov     [rbp+90h+var_40], r12w
0x140012afa  mov     [rbp+90h+var_3C], 4
0x140012b01  movzx   eax, byte ptr [r14+0Dh]
0x140012b06  mov     [rbp+90h+var_38], al
0x140012b09  movzx   eax, byte ptr [r14+0Eh]
0x140012b0e  mov     [rbp+90h+var_37], al
0x140012b11  movzx   eax, byte ptr [r14+0Fh]
0x140012b16  mov     [rsp+190h+var_119], al
0x140012b1a  mov     [rbp+90h+var_36], al
0x140012b1d  jmp     loc_1400129EC
```
