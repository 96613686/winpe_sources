# CDtcConfig::SetRemoteDtc(ushort *)

- ea: `0x180049f90`
- end: `0x18004a5f5`
- name: `?SetRemoteDtc@CDtcConfig@@UEAAJPEAG@Z`
- size: `1637`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180047fa4`
- `0x180049690`
- `0x180049f90`
- `0x1800537f0`
- `0x18007436c`
- `0x180081dd0`
- `0x180085010`

## string_xrefs

- `0x180049fca`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049fef`: `CDtcConfig::SetRemoteDtc`
- `0x18004a12b`: `About to copy remote proxy info`
- `0x18004a24a`: `CopyContact (DTCTM)`
- `0x18004a282`: `CopyContact (XATM)`
- `0x18004a2be`: `CopyContact (TIPGW)`
- `0x18004a2d5`: `HostName = %s resolves to local computer and not the remote host!`
- `0x18004a349`: `GetServiceId (MSDTC)`
- `0x18004a37b`: `SetServiceId (MSDTC)`
- `0x18004a3aa`: `WriteW (MSDTC)`
- `0x18004a3da`: `GetServiceId (MSDTCXATM)`
- `0x18004a40c`: `SetServiceId (MSDTCXATM)`
- `0x18004a43b`: `WriteW (MSDTCXATM)`
- `0x18004a46b`: `GetServiceId (TIPGW)`
- `0x18004a49a`: `SetServiceId (TIPGW)`
- `0x18004a4c6`: `WriteW (TIPGW)`

## pseudocode

```c
__int64 __fastcall CDtcConfig::SetRemoteDtc(CDtcConfig *this, unsigned __int16 *a2)
{
  int IsPropertiesEqual; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  CDtcConfig *v7; // rcx
  CDtcConfig *v8; // rcx
  __int64 v10; // [rsp+28h] [rbp-41h]
  struct IContactPool *v11; // [rsp+40h] [rbp-29h] BYREF
  int v12; // [rsp+48h] [rbp-21h] BYREF
  struct IProperties *v13; // [rsp+50h] [rbp-19h] BYREF
  struct IContactPool *v14; // [rsp+58h] [rbp-11h] BYREF
  __int64 v15; // [rsp+60h] [rbp-9h] BYREF
  __int64 v16; // [rsp+68h] [rbp-1h] BYREF
  int v17; // [rsp+70h] [rbp+7h] BYREF
  struct IProperties *v18; // [rsp+78h] [rbp+Fh] BYREF
  struct ITmInstance *v19; // [rsp+80h] [rbp+17h] BYREF
  __int128 v20; // [rsp+88h] [rbp+1Fh] BYREF

  v11 = 0;
  v19 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v12 = 0;
  v20 = 0;
  v17 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1787,
    L"CDtcConfig::SetRemoteDtc",
    0,
    L"In");
  IsPropertiesEqual = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct IContactPool **))(**((_QWORD **)this + 2) + 136LL))(
                        *((_QWORD *)this + 2),
                        &IID_IContactPool,
                        &v11);
  if ( IsPropertiesEqual >= 0 )
  {
    IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, _QWORD, const WCHAR *, GUID *, struct IProperties **))(*(_QWORD *)v11 + 32LL))(
                          v11,
                          0,
                          L"MSDTC",
                          &IID_IProperties,
                          &v13);
    if ( IsPropertiesEqual >= 0 )
    {
      IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, _QWORD, const WCHAR *, GUID *, __int64 *))(*(_QWORD *)v11 + 32LL))(
                            v11,
                            0,
                            L"MSDTCXATM",
                            &IID_IProperties,
                            &v15);
      if ( IsPropertiesEqual >= 0 )
      {
        IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, _QWORD, const WCHAR *, GUID *, __int64 *))(*(_QWORD *)v11 + 32LL))(
                              v11,
                              0,
                              L"MSDTCTIPGW",
                              &IID_IProperties,
                              &v16);
        if ( IsPropertiesEqual >= 0 )
        {
          if ( a2 )
          {
            TraceStringInline(
              15,
              4,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
              1837,
              L"CDtcConfig::SetRemoteDtc",
              0,
              L"About to copy remote proxy info");
            IsPropertiesEqual = CreateTmInstanceForRemoteAdmin(a2, &v19);
            if ( IsPropertiesEqual >= 0 )
            {
              IsPropertiesEqual = (*(__int64 (__fastcall **)(struct ITmInstance *, GUID *, struct IContactPool **))(*(_QWORD *)v19 + 136LL))(
                                    v19,
                                    &IID_IContactPool,
                                    &v14);
              if ( IsPropertiesEqual >= 0 )
              {
                IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, _QWORD, const WCHAR *, GUID *, struct IProperties **))(*(_QWORD *)v14 + 32LL))(
                                      v14,
                                      0,
                                      L"MSDTC",
                                      &IID_IProperties,
                                      &v18);
                if ( IsPropertiesEqual >= 0 )
                {
                  IsPropertiesEqual = CDtcConfig::IsPropertiesEqual(v8, v13, v18, &v17);
                  if ( IsPropertiesEqual >= 0 )
                  {
                    if ( v17 )
                    {
                      IsPropertiesEqual = -2147418113;
                      LODWORD(v10) = -2147418113;
                      TraceStringInline(
                        15,
                        1,
                        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
                        1910,
                        L"CDtcConfig::SetRemoteDtc",
                        v10,
                        L"HostName = %s resolves to local computer and not the remote host!",
                        a2);
                      goto LABEL_47;
                    }
                    IsPropertiesEqual = CopyAndConfigureContact(v14, (wchar_t *)L"MSDTC", v11, L"MSDTC Default", a2);
                    if ( IsPropertiesEqual >= 0 )
                    {
                      IsPropertiesEqual = CopyAndConfigureContact(
                                            v14,
                                            (wchar_t *)L"MSDTCXATM",
                                            v11,
                                            L"MSDTCXATM Default",
                                            a2);
                      if ( IsPropertiesEqual >= 0 )
                      {
                        IsPropertiesEqual = CopyAndConfigureContact(
                                              v14,
                                              (wchar_t *)L"MSDTCTIPGW",
                                              v11,
                                              L"MSDTCTIPGW Default",
                                              a2);
                        if ( IsPropertiesEqual >= 0 )
                          goto LABEL_47;
                        v5 = L"CopyContact (TIPGW)";
                        v6 = 1903;
                      }
                      else
                      {
                        v5 = L"CopyContact (XATM)";
                        v6 = 1894;
                      }
                    }
                    else
                    {
                      v5 = L"CopyContact (DTCTM)";
                      v6 = 1885;
                    }
                  }
                  else
                  {
                    v5 = L"IsPropertiesEqual failed!";
                    v6 = 1872;
                  }
                }
                else
                {
                  v5 = L"GetByIdentityW (MSDTC)";
                  v6 = 1863;
                }
              }
              else
              {
                v5 = L"GetContactPool (remote)";
                v6 = 1852;
              }
            }
            else
            {
              v5 = L"Creating 'remote' TM instance";
              v6 = 1843;
            }
          }
          else
          {
            IsPropertiesEqual = CDtcConfig::CleanDefaultContacts(v7, v11);
            if ( IsPropertiesEqual >= 0 )
            {
              IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IProperties *, __int128 *, int *))(*(_QWORD *)v13 + 112LL))(
                                    v13,
                                    &v20,
                                    &v12);
              if ( IsPropertiesEqual >= 0 )
              {
                IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IProperties *, __int128 *, __int64))(*(_QWORD *)v13 + 120LL))(
                                      v13,
                                      &v20,
                                      1);
                if ( IsPropertiesEqual >= 0 )
                {
                  IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, struct IProperties *, _QWORD))(*(_QWORD *)v11 + 64LL))(
                                        v11,
                                        v13,
                                        0);
                  if ( IsPropertiesEqual >= 0 )
                  {
                    IsPropertiesEqual = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)v15 + 112LL))(
                                          v15,
                                          &v20,
                                          &v12);
                    if ( IsPropertiesEqual >= 0 )
                    {
                      IsPropertiesEqual = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v15
                                                                                                  + 120LL))(
                                            v15,
                                            &v20,
                                            1);
                      if ( IsPropertiesEqual >= 0 )
                      {
                        IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, __int64, _QWORD))(*(_QWORD *)v11 + 64LL))(
                                              v11,
                                              v15,
                                              0);
                        if ( IsPropertiesEqual >= 0 )
                        {
                          IsPropertiesEqual = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)v16 + 112LL))(
                                                v16,
                                                &v20,
                                                &v12);
                          if ( IsPropertiesEqual >= 0 )
                          {
                            IsPropertiesEqual = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v16 + 120LL))(
                                                  v16,
                                                  &v20,
                                                  1);
                            if ( IsPropertiesEqual >= 0 )
                            {
                              IsPropertiesEqual = (*(__int64 (__fastcall **)(struct IContactPool *, __int64, _QWORD))(*(_QWORD *)v11 + 64LL))(
                                                    v11,
                                                    v16,
                                                    0);
                              if ( IsPropertiesEqual >= 0 )
                                goto LABEL_47;
                              v5 = L"WriteW (TIPGW)";
                              v6 = 1981;
                            }
                            else
                            {
                              v5 = L"SetServiceId (TIPGW)";
                              v6 = 1974;
                            }
                          }
                          else
                          {
                            v5 = L"GetServiceId (TIPGW)";
                            v6 = 1967;
                          }
                        }
                        else
                        {
                          v5 = L"WriteW (MSDTCXATM)";
                          v6 = 1961;
                        }
                      }
                      else
                      {
                        v5 = L"SetServiceId (MSDTCXATM)";
                        v6 = 1954;
                      }
                    }
                    else
                    {
                      v5 = L"GetServiceId (MSDTCXATM)";
                      v6 = 1947;
                    }
                  }
                  else
                  {
                    v5 = L"WriteW (MSDTC)";
                    v6 = 1940;
                  }
                }
                else
                {
                  v5 = L"SetServiceId (MSDTC)";
                  v6 = 1933;
                }
              }
              else
              {
                v5 = L"GetServiceId (MSDTC)";
                v6 = 1926;
              }
            }
            else
            {
              v5 = L"CleanDefaultContacts failed.";
              v6 = 1919;
            }
          }
        }
        else
        {
          v5 = L"GetByIdentityW (TIPGW)";
          v6 = 1831;
        }
      }
      else
      {
        v5 = L"GetByIdentityW (MSDTCXATM)";
        v6 = 1820;
      }
    }
    else
    {
      v5 = L"GetByIdentityW (MSDTC)";
      v6 = 1809;
    }
  }
  else
  {
    v5 = L"GetContactPool";
    v6 = 1793;
  }
  LODWORD(v10) = IsPropertiesEqual;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    v6,
    L"CDtcConfig::SetRemoteDtc",
    v10,
    v5);
LABEL_47:
  if ( v18 )
  {
    (*(void (__fastcall **)(struct IProperties *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(struct IProperties *))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(struct IContactPool *))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(struct IContactPool *))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  LODWORD(v10) = IsPropertiesEqual;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1995,
    L"CDtcConfig::SetRemoteDtc",
    v10,
    L"Out");
  return (unsigned int)IsPropertiesEqual;
}

```

## disassembly

```asm
0x180049f90  mov     [rsp-8+arg_10], rbx
0x180049f95  mov     [rsp-8+arg_18], rsi
0x180049f9a  push    rbp
0x180049f9b  push    rdi
0x180049f9c  push    r12
0x180049f9e  push    r14
0x180049fa0  push    r15
0x180049fa2  lea     rbp, [rsp-37h]
0x180049fa7  sub     rsp, 0A0h
0x180049fae  mov     rax, cs:__security_cookie
0x180049fb5  xor     rax, rsp
0x180049fb8  mov     [rbp+57h+var_28], rax
0x180049fbc  xor     esi, esi
0x180049fbe  lea     rax, aIn_0; "In"
0x180049fc5  mov     [rsp+0C0h+var_90], rax
0x180049fca  lea     r14, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049fd1  mov     rdi, rdx
0x180049fd4  mov     [rsp+0C0h+var_98], rsi
0x180049fd9  mov     rbx, rcx
0x180049fdc  mov     [rbp+57h+var_80], rsi
0x180049fe0  xorps   xmm0, xmm0
0x180049fe3  mov     [rbp+57h+var_40], rsi
0x180049fe7  lea     r15d, [rsi+0Fh]
0x180049feb  mov     [rbp+57h+var_68], rsi
0x180049fef  lea     r12, aCdtcconfigSetr_0; "CDtcConfig::SetRemoteDtc"
0x180049ff6  mov     [rbp+57h+var_70], rsi
0x180049ffa  mov     ecx, r15d
0x180049ffd  mov     [rbp+57h+var_60], rsi
0x18004a001  mov     r9d, 6FBh
0x18004a007  mov     [rbp+57h+var_58], rsi
0x18004a00b  mov     r8, r14
0x18004a00e  mov     [rbp+57h+var_48], rsi
0x18004a012  lea     edx, [rsi+6]
0x18004a015  mov     [rbp+57h+var_78], esi
0x18004a018  movups  [rbp+57h+var_38], xmm0
0x18004a01c  mov     [rbp+57h+var_50], esi
0x18004a01f  mov     [rsp+0C0h+var_A0], r12
0x18004a024  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004a029  mov     rcx, [rbx+10h]
0x18004a02d  lea     r8, [rbp+57h+var_80]
0x18004a031  lea     rdx, IID_IContactPool
0x18004a038  mov     rax, [rcx]
0x18004a03b  mov     rax, [rax+88h]
0x18004a042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a047  mov     ebx, eax
0x18004a049  test    eax, eax
0x18004a04b  jns     short loc_18004A05F
0x18004a04d  lea     rax, aGetcontactpool_0; "GetContactPool"
0x18004a054  mov     r9d, 701h
0x18004a05a  jmp     loc_18004A4D3
0x18004a05f  mov     rcx, [rbp+57h+var_80]
0x18004a063  lea     rdx, [rbp+57h+var_70]
0x18004a067  mov     [rsp+0C0h+var_A0], rdx
0x18004a06c  lea     r9, IID_IProperties
0x18004a073  lea     r8, aMsdtc; "MSDTC"
0x18004a07a  xor     edx, edx
0x18004a07c  mov     rax, [rcx]
0x18004a07f  mov     rax, [rax+20h]
0x18004a083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a088  mov     ebx, eax
0x18004a08a  test    eax, eax
0x18004a08c  jns     short loc_18004A0A0
0x18004a08e  lea     rax, aGetbyidentityw_0; "GetByIdentityW (MSDTC)"
0x18004a095  mov     r9d, 711h
0x18004a09b  jmp     loc_18004A4D3
0x18004a0a0  mov     rcx, [rbp+57h+var_80]
0x18004a0a4  lea     rdx, [rbp+57h+var_60]
0x18004a0a8  mov     [rsp+0C0h+var_A0], rdx
0x18004a0ad  lea     r9, IID_IProperties
0x18004a0b4  lea     r8, aMsdtcxatm; "MSDTCXATM"
0x18004a0bb  xor     edx, edx
0x18004a0bd  mov     rax, [rcx]
0x18004a0c0  mov     rax, [rax+20h]
0x18004a0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0c9  mov     ebx, eax
0x18004a0cb  test    eax, eax
0x18004a0cd  jns     short loc_18004A0E1
0x18004a0cf  lea     rax, aGetbyidentityw_1; "GetByIdentityW (MSDTCXATM)"
0x18004a0d6  mov     r9d, 71Ch
0x18004a0dc  jmp     loc_18004A4D3
0x18004a0e1  mov     rcx, [rbp+57h+var_80]
0x18004a0e5  lea     rdx, [rbp+57h+var_58]
0x18004a0e9  mov     [rsp+0C0h+var_A0], rdx
0x18004a0ee  lea     r9, IID_IProperties
0x18004a0f5  lea     r8, aMsdtctipgw; "MSDTCTIPGW"
0x18004a0fc  xor     edx, edx
0x18004a0fe  mov     rax, [rcx]
0x18004a101  mov     rax, [rax+20h]
0x18004a105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a10a  mov     ebx, eax
0x18004a10c  test    eax, eax
0x18004a10e  jns     short loc_18004A122
0x18004a110  lea     rax, aGetbyidentityw; "GetByIdentityW (TIPGW)"
0x18004a117  mov     r9d, 727h
0x18004a11d  jmp     loc_18004A4D3
0x18004a122  test    rdi, rdi
0x18004a125  jz      loc_18004A30A
0x18004a12b  lea     rax, aAboutToCopyRem; "About to copy remote proxy info"
0x18004a132  mov     r9d, 72Dh
0x18004a138  mov     [rsp+0C0h+var_90], rax
0x18004a13d  mov     r8, r14
0x18004a140  mov     [rsp+0C0h+var_98], rsi
0x18004a145  mov     edx, 4
0x18004a14a  mov     ecx, r15d
0x18004a14d  mov     [rsp+0C0h+var_A0], r12
0x18004a152  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004a157  lea     rdx, [rbp+57h+var_40]; struct ITmInstance **
0x18004a15b  mov     rcx, rdi; unsigned __int16 *
0x18004a15e  call    CreateTmInstanceForRemoteAdmin
0x18004a163  mov     ebx, eax
0x18004a165  test    eax, eax
0x18004a167  jns     short loc_18004A17B
0x18004a169  lea     rax, aCreatingRemote; "Creating 'remote' TM instance"
0x18004a170  mov     r9d, 733h
0x18004a176  jmp     loc_18004A4D3
0x18004a17b  mov     rcx, [rbp+57h+var_40]
0x18004a17f  lea     r8, [rbp+57h+var_68]
0x18004a183  lea     rdx, IID_IContactPool
0x18004a18a  mov     rax, [rcx]
0x18004a18d  mov     rax, [rax+88h]
0x18004a194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a199  mov     ebx, eax
0x18004a19b  test    eax, eax
0x18004a19d  jns     short loc_18004A1B1
0x18004a19f  lea     rax, aGetcontactpool; "GetContactPool (remote)"
0x18004a1a6  mov     r9d, 73Ch
0x18004a1ac  jmp     loc_18004A4D3
0x18004a1b1  mov     rcx, [rbp+57h+var_68]
0x18004a1b5  lea     rdx, [rbp+57h+var_48]
0x18004a1b9  mov     [rsp+0C0h+var_A0], rdx
0x18004a1be  lea     r9, IID_IProperties
0x18004a1c5  lea     r8, aMsdtc; "MSDTC"
0x18004a1cc  xor     edx, edx
0x18004a1ce  mov     rax, [rcx]
0x18004a1d1  mov     rax, [rax+20h]
0x18004a1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1da  mov     ebx, eax
0x18004a1dc  test    eax, eax
0x18004a1de  jns     short loc_18004A1F2
0x18004a1e0  lea     rax, aGetbyidentityw_0; "GetByIdentityW (MSDTC)"
0x18004a1e7  mov     r9d, 747h
0x18004a1ed  jmp     loc_18004A4D3
0x18004a1f2  mov     r8, [rbp+57h+var_48]; struct IProperties *
0x18004a1f6  lea     r9, [rbp+57h+var_50]; int *
0x18004a1fa  mov     rdx, [rbp+57h+var_70]; struct IProperties *
0x18004a1fe  call    ?IsPropertiesEqual@CDtcConfig@@AEAAJPEAUIProperties@@0PEAH@Z; CDtcConfig::IsPropertiesEqual(IProperties *,IProperties *,int *)
0x18004a203  mov     ebx, eax
0x18004a205  test    eax, eax
0x18004a207  jns     short loc_18004A21B
0x18004a209  lea     rax, aIspropertieseq; "IsPropertiesEqual failed!"
0x18004a210  mov     r9d, 750h
0x18004a216  jmp     loc_18004A4D3
0x18004a21b  cmp     [rbp+57h+var_50], esi
0x18004a21e  jnz     loc_18004A2D0
0x18004a224  mov     r8, [rbp+57h+var_80]; struct IContactPool *
0x18004a228  lea     r9, aMsdtcDefault; "MSDTC Default"
0x18004a22f  mov     rcx, [rbp+57h+var_68]; struct IContactPool *
0x18004a233  lea     rdx, aMsdtc; "MSDTC"
0x18004a23a  mov     [rsp+0C0h+var_A0], rdi; unsigned __int16 *
0x18004a23f  call    ?CopyAndConfigureContact@@YAJPEAUIContactPool@@PEBG011@Z; CopyAndConfigureContact(IContactPool *,ushort const *,IContactPool *,ushort const *,ushort const *)
0x18004a244  mov     ebx, eax
0x18004a246  test    eax, eax
0x18004a248  jns     short loc_18004A25C
0x18004a24a  lea     rax, aCopycontactDtc; "CopyContact (DTCTM)"
0x18004a251  mov     r9d, 75Dh
0x18004a257  jmp     loc_18004A4D3
0x18004a25c  mov     r8, [rbp+57h+var_80]; struct IContactPool *
0x18004a260  lea     r9, aMsdtcxatmDefau; "MSDTCXATM Default"
0x18004a267  mov     rcx, [rbp+57h+var_68]; struct IContactPool *
0x18004a26b  lea     rdx, aMsdtcxatm; "MSDTCXATM"
0x18004a272  mov     [rsp+0C0h+var_A0], rdi; unsigned __int16 *
0x18004a277  call    ?CopyAndConfigureContact@@YAJPEAUIContactPool@@PEBG011@Z; CopyAndConfigureContact(IContactPool *,ushort const *,IContactPool *,ushort const *,ushort const *)
0x18004a27c  mov     ebx, eax
0x18004a27e  test    eax, eax
0x18004a280  jns     short loc_18004A294
0x18004a282  lea     rax, aCopycontactXat; "CopyContact (XATM)"
0x18004a289  mov     r9d, 766h
0x18004a28f  jmp     loc_18004A4D3
0x18004a294  mov     r8, [rbp+57h+var_80]; struct IContactPool *
0x18004a298  lea     r9, aMsdtctipgwDefa; "MSDTCTIPGW Default"
0x18004a29f  mov     rcx, [rbp+57h+var_68]; struct IContactPool *
0x18004a2a3  lea     rdx, aMsdtctipgw; "MSDTCTIPGW"
0x18004a2aa  mov     [rsp+0C0h+var_A0], rdi; unsigned __int16 *
0x18004a2af  call    ?CopyAndConfigureContact@@YAJPEAUIContactPool@@PEBG011@Z; CopyAndConfigureContact(IContactPool *,ushort const *,IContactPool *,ushort const *,ushort const *)
0x18004a2b4  mov     ebx, eax
0x18004a2b6  test    eax, eax
0x18004a2b8  jns     loc_18004A4F1
0x18004a2be  lea     rax, aCopycontactTip; "CopyContact (TIPGW)"
0x18004a2c5  mov     r9d, 76Fh
0x18004a2cb  jmp     loc_18004A4D3
0x18004a2d0  mov     [rsp+0C0h+var_88], rdi
0x18004a2d5  lea     rax, aHostnameSResol; "HostName = %s resolves to local compute"...
0x18004a2dc  mov     [rsp+0C0h+var_90], rax
0x18004a2e1  mov     ebx, 8000FFFFh
0x18004a2e6  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18004a2ea  mov     r9d, 776h
0x18004a2f0  mov     r8, r14
0x18004a2f3  mov     [rsp+0C0h+var_A0], r12
0x18004a2f8  mov     edx, 1
0x18004a2fd  mov     ecx, r15d
0x18004a300  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004a305  jmp     loc_18004A4F1
0x18004a30a  mov     rdx, [rbp+57h+var_80]; struct IContactPool *
0x18004a30e  call    ?CleanDefaultContacts@CDtcConfig@@AEAAJPEAUIContactPool@@@Z; CDtcConfig::CleanDefaultContacts(IContactPool *)
0x18004a313  mov     ebx, eax
0x18004a315  test    eax, eax
0x18004a317  jns     short loc_18004A32B
0x18004a319  lea     rax, aCleandefaultco; "CleanDefaultContacts failed."
0x18004a320  mov     r9d, 77Fh
0x18004a326  jmp     loc_18004A4D3
0x18004a32b  mov     rcx, [rbp+57h+var_70]
0x18004a32f  lea     r8, [rbp+57h+var_78]
0x18004a333  lea     rdx, [rbp+57h+var_38]
0x18004a337  mov     rax, [rcx]
0x18004a33a  mov     rax, [rax+70h]
0x18004a33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a343  mov     ebx, eax
0x18004a345  test    eax, eax
0x18004a347  jns     short loc_18004A35B
0x18004a349  lea     rax, aGetserviceidMs; "GetServiceId (MSDTC)"
0x18004a350  mov     r9d, 786h
0x18004a356  jmp     loc_18004A4D3
0x18004a35b  mov     rcx, [rbp+57h+var_70]
0x18004a35f  lea     rdx, [rbp+57h+var_38]
0x18004a363  mov     r8d, 1
0x18004a369  mov     rax, [rcx]
0x18004a36c  mov     rax, [rax+78h]
0x18004a370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a375  mov     ebx, eax
0x18004a377  test    eax, eax
0x18004a379  jns     short loc_18004A38D
0x18004a37b  lea     rax, aSetserviceidMs; "SetServiceId (MSDTC)"
0x18004a382  mov     r9d, 78Dh
0x18004a388  jmp     loc_18004A4D3
0x18004a38d  mov     rcx, [rbp+57h+var_80]
0x18004a391  xor     r8d, r8d
0x18004a394  mov     rdx, [rbp+57h+var_70]
0x18004a398  mov     rax, [rcx]
0x18004a39b  mov     rax, [rax+40h]
0x18004a39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3a4  mov     ebx, eax
0x18004a3a6  test    eax, eax
0x18004a3a8  jns     short loc_18004A3BC
0x18004a3aa  lea     rax, aWritewMsdtc; "WriteW (MSDTC)"
0x18004a3b1  mov     r9d, 794h
0x18004a3b7  jmp     loc_18004A4D3
0x18004a3bc  mov     rcx, [rbp+57h+var_60]
0x18004a3c0  lea     r8, [rbp+57h+var_78]
0x18004a3c4  lea     rdx, [rbp+57h+var_38]
0x18004a3c8  mov     rax, [rcx]
0x18004a3cb  mov     rax, [rax+70h]
0x18004a3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3d4  mov     ebx, eax
0x18004a3d6  test    eax, eax
0x18004a3d8  jns     short loc_18004A3EC
0x18004a3da  lea     rax, aGetserviceidMs_0; "GetServiceId (MSDTCXATM)"
0x18004a3e1  mov     r9d, 79Bh
0x18004a3e7  jmp     loc_18004A4D3
0x18004a3ec  mov     rcx, [rbp+57h+var_60]
0x18004a3f0  lea     rdx, [rbp+57h+var_38]
0x18004a3f4  mov     r8d, 1
0x18004a3fa  mov     rax, [rcx]
0x18004a3fd  mov     rax, [rax+78h]
0x18004a401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a406  mov     ebx, eax
0x18004a408  test    eax, eax
0x18004a40a  jns     short loc_18004A41E
0x18004a40c  lea     rax, aSetserviceidMs_0; "SetServiceId (MSDTCXATM)"
0x18004a413  mov     r9d, 7A2h
0x18004a419  jmp     loc_18004A4D3
0x18004a41e  mov     rcx, [rbp+57h+var_80]
0x18004a422  xor     r8d, r8d
0x18004a425  mov     rdx, [rbp+57h+var_60]
0x18004a429  mov     rax, [rcx]
0x18004a42c  mov     rax, [rax+40h]
0x18004a430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a435  mov     ebx, eax
0x18004a437  test    eax, eax
0x18004a439  jns     short loc_18004A44D
0x18004a43b  lea     rax, aWritewMsdtcxat; "WriteW (MSDTCXATM)"
0x18004a442  mov     r9d, 7A9h
0x18004a448  jmp     loc_18004A4D3
0x18004a44d  mov     rcx, [rbp+57h+var_58]
0x18004a451  lea     r8, [rbp+57h+var_78]
0x18004a455  lea     rdx, [rbp+57h+var_38]
0x18004a459  mov     rax, [rcx]
0x18004a45c  mov     rax, [rax+70h]
0x18004a460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a465  mov     ebx, eax
0x18004a467  test    eax, eax
0x18004a469  jns     short loc_18004A47A
0x18004a46b  lea     rax, aGetserviceidTi; "GetServiceId (TIPGW)"
0x18004a472  mov     r9d, 7AFh
0x18004a478  jmp     short loc_18004A4D3
0x18004a47a  mov     rcx, [rbp+57h+var_58]
0x18004a47e  lea     rdx, [rbp+57h+var_38]
0x18004a482  mov     r8d, 1
0x18004a488  mov     rax, [rcx]
0x18004a48b  mov     rax, [rax+78h]
0x18004a48f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
