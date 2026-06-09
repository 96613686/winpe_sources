# CAdvancedSettingsReader::_s_RetrieveFileSharingMinEncryption(tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x1800157b8`
- end: `0x180015850`
- name: `?_s_RetrieveFileSharingMinEncryption@CAdvancedSettingsReader@@CAXPEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `152`
- prototype: `void __fastcall(struct tagADVANCED_SETTING_READER_VALUE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013368`

## callees

- `0x180012b60`
- `0x180012bc8`
- `0x180013600`
- `0x1800157b8`

## pseudocode

```c
void __fastcall CAdvancedSettingsReader::_s_RetrieveFileSharingMinEncryption(
        struct tagADVANCED_SETTING_READER_VALUE *a1)
{
  bool v2; // bl
  __int64 v3; // rdx
  HKEY v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  v2 = 1;
  if ( (int)SHRegGetDWORD((HKEY)a1, L"System\\CurrentControlSet\\Control\\Lsa\\MSV1_0", L"NtlmMinClientSec", &v6) >= 0
    && (v6 & 0x20000000) != 0 )
  {
    v7 = 0;
    if ( (int)SHRegGetDWORD(v4, L"System\\CurrentControlSet\\Control\\Lsa\\MSV1_0", L"NtlmMinServerSec", &v7) >= 0 )
      v2 = (v7 & 0x20000000) == 0;
  }
  LOBYTE(v5) = v2;
  *(_DWORD *)a1 = IsOnFromValue_bool_(&qword_18001EB30, v3, v5);
  *((_DWORD *)a1 + 1) = ButtonFromValue_bool_();
}

```

## disassembly

```asm
0x1800157b8  mov     [rsp+arg_10], rbx
0x1800157bd  push    rdi
0x1800157be  sub     rsp, 20h
0x1800157c2  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x1800157c7  mov     [rsp+28h+arg_0], 0
0x1800157cf  lea     r8, aNtlmminclients; "NtlmMinClientSec"
0x1800157d6  mov     rdi, rcx
0x1800157d9  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x1800157e0  mov     bl, 1
0x1800157e2  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800157e7  test    eax, eax
0x1800157e9  js      short loc_18001582C
0x1800157eb  test    [rsp+28h+arg_0], 20000000h
0x1800157f3  jz      short loc_18001582C
0x1800157f5  lea     r9, [rsp+28h+arg_8]; unsigned int *
0x1800157fa  mov     [rsp+28h+arg_8], 0
0x180015802  lea     r8, aNtlmminservers; "NtlmMinServerSec"
0x180015809  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x180015810  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180015815  test    eax, eax
0x180015817  js      short loc_18001582C
0x180015819  test    [rsp+28h+arg_8], 20000000h
0x180015821  mov     eax, 0
0x180015826  movzx   ebx, bl
0x180015829  cmovnz  ebx, eax
0x18001582c  mov     r8b, bl
0x18001582f  lea     rcx, qword_18001EB30
0x180015836  call    _IsOnFromValue_bool_
0x18001583b  mov     [rdi], eax
0x18001583d  call    _ButtonFromValue_bool_
0x180015842  mov     rbx, [rsp+28h+arg_10]
0x180015847  mov     [rdi+4], eax
0x18001584a  add     rsp, 20h
0x18001584e  pop     rdi
0x18001584f  retn
```
