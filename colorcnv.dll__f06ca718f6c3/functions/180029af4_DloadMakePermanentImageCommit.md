# DloadMakePermanentImageCommit

- ea: `0x180029af4`
- end: `0x180029bab`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180029bb4`

## callees

- `0x180029af4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180029b4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180029b4d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180029b31`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180029b31`

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
0x180029af4  mov     rax, rsp
0x180029af7  mov     [rax+8], rbx
0x180029afb  push    rdi
0x180029afc  sub     rsp, 80h
0x180029b03  xorps   xmm0, xmm0
0x180029b06  xorps   xmm1, xmm1
0x180029b09  mov     rdi, rdx
0x180029b0c  mov     r8d, 30h ; '0'; dwLength
0x180029b12  lea     rdx, [rax-68h]; lpBuffer
0x180029b16  mov     rbx, rcx
0x180029b19  movups  xmmword ptr [rax-68h], xmm0
0x180029b1d  movups  xmmword ptr [rax-58h], xmm0
0x180029b21  movups  xmmword ptr [rax-48h], xmm0
0x180029b25  movups  xmmword ptr [rax-38h], xmm1
0x180029b29  movups  xmmword ptr [rax-28h], xmm1
0x180029b2d  movups  xmmword ptr [rax-18h], xmm1
0x180029b31  call    cs:__imp_VirtualQuery
0x180029b37  test    rax, rax
0x180029b3a  jnz     short loc_180029B41
0x180029b3c  lea     ecx, [rax+19h]
0x180029b3f  int     29h; Win8: RtlFailFast(ecx)
0x180029b41  test    [rsp+88h+var_44], 44h
0x180029b46  jz      short loc_180029B9A
0x180029b48  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180029b4d  call    cs:__imp_GetSystemInfo
0x180029b53  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180029b58  xor     edx, edx
0x180029b5a  mov     eax, edi
0x180029b5c  mov     r8d, r9d
0x180029b5f  neg     r8
0x180029b62  and     r8, rbx
0x180029b65  lea     ecx, [r9-1]
0x180029b69  and     eax, ecx
0x180029b6b  and     ebx, ecx
0x180029b6d  add     eax, ebx
0x180029b6f  dec     rax
0x180029b72  add     rax, r9
0x180029b75  div     r9
0x180029b78  xor     edx, edx
0x180029b7a  mov     rcx, rax
0x180029b7d  mov     rax, rdi
0x180029b80  div     r9
0x180029b83  add     rcx, rax
0x180029b86  mov     eax, ecx
0x180029b88  test    ecx, ecx
0x180029b8a  jz      short loc_180029B9A
0x180029b8c  lock or dword ptr [r8], 0
0x180029b91  add     r8, r9
0x180029b94  sub     rax, 1
0x180029b98  jnz     short loc_180029B8C
0x180029b9a  mov     rbx, [rsp+88h+arg_0]
0x180029ba2  add     rsp, 80h
0x180029ba9  pop     rdi
0x180029baa  retn
```
