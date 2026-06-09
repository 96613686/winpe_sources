# QueryFirewallEnabled(int *)

- ea: `0x18001524c`
- end: `0x180015420`
- name: `?QueryFirewallEnabled@@YAJPEAH@Z`
- size: `468`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015430`

## callees

- `0x180004f34`
- `0x18001524c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001528e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001528e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015402`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015402`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800152ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800152ff`

## pseudocode

```c
__int64 __fastcall QueryFirewallEnabled(int *a1)
{
  HRESULT v2; // ebx
  int v3; // r14d
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int i; // edi
  __int64 v7; // rdx
  int v8; // eax
  _DWORD v10[4]; // [rsp+30h] [rbp-10h]
  __int16 v11; // [rsp+80h] [rbp+40h] BYREF
  int v12; // [rsp+88h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+50h] BYREF

  v10[1] = 2;
  ppv = 0;
  v11 = 0;
  v12 = 0;
  v10[2] = 4;
  *a1 = 1;
  v10[0] = 1;
  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
  {
    v3 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_27;
    v5 = 10;
LABEL_5:
    WPP_SF_d(v4[2], v5, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids, (unsigned int)v2);
LABEL_27:
    *a1 = 0;
    goto LABEL_28;
  }
  v3 = 1;
  v2 = CoCreateInstance(&CLSID_NetFwPolicy2, 0, 1u, &GUID_98325047_c671_4174_8d81_defcd3f03186, &ppv);
  if ( v2 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_27;
    v5 = 11;
    goto LABEL_5;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v12);
  if ( v2 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_27;
    v5 = 12;
    goto LABEL_5;
  }
  for ( i = 0; i < 3; ++i )
  {
    v7 = (unsigned int)v10[i];
    if ( ((unsigned int)v7 & v12) != 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)ppv + 64LL))(ppv, v7, &v11);
      if ( v2 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 13;
          goto LABEL_5;
        }
        goto LABEL_27;
      }
      if ( !*a1 || (v8 = 1, !v11) )
        v8 = 0;
      *a1 = v8;
    }
  }
LABEL_28:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v3 == 1 )
    CoUninitialize();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001524c  push    rbp
0x18001524e  push    rbx
0x18001524f  push    rsi
0x180015250  push    rdi
0x180015251  push    r12
0x180015253  push    r14
0x180015255  push    r15
0x180015257  mov     rbp, rsp
0x18001525a  sub     rsp, 40h
0x18001525e  xor     r15d, r15d
0x180015261  mov     [rbp+var_C], 2
0x180015268  mov     rsi, rcx
0x18001526b  mov     [rbp+arg_10], r15
0x18001526f  xor     edx, edx; dwCoInit
0x180015271  mov     [rbp+arg_0], r15w
0x180015276  mov     [rbp+arg_8], r15d
0x18001527a  lea     r12d, [r15+1]
0x18001527e  mov     [rbp+var_8], 4
0x180015285  mov     [rcx], r12d
0x180015288  xor     ecx, ecx; pvReserved
0x18001528a  mov     [rbp+var_10], r12d
0x18001528e  call    cs:__imp_CoInitializeEx
0x180015295  nop     dword ptr [rax+rax+00h]
0x18001529a  mov     ebx, eax
0x18001529c  test    eax, eax
0x18001529e  jns     short loc_1800152E0
0x1800152a0  mov     r14d, r15d
0x1800152a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152aa  lea     rax, WPP_GLOBAL_Control
0x1800152b1  cmp     rcx, rax
0x1800152b4  jz      loc_1800153E5
0x1800152ba  test    [rcx+1Ch], r12b
0x1800152be  jz      loc_1800153E5
0x1800152c4  lea     edx, [r15+0Ah]
0x1800152c8  mov     rcx, [rcx+10h]
0x1800152cc  lea     r8, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids
0x1800152d3  mov     r9d, ebx
0x1800152d6  call    WPP_SF_d
0x1800152db  jmp     loc_1800153E5
0x1800152e0  lea     rax, [rbp+arg_10]
0x1800152e4  mov     r8d, r12d; dwClsContext
0x1800152e7  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x1800152ee  mov     [rsp+40h+ppv], rax; ppv
0x1800152f3  xor     edx, edx; pUnkOuter
0x1800152f5  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x1800152fc  mov     r14d, r12d
0x1800152ff  call    cs:__imp_CoCreateInstance
0x180015306  nop     dword ptr [rax+rax+00h]
0x18001530b  mov     ebx, eax
0x18001530d  test    eax, eax
0x18001530f  jns     short loc_180015339
0x180015311  mov     rcx, cs:WPP_GLOBAL_Control
0x180015318  lea     rax, WPP_GLOBAL_Control
0x18001531f  cmp     rcx, rax
0x180015322  jz      loc_1800153E5
0x180015328  test    [rcx+1Ch], r12b
0x18001532c  jz      loc_1800153E5
0x180015332  mov     edx, 0Bh
0x180015337  jmp     short loc_1800152C8
0x180015339  mov     rcx, [rbp+arg_10]
0x18001533d  lea     rdx, [rbp+arg_8]
0x180015341  mov     rax, [rcx]
0x180015344  mov     rax, [rax+38h]
0x180015348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001534d  mov     ebx, eax
0x18001534f  test    eax, eax
0x180015351  jns     short loc_180015376
0x180015353  mov     rcx, cs:WPP_GLOBAL_Control
0x18001535a  lea     rax, WPP_GLOBAL_Control
0x180015361  cmp     rcx, rax
0x180015364  jz      short loc_1800153E5
0x180015366  test    [rcx+1Ch], r12b
0x18001536a  jz      short loc_1800153E5
0x18001536c  mov     edx, 0Ch
0x180015371  jmp     loc_1800152C8
0x180015376  mov     edi, r15d
0x180015379  mov     eax, ebx
0x18001537b  cmp     edi, 3
0x18001537e  jnb     short loc_1800153E1
0x180015380  mov     eax, edi
0x180015382  mov     edx, [rbp+rax*4+var_10]
0x180015386  test    [rbp+arg_8], edx
0x180015389  jz      short loc_1800153B9
0x18001538b  mov     rcx, [rbp+arg_10]
0x18001538f  lea     r8, [rbp+arg_0]
0x180015393  mov     rax, [rcx]
0x180015396  mov     rax, [rax+40h]
0x18001539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001539f  mov     ebx, eax
0x1800153a1  test    eax, eax
0x1800153a3  js      short loc_1800153BE
0x1800153a5  cmp     [rsi], r15d
0x1800153a8  jz      short loc_1800153B4
0x1800153aa  mov     eax, r12d
0x1800153ad  cmp     [rbp+arg_0], r15w
0x1800153b2  jnz     short loc_1800153B7
0x1800153b4  mov     eax, r15d
0x1800153b7  mov     [rsi], eax
0x1800153b9  add     edi, r12d
0x1800153bc  jmp     short loc_180015379
0x1800153be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153c5  lea     rax, WPP_GLOBAL_Control
0x1800153cc  cmp     rcx, rax
0x1800153cf  jz      short loc_1800153E5
0x1800153d1  test    [rcx+1Ch], r12b
0x1800153d5  jz      short loc_1800153E5
0x1800153d7  mov     edx, 0Dh
0x1800153dc  jmp     loc_1800152C8
0x1800153e1  test    eax, eax
0x1800153e3  jns     short loc_1800153E8
0x1800153e5  mov     [rsi], r15d
0x1800153e8  mov     rcx, [rbp+arg_10]
0x1800153ec  test    rcx, rcx
0x1800153ef  jz      short loc_1800153FD
0x1800153f1  mov     rax, [rcx]
0x1800153f4  mov     rax, [rax+10h]
0x1800153f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153fd  cmp     r14d, r12d
0x180015400  jnz     short loc_18001540E
0x180015402  call    cs:__imp_CoUninitialize
0x180015409  nop     dword ptr [rax+rax+00h]
0x18001540e  mov     eax, ebx
0x180015410  add     rsp, 40h
0x180015414  pop     r15
0x180015416  pop     r14
0x180015418  pop     r12
0x18001541a  pop     rdi
0x18001541b  pop     rsi
0x18001541c  pop     rbx
0x18001541d  pop     rbp
0x18001541e  retn
```
