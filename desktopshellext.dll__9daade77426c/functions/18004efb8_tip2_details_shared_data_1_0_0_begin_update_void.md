# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18004efb8`
- end: `0x18004f085`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a888`

## callees

- `0x1800278ac`
- `0x18002a3d0`
- `0x180033c80`
- `0x18004efb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004efd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004efd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f036`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f07b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f036`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f07b`

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
0x18004efb8  push    rbx
0x18004efba  sub     rsp, 60h
0x18004efbe  mov     rax, cs:__security_cookie
0x18004efc5  xor     rax, rsp
0x18004efc8  mov     [rsp+68h+var_18], rax
0x18004efcd  mov     rbx, rcx
0x18004efd0  add     rcx, 0C0h; lpCriticalSection
0x18004efd7  call    cs:__imp_EnterCriticalSection
0x18004efdd  inc     dword ptr [rbx+0E8h]
0x18004efe3  test    dword ptr [rbx+40h], 100h
0x18004efea  jnz     short loc_18004F03C
0x18004efec  mov     rcx, [rbx+0F0h]
0x18004eff3  test    rcx, rcx
0x18004eff6  jz      loc_18004F081
0x18004effc  cmp     dword ptr [rbx+0E8h], 1
0x18004f003  jnz     short loc_18004F081
0x18004f005  mov     r8d, [rbx+0B8h]
0x18004f00c  lea     r9, [rsp+68h+var_48]
0x18004f011  xorps   xmm0, xmm0
0x18004f014  mov     edx, 1
0x18004f019  movups  [rsp+68h+var_48], xmm0
0x18004f01e  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18004f023  movups  [rsp+68h+var_28], xmm0
0x18004f028  call    TestQueryData
0x18004f02d  mov     rcx, [rsp+68h+pv+8]; pv
0x18004f032  test    eax, eax
0x18004f034  jnz     short loc_18004F051
0x18004f036  call    cs:__imp_CoTaskMemFree
0x18004f03c  xor     al, al
0x18004f03e  mov     rcx, [rsp+68h+var_18]
0x18004f043  xor     rcx, rsp; StackCookie
0x18004f046  call    __security_check_cookie
0x18004f04b  add     rsp, 60h
0x18004f04f  pop     rbx
0x18004f050  retn
0x18004f051  mov     eax, dword ptr [rsp+68h+pv+4]
0x18004f055  or      [rbx+40h], eax
0x18004f058  test    rcx, rcx
0x18004f05b  jz      short loc_18004F071
0x18004f05d  lea     rdx, [rsp+68h+var_48]
0x18004f062  mov     rcx, rbx
0x18004f065  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004f06a  mov     rcx, [rsp+68h+pv+8]
0x18004f06f  jmp     short loc_18004F07B
0x18004f071  mov     edx, dword ptr [rsp+68h+pv]
0x18004f075  mov     [rbx+0B8h], edx
0x18004f07b  call    cs:__imp_CoTaskMemFree
0x18004f081  mov     al, 1
0x18004f083  jmp     short loc_18004F03E
```
