# tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(void)

- ea: `0x18003894c`
- end: `0x1800389bf`
- name: `?Release@?$merged_data@U_tip_EnrollmentAttestationTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800312e0`
- `0x180031328`
- `0x180031524`
- `0x180034b80`

## callees

- `0x180031274`
- `0x18003894c`
- `0x180039428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389a0`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // esi

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::`vftable';
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
0x18003894c  mov     [rsp+arg_0], rbx
0x180038951  mov     [rsp+arg_8], rsi
0x180038956  push    rdi
0x180038957  sub     rsp, 20h
0x18003895b  mov     rdi, rcx
0x18003895e  or      esi, 0FFFFFFFFh
0x180038961  lock xadd [rcx+118h], esi
0x180038969  sub     esi, 1
0x18003896c  jnz     short loc_1800389AC
0x18003896e  lea     rax, ??_7?$merged_data@U_tip_EnrollmentAttestationTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::`vftable'
0x180038975  mov     [rcx], rax
0x180038978  cmp     qword ptr [rcx+0F8h], 0
0x180038980  jz      short loc_180038994
0x180038982  test    byte ptr [rcx+1Ch], 1
0x180038986  jnz     short loc_180038994
0x180038988  lea     edx, [rsi+4]
0x18003898b  add     rcx, 8
0x18003898f  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180038994  lea     rcx, [rdi+8]
0x180038998  call    ??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)
0x18003899d  mov     rcx, rdi; pv
0x1800389a0  call    cs:__imp_CoTaskMemFree
0x1800389a7  nop     dword ptr [rax+rax+00h]
0x1800389ac  mov     rbx, [rsp+28h+arg_0]
0x1800389b1  mov     eax, esi
0x1800389b3  mov     rsi, [rsp+28h+arg_8]
0x1800389b8  add     rsp, 20h
0x1800389bc  pop     rdi
0x1800389bd  retn
```
