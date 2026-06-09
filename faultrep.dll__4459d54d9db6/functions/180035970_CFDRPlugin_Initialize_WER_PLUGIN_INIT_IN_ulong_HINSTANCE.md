# CFDRPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x180035970`
- end: `0x180035c42`
- name: `?Initialize@CFDRPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CFDRPlugin *this, struct WER_PLUGIN_INIT_IN *, __int64, HINSTANCE)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180035970`
- `0x1800363ac`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a27`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a3f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a7b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035bc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a27`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a3f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a7b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035bc0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180035b1e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180035b1e`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::Initialize(CFDRPlugin *this, struct WER_PLUGIN_INIT_IN *a2, __int64 a3, HINSTANCE a4)
{
  _WORD *v7; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  _WORD *v17; // r15
  _QWORD *v18; // r14
  DWORD ProcessId; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int64 v24; // r8
  __int64 v25; // rcx
  void *v26[2]; // [rsp+20h] [rbp-20h] BYREF
  _WORD v27[8]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v28; // [rsp+78h] [rbp+38h] BYREF

  v7 = v27;
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  v28 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      v7 = v26[0];
    }
    if ( v7 != v27 )
      operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"APPCRASH")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppCrash")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"AppHangB1")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"AppHangXProcB1")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppHang")
    || !(unsigned int)_o__wcsicmp(*(_QWORD *)a2, L"MoAppHangXProc") )
  {
    *((_QWORD *)this + 8) = a4;
    if ( (unsigned int)(*((_DWORD *)a2 + 63) - 1) > 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
    v16 = *((_DWORD *)a2 + 63);
    if ( v16 == 1 )
    {
      v17 = (_WORD *)*((_QWORD *)a2 + 33);
      v18 = (_QWORD *)((char *)this + 40);
      *((_QWORD *)this + 5) = *((_QWORD *)a2 + 38);
      *((_DWORD *)this + 12) = *((_DWORD *)a2 + 70);
    }
    else
    {
      if ( v16 != 2 )
      {
LABEL_37:
        v13 = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_41;
        v15 = 12;
        goto LABEL_40;
      }
      v17 = (_WORD *)*((_QWORD *)a2 + 32);
      v18 = (_QWORD *)((char *)this + 40);
      *((_QWORD *)this + 5) = *((_QWORD *)a2 + 33);
      ProcessId = GetProcessId(*((HANDLE *)a2 + 33));
      *((_DWORD *)this + 12) = ProcessId;
      if ( !ProcessId )
        MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22, v23);
    }
    if ( v17 && *v18 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v17[v24] );
      if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
             (__int64)this + 8,
             v17,
             v24) )
      {
        if ( (int)CFDRPlugin::ReadFDRSessionSettings(v25, (__int64)this + 80, (__int64)v26, &v28) >= 0 )
        {
          *((_DWORD *)this + 18) = 1;
          if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 1), v26[0]) && *((_DWORD *)this + 12) == v28 )
            *((_DWORD *)this + 19) = 1;
        }
        v13 = 0;
      }
      else
      {
        v13 = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_928a4490cd403d1d5470036a68085293_Traceguids,
            2147942414LL);
      }
      goto LABEL_41;
    }
    goto LABEL_37;
  }
  v13 = -2147467263;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    goto LABEL_41;
  v15 = 11;
LABEL_40:
  WPP_SF_(v14[2], v15, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_41:
  if ( v26[0] != v27 )
    operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
  return v13;
}

```

## disassembly

```asm
0x180035970  mov     [rsp-28h+arg_0], rbx
0x180035975  mov     [rsp-28h+arg_10], rsi
0x18003597a  push    rbp
0x18003597b  push    rdi
0x18003597c  push    r12
0x18003597e  push    r14
0x180035980  push    r15
0x180035982  mov     rbp, rsp
0x180035985  sub     rsp, 40h
0x180035989  mov     rdi, r9
0x18003598c  mov     rbx, rdx
0x18003598f  mov     rsi, rcx
0x180035992  lea     rcx, [rbp+var_10]
0x180035996  mov     [rbp+var_20], rcx
0x18003599a  lea     rax, [rbp+var_10]
0x18003599e  mov     [rbp+var_18], rax
0x1800359a2  xor     r12d, r12d
0x1800359a5  mov     [rbp+var_10], r12w
0x1800359aa  mov     [rbp+arg_8], r12d
0x1800359ae  test    rdx, rdx
0x1800359b1  jnz     short loc_180035A05
0x1800359b3  lea     rax, WPP_GLOBAL_Control
0x1800359ba  mov     r9, cs:WPP_GLOBAL_Control
0x1800359c1  cmp     r9, rax
0x1800359c4  jz      short loc_1800359E6
0x1800359c6  lea     edi, [rdx+1]
0x1800359c9  test    [r9+1Ch], dil
0x1800359cd  jz      short loc_1800359E6
0x1800359cf  lea     edx, [rbx+0Ah]
0x1800359d2  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1800359d9  mov     rcx, [r9+10h]
0x1800359dd  call    WPP_SF_
0x1800359e2  mov     rcx, [rbp+var_20]; void *
0x1800359e6  lea     rax, [rbp+var_10]
0x1800359ea  cmp     rcx, rax
0x1800359ed  jz      short loc_1800359FB
0x1800359ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800359f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800359fb  mov     eax, 80070057h
0x180035a00  jmp     loc_180035C29
0x180035a05  lea     rdx, aAppcrash; "APPCRASH"
0x180035a0c  mov     rcx, [rbx]
0x180035a0f  call    cs:__imp__o__wcsicmp
0x180035a15  test    eax, eax
0x180035a17  jz      loc_180035AB5
0x180035a1d  lea     rdx, aMoappcrash; "MoAppCrash"
0x180035a24  mov     rcx, [rbx]
0x180035a27  call    cs:__imp__o__wcsicmp
0x180035a2d  test    eax, eax
0x180035a2f  jz      loc_180035AB5
0x180035a35  lea     rdx, aApphangb1; "AppHangB1"
0x180035a3c  mov     rcx, [rbx]
0x180035a3f  call    cs:__imp__o__wcsicmp
0x180035a45  test    eax, eax
0x180035a47  jz      short loc_180035AB5
0x180035a49  lea     rdx, aApphangxprocb1; "AppHangXProcB1"
0x180035a50  mov     rcx, [rbx]
0x180035a53  call    cs:__imp__o__wcsicmp
0x180035a59  test    eax, eax
0x180035a5b  jz      short loc_180035AB5
0x180035a5d  lea     rdx, aMoapphang; "MoAppHang"
0x180035a64  mov     rcx, [rbx]
0x180035a67  call    cs:__imp__o__wcsicmp
0x180035a6d  test    eax, eax
0x180035a6f  jz      short loc_180035AB5
0x180035a71  lea     rdx, aMoapphangxproc; "MoAppHangXProc"
0x180035a78  mov     rcx, [rbx]
0x180035a7b  call    cs:__imp__o__wcsicmp
0x180035a81  test    eax, eax
0x180035a83  jz      short loc_180035AB5
0x180035a85  mov     ebx, 80004001h
0x180035a8a  lea     rax, WPP_GLOBAL_Control
0x180035a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a98  cmp     rcx, rax
0x180035a9b  jz      loc_180035C0E
0x180035aa1  test    byte ptr [rcx+1Ch], 4
0x180035aa5  jz      loc_180035C0E
0x180035aab  mov     edx, 0Bh
0x180035ab0  jmp     loc_180035BFD
0x180035ab5  mov     [rsi+40h], rdi
0x180035ab9  mov     eax, [rbx+0FCh]
0x180035abf  mov     edi, 1
0x180035ac4  sub     eax, edi
0x180035ac6  cmp     eax, edi
0x180035ac8  jbe     short loc_180035ACF
0x180035aca  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180035acf  mov     eax, [rbx+0FCh]
0x180035ad5  cmp     eax, edi
0x180035ad7  jnz     short loc_180035AF9
0x180035ad9  mov     r15, [rbx+108h]
0x180035ae0  lea     r14, [rsi+28h]
0x180035ae4  mov     rax, [rbx+130h]
0x180035aeb  mov     [r14], rax
0x180035aee  mov     eax, [rbx+118h]
0x180035af4  mov     [rsi+30h], eax
0x180035af7  jmp     short loc_180035B30
0x180035af9  cmp     eax, 2
0x180035afc  jnz     loc_180035BDA
0x180035b02  mov     r15, [rbx+100h]
0x180035b09  lea     r14, [rsi+28h]
0x180035b0d  mov     rax, [rbx+108h]
0x180035b14  mov     [r14], rax
0x180035b17  mov     rcx, [rbx+108h]; Process
0x180035b1e  call    cs:__imp_GetProcessId
0x180035b24  mov     [rsi+30h], eax
0x180035b27  test    eax, eax
0x180035b29  jnz     short loc_180035B30
0x180035b2b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180035b30  test    r15, r15
0x180035b33  jz      loc_180035BDA
0x180035b39  cmp     [r14], r12
0x180035b3c  jz      loc_180035BDA
0x180035b42  or      r8, 0FFFFFFFFFFFFFFFFh
0x180035b46  inc     r8
0x180035b49  cmp     [r15+r8*2], r12w
0x180035b4e  jnz     short loc_180035B46
0x180035b50  mov     rdx, r15
0x180035b53  lea     rcx, [rsi+8]
0x180035b57  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180035b5c  test    al, al
0x180035b5e  jnz     short loc_180035BA0
0x180035b60  mov     ebx, 8007000Eh
0x180035b65  lea     rax, WPP_GLOBAL_Control
0x180035b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b73  cmp     rcx, rax
0x180035b76  jz      loc_180035C0E
0x180035b7c  test    [rcx+1Ch], dil
0x180035b80  jz      loc_180035C0E
0x180035b86  mov     edx, 0Dh
0x180035b8b  mov     r9d, ebx
0x180035b8e  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180035b95  mov     rcx, [rcx+10h]
0x180035b99  call    WPP_SF_d
0x180035b9e  jmp     short loc_180035C0E
0x180035ba0  lea     rdx, [rsi+50h]
0x180035ba4  lea     r9, [rbp+arg_8]
0x180035ba8  lea     r8, [rbp+var_20]
0x180035bac  call    ?ReadFDRSessionSettings@CFDRPlugin@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0PEAK@Z; CFDRPlugin::ReadFDRSessionSettings(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ulong *)
0x180035bb1  test    eax, eax
0x180035bb3  js      short loc_180035BD5
0x180035bb5  mov     [rsi+48h], edi
0x180035bb8  mov     rdx, [rbp+var_20]
0x180035bbc  mov     rcx, [rsi+8]
0x180035bc0  call    cs:__imp__o__wcsicmp
0x180035bc6  test    eax, eax
0x180035bc8  jnz     short loc_180035BD5
0x180035bca  mov     eax, [rbp+arg_8]
0x180035bcd  cmp     [rsi+30h], eax
0x180035bd0  jnz     short loc_180035BD5
0x180035bd2  mov     [rsi+4Ch], edi
0x180035bd5  mov     ebx, r12d
0x180035bd8  jmp     short loc_180035C0E
0x180035bda  mov     ebx, 80070057h
0x180035bdf  lea     rax, WPP_GLOBAL_Control
0x180035be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bed  cmp     rcx, rax
0x180035bf0  jz      short loc_180035C0E
0x180035bf2  test    [rcx+1Ch], dil
0x180035bf6  jz      short loc_180035C0E
0x180035bf8  mov     edx, 0Ch
0x180035bfd  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180035c04  mov     rcx, [rcx+10h]
0x180035c08  call    WPP_SF_
0x180035c0d  nop
0x180035c0e  lea     rax, [rbp+var_10]
0x180035c12  mov     rcx, [rbp+var_20]; void *
0x180035c16  cmp     rcx, rax
0x180035c19  jz      short loc_180035C27
0x180035c1b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035c22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035c27  mov     eax, ebx
0x180035c29  lea     r11, [rsp+40h+var_s0]
0x180035c2e  mov     rbx, [r11+30h]
0x180035c32  mov     rsi, [r11+40h]
0x180035c36  mov     rsp, r11
0x180035c39  pop     r15
0x180035c3b  pop     r14
0x180035c3d  pop     r12
0x180035c3f  pop     rdi
0x180035c40  pop     rbp
0x180035c41  retn
```
