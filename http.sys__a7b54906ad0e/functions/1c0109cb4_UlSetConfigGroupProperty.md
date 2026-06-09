# UlSetConfigGroupProperty

- ea: `0x1c0109cb4`
- end: `0x1c010a3fd`
- name: `UlSetConfigGroupProperty`
- size: `1865`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c011d210`

## callees

- `0x1c00035ac`
- `0x1c0003974`
- `0x1c000b7cc`
- `0x1c001a4b0`
- `0x1c001addc`
- `0x1c001b900`
- `0x1c00295a4`
- `0x1c00325a8`
- `0x1c008f374`
- `0x1c008f3a8`
- `0x1c0093b84`
- `0x1c009416c`
- `0x1c00a17c0`
- `0x1c00a859c`
- `0x1c00a93f4`
- `0x1c00b0160`
- `0x1c0101848`
- `0x1c0109cb4`
- `0x1c010b338`
- `0x1c010bc14`
- `0x1c010d304`
- `0x1c01168d4`
- `0x1c0118f80`
- `0x1c0138aa4`
- `0x1c013a348`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1c0109e44`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010a11b`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010a26a`
- `ntoskrnl!IoIs32bitProcess` at `0x1c0109e44`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010a11b`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010a26a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0109fa2`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0109fa2`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0109d85`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0109d85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0109fae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0109fae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0109d72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0109d72`

## pseudocode

```c
__int64 __fastcall UlSetConfigGroupProperty(IRP *a1, __int64 a2, __int64 a3, int a4, __m128i *a5, int a6)
{
  int v8; // esi
  void *v9; // r13
  char v10; // r12
  __int64 v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 ObjectFromOpaqueId; // rax
  unsigned __int64 Flink_low; // rcx
  __int64 v17; // r14
  int v18; // edi
  unsigned int v19; // ebx
  int v20; // eax
  int v21; // r8d
  __int64 v22; // rax
  __m128i v24; // xmm0
  int v25; // eax
  BOOLEAN v26; // al
  __int8 v27; // r8
  __int8 v28; // r9
  __int8 v29; // r10
  int v30; // edi
  __int32 v31; // edx
  __int8 v32; // cl
  __int16 v33; // ax
  __int8 v34; // al
  __int64 v35; // r15
  HANDLE v36; // rcx
  int v37; // ebx
  struct _RTL_AVL_TABLE *v38; // rcx
  int v39; // eax
  __int64 v40; // rax
  unsigned __int64 v41; // rdx
  int started; // eax
  __int64 v43; // rax
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+28h] [rbp-D8h]
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v51[5]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle[2]; // [rsp+C0h] [rbp-40h]
  HANDLE v53[2]; // [rsp+D0h] [rbp-30h]
  __m128i v54; // [rsp+E0h] [rbp-20h]
  __int32 v55; // [rsp+F0h] [rbp-10h]
  __int128 v56; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v57; // [rsp+108h] [rbp+8h]
  char v58; // [rsp+110h] [rbp+10h]
  int v59; // [rsp+111h] [rbp+11h]
  __int16 v60; // [rsp+115h] [rbp+15h]
  char v61; // [rsp+117h] [rbp+17h]
  __int64 v62; // [rsp+118h] [rbp+18h] BYREF
  int v63; // [rsp+120h] [rbp+20h]

  v49 = 0;
  v8 = 0;
  v50 = 0;
  v9 = 0;
  v10 = 1;
  v62 = 0;
  v63 = 0;
  memset(v51, 0, sizeof(v51));
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
  {
    v45 = a4;
    v12 = a2;
    WPP_SF_qqiLqL(138, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, a1, a2, a3, v45, a5, a6);
  }
  else
  {
    v12 = a2;
  }
  v13 = *(_QWORD *)(v12 + 56);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v13 + 1360));
  v14 = a2;
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         a3,
                         2,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateConfigGroup,
                         a2);
  Flink_low = 0;
  v17 = ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId || *(_DWORD *)ObjectFromOpaqueId != 1245932629 )
  {
    v8 = -1073741811;
    goto LABEL_39;
  }
  v18 = *(_DWORD *)(*(_QWORD *)(ObjectFromOpaqueId + 48) + 16LL);
  if ( v18 != 1 )
  {
    v19 = a4;
    if ( a4 <= 8 )
    {
      if ( a4 == 8 || !a4 )
      {
        v26 = IoIs32bitProcess(a1);
        v27 = a5->m128i_i8[8];
        v28 = a5->m128i_i8[9];
        v29 = a5->m128i_i8[10];
        v30 = a5->m128i_i32[0];
        v31 = a5->m128i_i32[1];
        v32 = a5->m128i_i8[11];
        LODWORD(v51[0]) = a5->m128i_i32[0];
        DWORD1(v51[0]) = v31;
        BYTE8(v51[0]) = v27;
        BYTE9(v51[0]) = v28;
        BYTE10(v51[0]) = v29;
        if ( v26 )
        {
          *((_QWORD *)&v51[2] + 1) = a5[1].m128i_u32[2];
          LOWORD(v51[2]) = a5[1].m128i_i16[2];
          *((_QWORD *)&v51[1] + 1) = a5[1].m128i_u32[0];
          LOWORD(v51[1]) = a5->m128i_i16[6];
          *((_QWORD *)&v51[3] + 1) = a5[2].m128i_u32[0];
          v33 = a5[1].m128i_i16[6];
        }
        else
        {
          *((_QWORD *)&v51[2] + 1) = a5[2].m128i_i64[1];
          LOWORD(v51[2]) = a5[2].m128i_i16[0];
          *((_QWORD *)&v51[1] + 1) = a5[1].m128i_i64[1];
          LOWORD(v51[1]) = a5[1].m128i_i16[0];
          *((_QWORD *)&v51[3] + 1) = a5[3].m128i_i64[1];
          v33 = a5[3].m128i_i16[0];
        }
        LOWORD(v51[3]) = v33;
        v34 = v32;
        v51[4] = 0;
        if ( a4 != 8 )
          v34 = 0;
        BYTE11(v51[0]) = v34;
        v35 = *(_QWORD *)(a2 + 56);
        v8 = UlVerifyAuthConfig(v35, v51);
        if ( v8 < 0 )
          goto LABEL_30;
        if ( (v30 & 1) == 0 )
        {
          UlFreeAuthConfig(v17 + 304);
          goto LABEL_30;
        }
        v25 = UlCopyAuthConfig(v35, (int)v17 + 304, (unsigned int)v51, 0, a1->RequestorMode);
        goto LABEL_61;
      }
      if ( a4 == 1 )
      {
        v8 = UlConfigLogging(ObjectFromOpaqueId + 120, ObjectFromOpaqueId, a5->m128i_i32, a1);
        goto LABEL_31;
      }
      if ( a4 != 2 )
      {
        switch ( a4 )
        {
          case 3:
            v24 = *a5;
            Flink_low = a5[1].m128i_u32[0];
            v55 = a5[1].m128i_i32[0];
            v54 = v24;
            if ( (_mm_cvtsi128_si32(v24) & 1) != 0 )
            {
              *(__m128i *)(ObjectFromOpaqueId + 272) = v24;
              *(_DWORD *)(ObjectFromOpaqueId + 288) = Flink_low;
            }
            else
            {
              *(_OWORD *)(ObjectFromOpaqueId + 272) = 0;
              *(_DWORD *)(ObjectFromOpaqueId + 288) = 0;
            }
            goto LABEL_31;
          case 5:
            Flink_low = HIDWORD(a5->m128i_i64[0]);
            if ( (unsigned int)Flink_low <= 1 )
            {
              if ( *(_DWORD *)(ObjectFromOpaqueId + 60) == (_DWORD)Flink_low )
                v10 = 0;
              else
                *(_QWORD *)(ObjectFromOpaqueId + 56) = a5->m128i_i64[0];
              goto LABEL_31;
            }
            break;
          case 7:
            if ( IoIs32bitProcess(a1) )
            {
              Flink_low = a5->m128i_u32[1];
              v20 = a5->m128i_i32[0];
              Handle[1] = (HANDLE)Flink_low;
              LODWORD(Handle[0]) = v20;
            }
            else
            {
              *(__m128i *)Handle = *a5;
              Flink_low = (unsigned __int64)Handle[1];
              LOBYTE(v20) = Handle[0];
            }
            v21 = *(_DWORD *)(v17 + 64);
            if ( (v21 & 1) != 0 && *(_QWORD *)(v17 + 72) )
              v9 = *(void **)(v17 + 72);
            if ( (v20 & 1) == 0 )
            {
              *(_QWORD *)(v17 + 72) = 0;
              *(_DWORD *)(v17 + 64) = v21 & 0xFFFFFFFE;
LABEL_46:
              if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
                UlFreeRequestQueue(v9);
              goto LABEL_30;
            }
            v8 = UlReferenceRequestQueueByHandle((HANDLE)Flink_low);
            if ( v8 >= 0 )
            {
              if ( MEMORY[0x114] != (_WORD)v18 || (Flink_low = HIWORD(v18), MEMORY[0x116] != HIWORD(v18)) )
              {
                if ( _InterlockedExchangeAdd(0, 0xFFFFFFFF) == 1 )
                  UlFreeRequestQueue(0);
                v8 = -1073741735;
                goto LABEL_30;
              }
              *(_DWORD *)(v17 + 64) |= 1u;
              *(_QWORD *)(v17 + 72) = 0;
              goto LABEL_46;
            }
LABEL_30:
            v19 = a4;
LABEL_31:
            v22 = *(_QWORD *)(a2 + 56);
            if ( *(_BYTE *)(v22 + 1568) )
            {
              v59 = 0;
              v60 = 0;
              v61 = 0;
              v57 = v22;
              v56 = 0;
              v58 = 0;
              McTemplateK0qq_UlEtwWriteEventWrapper(Flink_low, HTTP_EVENT_SET_URL_GROUP_PROPERTY, &v56, v19, v8);
            }
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
              WPP_SF_DD(140, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, (unsigned int)v8, v19);
            if ( v8 >= 0 && v10 )
              UlFlushCacheByConfigGroup(v17);
            goto LABEL_38;
        }
LABEL_93:
        v8 = -1073741811;
        goto LABEL_31;
      }
      v8 = UlCaptureQosParameter(a1);
      if ( v8 >= 0 )
      {
        if ( !(_DWORD)v62 )
        {
          v25 = UlQosConfigureFlowCharacteristics(v17 + 80, (char *)&v62 + 4);
          goto LABEL_61;
        }
        if ( (_DWORD)v62 == 1 )
        {
          v25 = UlSetConnectionsProperty(v17, (char *)&v62 + 4);
          goto LABEL_61;
        }
        v8 = -1073741811;
      }
LABEL_38:
      v14 = a2;
      goto LABEL_39;
    }
    Flink_low = (unsigned int)(a4 - 9);
    if ( a4 == 9 )
    {
      v43 = a5->m128i_i64[0];
      if ( (a5->m128i_i64[0] & 1) == 0 )
        v43 = 0;
      *(_QWORD *)(v17 + 292) = v43;
      goto LABEL_31;
    }
    if ( a4 != 10 )
    {
      if ( a4 == 11 )
      {
        v50 = a5->m128i_i64[0];
        started = UlpNotifyEdgePolicyChange(ObjectFromOpaqueId, &v50);
      }
      else
      {
        if ( a4 != 12 )
        {
          Flink_low = (unsigned int)(a4 - 15);
          if ( a4 == 15 )
          {
            v40 = a5->m128i_i64[0];
            v41 = HIDWORD(a5->m128i_i64[0]);
            if ( (unsigned __int8)v41 < 2u )
            {
              *(_QWORD *)(v17 + 448) = v40;
              Flink_low = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
              if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
                WPP_SF_ill((unsigned __int8)v41, v41, *(_QWORD *)(v17 + 8), v40 & 1, (unsigned __int8)v41);
              goto LABEL_31;
            }
          }
          else if ( a4 == 16 )
          {
            if ( IoIs32bitProcess(a1) )
            {
              v36 = (HANDLE)a5->m128i_u32[1];
              v37 = a5->m128i_i32[0];
              v53[1] = v36;
              LODWORD(v53[0]) = v37;
            }
            else
            {
              *(__m128i *)v53 = *a5;
              v36 = v53[1];
              LOBYTE(v37) = v53[0];
            }
            v8 = UlReferenceRequestQueueByHandle(v36);
            if ( v8 >= 0 )
            {
              if ( MEMORY[0x114] == v18 )
              {
                v38 = (struct _RTL_AVL_TABLE *)(v17 + 456);
                if ( (v37 & 1) != 0 )
                  v39 = UxpAddDelegateQueueToTable(v38);
                else
                  v39 = UxpRemoveDelegateQueueFromTable(v38, 0);
                v8 = v39;
                Flink_low = (unsigned int)_InterlockedExchangeAdd(0, 0xFFFFFFFF);
                if ( (_DWORD)Flink_low == 1 )
                  UlFreeRequestQueue(0);
              }
              else
              {
                if ( _InterlockedExchangeAdd(0, 0xFFFFFFFF) == 1 )
                  UlFreeRequestQueue(0);
                v8 = -1073741735;
              }
            }
            goto LABEL_30;
          }
          goto LABEL_93;
        }
        v49 = a5->m128i_i64[0];
        started = UlScStartCounters(ObjectFromOpaqueId, &v49);
      }
      v8 = started;
      goto LABEL_31;
    }
    LOBYTE(v44) = a1->RequestorMode;
    v25 = UlCaptureChannelBindConfig(*(_QWORD *)(a2 + 56), a5, ObjectFromOpaqueId + 384, a1, v44);
LABEL_61:
    v8 = v25;
    goto LABEL_30;
  }
  v8 = -1073741637;
LABEL_39:
  v62 = 0;
  v63 = 0;
  if ( v17 && _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 4), 0xFFFFFFFF) == 1 )
    UlFreeConfigGroup((PVOID)v17);
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(v14 + 56) + 1360LL));
  KeLeaveCriticalRegion();
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_D(141, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1c0109cb4  push    rbp
0x1c0109cb6  push    rbx
0x1c0109cb7  push    rsi
0x1c0109cb8  push    rdi
0x1c0109cb9  push    r12
0x1c0109cbb  push    r13
0x1c0109cbd  push    r14
0x1c0109cbf  push    r15
0x1c0109cc1  lea     rbp, [rsp-38h]
0x1c0109cc6  sub     rsp, 138h
0x1c0109ccd  mov     rax, cs:__security_cookie
0x1c0109cd4  xor     rax, rsp
0x1c0109cd7  mov     [rbp+70h+var_48], rax
0x1c0109cdb  mov     r15, [rbp+70h+arg_20]
0x1c0109ce2  mov     rbx, rcx
0x1c0109ce5  mov     [rsp+170h+Irp], rcx
0x1c0109cea  xor     eax, eax
0x1c0109cec  xor     ecx, ecx
0x1c0109cee  mov     [rsp+170h+var_120], rdx
0x1c0109cf3  mov     rdi, r8
0x1c0109cf6  mov     [rsp+170h+var_110], rcx
0x1c0109cfb  mov     esi, ecx
0x1c0109cfd  mov     [rsp+170h+var_108], rcx
0x1c0109d02  mov     r13d, ecx
0x1c0109d05  mov     [rsp+170h+var_130], r9d
0x1c0109d0a  lea     r12d, [rcx+1]
0x1c0109d0e  mov     [rbp+70h+var_58], rax
0x1c0109d12  lea     r8d, [rcx+50h]; Size
0x1c0109d16  mov     [rbp+70h+var_50], eax
0x1c0109d19  lea     rcx, [rsp+170h+var_100]; void *
0x1c0109d1e  xor     edx, edx; Val
0x1c0109d20  mov     r14d, r9d
0x1c0109d23  call    memset
0x1c0109d28  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109d2e  test    al, 8
0x1c0109d30  jz      short loc_1C0109D69
0x1c0109d32  mov     eax, [rbp+70h+arg_28]
0x1c0109d38  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109d3f  mov     [rsp+170h+var_138], eax
0x1c0109d43  mov     ecx, 8Ah
0x1c0109d48  mov     [rsp+170h+var_140], r15
0x1c0109d4d  mov     r8, rbx
0x1c0109d50  mov     [rsp+170h+var_148], r14d
0x1c0109d55  mov     r14, [rsp+170h+var_120]
0x1c0109d5a  mov     r9, r14
0x1c0109d5d  mov     [rsp+170h+var_150], rdi
0x1c0109d62  call    WPP_SF_qqiLqL
0x1c0109d67  jmp     short loc_1C0109D6E
0x1c0109d69  mov     r14, [rsp+170h+var_120]
0x1c0109d6e  mov     rbx, [r14+38h]
0x1c0109d72  call    cs:__imp_KeEnterCriticalRegion
0x1c0109d79  nop     dword ptr [rax+rax+00h]
0x1c0109d7e  mov     rcx, [rbx+550h]
0x1c0109d85  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0109d8c  nop     dword ptr [rax+rax+00h]
0x1c0109d91  mov     rbx, [rsp+170h+var_120]
0x1c0109d96  lea     r9, UlValidateConfigGroup
0x1c0109d9d  lea     r8, UlReferenceServerSession
0x1c0109da4  mov     [rsp+170h+var_150], rbx
0x1c0109da9  mov     edx, 2
0x1c0109dae  mov     rcx, rdi
0x1c0109db1  call    UxGetObjectFromOpaqueId
0x1c0109db6  xor     ecx, ecx
0x1c0109db8  mov     r14, rax
0x1c0109dbb  test    rax, rax
0x1c0109dbe  jz      loc_1C010A3F3
0x1c0109dc4  cmp     dword ptr [rax], 4A436C55h
0x1c0109dca  jnz     loc_1C010A3F3
0x1c0109dd0  mov     rax, [rax+30h]
0x1c0109dd4  mov     edi, [rax+10h]
0x1c0109dd7  mov     [rsp+170h+var_12C], edi
0x1c0109ddb  cmp     r12w, di
0x1c0109ddf  jnz     short loc_1C0109DF5
0x1c0109de1  mov     eax, edi
0x1c0109de3  shr     eax, 10h
0x1c0109de6  cmp     cx, ax
0x1c0109de9  jnz     short loc_1C0109DF5
0x1c0109deb  mov     esi, 0C00000BBh
0x1c0109df0  jmp     loc_1C0109F73
0x1c0109df5  mov     ebx, [rsp+170h+var_130]
0x1c0109df9  cmp     ebx, 8
0x1c0109dfc  jg      loc_1C010A22D
0x1c0109e02  jz      loc_1C010A113
0x1c0109e08  mov     edx, ebx
0x1c0109e0a  test    ebx, ebx
0x1c0109e0c  jz      loc_1C010A113
0x1c0109e12  sub     edx, r12d
0x1c0109e15  jz      loc_1C010A0F8
0x1c0109e1b  sub     edx, r12d
0x1c0109e1e  jz      loc_1C010A09E
0x1c0109e24  sub     edx, r12d
0x1c0109e27  jz      loc_1C010A059
0x1c0109e2d  sub     edx, 2
0x1c0109e30  jz      loc_1C010A02F
0x1c0109e36  cmp     edx, 2
0x1c0109e39  jnz     loc_1C010A341
0x1c0109e3f  mov     rcx, [rsp+170h+Irp]; Irp
0x1c0109e44  call    cs:__imp_IoIs32bitProcess
0x1c0109e4b  nop     dword ptr [rax+rax+00h]
0x1c0109e50  xor     ebx, ebx
0x1c0109e52  test    al, al
0x1c0109e54  jz      short loc_1C0109E66
0x1c0109e56  mov     ecx, [r15+4]
0x1c0109e5a  mov     eax, [r15]
0x1c0109e5d  mov     [rbp+70h+Handle+8], rcx
0x1c0109e61  mov     dword ptr [rbp+70h+Handle], eax
0x1c0109e64  jmp     short loc_1C0109E76
0x1c0109e66  movups  xmm0, xmmword ptr [r15]
0x1c0109e6a  movdqu  xmmword ptr [rbp+70h+Handle], xmm0
0x1c0109e6f  mov     rcx, [rbp+70h+Handle+8]; Handle
0x1c0109e73  mov     eax, dword ptr [rbp+70h+Handle]
0x1c0109e76  mov     r8d, [r14+40h]
0x1c0109e7a  test    r12b, r8b
0x1c0109e7d  jz      short loc_1C0109E8A
0x1c0109e7f  mov     rdx, [r14+48h]
0x1c0109e83  test    rdx, rdx
0x1c0109e86  cmovnz  r13, rdx
0x1c0109e8a  test    r12b, al
0x1c0109e8d  jz      loc_1C0109FFB
0x1c0109e93  lea     r9, [rsp+170h+P]
0x1c0109e98  mov     [rsp+170h+P], rbx
0x1c0109e9d  mov     r8d, r12d
0x1c0109ea0  call    UlReferenceRequestQueueByHandle
0x1c0109ea5  mov     esi, eax
0x1c0109ea7  test    eax, eax
0x1c0109ea9  js      short loc_1C0109EEF
0x1c0109eab  mov     rdx, [rsp+170h+P]
0x1c0109eb0  cmp     [rdx+114h], di
0x1c0109eb7  jnz     short loc_1C0109ED4
0x1c0109eb9  movzx   ecx, word ptr [rsp+170h+var_12C+2]
0x1c0109ebe  cmp     [rdx+116h], cx
0x1c0109ec5  jnz     short loc_1C0109ED4
0x1c0109ec7  or      [r14+40h], r12d
0x1c0109ecb  mov     [r14+48h], rdx
0x1c0109ecf  jmp     loc_1C010A007
0x1c0109ed4  or      eax, 0FFFFFFFFh
0x1c0109ed7  lock xadd [rdx], eax
0x1c0109edb  cmp     eax, r12d
0x1c0109ede  jnz     short loc_1C0109EEA
0x1c0109ee0  mov     rcx, [rsp+170h+P]; P
0x1c0109ee5  call    UlFreeRequestQueue
0x1c0109eea  mov     esi, 0C0000059h
0x1c0109eef  xor     r13d, r13d
0x1c0109ef2  mov     ebx, [rsp+170h+var_130]
0x1c0109ef6  mov     rax, [rsp+170h+var_120]
0x1c0109efb  mov     rax, [rax+38h]
0x1c0109eff  cmp     [rax+620h], r13b
0x1c0109f06  jz      short loc_1C0109F3C
0x1c0109f08  xorps   xmm0, xmm0
0x1c0109f0b  mov     [rbp+70h+var_5F], r13d
0x1c0109f0f  mov     r9d, ebx
0x1c0109f12  mov     [rbp+70h+var_5B], r13w
0x1c0109f17  lea     r8, [rbp+70h+var_78]
0x1c0109f1b  mov     [rbp+70h+var_59], r13b
0x1c0109f1f  lea     rdx, HTTP_EVENT_SET_URL_GROUP_PROPERTY
0x1c0109f26  mov     [rbp+70h+var_68], rax
0x1c0109f2a  movdqu  [rbp+70h+var_78], xmm0
0x1c0109f2f  mov     [rbp+70h+var_60], r13b
0x1c0109f33  mov     dword ptr [rsp+170h+var_150], esi
0x1c0109f37  call    McTemplateK0qq_UlEtwWriteEventWrapper
0x1c0109f3c  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109f42  test    al, 8
0x1c0109f44  jz      short loc_1C0109F5D
0x1c0109f46  mov     ecx, 8Ch
0x1c0109f4b  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109f52  mov     r9d, ebx
0x1c0109f55  mov     r8d, esi
0x1c0109f58  call    WPP_SF_DD
0x1c0109f5d  test    esi, esi
0x1c0109f5f  js      short loc_1C0109F6E
0x1c0109f61  test    r12b, r12b
0x1c0109f64  jz      short loc_1C0109F6E
0x1c0109f66  mov     rcx, r14
0x1c0109f69  call    UlFlushCacheByConfigGroup
0x1c0109f6e  mov     rbx, [rsp+170h+var_120]
0x1c0109f73  xor     eax, eax
0x1c0109f75  mov     [rbp+70h+var_58], rax
0x1c0109f79  mov     [rbp+70h+var_50], eax
0x1c0109f7c  test    r14, r14
0x1c0109f7f  jz      short loc_1C0109F97
0x1c0109f81  or      eax, 0FFFFFFFFh
0x1c0109f84  lock xadd [r14+4], eax
0x1c0109f8a  cmp     eax, 1
0x1c0109f8d  jnz     short loc_1C0109F97
0x1c0109f8f  mov     rcx, r14; P
0x1c0109f92  call    UlFreeConfigGroup
0x1c0109f97  mov     rcx, [rbx+38h]
0x1c0109f9b  mov     rcx, [rcx+550h]
0x1c0109fa2  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0109fa9  nop     dword ptr [rax+rax+00h]
0x1c0109fae  call    cs:__imp_KeLeaveCriticalRegion
0x1c0109fb5  nop     dword ptr [rax+rax+00h]
0x1c0109fba  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109fc0  test    al, 8
0x1c0109fc2  jz      short loc_1C0109FD8
0x1c0109fc4  mov     ecx, 8Dh
0x1c0109fc9  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109fd0  mov     r8d, esi
0x1c0109fd3  call    WPP_SF_D
0x1c0109fd8  mov     eax, esi
0x1c0109fda  mov     rcx, [rbp+70h+var_48]
0x1c0109fde  xor     rcx, rsp; StackCookie
0x1c0109fe1  call    __security_check_cookie
0x1c0109fe6  add     rsp, 138h
0x1c0109fed  pop     r15
0x1c0109fef  pop     r14
0x1c0109ff1  pop     r13
0x1c0109ff3  pop     r12
0x1c0109ff5  pop     rdi
0x1c0109ff6  pop     rsi
0x1c0109ff7  pop     rbx
0x1c0109ff8  pop     rbp
0x1c0109ff9  retn
0x1c0109ffb  and     r8d, 0FFFFFFFEh
0x1c0109fff  mov     [r14+48h], rbx
0x1c010a003  mov     [r14+40h], r8d
0x1c010a007  test    r13, r13
0x1c010a00a  jz      loc_1C0109EEF
0x1c010a010  or      eax, 0FFFFFFFFh
0x1c010a013  lock xadd [r13+0], eax
0x1c010a019  cmp     eax, r12d
0x1c010a01c  jnz     loc_1C0109EEF
0x1c010a022  mov     rcx, r13; P
0x1c010a025  call    UlFreeRequestQueue
0x1c010a02a  jmp     loc_1C0109EEF
0x1c010a02f  mov     rax, [r15]
0x1c010a032  mov     rcx, rax
0x1c010a035  shr     rcx, 20h
0x1c010a039  cmp     ecx, r12d
0x1c010a03c  ja      loc_1C010A341
0x1c010a042  cmp     [r14+3Ch], ecx
0x1c010a046  jz      short loc_1C010A051
0x1c010a048  mov     [r14+38h], rax
0x1c010a04c  jmp     loc_1C0109EF6
0x1c010a051  mov     r12b, r13b
0x1c010a054  jmp     loc_1C0109EF6
0x1c010a059  movups  xmm0, xmmword ptr [r15]
0x1c010a05d  mov     ecx, [r15+10h]
0x1c010a061  mov     [rbp+70h+var_80], ecx
0x1c010a064  movd    eax, xmm0
0x1c010a068  movups  [rbp+70h+var_90], xmm0
0x1c010a06c  test    r12b, al
0x1c010a06f  jz      short loc_1C010A085
0x1c010a071  movups  xmmword ptr [r14+110h], xmm0
0x1c010a079  mov     [r14+120h], ecx
0x1c010a080  jmp     loc_1C0109EF6
0x1c010a085  xorps   xmm0, xmm0
0x1c010a088  xor     eax, eax
0x1c010a08a  movups  xmmword ptr [r14+110h], xmm0
0x1c010a092  mov     [r14+120h], eax
0x1c010a099  jmp     loc_1C0109EF6
0x1c010a09e  mov     r8d, [rbp+70h+arg_28]
0x1c010a0a5  lea     r9, [rbp+70h+var_58]
0x1c010a0a9  mov     rcx, [rsp+170h+Irp]; Irp
0x1c010a0ae  mov     rdx, r15
0x1c010a0b1  call    UlCaptureQosParameter
0x1c010a0b6  mov     esi, eax
0x1c010a0b8  test    eax, eax
0x1c010a0ba  js      loc_1C0109F6E
0x1c010a0c0  mov     eax, dword ptr [rbp+70h+var_58]
0x1c010a0c3  test    eax, eax
0x1c010a0c5  jnz     short loc_1C010A0D6
0x1c010a0c7  lea     rcx, [r14+50h]
0x1c010a0cb  lea     rdx, [rbp+70h+var_58+4]
0x1c010a0cf  call    UlQosConfigureFlowCharacteristics
0x1c010a0d4  jmp     short loc_1C010A0E7
0x1c010a0d6  cmp     eax, r12d
0x1c010a0d9  jnz     short loc_1C010A0EE
0x1c010a0db  lea     rdx, [rbp+70h+var_58+4]
0x1c010a0df  mov     rcx, r14
0x1c010a0e2  call    UlSetConnectionsProperty
0x1c010a0e7  mov     esi, eax
0x1c010a0e9  jmp     loc_1C0109EF2
0x1c010a0ee  mov     esi, 0C000000Dh
0x1c010a0f3  jmp     loc_1C0109F6E
0x1c010a0f8  mov     r9, [rsp+170h+Irp]
0x1c010a0fd  lea     rcx, [r14+78h]
0x1c010a101  mov     r8, r15
0x1c010a104  mov     rdx, r14
0x1c010a107  call    UlConfigLogging
0x1c010a10c  mov     esi, eax
0x1c010a10e  jmp     loc_1C0109EF6
0x1c010a113  mov     rbx, [rsp+170h+Irp]
0x1c010a118  mov     rcx, rbx; Irp
0x1c010a11b  call    cs:__imp_IoIs32bitProcess
0x1c010a122  nop     dword ptr [rax+rax+00h]
0x1c010a127  mov     r8b, [r15+8]
0x1c010a12b  xor     r11d, r11d
0x1c010a12e  mov     r9b, [r15+9]
0x1c010a132  mov     r10b, [r15+0Ah]
0x1c010a136  mov     edi, [r15]
0x1c010a139  mov     edx, [r15+4]
0x1c010a13d  movzx   ecx, byte ptr [r15+0Bh]
0x1c010a142  mov     [rsp+170h+var_100], edi
0x1c010a146  mov     [rsp+170h+var_FC], edx
0x1c010a14a  mov     [rsp+170h+var_F8], r8b
0x1c010a14f  mov     [rsp+170h+var_F7], r9b
0x1c010a154  mov     [rsp+170h+var_F6], r10b
0x1c010a159  test    al, al
0x1c010a15b  jz      short loc_1C010A18E
  ... truncated ...
```
