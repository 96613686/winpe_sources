# ClusterSpaceControl

- ea: `0x180012b60`
- end: `0x180012f2b`
- name: `ClusterSpaceControl`
- size: `971`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180006350`
- `0x18000f484`
- `0x180012b60`
- `0x1800179c0`
- `0x18001aa70`
- `0x180037e14`
- `0x1800958b8`
- `0x18010e91c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012def`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012def`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012c4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012c4a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012be4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012ed3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012be4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012ed3`
- `RPCRT4!RpcImpersonateClient` at `0x180012c0b`
- `RPCRT4!RpcImpersonateClient` at `0x180012c0b`
- `RPCRT4!RpcRevertToSelf` at `0x180012ee1`
- `RPCRT4!RpcRevertToSelf` at `0x180012ee1`

## string_xrefs

- `0x180012c43`: `mispace.dll`

## pseudocode

```c
__int64 __fastcall ClusterSpaceControl(
        __int64 a1,
        void *a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int *a7)
{
  signed int v7; // ebx
  enum _MI_Result v11; // eax
  int v12; // r14d
  RPC_STATUS v13; // eax
  unsigned __int64 *refreshed; // rax
  __int128 v15; // xmm0
  unsigned int v16; // edx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // edx
  __int128 v21; // xmm0
  __int64 v22; // rdx
  int *v23; // rcx
  _OWORD *v24; // rax
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm1
  int v33; // r9d
  __int64 v34; // r8
  unsigned int v35; // edx
  __int128 v36; // xmm0
  int v38[140]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+280h] [rbp+180h] BYREF
  __int64 v40; // [rsp+290h] [rbp+190h]
  GUID ActivityId; // [rsp+298h] [rbp+198h] BYREF

  v7 = 0;
  ActivityId = GUID_NULL;
  LODWORD(v39) = 0;
  v11 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v11 )
  {
    v12 = 0;
    if ( v11 == MI_RESULT_SERVER_IS_SHUTTING_DOWN )
      v7 = -2147023781;
  }
  else
  {
    v12 = 1;
    *a7 = 0;
    if ( a2 )
    {
      if ( !SetThreadToken(0, a2) )
      {
        _status_t::GetLastError((_status_t *)&v39);
        v7 = v39;
LABEL_38:
        SetThreadToken(0, 0);
        goto LABEL_40;
      }
    }
    else
    {
      v13 = RpcImpersonateClient(0);
      v7 = v13;
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
      LODWORD(v39) = v7;
      if ( v7 < 0 )
        goto LABEL_39;
    }
    if ( a4 < 8 )
      goto LABEL_9;
    g_SpacesModule = GetModuleHandleW(L"mispace.dll");
    if ( !g_SpacesModule )
    {
      _status_t::GetLastError((_status_t *)&v39);
      v7 = v39;
      goto LABEL_37;
    }
    refreshed = (unsigned __int64 *)SuexRefreshClusterSubsystem(&v39, 0);
    v7 = _mm_cvtsi128_si32((__m128i)*refreshed);
    DWORD2(v39) = *((_DWORD *)refreshed + 2);
    if ( v7 >= 0 )
    {
      if ( *(_QWORD *)a3 == 2147549183LL )
      {
        if ( a4 >= 0x48 )
        {
          v15 = *(_OWORD *)(a3 + 32);
          v40 = *(_QWORD *)(a3 + 48);
          v39 = v15;
          ActivityId = *(GUID *)(a3 + 56);
          v16 = *(_DWORD *)(a3 + 12);
          if ( v16 <= a4 && *(_DWORD *)(a3 + 8) >= 0x48u )
          {
            v17 = *(unsigned int *)(a3 + 28);
            if ( (unsigned int)v17 >= *(_DWORD *)(a3 + 8) && (unsigned int)v17 <= v16 )
            {
              v18 = PmcControlDispatch(
                      *(_DWORD *)(a3 + 24),
                      v16 - v17,
                      (void *)(a3 + v17),
                      a6,
                      a5,
                      a7,
                      &v39,
                      &ActivityId);
              goto LABEL_20;
            }
          }
        }
      }
      else
      {
        v40 = 0;
        v39 = 0;
        if ( a4 >= 0x23C )
        {
          v19 = *(_DWORD *)(a3 + 568);
          if ( v19 >= 0x23C && v19 <= a4 )
          {
            v20 = v19 + *(_DWORD *)(a3 + 564);
            if ( v20 >= v19 && v20 <= a4 )
            {
              if ( a4 >= 0x278 && *(_QWORD *)(a3 + 576) == 0x7415150A600D57ACLL && *(_DWORD *)(a3 + 588) >= 0x278u )
              {
                v21 = *(_OWORD *)(a3 + 592);
                v40 = *(_QWORD *)(a3 + 608);
                v39 = v21;
                ActivityId = *(GUID *)(a3 + 616);
              }
              else
              {
                EventActivityIdControl(1u, &ActivityId);
              }
              v22 = 4;
              v23 = v38;
              v24 = (_OWORD *)a3;
              do
              {
                v25 = v24[1];
                *(_OWORD *)v23 = *v24;
                v26 = v24[2];
                *((_OWORD *)v23 + 1) = v25;
                v27 = v24[3];
                *((_OWORD *)v23 + 2) = v26;
                v28 = v24[4];
                *((_OWORD *)v23 + 3) = v27;
                v29 = v24[5];
                *((_OWORD *)v23 + 4) = v28;
                v30 = v24[6];
                *((_OWORD *)v23 + 5) = v29;
                v31 = v24[7];
                v24 += 8;
                *((_OWORD *)v23 + 6) = v30;
                *((_OWORD *)v23 + 7) = v31;
                v23 += 32;
                --v22;
              }
              while ( v22 );
              v32 = v24[1];
              v33 = *(_DWORD *)(a3 + 564);
              v34 = a3 + *(unsigned int *)(a3 + 568);
              v35 = *(_DWORD *)(a3 + 560);
              *(_OWORD *)v23 = *v24;
              v36 = v24[2];
              *((_OWORD *)v23 + 1) = v32;
              *((_OWORD *)v23 + 2) = v36;
              v18 = ControlDispatch(v38, v35, v34, v33, a5, a6, (int *)a7, &v39, (__int128 *)&ActivityId);
LABEL_20:
              v7 = v18;
              if ( v18 > 0 )
                v7 = (unsigned __int16)v18 | 0x80070000;
              goto LABEL_37;
            }
          }
        }
      }
LABEL_9:
      v7 = -2147024809;
    }
  }
LABEL_37:
  if ( a2 )
    goto LABEL_38;
LABEL_39:
  RpcRevertToSelf();
LABEL_40:
  if ( v12 )
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012b60  mov     [rsp-8+arg_0], rbx
0x180012b65  push    rbp
0x180012b66  push    rsi
0x180012b67  push    rdi
0x180012b68  push    r12
0x180012b6a  push    r13
0x180012b6c  push    r14
0x180012b6e  push    r15
0x180012b70  lea     rbp, [rsp-1B0h]
0x180012b78  sub     rsp, 2B0h
0x180012b7f  mov     rax, cs:__security_cookie
0x180012b86  xor     rax, rsp
0x180012b89  mov     [rbp+1E0h+var_38], rax
0x180012b90  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180012b97  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180012b9e  xor     ebx, ebx
0x180012ba0  mov     r13, [rbp+1E0h+arg_20]
0x180012ba7  mov     esi, r9d
0x180012baa  mov     r12, [rbp+1E0h+arg_30]
0x180012bb1  mov     rdi, r8
0x180012bb4  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x180012bbc  mov     r15, rdx
0x180012bbf  mov     dword ptr [rbp+1E0h+var_60], ebx
0x180012bc5  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180012bca  test    eax, eax
0x180012bcc  jnz     loc_180012EBD
0x180012bd2  lea     r14d, [rbx+1]
0x180012bd6  mov     [r12], ebx
0x180012bda  xor     ecx, ecx; BindingHandle
0x180012bdc  test    r15, r15
0x180012bdf  jz      short loc_180012C0B
0x180012be1  mov     rdx, r15; Token
0x180012be4  call    cs:__imp_SetThreadToken
0x180012beb  nop     dword ptr [rax+rax+00h]
0x180012bf0  test    eax, eax
0x180012bf2  jnz     short loc_180012C34
0x180012bf4  lea     rcx, [rbp+1E0h+var_60]; this
0x180012bfb  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x180012c00  mov     ebx, dword ptr [rbp+1E0h+var_60]
0x180012c06  jmp     loc_180012ECF
0x180012c0b  call    cs:__imp_RpcImpersonateClient
0x180012c12  nop     dword ptr [rax+rax+00h]
0x180012c17  mov     ebx, eax
0x180012c19  test    eax, eax
0x180012c1b  jle     short loc_180012C26
0x180012c1d  movzx   ebx, ax
0x180012c20  or      ebx, 80070000h
0x180012c26  mov     dword ptr [rbp+1E0h+var_60], ebx
0x180012c2c  test    ebx, ebx
0x180012c2e  js      loc_180012EE1
0x180012c34  cmp     esi, 8
0x180012c37  jnb     short loc_180012C43
0x180012c39  mov     ebx, 80070057h
0x180012c3e  jmp     loc_180012ECA
0x180012c43  lea     rcx, aMispaceDll_0; "mispace.dll"
0x180012c4a  call    cs:__imp_GetModuleHandleW
0x180012c51  nop     dword ptr [rax+rax+00h]
0x180012c56  mov     cs:?g_SpacesModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_SpacesModule
0x180012c5d  lea     rcx, [rbp+1E0h+var_60]; this
0x180012c64  test    rax, rax
0x180012c67  jnz     short loc_180012C79
0x180012c69  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x180012c6e  mov     ebx, dword ptr [rbp+1E0h+var_60]
0x180012c74  jmp     loc_180012ECA
0x180012c79  xor     edx, edx
0x180012c7b  call    ?SuexRefreshClusterSubsystem@@YA?AV_status_t@@PEAH@Z; SuexRefreshClusterSubsystem(int *)
0x180012c80  movsd   xmm0, qword ptr [rax]
0x180012c84  mov     eax, [rax+8]
0x180012c87  movd    ebx, xmm0
0x180012c8b  mov     dword ptr [rbp+1E0h+var_60+8], eax
0x180012c91  test    ebx, ebx
0x180012c93  js      loc_180012ECA
0x180012c99  mov     eax, 8000FFFFh
0x180012c9e  cmp     [rdi], rax
0x180012ca1  jnz     loc_180012D47
0x180012ca7  cmp     esi, 48h ; 'H'
0x180012caa  jb      short loc_180012C39
0x180012cac  movups  xmm0, xmmword ptr [rdi+20h]
0x180012cb0  mov     rax, [rdi+30h]
0x180012cb4  mov     [rbp+1E0h+var_50], rax
0x180012cbb  movdqu  [rbp+1E0h+var_60], xmm0
0x180012cc3  movups  xmm0, xmmword ptr [rdi+38h]
0x180012cc7  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x180012ccf  mov     edx, [rdi+0Ch]
0x180012cd2  cmp     edx, esi
0x180012cd4  ja      loc_180012C39
0x180012cda  cmp     dword ptr [rdi+8], 48h ; 'H'
0x180012cde  jb      loc_180012C39
0x180012ce4  mov     eax, [rdi+1Ch]
0x180012ce7  cmp     eax, [rdi+8]
0x180012cea  jb      loc_180012C39
0x180012cf0  cmp     eax, edx
0x180012cf2  ja      loc_180012C39
0x180012cf8  mov     r9d, [rbp+1E0h+arg_28]; unsigned int
0x180012cff  lea     r8, [rdi+rax]; void *
0x180012d03  mov     ecx, [rdi+18h]; unsigned int
0x180012d06  sub     edx, eax; unsigned int
0x180012d08  lea     rax, [rbp+1E0h+ActivityId]
0x180012d0f  mov     [rsp+2E0h+var_2A8], rax; struct _GUID *
0x180012d14  lea     rax, [rbp+1E0h+var_60]
0x180012d1b  mov     [rsp+2E0h+var_2B0], rax; void *
0x180012d20  mov     [rsp+2E0h+var_2B8], r12; unsigned int *
0x180012d25  mov     [rsp+2E0h+var_2C0], r13; void *
0x180012d2a  call    ?PmcControlDispatch@@YAKKKPEAXK0PEAK0PEAU_GUID@@@Z; PmcControlDispatch(ulong,ulong,void *,ulong,void *,ulong *,void *,_GUID *)
0x180012d2f  mov     ebx, eax
0x180012d31  test    eax, eax
0x180012d33  jle     loc_180012ECA
0x180012d39  movzx   ebx, ax
0x180012d3c  or      ebx, 80070000h
0x180012d42  jmp     loc_180012ECA
0x180012d47  xor     eax, eax
0x180012d49  xorps   xmm0, xmm0
0x180012d4c  mov     [rbp+1E0h+var_50], rax
0x180012d53  mov     eax, 23Ch
0x180012d58  movups  [rbp+1E0h+var_60], xmm0
0x180012d5f  cmp     esi, eax
0x180012d61  jb      loc_180012C39
0x180012d67  mov     ecx, [rdi+238h]
0x180012d6d  cmp     ecx, eax
0x180012d6f  jb      loc_180012C39
0x180012d75  cmp     ecx, esi
0x180012d77  ja      loc_180012C39
0x180012d7d  mov     edx, [rdi+234h]
0x180012d83  add     edx, ecx
0x180012d85  cmp     edx, ecx
0x180012d87  jb      loc_180012C39
0x180012d8d  cmp     edx, esi
0x180012d8f  ja      loc_180012C39
0x180012d95  lea     ecx, [rax+3Ch]
0x180012d98  cmp     esi, ecx
0x180012d9a  jb      short loc_180012DE5
0x180012d9c  mov     rax, 7415150A600D57ACh
0x180012da6  cmp     [rdi+240h], rax
0x180012dad  jnz     short loc_180012DE5
0x180012daf  cmp     [rdi+24Ch], ecx
0x180012db5  jb      short loc_180012DE5
0x180012db7  movups  xmm0, xmmword ptr [rdi+250h]
0x180012dbe  mov     rax, [rdi+260h]
0x180012dc5  mov     [rbp+1E0h+var_50], rax
0x180012dcc  movdqu  [rbp+1E0h+var_60], xmm0
0x180012dd4  movups  xmm0, xmmword ptr [rdi+268h]
0x180012ddb  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x180012de3  jmp     short loc_180012DFB
0x180012de5  lea     rdx, [rbp+1E0h+ActivityId]; ActivityId
0x180012dec  mov     ecx, r14d; ControlCode
0x180012def  call    cs:__imp_EventActivityIdControl
0x180012df6  nop     dword ptr [rax+rax+00h]
0x180012dfb  mov     edx, 4
0x180012e00  lea     rcx, [rsp+2E0h+var_290]
0x180012e05  mov     rax, rdi
0x180012e08  lea     r8d, [rdx+7Ch]
0x180012e0c  movups  xmm0, xmmword ptr [rax]
0x180012e0f  movups  xmm1, xmmword ptr [rax+10h]
0x180012e13  movups  xmmword ptr [rcx], xmm0
0x180012e16  movups  xmm0, xmmword ptr [rax+20h]
0x180012e1a  movups  xmmword ptr [rcx+10h], xmm1
0x180012e1e  movups  xmm1, xmmword ptr [rax+30h]
0x180012e22  movups  xmmword ptr [rcx+20h], xmm0
0x180012e26  movups  xmm0, xmmword ptr [rax+40h]
0x180012e2a  movups  xmmword ptr [rcx+30h], xmm1
0x180012e2e  movups  xmm1, xmmword ptr [rax+50h]
0x180012e32  movups  xmmword ptr [rcx+40h], xmm0
0x180012e36  movups  xmm0, xmmword ptr [rax+60h]
0x180012e3a  movups  xmmword ptr [rcx+50h], xmm1
0x180012e3e  movups  xmm1, xmmword ptr [rax+70h]
0x180012e42  add     rax, r8
0x180012e45  movups  xmmword ptr [rcx+60h], xmm0
0x180012e49  movups  xmmword ptr [rcx+70h], xmm1
0x180012e4d  add     rcx, r8
0x180012e50  sub     rdx, r14
0x180012e53  jnz     short loc_180012E0C
0x180012e55  movups  xmm0, xmmword ptr [rax]
0x180012e58  mov     r8d, [rdi+238h]
0x180012e5f  movups  xmm1, xmmword ptr [rax+10h]
0x180012e63  mov     r9d, [rdi+234h]
0x180012e6a  add     r8, rdi
0x180012e6d  mov     edx, [rdi+230h]
0x180012e73  movups  xmmword ptr [rcx], xmm0
0x180012e76  movups  xmm0, xmmword ptr [rax+20h]
0x180012e7a  lea     rax, [rbp+1E0h+ActivityId]
0x180012e81  mov     [rsp+2E0h+var_2A0], rax
0x180012e86  lea     rax, [rbp+1E0h+var_60]
0x180012e8d  mov     [rsp+2E0h+var_2A8], rax
0x180012e92  mov     eax, [rbp+1E0h+arg_28]
0x180012e98  movups  xmmword ptr [rcx+10h], xmm1
0x180012e9c  mov     [rsp+2E0h+var_2B0], r12
0x180012ea1  movups  xmmword ptr [rcx+20h], xmm0
0x180012ea5  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x180012ea9  lea     rcx, [rsp+2E0h+var_290]
0x180012eae  mov     [rsp+2E0h+var_2C0], r13
0x180012eb3  call    ?ControlDispatch@@YAKU_SP_CONTROL_HANDLE@@KPEAXK1KPEAK1PEAU_GUID@@@Z; ControlDispatch(_SP_CONTROL_HANDLE,ulong,void *,ulong,void *,ulong,ulong *,void *,_GUID *)
0x180012eb8  jmp     loc_180012D2F
0x180012ebd  xor     r14d, r14d
0x180012ec0  cmp     eax, 1Ch
0x180012ec3  jnz     short loc_180012ECA
0x180012ec5  mov     ebx, 8007045Bh
0x180012eca  test    r15, r15
0x180012ecd  jz      short loc_180012EE1
0x180012ecf  xor     edx, edx; Token
0x180012ed1  xor     ecx, ecx; Thread
0x180012ed3  call    cs:__imp_SetThreadToken
0x180012eda  nop     dword ptr [rax+rax+00h]
0x180012edf  jmp     short loc_180012EED
0x180012ee1  call    cs:__imp_RpcRevertToSelf
0x180012ee8  nop     dword ptr [rax+rax+00h]
0x180012eed  test    r14d, r14d
0x180012ef0  jz      short loc_180012EFE
0x180012ef2  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180012ef9  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180012efe  mov     eax, ebx
0x180012f00  mov     rcx, [rbp+1E0h+var_38]
0x180012f07  xor     rcx, rsp; StackCookie
0x180012f0a  call    __security_check_cookie
0x180012f0f  mov     rbx, [rsp+2E0h+arg_0]
0x180012f17  add     rsp, 2B0h
0x180012f1e  pop     r15
0x180012f20  pop     r14
0x180012f22  pop     r13
0x180012f24  pop     r12
0x180012f26  pop     rdi
0x180012f27  pop     rsi
0x180012f28  pop     rbp
0x180012f29  retn
```
