# DeleteRTRMgrOwnedRoutesToDestFromStack

- ea: `0x1800010a0`
- end: `0x18000178f`
- name: `DeleteRTRMgrOwnedRoutesToDestFromStack`
- size: `1775`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bdbc`
- `0x1800229ec`
- `0x180045708`
- `0x18004b844`

## callees

- `0x1800010a0`
- `0x18000ac60`
- `0x18000f80c`
- `0x180011790`
- `0x180052dc4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18000120b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18000120b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180001219`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18000175f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180001219`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18000175f`
- `NSI!NsiAllocateAndGetTable` at `0x180001275`
- `NSI!NsiAllocateAndGetTable` at `0x180001275`
- `NSI!NsiGetParameter` at `0x1800011c0`
- `NSI!NsiGetParameter` at `0x1800011c0`
- `NSI!NsiFreeTable` at `0x180001753`
- `NSI!NsiFreeTable` at `0x180001753`

## string_xrefs

- `0x180001306`: `DeleteRTRMgrOwnedRoutesToDestFromStack: NsiGetRoutingDomainIdForCompartment failed with error %d`
- `0x1800016d9`: `DeleteRTRMgrOwnedRoutesToDestFromStack: SetCurrentThreadCompartmentId failed and returned %d`
- `0x180001290`: `DeleteRTRMgrOwnedRoutesToDestFromStack : error %d returned by NsiAllocateAndGetTable`
- `0x1800015c4`: `DeleteRTRMgrOwnedRoutesToDestFromStack : error %d returned by NsiAllocateAndGetTable`
- `0x1800013f9`: `DeleteRTRMgrOwnedRoutesToDestFromStack: Found , Address: %d.%d.%d.%d Mask: %d`
- `0x18000155e`: `DeleteRTRMgrOwnedRoutesToDestFromStack: Found, Address: %hs PrefixLength: %d `

## pseudocode

```c
__int64 __fastcall DeleteRTRMgrOwnedRoutesToDestFromStack(_BYTE *a1, int a2, NET_IF_COMPARTMENT_ID a3)
{
  int v5; // eax
  const NPI_MODULEID *v7; // rax
  int v8; // edi
  unsigned int Parameter; // edi
  unsigned int v10; // r13d
  int v11; // r14d
  NET_IF_COMPARTMENT_ID v12; // esi
  unsigned int v13; // eax
  unsigned int Table; // eax
  int v15; // ecx
  __int64 v16; // r8
  unsigned int v17; // ebx
  __int64 i; // rdi
  int v20; // ebx
  unsigned __int8 v21; // r9
  __int64 v22; // r10
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int128 v27; // xmm0
  unsigned int v28; // ebx
  __int64 Ipv6StringFromAddress; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+30h] [rbp-D0h]
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v37; // [rsp+80h] [rbp-80h]
  int v38; // [rsp+84h] [rbp-7Ch]
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  const NPI_MODULEID *v40; // [rsp+90h] [rbp-70h]
  __int128 v41; // [rsp+A0h] [rbp-60h] BYREF
  GUID v42; // [rsp+B0h] [rbp-50h] BYREF
  GUID v43; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v44[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v45[80]; // [rsp+110h] [rbp+10h] BYREF
  int v46; // [rsp+160h] [rbp+60h] BYREF
  __int128 v47; // [rsp+164h] [rbp+64h]
  __int128 v48; // [rsp+174h] [rbp+74h]
  int v49; // [rsp+184h] [rbp+84h]
  _BYTE v50[80]; // [rsp+190h] [rbp+90h] BYREF
  int v51; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v52[2044]; // [rsp+1E4h] [rbp+E4h] BYREF

  v36 = 0;
  v39 = 0;
  v37 = 0;
  v5 = 48;
  if ( !a2 )
    v5 = 72;
  v38 = v5;
  v7 = &NPI_MS_IPV4_MODULEID;
  if ( !a2 )
    v7 = &NPI_MS_IPV6_MODULEID;
  v40 = v7;
  memset(v44, 0, sizeof(v44));
  memset_0(v45, 0, 0x48u);
  v51 = 0;
  v42 = 0;
  memset_0(v52, 0, sizeof(v52));
  v46 = 0;
  v8 = 1;
  v49 = 0;
  v47 = 0;
  v48 = 0;
  if ( a3 == 1 || !gIsRtrMgrEtwEnabled )
    goto LABEL_10;
  CurrentThreadCompartmentId = a3;
  v43 = GUID_NULL;
  if ( a3 )
  {
    Parameter = NsiGetParameter(1, &NPI_MS_NDIS_MODULEID, 7, &CurrentThreadCompartmentId, 4, 0, &v43, 16, 1080);
    if ( !Parameter )
    {
      v42 = v43;
      v8 = 1;
LABEL_10:
      v10 = 0;
      v11 = 0;
      if ( !a1 )
      {
        a1 = v44;
        v11 = 1;
        if ( !a2 )
          a1 = v45;
      }
      CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
      v12 = CurrentThreadCompartmentId;
      v13 = SetCurrentThreadCompartmentId(a3);
      if ( v13 )
      {
        v8 = 0;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v51) = 0;
          LOWORD(v46) = 0;
          FormatRRASErrorString(
            &v51,
            L"DeleteRTRMgrOwnedRoutesToDestFromStack: SetCurrentThreadCompartmentId failed and returned %d",
            v13);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v51,
              (unsigned int)&v42,
              0,
              (__int64)&v46);
        }
        goto LABEL_61;
      }
      v34 = 32;
      Table = NsiAllocateAndGetTable(1, v40, 16, &v36, v38, &v39);
      v17 = Table;
      if ( Table )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v51) = 0;
          LOWORD(v46) = 0;
          FormatRRASErrorString(
            &v51,
            L"DeleteRTRMgrOwnedRoutesToDestFromStack : error %d returned by NsiAllocateAndGetTable",
            Table);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v51,
              (unsigned int)&v42,
              0,
              (__int64)&v46);
        }
        v10 = v17;
LABEL_61:
        if ( v36 )
          NsiFreeTable(v36, v39, 0, 0);
        if ( v8 )
          SetCurrentThreadCompartmentId(v12);
        return v10;
      }
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= v37 )
        {
          v12 = CurrentThreadCompartmentId;
          v8 = 1;
          goto LABEL_61;
        }
        if ( v11 )
          goto LABEL_45;
        if ( a2 )
        {
          v15 = v36;
          v20 = 0;
          if ( *((_DWORD *)a1 + 1) == *(_DWORD *)(v36 + 48 * i + 4) )
          {
            v16 = v36 + 48 * i;
            if ( a1[8] == *(_BYTE *)(v16 + 8) )
            {
              v20 = 1;
              *(_OWORD *)a1 = *(_OWORD *)v16;
              *((_OWORD *)a1 + 1) = *(_OWORD *)(v16 + 16);
              *((_OWORD *)a1 + 2) = *(_OWORD *)(v16 + 32);
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                LOWORD(v51) = 0;
                LOWORD(v46) = 0;
                v34 = *(unsigned __int8 *)(v16 + 8);
                LODWORD(v33) = *(unsigned __int8 *)(v16 + 7);
                LODWORD(v32) = *(unsigned __int8 *)(v16 + 6);
                FormatRRASErrorString(
                  &v51,
                  L"DeleteRTRMgrOwnedRoutesToDestFromStack: Found , Address: %d.%d.%d.%d Mask: %d",
                  *(unsigned __int8 *)(v16 + 4),
                  *(unsigned __int8 *)(v16 + 5),
                  v32,
                  v33);
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)&v51,
                    (unsigned int)&v42,
                    0,
                    (__int64)&v46);
              }
            }
          }
          if ( v20 )
            goto LABEL_45;
        }
        else
        {
          v21 = a1[20];
          v22 = 72 * i;
          v16 = v21 >> 3;
          v41 = *(_OWORD *)(a1 + 4);
          v23 = 0;
          v43 = *(GUID *)(72 * i + v36 + 4);
          while ( (unsigned int)v23 < (unsigned int)v16 )
          {
            v15 = *((unsigned __int8 *)&v43.Data1 + v23);
            if ( *((_BYTE *)&v41 + v23) != (_BYTE)v15 )
              goto LABEL_56;
            v23 = (unsigned int)(v23 + 1);
          }
          v24 = v21 & 7;
          if ( (v21 & 7) == 0
            || (v25 = (unsigned int)v16,
                v15 = 8 - v24,
                LODWORD(v16) = (unsigned __int8)((-1 << (8 - v24)) & *((_BYTE *)&v43.Data1 + v16)),
                ((unsigned __int8)(255 << (8 - v24)) & *((_BYTE *)&v41 + v25)) == (_BYTE)v16) )
          {
            v26 = v22 + v36;
            if ( v21 == *(_BYTE *)(v22 + v36 + 20) )
            {
              memset_0(v50, 0, 0x41u);
              *(_OWORD *)a1 = *(_OWORD *)v26;
              *((_OWORD *)a1 + 1) = *(_OWORD *)(v26 + 16);
              *((_OWORD *)a1 + 2) = *(_OWORD *)(v26 + 32);
              *((_OWORD *)a1 + 3) = *(_OWORD *)(v26 + 48);
              *((_QWORD *)a1 + 8) = *(_QWORD *)(v26 + 64);
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                LOWORD(v51) = 0;
                LOWORD(v46) = 0;
                v27 = *(_OWORD *)(v26 + 4);
                v28 = *(unsigned __int8 *)(v26 + 20);
                v41 = v27;
                Ipv6StringFromAddress = GetIpv6StringFromAddress(&v41, v50);
                FormatRRASErrorString(
                  &v51,
                  L"DeleteRTRMgrOwnedRoutesToDestFromStack: Found, Address: %hs PrefixLength: %d ",
                  Ipv6StringFromAddress,
                  v28);
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)&v51,
                    (unsigned int)&v42,
                    0,
                    (__int64)&v46);
              }
LABEL_45:
              v30 = v39 + 32LL * (unsigned int)i;
              if ( v30 )
              {
                if ( *(int *)(v30 + 16) > 4 )
                {
                  if ( v11 )
                  {
                    v31 = v36;
                    if ( a2 )
                    {
                      v15 = 6 * i;
                      *(_OWORD *)a1 = *(_OWORD *)(v36 + 48 * i);
                      *((_OWORD *)a1 + 1) = *(_OWORD *)(v31 + 48 * i + 16);
                      *((_OWORD *)a1 + 2) = *(_OWORD *)(v31 + 48 * i + 32);
                    }
                    else
                    {
                      v15 = 9 * i;
                      *(_OWORD *)a1 = *(_OWORD *)(v36 + 72 * i);
                      *((_OWORD *)a1 + 1) = *(_OWORD *)(v31 + 72 * i + 16);
                      *((_OWORD *)a1 + 2) = *(_OWORD *)(v31 + 72 * i + 32);
                      *((_OWORD *)a1 + 3) = *(_OWORD *)(v31 + 72 * i + 48);
                      *((_QWORD *)a1 + 8) = *(_QWORD *)(v31 + 72 * i + 64);
                    }
                  }
                  v10 = SetAllParameters(v15, (_DWORD)v40, v16, (_DWORD)a1, v38, v30, v34, 3);
                }
              }
              else
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  LOWORD(v51) = 0;
                  LOWORD(v46) = 0;
                  FormatRRASErrorString(
                    &v51,
                    L"DeleteRTRMgrOwnedRoutesToDestFromStack : error %d returned by NsiAllocateAndGetTable",
                    0);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrmgrParamTraceInfo,
                      (unsigned int)&v51,
                      (unsigned int)&v42,
                      0,
                      (__int64)&v46);
                }
                v10 = 0;
              }
              continue;
            }
          }
        }
LABEL_56:
        ;
      }
    }
  }
  else
  {
    Parameter = 87;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v51) = 0;
    FormatRRASErrorString(
      &v51,
      L"DeleteRTRMgrOwnedRoutesToDestFromStack: NsiGetRoutingDomainIdForCompartment failed with error %d",
      Parameter);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v51);
  }
  return Parameter;
}

```

## disassembly

```asm
0x1800010a0  push    rbp
0x1800010a2  push    rbx
0x1800010a3  push    rsi
0x1800010a4  push    rdi
0x1800010a5  push    r12
0x1800010a7  push    r15
0x1800010a9  lea     rbp, [rsp-8F8h]
0x1800010b1  sub     rsp, 9F8h
0x1800010b8  mov     rax, cs:__security_cookie
0x1800010bf  xor     rax, rsp
0x1800010c2  mov     [rbp+920h+var_40], rax
0x1800010c9  xor     esi, esi
0x1800010cb  xorps   xmm0, xmm0
0x1800010ce  test    edx, edx
0x1800010d0  mov     [rsp+0A20h+var_9A8], rsi
0x1800010d5  mov     r12, rcx
0x1800010d8  mov     [rbp+920h+var_998], rsi
0x1800010dc  mov     ebx, r8d
0x1800010df  mov     [rbp+920h+var_9A0], esi
0x1800010e2  mov     eax, 30h ; '0'
0x1800010e7  lea     rcx, NPI_MS_IPV6_MODULEID
0x1800010ee  mov     r8d, 48h ; 'H'; Size
0x1800010f4  mov     r15d, edx
0x1800010f7  cmovz   eax, r8d
0x1800010fb  mov     [rbp+920h+var_99C], eax
0x1800010fe  lea     rax, NPI_MS_IPV4_MODULEID
0x180001105  cmovz   rax, rcx
0x180001109  xor     edx, edx; Val
0x18000110b  lea     rcx, [rbp+920h+var_910]; void *
0x18000110f  mov     [rbp+920h+var_990], rax
0x180001113  movups  [rbp+920h+var_950], xmm0
0x180001117  movups  [rbp+920h+var_940], xmm0
0x18000111b  movups  [rbp+920h+var_930], xmm0
0x18000111f  call    memset_0
0x180001124  xorps   xmm0, xmm0
0x180001127  mov     [rbp+920h+var_840], esi
0x18000112d  xor     edx, edx; Val
0x18000112f  lea     rcx, [rbp+920h+var_83C]; void *
0x180001136  mov     r8d, 7FCh; Size
0x18000113c  movups  [rbp+920h+var_970], xmm0
0x180001140  call    memset_0
0x180001145  xorps   xmm0, xmm0
0x180001148  mov     [rbp+920h+var_8C0], esi
0x18000114b  xor     eax, eax
0x18000114d  mov     edi, 1
0x180001152  mov     [rbp+920h+var_89C], eax
0x180001158  movups  [rbp+920h+var_8BC], xmm0
0x18000115c  movups  [rbp+920h+var_8AC], xmm0
0x180001160  movups  [rbp+920h+var_920], xmm0
0x180001164  cmp     ebx, edi
0x180001166  jz      short loc_1800011DE
0x180001168  cmp     cs:gIsRtrMgrEtwEnabled, eax
0x18000116e  jz      short loc_1800011DE
0x180001170  mov     [rsp+0A20h+var_9B0], ebx
0x180001174  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000117b  movaps  [rbp+920h+var_960], xmm0
0x18000117f  test    ebx, ebx
0x180001181  jz      loc_1800012EE
0x180001187  mov     [rsp+0A20h+var_9E0], 438h
0x18000118f  lea     rax, [rbp+920h+var_960]
0x180001193  mov     dword ptr [rsp+0A20h+var_9E8], 10h
0x18000119b  lea     r9, [rsp+0A20h+var_9B0]
0x1800011a0  mov     [rsp+0A20h+var_9F0], rax
0x1800011a5  lea     rdx, NPI_MS_NDIS_MODULEID
0x1800011ac  mov     dword ptr [rsp+0A20h+var_9F8], esi
0x1800011b0  mov     r8d, 7
0x1800011b6  mov     ecx, edi
0x1800011b8  mov     dword ptr [rsp+0A20h+var_A00], 4
0x1800011c0  call    cs:__imp_NsiGetParameter
0x1800011c6  mov     edi, eax
0x1800011c8  test    eax, eax
0x1800011ca  jnz     loc_1800012F3
0x1800011d0  movaps  xmm0, [rbp+920h+var_960]
0x1800011d4  movdqa  [rbp+920h+var_970], xmm0
0x1800011d9  mov     edi, 1
0x1800011de  mov     [rsp+0A20h+arg_8], r13
0x1800011e6  mov     r13d, esi
0x1800011e9  mov     [rsp+0A20h+var_30], r14
0x1800011f1  mov     r14d, esi
0x1800011f4  test    r12, r12
0x1800011f7  jnz     short loc_18000120B
0x1800011f9  test    r15d, r15d
0x1800011fc  lea     r12, [rbp+920h+var_950]
0x180001200  lea     rax, [rbp+920h+var_910]
0x180001204  mov     r14d, edi
0x180001207  cmovz   r12, rax
0x18000120b  call    cs:__imp_GetCurrentThreadCompartmentId
0x180001211  mov     ecx, ebx; CompartmentId
0x180001213  mov     [rsp+0A20h+var_9B0], eax
0x180001217  mov     esi, eax
0x180001219  call    cs:__imp_SetCurrentThreadCompartmentId
0x18000121f  mov     r8d, eax
0x180001222  test    eax, eax
0x180001224  jnz     loc_1800016CC
0x18000122a  mov     rdx, [rbp+920h+var_990]
0x18000122e  lea     rax, [rbp+920h+var_9A0]
0x180001232  mov     [rsp+0A20h+var_9C0], r13b
0x180001237  lea     r9, [rsp+0A20h+var_9A8]
0x18000123c  mov     [rsp+0A20h+var_9C8], rax
0x180001241  mov     r8d, 10h
0x180001247  xor     eax, eax
0x180001249  mov     ecx, edi
0x18000124b  mov     [rsp+0A20h+var_9D0], eax
0x18000124f  mov     [rsp+0A20h+var_9D8], rax
0x180001254  mov     [rsp+0A20h+var_9E0], eax
0x180001258  mov     [rsp+0A20h+var_9E8], rax
0x18000125d  lea     rax, [rbp+920h+var_998]
0x180001261  mov     dword ptr [rsp+0A20h+var_9F0], 20h ; ' '
0x180001269  mov     [rsp+0A20h+var_9F8], rax
0x18000126e  mov     eax, [rbp+920h+var_99C]
0x180001271  mov     dword ptr [rsp+0A20h+var_A00], eax
0x180001275  call    cs:__imp_NsiAllocateAndGetTable
0x18000127b  mov     ebx, eax
0x18000127d  test    eax, eax
0x18000127f  jz      loc_180001343
0x180001285  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18000128c  jge     short loc_1800012E6
0x18000128e  xor     ecx, ecx
0x180001290  lea     rdx, aDeletertrmgrow_2; "DeleteRTRMgrOwnedRoutesToDestFromStack "...
0x180001297  mov     word ptr [rbp+920h+var_840], cx
0x18000129e  mov     r8d, eax
0x1800012a1  mov     word ptr [rbp+920h+var_8C0], cx
0x1800012a5  lea     rcx, [rbp+920h+var_840]
0x1800012ac  call    FormatRRASErrorString
0x1800012b1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800012b8  jge     short loc_1800012E6
0x1800012ba  lea     rax, [rbp+920h+var_8C0]
0x1800012be  mov     [rsp+0A20h+var_9F8], rax
0x1800012c3  lea     r9, [rbp+920h+var_970]
0x1800012c7  lea     r8, [rbp+920h+var_840]
0x1800012ce  mov     [rsp+0A20h+var_A00], r13
0x1800012d3  lea     rdx, RasRtrmgrParamTraceInfo
0x1800012da  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800012e1  call    McTemplateU0zjzz_EventWriteTransfer
0x1800012e6  mov     r13d, ebx
0x1800012e9  jmp     loc_180001737
0x1800012ee  mov     edi, 57h ; 'W'
0x1800012f3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800012fa  jz      short loc_18000133C
0x1800012fc  mov     r8d, edi
0x1800012ff  mov     word ptr [rbp+920h+var_840], si
0x180001306  lea     rdx, aDeletertrmgrow_3; "DeleteRTRMgrOwnedRoutesToDestFromStack:"...
0x18000130d  lea     rcx, [rbp+920h+var_840]
0x180001314  call    FormatRRASErrorString
0x180001319  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180001320  jz      short loc_18000133C
0x180001322  lea     r8, [rbp+920h+var_840]
0x180001329  lea     rdx, RasRtrMgrTraceError
0x180001330  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001337  call    McTemplateU0z_EventWriteTransfer
0x18000133c  mov     eax, edi
0x18000133e  jmp     loc_180001770
0x180001343  xor     edi, edi
0x180001345  cmp     edi, [rbp+920h+var_9A0]
0x180001348  jnb     loc_18000172E
0x18000134e  mov     esi, edi
0x180001350  test    r14d, r14d
0x180001353  jnz     loc_1800015AD
0x180001359  test    r15d, r15d
0x18000135c  jz      loc_18000144B
0x180001362  mov     rcx, [rsp+0A20h+var_9A8]
0x180001367  lea     rdx, [rdi+rdi*2]
0x18000136b  add     rdx, rdx
0x18000136e  xor     ebx, ebx
0x180001370  mov     eax, [rcx+rdx*8+4]
0x180001374  cmp     [r12+4], eax
0x180001379  jnz     loc_18000143E
0x18000137f  movzx   eax, byte ptr [rcx+rdx*8+8]
0x180001384  lea     r8, [rcx+rdx*8]
0x180001388  cmp     [r12+8], al
0x18000138d  jnz     loc_18000143E
0x180001393  movups  xmm0, xmmword ptr [r8]
0x180001397  mov     ebx, 1
0x18000139c  movups  xmmword ptr [r12], xmm0
0x1800013a1  movups  xmm1, xmmword ptr [r8+10h]
0x1800013a6  movups  xmmword ptr [r12+10h], xmm1
0x1800013ac  movups  xmm0, xmmword ptr [r8+20h]
0x1800013b1  movups  xmmword ptr [r12+20h], xmm0
0x1800013b7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800013be  jge     short loc_18000143E
0x1800013c0  xor     eax, eax
0x1800013c2  mov     word ptr [rbp+920h+var_840], ax
0x1800013c9  mov     word ptr [rbp+920h+var_8C0], ax
0x1800013cd  movzx   ecx, byte ptr [r8+7]
0x1800013d2  movzx   edx, byte ptr [r8+6]
0x1800013d7  movzx   eax, byte ptr [r8+8]
0x1800013dc  movzx   r9d, byte ptr [r8+5]
0x1800013e1  movzx   r8d, byte ptr [r8+4]
0x1800013e6  mov     dword ptr [rsp+0A20h+var_9F0], eax
0x1800013ea  mov     dword ptr [rsp+0A20h+var_9F8], ecx
0x1800013ee  lea     rcx, [rbp+920h+var_840]
0x1800013f5  mov     dword ptr [rsp+0A20h+var_A00], edx
0x1800013f9  lea     rdx, aDeletertrmgrow; "DeleteRTRMgrOwnedRoutesToDestFromStack:"...
0x180001400  call    FormatRRASErrorString
0x180001405  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18000140c  jge     short loc_18000143E
0x18000140e  lea     rax, [rbp+920h+var_8C0]
0x180001412  mov     [rsp+0A20h+var_9F8], rax
0x180001417  lea     r9, [rbp+920h+var_970]
0x18000141b  lea     r8, [rbp+920h+var_840]
0x180001422  mov     [rsp+0A20h+var_A00], 0
0x18000142b  lea     rdx, RasRtrmgrParamTraceInfo
0x180001432  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001439  call    McTemplateU0zjzz_EventWriteTransfer
0x18000143e  test    ebx, ebx
0x180001440  jnz     loc_1800015AD
0x180001446  jmp     loc_1800016C5
0x18000144b  movzx   r9d, byte ptr [r12+14h]
0x180001451  lea     rax, [rdi+rdi*8]
0x180001455  movups  xmm1, xmmword ptr [r12+4]
0x18000145b  lea     r10, ds:0[rax*8]
0x180001463  mov     r8d, r9d
0x180001466  mov     rax, [rsp+0A20h+var_9A8]
0x18000146b  shr     r8d, 3
0x18000146f  movaps  [rbp+920h+var_980], xmm1
0x180001473  movups  xmm0, xmmword ptr [r10+rax+4]
0x180001479  xor     eax, eax
0x18000147b  movaps  [rbp+920h+var_960], xmm0
0x18000147f  nop
0x180001480  cmp     eax, r8d
0x180001483  jnb     short loc_180001498
0x180001485  movzx   ecx, byte ptr [rbp+rax+920h+var_960]
0x18000148a  cmp     byte ptr [rbp+rax+920h+var_980], cl
0x18000148e  jnz     loc_1800016C5
0x180001494  inc     eax
0x180001496  jmp     short loc_180001480
0x180001498  mov     eax, r9d
0x18000149b  and     eax, 7
0x18000149e  jz      short loc_1800014D1
0x1800014a0  mov     edx, r8d
0x1800014a3  mov     ecx, 8
0x1800014a8  movzx   r8d, byte ptr [rbp+r8+920h+var_960]
0x1800014ae  sub     ecx, eax
0x1800014b0  mov     eax, 0FFh
0x1800014b5  shl     al, cl
0x1800014b7  movzx   edx, byte ptr [rbp+rdx+920h+var_980]
0x1800014bc  and     r8d, eax
0x1800014bf  mov     eax, 0FFh
0x1800014c4  shl     eax, cl
0x1800014c6  and     edx, eax
0x1800014c8  cmp     dl, r8b
0x1800014cb  jnz     loc_1800016C5
0x1800014d1  mov     rbx, [rsp+0A20h+var_9A8]
0x1800014d6  add     rbx, r10
0x1800014d9  cmp     r9b, [rbx+14h]
0x1800014dd  jnz     loc_1800016C5
0x1800014e3  xor     edx, edx; Val
0x1800014e5  lea     rcx, [rbp+920h+var_890]; void *
0x1800014ec  mov     r8d, 41h ; 'A'; Size
0x1800014f2  call    memset_0
0x1800014f7  movups  xmm0, xmmword ptr [rbx]
0x1800014fa  movups  xmmword ptr [r12], xmm0
0x1800014ff  movups  xmm1, xmmword ptr [rbx+10h]
0x180001503  movups  xmmword ptr [r12+10h], xmm1
0x180001509  movups  xmm0, xmmword ptr [rbx+20h]
0x18000150d  movups  xmmword ptr [r12+20h], xmm0
0x180001513  movups  xmm1, xmmword ptr [rbx+30h]
0x180001517  movups  xmmword ptr [r12+30h], xmm1
0x18000151d  movsd   xmm0, qword ptr [rbx+40h]
0x180001522  movsd   qword ptr [r12+40h], xmm0
0x180001529  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180001530  jge     short loc_1800015AD
0x180001532  xor     eax, eax
0x180001534  lea     rdx, [rbp+920h+var_890]
0x18000153b  mov     word ptr [rbp+920h+var_840], ax
0x180001542  lea     rcx, [rbp+920h+var_980]
0x180001546  mov     word ptr [rbp+920h+var_8C0], ax
0x18000154a  movups  xmm0, xmmword ptr [rbx+4]
0x18000154e  movzx   ebx, byte ptr [rbx+14h]
0x180001552  movaps  [rbp+920h+var_980], xmm0
0x180001556  call    GetIpv6StringFromAddress
0x18000155b  mov     r8, rax
0x18000155e  lea     rdx, aDeletertrmgrow_0; "DeleteRTRMgrOwnedRoutesToDestFromStack:"...
0x180001565  mov     r9d, ebx
0x180001568  lea     rcx, [rbp+920h+var_840]
0x18000156f  call    FormatRRASErrorString
0x180001574  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000157b  jge     short loc_1800015AD
0x18000157d  lea     rax, [rbp+920h+var_8C0]
0x180001581  mov     [rsp+0A20h+var_9F8], rax
0x180001586  lea     r9, [rbp+920h+var_970]
0x18000158a  lea     r8, [rbp+920h+var_840]
0x180001591  mov     [rsp+0A20h+var_A00], 0
0x18000159a  lea     rdx, RasRtrmgrParamTraceInfo
0x1800015a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800015a8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800015ad  mov     rdx, rsi
0x1800015b0  shl     rdx, 5
0x1800015b4  add     rdx, [rbp+920h+var_998]
0x1800015b8  jnz     short loc_180001626
0x1800015ba  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dl
0x1800015c0  jge     short loc_18000161E
0x1800015c2  xor     eax, eax
0x1800015c4  lea     rdx, aDeletertrmgrow_2; "DeleteRTRMgrOwnedRoutesToDestFromStack "...
0x1800015cb  xor     r8d, r8d
0x1800015ce  mov     word ptr [rbp+920h+var_840], ax
0x1800015d5  lea     rcx, [rbp+920h+var_840]
0x1800015dc  mov     word ptr [rbp+920h+var_8C0], ax
0x1800015e0  call    FormatRRASErrorString
0x1800015e5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
  ... truncated ...
```
