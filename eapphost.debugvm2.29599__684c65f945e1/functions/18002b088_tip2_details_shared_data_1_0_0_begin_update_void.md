# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18002b088`
- end: `0x18002b155`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b43c`

## callees

- `0x180002a90`
- `0x18002b088`
- `0x18002b548`
- `0x18002e4a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b0a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b0a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b14b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b14b`

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
0x18002b088  push    rbx
0x18002b08a  sub     rsp, 60h
0x18002b08e  mov     rax, cs:__security_cookie
0x18002b095  xor     rax, rsp
0x18002b098  mov     [rsp+68h+var_18], rax
0x18002b09d  mov     rbx, rcx
0x18002b0a0  add     rcx, 0C0h; lpCriticalSection
0x18002b0a7  call    cs:__imp_EnterCriticalSection
0x18002b0ad  inc     dword ptr [rbx+0E8h]
0x18002b0b3  test    dword ptr [rbx+40h], 100h
0x18002b0ba  jnz     short loc_18002B10C
0x18002b0bc  mov     rcx, [rbx+0F0h]
0x18002b0c3  test    rcx, rcx
0x18002b0c6  jz      loc_18002B151
0x18002b0cc  cmp     dword ptr [rbx+0E8h], 1
0x18002b0d3  jnz     short loc_18002B151
0x18002b0d5  mov     r8d, [rbx+0B8h]
0x18002b0dc  lea     r9, [rsp+68h+var_48]
0x18002b0e1  xorps   xmm0, xmm0
0x18002b0e4  mov     edx, 1
0x18002b0e9  movups  [rsp+68h+var_48], xmm0
0x18002b0ee  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18002b0f3  movups  [rsp+68h+var_28], xmm0
0x18002b0f8  call    TestQueryData
0x18002b0fd  mov     rcx, [rsp+68h+pv+8]; pv
0x18002b102  test    eax, eax
0x18002b104  jnz     short loc_18002B121
0x18002b106  call    cs:__imp_CoTaskMemFree
0x18002b10c  xor     al, al
0x18002b10e  mov     rcx, [rsp+68h+var_18]
0x18002b113  xor     rcx, rsp; StackCookie
0x18002b116  call    __security_check_cookie
0x18002b11b  add     rsp, 60h
0x18002b11f  pop     rbx
0x18002b120  retn
0x18002b121  mov     eax, dword ptr [rsp+68h+pv+4]
0x18002b125  or      [rbx+40h], eax
0x18002b128  test    rcx, rcx
0x18002b12b  jz      short loc_18002B141
0x18002b12d  lea     rdx, [rsp+68h+var_48]
0x18002b132  mov     rcx, rbx
0x18002b135  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002b13a  mov     rcx, [rsp+68h+pv+8]
0x18002b13f  jmp     short loc_18002B14B
0x18002b141  mov     edx, dword ptr [rsp+68h+pv]
0x18002b145  mov     [rbx+0B8h], edx
0x18002b14b  call    cs:__imp_CoTaskMemFree
0x18002b151  mov     al, 1
0x18002b153  jmp     short loc_18002B10E
```
