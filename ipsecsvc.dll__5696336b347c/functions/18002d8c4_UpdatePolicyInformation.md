# UpdatePolicyInformation

- ea: `0x18002d8c4`
- end: `0x18002d9f8`
- name: `UpdatePolicyInformation`
- size: `308`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18002cf74`
- `0x18002d2ec`
- `0x18002d64c`

## callees

- `0x18000f638`
- `0x1800277f8`
- `0x1800293a4`
- `0x18002a450`
- `0x18002a928`
- `0x18002afd0`
- `0x18002b314`
- `0x18002d8c4`

## pseudocode

```c
__int64 __fastcall UpdatePolicyInformation(__int64 a1, __int64 a2, int a3)
{
  _OWORD *v3; // rbx
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned int v7; // esi
  __int64 v8; // r14
  int v9; // r15d
  _QWORD *v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  int v13; // ecx
  __int128 v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+80h] [rbp+8h] BYREF
  _OWORD *v17; // [rsp+88h] [rbp+10h] BYREF

  v3 = *(_OWORD **)(a1 + 24);
  v5 = *(_QWORD *)(a2 + 24);
  v6 = *(_QWORD *)(a1 + 32);
  v7 = *(_DWORD *)(a1 + 40);
  v8 = *(_QWORD *)(a2 + 32);
  v9 = *(_DWORD *)(a2 + 40);
  v17 = v3;
  v16 = v5;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
      WPP_SF_(v10[2], 10, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids);
  }
  _mm_lfence();
  if ( !FindISAKMPData(v3, &v16) )
  {
    PADeleteMMFilters(v12, v6, v7);
    v15 = *v3;
    PADeleteMMPolicy(&v15);
  }
  PAUpdateISAKMPData((unsigned int)&v16, v11, v6, v7, (__int64)&v17);
  PADeleteObsoleteNFAData(v13, v6, v7, v8, v9);
  PAUpdateNFAData(v16, v8, v9, v6, v7, a3);
  return 0;
}

```

## disassembly

```asm
0x18002d8c4  mov     r11, rsp
0x18002d8c7  mov     [r11+18h], rbx
0x18002d8cb  mov     [r11+20h], rbp
0x18002d8cf  push    rsi
0x18002d8d0  push    rdi
0x18002d8d1  push    r12
0x18002d8d3  push    r14
0x18002d8d5  push    r15
0x18002d8d7  sub     rsp, 50h
0x18002d8db  mov     rbx, [rcx+18h]
0x18002d8df  mov     ebp, r8d
0x18002d8e2  mov     rax, [rdx+18h]
0x18002d8e6  mov     rdi, [rcx+20h]
0x18002d8ea  mov     esi, [rcx+28h]
0x18002d8ed  mov     r14, [rdx+20h]
0x18002d8f1  mov     r15d, [rdx+28h]
0x18002d8f5  mov     [r11+10h], rbx
0x18002d8f9  mov     [r11+8], rax
0x18002d8fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d904  lea     r12, WPP_GLOBAL_Control
0x18002d90b  cmp     rcx, r12
0x18002d90e  jz      short loc_18002D952
0x18002d910  test    byte ptr [rcx+1Ch], 4
0x18002d914  jz      short loc_18002D932
0x18002d916  mov     rcx, [rcx+10h]
0x18002d91a  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002d921  mov     edx, 86h
0x18002d926  call    WPP_SF_
0x18002d92b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d932  cmp     rcx, r12
0x18002d935  jz      short loc_18002D952
0x18002d937  test    byte ptr [rcx+1Ch], 4
0x18002d93b  jz      short loc_18002D952
0x18002d93d  mov     rcx, [rcx+10h]
0x18002d941  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002d948  mov     edx, 0Ah
0x18002d94d  call    WPP_SF_
0x18002d952  lfence
0x18002d955  lea     rdx, [rsp+78h+arg_0]
0x18002d95d  mov     rcx, rbx
0x18002d960  call    FindISAKMPData
0x18002d965  test    rax, rax
0x18002d968  jnz     short loc_18002D988
0x18002d96a  mov     r8d, esi
0x18002d96d  mov     rdx, rdi
0x18002d970  call    PADeleteMMFilters
0x18002d975  movups  xmm0, xmmword ptr [rbx]
0x18002d978  lea     rcx, [rsp+78h+var_38]
0x18002d97d  movdqu  [rsp+78h+var_38], xmm0
0x18002d983  call    PADeleteMMPolicy
0x18002d988  lea     rax, [rsp+78h+arg_8]
0x18002d990  mov     [rsp+78h+var_48], ebp
0x18002d994  mov     r9d, esi
0x18002d997  mov     [rsp+78h+var_58], rax
0x18002d99c  mov     r8, rdi
0x18002d99f  lea     rcx, [rsp+78h+arg_0]
0x18002d9a7  call    PAUpdateISAKMPData
0x18002d9ac  mov     r9, r14
0x18002d9af  mov     dword ptr [rsp+78h+var_58], r15d
0x18002d9b4  mov     r8d, esi
0x18002d9b7  mov     rdx, rdi
0x18002d9ba  call    PADeleteObsoleteNFAData
0x18002d9bf  mov     rcx, [rsp+78h+arg_0]
0x18002d9c7  mov     r9, rdi
0x18002d9ca  mov     r8d, r15d
0x18002d9cd  mov     [rsp+78h+var_50], ebp
0x18002d9d1  mov     rdx, r14
0x18002d9d4  mov     dword ptr [rsp+78h+var_58], esi
0x18002d9d8  call    PAUpdateNFAData
0x18002d9dd  lea     r11, [rsp+78h+var_28]
0x18002d9e2  xor     eax, eax
0x18002d9e4  mov     rbx, [r11+40h]
0x18002d9e8  mov     rbp, [r11+48h]
0x18002d9ec  mov     rsp, r11
0x18002d9ef  pop     r15
0x18002d9f1  pop     r14
0x18002d9f3  pop     r12
0x18002d9f5  pop     rdi
0x18002d9f6  pop     rsi
0x18002d9f7  retn
```
