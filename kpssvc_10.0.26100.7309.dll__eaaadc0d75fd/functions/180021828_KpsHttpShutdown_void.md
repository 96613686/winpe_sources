# KpsHttpShutdown(void)

- ea: `0x180021828`
- end: `0x180021b07`
- name: `?KpsHttpShutdown@@YAXXZ`
- size: `735`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019ad0`
- `0x18002ccd0`

## callees

- `0x18001ada8`
- `0x18001ae0c`
- `0x180021828`
- `0x180026d54`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800218a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800219a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800218a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800219a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a40`
- `WS2_32!__imp_closesocket` at `0x180021938`
- `WS2_32!__imp_closesocket` at `0x180021938`
- `WS2_32!__imp_WSACleanup` at `0x180021a1a`
- `WS2_32!__imp_WSACleanup` at `0x180021a1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800219ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800219ea`
- `ntdll!RtlLeaveCriticalSection` at `0x180021953`
- `ntdll!RtlLeaveCriticalSection` at `0x180021953`
- `ntdll!RtlEnterCriticalSection` at `0x1800218e2`
- `ntdll!RtlEnterCriticalSection` at `0x1800218e2`
- `ntdll!RtlDeleteCriticalSection` at `0x180021a2d`
- `ntdll!RtlDeleteCriticalSection` at `0x180021a2d`
- `HTTPAPI!HttpCloseUrlGroup` at `0x1800218b5`
- `HTTPAPI!HttpCloseUrlGroup` at `0x1800218b5`
- `HTTPAPI!HttpCloseServerSession` at `0x1800219fd`
- `HTTPAPI!HttpCloseServerSession` at `0x1800219fd`
- `HTTPAPI!HttpTerminate` at `0x180021a0e`
- `HTTPAPI!HttpTerminate` at `0x180021a0e`
- `HTTPAPI!HttpCloseRequestQueue` at `0x1800218c8`
- `HTTPAPI!HttpCloseRequestQueue` at `0x1800218c8`

## pseudocode

```c
void __fastcall KpsHttpShutdown(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // esi
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx
  char v6; // di
  __int64 v7; // rax
  SOCKET v8; // rcx
  __int64 v9; // r8
  signed __int64 v10; // rax
  signed __int64 v11; // rax
  _BYTE v12[16]; // [rsp+30h] [rbp-38h] BYREF

  v3 = 10;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( KpsGlobalHttpState )
  {
    WaitForSingleObject(h, 0x3E8u);
    HttpCloseUrlGroup(UrlGroupId);
    HttpCloseRequestQueue(RequestQueueHandle);
    do
    {
      RtlEnterCriticalSection(&stru_18003AC20);
      v5 = (_QWORD *)qword_18003AC48;
      if ( (__int64 *)qword_18003AC48 == &qword_18003AC48 )
      {
        v6 = 1;
      }
      else
      {
        v6 = 0;
        if ( *(__int64 **)(qword_18003AC48 + 8) != &qword_18003AC48
          || (v7 = *(_QWORD *)qword_18003AC48, *(_QWORD *)(*(_QWORD *)qword_18003AC48 + 8LL) != qword_18003AC48) )
        {
          __fastfail(3u);
        }
        qword_18003AC48 = *(_QWORD *)qword_18003AC48;
        *(_QWORD *)(v7 + 8) = &qword_18003AC48;
        *v5 = 0;
        v5[1] = 0;
        v8 = v5[22];
        if ( v8 != -1 )
        {
          closesocket(v8);
          v5[22] = -1;
        }
      }
      RtlLeaveCriticalSection(&stru_18003AC20);
    }
    while ( !v6 );
    while ( 1 )
    {
      v10 = _InterlockedCompareExchange64(&qword_18003AC58, 0, 0);
      if ( !v10 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v9, v10);
      WaitForSingleObject(h, 0x3E8u);
      if ( !--v3 )
      {
        v11 = _InterlockedCompareExchange64(&qword_18003AC58, 0, 0);
        if ( v11
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)(v3 + 36), v9, v11);
        }
        break;
      }
    }
    CloseThreadpoolIo(pio);
    HttpCloseServerSession(ServerSessionId);
    HttpTerminate(3u, 0);
    WSACleanup();
    RtlDeleteCriticalSection(&stru_18003AC20);
    CloseHandle(h);
    memset_0(&KpsGlobalHttpState, 0, 0x70u);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(v4, HttpShutdown, a3, 1, v12);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    {
      WPP_SF_(v4[2], 37, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
      WPP_SF_(v4[2], 38, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
  }
}

```

## disassembly

```asm
0x180021828  mov     [rsp+arg_0], rbx
0x18002182d  mov     [rsp+arg_8], rbp
0x180021832  mov     [rsp+arg_10], rsi
0x180021837  push    rdi
0x180021838  push    r12
0x18002183a  push    r14
0x18002183c  sub     rsp, 50h
0x180021840  mov     rax, cs:__security_cookie
0x180021847  xor     rax, rsp
0x18002184a  mov     [rsp+68h+var_28], rax
0x18002184f  mov     esi, 0Ah
0x180021854  mov     rcx, cs:WPP_GLOBAL_Control
0x18002185b  lea     r14, WPP_GLOBAL_Control
0x180021862  cmp     rcx, r14
0x180021865  jz      short loc_180021887
0x180021867  test    byte ptr [rcx+1Ch], 20h
0x18002186b  jz      short loc_180021887
0x18002186d  mov     rcx, [rcx+10h]
0x180021871  lea     edx, [rsi+18h]
0x180021874  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002187b  call    WPP_SF_
0x180021880  mov     rcx, cs:WPP_GLOBAL_Control
0x180021887  xor     ebp, ebp
0x180021889  cmp     cs:?KpsGlobalHttpState@@3U_KPS_GLOBAL_HTTP_STATE@@A, bpl; _KPS_GLOBAL_HTTP_STATE KpsGlobalHttpState
0x180021890  jz      loc_180021A65
0x180021896  mov     rcx, cs:h; hHandle
0x18002189d  mov     edx, 3E8h; dwMilliseconds
0x1800218a2  call    cs:__imp_WaitForSingleObject
0x1800218a9  nop     dword ptr [rax+rax+00h]
0x1800218ae  mov     rcx, cs:UrlGroupId; UrlGroupId
0x1800218b5  call    cs:__imp_HttpCloseUrlGroup
0x1800218bc  nop     dword ptr [rax+rax+00h]
0x1800218c1  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x1800218c8  call    cs:__imp_HttpCloseRequestQueue
0x1800218cf  nop     dword ptr [rax+rax+00h]
0x1800218d4  lea     r12, qword_18003AC48
0x1800218db  lea     rcx, stru_18003AC20; CriticalSection
0x1800218e2  call    cs:__imp_RtlEnterCriticalSection
0x1800218e9  nop     dword ptr [rax+rax+00h]
0x1800218ee  mov     rbx, cs:qword_18003AC48
0x1800218f5  cmp     rbx, r12
0x1800218f8  jnz     short loc_1800218FF
0x1800218fa  mov     dil, 1
0x1800218fd  jmp     short loc_18002194C
0x1800218ff  mov     dil, bpl
0x180021902  cmp     [rbx+8], r12
0x180021906  jnz     loc_180021B00
0x18002190c  mov     rax, [rbx]
0x18002190f  cmp     [rax+8], rbx
0x180021913  jnz     loc_180021B00
0x180021919  mov     cs:qword_18003AC48, rax
0x180021920  mov     [rax+8], r12
0x180021924  mov     [rbx], rbp
0x180021927  mov     [rbx+8], rbp
0x18002192b  mov     rcx, [rbx+0B0h]; s
0x180021932  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021936  jz      short loc_18002194C
0x180021938  call    cs:__imp_closesocket
0x18002193f  nop     dword ptr [rax+rax+00h]
0x180021944  or      qword ptr [rbx+0B0h], 0FFFFFFFFFFFFFFFFh
0x18002194c  lea     rcx, stru_18003AC20; CriticalSection
0x180021953  call    cs:__imp_RtlLeaveCriticalSection
0x18002195a  nop     dword ptr [rax+rax+00h]
0x18002195f  test    dil, dil
0x180021962  jz      loc_1800218DB
0x180021968  xor     eax, eax
0x18002196a  lock cmpxchg cs:qword_18003AC58, rbp
0x180021973  jz      short loc_1800219E3
0x180021975  mov     rcx, cs:WPP_GLOBAL_Control
0x18002197c  cmp     rcx, r14
0x18002197f  jz      short loc_180021998
0x180021981  test    byte ptr [rcx+1Ch], 4
0x180021985  jz      short loc_180021998
0x180021987  mov     rcx, [rcx+10h]
0x18002198b  mov     edx, 23h ; '#'
0x180021990  mov     r9, rax
0x180021993  call    WPP_SF_i
0x180021998  mov     rcx, cs:h; hHandle
0x18002199f  mov     edx, 3E8h; dwMilliseconds
0x1800219a4  call    cs:__imp_WaitForSingleObject
0x1800219ab  nop     dword ptr [rax+rax+00h]
0x1800219b0  add     esi, 0FFFFFFFFh
0x1800219b3  jnz     short loc_180021968
0x1800219b5  xor     eax, eax
0x1800219b7  lock cmpxchg cs:qword_18003AC58, rbp
0x1800219c0  jz      short loc_1800219E3
0x1800219c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219c9  cmp     rcx, r14
0x1800219cc  jz      short loc_1800219E3
0x1800219ce  test    byte ptr [rcx+1Ch], 1
0x1800219d2  jz      short loc_1800219E3
0x1800219d4  mov     rcx, [rcx+10h]
0x1800219d8  lea     edx, [rsi+24h]
0x1800219db  mov     r9, rax
0x1800219de  call    WPP_SF_i
0x1800219e3  mov     rcx, cs:pio; pio
0x1800219ea  call    cs:__imp_CloseThreadpoolIo
0x1800219f1  nop     dword ptr [rax+rax+00h]
0x1800219f6  mov     rcx, cs:ServerSessionId; ServerSessionId
0x1800219fd  call    cs:__imp_HttpCloseServerSession
0x180021a04  nop     dword ptr [rax+rax+00h]
0x180021a09  xor     edx, edx; pReserved
0x180021a0b  lea     ecx, [rdx+3]; Flags
0x180021a0e  call    cs:__imp_HttpTerminate
0x180021a15  nop     dword ptr [rax+rax+00h]
0x180021a1a  call    cs:__imp_WSACleanup
0x180021a21  nop     dword ptr [rax+rax+00h]
0x180021a26  lea     rcx, stru_18003AC20; CriticalSection
0x180021a2d  call    cs:__imp_RtlDeleteCriticalSection
0x180021a34  nop     dword ptr [rax+rax+00h]
0x180021a39  mov     rcx, cs:h; hObject
0x180021a40  call    cs:__imp_CloseHandle
0x180021a47  nop     dword ptr [rax+rax+00h]
0x180021a4c  xor     edx, edx; Val
0x180021a4e  lea     rcx, ?KpsGlobalHttpState@@3U_KPS_GLOBAL_HTTP_STATE@@A; void *
0x180021a55  lea     r8d, [rdx+70h]; Size
0x180021a59  call    memset_0
0x180021a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a65  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 8
0x180021a6c  jz      short loc_180021A91
0x180021a6e  lea     rax, [rsp+68h+var_38]
0x180021a73  mov     r9d, 1
0x180021a79  lea     rdx, HttpShutdown
0x180021a80  mov     [rsp+68h+var_48], rax
0x180021a85  call    McGenEventWrite_EventWriteTransfer
0x180021a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a91  cmp     rcx, r14
0x180021a94  jz      short loc_180021AD8
0x180021a96  test    byte ptr [rcx+1Ch], 10h
0x180021a9a  jz      short loc_180021AB8
0x180021a9c  mov     rcx, [rcx+10h]
0x180021aa0  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180021aa7  mov     edx, 25h ; '%'
0x180021aac  call    WPP_SF_
0x180021ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ab8  cmp     rcx, r14
0x180021abb  jz      short loc_180021AD8
0x180021abd  test    byte ptr [rcx+1Ch], 20h
0x180021ac1  jz      short loc_180021AD8
0x180021ac3  mov     rcx, [rcx+10h]
0x180021ac7  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180021ace  mov     edx, 26h ; '&'
0x180021ad3  call    WPP_SF_
0x180021ad8  mov     rcx, [rsp+68h+var_28]
0x180021add  xor     rcx, rsp; StackCookie
0x180021ae0  call    __security_check_cookie
0x180021ae5  lea     r11, [rsp+68h+var_18]
0x180021aea  mov     rbx, [r11+20h]
0x180021aee  mov     rbp, [r11+28h]
0x180021af2  mov     rsi, [r11+30h]
0x180021af6  mov     rsp, r11
0x180021af9  pop     r14
0x180021afb  pop     r12
0x180021afd  pop     rdi
0x180021afe  retn
0x180021b00  mov     ecx, 3
0x180021b05  int     29h; Win8: RtlFailFast(ecx)
```
