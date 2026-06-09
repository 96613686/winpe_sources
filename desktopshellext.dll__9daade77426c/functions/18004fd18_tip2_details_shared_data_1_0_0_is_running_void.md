# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x18004fd18`
- end: `0x18004fe11`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d84c`

## callees

- `0x18000e010`
- `0x1800278ac`
- `0x18002a3d0`
- `0x180033c80`
- `0x18004fd18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fda8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fe07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fda8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fe07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fd91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fd91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fded`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<1,0,0>::is_running(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  void *v5; // rcx
  bool v7; // bl
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+28h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-28h]
  __int128 v11; // [rsp+48h] [rbp-18h]

  wil::EnterCriticalSection(&lpCriticalSection, a1 + 192);
  v2 = *(_QWORD *)(a1 + 240);
  if ( !v2 || (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
  {
LABEL_6:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  if ( !*(_DWORD *)(a1 + 232) )
  {
    v3 = *(unsigned int *)(a1 + 184);
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
    v4 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int128 *, LPCRITICAL_SECTION))TestQueryData)(
           v2,
           0,
           v3,
           &v9,
           lpCriticalSection);
    v5 = pv[1];
    if ( !v4 )
    {
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      goto LABEL_6;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v5 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v9);
      v5 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v5);
  }
  v7 = (*(_DWORD *)(a1 + 64) & 0x100) == 0;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return v7;
}

```

## disassembly

```asm
0x18004fd18  mov     [rsp-8+arg_8], rbx
0x18004fd1d  push    rbp
0x18004fd1e  mov     rbp, rsp
0x18004fd21  sub     rsp, 60h
0x18004fd25  mov     rax, cs:__security_cookie
0x18004fd2c  xor     rax, rsp
0x18004fd2f  mov     [rbp+var_8], rax
0x18004fd33  mov     rbx, rcx
0x18004fd36  lea     rdx, [rcx+0C0h]
0x18004fd3d  lea     rcx, [rbp+lpCriticalSection]
0x18004fd41  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004fd46  mov     rcx, [rbx+0F0h]
0x18004fd4d  test    rcx, rcx
0x18004fd50  jz      short loc_18004FD9F
0x18004fd52  test    dword ptr [rbx+40h], 100h
0x18004fd59  jnz     short loc_18004FD9F
0x18004fd5b  cmp     dword ptr [rbx+0E8h], 0
0x18004fd62  jnz     loc_18004FDF3
0x18004fd68  mov     r8d, [rbx+0B8h]
0x18004fd6f  lea     r9, [rbp+var_38]
0x18004fd73  xorps   xmm0, xmm0
0x18004fd76  xor     edx, edx
0x18004fd78  movups  [rbp+var_38], xmm0
0x18004fd7c  movups  xmmword ptr [rbp+pv], xmm0
0x18004fd80  movups  [rbp+var_18], xmm0
0x18004fd84  call    TestQueryData
0x18004fd89  mov     rcx, [rbp+pv+8]; pv
0x18004fd8d  test    eax, eax
0x18004fd8f  jnz     short loc_18004FDC7
0x18004fd91  call    cs:__imp_CoTaskMemFree
0x18004fd97  mov     [rbp+pv+8], 0
0x18004fd9f  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004fda3  test    rcx, rcx
0x18004fda6  jz      short loc_18004FDAE
0x18004fda8  call    cs:__imp_LeaveCriticalSection
0x18004fdae  xor     al, al
0x18004fdb0  mov     rcx, [rbp+var_8]
0x18004fdb4  xor     rcx, rsp; StackCookie
0x18004fdb7  call    __security_check_cookie
0x18004fdbc  mov     rbx, [rsp+60h+arg_8]
0x18004fdc1  add     rsp, 60h
0x18004fdc5  pop     rbp
0x18004fdc6  retn
0x18004fdc7  mov     eax, dword ptr [rbp+pv+4]
0x18004fdca  or      [rbx+40h], eax
0x18004fdcd  test    rcx, rcx
0x18004fdd0  jz      short loc_18004FDE4
0x18004fdd2  lea     rdx, [rbp+var_38]
0x18004fdd6  mov     rcx, rbx
0x18004fdd9  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004fdde  mov     rcx, [rbp+pv+8]
0x18004fde2  jmp     short loc_18004FDED
0x18004fde4  mov     eax, dword ptr [rbp+pv]
0x18004fde7  mov     [rbx+0B8h], eax
0x18004fded  call    cs:__imp_CoTaskMemFree
0x18004fdf3  mov     ebx, [rbx+40h]
0x18004fdf6  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004fdfa  shr     ebx, 8
0x18004fdfd  not     bl
0x18004fdff  and     bl, 1
0x18004fe02  test    rcx, rcx
0x18004fe05  jz      short loc_18004FE0D
0x18004fe07  call    cs:__imp_LeaveCriticalSection
0x18004fe0d  mov     al, bl
0x18004fe0f  jmp     short loc_18004FDB0
```
