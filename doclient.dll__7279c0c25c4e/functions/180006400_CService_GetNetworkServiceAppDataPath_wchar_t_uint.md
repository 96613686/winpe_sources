# CService::GetNetworkServiceAppDataPath(wchar_t *,uint)

- ea: `0x180006400`
- end: `0x180006528`
- name: `?GetNetworkServiceAppDataPath@CService@@EEBAJPEA_WI@Z`
- size: `296`
- prototype: `__int64 __fastcall(CService *__hidden this, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000933c`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000645c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000645c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006506`

## string_xrefs

- `0x1800064eb`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`

## pseudocode

```c
__int64 __fastcall CService::GetNetworkServiceAppDataPath(CService *this, wchar_t *a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 *v5; // rcx
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // r8
  void *v11; // rcx
  signed __int64 v12; // r9
  wchar_t v13; // ax
  wchar_t *v14; // rax
  unsigned int v15; // ebx
  LPVOID pv; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = a3;
  v5 = (__int64 *)*((_QWORD *)this + 10);
  if ( !v5 )
    return 2147500034LL;
  v7 = *v5;
  pv = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v7 + 32))(v5, &pv);
  if ( v8 < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v8;
  }
  v9 = v3;
  v10 = 2147483646;
  if ( (unsigned int)(v3 - 1) > 0x7FFFFFFE )
  {
    v15 = -2147024809;
    if ( v9 )
      *a2 = 0;
  }
  else
  {
    v11 = pv;
    v12 = (_BYTE *)pv - (_BYTE *)a2;
    do
    {
      if ( !v10 )
        break;
      v13 = *(wchar_t *)((char *)a2 + v12);
      if ( !v13 )
        break;
      *a2++ = v13;
      --v10;
      --v9;
    }
    while ( v9 );
    v14 = a2 - 1;
    if ( v9 )
      v14 = a2;
    *v14 = 0;
    v15 = v9 == 0 ? 0x8007007A : 0;
    if ( v9 )
    {
      if ( v11 )
        CoTaskMemFree(v11);
      return 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13C,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
    (const char *)v15,
    (int)pv);
  if ( pv )
    CoTaskMemFree(pv);
  return v15;
}

```

## disassembly

```asm
0x180006400  mov     [rsp+arg_10], rbx
0x180006405  push    rbp
0x180006406  push    rsi
0x180006407  push    rdi
0x180006408  sub     rsp, 30h
0x18000640c  mov     rax, cs:__security_cookie
0x180006413  xor     rax, rsp
0x180006416  mov     [rsp+48h+var_20], rax
0x18000641b  mov     ebx, r8d
0x18000641e  mov     rdi, rdx
0x180006421  mov     rcx, [rcx+50h]
0x180006425  xor     ebp, ebp
0x180006427  test    rcx, rcx
0x18000642a  jnz     short loc_180006436
0x18000642c  mov     eax, 80004002h
0x180006431  jmp     loc_18000650E
0x180006436  mov     rax, [rcx]
0x180006439  mov     [rsp+48h+pv], rbp; int
0x18000643e  lea     rdx, [rsp+48h+pv]
0x180006443  mov     rax, [rax+20h]
0x180006447  call    _guard_dispatch_icall
0x18000644c  mov     esi, eax
0x18000644e  test    eax, eax
0x180006450  jns     short loc_180006469
0x180006452  mov     rcx, [rsp+48h+pv]; pv
0x180006457  test    rcx, rcx
0x18000645a  jz      short loc_180006462
0x18000645c  call    cs:__imp_CoTaskMemFree
0x180006462  mov     eax, esi
0x180006464  jmp     loc_18000650E
0x180006469  mov     rdx, rbx
0x18000646c  lea     eax, [rbx-1]
0x18000646f  mov     r8d, 7FFFFFFEh
0x180006475  cmp     eax, r8d
0x180006478  ja      short loc_1800064D6
0x18000647a  mov     rcx, [rsp+48h+pv]; pv
0x18000647f  mov     r9, rcx
0x180006482  sub     r9, rdi
0x180006485  test    r8, r8
0x180006488  jz      short loc_1800064A4
0x18000648a  movzx   eax, word ptr [r9+rdi]
0x18000648f  test    ax, ax
0x180006492  jz      short loc_1800064A4
0x180006494  mov     [rdi], ax
0x180006497  add     rdi, 2
0x18000649b  dec     r8
0x18000649e  sub     rdx, 1
0x1800064a2  jnz     short loc_180006485
0x1800064a4  lea     rax, [rdi-2]
0x1800064a8  test    rdx, rdx
0x1800064ab  cmovnz  rax, rdi
0x1800064af  mov     [rax], bp
0x1800064b2  mov     rax, rdx
0x1800064b5  neg     rax
0x1800064b8  sbb     ebx, ebx
0x1800064ba  not     ebx
0x1800064bc  and     ebx, 8007007Ah
0x1800064c2  test    rdx, rdx
0x1800064c5  jz      short loc_1800064E3
0x1800064c7  test    rcx, rcx
0x1800064ca  jz      short loc_1800064D2
0x1800064cc  call    cs:__imp_CoTaskMemFree
0x1800064d2  xor     eax, eax
0x1800064d4  jmp     short loc_18000650E
0x1800064d6  mov     ebx, 80070057h
0x1800064db  test    rdx, rdx
0x1800064de  jz      short loc_1800064E3
0x1800064e0  mov     [rdi], bp
0x1800064e3  mov     rcx, [rsp+48h]; this
0x1800064e8  mov     r9d, ebx; char *
0x1800064eb  lea     r8, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800064f2  mov     edx, 13Ch; void *
0x1800064f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064fc  mov     rcx, [rsp+48h+pv]; pv
0x180006501  test    rcx, rcx
0x180006504  jz      short loc_18000650C
0x180006506  call    cs:__imp_CoTaskMemFree
0x18000650c  mov     eax, ebx
0x18000650e  mov     rcx, [rsp+48h+var_20]
0x180006513  xor     rcx, rsp; StackCookie
0x180006516  call    __security_check_cookie
0x18000651b  mov     rbx, [rsp+48h+arg_10]
0x180006520  add     rsp, 30h
0x180006524  pop     rdi
0x180006525  pop     rsi
0x180006526  pop     rbp
0x180006527  retn
```
