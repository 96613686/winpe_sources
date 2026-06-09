# URLMONRequest::ApplySetting(TRANSPORT_SETTING_ID const *,ulong,uchar const *,ulong *,uchar * *)

- ea: `0x10133690`
- end: `0x10133806`
- name: `?ApplySetting@URLMONRequest@@UAEJPBUTRANSPORT_SETTING_ID@@KPBEPAKPAPAE@Z`
- size: `374`
- prototype: `HRESULT __thiscall(URLMONRequest *this, const TRANSPORT_SETTING_ID *pSettingId, unsigned int cbIn, const unsigned __int8 *pbValueIn, unsigned int *pcbOut, unsigned __int8 **ppbValueOut)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x10067b20`
- `0x10133690`
- `0x101375ab`
- `0x101712a4`
- `0x10180006`
- `0x101805e2`
- `0x10180e24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101337cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101337cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013374e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013374e`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::ApplySetting(
        URLMONRequest *this,
        const TRANSPORT_SETTING_ID *pSettingId,
        unsigned int cbIn,
        const unsigned __int8 *pbValueIn,
        unsigned int *pcbOut,
        unsigned __int8 **ppbValueOut)
{
  URLMONRequest *v6; // edi
  int v7; // ebx
  const TRANSPORT_SETTING_ID *v8; // eax
  unsigned __int8 *v9; // eax
  int v10; // ecx
  TRANSPORT_SETTING_ID *p_SettingId; // edi
  unsigned __int8 *v13; // [esp+8h] [ebp-8h]

  v6 = this;
  v7 = 0;
  if ( (byte_10185760[0] & 8) != 0 )
  {
    v8 = (const TRANSPORT_SETTING_ID *)&GUID_NULL;
    if ( pSettingId )
      v8 = pSettingId;
    WPP_SF_q_guid_dqqq(
      0x403u,
      0x61u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      this,
      &v8->Guid,
      cbIn,
      pbValueIn,
      pcbOut,
      ppbValueOut);
  }
  v6->Lock(v6);
  if ( pcbOut && (*pcbOut = 0, ppbValueOut) )
  {
    *ppbValueOut = 0;
    if ( pSettingId && pbValueIn )
    {
      URLMONRequest::_FreeTransportSettings(v6);
      if ( v6->_eState == OPENED )
      {
        if ( v6->_fAborted || v6->_fAbortPending )
        {
          v7 = -2147467260;
        }
        else if ( v6->_fMta )
        {
          v9 = (unsigned __int8 *)CoTaskMemAlloc(cbIn);
          v13 = v9;
          if ( v9 )
          {
            memcpy(v9, pbValueIn, cbIn);
            p_SettingId = &v6->_SettingId;
            p_SettingId->Guid.Data1 = pSettingId->Guid.Data1;
            p_SettingId = (TRANSPORT_SETTING_ID *)((char *)p_SettingId + 4);
            p_SettingId->Guid.Data1 = *(_DWORD *)&pSettingId->Guid.Data2;
            *(_QWORD *)&p_SettingId->Guid.Data2 = *(_QWORD *)pSettingId->Guid.Data4;
            v6 = this;
            this->_cbSetting = cbIn;
            this->_pbSetting = v13;
            *(_WORD *)&this->_fDisableUI = 1;
            if ( (byte_10185758 & 8) != 0 )
              WPP_SF_ll(v10, 1, 0);
          }
          else
          {
            v7 = -2147024882;
          }
        }
        else
        {
          v7 = -2147417854;
        }
      }
      else
      {
        v7 = -2147019873;
      }
    }
    else
    {
      v7 = -2147024809;
    }
  }
  else
  {
    v7 = -2147467261;
  }
  v6->Unlock(v6);
  CoTaskMemFree(0);
  if ( (byte_10185760[16 * (v7 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v7 >> 31) + 2) << 9) | 3, 0x63u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x10133690  mov     edi, edi
0x10133692  push    ebp
0x10133693  mov     ebp, esp
0x10133695  push    this
0x10133696  push    this
0x10133697  push    ebx
0x10133698  push    edi
0x10133699  mov     edi, this
0x1013369b  xor     ebx, ebx
0x1013369d  mov     [ebp+var_4], edi
0x101336a0  test    byte_10185760, 8; __annotation("TMF:",
0x101336a7  jz      short loc_101336D6
0x101336a9  push    [ebp+ppbValueOut]; _a6
0x101336ac  mov     eax, [ebp+cbIn]
0x101336af  mov     this, 403h; LevelKeyword
0x101336b4  push    [ebp+pcbOut]; _a5
0x101336b7  cmp     [ebp+pSettingId], ebx
0x101336ba  push    [ebp+pbValueIn]; _a4
0x101336bd  push    eax; _a3
0x101336be  mov     eax, offset _GUID_NULL
0x101336c3  cmovnz  eax, [ebp+pSettingId]
0x101336c7  push    eax; _a2
0x101336c8  push    edi; _a1
0x101336c9  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101336ce  push    61h ; 'a'
0x101336d0  pop     edx; id
0x101336d1  call    _WPP_SF_q_guid_dqqq@36; WPP_SF_q_guid_dqqq(x,x,x,x,x,x,x,x,x)
0x101336d6  mov     eax, [edi]
0x101336d8  push    esi
0x101336d9  mov     esi, [eax+7Ch]
0x101336dc  mov     this, esi; this
0x101336de  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101336e4  mov     this, edi
0x101336e6  call    esi
0x101336e8  mov     eax, [ebp+pcbOut]
0x101336eb  test    eax, eax
0x101336ed  jnz     short loc_101336F9
0x101336ef  mov     ebx, 80004003h
0x101336f4  jmp     CleanUp_462
0x101336f9  xor     esi, esi
0x101336fb  mov     [eax], esi
0x101336fd  mov     eax, [ebp+ppbValueOut]
0x10133700  test    eax, eax
0x10133702  jz      short loc_101336EF
0x10133704  mov     [eax], esi
0x10133706  cmp     [ebp+pSettingId], ebx
0x10133709  jnz     short loc_10133715
0x1013370b  mov     ebx, 80070057h
0x10133710  jmp     CleanUp_462
0x10133715  cmp     [ebp+pbValueIn], ebx
0x10133718  jz      short loc_1013370B
0x1013371a  mov     this, edi; this
0x1013371c  call    ?_FreeTransportSettings@URLMONRequest@@IAEXXZ; URLMONRequest::_FreeTransportSettings(void)
0x10133721  cmp     dword ptr [edi+50h], 1
0x10133725  jz      short loc_10133731
0x10133727  mov     ebx, 8007139Fh
0x1013372c  jmp     CleanUp_462
0x10133731  cmp     [edi+0Ah], bl
0x10133734  jnz     short loc_101337B2
0x10133736  cmp     [edi+168h], esi
0x1013373c  jnz     short loc_101337B2
0x1013373e  cmp     [edi+64h], esi
0x10133741  jnz     short loc_1013374A
0x10133743  mov     ebx, 80010102h
0x10133748  jmp     short CleanUp_462
0x1013374a  mov     esi, [ebp+cbIn]
0x1013374d  push    esi; cb
0x1013374e  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10133754  mov     [ebp+var_8], eax
0x10133757  test    eax, eax
0x10133759  jnz     short loc_10133762
0x1013375b  mov     ebx, 8007000Eh
0x10133760  jmp     short CleanUp_462
0x10133762  push    esi; Size
0x10133763  push    [ebp+pbValueIn]; Src
0x10133766  push    eax; void *
0x10133767  call    _memcpy
0x1013376c  mov     esi, [ebp+pSettingId]
0x1013376f  add     esp, 0Ch
0x10133772  mov     eax, [ebp+cbIn]
0x10133775  add     edi, 120h
0x1013377b  movsd
0x1013377c  movsd
0x1013377d  movsd
0x1013377e  movsd
0x1013377f  mov     edi, [ebp+var_4]
0x10133782  mov     [edi+130h], eax
0x10133788  mov     eax, [ebp+var_8]
0x1013378b  mov     [edi+134h], eax
0x10133791  mov     word ptr [edi+0E1h], 1
0x1013379a  test    byte_10185758, 8; __annotation("TMF:",
0x101337a1  jz      short CleanUp_462
0x101337a3  push    0; LevelKeyword
0x101337a5  push    1; _a2
0x101337a7  push    this; _a1
0x101337a8  push    62h ; 'b'
0x101337aa  pop     edx; id
0x101337ab  call    _WPP_SF_ll@20; WPP_SF_ll(x,x,x,x,x)
0x101337b0  jmp     short CleanUp_462
0x101337b2  mov     ebx, 80004004h
0x101337b7  mov     eax, [edi]
0x101337b9  mov     esi, [eax+80h]
0x101337bf  mov     this, esi; this
0x101337c1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101337c7  mov     this, edi
0x101337c9  call    esi
0x101337cb  push    0; pv
0x101337cd  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101337d3  mov     this, ebx; __annotation("TMF:",
0x101337d5  sar     this, 1Fh
0x101337d8  mov     eax, this
0x101337da  shl     eax, 4
0x101337dd  pop     esi
0x101337de  test    byte_10185760[eax], 8
0x101337e5  jz      short loc_101337FE
0x101337e7  push    ebx; _a1
0x101337e8  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101337ed  add     this, 2
0x101337f0  shl     this, 9
0x101337f3  push    63h ; 'c'
0x101337f5  or      this, 3; LevelKeyword
0x101337f8  pop     edx; id
0x101337f9  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101337fe  pop     edi
0x101337ff  mov     eax, ebx
0x10133801  pop     ebx
0x10133802  leave
0x10133803  retn    14h
```
