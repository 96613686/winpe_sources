# MdaDeviceControl

- ea: `0x140022c5c`
- end: `0x140022ff9`
- name: `MdaDeviceControl`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009b80`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140016b14`
- `0x140016cb8`
- `0x140022054`
- `0x140022c5c`
- `0x140023518`
- `0x14002dec4`
- `0x140038edc`
- `0x140039010`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140022dae`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140022dae`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140022e1d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140022e1d`
- `ntoskrnl!SeAccessCheck` at `0x140022e0a`
- `ntoskrnl!SeAccessCheck` at `0x140022e0a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140022dba`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140022dba`

## pseudocode

```c
__int64 __fastcall MdaDeviceControl(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _OWORD *v7; // r14
  __int64 v8; // r9
  unsigned int v9; // r15d
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v13; // bl
  __int64 v14; // rdx
  unsigned int *v15; // r8
  __int64 v16; // r10
  unsigned int v17; // esi
  unsigned int v18; // eax
  unsigned __int64 v19; // rax
  unsigned int MappingServerFromRegistry; // eax
  int AccessStatus; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-ACh] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[112]; // [rsp+80h] [rbp-80h] BYREF

  memset(v26, 0, sizeof(v26));
  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessStatus = -1073741790;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
  }
  v4 = *(_DWORD **)(a2 + 184);
  memset(v26, 0, sizeof(v26));
  v7 = *(_OWORD **)(a2 + 24);
  v26[5] = a2;
  v26[6] = v4;
  v26[10] = a1;
  v8 = (unsigned int)v4[6];
  v9 = v4[4];
  v10 = v4[2];
  *(_QWORD *)(a2 + 56) = 0;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 2316), 0, 0) & 0x18) != 0x10 )
    return 3221225473LL;
  switch ( (_DWORD)v8 )
  {
    case 0x140800:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
      {
        WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, v5, v6, v9, v7);
      }
      v11 = UserAuthentication((__int64)v26, (__int64)v7, v9, v7, v10);
      v19 = (((__int64)(int)v11 >> 63) & 0xFFFFFFFFFFFFFFB4uLL) + 76;
      goto LABEL_41;
    case 0x140804:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
      }
      v11 = SetMountOptions((__int64)v7, v9);
      goto LABEL_42;
    case 0x14C844:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
      }
      MappingServerFromRegistry = MapReadMappingServerFromRegistry(a1);
      goto LABEL_28;
    case 0x14C848:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids);
      }
      MappingServerFromRegistry = MdaReadRegistrySettings(a1);
LABEL_28:
      v11 = MappingServerFromRegistry;
      *(_QWORD *)(a2 + 56) = 0;
      goto LABEL_42;
  }
  if ( (_DWORD)v8 != 536928260 && (_DWORD)v8 != 536928264 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids, v8);
    }
    v11 = -1073741822;
    goto LABEL_42;
  }
  SeCaptureSubjectContext(&SubjectContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v13 = SeAccessCheck(
          (PSECURITY_DESCRIPTOR)(a1 + 2040),
          &SubjectContext,
          0,
          0x120116u,
          0,
          0,
          GenericMapping,
          1,
          &GrantedAccess,
          &AccessStatus);
  SeReleaseSubjectContext(&SubjectContext);
  if ( v13 || (v11 = AccessStatus, AccessStatus >= 0) )
  {
    v15 = *(unsigned int **)(a2 + 184);
    v16 = *(_QWORD *)(a1 + 2016);
    v17 = 0;
    v23 = 0;
    if ( v15[6] == 536928260 )
    {
      v18 = NfsProcessUpCallRequest(v16, *(_QWORD *)(a2 + 24), v15[2], &v23);
      v17 = v23;
    }
    else
    {
      if ( v15[6] != 536928264 )
      {
        v11 = -1073741811;
LABEL_23:
        *(_QWORD *)(a2 + 56) = v17;
        v19 = v17;
        *(_DWORD *)(a2 + 48) = v11;
LABEL_41:
        *(_QWORD *)(a2 + 56) = v19;
        goto LABEL_42;
      }
      v18 = NfsProcessUpCallReply(v16, v14, *(_QWORD *)(a2 + 24), v15[4]);
    }
    v11 = v18;
    goto LABEL_23;
  }
LABEL_42:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x140022c5c  mov     [rsp-8+arg_10], rbx
0x140022c61  push    rbp
0x140022c62  push    rsi
0x140022c63  push    rdi
0x140022c64  push    r12
0x140022c66  push    r13
0x140022c68  push    r14
0x140022c6a  push    r15
0x140022c6c  lea     rbp, [rsp-310h]
0x140022c74  sub     rsp, 410h
0x140022c7b  mov     rax, cs:__security_cookie
0x140022c82  xor     rax, rsp
0x140022c85  mov     [rbp+340h+var_40], rax
0x140022c8c  mov     rdi, rdx
0x140022c8f  mov     rsi, rcx
0x140022c92  mov     r14d, 380h
0x140022c98  lea     rcx, [rbp+340h+var_3C0]; void *
0x140022c9c  mov     r8d, r14d; Size
0x140022c9f  xor     edx, edx; Val
0x140022ca1  call    memset
0x140022ca6  xorps   xmm0, xmm0
0x140022ca9  mov     [rsp+440h+var_3E8], 0
0x140022cb1  movups  xmmword ptr [rsp+440h+SubjectContext.ClientToken], xmm0
0x140022cb6  mov     [rsp+440h+var_3F0], 0C0000022h
0x140022cbe  movups  xmmword ptr [rsp+440h+SubjectContext.PrimaryToken], xmm0
0x140022cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140022cca  lea     r13, WPP_GLOBAL_Control
0x140022cd1  cmp     rcx, r13
0x140022cd4  jz      short loc_140022CF2
0x140022cd6  bt      dword ptr [rcx+2Ch], 11h
0x140022cdb  jnb     short loc_140022CF2
0x140022cdd  mov     rcx, [rcx+18h]
0x140022ce1  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022ce8  mov     edx, 20h ; ' '
0x140022ced  call    WPP_SF_
0x140022cf2  mov     rbx, [rdi+0B8h]
0x140022cf9  lea     rcx, [rbp+340h+var_3C0]; void *
0x140022cfd  mov     r8, r14; Size
0x140022d00  xor     edx, edx; Val
0x140022d02  call    memset
0x140022d07  mov     r14, [rdi+18h]
0x140022d0b  xor     ecx, ecx
0x140022d0d  mov     [rbp+340h+var_398], rdi
0x140022d11  xor     eax, eax
0x140022d13  mov     [rbp+340h+var_390], rbx
0x140022d17  mov     [rbp+340h+var_370], rsi
0x140022d1b  mov     r9d, [rbx+18h]
0x140022d1f  mov     r15d, [rbx+10h]
0x140022d23  mov     ebx, [rbx+8]
0x140022d26  mov     qword ptr [rdi+38h], 0
0x140022d2e  lock cmpxchg [rsi+90Ch], ecx
0x140022d36  and     al, 18h
0x140022d38  cmp     al, 10h
0x140022d3a  jnz     loc_140022FC9
0x140022d40  mov     eax, r9d
0x140022d43  sub     eax, 140800h
0x140022d48  jz      loc_140022F4A
0x140022d4e  sub     eax, 4
0x140022d51  jz      loc_140022F13
0x140022d57  sub     eax, 0C040h
0x140022d5c  jz      loc_140022EE1
0x140022d62  sub     eax, 4
0x140022d65  jz      loc_140022EA2
0x140022d6b  sub     eax, 1FEC17BCh
0x140022d70  jz      short loc_140022DA9
0x140022d72  cmp     eax, 4
0x140022d75  jz      short loc_140022DA9
0x140022d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d7e  cmp     rcx, r13
0x140022d81  jz      short loc_140022D9F
0x140022d83  bt      dword ptr [rcx+2Ch], 11h
0x140022d88  jnb     short loc_140022D9F
0x140022d8a  mov     rcx, [rcx+18h]
0x140022d8e  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022d95  mov     edx, 2Ah ; '*'
0x140022d9a  call    WPP_SF_d
0x140022d9f  mov     ebx, 0C0000002h
0x140022da4  jmp     loc_140022F9A
0x140022da9  lea     rcx, [rsp+440h+SubjectContext]; SubjectContext
0x140022dae  call    cs:__imp_SeCaptureSubjectContext
0x140022db5  nop     dword ptr [rax+rax+00h]
0x140022dba  call    cs:__imp_IoGetFileObjectGenericMapping
0x140022dc1  nop     dword ptr [rax+rax+00h]
0x140022dc6  lea     rdx, [rsp+440h+var_3F0]
0x140022dcb  mov     r9d, 120116h; DesiredAccess
0x140022dd1  mov     [rsp+440h+AccessStatus], rdx; AccessStatus
0x140022dd6  lea     rcx, [rsi+7F8h]; SecurityDescriptor
0x140022ddd  lea     rdx, [rsp+440h+var_3E8]
0x140022de2  xor     r8d, r8d; SubjectContextLocked
0x140022de5  mov     [rsp+440h+GrantedAccess], rdx; GrantedAccess
0x140022dea  lea     rdx, [rsp+440h+SubjectContext]; SubjectSecurityContext
0x140022def  mov     [rsp+440h+AccessMode], 1; AccessMode
0x140022df4  mov     [rsp+440h+GenericMapping], rax; GenericMapping
0x140022df9  mov     [rsp+440h+Privileges], 0; Privileges
0x140022e02  mov     [rsp+440h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140022e0a  call    cs:__imp_SeAccessCheck
0x140022e11  nop     dword ptr [rax+rax+00h]
0x140022e16  lea     rcx, [rsp+440h+SubjectContext]; SubjectContext
0x140022e1b  mov     bl, al
0x140022e1d  call    cs:__imp_SeReleaseSubjectContext
0x140022e24  nop     dword ptr [rax+rax+00h]
0x140022e29  test    bl, bl
0x140022e2b  jnz     short loc_140022E39
0x140022e2d  mov     ebx, [rsp+440h+var_3F0]
0x140022e31  test    ebx, ebx
0x140022e33  js      loc_140022F9A
0x140022e39  mov     r8, [rdi+0B8h]
0x140022e40  mov     r10, [rsi+7E0h]
0x140022e47  xor     esi, esi
0x140022e49  mov     [rsp+440h+var_3EC], esi
0x140022e4d  mov     ecx, [r8+18h]
0x140022e51  sub     ecx, 2000E004h
0x140022e57  jz      short loc_140022E77
0x140022e59  cmp     ecx, 4
0x140022e5c  jz      short loc_140022E65
0x140022e5e  mov     ebx, 0C000000Dh
0x140022e63  jmp     short loc_140022E92
0x140022e65  mov     r9d, [r8+10h]
0x140022e69  mov     rcx, r10
0x140022e6c  mov     r8, [rdi+18h]
0x140022e70  call    NfsProcessUpCallReply
0x140022e75  jmp     short loc_140022E90
0x140022e77  mov     r8d, [r8+8]
0x140022e7b  lea     r9, [rsp+440h+var_3EC]
0x140022e80  mov     rdx, [rdi+18h]
0x140022e84  mov     rcx, r10
0x140022e87  call    NfsProcessUpCallRequest
0x140022e8c  mov     esi, [rsp+440h+var_3EC]
0x140022e90  mov     ebx, eax
0x140022e92  mov     eax, esi
0x140022e94  mov     [rdi+38h], rax
0x140022e98  mov     eax, eax
0x140022e9a  mov     [rdi+30h], ebx
0x140022e9d  jmp     loc_140022F96
0x140022ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ea9  cmp     rcx, r13
0x140022eac  jz      short loc_140022ECA
0x140022eae  bt      dword ptr [rcx+2Ch], 11h
0x140022eb3  jnb     short loc_140022ECA
0x140022eb5  mov     rcx, [rcx+18h]
0x140022eb9  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022ec0  mov     edx, 25h ; '%'
0x140022ec5  call    WPP_SF_
0x140022eca  mov     rcx, rsi
0x140022ecd  call    MdaReadRegistrySettings
0x140022ed2  mov     ebx, eax
0x140022ed4  mov     qword ptr [rdi+38h], 0
0x140022edc  jmp     loc_140022F9A
0x140022ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ee8  cmp     rcx, r13
0x140022eeb  jz      short loc_140022F09
0x140022eed  bt      dword ptr [rcx+2Ch], 11h
0x140022ef2  jnb     short loc_140022F09
0x140022ef4  mov     rcx, [rcx+18h]
0x140022ef8  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022eff  mov     edx, 26h ; '&'
0x140022f04  call    WPP_SF_
0x140022f09  mov     rcx, rsi
0x140022f0c  call    MapReadMappingServerFromRegistry
0x140022f11  jmp     short loc_140022ED2
0x140022f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f1a  cmp     rcx, r13
0x140022f1d  jz      short loc_140022F3B
0x140022f1f  bt      dword ptr [rcx+2Ch], 11h
0x140022f24  jnb     short loc_140022F3B
0x140022f26  mov     rcx, [rcx+18h]
0x140022f2a  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022f31  mov     edx, 22h ; '"'
0x140022f36  call    WPP_SF_
0x140022f3b  mov     edx, r15d
0x140022f3e  mov     rcx, r14
0x140022f41  call    SetMountOptions
0x140022f46  mov     ebx, eax
0x140022f48  jmp     short loc_140022F9A
0x140022f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f51  cmp     rcx, r13
0x140022f54  jz      short loc_140022F6E
0x140022f56  bt      dword ptr [rcx+2Ch], 11h
0x140022f5b  jnb     short loc_140022F6E
0x140022f5d  mov     rcx, [rcx+18h]
0x140022f61  mov     r9d, r15d
0x140022f64  mov     qword ptr [rsp+440h+PreviouslyGrantedAccess], r14
0x140022f69  call    WPP_SF_dq
0x140022f6e  mov     r9, r14
0x140022f71  mov     [rsp+440h+PreviouslyGrantedAccess], ebx
0x140022f75  mov     r8d, r15d
0x140022f78  lea     rcx, [rbp+340h+var_3C0]
0x140022f7c  mov     rdx, r14
0x140022f7f  call    UserAuthentication
0x140022f84  movsxd  rbx, eax
0x140022f87  mov     rax, rbx
0x140022f8a  sar     rax, 3Fh
0x140022f8e  and     rax, 0FFFFFFFFFFFFFFB4h
0x140022f92  add     rax, 4Ch ; 'L'
0x140022f96  mov     [rdi+38h], rax
0x140022f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140022fa1  cmp     rcx, r13
0x140022fa4  jz      short loc_140022FC5
0x140022fa6  bt      dword ptr [rcx+2Ch], 11h
0x140022fab  jnb     short loc_140022FC5
0x140022fad  mov     rcx, [rcx+18h]
0x140022fb1  lea     r8, WPP_42e659764de03be559bb1c7930cd00f7_Traceguids
0x140022fb8  mov     edx, 2Bh ; '+'
0x140022fbd  mov     r9d, ebx
0x140022fc0  call    WPP_SF_d
0x140022fc5  mov     eax, ebx
0x140022fc7  jmp     short loc_140022FCE
0x140022fc9  mov     eax, 0C0000001h
0x140022fce  mov     rcx, [rbp+340h+var_40]
0x140022fd5  xor     rcx, rsp; StackCookie
0x140022fd8  call    __security_check_cookie
0x140022fdd  mov     rbx, [rsp+440h+arg_10]
0x140022fe5  add     rsp, 410h
0x140022fec  pop     r15
0x140022fee  pop     r14
0x140022ff0  pop     r13
0x140022ff2  pop     r12
0x140022ff4  pop     rdi
0x140022ff5  pop     rsi
0x140022ff6  pop     rbp
0x140022ff7  retn
```
