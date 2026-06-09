# EnumOutboundRoutingRulesCB(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x14005fe20`
- end: `0x1400600d0`
- name: `?EnumOutboundRoutingRulesCB@@YAHPEAUHKEY__@@PEBGKPEAX@Z`
- size: `688`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14005f830`
- `0x14005fe20`
- `0x1400600d8`
- `0x140060558`
- `0x1400609cc`
- `0x1400708c4`
- `0x140070f1c`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005ffac`
- `ADVAPI32!RegCloseKey` at `0x14005ffac`
- `ADVAPI32!RegDeleteKeyW` at `0x14005ff5d`
- `ADVAPI32!RegDeleteKeyW` at `0x14005ff5d`
- `KERNEL32!GetLastError` at `0x14005ff18`
- `KERNEL32!GetLastError` at `0x14005ff18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumOutboundRoutingRulesCB(HKEY hKey, const unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  __int64 v7; // rcx
  DWORD LastError; // esi
  int v9; // r15d
  HKEY v10; // rax
  HKEY v11; // r14
  LSTATUS v12; // eax
  unsigned __int64 v13; // rdx
  unsigned int Status; // eax
  unsigned int v15; // eax
  int v17; // [rsp+30h] [rbp-40h] BYREF
  void *Block[3]; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-20h]
  int v20; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids);
  }
  v19 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  if ( a2 )
  {
    LastError = COutboundRoutingRule::Load((COutboundRoutingRule *)Block, hKey);
    if ( LastError )
    {
      v9 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids,
          (_DWORD)a2,
          LastError);
      }
      v10 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Rules", 0, 0x3001Fu);
      v11 = v10;
      if ( v10 )
      {
        v12 = RegDeleteKeyW(v10, a2);
        if ( v12 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              83,
              (unsigned int)WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids,
              (_DWORD)a2,
              v12);
          }
        }
        else
        {
          v9 = 1;
        }
        RegCloseKey(v11);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, LastError);
        }
      }
      if ( !LastError )
        goto LABEL_43;
      if ( v9 )
      {
        v13 = 3221257541LL;
LABEL_42:
        FaxLogOutboundRule(a2, v13);
LABEL_43:
        *a4 = 0;
        if ( v19 >= 8 )
          operator delete(Block[0]);
        return 1;
      }
    }
    else
    {
      if ( v20 && !(unsigned int)IsServerSku(v7) )
        goto LABEL_43;
      v17 = 0;
      Status = COutboundRoutingRule::GetStatus((COutboundRoutingRule *)Block, (enum FAX_ENUM_RULE_STATUS *)&v17);
      if ( Status )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, Status);
        }
      }
      else if ( v17 && v17 != 3 )
      {
        FaxLogOutboundRule(a2, 0x80007D44);
      }
      v15 = COutboundRulesMap::AddRule(g_pRulesMap, (struct COutboundRoutingRule *)Block);
      if ( !v15 )
        goto LABEL_43;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids,
          (_DWORD)a2,
          v15);
      }
    }
    v13 = 3221257543LL;
    goto LABEL_42;
  }
  return 1;
}

```

## disassembly

```asm
0x14005fe20  push    rbp
0x14005fe22  push    rbx
0x14005fe23  push    rsi
0x14005fe24  push    rdi
0x14005fe25  push    r12
0x14005fe27  push    r14
0x14005fe29  push    r15
0x14005fe2b  mov     rbp, rsp
0x14005fe2e  sub     rsp, 70h
0x14005fe32  mov     rax, cs:__security_cookie
0x14005fe39  xor     rax, rsp
0x14005fe3c  mov     [rbp+var_8], rax
0x14005fe40  mov     r12, r9
0x14005fe43  mov     rdi, rdx
0x14005fe46  mov     rbx, rcx
0x14005fe49  lea     r15, WPP_GLOBAL_Control
0x14005fe50  mov     r14b, 4
0x14005fe53  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fe5a  cmp     rcx, r15
0x14005fe5d  jz      short loc_14005FE80
0x14005fe5f  test    [rcx+1Ch], r14b
0x14005fe63  jz      short loc_14005FE80
0x14005fe65  cmp     byte ptr [rcx+19h], 5
0x14005fe69  jb      short loc_14005FE80
0x14005fe6b  mov     edx, 50h ; 'P'
0x14005fe70  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005fe77  mov     rcx, [rcx+10h]
0x14005fe7b  call    WPP_SF_
0x14005fe80  mov     [rbp+var_20], 7
0x14005fe88  mov     [rbp+var_28], 0
0x14005fe90  xor     eax, eax
0x14005fe92  mov     word ptr [rbp+Block], ax
0x14005fe96  test    rdi, rdi
0x14005fe99  jnz     short loc_14005FEA0
0x14005fe9b  jmp     loc_1400600B0
0x14005fea0  mov     rdx, rbx; hKey
0x14005fea3  lea     rcx, [rbp+Block]; this
0x14005fea7  call    ?Load@COutboundRoutingRule@@QEAAKPEAUHKEY__@@@Z; COutboundRoutingRule::Load(HKEY__ *)
0x14005feac  mov     esi, eax
0x14005feae  test    eax, eax
0x14005feb0  jz      loc_14005FFCD
0x14005feb6  xor     r15d, r15d
0x14005feb9  mov     bl, 2
0x14005febb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fec2  lea     rax, WPP_GLOBAL_Control
0x14005fec9  cmp     rcx, rax
0x14005fecc  jz      short loc_14005FEF4
0x14005fece  test    [rcx+1Ch], r14b
0x14005fed2  jz      short loc_14005FEF4
0x14005fed4  cmp     [rcx+19h], bl
0x14005fed7  jb      short loc_14005FEF4
0x14005fed9  lea     edx, [r15+51h]
0x14005fedd  mov     [rsp+70h+var_50], esi
0x14005fee1  mov     r9, rdi
0x14005fee4  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005feeb  mov     rcx, [rcx+10h]
0x14005feef  call    WPP_SF_Sd
0x14005fef4  mov     r9d, 3001Fh
0x14005fefa  xor     r8d, r8d
0x14005fefd  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x14005ff04  mov     rcx, 0FFFFFFFF80000002h
0x14005ff0b  call    OpenRegistryKey
0x14005ff10  mov     r14, rax
0x14005ff13  test    rax, rax
0x14005ff16  jnz     short loc_14005FF57
0x14005ff18  call    cs:__imp_GetLastError
0x14005ff1e  mov     esi, eax
0x14005ff20  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ff27  lea     rax, WPP_GLOBAL_Control
0x14005ff2e  cmp     rcx, rax
0x14005ff31  jz      short loc_14005FFB2
0x14005ff33  test    byte ptr [rcx+1Ch], 4
0x14005ff37  jz      short loc_14005FFB2
0x14005ff39  cmp     [rcx+19h], bl
0x14005ff3c  jb      short loc_14005FFB2
0x14005ff3e  lea     edx, [r14+52h]
0x14005ff42  mov     r9d, esi
0x14005ff45  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005ff4c  mov     rcx, [rcx+10h]
0x14005ff50  call    WPP_SF_d
0x14005ff55  jmp     short loc_14005FFB2
0x14005ff57  mov     rdx, rdi; lpSubKey
0x14005ff5a  mov     rcx, r14; hKey
0x14005ff5d  call    cs:__imp_RegDeleteKeyW
0x14005ff63  test    eax, eax
0x14005ff65  jz      short loc_14005FFA3
0x14005ff67  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ff6e  lea     rdx, WPP_GLOBAL_Control
0x14005ff75  cmp     rcx, rdx
0x14005ff78  jz      short loc_14005FFA9
0x14005ff7a  test    byte ptr [rcx+1Ch], 4
0x14005ff7e  jz      short loc_14005FFA9
0x14005ff80  cmp     [rcx+19h], bl
0x14005ff83  jb      short loc_14005FFA9
0x14005ff85  mov     edx, 53h ; 'S'
0x14005ff8a  mov     [rsp+70h+var_50], eax
0x14005ff8e  mov     r9, rdi
0x14005ff91  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005ff98  mov     rcx, [rcx+10h]
0x14005ff9c  call    WPP_SF_Sd
0x14005ffa1  jmp     short loc_14005FFA9
0x14005ffa3  mov     r15d, 1
0x14005ffa9  mov     rcx, r14; hKey
0x14005ffac  call    cs:__imp_RegCloseKey
0x14005ffb2  test    esi, esi
0x14005ffb4  jz      loc_140060098
0x14005ffba  test    r15d, r15d
0x14005ffbd  jz      loc_14006008B
0x14005ffc3  mov     edx, 0C0007D45h
0x14005ffc8  jmp     loc_140060090
0x14005ffcd  cmp     [rbp+var_10], 0
0x14005ffd1  jz      short loc_14005FFE0
0x14005ffd3  call    IsServerSku
0x14005ffd8  test    eax, eax
0x14005ffda  jz      loc_140060098
0x14005ffe0  mov     [rbp+var_40], 0
0x14005ffe7  lea     rdx, [rbp+var_40]; enum FAX_ENUM_RULE_STATUS *
0x14005ffeb  lea     rcx, [rbp+Block]; this
0x14005ffef  call    ?GetStatus@COutboundRoutingRule@@QEBAKPEAW4FAX_ENUM_RULE_STATUS@@@Z; COutboundRoutingRule::GetStatus(FAX_ENUM_RULE_STATUS *)
0x14005fff4  mov     bl, 2
0x14005fff6  test    eax, eax
0x14005fff8  jnz     short loc_140060015
0x14005fffa  mov     eax, [rbp+var_40]
0x14005fffd  test    eax, eax
0x14005ffff  jz      short loc_140060044
0x140060001  cmp     eax, 3
0x140060004  jz      short loc_140060044
0x140060006  mov     edx, 80007D44h; unsigned __int64
0x14006000b  mov     rcx, rdi; unsigned __int16 *
0x14006000e  call    ?FaxLogOutboundRule@@YAXPEBG_K@Z; FaxLogOutboundRule(ushort const *,unsigned __int64)
0x140060013  jmp     short loc_140060044
0x140060015  mov     rcx, cs:WPP_GLOBAL_Control
0x14006001c  cmp     rcx, r15
0x14006001f  jz      short loc_140060044
0x140060021  test    [rcx+1Ch], r14b
0x140060025  jz      short loc_140060044
0x140060027  cmp     [rcx+19h], bl
0x14006002a  jb      short loc_140060044
0x14006002c  mov     edx, 54h ; 'T'
0x140060031  mov     r9d, eax
0x140060034  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14006003b  mov     rcx, [rcx+10h]
0x14006003f  call    WPP_SF_d
0x140060044  lea     rdx, [rbp+Block]; struct COutboundRoutingRule *
0x140060048  mov     rcx, cs:?g_pRulesMap@@3PEAVCOutboundRulesMap@@EA; this
0x14006004f  call    ?AddRule@COutboundRulesMap@@QEAAKAEAVCOutboundRoutingRule@@@Z; COutboundRulesMap::AddRule(COutboundRoutingRule &)
0x140060054  test    eax, eax
0x140060056  jz      short loc_140060098
0x140060058  mov     rcx, cs:WPP_GLOBAL_Control
0x14006005f  cmp     rcx, r15
0x140060062  jz      short loc_14006008B
0x140060064  test    [rcx+1Ch], r14b
0x140060068  jz      short loc_14006008B
0x14006006a  cmp     [rcx+19h], bl
0x14006006d  jb      short loc_14006008B
0x14006006f  mov     edx, 55h ; 'U'
0x140060074  mov     [rsp+70h+var_50], eax
0x140060078  mov     r9, rdi
0x14006007b  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x140060082  mov     rcx, [rcx+10h]
0x140060086  call    WPP_SF_Sd
0x14006008b  mov     edx, 0C0007D47h; unsigned __int64
0x140060090  mov     rcx, rdi; unsigned __int16 *
0x140060093  call    ?FaxLogOutboundRule@@YAXPEBG_K@Z; FaxLogOutboundRule(ushort const *,unsigned __int64)
0x140060098  mov     dword ptr [r12], 0
0x1400600a0  cmp     [rbp+var_20], 8
0x1400600a5  jb      short loc_1400600B0
0x1400600a7  mov     rcx, [rbp+Block]; Block
0x1400600ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400600b0  mov     eax, 1
0x1400600b5  mov     rcx, [rbp+var_8]
0x1400600b9  xor     rcx, rsp; StackCookie
0x1400600bc  call    __security_check_cookie
0x1400600c1  add     rsp, 70h
0x1400600c5  pop     r15
0x1400600c7  pop     r14
0x1400600c9  pop     r12
0x1400600cb  pop     rdi
0x1400600cc  pop     rsi
0x1400600cd  pop     rbx
0x1400600ce  pop     rbp
0x1400600cf  retn
```
