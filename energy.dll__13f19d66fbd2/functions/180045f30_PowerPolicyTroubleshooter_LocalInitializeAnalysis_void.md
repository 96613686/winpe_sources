# PowerPolicyTroubleshooter::LocalInitializeAnalysis(void)

- ea: `0x180045f30`
- end: `0x18004605d`
- name: `?LocalInitializeAnalysis@PowerPolicyTroubleshooter@@MEAAXXZ`
- size: `301`
- prototype: `void __fastcall(PowerPolicyTroubleshooter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005038`
- `0x180035e30`
- `0x180045f30`
- `0x1800460d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004602a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004602a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046039`

## pseudocode

```c
void __fastcall PowerPolicyTroubleshooter::LocalInitializeAnalysis(PowerPolicyTroubleshooter *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  PpmSetting *v4; // rcx
  _QWORD *v5; // rbx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  *((_QWORD *)this + 65) = 0;
  *((_WORD *)this + 226) = 0;
  *((_QWORD *)this + 51) = 0;
  v2 = *((_QWORD *)this + 58);
  v3 = *((_QWORD *)this + 57);
  dwDisposition = 0;
  hKey = 0;
  if ( v3 != v2 )
  {
    std::_Destroy_range<std::allocator<PpmProfile>>(v3, v2);
    *((_QWORD *)this + 58) = *((_QWORD *)this + 57);
  }
  v4 = (PpmSetting *)*((_QWORD *)this + 60);
  if ( v4 != *((PpmSetting **)this + 61) )
  {
    std::_Destroy_range<std::allocator<PpmSetting>>(v4);
    *((_QWORD *)this + 61) = *((_QWORD *)this + 60);
  }
  v5 = (_QWORD *)*((_QWORD *)this + 63);
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Domain>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,Domain>,void *>>>(
    (char *)this + 504,
    (char *)this + 504,
    v5[1]);
  v5[1] = v5;
  *v5 = v5;
  v5[2] = v5;
  *((_QWORD *)this + 64) = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Power\\Profile\\BootCheck",
          0,
          0,
          1u,
          0x20019u,
          0,
          &hKey,
          &dwDisposition) )
  {
    RegCloseKey(hKey);
    if ( (dwDisposition & 1) != 0 )
      *((_BYTE *)this + 452) = 1;
  }
}

```

## disassembly

```asm
0x180045f30  mov     rax, rsp
0x180045f33  mov     [rax+18h], rbx
0x180045f37  mov     [rax+20h], rsi
0x180045f3b  push    rdi
0x180045f3c  sub     rsp, 50h
0x180045f40  mov     qword ptr [rcx+208h], 0
0x180045f4b  mov     rsi, rcx
0x180045f4e  mov     word ptr [rcx+1C4h], 0
0x180045f57  mov     qword ptr [rcx+198h], 0
0x180045f62  mov     rdx, [rcx+1D0h]
0x180045f69  mov     rcx, [rcx+1C8h]
0x180045f70  mov     dword ptr [rax+8], 0
0x180045f77  mov     qword ptr [rax+10h], 0
0x180045f7f  cmp     rcx, rdx
0x180045f82  jz      short loc_180045F97
0x180045f84  call    ??$_Destroy_range@V?$allocator@VPpmProfile@@@std@@@std@@YAXPEAVPpmProfile@@QEAV1@AEAV?$allocator@VPpmProfile@@@0@@Z; std::_Destroy_range<std::allocator<PpmProfile>>(PpmProfile *,PpmProfile * const,std::allocator<PpmProfile> &)
0x180045f89  mov     rax, [rsi+1C8h]
0x180045f90  mov     [rsi+1D0h], rax
0x180045f97  mov     rdx, [rsi+1E8h]
0x180045f9e  mov     rcx, [rsi+1E0h]; this
0x180045fa5  cmp     rcx, rdx
0x180045fa8  jz      short loc_180045FBD
0x180045faa  call    ??$_Destroy_range@V?$allocator@VPpmSetting@@@std@@@std@@YAXPEAVPpmSetting@@QEAV1@AEAV?$allocator@VPpmSetting@@@0@@Z; std::_Destroy_range<std::allocator<PpmSetting>>(PpmSetting *,PpmSetting * const,std::allocator<PpmSetting> &)
0x180045faf  mov     rax, [rsi+1E0h]
0x180045fb6  mov     [rsi+1E8h], rax
0x180045fbd  lea     rdi, [rsi+1F8h]
0x180045fc4  mov     rbx, [rdi]
0x180045fc7  mov     rdx, rdi
0x180045fca  mov     rcx, rdi
0x180045fcd  mov     r8, [rbx+8]
0x180045fd1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKVDomain@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVDomain@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKVDomain@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKVDomain@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Domain>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,Domain>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,Domain>,void *>> &,std::_Tree_node<std::pair<ulong const,Domain>,void *> *)
0x180045fd6  lea     rax, [rsp+58h+dwDisposition]
0x180045fdb  mov     [rbx+8], rbx
0x180045fdf  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180045fe4  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pow"...
0x180045feb  lea     rax, [rsp+58h+hKey]
0x180045ff0  mov     [rbx], rbx
0x180045ff3  mov     [rsp+58h+phkResult], rax; phkResult
0x180045ff8  xor     r9d, r9d; lpClass
0x180045ffb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180046004  xor     r8d, r8d; Reserved
0x180046007  mov     [rbx+10h], rbx
0x18004600b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046012  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18004601a  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180046022  mov     qword ptr [rdi+8], 0
0x18004602a  call    cs:__imp_RegCreateKeyExW
0x180046030  test    eax, eax
0x180046032  jnz     short loc_18004604D
0x180046034  mov     rcx, [rsp+58h+hKey]; hKey
0x180046039  call    cs:__imp_RegCloseKey
0x18004603f  test    byte ptr [rsp+58h+dwDisposition], 1
0x180046044  jz      short loc_18004604D
0x180046046  mov     byte ptr [rsi+1C4h], 1
0x18004604d  mov     rbx, [rsp+58h+arg_10]
0x180046052  mov     rsi, [rsp+58h+arg_18]
0x180046057  add     rsp, 50h
0x18004605b  pop     rdi
0x18004605c  retn
```
