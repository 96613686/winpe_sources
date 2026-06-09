# FREB_XML_SERIALIZER::AddString(unsigned __int64,ulong,char const *)

- ea: `0x1800094bc`
- end: `0x180009519`
- name: `?AddString@FREB_XML_SERIALIZER@@QEAAX_KKPEBD@Z`
- size: `93`
- prototype: `void(FREB_XML_SERIALIZER *__hidden this, unsigned __int64, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009948`

## callees

- `0x1800094bc`
- `0x180009690`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180009500`
- `msvcrt!_snprintf_s` at `0x180009500`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddString(FREB_XML_SERIALIZER *this, __int64 a2, __int64 a3, const char *a4)
{
  char *Memory; // rax
  int v8; // eax

  if ( !*((_DWORD *)this + 7) )
  {
    Memory = FREB_XML_SERIALIZER::AllocateMemory(this, 0x15u);
    if ( Memory )
    {
      v8 = _snprintf_s(Memory, 0x15u, 0xFFFFFFFFFFFFFFFFuLL, a4, a2);
      if ( v8 != 21 )
        *((_DWORD *)this + 6) += v8 - 21;
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
0x1800094bc  push    rbx
0x1800094be  push    rbp
0x1800094bf  push    rsi
0x1800094c0  push    rdi
0x1800094c1  sub     rsp, 38h
0x1800094c5  cmp     dword ptr [rcx+1Ch], 0
0x1800094c9  mov     rsi, r9
0x1800094cc  mov     rbp, rdx
0x1800094cf  mov     rbx, rcx
0x1800094d2  jnz     short loc_180009510
0x1800094d4  mov     edi, 15h
0x1800094d9  mov     edx, edi; unsigned int
0x1800094db  call    ?AllocateMemory@FREB_XML_SERIALIZER@@QEAAPEAEK@Z; FREB_XML_SERIALIZER::AllocateMemory(ulong)
0x1800094e0  test    rax, rax
0x1800094e3  jnz     short loc_1800094EE
0x1800094e5  mov     dword ptr [rbx+1Ch], 80070008h
0x1800094ec  jmp     short loc_180009510
0x1800094ee  mov     r9, rsi; Format
0x1800094f1  mov     [rsp+58h+var_38], rbp
0x1800094f6  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800094fa  mov     rdx, rdi; BufferCount
0x1800094fd  mov     rcx, rax; Buffer
0x180009500  call    cs:__imp__snprintf_s
0x180009506  cmp     edi, eax
0x180009508  jz      short loc_180009510
0x18000950a  add     eax, 0FFFFFFEBh
0x18000950d  add     [rbx+18h], eax
0x180009510  add     rsp, 38h
0x180009514  pop     rdi
0x180009515  pop     rsi
0x180009516  pop     rbp
0x180009517  pop     rbx
0x180009518  retn
```
