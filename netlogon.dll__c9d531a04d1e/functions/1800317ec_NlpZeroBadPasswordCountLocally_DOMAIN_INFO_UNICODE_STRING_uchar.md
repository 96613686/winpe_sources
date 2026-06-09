# NlpZeroBadPasswordCountLocally(_DOMAIN_INFO *,_UNICODE_STRING *,uchar)

- ea: `0x1800317ec`
- end: `0x18003193e`
- name: `?NlpZeroBadPasswordCountLocally@@YAJPEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@E@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002e730`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x1800317ec`

## import_xrefs

- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800318cf`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800318cf`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800318f9`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800318f9`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18003189a`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18003189a`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180031904`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180031904`
- `SAMSRV!SamrCloseHandle` at `0x180031917`
- `SAMSRV!SamrCloseHandle` at `0x180031917`

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
0x1800317ec  mov     [rsp-8+arg_10], rbx
0x1800317f1  push    rbp
0x1800317f2  push    rsi
0x1800317f3  push    rdi
0x1800317f4  lea     rbp, [rsp-40h]
0x1800317f9  sub     rsp, 140h
0x180031800  mov     rax, cs:__security_cookie
0x180031807  xor     rax, rsp
0x18003180a  mov     [rbp+50h+var_20], rax
0x18003180e  mov     dil, r8b
0x180031811  mov     [rsp+150h+var_100], 0
0x18003181a  mov     rsi, rdx
0x18003181d  mov     rbx, rcx
0x180031820  xor     edx, edx; Val
0x180031822  lea     rcx, [rsp+150h+var_E0]; void *
0x180031827  mov     r8d, 0C0h; Size
0x18003182d  call    memset_0
0x180031832  cmp     dword ptr [rbx+24Ch], 2
0x180031839  xorps   xmm0, xmm0
0x18003183c  movups  [rsp+150h+var_F0], xmm0
0x180031841  mov     [rsp+150h+var_F8], 0
0x18003184a  jz      short loc_180031856
0x18003184c  mov     eax, 0C00000DEh
0x180031851  jmp     loc_18003191F
0x180031856  mov     rcx, [rbx+178h]
0x18003185d  lea     rax, [rsp+150h+var_100]
0x180031862  mov     [rsp+150h+var_110], rax
0x180031867  mov     r9d, 4
0x18003186d  lea     rax, [rsp+150h+var_F0]
0x180031872  mov     r8, rsi
0x180031875  mov     [rsp+150h+var_118], rax
0x18003187a  mov     edx, 208h
0x18003187f  lea     rax, [rsp+150h+var_F8]
0x180031884  mov     [rsp+150h+var_120], rax
0x180031889  mov     [rsp+150h+var_128], 0
0x180031892  mov     [rsp+150h+var_130], 8
0x18003189a  call    cs:__imp_SamIGetUserLogonInformation2
0x1800318a0  mov     ebx, eax
0x1800318a2  test    eax, eax
0x1800318a4  jns     short loc_1800318AF
0x1800318a6  lea     rdx, aNlpzerobadpass; "NlpZeroBadPasswordCountLocally: SamIGet"...
0x1800318ad  jmp     short loc_1800318E2
0x1800318af  mov     rcx, [rsp+150h+var_100]
0x1800318b4  lea     rdx, [rsp+150h+var_E0]
0x1800318b9  neg     dil
0x1800318bc  sbb     eax, eax
0x1800318be  and     eax, 0FFF80000h
0x1800318c3  add     eax, 100000h
0x1800318c8  or      eax, 4
0x1800318cb  or      [rsp+150h+var_E0], eax
0x1800318cf  call    cs:__imp_SamIUpdateLogonStatistics
0x1800318d5  mov     ebx, eax
0x1800318d7  test    eax, eax
0x1800318d9  jns     short loc_1800318EF
0x1800318db  lea     rdx, aNlpzerobadpass_0; "NlpZeroBadPasswordCountLocally: SamrSet"...
0x1800318e2  mov     r8d, eax
0x1800318e5  mov     ecx, 100h; unsigned int
0x1800318ea  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800318ef  mov     rcx, [rsp+150h+var_F8]
0x1800318f4  test    rcx, rcx
0x1800318f7  jz      short loc_1800318FF
0x1800318f9  call    cs:__imp_SamIFree_UserInternal6Information
0x1800318ff  lea     rcx, [rsp+150h+var_F0]
0x180031904  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003190a  cmp     [rsp+150h+var_100], 0
0x180031910  jz      short loc_18003191D
0x180031912  lea     rcx, [rsp+150h+var_100]
0x180031917  call    cs:__imp_SamrCloseHandle
0x18003191d  mov     eax, ebx
0x18003191f  mov     rcx, [rbp+50h+var_20]
0x180031923  xor     rcx, rsp; StackCookie
0x180031926  call    __security_check_cookie
0x18003192b  mov     rbx, [rsp+150h+arg_10]
0x180031933  add     rsp, 140h
0x18003193a  pop     rdi
0x18003193b  pop     rsi
0x18003193c  pop     rbp
0x18003193d  retn
```
