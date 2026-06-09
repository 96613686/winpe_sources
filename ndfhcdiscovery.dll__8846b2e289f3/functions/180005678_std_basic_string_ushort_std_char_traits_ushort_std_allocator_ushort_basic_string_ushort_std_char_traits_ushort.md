# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180005678`
- end: `0x1800056af`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013c60`
- `0x180013e1b`
- `0x18001415e`
- `0x180014174`
- `0x18001418a`
- `0x18001429c`
- `0x180014366`
- `0x18001437c`

## callees

- `0x180005678`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000568b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000568b`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 24) >= 8u )
    operator delete(*(void **)a1);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180005678  push    rbx
0x18000567a  sub     rsp, 20h
0x18000567e  cmp     qword ptr [rcx+18h], 8
0x180005683  mov     rbx, rcx
0x180005686  jb      short loc_180005697
0x180005688  mov     rcx, [rcx]
0x18000568b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005692  nop     dword ptr [rax+rax+00h]
0x180005697  xor     eax, eax
0x180005699  mov     qword ptr [rbx+18h], 7
0x1800056a1  mov     [rbx+10h], rax
0x1800056a5  mov     [rbx], ax
0x1800056a8  add     rsp, 20h
0x1800056ac  pop     rbx
0x1800056ad  retn
```
