# CTscComHelper::StartRemoteApplication(ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x1400b4c1c`
- end: `0x1400b5260`
- name: `?StartRemoteApplication@CTscComHelper@@SAJPEAG0000@Z`
- size: `1604`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400441f8`

## callees

- `0x1400095f0`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14000d87c`
- `0x14005c2bc`
- `0x14005c864`
- `0x1400b4c1c`
- `0x140114010`

## import_xrefs

- `USER32!AllowSetForegroundWindow` at `0x1400b4f6c`
- `USER32!AllowSetForegroundWindow` at `0x1400b514c`
- `USER32!AllowSetForegroundWindow` at `0x1400b4f6c`
- `USER32!AllowSetForegroundWindow` at `0x1400b514c`
- `KERNEL32!GetLastError` at `0x1400b4f76`
- `KERNEL32!GetLastError` at `0x1400b5156`
- `KERNEL32!GetLastError` at `0x1400b4f76`
- `KERNEL32!GetLastError` at `0x1400b5156`
- `ole32!CoCreateInstance` at `0x1400b4e78`
- `ole32!CoCreateInstance` at `0x1400b50b6`
- `ole32!CoCreateInstance` at `0x1400b4e78`
- `ole32!CoCreateInstance` at `0x1400b50b6`

## string_xrefs

- `0x1400b4eb9`: `CoCreateInstance failed!`
- `0x1400b4c97`: `bstrCommandLine`
- `0x1400b513d`: `spRemoteDesktopClient->GetProcessId failed!`
- `0x1400b4d4a`: `saParams.Create failed!`
- `0x1400b4f5d`: `spWorkspace->GetProcessId failed!`

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
0x1400b4c1c  mov     rax, rsp
0x1400b4c1f  mov     [rax+20h], rbx
0x1400b4c23  mov     [rax+18h], r8
0x1400b4c27  mov     [rax+10h], rdx
0x1400b4c2b  mov     [rax+8], rcx
0x1400b4c2f  push    rbp
0x1400b4c30  push    rsi
0x1400b4c31  push    rdi
0x1400b4c32  push    r14
0x1400b4c34  push    r15
0x1400b4c36  mov     rbp, rsp
0x1400b4c39  sub     rsp, 60h
0x1400b4c3d  xor     r14d, r14d
0x1400b4c40  mov     rdi, r8
0x1400b4c43  mov     r8, rdx
0x1400b4c46  mov     [rbp+var_18], r14
0x1400b4c4a  mov     rax, rdi
0x1400b4c4d  mov     [rbp+var_8], r14
0x1400b4c51  neg     rax
0x1400b4c54  mov     [rbp+var_10], r14
0x1400b4c58  lea     r15d, [r14+2]
0x1400b4c5c  mov     [rbp+dwProcessId], r14d
0x1400b4c60  sbb     edx, edx
0x1400b4c62  mov     rsi, r9
0x1400b4c65  neg     edx
0x1400b4c67  add     edx, r15d
0x1400b4c6a  test    rcx, rcx
0x1400b4c6d  jnz     short loc_1400B4CCF
0x1400b4c6f  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4c76  lea     rdi, WPP_GLOBAL_Control
0x1400b4c7d  cmp     rax, rdi
0x1400b4c80  jz      short loc_1400B4CC5
0x1400b4c82  test    byte ptr [rax+1Ch], 8
0x1400b4c86  jz      short loc_1400B4CC5
0x1400b4c88  cmp     [rax+19h], r15b
0x1400b4c8c  jb      short loc_1400B4CC5
0x1400b4c8e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4c93  lea     edx, [r14+0Ah]
0x1400b4c97  lea     rcx, aBstrcommandlin; "bstrCommandLine"
0x1400b4c9e  mov     dword ptr [rsp+60h+var_38], 80070057h
0x1400b4ca6  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b4cad  mov     [rsp+60h+ppv], rcx
0x1400b4cb2  mov     r9d, eax
0x1400b4cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4cbc  mov     rcx, [rcx+10h]
0x1400b4cc0  call    WPP_SF_DsD
0x1400b4cc5  mov     ebx, 80070057h
0x1400b4cca  jmp     loc_1400B522F
0x1400b4ccf  test    r8, r8
0x1400b4cd2  jnz     short loc_1400B4D06
0x1400b4cd4  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4cdb  lea     rdi, WPP_GLOBAL_Control
0x1400b4ce2  cmp     rax, rdi
0x1400b4ce5  jz      short loc_1400B4CC5
0x1400b4ce7  test    byte ptr [rax+1Ch], 8
0x1400b4ceb  jz      short loc_1400B4CC5
0x1400b4ced  cmp     [rax+19h], r15b
0x1400b4cf1  jb      short loc_1400B4CC5
0x1400b4cf3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4cf8  mov     edx, 0Bh
0x1400b4cfd  lea     rcx, aBstrrdpfilenam; "bstrRDPFileName"
0x1400b4d04  jmp     short loc_1400B4C9E
0x1400b4d06  lea     rcx, [rbp+var_18]
0x1400b4d0a  call    ?Create@?$CComSafeArray@PEAG$07@ATL@@QEAAJKJ@Z; ATL::CComSafeArray<ushort *,8>::Create(ulong,long)
0x1400b4d0f  mov     ebx, eax
0x1400b4d11  test    eax, eax
0x1400b4d13  jns     short loc_1400B4D56
0x1400b4d15  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4d1c  lea     rdi, WPP_GLOBAL_Control
0x1400b4d23  cmp     rax, rdi
0x1400b4d26  jz      loc_1400B522F
0x1400b4d2c  test    byte ptr [rax+1Ch], 8
0x1400b4d30  jz      loc_1400B522F
0x1400b4d36  cmp     [rax+19h], r15b
0x1400b4d3a  jb      loc_1400B522F
0x1400b4d40  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4d45  mov     edx, 0Ch
0x1400b4d4a  lea     rcx, aSaparamsCreate; "saParams.Create failed!"
0x1400b4d51  jmp     loc_1400B520C
0x1400b4d56  lea     r8, [rbp+arg_0]
0x1400b4d5a  xor     edx, edx
0x1400b4d5c  lea     rcx, [rbp+var_18]
0x1400b4d60  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x1400b4d65  mov     ebx, eax
0x1400b4d67  test    eax, eax
0x1400b4d69  jns     short loc_1400B4DAC
0x1400b4d6b  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4d72  lea     rdi, WPP_GLOBAL_Control
0x1400b4d79  cmp     rax, rdi
0x1400b4d7c  jz      loc_1400B522F
0x1400b4d82  test    byte ptr [rax+1Ch], 8
0x1400b4d86  jz      loc_1400B522F
0x1400b4d8c  cmp     [rax+19h], r15b
0x1400b4d90  jb      loc_1400B522F
0x1400b4d96  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4d9b  mov     edx, 0Dh
0x1400b4da0  lea     rcx, aParamsSetatFai; "Params.SetAt failed!"
0x1400b4da7  jmp     loc_1400B520C
0x1400b4dac  lea     r8, [rbp+arg_8]
0x1400b4db0  mov     edx, 1
0x1400b4db5  lea     rcx, [rbp+var_18]
0x1400b4db9  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x1400b4dbe  mov     ebx, eax
0x1400b4dc0  test    eax, eax
0x1400b4dc2  jns     short loc_1400B4DFB
0x1400b4dc4  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4dcb  lea     rdi, WPP_GLOBAL_Control
0x1400b4dd2  cmp     rax, rdi
0x1400b4dd5  jz      loc_1400B522F
0x1400b4ddb  test    byte ptr [rax+1Ch], 8
0x1400b4ddf  jz      loc_1400B522F
0x1400b4de5  cmp     [rax+19h], r15b
0x1400b4de9  jb      loc_1400B522F
0x1400b4def  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4df4  mov     edx, 0Eh
0x1400b4df9  jmp     short loc_1400B4DA0
0x1400b4dfb  test    rdi, rdi
0x1400b4dfe  jz      short loc_1400B4E50
0x1400b4e00  lea     r8, [rbp+arg_10]
0x1400b4e04  mov     edx, r15d
0x1400b4e07  lea     rcx, [rbp+var_18]
0x1400b4e0b  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x1400b4e10  mov     ebx, eax
0x1400b4e12  test    eax, eax
0x1400b4e14  jns     short loc_1400B4E50
0x1400b4e16  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4e1d  lea     rdi, WPP_GLOBAL_Control
0x1400b4e24  cmp     rax, rdi
0x1400b4e27  jz      loc_1400B522F
0x1400b4e2d  test    byte ptr [rax+1Ch], 8
0x1400b4e31  jz      loc_1400B522F
0x1400b4e37  cmp     [rax+19h], r15b
0x1400b4e3b  jb      loc_1400B522F
0x1400b4e41  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4e46  mov     edx, 0Fh
0x1400b4e4b  jmp     loc_1400B4DA0
0x1400b4e50  test    rsi, rsi
0x1400b4e53  jz      short loc_1400B4EC5
0x1400b4e55  cmp     [rsi], r14w
0x1400b4e59  jz      short loc_1400B4EC5
0x1400b4e5b  xor     edx, edx; pUnkOuter
0x1400b4e5d  lea     rax, [rbp+var_10]
0x1400b4e61  lea     r9, _GUID_96d8d7cf_783e_4286_834c_ebc0e95f783c; riid
0x1400b4e68  mov     [rsp+60h+ppv], rax; ppv
0x1400b4e6d  lea     rcx, _GUID_4f1dfca6_3aad_48e1_8406_4bc21a501d7c; rclsid
0x1400b4e74  lea     r8d, [rdx+4]; dwClsContext
0x1400b4e78  call    cs:__imp_CoCreateInstance
0x1400b4e7e  mov     ebx, eax
0x1400b4e80  test    eax, eax
0x1400b4e82  jns     short loc_1400B4EC5
0x1400b4e84  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4e8b  lea     rdi, WPP_GLOBAL_Control
0x1400b4e92  cmp     rax, rdi
0x1400b4e95  jz      loc_1400B522F
0x1400b4e9b  test    byte ptr [rax+1Ch], 8
0x1400b4e9f  jz      loc_1400B522F
0x1400b4ea5  cmp     [rax+19h], r15b
0x1400b4ea9  jb      loc_1400B522F
0x1400b4eaf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4eb4  mov     edx, 10h
0x1400b4eb9  lea     rcx, aCocreateinstan_1; "CoCreateInstance failed!"
0x1400b4ec0  jmp     loc_1400B520C
0x1400b4ec5  mov     rcx, [rbp+var_10]
0x1400b4ec9  test    rcx, rcx
0x1400b4ecc  jz      loc_1400B5056
0x1400b4ed2  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4ed9  lea     rdi, WPP_GLOBAL_Control
0x1400b4ee0  cmp     rax, rdi
0x1400b4ee3  jz      short loc_1400B4F19
0x1400b4ee5  test    byte ptr [rax+1Ch], 1
0x1400b4ee9  jz      short loc_1400B4F19
0x1400b4eeb  cmp     byte ptr [rax+19h], 5
0x1400b4eef  jb      short loc_1400B4F19
0x1400b4ef1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4efd  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b4f04  mov     edx, 11h
0x1400b4f09  mov     r9d, eax
0x1400b4f0c  mov     rcx, [rcx+10h]
0x1400b4f10  call    WPP_SF_d
0x1400b4f15  mov     rcx, [rbp+var_10]
0x1400b4f19  mov     rax, [rcx]
0x1400b4f1c  lea     rdx, [rbp+dwProcessId]
0x1400b4f20  mov     rax, [rax+28h]
0x1400b4f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b4f29  mov     ebx, eax
0x1400b4f2b  test    eax, eax
0x1400b4f2d  jns     short loc_1400B4F69
0x1400b4f2f  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4f36  cmp     rax, rdi
0x1400b4f39  jz      loc_1400B522F
0x1400b4f3f  test    byte ptr [rax+1Ch], 8
0x1400b4f43  jz      loc_1400B522F
0x1400b4f49  cmp     [rax+19h], r15b
0x1400b4f4d  jb      loc_1400B522F
0x1400b4f53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4f58  mov     edx, 12h
0x1400b4f5d  lea     rcx, aSpworkspaceGet; "spWorkspace->GetProcessId failed!"
0x1400b4f64  jmp     loc_1400B520C
0x1400b4f69  mov     ecx, [rbp+dwProcessId]; dwProcessId
0x1400b4f6c  call    cs:__imp_AllowSetForegroundWindow
0x1400b4f72  test    eax, eax
0x1400b4f74  jnz     short loc_1400B4FDB
0x1400b4f76  call    cs:__imp_GetLastError
0x1400b4f7c  mov     ebx, eax
0x1400b4f7e  test    eax, eax
0x1400b4f80  jle     short loc_1400B4F8B
0x1400b4f82  movzx   ebx, ax
0x1400b4f85  or      ebx, 80070000h
0x1400b4f8b  test    ebx, ebx
0x1400b4f8d  jns     short loc_1400B4FDB
0x1400b4f8f  mov     rax, cs:WPP_GLOBAL_Control
0x1400b4f96  cmp     rax, rdi
0x1400b4f99  jz      short loc_1400B4FDB
0x1400b4f9b  test    byte ptr [rax+1Ch], 8
0x1400b4f9f  jz      short loc_1400B4FDB
0x1400b4fa1  cmp     [rax+19h], r15b
0x1400b4fa5  jb      short loc_1400B4FDB
0x1400b4fa7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4fac  lea     rcx, aAllowsetforegr; "AllowSetForegroundWindow failed!"
0x1400b4fb3  mov     dword ptr [rsp+60h+var_38], ebx
0x1400b4fb7  mov     [rsp+60h+ppv], rcx
0x1400b4fbc  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b4fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4fca  mov     edx, 13h
0x1400b4fcf  mov     r9d, eax
0x1400b4fd2  mov     rcx, [rcx+10h]
0x1400b4fd6  call    WPP_SF_DsD
0x1400b4fdb  mov     rcx, [rbp+var_10]
0x1400b4fdf  xor     r8d, r8d
0x1400b4fe2  mov     rdx, [rbp+var_18]
0x1400b4fe6  mov     r9, [rbp+arg_20]
0x1400b4fea  mov     [rsp+60h+var_30], rdx
0x1400b4fef  mov     rdx, rsi
0x1400b4ff2  mov     rax, [rcx]
0x1400b4ff5  mov     [rsp+60h+var_38], r14
0x1400b4ffa  mov     word ptr [rsp+60h+ppv], r14w
0x1400b5000  mov     rax, [rax+30h]
0x1400b5004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b5009  cmp     eax, 800700B7h
0x1400b500e  mov     ebx, r14d
0x1400b5011  cmovnz  ebx, eax
0x1400b5014  test    ebx, ebx
0x1400b5016  jns     loc_1400B522F
0x1400b501c  mov     rax, cs:WPP_GLOBAL_Control
0x1400b5023  cmp     rax, rdi
0x1400b5026  jz      loc_1400B522F
0x1400b502c  test    byte ptr [rax+1Ch], 8
0x1400b5030  jz      loc_1400B522F
0x1400b5036  cmp     [rax+19h], r15b
0x1400b503a  jb      loc_1400B522F
0x1400b5040  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b5045  mov     edx, 14h
0x1400b504a  lea     rcx, aSpworkspaceSta; "spWorkspace->StartRemoteApplication fai"...
0x1400b5051  jmp     loc_1400B520C
0x1400b5056  mov     rax, cs:WPP_GLOBAL_Control
0x1400b505d  lea     rdi, WPP_GLOBAL_Control
0x1400b5064  cmp     rax, rdi
0x1400b5067  jz      short loc_1400B5099
0x1400b5069  test    byte ptr [rax+1Ch], 1
0x1400b506d  jz      short loc_1400B5099
0x1400b506f  cmp     byte ptr [rax+19h], 5
0x1400b5073  jb      short loc_1400B5099
0x1400b5075  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b507a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5081  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1400b5088  mov     edx, 15h
0x1400b508d  mov     r9d, eax
0x1400b5090  mov     rcx, [rcx+10h]
0x1400b5094  call    WPP_SF_d
0x1400b5099  xor     edx, edx; pUnkOuter
0x1400b509b  lea     rax, [rbp+var_8]
0x1400b509f  lea     r9, _GUID_a0b2dd9a_7f53_4e65_8547_851952ec8c96; riid
0x1400b50a6  mov     [rsp+60h+ppv], rax; ppv
0x1400b50ab  lea     rcx, _GUID_1b462d7b_72d8_4544_acc1_d84e5b9a8a14; rclsid
0x1400b50b2  lea     r8d, [rdx+4]; dwClsContext
0x1400b50b6  call    cs:__imp_CoCreateInstance
0x1400b50bc  mov     ebx, eax
0x1400b50be  test    eax, eax
0x1400b50c0  jns     short loc_1400B50F5
0x1400b50c2  mov     rax, cs:WPP_GLOBAL_Control
0x1400b50c9  cmp     rax, rdi
0x1400b50cc  jz      loc_1400B522F
0x1400b50d2  test    byte ptr [rax+1Ch], 8
0x1400b50d6  jz      loc_1400B522F
0x1400b50dc  cmp     [rax+19h], r15b
0x1400b50e0  jb      loc_1400B522F
0x1400b50e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b50eb  mov     edx, 16h
0x1400b50f0  jmp     loc_1400B4EB9
0x1400b50f5  mov     rcx, [rbp+var_8]
0x1400b50f9  lea     rdx, [rbp+dwProcessId]
0x1400b50fd  mov     rax, [rcx]
0x1400b5100  mov     rax, [rax+20h]
0x1400b5104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b5109  mov     ebx, eax
0x1400b510b  test    eax, eax
0x1400b510d  jns     short loc_1400B5149
0x1400b510f  mov     rax, cs:WPP_GLOBAL_Control
0x1400b5116  cmp     rax, rdi
  ... truncated ...
```
