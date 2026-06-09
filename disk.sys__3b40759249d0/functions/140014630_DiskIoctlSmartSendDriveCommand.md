# DiskIoctlSmartSendDriveCommand

- ea: `0x140014630`
- end: `0x140014afa`
- name: `DiskIoctlSmartSendDriveCommand`
- size: `1226`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x140005d00`
- `0x140014630`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140014a7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014a7e`
- `ntoskrnl!KeInitializeEvent` at `0x1400146cb`
- `ntoskrnl!KeInitializeEvent` at `0x1400146cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001480d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001480d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ab8`
- `ntoskrnl!IofCallDriver` at `0x140014a53`
- `ntoskrnl!IofCallDriver` at `0x140014a53`
- `ntoskrnl!ExAllocatePool2` at `0x140014713`
- `ntoskrnl!ExAllocatePool2` at `0x140014713`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400147e3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400147e3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014673`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014673`

## pseudocode

```c
__int64 __fastcall DiskIoctlSmartSendDriveCommand(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v3; // rbx
  _BYTE *v4; // rsi
  __int64 v7; // r13
  unsigned int v8; // edx
  int v9; // ebp
  unsigned int v10; // ebx
  __int64 Pool2; // rax
  __int64 OutputBuffer; // r14
  bool v14; // zf
  size_t v15; // r8
  IRP *v16; // rax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  unsigned int Status; // ebp
  __int64 v22; // rbx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a2 + 184);
  v4 = *(_BYTE **)(a2 + 24);
  v7 = *(_QWORD *)(v2 + 96);
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  if ( *(_DWORD *)(v3 + 16) < 0x20u )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225485LL;
    }
    v18 = 112;
    goto LABEL_70;
  }
  if ( *(_DWORD *)(v3 + 8) < 0x10u )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v20 = 113;
LABEL_46:
      WPP_SF_(v19->AttachedDevice, v20, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225507LL;
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  if ( v4[10] != 0xB0 )
  {
LABEL_18:
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225485LL;
    }
    v18 = 116;
LABEL_70:
    WPP_SF_(v17->AttachedDevice, v18, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    return 3221225485LL;
  }
  v8 = 0;
  if ( (unsigned __int8)v4[4] != 216 )
  {
    switch ( v4[4] )
    {
      case 0xD2:
        v9 = 1770759;
        goto LABEL_9;
      case 0xD3:
        v9 = 1770760;
        goto LABEL_9;
      case 0xD4:
        if ( v4[6] > 2u )
          goto LABEL_18;
        v9 = 1770761;
        goto LABEL_9;
      case 0xD6:
        if ( *(_DWORD *)(v7 + 16) != 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
          }
          return 3221225488LL;
        }
        v8 = (unsigned __int8)v4[5] << 9;
        if ( !v8 )
          return 3221225485LL;
        if ( *(unsigned int *)(v3 + 16) >= (unsigned __int64)v8 + 32 )
        {
          v9 = 1770764;
          goto LABEL_9;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v20 = 115;
          goto LABEL_46;
        }
        break;
      case 0xD9:
        v9 = 1770757;
        goto LABEL_9;
      case 0xDA:
        if ( *(_DWORD *)(v3 + 8) < 0x18u )
          return 3221225507LL;
        v9 = 1770758;
        v8 = 8;
        goto LABEL_9;
      case 0xDB:
        v9 = 1770762;
        goto LABEL_9;
      default:
        goto LABEL_18;
    }
    return 3221225507LL;
  }
  v9 = 1770756;
LABEL_9:
  v10 = v8 + 33;
  Pool2 = ExAllocatePool2(64, v8 + 33 + 28LL, 1631871827);
  OutputBuffer = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225626LL;
  }
  *(_DWORD *)Pool2 = 28;
  *(_QWORD *)(Pool2 + 4) = 0x4B53494449534353LL;
  *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(v2 + 584);
  *(_DWORD *)(Pool2 + 24) = v10;
  *(_DWORD *)(Pool2 + 16) = v9;
  v14 = v4[4] == 0xD6;
  v4[12] = *(_BYTE *)(v7 + 14);
  if ( v14 )
    v15 = ((unsigned __int64)(unsigned __int8)v4[5] << 9) + 32;
  else
    v15 = 32;
  memmove((void *)(Pool2 + 28), *(const void **)(a2 + 24), v15);
  v16 = IoBuildDeviceIoControlRequest(
          0x4D008u,
          *(PDEVICE_OBJECT *)(v2 + 16),
          (PVOID)OutputBuffer,
          v10 + 28,
          (PVOID)OutputBuffer,
          v10 + 28,
          0,
          &Event,
          &IoStatusBlock);
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    ExFreePoolWithTag((PVOID)OutputBuffer, 0);
    return 3221225626LL;
  }
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 16), v16);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  v22 = 24;
  if ( v4[4] != 0xDA )
    v22 = 16;
  memmove(*(void **)(a2 + 24), (const void *)(OutputBuffer + 28), (unsigned int)v22);
  *(_QWORD *)(a2 + 56) = v22;
  ExFreePoolWithTag((PVOID)OutputBuffer, 0);
  return Status;
}

```

## disassembly

```asm
0x140014630  mov     [rsp+arg_10], rbx
0x140014635  push    rbp
0x140014636  push    rsi
0x140014637  push    rdi
0x140014638  push    r13
0x14001463a  push    r15
0x14001463c  sub     rsp, 80h
0x140014643  mov     r15, [rcx+40h]
0x140014647  xorps   xmm0, xmm0
0x14001464a  mov     rbx, [rdx+0B8h]
0x140014651  xorps   xmm1, xmm1
0x140014654  mov     rsi, [rdx+18h]
0x140014658  xor     eax, eax
0x14001465a  mov     rdi, rdx
0x14001465d  mov     rbp, rcx
0x140014660  mov     r13, [r15+60h]
0x140014664  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140014669  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14001466e  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm1
0x140014673  call    cs:__imp_KeGetCurrentIrql
0x14001467a  nop     dword ptr [rax+rax+00h]
0x14001467f  cmp     al, 2
0x140014681  jnb     loc_140014893
0x140014687  mov     rcx, cs:WPP_GLOBAL_Control
0x14001468e  mov     [rsp+0A8h+arg_0], r12
0x140014696  lea     r12, WPP_GLOBAL_Control
0x14001469d  cmp     rcx, r12
0x1400146a0  jz      short loc_1400146AD
0x1400146a2  mov     eax, [rcx+2Ch]
0x1400146a5  test    al, 10h
0x1400146a7  jnz     loc_14001489D
0x1400146ad  cmp     dword ptr [rbx+10h], 20h ; ' '
0x1400146b1  jb      loc_140014870
0x1400146b7  cmp     dword ptr [rbx+8], 10h
0x1400146bb  jb      loc_1400148C9
0x1400146c1  xor     r8d, r8d; State
0x1400146c4  lea     rcx, [rsp+0A8h+Event]; Event
0x1400146c9  xor     edx, edx; Type
0x1400146cb  call    cs:__imp_KeInitializeEvent
0x1400146d2  nop     dword ptr [rax+rax+00h]
0x1400146d7  cmp     byte ptr [rsi+0Ah], 0B0h
0x1400146db  jnz     def_140014856; jumptable 0000000140014856 default case, cases 213,215,216
0x1400146e1  movzx   eax, byte ptr [rsi+4]
0x1400146e5  xor     edx, edx
0x1400146e7  cmp     eax, 0D8h
0x1400146ec  jnz     loc_140014838
0x1400146f2  mov     ebp, 1B0504h
0x1400146f7  lea     ebx, [rdx+21h]
0x1400146fa  mov     [rsp+0A8h+arg_8], r14
0x140014702  mov     edx, ebx
0x140014704  mov     ecx, 40h ; '@'
0x140014709  add     rdx, 1Ch
0x14001470d  mov     r8d, 61446353h
0x140014713  call    cs:__imp_ExAllocatePool2
0x14001471a  nop     dword ptr [rax+rax+00h]
0x14001471f  mov     r14, rax
0x140014722  test    rax, rax
0x140014725  jnz     short loc_140014764
0x140014727  mov     rcx, cs:WPP_GLOBAL_Control
0x14001472e  cmp     rcx, r12
0x140014731  jnz     loc_1400149DC
0x140014737  mov     eax, 0C000009Ah
0x14001473c  mov     r14, [rsp+0A8h+arg_8]
0x140014744  mov     r12, [rsp+0A8h+arg_0]
0x14001474c  mov     rbx, [rsp+0A8h+arg_10]
0x140014754  add     rsp, 80h
0x14001475b  pop     r15
0x14001475d  pop     r13
0x14001475f  pop     rdi
0x140014760  pop     rsi
0x140014761  pop     rbp
0x140014762  retn
0x140014764  mov     dword ptr [rax], 1Ch
0x14001476a  lea     rcx, [r14+1Ch]; void *
0x14001476e  mov     rax, 4B53494449534353h
0x140014778  mov     [r14+4], rax
0x14001477c  mov     eax, [r15+248h]
0x140014783  mov     [r14+0Ch], eax
0x140014787  mov     [r14+18h], ebx
0x14001478b  mov     [r14+10h], ebp
0x14001478f  cmp     byte ptr [rsi+4], 0D6h
0x140014793  movzx   eax, byte ptr [r13+0Eh]
0x140014798  mov     [rsi+0Ch], al
0x14001479b  mov     rdx, [rdi+18h]; Src
0x14001479f  jz      loc_140014A0B
0x1400147a5  mov     r8d, 20h ; ' '; Size
0x1400147ab  call    memmove
0x1400147b0  mov     rdx, [r15+10h]; DeviceObject
0x1400147b4  lea     rax, [rsp+0A8h+var_58]
0x1400147b9  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x1400147be  lea     r9d, [rbx+1Ch]; InputBufferLength
0x1400147c2  lea     rax, [rsp+0A8h+Event]
0x1400147c7  mov     r8, r14; InputBuffer
0x1400147ca  mov     [rsp+0A8h+var_70], rax; Event
0x1400147cf  mov     ecx, 4D008h; IoControlCode
0x1400147d4  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400147d9  mov     [rsp+0A8h+OutputBufferLength], r9d; OutputBufferLength
0x1400147de  mov     [rsp+0A8h+OutputBuffer], r14; OutputBuffer
0x1400147e3  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400147ea  nop     dword ptr [rax+rax+00h]
0x1400147ef  test    rax, rax
0x1400147f2  jnz     loc_140014A4C
0x1400147f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147ff  cmp     rcx, r12
0x140014802  jnz     loc_140014A1D
0x140014808  xor     edx, edx; Tag
0x14001480a  mov     rcx, r14; P
0x14001480d  call    cs:__imp_ExFreePoolWithTag
0x140014814  nop     dword ptr [rax+rax+00h]
0x140014819  jmp     loc_140014737
0x14001481e  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140014856 default case, cases 213,215,216
0x140014825  cmp     rcx, r12
0x140014828  jnz     loc_140014ACB
0x14001482e  mov     eax, 0C000000Dh
0x140014833  jmp     loc_140014744
0x140014838  add     eax, 0FFFFFF2Eh; switch 10 cases
0x14001483d  cmp     eax, 9
0x140014840  ja      short def_140014856; jumptable 0000000140014856 default case, cases 213,215,216
0x140014842  lea     r8, cs:140000000h
0x140014849  cdqe
0x14001484b  mov     ecx, ds:(jpt_140014856 - 140000000h)[r8+rax*4]
0x140014853  add     rcx, r8
0x140014856  jmp     rcx; switch jump
0x14001485c  cmp     dword ptr [rbx+8], 18h; jumptable 0000000140014856 case 218
0x140014860  jnb     loc_14001499B
0x140014866  mov     eax, 0C0000023h
0x14001486b  jmp     loc_140014744
0x140014870  mov     rcx, cs:WPP_GLOBAL_Control
0x140014877  cmp     rcx, r12
0x14001487a  jz      short loc_14001482E
0x14001487c  mov     eax, [rcx+2Ch]
0x14001487f  test    al, 10h
0x140014881  jz      short loc_14001482E
0x140014883  cmp     byte ptr [rcx+29h], 2
0x140014887  jb      short loc_14001482E
0x140014889  mov     edx, 70h ; 'p'
0x14001488e  jmp     loc_140014AE5
0x140014893  mov     eax, 0C0000148h
0x140014898  jmp     loc_14001474C
0x14001489d  cmp     byte ptr [rcx+29h], 4
0x1400148a1  jb      loc_1400146AD
0x1400148a7  mov     rcx, [rcx+18h]
0x1400148ab  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400148b2  mov     edx, 6Fh ; 'o'
0x1400148b7  mov     [rsp+0A8h+OutputBuffer], rdi
0x1400148bc  mov     r9, rbp
0x1400148bf  call    WPP_SF_qq
0x1400148c4  jmp     loc_1400146AD
0x1400148c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148d0  cmp     rcx, r12
0x1400148d3  jz      short loc_140014866
0x1400148d5  mov     eax, [rcx+2Ch]
0x1400148d8  test    al, 10h
0x1400148da  jz      short loc_140014866
0x1400148dc  cmp     byte ptr [rcx+29h], 2
0x1400148e0  jb      short loc_140014866
0x1400148e2  mov     edx, 71h ; 'q'
0x1400148e7  jmp     loc_140014972
0x1400148ec  cmp     dword ptr [r13+10h], 2; jumptable 0000000140014856 case 214
0x1400148f1  jz      short loc_14001492B
0x1400148f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148fa  cmp     rcx, r12
0x1400148fd  jz      short loc_140014921
0x1400148ff  mov     eax, [rcx+2Ch]
0x140014902  test    al, 10h
0x140014904  jz      short loc_140014921
0x140014906  cmp     byte ptr [rcx+29h], 2
0x14001490a  jb      short loc_140014921
0x14001490c  mov     rcx, [rcx+18h]
0x140014910  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140014917  mov     edx, 72h ; 'r'
0x14001491c  call    WPP_SF_
0x140014921  mov     eax, 0C0000010h
0x140014926  jmp     loc_140014744
0x14001492b  movzx   edx, byte ptr [rsi+5]
0x14001492f  shl     edx, 9
0x140014932  test    edx, edx
0x140014934  jz      loc_14001482E
0x14001493a  mov     eax, [rbx+10h]
0x14001493d  mov     ecx, edx
0x14001493f  add     rcx, 20h ; ' '
0x140014943  cmp     rax, rcx
0x140014946  jnb     short loc_140014987
0x140014948  mov     rcx, cs:WPP_GLOBAL_Control
0x14001494f  cmp     rcx, r12
0x140014952  jz      loc_140014866
0x140014958  mov     eax, [rcx+2Ch]
0x14001495b  test    al, 10h
0x14001495d  jz      loc_140014866
0x140014963  cmp     byte ptr [rcx+29h], 2
0x140014967  jb      loc_140014866
0x14001496d  mov     edx, 73h ; 's'
0x140014972  mov     rcx, [rcx+18h]
0x140014976  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14001497d  call    WPP_SF_
0x140014982  jmp     loc_140014866
0x140014987  mov     ebp, 1B050Ch
0x14001498c  jmp     loc_1400146F7
0x140014991  mov     ebp, 1B0505h; jumptable 0000000140014856 case 217
0x140014996  jmp     loc_1400146F7
0x14001499b  mov     ebp, 1B0506h
0x1400149a0  mov     edx, 8
0x1400149a5  jmp     loc_1400146F7
0x1400149aa  mov     ebp, 1B0507h; jumptable 0000000140014856 case 210
0x1400149af  jmp     loc_1400146F7
0x1400149b4  mov     ebp, 1B0508h; jumptable 0000000140014856 case 211
0x1400149b9  jmp     loc_1400146F7
0x1400149be  cmp     byte ptr [rsi+6], 2; jumptable 0000000140014856 case 212
0x1400149c2  ja      def_140014856; jumptable 0000000140014856 default case, cases 213,215,216
0x1400149c8  mov     ebp, 1B0509h
0x1400149cd  jmp     loc_1400146F7
0x1400149d2  mov     ebp, 1B050Ah; jumptable 0000000140014856 case 219
0x1400149d7  jmp     loc_1400146F7
0x1400149dc  mov     eax, [rcx+2Ch]
0x1400149df  test    al, 10h
0x1400149e1  jz      loc_140014737
0x1400149e7  cmp     byte ptr [rcx+29h], 2
0x1400149eb  jb      loc_140014737
0x1400149f1  mov     rcx, [rcx+18h]
0x1400149f5  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400149fc  mov     edx, 75h ; 'u'
0x140014a01  call    WPP_SF_
0x140014a06  jmp     loc_140014737
0x140014a0b  movzx   r8d, byte ptr [rsi+5]
0x140014a10  shl     r8, 9
0x140014a14  add     r8, 20h ; ' '
0x140014a18  jmp     loc_1400147AB
0x140014a1d  mov     eax, [rcx+2Ch]
0x140014a20  test    al, 10h
0x140014a22  jz      loc_140014808
0x140014a28  cmp     byte ptr [rcx+29h], 2
0x140014a2c  jb      loc_140014808
0x140014a32  mov     rcx, [rcx+18h]
0x140014a36  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140014a3d  mov     edx, 76h ; 'v'
0x140014a42  call    WPP_SF_
0x140014a47  jmp     loc_140014808
0x140014a4c  mov     rcx, [r15+10h]; DeviceObject
0x140014a50  mov     rdx, rax; Irp
0x140014a53  call    cs:__imp_IofCallDriver
0x140014a5a  nop     dword ptr [rax+rax+00h]
0x140014a5f  mov     ebp, eax
0x140014a61  cmp     eax, 103h
0x140014a66  jnz     short loc_140014A8E
0x140014a68  xor     r9d, r9d; Alertable
0x140014a6b  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x140014a74  xor     r8d, r8d; WaitMode
0x140014a77  lea     rcx, [rsp+0A8h+Event]; Object
0x140014a7c  xor     edx, edx; WaitReason
0x140014a7e  call    cs:__imp_KeWaitForSingleObject
0x140014a85  nop     dword ptr [rax+rax+00h]
0x140014a8a  mov     ebp, dword ptr [rsp+0A8h+var_58]
0x140014a8e  cmp     byte ptr [rsi+4], 0DAh
0x140014a92  lea     rdx, [r14+1Ch]; Src
0x140014a96  mov     rcx, [rdi+18h]; void *
0x140014a9a  mov     eax, 10h
0x140014a9f  mov     ebx, 18h
0x140014aa4  cmovnz  ebx, eax
0x140014aa7  mov     r8d, ebx; Size
0x140014aaa  call    memmove
0x140014aaf  xor     edx, edx; Tag
0x140014ab1  mov     [rdi+38h], rbx
0x140014ab5  mov     rcx, r14; P
0x140014ab8  call    cs:__imp_ExFreePoolWithTag
0x140014abf  nop     dword ptr [rax+rax+00h]
0x140014ac4  mov     eax, ebp
0x140014ac6  jmp     loc_14001473C
0x140014acb  mov     eax, [rcx+2Ch]
0x140014ace  test    al, 10h
0x140014ad0  jz      loc_14001482E
0x140014ad6  cmp     byte ptr [rcx+29h], 2
0x140014ada  jb      loc_14001482E
0x140014ae0  mov     edx, 74h ; 't'
0x140014ae5  mov     rcx, [rcx+18h]
0x140014ae9  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140014af0  call    WPP_SF_
0x140014af5  jmp     loc_14001482E
```
