# DnsStopMulticastQuery

- ea: `0x180054880`
- end: `0x180054a40`
- name: `DnsStopMulticastQuery`
- size: `448`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052bb0`
- `0x180052f10`
- `0x1800541f0`
- `0x1800550d4`
- `0x1800737dc`
- `0x18007bf20`
- `0x1800aaa24`

## callees

- `0x180054880`
- `0x180054a48`
- `0x180054d24`
- `0x180054dc8`
- `0x180085d94`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800e4010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180054a07`
- `ntdll!RtlNtStatusToDosError` at `0x180054a07`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180054929`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180054929`
- `RPCRT4!RpcSmDestroyClientContext` at `0x1800549f4`
- `RPCRT4!RpcSmDestroyClientContext` at `0x1800549f4`

## pseudocode

```c
__int64 __fastcall DnsStopMulticastQuery(const struct _WNF_STATE_NAME *a1)
{
  unsigned int v2; // edx
  ULONG v3; // esi
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  WnfParams *v6; // rdi
  void *ContextHandle; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v9[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v10[528]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(v10, 0, 0x20Cu);
  ContextHandle = 0;
  memset(v9, 0, sizeof(v9));
  if ( a1 )
  {
    ContextHandle = RemoveMDnsMQueryEntry(a1 + 67);
    if ( !ContextHandle && (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_(1035, 52, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids);
    CopyMdnsQueryHandleToRpcQueryHandle(v10, a1);
    v3 = DnsStopMdnsQuery((struct _MDNS_RPC_QUERY_HANDLE *)v10, &ContextHandle);
    if ( ContextHandle )
      RpcSmDestroyClientContext(&ContextHandle);
    if ( a1[65] )
    {
      v4 = RtlUnsubscribeWnfNotificationWaitForCompletion();
      a1[65] = 0;
      v5 = v4;
      if ( v4 < 0 )
      {
        v3 = RtlNtStatusToDosError(v4);
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 53, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids, v5);
      }
    }
    v6 = (WnfParams *)a1[66];
    if ( v6 )
    {
      if ( *(_QWORD *)v6 && *(_QWORD *)(*(_QWORD *)v6 + 40LL) )
      {
        DWORD1(v9[0]) = 1223;
        LODWORD(v9[0]) = **(_DWORD **)v6;
        (*(void (__fastcall **)(_QWORD, __int64, _OWORD *))(*(_QWORD *)v6 + 40LL))(
          *(_QWORD *)(*(_QWORD *)v6 + 48LL),
          (__int64)v6 + 16,
          v9);
      }
      a1[66] = 0;
      WnfParams::`scalar deleting destructor'(v6, v2);
    }
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x180054880  push    rbp
0x180054882  push    rbx
0x180054883  push    rsi
0x180054884  push    rdi
0x180054885  lea     rbp, [rsp-178h]
0x18005488d  sub     rsp, 278h
0x180054894  mov     rax, cs:__security_cookie
0x18005489b  xor     rax, rsp
0x18005489e  mov     [rbp+190h+var_30], rax
0x1800548a5  mov     rbx, rcx
0x1800548a8  xor     edx, edx; Val
0x1800548aa  lea     rcx, [rsp+290h+var_240]; void *
0x1800548af  mov     r8d, 20Ch; Size
0x1800548b5  call    memset_0
0x1800548ba  mov     [rsp+290h+ContextHandle], 0
0x1800548c3  xorps   xmm0, xmm0
0x1800548c6  movups  [rsp+290h+var_268], xmm0
0x1800548cb  movups  [rsp+290h+var_258], xmm0
0x1800548d0  test    rbx, rbx
0x1800548d3  jz      loc_1800549C0
0x1800548d9  lea     rcx, [rbx+218h]; struct _WNF_STATE_NAME *
0x1800548e0  call    ?RemoveMDnsMQueryEntry@@YAPEAXPEBU_WNF_STATE_NAME@@@Z; RemoveMDnsMQueryEntry(_WNF_STATE_NAME const *)
0x1800548e5  mov     [rsp+290h+ContextHandle], rax
0x1800548ea  test    rax, rax
0x1800548ed  jz      loc_1800549C7
0x1800548f3  mov     rdx, rbx
0x1800548f6  lea     rcx, [rsp+290h+var_240]
0x1800548fb  call    CopyMdnsQueryHandleToRpcQueryHandle
0x180054900  lea     rdx, [rsp+290h+ContextHandle]; void **
0x180054905  lea     rcx, [rsp+290h+var_240]; struct _MDNS_RPC_QUERY_HANDLE *
0x18005490a  call    ?DnsStopMdnsQuery@@YAKPEAU_MDNS_RPC_QUERY_HANDLE@@PEAPEAX@Z; DnsStopMdnsQuery(_MDNS_RPC_QUERY_HANDLE *,void * *)
0x18005490f  mov     esi, eax
0x180054911  cmp     [rsp+290h+ContextHandle], 0
0x180054917  jnz     loc_1800549EF
0x18005491d  mov     rcx, [rbx+208h]
0x180054924  test    rcx, rcx
0x180054927  jz      short loc_18005494A
0x180054929  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180054930  nop     dword ptr [rax+rax+00h]
0x180054935  mov     qword ptr [rbx+208h], 0
0x180054940  mov     edi, eax
0x180054942  test    eax, eax
0x180054944  js      loc_180054A05
0x18005494a  mov     rdi, [rbx+210h]
0x180054951  test    rdi, rdi
0x180054954  jz      short loc_1800549A2
0x180054956  mov     rax, [rdi]
0x180054959  test    rax, rax
0x18005495c  jz      short loc_18005498F
0x18005495e  cmp     qword ptr [rax+28h], 0
0x180054963  jz      short loc_18005498F
0x180054965  mov     dword ptr [rsp+290h+var_268+4], 4C7h
0x18005496d  lea     r8, [rsp+290h+var_268]
0x180054972  mov     rax, [rdi]
0x180054975  mov     edx, [rax]
0x180054977  mov     dword ptr [rsp+290h+var_268], edx
0x18005497b  lea     rdx, [rdi+10h]
0x18005497f  mov     rax, [rdi]
0x180054982  mov     rcx, [rax+30h]
0x180054986  mov     rax, [rax+28h]
0x18005498a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005498f  mov     rcx, rdi; this
0x180054992  mov     qword ptr [rbx+210h], 0
0x18005499d  call    ??_GWnfParams@@QEAAPEAXI@Z; WnfParams::`scalar deleting destructor'(uint)
0x1800549a2  mov     eax, esi
0x1800549a4  mov     rcx, [rbp+190h+var_30]
0x1800549ab  xor     rcx, rsp; StackCookie
0x1800549ae  call    __security_check_cookie
0x1800549b3  add     rsp, 278h
0x1800549ba  pop     rdi
0x1800549bb  pop     rsi
0x1800549bc  pop     rbx
0x1800549bd  pop     rbp
0x1800549be  retn
0x1800549c0  mov     esi, 57h ; 'W'
0x1800549c5  jmp     short loc_1800549A2
0x1800549c7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800549ce  jz      loc_1800548F3
0x1800549d4  mov     edx, 34h ; '4'
0x1800549d9  lea     r8, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids
0x1800549e0  mov     ecx, 40Bh
0x1800549e5  call    WPP_SF_
0x1800549ea  jmp     loc_1800548F3
0x1800549ef  lea     rcx, [rsp+290h+ContextHandle]; ContextHandle
0x1800549f4  call    cs:__imp_RpcSmDestroyClientContext
0x1800549fb  nop     dword ptr [rax+rax+00h]
0x180054a00  jmp     loc_18005491D
0x180054a05  mov     ecx, edi; Status
0x180054a07  call    cs:__imp_RtlNtStatusToDosError
0x180054a0e  nop     dword ptr [rax+rax+00h]
0x180054a13  mov     esi, eax
0x180054a15  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180054a1c  jz      loc_18005494A
0x180054a22  mov     edx, 35h ; '5'
0x180054a27  lea     r8, WPP_acb40cfb6d3c3959d374627950e51c28_Traceguids
0x180054a2e  mov     ecx, 40Bh
0x180054a33  mov     r9d, edi
0x180054a36  call    WPP_SF_d
0x180054a3b  jmp     loc_18005494A
```
