# AiddRpcClient_AsyncWorkerThread

- ea: `0x18008f390`
- end: `0x18008f807`
- name: `AiddRpcClient_AsyncWorkerThread`
- size: `1143`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180012920`
- `0x18008f390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008f3d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008f3d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f3f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f48d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f5a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f713`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f3f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f48d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f5a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f713`
- `RPCRT4!NdrClientCall3` at `0x18008f528`
- `RPCRT4!NdrClientCall3` at `0x18008f528`

## string_xrefs

- `0x18008f3a0`: `AIDD: AiddRpcClient_AsyncWorkerThread: Started`
- `0x18008f5c3`: `AIDD: AiddRpcClient_AsyncWorkerThread: Server unavailable [0x%x], entering backoff for %ld ms (failures=%ld)`
- `0x18008f4e9`: `AIDD: AiddRpcClient_AsyncWorkerThread: Processing ProcessId=%lu`
- `0x18008f44b`: `AIDD: AiddRpcClient_AsyncWorkerThread: In backoff mode, skipping RPC calls until tick %llu (current: %llu)`
- `0x18008f3ad`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f458`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f4f6`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f5d0`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f600`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f62b`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f655`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f694`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f73b`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f76e`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f79a`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f7c4`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f7e3`: `AiddRpcClient_AsyncWorkerThread`
- `0x18008f687`: `AIDD: AiddRpcClient_AsyncWorkerThread: RPC call succeeded for ProcessId=%lu`
- `0x18008f648`: `AIDD: AiddRpcClient_AsyncWorkerThread: Server is now available`
- `0x18008f61e`: `AIDD: AiddRpcClient_AsyncWorkerThread: RPC call failed [0x%x] for ProcessId=%lu`
- `0x18008f5f3`: `AIDD: AiddRpcClient_AsyncWorkerThread: Server unavailable [0x%x] for ProcessId=%lu (failures=%ld)`
- `0x18008f7b7`: `AIDD: AiddRpcClient_AsyncWorkerThread: SEH exception occurred. Code: 0x%x`
- `0x18008f78d`: `AIDD: AiddRpcClient_AsyncWorkerThread: RPC exception [0x%x] for ProcessId=%lu`
- `0x18008f761`: `AIDD: AiddRpcClient_AsyncWorkerThread: Server unavailable (exception) [0x%x] for ProcessId=%lu (failures=%ld)`
- `0x18008f72e`: `AIDD: AiddRpcClient_AsyncWorkerThread: Server unavailable (exception) [0x%x], entering backoff for %ld ms`
- `0x18008f7d6`: `AIDD: AiddRpcClient_AsyncWorkerThread: Exiting`

## pseudocode

```c
__int64 __fastcall AiddRpcClient_AsyncWorkerThread(PVOID Parameter)
{
  DWORD v1; // eax
  ULONGLONG TickCount64; // rax
  ULONGLONG v3; // rax
  int v4; // edi
  unsigned int Pointer; // eax
  int v7; // r14d
  unsigned int v8; // edi
  __int64 v10; // [rsp+20h] [rbp-38h]

  AslLogCallPrintf(
    3,
    (unsigned int)"AiddRpcClient_AsyncWorkerThread",
    395,
    (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: Started");
LABEL_2:
  while ( !dword_18015C054 )
  {
    v1 = WaitForSingleObject(hEvent, 0x3E8u);
    if ( dword_18015C054 )
      break;
    if ( v1 != 258 )
    {
      TickCount64 = GetTickCount64();
      if ( qword_18015C068 <= 0 || TickCount64 >= qword_18015C068 )
      {
        while ( dword_18015C074 != dword_18015C050 )
        {
          if ( dword_18015C054 )
            break;
          v3 = GetTickCount64();
          if ( qword_18015C068 > 0 && v3 < qword_18015C068 )
            break;
          v4 = *((_DWORD *)qword_180159C20 + dword_18015C074 % 1024);
          _InterlockedCompareExchange(&dword_18015C074, dword_18015C074 + 1, dword_18015C074);
          AslLogCallPrintf(
            3,
            (unsigned int)"AiddRpcClient_AsyncWorkerThread",
            468,
            (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: Processing ProcessId=%lu");
          LODWORD(v10) = v4;
          Pointer = (unsigned int)NdrClientCall3(
                                    (MIDL_STUBLESS_PROXY_INFO *)&IAiddService_ProxyInfo,
                                    0,
                                    0,
                                    Binding,
                                    v10).Pointer;
          if ( Pointer )
          {
            if ( Pointer == 1715 || Pointer == 1717 || Pointer == 1722 || Pointer == 1723 || Pointer == 1753 )
            {
              v7 = _InterlockedIncrement(&dword_18015C088);
              dword_18015C05C = 0;
              if ( v7 >= 5 )
              {
                v8 = 60000;
                if ( (unsigned int)(5000 << (v7 - 5)) <= 0xEA60 )
                  v8 = 5000 << (v7 - 5);
                qword_18015C068 = v8 + GetTickCount64();
                AslLogCallPrintf(
                  3,
                  (unsigned int)"AiddRpcClient_AsyncWorkerThread",
                  503,
                  (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: Server unavailable [0x%x], entering backoff for %"
                                "ld ms (failures=%ld)");
                goto LABEL_2;
              }
              AslLogCallPrintf(
                3,
                (unsigned int)"AiddRpcClient_AsyncWorkerThread",
                512,
                (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: Server unavailable [0x%x] for ProcessId=%lu (failures=%ld)");
            }
            else
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"AiddRpcClient_AsyncWorkerThread",
                521,
                (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: RPC call failed [0x%x] for ProcessId=%lu");
            }
          }
          else
          {
            if ( !dword_18015C05C )
              AslLogCallPrintf(
                3,
                (unsigned int)"AiddRpcClient_AsyncWorkerThread",
                531,
                (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: Server is now available");
            dword_18015C05C = 1;
            dword_18015C088 = 0;
            qword_18015C068 = 0;
            AslLogCallPrintf(
              3,
              (unsigned int)"AiddRpcClient_AsyncWorkerThread",
              537,
              (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: RPC call succeeded for ProcessId=%lu");
          }
        }
      }
      else
      {
        while ( dword_18015C074 != dword_18015C050 )
          _InterlockedCompareExchange(&dword_18015C074, dword_18015C074 + 1, dword_18015C074);
        HIDWORD(v10) = HIDWORD(qword_18015C068);
        AslLogCallPrintf(
          3,
          (unsigned int)"AiddRpcClient_AsyncWorkerThread",
          436,
          (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: In backoff mode, skipping RPC calls until tick %llu (current: %llu)");
      }
    }
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"AiddRpcClient_AsyncWorkerThread",
    596,
    (unsigned int)"AIDD: AiddRpcClient_AsyncWorkerThread: Exiting");
  return 0;
}

```

## disassembly

```asm
0x18008f390  mov     [rsp+arg_0], rbx
0x18008f395  mov     [rsp+arg_10], rdi
0x18008f39a  push    r14
0x18008f39c  sub     rsp, 50h
0x18008f3a0  lea     r9, aAiddAiddrpccli_14; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f3a7  mov     r8d, 18Bh
0x18008f3ad  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f3b4  mov     ecx, 3
0x18008f3b9  call    AslLogCallPrintf
0x18008f3be  nop
0x18008f3bf  mov     eax, cs:dword_18015C054
0x18008f3c5  test    eax, eax
0x18008f3c7  jnz     loc_18008F7B1
0x18008f3cd  mov     edx, 3E8h; dwMilliseconds
0x18008f3d2  mov     rcx, cs:hEvent; hHandle
0x18008f3d9  call    cs:__imp_WaitForSingleObject
0x18008f3df  mov     ecx, cs:dword_18015C054
0x18008f3e5  test    ecx, ecx
0x18008f3e7  jnz     loc_18008F7B1
0x18008f3ed  cmp     eax, 102h
0x18008f3f2  jnz     short loc_18008F3F6
0x18008f3f4  jmp     short loc_18008F3BF
0x18008f3f6  call    cs:__imp_GetTickCount64
0x18008f3fc  mov     r8, rax
0x18008f3ff  mov     rcx, cs:qword_18015C068
0x18008f406  test    rcx, rcx
0x18008f409  jle     short loc_18008F46B
0x18008f40b  mov     rcx, cs:qword_18015C068
0x18008f412  cmp     rax, rcx
0x18008f415  jnb     short loc_18008F46B
0x18008f417  mov     edx, cs:dword_18015C050
0x18008f41d  mov     ecx, cs:dword_18015C074
0x18008f423  cmp     ecx, edx
0x18008f425  jz      short loc_18008F43A
0x18008f427  mov     eax, cs:dword_18015C074
0x18008f42d  lea     ecx, [rax+1]
0x18008f430  lock cmpxchg cs:dword_18015C074, ecx
0x18008f438  jmp     short loc_18008F417
0x18008f43a  mov     [rsp+58h+var_30], r8
0x18008f43f  mov     rax, cs:qword_18015C068
0x18008f446  mov     [rsp+58h+var_38], rax
0x18008f44b  lea     r9, aAiddAiddrpccli_12; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f452  mov     r8d, 1B4h
0x18008f458  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f45f  mov     ecx, 3
0x18008f464  call    AslLogCallPrintf
0x18008f469  jmp     short loc_18008F3F4
0x18008f46b  mov     ecx, cs:dword_18015C050
0x18008f471  mov     eax, cs:dword_18015C074
0x18008f477  cmp     eax, ecx
0x18008f479  jz      loc_18008F3F4
0x18008f47f  mov     eax, cs:dword_18015C054
0x18008f485  test    eax, eax
0x18008f487  jnz     loc_18008F3F4
0x18008f48d  call    cs:__imp_GetTickCount64
0x18008f493  mov     rcx, cs:qword_18015C068
0x18008f49a  test    rcx, rcx
0x18008f49d  jle     short loc_18008F4AF
0x18008f49f  mov     rcx, cs:qword_18015C068
0x18008f4a6  cmp     rax, rcx
0x18008f4a9  jb      loc_18008F3F4
0x18008f4af  mov     eax, cs:dword_18015C074
0x18008f4b5  mov     ecx, eax
0x18008f4b7  and     ecx, 800003FFh
0x18008f4bd  jge     short loc_18008F4C9
0x18008f4bf  dec     ecx
0x18008f4c1  or      ecx, 0FFFFFC00h
0x18008f4c7  inc     ecx
0x18008f4c9  movsxd  rcx, ecx
0x18008f4cc  lea     rdi, qword_180159C20
0x18008f4d3  mov     edi, [rdi+rcx*4]
0x18008f4d6  mov     [rsp+58h+var_18], edi
0x18008f4da  lea     ecx, [rax+1]
0x18008f4dd  lock cmpxchg cs:dword_18015C074, ecx
0x18008f4e5  mov     dword ptr [rsp+58h+var_38], edi
0x18008f4e9  lea     r9, aAiddAiddrpccli_18; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f4f0  mov     r8d, 1D4h
0x18008f4f6  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f4fd  mov     ecx, 3
0x18008f502  call    AslLogCallPrintf
0x18008f507  nop
0x18008f508  mov     [rsp+58h+arg_8], 0
0x18008f511  mov     dword ptr [rsp+58h+var_38], edi
0x18008f515  mov     r9, cs:Binding
0x18008f51c  xor     r8d, r8d; pReturnValue
0x18008f51f  xor     edx, edx; nProcNum
0x18008f521  lea     rcx, ?IAiddService_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18008f528  call    cs:__imp_NdrClientCall3
0x18008f52e  mov     rbx, rax
0x18008f531  mov     [rsp+58h+arg_8], rax
0x18008f536  test    eax, eax
0x18008f538  jz      loc_18008F63E
0x18008f53e  mov     ecx, ebx
0x18008f540  sub     ecx, 6B3h
0x18008f546  jz      short loc_18008F560
0x18008f548  sub     ecx, 2
0x18008f54b  jz      short loc_18008F560
0x18008f54d  sub     ecx, 5
0x18008f550  jz      short loc_18008F560
0x18008f552  sub     ecx, 1
0x18008f555  jz      short loc_18008F560
0x18008f557  cmp     ecx, 1Eh
0x18008f55a  jz      short loc_18008F560
0x18008f55c  xor     eax, eax
0x18008f55e  jmp     short loc_18008F565
0x18008f560  mov     eax, 1
0x18008f565  test    eax, eax
0x18008f567  jz      loc_18008F616
0x18008f56d  mov     r14d, 1
0x18008f573  lock xadd cs:dword_18015C088, r14d
0x18008f57c  inc     r14d
0x18008f57f  mov     cs:dword_18015C05C, 0
0x18008f589  cmp     r14d, 5
0x18008f58d  jl      short loc_18008F5E6
0x18008f58f  lea     ecx, [r14-5]
0x18008f593  mov     eax, 1388h
0x18008f598  shl     eax, cl
0x18008f59a  mov     edi, 0EA60h
0x18008f59f  cmp     eax, edi
0x18008f5a1  cmovbe  edi, eax
0x18008f5a4  call    cs:__imp_GetTickCount64
0x18008f5aa  mov     ecx, edi
0x18008f5ac  add     rax, rcx
0x18008f5af  mov     cs:qword_18015C068, rax
0x18008f5b6  mov     [rsp+58h+var_28], r14d
0x18008f5bb  mov     dword ptr [rsp+58h+var_30], edi
0x18008f5bf  mov     dword ptr [rsp+58h+var_38], ebx
0x18008f5c3  lea     r9, aAiddAiddrpccli_4; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f5ca  mov     r8d, 1F7h
0x18008f5d0  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f5d7  mov     ecx, 3
0x18008f5dc  call    AslLogCallPrintf
0x18008f5e1  jmp     loc_18008F3F4
0x18008f5e6  mov     [rsp+58h+var_28], r14d
0x18008f5eb  mov     dword ptr [rsp+58h+var_30], edi
0x18008f5ef  mov     dword ptr [rsp+58h+var_38], ebx
0x18008f5f3  lea     r9, aAiddAiddrpccli_0; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f5fa  mov     r8d, 200h
0x18008f600  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f607  mov     ecx, 3
0x18008f60c  call    AslLogCallPrintf
0x18008f611  jmp     loc_18008F6A5
0x18008f616  mov     dword ptr [rsp+58h+var_30], edi
0x18008f61a  mov     dword ptr [rsp+58h+var_38], ebx
0x18008f61e  lea     r9, aAiddAiddrpccli_7; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f625  mov     r8d, 209h
0x18008f62b  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f632  mov     ecx, 1
0x18008f637  call    AslLogCallPrintf
0x18008f63c  jmp     short loc_18008F6A5
0x18008f63e  mov     eax, cs:dword_18015C05C
0x18008f644  test    eax, eax
0x18008f646  jnz     short loc_18008F664
0x18008f648  lea     r9, aAiddAiddrpccli_24; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f64f  mov     r8d, 213h
0x18008f655  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f65c  lea     ecx, [rax+3]
0x18008f65f  call    AslLogCallPrintf
0x18008f664  mov     cs:dword_18015C05C, 1
0x18008f66e  mov     cs:dword_18015C088, 0
0x18008f678  mov     cs:qword_18015C068, 0
0x18008f683  mov     dword ptr [rsp+58h+var_38], edi
0x18008f687  lea     r9, aAiddAiddrpccli_9; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f68e  mov     r8d, 219h
0x18008f694  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f69b  mov     ecx, 3
0x18008f6a0  call    AslLogCallPrintf
0x18008f6a5  jmp     loc_18008F7AC
0x18008f6aa  mov     edi, eax
0x18008f6ac  mov     edx, eax
0x18008f6ae  sub     edx, 6B3h
0x18008f6b4  jz      short loc_18008F6CE
0x18008f6b6  sub     edx, 2
0x18008f6b9  jz      short loc_18008F6CE
0x18008f6bb  sub     edx, 5
0x18008f6be  jz      short loc_18008F6CE
0x18008f6c0  sub     edx, 1
0x18008f6c3  jz      short loc_18008F6CE
0x18008f6c5  cmp     edx, 1Eh
0x18008f6c8  jz      short loc_18008F6CE
0x18008f6ca  xor     eax, eax
0x18008f6cc  jmp     short loc_18008F6D3
0x18008f6ce  mov     eax, 1
0x18008f6d3  test    eax, eax
0x18008f6d5  jz      loc_18008F781
0x18008f6db  mov     eax, 1
0x18008f6e0  lock xadd cs:dword_18015C088, eax
0x18008f6e8  inc     eax
0x18008f6ea  mov     cs:dword_18015C05C, 0
0x18008f6f4  cmp     eax, 5
0x18008f6f7  jl      short loc_18008F751
0x18008f6f9  lea     ecx, [rax-5]
0x18008f6fc  mov     eax, 1
0x18008f701  shl     eax, cl
0x18008f703  imul    ebx, eax, 1388h
0x18008f709  mov     eax, 0EA60h
0x18008f70e  cmp     ebx, eax
0x18008f710  cmova   ebx, eax
0x18008f713  call    cs:__imp_GetTickCount64
0x18008f719  movsxd  rcx, ebx
0x18008f71c  add     rax, rcx
0x18008f71f  mov     cs:qword_18015C068, rax
0x18008f726  mov     dword ptr [rsp+58h+var_30], ebx
0x18008f72a  mov     dword ptr [rsp+58h+var_38], edi
0x18008f72e  lea     r9, aAiddAiddrpccli_2; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f735  mov     r8d, 236h
0x18008f73b  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f742  mov     ecx, 3
0x18008f747  call    AslLogCallPrintf
0x18008f74c  jmp     loc_18008F3F4
0x18008f751  mov     [rsp+58h+var_28], eax
0x18008f755  mov     eax, [rsp+58h+var_18]
0x18008f759  mov     dword ptr [rsp+58h+var_30], eax
0x18008f75d  mov     dword ptr [rsp+58h+var_38], edi
0x18008f761  lea     r9, aAiddAiddrpccli_17; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f768  mov     r8d, 23Fh
0x18008f76e  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f775  mov     ecx, 3
0x18008f77a  call    AslLogCallPrintf
0x18008f77f  jmp     short loc_18008F7AC
0x18008f781  mov     eax, [rsp+58h+var_18]
0x18008f785  mov     dword ptr [rsp+58h+var_30], eax
0x18008f789  mov     dword ptr [rsp+58h+var_38], edi
0x18008f78d  lea     r9, aAiddAiddrpccli_20; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f794  mov     r8d, 248h
0x18008f79a  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f7a1  mov     ecx, 1
0x18008f7a6  call    AslLogCallPrintf
0x18008f7ab  nop
0x18008f7ac  jmp     loc_18008F46B
0x18008f7b1  jmp     short loc_18008F7D6
0x18008f7b3  mov     dword ptr [rsp+58h+var_38], eax
0x18008f7b7  lea     r9, aAiddAiddrpccli_33; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f7be  mov     r8d, 251h
0x18008f7c4  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f7cb  mov     ecx, 1
0x18008f7d0  call    AslLogCallPrintf
0x18008f7d5  nop
0x18008f7d6  lea     r9, aAiddAiddrpccli_21; "AIDD: AiddRpcClient_AsyncWorkerThread: "...
0x18008f7dd  mov     r8d, 254h
0x18008f7e3  lea     rdx, aAiddrpcclientA; "AiddRpcClient_AsyncWorkerThread"
0x18008f7ea  mov     ecx, 3
0x18008f7ef  call    AslLogCallPrintf
0x18008f7f4  xor     eax, eax
0x18008f7f6  mov     rbx, [rsp+58h+arg_0]
0x18008f7fb  mov     rdi, [rsp+58h+arg_10]
0x18008f800  add     rsp, 50h
0x18008f804  pop     r14
0x18008f806  retn
```
