# tip2::details::shared_data<1,0,1>::begin_update(void)

- ea: `0x18003ce40`
- end: `0x18003cf0d`
- name: `?begin_update@?$shared_data@$00$0A@$00@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180026ae4`

## callees

- `0x18002771c`
- `0x18002a3d0`
- `0x180033c80`
- `0x18003ce40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ce5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ce5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cf03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cf03`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,1>::begin_update(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  void *v5; // rcx
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v9; // [rsp+40h] [rbp-28h]

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
    return 0;
  v2 = *(_QWORD *)(a1 + 240);
  if ( v2 && *(_DWORD *)(a1 + 232) == 1 )
  {
    v3 = *(unsigned int *)(a1 + 184);
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v4 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v2, 1, v3, &v7);
    v5 = pv[1];
    if ( !v4 )
    {
      CoTaskMemFree(pv[1]);
      return 0;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v5 )
    {
      tip2::details::shared_data<1,0,1>::deserialize_data(a1, &v7);
      v5 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x18003ce40  push    rbx
0x18003ce42  sub     rsp, 60h
0x18003ce46  mov     rax, cs:__security_cookie
0x18003ce4d  xor     rax, rsp
0x18003ce50  mov     [rsp+68h+var_18], rax
0x18003ce55  mov     rbx, rcx
0x18003ce58  add     rcx, 0C0h; lpCriticalSection
0x18003ce5f  call    cs:__imp_EnterCriticalSection
0x18003ce65  inc     dword ptr [rbx+0E8h]
0x18003ce6b  test    dword ptr [rbx+40h], 100h
0x18003ce72  jnz     short loc_18003CEC4
0x18003ce74  mov     rcx, [rbx+0F0h]
0x18003ce7b  test    rcx, rcx
0x18003ce7e  jz      loc_18003CF09
0x18003ce84  cmp     dword ptr [rbx+0E8h], 1
0x18003ce8b  jnz     short loc_18003CF09
0x18003ce8d  mov     r8d, [rbx+0B8h]
0x18003ce94  lea     r9, [rsp+68h+var_48]
0x18003ce99  xorps   xmm0, xmm0
0x18003ce9c  mov     edx, 1
0x18003cea1  movups  [rsp+68h+var_48], xmm0
0x18003cea6  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18003ceab  movups  [rsp+68h+var_28], xmm0
0x18003ceb0  call    TestQueryData
0x18003ceb5  mov     rcx, [rsp+68h+pv+8]; pv
0x18003ceba  test    eax, eax
0x18003cebc  jnz     short loc_18003CED9
0x18003cebe  call    cs:__imp_CoTaskMemFree
0x18003cec4  xor     al, al
0x18003cec6  mov     rcx, [rsp+68h+var_18]
0x18003cecb  xor     rcx, rsp; StackCookie
0x18003cece  call    __security_check_cookie
0x18003ced3  add     rsp, 60h
0x18003ced7  pop     rbx
0x18003ced8  retn
0x18003ced9  mov     eax, dword ptr [rsp+68h+pv+4]
0x18003cedd  or      [rbx+40h], eax
0x18003cee0  test    rcx, rcx
0x18003cee3  jz      short loc_18003CEF9
0x18003cee5  lea     rdx, [rsp+68h+var_48]
0x18003ceea  mov     rcx, rbx
0x18003ceed  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003cef2  mov     rcx, [rsp+68h+pv+8]
0x18003cef7  jmp     short loc_18003CF03
0x18003cef9  mov     edx, dword ptr [rsp+68h+pv]
0x18003cefd  mov     [rbx+0B8h], edx
0x18003cf03  call    cs:__imp_CoTaskMemFree
0x18003cf09  mov     al, 1
0x18003cf0b  jmp     short loc_18003CEC6
```
