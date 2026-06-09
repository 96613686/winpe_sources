# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18002bfb4`
- end: `0x18002c098`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c3b4`

## callees

- `0x180002af0`
- `0x18002bfb4`
- `0x18002c4bc`
- `0x18002f550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bfd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bfd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c03c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c03c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c088`

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
0x18002bfb4  push    rbx
0x18002bfb6  sub     rsp, 60h
0x18002bfba  mov     rax, cs:__security_cookie
0x18002bfc1  xor     rax, rsp
0x18002bfc4  mov     [rsp+68h+var_18], rax
0x18002bfc9  mov     rbx, rcx
0x18002bfcc  add     rcx, 0C0h; lpCriticalSection
0x18002bfd3  call    cs:__imp_EnterCriticalSection
0x18002bfda  nop     dword ptr [rax+rax+00h]
0x18002bfdf  inc     dword ptr [rbx+0E8h]
0x18002bfe5  test    dword ptr [rbx+40h], 100h
0x18002bfec  jnz     short loc_18002C048
0x18002bfee  mov     rcx, [rbx+0F0h]
0x18002bff5  test    rcx, rcx
0x18002bff8  jz      loc_18002C094
0x18002bffe  cmp     dword ptr [rbx+0E8h], 1
0x18002c005  jnz     loc_18002C094
0x18002c00b  mov     r8d, [rbx+0B8h]
0x18002c012  lea     r9, [rsp+68h+var_48]
0x18002c017  xorps   xmm0, xmm0
0x18002c01a  mov     edx, 1
0x18002c01f  movups  [rsp+68h+var_48], xmm0
0x18002c024  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18002c029  movups  [rsp+68h+var_28], xmm0
0x18002c02e  call    TestQueryData
0x18002c033  mov     rcx, [rsp+68h+pv+8]; pv
0x18002c038  test    eax, eax
0x18002c03a  jnz     short loc_18002C05E
0x18002c03c  call    cs:__imp_CoTaskMemFree
0x18002c043  nop     dword ptr [rax+rax+00h]
0x18002c048  xor     al, al
0x18002c04a  mov     rcx, [rsp+68h+var_18]
0x18002c04f  xor     rcx, rsp; StackCookie
0x18002c052  call    __security_check_cookie
0x18002c057  add     rsp, 60h
0x18002c05b  pop     rbx
0x18002c05c  retn
0x18002c05e  mov     eax, dword ptr [rsp+68h+pv+4]
0x18002c062  or      [rbx+40h], eax
0x18002c065  test    rcx, rcx
0x18002c068  jz      short loc_18002C07E
0x18002c06a  lea     rdx, [rsp+68h+var_48]
0x18002c06f  mov     rcx, rbx
0x18002c072  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002c077  mov     rcx, [rsp+68h+pv+8]
0x18002c07c  jmp     short loc_18002C088
0x18002c07e  mov     edx, dword ptr [rsp+68h+pv]
0x18002c082  mov     [rbx+0B8h], edx
0x18002c088  call    cs:__imp_CoTaskMemFree
0x18002c08f  nop     dword ptr [rax+rax+00h]
0x18002c094  mov     al, 1
0x18002c096  jmp     short loc_18002C04A
```
