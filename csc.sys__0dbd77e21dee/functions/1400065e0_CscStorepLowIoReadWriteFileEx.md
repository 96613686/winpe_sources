# CscStorepLowIoReadWriteFileEx

- ea: `0x1400065e0`
- end: `0x14000685e`
- name: `CscStorepLowIoReadWriteFileEx`
- size: `638`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int64 LowLimit, __int64, __int64)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140007228`
- `0x140007488`
- `0x140007ff8`
- `0x140016ad8`
- `0x1400171c0`
- `0x140029a78`
- `0x140029e9c`
- `0x14002cf50`

## callees

- `0x1400065e0`
- `0x140006870`
- `0x140006a00`
- `0x140018930`
- `0x14001a494`
- `0x14002a1fc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140006717`
- `ntoskrnl!ObfDereferenceObject` at `0x140006717`
- `ntoskrnl!IoFileObjectType` at `0x1400066d4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400066fd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400066fd`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140006679`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140006679`
- `ntoskrnl!IoGetStackLimits` at `0x14000663d`
- `ntoskrnl!IoGetStackLimits` at `0x14000663d`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoReadWriteFileEx(
        void *a1,
        unsigned __int8 a2,
        __int64 a3,
        ULONG a4,
        struct _FILE_OBJECT *LowLimit,
        __int64 a6,
        __int64 a7)
{
  NTSTATUS v7; // eax
  int v8; // ebx
  int v9; // edi
  __int64 v11; // rdx
  char v12; // al
  int Context; // [rsp+20h] [rbp-41h]
  unsigned __int64 HighLimit[2]; // [rsp+50h] [rbp-11h] BYREF
  HANDLE Parameter; // [rsp+60h] [rbp-1h] BYREF
  __int64 Parameter_8; // [rsp+68h] [rbp+7h]
  ULONG Length[4]; // [rsp+70h] [rbp+Fh]
  __int64 v18[2]; // [rsp+80h] [rbp+1Fh]
  __int128 v19; // [rsp+90h] [rbp+2Fh]

  v18[0] = (__int64)LowLimit;
  v18[1] = (unsigned __int8)a6;
  Length[3] = 0;
  Parameter = a1;
  Parameter_8 = a2;
  v19 = (unsigned __int64)a7;
  *(_QWORD *)Length = a3;
  Length[2] = a4;
  HighLimit[0] = 0;
  LowLimit = 0;
  IoGetStackLimits((PULONG_PTR)&LowLimit, HighLimit);
  if ( (char *)HighLimit - (char *)LowLimit >= (unsigned __int64)(unsigned int)dword_14003BD20 )
  {
    CscStorepLowIoReadWriteFileExCallout(&Parameter);
    return DWORD2(v19);
  }
  v7 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoReadWriteFileExCallout, &Parameter, 0x6000u, 0, 0);
  if ( v7 >= 0 )
    return DWORD2(v19);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_0d06f681978d342119bb40210e69c50f_Traceguids, (unsigned int)v7);
  LowLimit = 0;
  LODWORD(a6) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v11 = 78;
    v12 = 78;
    if ( LOBYTE(v18[1]) )
      v12 = 89;
    if ( (_BYTE)Parameter_8 )
      v11 = 89;
    LOBYTE(Context) = v11;
    WPP_SF_qcIDqc(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      89,
      Parameter,
      Context,
      *(_QWORD *)Length,
      Length[2],
      v18[0],
      v12);
  }
  v8 = ObReferenceObjectByHandle(Parameter, 0, (POBJECT_TYPE)IoFileObjectType, 0, (PVOID *)&LowLimit, 0);
  if ( v8 < 0 )
  {
    v9 = 2849;
  }
  else
  {
    ObfDereferenceObject(LowLimit);
    v9 = 0;
    v8 = CscStorepLowIoReadWriteFileIrpEx(
           LowLimit,
           Parameter_8,
           v18[1],
           *(__int64 *)Length,
           Length[2],
           Length[2],
           (void *)v18[0],
           0,
           (unsigned int *)&a6);
  }
  *(_DWORD *)v19 = a6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      (unsigned int)a6,
      v8,
      v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400065e0  mov     [rsp-8+arg_18], rsi
0x1400065e5  push    rbp
0x1400065e6  lea     rbp, [rsp-3Fh]
0x1400065eb  sub     rsp, 0A0h
0x1400065f2  mov     rax, [rbp+3Fh+LowLimit]
0x1400065f6  xorps   xmm0, xmm0
0x1400065f9  movups  xmmword ptr [rbp+3Fh+var_20], xmm0
0x1400065fd  mov     [rbp+3Fh+var_20], rax
0x140006601  xor     esi, esi
0x140006603  movzx   eax, byte ptr [rbp+3Fh+arg_28]
0x140006607  movups  [rbp+3Fh+Parameter], xmm0
0x14000660b  mov     byte ptr [rbp+3Fh+var_20+8], al
0x14000660e  mov     rax, [rbp+3Fh+arg_30]
0x140006612  movups  xmmword ptr [rbp+3Fh+Length], xmm0
0x140006616  mov     qword ptr [rbp+3Fh+Parameter], rcx
0x14000661a  lea     rcx, [rbp+3Fh+LowLimit]; LowLimit
0x14000661e  mov     byte ptr [rbp+3Fh+Parameter+8], dl
0x140006621  lea     rdx, [rbp+3Fh+HighLimit]; HighLimit
0x140006625  movups  [rbp+3Fh+var_10], xmm0
0x140006629  mov     qword ptr [rbp+3Fh+var_10], rax
0x14000662d  mov     qword ptr [rbp+3Fh+Length], r8
0x140006631  mov     [rbp+3Fh+Length+8], r9d
0x140006635  mov     [rbp+3Fh+HighLimit], rsi
0x140006639  mov     [rbp+3Fh+LowLimit], rsi
0x14000663d  call    cs:__imp_IoGetStackLimits
0x140006644  nop     dword ptr [rax+rax+00h]
0x140006649  mov     eax, cs:dword_14003BD20
0x14000664f  lea     rcx, [rbp+3Fh+HighLimit]
0x140006653  sub     rcx, [rbp+3Fh+LowLimit]
0x140006657  cmp     rcx, rax
0x14000665a  jnb     loc_1400067CC
0x140006660  xor     r9d, r9d; Wait
0x140006663  mov     [rsp+0A0h+Context], rsi; Context
0x140006668  mov     r8d, 6000h; Size
0x14000666e  lea     rdx, [rbp+3Fh+Parameter]; Parameter
0x140006672  lea     rcx, CscStorepLowIoReadWriteFileExCallout; Callout
0x140006679  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140006680  nop     dword ptr [rax+rax+00h]
0x140006685  test    eax, eax
0x140006687  jns     loc_1400067D5
0x14000668d  mov     [rsp+0A0h+arg_0], rbx
0x140006695  mov     [rsp+0A0h+arg_10], r14
0x14000669d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066a4  lea     r14, WPP_GLOBAL_Control
0x1400066ab  cmp     rcx, r14
0x1400066ae  jnz     loc_1400067E4
0x1400066b4  mov     [rbp+3Fh+LowLimit], rsi
0x1400066b8  mov     dword ptr [rbp+3Fh+arg_28], esi
0x1400066bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066c2  cmp     rcx, r14
0x1400066c5  jz      short loc_1400066D4
0x1400066c7  test    dword ptr [rcx+2Ch], 40000h
0x1400066ce  jnz     loc_14000680E
0x1400066d4  mov     r8, cs:__imp_IoFileObjectType
0x1400066db  lea     rax, [rbp+3Fh+LowLimit]
0x1400066df  mov     rcx, qword ptr [rbp+3Fh+Parameter]; Handle
0x1400066e3  xor     r9d, r9d; AccessMode
0x1400066e6  mov     [rsp+0A0h+HandleInformation], rsi; HandleInformation
0x1400066eb  xor     edx, edx; DesiredAccess
0x1400066ed  mov     [rsp+0A0h+arg_8], rdi
0x1400066f5  mov     r8, [r8]; ObjectType
0x1400066f8  mov     [rsp+0A0h+Context], rax; Object
0x1400066fd  call    cs:__imp_ObReferenceObjectByHandle
0x140006704  nop     dword ptr [rax+rax+00h]
0x140006709  mov     ebx, eax
0x14000670b  test    eax, eax
0x14000670d  js      loc_1400067DA
0x140006713  mov     rcx, [rbp+3Fh+LowLimit]; Object
0x140006717  call    cs:__imp_ObfDereferenceObject
0x14000671e  nop     dword ptr [rax+rax+00h]
0x140006723  mov     edx, [rbp+3Fh+Length+8]
0x140006726  lea     rax, [rbp+3Fh+arg_28]
0x14000672a  mov     r9, qword ptr [rbp+3Fh+Length]
0x14000672e  mov     edi, esi
0x140006730  movzx   r8d, byte ptr [rbp+3Fh+var_20+8]
0x140006735  mov     rcx, [rbp+3Fh+LowLimit]; FileObject
0x140006739  mov     [rsp+0A0h+var_60], rax; __int64
0x14000673e  mov     rax, [rbp+3Fh+var_20]
0x140006742  mov     [rsp+0A0h+var_68], rsi; __int64
0x140006747  mov     [rsp+0A0h+var_70], rax; __int64
0x14000674c  mov     dword ptr [rsp+0A0h+HandleInformation], edx; Length
0x140006750  mov     dword ptr [rsp+0A0h+Context], edx; int
0x140006754  movzx   edx, byte ptr [rbp+3Fh+Parameter+8]
0x140006758  call    CscStorepLowIoReadWriteFileIrpEx
0x14000675d  mov     ebx, eax
0x14000675f  mov     rcx, qword ptr [rbp+3Fh+var_10]
0x140006763  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x140006766  mov     [rcx], eax
0x140006768  mov     rcx, cs:WPP_GLOBAL_Control
0x14000676f  cmp     rcx, r14
0x140006772  mov     r14, [rsp+0A0h+arg_10]
0x14000677a  jnz     short loc_1400067A0
0x14000677c  mov     rdi, [rsp+0A0h+arg_8]
0x140006784  mov     eax, ebx
0x140006786  mov     rbx, [rsp+0A0h+arg_0]
0x14000678e  mov     rsi, [rsp+0A0h+arg_18]
0x140006796  add     rsp, 0A0h
0x14000679d  pop     rbp
0x14000679e  retn
0x1400067a0  test    dword ptr [rcx+2Ch], 40000h
0x1400067a7  jz      short loc_14000677C
0x1400067a9  mov     r9d, dword ptr [rbp+3Fh+arg_28]
0x1400067ad  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x1400067b4  mov     rcx, [rcx+18h]
0x1400067b8  mov     edx, 25h ; '%'
0x1400067bd  mov     dword ptr [rsp+0A0h+HandleInformation], edi
0x1400067c1  mov     dword ptr [rsp+0A0h+Context], ebx
0x1400067c5  call    WPP_SF_DDd
0x1400067ca  jmp     short loc_14000677C
0x1400067cc  lea     rcx, [rbp+3Fh+Parameter]; Parameter
0x1400067d0  call    CscStorepLowIoReadWriteFileExCallout
0x1400067d5  mov     eax, dword ptr [rbp+3Fh+var_10+8]
0x1400067d8  jmp     short loc_14000678E
0x1400067da  mov     edi, 0B21h
0x1400067df  jmp     loc_14000675F
0x1400067e4  test    dword ptr [rcx+2Ch], 40000h
0x1400067eb  jz      loc_1400066B4
0x1400067f1  mov     rcx, [rcx+18h]
0x1400067f5  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x1400067fc  mov     edx, 26h ; '&'
0x140006801  mov     r9d, eax
0x140006804  call    WPP_SF_d
0x140006809  jmp     loc_1400066B4
0x14000680e  cmp     byte ptr [rbp+3Fh+var_20+8], sil
0x140006812  mov     edx, 4Eh ; 'N'
0x140006817  mov     r9, qword ptr [rbp+3Fh+Parameter]
0x14000681b  mov     eax, edx
0x14000681d  mov     rcx, [rcx+18h]
0x140006821  mov     r8d, 59h ; 'Y'
0x140006827  cmovnz  eax, r8d
0x14000682b  cmp     byte ptr [rbp+3Fh+Parameter+8], sil
0x14000682f  mov     byte ptr [rsp+0A0h+var_60], al
0x140006833  mov     rax, [rbp+3Fh+var_20]
0x140006837  cmovnz  edx, r8d
0x14000683b  mov     [rsp+0A0h+var_68], rax
0x140006840  mov     eax, [rbp+3Fh+Length+8]
0x140006843  mov     dword ptr [rsp+0A0h+var_70], eax
0x140006847  mov     rax, qword ptr [rbp+3Fh+Length]
0x14000684b  mov     [rsp+0A0h+HandleInformation], rax
0x140006850  mov     byte ptr [rsp+0A0h+Context], dl
0x140006854  call    WPP_SF_qcIDqc
0x140006859  jmp     loc_1400066D4
```
