# ActiveScriptError::FillText(ushort const * &,ushort const *)

- ea: `0x1801d489c`
- end: `0x1801d4923`
- name: `?FillText@ActiveScriptError@@CAJAEAPEBGPEBG@Z`
- size: `135`
- prototype: `static int(const unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1801d3864`
- `0x1801d3a50`
- `0x1801d3fec`
- `0x1801d40b0`
- `0x1801d4438`
- `0x1801d4748`
- `0x1801d4df0`

## callees

- `0x1801d489c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1801d4904`
- `msvcrt!wcscpy_s` at `0x1801d4904`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d48db`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801d48db`

## pseudocode

```c
__int64 __fastcall ActiveScriptError::FillText(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  rsize_t v4; // rdi
  unsigned __int16 *v5; // rax

  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    v4 = v3 + 1;
    v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v3 + 1));
    *a1 = v5;
    if ( !v5 )
      return 2147942414LL;
    wcscpy_s(v5, v4, a2);
  }
  else
  {
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1801d489c  mov     rax, rsp
0x1801d489f  mov     [rax+18h], rbx
0x1801d48a3  mov     [rax+20h], rsi
0x1801d48a7  mov     [rax+10h], rdx
0x1801d48ab  mov     [rax+8], rcx
0x1801d48af  push    rdi
0x1801d48b0  sub     rsp, 20h
0x1801d48b4  xor     esi, esi
0x1801d48b6  mov     rbx, rdx
0x1801d48b9  test    rdx, rdx
0x1801d48bc  jnz     short loc_1801D48C6
0x1801d48be  mov     rax, rcx
0x1801d48c1  mov     [rcx], rsi
0x1801d48c4  jmp     short loc_1801D4910
0x1801d48c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801d48ca  inc     rax
0x1801d48cd  cmp     [rbx+rax*2], si
0x1801d48d1  jnz     short loc_1801D48CA
0x1801d48d3  lea     rdi, [rax+1]
0x1801d48d7  lea     rcx, [rdi+rdi]; cb
0x1801d48db  call    cs:__imp_CoTaskMemAlloc
0x1801d48e2  nop     dword ptr [rax+rax+00h]
0x1801d48e7  mov     rcx, [rsp+28h+arg_0]
0x1801d48ec  mov     [rcx], rax
0x1801d48ef  test    rax, rax
0x1801d48f2  jnz     short loc_1801D48FB
0x1801d48f4  mov     eax, 8007000Eh
0x1801d48f9  jmp     short loc_1801D4912
0x1801d48fb  mov     r8, rbx; Source
0x1801d48fe  mov     rdx, rdi; SizeInWords
0x1801d4901  mov     rcx, rax; Destination
0x1801d4904  call    cs:__imp_wcscpy_s
0x1801d490b  nop     dword ptr [rax+rax+00h]
0x1801d4910  xor     eax, eax
0x1801d4912  mov     rbx, [rsp+28h+arg_10]
0x1801d4917  mov     rsi, [rsp+28h+arg_18]
0x1801d491c  add     rsp, 20h
0x1801d4920  pop     rdi
0x1801d4921  retn
```
