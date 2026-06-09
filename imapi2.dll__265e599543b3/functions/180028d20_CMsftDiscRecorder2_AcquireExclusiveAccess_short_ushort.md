# CMsftDiscRecorder2::AcquireExclusiveAccess(short,ushort *)

- ea: `0x180028d20`
- end: `0x180029273`
- name: `?AcquireExclusiveAccess@CMsftDiscRecorder2@@UEAAJFPEAG@Z`
- size: `1363`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, __int16, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180005100`
- `0x18000908c`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180028d20`
- `0x18002abd4`
- `0x1800427fc`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180029097`
- `OLEAUT32!__imp_SysStringLen` at `0x180029097`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::AcquireExclusiveAccess(
        CMsftDiscRecorder2 *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v3; // r9
  __int16 v4; // r12
  signed int v6; // ebx
  const struct _GUID *v7; // r8
  int v8; // eax
  __int64 v9; // r9
  int VolumeHandle; // eax
  CMsftDiscRecorder2 *v12; // rcx
  void **v13; // rdx
  int v14; // eax
  CMsftDiscRecorder2 *v15; // rcx
  int v16; // eax
  CMsftDiscRecorder2 *v17; // rcx
  int v18; // eax
  int v19; // eax
  BSTR v20; // rbx
  UINT v21; // eax
  CMsftDiscRecorder2 *v22; // rcx
  UINT i; // r8d
  __int64 v24; // rdx
  int v25; // eax
  void *v26; // rdx
  __int64 v27; // rax
  void (__fastcall *v28)(char *, BSTR *, __int64, __int128 *, int); // rax
  void *v29; // rax
  unsigned __int8 v30[4]; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-55h] BYREF
  void *v32; // [rsp+48h] [rbp-51h] BYREF
  BSTR pbstr[2]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v34; // [rsp+60h] [rbp-39h] BYREF
  __int16 v35; // [rsp+70h] [rbp-29h]
  int v36; // [rsp+80h] [rbp-19h] BYREF
  int v37; // [rsp+84h] [rbp-15h]
  _BYTE v38[72]; // [rsp+88h] [rbp-11h]

  v3 = *((unsigned int *)this + 60);
  v32 = (void *)-1LL;
  pbstr[0] = a3;
  v4 = (__int16)a2;
  v30[0] = 0;
  if ( (v3 & 2) == 0 )
  {
    v6 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        164,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v3,
        -2147467259);
    }
    return (unsigned int)v6;
  }
  if ( !Imapi2Utility::BstrIsValidClientName((Imapi2Utility *)a3, a2) )
  {
    v6 = -1062600175;
    goto LABEL_62;
  }
  v8 = *((_DWORD *)this + 59);
  if ( !v8 )
  {
    VolumeHandle = CMsftDiscRecorder2::GetVolumeHandle(this, &v32, v30);
    v13 = 0;
    v6 = VolumeHandle;
    if ( VolumeHandle >= 0 )
    {
      v31 = 0;
      v14 = CMsftDiscRecorder2::SaferDeviceIoControl(v12, v32, 0x90018u, 0, 0, 0, 0, &v31);
      v13 = 0;
      v6 = v14;
      if ( v14 >= 0 )
      {
        *((_BYTE *)this + 168) = 1;
      }
      else
      {
        v15 = (CMsftDiscRecorder2 *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            166,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            (unsigned int)v14);
          v15 = (CMsftDiscRecorder2 *)WPP_GLOBAL_Control;
          v13 = 0;
        }
        if ( !v4 )
          goto LABEL_30;
      }
      v31 = 0;
      v16 = CMsftDiscRecorder2::SaferDeviceIoControl(v15, v32, 0x90028u, 0, 0, 0, 0, &v31);
      v13 = 0;
      if ( v16 < 0 )
      {
        v15 = (CMsftDiscRecorder2 *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            168,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            (unsigned int)v16);
          v15 = (CMsftDiscRecorder2 *)WPP_GLOBAL_Control;
          v13 = 0;
        }
        if ( v6 >= 0 )
          goto LABEL_47;
        goto LABEL_30;
      }
      v31 = 0;
      v18 = CMsftDiscRecorder2::SaferDeviceIoControl(v17, v32, 0x90020u, 0, 0, 0, 0, &v31);
      v13 = 0;
      v6 = v18;
      if ( v18 >= 0 )
        goto LABEL_47;
      v15 = (CMsftDiscRecorder2 *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
      {
LABEL_30:
        if ( v30[0] )
        {
          if ( v15 != (CMsftDiscRecorder2 *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v15 + 188) & 4) != 0
            && *((_BYTE *)v15 + 185) >= 3u )
          {
            WPP_SF_(*((_QWORD *)v15 + 22), 169, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
          }
          goto LABEL_47;
        }
        if ( !v4 )
        {
LABEL_46:
          if ( v6 < 0 )
            goto LABEL_60;
          goto LABEL_47;
        }
        if ( v15 != (CMsftDiscRecorder2 *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v15 + 188) & 4) != 0
          && *((_BYTE *)v15 + 185) >= 3u )
        {
          v6 = 0;
          WPP_SF_(*((_QWORD *)v15 + 22), 170, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
          v13 = 0;
          goto LABEL_46;
        }
LABEL_47:
        v31 = 0;
        memset_0(&v36, 0, 0x48u);
        v19 = v37;
        v20 = pbstr[0];
        v36 = 1;
        if ( v4 )
          v19 = 1;
        v37 = v19;
        v21 = SysStringLen(pbstr[0]);
        for ( i = 0; i < v21; v38[v24] = (_BYTE)v22 )
        {
          v24 = i;
          v22 = (CMsftDiscRecorder2 *)(2 * i);
          LOBYTE(v22) = *((_BYTE *)v20 + (_QWORD)v22);
          ++i;
        }
        v25 = CMsftDiscRecorder2::SaferDeviceIoControl(
                v22,
                *((void *const *)this + 11),
                0x2C05Cu,
                &v36,
                0x48u,
                0,
                0,
                &v31);
        v6 = v25;
        if ( v25 >= 0
          || v25 == -2147024874
          && !v4
          && *((_BYTE *)this + 168)
          && (v26 = (void *)*((_QWORD *)this + 11),
              v37 = 1,
              v6 = CMsftDiscRecorder2::SaferDeviceIoControl(0, v26, 0x2C05Cu, &v36, 0x48u, 0, 0, &v31),
              v6 >= 0) )
        {
          v35 = 0;
          v27 = *((_QWORD *)this + 1);
          *(_OWORD *)pbstr = 0;
          v28 = *(void (__fastcall **)(char *, BSTR *, __int64, __int128 *, int))(v27 + 24);
          v34 = 0;
          v28((char *)this + 8, pbstr, 6, &v34, 10);
          v29 = v32;
          ++*((_DWORD *)this + 59);
          *((_QWORD *)this + 20) = v29;
          *((_BYTE *)this + 169) = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 172, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
          }
LABEL_61:
          if ( (v6 & 0x80FF0000) != 0x80AA0000 )
            return (unsigned int)v6;
LABEL_62:
          Imapi2Utility::SetErrorDescription(v6, (__int64)&CLSID_MsftDiscRecorder2, v7);
          return (unsigned int)v6;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            171,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            (unsigned int)v6);
        }
LABEL_60:
        Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v32, v13);
        *((_BYTE *)this + 168) = 0;
        goto LABEL_61;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        167,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned int)v18);
      v13 = 0;
    }
    v15 = (CMsftDiscRecorder2 *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  v9 = (unsigned int)(v8 + 1);
  *((_DWORD *)this + 59) = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 165, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180028d20  mov     [rsp-8+arg_8], rbx
0x180028d25  mov     [rsp-8+arg_18], r12
0x180028d2a  push    rbp
0x180028d2b  push    r13
0x180028d2d  push    r14
0x180028d2f  lea     rbp, [rsp-47h]
0x180028d34  sub     rsp, 0E0h
0x180028d3b  mov     rax, cs:__security_cookie
0x180028d42  xor     rax, rsp
0x180028d45  mov     [rbp+57h+var_20], rax
0x180028d49  mov     r9d, [rcx+0F0h]
0x180028d50  xor     ebx, ebx
0x180028d52  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFFh
0x180028d5a  mov     rax, r8
0x180028d5d  mov     [rbp+57h+pbstr], rax
0x180028d61  movzx   r12d, dx
0x180028d65  mov     [rbp+57h+var_B0], bl
0x180028d68  mov     r13, rcx
0x180028d6b  test    r9b, 2
0x180028d6f  jnz     short loc_180028DC8
0x180028d71  mov     ebx, 80004005h
0x180028d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d7d  lea     r14, WPP_GLOBAL_Control
0x180028d84  cmp     rcx, r14
0x180028d87  jz      loc_1800291B1
0x180028d8d  test    byte ptr [rcx+0BCh], 4
0x180028d94  jz      loc_1800291B1
0x180028d9a  cmp     byte ptr [rcx+0B9h], 3
0x180028da1  jb      loc_1800291B1
0x180028da7  mov     rcx, [rcx+0B0h]
0x180028dae  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180028db5  mov     edx, 0A4h
0x180028dba  mov     [rsp+0F0h+var_D0], ebx
0x180028dbe  call    WPP_SF_Dd
0x180028dc3  jmp     loc_1800291B1
0x180028dc8  mov     rcx, rax; this
0x180028dcb  call    ?BstrIsValidClientName@Imapi2Utility@@YAEPEAG@Z; Imapi2Utility::BstrIsValidClientName(ushort *)
0x180028dd0  test    al, al
0x180028dd2  jnz     short loc_180028DDE
0x180028dd4  mov     ebx, 0C0AA0211h
0x180028dd9  jmp     loc_1800291A3
0x180028dde  mov     eax, [r13+0ECh]
0x180028de5  test    eax, eax
0x180028de7  jz      short loc_180028E38
0x180028de9  lea     r9d, [rax+1]
0x180028ded  mov     [r13+0ECh], r9d
0x180028df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dfb  lea     r14, WPP_GLOBAL_Control
0x180028e02  cmp     rcx, r14
0x180028e05  jz      short loc_180028E31
0x180028e07  test    byte ptr [rcx+0BCh], 4
0x180028e0e  jz      short loc_180028E31
0x180028e10  cmp     byte ptr [rcx+0B9h], 3
0x180028e17  jb      short loc_180028E31
0x180028e19  mov     rcx, [rcx+0B0h]
0x180028e20  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180028e27  mov     edx, 0A5h
0x180028e2c  call    WPP_SF_d
0x180028e31  xor     eax, eax
0x180028e33  jmp     loc_1800291B3
0x180028e38  lea     r8, [rbp+57h+var_B0]; unsigned __int8 *
0x180028e3c  mov     rcx, r13; this
0x180028e3f  lea     rdx, [rbp+57h+var_A8]; void **
0x180028e43  call    ?GetVolumeHandle@CMsftDiscRecorder2@@AEAAJAEAPEAXAEAE@Z; CMsftDiscRecorder2::GetVolumeHandle(void * &,uchar &)
0x180028e48  xor     edx, edx
0x180028e4a  lea     r14, WPP_GLOBAL_Control
0x180028e51  mov     ebx, eax
0x180028e53  test    eax, eax
0x180028e55  js      loc_180028F8B
0x180028e5b  lea     rax, [rbp+57h+var_AC]
0x180028e5f  mov     [rbp+57h+var_AC], edx
0x180028e62  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x180028e67  xor     r9d, r9d; void *
0x180028e6a  mov     [rsp+0F0h+var_C0], edx; unsigned int
0x180028e6e  mov     r8d, 90018h; unsigned int
0x180028e74  mov     [rsp+0F0h+var_C8], rdx; void *
0x180028e79  mov     [rsp+0F0h+var_D0], edx; unsigned int
0x180028e7d  mov     rdx, [rbp+57h+var_A8]; void *
0x180028e81  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180028e86  xor     edx, edx
0x180028e88  mov     ebx, eax
0x180028e8a  test    eax, eax
0x180028e8c  jns     short loc_180028EDC
0x180028e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e95  cmp     rcx, r14
0x180028e98  jz      short loc_180028ED0
0x180028e9a  test    byte ptr [rcx+0BCh], 4
0x180028ea1  jz      short loc_180028ED0
0x180028ea3  cmp     byte ptr [rcx+0B9h], 3
0x180028eaa  jb      short loc_180028ED0
0x180028eac  mov     rcx, [rcx+0B0h]
0x180028eb3  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180028eba  mov     edx, 0A6h
0x180028ebf  mov     r9d, eax
0x180028ec2  call    WPP_SF_d
0x180028ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ece  xor     edx, edx
0x180028ed0  test    r12w, r12w
0x180028ed4  jz      loc_180028F92
0x180028eda  jmp     short loc_180028EE4
0x180028edc  mov     byte ptr [r13+0A8h], 1
0x180028ee4  lea     rax, [rbp+57h+var_AC]
0x180028ee8  mov     [rbp+57h+var_AC], edx
0x180028eeb  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x180028ef0  xor     r9d, r9d; void *
0x180028ef3  mov     [rsp+0F0h+var_C0], edx; unsigned int
0x180028ef7  mov     r8d, 90028h; unsigned int
0x180028efd  mov     [rsp+0F0h+var_C8], rdx; void *
0x180028f02  mov     [rsp+0F0h+var_D0], edx; unsigned int
0x180028f06  mov     rdx, [rbp+57h+var_A8]; void *
0x180028f0a  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180028f0f  xor     edx, edx
0x180028f11  test    eax, eax
0x180028f13  js      loc_180028FDD
0x180028f19  lea     rax, [rbp+57h+var_AC]
0x180028f1d  mov     [rbp+57h+var_AC], edx
0x180028f20  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x180028f25  xor     r9d, r9d; void *
0x180028f28  mov     [rsp+0F0h+var_C0], edx; unsigned int
0x180028f2c  mov     r8d, 90020h; unsigned int
0x180028f32  mov     [rsp+0F0h+var_C8], rdx; void *
0x180028f37  mov     [rsp+0F0h+var_D0], edx; unsigned int
0x180028f3b  mov     rdx, [rbp+57h+var_A8]; void *
0x180028f3f  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180028f44  xor     edx, edx
0x180028f46  mov     ebx, eax
0x180028f48  test    eax, eax
0x180028f4a  jns     loc_180029069
0x180028f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f57  cmp     rcx, r14
0x180028f5a  jz      short loc_180028F92
0x180028f5c  test    byte ptr [rcx+0BCh], 4
0x180028f63  jz      short loc_180028F92
0x180028f65  cmp     byte ptr [rcx+0B9h], 3
0x180028f6c  jb      short loc_180028F92
0x180028f6e  mov     rcx, [rcx+0B0h]
0x180028f75  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180028f7c  mov     edx, 0A7h
0x180028f81  mov     r9d, eax
0x180028f84  call    WPP_SF_d
0x180028f89  xor     edx, edx
0x180028f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f92  cmp     [rbp+57h+var_B0], dl
0x180028f95  jz      loc_180029028
0x180028f9b  cmp     rcx, r14
0x180028f9e  jz      loc_180029069
0x180028fa4  test    byte ptr [rcx+0BCh], 4
0x180028fab  jz      loc_180029069
0x180028fb1  cmp     byte ptr [rcx+0B9h], 3
0x180028fb8  jb      loc_180029069
0x180028fbe  mov     rcx, [rcx+0B0h]
0x180028fc5  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180028fcc  mov     edx, 0A9h
0x180028fd1  call    WPP_SF_
0x180028fd6  xor     edx, edx
0x180028fd8  jmp     loc_180029069
0x180028fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fe4  cmp     rcx, r14
0x180028fe7  jz      short loc_18002901F
0x180028fe9  test    byte ptr [rcx+0BCh], 4
0x180028ff0  jz      short loc_18002901F
0x180028ff2  cmp     byte ptr [rcx+0B9h], 3
0x180028ff9  jb      short loc_18002901F
0x180028ffb  mov     rcx, [rcx+0B0h]
0x180029002  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029009  mov     edx, 0A8h
0x18002900e  mov     r9d, eax
0x180029011  call    WPP_SF_d
0x180029016  mov     rcx, cs:WPP_GLOBAL_Control
0x18002901d  xor     edx, edx
0x18002901f  test    ebx, ebx
0x180029021  jns     short loc_180029069
0x180029023  jmp     loc_180028F92
0x180029028  test    r12w, r12w
0x18002902c  jz      short loc_180029061
0x18002902e  cmp     rcx, r14
0x180029031  jz      short loc_180029069
0x180029033  test    byte ptr [rcx+0BCh], 4
0x18002903a  jz      short loc_180029069
0x18002903c  cmp     byte ptr [rcx+0B9h], 3
0x180029043  jb      short loc_180029069
0x180029045  mov     rcx, [rcx+0B0h]
0x18002904c  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029053  mov     ebx, edx
0x180029055  mov     edx, 0AAh
0x18002905a  call    WPP_SF_
0x18002905f  xor     edx, edx
0x180029061  test    ebx, ebx
0x180029063  js      loc_180029184
0x180029069  mov     [rbp+57h+var_AC], edx
0x18002906c  lea     rcx, [rbp+57h+var_70]; void *
0x180029070  xor     edx, edx; Val
0x180029072  lea     r8d, [rdx+48h]; Size
0x180029076  call    memset_0
0x18002907b  mov     eax, [rbp+57h+var_6C]
0x18002907e  mov     edx, 1
0x180029083  mov     rbx, [rbp+57h+pbstr]
0x180029087  test    r12w, r12w
0x18002908b  mov     rcx, rbx; pbstr
0x18002908e  mov     [rbp+57h+var_70], edx
0x180029091  cmovnz  eax, edx
0x180029094  mov     [rbp+57h+var_6C], eax
0x180029097  call    cs:__imp_SysStringLen
0x18002909d  xor     r9d, r9d
0x1800290a0  mov     r8d, r9d
0x1800290a3  test    eax, eax
0x1800290a5  jz      short loc_1800290BD
0x1800290a7  mov     edx, r8d
0x1800290aa  lea     ecx, [r8+r8]
0x1800290ae  mov     cl, [rcx+rbx]; this
0x1800290b1  inc     r8d
0x1800290b4  mov     [rbp+rdx+57h+var_68], cl
0x1800290b8  cmp     r8d, eax
0x1800290bb  jb      short loc_1800290A7
0x1800290bd  mov     rdx, [r13+58h]; void *
0x1800290c1  lea     rax, [rbp+57h+var_AC]
0x1800290c5  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x1800290ca  mov     r8d, 2C05Ch; unsigned int
0x1800290d0  mov     [rsp+0F0h+var_C0], r9d; unsigned int
0x1800290d5  mov     [rsp+0F0h+var_C8], r9; void *
0x1800290da  lea     r9, [rbp+57h+var_70]; void *
0x1800290de  mov     [rsp+0F0h+var_D0], 48h ; 'H'; unsigned int
0x1800290e6  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x1800290eb  xor     ecx, ecx; this
0x1800290ed  mov     ebx, eax
0x1800290ef  test    eax, eax
0x1800290f1  jns     loc_1800291D8
0x1800290f7  cmp     eax, 80070016h
0x1800290fc  jnz     short loc_18002914B
0x1800290fe  test    r12w, r12w
0x180029102  jnz     short loc_18002914B
0x180029104  cmp     [r13+0A8h], cl
0x18002910b  jz      short loc_18002914B
0x18002910d  mov     rdx, [r13+58h]; void *
0x180029111  lea     rax, [rbp+57h+var_AC]
0x180029115  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x18002911a  lea     r9, [rbp+57h+var_70]; void *
0x18002911e  mov     [rsp+0F0h+var_C0], ecx; unsigned int
0x180029122  mov     r8d, 2C05Ch; unsigned int
0x180029128  mov     [rsp+0F0h+var_C8], rcx; void *
0x18002912d  mov     [rsp+0F0h+var_D0], 48h ; 'H'; unsigned int
0x180029135  mov     [rbp+57h+var_6C], 1
0x18002913c  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180029141  mov     ebx, eax
0x180029143  test    eax, eax
0x180029145  jns     loc_1800291D8
0x18002914b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029152  cmp     rcx, r14
0x180029155  jz      short loc_180029184
0x180029157  test    byte ptr [rcx+0BCh], 4
0x18002915e  jz      short loc_180029184
0x180029160  cmp     byte ptr [rcx+0B9h], 3
0x180029167  jb      short loc_180029184
0x180029169  mov     rcx, [rcx+0B0h]
0x180029170  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029177  mov     edx, 0ABh
0x18002917c  mov     r9d, ebx
0x18002917f  call    WPP_SF_d
0x180029184  lea     rcx, [rbp+57h+var_A8]; this
0x180029188  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x18002918d  mov     byte ptr [r13+0A8h], 0
0x180029195  mov     eax, ebx
0x180029197  and     eax, 80FF0000h
0x18002919c  cmp     eax, 80AA0000h
0x1800291a1  jnz     short loc_1800291B1
0x1800291a3  lea     rdx, CLSID_MsftDiscRecorder2; int
0x1800291aa  mov     ecx, ebx; dwMessageId
0x1800291ac  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x1800291b1  mov     eax, ebx
0x1800291b3  mov     rcx, [rbp+57h+var_20]
0x1800291b7  xor     rcx, rsp; StackCookie
0x1800291ba  call    __security_check_cookie
0x1800291bf  lea     r11, [rsp+0F0h+var_10]
0x1800291c7  mov     rbx, [r11+28h]
0x1800291cb  mov     r12, [r11+38h]
0x1800291cf  mov     rsp, r11
0x1800291d2  pop     r14
0x1800291d4  pop     r13
0x1800291d6  pop     rbp
0x1800291d7  retn
0x1800291d8  xor     eax, eax
0x1800291da  mov     [rsp+0F0h+var_D0], 0Ah
0x1800291e2  mov     [rbp+57h+var_80], ax
0x1800291e6  lea     rcx, [r13+8]
0x1800291ea  mov     rax, [rcx]
0x1800291ed  lea     r9, [rbp+57h+var_90]
0x1800291f1  xorps   xmm0, xmm0
0x1800291f4  lea     rdx, [rbp+57h+pbstr]
0x1800291f8  xorps   xmm1, xmm1
0x1800291fb  mov     r8d, 6
0x180029201  movups  xmmword ptr [rbp+57h+pbstr], xmm0
0x180029205  mov     rax, [rax+18h]
0x180029209  movups  [rbp+57h+var_90], xmm1
0x18002920d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029212  mov     rax, [rbp+57h+var_A8]
0x180029216  inc     dword ptr [r13+0ECh]
0x18002921d  mov     [r13+0A0h], rax
0x180029224  mov     byte ptr [r13+0A9h], 0
0x18002922c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029233  cmp     rcx, r14
  ... truncated ...
```
