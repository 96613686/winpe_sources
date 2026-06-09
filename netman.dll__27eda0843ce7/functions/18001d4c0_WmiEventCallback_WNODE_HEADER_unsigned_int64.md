# WmiEventCallback(_WNODE_HEADER *,unsigned __int64)

- ea: `0x18001d4c0`
- end: `0x18001d68f`
- name: `?WmiEventCallback@@YAXPEAU_WNODE_HEADER@@_K@Z`
- size: `463`
- prototype: `void __fastcall(struct _WNODE_HEADER *, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001710`
- `0x1800052b4`
- `0x18000538c`
- `0x180019200`
- `0x180019c68`
- `0x18001d4c0`
- `0x18001f920`
- `0x18001fe84`
- `0x180020224`
- `0x180032c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001d55f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001d55f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d59a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d59a`

## pseudocode

```c
void __fastcall WmiEventCallback(struct _WNODE_HEADER *a1)
{
  PVOID *v2; // rcx
  const wchar_t *v3; // rcx
  wchar_t *v4; // rax
  const OLECHAR *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // edi
  __int64 v9; // rax
  struct CONMAN_EVENT *v10; // rax
  struct CONMAN_EVENT *v11; // rbx
  GUID v12; // xmm0
  GUID pclsid; // [rsp+20h] [rbp-28h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      WPP_SF_d(v2[2], 27, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, a1->Flags);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (a1->Flags & 2) != 0 )
  {
    v3 = (const wchar_t *)((char *)a1 + a1[1].Version);
    pclsid = 0;
    v4 = wcsrchr(v3, 0x7Bu);
    v5 = v4;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v4);
    if ( CLSIDFromString(v5, &pclsid) >= 0 )
    {
      v7 = *(_QWORD *)&a1->Guid.Data1 - *(_QWORD *)&GUID_NDIS_STATUS_MEDIA_CONNECT.Data1;
      if ( !v7 )
        v7 = *(_QWORD *)a1->Guid.Data4 - *(_QWORD *)GUID_NDIS_STATUS_MEDIA_CONNECT.Data4;
      if ( v7 )
      {
        v9 = *(_QWORD *)&a1->Guid.Data1 - *(_QWORD *)&GUID_NDIS_STATUS_MEDIA_DISCONNECT.Data1;
        if ( !v9 )
          v9 = *(_QWORD *)a1->Guid.Data4 - *(_QWORD *)GUID_NDIS_STATUS_MEDIA_DISCONNECT.Data4;
        if ( v9 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v6);
          return;
        }
        v8 = 7;
      }
      else
      {
        v8 = 2;
      }
      v10 = (struct CONMAN_EVENT *)MemAlloc(0xE68u);
      v11 = v10;
      if ( v10 )
      {
        *(_QWORD *)v10 = 0;
        *((_DWORD *)v10 + 2) = 2;
        v12 = pclsid;
        *((_DWORD *)v10 + 1) = 6;
        *((_DWORD *)v10 + 8) = v8;
        *((GUID *)v10 + 1) = v12;
        *(_DWORD *)v10 = 1;
        if ( !(unsigned int)QueueUserWorkItemInThread((unsigned int (*)(struct NMEVENT_HEADER *))LanEventWorkItem, v10) )
          FreeConmanEvent(v11);
      }
    }
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(v2[2], 29, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
    LanEventNotify(7, 0);
  }
}

```

## disassembly

```asm
0x18001d4c0  mov     [rsp+arg_8], rbx
0x18001d4c5  mov     [rsp+arg_10], rbp
0x18001d4ca  push    rdi
0x18001d4cb  sub     rsp, 40h
0x18001d4cf  mov     rax, cs:__security_cookie
0x18001d4d6  xor     rax, rsp
0x18001d4d9  mov     [rsp+48h+var_18], rax
0x18001d4de  mov     rbx, rcx
0x18001d4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4e8  lea     rbp, WPP_GLOBAL_Control
0x18001d4ef  cmp     rcx, rbp
0x18001d4f2  jz      short loc_18001D541
0x18001d4f4  test    byte ptr [rcx+1Ch], 8
0x18001d4f8  jz      short loc_18001D516
0x18001d4fa  mov     rcx, [rcx+10h]
0x18001d4fe  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d505  mov     edx, 1Ah
0x18001d50a  call    WPP_SF_
0x18001d50f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d516  cmp     rcx, rbp
0x18001d519  jz      short loc_18001D541
0x18001d51b  test    byte ptr [rcx+1Ch], 8
0x18001d51f  jz      short loc_18001D541
0x18001d521  mov     r9d, [rbx+2Ch]
0x18001d525  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d52c  mov     rcx, [rcx+10h]
0x18001d530  mov     edx, 1Bh
0x18001d535  call    WPP_SF_d
0x18001d53a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d541  mov     eax, [rbx+2Ch]
0x18001d544  test    al, 2
0x18001d546  jz      loc_18001D648
0x18001d54c  mov     ecx, [rbx+38h]
0x18001d54f  xorps   xmm0, xmm0
0x18001d552  add     rcx, rbx; Str
0x18001d555  mov     edx, 7Bh ; '{'; Ch
0x18001d55a  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0
0x18001d55f  call    cs:__imp_wcsrchr
0x18001d565  mov     rdi, rax
0x18001d568  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d56f  cmp     rcx, rbp
0x18001d572  jz      short loc_18001D592
0x18001d574  test    byte ptr [rcx+1Ch], 8
0x18001d578  jz      short loc_18001D592
0x18001d57a  mov     rcx, [rcx+10h]
0x18001d57e  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d585  mov     edx, 1Ch
0x18001d58a  mov     r9, rax
0x18001d58d  call    WPP_SF_S
0x18001d592  lea     rdx, [rsp+48h+pclsid]; pclsid
0x18001d597  mov     rcx, rdi; lpsz
0x18001d59a  call    cs:__imp_CLSIDFromString
0x18001d5a0  test    eax, eax
0x18001d5a2  js      loc_18001D672
0x18001d5a8  mov     rax, [rbx+18h]
0x18001d5ac  sub     rax, qword ptr cs:GUID_NDIS_STATUS_MEDIA_CONNECT.Data1
0x18001d5b3  jnz     short loc_18001D5C0
0x18001d5b5  mov     rax, [rbx+20h]
0x18001d5b9  sub     rax, qword ptr cs:GUID_NDIS_STATUS_MEDIA_CONNECT.Data4
0x18001d5c0  test    rax, rax
0x18001d5c3  jnz     short loc_18001D5CA
0x18001d5c5  lea     edi, [rax+2]
0x18001d5c8  jmp     short loc_18001D5EA
0x18001d5ca  mov     rax, [rbx+18h]
0x18001d5ce  sub     rax, qword ptr cs:GUID_NDIS_STATUS_MEDIA_DISCONNECT.Data1
0x18001d5d5  jnz     short loc_18001D5E2
0x18001d5d7  mov     rax, [rbx+20h]
0x18001d5db  sub     rax, qword ptr cs:GUID_NDIS_STATUS_MEDIA_DISCONNECT.Data4
0x18001d5e2  test    rax, rax
0x18001d5e5  jnz     short loc_18001D641
0x18001d5e7  lea     edi, [rax+7]
0x18001d5ea  mov     ecx, 0E68h; unsigned __int64
0x18001d5ef  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001d5f4  mov     rbx, rax
0x18001d5f7  test    rax, rax
0x18001d5fa  jz      short loc_18001D672
0x18001d5fc  mov     qword ptr [rax], 0
0x18001d603  lea     rcx, ?LanEventWorkItem@@YAKPEAUNMEVENT_HEADER@@@Z; unsigned int (*)(struct NMEVENT_HEADER *)
0x18001d60a  mov     dword ptr [rax+8], 2
0x18001d611  mov     rdx, rax; struct NMEVENT_HEADER *
0x18001d614  movups  xmm0, xmmword ptr [rsp+48h+pclsid.Data1]
0x18001d619  mov     dword ptr [rax+4], 6
0x18001d620  mov     [rax+20h], edi
0x18001d623  movdqu  xmmword ptr [rax+10h], xmm0
0x18001d628  mov     dword ptr [rax], 1
0x18001d62e  call    ?QueueUserWorkItemInThread@@YAHP6AKPEAUNMEVENT_HEADER@@@Z0@Z; QueueUserWorkItemInThread(ulong (*)(NMEVENT_HEADER *),NMEVENT_HEADER *)
0x18001d633  test    eax, eax
0x18001d635  jnz     short loc_18001D672
0x18001d637  mov     rcx, rbx; lpMem
0x18001d63a  call    ?FreeConmanEvent@@YAXPEAUCONMAN_EVENT@@@Z; FreeConmanEvent(CONMAN_EVENT *)
0x18001d63f  jmp     short loc_18001D672
0x18001d641  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d646  jmp     short loc_18001D672
0x18001d648  cmp     rcx, rbp
0x18001d64b  jz      short loc_18001D668
0x18001d64d  test    byte ptr [rcx+1Ch], 8
0x18001d651  jz      short loc_18001D668
0x18001d653  mov     rcx, [rcx+10h]
0x18001d657  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d65e  mov     edx, 1Dh
0x18001d663  call    WPP_SF_
0x18001d668  xor     edx, edx
0x18001d66a  lea     ecx, [rdx+7]
0x18001d66d  call    ?LanEventNotify@@YAXW4CONMAN_EVENTTYPE@@PEAUINetConnection@@PEBGPEBU_GUID@@@Z; LanEventNotify(CONMAN_EVENTTYPE,INetConnection *,ushort const *,_GUID const *)
0x18001d672  mov     rcx, [rsp+48h+var_18]
0x18001d677  xor     rcx, rsp; StackCookie
0x18001d67a  call    __security_check_cookie
0x18001d67f  mov     rbx, [rsp+48h+arg_8]
0x18001d684  mov     rbp, [rsp+48h+arg_10]
0x18001d689  add     rsp, 40h
0x18001d68d  pop     rdi
0x18001d68e  retn
```
