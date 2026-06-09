# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(void)

- ea: `0x180005720`
- end: `0x180005788`
- name: `??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005048`
- `0x180005aac`
- `0x18000a250`
- `0x18000a308`
- `0x18000a638`
- `0x180013c72`

## callees

- `0x180005720`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005734`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005760`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005734`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005760`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 56) >= 8u )
    operator delete(*(void **)(a1 + 32));
  *(_QWORD *)(a1 + 56) = 7;
  *(_QWORD *)(a1 + 48) = 0;
  *(_WORD *)(a1 + 32) = 0;
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
0x180005720  push    rbx
0x180005722  sub     rsp, 20h
0x180005726  cmp     qword ptr [rcx+38h], 8
0x18000572b  mov     rbx, rcx
0x18000572e  jb      short loc_180005740
0x180005730  mov     rcx, [rcx+20h]
0x180005734  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000573b  nop     dword ptr [rax+rax+00h]
0x180005740  xor     eax, eax
0x180005742  mov     qword ptr [rbx+38h], 7
0x18000574a  mov     qword ptr [rbx+30h], 0
0x180005752  mov     [rbx+20h], ax
0x180005756  cmp     qword ptr [rbx+18h], 8
0x18000575b  jb      short loc_18000576C
0x18000575d  mov     rcx, [rbx]
0x180005760  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005767  nop     dword ptr [rax+rax+00h]
0x18000576c  xor     eax, eax
0x18000576e  mov     qword ptr [rbx+18h], 7
0x180005776  mov     qword ptr [rbx+10h], 0
0x18000577e  mov     [rbx], ax
0x180005781  add     rsp, 20h
0x180005785  pop     rbx
0x180005786  retn
```
