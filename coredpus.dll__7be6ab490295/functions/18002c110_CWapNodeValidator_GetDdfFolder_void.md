# CWapNodeValidator::GetDdfFolder(void)

- ea: `0x18002c110`
- end: `0x18002c1c6`
- name: `?GetDdfFolder@CWapNodeValidator@@AEAAJXZ`
- size: `182`
- prototype: `int(CWapNodeValidator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d810`

## callees

- `0x180011d9c`
- `0x1800163d8`
- `0x18002c110`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c133`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c145`

## pseudocode

```c
int __fastcall CWapNodeValidator::GetDdfFolder(CWapNodeValidator *this)
{
  WCHAR *v2; // rcx
  UINT SystemDirectoryW; // eax
  int result; // eax
  int v5; // eax
  int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (WCHAR *)((char *)this + 8);
  if ( *v2 )
    return 0;
  SystemDirectoryW = GetSystemDirectoryW(v2, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( (unsigned __int64)(SystemDirectoryW + 1) + 5 >= 0x104 )
      return -2147418113;
    *((_WORD *)this + SystemDirectoryW + 4) = 92;
    v5 = StringCchCopyW((unsigned __int16 *)this + SystemDirectoryW + 5, 260LL - (SystemDirectoryW + 1), L"DDFs");
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
        (const char *)(unsigned int)v5,
        v7);
      return v6;
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c110  mov     [rsp+arg_0], rbx
0x18002c115  push    rdi; int
0x18002c116  sub     rsp, 20h
0x18002c11a  mov     rdi, rcx
0x18002c11d  xor     eax, eax
0x18002c11f  add     rcx, 8; lpBuffer
0x18002c123  cmp     ax, [rcx]
0x18002c126  jnz     loc_18002C1B8
0x18002c12c  mov     ebx, 104h
0x18002c131  mov     edx, ebx; uSize
0x18002c133  call    cs:__imp_GetSystemDirectoryW
0x18002c13a  nop     dword ptr [rax+rax+00h]
0x18002c13f  mov     edx, eax
0x18002c141  test    eax, eax
0x18002c143  jnz     short loc_18002C15F
0x18002c145  call    cs:__imp_GetLastError
0x18002c14c  nop     dword ptr [rax+rax+00h]
0x18002c151  test    eax, eax
0x18002c153  jle     short loc_18002C1BA
0x18002c155  movzx   eax, ax
0x18002c158  or      eax, 80070000h
0x18002c15d  jmp     short loc_18002C1BA
0x18002c15f  lea     eax, [rdx+1]
0x18002c162  mov     ecx, eax
0x18002c164  add     rax, 5
0x18002c168  cmp     rax, rbx
0x18002c16b  jb      short loc_18002C174
0x18002c16d  mov     eax, 8000FFFFh
0x18002c172  jmp     short loc_18002C1BA
0x18002c174  sub     rbx, rcx
0x18002c177  mov     word ptr [rdi+rdx*2+8], 5Ch ; '\'
0x18002c17e  add     rcx, 4
0x18002c182  lea     r8, aDdfs; "DDFs"
0x18002c189  mov     rdx, rbx; unsigned __int64
0x18002c18c  lea     rcx, [rdi+rcx*2]; unsigned __int16 *
0x18002c190  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c195  mov     ebx, eax
0x18002c197  test    eax, eax
0x18002c199  jns     short loc_18002C1B8
0x18002c19b  mov     rcx, [rsp+28h]; this
0x18002c1a0  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002c1a7  mov     r9d, eax; char *
0x18002c1aa  mov     edx, 14Bh; void *
0x18002c1af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c1b4  mov     eax, ebx
0x18002c1b6  jmp     short loc_18002C1BA
0x18002c1b8  xor     eax, eax
0x18002c1ba  mov     rbx, [rsp+28h+arg_0]
0x18002c1bf  add     rsp, 20h
0x18002c1c3  pop     rdi
0x18002c1c4  retn
```
