# tip2::details::shared_data<1,0,1>::is_running(void)

- ea: `0x180053798`
- end: `0x180053891`
- name: `?is_running@?$shared_data@$00$0A@$00@details@tip2@@AEAA_NXZ`
- size: `249`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800234ec`
- `0x18002663c`
- `0x1800273dc`
- `0x18005287c`

## callees

- `0x18000e010`
- `0x18002771c`
- `0x18002a3d0`
- `0x180033c80`
- `0x180053798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053828`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053887`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053828`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053887`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005386d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005386d`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<1,0,1>::is_running(__int64 a1)
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
      tip2::details::shared_data<1,0,1>::deserialize_data(a1, &v9);
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
0x180053798  mov     [rsp-8+arg_8], rbx
0x18005379d  push    rbp
0x18005379e  mov     rbp, rsp
0x1800537a1  sub     rsp, 60h
0x1800537a5  mov     rax, cs:__security_cookie
0x1800537ac  xor     rax, rsp
0x1800537af  mov     [rbp+var_8], rax
0x1800537b3  mov     rbx, rcx
0x1800537b6  lea     rdx, [rcx+0C0h]
0x1800537bd  lea     rcx, [rbp+lpCriticalSection]
0x1800537c1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800537c6  mov     rcx, [rbx+0F0h]
0x1800537cd  test    rcx, rcx
0x1800537d0  jz      short loc_18005381F
0x1800537d2  test    dword ptr [rbx+40h], 100h
0x1800537d9  jnz     short loc_18005381F
0x1800537db  cmp     dword ptr [rbx+0E8h], 0
0x1800537e2  jnz     loc_180053873
0x1800537e8  mov     r8d, [rbx+0B8h]
0x1800537ef  lea     r9, [rbp+var_38]
0x1800537f3  xorps   xmm0, xmm0
0x1800537f6  xor     edx, edx
0x1800537f8  movups  [rbp+var_38], xmm0
0x1800537fc  movups  xmmword ptr [rbp+pv], xmm0
0x180053800  movups  [rbp+var_18], xmm0
0x180053804  call    TestQueryData
0x180053809  mov     rcx, [rbp+pv+8]; pv
0x18005380d  test    eax, eax
0x18005380f  jnz     short loc_180053847
0x180053811  call    cs:__imp_CoTaskMemFree
0x180053817  mov     [rbp+pv+8], 0
0x18005381f  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180053823  test    rcx, rcx
0x180053826  jz      short loc_18005382E
0x180053828  call    cs:__imp_LeaveCriticalSection
0x18005382e  xor     al, al
0x180053830  mov     rcx, [rbp+var_8]
0x180053834  xor     rcx, rsp; StackCookie
0x180053837  call    __security_check_cookie
0x18005383c  mov     rbx, [rsp+60h+arg_8]
0x180053841  add     rsp, 60h
0x180053845  pop     rbp
0x180053846  retn
0x180053847  mov     eax, dword ptr [rbp+pv+4]
0x18005384a  or      [rbx+40h], eax
0x18005384d  test    rcx, rcx
0x180053850  jz      short loc_180053864
0x180053852  lea     rdx, [rbp+var_38]
0x180053856  mov     rcx, rbx
0x180053859  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18005385e  mov     rcx, [rbp+pv+8]
0x180053862  jmp     short loc_18005386D
0x180053864  mov     eax, dword ptr [rbp+pv]
0x180053867  mov     [rbx+0B8h], eax
0x18005386d  call    cs:__imp_CoTaskMemFree
0x180053873  mov     ebx, [rbx+40h]
0x180053876  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18005387a  shr     ebx, 8
0x18005387d  not     bl
0x18005387f  and     bl, 1
0x180053882  test    rcx, rcx
0x180053885  jz      short loc_18005388D
0x180053887  call    cs:__imp_LeaveCriticalSection
0x18005388d  mov     al, bl
0x18005388f  jmp     short loc_180053830
```
