# ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)

- ea: `0x1800382e0`
- end: `0x180038364`
- name: `?GetProgramDataProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ`
- size: `132`
- prototype: `const struct expanded_wstring *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013280`
- `0x1800172e8`

## callees

- `0x1800021b4`
- `0x18000fcc4`
- `0x180038278`
- `0x1800382e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180038342`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038342`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180038339`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180038339`

## string_xrefs

- `0x180038312`: `%PROGRAMDATA%\Microsoft\Provisioning\`

## pseudocode

```c
const struct expanded_wstring *ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)
{
  struct ProvisioningPaths *Instance; // rsi
  expanded_wstring *v1; // rbx
  expanded_wstring *v2; // rax
  void **v3; // rdi

  Instance = ProvisioningPaths::GetInstance();
  v1 = (expanded_wstring *)*((_QWORD *)Instance + 1);
  if ( !v1 )
  {
    v2 = (expanded_wstring *)operator new(0x10u);
    if ( v2 )
      v1 = expanded_wstring::expanded_wstring(v2, L"%PROGRAMDATA%\\Microsoft\\Provisioning\\");
    else
      v1 = 0;
    v3 = (void **)*((_QWORD *)Instance + 1);
    if ( v1 == (expanded_wstring *)v3 )
    {
      return (const struct expanded_wstring *)*((_QWORD *)Instance + 1);
    }
    else
    {
      if ( v3 )
      {
        operator delete[](*v3);
        operator delete(v3);
      }
      *((_QWORD *)Instance + 1) = v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800382e0  mov     [rsp+arg_8], rbx
0x1800382e5  mov     [rsp+arg_10], rsi
0x1800382ea  push    rdi
0x1800382eb  sub     rsp, 20h
0x1800382ef  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x1800382f4  mov     rsi, rax
0x1800382f7  mov     rbx, [rax+8]
0x1800382fb  test    rbx, rbx
0x1800382fe  jnz     short loc_180038351
0x180038300  lea     ecx, [rbx+10h]; Size
0x180038303  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038308  mov     [rsp+28h+arg_0], rax
0x18003830d  test    rax, rax
0x180038310  jz      short loc_180038326
0x180038312  lea     rdx, ?gc_szProvisioningFolderPath@@3QBGB; "%PROGRAMDATA%\\Microsoft\\Provisioning"...
0x180038319  mov     rcx, rax; this
0x18003831c  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180038321  mov     rbx, rax
0x180038324  jmp     short loc_180038328
0x180038326  xor     ebx, ebx
0x180038328  mov     rdi, [rsi+8]
0x18003832c  cmp     rbx, rdi
0x18003832f  jz      short loc_18003834E
0x180038331  test    rdi, rdi
0x180038334  jz      short loc_180038348
0x180038336  mov     rcx, [rdi]
0x180038339  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003833f  mov     rcx, rdi
0x180038342  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038348  mov     [rsi+8], rbx
0x18003834c  jmp     short loc_180038351
0x18003834e  mov     rbx, rdi
0x180038351  mov     rax, rbx
0x180038354  mov     rbx, [rsp+28h+arg_8]
0x180038359  mov     rsi, [rsp+28h+arg_10]
0x18003835e  add     rsp, 20h
0x180038362  pop     rdi
0x180038363  retn
```
