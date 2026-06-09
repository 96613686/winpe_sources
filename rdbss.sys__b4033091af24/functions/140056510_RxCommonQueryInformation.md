# RxCommonQueryInformation

- ea: `0x140056510`
- end: `0x14005764e`
- name: `RxCommonQueryInformation`
- size: `4414`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007ca0`
- `0x140009b80`
- `0x14000d3d0`
- `0x140016d40`
- `0x140016e20`
- `0x140017280`
- `0x1400172b0`
- `0x140017310`
- `0x140019a28`
- `0x140025d80`
- `0x140026080`
- `0x140044ab4`
- `0x140044b10`
- `0x140056510`
- `0x140057660`
- `0x14006ae70`
- `0x14006b270`
- `0x14006b410`
- `0x14006c500`
- `0x140077660`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140056c35`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140056c35`
- `MUP!MupSurrogateGetFileName` at `0x140056864`
- `MUP!MupSurrogateGetFileName` at `0x140056864`

## string_xrefs

- `0x14007ad65`: `RxCommonQueryInformation`

## pseudocode

```c
__int64 __fastcall RxCommonQueryInformation(PRX_CONTEXT RxContext, _QWORD *a2)
{
  __int64 v4; // r13
  int v5; // ebx
  char v6; // r15
  __int64 v7; // rax
  unsigned __int16 *v8; // rsi
  CHAR *v9; // r9
  unsigned __int16 v10; // di
  __int64 v11; // r8
  PWCH *p_CanonicalNameBuffer; // rdx
  __int64 v13; // rcx
  char *v14; // r15
  ULONG v15; // r8d
  NTSTATUS v16; // eax
  int InfoMiniRdr; // edi
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  char v20; // bl
  int v21; // ecx
  PDEVICE_OBJECT v22; // rcx
  char v23; // bl
  char OwnerTable; // bl
  __int64 v25; // rdx
  PWCH *v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // eax
  PWCH *v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rdx
  unsigned int v33; // ecx
  unsigned int v34; // ebx
  unsigned int v35; // ecx
  unsigned int v36; // eax
  unsigned int v37; // edx
  unsigned int v38; // eax
  int v39; // ecx
  unsigned __int64 v40; // rcx
  unsigned int v41; // edx
  __int64 v42; // rbx
  unsigned int v43; // eax
  unsigned int v44; // r15d
  unsigned int v45; // eax
  __int64 v46; // rdx
  int v47; // ecx
  int v48; // eax
  PWCH *v49; // rdx
  unsigned int v50; // eax
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rbx
  unsigned int v54; // eax
  unsigned int v55; // ecx
  unsigned int v56; // eax
  const CHAR *BugCheckOnFailure; // [rsp+20h] [rbp-98h]
  signed int Priority; // [rsp+28h] [rbp-90h]
  char v60; // [rsp+44h] [rbp-74h]
  char v61; // [rsp+45h] [rbp-73h]
  unsigned int Size; // [rsp+50h] [rbp-68h]
  unsigned int Size_4; // [rsp+54h] [rbp-64h]
  int v64; // [rsp+5Ch] [rbp-5Ch]
  void *Src[2]; // [rsp+70h] [rbp-48h] BYREF
  PFOBX Fobx; // [rsp+C8h] [rbp+10h]
  PFOBX Fobxa; // [rsp+C8h] [rbp+10h]
  struct _FILE_OBJECT *v68; // [rsp+D8h] [rbp+20h]
  unsigned __int64 v69; // [rsp+D8h] [rbp+20h]
  struct _FILE_OBJECT *v70; // [rsp+D8h] [rbp+20h]

  v4 = a2[23];
  v5 = *(_DWORD *)(v4 + 16);
  v6 = 0;
  v60 = 0;
  v7 = *(_QWORD *)(v4 + 48);
  if ( v7 )
  {
    v8 = *(unsigned __int16 **)(v7 + 24);
    v9 = *(CHAR **)(v7 + 32);
    Fobx = (PFOBX)v9;
    if ( *v8 == 0xEC23 && v9 )
      v10 = -5080;
    else
      v10 = *v8;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    Fobx = 0;
    v10 = -5088;
  }
  LODWORD(v11) = *(_DWORD *)(v4 + 8);
  p_CanonicalNameBuffer = &RxContext->Create.CanonicalNameBuffer;
  *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    Priority = (int)v8;
    BugCheckOnFailure = v9;
    WPP_SF_qqqld(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, RxContext);
    p_CanonicalNameBuffer = &RxContext->Create.CanonicalNameBuffer;
  }
  if ( v5 >= 84 )
  {
    InfoMiniRdr = -1073741821;
    v23 = 0;
  }
  else
  {
    v13 = a2[1];
    if ( v13 )
    {
      if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
      {
        v14 = *(char **)(v13 + 24);
      }
      else
      {
        v14 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
        p_CanonicalNameBuffer = &RxContext->Create.CanonicalNameBuffer;
      }
    }
    else
    {
      v14 = (char *)a2[3];
    }
    if ( v14 )
    {
      memset(v14, 0, *(unsigned int *)p_CanonicalNameBuffer);
      v9 = (CHAR *)v10;
      if ( v10 != 60449 && v10 != 60448 && v10 != 60450 )
      {
        if ( v10 == 60454 )
        {
          InfoMiniRdr = -1073741822;
          v6 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, v10);
          }
          InfoMiniRdr = -1073741811;
          v6 = 0;
        }
        goto LABEL_40;
      }
      if ( (*((_DWORD *)v8 + 39) & 4) != 0 || v5 == 9 )
      {
LABEL_18:
        if ( v5 != 5 )
        {
          if ( v5 != 9 )
          {
            if ( v5 == 4 )
            {
              *(_OWORD *)v14 = 0;
              *((_OWORD *)v14 + 1) = 0;
              *((_QWORD *)v14 + 4) = 0;
              InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 60449, 4, v14);
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v19 = 54;
LABEL_26:
                WPP_SF_d(
                  v18->AttachedDevice,
                  v19,
                  WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                  (unsigned int)InfoMiniRdr);
              }
              goto LABEL_39;
            }
            switch ( v5 )
            {
              case 6:
                InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 0x140000000uLL, 6, v14);
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v19 = 57;
                  goto LABEL_26;
                }
                goto LABEL_39;
              case 7:
                v42 = a2[23];
                v43 = RxpQueryInfoMiniRdr(RxContext, 0x140000000uLL, 7, v14);
                v44 = v43;
                if ( *(_DWORD *)(v42 + 16) == 18 && v43 == -1073741822 )
                {
                  *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 4;
                  v44 = 0;
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, v44);
                }
                InfoMiniRdr = v44;
                goto LABEL_39;
              case 14:
                InfoMiniRdr = RxQueryPositionInfo(RxContext, a2, v11, v14);
                goto LABEL_39;
              case 18:
                v45 = *(_DWORD *)(v4 + 8);
                if ( v45 < 0x68 )
                {
                  InfoMiniRdr = -1073741789;
                  *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = v45;
LABEL_39:
                  a2[7] = (unsigned int)(*(_DWORD *)(v4 + 8)
                                       - *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8));
                  v6 = v60;
LABEL_40:
                  v23 = 0;
                  goto LABEL_215;
                }
                *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = v45;
                *(_OWORD *)v14 = 0;
                *((_OWORD *)v14 + 1) = 0;
                *((_QWORD *)v14 + 4) = 0;
                InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 0x140000000uLL, 4, v14);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    54,
                    WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                    (unsigned int)InfoMiniRdr);
                }
                if ( InfoMiniRdr )
                  goto LABEL_39;
                *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = *(_DWORD *)(v4 + 8) - 40;
                v61 = 0;
                v70 = *(struct _FILE_OBJECT **)(a2[23] + 48LL);
                *(_OWORD *)(v14 + 40) = 0;
                *((_QWORD *)v14 + 7) = 0;
                LODWORD(v11) = 60449;
                if ( *v8 != 60449 && *v8 != 60450 || (*((_DWORD *)Fobx->Context2 + 32) & 0x4000) != 0 )
                  goto LABEL_141;
                v47 = *((_DWORD *)v8 + 62);
                *((_DWORD *)v14 + 14) = v47;
                v14[60] = v8[78] & 1;
                v14[61] = *v8 == 0xEC21;
                if ( !v47 )
                  *((_DWORD *)v14 + 14) = 1;
                if ( *v8 == 0xEC22 )
                {
                  *((_QWORD *)v14 + 5) = *((_QWORD *)v8 + 3);
                  *((_QWORD *)v14 + 6) = *((_QWORD *)v8 + 4);
                }
                if ( (*((_DWORD *)v8 + 41) & 8) != 0 && (*((_DWORD *)v8 + 40) & 0x100000) != 0 )
                {
                  if ( !RxForceQFIPassThrough )
                  {
                    *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 24;
LABEL_142:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_Dd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        55,
                        WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                        (unsigned int)InfoMiniRdr,
                        *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8));
                    }
                    if ( !InfoMiniRdr )
                    {
                      *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = *(_DWORD *)(v4 + 8)
                                                                                                - 64;
                      InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, v46, 6, v14 + 64);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          57,
                          WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                          (unsigned int)InfoMiniRdr);
                      }
                      if ( !InfoMiniRdr )
                      {
                        *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = *(_DWORD *)(v4 + 8) - 72;
                        v53 = a2[23];
                        v54 = RxpQueryInfoMiniRdr(RxContext, v52, 7, v14 + 72);
                        v55 = v54;
                        Size_4 = v54;
                        if ( *(_DWORD *)(v53 + 16) == 18 && v54 == -1073741822 )
                        {
                          *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 4;
                          v55 = 0;
                          Size_4 = 0;
                        }
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            58,
                            WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                            v55);
                          v55 = Size_4;
                        }
                        InfoMiniRdr = v55;
                        if ( !v55 )
                        {
                          v56 = *(_DWORD *)(v4 + 8) - 80;
                          *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = v56;
                          if ( v56 < 8 )
                          {
                            InfoMiniRdr = -1073741789;
                          }
                          else
                          {
                            *((_QWORD *)v14 + 10) = *(_QWORD *)(*(_QWORD *)(a2[23] + 48LL) + 104LL);
                            *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 8;
                            LODWORD(v11) = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                            {
                              WPP_SF_Dd(
                                WPP_GLOBAL_Control->AttachedDevice,
                                59,
                                WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                                0,
                                v11);
                            }
                            InfoMiniRdr = 0;
                          }
                          if ( !InfoMiniRdr )
                          {
                            *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = *(_DWORD *)(v4 + 8) - 96;
                            LODWORD(BugCheckOnFailure) = (_DWORD)v14 + 96;
                            InfoMiniRdr = RxQueryNameInfoInternal(
                                            RxContext,
                                            v8,
                                            Fobx,
                                            LOBYTE(RxContext->NonPagedFcb->BufferedLocksResource.OwnerTable));
                          }
                        }
                      }
                    }
                    goto LABEL_39;
                  }
                }
                else
                {
                  v61 = 1;
                }
LABEL_141:
                InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, v46, 5, v14 + 40);
                if ( InfoMiniRdr >= 0 && v61 && *v8 == 0xEC22 )
                  RxTryUpdateFileSizeAfterQuery((__int64)v8, v70, (__int64)(v14 + 40));
                goto LABEL_142;
              case 21:
                InfoMiniRdr = RxQueryAlternateNameInfo(RxContext, 0x140000000uLL, v11, v14);
                goto LABEL_39;
              case 23:
              case 24:
              case 25:
                InfoMiniRdr = RxQueryPipeInfo((_DWORD)RxContext, (_DWORD)a2, (_DWORD)v8, (_DWORD)Fobx, (__int64)v14);
                goto LABEL_39;
              case 28:
                InfoMiniRdr = RxQueryCompressedInfo(RxContext, 0x140000000uLL, v8, v14);
                goto LABEL_39;
              case 34:
                *(_OWORD *)v14 = 0;
                *((_OWORD *)v14 + 1) = 0;
                *((_OWORD *)v14 + 2) = 0;
                *((_QWORD *)v14 + 6) = 0;
                InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 0x140000000uLL, 34, v14);
                if ( InfoMiniRdr >= 0
                  && *v8 == 0xEC22
                  && (*((_DWORD *)Fobx->Context2 + 32) & 0x4000) == 0
                  && (*((_DWORD *)v8 + 41) & 2) != 0
                  && (*((_DWORD *)v8 + 40) & 0x8000000) != 0 )
                {
                  *((_QWORD *)v14 + 4) = *((_QWORD *)v8 + 3);
                  *((_QWORD *)v14 + 5) = *((_QWORD *)v8 + 4);
                }
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v32 = 56;
                  goto LABEL_214;
                }
                goto LABEL_39;
              case 48:
                v64 = 0;
                v33 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                if ( v33 < 4 )
                {
                  *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 0;
                  InfoMiniRdr = -1073741789;
                }
                else
                {
                  Fobxa = (PFOBX)*((_QWORD *)v8 + 15);
                  v34 = v33 - 4;
                  InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 0, 48, v14);
                  if ( (int)(InfoMiniRdr + 0x80000000) < 0 || InfoMiniRdr == -2147483643 )
                  {
                    v35 = *((unsigned __int16 *)&Fobxa->Specific.DiskFile + 36);
                    Size = v35;
                    v36 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                    if ( v36 > v34 )
                    {
                      InfoMiniRdr = -1073741629;
                    }
                    else
                    {
                      if ( *(_DWORD *)v14 )
                      {
                        if ( *((_WORD *)v14 + 2) == 58 )
                        {
                          v64 = 1;
                        }
                        else
                        {
                          v35 += 2;
                          Size = v35;
                        }
                      }
                      v37 = v34 - v36;
                      if ( v34 - v36 + v35 > v34 )
                      {
                        InfoMiniRdr = -2147483643;
                        if ( v35 <= v34 )
                        {
                          v37 = v34 - v35;
                        }
                        else
                        {
                          v37 = 0;
                          v35 = v34;
                          Size = v34;
                        }
                      }
                      v69 = v35;
                      memmove(&v14[v35 + 4], v14 + 4, v37);
                      v38 = *((unsigned __int16 *)&Fobxa->Specific.DiskFile + 36);
                      if ( Size < v38 )
                        v38 = Size;
                      memmove(v14 + 4, Fobxa->Specific.NamedPipe.WriteSerializationQueue.Flink, v38);
                      v39 = *(_DWORD *)v14;
                      LODWORD(v11) = v64;
                      if ( *(_DWORD *)v14 && !v64 )
                      {
                        v39 += 2;
                        *(_DWORD *)v14 = v39;
                      }
                      *(_DWORD *)v14 = v39 + *((unsigned __int16 *)&Fobxa->Specific.DiskFile + 36);
                      v40 = *((unsigned __int16 *)&Fobxa->Specific.DiskFile + 36);
                      if ( v69 >= v40 + 2 && !v64 )
                        *(_WORD *)&v14[2 * (v40 >> 1) + 4] = 92;
                      v41 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                      if ( Size > v41 )
                        *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 0;
                      else
                        *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = v41 - Size;
                    }
                  }
                }
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v19 = 65;
                  goto LABEL_26;
                }
                goto LABEL_39;
              case 49:
                v49 = &RxContext->Create.CanonicalNameBuffer;
                v50 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                if ( v50 < 4 )
                {
                  *(_DWORD *)v49 = 0;
                  InfoMiniRdr = -1073741789;
                }
                else
                {
                  *(_DWORD *)v49 = v50 - 4;
                  if ( *(PFCB *)(*(_QWORD *)(*((_QWORD *)v8 + 15) + 32LL) + 48LL) == Fcb )
                  {
                    InfoMiniRdr = -1073741772;
                  }
                  else
                  {
                    RxConjureOriginalName(
                      (PFCB)v8,
                      Fobx,
                      (PULONG)v14,
                      (PWCHAR)v14 + 2,
                      (PLONG)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8,
                      (RX_NAME_CONJURING_METHODS)Priority);
                    InfoMiniRdr = v51;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        63,
                        WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                        *((unsigned int *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8));
                    }
                  }
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  LODWORD(BugCheckOnFailure) = InfoMiniRdr;
                  LOBYTE(v9) = 78;
                  WPP_SF_cD(WPP_GLOBAL_Control->AttachedDevice, v49, v11, v9);
                }
                goto LABEL_39;
              case 54:
              case 56:
              case 57:
                InfoMiniRdr = -1073741637;
                goto LABEL_39;
              default:
                InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 60449, (unsigned int)v5, v14);
                RxContext->StoredStatus = InfoMiniRdr;
                goto LABEL_39;
            }
          }
          OwnerTable = (char)RxContext->NonPagedFcb->BufferedLocksResource.OwnerTable;
          v25 = 0;
          v26 = &RxContext->Create.CanonicalNameBuffer;
          v27 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
          if ( v27 < 4 )
          {
            *(_DWORD *)v26 = 0;
            InfoMiniRdr = -1073741789;
          }
          else
          {
            *(_DWORD *)v26 = v27 - 4;
            if ( OwnerTable )
            {
              *(_OWORD *)Src = 0;
              LOBYTE(v11) = 1;
              InfoMiniRdr = MupSurrogateGetFileName(RxContext->CurrentIrpSp->FileObject, 3, v11, Src);
              if ( InfoMiniRdr >= 0 )
              {
                v28 = LOWORD(Src[0]);
                if ( (unsigned int)LOWORD(Src[0]) >= *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory
                                                     + 8) )
                  v28 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                memmove(v14 + 4, Src[1], v28);
                *(_DWORD *)v14 = LOWORD(Src[0]);
                v25 = LOWORD(Src[0]);
                v29 = &RxContext->Create.CanonicalNameBuffer;
                v30 = *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
                if ( v30 >= LOWORD(Src[0]) )
                {
                  *(_DWORD *)v29 = v30 - LOWORD(Src[0]);
LABEL_50:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      63,
                      WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                      *(unsigned int *)v29);
                  }
                  goto LABEL_52;
                }
                *(_DWORD *)v29 = 0;
                InfoMiniRdr = -2147483643;
              }
            }
            else
            {
              if ( *(PFCB *)(*(_QWORD *)(*((_QWORD *)v8 + 15) + 32LL) + 48LL) != Fcb )
              {
                RxConjureOriginalName(
                  (PFCB)v8,
                  Fobx,
                  (PULONG)v14,
                  (PWCHAR)v14 + 2,
                  (PLONG)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8,
                  (RX_NAME_CONJURING_METHODS)Priority);
                InfoMiniRdr = v48;
                v29 = &RxContext->Create.CanonicalNameBuffer;
                goto LABEL_50;
              }
              InfoMiniRdr = -1073741772;
            }
          }
LABEL_52:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v31 = 89;
            if ( !OwnerTable )
              v31 = 78;
            LODWORD(BugCheckOnFailure) = InfoMiniRdr;
            WPP_SF_cD(WPP_GLOBAL_Control->AttachedDevice, v25, v11, v31);
          }
          goto LABEL_39;
        }
        InfoMiniRdr = 0;
        v20 = 0;
        v68 = *(struct _FILE_OBJECT **)(a2[23] + 48LL);
        *(_OWORD *)v14 = 0;
        *((_QWORD *)v14 + 2) = 0;
        if ( (*v8 == 60449 || *v8 == 60450) && (*((_DWORD *)Fobx->Context2 + 32) & 0x4000) == 0 )
        {
          v21 = *((_DWORD *)v8 + 62);
          *((_DWORD *)v14 + 4) = v21;
          v14[20] = v8[78] & 1;
          v14[21] = *v8 == 0xEC21;
          if ( !v21 )
            *((_DWORD *)v14 + 4) = 1;
          if ( *v8 == 0xEC22 )
          {
            *(_QWORD *)v14 = *((_QWORD *)v8 + 3);
            *((_QWORD *)v14 + 1) = *((_QWORD *)v8 + 4);
          }
          if ( (*((_DWORD *)v8 + 41) & 8) != 0 && (*((_DWORD *)v8 + 40) & 0x100000) != 0 )
          {
            if ( !RxForceQFIPassThrough )
            {
              *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 24;
LABEL_37:
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v32 = 55;
LABEL_214:
                WPP_SF_Dd(
                  v22->AttachedDevice,
                  v32,
                  WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
                  (unsigned int)InfoMiniRdr,
                  *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8));
              }
              goto LABEL_39;
            }
          }
          else
          {
            v20 = 1;
          }
        }
        InfoMiniRdr = RxpQueryInfoMiniRdr(RxContext, 60449, 5, v14);
        if ( InfoMiniRdr >= 0 && v20 && *v8 == 0xEC22 )
          RxTryUpdateFileSizeAfterQuery((__int64)v8, v68, (__int64)v14);
        goto LABEL_37;
      }
      if ( v5 == 28 )
        v15 = 1;
      else
        v15 = 2;
      v16 = _RxAcquireFcb((PFCB)v8, RxContext, v15, 0, BugCheckOnFailure, Priority);
      InfoMiniRdr = v16;
      if ( v16 == -1073741739 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids);
        }
        v23 = 1;
        v6 = 0;
      }
      else
      {
        if ( !v16 )
        {
          v60 = 1;
          goto LABEL_18;
        }
        v23 = 0;
        v6 = 0;
      }
    }
    else
    {
      InfoMiniRdr = -1073741670;
      v6 = 0;
      v23 = 0;
    }
  }
LABEL_215:
  if ( v6 )
    _RxReleaseFcb(RxContext, (PMRX_FCB)v8, v11, v9, (ULONG)BugCheckOnFailure);
  if ( InfoMiniRdr != 259 && (v23 || BYTE3(RxContext->RealDevice)) )
    InfoMiniRdr = RxFsdPostRequest(RxContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
      (unsigned int)InfoMiniRdr,
      *((_DWORD *)a2 + 14));
  }
  return (unsigned int)InfoMiniRdr;
}

```

## disassembly

```asm
0x140056510  mov     [rsp+arg_0], rcx
0x140056515  push    rbx
0x140056516  push    rsi
0x140056517  push    rdi
0x140056518  push    r12
0x14005651a  push    r13
0x14005651c  push    r14
0x14005651e  push    r15
0x140056520  sub     rsp, 80h
0x140056527  mov     r12, rdx
0x14005652a  mov     r14, rcx
0x14005652d  mov     r13, [rdx+0B8h]
0x140056534  mov     ebx, [r13+10h]
0x140056538  xor     r15b, r15b
0x14005653b  mov     [rsp+0B8h+var_74], r15b
0x140056540  mov     rax, [r13+30h]
0x140056544  test    rax, rax
0x140056547  jz      loc_1400575AF
0x14005654d  mov     rsi, [rax+18h]
0x140056551  mov     [rsp+0B8h+arg_10], rsi
0x140056559  mov     r9, [rax+20h]
0x14005655d  mov     [rsp+0B8h+Fobx], r9
0x140056565  movzx   eax, word ptr [rsi]
0x140056568  mov     ecx, 0EC23h
0x14005656d  cmp     ax, cx
0x140056570  jz      loc_14005759C
0x140056576  movzx   edi, ax
0x140056579  mov     r8d, [r13+8]
0x14005657d  lea     rdx, [r14+1D8h]
0x140056584  mov     [rdx], r8d
0x140056587  lea     rax, WPP_GLOBAL_Control
0x14005658e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056595  cmp     rcx, rax
0x140056598  jz      short loc_1400565A5
0x14005659a  mov     eax, [rcx+2Ch]
0x14005659d  test    al, 20h
0x14005659f  jnz     loc_1400575CE
0x1400565a5  cmp     ebx, 54h ; 'T'
0x1400565a8  jge     loc_14005724F
0x1400565ae  mov     rcx, [r12+8]; MemoryDescriptorList
0x1400565b3  test    rcx, rcx
0x1400565b6  jnz     loc_140056C10
0x1400565bc  mov     r15, [r12+18h]
0x1400565c1  test    r15, r15
0x1400565c4  jz      loc_1400567FD
0x1400565ca  mov     r8d, [rdx]; Size
0x1400565cd  xor     edx, edx; Val
0x1400565cf  mov     rcx, r15; void *
0x1400565d2  call    memset
0x1400565d7  movzx   r9d, di
0x1400565db  mov     edx, 0EC21h
0x1400565e0  cmp     r9d, edx
0x1400565e3  jnz     loc_140057299
0x1400565e9  mov     eax, [rsi+9Ch]
0x1400565ef  test    al, 4
0x1400565f1  jnz     short loc_140056638
0x1400565f3  cmp     ebx, 9
0x1400565f6  jz      short loc_140056638
0x1400565f8  xor     r9d, r9d; LineNumber
0x1400565fb  mov     rdx, r14; RxContext
0x1400565fe  mov     rcx, rsi; Fcb
0x140056601  cmp     ebx, 1Ch
0x140056604  jz      loc_14005730D
0x14005660a  mov     r8d, 2; Mode
0x140056610  call    __RxAcquireFcb
0x140056615  mov     [rsp+0B8h+var_78], eax
0x140056619  mov     edi, eax
0x14005661b  cmp     eax, 0C0000055h
0x140056620  jz      loc_140057318
0x140056626  test    eax, eax
0x140056628  jnz     loc_1400567EC
0x14005662e  mov     [rsp+0B8h+var_74], 1
0x140056633  mov     edx, 0EC21h
0x140056638  cmp     ebx, 5
0x14005663b  jz      loc_1400566DC
0x140056641  cmp     ebx, 9
0x140056644  jz      loc_140056817
0x14005664a  cmp     ebx, 4
0x14005664d  jz      loc_140056929
0x140056653  lea     eax, [rbx-6]; switch 52 cases
0x140056656  cmp     eax, 33h
0x140056659  ja      def_14005667A; jumptable 000000014005667A default case, cases 8-13,15-17,19,20,22,26,27,29-33,35-47,50-53,55
0x14005665f  cdqe
0x140056661  lea     rdx, cs:140000000h
0x140056668  movzx   eax, ds:(byte_14002AD87 - 140000000h)[rdx+rax]
0x140056670  mov     ecx, ds:(jpt_14005667A - 140000000h)[rdx+rax*4]
0x140056677  add     rcx, rdx
0x14005667a  jmp     rcx; switch jump
0x140056680  mov     r9, r15; jumptable 000000014005667A case 6
0x140056683  mov     r8d, 6
0x140056689  mov     rcx, r14
0x14005668c  call    RxpQueryInfoMiniRdr
0x140056691  mov     edi, eax
0x140056693  mov     rcx, cs:WPP_GLOBAL_Control
0x14005669a  lea     rax, WPP_GLOBAL_Control
0x1400566a1  cmp     rcx, rax
0x1400566a4  jz      loc_1400567C4
0x1400566aa  mov     eax, [rcx+2Ch]
0x1400566ad  test    al, 20h
0x1400566af  jz      loc_1400567C4
0x1400566b5  cmp     byte ptr [rcx+29h], 2
0x1400566b9  jb      loc_1400567C4
0x1400566bf  mov     edx, 39h ; '9'
0x1400566c4  mov     r9d, edi
0x1400566c7  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x1400566ce  mov     rcx, [rcx+18h]
0x1400566d2  call    WPP_SF_d
0x1400566d7  jmp     loc_1400567C4
0x1400566dc  xor     edi, edi
0x1400566de  mov     [rsp+0B8h+var_50], edi
0x1400566e2  mov     rax, [r12+0B8h]
0x1400566ea  xor     bl, bl
0x1400566ec  mov     [rsp+0B8h+var_72], bl
0x1400566f0  mov     rax, [rax+30h]
0x1400566f4  mov     [rsp+0B8h+arg_18], rax
0x1400566fc  xorps   xmm0, xmm0
0x1400566ff  xor     eax, eax
0x140056701  movups  xmmword ptr [r15], xmm0
0x140056705  mov     [r15+10h], rax
0x140056709  movzx   ecx, word ptr [rsi]
0x14005670c  sub     ecx, edx
0x14005670e  jz      short loc_140056715
0x140056710  cmp     ecx, 1
0x140056713  jnz     short loc_140056787
0x140056715  mov     rax, [rsp+0B8h+Fobx]
0x14005671d  mov     rax, [rax+20h]
0x140056721  test    dword ptr [rax+80h], 4000h
0x14005672b  jnz     short loc_140056787
0x14005672d  mov     ecx, [rsi+0F8h]
0x140056733  mov     [r15+10h], ecx
0x140056737  movzx   eax, byte ptr [rsi+9Ch]
0x14005673e  and     al, 1
0x140056740  mov     [r15+14h], al
0x140056744  cmp     [rsi], dx
0x140056747  setz    al
0x14005674a  mov     [r15+15h], al
0x14005674e  test    ecx, ecx
0x140056750  jnz     short loc_14005675A
0x140056752  mov     dword ptr [r15+10h], 1
0x14005675a  mov     eax, 0EC22h
0x14005675f  cmp     [rsi], ax
0x140056762  jnz     short loc_140056773
0x140056764  mov     rax, [rsi+18h]
0x140056768  mov     [r15], rax
0x14005676b  mov     rax, [rsi+20h]
0x14005676f  mov     [r15+8], rax
0x140056773  mov     eax, [rsi+0A4h]
0x140056779  test    al, 8
0x14005677b  jnz     loc_140056984
0x140056781  mov     bl, 1
0x140056783  mov     [rsp+0B8h+var_72], bl
0x140056787  mov     r9, r15
0x14005678a  mov     r8d, 5
0x140056790  mov     rcx, r14
0x140056793  call    RxpQueryInfoMiniRdr
0x140056798  mov     edi, eax
0x14005679a  mov     [rsp+0B8h+var_50], eax
0x14005679e  test    eax, eax
0x1400567a0  jns     loc_1400569CD
0x1400567a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400567ad  lea     rax, WPP_GLOBAL_Control
0x1400567b4  cmp     rcx, rax
0x1400567b7  jz      short loc_1400567C4
0x1400567b9  mov     eax, [rcx+2Ch]
0x1400567bc  test    al, 20h
0x1400567be  jnz     loc_140057513
0x1400567c4  mov     [rsp+0B8h+var_78], edi
0x1400567c8  mov     eax, [r13+8]
0x1400567cc  sub     eax, [r14+1D8h]
0x1400567d3  mov     [r12+38h], rax
0x1400567d8  movzx   r15d, [rsp+0B8h+var_74]
0x1400567de  lea     r13, WPP_GLOBAL_Control
0x1400567e5  xor     bl, bl
0x1400567e7  jmp     loc_140057545
0x1400567ec  xor     bl, bl
0x1400567ee  xor     r15b, r15b
0x1400567f1  lea     r13, WPP_GLOBAL_Control
0x1400567f8  jmp     loc_140057545
0x1400567fd  mov     edi, 0C000009Ah
0x140056802  mov     [rsp+0B8h+var_78], edi
0x140056806  xor     r15b, r15b
0x140056809  lea     r13, WPP_GLOBAL_Control
0x140056810  xor     bl, bl
0x140056812  jmp     loc_140057545
0x140056817  mov     rax, [r14+50h]
0x14005681b  movzx   ebx, byte ptr [rax+180h]
0x140056822  xor     edx, edx
0x140056824  mov     [rsp+0B8h+var_70], edx
0x140056828  lea     rcx, [r14+1D8h]
0x14005682f  mov     eax, [rcx]
0x140056831  cmp     eax, 4
0x140056834  jb      loc_140056BF9
0x14005683a  add     eax, 0FFFFFFFCh
0x14005683d  mov     [rcx], eax
0x14005683f  test    bl, bl
0x140056841  jz      loc_140056E50
0x140056847  xorps   xmm0, xmm0
0x14005684a  movups  xmmword ptr [rsp+0B8h+Src], xmm0
0x14005684f  mov     rcx, [r14+30h]
0x140056853  lea     r9, [rsp+0B8h+Src]
0x140056858  mov     r8b, 1
0x14005685b  mov     edx, 3
0x140056860  mov     rcx, [rcx+30h]
0x140056864  call    cs:__imp_MupSurrogateGetFileName
0x14005686b  nop     dword ptr [rax+rax+00h]
0x140056870  mov     edi, eax
0x140056872  mov     [rsp+0B8h+var_70], eax
0x140056876  test    eax, eax
0x140056878  js      loc_140056A0A
0x14005687e  mov     ecx, [r14+1D8h]
0x140056885  movzx   eax, word ptr [rsp+0B8h+Src]
0x14005688a  cmp     eax, ecx
0x14005688c  cmovnb  eax, ecx
0x14005688f  mov     r8d, eax; Size
0x140056892  lea     rcx, [r15+4]; void *
0x140056896  mov     rdx, [rsp+0B8h+Src+8]; Src
0x14005689b  call    memmove
0x1400568a0  movzx   eax, word ptr [rsp+0B8h+Src]
0x1400568a5  mov     [r15], eax
0x1400568a8  movzx   edx, word ptr [rsp+0B8h+Src]
0x1400568ad  lea     rcx, [r14+1D8h]
0x1400568b4  mov     eax, [rcx]
0x1400568b6  cmp     eax, edx
0x1400568b8  jb      loc_1400569FB
0x1400568be  sub     eax, edx
0x1400568c0  mov     [rcx], eax
0x1400568c2  mov     r10, cs:WPP_GLOBAL_Control
0x1400568c9  lea     r15, WPP_GLOBAL_Control
0x1400568d0  cmp     r10, r15
0x1400568d3  jz      short loc_1400568E1
0x1400568d5  mov     eax, [r10+2Ch]
0x1400568d9  test    al, 20h
0x1400568db  jnz     loc_1400574EB
0x1400568e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400568e8  cmp     rcx, r15
0x1400568eb  jz      loc_1400567C4
0x1400568f1  mov     eax, [rcx+2Ch]
0x1400568f4  test    al, 20h
0x1400568f6  jz      loc_1400567C4
0x1400568fc  cmp     byte ptr [rcx+29h], 2
0x140056900  jb      loc_1400567C4
0x140056906  mov     eax, 4Eh ; 'N'
0x14005690b  mov     r9d, 59h ; 'Y'
0x140056911  test    bl, bl
0x140056913  cmovz   r9d, eax
0x140056917  mov     [rsp+0B8h+BugCheckOnFailure], edi
0x14005691b  mov     rcx, [rcx+18h]
0x14005691f  call    WPP_SF_cD
0x140056924  jmp     loc_1400567C4
0x140056929  xorps   xmm0, xmm0
0x14005692c  xor     eax, eax
0x14005692e  movups  xmmword ptr [r15], xmm0
0x140056932  movups  xmmword ptr [r15+10h], xmm0
0x140056937  mov     [r15+20h], rax
0x14005693b  mov     r9, r15
0x14005693e  mov     r8d, 4
0x140056944  mov     rcx, r14
0x140056947  call    RxpQueryInfoMiniRdr
0x14005694c  mov     edi, eax
0x14005694e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056955  lea     rax, WPP_GLOBAL_Control
0x14005695c  cmp     rcx, rax
0x14005695f  jz      loc_1400567C4
0x140056965  mov     eax, [rcx+2Ch]
0x140056968  test    al, 20h
0x14005696a  jz      loc_1400567C4
0x140056970  cmp     byte ptr [rcx+29h], 2
0x140056974  jb      loc_1400567C4
0x14005697a  mov     edx, 36h ; '6'
0x14005697f  jmp     loc_1400566C4
0x140056984  test    dword ptr [rsi+0A0h], 100000h
0x14005698e  jz      loc_140056781
0x140056994  cmp     cs:RxForceQFIPassThrough, bl
0x14005699a  jnz     loc_140056787
0x1400569a0  add     dword ptr [r14+1D8h], 0FFFFFFE8h
0x1400569a8  jmp     loc_1400567A6
0x1400569ad  mov     r9, r15; jumptable 000000014005667A default case, cases 8-13,15-17,19,20,22,26,27,29-33,35-47,50-53,55
0x1400569b0  mov     r8d, ebx
0x1400569b3  mov     rcx, r14
0x1400569b6  call    RxpQueryInfoMiniRdr
0x1400569bb  mov     edi, eax
0x1400569bd  mov     [r14+0B0h], eax
0x1400569c4  mov     [rsp+0B8h+var_78], eax
0x1400569c8  jmp     loc_1400567C8
0x1400569cd  test    bl, bl
0x1400569cf  jz      loc_1400567A6
0x1400569d5  mov     ebx, 0EC22h
0x1400569da  cmp     [rsi], bx
0x1400569dd  jnz     loc_1400567A6
0x1400569e3  mov     r8, r15
0x1400569e6  mov     rdx, [rsp+0B8h+arg_18]
0x1400569ee  mov     rcx, rsi
0x1400569f1  call    RxTryUpdateFileSizeAfterQuery
0x1400569f6  jmp     loc_1400567A6
0x1400569fb  mov     dword ptr [rcx], 0
0x140056a01  mov     edi, 80000005h
0x140056a06  mov     [rsp+0B8h+var_70], edi
0x140056a0a  lea     r15, WPP_GLOBAL_Control
0x140056a11  jmp     loc_1400568E1
0x140056a16  xorps   xmm0, xmm0; jumptable 000000014005667A case 34
  ... truncated ...
```
