# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x140011384`
- end: `0x140011468`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000dda8`
- `0x14000dde4`

## callees

- `0x1400081f0`
- `0x140011384`
- `0x14001191c`
- `0x140061c90`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400113a3`
- `KERNEL32!EnterCriticalSection` at `0x1400113a3`
- `ole32!CoTaskMemFree` at `0x14001140c`
- `ole32!CoTaskMemFree` at `0x140011458`
- `ole32!CoTaskMemFree` at `0x14001140c`
- `ole32!CoTaskMemFree` at `0x140011458`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::begin_update(__int64 a1)
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
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
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
0x140011384  push    rbx
0x140011386  sub     rsp, 60h
0x14001138a  mov     rax, cs:__security_cookie
0x140011391  xor     rax, rsp
0x140011394  mov     [rsp+68h+var_18], rax
0x140011399  mov     rbx, rcx
0x14001139c  add     rcx, 0C0h; lpCriticalSection
0x1400113a3  call    cs:__imp_EnterCriticalSection
0x1400113aa  nop     dword ptr [rax+rax+00h]
0x1400113af  inc     dword ptr [rbx+0E8h]
0x1400113b5  test    dword ptr [rbx+40h], 100h
0x1400113bc  jnz     short loc_140011418
0x1400113be  mov     rcx, [rbx+0F0h]
0x1400113c5  test    rcx, rcx
0x1400113c8  jz      loc_140011464
0x1400113ce  cmp     dword ptr [rbx+0E8h], 1
0x1400113d5  jnz     loc_140011464
0x1400113db  mov     r8d, [rbx+0B8h]
0x1400113e2  lea     r9, [rsp+68h+var_48]
0x1400113e7  xorps   xmm0, xmm0
0x1400113ea  mov     edx, 1
0x1400113ef  movups  [rsp+68h+var_48], xmm0
0x1400113f4  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1400113f9  movups  [rsp+68h+var_28], xmm0
0x1400113fe  call    TestQueryData
0x140011403  mov     rcx, [rsp+68h+pv+8]; pv
0x140011408  test    eax, eax
0x14001140a  jnz     short loc_14001142E
0x14001140c  call    cs:__imp_CoTaskMemFree
0x140011413  nop     dword ptr [rax+rax+00h]
0x140011418  xor     al, al
0x14001141a  mov     rcx, [rsp+68h+var_18]
0x14001141f  xor     rcx, rsp; StackCookie
0x140011422  call    __security_check_cookie
0x140011427  add     rsp, 60h
0x14001142b  pop     rbx
0x14001142c  retn
0x14001142e  mov     eax, dword ptr [rsp+68h+pv+4]
0x140011432  or      [rbx+40h], eax
0x140011435  test    rcx, rcx
0x140011438  jz      short loc_14001144E
0x14001143a  lea     rdx, [rsp+68h+var_48]
0x14001143f  mov     rcx, rbx
0x140011442  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x140011447  mov     rcx, [rsp+68h+pv+8]
0x14001144c  jmp     short loc_140011458
0x14001144e  mov     edx, dword ptr [rsp+68h+pv]
0x140011452  mov     [rbx+0B8h], edx
0x140011458  call    cs:__imp_CoTaskMemFree
0x14001145f  nop     dword ptr [rax+rax+00h]
0x140011464  mov     al, 1
0x140011466  jmp     short loc_14001141A
```
