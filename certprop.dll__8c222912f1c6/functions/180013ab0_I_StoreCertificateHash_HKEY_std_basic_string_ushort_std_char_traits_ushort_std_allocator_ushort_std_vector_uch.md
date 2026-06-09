# I_StoreCertificateHash(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<uchar,std::allocator<uchar>>)

- ea: `0x180013ab0`
- end: `0x180013b0b`
- name: `?I_StoreCertificateHash@@YAKPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@3@@Z`
- size: `91`
- prototype: `__int64 __fastcall(HKEY hKey, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013b14`
- `0x18001466c`

## callees

- `0x180008554`
- `0x180013ab0`
- `0x180013dc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ae9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ae9`

## pseudocode

```c
__int64 __fastcall I_StoreCertificateHash(HKEY hKey, const WCHAR *a2, __int64 a3)
{
  const WCHAR *v4; // rdi
  unsigned int v5; // ebx

  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v5 = RegSetValueExW(hKey, a2, 0, 3u, *(const BYTE **)a3, *(_DWORD *)(a3 + 8) - *(_QWORD *)a3);
  std::wstring::_Tidy_deallocate(v4);
  std::vector<unsigned char>::_Tidy(a3);
  return v5;
}

```

## disassembly

```asm
0x180013ab0  push    rbx
0x180013ab2  push    rsi
0x180013ab3  push    rdi
0x180013ab4  sub     rsp, 30h
0x180013ab8  mov     eax, [r8+8]
0x180013abc  mov     r10, rcx
0x180013abf  mov     rcx, [r8]
0x180013ac2  mov     rsi, r8
0x180013ac5  sub     eax, ecx
0x180013ac7  mov     rdi, rdx
0x180013aca  cmp     qword ptr [rdx+18h], 7
0x180013acf  jbe     short loc_180013AD4
0x180013ad1  mov     rdx, [rdx]; lpValueName
0x180013ad4  mov     [rsp+48h+cbData], eax; cbData
0x180013ad8  mov     r9d, 3; dwType
0x180013ade  mov     [rsp+48h+lpData], rcx; lpData
0x180013ae3  xor     r8d, r8d; Reserved
0x180013ae6  mov     rcx, r10; hKey
0x180013ae9  call    cs:__imp_RegSetValueExW
0x180013aef  mov     rcx, rdi
0x180013af2  mov     ebx, eax
0x180013af4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013af9  mov     rcx, rsi
0x180013afc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180013b01  mov     eax, ebx
0x180013b03  add     rsp, 30h
0x180013b07  pop     rdi
0x180013b08  pop     rsi
0x180013b09  pop     rbx
0x180013b0a  retn
```
