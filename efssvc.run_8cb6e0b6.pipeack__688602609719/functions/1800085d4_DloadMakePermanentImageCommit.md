# DloadMakePermanentImageCommit

- ea: `0x1800085d4`
- end: `0x180008698`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800086a0`

## callees

- `0x1800085d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180008633`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180008633`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180008611`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180008611`

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
0x1800085d4  mov     rax, rsp
0x1800085d7  mov     [rax+8], rbx
0x1800085db  push    rdi
0x1800085dc  sub     rsp, 80h
0x1800085e3  xorps   xmm0, xmm0
0x1800085e6  xorps   xmm1, xmm1
0x1800085e9  mov     rdi, rdx
0x1800085ec  mov     r8d, 30h ; '0'; dwLength
0x1800085f2  lea     rdx, [rax-68h]; lpBuffer
0x1800085f6  mov     rbx, rcx
0x1800085f9  movups  xmmword ptr [rax-68h], xmm0
0x1800085fd  movups  xmmword ptr [rax-58h], xmm0
0x180008601  movups  xmmword ptr [rax-48h], xmm0
0x180008605  movups  xmmword ptr [rax-38h], xmm1
0x180008609  movups  xmmword ptr [rax-28h], xmm1
0x18000860d  movups  xmmword ptr [rax-18h], xmm1
0x180008611  call    cs:__imp_VirtualQuery
0x180008618  nop     dword ptr [rax+rax+00h]
0x18000861d  test    rax, rax
0x180008620  jnz     short loc_180008627
0x180008622  lea     ecx, [rax+19h]
0x180008625  int     29h; Win8: RtlFailFast(ecx)
0x180008627  test    [rsp+88h+var_44], 44h
0x18000862c  jz      short loc_180008686
0x18000862e  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180008633  call    cs:__imp_GetSystemInfo
0x18000863a  nop     dword ptr [rax+rax+00h]
0x18000863f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180008644  xor     edx, edx
0x180008646  mov     eax, edi
0x180008648  mov     r8d, r9d
0x18000864b  neg     r8
0x18000864e  and     r8, rbx
0x180008651  lea     ecx, [r9-1]
0x180008655  and     eax, ecx
0x180008657  and     ebx, ecx
0x180008659  add     eax, ebx
0x18000865b  dec     rax
0x18000865e  add     rax, r9
0x180008661  div     r9
0x180008664  xor     edx, edx
0x180008666  mov     rcx, rax
0x180008669  mov     rax, rdi
0x18000866c  div     r9
0x18000866f  add     rcx, rax
0x180008672  mov     eax, ecx
0x180008674  test    ecx, ecx
0x180008676  jz      short loc_180008686
0x180008678  lock or dword ptr [r8], 0
0x18000867d  add     r8, r9
0x180008680  sub     rax, 1
0x180008684  jnz     short loc_180008678
0x180008686  mov     rbx, [rsp+88h+arg_0]
0x18000868e  add     rsp, 80h
0x180008695  pop     rdi
0x180008696  retn
```
