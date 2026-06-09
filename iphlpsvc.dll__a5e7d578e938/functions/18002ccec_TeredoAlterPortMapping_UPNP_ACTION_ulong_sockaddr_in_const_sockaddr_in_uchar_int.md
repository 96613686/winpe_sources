# TeredoAlterPortMapping(_UPNP_ACTION,ulong,sockaddr_in const *,sockaddr_in *,uchar *,int *)

- ea: `0x18002ccec`
- end: `0x18002d207`
- name: `?TeredoAlterPortMapping@@YAXW4_UPNP_ACTION@@KPEBUsockaddr_in@@PEAU2@PEAEPEAH@Z`
- size: `1307`
- prototype: `void __fastcall(unsigned int, unsigned int, SOCKADDR *, __int64, _BYTE *, _DWORD *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002cb98`
- `0x180042348`
- `0x180076514`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x180029f9c`
- `0x18002b560`
- `0x18002ccec`
- `0x1800423f0`
- `0x18004b5f0`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ce2e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ce2e`
- `WS2_32!GetNameInfoW` at `0x18002cf33`
- `WS2_32!GetNameInfoW` at `0x18002cf33`
- `WS2_32!__imp_htons` at `0x18002d0a2`
- `WS2_32!__imp_htons` at `0x18002d0a2`
- `WS2_32!__imp_ntohs` at `0x18002cf96`
- `WS2_32!__imp_ntohs` at `0x18002cff5`
- `WS2_32!__imp_ntohs` at `0x18002d00d`
- `WS2_32!__imp_ntohs` at `0x18002d104`
- `WS2_32!__imp_ntohs` at `0x18002cf96`
- `WS2_32!__imp_ntohs` at `0x18002cff5`
- `WS2_32!__imp_ntohs` at `0x18002d00d`
- `WS2_32!__imp_ntohs` at `0x18002d104`
- `WS2_32!__imp_WSAGetLastError` at `0x18002cf43`
- `WS2_32!__imp_WSAGetLastError` at `0x18002cf43`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d1d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d1d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cdab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cdab`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002cd64`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002cd64`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cea0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cee8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf5f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cea0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cee8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d15a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d16e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d182`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d15a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d16e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d182`

## string_xrefs

- `0x18002cdbe`: `CoCreateInstance failed for altering UPnP mapping (hr 0x%08x)!`
- `0x18002cfd2`: `UPnP NAT external previous mapping could not be deleted: error (%d)`
- `0x18002d146`: `UPnP mapping could not be deleted: error (%d)`

## pseudocode

```c
void __fastcall TeredoAlterPortMapping(
        unsigned int a1,
        unsigned int a2,
        SOCKADDR *a3,
        __int64 a4,
        _BYTE *a5,
        _DWORD *a6)
{
  HRESULT v8; // eax
  HRESULT v9; // eax
  int i; // eax
  __int64 v11; // rcx
  DWORD v12; // ebx
  unsigned int v13; // ebx
  SOCKADDR *v14; // rdi
  OLECHAR *v15; // r13
  OLECHAR *v16; // r14
  OLECHAR *v17; // r12
  unsigned int Error; // eax
  unsigned int v19; // ebx
  int v20; // eax
  __int64 (__fastcall *v21)(__int64, _QWORD, OLECHAR *, _QWORD, OLECHAR *, DWORD, OLECHAR *, __int64 *); // rdi
  unsigned int v22; // ebx
  u_short v23; // ax
  int v24; // eax
  const unsigned __int16 *v25; // rcx
  struct in_addr v26; // eax
  u_short v27; // cx
  u_short v28; // ax
  OLECHAR *v29; // rcx
  __int64 (__fastcall *v30)(__int64, _QWORD, OLECHAR *); // rbx
  u_short v31; // ax
  int v32; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  __int64 ServiceBufferSize; // [rsp+28h] [rbp-D8h]
  DWORD ServiceBufferSizea; // [rsp+28h] [rbp-D8h]
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v38; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v40; // [rsp+68h] [rbp-98h] BYREF
  SOCKADDR *pSockaddr; // [rsp+70h] [rbp-90h]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v43; // [rsp+80h] [rbp-80h]
  WCHAR pNodeBuffer[1032]; // [rsp+90h] [rbp-70h] BYREF

  v37 = a1;
  pSockaddr = a3;
  *a6 = 0;
  v43 = a5;
  v40 = 0;
  v36 = 0;
  v38 = 0;
  v8 = CoInitializeEx(0, 4u);
  if ( v8 < 0 )
  {
    EventWriteError0(0x100000, L"CoInitializeEx failed for altering UPnP mapping (hr 0x%08x)!", (unsigned int)v8);
    return;
  }
  v9 = CoCreateInstance(&CLSID_UPnPNAT, 0, 1u, &GUID_b171c812_cc76_485a_94d8_b6b3a2794e99, &v40);
  if ( v9 >= 0 )
  {
    for ( i = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v40 + 56LL))(v40, &v36);
          ;
          i = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v40 + 56LL))(v40, &v36) )
    {
      v11 = v36;
      if ( i >= 0 )
      {
        if ( v36 )
          break;
      }
      if ( !a2 )
      {
        if ( i < 0 || !v36 )
        {
          EventWriteError0(
            0x100000,
            L"get_StaticPortMappingCollection for UPnP failed (hr 0x%08x, collection 0x%p)",
            (unsigned int)i,
            v36);
          goto LABEL_46;
        }
        break;
      }
      LODWORD(ServiceBufferSize) = a2;
      v12 = 1500;
      if ( a2 < 0x5DC )
        v12 = a2;
      LODWORD(ppv) = v12;
      EventWrite0(
        0x100000,
        L"Couldn't get static port mapping collection (hr 0x%08x, collection 0x%p), will retry after %u ms (%u total remaining)",
        (unsigned int)i,
        v36,
        ppv,
        ServiceBufferSize);
      Sleep(v12);
      a2 -= v12;
    }
    v13 = v37;
    *a6 = 1;
    if ( v13 == 2 )
      goto LABEL_47;
    v14 = pSockaddr;
    if ( !pSockaddr || !a4 || !a5 )
      goto LABEL_47;
    v15 = SysAllocString(L"UDP");
    if ( v15 )
    {
      v16 = 0;
      if ( v13 )
      {
        v17 = 0;
        if ( v13 == 1 )
        {
          v30 = *(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *))(*(_QWORD *)v36 + 80LL);
          v31 = ntohs(*(_WORD *)(a4 + 2));
          v32 = v30(v36, v31, v15);
          if ( v32 < 0 )
          {
            EventWriteError0(0x100000, L"UPnP mapping could not be deleted: error (%d)", (unsigned int)v32);
          }
          else
          {
            TeredoSetPreviousNatUPnPExternalPort(1, 0);
            *(_QWORD *)a4 = 2;
            *(_QWORD *)(a4 + 8) = 0;
            *v43 = 0;
          }
        }
      }
      else
      {
        v39 = 0;
        bstrString = 0;
        v37 = 0;
        v17 = SysAllocString(L"Teredo");
        if ( v17 )
        {
          if ( GetNameInfoW(v14, 16, pNodeBuffer, 0x401u, 0, 0, 2) )
          {
            Error = WSAGetLastError();
            EventWriteError0(0x100000, L"GetNameInfoW failed (err %i)!", Error);
          }
          else
          {
            v16 = SysAllocString(pNodeBuffer);
            if ( v16 )
            {
              if ( (int)TeredoGetPreviousNatUPnPExternalPort(&v38) >= 0 )
              {
                v19 = v38;
                if ( v38 )
                {
                  if ( v19 != ntohs(*(_WORD *)v14->sa_data) )
                  {
                    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *))(*(_QWORD *)v36 + 80LL))(v36, v19, v15);
                    if ( v20 < 0 )
                      EventWriteError0(
                        0x100000,
                        L"UPnP NAT external previous mapping could not be deleted: error (%d)",
                        (unsigned int)v20);
                    else
                      TeredoSetPreviousNatUPnPExternalPort(1, 0);
                  }
                }
              }
              v21 = *(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *, _QWORD, OLECHAR *, DWORD, OLECHAR *, __int64 *))(*(_QWORD *)v36 + 88LL);
              v22 = ntohs(*(_WORD *)pSockaddr->sa_data);
              v23 = ntohs(*(_WORD *)pSockaddr->sa_data);
              LOWORD(ServiceBufferSizea) = 1;
              v24 = v21(v36, v23, v15, v22, v16, ServiceBufferSizea, v17, &v39);
              if ( v24 < 0 )
              {
                EventWriteError0(0x100000, L"UPnP mapping failed to be added: error (%d)", (unsigned int)v24);
              }
              else
              {
                (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v39 + 56LL))(v39, &bstrString);
                (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 64LL))(v39, &v37);
                TeredoSetPreviousNatUPnPExternalPort(0, v37);
                v25 = bstrString;
                *(_WORD *)a4 = 2;
                v26 = inet_addrw(v25);
                v27 = v37;
                *(struct in_addr *)(a4 + 4) = v26;
                v28 = htons(v27);
                v29 = bstrString;
                *(_WORD *)(a4 + 2) = v28;
                *v43 = 1;
                SysFreeString(v29);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              }
            }
            else
            {
              EventWriteError0(0x100000, L"TeredoInternalIp failed");
            }
          }
        }
        else
        {
          EventWriteError0(0x100000, L"TeredoString failed");
        }
      }
      SysFreeString(v15);
      if ( v17 )
        SysFreeString(v17);
      if ( v16 )
        SysFreeString(v16);
    }
    else
    {
      EventWriteError0(0x100000, L"UdpString failed");
    }
  }
  else
  {
    EventWriteError0(0x100000, L"CoCreateInstance failed for altering UPnP mapping (hr 0x%08x)!", (unsigned int)v9);
  }
LABEL_46:
  v11 = v36;
LABEL_47:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v40 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
  CoUninitialize();
}

```

## disassembly

```asm
0x18002ccec  mov     [rsp-8+arg_0], rbx
0x18002ccf1  push    rbp
0x18002ccf2  push    rsi
0x18002ccf3  push    rdi
0x18002ccf4  push    r12
0x18002ccf6  push    r13
0x18002ccf8  push    r14
0x18002ccfa  push    r15
0x18002ccfc  lea     rbp, [rsp-7B0h]
0x18002cd04  sub     rsp, 8B0h
0x18002cd0b  mov     rax, cs:__security_cookie
0x18002cd12  xor     rax, rsp
0x18002cd15  mov     [rbp+7E0h+var_40], rax
0x18002cd1c  mov     r14, [rbp+7E0h+arg_28]
0x18002cd23  mov     edi, edx
0x18002cd25  mov     r12, [rbp+7E0h+arg_20]
0x18002cd2c  mov     edx, 4; dwCoInit
0x18002cd31  mov     [rsp+8E0h+var_888], ecx
0x18002cd35  mov     r15, r9
0x18002cd38  xor     ecx, ecx; pvReserved
0x18002cd3a  mov     [rsp+8E0h+pSockaddr], r8
0x18002cd3f  mov     dword ptr [r14], 0
0x18002cd46  mov     [rbp+7E0h+var_860], r12
0x18002cd4a  mov     [rsp+8E0h+var_878], 0
0x18002cd53  mov     [rsp+8E0h+var_890], 0
0x18002cd5c  mov     [rsp+8E0h+var_884], 0
0x18002cd64  call    cs:__imp_CoInitializeEx
0x18002cd6b  nop     dword ptr [rax+rax+00h]
0x18002cd70  test    eax, eax
0x18002cd72  jns     short loc_18002CD8D
0x18002cd74  mov     r8d, eax
0x18002cd77  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed for altering UPnP"...
0x18002cd7e  mov     ecx, 100000h
0x18002cd83  call    EventWriteError0
0x18002cd88  jmp     loc_18002D1DC
0x18002cd8d  xor     edx, edx; pUnkOuter
0x18002cd8f  lea     rax, [rsp+8E0h+var_878]
0x18002cd94  lea     r9, _GUID_b171c812_cc76_485a_94d8_b6b3a2794e99; riid
0x18002cd9b  mov     [rsp+8E0h+ppv], rax; ppv
0x18002cda0  lea     rcx, CLSID_UPnPNAT; rclsid
0x18002cda7  lea     r8d, [rdx+1]; dwClsContext
0x18002cdab  call    cs:__imp_CoCreateInstance
0x18002cdb2  nop     dword ptr [rax+rax+00h]
0x18002cdb7  test    eax, eax
0x18002cdb9  jns     short loc_18002CDD4
0x18002cdbb  mov     r8d, eax
0x18002cdbe  lea     rdx, aCocreateinstan_1; "CoCreateInstance failed for altering UP"...
0x18002cdc5  mov     ecx, 100000h
0x18002cdca  call    EventWriteError0
0x18002cdcf  jmp     loc_18002D1A4
0x18002cdd4  mov     rcx, [rsp+8E0h+var_878]
0x18002cdd9  lea     rdx, [rsp+8E0h+var_890]
0x18002cdde  mov     rax, [rcx]
0x18002cde1  mov     rax, [rax+38h]
0x18002cde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdea  mov     esi, 100000h
0x18002cdef  mov     r13d, 5DCh
0x18002cdf5  mov     rcx, [rsp+8E0h+var_890]
0x18002cdfa  test    eax, eax
0x18002cdfc  js      short loc_18002CE03
0x18002cdfe  test    rcx, rcx
0x18002ce01  jnz     short loc_18002CE65
0x18002ce03  test    edi, edi
0x18002ce05  jz      short loc_18002CE54
0x18002ce07  mov     r9, rcx
0x18002ce0a  mov     dword ptr [rsp+8E0h+ServiceBufferSize], edi
0x18002ce0e  cmp     edi, r13d
0x18002ce11  lea     rdx, aCouldnTGetStat; "Couldn't get static port mapping collec"...
0x18002ce18  mov     ebx, r13d
0x18002ce1b  mov     r8d, eax
0x18002ce1e  cmovb   ebx, edi
0x18002ce21  mov     ecx, esi
0x18002ce23  mov     dword ptr [rsp+8E0h+ppv], ebx
0x18002ce27  call    EventWrite0
0x18002ce2c  mov     ecx, ebx; dwMilliseconds
0x18002ce2e  call    cs:__imp_Sleep
0x18002ce35  nop     dword ptr [rax+rax+00h]
0x18002ce3a  mov     rcx, [rsp+8E0h+var_878]
0x18002ce3f  lea     rdx, [rsp+8E0h+var_890]
0x18002ce44  sub     edi, ebx
0x18002ce46  mov     rax, [rcx]
0x18002ce49  mov     rax, [rax+38h]
0x18002ce4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce52  jmp     short loc_18002CDF5
0x18002ce54  test    eax, eax
0x18002ce56  js      loc_18002D190
0x18002ce5c  test    rcx, rcx
0x18002ce5f  jz      loc_18002D190
0x18002ce65  mov     ebx, [rsp+8E0h+var_888]
0x18002ce69  mov     dword ptr [r14], 1
0x18002ce70  cmp     ebx, 2
0x18002ce73  jz      loc_18002D1A9
0x18002ce79  mov     rdi, [rsp+8E0h+pSockaddr]
0x18002ce7e  test    rdi, rdi
0x18002ce81  jz      loc_18002D1A9
0x18002ce87  test    r15, r15
0x18002ce8a  jz      loc_18002D1A9
0x18002ce90  test    r12, r12
0x18002ce93  jz      loc_18002D1A9
0x18002ce99  lea     rcx, aUdp; "UDP"
0x18002cea0  call    cs:__imp_SysAllocString
0x18002cea7  nop     dword ptr [rax+rax+00h]
0x18002ceac  mov     r13, rax
0x18002ceaf  test    rax, rax
0x18002ceb2  jnz     short loc_18002CEC7
0x18002ceb4  lea     rdx, aUdpstringFaile; "UdpString failed"
0x18002cebb  mov     ecx, esi
0x18002cebd  call    EventWriteError0
0x18002cec2  jmp     loc_18002D1A4
0x18002cec7  xor     r14d, r14d
0x18002ceca  test    ebx, ebx
0x18002cecc  jnz     loc_18002D0E7
0x18002ced2  lea     rcx, aTeredo; "Teredo"
0x18002ced9  mov     [rsp+8E0h+var_880], r14
0x18002cede  mov     [rsp+8E0h+bstrString], r14
0x18002cee3  mov     [rsp+8E0h+var_888], r14d
0x18002cee8  call    cs:__imp_SysAllocString
0x18002ceef  nop     dword ptr [rax+rax+00h]
0x18002cef4  mov     r12, rax
0x18002cef7  test    rax, rax
0x18002cefa  jnz     short loc_18002CF0F
0x18002cefc  lea     rdx, aTeredostringFa; "TeredoString failed"
0x18002cf03  mov     ecx, esi
0x18002cf05  call    EventWriteError0
0x18002cf0a  jmp     loc_18002D157
0x18002cf0f  mov     [rsp+8E0h+Flags], 2; Flags
0x18002cf17  lea     r8, [rbp+7E0h+pNodeBuffer]; pNodeBuffer
0x18002cf1b  mov     dword ptr [rsp+8E0h+ServiceBufferSize], r14d; ServiceBufferSize
0x18002cf20  mov     r9d, 401h; NodeBufferSize
0x18002cf26  mov     edx, 10h; SockaddrLength
0x18002cf2b  mov     [rsp+8E0h+ppv], r14; pServiceBuffer
0x18002cf30  mov     rcx, rdi; pSockaddr
0x18002cf33  call    cs:__imp_GetNameInfoW
0x18002cf3a  nop     dword ptr [rax+rax+00h]
0x18002cf3f  test    eax, eax
0x18002cf41  jz      short loc_18002CF5B
0x18002cf43  call    cs:__imp_WSAGetLastError
0x18002cf4a  nop     dword ptr [rax+rax+00h]
0x18002cf4f  lea     rdx, aGetnameinfowFa; "GetNameInfoW failed (err %i)!"
0x18002cf56  jmp     loc_18002D14D
0x18002cf5b  lea     rcx, [rbp+7E0h+pNodeBuffer]; psz
0x18002cf5f  call    cs:__imp_SysAllocString
0x18002cf66  nop     dword ptr [rax+rax+00h]
0x18002cf6b  mov     r14, rax
0x18002cf6e  test    rax, rax
0x18002cf71  jnz     short loc_18002CF7C
0x18002cf73  lea     rdx, aTeredointernal; "TeredoInternalIp failed"
0x18002cf7a  jmp     short loc_18002CF03
0x18002cf7c  lea     rcx, [rsp+8E0h+var_884]
0x18002cf81  call    TeredoGetPreviousNatUPnPExternalPort
0x18002cf86  test    eax, eax
0x18002cf88  js      short loc_18002CFE0
0x18002cf8a  mov     ebx, [rsp+8E0h+var_884]
0x18002cf8e  test    ebx, ebx
0x18002cf90  jz      short loc_18002CFE0
0x18002cf92  movzx   ecx, word ptr [rdi+2]; netshort
0x18002cf96  call    cs:__imp_ntohs
0x18002cf9d  nop     dword ptr [rax+rax+00h]
0x18002cfa2  movzx   eax, ax
0x18002cfa5  cmp     ebx, eax
0x18002cfa7  jz      short loc_18002CFE0
0x18002cfa9  mov     rcx, [rsp+8E0h+var_890]
0x18002cfae  mov     r8, r13
0x18002cfb1  mov     edx, ebx
0x18002cfb3  mov     rax, [rcx]
0x18002cfb6  mov     rax, [rax+50h]
0x18002cfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfbf  test    eax, eax
0x18002cfc1  js      short loc_18002CFCF
0x18002cfc3  xor     edx, edx
0x18002cfc5  lea     ecx, [rdx+1]
0x18002cfc8  call    TeredoSetPreviousNatUPnPExternalPort
0x18002cfcd  jmp     short loc_18002CFE0
0x18002cfcf  mov     r8d, eax
0x18002cfd2  lea     rdx, aUpnpNatExterna; "UPnP NAT external previous mapping coul"...
0x18002cfd9  mov     ecx, esi
0x18002cfdb  call    EventWriteError0
0x18002cfe0  mov     rax, [rsp+8E0h+var_890]
0x18002cfe5  mov     rcx, [rax]
0x18002cfe8  mov     rdi, [rcx+58h]
0x18002cfec  mov     rcx, [rsp+8E0h+pSockaddr]
0x18002cff1  movzx   ecx, word ptr [rcx+2]; netshort
0x18002cff5  call    cs:__imp_ntohs
0x18002cffc  nop     dword ptr [rax+rax+00h]
0x18002d001  movzx   ebx, ax
0x18002d004  mov     rax, [rsp+8E0h+pSockaddr]
0x18002d009  movzx   ecx, word ptr [rax+2]; netshort
0x18002d00d  call    cs:__imp_ntohs
0x18002d014  nop     dword ptr [rax+rax+00h]
0x18002d019  mov     rcx, [rsp+8E0h+var_890]
0x18002d01e  mov     r9d, ebx
0x18002d021  movzx   edx, ax
0x18002d024  mov     r8, r13
0x18002d027  lea     rax, [rsp+8E0h+var_880]
0x18002d02c  mov     [rsp+8E0h+var_8A8], rax
0x18002d031  mov     rax, rdi
0x18002d034  mov     qword ptr [rsp+8E0h+Flags], r12
0x18002d039  mov     word ptr [rsp+8E0h+ServiceBufferSize], 1
0x18002d040  mov     [rsp+8E0h+ppv], r14
0x18002d045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d04a  test    eax, eax
0x18002d04c  js      loc_18002D0DE
0x18002d052  mov     rcx, [rsp+8E0h+var_880]
0x18002d057  lea     rdx, [rsp+8E0h+bstrString]
0x18002d05c  mov     rax, [rcx]
0x18002d05f  mov     rax, [rax+38h]
0x18002d063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d068  mov     rcx, [rsp+8E0h+var_880]
0x18002d06d  lea     rdx, [rsp+8E0h+var_888]
0x18002d072  mov     rax, [rcx]
0x18002d075  mov     rax, [rax+40h]
0x18002d079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d07e  mov     edx, [rsp+8E0h+var_888]
0x18002d082  xor     ecx, ecx
0x18002d084  call    TeredoSetPreviousNatUPnPExternalPort
0x18002d089  mov     rcx, [rsp+8E0h+bstrString]; unsigned __int16 *
0x18002d08e  mov     word ptr [r15], 2
0x18002d094  call    ?inet_addrw@@YA?AUin_addr@@PEBG@Z; inet_addrw(ushort const *)
0x18002d099  movzx   ecx, word ptr [rsp+8E0h+var_888]; hostshort
0x18002d09e  mov     [r15+4], eax
0x18002d0a2  call    cs:__imp_htons
0x18002d0a9  nop     dword ptr [rax+rax+00h]
0x18002d0ae  mov     rcx, [rsp+8E0h+bstrString]; bstrString
0x18002d0b3  mov     [r15+2], ax
0x18002d0b8  mov     rax, [rbp+7E0h+var_860]
0x18002d0bc  mov     byte ptr [rax], 1
0x18002d0bf  call    cs:__imp_SysFreeString
0x18002d0c6  nop     dword ptr [rax+rax+00h]
0x18002d0cb  mov     rcx, [rsp+8E0h+var_880]
0x18002d0d0  mov     rax, [rcx]
0x18002d0d3  mov     rax, [rax+10h]
0x18002d0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0dc  jmp     short loc_18002D157
0x18002d0de  lea     rdx, aUpnpMappingFai; "UPnP mapping failed to be added: error "...
0x18002d0e5  jmp     short loc_18002D14D
0x18002d0e7  xor     r12d, r12d
0x18002d0ea  lea     edi, [r12+1]
0x18002d0ef  cmp     ebx, edi
0x18002d0f1  jnz     short loc_18002D157
0x18002d0f3  mov     rax, [rsp+8E0h+var_890]
0x18002d0f8  mov     rcx, [rax]
0x18002d0fb  mov     rbx, [rcx+50h]
0x18002d0ff  movzx   ecx, word ptr [r15+2]; netshort
0x18002d104  call    cs:__imp_ntohs
0x18002d10b  nop     dword ptr [rax+rax+00h]
0x18002d110  mov     rcx, [rsp+8E0h+var_890]
0x18002d115  mov     r8, r13
0x18002d118  movzx   edx, ax
0x18002d11b  mov     rax, rbx
0x18002d11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d123  test    eax, eax
0x18002d125  js      short loc_18002D146
0x18002d127  xor     edx, edx
0x18002d129  mov     ecx, edi
0x18002d12b  call    TeredoSetPreviousNatUPnPExternalPort
0x18002d130  xor     eax, eax
0x18002d132  mov     qword ptr [r15], 2
0x18002d139  mov     [r15+8], rax
0x18002d13d  mov     rax, [rbp+7E0h+var_860]
0x18002d141  mov     [rax], r12b
0x18002d144  jmp     short loc_18002D157
0x18002d146  lea     rdx, aUpnpMappingCou; "UPnP mapping could not be deleted: erro"...
0x18002d14d  mov     r8d, eax
0x18002d150  mov     ecx, esi
0x18002d152  call    EventWriteError0
0x18002d157  mov     rcx, r13; bstrString
0x18002d15a  call    cs:__imp_SysFreeString
0x18002d161  nop     dword ptr [rax+rax+00h]
0x18002d166  test    r12, r12
0x18002d169  jz      short loc_18002D17A
0x18002d16b  mov     rcx, r12; bstrString
0x18002d16e  call    cs:__imp_SysFreeString
0x18002d175  nop     dword ptr [rax+rax+00h]
0x18002d17a  test    r14, r14
0x18002d17d  jz      short loc_18002D1A4
0x18002d17f  mov     rcx, r14; bstrString
0x18002d182  call    cs:__imp_SysFreeString
0x18002d189  nop     dword ptr [rax+rax+00h]
0x18002d18e  jmp     short loc_18002D1A4
0x18002d190  mov     r9, rcx
0x18002d193  lea     rdx, aGetStaticportm; "get_StaticPortMappingCollection for UPn"...
0x18002d19a  mov     ecx, esi
0x18002d19c  mov     r8d, eax
0x18002d19f  call    EventWriteError0
0x18002d1a4  mov     rcx, [rsp+8E0h+var_890]
0x18002d1a9  test    rcx, rcx
0x18002d1ac  jz      short loc_18002D1BA
0x18002d1ae  mov     rax, [rcx]
0x18002d1b1  mov     rax, [rax+10h]
0x18002d1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1ba  mov     rcx, [rsp+8E0h+var_878]
0x18002d1bf  test    rcx, rcx
0x18002d1c2  jz      short loc_18002D1D0
0x18002d1c4  mov     rax, [rcx]
0x18002d1c7  mov     rax, [rax+10h]
0x18002d1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1d0  call    cs:__imp_CoUninitialize
0x18002d1d7  nop     dword ptr [rax+rax+00h]
0x18002d1dc  mov     rcx, [rbp+7E0h+var_40]
0x18002d1e3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
