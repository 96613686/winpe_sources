# EXTENDED_LOG_DATA::AddNameValue(ushort const *,ushort const *)

- ea: `0x1800055a4`
- end: `0x180005604`
- name: `?AddNameValue@EXTENDED_LOG_DATA@@QEAAJPEBG0@Z`
- size: `96`
- prototype: `signed int __fastcall(EXTENDED_LOG_DATA *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003510`

## callees

- `0x1800055a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055cc`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800055c2`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800055e6`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800055c2`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800055e6`

## pseudocode

```c
signed int __fastcall EXTENDED_LOG_DATA::AddNameValue(
        EXTENDED_LOG_DATA *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  MULTISZ *v4; // rdi
  signed int result; // eax

  if ( !a2 || !a3 )
    return -2147024809;
  v4 = (EXTENDED_LOG_DATA *)((char *)this + 40);
  if ( MULTISZ::Append((EXTENDED_LOG_DATA *)((char *)this + 40), a2) && MULTISZ::Append(v4, a3) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800055a4  mov     [rsp+arg_0], rbx
0x1800055a9  push    rdi
0x1800055aa  sub     rsp, 20h
0x1800055ae  mov     rbx, r8
0x1800055b1  test    rdx, rdx
0x1800055b4  jz      short loc_1800055F4
0x1800055b6  test    rbx, rbx
0x1800055b9  jz      short loc_1800055F4
0x1800055bb  lea     rdi, [rcx+28h]
0x1800055bf  mov     rcx, rdi
0x1800055c2  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800055c8  test    eax, eax
0x1800055ca  jnz     short loc_1800055E0
0x1800055cc  call    cs:__imp_GetLastError
0x1800055d2  test    eax, eax
0x1800055d4  jle     short loc_1800055F9
0x1800055d6  movzx   eax, ax
0x1800055d9  or      eax, 80070000h
0x1800055de  jmp     short loc_1800055F9
0x1800055e0  mov     rdx, rbx
0x1800055e3  mov     rcx, rdi
0x1800055e6  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800055ec  test    eax, eax
0x1800055ee  jz      short loc_1800055CC
0x1800055f0  xor     eax, eax
0x1800055f2  jmp     short loc_1800055F9
0x1800055f4  mov     eax, 80070057h
0x1800055f9  mov     rbx, [rsp+28h+arg_0]
0x1800055fe  add     rsp, 20h
0x180005602  pop     rdi
0x180005603  retn
```
