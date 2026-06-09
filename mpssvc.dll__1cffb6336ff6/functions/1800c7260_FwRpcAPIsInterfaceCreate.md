# FwRpcAPIsInterfaceCreate

- ea: `0x1800c7260`
- end: `0x1800c77ca`
- name: `FwRpcAPIsInterfaceCreate`
- size: `1386`
- prototype: `__int64 __usercall@<rax>(LPCWSTR StringSecurityDescriptor@<rcx>, RPC_IF_HANDLE IfSpec, int, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bf240`
- `0x1800c6110`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800c7164`
- `0x1800c7260`
- `0x1800c77d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c741e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c74e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c741e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c74e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7783`
- `RPCRT4!RpcServerInqBindings` at `0x1800c76ed`
- `RPCRT4!RpcServerInqBindings` at `0x1800c76ed`
- `RPCRT4!RpcEpRegisterW` at `0x1800c773a`
- `RPCRT4!RpcEpRegisterW` at `0x1800c773a`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800c76a2`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800c76a2`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800c75f9`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800c75f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c7414`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c7475`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c74da`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c7414`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c7475`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c74da`
- `fwbase!FwSizeTMultiply` at `0x1800c7535`
- `fwbase!FwSizeTMultiply` at `0x1800c7535`
- `fwbase!FwStringCopy` at `0x1800c75d4`
- `fwbase!FwStringCopy` at `0x1800c75d4`
- `fwbase!FwAlloc` at `0x1800c7571`
- `fwbase!FwAlloc` at `0x1800c7571`

## pseudocode

```c
__int64 __fastcall FwRpcAPIsInterfaceCreate(
        LPCWSTR StringSecurityDescriptor,
        int a2,
        __int64 a3,
        _QWORD *a4,
        RPC_IF_HANDLE IfSpec,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  WCHAR *v9; // rax
  __int64 v11; // rdx
  const wchar_t *v13; // rcx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  WCHAR *v21; // rcx
  __int64 v22; // rdx
  const wchar_t *v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  int v33; // eax
  signed int v34; // ebx
  __int64 v35; // rcx
  __int64 v36; // rdx
  signed int v37; // eax
  signed int LastError; // eax
  signed int v39; // eax
  __int64 v40; // rax
  __int64 v41; // r14
  RPC_WSTR *v42; // rcx
  PSECURITY_DESCRIPTOR v43; // r8
  RPC_STATUS v44; // eax
  int v45; // eax
  RPC_STATUS v46; // eax
  RPC_STATUS v47; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v52[160]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR StringSecurityDescriptora[192]; // [rsp+1A0h] [rbp+A0h] BYREF

  v9 = StringSecurityDescriptora;
  v11 = 3;
  v13 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1)(A;;GR;;;S-1-15-3-2)(A"
         ";;GR;;;S-1-15-3-3)(A;;GR;;;S-1-15-3-4214768333-1334025770-122408079-3919188833)";
  v51 = 0;
  do
  {
    v14 = *((_OWORD *)v13 + 1);
    *(_OWORD *)v9 = *(_OWORD *)v13;
    v15 = *((_OWORD *)v13 + 2);
    *((_OWORD *)v9 + 1) = v14;
    v16 = *((_OWORD *)v13 + 3);
    *((_OWORD *)v9 + 2) = v15;
    v17 = *((_OWORD *)v13 + 4);
    *((_OWORD *)v9 + 3) = v16;
    v18 = *((_OWORD *)v13 + 5);
    *((_OWORD *)v9 + 4) = v17;
    v19 = *((_OWORD *)v13 + 6);
    *((_OWORD *)v9 + 5) = v18;
    v20 = *((_OWORD *)v13 + 7);
    v13 += 64;
    *((_OWORD *)v9 + 6) = v19;
    *((_OWORD *)v9 + 7) = v20;
    v9 += 64;
    --v11;
  }
  while ( v11 );
  SecurityDescriptor = 0;
  v21 = v52;
  v22 = 2;
  v23 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-2-2668987081-2569674137-3179742174-427"
         "0009011-3803107086-2981642713-3349210623)";
  do
  {
    v24 = *((_OWORD *)v23 + 1);
    *(_OWORD *)v21 = *(_OWORD *)v23;
    v25 = *((_OWORD *)v23 + 2);
    *((_OWORD *)v21 + 1) = v24;
    v26 = *((_OWORD *)v23 + 3);
    *((_OWORD *)v21 + 2) = v25;
    v27 = *((_OWORD *)v23 + 4);
    *((_OWORD *)v21 + 3) = v26;
    v28 = *((_OWORD *)v23 + 5);
    *((_OWORD *)v21 + 4) = v27;
    v29 = *((_OWORD *)v23 + 6);
    *((_OWORD *)v21 + 5) = v28;
    v30 = *((_OWORD *)v23 + 7);
    v23 += 64;
    *((_OWORD *)v21 + 6) = v29;
    *((_OWORD *)v21 + 7) = v30;
    v21 += 64;
    --v22;
  }
  while ( v22 );
  v31 = *((_OWORD *)v23 + 1);
  *(_OWORD *)v21 = *(_OWORD *)v23;
  v32 = *((_OWORD *)v23 + 2);
  v33 = *((_DWORD *)v23 + 12);
  *((_OWORD *)v21 + 1) = v31;
  *((_OWORD *)v21 + 2) = v32;
  *((_DWORD *)v21 + 12) = v33;
  *(_OWORD *)a9 = 0;
  *(_OWORD *)(a9 + 16) = 0;
  *(_OWORD *)(a9 + 32) = 0;
  *(_QWORD *)(a9 + 48) = 0;
  *(_QWORD *)a9 = IfSpec;
  v34 = FwRpcAPIsRegisterAuthInfo();
  if ( v34 >= 0 )
  {
    if ( !StringSecurityDescriptor
      || ConvertStringSecurityDescriptorToSecurityDescriptorW(
           StringSecurityDescriptor,
           1u,
           (PSECURITY_DESCRIPTOR *)(a9 + 8),
           0) )
    {
      if ( a8 == 2 )
      {
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                StringSecurityDescriptora,
                1u,
                &SecurityDescriptor,
                0) )
        {
          LastError = GetLastError();
          v34 = LastError;
          if ( LastError > 0 )
            v34 = (unsigned __int16)LastError | 0x80070000;
          v35 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v36 = 14;
            goto LABEL_9;
          }
          goto LABEL_74;
        }
      }
      else if ( a8 == 1 && !ConvertStringSecurityDescriptorToSecurityDescriptorW(v52, 1u, &SecurityDescriptor, 0) )
      {
        v39 = GetLastError();
        v34 = v39;
        if ( v39 > 0 )
          v34 = (unsigned __int16)v39 | 0x80070000;
        v35 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v36 = 15;
          goto LABEL_9;
        }
        goto LABEL_74;
      }
      *(_DWORD *)(a9 + 16) = a2;
      v34 = FwSizeTMultiply(1, 8, &v51);
      if ( v34 >= 0 )
      {
        v40 = FwAlloc(v51);
        *(_QWORD *)(a9 + 32) = v40;
        if ( v40 )
        {
          v41 = 0;
          while ( !v41 )
          {
            v34 = FwStringCopy(*a4, *(_QWORD *)(a9 + 32));
            if ( v34 < 0 )
            {
              v35 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v36 = 18;
                goto LABEL_9;
              }
              goto LABEL_74;
            }
            v42 = *(RPC_WSTR **)(a9 + 32);
            v41 = 1;
            v43 = SecurityDescriptor;
            *(_QWORD *)(a9 + 24) = 1;
            v44 = RpcServerUseProtseqW(*v42, 0xAu, v43);
            if ( v44 )
            {
              if ( v44 > 0 )
                v34 = (unsigned __int16)v44 | 0x80070000;
              else
                v34 = v44;
              v35 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v36 = 19;
                goto LABEL_9;
              }
              goto LABEL_74;
            }
          }
          v45 = RpcServerRegisterIf3(IfSpec, 0, 0, a2 != 0 ? 9 : 41, 1234, 0, a7, SecurityDescriptor);
          if ( v45 )
          {
            if ( v45 > 0 )
              v34 = (unsigned __int16)v45 | 0x80070000;
            else
              v34 = v45;
            v35 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v36 = 20;
              goto LABEL_9;
            }
          }
          else
          {
            *(_DWORD *)(a9 + 52) = 1;
            v46 = RpcServerInqBindings((RPC_BINDING_VECTOR **)(a9 + 40));
            if ( v46 )
            {
              if ( v46 > 0 )
                v34 = (unsigned __int16)v46 | 0x80070000;
              else
                v34 = v46;
              v35 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v36 = 21;
                goto LABEL_9;
              }
            }
            else
            {
              v47 = RpcEpRegisterW(IfSpec, *(RPC_BINDING_VECTOR **)(a9 + 40), 0, (RPC_WSTR)L"Fw APIs");
              if ( v47 )
              {
                if ( v47 > 0 )
                  v34 = (unsigned __int16)v47 | 0x80070000;
                else
                  v34 = v47;
                v35 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v36 = 22;
                  goto LABEL_9;
                }
              }
              else
              {
                *(_DWORD *)(a9 + 48) = 1;
              }
            }
          }
        }
        else
        {
          v34 = -2147024882;
          v35 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v36 = 17;
            goto LABEL_9;
          }
        }
      }
      else
      {
        v35 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v36 = 16;
          goto LABEL_9;
        }
      }
      goto LABEL_74;
    }
    v37 = GetLastError();
    v34 = v37;
    if ( v37 > 0 )
      v34 = (unsigned __int16)v37 | 0x80070000;
    v35 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v36 = 13;
      goto LABEL_9;
    }
  }
  else
  {
    v35 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v36 = 12;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v35 + 16), v36, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v34);
    }
  }
LABEL_74:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v34 < 0 )
    FwRpcAPIsInterfaceDestroy(a9);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1800c7260  mov     [rsp-8+arg_8], rbx
0x1800c7265  push    rbp
0x1800c7266  push    rsi
0x1800c7267  push    rdi
0x1800c7268  push    r12
0x1800c726a  push    r13
0x1800c726c  push    r14
0x1800c726e  push    r15
0x1800c7270  lea     rbp, [rsp-230h]
0x1800c7278  sub     rsp, 330h
0x1800c727f  mov     rax, cs:__security_cookie
0x1800c7286  xor     rax, rsp
0x1800c7289  mov     [rbp+260h+var_40], rax
0x1800c7290  mov     r15, [rbp+260h+arg_30]
0x1800c7297  lea     rax, [rbp+260h+StringSecurityDescriptor]
0x1800c729e  mov     rsi, [rbp+260h+arg_40]
0x1800c72a5  mov     r12d, edx
0x1800c72a8  mov     r13, [rbp+260h+IfSpec]
0x1800c72af  mov     edx, 3
0x1800c72b4  mov     r14, rcx
0x1800c72b7  mov     [rsp+360h+var_320], r9
0x1800c72bc  mov     [rsp+360h+var_318], r15
0x1800c72c1  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800c72c8  mov     [rsp+360h+var_308], 0
0x1800c72d1  lea     r8d, [rdx+7Dh]
0x1800c72d5  movups  xmm0, xmmword ptr [rcx]
0x1800c72d8  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c72dc  movups  xmmword ptr [rax], xmm0
0x1800c72df  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c72e3  movups  xmmword ptr [rax+10h], xmm1
0x1800c72e7  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c72eb  movups  xmmword ptr [rax+20h], xmm0
0x1800c72ef  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c72f3  movups  xmmword ptr [rax+30h], xmm1
0x1800c72f7  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c72fb  movups  xmmword ptr [rax+40h], xmm0
0x1800c72ff  movups  xmm0, xmmword ptr [rcx+60h]
0x1800c7303  movups  xmmword ptr [rax+50h], xmm1
0x1800c7307  movups  xmm1, xmmword ptr [rcx+70h]
0x1800c730b  add     rcx, r8
0x1800c730e  movups  xmmword ptr [rax+60h], xmm0
0x1800c7312  movups  xmmword ptr [rax+70h], xmm1
0x1800c7316  add     rax, r8
0x1800c7319  sub     rdx, 1
0x1800c731d  jnz     short loc_1800C72D5
0x1800c731f  mov     [rsp+360h+SecurityDescriptor], rdx
0x1800c7324  lea     rcx, [rsp+360h+var_300]
0x1800c7329  mov     edx, 2
0x1800c732e  lea     rax, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800c7335  movups  xmm0, xmmword ptr [rax]
0x1800c7338  movups  xmm1, xmmword ptr [rax+10h]
0x1800c733c  movups  xmmword ptr [rcx], xmm0
0x1800c733f  movups  xmm0, xmmword ptr [rax+20h]
0x1800c7343  movups  xmmword ptr [rcx+10h], xmm1
0x1800c7347  movups  xmm1, xmmword ptr [rax+30h]
0x1800c734b  movups  xmmword ptr [rcx+20h], xmm0
0x1800c734f  movups  xmm0, xmmword ptr [rax+40h]
0x1800c7353  movups  xmmword ptr [rcx+30h], xmm1
0x1800c7357  movups  xmm1, xmmword ptr [rax+50h]
0x1800c735b  movups  xmmword ptr [rcx+40h], xmm0
0x1800c735f  movups  xmm0, xmmword ptr [rax+60h]
0x1800c7363  movups  xmmword ptr [rcx+50h], xmm1
0x1800c7367  movups  xmm1, xmmword ptr [rax+70h]
0x1800c736b  add     rax, r8
0x1800c736e  movups  xmmword ptr [rcx+60h], xmm0
0x1800c7372  movups  xmmword ptr [rcx+70h], xmm1
0x1800c7376  add     rcx, r8
0x1800c7379  sub     rdx, 1
0x1800c737d  jnz     short loc_1800C7335
0x1800c737f  movups  xmm0, xmmword ptr [rax]
0x1800c7382  movups  xmm1, xmmword ptr [rax+10h]
0x1800c7386  movups  xmmword ptr [rcx], xmm0
0x1800c7389  movups  xmm0, xmmword ptr [rax+20h]
0x1800c738d  mov     eax, [rax+30h]
0x1800c7390  movups  xmmword ptr [rcx+10h], xmm1
0x1800c7394  movups  xmmword ptr [rcx+20h], xmm0
0x1800c7398  mov     [rcx+30h], eax
0x1800c739b  xor     eax, eax
0x1800c739d  xorps   xmm0, xmm0
0x1800c73a0  movups  xmmword ptr [rsi], xmm0
0x1800c73a3  movups  xmmword ptr [rsi+10h], xmm0
0x1800c73a7  movups  xmmword ptr [rsi+20h], xmm0
0x1800c73ab  mov     [rsi+30h], rax
0x1800c73af  mov     [rsi], r13
0x1800c73b2  call    ?FwRpcAPIsRegisterAuthInfo@@YAJXZ; FwRpcAPIsRegisterAuthInfo(void)
0x1800c73b7  mov     ebx, eax
0x1800c73b9  test    eax, eax
0x1800c73bb  jns     short loc_1800C73FE
0x1800c73bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c73c4  lea     rax, WPP_GLOBAL_Control
0x1800c73cb  cmp     rcx, rax
0x1800c73ce  jz      loc_1800C7779
0x1800c73d4  mov     edi, 1
0x1800c73d9  test    [rcx+1Ch], dil
0x1800c73dd  jz      loc_1800C7779
0x1800c73e3  lea     edx, [rdi+0Bh]
0x1800c73e6  mov     rcx, [rcx+10h]
0x1800c73ea  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800c73f1  mov     r9d, ebx
0x1800c73f4  call    WPP_SF_d
0x1800c73f9  jmp     loc_1800C7779
0x1800c73fe  mov     edi, 1
0x1800c7403  test    r14, r14
0x1800c7406  jz      short loc_1800C745B
0x1800c7408  lea     r8, [rsi+8]; SecurityDescriptor
0x1800c740c  xor     r9d, r9d; SecurityDescriptorSize
0x1800c740f  mov     edx, edi; StringSDRevision
0x1800c7411  mov     rcx, r14; StringSecurityDescriptor
0x1800c7414  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800c741a  test    eax, eax
0x1800c741c  jnz     short loc_1800C745B
0x1800c741e  call    cs:__imp_GetLastError
0x1800c7424  mov     ebx, eax
0x1800c7426  test    eax, eax
0x1800c7428  jle     short loc_1800C7433
0x1800c742a  movzx   ebx, ax
0x1800c742d  or      ebx, 80070000h
0x1800c7433  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c743a  lea     rax, WPP_GLOBAL_Control
0x1800c7441  cmp     rcx, rax
0x1800c7444  jz      loc_1800C7779
0x1800c744a  test    [rcx+1Ch], dil
0x1800c744e  jz      loc_1800C7779
0x1800c7454  mov     edx, 0Dh
0x1800c7459  jmp     short loc_1800C73E6
0x1800c745b  cmp     [rbp+260h+arg_38], 2
0x1800c7462  jnz     short loc_1800C74C3
0x1800c7464  xor     r9d, r9d; SecurityDescriptorSize
0x1800c7467  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800c746c  mov     edx, edi; StringSDRevision
0x1800c746e  lea     rcx, [rbp+260h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800c7475  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800c747b  test    eax, eax
0x1800c747d  jnz     loc_1800C7524
0x1800c7483  call    cs:__imp_GetLastError
0x1800c7489  mov     ebx, eax
0x1800c748b  test    eax, eax
0x1800c748d  jle     short loc_1800C7498
0x1800c748f  movzx   ebx, ax
0x1800c7492  or      ebx, 80070000h
0x1800c7498  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c749f  lea     rax, WPP_GLOBAL_Control
0x1800c74a6  cmp     rcx, rax
0x1800c74a9  jz      loc_1800C7779
0x1800c74af  test    [rcx+1Ch], dil
0x1800c74b3  jz      loc_1800C7779
0x1800c74b9  mov     edx, 0Eh
0x1800c74be  jmp     loc_1800C73E6
0x1800c74c3  cmp     [rbp+260h+arg_38], edi
0x1800c74c9  jnz     short loc_1800C7524
0x1800c74cb  xor     r9d, r9d; SecurityDescriptorSize
0x1800c74ce  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800c74d3  mov     edx, edi; StringSDRevision
0x1800c74d5  lea     rcx, [rsp+360h+var_300]; StringSecurityDescriptor
0x1800c74da  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800c74e0  test    eax, eax
0x1800c74e2  jnz     short loc_1800C7524
0x1800c74e4  call    cs:__imp_GetLastError
0x1800c74ea  mov     ebx, eax
0x1800c74ec  test    eax, eax
0x1800c74ee  jle     short loc_1800C74F9
0x1800c74f0  movzx   ebx, ax
0x1800c74f3  or      ebx, 80070000h
0x1800c74f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7500  lea     rax, WPP_GLOBAL_Control
0x1800c7507  cmp     rcx, rax
0x1800c750a  jz      loc_1800C7779
0x1800c7510  test    [rcx+1Ch], dil
0x1800c7514  jz      loc_1800C7779
0x1800c751a  mov     edx, 0Fh
0x1800c751f  jmp     loc_1800C73E6
0x1800c7524  lea     r8, [rsp+360h+var_308]
0x1800c7529  mov     [rsi+10h], r12d
0x1800c752d  mov     edx, 8
0x1800c7532  mov     rcx, rdi
0x1800c7535  call    cs:__imp_FwSizeTMultiply
0x1800c753b  mov     ebx, eax
0x1800c753d  test    eax, eax
0x1800c753f  jns     short loc_1800C756C
0x1800c7541  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7548  lea     rax, WPP_GLOBAL_Control
0x1800c754f  cmp     rcx, rax
0x1800c7552  jz      loc_1800C7779
0x1800c7558  test    [rcx+1Ch], dil
0x1800c755c  jz      loc_1800C7779
0x1800c7562  mov     edx, 10h
0x1800c7567  jmp     loc_1800C73E6
0x1800c756c  mov     rcx, [rsp+360h+var_308]
0x1800c7571  call    cs:__imp_FwAlloc
0x1800c7577  mov     [rsi+20h], rax
0x1800c757b  test    rax, rax
0x1800c757e  jnz     short loc_1800C75B0
0x1800c7580  mov     ebx, 8007000Eh
0x1800c7585  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c758c  lea     rax, WPP_GLOBAL_Control
0x1800c7593  cmp     rcx, rax
0x1800c7596  jz      loc_1800C7779
0x1800c759c  test    [rcx+1Ch], dil
0x1800c75a0  jz      loc_1800C7779
0x1800c75a6  mov     edx, 11h
0x1800c75ab  jmp     loc_1800C73E6
0x1800c75b0  xor     r14d, r14d
0x1800c75b3  cmp     r14, rdi
0x1800c75b6  jnb     loc_1800C7668
0x1800c75bc  mov     rax, [rsp+360h+var_320]
0x1800c75c1  lea     r15, ds:0[r14*8]
0x1800c75c9  mov     rdx, [rsi+20h]
0x1800c75cd  add     rdx, r15
0x1800c75d0  mov     rcx, [r15+rax]
0x1800c75d4  call    cs:__imp_FwStringCopy
0x1800c75da  mov     ebx, eax
0x1800c75dc  test    eax, eax
0x1800c75de  js      short loc_1800C763D
0x1800c75e0  mov     rcx, [rsi+20h]
0x1800c75e4  inc     r14
0x1800c75e7  mov     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800c75ec  mov     edx, 0Ah; MaxCalls
0x1800c75f1  mov     [rsi+18h], r14
0x1800c75f5  mov     rcx, [r15+rcx]; Protseq
0x1800c75f9  call    cs:__imp_RpcServerUseProtseqW
0x1800c75ff  test    eax, eax
0x1800c7601  jz      short loc_1800C75B3
0x1800c7603  jg      short loc_1800C7609
0x1800c7605  mov     ebx, eax
0x1800c7607  jmp     short loc_1800C7612
0x1800c7609  movzx   ebx, ax
0x1800c760c  or      ebx, 80070000h
0x1800c7612  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7619  lea     rax, WPP_GLOBAL_Control
0x1800c7620  cmp     rcx, rax
0x1800c7623  jz      loc_1800C7779
0x1800c7629  test    [rcx+1Ch], dil
0x1800c762d  jz      loc_1800C7779
0x1800c7633  mov     edx, 13h
0x1800c7638  jmp     loc_1800C73E6
0x1800c763d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7644  lea     rax, WPP_GLOBAL_Control
0x1800c764b  cmp     rcx, rax
0x1800c764e  jz      loc_1800C7779
0x1800c7654  test    [rcx+1Ch], dil
0x1800c7658  jz      loc_1800C7779
0x1800c765e  mov     edx, 12h
0x1800c7663  jmp     loc_1800C73E6
0x1800c7668  mov     rax, [rsp+360h+SecurityDescriptor]
0x1800c766d  neg     r12d
0x1800c7670  mov     [rsp+360h+var_328], rax
0x1800c7675  mov     rcx, r13
0x1800c7678  mov     rax, [rsp+360h+var_318]
0x1800c767d  sbb     r9d, r9d
0x1800c7680  mov     [rsp+360h+var_330], rax
0x1800c7685  and     r9d, 0FFFFFFE0h
0x1800c7689  add     r9d, 29h ; ')'
0x1800c768d  mov     [rsp+360h+var_338], 0
0x1800c7695  xor     r8d, r8d
0x1800c7698  mov     [rsp+360h+var_340], 4D2h
0x1800c76a0  xor     edx, edx
0x1800c76a2  call    cs:__imp_RpcServerRegisterIf3
0x1800c76a8  test    eax, eax
0x1800c76aa  jz      short loc_1800C76E6
0x1800c76ac  jg      short loc_1800C76B2
0x1800c76ae  mov     ebx, eax
0x1800c76b0  jmp     short loc_1800C76BB
0x1800c76b2  movzx   ebx, ax
0x1800c76b5  or      ebx, 80070000h
0x1800c76bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c76c2  lea     rax, WPP_GLOBAL_Control
0x1800c76c9  cmp     rcx, rax
0x1800c76cc  jz      loc_1800C7779
0x1800c76d2  test    [rcx+1Ch], dil
0x1800c76d6  jz      loc_1800C7779
0x1800c76dc  mov     edx, 14h
0x1800c76e1  jmp     loc_1800C73E6
0x1800c76e6  lea     rcx, [rsi+28h]; BindingVector
0x1800c76ea  mov     [rsi+34h], edi
0x1800c76ed  call    cs:__imp_RpcServerInqBindings
0x1800c76f3  test    eax, eax
0x1800c76f5  jz      short loc_1800C7729
0x1800c76f7  jg      short loc_1800C76FD
0x1800c76f9  mov     ebx, eax
0x1800c76fb  jmp     short loc_1800C7706
0x1800c76fd  movzx   ebx, ax
0x1800c7700  or      ebx, 80070000h
0x1800c7706  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c770d  lea     rax, WPP_GLOBAL_Control
0x1800c7714  cmp     rcx, rax
0x1800c7717  jz      short loc_1800C7779
0x1800c7719  test    [rcx+1Ch], dil
0x1800c771d  jz      short loc_1800C7779
0x1800c771f  mov     edx, 15h
0x1800c7724  jmp     loc_1800C73E6
0x1800c7729  mov     rdx, [rsi+28h]; BindingVector
0x1800c772d  lea     r9, Annotation; "Fw APIs"
0x1800c7734  xor     r8d, r8d; UuidVector
0x1800c7737  mov     rcx, r13; IfSpec
0x1800c773a  call    cs:__imp_RpcEpRegisterW
0x1800c7740  test    eax, eax
0x1800c7742  jz      short loc_1800C7776
0x1800c7744  jg      short loc_1800C774A
0x1800c7746  mov     ebx, eax
0x1800c7748  jmp     short loc_1800C7753
  ... truncated ...
```
