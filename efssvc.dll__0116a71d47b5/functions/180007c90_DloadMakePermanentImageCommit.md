# DloadMakePermanentImageCommit

- ea: `0x180007c90`
- end: `0x180007d47`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: `SIZE_T __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007d50`

## callees

- `0x180007c90`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180007ce9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180007ce9`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180007ccd`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180007ccd`

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
0x180007c90  mov     rax, rsp
0x180007c93  mov     [rax+8], rbx
0x180007c97  push    rdi
0x180007c98  sub     rsp, 80h
0x180007c9f  xorps   xmm0, xmm0
0x180007ca2  xorps   xmm1, xmm1
0x180007ca5  mov     rdi, rdx
0x180007ca8  mov     r8d, 30h ; '0'; dwLength
0x180007cae  lea     rdx, [rax-68h]; lpBuffer
0x180007cb2  mov     rbx, rcx
0x180007cb5  movups  xmmword ptr [rax-68h], xmm0
0x180007cb9  movups  xmmword ptr [rax-58h], xmm0
0x180007cbd  movups  xmmword ptr [rax-48h], xmm0
0x180007cc1  movups  xmmword ptr [rax-38h], xmm1
0x180007cc5  movups  xmmword ptr [rax-28h], xmm1
0x180007cc9  movups  xmmword ptr [rax-18h], xmm1
0x180007ccd  call    cs:__imp_VirtualQuery
0x180007cd3  test    rax, rax
0x180007cd6  jnz     short loc_180007CDD
0x180007cd8  lea     ecx, [rax+19h]
0x180007cdb  int     29h; Win8: RtlFailFast(ecx)
0x180007cdd  test    [rsp+88h+var_44], 44h
0x180007ce2  jz      short loc_180007D36
0x180007ce4  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180007ce9  call    cs:__imp_GetSystemInfo
0x180007cef  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180007cf4  xor     edx, edx
0x180007cf6  mov     eax, edi
0x180007cf8  mov     r8d, r9d
0x180007cfb  neg     r8
0x180007cfe  and     r8, rbx
0x180007d01  lea     ecx, [r9-1]
0x180007d05  and     eax, ecx
0x180007d07  and     ebx, ecx
0x180007d09  add     eax, ebx
0x180007d0b  dec     rax
0x180007d0e  add     rax, r9
0x180007d11  div     r9
0x180007d14  xor     edx, edx
0x180007d16  mov     rcx, rax
0x180007d19  mov     rax, rdi
0x180007d1c  div     r9
0x180007d1f  add     rcx, rax
0x180007d22  mov     eax, ecx
0x180007d24  test    ecx, ecx
0x180007d26  jz      short loc_180007D36
0x180007d28  lock or dword ptr [r8], 0
0x180007d2d  add     r8, r9
0x180007d30  sub     rax, 1
0x180007d34  jnz     short loc_180007D28
0x180007d36  mov     rbx, [rsp+88h+arg_0]
0x180007d3e  add     rsp, 80h
0x180007d45  pop     rdi
0x180007d46  retn
```
