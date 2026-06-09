# BookKeepingXml::Empty(void)

- ea: `0x18000c68c`
- end: `0x18000c6d8`
- name: `?Empty@BookKeepingXml@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bd5c`
- `0x18000bd80`
- `0x18000c464`
- `0x18000c914`
- `0x18000d370`

## callees

- `0x18000c68c`

## pseudocode

```c
void __fastcall BookKeepingXml::Empty(BookKeepingXml *this)
{
  if ( *((_QWORD *)this + 2) != -1 )
    *((_QWORD *)this + 2) = -1;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 1030) = 0;
  *((_DWORD *)this + 2058) = 50;
  *((_DWORD *)this + 2059) = 50;
  *((_QWORD *)this + 3) = (char *)this + 40;
  *((_QWORD *)this + 4) = 4096;
  *((_WORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x18000c68c  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x18000c691  mov     rax, rcx
0x18000c694  jz      short loc_18000C69E
0x18000c696  mov     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x18000c69e  mov     qword ptr [rcx+8], 0
0x18000c6a6  mov     qword ptr [rcx+2030h], 0
0x18000c6b1  mov     ecx, 32h ; '2'
0x18000c6b6  mov     [rax+2028h], ecx
0x18000c6bc  mov     [rax+202Ch], ecx
0x18000c6c2  lea     rcx, [rax+28h]
0x18000c6c6  mov     [rax+18h], rcx
0x18000c6ca  mov     qword ptr [rax+20h], 1000h
0x18000c6d2  xor     eax, eax
0x18000c6d4  mov     [rcx], ax
0x18000c6d7  retn
```
