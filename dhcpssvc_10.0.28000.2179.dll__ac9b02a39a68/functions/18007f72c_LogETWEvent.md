# LogETWEvent

- ea: `0x18007f72c`
- end: `0x180080103`
- name: `LogETWEvent`
- size: `2519`
- prototype: ``
- caller_count: `19`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002c95c`
- `0x18002dc00`
- `0x180044e90`
- `0x180045660`
- `0x180048494`
- `0x1800489f0`
- `0x18004a288`
- `0x18004a4a4`
- `0x18004a8b0`
- `0x18004aa68`
- `0x18004ad58`
- `0x18004b2a0`
- `0x18004b6b0`
- `0x18004b8b0`
- `0x18004c2c0`
- `0x18007dbcc`
- `0x180081c6c`
- `0x180081f20`
- `0x1800825e0`

## callees

- `0x1800516fc`
- `0x180058208`
- `0x18007e04c`
- `0x18007e6b0`
- `0x18007f440`
- `0x18007f72c`
- `0x180083044`
- `0x180083358`
- `0x1800836c8`
- `0x1800cdac0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18007f7fd`
- `RPCRT4!RpcImpersonateClient` at `0x18007f7fd`
- `RPCRT4!RpcRevertToSelf` at `0x18007f8a9`
- `RPCRT4!RpcRevertToSelf` at `0x18007f8a9`
- `WS2_32!__imp_ntohl` at `0x18007f7af`
- `WS2_32!__imp_ntohl` at `0x18007f7e0`
- `WS2_32!__imp_ntohl` at `0x18007f7af`
- `WS2_32!__imp_ntohl` at `0x18007f7e0`
- `KERNEL32!HeapFree` at `0x18007f8c6`
- `KERNEL32!HeapFree` at `0x18007f8e3`
- `KERNEL32!HeapFree` at `0x18007f900`
- `KERNEL32!HeapFree` at `0x18007f8c6`
- `KERNEL32!HeapFree` at `0x18007f8e3`
- `KERNEL32!HeapFree` at `0x18007f900`

## pseudocode

```c
int __fastcall LogETWEvent(
        unsigned __int16 *a1,
        u_long a2,
        _WORD *a3,
        unsigned __int16 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  void *v11; // rbp
  __int64 v12; // rbx
  u_long v13; // eax
  void *v14; // rbx
  __int64 ClientDetails; // rdi
  u_long v16; // eax
  unsigned __int16 *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rcx
  __int128 *v20; // rdx
  int v21; // r9d
  int v22; // r8d
  void *v23; // rsi
  int v24; // r8d
  __int128 *v25; // rdx
  __int128 *v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int128 *v29; // rdx
  int v30; // ecx
  __int64 v31; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v32; // rax
  __int128 *v33; // rdx
  int v34; // ecx
  __int128 *v35; // rdx
  int v36; // ecx
  int v38; // [rsp+38h] [rbp-70h]
  __int64 v39; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 *v40; // [rsp+50h] [rbp-58h] BYREF

  v39 = a9;
  v40 = a1;
  v11 = 0;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
  }
  else
  {
    v12 = 0;
  }
  v13 = ntohl(a2);
  v14 = (void *)FormatIPandName(v13, a3, v12);
  ClientDetails = GetClientDetails();
  if ( a7 )
  {
    v16 = ntohl(*(_DWORD *)(a7 + 8));
    v11 = (void *)FormatIPandName(v16, 0, 0);
  }
  LODWORD(v17) = RpcImpersonateClient(0);
  v38 = (int)v17;
  v19 = *v40;
  if ( (unsigned int)v19 <= 0x62 )
  {
    if ( (_DWORD)v19 == 98 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v27 = (__int64)a3;
      v26 = &SuperScopeConfigured;
      goto LABEL_47;
    }
    if ( (unsigned int)v19 > 0x54 )
    {
      if ( (unsigned int)v19 > 0x5B )
      {
        LODWORD(v19) = v19 - 92;
        if ( !(_DWORD)v19 )
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v21 = (int)a4;
          v20 = &ScopeNAPProfileConfigured;
          goto LABEL_24;
        }
        LODWORD(v19) = v19 - 1;
        if ( !(_DWORD)v19 )
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v25 = &ScopeNAPProfileModified;
          goto LABEL_42;
        }
        LODWORD(v19) = v19 - 1;
        if ( !(_DWORD)v19 )
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v21 = (int)v14;
          v20 = &ScopeNAPProfileDeleted;
          v22 = (int)a4;
          goto LABEL_25;
        }
        v19 = (unsigned int)(v19 - 1);
        if ( (_DWORD)v19 )
        {
          v19 = (unsigned int)(v19 - 1);
          if ( (_DWORD)v19 )
          {
            if ( (_DWORD)v19 != 1 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
              goto LABEL_26;
            v21 = (int)a4;
            v20 = &SuperScopeAddExisting;
            goto LABEL_24;
          }
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v26 = &MulticastScopeDeleted;
        }
        else
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v26 = &MulticastScopeConfigured;
        }
      }
      else
      {
        if ( (_DWORD)v19 != 91 )
        {
          v28 = (unsigned int)(v19 - 85);
          if ( (_DWORD)v28 )
          {
            v28 = (unsigned int)(v28 - 1);
            if ( (_DWORD)v28 )
            {
              v19 = (unsigned int)(v28 - 1);
              if ( (_DWORD)v19 )
              {
                v19 = (unsigned int)(v19 - 1);
                if ( (_DWORD)v19 )
                {
                  v19 = (unsigned int)(v19 - 1);
                  if ( !(_DWORD)v19 )
                  {
                    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                      goto LABEL_26;
                    v25 = &ScopeSupportType;
                    goto LABEL_42;
                  }
                  if ( (_DWORD)v19 != 1 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                    goto LABEL_26;
                  v26 = &ScopeNAPEnabled;
                }
                else
                {
                  if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                    goto LABEL_26;
                  v26 = &ScopeDHCIDDisable;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                  goto LABEL_26;
                v26 = &ScopeDHCIDEnable;
              }
              goto LABEL_46;
            }
            if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
              goto LABEL_26;
            v29 = &ScopePBA_Activated;
          }
          else
          {
            if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
              goto LABEL_26;
            v29 = &ScopePBA_DeActivated;
          }
          LODWORD(v17) = McTemplateU0z_EventWriteTransfer(v28, v29, v14);
          goto LABEL_26;
        }
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v26 = &ScopeNAPDisabled;
      }
    }
    else if ( (_DWORD)v19 == 84 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v26 = &ScopeDNSDisable_Update_Client_NoReq;
    }
    else if ( (unsigned int)v19 > 0x4D )
    {
      v19 = (unsigned int)(v19 - 78);
      if ( (_DWORD)v19 )
      {
        v19 = (unsigned int)(v19 - 1);
        if ( (_DWORD)v19 )
        {
          v19 = (unsigned int)(v19 - 1);
          if ( (_DWORD)v19 )
          {
            v19 = (unsigned int)(v19 - 1);
            if ( (_DWORD)v19 )
            {
              v19 = (unsigned int)(v19 - 1);
              if ( (_DWORD)v19 )
              {
                if ( (_DWORD)v19 != 1 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                  goto LABEL_26;
                v26 = &ScopeDNSEnable_Update_Client_NoReq;
              }
              else
              {
                if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                  goto LABEL_26;
                v26 = &ScopeDNSDisable_Discard;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                goto LABEL_26;
              v26 = &ScopeDNSEnable_Discard;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
              goto LABEL_26;
            v26 = &ScopeDNSUpdate_Always;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v26 = &ScopeDNSUpdate_Req_by_Client;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v26 = &ScopeDNSDisable;
      }
    }
    else if ( (_DWORD)v19 == 77 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v26 = &ScopeDNSEnable;
    }
    else
    {
      v19 = (unsigned int)(v19 - 70);
      if ( (_DWORD)v19 )
      {
        v19 = (unsigned int)(v19 - 1);
        if ( (_DWORD)v19 )
        {
          v19 = (unsigned int)(v19 - 1);
          if ( (_DWORD)v19 )
          {
            v19 = (unsigned int)(v19 - 1);
            if ( (_DWORD)v19 )
            {
              v19 = (unsigned int)(v19 - 1);
              if ( (_DWORD)v19 )
              {
                LODWORD(v19) = v19 - 1;
                if ( (_DWORD)v19 )
                {
                  if ( (_DWORD)v19 != 1 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                    goto LABEL_26;
                  v20 = &ScopeOptionUpdate;
                  goto LABEL_23;
                }
                v17 = a4;
                do
                {
                  v24 = *(unsigned __int16 *)((char *)v17 + a5 - (_QWORD)a4);
                  LODWORD(v19) = *v17 - v24;
                  if ( (_DWORD)v19 )
                    break;
                  ++v17;
                }
                while ( v24 );
                if ( !(_DWORD)v19 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                  goto LABEL_26;
                v25 = &ScopeLeaseUpdate;
LABEL_42:
                LODWORD(v17) = McTemplateU0zzzz_EventWriteTransfer(
                                 v19,
                                 (_DWORD)v25,
                                 (_DWORD)v14,
                                 (_DWORD)a4,
                                 ClientDetails,
                                 a5);
                goto LABEL_26;
              }
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                goto LABEL_26;
              v26 = &ScopeDeActivated;
            }
            else
            {
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                goto LABEL_26;
              v26 = &ScopeActivated;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
              goto LABEL_26;
            v26 = &ScopeDeleted;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v26 = &ScopeModified;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v26 = &ScopeConfigured;
      }
    }
LABEL_46:
    v27 = (__int64)v14;
LABEL_47:
    LODWORD(v17) = McTemplateU0zz_EventWriteTransfer(v19, v26, v27, ClientDetails);
    goto LABEL_26;
  }
  if ( (unsigned int)v19 <= 0x70 )
  {
    if ( (_DWORD)v19 == 112 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v21 = (int)v14;
      v20 = &ReservationDNSEnable_Discard;
      v22 = (int)v11;
      goto LABEL_25;
    }
    if ( (unsigned int)v19 > 0x69 )
    {
      LODWORD(v19) = v19 - 106;
      if ( (_DWORD)v19 )
      {
        LODWORD(v19) = v19 - 1;
        if ( (_DWORD)v19 )
        {
          LODWORD(v19) = v19 - 1;
          if ( (_DWORD)v19 )
          {
            LODWORD(v19) = v19 - 1;
            if ( (_DWORD)v19 )
            {
              LODWORD(v19) = v19 - 1;
              if ( (_DWORD)v19 )
              {
                if ( (_DWORD)v19 != 1 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                  goto LABEL_26;
                v21 = (int)v14;
                v20 = &ReservationDNSUpdate_Always;
                v22 = (int)v11;
              }
              else
              {
                if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                  goto LABEL_26;
                v21 = (int)v14;
                v20 = &ReservationDNSUpdate_Req_by_Client;
                v22 = (int)v11;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
                goto LABEL_26;
              v21 = (int)v14;
              v20 = &ReservationDNSDisable;
              v22 = (int)v11;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
              goto LABEL_26;
            v21 = (int)v14;
            v20 = &ReservationDNSEnable;
            v22 = (int)v11;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
            goto LABEL_26;
          v21 = (int)v14;
          v20 = &ReservationDeleted;
          v22 = (int)v11;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v21 = (int)v14;
        v20 = &ReservationConfigured;
        v22 = (int)v11;
      }
      goto LABEL_25;
    }
    if ( (_DWORD)v19 == 105 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v27 = a6;
      v26 = &ServerOptionUpdate;
      goto LABEL_47;
    }
    v19 = (unsigned int)(v19 - 99);
    if ( !(_DWORD)v19 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v27 = (__int64)a3;
      v26 = &SuperScopeDeleted;
      goto LABEL_47;
    }
    LODWORD(v19) = v19 - 1;
    if ( !(_DWORD)v19 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v21 = (int)a4;
      v20 = &SuperScopeActivated;
      goto LABEL_24;
    }
    LODWORD(v19) = v19 - 1;
    if ( !(_DWORD)v19 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v21 = (int)a4;
      v20 = &SuperScopeDeActivated;
      goto LABEL_24;
    }
    LODWORD(v19) = v19 - 1;
    if ( !(_DWORD)v19 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
        goto LABEL_26;
      v21 = (int)a4;
      v20 = &SuperScopeDeleteTemp;
      goto LABEL_24;
    }
    LODWORD(v19) = v19 - 1;
    if ( (_DWORD)v19 )
    {
      if ( (_DWORD)v19 == 1 && (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
        LODWORD(v17) = McTemplateU0zzzz_EventWriteTransfer(
                         1,
                         (unsigned int)&ScopeDelayUpdate,
                         (_DWORD)a4,
                         (_DWORD)v14,
                         a5,
                         ClientDetails);
      goto LABEL_26;
    }
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
    {
      v21 = (int)a4;
      v20 = &SuperScopeDeletePerm;
      goto LABEL_24;
    }
    goto LABEL_26;
  }
  if ( (unsigned int)v19 > 0x77 )
  {
    v36 = v19 - 120;
    if ( v36 )
    {
      v19 = (unsigned int)(v36 - 44);
      if ( !(_DWORD)v19 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v26 = &ScopeDNSEnable_DisablePtrUpdates;
        goto LABEL_46;
      }
      v19 = (unsigned int)(v19 - 1);
      if ( !(_DWORD)v19 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v26 = &ScopeDNSDisable_DisablePtrUpdates;
        goto LABEL_46;
      }
      v19 = (unsigned int)(v19 - 2);
      if ( !(_DWORD)v19 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v27 = a6;
        v26 = &ServerOptionRemove;
        goto LABEL_47;
      }
      LODWORD(v19) = v19 - 1;
      if ( (_DWORD)v19 )
      {
        if ( (_DWORD)v19 == 1 && (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
          LODWORD(v17) = McTemplateU0zzzz_EventWriteTransfer(
                           1,
                           (unsigned int)&ReservationOptionRemove,
                           (_DWORD)v11,
                           (_DWORD)v14,
                           a6,
                           ClientDetails);
        goto LABEL_26;
      }
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
      {
        v20 = &ScopeOptionRemove;
LABEL_23:
        v21 = a6;
LABEL_24:
        v22 = (int)v14;
LABEL_25:
        LODWORD(v17) = McTemplateU0zzz_EventWriteTransfer(v19, (_DWORD)v20, v22, v21, ClientDetails);
      }
LABEL_26:
      v23 = 0;
      goto LABEL_27;
    }
    v17 = (unsigned __int16 *)FormatExclusionRange(a8, v39);
    v23 = v17;
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
    {
      v35 = &ScopeExclusionDeleted;
      goto LABEL_188;
    }
  }
  else
  {
    if ( (_DWORD)v19 != 119 )
    {
      LODWORD(v19) = v19 - 113;
      if ( !(_DWORD)v19 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v21 = (int)v14;
        v20 = &ReservationDNSDisable_Discard;
        v22 = (int)v11;
        goto LABEL_25;
      }
      LODWORD(v19) = v19 - 1;
      if ( !(_DWORD)v19 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v21 = (int)v14;
        v20 = &ReservationDNSEnableUpdate_No_Req_by_Client;
        v22 = (int)v11;
        goto LABEL_25;
      }
      LODWORD(v19) = v19 - 1;
      if ( !(_DWORD)v19 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v21 = (int)v14;
        v20 = &ReservationDNSDisableUpdate_No_Req_by_Client;
        v22 = (int)v11;
        goto LABEL_25;
      }
      v30 = v19 - 1;
      if ( !v30 )
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
          LODWORD(v17) = McTemplateU0zzzz_EventWriteTransfer(
                           0,
                           (unsigned int)&ReservationOptionUpdate,
                           (_DWORD)v11,
                           (_DWORD)v14,
                           a6,
                           ClientDetails);
        goto LABEL_26;
      }
      v31 = (unsigned int)(v30 - 1);
      if ( (_DWORD)v31 )
      {
        if ( (_DWORD)v31 != 1 || (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v32 = (struct _EVENT_DATA_DESCRIPTOR *)&v40;
        v33 = &ServerPBA_Activated;
      }
      else
      {
        if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
          goto LABEL_26;
        v32 = (struct _EVENT_DATA_DESCRIPTOR *)&v39;
        v33 = &ServerPBA_DeActivated;
      }
      LODWORD(v17) = McGenEventWrite_EventWriteTransfer(v31, (const EVENT_DESCRIPTOR *)v33, v18, 1u, v32);
      goto LABEL_26;
    }
    v17 = (unsigned __int16 *)FormatExclusionRange(a8, v39);
    v23 = v17;
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
    {
      v35 = &ScopeExclusionAdded;
LABEL_188:
      LODWORD(v17) = McTemplateU0zzz_EventWriteTransfer(v34, (_DWORD)v35, (_DWORD)v17, (_DWORD)v14, ClientDetails);
    }
  }
LABEL_27:
  if ( !v38 )
    LODWORD(v17) = RpcRevertToSelf();
  if ( v14 )
    LODWORD(v17) = HeapFree(gDhcpHeap, 0, v14);
  if ( v11 )
    LODWORD(v17) = HeapFree(gDhcpHeap, 0, v11);
  if ( v23 )
    LODWORD(v17) = HeapFree(gDhcpHeap, 0, v23);
  return (int)v17;
}

```

## disassembly

```asm
0x18007f72c  mov     [rsp+arg_0], rbx
0x18007f731  push    rbp
0x18007f732  push    rsi
0x18007f733  push    rdi
0x18007f734  push    r12
0x18007f736  push    r13
0x18007f738  push    r14
0x18007f73a  push    r15
0x18007f73c  sub     rsp, 70h
0x18007f740  mov     rax, cs:__security_cookie
0x18007f747  xor     rax, rsp
0x18007f74a  mov     [rsp+0A8h+var_48], rax
0x18007f74f  mov     rax, [rsp+0A8h+arg_30]
0x18007f757  mov     rsi, r9
0x18007f75a  mov     r12, [rsp+0A8h+arg_20]
0x18007f762  mov     r15, r8
0x18007f765  mov     r14, [rsp+0A8h+arg_28]
0x18007f76d  mov     r13, [rsp+0A8h+arg_38]
0x18007f775  mov     [rsp+0A8h+var_70], rax
0x18007f77a  mov     rax, [rsp+0A8h+arg_40]
0x18007f782  mov     [rsp+0A8h+var_68], rax
0x18007f787  xor     eax, eax
0x18007f789  mov     [rsp+0A8h+var_58], rcx
0x18007f78e  mov     ebp, eax
0x18007f790  mov     [rsp+0A8h+lpMem], rax
0x18007f795  test    r8, r8
0x18007f798  jz      short loc_18007F7AA
0x18007f79a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f79e  inc     rbx
0x18007f7a1  cmp     [r8+rbx*2], ax
0x18007f7a6  jnz     short loc_18007F79E
0x18007f7a8  jmp     short loc_18007F7AD
0x18007f7aa  mov     rbx, rax
0x18007f7ad  mov     ecx, edx; netlong
0x18007f7af  call    cs:__imp_ntohl
0x18007f7b6  nop     dword ptr [rax+rax+00h]
0x18007f7bb  mov     r8, rbx
0x18007f7be  mov     rdx, r15
0x18007f7c1  mov     ecx, eax
0x18007f7c3  call    FormatIPandName
0x18007f7c8  mov     rbx, rax
0x18007f7cb  call    GetClientDetails
0x18007f7d0  mov     rdi, rax
0x18007f7d3  mov     rax, [rsp+0A8h+var_70]
0x18007f7d8  test    rax, rax
0x18007f7db  jz      short loc_18007F7FB
0x18007f7dd  mov     ecx, [rax+8]; netlong
0x18007f7e0  call    cs:__imp_ntohl
0x18007f7e7  nop     dword ptr [rax+rax+00h]
0x18007f7ec  xor     r8d, r8d
0x18007f7ef  xor     edx, edx
0x18007f7f1  mov     ecx, eax
0x18007f7f3  call    FormatIPandName
0x18007f7f8  mov     rbp, rax
0x18007f7fb  xor     ecx, ecx; BindingHandle
0x18007f7fd  call    cs:__imp_RpcImpersonateClient
0x18007f804  nop     dword ptr [rax+rax+00h]
0x18007f809  mov     rcx, [rsp+0A8h+var_58]
0x18007f80e  mov     dword ptr [rsp+0A8h+var_70], eax
0x18007f812  movzx   ecx, word ptr [rcx]
0x18007f815  cmp     ecx, 62h ; 'b'
0x18007f818  ja      loc_18007FCBF
0x18007f81e  jz      loc_18007FCA3
0x18007f824  cmp     ecx, 54h ; 'T'
0x18007f827  ja      loc_18007FAEE
0x18007f82d  jz      loc_18007FAD5
0x18007f833  cmp     ecx, 4Dh ; 'M'
0x18007f836  ja      loc_18007FA19
0x18007f83c  jz      loc_18007FA03
0x18007f842  sub     ecx, 46h ; 'F'
0x18007f845  jz      loc_18007F9ED
0x18007f84b  sub     ecx, 1
0x18007f84e  jz      loc_18007F9D7
0x18007f854  sub     ecx, 1
0x18007f857  jz      loc_18007F9C1
0x18007f85d  sub     ecx, 1
0x18007f860  jz      loc_18007F9AB
0x18007f866  sub     ecx, 1
0x18007f869  jz      loc_18007F987
0x18007f86f  sub     ecx, 1
0x18007f872  jz      loc_18007F932
0x18007f878  cmp     ecx, 1
0x18007f87b  jnz     short loc_18007F89D
0x18007f87d  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f884  jz      short loc_18007F89D
0x18007f886  lea     rdx, ScopeOptionUpdate
0x18007f88d  mov     r9, r14
0x18007f890  mov     r8, rbx
0x18007f893  mov     [rsp+0A8h+var_88], rdi
0x18007f898  call    McTemplateU0zzz_EventWriteTransfer
0x18007f89d  mov     rsi, [rsp+0A8h+lpMem]
0x18007f8a2  cmp     dword ptr [rsp+0A8h+var_70], 0
0x18007f8a7  jnz     short loc_18007F8B5
0x18007f8a9  call    cs:__imp_RpcRevertToSelf
0x18007f8b0  nop     dword ptr [rax+rax+00h]
0x18007f8b5  test    rbx, rbx
0x18007f8b8  jz      short loc_18007F8D2
0x18007f8ba  mov     rcx, cs:gDhcpHeap; hHeap
0x18007f8c1  mov     r8, rbx; lpMem
0x18007f8c4  xor     edx, edx; dwFlags
0x18007f8c6  call    cs:__imp_HeapFree
0x18007f8cd  nop     dword ptr [rax+rax+00h]
0x18007f8d2  test    rbp, rbp
0x18007f8d5  jz      short loc_18007F8EF
0x18007f8d7  mov     rcx, cs:gDhcpHeap; hHeap
0x18007f8de  mov     r8, rbp; lpMem
0x18007f8e1  xor     edx, edx; dwFlags
0x18007f8e3  call    cs:__imp_HeapFree
0x18007f8ea  nop     dword ptr [rax+rax+00h]
0x18007f8ef  test    rsi, rsi
0x18007f8f2  jz      short loc_18007F90C
0x18007f8f4  mov     rcx, cs:gDhcpHeap; hHeap
0x18007f8fb  mov     r8, rsi; lpMem
0x18007f8fe  xor     edx, edx; dwFlags
0x18007f900  call    cs:__imp_HeapFree
0x18007f907  nop     dword ptr [rax+rax+00h]
0x18007f90c  mov     rcx, [rsp+0A8h+var_48]
0x18007f911  xor     rcx, rsp; StackCookie
0x18007f914  call    __security_check_cookie
0x18007f919  mov     rbx, [rsp+0A8h+arg_0]
0x18007f921  add     rsp, 70h
0x18007f925  pop     r15
0x18007f927  pop     r14
0x18007f929  pop     r13
0x18007f92b  pop     r12
0x18007f92d  pop     rdi
0x18007f92e  pop     rsi
0x18007f92f  pop     rbp
0x18007f930  retn
0x18007f932  mov     rdx, r12
0x18007f935  mov     rax, rsi
0x18007f938  sub     rdx, rsi
0x18007f93b  movzx   ecx, word ptr [rax]
0x18007f93e  movzx   r8d, word ptr [rax+rdx]
0x18007f943  sub     ecx, r8d
0x18007f946  jnz     short loc_18007F951
0x18007f948  add     rax, 2
0x18007f94c  test    r8d, r8d
0x18007f94f  jnz     short loc_18007F93B
0x18007f951  test    ecx, ecx
0x18007f953  jz      loc_18007F89D
0x18007f959  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f960  jz      loc_18007F89D
0x18007f966  lea     rdx, ScopeLeaseUpdate
0x18007f96d  mov     [rsp+0A8h+var_80], r12
0x18007f972  mov     r9, rsi
0x18007f975  mov     [rsp+0A8h+var_88], rdi
0x18007f97a  mov     r8, rbx
0x18007f97d  call    McTemplateU0zzzz_EventWriteTransfer
0x18007f982  jmp     loc_18007F89D
0x18007f987  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f98e  jz      loc_18007F89D
0x18007f994  lea     rdx, ScopeDeActivated
0x18007f99b  mov     r8, rbx
0x18007f99e  mov     r9, rdi
0x18007f9a1  call    McTemplateU0zz_EventWriteTransfer
0x18007f9a6  jmp     loc_18007F89D
0x18007f9ab  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f9b2  jz      loc_18007F89D
0x18007f9b8  lea     rdx, ScopeActivated
0x18007f9bf  jmp     short loc_18007F99B
0x18007f9c1  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f9c8  jz      loc_18007F89D
0x18007f9ce  lea     rdx, ScopeDeleted
0x18007f9d5  jmp     short loc_18007F99B
0x18007f9d7  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f9de  jz      loc_18007F89D
0x18007f9e4  lea     rdx, ScopeModified
0x18007f9eb  jmp     short loc_18007F99B
0x18007f9ed  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f9f4  jz      loc_18007F89D
0x18007f9fa  lea     rdx, ScopeConfigured
0x18007fa01  jmp     short loc_18007F99B
0x18007fa03  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fa0a  jz      loc_18007F89D
0x18007fa10  lea     rdx, ScopeDNSEnable
0x18007fa17  jmp     short loc_18007F99B
0x18007fa19  sub     ecx, 4Eh ; 'N'
0x18007fa1c  jz      loc_18007FABC
0x18007fa22  sub     ecx, 1
0x18007fa25  jz      short loc_18007FAA3
0x18007fa27  sub     ecx, 1
0x18007fa2a  jz      short loc_18007FA8A
0x18007fa2c  sub     ecx, 1
0x18007fa2f  jz      short loc_18007FA71
0x18007fa31  sub     ecx, 1
0x18007fa34  jz      short loc_18007FA58
0x18007fa36  cmp     ecx, 1
0x18007fa39  jnz     loc_18007F89D
0x18007fa3f  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fa46  jz      loc_18007F89D
0x18007fa4c  lea     rdx, ScopeDNSEnable_Update_Client_NoReq
0x18007fa53  jmp     loc_18007F99B
0x18007fa58  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fa5f  jz      loc_18007F89D
0x18007fa65  lea     rdx, ScopeDNSDisable_Discard
0x18007fa6c  jmp     loc_18007F99B
0x18007fa71  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fa78  jz      loc_18007F89D
0x18007fa7e  lea     rdx, ScopeDNSEnable_Discard
0x18007fa85  jmp     loc_18007F99B
0x18007fa8a  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fa91  jz      loc_18007F89D
0x18007fa97  lea     rdx, ScopeDNSUpdate_Always
0x18007fa9e  jmp     loc_18007F99B
0x18007faa3  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007faaa  jz      loc_18007F89D
0x18007fab0  lea     rdx, ScopeDNSUpdate_Req_by_Client
0x18007fab7  jmp     loc_18007F99B
0x18007fabc  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fac3  jz      loc_18007F89D
0x18007fac9  lea     rdx, ScopeDNSDisable
0x18007fad0  jmp     loc_18007F99B
0x18007fad5  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fadc  jz      loc_18007F89D
0x18007fae2  lea     rdx, ScopeDNSDisable_Update_Client_NoReq
0x18007fae9  jmp     loc_18007F99B
0x18007faee  cmp     ecx, 5Bh ; '['
0x18007faf1  ja      loc_18007FBD7
0x18007faf7  jz      loc_18007FBBE
0x18007fafd  sub     ecx, 55h ; 'U'
0x18007fb00  jz      loc_18007FBA8
0x18007fb06  sub     ecx, 1
0x18007fb09  jz      short loc_18007FB87
0x18007fb0b  sub     ecx, 1
0x18007fb0e  jz      short loc_18007FB6E
0x18007fb10  sub     ecx, 1
0x18007fb13  jz      short loc_18007FB55
0x18007fb15  sub     ecx, 1
0x18007fb18  jz      short loc_18007FB3C
0x18007fb1a  cmp     ecx, 1
0x18007fb1d  jnz     loc_18007F89D
0x18007fb23  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb2a  jz      loc_18007F89D
0x18007fb30  lea     rdx, ScopeNAPEnabled
0x18007fb37  jmp     loc_18007F99B
0x18007fb3c  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb43  jz      loc_18007F89D
0x18007fb49  lea     rdx, ScopeSupportType
0x18007fb50  jmp     loc_18007F96D
0x18007fb55  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb5c  jz      loc_18007F89D
0x18007fb62  lea     rdx, ScopeDHCIDDisable
0x18007fb69  jmp     loc_18007F99B
0x18007fb6e  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb75  jz      loc_18007F89D
0x18007fb7b  lea     rdx, ScopeDHCIDEnable
0x18007fb82  jmp     loc_18007F99B
0x18007fb87  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb8e  jz      loc_18007F89D
0x18007fb94  lea     rdx, ScopePBA_Activated
0x18007fb9b  mov     r8, rbx
0x18007fb9e  call    McTemplateU0z_EventWriteTransfer
0x18007fba3  jmp     loc_18007F89D
0x18007fba8  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fbaf  jz      loc_18007F89D
0x18007fbb5  lea     rdx, ScopePBA_DeActivated
0x18007fbbc  jmp     short loc_18007FB9B
0x18007fbbe  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fbc5  jz      loc_18007F89D
0x18007fbcb  lea     rdx, ScopeNAPDisabled
0x18007fbd2  jmp     loc_18007F99B
0x18007fbd7  sub     ecx, 5Ch ; '\'
0x18007fbda  jz      loc_18007FC87
0x18007fbe0  sub     ecx, 1
0x18007fbe3  jz      loc_18007FC6E
0x18007fbe9  sub     ecx, 1
0x18007fbec  jz      short loc_18007FC4F
0x18007fbee  sub     ecx, 1
0x18007fbf1  jz      short loc_18007FC36
0x18007fbf3  sub     ecx, 1
0x18007fbf6  jz      short loc_18007FC1D
0x18007fbf8  cmp     ecx, 1
0x18007fbfb  jnz     loc_18007F89D
0x18007fc01  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc08  jz      loc_18007F89D
0x18007fc0e  mov     r9, rsi
0x18007fc11  lea     rdx, SuperScopeAddExisting
0x18007fc18  jmp     loc_18007F890
0x18007fc1d  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc24  jz      loc_18007F89D
0x18007fc2a  lea     rdx, MulticastScopeDeleted
0x18007fc31  jmp     loc_18007F99B
0x18007fc36  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc3d  jz      loc_18007F89D
0x18007fc43  lea     rdx, MulticastScopeConfigured
0x18007fc4a  jmp     loc_18007F99B
0x18007fc4f  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc56  jz      loc_18007F89D
0x18007fc5c  mov     r9, rbx
0x18007fc5f  lea     rdx, ScopeNAPProfileDeleted
0x18007fc66  mov     r8, rsi
0x18007fc69  jmp     loc_18007F893
0x18007fc6e  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc75  jz      loc_18007F89D
0x18007fc7b  lea     rdx, ScopeNAPProfileModified
0x18007fc82  jmp     loc_18007F96D
0x18007fc87  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc8e  jz      loc_18007F89D
0x18007fc94  mov     r9, rsi
  ... truncated ...
```
