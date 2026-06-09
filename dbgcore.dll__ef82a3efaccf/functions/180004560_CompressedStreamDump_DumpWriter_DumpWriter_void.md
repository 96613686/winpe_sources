# CompressedStreamDump::DumpWriter::~DumpWriter(void)

- ea: `0x180004560`
- end: `0x1800045c5`
- name: `??1DumpWriter@CompressedStreamDump@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CompressedStreamDump::DumpWriter *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000450c`
- `0x18000d6f4`
- `0x18001e8f0`

## callees

- `0x180004560`
- `0x18000f34c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800045a9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800045a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000458a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000458a`

## pseudocode

```c
void __fastcall CompressedStreamDump::DumpWriter::~DumpWriter(CompressedStreamDump::DumpWriter *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  char *v5; // rcx
  void *v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  v5 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    VirtualFree(v6, 0, 0x8000u);
}

```

## disassembly

```asm
0x180004560  push    rbx
0x180004562  sub     rsp, 20h
0x180004566  mov     rbx, rcx
0x180004569  mov     rcx, [rcx+20h]; hObject
0x18000456d  test    rcx, rcx
0x180004570  jz      short loc_18000457C
0x180004572  call    cs:__imp_CloseHandle
0x180004578  test    eax, eax
0x18000457a  jz      short loc_1800045B5
0x18000457c  mov     rcx, [rbx+18h]; hObject
0x180004580  lea     rax, [rcx-1]
0x180004584  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004588  ja      short loc_180004590
0x18000458a  call    cs:__imp_CloseHandle
0x180004590  mov     rcx, [rbx+10h]; lpAddress
0x180004594  mov     qword ptr [rbx+10h], 0
0x18000459c  test    rcx, rcx
0x18000459f  jz      short loc_1800045AF
0x1800045a1  xor     edx, edx; dwSize
0x1800045a3  mov     r8d, 8000h; dwFreeType
0x1800045a9  call    cs:__imp_VirtualFree
0x1800045af  add     rsp, 20h
0x1800045b3  pop     rbx
0x1800045b4  retn
0x1800045b5  mov     rcx, [rsp+28h]; this
0x1800045ba  mov     edx, 0A0Bh; void *
0x1800045bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
