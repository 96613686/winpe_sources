# CTscComHelper::StartRemoteApplication(ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x1400b2aac`
- end: `0x1400b30f0`
- name: `?StartRemoteApplication@CTscComHelper@@SAJPEAG0000@Z`
- size: `1604`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140042088`

## callees

- `0x1400095f0`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14000d87c`
- `0x14005a14c`
- `0x14005a6f4`
- `0x1400b2aac`
- `0x140112010`

## import_xrefs

- `USER32!AllowSetForegroundWindow` at `0x1400b2dfc`
- `USER32!AllowSetForegroundWindow` at `0x1400b2fdc`
- `USER32!AllowSetForegroundWindow` at `0x1400b2dfc`
- `USER32!AllowSetForegroundWindow` at `0x1400b2fdc`
- `KERNEL32!GetLastError` at `0x1400b2e06`
- `KERNEL32!GetLastError` at `0x1400b2fe6`
- `KERNEL32!GetLastError` at `0x1400b2e06`
- `KERNEL32!GetLastError` at `0x1400b2fe6`
- `ole32!CoCreateInstance` at `0x1400b2d08`
- `ole32!CoCreateInstance` at `0x1400b2f46`
- `ole32!CoCreateInstance` at `0x1400b2d08`
- `ole32!CoCreateInstance` at `0x1400b2f46`

## string_xrefs

- `0x1400b2d49`: `CoCreateInstance failed!`
- `0x1400b2b27`: `bstrCommandLine`
- `0x1400b2bda`: `saParams.Create failed!`
- `0x1400b2ded`: `spWorkspace->GetProcessId failed!`
- `0x1400b2fcd`: `spRemoteDesktopClient->GetProcessId failed!`

## pseudocode

```c
__int64 __fastcall CTscComHelper::StartRemoteApplication(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v6; // r8
  __int64 v8; // rdx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  HRESULT v12; // ebx
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  LPVOID v16; // rcx
  unsigned int v17; // eax
  signed int LastError; // eax
  signed int v19; // ebx
  unsigned int v20; // eax
  HRESULT v21; // eax
  unsigned int v22; // eax
  signed int v23; // eax
  signed int v24; // ebx
  unsigned int v25; // eax
  HRESULT v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  int ppv; // [rsp+20h] [rbp-40h]
  DWORD dwProcessId; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v33; // [rsp+50h] [rbp-10h] BYREF
  LPVOID v34; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int16 *v35; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 *v36; // [rsp+98h] [rbp+38h] BYREF
  unsigned __int16 *v37; // [rsp+A0h] [rbp+40h] BYREF

  v37 = a3;
  v36 = a2;
  v35 = a1;
  v6 = a2;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  dwProcessId = 0;
  v8 = (unsigned int)(a3 != 0) + 2;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 10;
    v11 = "bstrCommandLine";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v11,
      87);
LABEL_7:
    v12 = -2147024809;
    goto LABEL_98;
  }
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 11;
    v11 = "bstrRDPFileName";
    goto LABEL_6;
  }
  v12 = ATL::CComSafeArray<unsigned short *,8>::Create(&v32, v8);
  if ( v12 >= 0 )
  {
    v12 = ATL::CComSafeArray<unsigned short *,8>::SetAt(&v32, 0, &v35);
    if ( v12 >= 0 )
    {
      v12 = ATL::CComSafeArray<unsigned short *,8>::SetAt(&v32, 1, &v36);
      if ( v12 >= 0 )
      {
        if ( !a3 || (v12 = ATL::CComSafeArray<unsigned short *,8>::SetAt(&v32, 2, &v37), v12 >= 0) )
        {
          if ( a4
            && *a4
            && (v12 = CoCreateInstance(
                        &GUID_4f1dfca6_3aad_48e1_8406_4bc21a501d7c,
                        0,
                        4u,
                        &GUID_96d8d7cf_783e_4286_834c_ebc0e95f783c,
                        &v33),
                v12 < 0) )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_98;
            }
            v13 = RdpWppGetCurrentThreadActivityIdPrefix();
            v14 = 16;
          }
          else
          {
            v16 = v33;
            if ( v33 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v17 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids, v17);
                v16 = v33;
              }
              v12 = (*(__int64 (__fastcall **)(LPVOID, DWORD *))(*(_QWORD *)v16 + 40LL))(v16, &dwProcessId);
              if ( v12 >= 0 )
              {
                if ( !AllowSetForegroundWindow(dwProcessId) )
                {
                  LastError = GetLastError();
                  v19 = LastError;
                  if ( LastError > 0 )
                    v19 = (unsigned __int16)LastError | 0x80070000;
                  if ( v19 < 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      19,
                      (unsigned int)WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
                      v20,
                      (__int64)"AllowSetForegroundWindow failed!",
                      v19);
                  }
                }
                LOWORD(ppv) = 0;
                v21 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD, unsigned __int16 *, int, _QWORD, __int64))(*(_QWORD *)v33 + 48LL))(
                        v33,
                        a4,
                        0,
                        a5,
                        ppv,
                        0,
                        v32);
                v12 = 0;
                if ( v21 != -2147024713 )
                  v12 = v21;
                if ( v12 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v14 = 20;
                  v15 = "spWorkspace->StartRemoteApplication failed!";
                  goto LABEL_97;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                v14 = 18;
                v15 = "spWorkspace->GetProcessId failed!";
                goto LABEL_97;
              }
              goto LABEL_98;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v22 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids, v22);
            }
            v12 = CoCreateInstance(
                    &GUID_1b462d7b_72d8_4544_acc1_d84e5b9a8a14,
                    0,
                    4u,
                    &GUID_a0b2dd9a_7f53_4e65_8547_851952ec8c96,
                    &v34);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(LPVOID, DWORD *))(*(_QWORD *)v34 + 32LL))(v34, &dwProcessId);
              if ( v12 >= 0 )
              {
                if ( !AllowSetForegroundWindow(dwProcessId) )
                {
                  v23 = GetLastError();
                  v24 = v23;
                  if ( v23 > 0 )
                    v24 = (unsigned __int16)v23 | 0x80070000;
                  if ( v24 < 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      24,
                      (unsigned int)WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
                      v25,
                      (__int64)"AllowSetForegroundWindow failed!",
                      v24);
                  }
                }
                v26 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD))(*(_QWORD *)v34 + 24LL))(
                        v34,
                        0,
                        v32,
                        0);
                v12 = 0;
                if ( v26 != -2147024713 )
                  v12 = v26;
                if ( v12 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v14 = 25;
                  v15 = "spRemoteDesktopClient->StartRemoteApplication failed!";
                  goto LABEL_97;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                v14 = 23;
                v15 = "spRemoteDesktopClient->GetProcessId failed!";
                goto LABEL_97;
              }
              goto LABEL_98;
            }
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_98;
            }
            v13 = RdpWppGetCurrentThreadActivityIdPrefix();
            v14 = 22;
          }
          v15 = "CoCreateInstance failed!";
          goto LABEL_97;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 15;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 14;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 13;
    }
    v15 = "Params.SetAt failed!";
    goto LABEL_97;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 12;
    v15 = "saParams.Create failed!";
LABEL_97:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
      v13,
      (__int64)v15,
      v12);
  }
LABEL_98:
  wil::com_ptr_t<IProgressDialog,wil::err_returncode_policy>::~com_ptr_t<IProgressDialog,wil::err_returncode_policy>(
    &v33,
    v8,
    v6);
  wil::com_ptr_t<IProgressDialog,wil::err_returncode_policy>::~com_ptr_t<IProgressDialog,wil::err_returncode_policy>(
    &v34,
    v27,
    v28);
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v32);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400b2aac  mov     rax, rsp
0x1400b2aaf  mov     [rax+20h], rbx
0x1400b2ab3  mov     [rax+18h], r8
0x1400b2ab7  mov     [rax+10h], rdx
0x1400b2abb  mov     [rax+8], rcx
0x1400b2abf  push    rbp
0x1400b2ac0  push    rsi
0x1400b2ac1  push    rdi
0x1400b2ac2  push    r14
0x1400b2ac4  push    r15
0x1400b2ac6  mov     rbp, rsp
0x1400b2ac9  sub     rsp, 60h
0x1400b2acd  xor     r14d, r14d
0x1400b2ad0  mov     rdi, r8
0x1400b2ad3  mov     r8, rdx
0x1400b2ad6  mov     [rbp+var_18], r14
0x1400b2ada  mov     rax, rdi
0x1400b2add  mov     [rbp+var_8], r14
0x1400b2ae1  neg     rax
0x1400b2ae4  mov     [rbp+var_10], r14
0x1400b2ae8  lea     r15d, [r14+2]
0x1400b2aec  mov     [rbp+dwProcessId], r14d
0x1400b2af0  sbb     edx, edx
0x1400b2af2  mov     rsi, r9
0x1400b2af5  neg     edx
0x1400b2af7  add     edx, r15d
0x1400b2afa  test    rcx, rcx
0x1400b2afd  jnz     short loc_1400B2B5F
0x1400b2aff  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2b06  lea     rdi, WPP_GLOBAL_Control
0x1400b2b0d  cmp     rax, rdi
0x1400b2b10  jz      short loc_1400B2B55
0x1400b2b12  test    byte ptr [rax+1Ch], 8
0x1400b2b16  jz      short loc_1400B2B55
0x1400b2b18  cmp     [rax+19h], r15b
0x1400b2b1c  jb      short loc_1400B2B55
0x1400b2b1e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2b23  lea     edx, [r14+0Ah]
0x1400b2b27  lea     rcx, aBstrcommandlin; "bstrCommandLine"
0x1400b2b2e  mov     dword ptr [rsp+60h+var_38], 80070057h
0x1400b2b36  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b2b3d  mov     [rsp+60h+ppv], rcx
0x1400b2b42  mov     r9d, eax
0x1400b2b45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2b4c  mov     rcx, [rcx+10h]
0x1400b2b50  call    WPP_SF_DsD
0x1400b2b55  mov     ebx, 80070057h
0x1400b2b5a  jmp     loc_1400B30BF
0x1400b2b5f  test    r8, r8
0x1400b2b62  jnz     short loc_1400B2B96
0x1400b2b64  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2b6b  lea     rdi, WPP_GLOBAL_Control
0x1400b2b72  cmp     rax, rdi
0x1400b2b75  jz      short loc_1400B2B55
0x1400b2b77  test    byte ptr [rax+1Ch], 8
0x1400b2b7b  jz      short loc_1400B2B55
0x1400b2b7d  cmp     [rax+19h], r15b
0x1400b2b81  jb      short loc_1400B2B55
0x1400b2b83  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2b88  mov     edx, 0Bh
0x1400b2b8d  lea     rcx, aBstrrdpfilenam; "bstrRDPFileName"
0x1400b2b94  jmp     short loc_1400B2B2E
0x1400b2b96  lea     rcx, [rbp+var_18]
0x1400b2b9a  call    ?Create@?$CComSafeArray@PEAG$07@ATL@@QEAAJKJ@Z; ATL::CComSafeArray<ushort *,8>::Create(ulong,long)
0x1400b2b9f  mov     ebx, eax
0x1400b2ba1  test    eax, eax
0x1400b2ba3  jns     short loc_1400B2BE6
0x1400b2ba5  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2bac  lea     rdi, WPP_GLOBAL_Control
0x1400b2bb3  cmp     rax, rdi
0x1400b2bb6  jz      loc_1400B30BF
0x1400b2bbc  test    byte ptr [rax+1Ch], 8
0x1400b2bc0  jz      loc_1400B30BF
0x1400b2bc6  cmp     [rax+19h], r15b
0x1400b2bca  jb      loc_1400B30BF
0x1400b2bd0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2bd5  mov     edx, 0Ch
0x1400b2bda  lea     rcx, aSaparamsCreate; "saParams.Create failed!"
0x1400b2be1  jmp     loc_1400B309C
0x1400b2be6  lea     r8, [rbp+arg_0]
0x1400b2bea  xor     edx, edx
0x1400b2bec  lea     rcx, [rbp+var_18]
0x1400b2bf0  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x1400b2bf5  mov     ebx, eax
0x1400b2bf7  test    eax, eax
0x1400b2bf9  jns     short loc_1400B2C3C
0x1400b2bfb  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2c02  lea     rdi, WPP_GLOBAL_Control
0x1400b2c09  cmp     rax, rdi
0x1400b2c0c  jz      loc_1400B30BF
0x1400b2c12  test    byte ptr [rax+1Ch], 8
0x1400b2c16  jz      loc_1400B30BF
0x1400b2c1c  cmp     [rax+19h], r15b
0x1400b2c20  jb      loc_1400B30BF
0x1400b2c26  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2c2b  mov     edx, 0Dh
0x1400b2c30  lea     rcx, aParamsSetatFai; "Params.SetAt failed!"
0x1400b2c37  jmp     loc_1400B309C
0x1400b2c3c  lea     r8, [rbp+arg_8]
0x1400b2c40  mov     edx, 1
0x1400b2c45  lea     rcx, [rbp+var_18]
0x1400b2c49  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x1400b2c4e  mov     ebx, eax
0x1400b2c50  test    eax, eax
0x1400b2c52  jns     short loc_1400B2C8B
0x1400b2c54  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2c5b  lea     rdi, WPP_GLOBAL_Control
0x1400b2c62  cmp     rax, rdi
0x1400b2c65  jz      loc_1400B30BF
0x1400b2c6b  test    byte ptr [rax+1Ch], 8
0x1400b2c6f  jz      loc_1400B30BF
0x1400b2c75  cmp     [rax+19h], r15b
0x1400b2c79  jb      loc_1400B30BF
0x1400b2c7f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2c84  mov     edx, 0Eh
0x1400b2c89  jmp     short loc_1400B2C30
0x1400b2c8b  test    rdi, rdi
0x1400b2c8e  jz      short loc_1400B2CE0
0x1400b2c90  lea     r8, [rbp+arg_10]
0x1400b2c94  mov     edx, r15d
0x1400b2c97  lea     rcx, [rbp+var_18]
0x1400b2c9b  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x1400b2ca0  mov     ebx, eax
0x1400b2ca2  test    eax, eax
0x1400b2ca4  jns     short loc_1400B2CE0
0x1400b2ca6  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2cad  lea     rdi, WPP_GLOBAL_Control
0x1400b2cb4  cmp     rax, rdi
0x1400b2cb7  jz      loc_1400B30BF
0x1400b2cbd  test    byte ptr [rax+1Ch], 8
0x1400b2cc1  jz      loc_1400B30BF
0x1400b2cc7  cmp     [rax+19h], r15b
0x1400b2ccb  jb      loc_1400B30BF
0x1400b2cd1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2cd6  mov     edx, 0Fh
0x1400b2cdb  jmp     loc_1400B2C30
0x1400b2ce0  test    rsi, rsi
0x1400b2ce3  jz      short loc_1400B2D55
0x1400b2ce5  cmp     [rsi], r14w
0x1400b2ce9  jz      short loc_1400B2D55
0x1400b2ceb  xor     edx, edx; pUnkOuter
0x1400b2ced  lea     rax, [rbp+var_10]
0x1400b2cf1  lea     r9, _GUID_96d8d7cf_783e_4286_834c_ebc0e95f783c; riid
0x1400b2cf8  mov     [rsp+60h+ppv], rax; ppv
0x1400b2cfd  lea     rcx, _GUID_4f1dfca6_3aad_48e1_8406_4bc21a501d7c; rclsid
0x1400b2d04  lea     r8d, [rdx+4]; dwClsContext
0x1400b2d08  call    cs:__imp_CoCreateInstance
0x1400b2d0e  mov     ebx, eax
0x1400b2d10  test    eax, eax
0x1400b2d12  jns     short loc_1400B2D55
0x1400b2d14  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2d1b  lea     rdi, WPP_GLOBAL_Control
0x1400b2d22  cmp     rax, rdi
0x1400b2d25  jz      loc_1400B30BF
0x1400b2d2b  test    byte ptr [rax+1Ch], 8
0x1400b2d2f  jz      loc_1400B30BF
0x1400b2d35  cmp     [rax+19h], r15b
0x1400b2d39  jb      loc_1400B30BF
0x1400b2d3f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2d44  mov     edx, 10h
0x1400b2d49  lea     rcx, aCocreateinstan_1; "CoCreateInstance failed!"
0x1400b2d50  jmp     loc_1400B309C
0x1400b2d55  mov     rcx, [rbp+var_10]
0x1400b2d59  test    rcx, rcx
0x1400b2d5c  jz      loc_1400B2EE6
0x1400b2d62  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2d69  lea     rdi, WPP_GLOBAL_Control
0x1400b2d70  cmp     rax, rdi
0x1400b2d73  jz      short loc_1400B2DA9
0x1400b2d75  test    byte ptr [rax+1Ch], 1
0x1400b2d79  jz      short loc_1400B2DA9
0x1400b2d7b  cmp     byte ptr [rax+19h], 5
0x1400b2d7f  jb      short loc_1400B2DA9
0x1400b2d81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2d86  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2d8d  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b2d94  mov     edx, 11h
0x1400b2d99  mov     r9d, eax
0x1400b2d9c  mov     rcx, [rcx+10h]
0x1400b2da0  call    WPP_SF_d
0x1400b2da5  mov     rcx, [rbp+var_10]
0x1400b2da9  mov     rax, [rcx]
0x1400b2dac  lea     rdx, [rbp+dwProcessId]
0x1400b2db0  mov     rax, [rax+28h]
0x1400b2db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b2db9  mov     ebx, eax
0x1400b2dbb  test    eax, eax
0x1400b2dbd  jns     short loc_1400B2DF9
0x1400b2dbf  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2dc6  cmp     rax, rdi
0x1400b2dc9  jz      loc_1400B30BF
0x1400b2dcf  test    byte ptr [rax+1Ch], 8
0x1400b2dd3  jz      loc_1400B30BF
0x1400b2dd9  cmp     [rax+19h], r15b
0x1400b2ddd  jb      loc_1400B30BF
0x1400b2de3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2de8  mov     edx, 12h
0x1400b2ded  lea     rcx, aSpworkspaceGet; "spWorkspace->GetProcessId failed!"
0x1400b2df4  jmp     loc_1400B309C
0x1400b2df9  mov     ecx, [rbp+dwProcessId]; dwProcessId
0x1400b2dfc  call    cs:__imp_AllowSetForegroundWindow
0x1400b2e02  test    eax, eax
0x1400b2e04  jnz     short loc_1400B2E6B
0x1400b2e06  call    cs:__imp_GetLastError
0x1400b2e0c  mov     ebx, eax
0x1400b2e0e  test    eax, eax
0x1400b2e10  jle     short loc_1400B2E1B
0x1400b2e12  movzx   ebx, ax
0x1400b2e15  or      ebx, 80070000h
0x1400b2e1b  test    ebx, ebx
0x1400b2e1d  jns     short loc_1400B2E6B
0x1400b2e1f  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2e26  cmp     rax, rdi
0x1400b2e29  jz      short loc_1400B2E6B
0x1400b2e2b  test    byte ptr [rax+1Ch], 8
0x1400b2e2f  jz      short loc_1400B2E6B
0x1400b2e31  cmp     [rax+19h], r15b
0x1400b2e35  jb      short loc_1400B2E6B
0x1400b2e37  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2e3c  lea     rcx, aAllowsetforegr; "AllowSetForegroundWindow failed!"
0x1400b2e43  mov     dword ptr [rsp+60h+var_38], ebx
0x1400b2e47  mov     [rsp+60h+ppv], rcx
0x1400b2e4c  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b2e53  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2e5a  mov     edx, 13h
0x1400b2e5f  mov     r9d, eax
0x1400b2e62  mov     rcx, [rcx+10h]
0x1400b2e66  call    WPP_SF_DsD
0x1400b2e6b  mov     rcx, [rbp+var_10]
0x1400b2e6f  xor     r8d, r8d
0x1400b2e72  mov     rdx, [rbp+var_18]
0x1400b2e76  mov     r9, [rbp+arg_20]
0x1400b2e7a  mov     [rsp+60h+var_30], rdx
0x1400b2e7f  mov     rdx, rsi
0x1400b2e82  mov     rax, [rcx]
0x1400b2e85  mov     [rsp+60h+var_38], r14
0x1400b2e8a  mov     word ptr [rsp+60h+ppv], r14w
0x1400b2e90  mov     rax, [rax+30h]
0x1400b2e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b2e99  cmp     eax, 800700B7h
0x1400b2e9e  mov     ebx, r14d
0x1400b2ea1  cmovnz  ebx, eax
0x1400b2ea4  test    ebx, ebx
0x1400b2ea6  jns     loc_1400B30BF
0x1400b2eac  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2eb3  cmp     rax, rdi
0x1400b2eb6  jz      loc_1400B30BF
0x1400b2ebc  test    byte ptr [rax+1Ch], 8
0x1400b2ec0  jz      loc_1400B30BF
0x1400b2ec6  cmp     [rax+19h], r15b
0x1400b2eca  jb      loc_1400B30BF
0x1400b2ed0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2ed5  mov     edx, 14h
0x1400b2eda  lea     rcx, aSpworkspaceSta; "spWorkspace->StartRemoteApplication fai"...
0x1400b2ee1  jmp     loc_1400B309C
0x1400b2ee6  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2eed  lea     rdi, WPP_GLOBAL_Control
0x1400b2ef4  cmp     rax, rdi
0x1400b2ef7  jz      short loc_1400B2F29
0x1400b2ef9  test    byte ptr [rax+1Ch], 1
0x1400b2efd  jz      short loc_1400B2F29
0x1400b2eff  cmp     byte ptr [rax+19h], 5
0x1400b2f03  jb      short loc_1400B2F29
0x1400b2f05  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2f11  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b2f18  mov     edx, 15h
0x1400b2f1d  mov     r9d, eax
0x1400b2f20  mov     rcx, [rcx+10h]
0x1400b2f24  call    WPP_SF_d
0x1400b2f29  xor     edx, edx; pUnkOuter
0x1400b2f2b  lea     rax, [rbp+var_8]
0x1400b2f2f  lea     r9, _GUID_a0b2dd9a_7f53_4e65_8547_851952ec8c96; riid
0x1400b2f36  mov     [rsp+60h+ppv], rax; ppv
0x1400b2f3b  lea     rcx, _GUID_1b462d7b_72d8_4544_acc1_d84e5b9a8a14; rclsid
0x1400b2f42  lea     r8d, [rdx+4]; dwClsContext
0x1400b2f46  call    cs:__imp_CoCreateInstance
0x1400b2f4c  mov     ebx, eax
0x1400b2f4e  test    eax, eax
0x1400b2f50  jns     short loc_1400B2F85
0x1400b2f52  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2f59  cmp     rax, rdi
0x1400b2f5c  jz      loc_1400B30BF
0x1400b2f62  test    byte ptr [rax+1Ch], 8
0x1400b2f66  jz      loc_1400B30BF
0x1400b2f6c  cmp     [rax+19h], r15b
0x1400b2f70  jb      loc_1400B30BF
0x1400b2f76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2f7b  mov     edx, 16h
0x1400b2f80  jmp     loc_1400B2D49
0x1400b2f85  mov     rcx, [rbp+var_8]
0x1400b2f89  lea     rdx, [rbp+dwProcessId]
0x1400b2f8d  mov     rax, [rcx]
0x1400b2f90  mov     rax, [rax+20h]
0x1400b2f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b2f99  mov     ebx, eax
0x1400b2f9b  test    eax, eax
0x1400b2f9d  jns     short loc_1400B2FD9
0x1400b2f9f  mov     rax, cs:WPP_GLOBAL_Control
0x1400b2fa6  cmp     rax, rdi
  ... truncated ...
```
