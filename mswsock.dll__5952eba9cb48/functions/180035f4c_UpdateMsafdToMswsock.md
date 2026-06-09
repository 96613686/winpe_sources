# UpdateMsafdToMswsock

- ea: `0x180035f4c`
- end: `0x180036395`
- name: `UpdateMsafdToMswsock`
- size: `1097`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800328c0`

## callees

- `0x1800222f0`
- `0x1800327a8`
- `0x180035f4c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003603b`
- `ntdll!RtlFreeHeap` at `0x180036092`
- `ntdll!RtlFreeHeap` at `0x18003603b`
- `ntdll!RtlFreeHeap` at `0x180036092`
- `WS2_32!WSCGetProviderPath` at `0x180035fb0`
- `WS2_32!WSCGetProviderPath` at `0x18003601f`
- `WS2_32!WSCGetProviderPath` at `0x180035fb0`
- `WS2_32!WSCGetProviderPath` at `0x18003601f`
- `WS2_32!WSCUpdateProvider` at `0x180036322`
- `WS2_32!WSCUpdateProvider` at `0x180036322`
- `WS2_32!WSCUpdateProvider32` at `0x180036350`
- `WS2_32!WSCUpdateProvider32` at `0x180036350`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18003606a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18003606a`

## string_xrefs

- `0x180036060`: `%SystemRoot%\system32\mswsock.dll`
- `0x180036318`: `%SystemRoot%\system32\mswsock.dll`
- `0x180036346`: `%SystemRoot%\system32\mswsock.dll`
- `0x180035ffc`: `Failed to allocate space for provider path`
- `0x18003604b`: `Failed to get provider path`

## pseudocode

```c
__int64 __fastcall UpdateMsafdToMswsock(__int64 a1, unsigned int a2, GUID *a3)
{
  WCHAR *v6; // rbx
  WCHAR *v7; // rax
  int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // r9d
  __int64 v12; // rsi
  __int64 v13; // rax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  __int64 v16; // r15
  __int64 v17; // r11
  __int64 v18; // r10
  __int64 v19; // rax
  _OWORD *v20; // rcx
  _OWORD *v21; // rdx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  int v36; // eax
  _OWORD *v37; // rcx
  _OWORD *v38; // rax
  __int64 v39; // r10
  __int128 v40; // xmm1
  _OWORD *v41; // rax
  __int64 v42; // rdx
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  int v56; // eax
  DWORD v57; // ebx
  int Errno; // [rsp+30h] [rbp-D0h] BYREF
  int ProviderDllPathLen[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v60[640]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szProviderDllPath[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  Errno = 0;
  ProviderDllPathLen[0] = 261;
  v6 = szProviderDllPath;
  if ( !WSCGetProviderPath(a3, szProviderDllPath, ProviderDllPathLen, &Errno) || Errno != 10014 )
    goto LABEL_7;
  v7 = (WCHAR *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(
                  SockPrivateHeap,
                  0,
                  2LL * ProviderDllPathLen[0]);
  v6 = v7;
  if ( !v7 )
  {
    LogError(8, L"Failed to allocate space for provider path");
    return 8;
  }
  if ( WSCGetProviderPath(a3, v7, ProviderDllPathLen, &Errno) )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v6);
    LogError((unsigned int)Errno, L"Failed to get provider path");
    return (unsigned int)Errno;
  }
  else
  {
LABEL_7:
    v9 = lstrcmpW(v6, L"%SystemRoot%\\system32\\mswsock.dll");
    Errno = v9;
    if ( v6 != szProviderDllPath )
    {
      RtlFreeHeap(SockPrivateHeap, 0, v6);
      v9 = Errno;
    }
    if ( v9 )
    {
      v10 = 2;
      v11 = 0;
      Errno = 2;
      while ( v11 < a2 )
      {
        v12 = a1 + 628LL * v11;
        v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)(v12 + 20);
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)(v12 + 20) )
          v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)(v12 + 28);
        v14 = v11 + 1;
        if ( !v13 )
        {
          v15 = v11 + 1;
          if ( v14 < a2 )
          {
            v16 = 4;
            v17 = v14;
            do
            {
              v18 = 628 * v17;
              v19 = *(_QWORD *)&a3->Data1 - *(_QWORD *)(628 * v17 + a1 + 20);
              if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)(628 * v17 + a1 + 20) )
                v19 = *(_QWORD *)a3->Data4 - *(_QWORD *)(v18 + a1 + 28);
              if ( !v19 )
              {
                if ( v15 != v14 )
                {
                  v20 = v60;
                  v21 = (_OWORD *)(a1 + 628LL * v15);
                  v22 = v21;
                  do
                  {
                    v23 = v22[1];
                    *v20 = *v22;
                    v24 = v22[2];
                    v20[1] = v23;
                    v25 = v22[3];
                    v20[2] = v24;
                    v26 = v22[4];
                    v20[3] = v25;
                    v27 = v22[5];
                    v20[4] = v26;
                    v28 = v22[6];
                    v20[5] = v27;
                    v29 = v22[7];
                    v22 += 8;
                    v20[6] = v28;
                    v20[7] = v29;
                    v20 += 8;
                    --v16;
                  }
                  while ( v16 );
                  v16 = 4;
                  v30 = v22[1];
                  *v20 = *v22;
                  v31 = v22[2];
                  v20[1] = v30;
                  v32 = v22[3];
                  v20[2] = v31;
                  v33 = v22[4];
                  v20[3] = v32;
                  v34 = v22[5];
                  v20[4] = v33;
                  v35 = v22[6];
                  v36 = *((_DWORD *)v22 + 28);
                  v20[5] = v34;
                  v20[6] = v35;
                  *((_DWORD *)v20 + 28) = v36;
                  v37 = (_OWORD *)(v18 + a1);
                  v38 = (_OWORD *)(v18 + a1);
                  v39 = 4;
                  do
                  {
                    *v21 = *v38;
                    v21[1] = v38[1];
                    v21[2] = v38[2];
                    v21[3] = v38[3];
                    v21[4] = v38[4];
                    v21[5] = v38[5];
                    v21[6] = v38[6];
                    v40 = v38[7];
                    v38 += 8;
                    v21[7] = v40;
                    v21 += 8;
                    --v39;
                  }
                  while ( v39 );
                  *v21 = *v38;
                  v21[1] = v38[1];
                  v21[2] = v38[2];
                  v21[3] = v38[3];
                  v21[4] = v38[4];
                  v21[5] = v38[5];
                  v21[6] = v38[6];
                  *((_DWORD *)v21 + 28) = *((_DWORD *)v38 + 28);
                  v41 = v60;
                  v42 = 4;
                  do
                  {
                    v43 = v41[1];
                    *v37 = *v41;
                    v44 = v41[2];
                    v37[1] = v43;
                    v45 = v41[3];
                    v37[2] = v44;
                    v46 = v41[4];
                    v37[3] = v45;
                    v47 = v41[5];
                    v37[4] = v46;
                    v48 = v41[6];
                    v37[5] = v47;
                    v49 = v41[7];
                    v41 += 8;
                    v37[6] = v48;
                    v37[7] = v49;
                    v37 += 8;
                    --v42;
                  }
                  while ( v42 );
                  v50 = v41[1];
                  *v37 = *v41;
                  v51 = v41[2];
                  v37[1] = v50;
                  v52 = v41[3];
                  v37[2] = v51;
                  v53 = v41[4];
                  v37[3] = v52;
                  v54 = v41[5];
                  v37[4] = v53;
                  v55 = v41[6];
                  v56 = *((_DWORD *)v41 + 28);
                  v37[5] = v54;
                  v37[6] = v55;
                  *((_DWORD *)v37 + 28) = v56;
                }
                ++v15;
              }
              ++v14;
              ++v17;
            }
            while ( v14 < a2 );
          }
          v57 = v15 - v11;
          if ( !WSCUpdateProvider(
                  a3,
                  L"%SystemRoot%\\system32\\mswsock.dll",
                  (const LPWSAPROTOCOL_INFOW)v12,
                  v57,
                  &Errno) )
            Errno = 0;
          if ( WSCUpdateProvider32(
                 a3,
                 L"%SystemRoot%\\system32\\mswsock.dll",
                 (const LPWSAPROTOCOL_INFOW)v12,
                 v57,
                 &Errno) )
          {
            return (unsigned int)Errno;
          }
          else
          {
            return 0;
          }
        }
        ++v11;
      }
      return v10;
    }
    else
    {
      return 1056;
    }
  }
}

```

## disassembly

```asm
0x180035f4c  mov     [rsp-8+arg_8], rbx
0x180035f51  push    rbp
0x180035f52  push    rsi
0x180035f53  push    rdi
0x180035f54  push    r12
0x180035f56  push    r13
0x180035f58  push    r14
0x180035f5a  push    r15
0x180035f5c  lea     rbp, [rsp-3E0h]
0x180035f64  sub     rsp, 4E0h
0x180035f6b  mov     rax, cs:__security_cookie
0x180035f72  xor     rax, rsp
0x180035f75  mov     [rbp+410h+var_40], rax
0x180035f7c  mov     rdi, r8
0x180035f7f  mov     [rsp+510h+Errno], 0
0x180035f87  mov     r12d, edx
0x180035f8a  mov     [rsp+510h+ProviderDllPathLen], 105h
0x180035f92  mov     r14, rcx
0x180035f95  lea     r9, [rsp+510h+Errno]; lpErrno
0x180035f9a  mov     rcx, rdi; lpProviderId
0x180035f9d  lea     r8, [rsp+510h+ProviderDllPathLen]; lpProviderDllPathLen
0x180035fa2  lea     rdx, [rbp+410h+szProviderDllPath]; lpszProviderDllPath
0x180035fa9  lea     rbx, [rbp+410h+szProviderDllPath]
0x180035fb0  call    cs:__imp_WSCGetProviderPath
0x180035fb7  nop     dword ptr [rax+rax+00h]
0x180035fbc  test    eax, eax
0x180035fbe  jz      loc_180036060
0x180035fc4  cmp     [rsp+510h+Errno], 271Eh
0x180035fcc  jnz     loc_180036060
0x180035fd2  movsxd  r8, [rsp+510h+ProviderDllPathLen]
0x180035fd7  xor     edx, edx
0x180035fd9  mov     rcx, cs:SockPrivateHeap
0x180035fe0  add     r8, r8
0x180035fe3  mov     rax, cs:SockAllocateHeapRoutine
0x180035fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fef  mov     rbx, rax
0x180035ff2  test    rax, rax
0x180035ff5  jnz     short loc_18003600F
0x180035ff7  lea     ebx, [rax+8]
0x180035ffa  mov     ecx, ebx
0x180035ffc  lea     rdx, aFailedToAlloca_7; "Failed to allocate space for provider p"...
0x180036003  call    LogError
0x180036008  mov     eax, ebx
0x18003600a  jmp     loc_18003636A
0x18003600f  lea     r9, [rsp+510h+Errno]; lpErrno
0x180036014  mov     rdx, rbx; lpszProviderDllPath
0x180036017  lea     r8, [rsp+510h+ProviderDllPathLen]; lpProviderDllPathLen
0x18003601c  mov     rcx, rdi; lpProviderId
0x18003601f  call    cs:__imp_WSCGetProviderPath
0x180036026  nop     dword ptr [rax+rax+00h]
0x18003602b  test    eax, eax
0x18003602d  jz      short loc_180036060
0x18003602f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180036036  mov     r8, rbx; P
0x180036039  xor     edx, edx; Flags
0x18003603b  call    cs:__imp_RtlFreeHeap
0x180036042  nop     dword ptr [rax+rax+00h]
0x180036047  mov     ecx, [rsp+510h+Errno]
0x18003604b  lea     rdx, aFailedToGetPro; "Failed to get provider path"
0x180036052  call    LogError
0x180036057  mov     eax, [rsp+510h+Errno]
0x18003605b  jmp     loc_18003636A
0x180036060  lea     rdx, szProviderDllPath; "%SystemRoot%\\system32\\mswsock.dll"
0x180036067  mov     rcx, rbx; lpString1
0x18003606a  call    cs:__imp_lstrcmpW
0x180036071  nop     dword ptr [rax+rax+00h]
0x180036076  lea     rcx, [rbp+410h+szProviderDllPath]
0x18003607d  mov     [rsp+510h+Errno], eax
0x180036081  cmp     rbx, rcx
0x180036084  jz      short loc_1800360A2
0x180036086  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003608d  mov     r8, rbx; P
0x180036090  xor     edx, edx; Flags
0x180036092  call    cs:__imp_RtlFreeHeap
0x180036099  nop     dword ptr [rax+rax+00h]
0x18003609e  mov     eax, [rsp+510h+Errno]
0x1800360a2  test    eax, eax
0x1800360a4  jnz     short loc_1800360B0
0x1800360a6  mov     eax, 420h
0x1800360ab  jmp     loc_18003636A
0x1800360b0  mov     edx, 2
0x1800360b5  xor     r9d, r9d
0x1800360b8  mov     [rsp+510h+Errno], edx
0x1800360bc  cmp     r9d, r12d
0x1800360bf  jnb     loc_180036368
0x1800360c5  mov     eax, r9d
0x1800360c8  imul    rsi, rax, 274h
0x1800360cf  mov     rax, [rdi]
0x1800360d2  add     rsi, r14
0x1800360d5  sub     rax, [rsi+14h]
0x1800360d9  jnz     short loc_1800360E3
0x1800360db  mov     rax, [rdi+8]
0x1800360df  sub     rax, [rsi+1Ch]
0x1800360e3  lea     r8d, [r9+1]
0x1800360e7  test    rax, rax
0x1800360ea  jz      short loc_1800360F1
0x1800360ec  mov     r9d, r8d
0x1800360ef  jmp     short loc_1800360BC
0x1800360f1  mov     ebx, r8d
0x1800360f4  cmp     r8d, r12d
0x1800360f7  jnb     loc_180036305
0x1800360fd  mov     r15d, 4
0x180036103  mov     r11d, r8d
0x180036106  lea     r13d, [r15+7Ch]
0x18003610a  mov     rax, [rdi]
0x18003610d  imul    r10, r11, 274h
0x180036114  sub     rax, [r10+r14+14h]
0x180036119  jnz     short loc_180036124
0x18003611b  mov     rax, [rdi+8]
0x18003611f  sub     rax, [r10+r14+1Ch]
0x180036124  test    rax, rax
0x180036127  jnz     loc_1800362F6
0x18003612d  cmp     ebx, r8d
0x180036130  jz      loc_1800362F4
0x180036136  mov     eax, ebx
0x180036138  lea     rcx, [rsp+510h+var_4D0]
0x18003613d  imul    rdx, rax, 274h
0x180036144  add     rdx, r14
0x180036147  mov     rax, rdx
0x18003614a  movups  xmm0, xmmword ptr [rax]
0x18003614d  movups  xmm1, xmmword ptr [rax+10h]
0x180036151  movups  xmmword ptr [rcx], xmm0
0x180036154  movups  xmm0, xmmword ptr [rax+20h]
0x180036158  movups  xmmword ptr [rcx+10h], xmm1
0x18003615c  movups  xmm1, xmmword ptr [rax+30h]
0x180036160  movups  xmmword ptr [rcx+20h], xmm0
0x180036164  movups  xmm0, xmmword ptr [rax+40h]
0x180036168  movups  xmmword ptr [rcx+30h], xmm1
0x18003616c  movups  xmm1, xmmword ptr [rax+50h]
0x180036170  movups  xmmword ptr [rcx+40h], xmm0
0x180036174  movups  xmm0, xmmword ptr [rax+60h]
0x180036178  movups  xmmword ptr [rcx+50h], xmm1
0x18003617c  movups  xmm1, xmmword ptr [rax+70h]
0x180036180  add     rax, r13
0x180036183  movups  xmmword ptr [rcx+60h], xmm0
0x180036187  movups  xmmword ptr [rcx+70h], xmm1
0x18003618b  add     rcx, r13
0x18003618e  sub     r15, 1
0x180036192  jnz     short loc_18003614A
0x180036194  movups  xmm0, xmmword ptr [rax]
0x180036197  mov     r15d, 4
0x18003619d  movups  xmm1, xmmword ptr [rax+10h]
0x1800361a1  movups  xmmword ptr [rcx], xmm0
0x1800361a4  movups  xmm0, xmmword ptr [rax+20h]
0x1800361a8  movups  xmmword ptr [rcx+10h], xmm1
0x1800361ac  movups  xmm1, xmmword ptr [rax+30h]
0x1800361b0  movups  xmmword ptr [rcx+20h], xmm0
0x1800361b4  movups  xmm0, xmmword ptr [rax+40h]
0x1800361b8  movups  xmmword ptr [rcx+30h], xmm1
0x1800361bc  movups  xmm1, xmmword ptr [rax+50h]
0x1800361c0  movups  xmmword ptr [rcx+40h], xmm0
0x1800361c4  movups  xmm0, xmmword ptr [rax+60h]
0x1800361c8  mov     eax, [rax+70h]
0x1800361cb  movups  xmmword ptr [rcx+50h], xmm1
0x1800361cf  movups  xmmword ptr [rcx+60h], xmm0
0x1800361d3  mov     [rcx+70h], eax
0x1800361d6  lea     rcx, [r10+r14]
0x1800361da  mov     rax, rcx
0x1800361dd  mov     r10d, r15d
0x1800361e0  movups  xmm0, xmmword ptr [rax]
0x1800361e3  movups  xmmword ptr [rdx], xmm0
0x1800361e6  movups  xmm1, xmmword ptr [rax+10h]
0x1800361ea  movups  xmmword ptr [rdx+10h], xmm1
0x1800361ee  movups  xmm0, xmmword ptr [rax+20h]
0x1800361f2  movups  xmmword ptr [rdx+20h], xmm0
0x1800361f6  movups  xmm1, xmmword ptr [rax+30h]
0x1800361fa  movups  xmmword ptr [rdx+30h], xmm1
0x1800361fe  movups  xmm0, xmmword ptr [rax+40h]
0x180036202  movups  xmmword ptr [rdx+40h], xmm0
0x180036206  movups  xmm1, xmmword ptr [rax+50h]
0x18003620a  movups  xmmword ptr [rdx+50h], xmm1
0x18003620e  movups  xmm0, xmmword ptr [rax+60h]
0x180036212  movups  xmmword ptr [rdx+60h], xmm0
0x180036216  movups  xmm1, xmmword ptr [rax+70h]
0x18003621a  add     rax, r13
0x18003621d  movups  xmmword ptr [rdx+70h], xmm1
0x180036221  add     rdx, r13
0x180036224  sub     r10, 1
0x180036228  jnz     short loc_1800361E0
0x18003622a  movups  xmm0, xmmword ptr [rax]
0x18003622d  movups  xmmword ptr [rdx], xmm0
0x180036230  movups  xmm1, xmmword ptr [rax+10h]
0x180036234  movups  xmmword ptr [rdx+10h], xmm1
0x180036238  movups  xmm0, xmmword ptr [rax+20h]
0x18003623c  movups  xmmword ptr [rdx+20h], xmm0
0x180036240  movups  xmm1, xmmword ptr [rax+30h]
0x180036244  movups  xmmword ptr [rdx+30h], xmm1
0x180036248  movups  xmm0, xmmword ptr [rax+40h]
0x18003624c  movups  xmmword ptr [rdx+40h], xmm0
0x180036250  movups  xmm1, xmmword ptr [rax+50h]
0x180036254  movups  xmmword ptr [rdx+50h], xmm1
0x180036258  movups  xmm0, xmmword ptr [rax+60h]
0x18003625c  movups  xmmword ptr [rdx+60h], xmm0
0x180036260  mov     eax, [rax+70h]
0x180036263  mov     [rdx+70h], eax
0x180036266  lea     rax, [rsp+510h+var_4D0]
0x18003626b  mov     rdx, r15
0x18003626e  movups  xmm0, xmmword ptr [rax]
0x180036271  movups  xmm1, xmmword ptr [rax+10h]
0x180036275  movups  xmmword ptr [rcx], xmm0
0x180036278  movups  xmm0, xmmword ptr [rax+20h]
0x18003627c  movups  xmmword ptr [rcx+10h], xmm1
0x180036280  movups  xmm1, xmmword ptr [rax+30h]
0x180036284  movups  xmmword ptr [rcx+20h], xmm0
0x180036288  movups  xmm0, xmmword ptr [rax+40h]
0x18003628c  movups  xmmword ptr [rcx+30h], xmm1
0x180036290  movups  xmm1, xmmword ptr [rax+50h]
0x180036294  movups  xmmword ptr [rcx+40h], xmm0
0x180036298  movups  xmm0, xmmword ptr [rax+60h]
0x18003629c  movups  xmmword ptr [rcx+50h], xmm1
0x1800362a0  movups  xmm1, xmmword ptr [rax+70h]
0x1800362a4  add     rax, r13
0x1800362a7  movups  xmmword ptr [rcx+60h], xmm0
0x1800362ab  movups  xmmword ptr [rcx+70h], xmm1
0x1800362af  add     rcx, r13
0x1800362b2  sub     rdx, 1
0x1800362b6  jnz     short loc_18003626E
0x1800362b8  movups  xmm0, xmmword ptr [rax]
0x1800362bb  movups  xmm1, xmmword ptr [rax+10h]
0x1800362bf  movups  xmmword ptr [rcx], xmm0
0x1800362c2  movups  xmm0, xmmword ptr [rax+20h]
0x1800362c6  movups  xmmword ptr [rcx+10h], xmm1
0x1800362ca  movups  xmm1, xmmword ptr [rax+30h]
0x1800362ce  movups  xmmword ptr [rcx+20h], xmm0
0x1800362d2  movups  xmm0, xmmword ptr [rax+40h]
0x1800362d6  movups  xmmword ptr [rcx+30h], xmm1
0x1800362da  movups  xmm1, xmmword ptr [rax+50h]
0x1800362de  movups  xmmword ptr [rcx+40h], xmm0
0x1800362e2  movups  xmm0, xmmword ptr [rax+60h]
0x1800362e6  mov     eax, [rax+70h]
0x1800362e9  movups  xmmword ptr [rcx+50h], xmm1
0x1800362ed  movups  xmmword ptr [rcx+60h], xmm0
0x1800362f1  mov     [rcx+70h], eax
0x1800362f4  inc     ebx
0x1800362f6  inc     r8d
0x1800362f9  inc     r11
0x1800362fc  cmp     r8d, r12d
0x1800362ff  jb      loc_18003610A
0x180036305  sub     ebx, r9d
0x180036308  lea     rax, [rsp+510h+Errno]
0x18003630d  mov     r9d, ebx; dwNumberOfEntries
0x180036310  mov     [rsp+510h+lpErrno], rax; lpErrno
0x180036315  mov     r8, rsi; lpProtocolInfoList
0x180036318  lea     rdx, szProviderDllPath; "%SystemRoot%\\system32\\mswsock.dll"
0x18003631f  mov     rcx, rdi; lpProviderId
0x180036322  call    cs:__imp_WSCUpdateProvider
0x180036329  nop     dword ptr [rax+rax+00h]
0x18003632e  test    eax, eax
0x180036330  jnz     short loc_180036336
0x180036332  mov     [rsp+510h+Errno], eax
0x180036336  lea     rax, [rsp+510h+Errno]
0x18003633b  mov     r9d, ebx; dwNumberOfEntries
0x18003633e  mov     r8, rsi; lpProtocolInfoList
0x180036341  mov     [rsp+510h+lpErrno], rax; lpErrno
0x180036346  lea     rdx, szProviderDllPath; "%SystemRoot%\\system32\\mswsock.dll"
0x18003634d  mov     rcx, rdi; lpProviderId
0x180036350  call    cs:__imp_WSCUpdateProvider32
0x180036357  nop     dword ptr [rax+rax+00h]
0x18003635c  test    eax, eax
0x18003635e  jnz     short loc_180036364
0x180036360  xor     edx, edx
0x180036362  jmp     short loc_180036368
0x180036364  mov     edx, [rsp+510h+Errno]
0x180036368  mov     eax, edx
0x18003636a  mov     rcx, [rbp+410h+var_40]
0x180036371  xor     rcx, rsp; StackCookie
0x180036374  call    __security_check_cookie
0x180036379  mov     rbx, [rsp+510h+arg_8]
0x180036381  add     rsp, 4E0h
0x180036388  pop     r15
0x18003638a  pop     r14
0x18003638c  pop     r13
0x18003638e  pop     r12
0x180036390  pop     rdi
0x180036391  pop     rsi
0x180036392  pop     rbp
0x180036393  retn
```
