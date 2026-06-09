# FindResourceExA

- ea: `0x18000e180`
- end: `0x18000e269`
- name: `FindResourceExA`
- size: `233`
- prototype: `HRSRC __stdcall(HMODULE hModule, LPCSTR lpType, LPCSTR lpName, WORD wLanguage)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e160`

## callees

- `0x18000e180`
- `0x18000e270`
- `0x18000f920`
- `0x18007a840`

## import_xrefs

- `ntdll!LdrFindResource_U` at `0x18000e1fe`
- `ntdll!LdrFindResource_U` at `0x18000e1fe`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000e22b`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000e236`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18007acde`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18007ace8`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000e22b`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000e236`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18007acde`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18007ace8`

## pseudocode

```c
HRSRC __stdcall FindResourceExA(HMODULE hModule, LPCSTR lpType, LPCSTR lpName, WORD wLanguage)
{
  ULONG_PTR v4; // rdi
  NTSTATUS Resource_U; // ebx
  PIMAGE_RESOURCE_DATA_ENTRY ResourceDataEntry; // [rsp+28h] [rbp-40h] BYREF
  _LDR_RESOURCE_INFO ResourceInfo; // [rsp+30h] [rbp-38h] BYREF

  v4 = wLanguage;
  ResourceDataEntry = 0;
  *(_OWORD *)&ResourceInfo.Type = 0;
  ResourceInfo.Type = BaseDllMapResourceIdA(lpType);
  if ( ResourceInfo.Type == -1 || (ResourceInfo.Name = BaseDllMapResourceIdA(lpName), ResourceInfo.Name == -1) )
  {
    Resource_U = -1073741811;
  }
  else
  {
    ResourceInfo.Language = v4;
    ResourceDataEntry = 0;
    if ( !hModule )
      hModule = (HMODULE)NtCurrentPeb()->ImageBaseAddress;
    Resource_U = LdrFindResource_U(hModule, &ResourceInfo, 3u, &ResourceDataEntry);
  }
  BaseDllFreeResourceId(ResourceInfo.Type);
  BaseDllFreeResourceId(ResourceInfo.Name);
  if ( Resource_U >= 0 )
    return (HRSRC)ResourceDataEntry;
  BaseSetLastNTError((unsigned int)Resource_U);
  return 0;
}

```

## disassembly

```asm
0x18000e180  push    rbx
0x18000e182  push    rsi
0x18000e183  push    rdi
0x18000e184  sub     rsp, 50h
0x18000e188  mov     rax, cs:__security_cookie
0x18000e18f  xor     rax, rsp
0x18000e192  mov     [rsp+68h+var_20], rax
0x18000e197  movzx   edi, r9w
0x18000e19b  mov     rsi, r8
0x18000e19e  mov     rbx, rcx
0x18000e1a1  mov     [rsp+68h+ResourceDataEntry], 0
0x18000e1aa  xorps   xmm0, xmm0
0x18000e1ad  movups  xmmword ptr [rsp+68h+ResourceInfo.Type], xmm0
0x18000e1b2  mov     rcx, rdx; SourceString
0x18000e1b5  call    BaseDllMapResourceIdA
0x18000e1ba  mov     [rsp+68h+ResourceInfo.Type], rax
0x18000e1bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e1c3  jz      short loc_18000E20C
0x18000e1c5  mov     rcx, rsi; SourceString
0x18000e1c8  call    BaseDllMapResourceIdA
0x18000e1cd  mov     [rsp+68h+ResourceInfo.Name], rax
0x18000e1d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e1d6  jz      short loc_18000E20C
0x18000e1d8  mov     [rsp+68h+ResourceInfo.Language], rdi
0x18000e1dd  mov     [rsp+68h+ResourceDataEntry], 0
0x18000e1e6  test    rbx, rbx
0x18000e1e9  jz      short loc_18000E217
0x18000e1eb  lea     r9, [rsp+68h+ResourceDataEntry]; ResourceDataEntry
0x18000e1f0  mov     r8d, 3; Level
0x18000e1f6  lea     rdx, [rsp+68h+ResourceInfo]; ResourceInfo
0x18000e1fb  mov     rcx, rbx; BaseAddress
0x18000e1fe  call    cs:__imp_LdrFindResource_U
0x18000e204  mov     ebx, eax
0x18000e206  mov     [rsp+68h+var_48], eax
0x18000e20a  jmp     short loc_18000E226
0x18000e20c  mov     ebx, 0C000000Dh
0x18000e211  mov     [rsp+68h+var_48], ebx
0x18000e215  jmp     short loc_18000E226
0x18000e217  mov     rax, gs:60h
0x18000e220  mov     rbx, [rax+10h]
0x18000e224  jmp     short loc_18000E1EB
0x18000e226  mov     rcx, [rsp+68h+ResourceInfo.Type]
0x18000e22b  call    cs:__imp_BaseDllFreeResourceId
0x18000e231  mov     rcx, [rsp+68h+ResourceInfo.Name]
0x18000e236  call    cs:__imp_BaseDllFreeResourceId
0x18000e23c  jmp     short loc_18000E240
0x18000e23e  mov     ebx, eax
0x18000e240  test    ebx, ebx
0x18000e242  js      short loc_18000E25E
0x18000e244  mov     rax, [rsp+68h+ResourceDataEntry]
0x18000e249  mov     rcx, [rsp+68h+var_20]
0x18000e24e  xor     rcx, rsp; StackCookie
0x18000e251  call    __security_check_cookie
0x18000e256  add     rsp, 50h
0x18000e25a  pop     rdi
0x18000e25b  pop     rsi
0x18000e25c  pop     rbx
0x18000e25d  retn
0x18000e25e  mov     ecx, ebx
0x18000e260  call    BaseSetLastNTError
0x18000e265  xor     eax, eax
0x18000e267  jmp     short loc_18000E249
0x18007acd1  push    rbp
0x18007acd3  sub     rsp, 20h
0x18007acd7  mov     rbp, rdx
0x18007acda  mov     rcx, [rbp+30h]
0x18007acde  call    cs:__imp_BaseDllFreeResourceId
0x18007ace4  mov     rcx, [rbp+38h]
0x18007ace8  call    cs:__imp_BaseDllFreeResourceId
0x18007acee  nop
0x18007acef  add     rsp, 20h
0x18007acf3  pop     rbp
0x18007acf4  retn
0x18007acf6  push    rbp
0x18007acf8  sub     rsp, 20h
0x18007acfc  mov     rbp, rdx
0x18007acff  mov     rax, [rcx]
0x18007ad02  xor     ecx, ecx
0x18007ad04  cmp     dword ptr [rax], 0C00000FDh
0x18007ad0a  setnz   cl
0x18007ad0d  mov     eax, ecx
0x18007ad0f  add     rsp, 20h
0x18007ad13  pop     rbp
0x18007ad14  retn
```
