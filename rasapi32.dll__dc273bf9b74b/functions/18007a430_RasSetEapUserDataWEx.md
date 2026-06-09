# RasSetEapUserDataWEx

- ea: `0x18007a430`
- end: `0x18007a748`
- name: `RasSetEapUserDataWEx`
- size: `792`
- prototype: `__int64 __usercall@<rax>(HANDLE Token@<rcx>, PCNZWCH lpString2@<rdx>, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18007a0f0`
- `0x18007a2f0`

## callees

- `0x18000ada0`
- `0x180010d10`
- `0x1800289e0`
- `0x18004e580`
- `0x18004e984`
- `0x18007a430`
- `0x18007e6c8`
- `0x1800c19ec`
- `0x1800d01a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007a504`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007a5d0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007a6bb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007a504`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007a5d0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007a6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a6c5`

## pseudocode

```c
__int64 __fastcall RasSetEapUserDataWEx(
        HANDLE Token,
        PCNZWCH lpString2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6)
{
  int v10; // r12d
  int v11; // r14d
  DWORD LastError; // eax
  DWORD v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD EntryFromSystem; // eax
  __int64 v17; // r13
  __int64 v18; // rdx
  __int64 v19; // rbx
  int v20; // ebp
  int v21; // eax
  __int64 v24; // [rsp+88h] [rbp+10h] BYREF
  __int64 v25; // [rsp+98h] [rbp+20h]

  v25 = a4;
  if ( lpString2 && a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        989,
        (unsigned int)WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
        (_DWORD)lpString2,
        a3);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 990, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  v24 = 0;
  DebugInit();
  v10 = 1;
  if ( !a5 || (v11 = 0, !a4) )
    v11 = 1;
  if ( SetThreadToken(0, Token) )
  {
    EntryFromSystem = ReadEntryFromSystem(lpString2, a3, 0x408u, 0, (size_t *)&v24, 0);
    v17 = v24;
    v13 = EntryFromSystem;
    if ( EntryFromSystem )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v18 = 992;
    }
    else
    {
      v19 = *(_QWORD *)(v24 + 16);
      v20 = IsRouterPhonebook(lpString2);
      if ( SetThreadToken(0, 0) )
      {
        v21 = a6;
        v10 = 0;
        if ( a6 == -1 )
          v21 = *(_DWORD *)(v19 + 192);
        EntryFromSystem = DwSetEapUserInfo(Token, *(_QWORD *)(v19 + 464), v25, a5, v11, v20, v21);
        v13 = EntryFromSystem;
        if ( !EntryFromSystem )
          goto LABEL_39;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v18 = 994;
      }
      else
      {
        EntryFromSystem = GetLastError();
        v13 = EntryFromSystem;
        if ( !EntryFromSystem )
        {
LABEL_39:
          v14 = WPP_GLOBAL_Control;
LABEL_40:
          if ( v17 )
          {
            DestroyEntryNode(v17);
            v14 = WPP_GLOBAL_Control;
          }
          if ( !v10 )
            goto LABEL_51;
          if ( SetThreadToken(0, 0) )
            goto LABEL_50;
          LastError = GetLastError();
          v13 = LastError;
          if ( !LastError )
            goto LABEL_50;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v13;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_51;
          v15 = 995;
          goto LABEL_49;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        v18 = 993;
      }
    }
    WPP_SF_d(v14[2], v18, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, EntryFromSystem);
    goto LABEL_39;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( !LastError )
  {
LABEL_50:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_51;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v13;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 991;
LABEL_49:
    WPP_SF_d(v14[2], v15, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, LastError);
    goto LABEL_50;
  }
LABEL_51:
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x800) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 996, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18007a430  mov     [rsp+arg_18], r9
0x18007a435  mov     [rsp+arg_0], rcx
0x18007a43a  push    rbx
0x18007a43b  push    rbp
0x18007a43c  push    rsi
0x18007a43d  push    rdi
0x18007a43e  push    r12
0x18007a440  push    r13
0x18007a442  push    r14
0x18007a444  sub     rsp, 40h
0x18007a448  mov     rsi, r9
0x18007a44b  mov     rbx, r8
0x18007a44e  mov     rbp, rdx
0x18007a451  mov     r13, rcx
0x18007a454  mov     eax, 800h
0x18007a459  test    rdx, rdx
0x18007a45c  jz      short loc_18007A4A0
0x18007a45e  test    rbx, rbx
0x18007a461  jz      short loc_18007A4A0
0x18007a463  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a46a  lea     rdi, WPP_GLOBAL_Control
0x18007a471  cmp     rcx, rdi
0x18007a474  jz      short loc_18007A4D3
0x18007a476  test    [rcx+1Ch], eax
0x18007a479  jz      short loc_18007A4D3
0x18007a47b  cmp     byte ptr [rcx+19h], 6
0x18007a47f  jb      short loc_18007A4D3
0x18007a481  mov     rcx, [rcx+10h]
0x18007a485  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007a48c  mov     edx, 3DDh
0x18007a491  mov     [rsp+78h+var_58], rbx
0x18007a496  mov     r9, rbp
0x18007a499  call    WPP_SF_SS
0x18007a49e  jmp     short loc_18007A4D3
0x18007a4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a4a7  lea     rdi, WPP_GLOBAL_Control
0x18007a4ae  cmp     rcx, rdi
0x18007a4b1  jz      short loc_18007A4D3
0x18007a4b3  test    [rcx+1Ch], eax
0x18007a4b6  jz      short loc_18007A4D3
0x18007a4b8  cmp     byte ptr [rcx+19h], 6
0x18007a4bc  jb      short loc_18007A4D3
0x18007a4be  mov     rcx, [rcx+10h]
0x18007a4c2  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007a4c9  mov     edx, 3DEh
0x18007a4ce  call    WPP_SF_
0x18007a4d3  mov     [rsp+78h+arg_8], 0
0x18007a4df  call    DebugInit
0x18007a4e4  cmp     [rsp+78h+arg_20], 0
0x18007a4ec  mov     r12d, 1
0x18007a4f2  jz      short loc_18007A4FC
0x18007a4f4  xor     r14d, r14d
0x18007a4f7  test    rsi, rsi
0x18007a4fa  jnz     short loc_18007A4FF
0x18007a4fc  mov     r14d, r12d
0x18007a4ff  mov     rdx, r13; Token
0x18007a502  xor     ecx, ecx; Thread
0x18007a504  call    cs:__imp_SetThreadToken
0x18007a50a  test    eax, eax
0x18007a50c  jnz     short loc_18007A552
0x18007a50e  call    cs:__imp_GetLastError
0x18007a514  mov     ebx, eax
0x18007a516  test    eax, eax
0x18007a518  jz      loc_18007A704
0x18007a51e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a525  cmp     rcx, rdi
0x18007a528  jz      loc_18007A737
0x18007a52e  test    dword ptr [rcx+1Ch], 800h
0x18007a535  jz      loc_18007A70B
0x18007a53b  mov     sil, 2
0x18007a53e  cmp     [rcx+19h], sil
0x18007a542  jb      loc_18007A70B
0x18007a548  mov     edx, 3DFh
0x18007a54d  jmp     loc_18007A6F1
0x18007a552  lea     rax, [rsp+78h+arg_8]
0x18007a55a  mov     [rsp+78h+var_50], 0; __int64
0x18007a563  xor     r9d, r9d
0x18007a566  mov     [rsp+78h+var_58], rax; __int64
0x18007a56b  mov     r8d, 408h
0x18007a571  mov     rdx, rbx
0x18007a574  mov     rcx, rbp; lpString2
0x18007a577  call    ReadEntryFromSystem
0x18007a57c  mov     r13, [rsp+78h+arg_8]
0x18007a584  mov     ebx, eax
0x18007a586  mov     sil, 2
0x18007a589  test    eax, eax
0x18007a58b  jz      short loc_18007A5BE
0x18007a58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a594  cmp     rcx, rdi
0x18007a597  jz      loc_18007A69E
0x18007a59d  test    dword ptr [rcx+1Ch], 800h
0x18007a5a4  jz      loc_18007A69E
0x18007a5aa  cmp     [rcx+19h], sil
0x18007a5ae  jb      loc_18007A69E
0x18007a5b4  mov     edx, 3E0h
0x18007a5b9  jmp     loc_18007A684
0x18007a5be  mov     rbx, [r13+10h]
0x18007a5c2  mov     rcx, rbp; lpString
0x18007a5c5  call    IsRouterPhonebook
0x18007a5ca  xor     edx, edx; Token
0x18007a5cc  xor     ecx, ecx; Thread
0x18007a5ce  mov     ebp, eax
0x18007a5d0  call    cs:__imp_SetThreadToken
0x18007a5d6  test    eax, eax
0x18007a5d8  jnz     short loc_18007A618
0x18007a5da  call    cs:__imp_GetLastError
0x18007a5e0  mov     ebx, eax
0x18007a5e2  test    eax, eax
0x18007a5e4  jz      loc_18007A697
0x18007a5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a5f1  cmp     rcx, rdi
0x18007a5f4  jz      loc_18007A69E
0x18007a5fa  test    dword ptr [rcx+1Ch], 800h
0x18007a601  jz      loc_18007A69E
0x18007a607  cmp     [rcx+19h], sil
0x18007a60b  jb      loc_18007A69E
0x18007a611  mov     edx, 3E1h
0x18007a616  jmp     short loc_18007A684
0x18007a618  mov     eax, [rsp+78h+arg_28]
0x18007a61f  xor     r12d, r12d
0x18007a622  cmp     eax, 0FFFFFFFFh
0x18007a625  jnz     short loc_18007A62D
0x18007a627  mov     eax, [rbx+0C0h]
0x18007a62d  mov     r9d, [rsp+78h+arg_20]
0x18007a635  mov     r8, [rsp+78h+arg_18]
0x18007a63d  mov     rdx, [rbx+1D0h]
0x18007a644  mov     rcx, [rsp+78h+arg_0]
0x18007a64c  mov     [rsp+78h+var_48], eax
0x18007a650  mov     dword ptr [rsp+78h+var_50], ebp
0x18007a654  mov     dword ptr [rsp+78h+var_58], r14d
0x18007a659  call    DwSetEapUserInfo
0x18007a65e  mov     ebx, eax
0x18007a660  test    eax, eax
0x18007a662  jz      short loc_18007A697
0x18007a664  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a66b  cmp     rcx, rdi
0x18007a66e  jz      short loc_18007A69E
0x18007a670  test    dword ptr [rcx+1Ch], 800h
0x18007a677  jz      short loc_18007A69E
0x18007a679  cmp     [rcx+19h], sil
0x18007a67d  jb      short loc_18007A69E
0x18007a67f  mov     edx, 3E2h
0x18007a684  mov     rcx, [rcx+10h]
0x18007a688  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007a68f  mov     r9d, eax
0x18007a692  call    WPP_SF_d
0x18007a697  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a69e  test    r13, r13
0x18007a6a1  jz      short loc_18007A6B2
0x18007a6a3  mov     rcx, r13
0x18007a6a6  call    DestroyEntryNode
0x18007a6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6b2  test    r12d, r12d
0x18007a6b5  jz      short loc_18007A70B
0x18007a6b7  xor     edx, edx; Token
0x18007a6b9  xor     ecx, ecx; Thread
0x18007a6bb  call    cs:__imp_SetThreadToken
0x18007a6c1  test    eax, eax
0x18007a6c3  jnz     short loc_18007A704
0x18007a6c5  call    cs:__imp_GetLastError
0x18007a6cb  mov     ebx, eax
0x18007a6cd  test    eax, eax
0x18007a6cf  jz      short loc_18007A704
0x18007a6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6d8  cmp     rcx, rdi
0x18007a6db  jz      short loc_18007A737
0x18007a6dd  test    dword ptr [rcx+1Ch], 800h
0x18007a6e4  jz      short loc_18007A70B
0x18007a6e6  cmp     [rcx+19h], sil
0x18007a6ea  jb      short loc_18007A70B
0x18007a6ec  mov     edx, 3E3h
0x18007a6f1  mov     rcx, [rcx+10h]
0x18007a6f5  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007a6fc  mov     r9d, eax
0x18007a6ff  call    WPP_SF_d
0x18007a704  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a70b  cmp     rcx, rdi
0x18007a70e  jz      short loc_18007A737
0x18007a710  test    dword ptr [rcx+1Ch], 800h
0x18007a717  jz      short loc_18007A737
0x18007a719  cmp     byte ptr [rcx+19h], 6
0x18007a71d  jb      short loc_18007A737
0x18007a71f  mov     rcx, [rcx+10h]
0x18007a723  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18007a72a  mov     edx, 3E4h
0x18007a72f  mov     r9d, ebx
0x18007a732  call    WPP_SF_d
0x18007a737  mov     eax, ebx
0x18007a739  add     rsp, 40h
0x18007a73d  pop     r14
0x18007a73f  pop     r13
0x18007a741  pop     r12
0x18007a743  pop     rdi
0x18007a744  pop     rsi
0x18007a745  pop     rbp
0x18007a746  pop     rbx
0x18007a747  retn
```
