# CHeapFactory::Init(void)

- ea: `0x180006c58`
- end: `0x180006cfb`
- name: `?Init@CHeapFactory@@AEAAXXZ`
- size: `163`
- prototype: `void __fastcall(CHeapFactory *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011f0`

## callees

- `0x180006c58`
- `0x180019494`
- `0x180019594`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cdd`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180006c7f`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180006c7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180006c72`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180006c72`

## pseudocode

```c
void __fastcall CHeapFactory::Init(CHeapFactory *this)
{
  HANDLE v1; // rax
  DWORD LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  struct _SYSTEM_INFO v5; // [rsp+20h] [rbp-38h] BYREF

  memset(&v5, 0, sizeof(v5));
  GetSystemInfo(&v5);
  v1 = HeapCreate(0, 0, 0);
  hHeap = v1;
  if ( v1 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_cdac69d58e113e0c8ccf6cdb6e0ba022_Traceguids, v1);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v3, v4, LastError);
  }
}

```

## disassembly

```asm
0x180006c58  mov     rax, rsp
0x180006c5b  sub     rsp, 58h
0x180006c5f  xorps   xmm0, xmm0
0x180006c62  lea     rcx, [rax-38h]; lpSystemInfo
0x180006c66  movups  xmmword ptr [rax-38h], xmm0
0x180006c6a  movups  xmmword ptr [rax-28h], xmm0
0x180006c6e  movups  xmmword ptr [rax-18h], xmm0
0x180006c72  call    cs:__imp_GetSystemInfo
0x180006c78  xor     r8d, r8d; dwMaximumSize
0x180006c7b  xor     edx, edx; dwInitialSize
0x180006c7d  xor     ecx, ecx; flOptions
0x180006c7f  call    cs:__imp_HeapCreate
0x180006c85  mov     cs:hHeap, rax
0x180006c8c  test    rax, rax
0x180006c8f  jz      short loc_180006CC4
0x180006c91  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c98  lea     rdx, WPP_GLOBAL_Control
0x180006c9f  cmp     rcx, rdx
0x180006ca2  jz      short loc_180006CF6
0x180006ca4  cmp     byte ptr [rcx+19h], 5
0x180006ca8  jb      short loc_180006CF6
0x180006caa  mov     rcx, [rcx+10h]
0x180006cae  lea     r8, WPP_cdac69d58e113e0c8ccf6cdb6e0ba022_Traceguids
0x180006cb5  mov     edx, 10h
0x180006cba  mov     r9, rax
0x180006cbd  call    WPP_SF_q
0x180006cc2  jmp     short loc_180006CF6
0x180006cc4  mov     rax, cs:WPP_GLOBAL_Control
0x180006ccb  lea     rdx, WPP_GLOBAL_Control
0x180006cd2  cmp     rax, rdx
0x180006cd5  jz      short loc_180006CF6
0x180006cd7  cmp     byte ptr [rax+19h], 2
0x180006cdb  jb      short loc_180006CF6
0x180006cdd  call    cs:__imp_GetLastError
0x180006ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cea  mov     r9d, eax
0x180006ced  mov     rcx, [rcx+10h]
0x180006cf1  call    WPP_SF_D
0x180006cf6  add     rsp, 58h
0x180006cfa  retn
```
