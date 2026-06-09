# KpsGPShutdown(void)

- ea: `0x18001a868`
- end: `0x18001a94f`
- name: `?KpsGPShutdown@@YAXXZ`
- size: `231`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ccd0`
- `0x18002cf60`

## callees

- `0x180019a20`
- `0x18001a868`
- `0x18001ae0c`
- `0x18003100e`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a8db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a8db`
- `ntdll!RtlDeregisterWaitEx` at `0x18001a8c8`
- `ntdll!RtlDeregisterWaitEx` at `0x18001a8c8`
- `ntdll!RtlDeleteCriticalSection` at `0x18001a901`
- `ntdll!RtlDeleteCriticalSection` at `0x18001a901`

## pseudocode

```c
void KpsGPShutdown(void)
{
  _QWORD *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( KpsGp )
  {
    KpsFreeUrlPrefixList((struct _KPS_URL_PREFIX_LIST *)&xmmword_18003A998);
    if ( phNewWaitObject )
      RtlDeregisterWaitEx(phNewWaitObject, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    CloseHandle(hObject);
    RegCloseKey(hKey);
    RtlDeleteCriticalSection(&stru_18003A958);
    memset_0(&KpsGp, 0, 0x80u);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 63, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
}

```

## disassembly

```asm
0x18001a868  push    rbx
0x18001a86a  sub     rsp, 20h
0x18001a86e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a875  lea     rbx, WPP_GLOBAL_Control
0x18001a87c  cmp     rcx, rbx
0x18001a87f  jz      short loc_18001A8A3
0x18001a881  test    byte ptr [rcx+1Ch], 20h
0x18001a885  jz      short loc_18001A8A3
0x18001a887  mov     rcx, [rcx+10h]
0x18001a88b  lea     r8, WPP_55dedb296c8337923463e18711d485b4_Traceguids
0x18001a892  mov     edx, 3Eh ; '>'
0x18001a897  call    WPP_SF_
0x18001a89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8a3  cmp     cs:?KpsGp@@3U_KPS_GP@@A, 0; _KPS_GP KpsGp
0x18001a8aa  jz      short loc_18001A928
0x18001a8ac  lea     rcx, xmmword_18003A998; struct _KPS_URL_PREFIX_LIST *
0x18001a8b3  call    ?KpsFreeUrlPrefixList@@YAXPEAU_KPS_URL_PREFIX_LIST@@@Z; KpsFreeUrlPrefixList(_KPS_URL_PREFIX_LIST *)
0x18001a8b8  mov     rcx, cs:phNewWaitObject; hWaitHandle
0x18001a8bf  test    rcx, rcx
0x18001a8c2  jz      short loc_18001A8D4
0x18001a8c4  or      rdx, 0FFFFFFFFFFFFFFFFh; hCompletionEvent
0x18001a8c8  call    cs:__imp_RtlDeregisterWaitEx
0x18001a8cf  nop     dword ptr [rax+rax+00h]
0x18001a8d4  mov     rcx, cs:hObject; hObject
0x18001a8db  call    cs:__imp_CloseHandle
0x18001a8e2  nop     dword ptr [rax+rax+00h]
0x18001a8e7  mov     rcx, cs:hKey; hKey
0x18001a8ee  call    cs:__imp_RegCloseKey
0x18001a8f5  nop     dword ptr [rax+rax+00h]
0x18001a8fa  lea     rcx, stru_18003A958; CriticalSection
0x18001a901  call    cs:__imp_RtlDeleteCriticalSection
0x18001a908  nop     dword ptr [rax+rax+00h]
0x18001a90d  xor     edx, edx; Val
0x18001a90f  lea     rcx, ?KpsGp@@3U_KPS_GP@@A; void *
0x18001a916  mov     r8d, 80h; Size
0x18001a91c  call    memset_0
0x18001a921  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a928  cmp     rcx, rbx
0x18001a92b  jz      short loc_18001A948
0x18001a92d  test    byte ptr [rcx+1Ch], 20h
0x18001a931  jz      short loc_18001A948
0x18001a933  mov     rcx, [rcx+10h]
0x18001a937  lea     r8, WPP_55dedb296c8337923463e18711d485b4_Traceguids
0x18001a93e  mov     edx, 3Fh ; '?'
0x18001a943  call    WPP_SF_
0x18001a948  add     rsp, 20h
0x18001a94c  pop     rbx
0x18001a94d  retn
```
