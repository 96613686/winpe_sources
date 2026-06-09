# HandleInterfaceNotification

- ea: `0x18007ce70`
- end: `0x18007d0b1`
- name: `HandleInterfaceNotification`
- size: `577`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18007d0c0`
- `0x18007d130`

## callees

- `0x180002de6`
- `0x1800719a8`
- `0x1800749f4`
- `0x180074b7c`
- `0x18007ce70`
- `0x18007d7ac`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18007d060`
- `KERNEL32!LeaveCriticalSection` at `0x18007d060`
- `KERNEL32!EnterCriticalSection` at `0x18007cf1f`
- `KERNEL32!EnterCriticalSection` at `0x18007cf1f`

## string_xrefs

- `0x18007cf2a`: `DELETE`
- `0x18007cfa4`: `HandleInterfaceNotification: Ignoring ADD event already processed on this interface`
- `0x18007d04d`: `HandleInterfaceNotification: Ignoring DELETE event already processed on this interface`

## pseudocode

```c
void __fastcall HandleInterfaceNotification(char a1, __int64 a2, int a3)
{
  const NET_LUID *v6; // rdi
  _QWORD *v7; // rax
  _BYTE *v8; // rbx
  char v9; // cl
  const CHAR *v10; // rcx
  int v11; // r9d
  LPVOID *v12; // r8
  char v13; // zf
  LPVOID *v14; // rcx
  __int64 v15; // r9
  LPVOID *v16; // rcx
  LPVOID *v17; // r8
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
                v8 = g_RasVpnLuids;
                v9 = 0;
                while ( v8 )
                {
                  if ( v8[8] )
                  {
                    TraceMsg("HandleInterfaceNotification: %I64X is dormant");
                    v9 = 1;
                  }
                  if ( *(_QWORD *)v8 == v6->Value )
                  {
                    v10 = "HandleInterfaceNotification: Ignoring ADD as the event is for RAS VPN interface";
                    goto LABEL_37;
                  }
                  v8 = (_BYTE *)*((_QWORD *)v8 + 2);
                }
                v11 = g_NumVpnIpv6RouteTableChanges;
                v12 = &g_IpV4InterfaceTable;
                if ( a1 )
                  v11 = g_NumVpnIpv4RouteTableChanges;
                v13 = v9 == 0;
                v14 = &g_IpV6InterfaceTable;
                if ( !a1 )
                  v12 = &g_IpV6InterfaceTable;
                LOBYTE(v14) = a1;
                AdjustInterfaceMetricsOnNewlyAddedInterface((_DWORD)v14, v6->Value, (_DWORD)v12, v11, v13);
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
                    goto LABEL_36;
                }
                v15 = (unsigned int)g_NumVpnIpv6RouteTableChanges;
                v16 = &g_IpV6InterfaceTable;
                v17 = &g_IpV4InterfaceTable;
                if ( a1 )
                  v15 = (unsigned int)g_NumVpnIpv4RouteTableChanges;
                else
                  v17 = &g_IpV6InterfaceTable;
                LOBYTE(v16) = a1;
                AdjustInterfaceMetricsOnDeletingInterface(v16, v6->Value, v17, v15, Value);
                v10 = "HandleInterfaceNotification: AdjustInterfaceMetricsOnDeletingInterface returned: %d";
              }
              else
              {
LABEL_36:
                v10 = "HandleInterfaceNotification: Ignoring DELETE event already processed on this interface";
              }
            }
LABEL_37:
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
0x18007ce70  mov     [rsp+arg_0], rbx
0x18007ce75  mov     [rsp+arg_10], rsi
0x18007ce7a  push    rdi
0x18007ce7b  sub     rsp, 30h
0x18007ce7f  mov     ebx, r8d
0x18007ce82  mov     rdi, rdx
0x18007ce85  mov     sil, cl
0x18007ce88  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce8f  lea     rax, WPP_GLOBAL_Control
0x18007ce96  cmp     rcx, rax
0x18007ce99  jz      short loc_18007CEBC
0x18007ce9b  test    byte ptr [rcx+1Ch], 20h
0x18007ce9f  jz      short loc_18007CEBC
0x18007cea1  cmp     byte ptr [rcx+19h], 6
0x18007cea5  jb      short loc_18007CEBC
0x18007cea7  mov     rcx, [rcx+10h]
0x18007ceab  lea     r8, WPP_8e5cd7b600883acb2381d11173a944d5_Traceguids
0x18007ceb2  mov     edx, 0Ah
0x18007ceb7  call    WPP_SF_
0x18007cebc  mov     [rsp+38h+InterfaceIndex], 0
0x18007cec4  test    rdi, rdi
0x18007cec7  jz      loc_18007D066
0x18007cecd  cmp     dword ptr [rdi+8], 0
0x18007ced1  jz      loc_18007D066
0x18007ced7  mov     rdi, [rdi]
0x18007ceda  test    rdi, rdi
0x18007cedd  jz      loc_18007D066
0x18007cee3  cmp     ebx, 3
0x18007cee6  jz      loc_18007D066
0x18007ceec  test    ebx, ebx
0x18007ceee  jz      loc_18007D066
0x18007cef4  lea     rdx, [rsp+38h+InterfaceIndex]; InterfaceIndex
0x18007cef9  mov     rcx, rdi; InterfaceLuid
0x18007cefc  call    ConvertInterfaceLuidToIndex_0
0x18007cf01  test    eax, eax
0x18007cf03  jz      short loc_18007CF18
0x18007cf05  mov     edx, eax
0x18007cf07  lea     rcx, aHandleinterfac_3; "HandleInterfaceNotification: ConvertInt"...
0x18007cf0e  call    TraceMsg
0x18007cf13  jmp     loc_18007D066
0x18007cf18  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18007cf1f  call    cs:__imp_EnterCriticalSection
0x18007cf25  mov     r8d, [rsp+38h+InterfaceIndex]
0x18007cf2a  lea     rax, aDelete; "DELETE"
0x18007cf31  cmp     ebx, 1
0x18007cf34  lea     r9, aAdd_0; "ADD"
0x18007cf3b  lea     rdx, aIpv4_0; "(IPv4)"
0x18007cf42  cmovnz  r9, rax
0x18007cf46  lea     rcx, aHandleinterfac_1; "HandleInterfaceNotification:%s: [Index:"...
0x18007cf4d  lea     rax, aIpv6_0; "(IPv6)"
0x18007cf54  test    sil, sil
0x18007cf57  cmovz   rdx, rax
0x18007cf5b  mov     rax, [rdi]
0x18007cf5e  mov     [rsp+38h+var_18], rax
0x18007cf63  call    TraceMsg
0x18007cf68  mov     rax, cs:g_IpV6InterfaceTable
0x18007cf6f  cmp     ebx, 1
0x18007cf72  jnz     loc_18007D02C
0x18007cf78  test    sil, sil
0x18007cf7b  cmovnz  rax, cs:g_IpV4InterfaceTable
0x18007cf83  test    rax, rax
0x18007cf86  jz      short loc_18007CF99
0x18007cf88  mov     rcx, [rdi]
0x18007cf8b  cmp     [rax], rcx
0x18007cf8e  jz      short loc_18007CFA4
0x18007cf90  mov     rax, [rax+10h]
0x18007cf94  test    rax, rax
0x18007cf97  jnz     short loc_18007CF8B
0x18007cf99  mov     rbx, cs:g_RasVpnLuids
0x18007cfa0  xor     cl, cl
0x18007cfa2  jmp     short loc_18007CFD3
0x18007cfa4  lea     rcx, aHandleinterfac_4; "HandleInterfaceNotification: Ignoring A"...
0x18007cfab  jmp     loc_18007D054
0x18007cfb0  cmp     byte ptr [rbx+8], 0
0x18007cfb4  jz      short loc_18007CFC7
0x18007cfb6  mov     rdx, [rbx]
0x18007cfb9  lea     rcx, aHandleinterfac_5; "HandleInterfaceNotification: %I64X is d"...
0x18007cfc0  call    TraceMsg
0x18007cfc5  mov     cl, 1
0x18007cfc7  mov     rax, [rdi]
0x18007cfca  cmp     [rbx], rax
0x18007cfcd  jz      short loc_18007D023
0x18007cfcf  mov     rbx, [rbx+10h]
0x18007cfd3  test    rbx, rbx
0x18007cfd6  jnz     short loc_18007CFB0
0x18007cfd8  mov     r9d, cs:g_NumVpnIpv6RouteTableChanges
0x18007cfdf  lea     r8, g_IpV4InterfaceTable
0x18007cfe6  mov     rdx, [rdi]
0x18007cfe9  test    sil, sil
0x18007cfec  cmovnz  r9d, cs:g_NumVpnIpv4RouteTableChanges
0x18007cff4  test    cl, cl
0x18007cff6  lea     rcx, g_IpV6InterfaceTable
0x18007cffd  setz    al
0x18007d000  test    sil, sil
0x18007d003  mov     byte ptr [rsp+38h+var_18], al
0x18007d007  cmovz   r8, rcx
0x18007d00b  mov     cl, sil
0x18007d00e  call    AdjustInterfaceMetricsOnNewlyAddedInterface
0x18007d013  lea     rcx, aHandleinterfac; "HandleInterfaceNotification: AdjustInte"...
0x18007d01a  mov     edx, eax
0x18007d01c  call    TraceMsg
0x18007d021  jmp     short loc_18007D059
0x18007d023  lea     rcx, aHandleinterfac_0; "HandleInterfaceNotification: Ignoring A"...
0x18007d02a  jmp     short loc_18007D054
0x18007d02c  test    sil, sil
0x18007d02f  cmovnz  rax, cs:g_IpV4InterfaceTable
0x18007d037  test    rax, rax
0x18007d03a  jz      short loc_18007D04D
0x18007d03c  mov     rcx, [rdi]
0x18007d03f  cmp     [rax], rcx
0x18007d042  jz      short loc_18007D076
0x18007d044  mov     rax, [rax+10h]
0x18007d048  test    rax, rax
0x18007d04b  jnz     short loc_18007D03F
0x18007d04d  lea     rcx, aHandleinterfac_6; "HandleInterfaceNotification: Ignoring D"...
0x18007d054  call    TraceMsg
0x18007d059  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18007d060  call    cs:__imp_LeaveCriticalSection
0x18007d066  mov     rbx, [rsp+38h+arg_0]
0x18007d06b  mov     rsi, [rsp+38h+arg_10]
0x18007d070  add     rsp, 30h
0x18007d074  pop     rdi
0x18007d075  retn
0x18007d076  mov     r9d, cs:g_NumVpnIpv6RouteTableChanges
0x18007d07d  lea     rcx, g_IpV6InterfaceTable
0x18007d084  mov     rdx, [rdi]
0x18007d087  lea     r8, g_IpV4InterfaceTable
0x18007d08e  test    sil, sil
0x18007d091  cmovnz  r9d, cs:g_NumVpnIpv4RouteTableChanges
0x18007d099  cmovz   r8, rcx
0x18007d09d  mov     cl, sil
0x18007d0a0  call    AdjustInterfaceMetricsOnDeletingInterface
0x18007d0a5  lea     rcx, aHandleinterfac_2; "HandleInterfaceNotification: AdjustInte"...
0x18007d0ac  jmp     loc_18007D01A
```
