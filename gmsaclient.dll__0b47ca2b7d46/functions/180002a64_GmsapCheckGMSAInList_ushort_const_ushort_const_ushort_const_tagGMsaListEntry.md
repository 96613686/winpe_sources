# GmsapCheckGMSAInList(ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)

- ea: `0x180002a64`
- end: `0x180002b10`
- name: `?GmsapCheckGMSAInList@@YAXPEBG00PEAPEAU_tagGMsaListEntry@@@Z`
- size: `172`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _tagGMsaListEntry **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e18`
- `0x180003e84`
- `0x1800056d0`

## callees

- `0x180002a64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002a9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002ab7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002ace`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002ae5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002a9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002ab7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002ace`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002ae5`

## pseudocode

```c
void __fastcall GmsapCheckGMSAInList(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _tagGMsaListEntry **a4)
{
  struct _tagGMsaListEntry *i; // rbx

  *a4 = 0;
  for ( i = (struct _tagGMsaListEntry *)hMem; i != (struct _tagGMsaListEntry *)&hMem; i = *(struct _tagGMsaListEntry **)i )
  {
    if ( (!(unsigned int)_o__wcsicmp(a1, *((_QWORD *)i + 2)) || a2 && !(unsigned int)_o__wcsicmp(a2, *((_QWORD *)i + 2)))
      && (!(unsigned int)_o__wcsicmp(a3, *((_QWORD *)i + 3)) || !(unsigned int)_o__wcsicmp(a3, *((_QWORD *)i + 4))) )
    {
      *a4 = i;
      return;
    }
  }
}

```

## disassembly

```asm
0x180002a64  push    rbx
0x180002a66  push    rbp
0x180002a67  push    rsi
0x180002a68  push    rdi
0x180002a69  push    r14
0x180002a6b  push    r15
0x180002a6d  sub     rsp, 28h
0x180002a71  mov     qword ptr [r9], 0
0x180002a78  lea     r15, hMem
0x180002a7f  mov     rbx, cs:hMem
0x180002a86  mov     rdi, r9
0x180002a89  mov     rbp, r8
0x180002a8c  mov     rsi, rdx
0x180002a8f  mov     r14, rcx
0x180002a92  jmp     short loc_180002AF8
0x180002a94  mov     rdx, [rbx+10h]
0x180002a98  mov     rcx, r14
0x180002a9b  call    cs:__imp__o__wcsicmp
0x180002aa2  nop     dword ptr [rax+rax+00h]
0x180002aa7  test    eax, eax
0x180002aa9  jz      short loc_180002AC7
0x180002aab  test    rsi, rsi
0x180002aae  jz      short loc_180002AF5
0x180002ab0  mov     rdx, [rbx+10h]
0x180002ab4  mov     rcx, rsi
0x180002ab7  call    cs:__imp__o__wcsicmp
0x180002abe  nop     dword ptr [rax+rax+00h]
0x180002ac3  test    eax, eax
0x180002ac5  jnz     short loc_180002AF5
0x180002ac7  mov     rdx, [rbx+18h]
0x180002acb  mov     rcx, rbp
0x180002ace  call    cs:__imp__o__wcsicmp
0x180002ad5  nop     dword ptr [rax+rax+00h]
0x180002ada  test    eax, eax
0x180002adc  jz      short loc_180002AFF
0x180002ade  mov     rdx, [rbx+20h]
0x180002ae2  mov     rcx, rbp
0x180002ae5  call    cs:__imp__o__wcsicmp
0x180002aec  nop     dword ptr [rax+rax+00h]
0x180002af1  test    eax, eax
0x180002af3  jz      short loc_180002AFF
0x180002af5  mov     rbx, [rbx]
0x180002af8  cmp     rbx, r15
0x180002afb  jnz     short loc_180002A94
0x180002afd  jmp     short loc_180002B02
0x180002aff  mov     [rdi], rbx
0x180002b02  add     rsp, 28h
0x180002b06  pop     r15
0x180002b08  pop     r14
0x180002b0a  pop     rdi
0x180002b0b  pop     rsi
0x180002b0c  pop     rbp
0x180002b0d  pop     rbx
0x180002b0e  retn
```
