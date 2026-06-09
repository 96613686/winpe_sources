# FwRpcAPIsInterfaceCreate

- ea: `0x1800ce7b4`
- end: `0x1800ced76`
- name: `FwRpcAPIsInterfaceCreate`
- size: `1474`
- prototype: `__int64 __usercall@<rax>(LPCWSTR StringSecurityDescriptor@<rcx>, RPC_IF_HANDLE IfSpec, int, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c5f00`
- `0x1800cd610`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x1800ce6a4`
- `0x1800ce7b4`
- `0x1800ced7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cea59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cea59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ced28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ced28`
- `RPCRT4!RpcServerInqBindings` at `0x1800cec86`
- `RPCRT4!RpcServerInqBindings` at `0x1800cec86`
- `RPCRT4!RpcEpRegisterW` at `0x1800cecd9`
- `RPCRT4!RpcEpRegisterW` at `0x1800cecd9`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800cec35`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800cec35`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ceb86`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ceb86`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ce968`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ce9d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800cea49`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ce968`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ce9d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800cea49`
- `fwbase!FwSizeTMultiply` at `0x1800ceab0`
- `fwbase!FwSizeTMultiply` at `0x1800ceab0`
- `fwbase!FwStringCopy` at `0x1800ceb5b`
- `fwbase!FwStringCopy` at `0x1800ceb5b`
- `fwbase!FwAlloc` at `0x1800ceaf2`
- `fwbase!FwAlloc` at `0x1800ceaf2`

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
0x1800ce7b4  mov     [rsp-8+arg_8], rbx
0x1800ce7b9  push    rbp
0x1800ce7ba  push    rsi
0x1800ce7bb  push    rdi
0x1800ce7bc  push    r12
0x1800ce7be  push    r13
0x1800ce7c0  push    r14
0x1800ce7c2  push    r15
0x1800ce7c4  lea     rbp, [rsp-230h]
0x1800ce7cc  sub     rsp, 330h
0x1800ce7d3  mov     rax, cs:__security_cookie
0x1800ce7da  xor     rax, rsp
0x1800ce7dd  mov     [rbp+260h+var_40], rax
0x1800ce7e4  mov     r15, [rbp+260h+arg_30]
0x1800ce7eb  lea     rax, [rbp+260h+StringSecurityDescriptor]
0x1800ce7f2  mov     rsi, [rbp+260h+arg_40]
0x1800ce7f9  mov     r12d, edx
0x1800ce7fc  mov     r13, [rbp+260h+IfSpec]
0x1800ce803  mov     edx, 3
0x1800ce808  mov     r14, rcx
0x1800ce80b  mov     [rsp+360h+var_320], r9
0x1800ce810  mov     [rsp+360h+var_318], r15
0x1800ce815  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800ce81c  mov     [rsp+360h+var_308], 0
0x1800ce825  lea     r8d, [rdx+7Dh]
0x1800ce829  movups  xmm0, xmmword ptr [rcx]
0x1800ce82c  movups  xmm1, xmmword ptr [rcx+10h]
0x1800ce830  movups  xmmword ptr [rax], xmm0
0x1800ce833  movups  xmm0, xmmword ptr [rcx+20h]
0x1800ce837  movups  xmmword ptr [rax+10h], xmm1
0x1800ce83b  movups  xmm1, xmmword ptr [rcx+30h]
0x1800ce83f  movups  xmmword ptr [rax+20h], xmm0
0x1800ce843  movups  xmm0, xmmword ptr [rcx+40h]
0x1800ce847  movups  xmmword ptr [rax+30h], xmm1
0x1800ce84b  movups  xmm1, xmmword ptr [rcx+50h]
0x1800ce84f  movups  xmmword ptr [rax+40h], xmm0
0x1800ce853  movups  xmm0, xmmword ptr [rcx+60h]
0x1800ce857  movups  xmmword ptr [rax+50h], xmm1
0x1800ce85b  movups  xmm1, xmmword ptr [rcx+70h]
0x1800ce85f  add     rcx, r8
0x1800ce862  movups  xmmword ptr [rax+60h], xmm0
0x1800ce866  movups  xmmword ptr [rax+70h], xmm1
0x1800ce86a  add     rax, r8
0x1800ce86d  sub     rdx, 1
0x1800ce871  jnz     short loc_1800CE829
0x1800ce873  mov     [rsp+360h+SecurityDescriptor], rdx
0x1800ce878  lea     rcx, [rsp+360h+var_300]
0x1800ce87d  mov     edx, 2
0x1800ce882  lea     rax, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800ce889  movups  xmm0, xmmword ptr [rax]
0x1800ce88c  movups  xmm1, xmmword ptr [rax+10h]
0x1800ce890  movups  xmmword ptr [rcx], xmm0
0x1800ce893  movups  xmm0, xmmword ptr [rax+20h]
0x1800ce897  movups  xmmword ptr [rcx+10h], xmm1
0x1800ce89b  movups  xmm1, xmmword ptr [rax+30h]
0x1800ce89f  movups  xmmword ptr [rcx+20h], xmm0
0x1800ce8a3  movups  xmm0, xmmword ptr [rax+40h]
0x1800ce8a7  movups  xmmword ptr [rcx+30h], xmm1
0x1800ce8ab  movups  xmm1, xmmword ptr [rax+50h]
0x1800ce8af  movups  xmmword ptr [rcx+40h], xmm0
0x1800ce8b3  movups  xmm0, xmmword ptr [rax+60h]
0x1800ce8b7  movups  xmmword ptr [rcx+50h], xmm1
0x1800ce8bb  movups  xmm1, xmmword ptr [rax+70h]
0x1800ce8bf  add     rax, r8
0x1800ce8c2  movups  xmmword ptr [rcx+60h], xmm0
0x1800ce8c6  movups  xmmword ptr [rcx+70h], xmm1
0x1800ce8ca  add     rcx, r8
0x1800ce8cd  sub     rdx, 1
0x1800ce8d1  jnz     short loc_1800CE889
0x1800ce8d3  movups  xmm0, xmmword ptr [rax]
0x1800ce8d6  movups  xmm1, xmmword ptr [rax+10h]
0x1800ce8da  movups  xmmword ptr [rcx], xmm0
0x1800ce8dd  movups  xmm0, xmmword ptr [rax+20h]
0x1800ce8e1  mov     eax, [rax+30h]
0x1800ce8e4  movups  xmmword ptr [rcx+10h], xmm1
0x1800ce8e8  movups  xmmword ptr [rcx+20h], xmm0
0x1800ce8ec  mov     [rcx+30h], eax
0x1800ce8ef  xor     eax, eax
0x1800ce8f1  xorps   xmm0, xmm0
0x1800ce8f4  movups  xmmword ptr [rsi], xmm0
0x1800ce8f7  movups  xmmword ptr [rsi+10h], xmm0
0x1800ce8fb  movups  xmmword ptr [rsi+20h], xmm0
0x1800ce8ff  mov     [rsi+30h], rax
0x1800ce903  mov     [rsi], r13
0x1800ce906  call    ?FwRpcAPIsRegisterAuthInfo@@YAJXZ; FwRpcAPIsRegisterAuthInfo(void)
0x1800ce90b  mov     ebx, eax
0x1800ce90d  test    eax, eax
0x1800ce90f  jns     short loc_1800CE952
0x1800ce911  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce918  lea     rax, WPP_GLOBAL_Control
0x1800ce91f  cmp     rcx, rax
0x1800ce922  jz      loc_1800CED1E
0x1800ce928  mov     edi, 1
0x1800ce92d  test    [rcx+1Ch], dil
0x1800ce931  jz      loc_1800CED1E
0x1800ce937  lea     edx, [rdi+0Bh]
0x1800ce93a  mov     rcx, [rcx+10h]
0x1800ce93e  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800ce945  mov     r9d, ebx
0x1800ce948  call    WPP_SF_d
0x1800ce94d  jmp     loc_1800CED1E
0x1800ce952  mov     edi, 1
0x1800ce957  test    r14, r14
0x1800ce95a  jz      short loc_1800CE9BE
0x1800ce95c  lea     r8, [rsi+8]; SecurityDescriptor
0x1800ce960  xor     r9d, r9d; SecurityDescriptorSize
0x1800ce963  mov     edx, edi; StringSDRevision
0x1800ce965  mov     rcx, r14; StringSecurityDescriptor
0x1800ce968  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ce96f  nop     dword ptr [rax+rax+00h]
0x1800ce974  test    eax, eax
0x1800ce976  jnz     short loc_1800CE9BE
0x1800ce978  call    cs:__imp_GetLastError
0x1800ce97f  nop     dword ptr [rax+rax+00h]
0x1800ce984  mov     ebx, eax
0x1800ce986  test    eax, eax
0x1800ce988  jle     short loc_1800CE993
0x1800ce98a  movzx   ebx, ax
0x1800ce98d  or      ebx, 80070000h
0x1800ce993  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce99a  lea     rax, WPP_GLOBAL_Control
0x1800ce9a1  cmp     rcx, rax
0x1800ce9a4  jz      loc_1800CED1E
0x1800ce9aa  test    [rcx+1Ch], dil
0x1800ce9ae  jz      loc_1800CED1E
0x1800ce9b4  mov     edx, 0Dh
0x1800ce9b9  jmp     loc_1800CE93A
0x1800ce9be  cmp     [rbp+260h+arg_38], 2
0x1800ce9c5  jnz     short loc_1800CEA32
0x1800ce9c7  xor     r9d, r9d; SecurityDescriptorSize
0x1800ce9ca  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800ce9cf  mov     edx, edi; StringSDRevision
0x1800ce9d1  lea     rcx, [rbp+260h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800ce9d8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ce9df  nop     dword ptr [rax+rax+00h]
0x1800ce9e4  test    eax, eax
0x1800ce9e6  jnz     loc_1800CEA9F
0x1800ce9ec  call    cs:__imp_GetLastError
0x1800ce9f3  nop     dword ptr [rax+rax+00h]
0x1800ce9f8  mov     ebx, eax
0x1800ce9fa  test    eax, eax
0x1800ce9fc  jle     short loc_1800CEA07
0x1800ce9fe  movzx   ebx, ax
0x1800cea01  or      ebx, 80070000h
0x1800cea07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cea0e  lea     rax, WPP_GLOBAL_Control
0x1800cea15  cmp     rcx, rax
0x1800cea18  jz      loc_1800CED1E
0x1800cea1e  test    [rcx+1Ch], dil
0x1800cea22  jz      loc_1800CED1E
0x1800cea28  mov     edx, 0Eh
0x1800cea2d  jmp     loc_1800CE93A
0x1800cea32  cmp     [rbp+260h+arg_38], edi
0x1800cea38  jnz     short loc_1800CEA9F
0x1800cea3a  xor     r9d, r9d; SecurityDescriptorSize
0x1800cea3d  lea     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800cea42  mov     edx, edi; StringSDRevision
0x1800cea44  lea     rcx, [rsp+360h+var_300]; StringSecurityDescriptor
0x1800cea49  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800cea50  nop     dword ptr [rax+rax+00h]
0x1800cea55  test    eax, eax
0x1800cea57  jnz     short loc_1800CEA9F
0x1800cea59  call    cs:__imp_GetLastError
0x1800cea60  nop     dword ptr [rax+rax+00h]
0x1800cea65  mov     ebx, eax
0x1800cea67  test    eax, eax
0x1800cea69  jle     short loc_1800CEA74
0x1800cea6b  movzx   ebx, ax
0x1800cea6e  or      ebx, 80070000h
0x1800cea74  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cea7b  lea     rax, WPP_GLOBAL_Control
0x1800cea82  cmp     rcx, rax
0x1800cea85  jz      loc_1800CED1E
0x1800cea8b  test    [rcx+1Ch], dil
0x1800cea8f  jz      loc_1800CED1E
0x1800cea95  mov     edx, 0Fh
0x1800cea9a  jmp     loc_1800CE93A
0x1800cea9f  lea     r8, [rsp+360h+var_308]
0x1800ceaa4  mov     [rsi+10h], r12d
0x1800ceaa8  mov     edx, 8
0x1800ceaad  mov     rcx, rdi
0x1800ceab0  call    cs:__imp_FwSizeTMultiply
0x1800ceab7  nop     dword ptr [rax+rax+00h]
0x1800ceabc  mov     ebx, eax
0x1800ceabe  test    eax, eax
0x1800ceac0  jns     short loc_1800CEAED
0x1800ceac2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceac9  lea     rax, WPP_GLOBAL_Control
0x1800cead0  cmp     rcx, rax
0x1800cead3  jz      loc_1800CED1E
0x1800cead9  test    [rcx+1Ch], dil
0x1800ceadd  jz      loc_1800CED1E
0x1800ceae3  mov     edx, 10h
0x1800ceae8  jmp     loc_1800CE93A
0x1800ceaed  mov     rcx, [rsp+360h+var_308]
0x1800ceaf2  call    cs:__imp_FwAlloc
0x1800ceaf9  nop     dword ptr [rax+rax+00h]
0x1800ceafe  mov     [rsi+20h], rax
0x1800ceb02  test    rax, rax
0x1800ceb05  jnz     short loc_1800CEB37
0x1800ceb07  mov     ebx, 8007000Eh
0x1800ceb0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceb13  lea     rax, WPP_GLOBAL_Control
0x1800ceb1a  cmp     rcx, rax
0x1800ceb1d  jz      loc_1800CED1E
0x1800ceb23  test    [rcx+1Ch], dil
0x1800ceb27  jz      loc_1800CED1E
0x1800ceb2d  mov     edx, 11h
0x1800ceb32  jmp     loc_1800CE93A
0x1800ceb37  xor     r14d, r14d
0x1800ceb3a  cmp     r14, rdi
0x1800ceb3d  jnb     loc_1800CEBFB
0x1800ceb43  mov     rax, [rsp+360h+var_320]
0x1800ceb48  lea     r15, ds:0[r14*8]
0x1800ceb50  mov     rdx, [rsi+20h]
0x1800ceb54  add     rdx, r15
0x1800ceb57  mov     rcx, [r15+rax]
0x1800ceb5b  call    cs:__imp_FwStringCopy
0x1800ceb62  nop     dword ptr [rax+rax+00h]
0x1800ceb67  mov     ebx, eax
0x1800ceb69  test    eax, eax
0x1800ceb6b  js      short loc_1800CEBD0
0x1800ceb6d  mov     rcx, [rsi+20h]
0x1800ceb71  inc     r14
0x1800ceb74  mov     r8, [rsp+360h+SecurityDescriptor]; SecurityDescriptor
0x1800ceb79  mov     edx, 0Ah; MaxCalls
0x1800ceb7e  mov     [rsi+18h], r14
0x1800ceb82  mov     rcx, [r15+rcx]; Protseq
0x1800ceb86  call    cs:__imp_RpcServerUseProtseqW
0x1800ceb8d  nop     dword ptr [rax+rax+00h]
0x1800ceb92  test    eax, eax
0x1800ceb94  jz      short loc_1800CEB3A
0x1800ceb96  jg      short loc_1800CEB9C
0x1800ceb98  mov     ebx, eax
0x1800ceb9a  jmp     short loc_1800CEBA5
0x1800ceb9c  movzx   ebx, ax
0x1800ceb9f  or      ebx, 80070000h
0x1800ceba5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cebac  lea     rax, WPP_GLOBAL_Control
0x1800cebb3  cmp     rcx, rax
0x1800cebb6  jz      loc_1800CED1E
0x1800cebbc  test    [rcx+1Ch], dil
0x1800cebc0  jz      loc_1800CED1E
0x1800cebc6  mov     edx, 13h
0x1800cebcb  jmp     loc_1800CE93A
0x1800cebd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cebd7  lea     rax, WPP_GLOBAL_Control
0x1800cebde  cmp     rcx, rax
0x1800cebe1  jz      loc_1800CED1E
0x1800cebe7  test    [rcx+1Ch], dil
0x1800cebeb  jz      loc_1800CED1E
0x1800cebf1  mov     edx, 12h
0x1800cebf6  jmp     loc_1800CE93A
0x1800cebfb  mov     rax, [rsp+360h+SecurityDescriptor]
0x1800cec00  neg     r12d
0x1800cec03  mov     [rsp+360h+var_328], rax
0x1800cec08  mov     rcx, r13
0x1800cec0b  mov     rax, [rsp+360h+var_318]
0x1800cec10  sbb     r9d, r9d
0x1800cec13  mov     [rsp+360h+var_330], rax
0x1800cec18  and     r9d, 0FFFFFFE0h
0x1800cec1c  add     r9d, 29h ; ')'
0x1800cec20  mov     [rsp+360h+var_338], 0
0x1800cec28  xor     r8d, r8d
0x1800cec2b  mov     [rsp+360h+var_340], 4D2h
0x1800cec33  xor     edx, edx
0x1800cec35  call    cs:__imp_RpcServerRegisterIf3
0x1800cec3c  nop     dword ptr [rax+rax+00h]
0x1800cec41  test    eax, eax
0x1800cec43  jz      short loc_1800CEC7F
0x1800cec45  jg      short loc_1800CEC4B
0x1800cec47  mov     ebx, eax
0x1800cec49  jmp     short loc_1800CEC54
0x1800cec4b  movzx   ebx, ax
0x1800cec4e  or      ebx, 80070000h
0x1800cec54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cec5b  lea     rax, WPP_GLOBAL_Control
0x1800cec62  cmp     rcx, rax
0x1800cec65  jz      loc_1800CED1E
0x1800cec6b  test    [rcx+1Ch], dil
0x1800cec6f  jz      loc_1800CED1E
0x1800cec75  mov     edx, 14h
0x1800cec7a  jmp     loc_1800CE93A
0x1800cec7f  lea     rcx, [rsi+28h]; BindingVector
0x1800cec83  mov     [rsi+34h], edi
0x1800cec86  call    cs:__imp_RpcServerInqBindings
0x1800cec8d  nop     dword ptr [rax+rax+00h]
0x1800cec92  test    eax, eax
0x1800cec94  jz      short loc_1800CECC8
0x1800cec96  jg      short loc_1800CEC9C
0x1800cec98  mov     ebx, eax
0x1800cec9a  jmp     short loc_1800CECA5
0x1800cec9c  movzx   ebx, ax
0x1800cec9f  or      ebx, 80070000h
0x1800ceca5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cecac  lea     rax, WPP_GLOBAL_Control
0x1800cecb3  cmp     rcx, rax
0x1800cecb6  jz      short loc_1800CED1E
0x1800cecb8  test    [rcx+1Ch], dil
0x1800cecbc  jz      short loc_1800CED1E
  ... truncated ...
```
