# tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>::Release(void)

- ea: `0x140048ad0`
- end: `0x140048b43`
- name: `?Release@?$merged_data@U_tip_OmadmClientAadTokenRetryUserLogonTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140046f98`
- `0x140046fe0`
- `0x140047060`
- `0x140048db0`

## callees

- `0x14001f978`
- `0x14002409c`
- `0x140048ad0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048b24`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // esi

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>::`vftable';
    if ( *((_QWORD *)pv + 31) && (pv[7] & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(pv + 2), 4u);
    tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>((__int64)(pv + 2));
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140048ad0  mov     [rsp+arg_0], rbx
0x140048ad5  mov     [rsp+arg_8], rsi
0x140048ada  push    rdi
0x140048adb  sub     rsp, 20h
0x140048adf  mov     rdi, rcx
0x140048ae2  or      esi, 0FFFFFFFFh
0x140048ae5  lock xadd [rcx+120h], esi
0x140048aed  sub     esi, 1
0x140048af0  jnz     short loc_140048B30
0x140048af2  lea     rax, ??_7?$merged_data@U_tip_OmadmClientAadTokenRetryUserLogonTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>::`vftable'
0x140048af9  mov     [rcx], rax
0x140048afc  cmp     qword ptr [rcx+0F8h], 0
0x140048b04  jz      short loc_140048B18
0x140048b06  test    byte ptr [rcx+1Ch], 1
0x140048b0a  jnz     short loc_140048B18
0x140048b0c  lea     edx, [rsi+4]
0x140048b0f  add     rcx, 8
0x140048b13  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x140048b18  lea     rcx, [rdi+8]
0x140048b1c  call    ??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)
0x140048b21  mov     rcx, rdi; pv
0x140048b24  call    cs:__imp_CoTaskMemFree
0x140048b2b  nop     dword ptr [rax+rax+00h]
0x140048b30  mov     rbx, [rsp+28h+arg_0]
0x140048b35  mov     eax, esi
0x140048b37  mov     rsi, [rsp+28h+arg_8]
0x140048b3c  add     rsp, 20h
0x140048b40  pop     rdi
0x140048b41  retn
```
