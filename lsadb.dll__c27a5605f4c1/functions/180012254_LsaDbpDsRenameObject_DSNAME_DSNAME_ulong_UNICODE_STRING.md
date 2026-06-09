# LsaDbpDsRenameObject(_DSNAME *,_DSNAME *,ulong,_UNICODE_STRING *)

- ea: `0x180012254`
- end: `0x180012394`
- name: `?LsaDbpDsRenameObject@@YAJPEAU_DSNAME@@0KPEAU_UNICODE_STRING@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct _DSNAME *, struct _DSNAME *, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014358`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18001182c`
- `0x180011d6c`
- `0x180012254`
- `0x18001f3b4`
- `0x18001f5c0`
- `0x18001fbcc`

## import_xrefs

- `NTDSA!THClearErrors` at `0x180012344`
- `NTDSA!THClearErrors` at `0x180012344`
- `NTDSA!DirModifyDN` at `0x180012334`
- `NTDSA!DirModifyDN` at `0x180012334`

## pseudocode

```c
__int64 __fastcall LsaDbpDsRenameObject(struct _DSNAME *a1, struct _DSNAME *a2, __int64 a3, struct _UNICODE_STRING *a4)
{
  __int64 result; // rax
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  char v10[8]; // [rsp+20h] [rbp-E0h] BYREF
  struct _COMMRES *v11; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h] BYREF
  __int128 *v14; // [rsp+50h] [rbp-B0h]
  _QWORD v15[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v17[224]; // [rsp+80h] [rbp-80h] BYREF

  v10[0] = 0;
  memset_0(v15, 0, 0x100u);
  v11 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  result = LsaDbpDsInitAllocAsNeededEx(2, 5, v10);
  if ( (int)result >= 0 )
  {
    memset_0(v16, 0, 0xE8u);
    LODWORD(v12) = a4->Length;
    *((_QWORD *)&v12 + 1) = a4->Buffer;
    v14 = &v12;
    v15[2] = &v13;
    LODWORD(v13) = 3;
    DWORD2(v13) = 1;
    v15[0] = a1;
    v15[1] = 0;
    LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v17, 0);
    v7 = DirModifyDN(v15, &v11);
    if ( v11 )
    {
      v9 = LsaDbpDsMapDsReturnToStatusEx(v7, v11);
    }
    else
    {
      THClearErrors(v8);
      v9 = -1073741801;
    }
    LsaDbpDsContinueTransaction();
    LsaDbpDsDeleteAllocAsNeededEx(2, 5u, v10[0]);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180012254  mov     [rsp-8+arg_8], rbx
0x180012259  mov     [rsp-8+arg_10], rdi
0x18001225e  push    rbp
0x18001225f  lea     rbp, [rsp-70h]
0x180012264  sub     rsp, 170h
0x18001226b  mov     rax, cs:__security_cookie
0x180012272  xor     rax, rsp
0x180012275  mov     [rbp+70h+var_10], rax
0x180012279  mov     rdi, rcx
0x18001227c  mov     [rsp+170h+var_150], 0
0x180012281  lea     rcx, [rsp+170h+var_110]; void *
0x180012286  xor     edx, edx; Val
0x180012288  mov     r8d, 100h; Size
0x18001228e  mov     rbx, r9
0x180012291  call    memset_0
0x180012296  xor     eax, eax
0x180012298  mov     [rsp+170h+var_148], 0
0x1800122a1  xorps   xmm0, xmm0
0x1800122a4  mov     [rsp+170h+var_120], rax
0x1800122a9  lea     r8, [rsp+170h+var_150]
0x1800122ae  movups  [rsp+170h+var_130], xmm0
0x1800122b3  lea     edx, [rax+5]
0x1800122b6  lea     ecx, [rax+2]
0x1800122b9  movups  [rsp+170h+var_140], xmm0
0x1800122be  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x1800122c3  test    eax, eax
0x1800122c5  js      loc_180012373
0x1800122cb  xor     edx, edx; Val
0x1800122cd  lea     rcx, [rsp+170h+var_F8]; void *
0x1800122d2  mov     r8d, 0E8h; Size
0x1800122d8  call    memset_0
0x1800122dd  movzx   eax, word ptr [rbx]
0x1800122e0  lea     rcx, [rbp+70h+var_F0]; struct _COMMARG *
0x1800122e4  mov     dword ptr [rsp+170h+var_140], eax
0x1800122e8  xor     edx, edx; unsigned int
0x1800122ea  mov     rax, [rbx+8]
0x1800122ee  mov     qword ptr [rsp+170h+var_140+8], rax
0x1800122f3  lea     rax, [rsp+170h+var_140]
0x1800122f8  mov     [rsp+170h+var_120], rax
0x1800122fd  lea     rax, [rsp+170h+var_130]
0x180012302  mov     [rsp+170h+var_100], rax
0x180012307  mov     dword ptr [rsp+170h+var_130], 3
0x18001230f  mov     dword ptr [rsp+170h+var_130+8], 1
0x180012317  mov     [rsp+170h+var_110], rdi
0x18001231c  mov     [rsp+170h+var_108], 0
0x180012325  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x18001232a  lea     rdx, [rsp+170h+var_148]
0x18001232f  lea     rcx, [rsp+170h+var_110]
0x180012334  call    cs:__imp_DirModifyDN
0x18001233a  mov     rdx, [rsp+170h+var_148]; struct _COMMRES *
0x18001233f  test    rdx, rdx
0x180012342  jnz     short loc_180012351
0x180012344  call    cs:__imp_THClearErrors
0x18001234a  mov     ebx, 0C0000017h
0x18001234f  jmp     short loc_18001235A
0x180012351  mov     ecx, eax; unsigned int
0x180012353  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x180012358  mov     ebx, eax
0x18001235a  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x18001235f  mov     r8b, [rsp+170h+var_150]
0x180012364  mov     edx, 5
0x180012369  lea     ecx, [rdx-3]
0x18001236c  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x180012371  mov     eax, ebx
0x180012373  mov     rcx, [rbp+70h+var_10]
0x180012377  xor     rcx, rsp; StackCookie
0x18001237a  call    __security_check_cookie
0x18001237f  lea     r11, [rsp+170h+var_s0]
0x180012387  mov     rbx, [r11+18h]
0x18001238b  mov     rdi, [r11+20h]
0x18001238f  mov     rsp, r11
0x180012392  pop     rbp
0x180012393  retn
```
