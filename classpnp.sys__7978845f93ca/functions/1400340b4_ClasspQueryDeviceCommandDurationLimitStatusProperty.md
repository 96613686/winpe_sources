# ClasspQueryDeviceCommandDurationLimitStatusProperty

- ea: `0x1400340b4`
- end: `0x1400344a1`
- name: `ClasspQueryDeviceCommandDurationLimitStatusProperty`
- size: `1005`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x14002c674`
- `0x140031634`
- `0x1400317b4`
- `0x1400340b4`
- `0x140037650`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140034433`
- `ntoskrnl!KeReleaseMutex` at `0x140034433`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400341f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400341f2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140034174`
- `ntoskrnl!KeGetCurrentIrql` at `0x140034174`

## pseudocode

```c
__int64 __fastcall ClasspQueryDeviceCommandDurationLimitStatusProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r15
  unsigned int v3; // r12d
  _IRP *MasterIrp; // rdi
  char v5; // r13
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v9; // r8d
  unsigned int v10; // ebx
  size_t Length; // r14
  int v12; // eax
  __int64 v13; // r10
  __int64 v14; // rcx
  __int64 i; // r9
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // r10
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // r10
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int16 *v28; // r10
  __int64 v29; // rcx
  __int64 j; // r9
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // r10
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r9
  __int64 v39; // r8
  __int64 v40; // r10
  __int64 v41; // rcx
  __int64 v42; // rax

  DeviceExtension = DeviceObject->DeviceExtension;
  v3 = 0;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v5 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 190, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v9 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v9 == 1 )
    goto LABEL_41;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        191,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v9);
    }
    v10 = -1073741637;
    goto LABEL_42;
  }
  if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 192, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
    v10 = -1073741496;
    goto LABEL_42;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (unsigned int)Length < 8 )
  {
    v10 = -1073741789;
    goto LABEL_42;
  }
  KeWaitForSingleObject((PVOID)(DeviceExtension[143] + 56LL), Executive, 0, 0, 0);
  v5 = 1;
  v12 = ClasspInitializeCommandDurationLimit(DeviceExtension);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        193,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v12);
    }
    goto LABEL_42;
  }
  if ( (unsigned __int8)ClasspIsCommandDurationLimitSupported(DeviceExtension) )
  {
    memset(MasterIrp, 0, Length);
    *(_DWORD *)&MasterIrp->Type = 352;
    *(_DWORD *)(&MasterIrp->Size + 1) = 352;
    if ( (unsigned int)Length >= 0x160 )
    {
      v13 = DeviceExtension[143];
      v14 = LODWORD(MasterIrp->MdlAddress)
          ^ ((unsigned __int8)LODWORD(MasterIrp->MdlAddress)
           ^ (unsigned __int8)(*(unsigned __int16 *)(v13 + 112) >> 2))
          & 1u;
      LODWORD(MasterIrp->MdlAddress) = v14;
      for ( i = 0; i != 7; ++i )
      {
        v16 = *(unsigned __int8 *)(v13 + i + 114);
        if ( (unsigned __int8)v16 < 7u )
        {
          LOBYTE(v14) = *(_BYTE *)(v13 + 20 * v16 + 132);
          v17 = ClasspConvertCommandLimitDurationTo100ns(v14, *(unsigned __int16 *)(v13 + 20 * v16 + 136));
          *((_QWORD *)&MasterIrp->Flags + v18) = v17;
          LOBYTE(v21) = *(_BYTE *)(v20 + 4 * v19 + 132);
          v22 = ClasspConvertCommandLimitDurationTo100ns(v21, *(unsigned __int16 *)(v20 + 4 * v19 + 138));
          *((_QWORD *)&MasterIrp->UserIosb + v23) = v22;
          LOBYTE(v26) = *(_BYTE *)(v25 + 4 * v24 + 132);
          v27 = ClasspConvertCommandLimitDurationTo100ns(v26, *(unsigned __int16 *)(v25 + 4 * v24 + 140));
          *((_QWORD *)&MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink + i) = v27;
        }
      }
      v28 = (unsigned __int16 *)(DeviceExtension[143] + 284LL);
      v29 = LODWORD(MasterIrp->MdlAddress)
          ^ ((unsigned __int8)LODWORD(MasterIrp->MdlAddress)
           ^ (unsigned __int8)(*v28 >> 1))
          & 2u;
      LODWORD(MasterIrp->MdlAddress) = v29;
      for ( j = 0; j != 7; ++j )
      {
        v31 = *((unsigned __int8 *)v28 + j + 2);
        if ( (unsigned __int8)v31 < 7u )
        {
          LOBYTE(v29) = v28[10 * v31 + 10];
          v32 = ClasspConvertCommandLimitDurationTo100ns(v29, v28[10 * v31 + 12]);
          *((_QWORD *)&MasterIrp->Tail.Overlay.CurrentStackLocation + v33) = v32;
          LOBYTE(v36) = *(_BYTE *)(v35 + 4 * v34 + 20);
          v37 = ClasspConvertCommandLimitDurationTo100ns(v36, *(unsigned __int16 *)(v35 + 4 * v34 + 26));
          *((_QWORD *)&MasterIrp[1].ThreadListEntry.Flink + v38) = v37;
          LOBYTE(v41) = *(_BYTE *)(v40 + 4 * v39 + 20);
          v42 = ClasspConvertCommandLimitDurationTo100ns(v41, *(unsigned __int16 *)(v40 + 4 * v39 + 28));
          *(&MasterIrp[1].Overlay.AllocationSize.QuadPart + j) = v42;
        }
      }
      v3 = *(_DWORD *)(&MasterIrp->Size + 1);
    }
    else
    {
      v3 = 8;
    }
LABEL_41:
    v10 = 0;
    goto LABEL_42;
  }
  v10 = -1073741637;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qdd(
      WPP_GLOBAL_Control->AttachedDevice,
      194,
      *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
      DeviceObject,
      *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
      *(_WORD *)(DeviceExtension[143] + 284LL) & 1);
  }
LABEL_42:
  Irp->IoStatus.Information = v3;
  Irp->IoStatus.Status = v10;
  if ( v5 )
    KeReleaseMutex((PRKMUTEX)(DeviceExtension[143] + 56LL), 0);
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      195,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1400340b4  push    rbx
0x1400340b6  push    rbp
0x1400340b7  push    rsi
0x1400340b8  push    rdi
0x1400340b9  push    r12
0x1400340bb  push    r13
0x1400340bd  push    r14
0x1400340bf  push    r15
0x1400340c1  sub     rsp, 38h
0x1400340c5  mov     r15, [rcx+40h]
0x1400340c9  xor     r12d, r12d
0x1400340cc  mov     rdi, [rdx+18h]
0x1400340d0  xor     r13b, r13b
0x1400340d3  mov     r14, [rdx+0B8h]
0x1400340da  mov     rbp, rdx
0x1400340dd  mov     rsi, rcx
0x1400340e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400340e7  lea     rax, WPP_GLOBAL_Control
0x1400340ee  mov     bl, 10h
0x1400340f0  cmp     rcx, rax
0x1400340f3  jz      short loc_140034121
0x1400340f5  mov     eax, [rcx+2Ch]
0x1400340f8  test    bl, al
0x1400340fa  jz      short loc_14003411A
0x1400340fc  cmp     byte ptr [rcx+29h], 5
0x140034100  jb      short loc_14003411A
0x140034102  mov     rcx, [rcx+18h]
0x140034106  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003410d  mov     edx, 0BEh
0x140034112  mov     r9, rsi
0x140034115  call    WPP_SF_q
0x14003411a  lea     rax, WPP_GLOBAL_Control
0x140034121  mov     r8d, [rdi+4]
0x140034125  cmp     r8d, 1
0x140034129  jz      loc_14003440E
0x14003412f  test    r8d, r8d
0x140034132  jz      short loc_140034174
0x140034134  mov     rcx, cs:WPP_GLOBAL_Control
0x14003413b  cmp     rcx, rax
0x14003413e  jz      short loc_14003416A
0x140034140  mov     eax, [rcx+2Ch]
0x140034143  test    bl, al
0x140034145  jz      short loc_14003416A
0x140034147  cmp     byte ptr [rcx+29h], 2
0x14003414b  jb      short loc_14003416A
0x14003414d  mov     rcx, [rcx+18h]
0x140034151  mov     edx, 0BFh
0x140034156  mov     dword ptr [rsp+78h+Timeout], r8d
0x14003415b  mov     r9, rsi
0x14003415e  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034165  call    WPP_SF_qD
0x14003416a  mov     ebx, 0C00000BBh
0x14003416f  jmp     loc_140034410
0x140034174  call    cs:__imp_KeGetCurrentIrql
0x14003417b  nop     dword ptr [rax+rax+00h]
0x140034180  cmp     al, 2
0x140034182  jb      short loc_1400341C6
0x140034184  mov     rcx, cs:WPP_GLOBAL_Control
0x14003418b  lea     rdi, WPP_GLOBAL_Control
0x140034192  cmp     rcx, rdi
0x140034195  jz      short loc_1400341BC
0x140034197  mov     eax, [rcx+2Ch]
0x14003419a  test    bl, al
0x14003419c  jz      short loc_1400341BC
0x14003419e  cmp     byte ptr [rcx+29h], 2
0x1400341a2  jb      short loc_1400341BC
0x1400341a4  mov     rcx, [rcx+18h]
0x1400341a8  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400341af  mov     edx, 0C0h
0x1400341b4  mov     r9, rsi
0x1400341b7  call    WPP_SF_q
0x1400341bc  mov     ebx, 0C0000148h
0x1400341c1  jmp     loc_140034417
0x1400341c6  mov     r14d, [r14+8]
0x1400341ca  cmp     r14d, 8
0x1400341ce  jnb     short loc_1400341DA
0x1400341d0  mov     ebx, 0C0000023h
0x1400341d5  jmp     loc_140034410
0x1400341da  mov     rcx, [r15+478h]
0x1400341e1  xor     r9d, r9d; Alertable
0x1400341e4  add     rcx, 38h ; '8'; Object
0x1400341e8  mov     [rsp+78h+Timeout], r12; Timeout
0x1400341ed  xor     r8d, r8d; WaitMode
0x1400341f0  xor     edx, edx; WaitReason
0x1400341f2  call    cs:__imp_KeWaitForSingleObject
0x1400341f9  nop     dword ptr [rax+rax+00h]
0x1400341fe  mov     rcx, r15
0x140034201  mov     r13b, 1
0x140034204  call    ClasspInitializeCommandDurationLimit
0x140034209  mov     ebx, eax
0x14003420b  test    eax, eax
0x14003420d  jns     short loc_14003425D
0x14003420f  mov     rcx, cs:WPP_GLOBAL_Control
0x140034216  lea     rdi, WPP_GLOBAL_Control
0x14003421d  cmp     rcx, rdi
0x140034220  jz      loc_140034417
0x140034226  mov     edx, [rcx+2Ch]
0x140034229  test    dl, 10h
0x14003422c  jz      loc_140034417
0x140034232  cmp     byte ptr [rcx+29h], 2
0x140034236  jb      loc_140034417
0x14003423c  mov     rcx, [rcx+18h]
0x140034240  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034247  mov     edx, 0C1h
0x14003424c  mov     dword ptr [rsp+78h+Timeout], eax
0x140034250  mov     r9, rsi
0x140034253  call    WPP_SF_qD
0x140034258  jmp     loc_140034417
0x14003425d  mov     rcx, r15
0x140034260  call    ClasspIsCommandDurationLimitSupported
0x140034265  test    al, al
0x140034267  jnz     short loc_1400342D6
0x140034269  mov     ebx, 0C00000BBh
0x14003426e  mov     rcx, cs:WPP_GLOBAL_Control
0x140034275  lea     rdi, WPP_GLOBAL_Control
0x14003427c  cmp     rcx, rdi
0x14003427f  jz      loc_140034417
0x140034285  mov     eax, [rcx+2Ch]
0x140034288  test    al, 10h
0x14003428a  jz      loc_140034417
0x140034290  cmp     byte ptr [rcx+29h], 2
0x140034294  jb      loc_140034417
0x14003429a  mov     rax, [r15+478h]
0x1400342a1  mov     edx, 0C2h
0x1400342a6  mov     rcx, [rcx+18h]
0x1400342aa  movzx   r9d, word ptr [rax+11Ch]
0x1400342b2  movzx   r8d, word ptr [rax+70h]
0x1400342b7  and     r9d, 1
0x1400342bb  mov     [rsp+78h+var_50], r9d
0x1400342c0  and     r8d, 1
0x1400342c4  mov     r9, rsi
0x1400342c7  mov     dword ptr [rsp+78h+Timeout], r8d
0x1400342cc  call    WPP_SF_qdd
0x1400342d1  jmp     loc_140034417
0x1400342d6  mov     r8, r14; Size
0x1400342d9  xor     edx, edx; Val
0x1400342db  mov     rcx, rdi; void *
0x1400342de  call    memset
0x1400342e3  mov     eax, 160h
0x1400342e8  mov     [rdi], eax
0x1400342ea  mov     [rdi+4], eax
0x1400342ed  cmp     r14d, eax
0x1400342f0  jnb     short loc_1400342FD
0x1400342f2  mov     r12d, 8
0x1400342f8  jmp     loc_14003440E
0x1400342fd  mov     eax, [rdi+8]
0x140034300  mov     r10, [r15+478h]
0x140034307  movzx   ecx, word ptr [r10+70h]
0x14003430c  shr     ecx, 2
0x14003430f  xor     ecx, eax
0x140034311  and     ecx, 1
0x140034314  xor     ecx, eax
0x140034316  mov     [rdi+8], ecx
0x140034319  xor     r9d, r9d
0x14003431c  movzx   eax, byte ptr [r10+r9+72h]
0x140034322  cmp     al, 7
0x140034324  jnb     short loc_14003437E
0x140034326  lea     r8, [rax+rax*4]
0x14003432a  movzx   edx, word ptr [r10+r8*4+88h]
0x140034333  mov     cl, [r10+r8*4+84h]
0x14003433b  call    ClasspConvertCommandLimitDurationTo100ns
0x140034340  mov     [rdi+r9*8+10h], rax
0x140034345  movzx   edx, word ptr [r10+r8*4+8Ah]
0x14003434e  mov     cl, [r10+r8*4+84h]
0x140034356  call    ClasspConvertCommandLimitDurationTo100ns
0x14003435b  mov     [rdi+r9*8+48h], rax
0x140034360  movzx   edx, word ptr [r10+r8*4+8Ch]
0x140034369  mov     cl, [r10+r8*4+84h]
0x140034371  call    ClasspConvertCommandLimitDurationTo100ns
0x140034376  mov     [rdi+r9*8+80h], rax
0x14003437e  inc     r9
0x140034381  cmp     r9, 7
0x140034385  jnz     short loc_14003431C
0x140034387  mov     eax, [rdi+8]
0x14003438a  mov     r10, [r15+478h]
0x140034391  add     r10, 11Ch
0x140034398  movzx   ecx, word ptr [r10]
0x14003439c  shr     ecx, 1
0x14003439e  xor     ecx, eax
0x1400343a0  and     ecx, 2
0x1400343a3  xor     ecx, eax
0x1400343a5  mov     [rdi+8], ecx
0x1400343a8  xor     r9d, r9d
0x1400343ab  movzx   eax, byte ptr [r10+r9+2]
0x1400343b1  cmp     al, 7
0x1400343b3  jnb     short loc_140034401
0x1400343b5  lea     r8, [rax+rax*4]
0x1400343b9  movzx   edx, word ptr [r10+r8*4+18h]
0x1400343bf  mov     cl, [r10+r8*4+14h]
0x1400343c4  call    ClasspConvertCommandLimitDurationTo100ns
0x1400343c9  mov     [rdi+r9*8+0B8h], rax
0x1400343d1  movzx   edx, word ptr [r10+r8*4+1Ah]
0x1400343d7  mov     cl, [r10+r8*4+14h]
0x1400343dc  call    ClasspConvertCommandLimitDurationTo100ns
0x1400343e1  mov     [rdi+r9*8+0F0h], rax
0x1400343e9  movzx   edx, word ptr [r10+r8*4+1Ch]
0x1400343ef  mov     cl, [r10+r8*4+14h]
0x1400343f4  call    ClasspConvertCommandLimitDurationTo100ns
0x1400343f9  mov     [rdi+r9*8+128h], rax
0x140034401  inc     r9
0x140034404  cmp     r9, 7
0x140034408  jnz     short loc_1400343AB
0x14003440a  mov     r12d, [rdi+4]
0x14003440e  xor     ebx, ebx
0x140034410  lea     rdi, WPP_GLOBAL_Control
0x140034417  mov     eax, r12d
0x14003441a  mov     [rbp+38h], rax
0x14003441e  mov     [rbp+30h], ebx
0x140034421  test    r13b, r13b
0x140034424  jz      short loc_14003443F
0x140034426  mov     rcx, [r15+478h]
0x14003442d  xor     edx, edx; Wait
0x14003442f  add     rcx, 38h ; '8'; Mutex
0x140034433  call    cs:__imp_KeReleaseMutex
0x14003443a  nop     dword ptr [rax+rax+00h]
0x14003443f  mov     rdx, rbp; Tag
0x140034442  mov     rcx, rsi; DeviceObject
0x140034445  call    ClassReleaseRemoveLock
0x14003444a  xor     r8d, r8d; PriorityBoost
0x14003444d  mov     rdx, rbp; Irp
0x140034450  mov     rcx, rsi; DeviceObject
0x140034453  call    ClassCompleteRequest
0x140034458  mov     rcx, cs:WPP_GLOBAL_Control
0x14003445f  cmp     rcx, rdi
0x140034462  jz      short loc_14003448D
0x140034464  mov     eax, [rcx+2Ch]
0x140034467  test    al, 10h
0x140034469  jz      short loc_14003448D
0x14003446b  cmp     byte ptr [rcx+29h], 5
0x14003446f  jb      short loc_14003448D
0x140034471  mov     rcx, [rcx+18h]
0x140034475  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003447c  mov     edx, 0C3h
0x140034481  mov     dword ptr [rsp+78h+Timeout], ebx
0x140034485  mov     r9, rsi
0x140034488  call    WPP_SF_qD
0x14003448d  mov     eax, ebx
0x14003448f  add     rsp, 38h
0x140034493  pop     r15
0x140034495  pop     r14
0x140034497  pop     r13
0x140034499  pop     r12
0x14003449b  pop     rdi
0x14003449c  pop     rsi
0x14003449d  pop     rbp
0x14003449e  pop     rbx
0x14003449f  retn
```
