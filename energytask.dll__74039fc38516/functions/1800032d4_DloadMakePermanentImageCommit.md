# DloadMakePermanentImageCommit

- ea: `0x1800032d4`
- end: `0x18000338b`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: `SIZE_T __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003394`

## callees

- `0x1800032d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000332d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000332d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180003311`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180003311`

## pseudocode

```c
SIZE_T __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T result; // rax
  __int64 dwPageSize; // r9
  volatile signed __int32 *v6; // r8
  unsigned __int64 v7; // rcx
  struct _MEMORY_BASIC_INFORMATION v8; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  memset(&v8, 0, sizeof(v8));
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  result = VirtualQuery((LPCVOID)a1, &v8, 0x30u);
  if ( !result )
    __fastfail(0x19u);
  if ( (v8.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v6 = (volatile signed __int32 *)(a1 & -(__int64)SystemInfo.dwPageSize);
    v7 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((SystemInfo.dwPageSize - 1) & (unsigned int)a1)
                           + ((SystemInfo.dwPageSize - 1) & (unsigned int)a2))
        - 1)
       / SystemInfo.dwPageSize;
    for ( result = (unsigned int)v7; result; --result )
    {
      _InterlockedOr(v6, 0);
      v6 = (volatile signed __int32 *)((char *)v6 + dwPageSize);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800032d4  mov     rax, rsp
0x1800032d7  mov     [rax+8], rbx
0x1800032db  push    rdi
0x1800032dc  sub     rsp, 80h
0x1800032e3  xorps   xmm0, xmm0
0x1800032e6  xorps   xmm1, xmm1
0x1800032e9  mov     rdi, rdx
0x1800032ec  mov     r8d, 30h ; '0'; dwLength
0x1800032f2  lea     rdx, [rax-68h]; lpBuffer
0x1800032f6  mov     rbx, rcx
0x1800032f9  movups  xmmword ptr [rax-68h], xmm0
0x1800032fd  movups  xmmword ptr [rax-58h], xmm0
0x180003301  movups  xmmword ptr [rax-48h], xmm0
0x180003305  movups  xmmword ptr [rax-38h], xmm1
0x180003309  movups  xmmword ptr [rax-28h], xmm1
0x18000330d  movups  xmmword ptr [rax-18h], xmm1
0x180003311  call    cs:__imp_VirtualQuery
0x180003317  test    rax, rax
0x18000331a  jnz     short loc_180003321
0x18000331c  lea     ecx, [rax+19h]
0x18000331f  int     29h; Win8: RtlFailFast(ecx)
0x180003321  test    [rsp+88h+var_44], 44h
0x180003326  jz      short loc_18000337A
0x180003328  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18000332d  call    cs:__imp_GetSystemInfo
0x180003333  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180003338  xor     edx, edx
0x18000333a  mov     eax, edi
0x18000333c  mov     r8d, r9d
0x18000333f  neg     r8
0x180003342  and     r8, rbx
0x180003345  lea     ecx, [r9-1]
0x180003349  and     eax, ecx
0x18000334b  and     ebx, ecx
0x18000334d  add     eax, ebx
0x18000334f  dec     rax
0x180003352  add     rax, r9
0x180003355  div     r9
0x180003358  xor     edx, edx
0x18000335a  mov     rcx, rax
0x18000335d  mov     rax, rdi
0x180003360  div     r9
0x180003363  add     rcx, rax
0x180003366  mov     eax, ecx
0x180003368  test    ecx, ecx
0x18000336a  jz      short loc_18000337A
0x18000336c  lock or dword ptr [r8], 0
0x180003371  add     r8, r9
0x180003374  sub     rax, 1
0x180003378  jnz     short loc_18000336C
0x18000337a  mov     rbx, [rsp+88h+arg_0]
0x180003382  add     rsp, 80h
0x180003389  pop     rdi
0x18000338a  retn
```
