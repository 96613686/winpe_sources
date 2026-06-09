# URLMONRequest::ApplySetting(TRANSPORT_SETTING_ID const *,ulong,uchar const *,ulong *,uchar * *)

- ea: `0x10133580`
- end: `0x101336f6`
- name: `?ApplySetting@URLMONRequest@@UAEJPBUTRANSPORT_SETTING_ID@@KPBEPAKPAPAE@Z`
- size: `374`
- prototype: `HRESULT __thiscall(URLMONRequest *this, const TRANSPORT_SETTING_ID *pSettingId, unsigned int cbIn, const unsigned __int8 *pbValueIn, unsigned int *pcbOut, unsigned __int8 **ppbValueOut)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x10067bc0`
- `0x10133580`
- `0x1013749b`
- `0x101711b4`
- `0x10180006`
- `0x101805e2`
- `0x10180e24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101336bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101336bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013363e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1013363e`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
            if ( (byte_10185798 & 8) != 0 )
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
  if ( (byte_101857A0[16 * (v7 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v7 >> 31) + 2) << 9) | 3, 0x63u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x10133580  mov     edi, edi
0x10133582  push    ebp
0x10133583  mov     ebp, esp
0x10133585  push    this
0x10133586  push    this
0x10133587  push    ebx
0x10133588  push    edi
0x10133589  mov     edi, this
0x1013358b  xor     ebx, ebx
0x1013358d  mov     [ebp+var_4], edi
0x10133590  test    byte_101857A0, 8; __annotation("TMF:",
0x10133597  jz      short loc_101335C6
0x10133599  push    [ebp+ppbValueOut]; _a6
0x1013359c  mov     eax, [ebp+cbIn]
0x1013359f  mov     this, 403h; LevelKeyword
0x101335a4  push    [ebp+pcbOut]; _a5
0x101335a7  cmp     [ebp+pSettingId], ebx
0x101335aa  push    [ebp+pbValueIn]; _a4
0x101335ad  push    eax; _a3
0x101335ae  mov     eax, offset _GUID_NULL
0x101335b3  cmovnz  eax, [ebp+pSettingId]
0x101335b7  push    eax; _a2
0x101335b8  push    edi; _a1
0x101335b9  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101335be  push    61h ; 'a'
0x101335c0  pop     edx; id
0x101335c1  call    _WPP_SF_q_guid_dqqq@36; WPP_SF_q_guid_dqqq(x,x,x,x,x,x,x,x,x)
0x101335c6  mov     eax, [edi]
0x101335c8  push    esi
0x101335c9  mov     esi, [eax+7Ch]
0x101335cc  mov     this, esi; this
0x101335ce  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101335d4  mov     this, edi
0x101335d6  call    esi
0x101335d8  mov     eax, [ebp+pcbOut]
0x101335db  test    eax, eax
0x101335dd  jnz     short loc_101335E9
0x101335df  mov     ebx, 80004003h
0x101335e4  jmp     CleanUp_462
0x101335e9  xor     esi, esi
0x101335eb  mov     [eax], esi
0x101335ed  mov     eax, [ebp+ppbValueOut]
0x101335f0  test    eax, eax
0x101335f2  jz      short loc_101335DF
0x101335f4  mov     [eax], esi
0x101335f6  cmp     [ebp+pSettingId], ebx
0x101335f9  jnz     short loc_10133605
0x101335fb  mov     ebx, 80070057h
0x10133600  jmp     CleanUp_462
0x10133605  cmp     [ebp+pbValueIn], ebx
0x10133608  jz      short loc_101335FB
0x1013360a  mov     this, edi; this
0x1013360c  call    ?_FreeTransportSettings@URLMONRequest@@IAEXXZ; URLMONRequest::_FreeTransportSettings(void)
0x10133611  cmp     dword ptr [edi+50h], 1
0x10133615  jz      short loc_10133621
0x10133617  mov     ebx, 8007139Fh
0x1013361c  jmp     CleanUp_462
0x10133621  cmp     [edi+0Ah], bl
0x10133624  jnz     short loc_101336A2
0x10133626  cmp     [edi+168h], esi
0x1013362c  jnz     short loc_101336A2
0x1013362e  cmp     [edi+64h], esi
0x10133631  jnz     short loc_1013363A
0x10133633  mov     ebx, 80010102h
0x10133638  jmp     short CleanUp_462
0x1013363a  mov     esi, [ebp+cbIn]
0x1013363d  push    esi; cb
0x1013363e  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10133644  mov     [ebp+var_8], eax
0x10133647  test    eax, eax
0x10133649  jnz     short loc_10133652
0x1013364b  mov     ebx, 8007000Eh
0x10133650  jmp     short CleanUp_462
0x10133652  push    esi; Size
0x10133653  push    [ebp+pbValueIn]; Src
0x10133656  push    eax; void *
0x10133657  call    _memcpy
0x1013365c  mov     esi, [ebp+pSettingId]
0x1013365f  add     esp, 0Ch
0x10133662  mov     eax, [ebp+cbIn]
0x10133665  add     edi, 120h
0x1013366b  movsd
0x1013366c  movsd
0x1013366d  movsd
0x1013366e  movsd
0x1013366f  mov     edi, [ebp+var_4]
0x10133672  mov     [edi+130h], eax
0x10133678  mov     eax, [ebp+var_8]
0x1013367b  mov     [edi+134h], eax
0x10133681  mov     word ptr [edi+0E1h], 1
0x1013368a  test    byte_10185798, 8; __annotation("TMF:",
0x10133691  jz      short CleanUp_462
0x10133693  push    0; LevelKeyword
0x10133695  push    1; _a2
0x10133697  push    this; _a1
0x10133698  push    62h ; 'b'
0x1013369a  pop     edx; id
0x1013369b  call    _WPP_SF_ll@20; WPP_SF_ll(x,x,x,x,x)
0x101336a0  jmp     short CleanUp_462
0x101336a2  mov     ebx, 80004004h
0x101336a7  mov     eax, [edi]
0x101336a9  mov     esi, [eax+80h]
0x101336af  mov     this, esi; this
0x101336b1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101336b7  mov     this, edi
0x101336b9  call    esi
0x101336bb  push    0; pv
0x101336bd  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101336c3  mov     this, ebx; __annotation("TMF:",
0x101336c5  sar     this, 1Fh
0x101336c8  mov     eax, this
0x101336ca  shl     eax, 4
0x101336cd  pop     esi
0x101336ce  test    byte_101857A0[eax], 8
0x101336d5  jz      short loc_101336EE
0x101336d7  push    ebx; _a1
0x101336d8  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101336dd  add     this, 2
0x101336e0  shl     this, 9
0x101336e3  push    63h ; 'c'
0x101336e5  or      this, 3; LevelKeyword
0x101336e8  pop     edx; id
0x101336e9  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101336ee  pop     edi
0x101336ef  mov     eax, ebx
0x101336f1  pop     ebx
0x101336f2  leave
0x101336f3  retn    14h
```
