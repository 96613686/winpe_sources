# ProvisioningPaths::GetWindowsProvisioningFolderPath(void)

- ea: `0x180033334`
- end: `0x1800333c2`
- name: `?GetWindowsProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ`
- size: `142`
- prototype: `const struct expanded_wstring *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180026be4`

## callees

- `0x180002fd4`
- `0x180026454`
- `0x1800332c8`
- `0x180033334`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003338b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003338b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003339a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003339a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct expanded_wstring *ProvisioningPaths::GetWindowsProvisioningFolderPath(void)
{
  struct ProvisioningPaths *Instance; // rsi
  expanded_wstring *v1; // rbx
  expanded_wstring *v2; // rax
  void **v3; // rdi

  Instance = ProvisioningPaths::GetInstance();
  v1 = *(expanded_wstring **)Instance;
  if ( !*(_QWORD *)Instance )
  {
    v2 = (expanded_wstring *)operator new(0x10u);
    if ( v2 )
      v1 = expanded_wstring::expanded_wstring(v2, L"%WINDIR%\\Provisioning\\");
    else
      v1 = 0;
    v3 = *(void ***)Instance;
    if ( v1 == *(expanded_wstring **)Instance )
    {
      return *(const struct expanded_wstring **)Instance;
    }
    else
    {
      if ( v3 )
      {
        operator delete[](*v3);
        operator delete(v3);
      }
      *(_QWORD *)Instance = v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180033334  mov     [rsp+arg_8], rbx
0x180033339  mov     [rsp+arg_10], rsi
0x18003333e  push    rdi
0x18003333f  sub     rsp, 20h
0x180033343  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x180033348  mov     rsi, rax
0x18003334b  mov     rbx, [rax]
0x18003334e  test    rbx, rbx
0x180033351  jnz     short loc_1800333AE
0x180033353  lea     ecx, [rbx+10h]; Size
0x180033356  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003335b  mov     [rsp+28h+arg_0], rax
0x180033360  test    rax, rax
0x180033363  jz      short loc_180033379
0x180033365  lea     rdx, ?gc_szWindowsProvisioningFolderPath@@3QBGB; "%WINDIR%\\Provisioning\\"
0x18003336c  mov     rcx, rax; this
0x18003336f  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180033374  mov     rbx, rax
0x180033377  jmp     short loc_18003337B
0x180033379  xor     ebx, ebx
0x18003337b  mov     rdi, [rsi]
0x18003337e  cmp     rbx, rdi
0x180033381  jz      short loc_1800333AB
0x180033383  test    rdi, rdi
0x180033386  jz      short loc_1800333A6
0x180033388  mov     rcx, [rdi]
0x18003338b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033392  nop     dword ptr [rax+rax+00h]
0x180033397  mov     rcx, rdi
0x18003339a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800333a1  nop     dword ptr [rax+rax+00h]
0x1800333a6  mov     [rsi], rbx
0x1800333a9  jmp     short loc_1800333AE
0x1800333ab  mov     rbx, rdi
0x1800333ae  mov     rax, rbx
0x1800333b1  mov     rbx, [rsp+28h+arg_8]
0x1800333b6  mov     rsi, [rsp+28h+arg_10]
0x1800333bb  add     rsp, 20h
0x1800333bf  pop     rdi
0x1800333c0  retn
```
