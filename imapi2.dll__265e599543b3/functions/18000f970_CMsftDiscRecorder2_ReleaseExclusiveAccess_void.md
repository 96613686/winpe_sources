# CMsftDiscRecorder2::ReleaseExclusiveAccess(void)

- ea: `0x18000f970`
- end: `0x18000fc03`
- name: `?ReleaseExclusiveAccess@CMsftDiscRecorder2@@UEAAJXZ`
- size: `659`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180005100`
- `0x18000f970`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000fa98`
- `KERNEL32!CloseHandle` at `0x18000fa98`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::ReleaseExclusiveAccess(
        CMsftDiscRecorder2 *this,
        __int64 a2,
        const struct _GUID *a3)
{
  __int64 v3; // r9
  signed int v5; // edi
  unsigned int v6; // r9d
  __int64 v7; // r9
  __int64 *v9; // rcx
  __int64 v10; // rax
  void *v11; // rcx
  bool v12; // zf
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // [rsp+40h] [rbp-40h] BYREF
  __int128 v17; // [rsp+48h] [rbp-38h] BYREF
  __int128 v18; // [rsp+58h] [rbp-28h] BYREF
  __int16 v19; // [rsp+68h] [rbp-18h]

  v3 = *((unsigned int *)this + 60);
  if ( (v3 & 2) == 0 )
  {
    v5 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        173,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v3,
        -2147467259);
    }
LABEL_13:
    v11 = (void *)*((_QWORD *)this + 20);
    if ( v11 != (void *)-1LL )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 20) = -1;
      *((_BYTE *)this + 168) = 0;
    }
    if ( v5 < 0 )
      goto LABEL_33;
    v12 = *((_BYTE *)this + 169) == 0;
    *(_QWORD *)&v17 = 2;
    v16 = 0;
    if ( v12 )
    {
      DWORD1(v17) |= 2u;
      *((_BYTE *)this + 169) = 0;
    }
    v13 = CMsftDiscRecorder2::SaferDeviceIoControl(
            (CMsftDiscRecorder2 *)v11,
            *((void *const *)this + 11),
            0x2C05Cu,
            &v17,
            8u,
            0,
            0,
            &v16);
    v5 = v13;
    if ( v13 == -2147024809 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 2u )
      {
        v15 = 175;
LABEL_32:
        WPP_SF_(v14[22], v15, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
    }
    else
    {
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            176,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            (unsigned int)v13);
        }
        goto LABEL_33;
      }
      --*((_DWORD *)this + 59);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        v15 = 177;
        goto LABEL_32;
      }
    }
LABEL_33:
    if ( (v5 & 0x80FF0000) == 0x80AA0000 )
      Imapi2Utility::SetErrorDescription(v5, (__int64)&CLSID_MsftDiscRecorder2, a3);
    return (unsigned int)v5;
  }
  v6 = *((_DWORD *)this + 59);
  if ( v6 <= 1 )
  {
    v19 = 0;
    v9 = (__int64 *)((char *)this + 8);
    v5 = 0;
    v17 = 0;
    v10 = *v9;
    v18 = 0;
    (*(void (__fastcall **)(__int64 *, __int128 *, __int64, __int128 *, int))(v10 + 24))(v9, &v17, 6, &v18, 10);
    goto LABEL_13;
  }
  v7 = v6 - 1;
  *((_DWORD *)this + 59) = v7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 174, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp-18h+arg_8], rbx
0x18000f975  mov     [rsp-18h+arg_10], rdi
0x18000f97a  push    rbp
0x18000f97b  push    r12
0x18000f97d  push    r13
0x18000f97f  mov     rbp, rsp
0x18000f982  sub     rsp, 80h
0x18000f989  mov     rax, cs:__security_cookie
0x18000f990  xor     rax, rsp
0x18000f993  mov     [rbp+var_10], rax
0x18000f997  mov     r9d, [rcx+0F0h]
0x18000f99e  lea     r13, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000f9a5  lea     r12, WPP_GLOBAL_Control
0x18000f9ac  mov     rbx, rcx
0x18000f9af  test    r9b, 2
0x18000f9b3  jnz     short loc_18000FA01
0x18000f9b5  mov     edi, 80004005h
0x18000f9ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c1  cmp     rcx, r12
0x18000f9c4  jz      loc_18000FA8B
0x18000f9ca  test    byte ptr [rcx+0BCh], 4
0x18000f9d1  jz      loc_18000FA8B
0x18000f9d7  cmp     byte ptr [rcx+0B9h], 3
0x18000f9de  jb      loc_18000FA8B
0x18000f9e4  mov     rcx, [rcx+0B0h]
0x18000f9eb  mov     edx, 0ADh
0x18000f9f0  mov     r8, r13
0x18000f9f3  mov     [rsp+80h+var_60], edi
0x18000f9f7  call    WPP_SF_Dd
0x18000f9fc  jmp     loc_18000FA8B
0x18000fa01  mov     r9d, [rcx+0ECh]
0x18000fa08  cmp     r9d, 1
0x18000fa0c  jbe     short loc_18000FA51
0x18000fa0e  dec     r9d
0x18000fa11  mov     [rcx+0ECh], r9d
0x18000fa18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa1f  cmp     rcx, r12
0x18000fa22  jz      short loc_18000FA4A
0x18000fa24  test    byte ptr [rcx+0BCh], 4
0x18000fa2b  jz      short loc_18000FA4A
0x18000fa2d  cmp     byte ptr [rcx+0B9h], 3
0x18000fa34  jb      short loc_18000FA4A
0x18000fa36  mov     rcx, [rcx+0B0h]
0x18000fa3d  mov     edx, 0AEh
0x18000fa42  mov     r8, r13
0x18000fa45  call    WPP_SF_d
0x18000fa4a  xor     eax, eax
0x18000fa4c  jmp     loc_18000FBDE
0x18000fa51  xor     eax, eax
0x18000fa53  mov     [rsp+80h+var_60], 0Ah
0x18000fa5b  mov     [rbp+var_18], ax
0x18000fa5f  lea     r9, [rbp+var_28]
0x18000fa63  add     rcx, 8
0x18000fa67  lea     rdx, [rbp+var_38]
0x18000fa6b  xor     edi, edi
0x18000fa6d  xorps   xmm0, xmm0
0x18000fa70  xorps   xmm1, xmm1
0x18000fa73  movups  [rbp+var_38], xmm0
0x18000fa77  mov     rax, [rcx]
0x18000fa7a  lea     r8d, [rdi+6]
0x18000fa7e  movups  [rbp+var_28], xmm1
0x18000fa82  mov     rax, [rax+18h]
0x18000fa86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa8b  mov     rcx, [rbx+0A0h]; hObject
0x18000fa92  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fa96  jz      short loc_18000FAB0
0x18000fa98  call    cs:__imp_CloseHandle
0x18000fa9e  mov     qword ptr [rbx+0A0h], 0FFFFFFFFFFFFFFFFh
0x18000faa9  mov     byte ptr [rbx+0A8h], 0
0x18000fab0  test    edi, edi
0x18000fab2  js      loc_18000FBC0
0x18000fab8  cmp     byte ptr [rbx+0A9h], 0
0x18000fabf  mov     qword ptr [rbp+var_38], 0
0x18000fac7  mov     dword ptr [rbp+var_38], 2
0x18000face  mov     [rbp+var_40], 0
0x18000fad5  jnz     short loc_18000FAE2
0x18000fad7  or      dword ptr [rbp+var_38+4], 2
0x18000fadb  mov     byte ptr [rbx+0A9h], 0
0x18000fae2  mov     rdx, [rbx+58h]; void *
0x18000fae6  lea     rax, [rbp+var_40]
0x18000faea  mov     [rsp+80h+var_48], rax; unsigned int *
0x18000faef  lea     r9, [rbp+var_38]; void *
0x18000faf3  mov     [rsp+80h+var_50], 0; unsigned int
0x18000fafb  mov     r8d, 2C05Ch; unsigned int
0x18000fb01  mov     [rsp+80h+var_58], 0; void *
0x18000fb0a  mov     [rsp+80h+var_60], 8; unsigned int
0x18000fb12  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x18000fb17  mov     edi, eax
0x18000fb19  cmp     eax, 80070057h
0x18000fb1e  jnz     short loc_18000FB4D
0x18000fb20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb27  cmp     rcx, r12
0x18000fb2a  jz      loc_18000FBC0
0x18000fb30  test    byte ptr [rcx+0BCh], 4
0x18000fb37  jz      loc_18000FBC0
0x18000fb3d  cmp     byte ptr [rcx+0B9h], 2
0x18000fb44  jb      short loc_18000FBC0
0x18000fb46  mov     edx, 0AFh
0x18000fb4b  jmp     short loc_18000FBB1
0x18000fb4d  test    eax, eax
0x18000fb4f  jns     short loc_18000FB88
0x18000fb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb58  cmp     rcx, r12
0x18000fb5b  jz      short loc_18000FBC0
0x18000fb5d  test    byte ptr [rcx+0BCh], 4
0x18000fb64  jz      short loc_18000FBC0
0x18000fb66  cmp     byte ptr [rcx+0B9h], 2
0x18000fb6d  jb      short loc_18000FBC0
0x18000fb6f  mov     rcx, [rcx+0B0h]
0x18000fb76  mov     edx, 0B0h
0x18000fb7b  mov     r9d, eax
0x18000fb7e  mov     r8, r13
0x18000fb81  call    WPP_SF_d
0x18000fb86  jmp     short loc_18000FBC0
0x18000fb88  dec     dword ptr [rbx+0ECh]
0x18000fb8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb95  cmp     rcx, r12
0x18000fb98  jz      short loc_18000FBC0
0x18000fb9a  test    byte ptr [rcx+0BCh], 4
0x18000fba1  jz      short loc_18000FBC0
0x18000fba3  cmp     byte ptr [rcx+0B9h], 3
0x18000fbaa  jb      short loc_18000FBC0
0x18000fbac  mov     edx, 0B1h
0x18000fbb1  mov     rcx, [rcx+0B0h]
0x18000fbb8  mov     r8, r13
0x18000fbbb  call    WPP_SF_
0x18000fbc0  mov     eax, edi
0x18000fbc2  and     eax, 80FF0000h
0x18000fbc7  cmp     eax, 80AA0000h
0x18000fbcc  jnz     short loc_18000FBDC
0x18000fbce  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18000fbd5  mov     ecx, edi; dwMessageId
0x18000fbd7  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18000fbdc  mov     eax, edi
0x18000fbde  mov     rcx, [rbp+var_10]
0x18000fbe2  xor     rcx, rsp; StackCookie
0x18000fbe5  call    __security_check_cookie
0x18000fbea  lea     r11, [rsp+80h+var_s0]
0x18000fbf2  mov     rbx, [r11+28h]
0x18000fbf6  mov     rdi, [r11+30h]
0x18000fbfa  mov     rsp, r11
0x18000fbfd  pop     r13
0x18000fbff  pop     r12
0x18000fc01  pop     rbp
0x18000fc02  retn
```
