# CscReadFinalize

- ea: `0x1400043b4`
- end: `0x140004924`
- name: `CscReadFinalize`
- size: `1392`
- prototype: `__int64 __usercall@<rax>(PRX_CONTEXT RxContext@<rcx>, void *Src, PMDL Mdl, char)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002680`
- `0x14001e178`

## callees

- `0x140001008`
- `0x1400043b4`
- `0x1400053f8`
- `0x14000a4f0`
- `0x1400169d4`
- `0x140018930`
- `0x140018b50`
- `0x140019140`
- `0x14001a494`
- `0x14001efb4`
- `0x14002f140`
- `0x140076afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400048ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400048ed`
- `ntoskrnl!IoFreeMdl` at `0x140004895`
- `ntoskrnl!IoFreeMdl` at `0x140004895`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400047ae`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400047ae`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400045c6`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400048c3`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400045c6`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400048c3`
- `rdbss!RxAcquirePowerContextLock` at `0x140004815`
- `rdbss!RxAcquirePowerContextLock` at `0x140004815`
- `rdbss!RxUpdateFcbPowerState` at `0x14000483b`
- `rdbss!RxUpdateFcbPowerState` at `0x14000483b`
- `rdbss!RxReleasePowerContextLock` at `0x140004847`
- `rdbss!RxReleasePowerContextLock` at `0x140004847`

## pseudocode

```c
void __fastcall CscReadFinalize(
        PRX_CONTEXT RxContext,
        _QWORD *a2,
        _BYTE *a3,
        struct _MDL *a4,
        void *Src,
        PMDL Mdl,
        char a7)
{
  NTSTATUS StoredStatus; // r13d
  PMRX_FCB pFcb; // rbp
  __int64 v11; // rax
  unsigned __int64 Information_low; // r15
  char v13; // bl
  int v14; // ebp
  void *v15; // rbx
  int v16; // esi
  PVOID BufferAddress; // rax
  int v18; // r14d
  int v19; // r8d
  int v20; // edx
  int v21; // eax
  __int64 v22; // rdx
  int Blink_high; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  char v26; // al
  struct _MDL *v27; // rcx
  PVOID v28; // rax
  bool v29; // [rsp+50h] [rbp-68h]
  ULONG PipeCompletionMode; // [rsp+58h] [rbp-60h]
  char v31; // [rsp+58h] [rbp-60h]
  PMDL MdlAddress; // [rsp+58h] [rbp-60h]
  unsigned int v33; // [rsp+60h] [rbp-58h] BYREF
  NTSTATUS v34; // [rsp+64h] [rbp-54h]
  int v35; // [rsp+68h] [rbp-50h]
  PWSTR Buffer; // [rsp+70h] [rbp-48h]
  char v37; // [rsp+C0h] [rbp+8h] BYREF
  _QWORD *v38; // [rsp+C8h] [rbp+10h]
  struct _MDL *v39; // [rsp+D8h] [rbp+20h]

  v39 = a4;
  v38 = a2;
  v33 = 0;
  v37 = 0;
  StoredStatus = RxContext->StoredStatus;
  v29 = RxContext->NonPagedFcb != (PNON_PAGED_FCB)CscDeviceObject;
  pFcb = RxContext->pFcb;
  v35 = *((_DWORD *)&RxContext->9 + 42);
  Buffer = RxContext->Create.TransportName.Buffer;
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  v11 = *a2;
  v34 = StoredStatus;
  if ( v11 && _bittest((const signed __int32 *)(v11 + 4), 9u) )
    _InterlockedAnd((volatile signed __int32 *)(a2[1] + 96LL), 0xFFFFFFEF);
  if ( StoredStatus < 0 )
  {
    LODWORD(Information_low) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_61114c5048fe38b79d273cf1da5b551c_Traceguids,
        (unsigned int)StoredStatus);
    if ( (unsigned __int8)CscTransitnOKToGoOffline((unsigned int)StoredStatus) )
    {
      if ( (*a3 & 0x20) == 0 || (a3[1] & 2) != 0 || (unsigned __int8)CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount) )
      {
        a3[1] |= 0x40u;
      }
      else
      {
        *a3 |= 0x13u;
        LOBYTE(v22) = 1;
        CscTransitionFcbOffline(pFcb, v22, 2, 2);
        _InterlockedAnd8((volatile signed __int8 *)&pFcb[1].Header.FileContextSupportPointer, 0xFDu);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_cc(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_61114c5048fe38b79d273cf1da5b551c_Traceguids);
    v14 = 394;
  }
  else
  {
    Information_low = LODWORD(RxContext->IoStatusBlock.Information);
    if ( *a2 && _bittest((const signed __int32 *)(*a2 + 4LL), 9u) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          (unsigned int)Information_low);
      _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 1440), Information_low);
    }
    v13 = a7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_ccDDD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_a14d127135023115663fdf7ff6985b18_Traceguids);
    if ( !v13 )
      goto LABEL_8;
    v31 = PipeCompletionMode & 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_a14d127135023115663fdf7ff6985b18_Traceguids);
    if ( v31 )
      MdlAddress = RxContext->CurrentIrp->MdlAddress;
    else
      MdlAddress = 0;
    BufferAddress = RxLowIoGetBufferAddress(RxContext);
    v18 = (int)v38;
    v19 = (int)MdlAddress;
    LOBYTE(v19) = 1;
    LOBYTE(v20) = (*a3 & 0x10) != 0;
    v21 = CscEnWriteData(
            *(_QWORD *)(v38[2] + 8LL),
            v20,
            v19,
            (_DWORD)Buffer,
            Information_low,
            (__int64)BufferAddress,
            (__int64)MdlAddress,
            (__int64)&v33,
            0,
            (__int64)&v37);
    if ( v21 >= 0 && v33 == (_DWORD)Information_low )
    {
      if ( KeAreAllApcsDisabled() )
        _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 2528), v33);
      if ( !v37 )
        goto LABEL_8;
      if ( v29 && (*a3 & 0x18) == 8 )
      {
        Blink_high = HIDWORD(pFcb->SrvOpenList.Blink);
        if ( (Blink_high & 2) != 0 || (Blink_high & 1) != 0 )
          CscPrefetchAttempt((_DWORD)RxContext, v18, (_DWORD)Buffer, v35, 1);
      }
      RxAcquirePowerContextLock();
      v26 = BYTE2(pFcb[1].Context2);
      if ( (v26 & 2) != 0 )
      {
        LOBYTE(v24) = 2;
      }
      else
      {
        LOBYTE(v24) = 4;
        if ( (v26 & 4) == 0 )
        {
LABEL_57:
          RxReleasePowerContextLock();
LABEL_8:
          v14 = 0;
          goto LABEL_9;
        }
      }
      LOBYTE(v25) = 1;
      RxUpdateFcbPowerState(pFcb, v24, v25);
      goto LABEL_57;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_DDd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
        (unsigned int)v21,
        v33,
        Information_low);
    v14 = 0;
    if ( (a3[1] & 2) != 0 )
      _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 1480), Information_low);
  }
LABEL_9:
  v15 = Src;
  if ( Src )
  {
    if ( Mdl )
    {
      IoFreeMdl(Mdl);
      v27 = v39;
      v16 = v34;
      RxContext->CurrentIrp->MdlAddress = v39;
      *((_QWORD *)&RxContext->9 + 18) = v27;
      if ( v16 >= 0 )
      {
        v28 = RxLowIoGetBufferAddress(RxContext);
        if ( v28 )
          memmove(v28, v15, (unsigned int)Information_low);
      }
    }
    else
    {
      v16 = v34;
    }
    ExFreePoolWithTag(v15, 0);
  }
  else
  {
    v16 = v34;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
      (unsigned int)v16,
      v14,
      Information_low);
}

```

## disassembly

```asm
0x1400043b4  mov     r11, rsp
0x1400043b7  mov     [r11+18h], rbx
0x1400043bb  mov     [r11+20h], r9
0x1400043bf  mov     [r11+10h], rdx
0x1400043c3  push    rbp
0x1400043c4  push    rsi
0x1400043c5  push    rdi
0x1400043c6  push    r12
0x1400043c8  push    r13
0x1400043ca  push    r14
0x1400043cc  push    r15
0x1400043ce  sub     rsp, 80h
0x1400043d5  mov     rax, cs:CscDeviceObject
0x1400043dc  mov     rdi, rcx
0x1400043df  xor     ecx, ecx
0x1400043e1  mov     rsi, r8
0x1400043e4  mov     [rsp+0B8h+var_58], ecx
0x1400043e8  mov     [r11+8], cl
0x1400043ec  cmp     [rdi+50h], rax
0x1400043f0  mov     eax, [rdi+238h]
0x1400043f6  mov     r13d, [rdi+0B0h]
0x1400043fd  setnz   [rsp+0B8h+var_68]
0x140004402  mov     rbp, [rdi+38h]
0x140004406  mov     [rsp+0B8h+var_50], eax
0x14000440a  mov     rax, [rdi+230h]
0x140004411  mov     [rsp+0B8h+var_48], rax
0x140004416  mov     eax, [rdi+218h]
0x14000441c  mov     dword ptr [rsp+0B8h+var_60], eax
0x140004420  mov     rax, [rdx]
0x140004423  mov     [rsp+0B8h+var_54], r13d
0x140004428  test    rax, rax
0x14000442b  jnz     loc_14000452E
0x140004431  test    r13d, r13d
0x140004434  js      loc_1400044D2
0x14000443a  mov     rax, [rdx]
0x14000443d  lea     r12, WPP_GLOBAL_Control
0x140004444  mov     r15d, [rdi+0B8h]
0x14000444b  mov     r13b, 20h ; ' '
0x14000444e  mov     [rsp+0B8h+var_64], ecx
0x140004452  test    rax, rax
0x140004455  jnz     loc_140004547
0x14000445b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004462  mov     r14b, 40h ; '@'
0x140004465  mov     bl, [rsp+0B8h+arg_30]
0x14000446c  cmp     rcx, r12
0x14000446f  jz      short loc_14000447D
0x140004471  mov     eax, [rcx+2Ch]
0x140004474  test    r14b, al
0x140004477  jnz     loc_140004722
0x14000447d  test    bl, bl
0x14000447f  jnz     loc_140004595
0x140004485  mov     ebp, [rsp+0B8h+var_64]
0x140004489  mov     rbx, [rsp+0B8h+Src]
0x140004491  test    rbx, rbx
0x140004494  jnz     loc_140004888
0x14000449a  mov     esi, [rsp+0B8h+var_54]
0x14000449e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044a5  cmp     rcx, r12
0x1400044a8  jz      short loc_1400044B6
0x1400044aa  mov     eax, [rcx+2Ch]
0x1400044ad  test    r13b, al
0x1400044b0  jnz     loc_1400048FE
0x1400044b6  mov     rbx, [rsp+0B8h+arg_10]
0x1400044be  add     rsp, 80h
0x1400044c5  pop     r15
0x1400044c7  pop     r14
0x1400044c9  pop     r13
0x1400044cb  pop     r12
0x1400044cd  pop     rdi
0x1400044ce  pop     rsi
0x1400044cf  pop     rbp
0x1400044d0  retn
0x1400044d2  mov     r15d, ecx
0x1400044d5  mov     bl, cl
0x1400044d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044de  lea     r12, WPP_GLOBAL_Control
0x1400044e5  mov     r14b, 40h ; '@'
0x1400044e8  cmp     rcx, r12
0x1400044eb  jz      short loc_1400044F9
0x1400044ed  mov     eax, [rcx+2Ch]
0x1400044f0  test    r14b, al
0x1400044f3  jnz     loc_14000467D
0x1400044f9  mov     ecx, r13d
0x1400044fc  call    CscTransitnOKToGoOffline
0x140004501  mov     r13b, 20h ; ' '
0x140004504  test    al, al
0x140004506  jnz     loc_14000469A
0x14000450c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004513  cmp     rcx, r12
0x140004516  jz      short loc_140004524
0x140004518  mov     eax, [rcx+2Ch]
0x14000451b  test    r13b, al
0x14000451e  jnz     loc_1400046E3
0x140004524  mov     ebp, 18Ah
0x140004529  jmp     loc_140004489
0x14000452e  bt      dword ptr [rax+4], 9
0x140004533  jnb     loc_140004431
0x140004539  mov     rax, [rdx+8]
0x14000453d  lock and dword ptr [rax+60h], 0FFFFFFEFh
0x140004542  jmp     loc_140004431
0x140004547  bt      dword ptr [rax+4], 9
0x14000454c  jnb     loc_14000445B
0x140004552  mov     rcx, cs:WPP_GLOBAL_Control
0x140004559  cmp     rcx, r12
0x14000455c  jz      short loc_14000457E
0x14000455e  mov     eax, [rcx+2Ch]
0x140004561  test    r13b, al
0x140004564  jz      short loc_14000457E
0x140004566  mov     rcx, [rcx+18h]
0x14000456a  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140004571  mov     edx, 0Ch
0x140004576  mov     r9d, r15d
0x140004579  call    WPP_SF_d
0x14000457e  mov     rax, cs:CscDevExtn
0x140004585  mov     rcx, r15
0x140004588  lock add [rax+5A0h], rcx
0x140004590  jmp     loc_14000445B
0x140004595  mov     bl, 1
0x140004597  and     byte ptr [rsp+0B8h+var_60], bl
0x14000459b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045a2  cmp     rcx, r12
0x1400045a5  jnz     loc_14000477F
0x1400045ab  cmp     byte ptr [rsp+0B8h+var_60], 0
0x1400045b0  jz      loc_14000466F
0x1400045b6  mov     rax, [rdi+28h]
0x1400045ba  mov     rax, [rax+8]
0x1400045be  mov     [rsp+0B8h+var_60], rax
0x1400045c3  mov     rcx, rdi; RxContext
0x1400045c6  call    cs:__imp_RxLowIoGetBufferAddress
0x1400045cd  nop     dword ptr [rax+rax+00h]
0x1400045d2  mov     dl, [rsi]
0x1400045d4  lea     r8, [rsp+0B8h+arg_0]
0x1400045dc  mov     r14, [rsp+0B8h+arg_8]
0x1400045e4  mov     r9, [rsp+0B8h+var_48]
0x1400045e9  mov     [rsp+0B8h+var_70], r8
0x1400045ee  lea     r8, [rsp+0B8h+var_58]
0x1400045f3  mov     [rsp+0B8h+var_78], 0
0x1400045fc  mov     rcx, [r14+10h]
0x140004600  mov     [rsp+0B8h+var_80], r8
0x140004605  mov     r8, [rsp+0B8h+var_60]
0x14000460a  mov     [rsp+0B8h+var_88], r8
0x14000460f  mov     r8b, bl
0x140004612  mov     rcx, [rcx+8]
0x140004616  shr     dl, 4
0x140004619  mov     [rsp+0B8h+var_90], rax
0x14000461e  and     dl, bl
0x140004620  mov     [rsp+0B8h+var_98], r15d
0x140004625  call    CscEnWriteData
0x14000462a  mov     r8d, [rsp+0B8h+var_58]
0x14000462f  mov     r9d, eax
0x140004632  test    eax, eax
0x140004634  jns     loc_1400047A5
0x14000463a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004641  cmp     rcx, r12
0x140004644  jnz     loc_140004858
0x14000464a  test    byte ptr [rsi+1], 2
0x14000464e  mov     ebp, [rsp+0B8h+var_64]
0x140004652  jz      loc_140004489
0x140004658  mov     rax, cs:CscDevExtn
0x14000465f  mov     rcx, r15
0x140004662  lock add [rax+5C8h], rcx
0x14000466a  jmp     loc_140004489
0x14000466f  mov     [rsp+0B8h+var_60], 0
0x140004678  jmp     loc_1400045C3
0x14000467d  mov     rcx, [rcx+18h]
0x140004681  lea     r8, WPP_61114c5048fe38b79d273cf1da5b551c_Traceguids
0x140004688  mov     edx, 16h
0x14000468d  mov     r9d, r13d
0x140004690  call    WPP_SF_d
0x140004695  jmp     loc_1400044F9
0x14000469a  mov     bl, 1
0x14000469c  test    [rsi], r13b
0x14000469f  jz      short loc_1400046DA
0x1400046a1  test    byte ptr [rsi+1], 2
0x1400046a5  jnz     short loc_1400046DA
0x1400046a7  mov     rcx, [rbp+80h]
0x1400046ae  call    CscLViewIsRootGhosted
0x1400046b3  test    al, al
0x1400046b5  jnz     short loc_1400046DA
0x1400046b7  or      byte ptr [rsi], 13h
0x1400046ba  mov     r9d, 2
0x1400046c0  mov     r8d, r9d
0x1400046c3  mov     dl, bl
0x1400046c5  mov     rcx, rbp
0x1400046c8  call    CscTransitionFcbOffline
0x1400046cd  lock and byte ptr [rbp+100h], 0FDh
0x1400046d5  jmp     loc_14000450C
0x1400046da  or      [rsi+1], r14b
0x1400046de  jmp     loc_14000450C
0x1400046e3  mov     al, [rsi+1]
0x1400046e6  lea     r8, WPP_61114c5048fe38b79d273cf1da5b551c_Traceguids
0x1400046ed  mov     rcx, [rcx+18h]
0x1400046f1  and     al, r14b
0x1400046f4  neg     al
0x1400046f6  mov     edx, 17h
0x1400046fb  sbb     r10b, r10b
0x1400046fe  and     r10b, 0Bh
0x140004702  add     r10b, 4Eh ; 'N'
0x140004706  neg     bl
0x140004708  mov     byte ptr [rsp+0B8h+var_98], r10b
0x14000470d  sbb     r9b, r9b
0x140004710  and     r9b, 0Bh
0x140004714  add     r9b, 4Eh ; 'N'
0x140004718  call    WPP_SF_cc
0x14000471d  jmp     loc_140004524
0x140004722  mov     al, [rsi]
0x140004724  mov     edx, 0Dh
0x140004729  mov     rcx, [rcx+18h]
0x14000472d  and     al, 8
0x14000472f  neg     al
0x140004731  mov     al, bl
0x140004733  sbb     r8b, r8b
0x140004736  and     r8b, 0Bh
0x14000473a  add     r8b, 4Eh ; 'N'
0x14000473e  neg     al
0x140004740  mov     eax, [rbp+0A0h]
0x140004746  mov     dword ptr [rsp+0B8h+var_80], eax
0x14000474a  sbb     r9b, r9b
0x14000474d  mov     eax, [rbp+0A4h]
0x140004753  and     r9b, 0Bh
0x140004757  mov     dword ptr [rsp+0B8h+var_88], eax
0x14000475b  add     r9b, 4Eh ; 'N'
0x14000475f  mov     eax, [rbp+9Ch]
0x140004765  mov     dword ptr [rsp+0B8h+var_90], eax
0x140004769  mov     byte ptr [rsp+0B8h+var_98], r8b
0x14000476e  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140004775  call    WPP_SF_ccDDD
0x14000477a  jmp     loc_14000447D
0x14000477f  mov     eax, [rcx+2Ch]
0x140004782  test    r14b, al
0x140004785  jz      loc_1400045AB
0x14000478b  mov     rcx, [rcx+18h]
0x14000478f  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140004796  mov     edx, 0Eh
0x14000479b  call    WPP_SF_
0x1400047a0  jmp     loc_1400045AB
0x1400047a5  cmp     r8d, r15d
0x1400047a8  jnz     loc_14000463A
0x1400047ae  call    cs:__imp_KeAreAllApcsDisabled
0x1400047b5  nop     dword ptr [rax+rax+00h]
0x1400047ba  test    al, al
0x1400047bc  jz      short loc_1400047D1
0x1400047be  mov     ecx, [rsp+0B8h+var_58]
0x1400047c2  mov     rax, cs:CscDevExtn
0x1400047c9  lock add [rax+9E0h], rcx
0x1400047d1  cmp     [rsp+0B8h+arg_0], 0
0x1400047d9  jz      loc_140004485
0x1400047df  cmp     [rsp+0B8h+var_68], 0
0x1400047e4  jz      short loc_140004815
0x1400047e6  mov     al, [rsi]
0x1400047e8  and     al, 18h
0x1400047ea  cmp     al, 8
0x1400047ec  jnz     short loc_140004815
0x1400047ee  mov     eax, [rbp+0A4h]
0x1400047f4  test    al, 2
0x1400047f6  jnz     short loc_1400047FC
0x1400047f8  test    bl, al
0x1400047fa  jz      short loc_140004815
0x1400047fc  mov     r9d, [rsp+0B8h+var_50]
0x140004801  mov     rdx, r14
0x140004804  mov     r8, [rsp+0B8h+var_48]
0x140004809  mov     rcx, rdi
0x14000480c  mov     byte ptr [rsp+0B8h+var_98], bl
0x140004810  call    CscPrefetchAttempt
0x140004815  call    cs:__imp_RxAcquirePowerContextLock
0x14000481c  nop     dword ptr [rax+rax+00h]
0x140004821  mov     al, [rbp+11Ah]
0x140004827  test    al, 2
0x140004829  jz      short loc_14000482F
0x14000482b  mov     dl, 2
0x14000482d  jmp     short loc_140004835
0x14000482f  mov     dl, 4
0x140004831  test    dl, al
0x140004833  jz      short loc_140004847
0x140004835  mov     r8b, bl
0x140004838  mov     rcx, rbp
0x14000483b  call    cs:__imp_RxUpdateFcbPowerState
0x140004842  nop     dword ptr [rax+rax+00h]
0x140004847  call    cs:__imp_RxReleasePowerContextLock
0x14000484e  nop     dword ptr [rax+rax+00h]
0x140004853  jmp     loc_140004485
0x140004858  mov     eax, [rcx+2Ch]
0x14000485b  test    r13b, al
0x14000485e  jz      loc_14000464A
0x140004864  mov     rcx, [rcx+18h]
0x140004868  mov     edx, 0Fh
0x14000486d  mov     dword ptr [rsp+0B8h+var_90], r15d
0x140004872  mov     [rsp+0B8h+var_98], r8d
0x140004877  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14000487e  call    WPP_SF_DDd
0x140004883  jmp     loc_14000464A
0x140004888  mov     rcx, [rsp+0B8h+Mdl]; Mdl
0x140004890  test    rcx, rcx
0x140004893  jz      short loc_1400048E4
0x140004895  call    cs:__imp_IoFreeMdl
0x14000489c  nop     dword ptr [rax+rax+00h]
0x1400048a1  mov     rcx, [rsp+0B8h+arg_18]
0x1400048a9  mov     rax, [rdi+28h]
0x1400048ad  mov     esi, [rsp+0B8h+var_54]
0x1400048b1  mov     [rax+8], rcx
  ... truncated ...
```
