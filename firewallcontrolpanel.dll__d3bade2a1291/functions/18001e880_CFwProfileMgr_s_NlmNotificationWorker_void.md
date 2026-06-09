# CFwProfileMgr::s_NlmNotificationWorker(void *)

- ea: `0x18001e880`
- end: `0x18001e945`
- name: `?s_NlmNotificationWorker@CFwProfileMgr@@CAKPEAX@Z`
- size: `197`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000994c`
- `0x18001dc58`
- `0x18001de38`
- `0x18001df38`
- `0x18001e880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e8f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e8fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e8fc`

## pseudocode

```c
__int64 __fastcall CFwProfileMgr::s_NlmNotificationWorker(char *Parameter)
{
  unsigned int v1; // esi
  CFwProfileMgr *v2; // rdi
  int v4; // eax

  v1 = 0;
  v2 = *(CFwProfileMgr **)Parameter;
  switch ( *((_DWORD *)Parameter + 2) )
  {
    case 1:
      v4 = CFwProfileMgr::OnNetworkDeletedWorker(*(CFwProfileMgr **)Parameter, (const struct _GUID *)(Parameter + 12));
      break;
    case 2:
    case 3:
      v4 = CFwProfileMgr::OnNetworkConnectedWorker(*(CFwProfileMgr **)Parameter, (const struct _GUID *)(Parameter + 12));
      break;
    case 4:
      v4 = CFwProfileMgr::OnNetworkPropertyChangeWorker(
             *(_QWORD *)Parameter,
             Parameter + 12,
             *((unsigned int *)Parameter + 7));
      break;
    default:
      goto LABEL_9;
  }
  v1 = v4;
LABEL_9:
  _InterlockedDecrement((volatile signed __int32 *)v2 + 54);
  if ( !*((_DWORD *)v2 + 54) )
    SetEvent(*((HANDLE *)v2 + 26));
  CoTaskMemFree(Parameter);
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, v1);
  return 0;
}

```

## disassembly

```asm
0x18001e880  mov     [rsp+arg_0], rbx
0x18001e885  mov     [rsp+arg_8], rsi
0x18001e88a  push    rdi
0x18001e88b  sub     rsp, 20h
0x18001e88f  mov     edx, [rcx+8]
0x18001e892  xor     esi, esi
0x18001e894  mov     rdi, [rcx]
0x18001e897  mov     rbx, rcx
0x18001e89a  sub     edx, 1
0x18001e89d  jz      short loc_18001E8CE
0x18001e89f  sub     edx, 1
0x18001e8a2  jz      short loc_18001E8C0
0x18001e8a4  sub     edx, 1
0x18001e8a7  jz      short loc_18001E8C0
0x18001e8a9  cmp     edx, 1
0x18001e8ac  jnz     short loc_18001E8DC
0x18001e8ae  mov     r8d, [rcx+1Ch]
0x18001e8b2  lea     rdx, [rcx+0Ch]
0x18001e8b6  mov     rcx, rdi
0x18001e8b9  call    ?OnNetworkPropertyChangeWorker@CFwProfileMgr@@AEAAJPEBU_GUID@@W4tagNP_NETWORK_PROPERTY_CHANGE@@@Z; CFwProfileMgr::OnNetworkPropertyChangeWorker(_GUID const *,tagNP_NETWORK_PROPERTY_CHANGE)
0x18001e8be  jmp     short loc_18001E8DA
0x18001e8c0  lea     rdx, [rcx+0Ch]; struct _GUID *
0x18001e8c4  mov     rcx, rdi; this
0x18001e8c7  call    ?OnNetworkConnectedWorker@CFwProfileMgr@@AEAAJPEBU_GUID@@@Z; CFwProfileMgr::OnNetworkConnectedWorker(_GUID const *)
0x18001e8cc  jmp     short loc_18001E8DA
0x18001e8ce  lea     rdx, [rcx+0Ch]; struct _GUID *
0x18001e8d2  mov     rcx, rdi; this
0x18001e8d5  call    ?OnNetworkDeletedWorker@CFwProfileMgr@@AEAAJPEBU_GUID@@@Z; CFwProfileMgr::OnNetworkDeletedWorker(_GUID const *)
0x18001e8da  mov     esi, eax
0x18001e8dc  lock dec dword ptr [rdi+0D8h]
0x18001e8e3  cmp     dword ptr [rdi+0D8h], 0
0x18001e8ea  jnz     short loc_18001E8F9
0x18001e8ec  mov     rcx, [rdi+0D0h]; hEvent
0x18001e8f3  call    cs:__imp_SetEvent
0x18001e8f9  mov     rcx, rbx; pv
0x18001e8fc  call    cs:__imp_CoTaskMemFree
0x18001e902  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e909  lea     rax, WPP_GLOBAL_Control
0x18001e910  cmp     rcx, rax
0x18001e913  jz      short loc_18001E933
0x18001e915  test    byte ptr [rcx+1Ch], 8
0x18001e919  jz      short loc_18001E933
0x18001e91b  mov     rcx, [rcx+10h]
0x18001e91f  lea     r8, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids
0x18001e926  mov     edx, 49h ; 'I'
0x18001e92b  mov     r9d, esi
0x18001e92e  call    WPP_SF_d
0x18001e933  mov     rbx, [rsp+28h+arg_0]
0x18001e938  xor     eax, eax
0x18001e93a  mov     rsi, [rsp+28h+arg_8]
0x18001e93f  add     rsp, 20h
0x18001e943  pop     rdi
0x18001e944  retn
```
