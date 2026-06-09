# DloadMakePermanentImageCommit

- ea: `0x180022218`
- end: `0x1800222dc`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800222e4`

## callees

- `0x180022218`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180022277`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180022277`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180022255`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180022255`

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
0x180022218  mov     rax, rsp
0x18002221b  mov     [rax+8], rbx
0x18002221f  push    rdi
0x180022220  sub     rsp, 80h
0x180022227  xorps   xmm0, xmm0
0x18002222a  xorps   xmm1, xmm1
0x18002222d  mov     rdi, rdx
0x180022230  mov     r8d, 30h ; '0'; dwLength
0x180022236  lea     rdx, [rax-68h]; lpBuffer
0x18002223a  mov     rbx, rcx
0x18002223d  movups  xmmword ptr [rax-68h], xmm0
0x180022241  movups  xmmword ptr [rax-58h], xmm0
0x180022245  movups  xmmword ptr [rax-48h], xmm0
0x180022249  movups  xmmword ptr [rax-38h], xmm1
0x18002224d  movups  xmmword ptr [rax-28h], xmm1
0x180022251  movups  xmmword ptr [rax-18h], xmm1
0x180022255  call    cs:__imp_VirtualQuery
0x18002225c  nop     dword ptr [rax+rax+00h]
0x180022261  test    rax, rax
0x180022264  jnz     short loc_18002226B
0x180022266  lea     ecx, [rax+19h]
0x180022269  int     29h; Win8: RtlFailFast(ecx)
0x18002226b  test    [rsp+88h+var_44], 44h
0x180022270  jz      short loc_1800222CA
0x180022272  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180022277  call    cs:__imp_GetSystemInfo
0x18002227e  nop     dword ptr [rax+rax+00h]
0x180022283  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180022288  xor     edx, edx
0x18002228a  mov     eax, edi
0x18002228c  mov     r8d, r9d
0x18002228f  neg     r8
0x180022292  and     r8, rbx
0x180022295  lea     ecx, [r9-1]
0x180022299  and     eax, ecx
0x18002229b  and     ebx, ecx
0x18002229d  add     eax, ebx
0x18002229f  dec     rax
0x1800222a2  add     rax, r9
0x1800222a5  div     r9
0x1800222a8  xor     edx, edx
0x1800222aa  mov     rcx, rax
0x1800222ad  mov     rax, rdi
0x1800222b0  div     r9
0x1800222b3  add     rcx, rax
0x1800222b6  mov     eax, ecx
0x1800222b8  test    ecx, ecx
0x1800222ba  jz      short loc_1800222CA
0x1800222bc  lock or dword ptr [r8], 0
0x1800222c1  add     r8, r9
0x1800222c4  sub     rax, 1
0x1800222c8  jnz     short loc_1800222BC
0x1800222ca  mov     rbx, [rsp+88h+arg_0]
0x1800222d2  add     rsp, 80h
0x1800222d9  pop     rdi
0x1800222da  retn
```
