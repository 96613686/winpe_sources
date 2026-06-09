# TeredoAlterPortMapping(_UPNP_ACTION,ulong,sockaddr_in const *,sockaddr_in *,uchar *,int *)

- ea: `0x18002ccdc`
- end: `0x18002d1f7`
- name: `?TeredoAlterPortMapping@@YAXW4_UPNP_ACTION@@KPEBUsockaddr_in@@PEAU2@PEAEPEAH@Z`
- size: `1307`
- prototype: `void __high(enum _UPNP_ACTION, unsigned int, const struct sockaddr_in *, struct sockaddr_in *, unsigned __int8 *, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002cb88`
- `0x180042388`
- `0x1800764f4`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x180029f8c`
- `0x18002b550`
- `0x18002ccdc`
- `0x180042430`
- `0x18004b630`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ce1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ce1e`
- `WS2_32!GetNameInfoW` at `0x18002cf23`
- `WS2_32!GetNameInfoW` at `0x18002cf23`
- `WS2_32!__imp_htons` at `0x18002d092`
- `WS2_32!__imp_htons` at `0x18002d092`
- `WS2_32!__imp_ntohs` at `0x18002cf86`
- `WS2_32!__imp_ntohs` at `0x18002cfe5`
- `WS2_32!__imp_ntohs` at `0x18002cffd`
- `WS2_32!__imp_ntohs` at `0x18002d0f4`
- `WS2_32!__imp_ntohs` at `0x18002cf86`
- `WS2_32!__imp_ntohs` at `0x18002cfe5`
- `WS2_32!__imp_ntohs` at `0x18002cffd`
- `WS2_32!__imp_ntohs` at `0x18002d0f4`
- `WS2_32!__imp_WSAGetLastError` at `0x18002cf33`
- `WS2_32!__imp_WSAGetLastError` at `0x18002cf33`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d1c0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d1c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cd9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cd9b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002cd54`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002cd54`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ce90`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ced8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf4f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ce90`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ced8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0af`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d14a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d15e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d172`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0af`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d14a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d15e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d172`

## string_xrefs

- `0x18002cdae`: `CoCreateInstance failed for altering UPnP mapping (hr 0x%08x)!`
- `0x18002cfc2`: `UPnP NAT external previous mapping could not be deleted: error (%d)`
- `0x18002d136`: `UPnP mapping could not be deleted: error (%d)`

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
0x18002ccdc  mov     [rsp-8+arg_0], rbx
0x18002cce1  push    rbp
0x18002cce2  push    rsi
0x18002cce3  push    rdi
0x18002cce4  push    r12
0x18002cce6  push    r13
0x18002cce8  push    r14
0x18002ccea  push    r15
0x18002ccec  lea     rbp, [rsp-7B0h]
0x18002ccf4  sub     rsp, 8B0h
0x18002ccfb  mov     rax, cs:__security_cookie
0x18002cd02  xor     rax, rsp
0x18002cd05  mov     [rbp+7E0h+var_40], rax
0x18002cd0c  mov     r14, [rbp+7E0h+arg_28]
0x18002cd13  mov     edi, edx
0x18002cd15  mov     r12, [rbp+7E0h+arg_20]
0x18002cd1c  mov     edx, 4; dwCoInit
0x18002cd21  mov     [rsp+8E0h+var_888], ecx
0x18002cd25  mov     r15, r9
0x18002cd28  xor     ecx, ecx; pvReserved
0x18002cd2a  mov     [rsp+8E0h+pSockaddr], r8
0x18002cd2f  mov     dword ptr [r14], 0
0x18002cd36  mov     [rbp+7E0h+var_860], r12
0x18002cd3a  mov     [rsp+8E0h+var_878], 0
0x18002cd43  mov     [rsp+8E0h+var_890], 0
0x18002cd4c  mov     [rsp+8E0h+var_884], 0
0x18002cd54  call    cs:__imp_CoInitializeEx
0x18002cd5b  nop     dword ptr [rax+rax+00h]
0x18002cd60  test    eax, eax
0x18002cd62  jns     short loc_18002CD7D
0x18002cd64  mov     r8d, eax
0x18002cd67  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed for altering UPnP"...
0x18002cd6e  mov     ecx, 100000h
0x18002cd73  call    EventWriteError0
0x18002cd78  jmp     loc_18002D1CC
0x18002cd7d  xor     edx, edx; pUnkOuter
0x18002cd7f  lea     rax, [rsp+8E0h+var_878]
0x18002cd84  lea     r9, _GUID_b171c812_cc76_485a_94d8_b6b3a2794e99; riid
0x18002cd8b  mov     [rsp+8E0h+ppv], rax; ppv
0x18002cd90  lea     rcx, CLSID_UPnPNAT; rclsid
0x18002cd97  lea     r8d, [rdx+1]; dwClsContext
0x18002cd9b  call    cs:__imp_CoCreateInstance
0x18002cda2  nop     dword ptr [rax+rax+00h]
0x18002cda7  test    eax, eax
0x18002cda9  jns     short loc_18002CDC4
0x18002cdab  mov     r8d, eax
0x18002cdae  lea     rdx, aCocreateinstan_1; "CoCreateInstance failed for altering UP"...
0x18002cdb5  mov     ecx, 100000h
0x18002cdba  call    EventWriteError0
0x18002cdbf  jmp     loc_18002D194
0x18002cdc4  mov     rcx, [rsp+8E0h+var_878]
0x18002cdc9  lea     rdx, [rsp+8E0h+var_890]
0x18002cdce  mov     rax, [rcx]
0x18002cdd1  mov     rax, [rax+38h]
0x18002cdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdda  mov     esi, 100000h
0x18002cddf  mov     r13d, 5DCh
0x18002cde5  mov     rcx, [rsp+8E0h+var_890]
0x18002cdea  test    eax, eax
0x18002cdec  js      short loc_18002CDF3
0x18002cdee  test    rcx, rcx
0x18002cdf1  jnz     short loc_18002CE55
0x18002cdf3  test    edi, edi
0x18002cdf5  jz      short loc_18002CE44
0x18002cdf7  mov     r9, rcx
0x18002cdfa  mov     dword ptr [rsp+8E0h+ServiceBufferSize], edi
0x18002cdfe  cmp     edi, r13d
0x18002ce01  lea     rdx, aCouldnTGetStat; "Couldn't get static port mapping collec"...
0x18002ce08  mov     ebx, r13d
0x18002ce0b  mov     r8d, eax
0x18002ce0e  cmovb   ebx, edi
0x18002ce11  mov     ecx, esi
0x18002ce13  mov     dword ptr [rsp+8E0h+ppv], ebx
0x18002ce17  call    EventWrite0
0x18002ce1c  mov     ecx, ebx; dwMilliseconds
0x18002ce1e  call    cs:__imp_Sleep
0x18002ce25  nop     dword ptr [rax+rax+00h]
0x18002ce2a  mov     rcx, [rsp+8E0h+var_878]
0x18002ce2f  lea     rdx, [rsp+8E0h+var_890]
0x18002ce34  sub     edi, ebx
0x18002ce36  mov     rax, [rcx]
0x18002ce39  mov     rax, [rax+38h]
0x18002ce3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce42  jmp     short loc_18002CDE5
0x18002ce44  test    eax, eax
0x18002ce46  js      loc_18002D180
0x18002ce4c  test    rcx, rcx
0x18002ce4f  jz      loc_18002D180
0x18002ce55  mov     ebx, [rsp+8E0h+var_888]
0x18002ce59  mov     dword ptr [r14], 1
0x18002ce60  cmp     ebx, 2
0x18002ce63  jz      loc_18002D199
0x18002ce69  mov     rdi, [rsp+8E0h+pSockaddr]
0x18002ce6e  test    rdi, rdi
0x18002ce71  jz      loc_18002D199
0x18002ce77  test    r15, r15
0x18002ce7a  jz      loc_18002D199
0x18002ce80  test    r12, r12
0x18002ce83  jz      loc_18002D199
0x18002ce89  lea     rcx, aUdp; "UDP"
0x18002ce90  call    cs:__imp_SysAllocString
0x18002ce97  nop     dword ptr [rax+rax+00h]
0x18002ce9c  mov     r13, rax
0x18002ce9f  test    rax, rax
0x18002cea2  jnz     short loc_18002CEB7
0x18002cea4  lea     rdx, aUdpstringFaile; "UdpString failed"
0x18002ceab  mov     ecx, esi
0x18002cead  call    EventWriteError0
0x18002ceb2  jmp     loc_18002D194
0x18002ceb7  xor     r14d, r14d
0x18002ceba  test    ebx, ebx
0x18002cebc  jnz     loc_18002D0D7
0x18002cec2  lea     rcx, aTeredo; "Teredo"
0x18002cec9  mov     [rsp+8E0h+var_880], r14
0x18002cece  mov     [rsp+8E0h+bstrString], r14
0x18002ced3  mov     [rsp+8E0h+var_888], r14d
0x18002ced8  call    cs:__imp_SysAllocString
0x18002cedf  nop     dword ptr [rax+rax+00h]
0x18002cee4  mov     r12, rax
0x18002cee7  test    rax, rax
0x18002ceea  jnz     short loc_18002CEFF
0x18002ceec  lea     rdx, aTeredostringFa; "TeredoString failed"
0x18002cef3  mov     ecx, esi
0x18002cef5  call    EventWriteError0
0x18002cefa  jmp     loc_18002D147
0x18002ceff  mov     [rsp+8E0h+Flags], 2; Flags
0x18002cf07  lea     r8, [rbp+7E0h+pNodeBuffer]; pNodeBuffer
0x18002cf0b  mov     dword ptr [rsp+8E0h+ServiceBufferSize], r14d; ServiceBufferSize
0x18002cf10  mov     r9d, 401h; NodeBufferSize
0x18002cf16  mov     edx, 10h; SockaddrLength
0x18002cf1b  mov     [rsp+8E0h+ppv], r14; pServiceBuffer
0x18002cf20  mov     rcx, rdi; pSockaddr
0x18002cf23  call    cs:__imp_GetNameInfoW
0x18002cf2a  nop     dword ptr [rax+rax+00h]
0x18002cf2f  test    eax, eax
0x18002cf31  jz      short loc_18002CF4B
0x18002cf33  call    cs:__imp_WSAGetLastError
0x18002cf3a  nop     dword ptr [rax+rax+00h]
0x18002cf3f  lea     rdx, aGetnameinfowFa; "GetNameInfoW failed (err %i)!"
0x18002cf46  jmp     loc_18002D13D
0x18002cf4b  lea     rcx, [rbp+7E0h+pNodeBuffer]; psz
0x18002cf4f  call    cs:__imp_SysAllocString
0x18002cf56  nop     dword ptr [rax+rax+00h]
0x18002cf5b  mov     r14, rax
0x18002cf5e  test    rax, rax
0x18002cf61  jnz     short loc_18002CF6C
0x18002cf63  lea     rdx, aTeredointernal; "TeredoInternalIp failed"
0x18002cf6a  jmp     short loc_18002CEF3
0x18002cf6c  lea     rcx, [rsp+8E0h+var_884]
0x18002cf71  call    TeredoGetPreviousNatUPnPExternalPort
0x18002cf76  test    eax, eax
0x18002cf78  js      short loc_18002CFD0
0x18002cf7a  mov     ebx, [rsp+8E0h+var_884]
0x18002cf7e  test    ebx, ebx
0x18002cf80  jz      short loc_18002CFD0
0x18002cf82  movzx   ecx, word ptr [rdi+2]; netshort
0x18002cf86  call    cs:__imp_ntohs
0x18002cf8d  nop     dword ptr [rax+rax+00h]
0x18002cf92  movzx   eax, ax
0x18002cf95  cmp     ebx, eax
0x18002cf97  jz      short loc_18002CFD0
0x18002cf99  mov     rcx, [rsp+8E0h+var_890]
0x18002cf9e  mov     r8, r13
0x18002cfa1  mov     edx, ebx
0x18002cfa3  mov     rax, [rcx]
0x18002cfa6  mov     rax, [rax+50h]
0x18002cfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfaf  test    eax, eax
0x18002cfb1  js      short loc_18002CFBF
0x18002cfb3  xor     edx, edx
0x18002cfb5  lea     ecx, [rdx+1]
0x18002cfb8  call    TeredoSetPreviousNatUPnPExternalPort
0x18002cfbd  jmp     short loc_18002CFD0
0x18002cfbf  mov     r8d, eax
0x18002cfc2  lea     rdx, aUpnpNatExterna; "UPnP NAT external previous mapping coul"...
0x18002cfc9  mov     ecx, esi
0x18002cfcb  call    EventWriteError0
0x18002cfd0  mov     rax, [rsp+8E0h+var_890]
0x18002cfd5  mov     rcx, [rax]
0x18002cfd8  mov     rdi, [rcx+58h]
0x18002cfdc  mov     rcx, [rsp+8E0h+pSockaddr]
0x18002cfe1  movzx   ecx, word ptr [rcx+2]; netshort
0x18002cfe5  call    cs:__imp_ntohs
0x18002cfec  nop     dword ptr [rax+rax+00h]
0x18002cff1  movzx   ebx, ax
0x18002cff4  mov     rax, [rsp+8E0h+pSockaddr]
0x18002cff9  movzx   ecx, word ptr [rax+2]; netshort
0x18002cffd  call    cs:__imp_ntohs
0x18002d004  nop     dword ptr [rax+rax+00h]
0x18002d009  mov     rcx, [rsp+8E0h+var_890]
0x18002d00e  mov     r9d, ebx
0x18002d011  movzx   edx, ax
0x18002d014  mov     r8, r13
0x18002d017  lea     rax, [rsp+8E0h+var_880]
0x18002d01c  mov     [rsp+8E0h+var_8A8], rax
0x18002d021  mov     rax, rdi
0x18002d024  mov     qword ptr [rsp+8E0h+Flags], r12
0x18002d029  mov     word ptr [rsp+8E0h+ServiceBufferSize], 1
0x18002d030  mov     [rsp+8E0h+ppv], r14
0x18002d035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d03a  test    eax, eax
0x18002d03c  js      loc_18002D0CE
0x18002d042  mov     rcx, [rsp+8E0h+var_880]
0x18002d047  lea     rdx, [rsp+8E0h+bstrString]
0x18002d04c  mov     rax, [rcx]
0x18002d04f  mov     rax, [rax+38h]
0x18002d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d058  mov     rcx, [rsp+8E0h+var_880]
0x18002d05d  lea     rdx, [rsp+8E0h+var_888]
0x18002d062  mov     rax, [rcx]
0x18002d065  mov     rax, [rax+40h]
0x18002d069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d06e  mov     edx, [rsp+8E0h+var_888]
0x18002d072  xor     ecx, ecx
0x18002d074  call    TeredoSetPreviousNatUPnPExternalPort
0x18002d079  mov     rcx, [rsp+8E0h+bstrString]; unsigned __int16 *
0x18002d07e  mov     word ptr [r15], 2
0x18002d084  call    ?inet_addrw@@YA?AUin_addr@@PEBG@Z; inet_addrw(ushort const *)
0x18002d089  movzx   ecx, word ptr [rsp+8E0h+var_888]; hostshort
0x18002d08e  mov     [r15+4], eax
0x18002d092  call    cs:__imp_htons
0x18002d099  nop     dword ptr [rax+rax+00h]
0x18002d09e  mov     rcx, [rsp+8E0h+bstrString]; bstrString
0x18002d0a3  mov     [r15+2], ax
0x18002d0a8  mov     rax, [rbp+7E0h+var_860]
0x18002d0ac  mov     byte ptr [rax], 1
0x18002d0af  call    cs:__imp_SysFreeString
0x18002d0b6  nop     dword ptr [rax+rax+00h]
0x18002d0bb  mov     rcx, [rsp+8E0h+var_880]
0x18002d0c0  mov     rax, [rcx]
0x18002d0c3  mov     rax, [rax+10h]
0x18002d0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0cc  jmp     short loc_18002D147
0x18002d0ce  lea     rdx, aUpnpMappingFai; "UPnP mapping failed to be added: error "...
0x18002d0d5  jmp     short loc_18002D13D
0x18002d0d7  xor     r12d, r12d
0x18002d0da  lea     edi, [r12+1]
0x18002d0df  cmp     ebx, edi
0x18002d0e1  jnz     short loc_18002D147
0x18002d0e3  mov     rax, [rsp+8E0h+var_890]
0x18002d0e8  mov     rcx, [rax]
0x18002d0eb  mov     rbx, [rcx+50h]
0x18002d0ef  movzx   ecx, word ptr [r15+2]; netshort
0x18002d0f4  call    cs:__imp_ntohs
0x18002d0fb  nop     dword ptr [rax+rax+00h]
0x18002d100  mov     rcx, [rsp+8E0h+var_890]
0x18002d105  mov     r8, r13
0x18002d108  movzx   edx, ax
0x18002d10b  mov     rax, rbx
0x18002d10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d113  test    eax, eax
0x18002d115  js      short loc_18002D136
0x18002d117  xor     edx, edx
0x18002d119  mov     ecx, edi
0x18002d11b  call    TeredoSetPreviousNatUPnPExternalPort
0x18002d120  xor     eax, eax
0x18002d122  mov     qword ptr [r15], 2
0x18002d129  mov     [r15+8], rax
0x18002d12d  mov     rax, [rbp+7E0h+var_860]
0x18002d131  mov     [rax], r12b
0x18002d134  jmp     short loc_18002D147
0x18002d136  lea     rdx, aUpnpMappingCou; "UPnP mapping could not be deleted: erro"...
0x18002d13d  mov     r8d, eax
0x18002d140  mov     ecx, esi
0x18002d142  call    EventWriteError0
0x18002d147  mov     rcx, r13; bstrString
0x18002d14a  call    cs:__imp_SysFreeString
0x18002d151  nop     dword ptr [rax+rax+00h]
0x18002d156  test    r12, r12
0x18002d159  jz      short loc_18002D16A
0x18002d15b  mov     rcx, r12; bstrString
0x18002d15e  call    cs:__imp_SysFreeString
0x18002d165  nop     dword ptr [rax+rax+00h]
0x18002d16a  test    r14, r14
0x18002d16d  jz      short loc_18002D194
0x18002d16f  mov     rcx, r14; bstrString
0x18002d172  call    cs:__imp_SysFreeString
0x18002d179  nop     dword ptr [rax+rax+00h]
0x18002d17e  jmp     short loc_18002D194
0x18002d180  mov     r9, rcx
0x18002d183  lea     rdx, aGetStaticportm; "get_StaticPortMappingCollection for UPn"...
0x18002d18a  mov     ecx, esi
0x18002d18c  mov     r8d, eax
0x18002d18f  call    EventWriteError0
0x18002d194  mov     rcx, [rsp+8E0h+var_890]
0x18002d199  test    rcx, rcx
0x18002d19c  jz      short loc_18002D1AA
0x18002d19e  mov     rax, [rcx]
0x18002d1a1  mov     rax, [rax+10h]
0x18002d1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1aa  mov     rcx, [rsp+8E0h+var_878]
0x18002d1af  test    rcx, rcx
0x18002d1b2  jz      short loc_18002D1C0
0x18002d1b4  mov     rax, [rcx]
0x18002d1b7  mov     rax, [rax+10h]
0x18002d1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1c0  call    cs:__imp_CoUninitialize
0x18002d1c7  nop     dword ptr [rax+rax+00h]
0x18002d1cc  mov     rcx, [rbp+7E0h+var_40]
0x18002d1d3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
