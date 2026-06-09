# tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)

- ea: `0x180010ba8`
- end: `0x180010c1b`
- name: `?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006a0c`
- `0x180007cd0`
- `0x180015cd0`
- `0x180023850`

## callees

- `0x180007c64`
- `0x180010ba8`
- `0x180016740`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180010bfc`
- `ole32!CoTaskMemFree` at `0x180010bfc`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 68);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable';
    if ( *((_QWORD *)pv + 31) && (pv[7] & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(pv + 2), 4);
    tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>((__int64)(pv + 2));
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180010ba8  mov     [rsp+arg_0], rbx
0x180010bad  mov     [rsp+arg_8], rsi
0x180010bb2  push    rdi
0x180010bb3  sub     rsp, 20h
0x180010bb7  mov     rdi, rcx
0x180010bba  or      ebx, 0FFFFFFFFh
0x180010bbd  lock xadd [rcx+110h], ebx
0x180010bc5  sub     ebx, 1
0x180010bc8  jnz     short loc_180010C08
0x180010bca  lea     rax, ??_7?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable'
0x180010bd1  mov     [rcx], rax
0x180010bd4  cmp     qword ptr [rcx+0F8h], 0
0x180010bdc  jz      short loc_180010BF0
0x180010bde  test    byte ptr [rcx+1Ch], 1
0x180010be2  jnz     short loc_180010BF0
0x180010be4  lea     edx, [rbx+4]
0x180010be7  add     rcx, 8
0x180010beb  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180010bf0  lea     rcx, [rdi+8]
0x180010bf4  call    ??1?$shared_data@$0A@$0A@$00@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(void)
0x180010bf9  mov     rcx, rdi; pv
0x180010bfc  call    cs:__imp_CoTaskMemFree
0x180010c03  nop     dword ptr [rax+rax+00h]
0x180010c08  mov     rsi, [rsp+28h+arg_8]
0x180010c0d  mov     eax, ebx
0x180010c0f  mov     rbx, [rsp+28h+arg_0]
0x180010c14  add     rsp, 20h
0x180010c18  pop     rdi
0x180010c19  retn
```
