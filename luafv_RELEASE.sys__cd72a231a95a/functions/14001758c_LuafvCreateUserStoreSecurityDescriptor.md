# LuafvCreateUserStoreSecurityDescriptor

- ea: `0x14001758c`
- end: `0x1400175f1`
- name: `LuafvCreateUserStoreSecurityDescriptor`
- size: `101`
- prototype: `__int64 __fastcall(__int64, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140018030`

## callees

- `0x140017140`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140017593`

## pseudocode

```c
__int64 __fastcall LuafvCreateUserStoreSecurityDescriptor(__int64 a1, struct _ACL **a2)
{
  PSID SeAliasAdminsSid; // rax
  PSID SeLocalSystemSid; // [rsp+20h] [rbp-38h] BYREF
  int v5; // [rsp+28h] [rbp-30h]
  int v6; // [rsp+2Ch] [rbp-2Ch]
  PSID v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+38h] [rbp-20h]
  int v9; // [rsp+3Ch] [rbp-1Ch]
  void *v10; // [rsp+40h] [rbp-18h]
  int v11; // [rsp+48h] [rbp-10h]
  int v12; // [rsp+4Ch] [rbp-Ch]

  v6 = 0x1FFFFF;
  v9 = 0x1FFFFF;
  v12 = 0x1FFFFF;
  v5 = 3;
  v8 = 3;
  v11 = 3;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v10 = *(void **)(a1 + 80);
  v7 = SeAliasAdminsSid;
  return LuafvBuildSecurityDescriptor((__int64)&SeLocalSystemSid, (__int64)a2, v10, a2);
}

```

## disassembly

```asm
0x14001758c  mov     r11, rsp
0x14001758f  sub     rsp, 58h
0x140017593  mov     rax, cs:__imp_SeExports
0x14001759a  mov     r9d, 1FFFFFh
0x1400175a0  mov     r10d, 3
0x1400175a6  mov     [r11-2Ch], r9d
0x1400175aa  mov     [r11-1Ch], r9d
0x1400175ae  mov     [r11-0Ch], r9d
0x1400175b2  mov     r9, rdx
0x1400175b5  mov     r8, [rax]
0x1400175b8  mov     [r11-30h], r10d
0x1400175bc  mov     [r11-20h], r10d
0x1400175c0  mov     [r11-10h], r10d
0x1400175c4  mov     rax, [r8+108h]
0x1400175cb  mov     [r11-38h], rax
0x1400175cf  mov     rax, [r8+110h]
0x1400175d6  mov     r8, [rcx+50h]
0x1400175da  lea     rcx, [r11-38h]
0x1400175de  mov     [r11-18h], r8
0x1400175e2  mov     [r11-28h], rax
0x1400175e6  call    LuafvBuildSecurityDescriptor
0x1400175eb  add     rsp, 58h
0x1400175ef  retn
```
