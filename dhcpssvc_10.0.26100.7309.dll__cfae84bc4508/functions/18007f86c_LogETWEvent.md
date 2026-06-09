# LogETWEvent

- ea: `0x18007f86c`
- end: `0x180080243`
- name: `LogETWEvent`
- size: `2519`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d3dc`
- `0x18002e5f0`
- `0x1800453a0`
- `0x180045b70`
- `0x18004884c`
- `0x180048cf0`
- `0x18004a5fc`
- `0x18004a744`
- `0x18004aba0`
- `0x18004ad58`
- `0x18004b040`
- `0x18004b5dc`
- `0x18004b9e0`
- `0x18004bcf0`
- `0x18004c690`
- `0x18007dce4`
- `0x180081d98`
- `0x18008204c`
- `0x180082708`

## callees

- `0x1800519fc`
- `0x180058530`
- `0x18007e164`
- `0x18007e7c8`
- `0x18007f580`
- `0x18007f86c`
- `0x18008318c`
- `0x1800834a4`
- `0x180083838`
- `0x1800cc9e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18007f93d`
- `RPCRT4!RpcImpersonateClient` at `0x18007f93d`
- `RPCRT4!RpcRevertToSelf` at `0x18007f9e9`
- `RPCRT4!RpcRevertToSelf` at `0x18007f9e9`
- `WS2_32!__imp_ntohl` at `0x18007f8ef`
- `WS2_32!__imp_ntohl` at `0x18007f920`
- `WS2_32!__imp_ntohl` at `0x18007f8ef`
- `WS2_32!__imp_ntohl` at `0x18007f920`
- `KERNEL32!HeapFree` at `0x18007fa06`
- `KERNEL32!HeapFree` at `0x18007fa23`
- `KERNEL32!HeapFree` at `0x18007fa40`
- `KERNEL32!HeapFree` at `0x18007fa06`
- `KERNEL32!HeapFree` at `0x18007fa23`
- `KERNEL32!HeapFree` at `0x18007fa40`

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
0x18007f86c  mov     [rsp+arg_0], rbx
0x18007f871  push    rbp
0x18007f872  push    rsi
0x18007f873  push    rdi
0x18007f874  push    r12
0x18007f876  push    r13
0x18007f878  push    r14
0x18007f87a  push    r15
0x18007f87c  sub     rsp, 70h
0x18007f880  mov     rax, cs:__security_cookie
0x18007f887  xor     rax, rsp
0x18007f88a  mov     [rsp+0A8h+var_48], rax
0x18007f88f  mov     rax, [rsp+0A8h+arg_30]
0x18007f897  mov     rsi, r9
0x18007f89a  mov     r12, [rsp+0A8h+arg_20]
0x18007f8a2  mov     r15, r8
0x18007f8a5  mov     r14, [rsp+0A8h+arg_28]
0x18007f8ad  mov     r13, [rsp+0A8h+arg_38]
0x18007f8b5  mov     [rsp+0A8h+var_70], rax
0x18007f8ba  mov     rax, [rsp+0A8h+arg_40]
0x18007f8c2  mov     [rsp+0A8h+var_68], rax
0x18007f8c7  xor     eax, eax
0x18007f8c9  mov     [rsp+0A8h+var_58], rcx
0x18007f8ce  mov     ebp, eax
0x18007f8d0  mov     [rsp+0A8h+lpMem], rax
0x18007f8d5  test    r8, r8
0x18007f8d8  jz      short loc_18007F8EA
0x18007f8da  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f8de  inc     rbx
0x18007f8e1  cmp     [r8+rbx*2], ax
0x18007f8e6  jnz     short loc_18007F8DE
0x18007f8e8  jmp     short loc_18007F8ED
0x18007f8ea  mov     rbx, rax
0x18007f8ed  mov     ecx, edx; netlong
0x18007f8ef  call    cs:__imp_ntohl
0x18007f8f6  nop     dword ptr [rax+rax+00h]
0x18007f8fb  mov     r8, rbx
0x18007f8fe  mov     rdx, r15
0x18007f901  mov     ecx, eax
0x18007f903  call    FormatIPandName
0x18007f908  mov     rbx, rax
0x18007f90b  call    GetClientDetails
0x18007f910  mov     rdi, rax
0x18007f913  mov     rax, [rsp+0A8h+var_70]
0x18007f918  test    rax, rax
0x18007f91b  jz      short loc_18007F93B
0x18007f91d  mov     ecx, [rax+8]; netlong
0x18007f920  call    cs:__imp_ntohl
0x18007f927  nop     dword ptr [rax+rax+00h]
0x18007f92c  xor     r8d, r8d
0x18007f92f  xor     edx, edx
0x18007f931  mov     ecx, eax
0x18007f933  call    FormatIPandName
0x18007f938  mov     rbp, rax
0x18007f93b  xor     ecx, ecx; BindingHandle
0x18007f93d  call    cs:__imp_RpcImpersonateClient
0x18007f944  nop     dword ptr [rax+rax+00h]
0x18007f949  mov     rcx, [rsp+0A8h+var_58]
0x18007f94e  mov     dword ptr [rsp+0A8h+var_70], eax
0x18007f952  movzx   ecx, word ptr [rcx]
0x18007f955  cmp     ecx, 62h ; 'b'
0x18007f958  ja      loc_18007FDFF
0x18007f95e  jz      loc_18007FDE3
0x18007f964  cmp     ecx, 54h ; 'T'
0x18007f967  ja      loc_18007FC2E
0x18007f96d  jz      loc_18007FC15
0x18007f973  cmp     ecx, 4Dh ; 'M'
0x18007f976  ja      loc_18007FB59
0x18007f97c  jz      loc_18007FB43
0x18007f982  sub     ecx, 46h ; 'F'
0x18007f985  jz      loc_18007FB2D
0x18007f98b  sub     ecx, 1
0x18007f98e  jz      loc_18007FB17
0x18007f994  sub     ecx, 1
0x18007f997  jz      loc_18007FB01
0x18007f99d  sub     ecx, 1
0x18007f9a0  jz      loc_18007FAEB
0x18007f9a6  sub     ecx, 1
0x18007f9a9  jz      loc_18007FAC7
0x18007f9af  sub     ecx, 1
0x18007f9b2  jz      loc_18007FA72
0x18007f9b8  cmp     ecx, 1
0x18007f9bb  jnz     short loc_18007F9DD
0x18007f9bd  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007f9c4  jz      short loc_18007F9DD
0x18007f9c6  lea     rdx, ScopeOptionUpdate
0x18007f9cd  mov     r9, r14
0x18007f9d0  mov     r8, rbx
0x18007f9d3  mov     [rsp+0A8h+var_88], rdi
0x18007f9d8  call    McTemplateU0zzz_EventWriteTransfer
0x18007f9dd  mov     rsi, [rsp+0A8h+lpMem]
0x18007f9e2  cmp     dword ptr [rsp+0A8h+var_70], 0
0x18007f9e7  jnz     short loc_18007F9F5
0x18007f9e9  call    cs:__imp_RpcRevertToSelf
0x18007f9f0  nop     dword ptr [rax+rax+00h]
0x18007f9f5  test    rbx, rbx
0x18007f9f8  jz      short loc_18007FA12
0x18007f9fa  mov     rcx, cs:gDhcpHeap; hHeap
0x18007fa01  mov     r8, rbx; lpMem
0x18007fa04  xor     edx, edx; dwFlags
0x18007fa06  call    cs:__imp_HeapFree
0x18007fa0d  nop     dword ptr [rax+rax+00h]
0x18007fa12  test    rbp, rbp
0x18007fa15  jz      short loc_18007FA2F
0x18007fa17  mov     rcx, cs:gDhcpHeap; hHeap
0x18007fa1e  mov     r8, rbp; lpMem
0x18007fa21  xor     edx, edx; dwFlags
0x18007fa23  call    cs:__imp_HeapFree
0x18007fa2a  nop     dword ptr [rax+rax+00h]
0x18007fa2f  test    rsi, rsi
0x18007fa32  jz      short loc_18007FA4C
0x18007fa34  mov     rcx, cs:gDhcpHeap; hHeap
0x18007fa3b  mov     r8, rsi; lpMem
0x18007fa3e  xor     edx, edx; dwFlags
0x18007fa40  call    cs:__imp_HeapFree
0x18007fa47  nop     dword ptr [rax+rax+00h]
0x18007fa4c  mov     rcx, [rsp+0A8h+var_48]
0x18007fa51  xor     rcx, rsp; StackCookie
0x18007fa54  call    __security_check_cookie
0x18007fa59  mov     rbx, [rsp+0A8h+arg_0]
0x18007fa61  add     rsp, 70h
0x18007fa65  pop     r15
0x18007fa67  pop     r14
0x18007fa69  pop     r13
0x18007fa6b  pop     r12
0x18007fa6d  pop     rdi
0x18007fa6e  pop     rsi
0x18007fa6f  pop     rbp
0x18007fa70  retn
0x18007fa72  mov     rdx, r12
0x18007fa75  mov     rax, rsi
0x18007fa78  sub     rdx, rsi
0x18007fa7b  movzx   ecx, word ptr [rax]
0x18007fa7e  movzx   r8d, word ptr [rax+rdx]
0x18007fa83  sub     ecx, r8d
0x18007fa86  jnz     short loc_18007FA91
0x18007fa88  add     rax, 2
0x18007fa8c  test    r8d, r8d
0x18007fa8f  jnz     short loc_18007FA7B
0x18007fa91  test    ecx, ecx
0x18007fa93  jz      loc_18007F9DD
0x18007fa99  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007faa0  jz      loc_18007F9DD
0x18007faa6  lea     rdx, ScopeLeaseUpdate
0x18007faad  mov     [rsp+0A8h+var_80], r12
0x18007fab2  mov     r9, rsi
0x18007fab5  mov     [rsp+0A8h+var_88], rdi
0x18007faba  mov     r8, rbx
0x18007fabd  call    McTemplateU0zzzz_EventWriteTransfer
0x18007fac2  jmp     loc_18007F9DD
0x18007fac7  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007face  jz      loc_18007F9DD
0x18007fad4  lea     rdx, ScopeDeActivated
0x18007fadb  mov     r8, rbx
0x18007fade  mov     r9, rdi
0x18007fae1  call    McTemplateU0zz_EventWriteTransfer
0x18007fae6  jmp     loc_18007F9DD
0x18007faeb  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007faf2  jz      loc_18007F9DD
0x18007faf8  lea     rdx, ScopeActivated
0x18007faff  jmp     short loc_18007FADB
0x18007fb01  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb08  jz      loc_18007F9DD
0x18007fb0e  lea     rdx, ScopeDeleted
0x18007fb15  jmp     short loc_18007FADB
0x18007fb17  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb1e  jz      loc_18007F9DD
0x18007fb24  lea     rdx, ScopeModified
0x18007fb2b  jmp     short loc_18007FADB
0x18007fb2d  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb34  jz      loc_18007F9DD
0x18007fb3a  lea     rdx, ScopeConfigured
0x18007fb41  jmp     short loc_18007FADB
0x18007fb43  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb4a  jz      loc_18007F9DD
0x18007fb50  lea     rdx, ScopeDNSEnable
0x18007fb57  jmp     short loc_18007FADB
0x18007fb59  sub     ecx, 4Eh ; 'N'
0x18007fb5c  jz      loc_18007FBFC
0x18007fb62  sub     ecx, 1
0x18007fb65  jz      short loc_18007FBE3
0x18007fb67  sub     ecx, 1
0x18007fb6a  jz      short loc_18007FBCA
0x18007fb6c  sub     ecx, 1
0x18007fb6f  jz      short loc_18007FBB1
0x18007fb71  sub     ecx, 1
0x18007fb74  jz      short loc_18007FB98
0x18007fb76  cmp     ecx, 1
0x18007fb79  jnz     loc_18007F9DD
0x18007fb7f  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb86  jz      loc_18007F9DD
0x18007fb8c  lea     rdx, ScopeDNSEnable_Update_Client_NoReq
0x18007fb93  jmp     loc_18007FADB
0x18007fb98  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fb9f  jz      loc_18007F9DD
0x18007fba5  lea     rdx, ScopeDNSDisable_Discard
0x18007fbac  jmp     loc_18007FADB
0x18007fbb1  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fbb8  jz      loc_18007F9DD
0x18007fbbe  lea     rdx, ScopeDNSEnable_Discard
0x18007fbc5  jmp     loc_18007FADB
0x18007fbca  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fbd1  jz      loc_18007F9DD
0x18007fbd7  lea     rdx, ScopeDNSUpdate_Always
0x18007fbde  jmp     loc_18007FADB
0x18007fbe3  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fbea  jz      loc_18007F9DD
0x18007fbf0  lea     rdx, ScopeDNSUpdate_Req_by_Client
0x18007fbf7  jmp     loc_18007FADB
0x18007fbfc  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc03  jz      loc_18007F9DD
0x18007fc09  lea     rdx, ScopeDNSDisable
0x18007fc10  jmp     loc_18007FADB
0x18007fc15  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc1c  jz      loc_18007F9DD
0x18007fc22  lea     rdx, ScopeDNSDisable_Update_Client_NoReq
0x18007fc29  jmp     loc_18007FADB
0x18007fc2e  cmp     ecx, 5Bh ; '['
0x18007fc31  ja      loc_18007FD17
0x18007fc37  jz      loc_18007FCFE
0x18007fc3d  sub     ecx, 55h ; 'U'
0x18007fc40  jz      loc_18007FCE8
0x18007fc46  sub     ecx, 1
0x18007fc49  jz      short loc_18007FCC7
0x18007fc4b  sub     ecx, 1
0x18007fc4e  jz      short loc_18007FCAE
0x18007fc50  sub     ecx, 1
0x18007fc53  jz      short loc_18007FC95
0x18007fc55  sub     ecx, 1
0x18007fc58  jz      short loc_18007FC7C
0x18007fc5a  cmp     ecx, 1
0x18007fc5d  jnz     loc_18007F9DD
0x18007fc63  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc6a  jz      loc_18007F9DD
0x18007fc70  lea     rdx, ScopeNAPEnabled
0x18007fc77  jmp     loc_18007FADB
0x18007fc7c  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc83  jz      loc_18007F9DD
0x18007fc89  lea     rdx, ScopeSupportType
0x18007fc90  jmp     loc_18007FAAD
0x18007fc95  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fc9c  jz      loc_18007F9DD
0x18007fca2  lea     rdx, ScopeDHCIDDisable
0x18007fca9  jmp     loc_18007FADB
0x18007fcae  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fcb5  jz      loc_18007F9DD
0x18007fcbb  lea     rdx, ScopeDHCIDEnable
0x18007fcc2  jmp     loc_18007FADB
0x18007fcc7  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fcce  jz      loc_18007F9DD
0x18007fcd4  lea     rdx, ScopePBA_Activated
0x18007fcdb  mov     r8, rbx
0x18007fcde  call    McTemplateU0z_EventWriteTransfer
0x18007fce3  jmp     loc_18007F9DD
0x18007fce8  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fcef  jz      loc_18007F9DD
0x18007fcf5  lea     rdx, ScopePBA_DeActivated
0x18007fcfc  jmp     short loc_18007FCDB
0x18007fcfe  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fd05  jz      loc_18007F9DD
0x18007fd0b  lea     rdx, ScopeNAPDisabled
0x18007fd12  jmp     loc_18007FADB
0x18007fd17  sub     ecx, 5Ch ; '\'
0x18007fd1a  jz      loc_18007FDC7
0x18007fd20  sub     ecx, 1
0x18007fd23  jz      loc_18007FDAE
0x18007fd29  sub     ecx, 1
0x18007fd2c  jz      short loc_18007FD8F
0x18007fd2e  sub     ecx, 1
0x18007fd31  jz      short loc_18007FD76
0x18007fd33  sub     ecx, 1
0x18007fd36  jz      short loc_18007FD5D
0x18007fd38  cmp     ecx, 1
0x18007fd3b  jnz     loc_18007F9DD
0x18007fd41  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fd48  jz      loc_18007F9DD
0x18007fd4e  mov     r9, rsi
0x18007fd51  lea     rdx, SuperScopeAddExisting
0x18007fd58  jmp     loc_18007F9D0
0x18007fd5d  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fd64  jz      loc_18007F9DD
0x18007fd6a  lea     rdx, MulticastScopeDeleted
0x18007fd71  jmp     loc_18007FADB
0x18007fd76  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fd7d  jz      loc_18007F9DD
0x18007fd83  lea     rdx, MulticastScopeConfigured
0x18007fd8a  jmp     loc_18007FADB
0x18007fd8f  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fd96  jz      loc_18007F9DD
0x18007fd9c  mov     r9, rbx
0x18007fd9f  lea     rdx, ScopeNAPProfileDeleted
0x18007fda6  mov     r8, rsi
0x18007fda9  jmp     loc_18007F9D3
0x18007fdae  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fdb5  jz      loc_18007F9DD
0x18007fdbb  lea     rdx, ScopeNAPProfileModified
0x18007fdc2  jmp     loc_18007FAAD
0x18007fdc7  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x18007fdce  jz      loc_18007F9DD
0x18007fdd4  mov     r9, rsi
  ... truncated ...
```
