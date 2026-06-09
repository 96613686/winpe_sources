# ProvisioningPaths::GetCosaFolderPath(void)

- ea: `0x18003804c`
- end: `0x1800380d0`
- name: `?GetCosaFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ`
- size: `132`
- prototype: `const struct expanded_wstring *(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001a4a0`
- `0x18001a6fc`
- `0x1800380d8`
- `0x1800381a8`

## callees

- `0x1800021b4`
- `0x18000fcc4`
- `0x18003804c`
- `0x180038278`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800380ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800380ae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800380a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800380a5`

## pseudocode

```c
const struct expanded_wstring *ProvisioningPaths::GetCosaFolderPath(void)
{
  struct ProvisioningPaths *Instance; // rsi
  expanded_wstring *v1; // rbx
  expanded_wstring *v2; // rax
  void **v3; // rdi

  Instance = ProvisioningPaths::GetInstance();
  v1 = (expanded_wstring *)*((_QWORD *)Instance + 2);
  if ( !v1 )
  {
    v2 = (expanded_wstring *)operator new(0x10u);
    if ( v2 )
      v1 = expanded_wstring::expanded_wstring(v2, L"%WINDIR%\\Provisioning\\COSA");
    else
      v1 = 0;
    v3 = (void **)*((_QWORD *)Instance + 2);
    if ( v1 == (expanded_wstring *)v3 )
    {
      return (const struct expanded_wstring *)*((_QWORD *)Instance + 2);
    }
    else
    {
      if ( v3 )
      {
        operator delete[](*v3);
        operator delete(v3);
      }
      *((_QWORD *)Instance + 2) = v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18003804c  mov     [rsp+arg_8], rbx
0x180038051  mov     [rsp+arg_10], rsi
0x180038056  push    rdi
0x180038057  sub     rsp, 20h
0x18003805b  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x180038060  mov     rsi, rax
0x180038063  mov     rbx, [rax+10h]
0x180038067  test    rbx, rbx
0x18003806a  jnz     short loc_1800380BD
0x18003806c  lea     ecx, [rbx+10h]; Size
0x18003806f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038074  mov     [rsp+28h+arg_0], rax
0x180038079  test    rax, rax
0x18003807c  jz      short loc_180038092
0x18003807e  lea     rdx, ?gc_szCosaFolderPath@@3QBGB; "%WINDIR%\\Provisioning\\COSA"
0x180038085  mov     rcx, rax; this
0x180038088  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x18003808d  mov     rbx, rax
0x180038090  jmp     short loc_180038094
0x180038092  xor     ebx, ebx
0x180038094  mov     rdi, [rsi+10h]
0x180038098  cmp     rbx, rdi
0x18003809b  jz      short loc_1800380BA
0x18003809d  test    rdi, rdi
0x1800380a0  jz      short loc_1800380B4
0x1800380a2  mov     rcx, [rdi]
0x1800380a5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800380ab  mov     rcx, rdi
0x1800380ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800380b4  mov     [rsi+10h], rbx
0x1800380b8  jmp     short loc_1800380BD
0x1800380ba  mov     rbx, rdi
0x1800380bd  mov     rax, rbx
0x1800380c0  mov     rbx, [rsp+28h+arg_8]
0x1800380c5  mov     rsi, [rsp+28h+arg_10]
0x1800380ca  add     rsp, 20h
0x1800380ce  pop     rdi
0x1800380cf  retn
```
