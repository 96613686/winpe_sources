# CWMWriterInputPin::EndOfStream(void)

- ea: `0x180013fc0`
- end: `0x180014046`
- name: `?EndOfStream@CWMWriterInputPin@@UEAAJXZ`
- size: `134`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f738`
- `0x180013fc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180013fe0`
- `KERNEL32!EnterCriticalSection` at `0x180013fe0`
- `KERNEL32!LeaveCriticalSection` at `0x18001402e`
- `KERNEL32!LeaveCriticalSection` at `0x18001402e`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::EndOfStream(CWMWriterInputPin *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // edx

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 40);
  EnterCriticalSection(v1 + 6);
  v3 = 0;
  if ( *((_BYTE *)this + 209) )
    goto LABEL_7;
  v4 = *((_QWORD *)this + 40);
  if ( *(_DWORD *)(v4 + 40) )
  {
    if ( *((_DWORD *)this + 101) )
    {
      v5 = -2147418113;
      goto LABEL_8;
    }
    v6 = *((_DWORD *)this + 93);
    *((_DWORD *)this + 101) = 1;
    v3 = CWMWriter::EndOfStreamFromPin((struct _RTL_CRITICAL_SECTION *)v4, v6);
LABEL_7:
    v5 = v3;
    goto LABEL_8;
  }
  v5 = 1;
LABEL_8:
  LeaveCriticalSection(v1 + 6);
  return v5;
}

```

## disassembly

```asm
0x180013fc0  mov     [rsp+arg_0], rbx
0x180013fc5  mov     [rsp+arg_8], rsi
0x180013fca  push    rdi
0x180013fcb  sub     rsp, 20h
0x180013fcf  mov     rsi, [rcx+140h]
0x180013fd6  mov     rdi, rcx
0x180013fd9  lea     rcx, [rsi+0F0h]; lpCriticalSection
0x180013fe0  call    cs:__imp_EnterCriticalSection
0x180013fe6  xor     eax, eax
0x180013fe8  cmp     [rdi+0D1h], al
0x180013fee  jnz     short loc_180014025
0x180013ff0  mov     rcx, [rdi+140h]; this
0x180013ff7  cmp     [rcx+28h], eax
0x180013ffa  jnz     short loc_180014001
0x180013ffc  lea     ebx, [rax+1]
0x180013fff  jmp     short loc_180014027
0x180014001  cmp     [rdi+194h], eax
0x180014007  jz      short loc_180014010
0x180014009  mov     ebx, 8000FFFFh
0x18001400e  jmp     short loc_180014027
0x180014010  mov     edx, [rdi+174h]; int
0x180014016  mov     dword ptr [rdi+194h], 1
0x180014020  call    ?EndOfStreamFromPin@CWMWriter@@QEAAJH@Z; CWMWriter::EndOfStreamFromPin(int)
0x180014025  mov     ebx, eax
0x180014027  lea     rcx, [rsi+0F0h]; lpCriticalSection
0x18001402e  call    cs:__imp_LeaveCriticalSection
0x180014034  mov     rsi, [rsp+28h+arg_8]
0x180014039  mov     eax, ebx
0x18001403b  mov     rbx, [rsp+28h+arg_0]
0x180014040  add     rsp, 20h
0x180014044  pop     rdi
0x180014045  retn
```
