# ProvisioningPaths::GetProgramDataProvisioningFolderPath(void)

- ea: `0x180024880`
- end: `0x180024904`
- name: `?GetProgramDataProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ`
- size: `132`
- prototype: `const struct expanded_wstring *(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x180016840`
- `0x180017020`

## callees

- `0x180002f44`
- `0x1800245fc`
- `0x180024818`
- `0x180024880`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800248e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800248e2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800248d9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800248d9`

## string_xrefs

- `0x1800248b2`: `%PROGRAMDATA%\Microsoft\Provisioning\`

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
0x180024880  mov     [rsp+arg_8], rbx
0x180024885  mov     [rsp+arg_10], rsi
0x18002488a  push    rdi
0x18002488b  sub     rsp, 20h
0x18002488f  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x180024894  mov     rsi, rax
0x180024897  mov     rbx, [rax+8]
0x18002489b  test    rbx, rbx
0x18002489e  jnz     short loc_1800248F1
0x1800248a0  lea     ecx, [rbx+10h]; Size
0x1800248a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800248a8  mov     [rsp+28h+arg_0], rax
0x1800248ad  test    rax, rax
0x1800248b0  jz      short loc_1800248C6
0x1800248b2  lea     rdx, ?gc_szProvisioningFolderPath@@3QBGB; "%PROGRAMDATA%\\Microsoft\\Provisioning"...
0x1800248b9  mov     rcx, rax; this
0x1800248bc  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800248c1  mov     rbx, rax
0x1800248c4  jmp     short loc_1800248C8
0x1800248c6  xor     ebx, ebx
0x1800248c8  mov     rdi, [rsi+8]
0x1800248cc  cmp     rbx, rdi
0x1800248cf  jz      short loc_1800248EE
0x1800248d1  test    rdi, rdi
0x1800248d4  jz      short loc_1800248E8
0x1800248d6  mov     rcx, [rdi]
0x1800248d9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800248df  mov     rcx, rdi
0x1800248e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800248e8  mov     [rsi+8], rbx
0x1800248ec  jmp     short loc_1800248F1
0x1800248ee  mov     rbx, rdi
0x1800248f1  mov     rax, rbx
0x1800248f4  mov     rbx, [rsp+28h+arg_8]
0x1800248f9  mov     rsi, [rsp+28h+arg_10]
0x1800248fe  add     rsp, 20h
0x180024902  pop     rdi
0x180024903  retn
```
