# CtfImeSetActiveContext

- ea: `0x18001e650`
- end: `0x18001e9e7`
- name: `CtfImeSetActiveContext`
- size: `919`
- prototype: `__int64 __fastcall(HIMC)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800139a4`
- `0x1800185f0`
- `0x18001a460`
- `0x18001cc80`
- `0x18001e2c0`
- `0x18001e650`
- `0x180045040`
- `0x18009eaea`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18001e8d7`
- `ntdll!RtlDllShutdownInProgress` at `0x18001e8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e870`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e915`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e915`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e68d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e68d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e8fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e8fa`
- `IMM32!ImmLockIMC` at `0x18001e6c5`
- `IMM32!ImmLockIMC` at `0x18001e6c5`
- `IMM32!ImmUnlockIMC` at `0x18001e81a`
- `IMM32!ImmUnlockIMC` at `0x18001e882`
- `IMM32!ImmUnlockIMC` at `0x18001e81a`
- `IMM32!ImmUnlockIMC` at `0x18001e882`
- `IMM32!ImmLockIMCC` at `0x18001e745`
- `IMM32!ImmLockIMCC` at `0x18001e7ce`
- `IMM32!ImmLockIMCC` at `0x18001e745`
- `IMM32!ImmLockIMCC` at `0x18001e7ce`
- `IMM32!ImmUnlockIMCC` at `0x18001e7e6`
- `IMM32!ImmUnlockIMCC` at `0x18001e7fe`
- `IMM32!ImmUnlockIMCC` at `0x18001e83e`
- `IMM32!ImmUnlockIMCC` at `0x18001e866`
- `IMM32!ImmUnlockIMCC` at `0x18001e7e6`
- `IMM32!ImmUnlockIMCC` at `0x18001e7fe`
- `IMM32!ImmUnlockIMCC` at `0x18001e83e`
- `IMM32!ImmUnlockIMCC` at `0x18001e866`
- `ext-ms-win-imm-l1-1-0!ImmNotifyIME` at `0x18001e9ac`
- `ext-ms-win-imm-l1-1-0!ImmNotifyIME` at `0x18001e9ac`

## string_xrefs

- `0x18001e825`: `ImeSetActiveContext. comp==NULL.`

## pseudocode

```c
__int64 __fastcall CtfImeSetActiveContext(HIMC a1, int a2)
{
  _DWORD *Value; // rdi
  unsigned int v4; // ebx
  LPINPUTCONTEXT v5; // rax
  LPINPUTCONTEXT v6; // rsi
  HIMCC v8; // r13
  __int64 *v9; // r14
  signed int v10; // eax
  __int64 *v11; // rdx
  __int64 v12; // rdi
  __int16 v13; // r12
  HIMCC hCompStr; // rdi
  _DWORD *v15; // rax
  _DWORD *v16; // rax
  __int16 v17; // ax
  __int64 v18; // rax
  _QWORD v20[3]; // [rsp+28h] [rbp-A1h] BYREF
  int v21; // [rsp+40h] [rbp-89h]
  int v22; // [rsp+44h] [rbp-85h]
  void **v23; // [rsp+48h] [rbp-81h] BYREF
  __int64 *v24; // [rsp+50h] [rbp-79h]
  HIMCC v25; // [rsp+58h] [rbp-71h]
  signed int v26; // [rsp+60h] [rbp-69h]
  _BYTE v27[4]; // [rsp+70h] [rbp-59h] BYREF
  __int16 v28; // [rsp+74h] [rbp-55h]

  if ( TLS::dwTLSIndex == -1 )
    goto LABEL_52;
  Value = TlsGetValue(TLS::dwTLSIndex);
  v4 = 1;
  if ( Value )
    goto LABEL_3;
  if ( RtlDllShutdownInProgress()
    || !(unsigned int)_IsFlsCallbackNotCalled()
    || (v16 = LocalAlloc(0x40u, 0x38u), (Value = v16) == 0) )
  {
LABEL_52:
    CicTrace(1u, "ImeSetActiveContext. ptls==NULL.");
    return 0;
  }
  if ( !TlsSetValue(TLS::dwTLSIndex, v16) )
  {
    cicMemFree(Value);
    goto LABEL_52;
  }
  Value[6] |= 1u;
  Value[8] |= 1u;
LABEL_3:
  if ( !a1 )
    return v4;
  v20[2] = a1;
  v20[0] = &IMCLock::`vftable';
  v22 = 0;
  v5 = ImmLockIMC(a1);
  v20[1] = v5;
  v6 = v5;
  if ( !v5 )
  {
    v21 = -2147467259;
    CicTrace(1u, "ImeSetActiveContext. imc==NULL");
LABEL_6:
    IMCLock::~IMCLock((IMCLock *)v20);
    return 0;
  }
  v8 = *(HIMCC *)&v5[1].lfFont.W.lfWidth;
  v9 = 0;
  v10 = 0;
  v21 = 0;
  v11 = 0;
  v24 = 0;
  v25 = v8;
  v26 = 0;
  if ( v8 )
  {
    v24 = (__int64 *)ImmLockIMCC(v8);
    v9 = v24;
    v11 = v24;
    v10 = v24 == 0 ? 0x80004005 : 0;
    v26 = v10;
  }
  v23 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
  if ( !v11 || v10 < 0 )
  {
    CicTrace(1u, "ImeSetActiveContext. imc_ctfime==NULL");
    InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v23);
    goto LABEL_6;
  }
  v12 = *((_QWORD *)Value + 1);
  if ( !v12 )
  {
    CicTrace(1u, "ImeSetActiveContext. _pProfile==NULL.");
    if ( v9 && !ImmUnlockIMCC(v8) )
      GetLastError();
    if ( !v6 )
      return 0;
    goto LABEL_36;
  }
  v13 = 0;
  if ( *(_QWORD *)(v12 + 8) )
  {
    if ( (*(_BYTE *)(v12 + 24) & 2) != 0 )
    {
      v13 = *(_WORD *)(v12 + 32);
    }
    else
    {
      memset_0(v27, 0, 0x58u);
      if ( (*(int (__fastcall **)(_QWORD, GUID *, _BYTE *))(**(_QWORD **)(v12 + 8) + 80LL))(
             *(_QWORD *)(v12 + 8),
             &GUID_TFCAT_TIP_KEYBOARD,
             v27) < 0 )
      {
        CicTrace(2u, "CicProfile::GetLangId: failed for GetCurrentLanguage");
      }
      else
      {
        v17 = v28;
        *(_DWORD *)(v12 + 24) |= 2u;
        v13 = v17;
        *(_WORD *)(v12 + 32) = v17;
      }
    }
  }
  if ( a2 )
  {
    if ( (v13 & 0x3FF) == 4 )
    {
      v6->cfCandForm[0].dwStyle = 0;
      v6->cfCandForm[0].dwIndex = -1;
    }
    goto LABEL_24;
  }
  if ( (TF_GetAppCompatFlags() & 0x8000) == 0 )
  {
    hCompStr = v6->hCompStr;
    if ( hCompStr )
    {
      v15 = ImmLockIMCC(v6->hCompStr);
      if ( v15 )
      {
        if ( v15[11] )
        {
          v18 = *v9;
          if ( *v9 )
          {
            if ( (*(_BYTE *)(v18 + 208) & 1) == 0 && (*(_BYTE *)(v18 + 212) & 1) == 0 )
              ImmNotifyIME(a1, 0x15u, 1u, 0);
          }
        }
        if ( !ImmUnlockIMCC(hCompStr) )
          GetLastError();
        goto LABEL_24;
      }
    }
    CicTrace(2u, "ImeSetActiveContext. comp==NULL.");
    if ( v9 && !ImmUnlockIMCC(v8) )
      GetLastError();
LABEL_36:
    ImmUnlockIMC(a1);
    return 0;
  }
LABEL_24:
  if ( v9 && !ImmUnlockIMCC(v8) )
    GetLastError();
  if ( v6 )
    ImmUnlockIMC(a1);
  return v4;
}

```

## disassembly

```asm
0x18001e650  push    rbp
0x18001e652  push    rbx
0x18001e653  push    rsi
0x18001e654  push    rdi
0x18001e655  push    r12
0x18001e657  push    r13
0x18001e659  push    r14
0x18001e65b  push    r15
0x18001e65d  lea     rbp, [rsp-1Fh]
0x18001e662  sub     rsp, 0E8h
0x18001e669  mov     rax, cs:__security_cookie
0x18001e670  xor     rax, rsp
0x18001e673  mov     [rbp+57h+var_50], rax
0x18001e677  mov     r15, rcx
0x18001e67a  mov     [rsp+120h+var_100], edx
0x18001e67e  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x18001e684  cmp     ecx, 0FFFFFFFFh
0x18001e687  jz      loc_18001E9E0
0x18001e68d  call    cs:__imp_TlsGetValue
0x18001e693  mov     rdi, rax
0x18001e696  mov     ebx, 1
0x18001e69b  test    rax, rax
0x18001e69e  jz      loc_18001E8D7
0x18001e6a4  test    r15, r15
0x18001e6a7  jz      short loc_18001E6FA
0x18001e6a9  lea     rax, ??_7IMCLock@@6B@; const IMCLock::`vftable'
0x18001e6b0  mov     [rsp+120h+var_E8], r15
0x18001e6b5  mov     rcx, r15; HIMC
0x18001e6b8  mov     [rsp+120h+var_F8], rax
0x18001e6bd  mov     [rsp+120h+var_DC], 0
0x18001e6c5  call    cs:__imp_ImmLockIMC
0x18001e6cb  mov     [rsp+120h+var_F0], rax
0x18001e6d0  mov     rsi, rax
0x18001e6d3  test    rax, rax
0x18001e6d6  jnz     short loc_18001E71C
0x18001e6d8  lea     rdx, aImesetactiveco_1; "ImeSetActiveContext. imc==NULL"
0x18001e6df  mov     [rsp+120h+var_E0], 80004005h
0x18001e6e7  mov     ecx, ebx; unsigned int
0x18001e6e9  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e6ee  lea     rcx, [rsp+120h+var_F8]; this
0x18001e6f3  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x18001e6f8  xor     ebx, ebx
0x18001e6fa  mov     eax, ebx
0x18001e6fc  mov     rcx, [rbp+57h+var_50]
0x18001e700  xor     rcx, rsp; StackCookie
0x18001e703  call    __security_check_cookie
0x18001e708  add     rsp, 0E8h
0x18001e70f  pop     r15
0x18001e711  pop     r14
0x18001e713  pop     r13
0x18001e715  pop     r12
0x18001e717  pop     rdi
0x18001e718  pop     rsi
0x18001e719  pop     rbx
0x18001e71a  pop     rbp
0x18001e71b  retn
0x18001e71c  mov     r13, [rax+188h]
0x18001e723  xor     r14d, r14d
0x18001e726  xor     eax, eax
0x18001e728  mov     [rsp+120h+var_E0], 0
0x18001e730  xor     edx, edx
0x18001e732  mov     [rbp+57h+var_D0], r14
0x18001e736  mov     [rbp+57h+var_C8], r13
0x18001e73a  mov     [rbp+57h+var_C0], eax
0x18001e73d  test    r13, r13
0x18001e740  jz      short loc_18001E767
0x18001e742  mov     rcx, r13; HIMCC
0x18001e745  call    cs:__imp_ImmLockIMCC
0x18001e74b  mov     rcx, rax
0x18001e74e  mov     [rbp+57h+var_D0], rax
0x18001e752  mov     r14, rax
0x18001e755  mov     rdx, rax
0x18001e758  neg     rcx
0x18001e75b  sbb     eax, eax
0x18001e75d  not     eax
0x18001e75f  and     eax, 80004005h
0x18001e764  mov     [rbp+57h+var_C0], eax
0x18001e767  lea     rcx, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x18001e76e  mov     [rsp+120h+var_D8], rcx
0x18001e773  test    rdx, rdx
0x18001e776  jz      loc_18001E8BA
0x18001e77c  test    eax, eax
0x18001e77e  js      loc_18001E8BA
0x18001e784  mov     rdi, [rdi+8]
0x18001e788  test    rdi, rdi
0x18001e78b  jz      loc_18001E850
0x18001e791  xor     r12d, r12d
0x18001e794  cmp     [rdi+8], r12
0x18001e798  jz      short loc_18001E7A9
0x18001e79a  test    byte ptr [rdi+18h], 2
0x18001e79e  jz      loc_18001E92E
0x18001e7a4  movzx   r12d, word ptr [rdi+20h]
0x18001e7a9  cmp     [rsp+120h+var_100], 0
0x18001e7ae  jnz     loc_18001E88D
0x18001e7b4  call    TF_GetAppCompatFlags
0x18001e7b9  bt      eax, 0Fh
0x18001e7bd  jb      short loc_18001E7F6
0x18001e7bf  mov     rdi, [rsi+120h]
0x18001e7c6  test    rdi, rdi
0x18001e7c9  jz      short loc_18001E825
0x18001e7cb  mov     rcx, rdi; HIMCC
0x18001e7ce  call    cs:__imp_ImmLockIMCC
0x18001e7d4  test    rax, rax
0x18001e7d7  jz      short loc_18001E825
0x18001e7d9  cmp     dword ptr [rax+2Ch], 0
0x18001e7dd  jnz     loc_18001E9D2
0x18001e7e3  mov     rcx, rdi; HIMCC
0x18001e7e6  call    cs:__imp_ImmUnlockIMCC
0x18001e7ec  test    eax, eax
0x18001e7ee  jnz     short loc_18001E7F6
0x18001e7f0  call    cs:__imp_GetLastError
0x18001e7f6  test    r14, r14
0x18001e7f9  jz      short loc_18001E80E
0x18001e7fb  mov     rcx, r13; HIMCC
0x18001e7fe  call    cs:__imp_ImmUnlockIMCC
0x18001e804  test    eax, eax
0x18001e806  jnz     short loc_18001E80E
0x18001e808  call    cs:__imp_GetLastError
0x18001e80e  test    rsi, rsi
0x18001e811  jz      loc_18001E6FA
0x18001e817  mov     rcx, r15; HIMC
0x18001e81a  call    cs:__imp_ImmUnlockIMC
0x18001e820  jmp     loc_18001E6FA
0x18001e825  lea     rdx, aImesetactiveco; "ImeSetActiveContext. comp==NULL."
0x18001e82c  mov     ecx, 2; unsigned int
0x18001e831  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e836  test    r14, r14
0x18001e839  jz      short loc_18001E87F
0x18001e83b  mov     rcx, r13; HIMCC
0x18001e83e  call    cs:__imp_ImmUnlockIMCC
0x18001e844  test    eax, eax
0x18001e846  jnz     short loc_18001E87F
0x18001e848  call    cs:__imp_GetLastError
0x18001e84e  jmp     short loc_18001E87F
0x18001e850  lea     rdx, aImesetactiveco_3; "ImeSetActiveContext. _pProfile==NULL."
0x18001e857  mov     ecx, ebx; unsigned int
0x18001e859  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e85e  test    r14, r14
0x18001e861  jz      short loc_18001E876
0x18001e863  mov     rcx, r13; HIMCC
0x18001e866  call    cs:__imp_ImmUnlockIMCC
0x18001e86c  test    eax, eax
0x18001e86e  jnz     short loc_18001E876
0x18001e870  call    cs:__imp_GetLastError
0x18001e876  test    rsi, rsi
0x18001e879  jz      loc_18001E6F8
0x18001e87f  mov     rcx, r15; HIMC
0x18001e882  call    cs:__imp_ImmUnlockIMC
0x18001e888  jmp     loc_18001E6F8
0x18001e88d  mov     eax, 3FFh
0x18001e892  and     r12w, ax
0x18001e896  cmp     r12w, 4
0x18001e89b  jnz     loc_18001E7F6
0x18001e8a1  mov     dword ptr [rsi+0A0h], 0
0x18001e8ab  mov     dword ptr [rsi+9Ch], 0FFFFFFFFh
0x18001e8b5  jmp     loc_18001E7F6
0x18001e8ba  lea     rdx, aImesetactiveco_2; "ImeSetActiveContext. imc_ctfime==NULL"
0x18001e8c1  mov     ecx, ebx; unsigned int
0x18001e8c3  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e8c8  lea     rcx, [rsp+120h+var_D8]; this
0x18001e8cd  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x18001e8d2  jmp     loc_18001E6EE
0x18001e8d7  call    cs:__imp_RtlDllShutdownInProgress
0x18001e8dd  test    al, al
0x18001e8df  jnz     loc_18001E9BF
0x18001e8e5  call    ?_IsFlsCallbackNotCalled@@YAHXZ; _IsFlsCallbackNotCalled(void)
0x18001e8ea  test    eax, eax
0x18001e8ec  jz      loc_18001E9BF
0x18001e8f2  mov     edx, 38h ; '8'; uBytes
0x18001e8f7  lea     ecx, [rdx+8]; uFlags
0x18001e8fa  call    cs:__imp_LocalAlloc
0x18001e900  mov     rdi, rax
0x18001e903  test    rax, rax
0x18001e906  jz      loc_18001E9BF
0x18001e90c  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x18001e912  mov     rdx, rax; lpTlsValue
0x18001e915  call    cs:__imp_TlsSetValue
0x18001e91b  test    eax, eax
0x18001e91d  jz      loc_18001E9B7
0x18001e923  or      [rdi+18h], ebx
0x18001e926  or      [rdi+20h], ebx
0x18001e929  jmp     loc_18001E6A4
0x18001e92e  xor     edx, edx; Val
0x18001e930  lea     rcx, [rbp+57h+var_B0]; void *
0x18001e934  lea     r8d, [rdx+58h]; Size
0x18001e938  call    memset_0
0x18001e93d  mov     rcx, [rdi+8]
0x18001e941  lea     r8, [rbp+57h+var_B0]
0x18001e945  lea     rdx, GUID_TFCAT_TIP_KEYBOARD
0x18001e94c  mov     rax, [rcx]
0x18001e94f  mov     rax, [rax+50h]
0x18001e953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e958  test    eax, eax
0x18001e95a  js      short loc_18001E971
0x18001e95c  movzx   eax, [rbp+57h+var_AC]
0x18001e960  or      dword ptr [rdi+18h], 2
0x18001e964  movzx   r12d, ax
0x18001e968  mov     [rdi+20h], ax
0x18001e96c  jmp     loc_18001E7A9
0x18001e971  xor     eax, eax
0x18001e973  lea     rdx, aCicprofileGetl; "CicProfile::GetLangId: failed for GetCu"...
0x18001e97a  lea     ecx, [rax+2]; unsigned int
0x18001e97d  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e982  jmp     loc_18001E7A9
0x18001e987  test    [rax+0D0h], bl
0x18001e98d  jnz     loc_18001E7E3
0x18001e993  test    [rax+0D4h], bl
0x18001e999  jnz     loc_18001E7E3
0x18001e99f  xor     r9d, r9d; dwValue
0x18001e9a2  mov     r8d, ebx; dwIndex
0x18001e9a5  mov     rcx, r15; HIMC
0x18001e9a8  lea     edx, [r9+15h]; dwAction
0x18001e9ac  call    cs:__imp_ImmNotifyIME
0x18001e9b2  jmp     loc_18001E7E3
0x18001e9b7  mov     rcx, rdi
0x18001e9ba  call    cicMemFree
0x18001e9bf  lea     rdx, aImesetactiveco_0; "ImeSetActiveContext. ptls==NULL."
0x18001e9c6  mov     ecx, ebx; unsigned int
0x18001e9c8  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e9cd  jmp     loc_18001E6F8
0x18001e9d2  mov     rax, [r14]
0x18001e9d5  test    rax, rax
0x18001e9d8  jz      loc_18001E7E3
0x18001e9de  jmp     short loc_18001E987
0x18001e9e0  mov     ebx, 1
0x18001e9e5  jmp     short loc_18001E9BF
```
