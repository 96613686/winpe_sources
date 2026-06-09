# _NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1_::operator()

- ea: `0x1800272f0`
- end: `0x18002774d`
- name: `_NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1_::operator()`
- size: `1117`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800272e0`

## callees

- `0x18000e59c`
- `0x1800272f0`
- `0x180027754`
- `0x18002d1c4`
- `0x18002e008`
- `0x180047f60`
- `0x18005587c`
- `0x18006d908`
- `0x18006d960`
- `0x18006d9b8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800273e8`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800273e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002742a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002744e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002748a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002749e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002742a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002744e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002748a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002749e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027314`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027314`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1_::operator()(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  const char *v3; // r9
  __int64 v4; // rcx
  void (__fastcall *v5)(__int128 *); // rbx
  __int128 *v6; // rcx
  void (__fastcall *v7)(__int128 *, __int128 *); // r14
  __int128 *v8; // rbx
  __int128 *v9; // rax
  __int128 *v10; // rdx
  __int128 v11; // xmm0
  void (__fastcall *v12)(__int128 *, __int128 *); // rax
  void (__fastcall *v13)(__int128 *, __int64 *); // rbx
  void (__fastcall *v14)(_QWORD); // rbx
  unsigned int *v15; // rsi
  void (__fastcall *v16)(__int128 *, __int128 *); // rbx
  __int64 v17; // rax
  int v18; // r14d
  const void *v19; // rax
  _OWORD *v20; // rax
  _OWORD *v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rdx
  _OWORD *v24; // rcx
  _OWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // xmm6_8
  int v28; // r14d
  __int128 *v29; // rax
  __int128 v30; // [rsp+20h] [rbp-EE8h] BYREF
  __int128 v31; // [rsp+30h] [rbp-ED8h] BYREF
  int v32; // [rsp+40h] [rbp-EC8h]
  __int64 v33; // [rsp+50h] [rbp-EB8h] BYREF
  int v34; // [rsp+58h] [rbp-EB0h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+70h] [rbp-E98h]
  _BYTE v36[544]; // [rsp+80h] [rbp-E88h] BYREF
  _BYTE v37[1568]; // [rsp+2A0h] [rbp-C68h] BYREF
  _OWORD v38[99]; // [rsp+8C0h] [rbp-648h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F08h] [rbp+0h]

  v2 = *(struct _RTL_CRITICAL_SECTION **)a1;
  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  try
  {
    v35 = v2;
    v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 1);
    if ( *(_DWORD *)(a1 + 72) == 1 )
    {
      v13 = *(void (__fastcall **)(__int128 *, __int64 *))(*(_QWORD *)a1 + 40LL);
      if ( !v13 )
      {
        if ( v2 )
          LeaveCriticalSection(v2);
        return;
      }
      v26 = std::any_cast<_NcsiCapabilityChangeMetadata>(&v30, a1 + 8);
      v27 = *(_QWORD *)v26;
      v28 = *(_DWORD *)(v26 + 8);
      v29 = (__int128 *)std::optional<_GUID>::value(a1 + 80);
      v33 = v27;
      v34 = v28;
      v31 = *v29;
      v13(&v31, &v33);
LABEL_12:
      if ( v2 )
        LeaveCriticalSection(v2);
      return;
    }
    v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 2);
    if ( *(_DWORD *)(a1 + 72) == 2 )
    {
      v7 = *(void (__fastcall **)(__int128 *, __int128 *))(*(_QWORD *)a1 + 48LL);
      if ( !v7 )
      {
        if ( v2 )
          LeaveCriticalSection(v2);
        return;
      }
      v20 = std::any_cast<_NcsiActiveProbeCompleteMetadata>(v38, a1 + 8);
      v21 = v36;
      v22 = 4;
      v23 = 4;
      do
      {
        *v21 = *v20;
        v21[1] = v20[1];
        v21[2] = v20[2];
        v21[3] = v20[3];
        v21[4] = v20[4];
        v21[5] = v20[5];
        v21[6] = v20[6];
        v21[7] = v20[7];
        v21 += 8;
        v20 += 8;
        --v23;
      }
      while ( v23 );
      *v21 = *v20;
      v21[1] = v20[1];
      v9 = (__int128 *)std::optional<_GUID>::value(a1 + 80);
      v24 = v37;
      v25 = v36;
      do
      {
        *v24 = *v25;
        v24[1] = v25[1];
        v24[2] = v25[2];
        v24[3] = v25[3];
        v24[4] = v25[4];
        v24[5] = v25[5];
        v24[6] = v25[6];
        v24[7] = v25[7];
        v24 += 8;
        v25 += 8;
        --v22;
      }
      while ( v22 );
      *v24 = *v25;
      v24[1] = v25[1];
      v10 = (__int128 *)v37;
    }
    else
    {
      v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 3);
      if ( *(_DWORD *)(a1 + 72) != 3 )
      {
        v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 4);
        if ( *(_DWORD *)(a1 + 72) == 4 )
        {
          v14 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)a1 + 80LL);
          if ( !v14 )
          {
            if ( v2 )
              LeaveCriticalSection(v2);
            return;
          }
          v15 = (unsigned int *)(a1 + 8);
          if ( !v15
            || (*((_QWORD *)v15 + 7) & 0xFFFFFFFFFFFFFFFCuLL) == 0
            || !(unsigned __int8)type_info::operator==(
                                   *((_QWORD *)v15 + 7) & 0xFFFFFFFFFFFFFFFCuLL,
                                   &_NcsiActiveProbeConfigChangeMetadata `RTTI Type Descriptor') )
          {
            std::_Throw_bad_any_cast();
          }
LABEL_62:
          v14(*v15);
          goto LABEL_12;
        }
        v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 5);
        if ( *(_DWORD *)(a1 + 72) != 5 )
        {
          v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 6);
          if ( *(_DWORD *)(a1 + 72) != 6 )
          {
            v4 = (unsigned int)(*(_DWORD *)(a1 + 72) - 7);
            if ( *(_DWORD *)(a1 + 72) == 7 )
            {
              v5 = *(void (__fastcall **)(__int128 *))(*(_QWORD *)a1 + 88LL);
              if ( v5 )
              {
                v30 = *(_OWORD *)std::optional<_GUID>::value(a1 + 80);
                v6 = &v30;
LABEL_11:
                v5(v6);
                goto LABEL_12;
              }
              if ( v2 )
                LeaveCriticalSection(v2);
              return;
            }
            if ( *(_DWORD *)(a1 + 72) != 8 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v4);
              goto LABEL_12;
            }
            v14 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)a1 + 96LL);
            if ( !v14 )
            {
              if ( v2 )
                LeaveCriticalSection(v2);
              return;
            }
            v15 = (unsigned int *)(a1 + 8);
            if ( !v15
              || (*((_QWORD *)v15 + 7) & 0xFFFFFFFFFFFFFFFCuLL) == 0
              || !(unsigned __int8)type_info::operator==(
                                     *((_QWORD *)v15 + 7) & 0xFFFFFFFFFFFFFFFCuLL,
                                     &_NcsiPassivePollingConfigChangeMetadata `RTTI Type Descriptor') )
            {
              std::_Throw_bad_any_cast();
            }
            goto LABEL_62;
          }
          v16 = *(void (__fastcall **)(__int128 *, __int128 *))(*(_QWORD *)a1 + 56LL);
          if ( !v16 )
          {
            if ( v2 )
              LeaveCriticalSection(v2);
            return;
          }
          v17 = std::any_cast<_NcsiNoneCheckCompleteMetadata>((__int64)&v33, a1 + 8);
          v18 = *(_DWORD *)(v17 + 16);
          v31 = *(_OWORD *)v17;
          v32 = v18;
          v11 = *(_OWORD *)std::optional<_GUID>::value(a1 + 80);
          v10 = &v31;
          v12 = v16;
LABEL_20:
          v30 = v11;
          v12(&v30, v10);
          goto LABEL_12;
        }
        v5 = *(void (__fastcall **)(__int128 *))(*(_QWORD *)a1 + 72LL);
        if ( v5 )
        {
          v19 = (const void *)std::any_cast<_NcsiUserProxyChangeMetadata>(v37);
          memcpy_0(v38, v19, 0x61Cu);
          v6 = v38;
          goto LABEL_11;
        }
        if ( v2 )
          LeaveCriticalSection(v2);
        return;
      }
      v7 = *(void (__fastcall **)(__int128 *, __int128 *))(*(_QWORD *)a1 + 64LL);
      if ( !v7 )
      {
        if ( v2 )
          LeaveCriticalSection(v2);
        return;
      }
      if ( a1 == -8
        || (*(_QWORD *)(a1 + 64) & 0xFFFFFFFFFFFFFFFCuLL) == 0
        || (unsigned int)__std_type_info_compare((*(_QWORD *)(a1 + 64) & 0xFFFFFFFFFFFFFFFCuLL) + 8, &qword_18009A5C8) )
      {
        std::_Throw_bad_any_cast();
      }
      v8 = *(__int128 **)(a1 + 8);
      v9 = (__int128 *)std::optional<_GUID>::value(a1 + 80);
      v10 = v8;
    }
    v11 = *v9;
    v12 = v7;
    goto LABEL_20;
  }
  catch ( std::bad_any_cast )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    return;
  }
  catch ( std::bad_optional_access )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    return;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\nlmmanager\\lib\\nlmmanager.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x1800272f0  mov     rax, rsp
0x1800272f3  mov     [rax+10h], rbx
0x1800272f7  mov     [rax+18h], rsi
0x1800272fb  push    rdi
0x1800272fc  push    r14
0x1800272fe  push    r15
0x180027300  sub     rsp, 0EF0h
0x180027307  movaps  xmmword ptr [rax-28h], xmm6
0x18002730b  mov     rsi, rcx
0x18002730e  mov     rdi, [rcx]
0x180027311  mov     rcx, rdi; lpCriticalSection
0x180027314  call    cs:__imp_EnterCriticalSection
0x18002731a  mov     [rsp+0F08h+var_E98], rdi
0x18002731f  mov     ecx, [rsi+48h]
0x180027322  sub     ecx, 1
0x180027325  jz      loc_180027436
0x18002732b  sub     ecx, 1
0x18002732e  jz      loc_1800275EA
0x180027334  sub     ecx, 1
0x180027337  jz      loc_1800273BE
0x18002733d  sub     ecx, 1
0x180027340  jz      loc_1800275A6
0x180027346  sub     ecx, 1
0x180027349  jz      loc_180027562
0x18002734f  sub     ecx, 1
0x180027352  jz      loc_18002751A
0x180027358  sub     ecx, 1
0x18002735b  jnz     loc_1800274D2
0x180027361  mov     rax, [rsi]
0x180027364  mov     rbx, [rax+58h]
0x180027368  test    rbx, rbx
0x18002736b  jz      loc_18002746E
0x180027371  lea     rcx, [rsi+50h]
0x180027375  call    ?value@?$optional@U_GUID@@@std@@QEGBAAEBU_GUID@@XZ; std::optional<_GUID>::value(void)
0x18002737a  movups  xmm0, xmmword ptr [rax]
0x18002737d  movdqu  [rsp+0F08h+var_EE8], xmm0
0x180027383  lea     rcx, [rsp+0F08h+var_EE8]
0x180027388  mov     rax, rbx
0x18002738b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027390  nop
0x180027391  test    rdi, rdi
0x180027394  jz      short loc_1800273A0
0x180027396  mov     rcx, rdi; lpCriticalSection
0x180027399  call    cs:__imp_LeaveCriticalSection
0x18002739f  nop
0x1800273a0  lea     r11, [rsp+0F08h+var_18]
0x1800273a8  mov     rbx, [r11+28h]
0x1800273ac  mov     rsi, [r11+30h]
0x1800273b0  movaps  xmm6, xmmword ptr [r11-10h]
0x1800273b5  mov     rsp, r11
0x1800273b8  pop     r15
0x1800273ba  pop     r14
0x1800273bc  pop     rdi
0x1800273bd  retn
0x1800273be  mov     rax, [rsi]
0x1800273c1  mov     r14, [rax+40h]
0x1800273c5  test    r14, r14
0x1800273c8  jz      short loc_180027422
0x1800273ca  lea     rbx, [rsi+8]
0x1800273ce  test    rbx, rbx
0x1800273d1  jz      short loc_18002741C
0x1800273d3  mov     rcx, [rbx+38h]
0x1800273d7  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800273db  jz      short loc_18002741C
0x1800273dd  add     rcx, 8
0x1800273e1  lea     rdx, qword_18009A5C8
0x1800273e8  call    cs:__imp___std_type_info_compare
0x1800273ee  test    eax, eax
0x1800273f0  jnz     short loc_18002741C
0x1800273f2  mov     rbx, [rbx]
0x1800273f5  lea     rcx, [rsi+50h]
0x1800273f9  call    ?value@?$optional@U_GUID@@@std@@QEGBAAEBU_GUID@@XZ; std::optional<_GUID>::value(void)
0x1800273fe  mov     rdx, rbx
0x180027401  movups  xmm0, xmmword ptr [rax]
0x180027404  mov     rax, r14
0x180027407  movdqu  [rsp+0F08h+var_EE8], xmm0
0x18002740d  lea     rcx, [rsp+0F08h+var_EE8]
0x180027412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027417  jmp     loc_180027391
0x18002741c  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x180027422  test    rdi, rdi
0x180027425  jz      short loc_180027431
0x180027427  mov     rcx, rdi; lpCriticalSection
0x18002742a  call    cs:__imp_LeaveCriticalSection
0x180027430  nop
0x180027431  jmp     loc_1800273A0
0x180027436  mov     rax, [rsi]
0x180027439  mov     rbx, [rax+28h]
0x18002743d  test    rbx, rbx
0x180027440  jnz     loc_1800276F4
0x180027446  test    rdi, rdi
0x180027449  jz      short loc_180027455
0x18002744b  mov     rcx, rdi; lpCriticalSection
0x18002744e  call    cs:__imp_LeaveCriticalSection
0x180027454  nop
0x180027455  jmp     loc_1800273A0
0x18002745a  test    rdi, rdi
0x18002745d  jz      short loc_180027469
0x18002745f  mov     rcx, rdi; lpCriticalSection
0x180027462  call    cs:__imp_LeaveCriticalSection
0x180027468  nop
0x180027469  jmp     loc_1800273A0
0x18002746e  test    rdi, rdi
0x180027471  jz      short loc_18002747D
0x180027473  mov     rcx, rdi; lpCriticalSection
0x180027476  call    cs:__imp_LeaveCriticalSection
0x18002747c  nop
0x18002747d  jmp     loc_1800273A0
0x180027482  test    rdi, rdi
0x180027485  jz      short loc_180027491
0x180027487  mov     rcx, rdi; lpCriticalSection
0x18002748a  call    cs:__imp_LeaveCriticalSection
0x180027490  nop
0x180027491  jmp     loc_1800273A0
0x180027496  test    rdi, rdi
0x180027499  jz      short loc_1800274A5
0x18002749b  mov     rcx, rdi; lpCriticalSection
0x18002749e  call    cs:__imp_LeaveCriticalSection
0x1800274a4  nop
0x1800274a5  jmp     loc_1800273A0
0x1800274aa  test    rdi, rdi
0x1800274ad  jz      short loc_1800274B9
0x1800274af  mov     rcx, rdi; lpCriticalSection
0x1800274b2  call    cs:__imp_LeaveCriticalSection
0x1800274b8  nop
0x1800274b9  jmp     loc_1800273A0
0x1800274be  test    rdi, rdi
0x1800274c1  jz      short loc_1800274CD
0x1800274c3  mov     rcx, rdi; lpCriticalSection
0x1800274c6  call    cs:__imp_LeaveCriticalSection
0x1800274cc  nop
0x1800274cd  jmp     loc_1800273A0
0x1800274d2  cmp     ecx, 1
0x1800274d5  jz      short loc_1800274E1
0x1800274d7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800274dc  jmp     loc_180027391
0x1800274e1  mov     rax, [rsi]
0x1800274e4  mov     rbx, [rax+60h]
0x1800274e8  test    rbx, rbx
0x1800274eb  jz      loc_18002745A
0x1800274f1  add     rsi, 8
0x1800274f5  jz      short loc_180027515
0x1800274f7  mov     rcx, [rsi+38h]
0x1800274fb  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800274ff  jz      short loc_180027515
0x180027501  lea     rdx, ??_R0?AU_NcsiPassivePollingConfigChangeMetadata@@@8; _NcsiPassivePollingConfigChangeMetadata `RTTI Type Descriptor'
0x180027508  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x18002750d  test    al, al
0x18002750f  jnz     loc_1800275D6
0x180027515  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x18002751a  mov     rax, [rsi]
0x18002751d  mov     rbx, [rax+38h]
0x180027521  test    rbx, rbx
0x180027524  jz      loc_180027482
0x18002752a  lea     rdx, [rsi+8]
0x18002752e  lea     rcx, [rsp+0F08h+var_EB8]
0x180027533  call    ??$any_cast@U_NcsiNoneCheckCompleteMetadata@@@std@@YA?AU_NcsiNoneCheckCompleteMetadata@@AEBVany@0@@Z; std::any_cast<_NcsiNoneCheckCompleteMetadata>(std::any const &)
0x180027538  movups  xmm6, xmmword ptr [rax]
0x18002753b  mov     r14d, [rax+10h]
0x18002753f  lea     rcx, [rsi+50h]
0x180027543  call    ?value@?$optional@U_GUID@@@std@@QEGBAAEBU_GUID@@XZ; std::optional<_GUID>::value(void)
0x180027548  movaps  [rsp+0F08h+var_ED8], xmm6
0x18002754d  mov     [rsp+0F08h+var_EC8], r14d
0x180027552  movups  xmm0, xmmword ptr [rax]
0x180027555  lea     rdx, [rsp+0F08h+var_ED8]
0x18002755a  mov     rax, rbx
0x18002755d  jmp     loc_180027407
0x180027562  mov     rax, [rsi]
0x180027565  mov     rbx, [rax+48h]
0x180027569  test    rbx, rbx
0x18002756c  jz      loc_180027496
0x180027572  lea     rdx, [rsi+8]
0x180027576  lea     rcx, [rsp+0F08h+var_C68]; void *
0x18002757e  call    ??$any_cast@U_NcsiUserProxyChangeMetadata@@@std@@YA?AU_NcsiUserProxyChangeMetadata@@AEBVany@0@@Z; std::any_cast<_NcsiUserProxyChangeMetadata>(std::any const &)
0x180027583  lea     rcx, [rsp+0F08h+var_648]; void *
0x18002758b  mov     rdx, rax; Src
0x18002758e  mov     r8d, 61Ch; Size
0x180027594  call    memcpy_0
0x180027599  lea     rcx, [rsp+0F08h+var_648]
0x1800275a1  jmp     loc_180027388
0x1800275a6  mov     rax, [rsi]
0x1800275a9  mov     rbx, [rax+50h]
0x1800275ad  test    rbx, rbx
0x1800275b0  jz      loc_1800274AA
0x1800275b6  add     rsi, 8
0x1800275ba  jz      short loc_1800275E5
0x1800275bc  mov     rcx, [rsi+38h]
0x1800275c0  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800275c4  jz      short loc_1800275E5
0x1800275c6  lea     rdx, ??_R0?AU_NcsiActiveProbeConfigChangeMetadata@@@8; _NcsiActiveProbeConfigChangeMetadata `RTTI Type Descriptor'
0x1800275cd  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x1800275d2  test    al, al
0x1800275d4  jz      short loc_1800275E5
0x1800275d6  mov     ecx, [rsi]
0x1800275d8  mov     rax, rbx
0x1800275db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275e0  jmp     loc_180027391
0x1800275e5  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x1800275ea  mov     rax, [rsi]
0x1800275ed  mov     r14, [rax+30h]
0x1800275f1  test    r14, r14
0x1800275f4  jz      loc_1800274BE
0x1800275fa  lea     rdx, [rsi+8]
0x1800275fe  lea     rcx, [rsp+0F08h+var_648]
0x180027606  call    ??$any_cast@U_NcsiActiveProbeCompleteMetadata@@@std@@YA?AU_NcsiActiveProbeCompleteMetadata@@AEBVany@0@@Z; std::any_cast<_NcsiActiveProbeCompleteMetadata>(std::any const &)
0x18002760b  lea     rcx, [rsp+0F08h+var_E88]
0x180027613  mov     ebx, 4
0x180027618  mov     edx, ebx
0x18002761a  lea     r15d, [rbx+7Ch]
0x18002761e  movups  xmm0, xmmword ptr [rax]
0x180027621  movups  xmmword ptr [rcx], xmm0
0x180027624  movups  xmm1, xmmword ptr [rax+10h]
0x180027628  movups  xmmword ptr [rcx+10h], xmm1
0x18002762c  movups  xmm0, xmmword ptr [rax+20h]
0x180027630  movups  xmmword ptr [rcx+20h], xmm0
0x180027634  movups  xmm1, xmmword ptr [rax+30h]
0x180027638  movups  xmmword ptr [rcx+30h], xmm1
0x18002763c  movups  xmm0, xmmword ptr [rax+40h]
0x180027640  movups  xmmword ptr [rcx+40h], xmm0
0x180027644  movups  xmm1, xmmword ptr [rax+50h]
0x180027648  movups  xmmword ptr [rcx+50h], xmm1
0x18002764c  movups  xmm0, xmmword ptr [rax+60h]
0x180027650  movups  xmmword ptr [rcx+60h], xmm0
0x180027654  movups  xmm1, xmmword ptr [rax+70h]
0x180027658  movups  xmmword ptr [rcx+70h], xmm1
0x18002765c  add     rcx, r15
0x18002765f  add     rax, r15
0x180027662  sub     rdx, 1
0x180027666  jnz     short loc_18002761E
0x180027668  movups  xmm0, xmmword ptr [rax]
0x18002766b  movups  xmmword ptr [rcx], xmm0
0x18002766e  movups  xmm1, xmmword ptr [rax+10h]
0x180027672  movups  xmmword ptr [rcx+10h], xmm1
0x180027676  lea     rcx, [rsi+50h]
0x18002767a  call    ?value@?$optional@U_GUID@@@std@@QEGBAAEBU_GUID@@XZ; std::optional<_GUID>::value(void)
0x18002767f  lea     rcx, [rsp+0F08h+var_C68]
0x180027687  lea     rdx, [rsp+0F08h+var_E88]
0x18002768f  movups  xmm0, xmmword ptr [rdx]
0x180027692  movups  xmmword ptr [rcx], xmm0
0x180027695  movups  xmm1, xmmword ptr [rdx+10h]
0x180027699  movups  xmmword ptr [rcx+10h], xmm1
0x18002769d  movups  xmm0, xmmword ptr [rdx+20h]
0x1800276a1  movups  xmmword ptr [rcx+20h], xmm0
0x1800276a5  movups  xmm1, xmmword ptr [rdx+30h]
0x1800276a9  movups  xmmword ptr [rcx+30h], xmm1
0x1800276ad  movups  xmm0, xmmword ptr [rdx+40h]
0x1800276b1  movups  xmmword ptr [rcx+40h], xmm0
0x1800276b5  movups  xmm1, xmmword ptr [rdx+50h]
0x1800276b9  movups  xmmword ptr [rcx+50h], xmm1
0x1800276bd  movups  xmm0, xmmword ptr [rdx+60h]
0x1800276c1  movups  xmmword ptr [rcx+60h], xmm0
0x1800276c5  movups  xmm1, xmmword ptr [rdx+70h]
0x1800276c9  movups  xmmword ptr [rcx+70h], xmm1
0x1800276cd  add     rcx, r15
0x1800276d0  add     rdx, r15
0x1800276d3  sub     rbx, 1
0x1800276d7  jnz     short loc_18002768F
0x1800276d9  movups  xmm0, xmmword ptr [rdx]
0x1800276dc  movups  xmmword ptr [rcx], xmm0
0x1800276df  movups  xmm1, xmmword ptr [rdx+10h]
0x1800276e3  movups  xmmword ptr [rcx+10h], xmm1
0x1800276e7  lea     rdx, [rsp+0F08h+var_C68]
0x1800276ef  jmp     loc_180027401
0x1800276f4  lea     rdx, [rsi+8]
0x1800276f8  lea     rcx, [rsp+0F08h+var_EE8]
0x1800276fd  call    ??$any_cast@U_NcsiCapabilityChangeMetadata@@@std@@YA?AU_NcsiCapabilityChangeMetadata@@AEBVany@0@@Z; std::any_cast<_NcsiCapabilityChangeMetadata>(std::any const &)
0x180027702  movsd   xmm6, qword ptr [rax]
0x180027706  mov     r14d, [rax+8]
0x18002770a  lea     rcx, [rsi+50h]
0x18002770e  call    ?value@?$optional@U_GUID@@@std@@QEGBAAEBU_GUID@@XZ; std::optional<_GUID>::value(void)
0x180027713  movsd   [rsp+0F08h+var_EB8], xmm6
0x180027719  mov     [rsp+0F08h+var_EB0], r14d
0x18002771e  movups  xmm0, xmmword ptr [rax]
0x180027721  movdqu  [rsp+0F08h+var_ED8], xmm0
0x180027727  lea     rdx, [rsp+0F08h+var_EB8]
0x18002772c  lea     rcx, [rsp+0F08h+var_ED8]
0x180027731  mov     rax, rbx
0x180027734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027739  jmp     loc_180027391
0x18002773e  jmp     loc_1800273A0
0x180027743  jmp     loc_1800273A0
0x180027748  jmp     loc_1800273A0
```
