# CscWriteFinalize

- ea: `0x140014888`
- end: `0x140014cb9`
- name: `CscWriteFinalize`
- size: `1073`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140017ac0`
- `0x14001ea30`

## callees

- `0x1400017c0`
- `0x1400053f8`
- `0x1400084f0`
- `0x140014888`
- `0x1400169d4`
- `0x1400190ec`
- `0x14001aba0`
- `0x14001ac1c`
- `0x14001eee0`
- `0x14001f2b8`
- `0x14004fe58`
- `0x140088580`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140014bd4`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140014bd4`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140014ac6`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140014ac6`
- `rdbss!RxLowIoGetBufferAddress` at `0x140014a65`
- `rdbss!RxLowIoGetBufferAddress` at `0x140014a65`

## pseudocode

```c
__int64 __fastcall CscWriteFinalize(PRX_CONTEXT RxContext, __int64 a2, char *a3, __int64 a4)
{
  unsigned int v4; // r15d
  PMRX_FCB pFcb; // r13
  int v6; // r14d
  ULONG PipeCompletionMode; // r12d
  char v11; // cl
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  char v15; // dl
  int Blink_high; // eax
  char v17; // bl
  int v18; // eax
  char v19; // r14
  char v20; // r12
  PMDL MdlAddress; // r14
  char v22; // bl
  char *BufferAddress; // rax
  __int64 v24; // r12
  unsigned int v25; // r14d
  NTSTATUS v26; // ebx
  __int64 v27; // rdx
  bool v28; // r14
  bool v29; // cf
  unsigned int v30; // ecx
  BOOLEAN IsResourceAcquiredExclusiveLite; // al
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // r10d
  int v36; // [rsp+20h] [rbp-50h]
  __int64 v37; // [rsp+30h] [rbp-40h]
  int Information; // [rsp+54h] [rbp-1Ch]
  unsigned int v39; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v40; // [rsp+5Ch] [rbp-14h]
  unsigned int v41; // [rsp+60h] [rbp-10h]
  PWSTR Buffer; // [rsp+68h] [rbp-8h]
  int v43; // [rsp+B0h] [rbp+40h] BYREF
  int v44; // [rsp+B4h] [rbp+44h]
  __int64 v45; // [rsp+B8h] [rbp+48h]
  bool v46; // [rsp+C8h] [rbp+58h] BYREF

  v45 = a2;
  v4 = a4;
  pFcb = RxContext->pFcb;
  v6 = 0;
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  Buffer = RxContext->Create.TransportName.Buffer;
  v40 = *((_DWORD *)&RxContext->9 + 42);
  v41 = 0;
  Information = 0;
  if ( (int)a4 >= 0 )
    goto LABEL_5;
  v11 = CscCheckRdrStatusTransitionIfNetErr((unsigned int)a4, a3, pFcb);
  if ( (*a3 & 0x10) == 0 )
  {
    v12 = 1882;
    goto LABEL_59;
  }
  if ( !v11 )
  {
LABEL_5:
    if ( (*a3 & 0x10) == 0 )
      Information = RxContext->IoStatusBlock.Information;
  }
  v13 = *(_QWORD *)(a2 + 16);
  if ( v13 && (*a3 & 0x10) == 0 )
    _InterlockedOr((volatile signed __int32 *)(v13 + 28), 0x8000u);
  v14 = *(_QWORD *)(a2 + 16);
  if ( v14 && *(_QWORD *)(v14 + 8) )
  {
    v15 = 1;
    if ( (*a3 & 0x10) != 0
      || (*a3 & 8) != 0
      && ((Blink_high = HIDWORD(pFcb->SrvOpenList.Blink), (Blink_high & 2) != 0) || (Blink_high & 1) != 0) )
    {
      v17 = 1;
      goto LABEL_19;
    }
  }
  else
  {
    v15 = 0;
  }
  v17 = 0;
LABEL_19:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v18 = HIDWORD(pFcb->SrvOpenList.Blink);
    if ( (v18 & 2) != 0 || (v19 = 78, (v18 & 1) != 0) )
      v19 = 89;
    LOBYTE(a4) = v15 != 0 ? 89 : 78;
    WPP_SF_ccccc(
      WPP_GLOBAL_Control->AttachedDevice,
      53,
      WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
      a4,
      (*a3 & 0x10) != 0 ? 89 : 78,
      (*a3 & 8) != 0 ? 89 : 78,
      v19,
      v17 != 0 ? 89 : 78);
  }
  if ( v17 )
  {
    v20 = PipeCompletionMode & 1;
    v39 = 0;
    v46 = 0;
    LOBYTE(v43) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_a14d127135023115663fdf7ff6985b18_Traceguids);
    if ( v20 )
      MdlAddress = RxContext->CurrentIrp->MdlAddress;
    else
      MdlAddress = 0;
    v22 = *a3;
    BufferAddress = (char *)RxLowIoGetBufferAddress(RxContext);
    v24 = v45;
    v37 = (__int64)MdlAddress;
    v25 = v40;
    v26 = CscEnWriteData(
            *(_QWORD *)(*(_QWORD *)(v45 + 16) + 8LL),
            (*a3 & 0x10) != 0,
            (v22 & 0x10) == 0,
            (__int64)Buffer,
            v40,
            BufferAddress,
            v37,
            &v39,
            &v46,
            (bool *)&v43);
    if ( KeAreAllApcsDisabled() )
      _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 2528), v39);
    if ( (*a3 & 0x10) != 0 && (v4 = v26, v26 >= 0) )
    {
      v41 = v25;
      v28 = v46;
      if ( v46 )
        CscNotifyReportChange(RxContext, 8, 3);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      {
        v25 = v40;
      }
      else
      {
        v29 = v28;
        v25 = v40;
        LOBYTE(v36) = v29 ? 89 : 78;
        WPP_SF_dc(WPP_GLOBAL_Control->AttachedDevice, v27, a3, v40, v36);
      }
      v30 = v39;
      RxContext->InformationToReturn = v39;
      RxContext->StoredStatus = v26;
    }
    else
    {
      v30 = v39;
    }
    if ( (_BYTE)v43 )
    {
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 24LL) |= 0x400u;
      v30 = v39;
    }
    if ( v26 < 0 || v30 != v25 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          56,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          (unsigned int)v26,
          v30);
      if ( (*a3 & 0x10) == 0 && v26 != -1073741802 )
      {
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(pFcb->Header.Resource);
        v32 = 0;
        if ( IsResourceAcquiredExclusiveLite )
        {
          LOBYTE(v32) = (*a3 & 0x10) != 0;
          CscHandleStoreError(RxContext, v32, (unsigned int)v26);
        }
        else
        {
          v33 = *(_QWORD *)(v24 + 8);
          v43 = 0;
          v44 = 32;
          v34 = CscStoreSetInformationEntry(*(_QWORD *)(v33 + 56), (__int64)&v43, 0, 0, 0, 0, 0);
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return v4;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              57,
              WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
              pFcb,
              v34);
        }
      }
    }
  }
  v12 = 0;
  v6 = Information;
LABEL_59:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DdDD(WPP_GLOBAL_Control->AttachedDevice, v41, a3, v4, v12, v6, v41);
  return v4;
}

```

## disassembly

```asm
0x140014888  mov     [rsp-38h+arg_10], rbx
0x14001488d  mov     [rsp-38h+arg_8], rdx
0x140014892  push    rbp
0x140014893  push    rsi
0x140014894  push    rdi
0x140014895  push    r12
0x140014897  push    r13
0x140014899  push    r14
0x14001489b  push    r15
0x14001489d  mov     rbp, rsp
0x1400148a0  sub     rsp, 70h
0x1400148a4  mov     rax, [rcx+230h]
0x1400148ab  mov     r15d, r9d
0x1400148ae  mov     r13, [rcx+38h]
0x1400148b2  xor     r14d, r14d
0x1400148b5  mov     r12d, [rcx+218h]
0x1400148bc  mov     rsi, r8
0x1400148bf  mov     [rbp+var_8], rax
0x1400148c3  mov     rbx, rdx
0x1400148c6  mov     eax, [rcx+238h]
0x1400148cc  mov     rdi, rcx
0x1400148cf  mov     [rbp+var_14], eax
0x1400148d2  mov     r9b, 10h
0x1400148d5  mov     [rbp+var_10], 0
0x1400148dc  mov     [rbp+var_1C], r14d
0x1400148e0  test    r15d, r15d
0x1400148e3  jns     short loc_140014912
0x1400148e5  mov     r8, r13
0x1400148e8  mov     rdx, rsi
0x1400148eb  mov     ecx, r15d
0x1400148ee  call    CscCheckRdrStatusTransitionIfNetErr
0x1400148f3  mov     r9b, 10h
0x1400148f6  mov     cl, al
0x1400148f8  test    [rsi], r9b
0x1400148fb  jnz     short loc_140014907
0x1400148fd  mov     eax, 75Ah
0x140014902  jmp     loc_140014C66
0x140014907  xor     eax, eax
0x140014909  mov     [rbp+var_20], eax
0x14001490c  test    cl, cl
0x14001490e  jz      short loc_140014917
0x140014910  jmp     short loc_140014925
0x140014912  xor     eax, eax
0x140014914  mov     [rbp+var_20], eax
0x140014917  test    [rsi], r9b
0x14001491a  jnz     short loc_140014925
0x14001491c  mov     eax, [rdi+0B8h]
0x140014922  mov     [rbp+var_1C], eax
0x140014925  mov     rcx, [rbx+10h]
0x140014929  test    rcx, rcx
0x14001492c  jz      short loc_14001493B
0x14001492e  test    [rsi], r9b
0x140014931  jnz     short loc_14001493B
0x140014933  lock or dword ptr [rcx+1Ch], 8000h
0x14001493b  mov     rax, [rbx+10h]
0x14001493f  test    rax, rax
0x140014942  jz      short loc_14001496A
0x140014944  cmp     [rax+8], r14
0x140014948  jz      short loc_14001496A
0x14001494a  mov     al, [rsi]
0x14001494c  mov     dl, 1
0x14001494e  test    r9b, al
0x140014951  jnz     short loc_140014966
0x140014953  test    al, 8
0x140014955  jz      short loc_14001496C
0x140014957  mov     eax, [r13+0A4h]
0x14001495e  test    al, 2
0x140014960  jnz     short loc_140014966
0x140014962  test    dl, al
0x140014964  jz      short loc_14001496C
0x140014966  mov     bl, dl
0x140014968  jmp     short loc_14001496E
0x14001496a  xor     dl, dl
0x14001496c  xor     bl, bl
0x14001496e  mov     r11, cs:WPP_GLOBAL_Control
0x140014975  lea     rax, WPP_GLOBAL_Control
0x14001497c  cmp     r11, rax
0x14001497f  jz      loc_140014A0B
0x140014985  mov     eax, [r11+2Ch]
0x140014989  test    al, 20h
0x14001498b  jz      short loc_140014A04
0x14001498d  mov     eax, [r13+0A4h]
0x140014994  test    al, 2
0x140014996  jnz     short loc_14001499F
0x140014998  mov     r14b, 4Eh ; 'N'
0x14001499b  test    al, 1
0x14001499d  jz      short loc_1400149A2
0x14001499f  mov     r14b, 59h ; 'Y'
0x1400149a2  mov     cl, [rsi]
0x1400149a4  mov     al, bl
0x1400149a6  neg     al
0x1400149a8  mov     al, cl
0x1400149aa  sbb     r10b, r10b
0x1400149ad  and     al, 8
0x1400149af  and     r10b, 0Bh
0x1400149b3  add     r10b, 4Eh ; 'N'
0x1400149b7  neg     al
0x1400149b9  mov     byte ptr [rsp+70h+var_38], r10b
0x1400149be  mov     byte ptr [rsp+70h+var_40], r14b
0x1400149c3  sbb     r8b, r8b
0x1400149c6  and     cl, r9b
0x1400149c9  and     r8b, 0Bh
0x1400149cd  add     r8b, 4Eh ; 'N'
0x1400149d1  neg     cl
0x1400149d3  mov     byte ptr [rsp+70h+var_48], r8b
0x1400149d8  mov     rcx, [r11+18h]
0x1400149dc  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x1400149e3  sbb     al, al
0x1400149e5  and     al, 0Bh
0x1400149e7  add     al, 4Eh ; 'N'
0x1400149e9  neg     dl
0x1400149eb  mov     byte ptr [rsp+70h+var_50], al
0x1400149ef  mov     edx, 35h ; '5'
0x1400149f4  sbb     r9b, r9b
0x1400149f7  and     r9b, 0Bh
0x1400149fb  add     r9b, 4Eh ; 'N'
0x1400149ff  call    WPP_SF_ccccc
0x140014a04  lea     rax, WPP_GLOBAL_Control
0x140014a0b  test    bl, bl
0x140014a0d  jz      loc_140014C5F
0x140014a13  and     r12b, 1
0x140014a17  mov     [rbp+var_18], 0
0x140014a1e  mov     [rbp+arg_18], 0
0x140014a22  mov     byte ptr [rbp+arg_0], 0
0x140014a26  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a2d  cmp     rcx, rax
0x140014a30  jz      short loc_140014A4E
0x140014a32  mov     eax, [rcx+2Ch]
0x140014a35  test    al, 40h
0x140014a37  jz      short loc_140014A4E
0x140014a39  mov     rcx, [rcx+18h]
0x140014a3d  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140014a44  mov     edx, 36h ; '6'
0x140014a49  call    WPP_SF_
0x140014a4e  test    r12b, r12b
0x140014a51  jz      short loc_140014A5D
0x140014a53  mov     rax, [rdi+28h]
0x140014a57  mov     r14, [rax+8]
0x140014a5b  jmp     short loc_140014A60
0x140014a5d  xor     r14d, r14d
0x140014a60  mov     bl, [rsi]
0x140014a62  mov     rcx, rdi; RxContext
0x140014a65  call    cs:__imp_RxLowIoGetBufferAddress
0x140014a6c  nop     dword ptr [rax+rax+00h]
0x140014a71  mov     dl, [rsi]
0x140014a73  lea     r9, [rbp+arg_0]
0x140014a77  mov     r12, [rbp+arg_8]
0x140014a7b  test    bl, 10h
0x140014a7e  mov     [rsp+70h+var_28], r9
0x140014a83  lea     r9, [rbp+arg_18]
0x140014a87  mov     [rsp+70h+var_30], r9
0x140014a8c  setz    r8b
0x140014a90  lea     r9, [rbp+var_18]
0x140014a94  shr     dl, 4
0x140014a97  mov     rcx, [r12+10h]
0x140014a9c  and     dl, 1
0x140014a9f  mov     [rsp+70h+var_38], r9
0x140014aa4  mov     r9, [rbp+var_8]
0x140014aa8  mov     [rsp+70h+var_40], r14
0x140014aad  mov     r14d, [rbp+var_14]
0x140014ab1  mov     rcx, [rcx+8]
0x140014ab5  mov     [rsp+70h+var_48], rax
0x140014aba  mov     dword ptr [rsp+70h+var_50], r14d
0x140014abf  call    CscEnWriteData
0x140014ac4  mov     ebx, eax
0x140014ac6  call    cs:__imp_KeAreAllApcsDisabled
0x140014acd  nop     dword ptr [rax+rax+00h]
0x140014ad2  test    al, al
0x140014ad4  jz      short loc_140014AE8
0x140014ad6  mov     ecx, [rbp+var_18]
0x140014ad9  mov     rax, cs:CscDevExtn
0x140014ae0  lock add [rax+9E0h], rcx
0x140014ae8  test    byte ptr [rsi], 10h
0x140014aeb  jz      short loc_140014B61
0x140014aed  mov     r15d, ebx
0x140014af0  test    ebx, ebx
0x140014af2  js      short loc_140014B61
0x140014af4  mov     [rbp+var_10], r14d
0x140014af8  mov     r14b, [rbp+arg_18]
0x140014afc  test    r14b, r14b
0x140014aff  jz      short loc_140014B12
0x140014b01  mov     edx, 8
0x140014b06  mov     rcx, rdi
0x140014b09  lea     r8d, [rdx-5]
0x140014b0d  call    CscNotifyReportChange
0x140014b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b19  lea     rax, WPP_GLOBAL_Control
0x140014b20  cmp     rcx, rax
0x140014b23  jz      short loc_140014B4B
0x140014b25  mov     eax, [rcx+2Ch]
0x140014b28  test    al, 40h
0x140014b2a  jz      short loc_140014B4B
0x140014b2c  mov     rcx, [rcx+18h]
0x140014b30  neg     r14b
0x140014b33  mov     r14d, [rbp+var_14]
0x140014b37  mov     r9d, r14d
0x140014b3a  sbb     al, al
0x140014b3c  and     al, 0Bh
0x140014b3e  add     al, 4Eh ; 'N'
0x140014b40  mov     byte ptr [rsp+70h+var_50], al
0x140014b44  call    WPP_SF_dc
0x140014b49  jmp     short loc_140014B4F
0x140014b4b  mov     r14d, [rbp+var_14]
0x140014b4f  mov     ecx, [rbp+var_18]
0x140014b52  mov     [rdi+0B8h], rcx
0x140014b59  mov     [rdi+0B0h], ebx
0x140014b5f  jmp     short loc_140014B64
0x140014b61  mov     ecx, [rbp+var_18]
0x140014b64  cmp     byte ptr [rbp+arg_0], 0
0x140014b68  jz      short loc_140014B77
0x140014b6a  mov     rax, [r12+10h]
0x140014b6f  bts     dword ptr [rax+18h], 0Ah
0x140014b74  mov     ecx, [rbp+var_18]
0x140014b77  test    ebx, ebx
0x140014b79  js      short loc_140014B84
0x140014b7b  cmp     ecx, r14d
0x140014b7e  jz      loc_140014C5F
0x140014b84  mov     r10, cs:WPP_GLOBAL_Control
0x140014b8b  lea     r14, WPP_GLOBAL_Control
0x140014b92  cmp     r10, r14
0x140014b95  jz      short loc_140014BBB
0x140014b97  mov     eax, [r10+2Ch]
0x140014b9b  test    al, 20h
0x140014b9d  jz      short loc_140014BBB
0x140014b9f  mov     dword ptr [rsp+70h+var_50], ecx
0x140014ba3  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140014baa  mov     rcx, [r10+18h]
0x140014bae  mov     edx, 38h ; '8'
0x140014bb3  mov     r9d, ebx
0x140014bb6  call    WPP_SF_Dd
0x140014bbb  test    byte ptr [rsi], 10h
0x140014bbe  jnz     loc_140014C5F
0x140014bc4  cmp     ebx, 0C0000016h
0x140014bca  jz      loc_140014C5F
0x140014bd0  mov     rcx, [r13+8]; Resource
0x140014bd4  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140014bdb  nop     dword ptr [rax+rax+00h]
0x140014be0  xor     edx, edx
0x140014be2  test    al, al
0x140014be4  jz      short loc_140014BFB
0x140014be6  mov     dl, [rsi]
0x140014be8  mov     r8d, ebx
0x140014beb  shr     dl, 4
0x140014bee  mov     rcx, rdi
0x140014bf1  and     dl, 1
0x140014bf4  call    CscHandleStoreError
0x140014bf9  jmp     short loc_140014C5F
0x140014bfb  mov     rcx, [r12+8]
0x140014c00  xor     r9d, r9d
0x140014c03  mov     [rsp+70h+var_40], rdx
0x140014c08  xor     r8d, r8d
0x140014c0b  mov     [rsp+70h+var_48], rdx
0x140014c10  mov     [rbp+arg_0], edx
0x140014c13  mov     [rbp+arg_4], 20h ; ' '
0x140014c1a  mov     rcx, [rcx+38h]
0x140014c1e  mov     [rsp+70h+var_50], rdx
0x140014c23  lea     rdx, [rbp+arg_0]
0x140014c27  call    CscStoreSetInformationEntry
0x140014c2c  mov     r10d, eax
0x140014c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c36  cmp     rcx, r14
0x140014c39  jz      short loc_140014C9D
0x140014c3b  mov     eax, [rcx+2Ch]
0x140014c3e  test    al, 20h
0x140014c40  jz      short loc_140014C5F
0x140014c42  mov     rcx, [rcx+18h]
0x140014c46  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140014c4d  mov     edx, 39h ; '9'
0x140014c52  mov     dword ptr [rsp+70h+var_50], r10d
0x140014c57  mov     r9, r13
0x140014c5a  call    WPP_SF_qD
0x140014c5f  mov     eax, [rbp+var_20]
0x140014c62  mov     r14d, [rbp+var_1C]
0x140014c66  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c6d  lea     rdx, WPP_GLOBAL_Control
0x140014c74  cmp     rcx, rdx
0x140014c77  jz      short loc_140014C9D
0x140014c79  mov     edx, [rcx+2Ch]
0x140014c7c  test    dl, 20h
0x140014c7f  jz      short loc_140014C9D
0x140014c81  mov     edx, [rbp+var_10]
0x140014c84  mov     r9d, r15d
0x140014c87  mov     rcx, [rcx+18h]
0x140014c8b  mov     dword ptr [rsp+70h+var_40], edx
0x140014c8f  mov     dword ptr [rsp+70h+var_48], r14d
0x140014c94  mov     dword ptr [rsp+70h+var_50], eax
0x140014c98  call    WPP_SF_DdDD
0x140014c9d  mov     rbx, [rsp+70h+arg_10]
0x140014ca5  mov     eax, r15d
0x140014ca8  add     rsp, 70h
0x140014cac  pop     r15
0x140014cae  pop     r14
0x140014cb0  pop     r13
0x140014cb2  pop     r12
0x140014cb4  pop     rdi
0x140014cb5  pop     rsi
0x140014cb6  pop     rbp
0x140014cb7  retn
```
