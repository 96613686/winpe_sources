# _anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry

- ea: `0x140021068`
- end: `0x1400211ca`
- name: `_anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry`
- size: `354`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400205a8`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x14000df60`
- `0x14001cb58`
- `0x140021068`
- `0x14002134c`
- `0x1400255dc`
- `0x14002562c`

## string_xrefs

- `0x14002108f`: ``anonymous-namespace'::WriteAccessibilityConfigStringListToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a3,
        const BYTE *a4)
{
  int v8; // eax
  int v9; // r8d
  const wchar_t *v10; // rdi
  _QWORD *v11; // rcx
  int v12; // edx
  unsigned int v13; // ebx
  _BYTE v15[16]; // [rsp+30h] [rbp-38h] BYREF
  HKEY v16[5]; // [rsp+40h] [rbp-28h] BYREF
  int v17; // [rsp+A0h] [rbp+38h] BYREF

  v17 = 0;
  _Trace::_Trace((_Trace *)v15, L"`anonymous-namespace'::WriteAccessibilityConfigStringListToRegistry", &v17);
  memset(v16, 0, 24);
  v8 = ATL::CRegKey::Open((ATL::CRegKey *)v16, hKey, lpSubKey, 0x20006u);
  v10 = L"HKLM";
  if ( hKey != HKEY_LOCAL_MACHINE )
    v10 = L"HKCU";
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v17 = v8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 22;
LABEL_15:
      WPP_SF_SSd(v11[2], v12, v9, (_DWORD)v10, (__int64)lpSubKey, v8);
    }
  }
  else
  {
    v8 = ATL::CRegKey::SetStringValue(v16, a3, a4);
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v17 = v8;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 23;
        goto LABEL_15;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, a4);
    }
  }
  v13 = v17;
  ATL::CRegKey::Close((ATL::CRegKey *)v16);
  _Trace::~_Trace((_Trace *)v15);
  return v13;
}

```

## disassembly

```asm
0x140021068  push    rbp
0x14002106a  push    rbx
0x14002106b  push    rsi
0x14002106c  push    rdi
0x14002106d  push    r14
0x14002106f  push    r15
0x140021071  mov     rbp, rsp
0x140021074  sub     rsp, 68h
0x140021078  mov     rsi, r9
0x14002107b  mov     r15, r8
0x14002107e  mov     r14, rdx
0x140021081  mov     rbx, rcx
0x140021084  mov     [rbp+arg_0], 0
0x14002108b  lea     r8, [rbp+arg_0]; int *
0x14002108f  lea     rdx, aAnonymousNames; "`anonymous-namespace'::WriteAccessibili"...
0x140021096  lea     rcx, [rbp+var_38]; this
0x14002109a  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x14002109f  nop
0x1400210a0  mov     [rbp+var_28], 0
0x1400210a8  mov     [rbp+var_20], 0
0x1400210b0  mov     [rbp+var_18], 0
0x1400210b8  mov     r9d, 20006h; unsigned int
0x1400210be  mov     r8, r14; lpSubKey
0x1400210c1  mov     rdx, rbx; hKey
0x1400210c4  lea     rcx, [rbp+var_28]; this
0x1400210c8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400210cd  lea     rcx, aHkcu; "HKCU"
0x1400210d4  lea     rdi, aHklm; "HKLM"
0x1400210db  cmp     rbx, 0FFFFFFFF80000002h
0x1400210e2  cmovnz  rdi, rcx
0x1400210e6  test    eax, eax
0x1400210e8  jz      short loc_14002111F
0x1400210ea  jle     short loc_1400210F4
0x1400210ec  movzx   eax, ax
0x1400210ef  or      eax, 80070000h
0x1400210f4  mov     [rbp+arg_0], eax
0x1400210f7  lea     rdx, WPP_GLOBAL_Control
0x1400210fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140021105  cmp     rcx, rdx
0x140021108  jz      loc_1400211A5
0x14002110e  test    byte ptr [rcx+1Ch], 8
0x140021112  jz      loc_1400211A5
0x140021118  mov     edx, 16h
0x14002111d  jmp     short loc_14002115D
0x14002111f  mov     r8, rsi; unsigned __int16 *
0x140021122  mov     rdx, r15; unsigned __int16 *
0x140021125  lea     rcx, [rbp+var_28]; this
0x140021129  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x14002112e  test    eax, eax
0x140021130  jz      short loc_140021174
0x140021132  jle     short loc_14002113C
0x140021134  movzx   eax, ax
0x140021137  or      eax, 80070000h
0x14002113c  mov     [rbp+arg_0], eax
0x14002113f  lea     rdx, WPP_GLOBAL_Control
0x140021146  mov     rcx, cs:WPP_GLOBAL_Control
0x14002114d  cmp     rcx, rdx
0x140021150  jz      short loc_1400211A5
0x140021152  test    byte ptr [rcx+1Ch], 8
0x140021156  jz      short loc_1400211A5
0x140021158  mov     edx, 17h
0x14002115d  mov     [rsp+68h+var_40], eax
0x140021161  mov     [rsp+68h+var_48], r14
0x140021166  mov     r9, rdi
0x140021169  mov     rcx, [rcx+10h]
0x14002116d  call    WPP_SF_SSd
0x140021172  jmp     short loc_1400211A5
0x140021174  lea     rdx, WPP_GLOBAL_Control
0x14002117b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021182  cmp     rcx, rdx
0x140021185  jz      short loc_1400211A5
0x140021187  test    byte ptr [rcx+1Ch], 10h
0x14002118b  jz      short loc_1400211A5
0x14002118d  mov     edx, 18h
0x140021192  mov     r9, rsi
0x140021195  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14002119c  mov     rcx, [rcx+10h]
0x1400211a0  call    WPP_SF_S
0x1400211a5  mov     ebx, [rbp+arg_0]
0x1400211a8  lea     rcx, [rbp+var_28]; this
0x1400211ac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400211b1  nop
0x1400211b2  lea     rcx, [rbp+var_38]; this
0x1400211b6  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x1400211bb  mov     eax, ebx
0x1400211bd  add     rsp, 68h
0x1400211c1  pop     r15
0x1400211c3  pop     r14
0x1400211c5  pop     rdi
0x1400211c6  pop     rsi
0x1400211c7  pop     rbx
0x1400211c8  pop     rbp
0x1400211c9  retn
```
