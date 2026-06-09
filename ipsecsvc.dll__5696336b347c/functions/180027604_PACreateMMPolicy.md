# PACreateMMPolicy

- ea: `0x180027604`
- end: `0x180027750`
- name: `PACreateMMPolicy`
- size: `332`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180007b54`
- `0x180008ff4`
- `0x18002aa3c`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x18001cc18`
- `0x180027438`
- `0x180027604`
- `0x18002791c`

## pseudocode

```c
__int64 __fastcall PACreateMMPolicy(__int64 a1, __int64 a2, _QWORD *a3)
{
  _OWORD *v6; // rax
  _OWORD *v7; // rbx
  __int64 v8; // r9
  unsigned int v9; // esi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned int v13; // eax
  _DWORD *v15; // rax

  v6 = IpsecAllocMem(0x30u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = 8;
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_19:
      *a3 = 0;
      return v9;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_14;
    v11 = 15;
    goto LABEL_13;
  }
  *v6 = *(_OWORD *)a1;
  v12 = IpsecAllocStr(*(unsigned __int16 **)(a2 + 16));
  *((_QWORD *)v7 + 2) = v12;
  if ( !v12 )
  {
    v8 = 8;
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_14;
      v11 = 16;
      goto LABEL_13;
    }
    goto LABEL_18;
  }
  *((_DWORD *)v7 + 6) = 2;
  v13 = PACreateMMOffers(*(unsigned int *)(a1 + 76), *(_QWORD *)(a1 + 80), v7 + 2, (char *)v7 + 40);
  v9 = v13;
  if ( v13 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_14;
      v11 = 17;
      v8 = v13;
LABEL_13:
      WPP_SF_d(v10[2], v11, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, v8);
      v10 = WPP_GLOBAL_Control;
LABEL_14:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
        WPP_SF__guid_(v10[2], 18, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, a1);
      if ( !v7 )
        goto LABEL_19;
    }
LABEL_18:
    PAFreeQMPolicy(v7);
    goto LABEL_19;
  }
  v15 = (_DWORD *)*((_QWORD *)v7 + 5);
  *a3 = v7;
  *((_DWORD *)v7 + 7) = *v15;
  *((_DWORD *)v7 + 6) |= *(_DWORD *)(a1 + 40);
  return 0;
}

```

## disassembly

```asm
0x180027604  push    rbx
0x180027606  push    rbp
0x180027607  push    rsi
0x180027608  push    rdi
0x180027609  push    r14
0x18002760b  sub     rsp, 20h
0x18002760f  mov     rbp, rcx
0x180027612  mov     r14, r8
0x180027615  mov     ecx, 30h ; '0'
0x18002761a  mov     rdi, rdx
0x18002761d  call    IpsecAllocMem
0x180027622  mov     rbx, rax
0x180027625  test    rax, rax
0x180027628  jnz     short loc_18002765A
0x18002762a  lea     r9d, [rax+8]
0x18002762e  mov     esi, r9d
0x180027631  mov     rcx, cs:WPP_GLOBAL_Control
0x180027638  lea     rdi, WPP_GLOBAL_Control
0x18002763f  cmp     rcx, rdi
0x180027642  jz      loc_180027726
0x180027648  test    byte ptr [rcx+1Ch], 10h
0x18002764c  jz      loc_1800276F6
0x180027652  lea     edx, [rax+0Fh]
0x180027655  jmp     loc_1800276DF
0x18002765a  movups  xmm0, xmmword ptr [rbp+0]
0x18002765e  movdqu  xmmword ptr [rax], xmm0
0x180027662  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180027666  call    IpsecAllocStr
0x18002766b  mov     [rbx+10h], rax
0x18002766f  test    rax, rax
0x180027672  jnz     short loc_18002769D
0x180027674  lea     r9d, [rax+8]
0x180027678  mov     esi, r9d
0x18002767b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027682  lea     rdi, WPP_GLOBAL_Control
0x180027689  cmp     rcx, rdi
0x18002768c  jz      loc_18002771E
0x180027692  test    byte ptr [rcx+1Ch], 10h
0x180027696  jz      short loc_1800276F6
0x180027698  lea     edx, [rax+10h]
0x18002769b  jmp     short loc_1800276DF
0x18002769d  mov     dword ptr [rbx+18h], 2
0x1800276a4  lea     r8, [rbx+20h]
0x1800276a8  mov     rdx, [rbp+50h]
0x1800276ac  lea     r9, [rbx+28h]
0x1800276b0  mov     ecx, [rbp+4Ch]
0x1800276b3  call    PACreateMMOffers
0x1800276b8  mov     esi, eax
0x1800276ba  test    eax, eax
0x1800276bc  jz      short loc_180027731
0x1800276be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276c5  lea     rdi, WPP_GLOBAL_Control
0x1800276cc  cmp     rcx, rdi
0x1800276cf  jz      short loc_18002771E
0x1800276d1  test    byte ptr [rcx+1Ch], 10h
0x1800276d5  jz      short loc_1800276F6
0x1800276d7  mov     edx, 11h
0x1800276dc  mov     r9d, eax
0x1800276df  mov     rcx, [rcx+10h]
0x1800276e3  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x1800276ea  call    WPP_SF_d
0x1800276ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276f6  cmp     rcx, rdi
0x1800276f9  jz      short loc_180027719
0x1800276fb  test    byte ptr [rcx+1Ch], 10h
0x1800276ff  jz      short loc_180027719
0x180027701  mov     rcx, [rcx+10h]
0x180027705  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x18002770c  mov     edx, 12h
0x180027711  mov     r9, rbp
0x180027714  call    WPP_SF__guid_
0x180027719  test    rbx, rbx
0x18002771c  jz      short loc_180027726
0x18002771e  mov     rcx, rbx; lpMem
0x180027721  call    PAFreeQMPolicy
0x180027726  mov     qword ptr [r14], 0
0x18002772d  mov     eax, esi
0x18002772f  jmp     short loc_180027745
0x180027731  mov     rax, [rbx+28h]
0x180027735  mov     [r14], rbx
0x180027738  mov     ecx, [rax]
0x18002773a  mov     [rbx+1Ch], ecx
0x18002773d  mov     eax, [rbp+28h]
0x180027740  or      [rbx+18h], eax
0x180027743  xor     eax, eax
0x180027745  add     rsp, 20h
0x180027749  pop     r14
0x18002774b  pop     rdi
0x18002774c  pop     rsi
0x18002774d  pop     rbp
0x18002774e  pop     rbx
0x18002774f  retn
```
