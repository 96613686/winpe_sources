# LsaDbpDsDeleteObject(_UNICODE_STRING *)

- ea: `0x18001f740`
- end: `0x18001f88a`
- name: `?LsaDbpDsDeleteObject@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015bf0`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x1800107e0`
- `0x18001182c`
- `0x180011d6c`
- `0x18001f3b4`
- `0x18001f5c0`
- `0x18001f740`
- `0x18001fbcc`

## import_xrefs

- `NTDSA!THFree` at `0x18001f82d`
- `NTDSA!THFree` at `0x18001f82d`
- `NTDSA!THClearErrors` at `0x18001f80f`
- `NTDSA!THClearErrors` at `0x18001f80f`
- `NTDSA!DirRemoveEntry` at `0x18001f7ff`
- `NTDSA!DirRemoveEntry` at `0x18001f7ff`

## pseudocode

```c
__int64 __fastcall LsaDbpDsDeleteObject(struct _UNICODE_STRING *a1)
{
  int inited; // ebx
  __int64 v3; // r8
  struct _DSNAME *v4; // rdi
  unsigned int v5; // eax
  _BYTE v7[8]; // [rsp+20h] [rbp-E0h] BYREF
  struct _DSNAME *v8; // [rsp+28h] [rbp-D8h] BYREF
  struct _COMMRES *v9; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[208]; // [rsp+60h] [rbp-A0h] BYREF

  v8 = 0;
  v7[0] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids);
  inited = LsaDbpDsInitAllocAsNeededEx(2, 0, v7);
  if ( inited >= 0 )
  {
    inited = LsaDbpAllocAndInitializeDsNameFromUnicode(a1, &v8);
    if ( inited >= 0 )
    {
      v9 = 0;
      memset_0(v10, 0, 0xE8u);
      LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v11, 0);
      v4 = v8;
      v10[0] = v8;
      v5 = DirRemoveEntry(v10, &v9);
      if ( v9 )
      {
        inited = LsaDbpDsMapDsReturnToStatusEx(v5, v9);
      }
      else
      {
        THClearErrors();
        inited = -1073741801;
      }
      LsaDbpDsContinueTransaction();
      THFree(v4);
    }
    LOBYTE(v3) = v7[0];
    LsaDbpDsDeleteAllocAsNeededEx(2, 0, v3);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids,
      (unsigned int)inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001f740  mov     [rsp-8+arg_8], rbx
0x18001f745  mov     [rsp-8+arg_10], rdi
0x18001f74a  push    rbp
0x18001f74b  lea     rbp, [rsp-40h]
0x18001f750  sub     rsp, 140h
0x18001f757  mov     rax, cs:__security_cookie
0x18001f75e  xor     rax, rsp
0x18001f761  mov     [rbp+40h+var_10], rax
0x18001f765  mov     rdi, rcx
0x18001f768  mov     [rsp+140h+var_118], 0
0x18001f771  mov     [rsp+140h+var_120], 0
0x18001f776  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f77d  test    byte ptr [rcx+1Ch], 1
0x18001f781  jz      short loc_18001F798
0x18001f783  mov     rcx, [rcx+10h]
0x18001f787  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x18001f78e  mov     edx, 22h ; '"'
0x18001f793  call    WPP_SF_
0x18001f798  xor     edx, edx
0x18001f79a  lea     r8, [rsp+140h+var_120]
0x18001f79f  lea     ecx, [rdx+2]
0x18001f7a2  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x18001f7a7  mov     ebx, eax
0x18001f7a9  test    eax, eax
0x18001f7ab  js      loc_18001F842
0x18001f7b1  lea     rdx, [rsp+140h+var_118]; struct _DSNAME **
0x18001f7b6  mov     rcx, rdi; struct _UNICODE_STRING *
0x18001f7b9  call    ?LsaDbpAllocAndInitializeDsNameFromUnicode@@YAJPEAU_UNICODE_STRING@@PEAPEAU_DSNAME@@@Z; LsaDbpAllocAndInitializeDsNameFromUnicode(_UNICODE_STRING *,_DSNAME * *)
0x18001f7be  mov     ebx, eax
0x18001f7c0  test    eax, eax
0x18001f7c2  js      short loc_18001F833
0x18001f7c4  xor     edx, edx; Val
0x18001f7c6  mov     [rsp+140h+var_110], 0
0x18001f7cf  mov     r8d, 0E8h; Size
0x18001f7d5  lea     rcx, [rsp+140h+var_100]; void *
0x18001f7da  call    memset_0
0x18001f7df  xor     edx, edx; unsigned int
0x18001f7e1  lea     rcx, [rsp+140h+var_E0]; struct _COMMARG *
0x18001f7e6  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x18001f7eb  mov     rdi, [rsp+140h+var_118]
0x18001f7f0  lea     rdx, [rsp+140h+var_110]
0x18001f7f5  lea     rcx, [rsp+140h+var_100]
0x18001f7fa  mov     [rsp+140h+var_100], rdi
0x18001f7ff  call    cs:__imp_DirRemoveEntry
0x18001f805  mov     rdx, [rsp+140h+var_110]; struct _COMMRES *
0x18001f80a  test    rdx, rdx
0x18001f80d  jnz     short loc_18001F81C
0x18001f80f  call    cs:__imp_THClearErrors
0x18001f815  mov     ebx, 0C0000017h
0x18001f81a  jmp     short loc_18001F825
0x18001f81c  mov     ecx, eax; unsigned int
0x18001f81e  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x18001f823  mov     ebx, eax
0x18001f825  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x18001f82a  mov     rcx, rdi
0x18001f82d  call    cs:__imp_THFree
0x18001f833  mov     r8b, [rsp+140h+var_120]
0x18001f838  xor     edx, edx
0x18001f83a  lea     ecx, [rdx+2]
0x18001f83d  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x18001f842  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f849  test    byte ptr [rcx+1Ch], 1
0x18001f84d  jz      short loc_18001F867
0x18001f84f  mov     rcx, [rcx+10h]
0x18001f853  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x18001f85a  mov     edx, 23h ; '#'
0x18001f85f  mov     r9d, ebx
0x18001f862  call    WPP_SF_d
0x18001f867  mov     eax, ebx
0x18001f869  mov     rcx, [rbp+40h+var_10]
0x18001f86d  xor     rcx, rsp; StackCookie
0x18001f870  call    __security_check_cookie
0x18001f875  lea     r11, [rsp+140h+var_s0]
0x18001f87d  mov     rbx, [r11+18h]
0x18001f881  mov     rdi, [r11+20h]
0x18001f885  mov     rsp, r11
0x18001f888  pop     rbp
0x18001f889  retn
```
