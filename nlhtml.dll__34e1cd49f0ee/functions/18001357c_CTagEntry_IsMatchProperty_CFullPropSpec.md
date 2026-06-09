# CTagEntry::IsMatchProperty(CFullPropSpec &)

- ea: `0x18001357c`
- end: `0x180013607`
- name: `?IsMatchProperty@CTagEntry@@QEAAHAEAVCFullPropSpec@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(CTagEntry *__hidden this, struct CFullPropSpec *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000ad20`

## callees

- `0x18001357c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800135ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800135ba`

## pseudocode

```c
_BOOL8 __fastcall CTagEntry::IsMatchProperty(CTagEntry *this, struct CFullPropSpec *a2)
{
  _DWORD *v4; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rcx

  if ( !*((_QWORD *)this + 5) )
    return 0;
  if ( *((_DWORD *)a2 + 4) )
  {
    v4 = (_DWORD *)((char *)a2 + 24);
  }
  else
  {
    if ( *((_DWORD *)this + 8) )
      return 0;
    if ( !*((_QWORD *)this + 8) )
      return 0;
    v4 = (_DWORD *)((char *)a2 + 24);
    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 3)) )
      return 0;
  }
  if ( *((_DWORD *)a2 + 4) == 1 && (*((_DWORD *)this + 8) != 1 || *((_DWORD *)this + 12) != *v4) )
    return 0;
  v5 = (_QWORD *)*((_QWORD *)this + 5);
  v6 = *(_QWORD *)a2 - *v5;
  if ( *(_QWORD *)a2 == *v5 )
    v6 = *((_QWORD *)a2 + 1) - v5[1];
  return v6 == 0;
}

```

## disassembly

```asm
0x18001357c  mov     [rsp+arg_0], rbx
0x180013581  mov     [rsp+arg_8], rsi
0x180013586  push    rdi
0x180013587  sub     rsp, 20h
0x18001358b  cmp     qword ptr [rcx+28h], 0
0x180013590  mov     rdi, rdx
0x180013593  mov     rbx, rcx
0x180013596  jz      short loc_1800135F5
0x180013598  cmp     dword ptr [rdx+10h], 0
0x18001359c  jz      short loc_1800135A4
0x18001359e  lea     rsi, [rdx+18h]
0x1800135a2  jmp     short loc_1800135C4
0x1800135a4  cmp     dword ptr [rcx+20h], 0
0x1800135a8  jnz     short loc_1800135F5
0x1800135aa  mov     rdx, [rcx+40h]
0x1800135ae  test    rdx, rdx
0x1800135b1  jz      short loc_1800135F5
0x1800135b3  lea     rsi, [rdi+18h]
0x1800135b7  mov     rcx, [rsi]
0x1800135ba  call    cs:__imp__o__wcsicmp
0x1800135c0  test    eax, eax
0x1800135c2  jnz     short loc_1800135F5
0x1800135c4  cmp     dword ptr [rdi+10h], 1
0x1800135c8  jnz     short loc_1800135D7
0x1800135ca  cmp     dword ptr [rbx+20h], 1
0x1800135ce  jnz     short loc_1800135F5
0x1800135d0  mov     eax, [rsi]
0x1800135d2  cmp     [rbx+30h], eax
0x1800135d5  jnz     short loc_1800135F5
0x1800135d7  mov     rax, [rbx+28h]
0x1800135db  mov     rcx, [rdi]
0x1800135de  sub     rcx, [rax]
0x1800135e1  jnz     short loc_1800135EB
0x1800135e3  mov     rcx, [rdi+8]
0x1800135e7  sub     rcx, [rax+8]
0x1800135eb  xor     eax, eax
0x1800135ed  test    rcx, rcx
0x1800135f0  setz    al
0x1800135f3  jmp     short loc_1800135F7
0x1800135f5  xor     eax, eax
0x1800135f7  mov     rbx, [rsp+28h+arg_0]
0x1800135fc  mov     rsi, [rsp+28h+arg_8]
0x180013601  add     rsp, 20h
0x180013605  pop     rdi
0x180013606  retn
```
