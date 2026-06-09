# CAdvancedSettingsWriter::_s_CommitFileSharingMinEncryption(ADVANCED_SETTING_WRITER_VALUE const &)

- ea: `0x18001505c`
- end: `0x180015106`
- name: `?_s_CommitFileSharingMinEncryption@CAdvancedSettingsWriter@@CAXAEBUADVANCED_SETTING_WRITER_VALUE@@@Z`
- size: `170`
- prototype: `void __fastcall(const struct ADVANCED_SETTING_WRITER_VALUE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012fe0`

## callees

- `0x180012c30`
- `0x180013600`
- `0x180013654`
- `0x18001505c`

## pseudocode

```c
void __fastcall CAdvancedSettingsWriter::_s_CommitFileSharingMinEncryption(
        const struct ADVANCED_SETTING_WRITER_VALUE *a1,
        __int64 a2)
{
  char v2; // al
  char v3; // bl
  HKEY v4; // rcx
  const unsigned __int16 *v5; // rdx
  HKEY v6; // rcx
  unsigned int v7; // r9d
  HKEY v8; // rcx
  const unsigned __int16 *v9; // rdx
  HKEY v10; // rcx
  unsigned int v11; // r9d
  unsigned int v12; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+38h] [rbp+10h] BYREF

  v2 = ValueFromButton_bool_(&qword_18001EB30, a2, *((unsigned int *)a1 + 1));
  v12 = 0;
  v3 = v2;
  SHRegGetDWORD(v4, L"System\\CurrentControlSet\\Control\\Lsa\\MSV1_0", L"NtlmMinClientSec", &v12);
  if ( v3 )
    v7 = v12 & 0xDFFFFFFF;
  else
    v7 = v12 | 0x20000000;
  v12 = v7;
  SHRegSetDWORD(v6, v5, L"NtlmMinClientSec", v7);
  v13 = 0;
  SHRegGetDWORD(v8, L"System\\CurrentControlSet\\Control\\Lsa\\MSV1_0", L"NtlmMinServerSec", &v13);
  if ( v3 )
    v11 = v13 & 0xDFFFFFFF;
  else
    v11 = v13 | 0x20000000;
  v13 = v11;
  SHRegSetDWORD(v10, v9, L"NtlmMinServerSec", v11);
}

```

## disassembly

```asm
0x18001505c  push    rbx
0x18001505e  sub     rsp, 20h
0x180015062  mov     r8d, [rcx+4]
0x180015066  lea     rcx, qword_18001EB30
0x18001506d  call    _ValueFromButton_bool_
0x180015072  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x180015077  mov     [rsp+28h+arg_0], 0
0x18001507f  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x180015086  mov     bl, al
0x180015088  lea     r8, aNtlmminclients; "NtlmMinClientSec"
0x18001508f  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180015094  mov     r9d, [rsp+28h+arg_0]
0x180015099  test    bl, bl
0x18001509b  jz      short loc_1800150A4
0x18001509d  btr     r9d, 1Dh
0x1800150a2  jmp     short loc_1800150A9
0x1800150a4  bts     r9d, 1Dh; unsigned int
0x1800150a9  lea     r8, aNtlmminclients; "NtlmMinClientSec"
0x1800150b0  mov     [rsp+28h+arg_0], r9d
0x1800150b5  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800150ba  lea     r9, [rsp+28h+arg_8]; unsigned int *
0x1800150bf  mov     [rsp+28h+arg_8], 0
0x1800150c7  lea     r8, aNtlmminservers; "NtlmMinServerSec"
0x1800150ce  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x1800150d5  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800150da  mov     r9d, [rsp+28h+arg_8]
0x1800150df  test    bl, bl
0x1800150e1  jz      short loc_1800150EA
0x1800150e3  btr     r9d, 1Dh
0x1800150e8  jmp     short loc_1800150EF
0x1800150ea  bts     r9d, 1Dh; unsigned int
0x1800150ef  lea     r8, aNtlmminservers; "NtlmMinServerSec"
0x1800150f6  mov     [rsp+28h+arg_8], r9d
0x1800150fb  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180015100  add     rsp, 20h
0x180015104  pop     rbx
0x180015105  retn
```
