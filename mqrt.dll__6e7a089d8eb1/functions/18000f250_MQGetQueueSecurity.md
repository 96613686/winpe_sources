# MQGetQueueSecurity

- ea: `0x18000f250`
- end: `0x18000f5f0`
- name: `MQGetQueueSecurity`
- size: `928`
- prototype: `HRESULT __stdcall(LPCWSTR lpwcsFormatName, SECURITY_INFORMATION RequestedInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800027f4`
- `0x180005488`
- `0x18000a364`
- `0x18000dae4`
- `0x18000f250`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x18001a864`
- `0x18001d560`
- `0x180021060`
- `0x1800216a8`
- `0x180023c36`
- `0x180023c4e`
- `0x180026010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000f41e`
- `RPCRT4!NdrClientCall3` at `0x18000f41e`
- `KERNEL32!TlsGetValue` at `0x18000f3d7`
- `KERNEL32!TlsGetValue` at `0x18000f3d7`

## pseudocode

```c
HRESULT __stdcall MQGetQueueSecurity(
        LPCWSTR lpwcsFormatName,
        SECURITY_INFORMATION RequestedInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD nLength,
        LPDWORD lpnLengthNeeded)
{
  __int64 *v6; // r12
  int v9; // eax
  HRESULT v10; // ebx
  int v12; // edi
  LPVOID Value; // rax
  CLIENT_CALL_RETURN v14; // rax
  int Pointer; // ebx
  const wchar_t *v16; // rdi
  bool v17; // dl
  void (*v18)(void); // rcx
  bool v19; // r8
  bool v20; // r9
  int v21; // ebx
  void *v22; // rbx
  __int64 v23; // [rsp+0h] [rbp-108h] BYREF
  __int64 v24; // [rsp+28h] [rbp-E0h]
  __int64 v25; // [rsp+38h] [rbp-D0h]
  char v26[4]; // [rsp+50h] [rbp-B8h]
  int v27; // [rsp+54h] [rbp-B4h]
  unsigned int v28; // [rsp+58h] [rbp-B0h]
  HRESULT v29; // [rsp+60h] [rbp-A8h]
  HRESULT v30; // [rsp+64h] [rbp-A4h]
  wchar_t *v31; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-98h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-90h]
  _OWORD v34[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v35; // [rsp+A8h] [rbp-60h]
  CLIENT_CALL_RETURN v36; // [rsp+B0h] [rbp-58h]
  _QWORD v37[10]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v39; // [rsp+120h] [rbp+18h] BYREF

  v35 = &v23;
  v6 = (__int64 *)pSecurityDescriptor;
  if ( !pSecurityDescriptor && !nLength )
    v6 = &v39;
  v9 = RtpOneTimeThreadInit();
  v10 = v9;
  if ( v9 >= 0 )
  {
    v28 = 1;
    v31 = 0;
    memset(v34, 0, sizeof(v34));
    LOWORD(v34[0]) = 0;
    if ( (unsigned int)FnFormatNameToQueueFormat(lpwcsFormatName, (struct QUEUE_FORMAT *)v34, &v31) )
    {
      if ( (unsigned int)IsLegalFormatNameOperation((const struct QUEUE_FORMAT *)v34) )
      {
        if ( LOBYTE(v34[0]) == 1 )
        {
          v32 = 1;
          *(_OWORD *)Src = 0;
          v16 = MachineDomain();
          v21 = ADInit(v18, v17, v19, v20);
          if ( v21 >= 0 )
            v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD, char *, SECURITY_INFORMATION, int, __int64 *))(*(_QWORD *)g_pAD + 80LL))(
                    g_pAD,
                    0,
                    v16,
                    0,
                    (char *)v34 + 8,
                    RequestedInformation,
                    1101,
                    &v32);
          v12 = RTpConvertToMQCode(v21, 1u);
          *(_DWORD *)v26 = v12;
          v27 = v21;
          if ( v12 >= 0 )
          {
            if ( LODWORD(Src[0]) > nLength )
            {
              v12 = RTpConvertToMQCode(-1072824285, 1u);
              *(_DWORD *)v26 = v12;
              v27 = -1072824285;
              v22 = Src[1];
            }
            else
            {
              v22 = Src[1];
              memcpy_0(v6, Src[1], LODWORD(Src[0]));
            }
            operator delete(v22);
            *lpnLengthNeeded = (DWORD)Src[0];
          }
        }
        else if ( (unsigned int)LOBYTE(v34[0]) - 2 < 2 )
        {
          v37[0] = 1;
          v37[1] = v34;
          Value = TlsGetValue(g_hBindIndex);
          v36.Simple = 0;
          LODWORD(v25) = nLength;
          LODWORD(v24) = RequestedInformation;
          v14.Pointer = NdrClientCall3(
                          (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                          8u,
                          0,
                          Value,
                          v37,
                          v24,
                          v6,
                          v25,
                          lpnLengthNeeded).Pointer;
          Pointer = (int)v14.Pointer;
          v36.Pointer = v14.Pointer;
          v12 = RTpConvertToMQCode(v14.Simple, 1u);
          *(_DWORD *)v26 = v12;
          v27 = Pointer;
        }
        else
        {
          v12 = *(_DWORD *)v26;
        }
        MmDeallocate(v31);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12);
          LogMsgHR(v12, (wchar_t *)L"rt/queue", 0x471u);
        }
        return v12;
      }
      else
      {
        v30 = LogHR(-1072824288, (wchar_t *)L"rt/queue", 0x1AEu);
        local_unwind_0(v35, &loc_18000F381);
        return v30;
      }
    }
    else
    {
      v29 = LogHR(-1072824290, (wchar_t *)L"rt/queue", 0x1A4u);
      local_unwind_0(v35, &loc_18000F337);
      return v29;
    }
  }
  else
  {
    LogMsgHR(v9, (wchar_t *)L"rt/queue", 0x470u);
    return v10;
  }
}

```

## disassembly

```asm
0x18000f250  mov     rax, rsp
0x18000f253  mov     [rax+10h], edx
0x18000f256  mov     [rax+8], rcx
0x18000f25a  push    rbx
0x18000f25b  push    rsi
0x18000f25c  push    rdi
0x18000f25d  push    r12
0x18000f25f  push    r13
0x18000f261  push    r14
0x18000f263  push    r15
0x18000f265  sub     rsp, 0D0h
0x18000f26c  mov     [rsp+108h+var_60], rsp
0x18000f274  mov     r13d, r9d
0x18000f277  mov     r12, r8
0x18000f27a  mov     edi, edx
0x18000f27c  mov     r15, rcx
0x18000f27f  xor     esi, esi
0x18000f281  test    r8, r8
0x18000f284  jnz     short loc_18000F28F
0x18000f286  test    r9d, r9d
0x18000f289  jnz     short loc_18000F28F
0x18000f28b  lea     r12, [rax+18h]
0x18000f28f  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18000f294  mov     ebx, eax
0x18000f296  test    eax, eax
0x18000f298  jns     short loc_18000F2C3
0x18000f29a  mov     r8d, 470h; unsigned __int16
0x18000f2a0  lea     rdx, aRtQueue; "rt/queue"
0x18000f2a7  mov     ecx, eax; int
0x18000f2a9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000f2ae  mov     eax, ebx
0x18000f2b0  add     rsp, 0D0h
0x18000f2b7  pop     r15
0x18000f2b9  pop     r14
0x18000f2bb  pop     r13
0x18000f2bd  pop     r12
0x18000f2bf  pop     rdi
0x18000f2c0  pop     rsi
0x18000f2c1  pop     rbx
0x18000f2c2  retn
0x18000f2c3  mov     r14d, 1
0x18000f2c9  mov     [rsp+108h+var_B0], r14d
0x18000f2ce  mov     [rsp+108h+var_A0], rsi
0x18000f2d3  xorps   xmm0, xmm0
0x18000f2d6  movups  [rsp+108h+var_80], xmm0
0x18000f2de  movups  [rsp+108h+var_70], xmm0
0x18000f2e6  mov     word ptr [rsp+108h+var_80], si
0x18000f2ee  lea     r8, [rsp+108h+var_A0]; wchar_t **
0x18000f2f3  lea     rdx, [rsp+108h+var_80]; struct QUEUE_FORMAT *
0x18000f2fb  mov     rcx, r15; wchar_t *
0x18000f2fe  call    ?FnFormatNameToQueueFormat@@YAHPEB_WPEAUQUEUE_FORMAT@@PEAPEA_W@Z; FnFormatNameToQueueFormat(wchar_t const *,QUEUE_FORMAT *,wchar_t * *)
0x18000f303  test    eax, eax
0x18000f305  jnz     short loc_18000F340
0x18000f307  mov     r8d, 1A4h; unsigned __int16
0x18000f30d  lea     rdx, aRtQueue; "rt/queue"
0x18000f314  mov     ecx, 0C00E001Eh; int
0x18000f319  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000f31e  mov     [rsp+108h+var_A8], eax
0x18000f322  lea     rdx, loc_18000F337
0x18000f329  mov     rcx, [rsp+108h+var_60]
0x18000f331  call    _local_unwind_0
0x18000f336  nop
0x18000f337  mov     eax, [rsp+108h+var_A8]
0x18000f33b  jmp     loc_18000F2B0
0x18000f340  lea     rcx, [rsp+108h+var_80]; struct QUEUE_FORMAT *
0x18000f348  call    ?IsLegalFormatNameOperation@@YAHPEBUQUEUE_FORMAT@@@Z; IsLegalFormatNameOperation(QUEUE_FORMAT const *)
0x18000f34d  test    eax, eax
0x18000f34f  jnz     short loc_18000F38A
0x18000f351  mov     r8d, 1AEh; unsigned __int16
0x18000f357  lea     rdx, aRtQueue; "rt/queue"
0x18000f35e  mov     ecx, 0C00E0020h; int
0x18000f363  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000f368  mov     [rsp+108h+var_A4], eax
0x18000f36c  lea     rdx, loc_18000F381
0x18000f373  mov     rcx, [rsp+108h+var_60]
0x18000f37b  call    _local_unwind_0
0x18000f380  nop
0x18000f381  mov     eax, [rsp+108h+var_A4]
0x18000f385  jmp     loc_18000F2B0
0x18000f38a  movzx   ecx, byte ptr [rsp+108h+var_80]
0x18000f392  sub     ecx, 1
0x18000f395  jz      loc_18000F448
0x18000f39b  sub     ecx, 1
0x18000f39e  jz      short loc_18000F3AE
0x18000f3a0  cmp     ecx, 1
0x18000f3a3  jz      short loc_18000F3AE
0x18000f3a5  mov     edi, dword ptr [rsp+108h+var_B8]
0x18000f3a9  jmp     loc_18000F524
0x18000f3ae  xorps   xmm0, xmm0
0x18000f3b1  movups  xmmword ptr [rsp+108h+var_50], xmm0
0x18000f3b9  mov     dword ptr [rsp+108h+var_50], r14d
0x18000f3c1  lea     rax, [rsp+108h+var_80]
0x18000f3c9  mov     [rsp+108h+var_50+8], rax
0x18000f3d1  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000f3d7  call    cs:__imp_TlsGetValue
0x18000f3dd  mov     [rsp+108h+var_58], rsi
0x18000f3e5  mov     rcx, [rsp+108h+lpnLengthNeeded]
0x18000f3ed  mov     [rsp+108h+var_C8], rcx
0x18000f3f2  mov     dword ptr [rsp+108h+var_D0], r13d
0x18000f3f7  mov     [rsp+108h+var_D8], r12
0x18000f3fc  mov     dword ptr [rsp+108h+var_E0], edi
0x18000f400  lea     rcx, [rsp+108h+var_50]
0x18000f408  mov     qword ptr [rsp+108h+var_E8], rcx
0x18000f40d  mov     r9, rax
0x18000f410  xor     r8d, r8d; pReturnValue
0x18000f413  lea     edx, [r8+8]; nProcNum
0x18000f417  lea     rcx, pProxyInfo; pProxyInfo
0x18000f41e  call    cs:__imp_NdrClientCall3
0x18000f424  mov     rbx, rax
0x18000f427  mov     [rsp+108h+var_58], rax
0x18000f42f  mov     edx, r14d; unsigned int
0x18000f432  mov     ecx, eax; int
0x18000f434  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000f439  mov     edi, eax
0x18000f43b  mov     dword ptr [rsp+108h+var_B8], eax
0x18000f43f  mov     [rsp+108h+var_B4], ebx
0x18000f443  jmp     loc_18000F524
0x18000f448  mov     [rsp+108h+var_98], 1
0x18000f451  xorps   xmm0, xmm0
0x18000f454  movdqu  xmmword ptr [rsp+108h+Src], xmm0
0x18000f45a  call    ?MachineDomain@@YAPEB_WXZ; MachineDomain(void)
0x18000f45f  mov     rdi, rax
0x18000f462  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x18000f467  mov     ebx, eax
0x18000f469  test    eax, eax
0x18000f46b  js      short loc_18000F4B4
0x18000f46d  mov     rcx, cs:?g_pAD@@3V?$P@VCBaseADProvider@@@@A; P<CBaseADProvider> g_pAD
0x18000f474  mov     rax, [rcx]
0x18000f477  lea     rdx, [rsp+108h+var_98]
0x18000f47c  mov     [rsp+108h+var_D0], rdx
0x18000f481  mov     dword ptr [rsp+108h+var_D8], 44Dh
0x18000f489  mov     edx, [rsp+108h+arg_8]
0x18000f490  mov     dword ptr [rsp+108h+var_E0], edx
0x18000f494  lea     rdx, [rsp+108h+var_80+8]
0x18000f49c  mov     qword ptr [rsp+108h+var_E8], rdx
0x18000f4a1  xor     r9d, r9d
0x18000f4a4  mov     r8, rdi
0x18000f4a7  xor     edx, edx
0x18000f4a9  mov     rax, [rax+50h]
0x18000f4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4b2  mov     ebx, eax
0x18000f4b4  mov     edx, r14d; unsigned int
0x18000f4b7  mov     ecx, ebx; int
0x18000f4b9  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000f4be  mov     edi, eax
0x18000f4c0  mov     dword ptr [rsp+108h+var_B8], eax
0x18000f4c4  mov     [rsp+108h+var_B4], ebx
0x18000f4c8  test    eax, eax
0x18000f4ca  js      short loc_18000F524
0x18000f4cc  cmp     dword ptr [rsp+108h+Src], r13d
0x18000f4d1  ja      short loc_18000F4ED
0x18000f4d3  mov     r8d, dword ptr [rsp+108h+Src]; Size
0x18000f4d8  mov     rbx, [rsp+108h+Src+8]
0x18000f4e0  mov     rdx, rbx; Src
0x18000f4e3  mov     rcx, r12; void *
0x18000f4e6  call    memcpy_0
0x18000f4eb  jmp     short loc_18000F50E
0x18000f4ed  mov     edx, r14d; unsigned int
0x18000f4f0  mov     ebx, 0C00E0023h
0x18000f4f5  mov     ecx, ebx; int
0x18000f4f7  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000f4fc  mov     edi, eax
0x18000f4fe  mov     dword ptr [rsp+108h+var_B8], eax
0x18000f502  mov     [rsp+108h+var_B4], ebx
0x18000f506  mov     rbx, [rsp+108h+Src+8]
0x18000f50e  mov     rcx, rbx; void *
0x18000f511  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f516  mov     ecx, dword ptr [rsp+108h+Src]
0x18000f51a  mov     rax, [rsp+108h+lpnLengthNeeded]
0x18000f522  mov     [rax], ecx
0x18000f524  jmp     short loc_18000F58E
0x18000f526  mov     ebx, eax
0x18000f528  mov     edx, [rsp+108h+var_B0]; unsigned int
0x18000f52c  mov     ecx, eax; int
0x18000f52e  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000f533  mov     edi, eax
0x18000f535  mov     dword ptr [rsp+108h+var_B8], eax
0x18000f539  mov     [rsp+108h+var_B4], ebx
0x18000f53d  test    eax, eax
0x18000f53f  jg      short loc_18000F545
0x18000f541  mov     ecx, eax
0x18000f543  jmp     short loc_18000F54E
0x18000f545  movzx   ecx, di
0x18000f548  or      ecx, 80070000h; int
0x18000f54e  mov     r8d, 1B8h; unsigned __int16
0x18000f554  lea     rdx, aRtQueue; "rt/queue"
0x18000f55b  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000f560  test    edi, edi
0x18000f562  js      short loc_18000F580
0x18000f564  mov     edx, [rsp+108h+var_B0]; unsigned int
0x18000f568  mov     ecx, 0C00E000Bh; int
0x18000f56d  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000f572  mov     edi, eax
0x18000f574  mov     dword ptr [rsp+108h+var_B8], eax
0x18000f578  mov     [rsp+108h+var_B4], 0C00E000Bh
0x18000f580  mov     r14d, 1
0x18000f586  mov     r15, [rsp+108h+arg_0]
0x18000f58e  mov     rcx, [rsp+108h+var_A0]; void *
0x18000f593  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18000f598  test    edi, edi
0x18000f59a  jns     short loc_18000F5E9
0x18000f59c  lea     rax, WPP_GLOBAL_Control
0x18000f5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5aa  cmp     rcx, rax
0x18000f5ad  jz      short loc_18000F5D1
0x18000f5af  test    [rcx+1Ch], r14b
0x18000f5b3  jz      short loc_18000F5D1
0x18000f5b5  mov     edx, 11h
0x18000f5ba  mov     dword ptr [rsp+108h+var_E8], edi; char
0x18000f5be  mov     r9, r15
0x18000f5c1  lea     r8, WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids
0x18000f5c8  mov     rcx, [rcx+10h]; LoggerHandle
0x18000f5cc  call    WPP_SF_Sd
0x18000f5d1  test    edi, edi
0x18000f5d3  jns     short loc_18000F5E9
0x18000f5d5  mov     r8d, 471h; unsigned __int16
0x18000f5db  lea     rdx, aRtQueue; "rt/queue"
0x18000f5e2  mov     ecx, edi; int
0x18000f5e4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000f5e9  mov     eax, edi
0x18000f5eb  jmp     loc_18000F2B0
0x18002472b  push    rbp
0x18002472d  sub     rsp, 50h
0x180024731  mov     rbp, rdx
0x180024734  mov     rcx, [rbp+68h]; void *
0x180024738  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x18002473d  nop
0x18002473e  add     rsp, 50h
0x180024742  pop     rbp
0x180024743  retn
```
