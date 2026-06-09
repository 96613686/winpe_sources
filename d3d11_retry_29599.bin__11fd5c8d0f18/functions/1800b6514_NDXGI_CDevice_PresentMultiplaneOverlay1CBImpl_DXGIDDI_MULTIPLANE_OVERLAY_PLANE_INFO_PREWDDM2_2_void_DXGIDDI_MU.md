# NDXGI::CDevice::PresentMultiplaneOverlay1CBImpl<DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO_PREWDDM2_2>(void *,DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO_PREWDDM2_2 * *,uint,void *)

- ea: `0x1800b6514`
- end: `0x1800b68ac`
- name: `??$PresentMultiplaneOverlay1CBImpl@UDXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO_PREWDDM2_2@@@CDevice@NDXGI@@KAJPEAXPEAPEAUDXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO_PREWDDM2_2@@I0@Z`
- size: `920`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800baac0`

## callees

- `0x180021b90`
- `0x180022630`
- `0x180035e3c`
- `0x18005ec80`
- `0x180086260`
- `0x1800a7328`
- `0x1800a9d20`
- `0x1800b6364`
- `0x1800b6514`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b680d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b680d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b6807`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b6807`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b684d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b684d`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTPresentMultiPlaneOverlay3` at `0x1800b6756`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NDXGI::CDevice::PresentMultiplaneOverlay1CBImpl<DXGIDDI_MULTIPLANE_OVERLAY_PLANE_INFO_PREWDDM2_2>(
        RTL_SRWLOCK *this,
        __int64 a2,
        int a3,
        _com_error *a4)
{
  RTL_SRWLOCK *v7; // r13
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r11
  __int64 DataFrom; // r8
  struct _RTL_CRITICAL_SECTION *v13; // r15
  char v14; // di
  __int64 v15; // r10
  int *v16; // r9
  __int64 v17; // r11
  int v18; // eax
  signed int v19; // edi
  int v20; // eax
  _QWORD *Ptr; // rcx
  PVOID *v22; // rax
  _BYTE *v23; // rdx
  _BYTE *v24; // rdx
  _BYTE v25[48]; // [rsp+0h] [rbp-1B8h] BYREF
  char v26; // [rsp+30h] [rbp-188h]
  DWORD CurrentThreadId; // [rsp+34h] [rbp-184h] BYREF
  __int64 v28; // [rsp+38h] [rbp-180h]
  RTL_SRWLOCK *v29; // [rsp+40h] [rbp-178h]
  __int64 v30; // [rsp+48h] [rbp-170h] BYREF
  _com_error *v31; // [rsp+50h] [rbp-168h]
  struct _RTL_CRITICAL_SECTION *v32; // [rsp+58h] [rbp-160h]
  _com_error *v33[4]; // [rsp+60h] [rbp-158h] BYREF
  _DWORD v34[64]; // [rsp+80h] [rbp-138h] BYREF

  v30 = a2;
  v31 = a4;
  v28 = 0;
  v33[1] = (_com_error *)this;
  v33[2] = a4;
  v7 = this + 9;
  v29 = this + 9;
  LOBYTE(a2) = 9;
  if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(this[9].Ptr, a2, 4) )
  {
    try
    {
      v13 = (struct _RTL_CRITICAL_SECTION *)&this[240];
      v32 = (struct _RTL_CRITICAL_SECTION *)&this[240];
      DataFrom = NDXGI::OpaqueHandleManager<BatchablePresentMPO>::GetDataFromToken<_lambda_005e3fab6570a2faca41cdd9726fee38_>((LPCRITICAL_SECTION)&this[240]);
      v10 = v30;
    }
    catch ( _com_error *v33 )
    {
      v23 = v25;
      CurrentThreadId = *((_DWORD *)v33[0] + 2);
      LOBYTE(v23) = 9;
      if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v29->Ptr, v23, 4) )
        NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v32, (ULONG_PTR)v31);
      return CurrentThreadId;
    }
    catch ( std::bad_alloc )
    {
      v24 = v25;
      LOBYTE(v24) = 9;
      if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v29->Ptr, v24, 4) )
        NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v32, (ULONG_PTR)v31);
      return 2147942414LL;
    }
  }
  else
  {
    DataFrom = (__int64)a4;
    v13 = (struct _RTL_CRITICAL_SECTION *)&this[240];
  }
  if ( a3 != *(_DWORD *)(DataFrom + 28) )
  {
LABEL_25:
    LOBYTE(v8) = 9;
    if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v7->Ptr, v8, 4) )
      NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v13, (ULONG_PTR)a4);
    return 2147942487LL;
  }
  *(_QWORD *)(DataFrom + 8) = v34;
  *(_DWORD *)(DataFrom + 4) = 0;
  v14 = 1;
  v26 = 1;
  v8 = 0;
  CurrentThreadId = 0;
  if ( *(_DWORD *)(DataFrom + 28) )
  {
    while ( 1 )
    {
      v15 = *(_QWORD *)(*(_QWORD *)(DataFrom + 32) + 8 * v8);
      v16 = *(int **)(v10 + 8 * v8);
      if ( (*(_BYTE *)(v15 + 4) & 1) != 0 )
      {
        if ( (unsigned int)*v16 > 0x40 )
          goto LABEL_25;
        *(_QWORD *)(v15 + 24) = *((_QWORD *)v16 + 2);
        *(_DWORD *)(v15 + 16) = *v16;
        if ( v14 )
        {
          v26 = 0;
          v17 = 0;
          v18 = *v16;
          if ( *v16 )
          {
            do
            {
              v9 = *(_QWORD *)(*((_QWORD *)v16 + 1) + 8 * v17);
              v34[v17] = *(_DWORD *)(v9 + 8);
              v17 = (unsigned int)(v17 + 1);
              v18 = *v16;
            }
            while ( (unsigned int)v17 < *v16 );
            LODWORD(v8) = CurrentThreadId;
          }
          *(_DWORD *)(DataFrom + 4) = v18;
          v10 = v30;
        }
        if ( (*(_BYTE *)(DataFrom + 24) & 0x40) == 0 )
        {
          v19 = D3DKMTWaitForSynchronizationObject((struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT *)v9);
          LODWORD(v28) = v19;
          if ( v19 < 0 )
            goto LABEL_55;
        }
      }
      else
      {
        *(_QWORD *)(v15 + 24) = 0;
        *(_DWORD *)(v15 + 16) = 0;
      }
      *(_DWORD *)(v15 + 32) = v16[6];
      *(_QWORD *)(v15 + 40) = *((_QWORD *)v16 + 4);
      v8 = (unsigned int)(v8 + 1);
      CurrentThreadId = v8;
      if ( (unsigned int)v8 >= *(_DWORD *)(DataFrom + 28) )
        break;
      v14 = v26;
    }
  }
  if ( !*(_DWORD *)(DataFrom + 4) )
  {
    *(_DWORD *)(DataFrom + 4) = 1;
    v34[0] = *(_DWORD *)(**(_QWORD **)(*(_QWORD *)v10 + 8LL) + 8LL);
  }
  v20 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
          D3DKMTPresentMultiPlaneOverlay3,
          "PresentMultiplaneOverlay3",
          DataFrom);
  v8 = (unsigned int)v20;
  HIDWORD(v28) = v20;
  if ( v20 > -1071775733 )
  {
    if ( v20 == -1071775731 )
    {
      HIDWORD(v28) = 0;
    }
    else if ( (unsigned int)(v20 + 1071775720) > 1 && v20 != -1071774910 )
    {
      if ( v20 != 259 )
      {
LABEL_40:
        v19 = NDXGI::CDevice::NTStatusToHResult((NDXGI::CDevice *)this, v20);
        LODWORD(v28) = v19;
        goto LABEL_44;
      }
      goto LABEL_35;
    }
LABEL_42:
    v19 = SLODWORD(this[156].Ptr) < 0 ? 0x88760870 : 0;
    goto LABEL_43;
  }
  if ( v20 != -1071775733 )
  {
    if ( v20 != -1071775744 && (unsigned int)(v20 + 1071775739) > 2 )
      goto LABEL_40;
    goto LABEL_42;
  }
LABEL_35:
  v19 = 0;
LABEL_43:
  LODWORD(v28) = v19;
LABEL_44:
  if ( BYTE2(this[112].Ptr) )
  {
    Ptr = this[176].Ptr;
    if ( Ptr )
      *Ptr = v28;
  }
  else
  {
    AcquireSRWLockShared(this + 167);
    CurrentThreadId = GetCurrentThreadId();
    v22 = (PVOID *)std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::find(
                     &this[168],
                     &v30,
                     &CurrentThreadId);
    v8 = (unsigned __int64)*v22;
    if ( *v22 != this[169].Ptr )
    {
      v8 = *(_QWORD *)(v8 + 24);
      *(_QWORD *)v8 = v28;
    }
    if ( this != (RTL_SRWLOCK *)-1336LL )
      ReleaseSRWLockShared(this + 167);
    v7 = v29;
  }
  if ( v19 == -2005532132 || v19 == -2005530512 )
    v19 = 0;
LABEL_55:
  LOBYTE(v8) = 9;
  if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(v7->Ptr, v8, 4) )
    NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(v13, (ULONG_PTR)a4);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800b6514  push    rsi
0x1800b6516  push    rdi
0x1800b6517  push    r12
0x1800b6519  push    r13
0x1800b651b  push    r15
0x1800b651d  sub     rsp, 190h
0x1800b6524  mov     rax, cs:__security_cookie
0x1800b652b  xor     rax, rsp
0x1800b652e  mov     [rsp+1B8h+var_38], rax
0x1800b6536  mov     r12, r9
0x1800b6539  mov     edi, r8d
0x1800b653c  mov     r11, rdx
0x1800b653f  mov     [rsp+1B8h+var_170], rdx
0x1800b6544  mov     rsi, rcx
0x1800b6547  mov     [rsp+1B8h+var_168], r9
0x1800b654c  mov     [rsp+1B8h+var_180], 0
0x1800b6555  mov     [rsp+1B8h+var_150], rcx
0x1800b655a  mov     [rsp+1B8h+var_148], r9
0x1800b655f  lea     r13, [rcx+48h]
0x1800b6563  mov     [rsp+1B8h+var_178], r13
0x1800b6568  mov     r8d, 4
0x1800b656e  mov     dl, 9
0x1800b6570  mov     rcx, [r13+0]
0x1800b6574  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800b6579  test    al, al
0x1800b657b  jz      loc_1800B6605
0x1800b6581  lea     r15, [rsi+780h]
0x1800b6588  mov     [rsp+1B8h+var_160], r15
0x1800b658d  mov     rdx, r9
0x1800b6590  mov     rcx, r15; lpCriticalSection
0x1800b6593  call    ??$GetDataFromToken@V_lambda_005e3fab6570a2faca41cdd9726fee38_@@@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAA?A_PPEAX$$QEAV_lambda_005e3fab6570a2faca41cdd9726fee38_@@@Z
0x1800b6598  mov     r8, rax
0x1800b659b  mov     r11, [rsp+1B8h+var_170]
0x1800b65a0  jmp     short loc_1800B660F
0x1800b65a2  mov     r8d, 4
0x1800b65a8  mov     dl, 9
0x1800b65aa  mov     rcx, [rsp+1B8h+var_178]
0x1800b65af  mov     rcx, [rcx]
0x1800b65b2  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800b65b7  test    al, al
0x1800b65b9  jz      short loc_1800B65CA
0x1800b65bb  mov     rdx, [rsp+1B8h+var_168]
0x1800b65c0  mov     rcx, [rsp+1B8h+var_160]
0x1800b65c5  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800b65ca  mov     eax, [rsp+1B8h+var_184]
0x1800b65ce  jmp     loc_1800B688C
0x1800b65d3  mov     r8d, 4
0x1800b65d9  mov     dl, 9
0x1800b65db  mov     rcx, [rsp+1B8h+var_178]
0x1800b65e0  mov     rcx, [rcx]
0x1800b65e3  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800b65e8  test    al, al
0x1800b65ea  jz      short loc_1800B65FB
0x1800b65ec  mov     rdx, [rsp+1B8h+var_168]
0x1800b65f1  mov     rcx, [rsp+1B8h+var_160]
0x1800b65f6  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800b65fb  mov     eax, 8007000Eh
0x1800b6600  jmp     loc_1800B688C
0x1800b6605  mov     r8, r12
0x1800b6608  lea     r15, [rsi+780h]
0x1800b660f  cmp     edi, [r8+1Ch]
0x1800b6613  jnz     loc_1800B6702
0x1800b6619  lea     rax, [rsp+1B8h+var_138]
0x1800b6621  mov     [r8+8], rax
0x1800b6625  mov     dword ptr [r8+4], 0
0x1800b662d  mov     dil, 1
0x1800b6630  mov     [rsp+1B8h+var_188], dil
0x1800b6635  xor     edx, edx
0x1800b6637  mov     [rsp+1B8h+var_184], edx
0x1800b663b  cmp     [r8+1Ch], edx
0x1800b663f  jbe     loc_1800B672C
0x1800b6645  mov     rax, [r8+20h]
0x1800b6649  mov     r10, [rax+rdx*8]
0x1800b664d  mov     r9, [r11+rdx*8]
0x1800b6651  test    byte ptr [r10+4], 1
0x1800b6656  jz      short loc_1800B66CC
0x1800b6658  cmp     dword ptr [r9], 40h ; '@'
0x1800b665c  ja      loc_1800B6702
0x1800b6662  mov     rax, [r9+10h]
0x1800b6666  mov     [r10+18h], rax
0x1800b666a  mov     eax, [r9]
0x1800b666d  mov     [r10+10h], eax
0x1800b6671  test    dil, dil
0x1800b6674  jz      short loc_1800B66B0
0x1800b6676  mov     [rsp+1B8h+var_188], 0
0x1800b667b  xor     r11d, r11d
0x1800b667e  mov     eax, [r9]
0x1800b6681  test    eax, eax
0x1800b6683  jz      short loc_1800B66A7
0x1800b6685  mov     rax, [r9+8]
0x1800b6689  mov     rcx, [rax+r11*8]; struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT *
0x1800b668d  mov     eax, [rcx+8]
0x1800b6690  mov     [rsp+r11*4+1B8h+var_138], eax
0x1800b6698  inc     r11d
0x1800b669b  mov     eax, [r9]
0x1800b669e  cmp     r11d, eax
0x1800b66a1  jb      short loc_1800B6685
0x1800b66a3  mov     edx, [rsp+1B8h+var_184]
0x1800b66a7  mov     [r8+4], eax
0x1800b66ab  mov     r11, [rsp+1B8h+var_170]
0x1800b66b0  test    byte ptr [r8+18h], 40h
0x1800b66b5  jnz     short loc_1800B66DC
0x1800b66b7  call    ?D3DKMTWaitForSynchronizationObject@@YAJPEAU_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT@@@Z; D3DKMTWaitForSynchronizationObject(_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT *)
0x1800b66bc  mov     edi, eax
0x1800b66be  mov     dword ptr [rsp+1B8h+var_180], eax
0x1800b66c2  test    eax, eax
0x1800b66c4  js      loc_1800B686A
0x1800b66ca  jmp     short loc_1800B66DC
0x1800b66cc  mov     qword ptr [r10+18h], 0
0x1800b66d4  mov     dword ptr [r10+10h], 0
0x1800b66dc  mov     eax, [r9+18h]
0x1800b66e0  mov     [r10+20h], eax
0x1800b66e4  mov     rax, [r9+20h]
0x1800b66e8  mov     [r10+28h], rax
0x1800b66ec  inc     edx
0x1800b66ee  mov     [rsp+1B8h+var_184], edx
0x1800b66f2  cmp     edx, [r8+1Ch]
0x1800b66f6  jnb     short loc_1800B672C
0x1800b66f8  mov     dil, [rsp+1B8h+var_188]
0x1800b66fd  jmp     loc_1800B6645
0x1800b6702  mov     r8d, 4
0x1800b6708  mov     dl, 9
0x1800b670a  mov     rcx, [r13+0]
0x1800b670e  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800b6713  test    al, al
0x1800b6715  jz      short loc_1800B6722
0x1800b6717  mov     rdx, r12
0x1800b671a  mov     rcx, r15
0x1800b671d  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800b6722  mov     eax, 80070057h
0x1800b6727  jmp     loc_1800B688C
0x1800b672c  cmp     dword ptr [r8+4], 0
0x1800b6731  jnz     short loc_1800B674F
0x1800b6733  mov     dword ptr [r8+4], 1
0x1800b673b  mov     rax, [r11]
0x1800b673e  mov     rcx, [rax+8]
0x1800b6742  mov     rax, [rcx]
0x1800b6745  mov     ecx, [rax+8]
0x1800b6748  mov     [rsp+1B8h+var_138], ecx
0x1800b674f  lea     rdx, aPresentmultipl_0; "PresentMultiplaneOverlay3"
0x1800b6756  mov     rcx, cs:__imp_D3DKMTPresentMultiPlaneOverlay3
0x1800b675d  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT@@@ZPEBDPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),char const *,_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *)
0x1800b6762  mov     edx, eax; int
0x1800b6764  mov     dword ptr [rsp+1B8h+var_180+4], eax
0x1800b6768  mov     eax, 0C01E000Bh
0x1800b676d  cmp     edx, eax
0x1800b676f  jg      short loc_1800B678C
0x1800b6771  jz      short loc_1800B6788
0x1800b6773  cmp     edx, 0C01E0000h
0x1800b6779  jz      short loc_1800B67C7
0x1800b677b  lea     eax, [rdx+3FE1FFFBh]
0x1800b6781  cmp     eax, 2
0x1800b6784  jbe     short loc_1800B67C7
0x1800b6786  jmp     short loc_1800B67AF
0x1800b6788  xor     edi, edi
0x1800b678a  jmp     short loc_1800B67DA
0x1800b678c  cmp     edx, 0C01E000Dh
0x1800b6792  jz      short loc_1800B67BF
0x1800b6794  lea     eax, [rdx+3FE1FFE8h]
0x1800b679a  cmp     eax, 1
0x1800b679d  jbe     short loc_1800B67C7
0x1800b679f  cmp     edx, 0C01E0342h
0x1800b67a5  jz      short loc_1800B67C7
0x1800b67a7  cmp     edx, 103h
0x1800b67ad  jz      short loc_1800B6788
0x1800b67af  mov     rcx, rsi; this
0x1800b67b2  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x1800b67b7  mov     edi, eax
0x1800b67b9  mov     dword ptr [rsp+1B8h+var_180], eax
0x1800b67bd  jmp     short loc_1800B67DE
0x1800b67bf  mov     dword ptr [rsp+1B8h+var_180+4], 0
0x1800b67c7  mov     eax, [rsi+4E0h]
0x1800b67cd  shr     eax, 1Fh
0x1800b67d0  neg     al
0x1800b67d2  sbb     edi, edi
0x1800b67d4  and     edi, 88760870h
0x1800b67da  mov     dword ptr [rsp+1B8h+var_180], edi
0x1800b67de  cmp     byte ptr [rsi+382h], 0
0x1800b67e5  jz      short loc_1800B67FD
0x1800b67e7  mov     rcx, [rsi+580h]
0x1800b67ee  test    rcx, rcx
0x1800b67f1  jz      short loc_1800B6858
0x1800b67f3  mov     rax, [rsp+1B8h+var_180]
0x1800b67f8  mov     [rcx], rax
0x1800b67fb  jmp     short loc_1800B6858
0x1800b67fd  lea     r13, [rsi+538h]
0x1800b6804  mov     rcx, r13; SRWLock
0x1800b6807  call    cs:__imp_AcquireSRWLockShared
0x1800b680d  call    cs:__imp_GetCurrentThreadId
0x1800b6813  mov     [rsp+1B8h+var_184], eax
0x1800b6817  lea     rcx, [rsi+540h]
0x1800b681e  lea     r8, [rsp+1B8h+var_184]
0x1800b6823  lea     rdx, [rsp+1B8h+var_170]
0x1800b6828  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::find(ulong const &)
0x1800b682d  mov     rdx, [rax]
0x1800b6830  cmp     rdx, [rsi+548h]
0x1800b6837  jz      short loc_1800B6845
0x1800b6839  mov     rdx, [rdx+18h]
0x1800b683d  mov     rax, [rsp+1B8h+var_180]
0x1800b6842  mov     [rdx], rax
0x1800b6845  test    r13, r13
0x1800b6848  jz      short loc_1800B6853
0x1800b684a  mov     rcx, r13; SRWLock
0x1800b684d  call    cs:__imp_ReleaseSRWLockShared
0x1800b6853  mov     r13, [rsp+1B8h+var_178]
0x1800b6858  cmp     edi, 8876021Ch
0x1800b685e  jz      short loc_1800B6868
0x1800b6860  cmp     edi, 88760870h
0x1800b6866  jnz     short loc_1800B686A
0x1800b6868  xor     edi, edi
0x1800b686a  mov     r8d, 4
0x1800b6870  mov     dl, 9
0x1800b6872  mov     rcx, [r13+0]
0x1800b6876  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800b687b  test    al, al
0x1800b687d  jz      short loc_1800B688A
0x1800b687f  mov     rdx, r12
0x1800b6882  mov     rcx, r15
0x1800b6885  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::FreeToken(void *)
0x1800b688a  mov     eax, edi
0x1800b688c  mov     rcx, [rsp+1B8h+var_38]
0x1800b6894  xor     rcx, rsp; StackCookie
0x1800b6897  call    __security_check_cookie
0x1800b689c  add     rsp, 190h
0x1800b68a3  pop     r15
0x1800b68a5  pop     r13
0x1800b68a7  pop     r12
0x1800b68a9  pop     rdi
0x1800b68aa  pop     rsi
0x1800b68ab  retn
```
