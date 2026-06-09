# CLMSubStr::TrimSpaces(void)

- ea: `0x18003822c`
- end: `0x1800382d4`
- name: `?TrimSpaces@CLMSubStr@@QEAAXXZ`
- size: `168`
- prototype: `void(CLMSubStr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180037a7c`

## callees

- `0x180016360`
- `0x18003822c`
- `0x1800382dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180038259`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800382a2`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180038259`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800382a2`

## string_xrefs

- `0x180038279`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall CLMSubStr::TrimSpaces(CLMSubStr *this)
{
  char *v2; // rdi
  int v3; // eax
  int v4; // ecx
  unsigned int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (char *)this + 8;
  while ( *((_DWORD *)this + 1) )
  {
    v2 = (char *)this + 8;
    if ( !(unsigned int)_o_iswspace(*(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL)
                                                        + 2LL * *(unsigned int *)this)) )
      break;
    v3 = *((_DWORD *)this + 1);
    if ( !v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x39A,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        v5);
    ++*(_DWORD *)this;
    *((_DWORD *)this + 1) = v3 - 1;
  }
  while ( 1 )
  {
    v4 = *((_DWORD *)this + 1);
    if ( !v4
      || !(unsigned int)_o_iswspace(*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)v2 + 8LL)
                                                        + 2LL * (unsigned int)(v4 + *(_DWORD *)this - 1))) )
    {
      break;
    }
    CLMSubStr::Truncate(this, *((_DWORD *)this + 1) - 1);
    v2 = (char *)this + 8;
  }
}

```

## disassembly

```asm
0x18003822c  mov     [rsp+arg_0], rbx
0x180038231  mov     [rsp+arg_8], rsi
0x180038236  push    rdi; unsigned int
0x180038237  sub     rsp, 20h
0x18003823b  mov     rbx, rcx
0x18003823e  lea     rdi, [rcx+8]
0x180038242  cmp     dword ptr [rbx+4], 0
0x180038246  jz      short loc_1800382BD
0x180038248  mov     edx, [rbx]
0x18003824a  lea     rdi, [rbx+8]
0x18003824e  mov     rax, [rdi]
0x180038251  mov     rcx, [rax+8]
0x180038255  movzx   ecx, word ptr [rcx+rdx*2]
0x180038259  call    cs:__imp__o_iswspace
0x18003825f  test    eax, eax
0x180038261  jz      short loc_1800382BD
0x180038263  mov     eax, [rbx+4]
0x180038266  cmp     eax, 1
0x180038269  jb      short loc_180038274
0x18003826b  inc     dword ptr [rbx]
0x18003826d  dec     eax
0x18003826f  mov     [rbx+4], eax
0x180038272  jmp     short loc_180038242
0x180038274  mov     rcx, [rsp+28h]; this
0x180038279  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180038280  mov     r9d, 0CEh; char *
0x180038286  mov     edx, 39Ah; void *
0x18003828b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180038291  mov     edx, [rbx]
0x180038293  mov     rax, [rdi]
0x180038296  dec     edx
0x180038298  add     edx, ecx
0x18003829a  mov     rcx, [rax+8]
0x18003829e  movzx   ecx, word ptr [rcx+rdx*2]
0x1800382a2  call    cs:__imp__o_iswspace
0x1800382a8  test    eax, eax
0x1800382aa  jz      short loc_1800382C4
0x1800382ac  mov     edx, [rbx+4]
0x1800382af  mov     rcx, rbx; this
0x1800382b2  dec     edx; unsigned int
0x1800382b4  call    ?Truncate@CLMSubStr@@QEAAXI@Z; CLMSubStr::Truncate(uint)
0x1800382b9  lea     rdi, [rbx+8]
0x1800382bd  mov     ecx, [rbx+4]
0x1800382c0  test    ecx, ecx
0x1800382c2  jnz     short loc_180038291
0x1800382c4  mov     rbx, [rsp+28h+arg_0]
0x1800382c9  mov     rsi, [rsp+28h+arg_8]
0x1800382ce  add     rsp, 20h
0x1800382d2  pop     rdi
0x1800382d3  retn
```
