# RxpQueryDirectAccessExtentsFsctl

- ea: `0x14004bed8`
- end: `0x14004c3f1`
- name: `RxpQueryDirectAccessExtentsFsctl`
- size: `1305`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x140077390`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x14000f130`
- `0x1400105f0`
- `0x140017a38`
- `0x140017a8c`
- `0x14001810c`
- `0x14001dc44`
- `0x14001e678`
- `0x14001e704`
- `0x14001e78c`
- `0x140025d00`
- `0x14004bed8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004bfe6`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1ed`
- `ntoskrnl!ExAllocatePool2` at `0x14004bfe6`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c38c`

## pseudocode

```c
__int64 __fastcall RxpQueryDirectAccessExtentsFsctl(__int64 a1, int a2, char a3)
{
  unsigned __int16 v5; // ax
  _QWORD *p_NodeTypeCode; // rsi
  unsigned int v7; // ebx
  wchar_t *Pool2; // r15
  PRX_CONTEXT v9; // r14
  int StoredStatus; // r12d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  struct _MRX_FOBX_ *v14; // rax
  struct _MRX_SRV_OPEN_ *Context2; // rax
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rbx
  int v20; // edx
  __int64 v21; // r13
  struct _MRX_FOBX_ *v22; // r14
  __int64 v23; // r8
  __int64 v24; // r8
  struct _MRX_FOBX_ *v25; // rax
  PRX_CONTEXT v27[11]; // [rsp+60h] [rbp-58h] BYREF
  struct _MRX_FOBX_ *v28; // [rsp+D8h] [rbp+20h] BYREF

  v27[0] = 0;
  v28 = 0;
  v5 = RxDecodeFileObject2(a1, v27, &v28);
  if ( v5 != 0xEC22 )
  {
    p_NodeTypeCode = &v27[0]->NodeTypeCode;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
        v28,
        v27[0],
        v5);
    }
    v7 = -1073741811;
    goto LABEL_51;
  }
  p_NodeTypeCode = &v27[0]->NodeTypeCode;
  if ( *(_QWORD *)&v27[0]->TrackerHistory[3].AcquireRelease )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 32, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
    }
    v7 = 0;
    goto LABEL_51;
  }
  Pool2 = (wchar_t *)ExAllocatePool2(256, 72, 1934456914);
  if ( !Pool2 )
  {
    v7 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_iiqd(WPP_GLOBAL_Control->AttachedDevice);
    }
    goto LABEL_51;
  }
  v27[0] = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(p_NodeTypeCode[15] + 32LL) + 48LL), 2u);
  v9 = v27[0];
  if ( v27[0] )
  {
    *(_DWORD *)Pool2 = a2;
    *((_DWORD *)Pool2 + 1) = a3 != 0 ? 0x1000000 : 0x8000000;
    v14 = v28;
    v9->pFcb = (PMRX_FCB)p_NodeTypeCode;
    v9->pFobx = v14;
    Context2 = (struct _MRX_SRV_OPEN_ *)v14->Context2;
    LODWORD(v9->RdbssDbgExtension) |= 0x200000u;
    *((_DWORD *)&v9->9 + 43) = 72;
    *((_WORD *)&v9->9 + 61) |= 1u;
    v9->pRelevantSrvOpen = Context2;
    LOBYTE(v9->RealDevice) = 13;
    *((_WORD *)&v9->9 + 60) = 6;
    *((_DWORD *)&v9->9 + 35) = 1311692;
    *((_BYTE *)&v9->9 + 176) = 0;
    *((_DWORD *)&v9->9 + 42) = 8;
    *((_QWORD *)&v9->9 + 19) = Pool2;
    v9->Create.TransportName.Buffer = Pool2;
    v9->InformationToReturn = 0;
    *((_QWORD *)&v9->9 + 16) = 0;
    StoredStatus = (*(__int64 (__fastcall **)(PRX_CONTEXT))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(p_NodeTypeCode[15] + 32LL)
                                                                                  + 48LL)
                                                                      + 352LL)
                                                          + 352LL))(v9);
    if ( StoredStatus == 259 )
    {
      RxWaitSync(v9);
      StoredStatus = v9->StoredStatus;
    }
    v9->CurrentIrp = 0;
    if ( StoredStatus >= 0 )
    {
      v16 = (unsigned int)(16 * (*((_DWORD *)Pool2 + 2) + 1));
      v17 = ExAllocatePool2(258, v16, 1934456914);
      v19 = v17;
      if ( v17 )
      {
        v20 = *((_DWORD *)Pool2 + 2);
        *(_DWORD *)v17 = v20;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqDi(
            WPP_GLOBAL_Control->AttachedDevice,
            v28,
            v18,
            v28,
            v28->Context2,
            p_NodeTypeCode,
            v20,
            *(_QWORD *)(v17 + 8));
        }
        v21 = 0;
        *(_QWORD *)(v19 + 8) = *((_QWORD *)Pool2 + 2);
        if ( *(_DWORD *)v19 )
        {
          v22 = v28;
          do
          {
            v23 = 2LL * (unsigned int)v21;
            *(_QWORD *)(v19 + 8 * v23 + 16) = *(_QWORD *)&Pool2[8 * (unsigned int)v21 + 12];
            *(_QWORD *)(v19 + 8 * v23 + 24) = *(_QWORD *)&Pool2[8 * v21 + 16];
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v24 = *(_QWORD *)&Pool2[8 * (unsigned int)v21 + 12];
              WPP_SF_qqqDiiii(
                WPP_GLOBAL_Control->AttachedDevice,
                v24 + *(_QWORD *)&Pool2[8 * v21 + 16],
                v24,
                v22,
                v22->Context2,
                p_NodeTypeCode,
                v21,
                *(_QWORD *)&Pool2[8 * v21 + 16],
                v24,
                v24 + *(_QWORD *)&Pool2[8 * v21 + 16],
                *(_QWORD *)Pool2);
            }
            v21 = (unsigned int)(v21 + 1);
          }
          while ( (unsigned int)v21 < *(_DWORD *)v19 );
          v9 = v27[0];
        }
        v25 = v28;
        p_NodeTypeCode[89] = v19;
        p_NodeTypeCode[90] = v25->Context2;
        p_NodeTypeCode[91] = *(_QWORD *)Pool2;
      }
      else
      {
        StoredStatus = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_ddq(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
            (unsigned int)v16);
        }
      }
      goto LABEL_49;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 35;
      v13 = (unsigned int)StoredStatus;
      goto LABEL_23;
    }
  }
  else
  {
    StoredStatus = -1073741670;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 34;
      v13 = 3221225626LL;
LABEL_23:
      WPP_SF_dq(v11->AttachedDevice, v12, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v13, p_NodeTypeCode);
    }
  }
LABEL_49:
  v7 = StoredStatus;
  ExFreePoolWithTag(Pool2, 0x734D7852u);
  if ( v9 )
    RxDereferenceAndDeleteRxContext_Real(v9);
LABEL_51:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      39,
      &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
      v7,
      p_NodeTypeCode);
  }
  return v7;
}

```

## disassembly

```asm
0x14004bed8  mov     rax, rsp
0x14004bedb  push    rbx
0x14004bedc  push    rbp
0x14004bedd  push    rsi
0x14004bede  push    rdi
0x14004bedf  push    r12
0x14004bee1  push    r13
0x14004bee3  push    r14
0x14004bee5  push    r15
0x14004bee7  sub     rsp, 78h
0x14004beeb  mov     edi, edx
0x14004beed  xor     r12d, r12d
0x14004bef0  mov     bl, r8b
0x14004bef3  mov     [rax-58h], r12
0x14004bef7  lea     r8, [rax+20h]
0x14004befb  mov     [rax+20h], r12
0x14004beff  lea     rdx, [rax-58h]
0x14004bf03  call    RxDecodeFileObject2
0x14004bf08  movzx   r9d, ax
0x14004bf0c  mov     eax, 0EC22h
0x14004bf11  cmp     r9w, ax
0x14004bf15  jz      short loc_14004BF71
0x14004bf17  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bf1e  lea     rdi, WPP_GLOBAL_Control
0x14004bf25  mov     rsi, [rsp+0B8h+var_58]
0x14004bf2a  cmp     rcx, rdi
0x14004bf2d  jz      short loc_14004BF67
0x14004bf2f  mov     eax, [rcx+2Ch]
0x14004bf32  lea     ebp, [r12+1]
0x14004bf37  test    bpl, al
0x14004bf3a  jz      short loc_14004BF67
0x14004bf3c  cmp     [rcx+29h], bpl
0x14004bf40  jb      short loc_14004BF67
0x14004bf42  mov     rcx, [rcx+18h]
0x14004bf46  lea     edx, [rbp+1Eh]
0x14004bf49  mov     dword ptr [rsp+0B8h+var_90], r9d
0x14004bf4e  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14004bf55  mov     r9, [rsp+0B8h+arg_18]
0x14004bf5d  mov     [rsp+0B8h+var_98], rsi
0x14004bf62  call    WPP_SF_qqD
0x14004bf67  mov     ebx, 0C000000Dh
0x14004bf6c  jmp     loc_14004C3A5
0x14004bf71  mov     rsi, [rsp+0B8h+var_58]
0x14004bf76  cmp     [rsi+2C8h], r12
0x14004bf7d  jz      short loc_14004BFD4
0x14004bf7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bf86  lea     rdi, WPP_GLOBAL_Control
0x14004bf8d  cmp     rcx, rdi
0x14004bf90  jz      short loc_14004BFCC
0x14004bf92  test    dword ptr [rcx+2Ch], 100h
0x14004bf99  jz      short loc_14004BFCC
0x14004bf9b  cmp     byte ptr [rcx+29h], 2
0x14004bf9f  jb      short loc_14004BFCC
0x14004bfa1  mov     r9, [rsp+0B8h+arg_18]
0x14004bfa9  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14004bfb0  mov     rcx, [rcx+18h]
0x14004bfb4  mov     edx, 20h ; ' '
0x14004bfb9  mov     [rsp+0B8h+var_90], rsi
0x14004bfbe  mov     rax, [r9+20h]
0x14004bfc2  mov     [rsp+0B8h+var_98], rax
0x14004bfc7  call    WPP_SF_qqq
0x14004bfcc  mov     ebx, r12d
0x14004bfcf  jmp     loc_14004C3A5
0x14004bfd4  mov     ebp, 48h ; 'H'
0x14004bfd9  mov     r8d, 734D7852h
0x14004bfdf  mov     edx, ebp
0x14004bfe1  mov     ecx, 100h
0x14004bfe6  call    cs:__imp_ExAllocatePool2
0x14004bfed  nop     dword ptr [rax+rax+00h]
0x14004bff2  mov     r15, rax
0x14004bff5  test    rax, rax
0x14004bff8  jnz     short loc_14004C043
0x14004bffa  mov     ebx, 0C000009Ah
0x14004bfff  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c006  lea     rdi, WPP_GLOBAL_Control
0x14004c00d  cmp     rcx, rdi
0x14004c010  jz      loc_14004C3A5
0x14004c016  test    dword ptr [rcx+2Ch], 100h
0x14004c01d  jz      loc_14004C3A5
0x14004c023  lea     ebp, [rax+1]
0x14004c026  cmp     [rcx+29h], bpl
0x14004c02a  jb      loc_14004C3A5
0x14004c030  mov     rcx, [rcx+18h]
0x14004c034  mov     [rsp+0B8h+var_90], rsi
0x14004c039  call    WPP_SF_iiqd
0x14004c03e  jmp     loc_14004C3A5
0x14004c043  mov     rax, [rsi+78h]
0x14004c047  mov     r8d, 2; InitialContextFlags
0x14004c04d  xor     ecx, ecx; Irp
0x14004c04f  mov     rdx, [rax+20h]
0x14004c053  mov     rdx, [rdx+30h]; RxDeviceObject
0x14004c057  call    RxCreateRxContext
0x14004c05c  mov     [rsp+0B8h+var_58], rax
0x14004c061  mov     r14, rax
0x14004c064  test    rax, rax
0x14004c067  jnz     short loc_14004C0C2
0x14004c069  mov     ebx, 0C000009Ah
0x14004c06e  mov     r12d, ebx
0x14004c071  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c078  lea     rdi, WPP_GLOBAL_Control
0x14004c07f  cmp     rcx, rdi
0x14004c082  jz      loc_14004C381
0x14004c088  test    dword ptr [rcx+2Ch], 100h
0x14004c08f  jz      loc_14004C381
0x14004c095  lea     ebp, [rax+1]
0x14004c098  cmp     [rcx+29h], bpl
0x14004c09c  jb      loc_14004C381
0x14004c0a2  lea     edx, [rax+22h]
0x14004c0a5  mov     r9d, ebx
0x14004c0a8  mov     rcx, [rcx+18h]
0x14004c0ac  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14004c0b3  mov     [rsp+0B8h+var_98], rsi
0x14004c0b8  call    WPP_SF_dq
0x14004c0bd  jmp     loc_14004C381
0x14004c0c2  mov     [r15], edi
0x14004c0c5  neg     bl
0x14004c0c7  sbb     eax, eax
0x14004c0c9  and     eax, 0F9000000h
0x14004c0ce  add     eax, 8000000h
0x14004c0d3  mov     [r15+4], eax
0x14004c0d7  mov     rax, [rsp+0B8h+arg_18]
0x14004c0df  mov     [r14+38h], rsi
0x14004c0e3  mov     [r14+40h], rax
0x14004c0e7  mov     rax, [rax+20h]
0x14004c0eb  bts     dword ptr [r14+78h], 15h
0x14004c0f1  mov     [r14+23Ch], ebp
0x14004c0f8  mov     ebp, 1
0x14004c0fd  or      [r14+20Ah], bp
0x14004c105  mov     [r14+48h], rax
0x14004c109  mov     byte ptr [r14+20h], 0Dh
0x14004c10e  mov     word ptr [r14+208h], 6
0x14004c118  mov     dword ptr [r14+21Ch], 1403CCh
0x14004c123  mov     [r14+240h], r12b
0x14004c12a  mov     dword ptr [r14+238h], 8
0x14004c135  mov     [r14+228h], r15
0x14004c13c  mov     [r14+230h], r15
0x14004c143  mov     [r14+0B8h], r12
0x14004c14a  mov     [r14+210h], r12
0x14004c151  mov     rax, [rsi+78h]
0x14004c155  mov     rcx, [rax+20h]
0x14004c159  mov     rax, [rcx+30h]
0x14004c15d  mov     rcx, [rax+160h]
0x14004c164  mov     rax, [rcx+160h]
0x14004c16b  mov     rcx, r14
0x14004c16e  call    _guard_dispatch_icall
0x14004c173  mov     r12d, eax
0x14004c176  cmp     eax, 103h
0x14004c17b  jnz     short loc_14004C18C
0x14004c17d  mov     rcx, r14
0x14004c180  call    RxWaitSync
0x14004c185  mov     r12d, [r14+0B0h]
0x14004c18c  mov     qword ptr [r14+28h], 0
0x14004c194  test    r12d, r12d
0x14004c197  jns     short loc_14004C1D4
0x14004c199  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c1a0  lea     rdi, WPP_GLOBAL_Control
0x14004c1a7  cmp     rcx, rdi
0x14004c1aa  jz      loc_14004C381
0x14004c1b0  test    dword ptr [rcx+2Ch], 100h
0x14004c1b7  jz      loc_14004C381
0x14004c1bd  cmp     [rcx+29h], bpl
0x14004c1c1  jb      loc_14004C381
0x14004c1c7  mov     edx, 23h ; '#'
0x14004c1cc  mov     r9d, r12d
0x14004c1cf  jmp     loc_14004C0A8
0x14004c1d4  mov     eax, [r15+8]
0x14004c1d8  mov     ecx, 102h
0x14004c1dd  add     eax, ebp
0x14004c1df  mov     r8d, 734D7852h
0x14004c1e5  shl     eax, 4
0x14004c1e8  mov     edx, eax
0x14004c1ea  mov     r13d, eax
0x14004c1ed  call    cs:__imp_ExAllocatePool2
0x14004c1f4  nop     dword ptr [rax+rax+00h]
0x14004c1f9  mov     rbx, rax
0x14004c1fc  test    rax, rax
0x14004c1ff  jnz     short loc_14004C25B
0x14004c201  mov     ebx, 0C000009Ah
0x14004c206  mov     r12d, ebx
0x14004c209  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c210  lea     rdi, WPP_GLOBAL_Control
0x14004c217  cmp     rcx, rdi
0x14004c21a  jz      loc_14004C381
0x14004c220  test    dword ptr [rcx+2Ch], 100h
0x14004c227  jz      loc_14004C381
0x14004c22d  cmp     [rcx+29h], bpl
0x14004c231  jb      loc_14004C381
0x14004c237  mov     rcx, [rcx+18h]
0x14004c23b  lea     edx, [rax+24h]
0x14004c23e  mov     [rsp+0B8h+var_90], rsi
0x14004c243  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14004c24a  mov     r9d, r13d
0x14004c24d  mov     dword ptr [rsp+0B8h+var_98], ebx
0x14004c251  call    WPP_SF_ddq
0x14004c256  jmp     loc_14004C381
0x14004c25b  mov     edx, [r15+8]
0x14004c25f  mov     [rax], edx
0x14004c261  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c268  lea     rdi, WPP_GLOBAL_Control
0x14004c26f  cmp     rcx, rdi
0x14004c272  jz      short loc_14004C2B2
0x14004c274  test    dword ptr [rcx+2Ch], 100h
0x14004c27b  jz      short loc_14004C2B2
0x14004c27d  cmp     byte ptr [rcx+29h], 2
0x14004c281  jb      short loc_14004C2B2
0x14004c283  mov     rax, [rax+8]
0x14004c287  mov     rcx, [rcx+18h]
0x14004c28b  mov     [rsp+0B8h+var_80], rax
0x14004c290  mov     [rsp+0B8h+var_88], edx
0x14004c294  mov     rdx, [rsp+0B8h+arg_18]
0x14004c29c  mov     [rsp+0B8h+var_90], rsi
0x14004c2a1  mov     r9, rdx
0x14004c2a4  mov     rax, [rdx+20h]
0x14004c2a8  mov     [rsp+0B8h+var_98], rax
0x14004c2ad  call    WPP_SF_qqqDi
0x14004c2b2  mov     rax, [r15+10h]
0x14004c2b6  xor     r13d, r13d
0x14004c2b9  mov     [rbx+8], rax
0x14004c2bd  cmp     [rbx], r13d
0x14004c2c0  jbe     loc_14004C35D
0x14004c2c6  mov     r14, [rsp+0B8h+arg_18]
0x14004c2ce  mov     r8d, r13d
0x14004c2d1  lea     r9, [r13+2]
0x14004c2d5  add     r8, r8
0x14004c2d8  add     r9, r9
0x14004c2db  mov     rax, [r15+r8*8+18h]
0x14004c2e0  mov     [rbx+r8*8+10h], rax
0x14004c2e5  mov     rax, [r15+r9*8]
0x14004c2e9  mov     [rbx+r8*8+18h], rax
0x14004c2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c2f5  cmp     rcx, rdi
0x14004c2f8  jz      short loc_14004C34C
0x14004c2fa  test    dword ptr [rcx+2Ch], 100h
0x14004c301  jz      short loc_14004C34C
0x14004c303  cmp     byte ptr [rcx+29h], 2
0x14004c307  jb      short loc_14004C34C
0x14004c309  mov     r9, [r15+r9*8]
0x14004c30d  mov     r8, [r15+r8*8+18h]
0x14004c312  mov     rax, [r15]
0x14004c315  mov     rcx, [rcx+18h]
0x14004c319  mov     [rsp+0B8h+var_68], rax
0x14004c31e  mov     rax, [r14+20h]
0x14004c322  lea     rdx, [r8+r9]
0x14004c326  mov     [rsp+0B8h+var_70], rdx
0x14004c32b  mov     [rsp+0B8h+var_78], r8
0x14004c330  mov     [rsp+0B8h+var_80], r9
0x14004c335  mov     r9, r14
0x14004c338  mov     [rsp+0B8h+var_88], r13d
0x14004c33d  mov     [rsp+0B8h+var_90], rsi
0x14004c342  mov     [rsp+0B8h+var_98], rax
0x14004c347  call    WPP_SF_qqqDiiii
0x14004c34c  add     r13d, ebp
0x14004c34f  cmp     r13d, [rbx]
0x14004c352  jb      loc_14004C2CE
0x14004c358  mov     r14, [rsp+0B8h+var_58]
0x14004c35d  mov     rax, [rsp+0B8h+arg_18]
0x14004c365  mov     [rsi+2C8h], rbx
0x14004c36c  mov     rax, [rax+20h]
0x14004c370  mov     [rsi+2D0h], rax
0x14004c377  mov     rax, [r15]
0x14004c37a  mov     [rsi+2D8h], rax
0x14004c381  mov     edx, 734D7852h; Tag
0x14004c386  mov     rcx, r15; P
0x14004c389  mov     ebx, r12d
0x14004c38c  call    cs:__imp_ExFreePoolWithTag
0x14004c393  nop     dword ptr [rax+rax+00h]
0x14004c398  test    r14, r14
0x14004c39b  jz      short loc_14004C3A5
0x14004c39d  mov     rcx, r14; RxContext
0x14004c3a0  call    RxDereferenceAndDeleteRxContext_Real
0x14004c3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c3ac  cmp     rcx, rdi
0x14004c3af  jz      short loc_14004C3DD
0x14004c3b1  test    dword ptr [rcx+2Ch], 100h
0x14004c3b8  jz      short loc_14004C3DD
0x14004c3ba  cmp     byte ptr [rcx+29h], 2
0x14004c3be  jb      short loc_14004C3DD
0x14004c3c0  mov     rcx, [rcx+18h]
0x14004c3c4  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14004c3cb  mov     edx, 27h ; '''
0x14004c3d0  mov     [rsp+0B8h+var_98], rsi
0x14004c3d5  mov     r9d, ebx
0x14004c3d8  call    WPP_SF_dq
0x14004c3dd  mov     eax, ebx
0x14004c3df  add     rsp, 78h
0x14004c3e3  pop     r15
0x14004c3e5  pop     r14
0x14004c3e7  pop     r13
0x14004c3e9  pop     r12
0x14004c3eb  pop     rdi
0x14004c3ec  pop     rsi
0x14004c3ed  pop     rbp
0x14004c3ee  pop     rbx
0x14004c3ef  retn
```
