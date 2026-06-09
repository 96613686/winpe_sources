# ProvisioningPaths::GetWindowsProvisioningFolderPath(void)

- ea: `0x18003836c`
- end: `0x1800383ed`
- name: `?GetWindowsProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ`
- size: `129`
- prototype: `const struct expanded_wstring *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800172e8`
- `0x18003f334`

## callees

- `0x1800021b4`
- `0x18000fcc4`
- `0x180038278`
- `0x18003836c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800383cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800383cc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800383c3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800383c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x18003836c  mov     [rsp+arg_8], rbx
0x180038371  mov     [rsp+arg_10], rsi
0x180038376  push    rdi
0x180038377  sub     rsp, 20h
0x18003837b  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x180038380  mov     rsi, rax
0x180038383  mov     rbx, [rax]
0x180038386  test    rbx, rbx
0x180038389  jnz     short loc_1800383DA
0x18003838b  lea     ecx, [rbx+10h]; Size
0x18003838e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038393  mov     [rsp+28h+arg_0], rax
0x180038398  test    rax, rax
0x18003839b  jz      short loc_1800383B1
0x18003839d  lea     rdx, ?gc_szWindowsProvisioningFolderPath@@3QBGB; "%WINDIR%\\Provisioning\\"
0x1800383a4  mov     rcx, rax; this
0x1800383a7  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800383ac  mov     rbx, rax
0x1800383af  jmp     short loc_1800383B3
0x1800383b1  xor     ebx, ebx
0x1800383b3  mov     rdi, [rsi]
0x1800383b6  cmp     rbx, rdi
0x1800383b9  jz      short loc_1800383D7
0x1800383bb  test    rdi, rdi
0x1800383be  jz      short loc_1800383D2
0x1800383c0  mov     rcx, [rdi]
0x1800383c3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800383c9  mov     rcx, rdi
0x1800383cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800383d2  mov     [rsi], rbx
0x1800383d5  jmp     short loc_1800383DA
0x1800383d7  mov     rbx, rdi
0x1800383da  mov     rax, rbx
0x1800383dd  mov     rbx, [rsp+28h+arg_8]
0x1800383e2  mov     rsi, [rsp+28h+arg_10]
0x1800383e7  add     rsp, 20h
0x1800383eb  pop     rdi
0x1800383ec  retn
```
