# FindResourceExA

- ea: `0x18000b370`
- end: `0x18000b46c`
- name: `FindResourceExA`
- size: `252`
- prototype: `HRSRC __stdcall(HMODULE hModule, LPCSTR lpType, LPCSTR lpName, WORD wLanguage)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b350`

## callees

- `0x18000b370`
- `0x18000b474`
- `0x18000ccf0`
- `0x1800827c0`

## import_xrefs

- `ntdll!LdrFindResource_U` at `0x18000b3ee`
- `ntdll!LdrFindResource_U` at `0x18000b3ee`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000b421`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000b432`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18008292a`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18008293a`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000b421`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18000b432`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18008292a`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18008293a`

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
0x18000b370  push    rbx
0x18000b372  push    rsi
0x18000b373  push    rdi
0x18000b374  sub     rsp, 50h
0x18000b378  mov     rax, cs:__security_cookie
0x18000b37f  xor     rax, rsp
0x18000b382  mov     [rsp+68h+var_20], rax
0x18000b387  movzx   edi, r9w
0x18000b38b  mov     rsi, r8
0x18000b38e  mov     rbx, rcx
0x18000b391  mov     [rsp+68h+ResourceDataEntry], 0
0x18000b39a  xorps   xmm0, xmm0
0x18000b39d  movups  xmmword ptr [rsp+68h+ResourceInfo.Type], xmm0
0x18000b3a2  mov     rcx, rdx; SourceString
0x18000b3a5  call    BaseDllMapResourceIdA
0x18000b3aa  mov     [rsp+68h+ResourceInfo.Type], rax
0x18000b3af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b3b3  jz      short loc_18000B402
0x18000b3b5  mov     rcx, rsi; SourceString
0x18000b3b8  call    BaseDllMapResourceIdA
0x18000b3bd  mov     [rsp+68h+ResourceInfo.Name], rax
0x18000b3c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b3c6  jz      short loc_18000B402
0x18000b3c8  mov     [rsp+68h+ResourceInfo.Language], rdi
0x18000b3cd  mov     [rsp+68h+ResourceDataEntry], 0
0x18000b3d6  test    rbx, rbx
0x18000b3d9  jz      short loc_18000B40D
0x18000b3db  lea     r9, [rsp+68h+ResourceDataEntry]; ResourceDataEntry
0x18000b3e0  mov     r8d, 3; Level
0x18000b3e6  lea     rdx, [rsp+68h+ResourceInfo]; ResourceInfo
0x18000b3eb  mov     rcx, rbx; BaseAddress
0x18000b3ee  call    cs:__imp_LdrFindResource_U
0x18000b3f5  nop     dword ptr [rax+rax+00h]
0x18000b3fa  mov     ebx, eax
0x18000b3fc  mov     [rsp+68h+var_48], eax
0x18000b400  jmp     short loc_18000B41C
0x18000b402  mov     ebx, 0C000000Dh
0x18000b407  mov     [rsp+68h+var_48], ebx
0x18000b40b  jmp     short loc_18000B41C
0x18000b40d  mov     rax, gs:60h
0x18000b416  mov     rbx, [rax+10h]
0x18000b41a  jmp     short loc_18000B3DB
0x18000b41c  mov     rcx, [rsp+68h+ResourceInfo.Type]
0x18000b421  call    cs:__imp_BaseDllFreeResourceId
0x18000b428  nop     dword ptr [rax+rax+00h]
0x18000b42d  mov     rcx, [rsp+68h+ResourceInfo.Name]
0x18000b432  call    cs:__imp_BaseDllFreeResourceId
0x18000b439  nop     dword ptr [rax+rax+00h]
0x18000b43e  jmp     short loc_18000B442
0x18000b440  mov     ebx, eax
0x18000b442  test    ebx, ebx
0x18000b444  js      short loc_18000B461
0x18000b446  mov     rax, [rsp+68h+ResourceDataEntry]
0x18000b44b  mov     rcx, [rsp+68h+var_20]
0x18000b450  xor     rcx, rsp; StackCookie
0x18000b453  call    __security_check_cookie
0x18000b458  add     rsp, 50h
0x18000b45c  pop     rdi
0x18000b45d  pop     rsi
0x18000b45e  pop     rbx
0x18000b45f  retn
0x18000b461  mov     ecx, ebx
0x18000b463  call    BaseSetLastNTError
0x18000b468  xor     eax, eax
0x18000b46a  jmp     short loc_18000B44B
0x18008291d  push    rbp
0x18008291f  sub     rsp, 20h
0x180082923  mov     rbp, rdx
0x180082926  mov     rcx, [rbp+30h]
0x18008292a  call    cs:__imp_BaseDllFreeResourceId
0x180082931  nop     dword ptr [rax+rax+00h]
0x180082936  mov     rcx, [rbp+38h]
0x18008293a  call    cs:__imp_BaseDllFreeResourceId
0x180082941  nop     dword ptr [rax+rax+00h]
0x180082946  nop
0x180082947  add     rsp, 20h
0x18008294b  pop     rbp
0x18008294c  retn
0x18008294e  push    rbp
0x180082950  sub     rsp, 20h
0x180082954  mov     rbp, rdx
0x180082957  mov     rax, [rcx]
0x18008295a  xor     ecx, ecx
0x18008295c  cmp     dword ptr [rax], 0C00000FDh
0x180082962  setnz   cl
0x180082965  mov     eax, ecx
0x180082967  add     rsp, 20h
0x18008296b  pop     rbp
0x18008296c  retn
```
