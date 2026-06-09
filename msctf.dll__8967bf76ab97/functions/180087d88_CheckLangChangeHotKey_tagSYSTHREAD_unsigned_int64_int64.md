# CheckLangChangeHotKey(tagSYSTHREAD *,unsigned __int64,__int64)

- ea: `0x180087d88`
- end: `0x1800880da`
- name: `?CheckLangChangeHotKey@@YAHPEAUtagSYSTHREAD@@_K_J@Z`
- size: `850`
- prototype: `__int64 __fastcall(struct tagSYSTHREAD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800851a8`

## callees

- `0x180010fbc`
- `0x18005886c`
- `0x180076428`
- `0x180087d88`
- `0x1800ae670`
- `0x1800aedb0`
- `0x1800b7078`
- `0x1800daa44`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180087f9b`
- `ntdll!RtlPublishWnfStateData` at `0x180088095`
- `ntdll!RtlPublishWnfStateData` at `0x180087f9b`
- `ntdll!RtlPublishWnfStateData` at `0x180088095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008803e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800880c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008803e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800880c1`
- `USER32!PostThreadMessageW` at `0x180087f60`
- `USER32!PostThreadMessageW` at `0x180087fd0`
- `USER32!PostThreadMessageW` at `0x180088051`
- `USER32!PostThreadMessageW` at `0x1800880d2`
- `USER32!PostThreadMessageW` at `0x180087f60`
- `USER32!PostThreadMessageW` at `0x180087fd0`
- `USER32!PostThreadMessageW` at `0x180088051`
- `USER32!PostThreadMessageW` at `0x1800880d2`

## pseudocode

```c
__int64 __fastcall CheckLangChangeHotKey(struct tagSYSTHREAD *a1, __int64 a2, int a3)
{
  __int64 v6; // r9
  __int64 v7; // r11
  int v8; // eax
  int v9; // ecx
  __int64 v10; // r10
  int v11; // eax
  int v12; // ebp
  int v13; // r8d
  int v14; // r8d
  int v16; // r8d
  int v17; // ecx
  LPARAM v18; // rdi
  UINT v19; // ebx
  DWORD CurrentThreadId; // eax
  int v21; // ecx
  UINT v22; // ebx
  DWORD v23; // eax
  CInputProfileManager *v24; // rcx
  LPARAM v25; // rsi
  UINT v26; // ebx
  DWORD v27; // eax
  CInputProfileManager *v28; // rcx
  UINT v29; // ebx
  DWORD v30; // eax
  unsigned int v31[18]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v32; // [rsp+98h] [rbp+20h] BYREF

  if ( !(unsigned int)EnsureLangChangeHotKey(0) )
    return 0;
  if ( !a1 )
    return 0;
  if ( (unsigned __int16)a3 > 1uLL )
    return 0;
  v6 = a3 & 0x80000000;
  if ( (a3 & 0x80000000) == 0 && (a3 & 0x40000000) != 0 )
    return 0;
  v7 = (unsigned int)g_uLangHotKeyVKey;
  if ( (unsigned int)g_uLangHotKeyVKey == a2 || HIDWORD(g_uLangHotKeyVKey) == a2 )
  {
    v9 = 1;
  }
  else
  {
    v8 = *((_DWORD *)a1 + 48);
    if ( (v8 & 2) != 0 )
      *((_DWORD *)a1 + 48) = v8 & 0xFFFFFFFD;
    v9 = 0;
  }
  v10 = (unsigned int)g_uKeyTipHotKeyVKey;
  if ( (unsigned int)g_uKeyTipHotKeyVKey == a2 || HIDWORD(g_uKeyTipHotKeyVKey) == a2 )
  {
    v12 = 1;
  }
  else
  {
    v11 = *((_DWORD *)a1 + 48);
    if ( (v11 & 4) != 0 )
      *((_DWORD *)a1 + 48) = v11 & 0xFFFFFFFB;
    v12 = 0;
  }
  if ( v9 )
  {
    v13 = *((_DWORD *)a1 + 48);
    if ( (v13 & 2) == 0
      && (a3 & 0x80000000) == 0
      && (g_uLangHotKeyModifiers && (unsigned int)ModifiersCheck(g_uModifiers, g_uLangHotKeyModifiers)
       || a2 == 192 && v7 == 192) )
    {
      v14 = v13 | 2;
LABEL_26:
      *((_DWORD *)a1 + 48) = v14;
      return 1;
    }
  }
  if ( !v12 || (v16 = *((_DWORD *)a1 + 48), (v16 & 4) != 0) )
  {
    if ( !v6 )
    {
      if ( a2 != 192 )
        return 0;
      goto LABEL_38;
    }
LABEL_41:
    v17 = *((_DWORD *)a1 + 48);
    *((_DWORD *)a1 + 48) = v17 & 0xFFFFFFF9;
    if ( (v17 & 2) != 0 )
    {
      RemoveInputLangChangeRequests();
      if ( (_DWORD)g_uLangHotKeyVKey == 16 )
      {
        if ( (_BYTE)a2 == 16 && (a3 & 0xFF0000) == 0x360000 || (v18 = 0, (g_uModifiers & 0x20) != 0) )
          v18 = 1;
        v19 = g_msgPrivate;
        CurrentThreadId = GetCurrentThreadId();
        PostThreadMessageW(CurrentThreadId, v19, 5u, v18);
        v32 = (2 * (g_uModifiers & 7)) | 1;
        RtlPublishWnfStateData(WNF_IME_INPUT_SWITCH_NOTIFY, 0, &v32, 4, 0);
      }
      else
      {
        if ( (_DWORD)g_uLangHotKeyVKey != 192 )
          return 0;
        v22 = g_msgPrivate;
        v23 = GetCurrentThreadId();
        PostThreadMessageW(v23, v22, 5u, 0);
      }
      v21 = 100;
    }
    else
    {
      if ( (v17 & 4) == 0 )
        return 0;
      RemoveInputLangChangeRequests();
      v24 = (CInputProfileManager *)*((_QWORD *)a1 + 4);
      LOWORD(v32) = 0;
      if ( v24 )
        LOWORD(v32) = CInputProfileManager::GetActiveLanguage(v24);
      if ( (_DWORD)g_uKeyTipHotKeyVKey == 16 )
      {
        if ( (_BYTE)a2 == 16 && (a3 & 0xFF0000) == 0x360000 || (v25 = 0, (g_uModifiers & 0x20) != 0) )
          v25 = 1;
        v26 = g_msgPrivate;
        v27 = GetCurrentThreadId();
        PostThreadMessageW(v27, v26, 6u, v25);
        v28 = (CInputProfileManager *)*((_QWORD *)a1 + 4);
        if ( v28 && CInputProfileManager::HasNextKeyboardProfile(v28) )
        {
          v31[0] = 2 * (g_uModifiers & 7);
          RtlPublishWnfStateData(WNF_IME_INPUT_SWITCH_NOTIFY, 0, v31, 4, 0);
        }
      }
      else
      {
        if ( (_DWORD)g_uKeyTipHotKeyVKey != 192 )
          return 0;
        v29 = g_msgPrivate;
        v30 = GetCurrentThreadId();
        PostThreadMessageW(v30, v29, 6u, 0);
      }
      CtfTraceLoggingTelemetry::KbdSwitchHotkeyUsage<unsigned short &>(&v32);
      v21 = 101;
    }
    FileInputSwitchSqmEvent(v21);
    return 1;
  }
  if ( v6 )
    goto LABEL_41;
  if ( g_uKeyTipHotKeyModifiers && (unsigned int)ModifiersCheck(g_uModifiers, g_uKeyTipHotKeyModifiers) )
    goto LABEL_35;
  if ( a2 == 192 )
  {
    if ( v10 == 192 )
    {
LABEL_35:
      v14 = v16 | 4;
      goto LABEL_26;
    }
LABEL_38:
    if ( v7 == 192 || v10 == 192 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180087d88  push    rbx
0x180087d8a  push    rbp
0x180087d8b  push    rsi
0x180087d8c  push    rdi
0x180087d8d  push    r12
0x180087d8f  push    r15
0x180087d91  sub     rsp, 48h
0x180087d95  mov     rdi, rcx
0x180087d98  mov     rbx, r8
0x180087d9b  xor     ecx, ecx; int
0x180087d9d  mov     rsi, rdx
0x180087da0  call    ?EnsureLangChangeHotKey@@YAHH@Z; EnsureLangChangeHotKey(int)
0x180087da5  test    eax, eax
0x180087da7  jz      loc_180087EE4
0x180087dad  test    rdi, rdi
0x180087db0  jz      loc_180087EE4
0x180087db6  movzx   eax, bx
0x180087db9  mov     r15d, 1
0x180087dbf  cmp     rax, r15
0x180087dc2  ja      loc_180087EE4
0x180087dc8  mov     eax, 80000000h
0x180087dcd  mov     r9, rbx
0x180087dd0  and     r9, rax
0x180087dd3  jnz     short loc_180087DE0
0x180087dd5  bt      rbx, 1Eh
0x180087dda  jb      loc_180087EE4
0x180087de0  mov     r11d, dword ptr cs:?g_uLangHotKeyVKey@@3PAIA; uint near * g_uLangHotKeyVKey
0x180087de7  cmp     r11, rsi
0x180087dea  jz      short loc_180087E0E
0x180087dec  mov     eax, dword ptr cs:?g_uLangHotKeyVKey@@3PAIA+4; uint near * g_uLangHotKeyVKey
0x180087df2  cmp     rax, rsi
0x180087df5  jz      short loc_180087E0E
0x180087df7  mov     eax, [rdi+0C0h]
0x180087dfd  test    al, 2
0x180087dff  jz      short loc_180087E0A
0x180087e01  and     eax, 0FFFFFFFDh
0x180087e04  mov     [rdi+0C0h], eax
0x180087e0a  xor     ecx, ecx
0x180087e0c  jmp     short loc_180087E11
0x180087e0e  mov     ecx, r15d
0x180087e11  mov     r10d, dword ptr cs:?g_uKeyTipHotKeyVKey@@3PAIA; uint near * g_uKeyTipHotKeyVKey
0x180087e18  cmp     r10, rsi
0x180087e1b  jz      short loc_180087E3F
0x180087e1d  mov     eax, dword ptr cs:?g_uKeyTipHotKeyVKey@@3PAIA+4; uint near * g_uKeyTipHotKeyVKey
0x180087e23  cmp     rax, rsi
0x180087e26  jz      short loc_180087E3F
0x180087e28  mov     eax, [rdi+0C0h]
0x180087e2e  test    al, 4
0x180087e30  jz      short loc_180087E3B
0x180087e32  and     eax, 0FFFFFFFBh
0x180087e35  mov     [rdi+0C0h], eax
0x180087e3b  xor     ebp, ebp
0x180087e3d  jmp     short loc_180087E42
0x180087e3f  mov     ebp, r15d
0x180087e42  mov     r12d, 0C0h
0x180087e48  test    ecx, ecx
0x180087e4a  jz      short loc_180087E91
0x180087e4c  mov     r8d, [rdi+0C0h]
0x180087e53  test    r8b, 2
0x180087e57  jnz     short loc_180087E91
0x180087e59  test    r9, r9
0x180087e5c  jnz     short loc_180087E91
0x180087e5e  mov     edx, cs:?g_uLangHotKeyModifiers@@3IA; unsigned int
0x180087e64  test    edx, edx
0x180087e66  jz      short loc_180087E77
0x180087e68  mov     ecx, cs:?g_uModifiers@@3IA; unsigned int
0x180087e6e  call    ?ModifiersCheck@@YAHII@Z; ModifiersCheck(uint,uint)
0x180087e73  test    eax, eax
0x180087e75  jnz     short loc_180087E81
0x180087e77  cmp     rsi, r12
0x180087e7a  jnz     short loc_180087E91
0x180087e7c  cmp     r11, r12
0x180087e7f  jnz     short loc_180087E91
0x180087e81  or      r8d, 2
0x180087e85  mov     [rdi+0C0h], r8d
0x180087e8c  mov     eax, r15d
0x180087e8f  jmp     short loc_180087EE6
0x180087e91  test    ebp, ebp
0x180087e93  jz      short loc_180087ED0
0x180087e95  mov     r8d, [rdi+0C0h]
0x180087e9c  test    r8b, 4
0x180087ea0  jnz     short loc_180087ED0
0x180087ea2  test    r9, r9
0x180087ea5  jnz     short loc_180087EF3
0x180087ea7  mov     edx, cs:?g_uKeyTipHotKeyModifiers@@3IA; unsigned int
0x180087ead  test    edx, edx
0x180087eaf  jz      short loc_180087EC0
0x180087eb1  mov     ecx, cs:?g_uModifiers@@3IA; unsigned int
0x180087eb7  call    ?ModifiersCheck@@YAHII@Z; ModifiersCheck(uint,uint)
0x180087ebc  test    eax, eax
0x180087ebe  jnz     short loc_180087ECA
0x180087ec0  cmp     rsi, r12
0x180087ec3  jnz     short loc_180087EE4
0x180087ec5  cmp     r10, r12
0x180087ec8  jnz     short loc_180087EDA
0x180087eca  or      r8d, 4
0x180087ece  jmp     short loc_180087E85
0x180087ed0  test    r9, r9
0x180087ed3  jnz     short loc_180087EF3
0x180087ed5  cmp     rsi, r12
0x180087ed8  jnz     short loc_180087EE4
0x180087eda  cmp     r11, r12
0x180087edd  jz      short loc_180087E8C
0x180087edf  cmp     r10, r12
0x180087ee2  jz      short loc_180087E8C
0x180087ee4  xor     eax, eax
0x180087ee6  add     rsp, 48h
0x180087eea  pop     r15
0x180087eec  pop     r12
0x180087eee  pop     rdi
0x180087eef  pop     rsi
0x180087ef0  pop     rbp
0x180087ef1  pop     rbx
0x180087ef2  retn
0x180087ef3  mov     ecx, [rdi+0C0h]
0x180087ef9  mov     eax, ecx
0x180087efb  and     eax, 0FFFFFFFDh
0x180087efe  and     eax, 0FFFFFFFBh
0x180087f01  mov     [rdi+0C0h], eax
0x180087f07  test    cl, 2
0x180087f0a  jz      loc_180087FD8
0x180087f10  call    ?RemoveInputLangChangeRequests@@YAXXZ; RemoveInputLangChangeRequests(void)
0x180087f15  mov     rax, cs:?g_uLangHotKeyVKey@@3PAIA; uint near * g_uLangHotKeyVKey
0x180087f1c  cmp     eax, 10h
0x180087f1f  jnz     loc_180087FB0
0x180087f25  cmp     sil, al
0x180087f28  jnz     short loc_180087F39
0x180087f2a  and     ebx, 0FF0000h
0x180087f30  cmp     rbx, 360000h
0x180087f37  jz      short loc_180087F44
0x180087f39  xor     edi, edi
0x180087f3b  test    byte ptr cs:?g_uModifiers@@3IA, 20h; uint g_uModifiers
0x180087f42  jz      short loc_180087F47
0x180087f44  mov     rdi, r15
0x180087f47  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x180087f4d  call    cs:__imp_GetCurrentThreadId
0x180087f53  mov     r9, rdi; lParam
0x180087f56  mov     r8d, 5; wParam
0x180087f5c  mov     ecx, eax; idThread
0x180087f5e  mov     edx, ebx; Msg
0x180087f60  call    cs:__imp_PostThreadMessageW
0x180087f66  mov     eax, cs:?g_uModifiers@@3IA; uint g_uModifiers
0x180087f6c  lea     r8, [rsp+78h+arg_18]
0x180087f74  mov     rcx, cs:WNF_IME_INPUT_SWITCH_NOTIFY
0x180087f7b  and     eax, 7
0x180087f7e  add     eax, eax
0x180087f80  mov     [rsp+78h+var_58], 0
0x180087f89  or      eax, r15d
0x180087f8c  mov     r9d, 4
0x180087f92  xor     edx, edx
0x180087f94  mov     [rsp+78h+arg_18], eax
0x180087f9b  call    cs:__imp_RtlPublishWnfStateData
0x180087fa1  mov     ecx, 64h ; 'd'; int
0x180087fa6  call    ?FileInputSwitchSqmEvent@@YAXH@Z; FileInputSwitchSqmEvent(int)
0x180087fab  jmp     loc_180087E8C
0x180087fb0  cmp     eax, r12d
0x180087fb3  jnz     loc_180087EE4
0x180087fb9  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x180087fbf  call    cs:__imp_GetCurrentThreadId
0x180087fc5  xor     r9d, r9d; lParam
0x180087fc8  mov     edx, ebx; Msg
0x180087fca  mov     ecx, eax; idThread
0x180087fcc  lea     r8d, [r9+5]; wParam
0x180087fd0  call    cs:__imp_PostThreadMessageW
0x180087fd6  jmp     short loc_180087FA1
0x180087fd8  test    cl, 4
0x180087fdb  jz      loc_180087EE4
0x180087fe1  call    ?RemoveInputLangChangeRequests@@YAXXZ; RemoveInputLangChangeRequests(void)
0x180087fe6  mov     rcx, [rdi+20h]; this
0x180087fea  xor     eax, eax
0x180087fec  mov     word ptr [rsp+78h+arg_18], ax
0x180087ff4  test    rcx, rcx
0x180087ff7  jz      short loc_180088006
0x180087ff9  call    ?GetActiveLanguage@CInputProfileManager@@QEBAGXZ; CInputProfileManager::GetActiveLanguage(void)
0x180087ffe  mov     word ptr [rsp+78h+arg_18], ax
0x180088006  mov     rax, cs:?g_uKeyTipHotKeyVKey@@3PAIA; uint near * g_uKeyTipHotKeyVKey
0x18008800d  cmp     eax, 10h
0x180088010  jnz     loc_1800880B2
0x180088016  cmp     sil, al
0x180088019  jnz     short loc_18008802A
0x18008801b  and     ebx, 0FF0000h
0x180088021  cmp     rbx, 360000h
0x180088028  jz      short loc_180088035
0x18008802a  xor     esi, esi
0x18008802c  test    byte ptr cs:?g_uModifiers@@3IA, 20h; uint g_uModifiers
0x180088033  jz      short loc_180088038
0x180088035  mov     rsi, r15
0x180088038  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x18008803e  call    cs:__imp_GetCurrentThreadId
0x180088044  mov     r9, rsi; lParam
0x180088047  mov     r8d, 6; wParam
0x18008804d  mov     ecx, eax; idThread
0x18008804f  mov     edx, ebx; Msg
0x180088051  call    cs:__imp_PostThreadMessageW
0x180088057  mov     rcx, [rdi+20h]; this
0x18008805b  test    rcx, rcx
0x18008805e  jz      short loc_18008809B
0x180088060  call    ?HasNextKeyboardProfile@CInputProfileManager@@QEAA_NXZ; CInputProfileManager::HasNextKeyboardProfile(void)
0x180088065  test    al, al
0x180088067  jz      short loc_18008809B
0x180088069  mov     eax, cs:?g_uModifiers@@3IA; uint g_uModifiers
0x18008806f  lea     r8, [rsp+78h+var_48]
0x180088074  mov     rcx, cs:WNF_IME_INPUT_SWITCH_NOTIFY
0x18008807b  and     eax, 7
0x18008807e  add     eax, eax
0x180088080  mov     [rsp+78h+var_58], 0
0x180088089  mov     r9d, 4
0x18008808f  mov     [rsp+78h+var_48], eax
0x180088093  xor     edx, edx
0x180088095  call    cs:__imp_RtlPublishWnfStateData
0x18008809b  lea     rcx, [rsp+78h+arg_18]
0x1800880a3  call    ??$KbdSwitchHotkeyUsage@AEAG@CtfTraceLoggingTelemetry@@SAXAEAG@Z; CtfTraceLoggingTelemetry::KbdSwitchHotkeyUsage<ushort &>(ushort &)
0x1800880a8  mov     ecx, 65h ; 'e'
0x1800880ad  jmp     loc_180087FA6
0x1800880b2  cmp     eax, r12d
0x1800880b5  jnz     loc_180087EE4
0x1800880bb  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x1800880c1  call    cs:__imp_GetCurrentThreadId
0x1800880c7  xor     r9d, r9d; lParam
0x1800880ca  mov     edx, ebx; Msg
0x1800880cc  mov     ecx, eax; idThread
0x1800880ce  lea     r8d, [r9+6]; wParam
0x1800880d2  call    cs:__imp_PostThreadMessageW
0x1800880d8  jmp     short loc_18008809B
```
