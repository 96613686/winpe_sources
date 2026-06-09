# FreeStrings

- ea: `0x1800026f0`
- end: `0x180002763`
- name: `FreeStrings`
- size: `115`
- prototype: `void *()`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002974`
- `0x180007c10`

## callees

- `0x180002616`
- `0x1800026f0`
- `0x180002e7c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000273a`
- `KERNEL32!LocalFree` at `0x18000273a`

## pseudocode

```c
void *FreeStrings()
{
  __int64 i; // rbx
  void *v1; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids);
  for ( i = 0; i != 23; ++i )
  {
    v1 = (void *)g_ppszStrings[i];
    if ( v1 )
      LocalFree(v1);
  }
  return memset_0(g_ppszStrings, 0, 0xB8u);
}

```

## disassembly

```asm
0x1800026f0  mov     [rsp+arg_0], rbx
0x1800026f5  push    rdi
0x1800026f6  sub     rsp, 20h
0x1800026fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180002701  lea     rax, WPP_GLOBAL_Control
0x180002708  cmp     rcx, rax
0x18000270b  jz      short loc_180002728
0x18000270d  test    byte ptr [rcx+1Ch], 1
0x180002711  jz      short loc_180002728
0x180002713  mov     rcx, [rcx+10h]
0x180002717  lea     r8, WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids
0x18000271e  mov     edx, 10h
0x180002723  call    WPP_SF_
0x180002728  xor     ebx, ebx
0x18000272a  lea     rdi, g_ppszStrings
0x180002731  mov     rcx, [rdi+rbx*8]; hMem
0x180002735  test    rcx, rcx
0x180002738  jz      short loc_180002740
0x18000273a  call    cs:__imp_LocalFree
0x180002740  inc     rbx
0x180002743  cmp     rbx, 17h
0x180002747  jnz     short loc_180002731
0x180002749  xor     edx, edx; Val
0x18000274b  mov     r8d, 0B8h; Size
0x180002751  mov     rcx, rdi; void *
0x180002754  mov     rbx, [rsp+28h+arg_0]
0x180002759  add     rsp, 20h
0x18000275d  pop     rdi
0x18000275e  jmp     memset_0
```
