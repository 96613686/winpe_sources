# RemoveRecvCtxtFromGlobalList

- ea: `0x180010308`
- end: `0x18001042a`
- name: `RemoveRecvCtxtFromGlobalList`
- size: `290`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180016d60`
- `0x1800261d4`
- `0x180030e74`
- `0x180033480`

## callees

- `0x180010308`
- `0x18004d1e0`
- `0x18004d958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010385`
- `WS2_32!WSASetEvent` at `0x18001041a`
- `WS2_32!WSASetEvent` at `0x18001041a`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800103b0`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800103b0`
- `WS2_32!WSACloseEvent` at `0x1800103dc`
- `WS2_32!WSACloseEvent` at `0x1800103dc`

## pseudocode

```c
void __fastcall RemoveRecvCtxtFromGlobalList(__int64 *a1, int a2)
{
  DWORD v4; // eax
  __int64 *v5; // rdx
  DWORD v6; // esi
  __int64 **v7; // rcx
  HANDLE hEvents; // [rsp+40h] [rbp+8h] BYREF

  hEvents = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 22, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, a1, a2);
  if ( a1 )
  {
    EnterCriticalSection(&DhcpGlobalRecvFromCritSect);
    if ( (__int64 *)*a1 != a1 )
    {
      hEvents = (HANDLE)a1[7];
      v4 = WSAWaitForMultipleEvents(1u, &hEvents, 0, 0, 0);
      v5 = (__int64 *)*a1;
      v6 = v4;
      if ( *(__int64 **)(*a1 + 8) != a1 || (v7 = (__int64 **)a1[1], *v7 != a1) )
        __fastfail(3u);
      *v7 = v5;
      v5[1] = (__int64)v7;
      a1[1] = (__int64)a1;
      *a1 = (__int64)a1;
      WSACloseEvent((HANDLE)a1[7]);
      if ( (!v6 && !*((_DWORD *)a1 + 16) || a2) && DhcpGlobalRecvFromList != (_UNKNOWN *)&DhcpGlobalRecvFromList )
        WSASetEvent(*((HANDLE *)DhcpGlobalRecvFromList + 7));
    }
    LeaveCriticalSection(&DhcpGlobalRecvFromCritSect);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 23, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids);
}

```

## disassembly

```asm
0x180010308  mov     rax, rsp
0x18001030b  mov     [rax+10h], rbx
0x18001030f  mov     [rax+18h], rsi
0x180010313  push    rdi
0x180010314  sub     rsp, 30h
0x180010318  mov     edi, edx
0x18001031a  mov     qword ptr [rax+8], 0
0x180010322  mov     rbx, rcx
0x180010325  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001032c  jz      short loc_18001034A
0x18001032e  mov     edx, 16h
0x180010333  mov     [rax-18h], edi
0x180010336  mov     ecx, 404h
0x18001033b  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180010342  mov     r9, rbx
0x180010345  call    WPP_SF_qD
0x18001034a  test    rbx, rbx
0x18001034d  jnz     short loc_18001037E
0x18001034f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180010356  jz      short loc_18001036E
0x180010358  mov     edx, 17h
0x18001035d  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180010364  mov     ecx, 404h
0x180010369  call    WPP_SF_
0x18001036e  mov     rbx, [rsp+38h+arg_8]
0x180010373  mov     rsi, [rsp+38h+arg_10]
0x180010378  add     rsp, 30h
0x18001037c  pop     rdi
0x18001037d  retn
0x18001037e  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x180010385  call    cs:__imp_EnterCriticalSection
0x18001038b  cmp     [rbx], rbx
0x18001038e  jz      short loc_1800103EA
0x180010390  mov     rax, [rbx+38h]
0x180010394  lea     rdx, [rsp+38h+hEvents]; lphEvents
0x180010399  xor     r9d, r9d; dwTimeout
0x18001039c  mov     [rsp+38h+hEvents], rax
0x1800103a1  xor     r8d, r8d; fWaitAll
0x1800103a4  mov     [rsp+38h+fAlertable], 0; fAlertable
0x1800103ac  lea     ecx, [r9+1]; cEvents
0x1800103b0  call    cs:__imp_WSAWaitForMultipleEvents
0x1800103b6  mov     rdx, [rbx]
0x1800103b9  mov     esi, eax
0x1800103bb  cmp     [rdx+8], rbx
0x1800103bf  jnz     short loc_1800103FC
0x1800103c1  mov     rcx, [rbx+8]
0x1800103c5  cmp     [rcx], rbx
0x1800103c8  jnz     short loc_1800103FC
0x1800103ca  mov     [rcx], rdx
0x1800103cd  mov     [rdx+8], rcx
0x1800103d1  mov     [rbx+8], rbx
0x1800103d5  mov     [rbx], rbx
0x1800103d8  mov     rcx, [rbx+38h]; hEvent
0x1800103dc  call    cs:__imp_WSACloseEvent
0x1800103e2  test    esi, esi
0x1800103e4  jz      short loc_180010422
0x1800103e6  test    edi, edi
0x1800103e8  jnz     short loc_180010403
0x1800103ea  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x1800103f1  call    cs:__imp_LeaveCriticalSection
0x1800103f7  jmp     loc_18001034F
0x1800103fc  mov     ecx, 3
0x180010401  int     29h; Win8: RtlFailFast(ecx)
0x180010403  mov     rcx, cs:DhcpGlobalRecvFromList
0x18001040a  lea     rax, DhcpGlobalRecvFromList
0x180010411  cmp     rcx, rax
0x180010414  jz      short loc_1800103EA
0x180010416  mov     rcx, [rcx+38h]; hEvent
0x18001041a  call    cs:__imp_WSASetEvent
0x180010420  jmp     short loc_1800103EA
0x180010422  cmp     dword ptr [rbx+40h], 0
0x180010426  jz      short loc_180010403
0x180010428  jmp     short loc_1800103E6
```
