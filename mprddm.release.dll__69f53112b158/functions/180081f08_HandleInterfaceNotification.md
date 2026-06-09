# HandleInterfaceNotification

- ea: `0x180081f08`
- end: `0x180082153`
- name: `HandleInterfaceNotification`
- size: `587`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180082160`
- `0x1800821d0`

## callees

- `0x180002e36`
- `0x18007526c`
- `0x1800786f0`
- `0x180078878`
- `0x180081f08`
- `0x1800828b4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800820fb`
- `KERNEL32!LeaveCriticalSection` at `0x1800820fb`
- `KERNEL32!EnterCriticalSection` at `0x180081fb4`
- `KERNEL32!EnterCriticalSection` at `0x180081fb4`

## string_xrefs

- `0x180081fc5`: `DELETE`
- `0x18008203f`: `HandleInterfaceNotification: Ignoring ADD event already processed on this interface`
- `0x1800820e8`: `HandleInterfaceNotification: Ignoring DELETE event already processed on this interface`

## pseudocode

```c
void __fastcall HandleInterfaceNotification(char a1, __int64 a2, int a3)
{
  const NET_LUID *v6; // rdi
  _QWORD *v7; // rax
  char v8; // dl
  _QWORD *i; // rbx
  const CHAR *v10; // rcx
  int v11; // r9d
  LPVOID *v12; // rcx
  LPVOID *v13; // r8
  __int64 v14; // r9
  LPVOID *v15; // rcx
  LPVOID *v16; // r8
  ULONG64 Value; // [rsp+20h] [rbp-18h]
  ULONG InterfaceIndex; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8e5cd7b600883acb2381d11173a944d5_Traceguids);
  }
  InterfaceIndex = 0;
  if ( a2 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      v6 = *(const NET_LUID **)a2;
      if ( v6 )
      {
        if ( a3 != 3 && a3 )
        {
          if ( ConvertInterfaceLuidToIndex_0(v6, &InterfaceIndex) )
          {
            TraceMsg("HandleInterfaceNotification: ConvertInterfaceLuidToIndex failed: %u");
          }
          else
          {
            EnterCriticalSection(&g_csInterfaceCache);
            Value = v6->Value;
            TraceMsg("HandleInterfaceNotification:%s: [Index: %u]: %s :[LUID: %I64X]");
            v7 = g_IpV6InterfaceTable;
            if ( a3 == 1 )
            {
              v8 = 0;
              if ( a1 )
                v7 = g_IpV4InterfaceTable;
              if ( v7 )
              {
                while ( *v7 != v6->Value )
                {
                  v7 = (_QWORD *)v7[2];
                  if ( !v7 )
                    goto LABEL_18;
                }
                v10 = "HandleInterfaceNotification: Ignoring ADD event already processed on this interface";
              }
              else
              {
LABEL_18:
                for ( i = g_RasVpnLuids; i; i = (_QWORD *)i[2] )
                {
                  if ( *((_BYTE *)i + 8) )
                  {
                    TraceMsg("HandleInterfaceNotification: %I64X is dormant");
                    v8 = 1;
                  }
                  if ( *i == v6->Value )
                  {
                    v10 = "HandleInterfaceNotification: Ignoring ADD as the event is for RAS VPN interface";
                    goto LABEL_36;
                  }
                }
                v11 = g_NumVpnIpv6RouteTableChanges;
                v12 = &g_IpV6InterfaceTable;
                v13 = &g_IpV4InterfaceTable;
                if ( a1 )
                  v11 = g_NumVpnIpv4RouteTableChanges;
                else
                  v13 = &g_IpV6InterfaceTable;
                LOBYTE(v12) = a1;
                AdjustInterfaceMetricsOnNewlyAddedInterface((_DWORD)v12, v6->Value, (_DWORD)v13, v11, v8 == 0);
                v10 = "HandleInterfaceNotification: AdjustInterfaceMetricsOnNewlyAddedInterface returned: %d";
              }
            }
            else
            {
              if ( a1 )
                v7 = g_IpV4InterfaceTable;
              if ( v7 )
              {
                while ( *v7 != v6->Value )
                {
                  v7 = (_QWORD *)v7[2];
                  if ( !v7 )
                    goto LABEL_35;
                }
                v14 = (unsigned int)g_NumVpnIpv6RouteTableChanges;
                v15 = &g_IpV6InterfaceTable;
                v16 = &g_IpV4InterfaceTable;
                if ( a1 )
                  v14 = (unsigned int)g_NumVpnIpv4RouteTableChanges;
                else
                  v16 = &g_IpV6InterfaceTable;
                LOBYTE(v15) = a1;
                AdjustInterfaceMetricsOnDeletingInterface(v15, v6->Value, v16, v14, Value);
                v10 = "HandleInterfaceNotification: AdjustInterfaceMetricsOnDeletingInterface returned: %d";
              }
              else
              {
LABEL_35:
                v10 = "HandleInterfaceNotification: Ignoring DELETE event already processed on this interface";
              }
            }
LABEL_36:
            TraceMsg(v10);
            LeaveCriticalSection(&g_csInterfaceCache);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180081f08  mov     [rsp+arg_0], rbx
0x180081f0d  mov     [rsp+arg_10], rsi
0x180081f12  push    rdi
0x180081f13  sub     rsp, 30h
0x180081f17  mov     ebx, r8d
0x180081f1a  mov     rdi, rdx
0x180081f1d  mov     sil, cl
0x180081f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180081f27  lea     rax, WPP_GLOBAL_Control
0x180081f2e  cmp     rcx, rax
0x180081f31  jz      short loc_180081F54
0x180081f33  test    byte ptr [rcx+1Ch], 20h
0x180081f37  jz      short loc_180081F54
0x180081f39  cmp     byte ptr [rcx+19h], 6
0x180081f3d  jb      short loc_180081F54
0x180081f3f  mov     rcx, [rcx+10h]
0x180081f43  lea     r8, WPP_8e5cd7b600883acb2381d11173a944d5_Traceguids
0x180081f4a  mov     edx, 0Ah
0x180081f4f  call    WPP_SF_
0x180081f54  and     [rsp+38h+InterfaceIndex], 0
0x180081f59  test    rdi, rdi
0x180081f5c  jz      loc_180082107
0x180081f62  cmp     dword ptr [rdi+8], 0
0x180081f66  jz      loc_180082107
0x180081f6c  mov     rdi, [rdi]
0x180081f6f  test    rdi, rdi
0x180081f72  jz      loc_180082107
0x180081f78  cmp     ebx, 3
0x180081f7b  jz      loc_180082107
0x180081f81  test    ebx, ebx
0x180081f83  jz      loc_180082107
0x180081f89  lea     rdx, [rsp+38h+InterfaceIndex]; InterfaceIndex
0x180081f8e  mov     rcx, rdi; InterfaceLuid
0x180081f91  call    ConvertInterfaceLuidToIndex_0
0x180081f96  test    eax, eax
0x180081f98  jz      short loc_180081FAD
0x180081f9a  mov     edx, eax
0x180081f9c  lea     rcx, aHandleinterfac_3; "HandleInterfaceNotification: ConvertInt"...
0x180081fa3  call    TraceMsg
0x180081fa8  jmp     loc_180082107
0x180081fad  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x180081fb4  call    cs:__imp_EnterCriticalSection
0x180081fbb  nop     dword ptr [rax+rax+00h]
0x180081fc0  mov     r8d, [rsp+38h+InterfaceIndex]
0x180081fc5  lea     rax, aDelete; "DELETE"
0x180081fcc  cmp     ebx, 1
0x180081fcf  lea     r9, aAdd_0; "ADD"
0x180081fd6  lea     rdx, aIpv4_0; "(IPv4)"
0x180081fdd  cmovnz  r9, rax
0x180081fe1  lea     rcx, aHandleinterfac_1; "HandleInterfaceNotification:%s: [Index:"...
0x180081fe8  lea     rax, aIpv6_0; "(IPv6)"
0x180081fef  test    sil, sil
0x180081ff2  cmovz   rdx, rax
0x180081ff6  mov     rax, [rdi]
0x180081ff9  mov     [rsp+38h+var_18], rax
0x180081ffe  call    TraceMsg
0x180082003  mov     rax, cs:g_IpV6InterfaceTable
0x18008200a  cmp     ebx, 1
0x18008200d  jnz     loc_1800820C7
0x180082013  xor     dl, dl
0x180082015  test    sil, sil
0x180082018  cmovnz  rax, cs:g_IpV4InterfaceTable
0x180082020  test    rax, rax
0x180082023  jz      short loc_180082036
0x180082025  mov     rcx, [rdi]
0x180082028  cmp     [rax], rcx
0x18008202b  jz      short loc_18008203F
0x18008202d  mov     rax, [rax+10h]
0x180082031  test    rax, rax
0x180082034  jnz     short loc_180082028
0x180082036  mov     rbx, cs:g_RasVpnLuids
0x18008203d  jmp     short loc_18008206E
0x18008203f  lea     rcx, aHandleinterfac_4; "HandleInterfaceNotification: Ignoring A"...
0x180082046  jmp     loc_1800820EF
0x18008204b  cmp     byte ptr [rbx+8], 0
0x18008204f  jz      short loc_180082062
0x180082051  mov     rdx, [rbx]
0x180082054  lea     rcx, aHandleinterfac_5; "HandleInterfaceNotification: %I64X is d"...
0x18008205b  call    TraceMsg
0x180082060  mov     dl, 1
0x180082062  mov     rax, [rdi]
0x180082065  cmp     [rbx], rax
0x180082068  jz      short loc_1800820BE
0x18008206a  mov     rbx, [rbx+10h]
0x18008206e  test    rbx, rbx
0x180082071  jnz     short loc_18008204B
0x180082073  mov     r9d, cs:g_NumVpnIpv6RouteTableChanges
0x18008207a  lea     rcx, g_IpV6InterfaceTable
0x180082081  test    sil, sil
0x180082084  lea     r8, g_IpV4InterfaceTable
0x18008208b  cmovnz  r9d, cs:g_NumVpnIpv4RouteTableChanges
0x180082093  test    dl, dl
0x180082095  mov     rdx, [rdi]
0x180082098  setz    al
0x18008209b  test    sil, sil
0x18008209e  mov     byte ptr [rsp+38h+var_18], al
0x1800820a2  cmovz   r8, rcx
0x1800820a6  mov     cl, sil
0x1800820a9  call    AdjustInterfaceMetricsOnNewlyAddedInterface
0x1800820ae  lea     rcx, aHandleinterfac; "HandleInterfaceNotification: AdjustInte"...
0x1800820b5  mov     edx, eax
0x1800820b7  call    TraceMsg
0x1800820bc  jmp     short loc_1800820F4
0x1800820be  lea     rcx, aHandleinterfac_0; "HandleInterfaceNotification: Ignoring A"...
0x1800820c5  jmp     short loc_1800820EF
0x1800820c7  test    sil, sil
0x1800820ca  cmovnz  rax, cs:g_IpV4InterfaceTable
0x1800820d2  test    rax, rax
0x1800820d5  jz      short loc_1800820E8
0x1800820d7  mov     rcx, [rdi]
0x1800820da  cmp     [rax], rcx
0x1800820dd  jz      short loc_180082118
0x1800820df  mov     rax, [rax+10h]
0x1800820e3  test    rax, rax
0x1800820e6  jnz     short loc_1800820DA
0x1800820e8  lea     rcx, aHandleinterfac_6; "HandleInterfaceNotification: Ignoring D"...
0x1800820ef  call    TraceMsg
0x1800820f4  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x1800820fb  call    cs:__imp_LeaveCriticalSection
0x180082102  nop     dword ptr [rax+rax+00h]
0x180082107  mov     rbx, [rsp+38h+arg_0]
0x18008210c  mov     rsi, [rsp+38h+arg_10]
0x180082111  add     rsp, 30h
0x180082115  pop     rdi
0x180082116  retn
0x180082118  mov     r9d, cs:g_NumVpnIpv6RouteTableChanges
0x18008211f  lea     rcx, g_IpV6InterfaceTable
0x180082126  mov     rdx, [rdi]
0x180082129  lea     r8, g_IpV4InterfaceTable
0x180082130  test    sil, sil
0x180082133  cmovnz  r9d, cs:g_NumVpnIpv4RouteTableChanges
0x18008213b  cmovz   r8, rcx
0x18008213f  mov     cl, sil
0x180082142  call    AdjustInterfaceMetricsOnDeletingInterface
0x180082147  lea     rcx, aHandleinterfac_2; "HandleInterfaceNotification: AdjustInte"...
0x18008214e  jmp     loc_1800820B5
```
