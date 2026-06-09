# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180009a30`
- end: `0x180009a67`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(__int64)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042a4`
- `0x180009608`
- `0x1800099a8`
- `0x180009a9c`
- `0x180009fb8`
- `0x18000a840`
- `0x18000a9d5`
- `0x18000aa01`
- `0x18000aa13`
- `0x18000aa25`
- `0x18000ab93`
- `0x18000aba5`

## callees

- `0x180004270`
- `0x180009a30`

## pseudocode

```c
void __fastcall std::string::~string(__int64 a1)
{
  unsigned __int64 v1; // rdx

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 0xF )
    std::_Deallocate<16>(*(_QWORD **)a1, v1 + 1);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x180009a30  push    rbx
0x180009a32  sub     rsp, 20h
0x180009a36  mov     rdx, [rcx+18h]
0x180009a3a  mov     rbx, rcx
0x180009a3d  cmp     rdx, 0Fh
0x180009a41  jbe     short loc_180009A4E
0x180009a43  mov     rcx, [rcx]
0x180009a46  inc     rdx
0x180009a49  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009a4e  mov     qword ptr [rbx+10h], 0
0x180009a56  mov     qword ptr [rbx+18h], 0Fh
0x180009a5e  mov     byte ptr [rbx], 0
0x180009a61  add     rsp, 20h
0x180009a65  pop     rbx
0x180009a66  retn
```
