# NetworkDiagnosticsEngine::GetTraceFile(DiagnosticsClient *)

- ea: `0x18001b094`
- end: `0x18001b24f`
- name: `?GetTraceFile@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(NetworkDiagnosticsEngine *this, struct DiagnosticsClient *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004940`

## callees

- `0x1800035a8`
- `0x18000506c`
- `0x180005b44`
- `0x18000c478`
- `0x18001b094`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b205`

## string_xrefs

- `0x18001b1a0`: `NetworkDiagnosticsEngine::GetTraceFile: Could not retrieve trace file path (error=0x%08X)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NetworkDiagnosticsEngine::GetTraceFile(NetworkDiagnosticsEngine *this, struct DiagnosticsClient *a2)
{
  NetworkDiagnosticsEngine *v2; // rdi
  int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  NetworkIncident *v7; // rcx
  int TraceFileCopy; // eax
  int v9; // eax
  int v10; // eax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v13[8]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = qword_180041BB8;
  memset_0(v15, 0, 0x208u);
  pv = 0;
  if ( !a2 )
  {
    if ( *(_QWORD *)v2 )
      (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**(_QWORD **)v2 + 96LL))(
        *(_QWORD *)v2,
        6,
        L"NetworkDiagnosticsEngine::GetTraceFile: Invalid parameter");
    return (unsigned int)-2147024890;
  }
  v5 = *(_QWORD *)a2;
  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, __int128 *))(v5 + 72))(a2, &v14);
  if ( v4 < 0 )
  {
    if ( *(_QWORD *)v2 )
      (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**(_QWORD **)v2 + 96LL))(
        *(_QWORD *)v2,
        6,
        L"NetworkDiagnosticsEngine::GetTraceFile: Instance ID not available");
    return (unsigned int)v4;
  }
  v6 = std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(
         (char *)v2 + 8,
         v13,
         &v14);
  if ( *(_QWORD *)v6 != *((_QWORD *)v2 + 1) )
  {
    v7 = *(NetworkIncident **)(*(_QWORD *)v6 + 48LL);
    if ( v7 )
    {
      *((_QWORD *)v7 + 10) = a2;
      TraceFileCopy = NetworkIncident::GetTraceFileCopy(v7, (unsigned __int16 **)&pv);
      v4 = TraceFileCopy;
      if ( TraceFileCopy >= 0 )
      {
        v10 = DiagnosticsClient::AddTraceFile(a2, (const unsigned __int16 *)pv);
        v4 = v10;
        if ( v10 < 0 && *(_QWORD *)v2 )
        {
          v9 = StringCchPrintfW(
                 v15,
                 0x104u,
                 L"NetworkDiagnosticsEngine::GetTraceFile: Could not add trace file to parameter stack (error=0x%08X)",
                 (unsigned int)v10,
                 pv);
LABEL_16:
          if ( v9 >= 0 )
            (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**(_QWORD **)v2 + 96LL))(
              *(_QWORD *)v2,
              6,
              v15);
        }
      }
      else if ( *(_QWORD *)v2 )
      {
        v9 = StringCchPrintfW(
               v15,
               0x104u,
               L"NetworkDiagnosticsEngine::GetTraceFile: Could not retrieve trace file path (error=0x%08X)",
               (unsigned int)TraceFileCopy,
               pv);
        goto LABEL_16;
      }
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)v4;
    }
  }
  if ( *(_QWORD *)v2 )
    (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**(_QWORD **)v2 + 96LL))(
      *(_QWORD *)v2,
      6,
      L"NetworkDiagnosticsEngine::GetTraceFile: Instance not found");
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18001b094  push    rbp
0x18001b096  push    rbx
0x18001b097  push    rsi
0x18001b098  push    rdi
0x18001b099  lea     rbp, [rsp-168h]
0x18001b0a1  sub     rsp, 268h
0x18001b0a8  mov     rax, cs:__security_cookie
0x18001b0af  xor     rax, rsp
0x18001b0b2  mov     [rbp+180h+var_30], rax
0x18001b0b9  mov     rdi, cs:qword_180041BB8
0x18001b0c0  lea     rcx, [rsp+280h+var_240]; void *
0x18001b0c5  mov     rsi, rdx
0x18001b0c8  mov     r8d, 208h; Size
0x18001b0ce  xor     edx, edx; Val
0x18001b0d0  call    memset_0
0x18001b0d5  mov     [rsp+280h+pv], 0
0x18001b0de  test    rsi, rsi
0x18001b0e1  jnz     short loc_18001B10B
0x18001b0e3  mov     rcx, [rdi]
0x18001b0e6  test    rcx, rcx
0x18001b0e9  jz      short loc_18001B101
0x18001b0eb  mov     rax, [rcx]
0x18001b0ee  lea     r8, aNetworkdiagnos_3; "NetworkDiagnosticsEngine::GetTraceFile:"...
0x18001b0f5  lea     edx, [rsi+6]
0x18001b0f8  mov     rax, [rax+60h]
0x18001b0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b101  mov     ebx, 80070006h
0x18001b106  jmp     loc_18001B232
0x18001b10b  mov     rax, [rsi]
0x18001b10e  lea     rdx, [rsp+280h+var_250]
0x18001b113  xorps   xmm0, xmm0
0x18001b116  mov     rcx, rsi
0x18001b119  movups  [rsp+280h+var_250], xmm0
0x18001b11e  mov     rax, [rax+48h]
0x18001b122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b127  mov     ebx, eax
0x18001b129  test    eax, eax
0x18001b12b  jns     short loc_18001B159
0x18001b12d  mov     r9, [rdi]
0x18001b130  test    r9, r9
0x18001b133  jz      loc_18001B232
0x18001b139  mov     rcx, [r9]
0x18001b13c  lea     r8, aNetworkdiagnos; "NetworkDiagnosticsEngine::GetTraceFile:"...
0x18001b143  mov     edx, 6
0x18001b148  mov     rax, [rcx+60h]
0x18001b14c  mov     rcx, r9
0x18001b14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b154  jmp     loc_18001B232
0x18001b159  lea     r8, [rsp+280h+var_250]
0x18001b15e  lea     rdx, [rsp+280h+var_258]
0x18001b163  lea     rcx, [rdi+8]
0x18001b167  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(_GUID const &)
0x18001b16c  mov     rcx, [rax]
0x18001b16f  cmp     rcx, [rdi+8]
0x18001b173  jz      loc_18001B20D
0x18001b179  mov     rcx, [rcx+30h]; this
0x18001b17d  test    rcx, rcx
0x18001b180  jz      loc_18001B20D
0x18001b186  lea     rdx, [rsp+280h+pv]; unsigned __int16 **
0x18001b18b  mov     [rcx+50h], rsi
0x18001b18f  call    ?GetTraceFileCopy@NetworkIncident@@QEAAJPEAPEAG@Z; NetworkIncident::GetTraceFileCopy(ushort * *)
0x18001b194  mov     ebx, eax
0x18001b196  test    eax, eax
0x18001b198  jns     short loc_18001B1A9
0x18001b19a  cmp     qword ptr [rdi], 0
0x18001b19e  jz      short loc_18001B1F8
0x18001b1a0  lea     r8, aNetworkdiagnos_4; "NetworkDiagnosticsEngine::GetTraceFile:"...
0x18001b1a7  jmp     short loc_18001B1C9
0x18001b1a9  mov     rdx, [rsp+280h+pv]; unsigned __int16 *
0x18001b1ae  mov     rcx, rsi; this
0x18001b1b1  call    ?AddTraceFile@DiagnosticsClient@@QEAAJPEBG@Z; DiagnosticsClient::AddTraceFile(ushort const *)
0x18001b1b6  mov     ebx, eax
0x18001b1b8  test    eax, eax
0x18001b1ba  jns     short loc_18001B1F8
0x18001b1bc  cmp     qword ptr [rdi], 0
0x18001b1c0  jz      short loc_18001B1F8
0x18001b1c2  lea     r8, aNetworkdiagnos_2; "NetworkDiagnosticsEngine::GetTraceFile:"...
0x18001b1c9  mov     r9d, eax
0x18001b1cc  lea     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x18001b1d1  mov     edx, 104h; unsigned __int64
0x18001b1d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b1db  test    eax, eax
0x18001b1dd  js      short loc_18001B1F8
0x18001b1df  mov     rcx, [rdi]
0x18001b1e2  lea     r8, [rsp+280h+var_240]
0x18001b1e7  mov     edx, 6
0x18001b1ec  mov     rax, [rcx]
0x18001b1ef  mov     rax, [rax+60h]
0x18001b1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f8  cmp     [rsp+280h+pv], 0
0x18001b1fe  jz      short loc_18001B232
0x18001b200  mov     rcx, [rsp+280h+pv]; pv
0x18001b205  call    cs:__imp_CoTaskMemFree
0x18001b20b  jmp     short loc_18001B232
0x18001b20d  mov     rcx, [rdi]
0x18001b210  test    rcx, rcx
0x18001b213  jz      short loc_18001B22D
0x18001b215  mov     rax, [rcx]
0x18001b218  lea     r8, aNetworkdiagnos_1; "NetworkDiagnosticsEngine::GetTraceFile:"...
0x18001b21f  mov     edx, 6
0x18001b224  mov     rax, [rax+60h]
0x18001b228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b22d  mov     ebx, 80070057h
0x18001b232  mov     eax, ebx
0x18001b234  mov     rcx, [rbp+180h+var_30]
0x18001b23b  xor     rcx, rsp; StackCookie
0x18001b23e  call    __security_check_cookie
0x18001b243  add     rsp, 268h
0x18001b24a  pop     rdi
0x18001b24b  pop     rsi
0x18001b24c  pop     rbx
0x18001b24d  pop     rbp
0x18001b24e  retn
```
