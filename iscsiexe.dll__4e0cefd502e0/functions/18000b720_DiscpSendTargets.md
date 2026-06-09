# DiscpSendTargets

- ea: `0x18000b720`
- end: `0x18000ba0a`
- name: `DiscpSendTargets`
- size: `746`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180002cbc`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180006998`
- `0x180009f14`
- `0x18000a404`
- `0x18000a748`
- `0x18000b720`
- `0x180016de8`

## import_xrefs

- `ISCSIUM!DiscpCopyToCountedString` at `0x18000b86b`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000b86b`
- `ISCSIUM!DiscpExecuteMethod` at `0x18000b8ad`
- `ISCSIUM!DiscpExecuteMethod` at `0x18000b8ad`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000b96b`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000b990`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000b96b`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000b990`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b8f9`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b974`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b9ce`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b9e1`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b8f9`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b974`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b9ce`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b9e1`

## pseudocode

```c
__int64 __fastcall DiscpSendTargets(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  int v6; // edi
  unsigned int InitiatorInstanceList; // esi
  __int64 v9; // r9
  __int64 v10; // r15
  __int64 v11; // r13
  __int64 v12; // rbx
  unsigned int v13; // edi
  unsigned int v14; // eax
  unsigned int *v15; // rcx
  __int64 v16; // r8
  wchar_t *v17; // rbx
  __int64 v18; // rbx
  int v20; // [rsp+30h] [rbp-D0h]
  size_t v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+58h] [rbp-A8h]
  unsigned int v23; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+84h] [rbp-7Ch]
  unsigned int v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v27; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v28; // [rsp+98h] [rbp-68h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h]
  wchar_t *v30; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-50h]
  __int64 v32[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v33[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v35[456]; // [rsp+E8h] [rbp-18h] BYREF

  v6 = a2;
  v29 = a3;
  v25 = a2;
  v31 = a4;
  *(_OWORD *)v32 = 0;
  *(_OWORD *)v33 = 0;
  memset_0(&v34, 0, 0x1C8u);
  v28 = 0;
  v27 = 0;
  v23 = 0;
  v26 = 0;
  v30 = 0;
  InitiatorInstanceList = DiscpGetInitiatorInstanceList(a1, &v23, &v27);
  if ( !InitiatorInstanceList )
  {
    v10 = v27;
    v11 = 0;
    InitiatorInstanceList = -268500991;
    a6[1] = a6;
    *a6 = a6;
    v24 = -268500991;
    if ( v23 )
    {
      do
      {
        v12 = *(_QWORD *)(v10 + 8 * v11);
        LODWORD(v21) = 0;
        v13 = DiscpLoginTarget(v12, v6, 0, v9, 0, v29, 0, v31, a5, v21, 0, v22, 0, (__int64)v32, (__int64)v33);
        if ( v13 )
          goto LABEL_30;
        v34 = v32[1];
        v28 = 0;
        v26 = 32776;
        DiscpCopyToCountedString(v35, L"SendTargets=All", 223);
        v14 = DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, *(_QWORD *)(v12 + 40), 10, &v34, 456, &v28, &v26, 8);
        v13 = v14;
        if ( v14 )
        {
          if ( v14 - 4200 <= 2 )
            v13 = -268500924;
        }
        else
        {
          v15 = v28;
          v13 = *v28;
          if ( !*v28 )
          {
            v16 = v28[1];
            if ( (_DWORD)v16 )
            {
              v13 = DiscpParseSendTargets(v12, v25, v16, v28 + 2, v29, a6);
              InitiatorInstanceList &= -(v13 != 0);
              v15 = v28;
            }
            else
            {
              InitiatorInstanceList = 0;
            }
          }
          DiscpFreeMemory(v15);
        }
        DiscpLogoutTarget(v12, v32);
        if ( v13 )
        {
LABEL_30:
          if ( (unsigned int)DiscpCreatePortalName(v29, *(int **)(v12 + 40), v25, 0, &v30) )
          {
            LOWORD(v20) = 0;
            DiscpReportEventlogWithStatus(113, 2, 0, v13, 0, 0, v20);
          }
          else
          {
            v17 = v30;
            LOWORD(v20) = 1;
            DiscpReportEventlogWithStatus(113, 2, 0, v13, 0, 0, v20);
            DiscpFreeMemory(v17);
          }
        }
        if ( InitiatorInstanceList && v13 )
          InitiatorInstanceList = v13;
        v6 = v25;
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < v23 );
      v24 = InitiatorInstanceList;
    }
    v18 = 0;
    if ( v23 )
    {
      do
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(v10 + 8 * v18) + 16LL), 0xFFFFFFFF) == 1 )
          DiscpFreeMemory(*(_QWORD *)(v10 + 8 * v18));
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < v23 );
      InitiatorInstanceList = v24;
    }
    DiscpFreeMemory(v10);
  }
  return InitiatorInstanceList;
}

```

## disassembly

```asm
0x18000b720  push    rbp
0x18000b722  push    rbx
0x18000b723  push    rsi
0x18000b724  push    rdi
0x18000b725  push    r12
0x18000b727  push    r13
0x18000b729  push    r15
0x18000b72b  lea     rbp, [rsp-1C0h]
0x18000b733  sub     rsp, 2C0h
0x18000b73a  mov     rax, cs:__security_cookie
0x18000b741  xor     rax, rsp
0x18000b744  mov     [rbp+1F0h+var_40], rax
0x18000b74b  mov     r12, [rbp+1F0h+arg_28]
0x18000b752  mov     edi, edx
0x18000b754  mov     [rbp+1F0h+var_250], r8
0x18000b758  mov     rbx, rcx
0x18000b75b  mov     [rbp+1F0h+var_268], edx
0x18000b75e  lea     rcx, [rbp+1F0h+var_210]; void *
0x18000b762  xorps   xmm0, xmm0
0x18000b765  mov     [rbp+1F0h+var_240], r9
0x18000b769  xorps   xmm1, xmm1
0x18000b76c  xor     edx, edx; Val
0x18000b76e  mov     r8d, 1C8h; Size
0x18000b774  movups  xmmword ptr [rbp+1F0h+var_238], xmm0
0x18000b778  movups  xmmword ptr [rbp+1F0h+var_228], xmm1
0x18000b77c  call    memset_0
0x18000b781  xor     eax, eax
0x18000b783  lea     r8, [rbp+1F0h+var_260]
0x18000b787  lea     rdx, [rbp+1F0h+var_270]
0x18000b78b  mov     [rbp+1F0h+var_258], rax
0x18000b78f  mov     rcx, rbx
0x18000b792  mov     [rbp+1F0h+var_260], rax
0x18000b796  mov     [rbp+1F0h+var_270], eax
0x18000b799  mov     [rbp+1F0h+var_264], eax
0x18000b79c  mov     [rbp+1F0h+var_248], rax
0x18000b7a0  call    DiscpGetInitiatorInstanceList
0x18000b7a5  mov     esi, eax
0x18000b7a7  test    eax, eax
0x18000b7a9  jnz     loc_18000B9E7
0x18000b7af  mov     r15, [rbp+1F0h+var_260]
0x18000b7b3  xor     r13d, r13d
0x18000b7b6  mov     esi, 0EFFF0001h
0x18000b7bb  mov     [r12+8], r12
0x18000b7c0  mov     [r12], r12
0x18000b7c4  mov     [rbp+1F0h+var_26C], esi
0x18000b7c7  cmp     [rbp+1F0h+var_270], r13d
0x18000b7cb  jbe     loc_18000B9B2
0x18000b7d1  mov     rbx, [r15+r13*8]
0x18000b7d5  lea     rax, [rbp+1F0h+var_228]
0x18000b7d9  mov     [rsp+2F0h+var_280], rax; __int64
0x18000b7de  xor     r8d, r8d; int
0x18000b7e1  lea     rax, [rbp+1F0h+var_238]
0x18000b7e5  mov     edx, edi; int
0x18000b7e7  mov     [rsp+2F0h+var_288], rax; __int64
0x18000b7ec  mov     rcx, rbx; int
0x18000b7ef  mov     rax, [rbp+1F0h+arg_20]
0x18000b7f6  mov     [rsp+2F0h+var_290], 0; char
0x18000b7fb  mov     [rsp+2F0h+var_2A0], 0; __int64
0x18000b804  mov     dword ptr [rsp+2F0h+var_2A8], 0; size_t
0x18000b80c  mov     [rsp+2F0h+var_2B0], rax; __int64
0x18000b811  mov     rax, [rbp+1F0h+var_240]
0x18000b815  mov     [rsp+2F0h+var_2B8], rax; __int64
0x18000b81a  mov     rax, [rbp+1F0h+var_250]
0x18000b81e  mov     [rsp+2F0h+var_2C0], 0; __int64
0x18000b827  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18000b82c  mov     [rsp+2F0h+var_2D0], 0; int
0x18000b834  call    DiscpLoginTarget
0x18000b839  mov     edi, eax
0x18000b83b  test    eax, eax
0x18000b83d  jnz     loc_18000B921
0x18000b843  mov     rax, [rbp+1F0h+var_238+8]
0x18000b847  lea     rdx, aSendtargetsAll; "SendTargets=All"
0x18000b84e  mov     r8d, 0DFh
0x18000b854  mov     [rbp+1F0h+var_210], rax
0x18000b858  lea     rcx, [rbp+1F0h+var_208]
0x18000b85c  mov     [rbp+1F0h+var_258], 0
0x18000b864  mov     [rbp+1F0h+var_264], 8008h
0x18000b86b  call    cs:__imp_DiscpCopyToCountedString
0x18000b871  mov     r8, [rbx+28h]
0x18000b875  lea     rax, [rbp+1F0h+var_264]
0x18000b879  mov     dword ptr [rsp+2F0h+var_2B0], 8
0x18000b881  lea     r9d, [rdi+0Ah]
0x18000b885  mov     [rsp+2F0h+var_2B8], rax
0x18000b88a  lea     rcx, MSiSCSI_Operations_GUID
0x18000b891  lea     rax, [rbp+1F0h+var_258]
0x18000b895  xor     edx, edx
0x18000b897  mov     [rsp+2F0h+var_2C0], rax
0x18000b89c  lea     rax, [rbp+1F0h+var_210]
0x18000b8a0  mov     dword ptr [rsp+2F0h+var_2C8], 1C8h
0x18000b8a8  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18000b8ad  call    cs:__imp_DiscpExecuteMethod
0x18000b8b3  mov     edi, eax
0x18000b8b5  test    eax, eax
0x18000b8b7  jnz     short loc_18000B901
0x18000b8b9  mov     rcx, [rbp+1F0h+var_258]
0x18000b8bd  mov     edi, [rcx]
0x18000b8bf  test    edi, edi
0x18000b8c1  jnz     short loc_18000B8F9
0x18000b8c3  mov     r8d, [rcx+4]
0x18000b8c7  test    r8d, r8d
0x18000b8ca  jz      short loc_18000B8F7
0x18000b8cc  mov     rax, [rbp+1F0h+var_250]
0x18000b8d0  lea     r9, [rcx+8]
0x18000b8d4  mov     edx, [rbp+1F0h+var_268]
0x18000b8d7  mov     rcx, rbx
0x18000b8da  mov     [rsp+2F0h+var_2C8], r12
0x18000b8df  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18000b8e4  call    DiscpParseSendTargets
0x18000b8e9  mov     edi, eax
0x18000b8eb  neg     eax
0x18000b8ed  sbb     ecx, ecx
0x18000b8ef  and     esi, ecx
0x18000b8f1  mov     rcx, [rbp+1F0h+var_258]
0x18000b8f5  jmp     short loc_18000B8F9
0x18000b8f7  xor     esi, esi
0x18000b8f9  call    cs:__imp_DiscpFreeMemory
0x18000b8ff  jmp     short loc_18000B911
0x18000b901  add     eax, 0FFFFEF98h
0x18000b906  mov     ecx, 0EFFF0044h
0x18000b90b  cmp     eax, 2
0x18000b90e  cmovbe  edi, ecx
0x18000b911  lea     rdx, [rbp+1F0h+var_238]
0x18000b915  mov     rcx, rbx
0x18000b918  call    DiscpLogoutTarget
0x18000b91d  test    edi, edi
0x18000b91f  jz      short loc_18000B996
0x18000b921  mov     r8d, [rbp+1F0h+var_268]
0x18000b925  lea     rax, [rbp+1F0h+var_248]
0x18000b929  mov     rdx, [rbx+28h]
0x18000b92d  xor     r9d, r9d
0x18000b930  mov     rcx, [rbp+1F0h+var_250]
0x18000b934  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18000b939  call    DiscpCreatePortalName
0x18000b93e  xor     edx, edx
0x18000b940  mov     r9d, edi
0x18000b943  movzx   r8d, dx
0x18000b947  lea     ecx, [rdx+71h]
0x18000b94a  test    eax, eax
0x18000b94c  jnz     short loc_18000B97C
0x18000b94e  mov     rbx, [rbp+1F0h+var_248]
0x18000b952  mov     [rsp+2F0h+var_2B8], rbx
0x18000b957  mov     word ptr [rsp+2F0h+var_2C0], 1
0x18000b95e  mov     [rsp+2F0h+var_2C8], rdx
0x18000b963  mov     qword ptr [rsp+2F0h+var_2D0], rdx
0x18000b968  lea     edx, [rcx-6Fh]
0x18000b96b  call    cs:__imp_DiscpReportEventlogWithStatus
0x18000b971  mov     rcx, rbx
0x18000b974  call    cs:__imp_DiscpFreeMemory
0x18000b97a  jmp     short loc_18000B996
0x18000b97c  mov     word ptr [rsp+2F0h+var_2C0], dx
0x18000b981  mov     [rsp+2F0h+var_2C8], rdx
0x18000b986  mov     qword ptr [rsp+2F0h+var_2D0], rdx
0x18000b98b  mov     edx, 2
0x18000b990  call    cs:__imp_DiscpReportEventlogWithStatus
0x18000b996  test    esi, esi
0x18000b998  jz      short loc_18000B99F
0x18000b99a  test    edi, edi
0x18000b99c  cmovnz  esi, edi
0x18000b99f  mov     edi, [rbp+1F0h+var_268]
0x18000b9a2  inc     r13d
0x18000b9a5  cmp     r13d, [rbp+1F0h+var_270]
0x18000b9a9  jb      loc_18000B7D1
0x18000b9af  mov     [rbp+1F0h+var_26C], esi
0x18000b9b2  xor     ebx, ebx
0x18000b9b4  cmp     [rbp+1F0h+var_270], ebx
0x18000b9b7  jbe     short loc_18000B9DE
0x18000b9b9  mov     rdx, [r15+rbx*8]
0x18000b9bd  or      eax, 0FFFFFFFFh
0x18000b9c0  lock xadd [rdx+10h], eax
0x18000b9c5  cmp     eax, 1
0x18000b9c8  jnz     short loc_18000B9D4
0x18000b9ca  mov     rcx, [r15+rbx*8]
0x18000b9ce  call    cs:__imp_DiscpFreeMemory
0x18000b9d4  inc     ebx
0x18000b9d6  cmp     ebx, [rbp+1F0h+var_270]
0x18000b9d9  jb      short loc_18000B9B9
0x18000b9db  mov     esi, [rbp+1F0h+var_26C]
0x18000b9de  mov     rcx, r15
0x18000b9e1  call    cs:__imp_DiscpFreeMemory
0x18000b9e7  mov     eax, esi
0x18000b9e9  mov     rcx, [rbp+1F0h+var_40]
0x18000b9f0  xor     rcx, rsp; StackCookie
0x18000b9f3  call    __security_check_cookie
0x18000b9f8  add     rsp, 2C0h
0x18000b9ff  pop     r15
0x18000ba01  pop     r13
0x18000ba03  pop     r12
0x18000ba05  pop     rdi
0x18000ba06  pop     rsi
0x18000ba07  pop     rbx
0x18000ba08  pop     rbp
0x18000ba09  retn
```
