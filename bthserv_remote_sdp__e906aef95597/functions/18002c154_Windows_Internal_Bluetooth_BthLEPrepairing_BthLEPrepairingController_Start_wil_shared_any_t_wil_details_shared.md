# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Start(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)

- ea: `0x18002c154`
- end: `0x18002c366`
- name: `?Start@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000ebac`

## callees

- `0x180012004`
- `0x180012384`
- `0x18002c154`
- `0x18002c36c`
- `0x18002c9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c1e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c1e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c2d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c2d8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Start(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)
{
  char v2; // di
  bool v3; // dl
  int started; // ebx
  int v5; // edx
  int v6; // r8d
  int v7; // ecx
  int v8; // ecx
  _QWORD *v9; // rcx
  bool v10; // dl
  bool v11; // r8
  int v12; // eax
  bool v13; // cf

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  started = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v7 = *((_DWORD *)this + 2);
  if ( !v7 )
  {
    started = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StartInternal(this);
    if ( started >= 0 )
      *((_DWORD *)this + 2) = 1;
    goto LABEL_27;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    started = -2147483634;
    v9 = WPP_GLOBAL_Control;
    v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_24;
    goto LABEL_28;
  }
  if ( v8 != 1 )
  {
LABEL_27:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  started = -2147483634;
  v9 = WPP_GLOBAL_Control;
  v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
LABEL_24:
    WPP_RECORDER_AND_TRACE_SF_s(v9[2], v10, v11, v9[5]);
    v9 = WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v9 = WPP_GLOBAL_Control;
  }
  v12 = 0;
  if ( started )
    v13 = *((_BYTE *)v9 + 25) < 2u;
  else
    v13 = *((_BYTE *)v9 + 25) < 5u;
  if ( v9 == &WPP_GLOBAL_Control || (LOBYTE(v12) = !v13, !v12) )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = v2;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(v9[2], v5, v6, v9[5]);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18002c154  mov     rax, rsp
0x18002c157  mov     [rax+8], rbx
0x18002c15b  mov     [rax+10h], rbp
0x18002c15f  mov     [rax+18h], rsi
0x18002c163  mov     [rax+20h], rdi
0x18002c167  push    r13
0x18002c169  push    r14
0x18002c16b  push    r15
0x18002c16d  sub     rsp, 60h
0x18002c171  mov     rbp, rdx
0x18002c174  mov     rsi, rcx
0x18002c177  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c17e  lea     r15, WPP_GLOBAL_Control
0x18002c185  mov     edi, 1
0x18002c18a  cmp     rcx, r15
0x18002c18d  jz      short loc_18002C19A
0x18002c18f  cmp     byte ptr [rcx+19h], 5
0x18002c193  jb      short loc_18002C19A
0x18002c195  mov     dl, dil
0x18002c198  jmp     short loc_18002C19C
0x18002c19a  xor     dl, dl
0x18002c19c  lea     r13, WPP_RECORDER_INITIALIZED
0x18002c1a3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002c1aa  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002c1b1  setnz   r8b
0x18002c1b5  test    dl, dl
0x18002c1b7  jnz     short loc_18002C1BE
0x18002c1b9  test    r8b, r8b
0x18002c1bc  jz      short loc_18002C1DC
0x18002c1be  mov     [rsp+78h+var_30], rsi
0x18002c1c3  mov     [rsp+78h+var_40], r9
0x18002c1c8  mov     r9, [rcx+28h]
0x18002c1cc  mov     rcx, [rcx+10h]
0x18002c1d0  mov     [rsp+78h+var_48], 0Ah
0x18002c1d7  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c1dc  lea     r14, [rsi+30h]
0x18002c1e0  xor     ebx, ebx
0x18002c1e2  mov     rcx, r14; lpCriticalSection
0x18002c1e5  call    cs:__imp_EnterCriticalSection
0x18002c1ec  nop     dword ptr [rax+rax+00h]
0x18002c1f1  mov     ecx, [rsi+8]
0x18002c1f4  test    ecx, ecx
0x18002c1f6  jz      loc_18002C2AE
0x18002c1fc  sub     ecx, edi
0x18002c1fe  jz      short loc_18002C253
0x18002c200  cmp     ecx, edi
0x18002c202  jnz     loc_18002C2C2
0x18002c208  mov     ebx, 8000000Eh
0x18002c20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c214  cmp     rcx, r15
0x18002c217  jz      short loc_18002C224
0x18002c219  cmp     byte ptr [rcx+19h], 2
0x18002c21d  jb      short loc_18002C224
0x18002c21f  mov     dl, dil
0x18002c222  jmp     short loc_18002C226
0x18002c224  xor     dl, dl
0x18002c226  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002c22d  setnz   r8b
0x18002c231  test    dl, dl
0x18002c233  jnz     short loc_18002C23E
0x18002c235  test    r8b, r8b
0x18002c238  jz      loc_18002C2C9
0x18002c23e  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002c245  mov     [rsp+78h+var_40], rbp
0x18002c24a  mov     [rsp+78h+var_48], 0Ch
0x18002c251  jmp     short loc_18002C298
0x18002c253  mov     ebx, 8000000Eh
0x18002c258  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c25f  cmp     rcx, r15
0x18002c262  jz      short loc_18002C26F
0x18002c264  cmp     byte ptr [rcx+19h], 2
0x18002c268  jb      short loc_18002C26F
0x18002c26a  mov     dl, dil
0x18002c26d  jmp     short loc_18002C271
0x18002c26f  xor     dl, dl
0x18002c271  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002c278  setnz   r8b
0x18002c27c  test    dl, dl
0x18002c27e  jnz     short loc_18002C285
0x18002c280  test    r8b, r8b
0x18002c283  jz      short loc_18002C2C9
0x18002c285  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002c28c  mov     [rsp+78h+var_40], rbp
0x18002c291  mov     [rsp+78h+var_48], 0Bh
0x18002c298  mov     r9, [rcx+28h]
0x18002c29c  mov     rcx, [rcx+10h]
0x18002c2a0  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002c2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2ac  jmp     short loc_18002C2D0
0x18002c2ae  mov     rdx, rbp
0x18002c2b1  mov     rcx, rsi; this
0x18002c2b4  call    ?StartInternal@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StartInternal(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18002c2b9  mov     ebx, eax
0x18002c2bb  test    eax, eax
0x18002c2bd  js      short loc_18002C2C2
0x18002c2bf  mov     [rsi+8], edi
0x18002c2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2c9  lea     rbp, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002c2d0  test    r14, r14
0x18002c2d3  jz      short loc_18002C2EB
0x18002c2d5  mov     rcx, r14; lpCriticalSection
0x18002c2d8  call    cs:__imp_LeaveCriticalSection
0x18002c2df  nop     dword ptr [rax+rax+00h]
0x18002c2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2eb  xor     eax, eax
0x18002c2ed  test    ebx, ebx
0x18002c2ef  jnz     short loc_18002C2F7
0x18002c2f1  cmp     byte ptr [rcx+19h], 5
0x18002c2f5  jmp     short loc_18002C2FB
0x18002c2f7  cmp     byte ptr [rcx+19h], 2
0x18002c2fb  setnb   al
0x18002c2fe  cmp     rcx, r15
0x18002c301  jz      short loc_18002C307
0x18002c303  test    eax, eax
0x18002c305  jnz     short loc_18002C30A
0x18002c307  xor     dil, dil
0x18002c30a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002c311  setnz   r8b
0x18002c315  test    dil, dil
0x18002c318  jnz     short loc_18002C31F
0x18002c31a  test    r8b, r8b
0x18002c31d  jz      short loc_18002C344
0x18002c31f  mov     r9, [rcx+28h]
0x18002c323  mov     dl, dil
0x18002c326  mov     rcx, [rcx+10h]
0x18002c32a  mov     [rsp+78h+var_28], ebx
0x18002c32e  mov     [rsp+78h+var_30], rsi
0x18002c333  mov     [rsp+78h+var_40], rbp
0x18002c338  mov     [rsp+78h+var_48], 0Dh
0x18002c33f  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002c344  lea     r11, [rsp+78h+var_18]
0x18002c349  mov     eax, ebx
0x18002c34b  mov     rbx, [r11+20h]
0x18002c34f  mov     rbp, [r11+28h]
0x18002c353  mov     rsi, [r11+30h]
0x18002c357  mov     rdi, [r11+38h]
0x18002c35b  mov     rsp, r11
0x18002c35e  pop     r15
0x18002c360  pop     r14
0x18002c362  pop     r13
0x18002c364  retn
```
