# FREB_XML_SERIALIZER::AddString(ulong,ulong,char const *)

- ea: `0x18000927c`
- end: `0x1800092d7`
- name: `?AddString@FREB_XML_SERIALIZER@@QEAAXKKPEBD@Z`
- size: `91`
- prototype: `void(FREB_XML_SERIALIZER *__hidden this, unsigned int, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004ae4`
- `0x180009948`

## callees

- `0x18000927c`
- `0x180009690`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x1800092be`
- `msvcrt!_snprintf_s` at `0x1800092be`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddString(FREB_XML_SERIALIZER *this, int a2, __int64 a3, const char *a4)
{
  char *Memory; // rax
  int v8; // eax

  if ( !*((_DWORD *)this + 7) )
  {
    Memory = FREB_XML_SERIALIZER::AllocateMemory(this, 0xBu);
    if ( Memory )
    {
      v8 = _snprintf_s(Memory, 0xBu, 0xFFFFFFFFFFFFFFFFuLL, a4, a2);
      if ( v8 != 11 )
        *((_DWORD *)this + 6) += v8 - 11;
    }
    else
    {
      *((_DWORD *)this + 7) = -2147024888;
    }
  }
}

```

## disassembly

```asm
0x18000927c  push    rbx
0x18000927e  push    rbp
0x18000927f  push    rsi
0x180009280  push    rdi
0x180009281  sub     rsp, 38h
0x180009285  cmp     dword ptr [rcx+1Ch], 0
0x180009289  mov     rsi, r9
0x18000928c  mov     ebp, edx
0x18000928e  mov     rbx, rcx
0x180009291  jnz     short loc_1800092CE
0x180009293  mov     edi, 0Bh
0x180009298  mov     edx, edi; unsigned int
0x18000929a  call    ?AllocateMemory@FREB_XML_SERIALIZER@@QEAAPEAEK@Z; FREB_XML_SERIALIZER::AllocateMemory(ulong)
0x18000929f  test    rax, rax
0x1800092a2  jnz     short loc_1800092AD
0x1800092a4  mov     dword ptr [rbx+1Ch], 80070008h
0x1800092ab  jmp     short loc_1800092CE
0x1800092ad  mov     r9, rsi; Format
0x1800092b0  mov     [rsp+58h+var_38], ebp
0x1800092b4  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800092b8  mov     rdx, rdi; BufferCount
0x1800092bb  mov     rcx, rax; Buffer
0x1800092be  call    cs:__imp__snprintf_s
0x1800092c4  cmp     edi, eax
0x1800092c6  jz      short loc_1800092CE
0x1800092c8  add     eax, 0FFFFFFF5h
0x1800092cb  add     [rbx+18h], eax
0x1800092ce  add     rsp, 38h
0x1800092d2  pop     rdi
0x1800092d3  pop     rsi
0x1800092d4  pop     rbp
0x1800092d5  pop     rbx
0x1800092d6  retn
```
