# Coalesce_Cleanup

- ea: `0x180072f4c`
- end: `0x180072ffb`
- name: `Coalesce_Cleanup`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18008fe54`

## callees

- `0x18002b050`
- `0x180072f4c`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072f6a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072f6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072fa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072fa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072fd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072fd3`

## pseudocode

```c
void Coalesce_Cleanup()
{
  if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
    WPP_SF_(1033, 41, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids);
  if ( lpMem )
  {
    EnterCriticalSection(&stru_180112540);
    if ( lpMem )
    {
      DnsApiFree(lpMem);
      lpMem = 0;
    }
    LeaveCriticalSection(&stru_180112540);
  }
  DeleteCriticalSection(&stru_180112540);
  if ( (BYTE1(xmmword_1801119E0) & 2) != 0 )
    WPP_SF_(1033, 42, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids);
}

```

## disassembly

```asm
0x180072f4c  sub     rsp, 28h
0x180072f50  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180072f57  jnz     short loc_180072F85
0x180072f59  cmp     cs:lpMem, 0
0x180072f61  jnz     short loc_180072F9D
0x180072f63  lea     rcx, stru_180112540; lpCriticalSection
0x180072f6a  call    cs:__imp_DeleteCriticalSection
0x180072f71  nop     dword ptr [rax+rax+00h]
0x180072f76  test    byte ptr cs:xmmword_1801119E0+1, 2
0x180072f7d  jnz     short loc_180072FE1
0x180072f7f  add     rsp, 28h
0x180072f83  retn
0x180072f85  mov     edx, 29h ; ')'
0x180072f8a  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x180072f91  mov     ecx, 409h
0x180072f96  call    WPP_SF_
0x180072f9b  jmp     short loc_180072F59
0x180072f9d  lea     rcx, stru_180112540; lpCriticalSection
0x180072fa4  call    cs:__imp_EnterCriticalSection
0x180072fab  nop     dword ptr [rax+rax+00h]
0x180072fb0  mov     rcx, cs:lpMem; lpMem
0x180072fb7  test    rcx, rcx
0x180072fba  jz      short loc_180072FCC
0x180072fbc  call    DnsApiFree
0x180072fc1  mov     cs:lpMem, 0
0x180072fcc  lea     rcx, stru_180112540; lpCriticalSection
0x180072fd3  call    cs:__imp_LeaveCriticalSection
0x180072fda  nop     dword ptr [rax+rax+00h]
0x180072fdf  jmp     short loc_180072F63
0x180072fe1  mov     edx, 2Ah ; '*'
0x180072fe6  lea     r8, WPP_e7fac564e5f8353b8d950ea20f4a7fe5_Traceguids
0x180072fed  mov     ecx, 409h
0x180072ff2  add     rsp, 28h
0x180072ff6  jmp     WPP_SF_
```
