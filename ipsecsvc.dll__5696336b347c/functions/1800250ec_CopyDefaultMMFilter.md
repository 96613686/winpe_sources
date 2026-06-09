# CopyDefaultMMFilter

- ea: `0x1800250ec`
- end: `0x1800251f1`
- name: `CopyDefaultMMFilter`
- size: `261`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180025320`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x1800250ec`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180025110`
- `RPCRT4!UuidCreate` at `0x180025110`

## pseudocode

```c
__int64 __fastcall CopyDefaultMMFilter(__int64 a1)
{
  _OWORD *v1; // rsi
  _OWORD *v3; // rbp
  RPC_STATUS v4; // eax
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  v1 = (_OWORD *)gpIniDefaultMMPolicy;
  v3 = (_OWORD *)gpIniDefaultMMAuthMethods;
  *(_DWORD *)a1 = 0;
  v4 = UuidCreate((UUID *)(a1 + 4));
  if ( !v4 || v4 == 1824 )
  {
    v5 = CopyName(L"0");
    if ( !v5 )
    {
      *(_QWORD *)(a1 + 40) = 3;
      *(_DWORD *)(a1 + 32) = 1;
      *(_DWORD *)(a1 + 36) = 1;
      *(_DWORD *)(a1 + 88) = 2;
      *(_DWORD *)(a1 + 128) = 2;
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 136) = 0;
      *(_DWORD *)(a1 + 48) = 0;
      *(_OWORD *)(a1 + 52) = *v3;
      *(_OWORD *)(a1 + 68) = *v1;
      return v5;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 71;
      goto LABEL_6;
    }
  }
  else
  {
    v5 = 1726;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 70;
LABEL_6:
      WPP_SF_d(v6[2], v7, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids, v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800250ec  push    rbx
0x1800250ee  push    rbp
0x1800250ef  push    rsi
0x1800250f0  push    rdi
0x1800250f1  sub     rsp, 28h
0x1800250f5  mov     rsi, cs:gpIniDefaultMMPolicy
0x1800250fc  mov     rbx, rcx
0x1800250ff  mov     rbp, cs:gpIniDefaultMMAuthMethods
0x180025106  mov     dword ptr [rcx], 0
0x18002510c  add     rcx, 4; Uuid
0x180025110  call    cs:__imp_UuidCreate
0x180025116  test    eax, eax
0x180025118  jz      short loc_180025164
0x18002511a  cmp     eax, 720h
0x18002511f  jz      short loc_180025164
0x180025121  mov     edi, 6BEh
0x180025126  mov     rcx, cs:WPP_GLOBAL_Control
0x18002512d  lea     rax, WPP_GLOBAL_Control
0x180025134  cmp     rcx, rax
0x180025137  jz      loc_1800251E6
0x18002513d  test    byte ptr [rcx+1Ch], 10h
0x180025141  jz      loc_1800251E6
0x180025147  mov     edx, 46h ; 'F'
0x18002514c  mov     rcx, [rcx+10h]
0x180025150  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x180025157  mov     r9d, edi
0x18002515a  call    WPP_SF_d
0x18002515f  jmp     loc_1800251E6
0x180025164  lea     rdx, [rbx+18h]
0x180025168  lea     rcx, a0; "0"
0x18002516f  call    CopyName
0x180025174  mov     edi, eax
0x180025176  test    eax, eax
0x180025178  jz      short loc_18002519A
0x18002517a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025181  lea     rax, WPP_GLOBAL_Control
0x180025188  cmp     rcx, rax
0x18002518b  jz      short loc_1800251E6
0x18002518d  test    byte ptr [rcx+1Ch], 10h
0x180025191  jz      short loc_1800251E6
0x180025193  mov     edx, 47h ; 'G'
0x180025198  jmp     short loc_18002514C
0x18002519a  mov     eax, 1
0x18002519f  mov     qword ptr [rbx+28h], 3
0x1800251a7  mov     [rbx+20h], eax
0x1800251aa  mov     [rbx+24h], eax
0x1800251ad  mov     eax, 2
0x1800251b2  mov     [rbx+58h], eax
0x1800251b5  mov     [rbx+80h], eax
0x1800251bb  mov     qword ptr [rbx+60h], 0
0x1800251c3  mov     qword ptr [rbx+88h], 0
0x1800251ce  mov     dword ptr [rbx+30h], 0
0x1800251d5  movups  xmm0, xmmword ptr [rbp+0]
0x1800251d9  movdqu  xmmword ptr [rbx+34h], xmm0
0x1800251de  movups  xmm1, xmmword ptr [rsi]
0x1800251e1  movdqu  xmmword ptr [rbx+44h], xmm1
0x1800251e6  mov     eax, edi
0x1800251e8  add     rsp, 28h
0x1800251ec  pop     rdi
0x1800251ed  pop     rsi
0x1800251ee  pop     rbp
0x1800251ef  pop     rbx
0x1800251f0  retn
```
