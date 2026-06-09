# ResolveContext::StartDnsQueries(_DNS_SERVICE_RESOLVE_REQUEST *,_DNS_SERVICE_CANCEL *)

- ea: `0x180055efc`
- end: `0x18005621f`
- name: `?StartDnsQueries@ResolveContext@@SAJPEAU_DNS_SERVICE_RESOLVE_REQUEST@@PEAU_DNS_SERVICE_CANCEL@@@Z`
- size: `803`
- prototype: `__int64 __fastcall(struct _DNS_SERVICE_RESOLVE_REQUEST *, struct _DNS_SERVICE_CANCEL *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054050`

## callees

- `0x180012510`
- `0x18005464c`
- `0x18005536c`
- `0x180055efc`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dbc44`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800dfdc8`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800561cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800561cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005613c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005613c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056187`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056187`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005600f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005600f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056167`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056167`

## pseudocode

```c
__int64 __fastcall ResolveContext::StartDnsQueries(
        struct _DNS_SERVICE_RESOLVE_REQUEST *a1,
        struct _DNS_SERVICE_CANCEL *a2)
{
  HANDLE EventW; // rsi
  DWORD LastError; // edi
  CallbackContext *v6; // rbx
  char v7; // al
  unsigned int v8; // eax
  void *v10; // rcx
  int v11; // r14d
  CallbackContext *v13; // [rsp+30h] [rbp-69h] BYREF
  struct _DNS_QUERY_REQUEST pQueryRequest; // [rsp+40h] [rbp-59h] BYREF
  struct _DNS_QUERY_REQUEST v15; // [rsp+80h] [rbp-19h] BYREF

  v13 = 0;
  memset_0(&pQueryRequest, 0, sizeof(pQueryRequest));
  memset_0(&v15, 0, sizeof(v15));
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_qq(1035, 70, (unsigned int)WPP_5d3becedec4b303253ed7989a2efa646_Traceguids, (_DWORD)a1, (__int64)a2);
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SDD(
        1035,
        71,
        (unsigned int)WPP_5d3becedec4b303253ed7989a2efa646_Traceguids,
        *((_QWORD *)a1 + 1),
        *(_DWORD *)a1,
        *((_DWORD *)a1 + 1));
  }
  pQueryRequest.QueryName = (PCWSTR)*((_QWORD *)a1 + 1);
  pQueryRequest.Version = *(_DWORD *)a1;
  pQueryRequest.InterfaceIndex = *((_DWORD *)a1 + 1);
  pQueryRequest.pQueryCompletionCallback = (PDNS_QUERY_COMPLETION_ROUTINE)CallbackContext::StaticCallback;
  pQueryRequest.QueryOptions = 0;
  *(_OWORD *)&v15.QueryType = *(unsigned __int64 *)&pQueryRequest.QueryType;
  pQueryRequest.QueryType = 33;
  *(_OWORD *)&v15.Version = *(_OWORD *)&pQueryRequest.Version;
  v15.QueryType = 16;
  *(_OWORD *)&v15.pDnsServerList = *(_OWORD *)&pQueryRequest.pDnsServerList;
  *(_OWORD *)&v15.pQueryCompletionCallback = *(_OWORD *)&pQueryRequest.pQueryCompletionCallback;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    LastError = ResolveContext::CreateInstance(0, a1, a2, &v13);
    if ( LastError )
    {
      CloseHandle(EventW);
    }
    else
    {
      v6 = v13;
      *((_QWORD *)v13 + 322) = EventW;
      pQueryRequest.pQueryContext = v6;
      v15.pQueryContext = v6;
      *((_DWORD *)v6 + 50) = 1;
      *((_DWORD *)v6 + 51) = 1;
      *((_DWORD *)v6 + 646) = 2;
      LastError = DnsQueryEx(
                    &pQueryRequest,
                    (PDNS_QUERY_RESULT)((char *)v6 + 88),
                    (PDNS_QUERY_CANCEL)((char *)v6 + 304));
      v7 = BYTE1(xmmword_1801119E0);
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        WPP_SF_d(1035, 72, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids, LastError);
        v7 = BYTE1(xmmword_1801119E0);
      }
      if ( LastError == 9506 )
      {
        v8 = DnsQueryEx(&v15, (PDNS_QUERY_RESULT)((char *)v6 + 368), (PDNS_QUERY_CANCEL)((char *)v6 + 336));
        LastError = v8;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 74, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids, v8);
        if ( LastError != 9506 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 256));
          *((_DWORD *)v6 + 51) = 0;
          if ( (*((_DWORD *)v6 + 646))-- == 1 )
          {
            v10 = (void *)*((_QWORD *)v6 + 322);
            if ( v10 )
              SetEvent(v10);
          }
          v11 = *((_DWORD *)v6 + 74);
          *((_DWORD *)v6 + 74) = 1;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 256));
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_(1035, 75, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids);
          if ( v11 )
            LastError = 9506;
          else
            (*(void (__fastcall **)(CallbackContext *))(*(_QWORD *)v6 + 16LL))(v6);
        }
      }
      else
      {
        if ( (v7 & 8) != 0 )
          WPP_SF_(1035, 73, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids);
        *((_QWORD *)v6 + 25) = 0;
        *((_DWORD *)v6 + 646) = 0;
        CallbackContext::deref(v6);
      }
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 76, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180055efc  mov     [rsp-8+arg_10], rbx
0x180055f01  mov     [rsp-8+arg_18], rsi
0x180055f06  push    rbp
0x180055f07  push    rdi
0x180055f08  push    r12
0x180055f0a  push    r13
0x180055f0c  push    r14
0x180055f0e  lea     rbp, [rsp-37h]
0x180055f13  sub     rsp, 0D0h
0x180055f1a  mov     rax, cs:__security_cookie
0x180055f21  xor     rax, rsp
0x180055f24  mov     [rbp+57h+var_30], rax
0x180055f28  mov     rdi, rdx
0x180055f2b  mov     [rbp+57h+var_C0], 0
0x180055f33  mov     rbx, rcx
0x180055f36  mov     esi, 40h ; '@'
0x180055f3b  mov     r8d, esi; Size
0x180055f3e  lea     rcx, [rbp+57h+pQueryRequest]; void *
0x180055f42  xor     edx, edx; Val
0x180055f44  call    memset_0
0x180055f49  mov     r8d, esi; Size
0x180055f4c  lea     rcx, [rbp+57h+var_70]; void *
0x180055f50  xor     edx, edx; Val
0x180055f52  call    memset_0
0x180055f57  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180055f5d  lea     r13, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids
0x180055f64  mov     r12d, 40Bh
0x180055f6a  test    al, 8
0x180055f6c  jz      short loc_180055FAD
0x180055f6e  lea     edx, [rsi+6]
0x180055f71  mov     [rsp+0F0h+var_D0], rdi
0x180055f76  mov     ecx, r12d
0x180055f79  mov     r9, rbx
0x180055f7c  mov     r8, r13
0x180055f7f  call    WPP_SF_qq
0x180055f84  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180055f8a  test    al, 8
0x180055f8c  jz      short loc_180055FAD
0x180055f8e  mov     eax, [rbx+4]
0x180055f91  lea     edx, [rsi+7]
0x180055f94  mov     r9, [rbx+8]
0x180055f98  mov     ecx, r12d
0x180055f9b  mov     [rsp+0F0h+var_C8], eax
0x180055f9f  mov     r8, r13
0x180055fa2  mov     eax, [rbx]
0x180055fa4  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180055fa8  call    WPP_SF_SDD
0x180055fad  mov     rax, [rbx+8]
0x180055fb1  xor     r9d, r9d; lpName
0x180055fb4  mov     [rbp+57h+pQueryRequest.QueryName], rax
0x180055fb8  xor     r8d, r8d; bInitialState
0x180055fbb  mov     eax, [rbx]
0x180055fbd  xor     edx, edx; bManualReset
0x180055fbf  mov     [rbp+57h+pQueryRequest.Version], eax
0x180055fc2  xor     ecx, ecx; lpEventAttributes
0x180055fc4  mov     eax, [rbx+4]
0x180055fc7  movaps  xmm0, xmmword ptr [rbp+57h+pQueryRequest.Version]
0x180055fcb  mov     [rbp+57h+pQueryRequest.InterfaceIndex], eax
0x180055fce  lea     rax, ?StaticCallback@CallbackContext@@SAXPEAXPEAU_DNS_QUERY_RESULT@@@Z; CallbackContext::StaticCallback(void *,_DNS_QUERY_RESULT *)
0x180055fd5  mov     [rbp+57h+pQueryRequest.pQueryCompletionCallback], rax
0x180055fd9  mov     eax, 21h ; '!'
0x180055fde  mov     [rbp+57h+pQueryRequest.QueryOptions], 0
0x180055fe6  movaps  xmm1, xmmword ptr [rbp+57h+pQueryRequest.QueryType]
0x180055fea  movaps  xmmword ptr [rbp+57h+var_70.QueryType], xmm1
0x180055fee  movaps  xmm1, xmmword ptr [rbp+57h+pQueryRequest.pQueryCompletionCallback]
0x180055ff2  mov     [rbp+57h+pQueryRequest.QueryType], ax
0x180055ff6  mov     eax, 10h
0x180055ffb  movaps  xmmword ptr [rbp+57h+var_70.Version], xmm0
0x180055fff  movaps  xmm0, xmmword ptr [rbp-39h]
0x180056003  mov     [rbp+57h+var_70.QueryType], ax
0x180056007  movaps  xmmword ptr [rbp+57h+var_70.pDnsServerList], xmm0
0x18005600b  movaps  xmmword ptr [rbp+57h+var_70.pQueryCompletionCallback], xmm1
0x18005600f  call    cs:__imp_CreateEventW
0x180056016  nop     dword ptr [rax+rax+00h]
0x18005601b  mov     rsi, rax
0x18005601e  test    rax, rax
0x180056021  jnz     short loc_180056036
0x180056023  call    cs:__imp_GetLastError
0x18005602a  nop     dword ptr [rax+rax+00h]
0x18005602f  mov     edi, eax
0x180056031  jmp     loc_1800561D8
0x180056036  lea     r9, [rbp+57h+var_C0]
0x18005603a  mov     r8, rdi
0x18005603d  mov     rdx, rbx
0x180056040  xor     ecx, ecx
0x180056042  call    ?CreateInstance@ResolveContext@@SAKW4QueryType@CallbackContext@@PEAU_DNS_SERVICE_RESOLVE_REQUEST@@PEAU_DNS_SERVICE_CANCEL@@PEAPEAV1@@Z; ResolveContext::CreateInstance(CallbackContext::QueryType,_DNS_SERVICE_RESOLVE_REQUEST *,_DNS_SERVICE_CANCEL *,ResolveContext * *)
0x180056047  mov     edi, eax
0x180056049  test    eax, eax
0x18005604b  jnz     loc_1800561C9
0x180056051  mov     rbx, [rbp+57h+var_C0]
0x180056055  lea     eax, [rdi+1]
0x180056058  lea     rcx, [rbp+57h+pQueryRequest]; pQueryRequest
0x18005605c  mov     [rbx+0A10h], rsi
0x180056063  lea     r8, [rbx+130h]; pCancelHandle
0x18005606a  mov     [rbp+57h+pQueryRequest.pQueryContext], rbx
0x18005606e  lea     rdx, [rbx+58h]; pQueryResults
0x180056072  mov     [rbp+57h+var_70.pQueryContext], rbx
0x180056076  mov     [rbx+0C8h], eax
0x18005607c  mov     [rbx+0CCh], eax
0x180056082  mov     dword ptr [rbx+0A18h], 2
0x18005608c  call    DnsQueryEx
0x180056091  mov     edi, eax
0x180056093  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180056099  test    al, 8
0x18005609b  jz      short loc_1800560B6
0x18005609d  mov     edx, 48h ; 'H'
0x1800560a2  mov     ecx, r12d
0x1800560a5  mov     r9d, edi
0x1800560a8  mov     r8, r13
0x1800560ab  call    WPP_SF_d
0x1800560b0  mov     al, byte ptr cs:xmmword_1801119E0+1
0x1800560b6  mov     esi, 2522h
0x1800560bb  cmp     edi, esi
0x1800560bd  jz      short loc_1800560F5
0x1800560bf  test    al, 8
0x1800560c1  jz      short loc_1800560D3
0x1800560c3  mov     edx, 49h ; 'I'
0x1800560c8  mov     ecx, r12d
0x1800560cb  mov     r8, r13
0x1800560ce  call    WPP_SF_
0x1800560d3  mov     qword ptr [rbx+0C8h], 0
0x1800560de  mov     rcx, rbx; this
0x1800560e1  mov     dword ptr [rbx+0A18h], 0
0x1800560eb  call    ?deref@CallbackContext@@QEAAKXZ; CallbackContext::deref(void)
0x1800560f0  jmp     loc_1800561D8
0x1800560f5  lea     r8, [rbx+150h]; pCancelHandle
0x1800560fc  lea     rdx, [rbx+170h]; pQueryResults
0x180056103  lea     rcx, [rbp+57h+var_70]; pQueryRequest
0x180056107  call    DnsQueryEx
0x18005610c  mov     edi, eax
0x18005610e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180056115  jz      short loc_18005612A
0x180056117  mov     edx, 4Ah ; 'J'
0x18005611c  mov     ecx, r12d
0x18005611f  mov     r9d, eax
0x180056122  mov     r8, r13
0x180056125  call    WPP_SF_d
0x18005612a  cmp     edi, esi
0x18005612c  jz      loc_1800561D8
0x180056132  lea     rsi, [rbx+100h]
0x180056139  mov     rcx, rsi; lpCriticalSection
0x18005613c  call    cs:__imp_EnterCriticalSection
0x180056143  nop     dword ptr [rax+rax+00h]
0x180056148  mov     dword ptr [rbx+0CCh], 0
0x180056152  add     dword ptr [rbx+0A18h], 0FFFFFFFFh
0x180056159  jnz     short loc_180056173
0x18005615b  mov     rcx, [rbx+0A10h]; hEvent
0x180056162  test    rcx, rcx
0x180056165  jz      short loc_180056173
0x180056167  call    cs:__imp_SetEvent
0x18005616e  nop     dword ptr [rax+rax+00h]
0x180056173  mov     r14d, [rbx+128h]
0x18005617a  mov     rcx, rsi; lpCriticalSection
0x18005617d  mov     dword ptr [rbx+128h], 1
0x180056187  call    cs:__imp_LeaveCriticalSection
0x18005618e  nop     dword ptr [rax+rax+00h]
0x180056193  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005619a  jz      short loc_1800561AC
0x18005619c  mov     edx, 4Bh ; 'K'
0x1800561a1  mov     ecx, r12d
0x1800561a4  mov     r8, r13
0x1800561a7  call    WPP_SF_
0x1800561ac  test    r14d, r14d
0x1800561af  jz      short loc_1800561B8
0x1800561b1  mov     edi, 2522h
0x1800561b6  jmp     short loc_1800561D8
0x1800561b8  mov     rax, [rbx]
0x1800561bb  mov     rcx, rbx
0x1800561be  mov     rax, [rax+10h]
0x1800561c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561c7  jmp     short loc_1800561D8
0x1800561c9  mov     rcx, rsi; hObject
0x1800561cc  call    cs:__imp_CloseHandle
0x1800561d3  nop     dword ptr [rax+rax+00h]
0x1800561d8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800561df  jz      short loc_1800561F4
0x1800561e1  mov     edx, 4Ch ; 'L'
0x1800561e6  mov     ecx, r12d
0x1800561e9  mov     r9d, edi
0x1800561ec  mov     r8, r13
0x1800561ef  call    WPP_SF_d
0x1800561f4  mov     eax, edi
0x1800561f6  mov     rcx, [rbp+57h+var_30]
0x1800561fa  xor     rcx, rsp; StackCookie
0x1800561fd  call    __security_check_cookie
0x180056202  lea     r11, [rsp+0F0h+var_20]
0x18005620a  mov     rbx, [r11+40h]
0x18005620e  mov     rsi, [r11+48h]
0x180056212  mov     rsp, r11
0x180056215  pop     r14
0x180056217  pop     r13
0x180056219  pop     r12
0x18005621b  pop     rdi
0x18005621c  pop     rbp
0x18005621d  retn
```
