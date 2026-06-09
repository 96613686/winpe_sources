# SetDefaultDeviceProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,COLORPROFILETYPE,ushort const *,int)

- ea: `0x180042ccc`
- end: `0x18004308e`
- name: `?SetDefaultDeviceProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKW4COLORPROFILETYPE@@1H@Z`
- size: `962`
- prototype: `unsigned int(enum WCS_PROFILE_MANAGEMENT_SCOPE, const unsigned __int16 *, unsigned int, enum COLORPROFILETYPE, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18002435c`

## callees

- `0x18000b828`
- `0x18000be44`
- `0x18001b3a8`
- `0x180020750`
- `0x1800211e4`
- `0x1800212e0`
- `0x18002af3c`
- `0x18002e5f0`
- `0x18002f2dc`
- `0x18003e944`
- `0x180041bf0`
- `0x180042ccc`
- `0x18004344c`
- `0x18004364c`
- `0x18004b680`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004303f`
- `ntdll!EtwEventWrite` at `0x18004303f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f16`

## pseudocode

```c
__int64 __fastcall SetDefaultDeviceProfile(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        unsigned __int16 *a2,
        __int64 a3,
        enum COLORPROFILETYPE a4,
        const unsigned __int16 *Src,
        int a6)
{
  const unsigned __int16 *v6; // r15
  WCHAR *v8; // rdi
  DWORD AssociatedProfileList; // ebx
  unsigned int v10; // r8d
  enum WCS_PROFILE_MANAGEMENT_SCOPE v11; // r10d
  int v12; // r12d
  unsigned __int16 *v13; // r14
  unsigned int v14; // eax
  signed int LastError; // eax
  __int64 v16; // r13
  unsigned int v17; // r12d
  unsigned __int16 *v18; // rax
  enum COLORPROFILETYPE v19; // r13d
  unsigned __int16 *v20; // rax
  bool v21; // zf
  unsigned int DefaultDeviceProfile; // eax
  __int64 v23; // rax
  __int64 v24; // rcx
  int v25; // ecx
  int v26; // eax
  enum COLORPROFILETYPE v28; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-45h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v31; // [rsp+4Ch] [rbp-3Dh] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int64 v33; // [rsp+58h] [rbp-31h] BYREF
  const unsigned __int16 *v34; // [rsp+60h] [rbp-29h] BYREF
  int v35; // [rsp+68h] [rbp-21h]
  int v36; // [rsp+6Ch] [rbp-1Dh]
  unsigned __int16 *v37; // [rsp+70h] [rbp-19h]
  int v38; // [rsp+78h] [rbp-11h]
  int v39; // [rsp+7Ch] [rbp-Dh]
  enum WCS_PROFILE_MANAGEMENT_SCOPE *v40; // [rsp+80h] [rbp-9h]
  __int64 v41; // [rsp+88h] [rbp-1h]
  enum WCS_PROFILE_MANAGEMENT_SCOPE v42; // [rsp+E0h] [rbp+57h] BYREF

  v42 = a1;
  v6 = Src;
  v28 = a4;
  lpMem = 0;
  v30 = 0;
  v8 = 0;
  v31 = 0;
  v29 = 0;
  v33 = 0;
  if ( (unsigned int)a4 > CPT_GMMP )
    return 87;
  if ( (unsigned int)IsLegacyColorManagedShimAppliedOnDeviceClass(1936744803) )
    return 50;
  v12 = a6;
  v13 = 0;
  v14 = AddProfileToAssociatedProfileList(v11, a2, v10, v6, 0, 1, a6, (int *)&v29);
  AssociatedProfileList = v14;
  if ( !v14 || v14 == 183 )
  {
    AssociatedProfileList = GetAssociatedProfileList(v42, a2, 0x73706163u, 0, v12, (unsigned __int16 **)&lpMem, &v30);
    if ( AssociatedProfileList )
    {
      v8 = (WCHAR *)lpMem;
      goto LABEL_50;
    }
    LastError = StringCbLengthW(v6, 0x208u, &v33);
    v8 = (WCHAR *)lpMem;
    if ( LastError < 0 )
    {
      if ( (LastError & 0x1FFF0000) == 0x70000 )
      {
        AssociatedProfileList = (unsigned __int16)LastError;
        goto LABEL_35;
      }
      goto LABEL_23;
    }
    v16 = (unsigned int)(v33 + 2);
    if ( lpMem )
    {
      v17 = v30;
      if ( v30 > 0x7FFFFEFA || (v18 = (unsigned __int16 *)MemAlloc(v16 + 2LL * v30), (v13 = v18) == 0) )
      {
        AssociatedProfileList = 8;
        goto LABEL_50;
      }
      v19 = v28;
      if ( !(unsigned int)SetLastStringInMultiSz(v8, v17, v28, v6, &v31, v18)
        || (v12 = a6, !(unsigned int)SetDeviceData(v42, a2, v13, 2 * v31)) )
      {
        AssociatedProfileList = GetLastError();
        goto LABEL_35;
      }
    }
    else
    {
      v20 = (unsigned __int16 *)MemAlloc((unsigned int)v16 + 2LL);
      v13 = v20;
      if ( !v20 )
        return 8;
      memcpy_0(v20, v6, (unsigned int)v16);
      *(unsigned __int16 *)((char *)v13 + v16) = 0;
      if ( !(unsigned int)SetDeviceData(v42, a2, v13, (int)v16 + 2) )
        goto LABEL_22;
      v19 = v28;
    }
    if ( (unsigned int)v19 > CPT_DMP )
      goto LABEL_39;
    v28 = CPT_ICC;
    if ( (unsigned int)InternalGetUsePerUserProfiles(a2, 0x73706163u, (int *)&v28) )
    {
      if ( v28 )
        v21 = v42 == WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER;
      else
        v21 = v42 == WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE;
      if ( v21 )
      {
LABEL_34:
        InternalRefreshCalibration(a2, 0);
        NotifyOfPossibleColorProfileChange();
        goto LABEL_35;
      }
      if ( v28 )
      {
        v29 = 0;
        DefaultDeviceProfile = GetDefaultDeviceProfile(
                                 WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER,
                                 a2,
                                 0x6D6E7472u,
                                 CPT_DMP,
                                 v12,
                                 0,
                                 &v29);
        AssociatedProfileList = DefaultDeviceProfile;
        if ( DefaultDeviceProfile != 2 )
        {
          if ( DefaultDeviceProfile )
            goto LABEL_50;
          goto LABEL_35;
        }
        AssociatedProfileList = 0;
        goto LABEL_34;
      }
LABEL_39:
      v23 = -1;
      if ( v6 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v6[v24] );
        v25 = 2 * v24 + 2;
      }
      else
      {
        v25 = 0;
      }
      v34 = v6;
      v35 = v25;
      v36 = 0;
      if ( a2 )
      {
        do
          ++v23;
        while ( a2[v23] );
        v26 = 2 * v23 + 2;
      }
      else
      {
        v26 = 0;
      }
      v38 = v26;
      v37 = a2;
      v40 = &v42;
      v39 = 0;
      v41 = 4;
      EtwEventWrite(g_etwHandle, SET_DEFAULT_DEVICE_PROFILE, 3, &v34);
      goto LABEL_50;
    }
LABEL_22:
    LastError = GetLastError();
LABEL_23:
    AssociatedProfileList = LastError;
  }
LABEL_35:
  if ( !AssociatedProfileList )
    goto LABEL_39;
LABEL_50:
  if ( v8 )
    MemFree(v8);
  if ( v13 )
    MemFree(v13);
  return AssociatedProfileList;
}

```

## disassembly

```asm
0x180042ccc  mov     [rsp-8+arg_10], rbx
0x180042cd1  mov     [rsp-8+arg_0], ecx
0x180042cd5  push    rbp
0x180042cd6  push    rsi
0x180042cd7  push    rdi
0x180042cd8  push    r12
0x180042cda  push    r13
0x180042cdc  push    r14
0x180042cde  push    r15
0x180042ce0  lea     rbp, [rsp-17h]
0x180042ce5  sub     rsp, 0A0h
0x180042cec  mov     rax, cs:__security_cookie
0x180042cf3  xor     rax, rsp
0x180042cf6  mov     [rbp+47h+var_40], rax
0x180042cfa  mov     r15, [rbp+47h+Src]
0x180042cfe  xor     r13d, r13d
0x180042d01  mov     [rbp+47h+var_90], r9d
0x180042d05  mov     rsi, rdx
0x180042d08  mov     [rbp+47h+lpMem], r13
0x180042d0c  mov     r10d, ecx
0x180042d0f  mov     [rbp+47h+var_88], r13d
0x180042d13  mov     edi, r13d
0x180042d16  mov     [rbp+47h+var_84], r13d
0x180042d1a  mov     [rbp+47h+var_8C], r13d
0x180042d1e  mov     [rbp+47h+var_78], r13
0x180042d22  cmp     r9d, 3
0x180042d26  jbe     short loc_180042D31
0x180042d28  lea     ebx, [r13+57h]
0x180042d2c  jmp     loc_180043065
0x180042d31  mov     r8d, 73706163h
0x180042d37  mov     ecx, r8d
0x180042d3a  call    IsLegacyColorManagedShimAppliedOnDeviceClass
0x180042d3f  test    eax, eax
0x180042d41  jz      short loc_180042D4D
0x180042d43  mov     ebx, 32h ; '2'
0x180042d48  jmp     loc_180043065
0x180042d4d  mov     r12d, [rbp+47h+arg_28]
0x180042d51  lea     rax, [rbp+47h+var_8C]
0x180042d55  mov     [rsp+0D0h+var_98], rax; int *
0x180042d5a  mov     r9, r15; unsigned __int16 *
0x180042d5d  mov     dword ptr [rsp+0D0h+var_A0], r12d; int
0x180042d62  mov     rdx, rsi; unsigned __int16 *
0x180042d65  mov     dword ptr [rsp+0D0h+var_A8], 1; int
0x180042d6d  mov     ecx, r10d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180042d70  mov     [rsp+0D0h+var_B0], r13; unsigned int *
0x180042d75  mov     r14, r13
0x180042d78  call    ?AddProfileToAssociatedProfileList@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGK1PEBKHHPEAH@Z; AddProfileToAssociatedProfileList(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,ushort const *,ulong const *,int,int,int *)
0x180042d7d  mov     ebx, eax
0x180042d7f  test    eax, eax
0x180042d81  jz      short loc_180042D8E
0x180042d83  cmp     eax, 0B7h
0x180042d88  jnz     loc_180042FAB
0x180042d8e  mov     ecx, [rbp+47h+arg_0]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180042d91  lea     rax, [rbp+47h+var_88]
0x180042d95  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x180042d9a  xor     r9d, r9d; int
0x180042d9d  lea     rax, [rbp+47h+lpMem]
0x180042da1  mov     r8d, 73706163h; unsigned int
0x180042da7  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180042dac  mov     rdx, rsi; unsigned __int16 *
0x180042daf  mov     dword ptr [rsp+0D0h+var_B0], r12d; int
0x180042db4  call    ?GetAssociatedProfileList@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKHHPEAPEAGPEAK@Z; GetAssociatedProfileList(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int,int,ushort * *,ulong *)
0x180042db9  mov     ebx, eax
0x180042dbb  test    eax, eax
0x180042dbd  jnz     loc_180043047
0x180042dc3  lea     r8, [rbp+47h+var_78]; unsigned __int64 *
0x180042dc7  mov     edx, 208h; unsigned __int64
0x180042dcc  mov     rcx, r15; unsigned __int16 *
0x180042dcf  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180042dd4  mov     rdi, [rbp+47h+lpMem]
0x180042dd8  test    eax, eax
0x180042dda  jns     short loc_180042DF8
0x180042ddc  mov     ecx, eax
0x180042dde  and     ecx, 1FFF0000h
0x180042de4  cmp     ecx, 70000h
0x180042dea  jnz     loc_180042F1C
0x180042df0  movzx   ebx, ax
0x180042df3  jmp     loc_180042FAB
0x180042df8  mov     r13d, dword ptr [rbp+47h+var_78]
0x180042dfc  add     r13d, 2
0x180042e00  test    rdi, rdi
0x180042e03  jz      loc_180042EB0
0x180042e09  mov     r12d, [rbp+47h+var_88]
0x180042e0d  cmp     r12d, 7FFFFEFAh
0x180042e14  ja      loc_180042EA6
0x180042e1a  lea     rcx, ds:0[r12*2]
0x180042e22  add     rcx, r13
0x180042e25  call    MemAlloc
0x180042e2a  mov     r14, rax
0x180042e2d  test    rax, rax
0x180042e30  jz      short loc_180042EA6
0x180042e32  mov     r13d, [rbp+47h+var_90]
0x180042e36  mov     r9, r15; unsigned __int16 *
0x180042e39  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 *
0x180042e3e  mov     r8d, r13d; enum COLORPROFILETYPE
0x180042e41  lea     rax, [rbp+47h+var_84]
0x180042e45  mov     edx, r12d; unsigned int
0x180042e48  mov     rcx, rdi; lpString1
0x180042e4b  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x180042e50  call    ?SetLastStringInMultiSz@@YAHPEBGKW4COLORPROFILETYPE@@0PEAKPEAG@Z; SetLastStringInMultiSz(ushort const *,ulong,COLORPROFILETYPE,ushort const *,ulong *,ushort *)
0x180042e55  test    eax, eax
0x180042e57  jnz     short loc_180042E69
0x180042e59  call    cs:__imp_GetLastError
0x180042e5f  mov     ebx, eax
0x180042e61  xor     r13d, r13d
0x180042e64  jmp     loc_180042FAB
0x180042e69  mov     eax, [rbp+47h+var_84]
0x180042e6c  mov     r8d, 73706163h
0x180042e72  mov     r12d, [rbp+47h+arg_28]
0x180042e76  mov     rdx, rsi; unsigned __int16 *
0x180042e79  lea     ecx, [rax+rax]
0x180042e7c  mov     eax, r12d
0x180042e7f  mov     dword ptr [rsp+0D0h+var_A8], ecx; unsigned int
0x180042e83  neg     eax
0x180042e85  mov     ecx, [rbp+47h+arg_0]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180042e88  sbb     r9d, r9d
0x180042e8b  mov     [rsp+0D0h+var_B0], r14; void *
0x180042e90  and     r9d, 4
0x180042e94  inc     r9d
0x180042e97  call    SetDeviceData
0x180042e9c  test    eax, eax
0x180042e9e  jnz     loc_180042F27
0x180042ea4  jmp     short loc_180042E59
0x180042ea6  mov     ebx, 8
0x180042eab  jmp     loc_18004304B
0x180042eb0  mov     ecx, r13d
0x180042eb3  add     rcx, 2
0x180042eb7  call    MemAlloc
0x180042ebc  mov     r14, rax
0x180042ebf  test    rax, rax
0x180042ec2  jnz     short loc_180042ECC
0x180042ec4  lea     ebx, [rax+8]
0x180042ec7  jmp     loc_180043065
0x180042ecc  mov     r8d, r13d; Size
0x180042ecf  mov     rdx, r15; Src
0x180042ed2  mov     rcx, r14; void *
0x180042ed5  call    memcpy_0
0x180042eda  xor     eax, eax
0x180042edc  lea     ecx, [r13+2]
0x180042ee0  mov     [r13+r14+0], ax
0x180042ee6  mov     r8d, 73706163h
0x180042eec  mov     dword ptr [rsp+0D0h+var_A8], ecx; unsigned int
0x180042ef0  mov     eax, r12d
0x180042ef3  mov     ecx, [rbp+47h+arg_0]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180042ef6  neg     eax
0x180042ef8  mov     rdx, rsi; unsigned __int16 *
0x180042efb  mov     [rsp+0D0h+var_B0], r14; void *
0x180042f00  sbb     r9d, r9d
0x180042f03  and     r9d, 4
0x180042f07  inc     r9d
0x180042f0a  call    SetDeviceData
0x180042f0f  xor     r13d, r13d
0x180042f12  test    eax, eax
0x180042f14  jnz     short loc_180042F23
0x180042f16  call    cs:__imp_GetLastError
0x180042f1c  mov     ebx, eax
0x180042f1e  jmp     loc_180042FAB
0x180042f23  mov     r13d, [rbp+47h+var_90]
0x180042f27  cmp     r13d, 1
0x180042f2b  ja      loc_180042FBF
0x180042f31  xor     r13d, r13d
0x180042f34  lea     r8, [rbp+47h+var_90]; int *
0x180042f38  mov     edx, 73706163h; unsigned int
0x180042f3d  mov     [rbp+47h+var_90], r13d
0x180042f41  mov     rcx, rsi; unsigned __int16 *
0x180042f44  call    ?InternalGetUsePerUserProfiles@@YAHPEBGKPEAH@Z; InternalGetUsePerUserProfiles(ushort const *,ulong,int *)
0x180042f49  test    eax, eax
0x180042f4b  jz      short loc_180042F16
0x180042f4d  mov     eax, [rbp+47h+var_90]
0x180042f50  test    eax, eax
0x180042f52  jz      short loc_180042F5A
0x180042f54  cmp     [rbp+47h+arg_0], 1
0x180042f58  jmp     short loc_180042F5E
0x180042f5a  cmp     [rbp+47h+arg_0], r13d
0x180042f5e  jz      short loc_180042F9C
0x180042f60  test    eax, eax
0x180042f62  jz      short loc_180042FC2
0x180042f64  lea     rax, [rbp+47h+var_8C]
0x180042f68  mov     [rbp+47h+var_8C], r13d
0x180042f6c  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x180042f71  mov     r9d, 1; enum COLORPROFILETYPE
0x180042f77  mov     [rsp+0D0h+var_A8], r13; unsigned __int16 *
0x180042f7c  mov     r8d, 6D6E7472h; unsigned int
0x180042f82  mov     rdx, rsi; unsigned __int16 *
0x180042f85  mov     dword ptr [rsp+0D0h+var_B0], r12d; int
0x180042f8a  mov     ecx, r9d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180042f8d  call    ?GetDefaultDeviceProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKW4COLORPROFILETYPE@@HPEAGPEAK@Z; GetDefaultDeviceProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,COLORPROFILETYPE,int,ushort *,ulong *)
0x180042f92  mov     ebx, eax
0x180042f94  cmp     eax, 2
0x180042f97  jnz     short loc_180042FB5
0x180042f99  mov     ebx, r13d
0x180042f9c  xor     edx, edx
0x180042f9e  mov     rcx, rsi; lpString1
0x180042fa1  call    InternalRefreshCalibration
0x180042fa6  call    ?NotifyOfPossibleColorProfileChange@@YAXXZ; NotifyOfPossibleColorProfileChange(void)
0x180042fab  test    ebx, ebx
0x180042fad  jnz     loc_18004304B
0x180042fb3  jmp     short loc_180042FC2
0x180042fb5  test    eax, eax
0x180042fb7  jnz     loc_18004304B
0x180042fbd  jmp     short loc_180042FAB
0x180042fbf  xor     r13d, r13d
0x180042fc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042fc6  test    r15, r15
0x180042fc9  jz      short loc_180042FE2
0x180042fcb  mov     rcx, rax
0x180042fce  inc     rcx
0x180042fd1  cmp     [r15+rcx*2], r13w
0x180042fd6  jnz     short loc_180042FCE
0x180042fd8  lea     rcx, ds:2[rcx*2]
0x180042fe0  jmp     short loc_180042FE5
0x180042fe2  mov     rcx, r13
0x180042fe5  mov     [rbp+47h+var_70], r15
0x180042fe9  mov     [rbp+47h+var_68], ecx
0x180042fec  mov     [rbp+47h+var_64], r13d
0x180042ff0  test    rsi, rsi
0x180042ff3  jz      short loc_180043009
0x180042ff5  inc     rax
0x180042ff8  cmp     [rsi+rax*2], r13w
0x180042ffd  jnz     short loc_180042FF5
0x180042fff  lea     rax, ds:2[rax*2]
0x180043007  jmp     short loc_18004300C
0x180043009  mov     rax, r13
0x18004300c  mov     rcx, cs:g_etwHandle
0x180043013  lea     r9, [rbp+47h+var_70]
0x180043017  mov     [rbp+47h+var_58], eax
0x18004301a  lea     rdx, SET_DEFAULT_DEVICE_PROFILE
0x180043021  lea     rax, [rbp+47h+arg_0]
0x180043025  mov     [rbp+47h+var_60], rsi
0x180043029  mov     r8d, 3
0x18004302f  mov     [rbp+47h+var_50], rax
0x180043033  mov     [rbp+47h+var_54], r13d
0x180043037  mov     [rbp+47h+var_48], 4
0x18004303f  call    cs:__imp_EtwEventWrite
0x180043045  jmp     short loc_18004304B
0x180043047  mov     rdi, [rbp+47h+lpMem]
0x18004304b  test    rdi, rdi
0x18004304e  jz      short loc_180043058
0x180043050  mov     rcx, rdi; lpMem
0x180043053  call    MemFree
0x180043058  test    r14, r14
0x18004305b  jz      short loc_180043065
0x18004305d  mov     rcx, r14; lpMem
0x180043060  call    MemFree
0x180043065  mov     eax, ebx
0x180043067  mov     rcx, [rbp+47h+var_40]
0x18004306b  xor     rcx, rsp; StackCookie
0x18004306e  call    __security_check_cookie
0x180043073  mov     rbx, [rsp+0D0h+arg_10]
0x18004307b  add     rsp, 0A0h
0x180043082  pop     r15
0x180043084  pop     r14
0x180043086  pop     r13
0x180043088  pop     r12
0x18004308a  pop     rdi
0x18004308b  pop     rsi
0x18004308c  pop     rbp
0x18004308d  retn
```
