# tip2::details::merged_data<_tip_OmaDmCertHealth,_tip_OmaDmCertHealth>::Release(void)

- ea: `0x140023bac`
- end: `0x140023c1f`
- name: `?Release@?$merged_data@U_tip_OmaDmCertHealth@@U1@@details@tip2@@AEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001fc10`
- `0x140020870`
- `0x1400223f0`
- `0x140039cfc`
- `0x14003a0e4`
- `0x14003b9f0`

## callees

- `0x14001f978`
- `0x140023bac`
- `0x14002409c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140023c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140023c00`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_OmaDmCertHealth,_tip_OmaDmCertHealth>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // esi

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<_tip_OmaDmCertHealth,_tip_OmaDmCertHealth>::`vftable';
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
0x140023bac  mov     [rsp+arg_0], rbx
0x140023bb1  mov     [rsp+arg_8], rsi
0x140023bb6  push    rdi
0x140023bb7  sub     rsp, 20h
0x140023bbb  mov     rdi, rcx
0x140023bbe  or      esi, 0FFFFFFFFh
0x140023bc1  lock xadd [rcx+120h], esi
0x140023bc9  sub     esi, 1
0x140023bcc  jnz     short loc_140023C0C
0x140023bce  lea     rax, ??_7?$merged_data@U_tip_OmaDmCertHealth@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_OmaDmCertHealth,_tip_OmaDmCertHealth>::`vftable'
0x140023bd5  mov     [rcx], rax
0x140023bd8  cmp     qword ptr [rcx+0F8h], 0
0x140023be0  jz      short loc_140023BF4
0x140023be2  test    byte ptr [rcx+1Ch], 1
0x140023be6  jnz     short loc_140023BF4
0x140023be8  lea     edx, [rsi+4]
0x140023beb  add     rcx, 8
0x140023bef  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x140023bf4  lea     rcx, [rdi+8]
0x140023bf8  call    ??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)
0x140023bfd  mov     rcx, rdi; pv
0x140023c00  call    cs:__imp_CoTaskMemFree
0x140023c07  nop     dword ptr [rax+rax+00h]
0x140023c0c  mov     rbx, [rsp+28h+arg_0]
0x140023c11  mov     eax, esi
0x140023c13  mov     rsi, [rsp+28h+arg_8]
0x140023c18  add     rsp, 20h
0x140023c1c  pop     rdi
0x140023c1d  retn
```
