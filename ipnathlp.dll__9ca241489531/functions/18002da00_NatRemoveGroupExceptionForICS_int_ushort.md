# NatRemoveGroupExceptionForICS(int,ushort *)

- ea: `0x18002da00`
- end: `0x18002dd89`
- name: `?NatRemoveGroupExceptionForICS@@YAJHPEAG@Z`
- size: `905`
- prototype: `__int64 __fastcall(size_t MaxCount, wchar_t *String1)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d3cc`
- `0x18002d4c8`
- `0x18002d87c`
- `0x180042a44`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002da00`
- `0x18007d6a4`
- `0x18008e8f0`

## import_xrefs

- `FirewallAPI!FWQueryFirewallRules` at `0x18002dbac`
- `FirewallAPI!FWQueryFirewallRules` at `0x18002dbac`
- `FirewallAPI!FWClosePolicyStore` at `0x18002dcd3`
- `FirewallAPI!FWClosePolicyStore` at `0x18002dcd3`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002dcbd`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002dcbd`
- `FirewallAPI!FWOpenPolicyStore` at `0x18002dae7`
- `FirewallAPI!FWOpenPolicyStore` at `0x18002dae7`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18002dd26`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18002dd26`

## string_xrefs

- `0x18002db4f`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 __fastcall NatRemoveGroupExceptionForICS(size_t MaxCount, wchar_t *String1, int a3)
{
  unsigned int v3; // r12d
  unsigned int v5; // esi
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  PVOID *v9; // rbx
  __int64 v10; // rdx
  __int64 **v11; // rdi
  unsigned int v13; // eax
  int v14; // edi
  __int128 v15; // [rsp+38h] [rbp-19h] BYREF
  __int128 v16; // [rsp+48h] [rbp-9h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp+7h]
  __int128 v18; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+70h] [rbp+1Fh]
  unsigned int v20; // [rsp+C0h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+C8h] [rbp+77h] BYREF
  __int64 **v22; // [rsp+D0h] [rbp+7Fh] BYREF

  v3 = MaxCount;
  if ( String1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, a3, MaxCount, (__int64)String1);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      &WPP_213010f39927376708ca656d45278473_Traceguids,
      (unsigned int)MaxCount);
  }
  v5 = 0;
  v17 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v16 = 0;
  v15 = 0;
  v18 = 0;
  v6 = FWOpenPolicyStore(545, 0, 5, 2, 0, &v21);
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 45;
LABEL_18:
      WPP_SF_d(v9[2], v10, &WPP_213010f39927376708ca656d45278473_Traceguids, (unsigned int)v6);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v17 = L"@ipnathlp.dll,-140";
    *((_QWORD *)&v15 + 1) = &v16;
    *(_QWORD *)&v16 = 0x100000008LL;
    *((_QWORD *)&v18 + 1) = &v15;
    DWORD2(v16) = 5;
    LODWORD(v15) = 1;
    DWORD1(v18) = 1;
    LODWORD(v19) = 0x10000;
    LOWORD(v18) = 545;
    v6 = FWQueryFirewallRules(v21, &v18, 0, &v20, &v22);
    if ( !v6 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_213010f39927376708ca656d45278473_Traceguids, v20);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = v22;
      if ( v22 )
      {
        while ( wcsncmp_0(String1, (const wchar_t *)v11[3], v3) )
        {
          v11 = (__int64 **)*v11;
          if ( !v11 )
            goto LABEL_34;
        }
        v13 = FWDeleteFirewallRule(v21, v11[2]);
        v14 = v13;
        if ( v13 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_213010f39927376708ca656d45278473_Traceguids, v13);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v14 > 0 )
            v5 = (unsigned __int16)v14 | 0x80070000;
          else
            v5 = v14;
          goto LABEL_39;
        }
      }
      else
      {
LABEL_34:
        if ( v9 == &WPP_GLOBAL_Control || (*((_DWORD *)v9 + 7) & 0x200) == 0 || *((_BYTE *)v9 + 25) < 3u )
          goto LABEL_39;
        WPP_SF_(v9[2], 49, &WPP_213010f39927376708ca656d45278473_Traceguids);
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_39;
    }
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 46;
      goto LABEL_18;
    }
  }
LABEL_39:
  if ( v22 )
  {
    FWFreeFirewallRules(v22);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 )
  {
    FWClosePolicyStore(v21, v7, v8);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 50, &WPP_213010f39927376708ca656d45278473_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18002da00  mov     rax, rsp
0x18002da03  push    rbp
0x18002da04  push    rbx
0x18002da05  push    rsi
0x18002da06  lea     rbp, [rax-5Fh]
0x18002da0a  sub     rsp, 90h
0x18002da11  mov     [rax-28h], r12
0x18002da15  mov     r12d, ecx
0x18002da18  mov     [rax-30h], r14
0x18002da1c  mov     [rax-38h], r15
0x18002da20  mov     r15, rdx
0x18002da23  test    rdx, rdx
0x18002da26  jz      short loc_18002DA62
0x18002da28  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da2f  lea     r14, WPP_GLOBAL_Control
0x18002da36  cmp     rcx, r14
0x18002da39  jz      short loc_18002DA9C
0x18002da3b  test    dword ptr [rcx+1Ch], 200h
0x18002da42  jz      short loc_18002DA9C
0x18002da44  cmp     byte ptr [rcx+19h], 6
0x18002da48  jb      short loc_18002DA9C
0x18002da4a  mov     rcx, [rcx+10h]
0x18002da4e  mov     edx, 2Bh ; '+'
0x18002da53  mov     r9d, r12d
0x18002da56  mov     [rsp+0A0h+var_80], r15
0x18002da5b  call    WPP_SF_dS
0x18002da60  jmp     short loc_18002DA9C
0x18002da62  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da69  lea     r14, WPP_GLOBAL_Control
0x18002da70  cmp     rcx, r14
0x18002da73  jz      short loc_18002DA9C
0x18002da75  test    dword ptr [rcx+1Ch], 200h
0x18002da7c  jz      short loc_18002DA9C
0x18002da7e  cmp     byte ptr [rcx+19h], 6
0x18002da82  jb      short loc_18002DA9C
0x18002da84  mov     rcx, [rcx+10h]
0x18002da88  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18002da8f  mov     edx, 2Ch ; ','
0x18002da94  mov     r9d, r12d
0x18002da97  call    WPP_SF_d
0x18002da9c  xor     eax, eax
0x18002da9e  xor     esi, esi
0x18002daa0  xorps   xmm0, xmm0
0x18002daa3  mov     [rbp+57h+var_50], rax
0x18002daa7  mov     [rbp+57h+var_38], rax
0x18002daab  xorps   xmm1, xmm1
0x18002daae  lea     rax, [rbp+57h+arg_10]
0x18002dab2  mov     [rbp+57h+arg_10], rsi
0x18002dab6  mov     [rsp+28h], rax
0x18002dabb  mov     ebx, 221h
0x18002dac0  mov     ecx, ebx
0x18002dac2  mov     dword ptr [rsp+0A0h+var_80], esi
0x18002dac6  xor     edx, edx
0x18002dac8  mov     [rbp+57h+arg_8], esi
0x18002dacb  mov     r9d, 2
0x18002dad1  mov     [rbp+57h+arg_18], rsi
0x18002dad5  mov     r8d, 5
0x18002dadb  movups  [rbp+57h+var_60], xmm0
0x18002dadf  movups  [rbp+57h+var_70], xmm0
0x18002dae3  movups  [rbp+57h+var_48], xmm1
0x18002dae7  call    cs:__imp_FWOpenPolicyStore
0x18002daed  test    eax, eax
0x18002daef  jz      short loc_18002DB4B
0x18002daf1  jg      short loc_18002DAF7
0x18002daf3  mov     esi, eax
0x18002daf5  jmp     short loc_18002DB00
0x18002daf7  movzx   esi, ax
0x18002dafa  or      esi, 80070000h
0x18002db00  mov     rbx, cs:WPP_GLOBAL_Control
0x18002db07  cmp     rbx, r14
0x18002db0a  jz      loc_18002DCA7
0x18002db10  test    dword ptr [rbx+1Ch], 200h
0x18002db17  jz      loc_18002DCA7
0x18002db1d  cmp     byte ptr [rbx+19h], 2
0x18002db21  jb      loc_18002DCA7
0x18002db27  mov     edx, 2Dh ; '-'
0x18002db2c  mov     rcx, [rbx+10h]
0x18002db30  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18002db37  mov     r9d, eax
0x18002db3a  call    WPP_SF_d
0x18002db3f  mov     rbx, cs:WPP_GLOBAL_Control
0x18002db46  jmp     loc_18002DCA7
0x18002db4b  mov     rcx, [rbp+57h+arg_10]
0x18002db4f  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x18002db56  mov     [rbp+57h+var_50], rax
0x18002db5a  lea     r9, [rbp+57h+arg_8]
0x18002db5e  lea     rax, [rbp+57h+var_60]
0x18002db62  mov     dword ptr [rbp+57h+var_60+4], 1
0x18002db69  mov     qword ptr [rbp+57h+var_70+8], rax
0x18002db6d  lea     rdx, [rbp+57h+var_48]
0x18002db71  lea     rax, [rbp+57h+var_70]
0x18002db75  mov     dword ptr [rbp+57h+var_60], 8
0x18002db7c  mov     qword ptr [rbp+57h+var_48+8], rax
0x18002db80  xor     r8d, r8d
0x18002db83  lea     rax, [rbp+57h+arg_18]
0x18002db87  mov     dword ptr [rbp+57h+var_60+8], 5
0x18002db8e  mov     [rsp+0A0h+var_80], rax
0x18002db93  mov     dword ptr [rbp+57h+var_70], 1
0x18002db9a  mov     dword ptr [rbp+57h+var_48+4], 1
0x18002dba1  mov     dword ptr [rbp+57h+var_38], 10000h
0x18002dba8  mov     word ptr [rbp+57h+var_48], bx
0x18002dbac  call    cs:__imp_FWQueryFirewallRules
0x18002dbb2  test    eax, eax
0x18002dbb4  jz      short loc_18002DBF6
0x18002dbb6  jg      short loc_18002DBBC
0x18002dbb8  mov     esi, eax
0x18002dbba  jmp     short loc_18002DBC5
0x18002dbbc  movzx   esi, ax
0x18002dbbf  or      esi, 80070000h
0x18002dbc5  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dbcc  cmp     rbx, r14
0x18002dbcf  jz      loc_18002DCA7
0x18002dbd5  test    dword ptr [rbx+1Ch], 200h
0x18002dbdc  jz      loc_18002DCA7
0x18002dbe2  cmp     byte ptr [rbx+19h], 2
0x18002dbe6  jb      loc_18002DCA7
0x18002dbec  mov     edx, 2Eh ; '.'
0x18002dbf1  jmp     loc_18002DB2C
0x18002dbf6  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dbfd  mov     [rsp+88h], rdi
0x18002dc05  cmp     rbx, r14
0x18002dc08  jz      short loc_18002DC39
0x18002dc0a  test    dword ptr [rbx+1Ch], 200h
0x18002dc11  jz      short loc_18002DC39
0x18002dc13  cmp     byte ptr [rbx+19h], 5
0x18002dc17  jb      short loc_18002DC39
0x18002dc19  mov     r9d, [rbp+57h+arg_8]
0x18002dc1d  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18002dc24  mov     rcx, [rbx+10h]
0x18002dc28  mov     edx, 2Fh ; '/'
0x18002dc2d  call    WPP_SF_d
0x18002dc32  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dc39  mov     rdi, [rbp+57h+arg_18]
0x18002dc3d  test    rdi, rdi
0x18002dc40  jz      short loc_18002DC6F
0x18002dc42  nop     dword ptr [rax+00h]
0x18002dc46  nop     word ptr [rax+rax+00000000h]
0x18002dc50  mov     rdx, [rdi+18h]; String2
0x18002dc54  mov     r8d, r12d; MaxCount
0x18002dc57  mov     rcx, r15; String1
0x18002dc5a  call    wcsncmp_0
0x18002dc5f  test    eax, eax
0x18002dc61  jz      loc_18002DD1E
0x18002dc67  mov     rdi, [rdi]
0x18002dc6a  test    rdi, rdi
0x18002dc6d  jnz     short loc_18002DC50
0x18002dc6f  cmp     rbx, r14
0x18002dc72  jz      short loc_18002DC9F
0x18002dc74  test    dword ptr [rbx+1Ch], 200h
0x18002dc7b  jz      short loc_18002DC9F
0x18002dc7d  cmp     byte ptr [rbx+19h], 3
0x18002dc81  jb      short loc_18002DC9F
0x18002dc83  mov     rcx, [rbx+10h]
0x18002dc87  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18002dc8e  mov     edx, 31h ; '1'
0x18002dc93  call    WPP_SF_
0x18002dc98  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dc9f  mov     rdi, [rsp+88h]
0x18002dca7  mov     rcx, [rbp+57h+arg_18]
0x18002dcab  mov     r15, [rsp+0A0h+var_30]
0x18002dcb0  mov     r12, [rsp+0A0h+var_20]
0x18002dcb8  test    rcx, rcx
0x18002dcbb  jz      short loc_18002DCCA
0x18002dcbd  call    cs:__imp_FWFreeFirewallRules
0x18002dcc3  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dcca  mov     rcx, [rbp+57h+arg_10]
0x18002dcce  test    rcx, rcx
0x18002dcd1  jz      short loc_18002DCE0
0x18002dcd3  call    cs:__imp_FWClosePolicyStore
0x18002dcd9  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dce0  cmp     rbx, r14
0x18002dce3  mov     r14, [rsp+0A0h+var_28]
0x18002dce8  jz      short loc_18002DD11
0x18002dcea  test    dword ptr [rbx+1Ch], 200h
0x18002dcf1  jz      short loc_18002DD11
0x18002dcf3  cmp     byte ptr [rbx+19h], 6
0x18002dcf7  jb      short loc_18002DD11
0x18002dcf9  mov     rcx, [rbx+10h]
0x18002dcfd  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18002dd04  mov     edx, 32h ; '2'
0x18002dd09  mov     r9d, esi
0x18002dd0c  call    WPP_SF_d
0x18002dd11  mov     eax, esi
0x18002dd13  add     rsp, 90h
0x18002dd1a  pop     rsi
0x18002dd1b  pop     rbx
0x18002dd1c  pop     rbp
0x18002dd1d  retn
0x18002dd1e  mov     rdx, [rdi+10h]
0x18002dd22  mov     rcx, [rbp+57h+arg_10]
0x18002dd26  call    cs:__imp_FWDeleteFirewallRule
0x18002dd2c  mov     edi, eax
0x18002dd2e  test    eax, eax
0x18002dd30  jz      loc_18002DC98
0x18002dd36  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dd3d  cmp     rbx, r14
0x18002dd40  jz      short loc_18002DD70
0x18002dd42  test    dword ptr [rbx+1Ch], 200h
0x18002dd49  jz      short loc_18002DD70
0x18002dd4b  cmp     byte ptr [rbx+19h], 2
0x18002dd4f  jb      short loc_18002DD70
0x18002dd51  mov     rcx, [rbx+10h]
0x18002dd55  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18002dd5c  mov     edx, 30h ; '0'
0x18002dd61  mov     r9d, eax
0x18002dd64  call    WPP_SF_d
0x18002dd69  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dd70  test    edi, edi
0x18002dd72  jg      short loc_18002DD7B
0x18002dd74  mov     esi, edi
0x18002dd76  jmp     loc_18002DC9F
0x18002dd7b  movzx   esi, di
0x18002dd7e  or      esi, 80070000h
0x18002dd84  jmp     loc_18002DC9F
```
