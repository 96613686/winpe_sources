# PsmpDeleteCacheEntry

- ea: `0x180022b2c`
- end: `0x180022bfb`
- name: `PsmpDeleteCacheEntry`
- size: `207`
- prototype: `NTSTATUS __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000191c`
- `0x1800162b0`

## callees

- `0x180017ca4`
- `0x18001dab8`
- `0x180022b2c`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180022bcc`
- `ntdll!NtSetEvent` at `0x180022bcc`
- `ntdll!NtClearEvent` at `0x180022b70`
- `ntdll!NtClearEvent` at `0x180022b70`

## pseudocode

```c
NTSTATUS __fastcall PsmpDeleteCacheEntry(__int64 a1, char a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // rcx
  _QWORD *v6; // rax
  NTSTATUS result; // eax

  v2 = (_QWORD *)(a1 + 6720);
  v4 = *(_QWORD *)(a1 + 6720);
  if ( *(_QWORD **)(v4 + 8) != v2 || (v6 = (_QWORD *)v2[1], (_QWORD *)*v6 != v2) )
    __fastfail(3u);
  *v6 = v4;
  *(_QWORD *)(v4 + 8) = v6;
  result = NtClearEvent(*(HANDLE *)(a1 + 224));
  if ( (*(_DWORD *)(a1 + 128) & 0x400) == 0 || a2 )
  {
    v2[1] = v2;
    *v2 = v2;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_i(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_b5485372ff90327e3674091dc1985471_Traceguids,
        *(_QWORD *)(a1 + 96));
    result = PsmpInsertNewApplication(a1);
    if ( (_BYTE)result )
      result = NtSetEvent(*(HANDLE *)(*(_QWORD *)(a1 + 320) + 56LL), 0);
  }
  _interlockedbittestandreset((volatile signed __int32 *)(a1 + 128), 1u);
  return result;
}

```

## disassembly

```asm
0x180022b2c  mov     [rsp+arg_8], rbx
0x180022b31  mov     [rsp+arg_10], rsi
0x180022b36  push    rdi
0x180022b37  sub     rsp, 20h
0x180022b3b  lea     rbx, [rcx+1A40h]
0x180022b42  mov     rdi, rcx
0x180022b45  mov     rcx, [rbx]
0x180022b48  mov     sil, dl
0x180022b4b  cmp     [rcx+8], rbx
0x180022b4f  jnz     loc_180022BF4
0x180022b55  mov     rax, [rbx+8]
0x180022b59  cmp     [rax], rbx
0x180022b5c  jnz     loc_180022BF4
0x180022b62  mov     [rax], rcx
0x180022b65  mov     [rcx+8], rax
0x180022b69  mov     rcx, [rdi+0E0h]; EventHandle
0x180022b70  call    cs:__imp_NtClearEvent
0x180022b76  test    dword ptr [rdi+80h], 400h
0x180022b80  jz      short loc_180022BD4
0x180022b82  test    sil, sil
0x180022b85  jnz     short loc_180022BD4
0x180022b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b8e  test    byte ptr [rcx+1Ch], 2
0x180022b92  jz      short loc_180022BB3
0x180022b94  cmp     byte ptr [rcx+19h], 4
0x180022b98  jb      short loc_180022BB3
0x180022b9a  mov     r9, [rdi+60h]
0x180022b9e  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids
0x180022ba5  mov     rcx, [rcx+10h]
0x180022ba9  mov     edx, 0Dh
0x180022bae  call    WPP_SF_i
0x180022bb3  mov     rcx, rdi
0x180022bb6  call    PsmpInsertNewApplication
0x180022bbb  test    al, al
0x180022bbd  jz      short loc_180022BDB
0x180022bbf  mov     rcx, [rdi+140h]
0x180022bc6  xor     edx, edx; PreviousState
0x180022bc8  mov     rcx, [rcx+38h]; EventHandle
0x180022bcc  call    cs:__imp_NtSetEvent
0x180022bd2  jmp     short loc_180022BDB
0x180022bd4  mov     [rbx+8], rbx
0x180022bd8  mov     [rbx], rbx
0x180022bdb  lock btr dword ptr [rdi+80h], 1
0x180022be4  mov     rbx, [rsp+28h+arg_8]
0x180022be9  mov     rsi, [rsp+28h+arg_10]
0x180022bee  add     rsp, 20h
0x180022bf2  pop     rdi
0x180022bf3  retn
0x180022bf4  mov     ecx, 3
0x180022bf9  int     29h; Win8: RtlFailFast(ecx)
```
