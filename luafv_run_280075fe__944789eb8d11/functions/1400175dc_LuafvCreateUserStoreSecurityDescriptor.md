# LuafvCreateUserStoreSecurityDescriptor

- ea: `0x1400175dc`
- end: `0x140017641`
- name: `LuafvCreateUserStoreSecurityDescriptor`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140018080`

## callees

- `0x140017190`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400175e3`

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
0x1400175dc  mov     r11, rsp
0x1400175df  sub     rsp, 58h
0x1400175e3  mov     rax, cs:__imp_SeExports
0x1400175ea  mov     r9d, 1FFFFFh
0x1400175f0  mov     r10d, 3
0x1400175f6  mov     [r11-2Ch], r9d
0x1400175fa  mov     [r11-1Ch], r9d
0x1400175fe  mov     [r11-0Ch], r9d
0x140017602  mov     r9, rdx
0x140017605  mov     r8, [rax]
0x140017608  mov     [r11-30h], r10d
0x14001760c  mov     [r11-20h], r10d
0x140017610  mov     [r11-10h], r10d
0x140017614  mov     rax, [r8+108h]
0x14001761b  mov     [r11-38h], rax
0x14001761f  mov     rax, [r8+110h]
0x140017626  mov     r8, [rcx+50h]
0x14001762a  lea     rcx, [r11-38h]
0x14001762e  mov     [r11-18h], r8
0x140017632  mov     [r11-28h], rax
0x140017636  call    LuafvBuildSecurityDescriptor
0x14001763b  add     rsp, 58h
0x14001763f  retn
```
