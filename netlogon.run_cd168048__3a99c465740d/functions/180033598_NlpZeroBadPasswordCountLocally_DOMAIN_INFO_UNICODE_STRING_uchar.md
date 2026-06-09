# NlpZeroBadPasswordCountLocally(_DOMAIN_INFO *,_UNICODE_STRING *,uchar)

- ea: `0x180033598`
- end: `0x180033709`
- name: `?NlpZeroBadPasswordCountLocally@@YAJPEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@E@Z`
- size: `369`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18003033c`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x180033598`

## import_xrefs

- `SAMSRV!SamIUpdateLogonStatistics` at `0x180033681`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180033681`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800336b1`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800336b1`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180033646`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180033646`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800336c2`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800336c2`
- `SAMSRV!SamrCloseHandle` at `0x1800336db`
- `SAMSRV!SamrCloseHandle` at `0x1800336db`

## pseudocode

```c
__int64 __fastcall NlpZeroBadPasswordCountLocally(struct _DOMAIN_INFO *a1, struct _UNICODE_STRING *a2, char a3)
{
  bool v6; // zf
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v13; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v14[48]; // [rsp+70h] [rbp-90h] BYREF

  v11 = 0;
  memset_0(v14, 0, sizeof(v14));
  v6 = *((_DWORD *)a1 + 147) == 2;
  v13 = 0;
  v12 = 0;
  if ( !v6 )
    return 3221225694LL;
  v8 = SamIGetUserLogonInformation2(*((_QWORD *)a1 + 47), 520, a2, 4, 8, 0, &v12, &v13, &v11);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v14[0] |= (a3 != 0 ? 0x80000 : 0x100000) | 4;
    v10 = SamIUpdateLogonStatistics(v11, v14);
    v9 = v10;
    if ( v10 < 0 )
      NlPrintRoutine(0x100u, L"NlpZeroBadPasswordCountLocally: SamrSetInformationUser failed 0x%lx", (unsigned int)v10);
  }
  else
  {
    NlPrintRoutine(
      0x100u,
      L"NlpZeroBadPasswordCountLocally: SamIGetUserLogonInformation2 failed 0x%lx",
      (unsigned int)v8);
  }
  if ( v12 )
    SamIFree_UserInternal6Information();
  SamIFreeSidAndAttributesList(&v13);
  if ( v11 )
    SamrCloseHandle(&v11);
  return v9;
}

```

## disassembly

```asm
0x180033598  mov     [rsp-8+arg_10], rbx
0x18003359d  push    rbp
0x18003359e  push    rsi
0x18003359f  push    rdi
0x1800335a0  lea     rbp, [rsp-40h]
0x1800335a5  sub     rsp, 140h
0x1800335ac  mov     rax, cs:__security_cookie
0x1800335b3  xor     rax, rsp
0x1800335b6  mov     [rbp+50h+var_20], rax
0x1800335ba  mov     dil, r8b
0x1800335bd  mov     [rsp+150h+var_100], 0
0x1800335c6  mov     rsi, rdx
0x1800335c9  mov     rbx, rcx
0x1800335cc  xor     edx, edx; Val
0x1800335ce  lea     rcx, [rsp+150h+var_E0]; void *
0x1800335d3  mov     r8d, 0C0h; Size
0x1800335d9  call    memset_0
0x1800335de  cmp     dword ptr [rbx+24Ch], 2
0x1800335e5  xorps   xmm0, xmm0
0x1800335e8  movups  [rsp+150h+var_F0], xmm0
0x1800335ed  mov     [rsp+150h+var_F8], 0
0x1800335f6  jz      short loc_180033602
0x1800335f8  mov     eax, 0C00000DEh
0x1800335fd  jmp     loc_1800336E9
0x180033602  mov     rcx, [rbx+178h]
0x180033609  lea     rax, [rsp+150h+var_100]
0x18003360e  mov     [rsp+150h+var_110], rax
0x180033613  mov     r9d, 4
0x180033619  lea     rax, [rsp+150h+var_F0]
0x18003361e  mov     r8, rsi
0x180033621  mov     [rsp+150h+var_118], rax
0x180033626  mov     edx, 208h
0x18003362b  lea     rax, [rsp+150h+var_F8]
0x180033630  mov     [rsp+150h+var_120], rax
0x180033635  mov     [rsp+150h+var_128], 0
0x18003363e  mov     [rsp+150h+var_130], 8
0x180033646  call    cs:__imp_SamIGetUserLogonInformation2
0x18003364d  nop     dword ptr [rax+rax+00h]
0x180033652  mov     ebx, eax
0x180033654  test    eax, eax
0x180033656  jns     short loc_180033661
0x180033658  lea     rdx, aNlpzerobadpass; "NlpZeroBadPasswordCountLocally: SamIGet"...
0x18003365f  jmp     short loc_18003369A
0x180033661  mov     rcx, [rsp+150h+var_100]
0x180033666  lea     rdx, [rsp+150h+var_E0]
0x18003366b  neg     dil
0x18003366e  sbb     eax, eax
0x180033670  and     eax, 0FFF80000h
0x180033675  add     eax, 100000h
0x18003367a  or      eax, 4
0x18003367d  or      [rsp+150h+var_E0], eax
0x180033681  call    cs:__imp_SamIUpdateLogonStatistics
0x180033688  nop     dword ptr [rax+rax+00h]
0x18003368d  mov     ebx, eax
0x18003368f  test    eax, eax
0x180033691  jns     short loc_1800336A7
0x180033693  lea     rdx, aNlpzerobadpass_0; "NlpZeroBadPasswordCountLocally: SamrSet"...
0x18003369a  mov     r8d, eax
0x18003369d  mov     ecx, 100h; unsigned int
0x1800336a2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800336a7  mov     rcx, [rsp+150h+var_F8]
0x1800336ac  test    rcx, rcx
0x1800336af  jz      short loc_1800336BD
0x1800336b1  call    cs:__imp_SamIFree_UserInternal6Information
0x1800336b8  nop     dword ptr [rax+rax+00h]
0x1800336bd  lea     rcx, [rsp+150h+var_F0]
0x1800336c2  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800336c9  nop     dword ptr [rax+rax+00h]
0x1800336ce  cmp     [rsp+150h+var_100], 0
0x1800336d4  jz      short loc_1800336E7
0x1800336d6  lea     rcx, [rsp+150h+var_100]
0x1800336db  call    cs:__imp_SamrCloseHandle
0x1800336e2  nop     dword ptr [rax+rax+00h]
0x1800336e7  mov     eax, ebx
0x1800336e9  mov     rcx, [rbp+50h+var_20]
0x1800336ed  xor     rcx, rsp; StackCookie
0x1800336f0  call    __security_check_cookie
0x1800336f5  mov     rbx, [rsp+150h+arg_10]
0x1800336fd  add     rsp, 140h
0x180033704  pop     rdi
0x180033705  pop     rsi
0x180033706  pop     rbp
0x180033707  retn
```
