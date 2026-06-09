# PublicNetworkListManager::InitializeIpHlpEventMgr(int *)

- ea: `0x18002716c`
- end: `0x180027291`
- name: `?InitializeIpHlpEventMgr@PublicNetworkListManager@@AEAAJPEAH@Z`
- size: `293`
- prototype: `__int64 __fastcall(PVOID pv, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180027bd0`

## callees

- `0x180006770`
- `0x180006810`
- `0x18002716c`
- `0x18002ae7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027255`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800271bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800271bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027245`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027245`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800271df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800271df`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::InitializeIpHlpEventMgr(char *pv, int *a2)
{
  unsigned int v4; // ebx
  PTP_WAIT *v5; // rsi
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  *a2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 664));
  v5 = (PTP_WAIT *)(pv + 704);
  if ( !*((_QWORD *)pv + 88) )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       (PTP_WAIT_CALLBACK)PublicNetworkListManager::ClientIpHlpEventMgrCallback,
                       pv,
                       0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      pv + 704,
      ThreadpoolWait);
    if ( *v5 )
      goto LABEL_12;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v4);
    if ( (v4 & 0x80000000) == 0 )
    {
LABEL_12:
      SetThreadpoolWait(*v5, *((HANDLE *)pv + 96), 0);
      *a2 = 1;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 664));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x18002716c  push    rbx
0x18002716e  push    rbp
0x18002716f  push    rsi
0x180027170  push    rdi
0x180027171  push    r12
0x180027173  push    r14
0x180027175  sub     rsp, 28h
0x180027179  mov     r14, rdx
0x18002717c  mov     rdi, rcx
0x18002717f  xor     ebx, ebx
0x180027181  mov     rcx, cs:WPP_GLOBAL_Control
0x180027188  lea     r12, WPP_GLOBAL_Control
0x18002718f  cmp     rcx, r12
0x180027192  jz      short loc_1800271AF
0x180027194  test    byte ptr [rcx+1Ch], 8
0x180027198  jz      short loc_1800271AF
0x18002719a  mov     rcx, [rcx+10h]
0x18002719e  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800271a5  mov     edx, 0D1h
0x1800271aa  call    WPP_SF_
0x1800271af  lea     rbp, [rdi+298h]
0x1800271b6  mov     [r14], ebx
0x1800271b9  mov     rcx, rbp; lpCriticalSection
0x1800271bc  call    cs:__imp_EnterCriticalSection
0x1800271c2  lea     rsi, [rdi+2C0h]
0x1800271c9  cmp     [rsi], rbx
0x1800271cc  jnz     loc_180027252
0x1800271d2  xor     r8d, r8d; pcbe
0x1800271d5  lea     rcx, ?ClientIpHlpEventMgrCallback@PublicNetworkListManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800271dc  mov     rdx, rdi; pv
0x1800271df  call    cs:__imp_CreateThreadpoolWait
0x1800271e5  mov     rdx, rax
0x1800271e8  mov     rcx, rsi
0x1800271eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800271f0  cmp     [rsi], rbx
0x1800271f3  jnz     short loc_180027238
0x1800271f5  call    cs:__imp_GetLastError
0x1800271fb  mov     ebx, eax
0x1800271fd  test    eax, eax
0x1800271ff  jle     short loc_18002720A
0x180027201  movzx   ebx, ax
0x180027204  or      ebx, 80070000h
0x18002720a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027211  cmp     rcx, r12
0x180027214  jz      short loc_180027234
0x180027216  test    byte ptr [rcx+1Ch], 1
0x18002721a  jz      short loc_180027234
0x18002721c  mov     rcx, [rcx+10h]
0x180027220  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180027227  mov     edx, 0D2h
0x18002722c  mov     r9d, ebx
0x18002722f  call    WPP_SF_d
0x180027234  test    ebx, ebx
0x180027236  js      short loc_180027252
0x180027238  mov     rdx, [rdi+300h]; h
0x18002723f  xor     r8d, r8d; pftTimeout
0x180027242  mov     rcx, [rsi]; pwa
0x180027245  call    cs:__imp_SetThreadpoolWait
0x18002724b  mov     dword ptr [r14], 1
0x180027252  mov     rcx, rbp; lpCriticalSection
0x180027255  call    cs:__imp_LeaveCriticalSection
0x18002725b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027262  cmp     rcx, r12
0x180027265  jz      short loc_180027282
0x180027267  test    byte ptr [rcx+1Ch], 8
0x18002726b  jz      short loc_180027282
0x18002726d  mov     rcx, [rcx+10h]
0x180027271  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180027278  mov     edx, 0D3h
0x18002727d  call    WPP_SF_
0x180027282  mov     eax, ebx
0x180027284  add     rsp, 28h
0x180027288  pop     r14
0x18002728a  pop     r12
0x18002728c  pop     rdi
0x18002728d  pop     rsi
0x18002728e  pop     rbp
0x18002728f  pop     rbx
0x180027290  retn
```
