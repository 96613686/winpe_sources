# SelectClipPathImpl

- ea: `0x18005d410`
- end: `0x18005d47a`
- name: `SelectClipPathImpl`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005d410`
- `0x18005d480`

## import_xrefs

- `GDI32!pldcGet` at `0x18005d434`
- `GDI32!pldcGet` at `0x18005d434`
- `GDI32!GdiSetLastError` at `0x18005d472`
- `GDI32!GdiSetLastError` at `0x18005d472`
- `win32u!NtGdiSelectClipPath` at `0x18005d465`
- `win32u!NtGdiSelectClipPath` at `0x18005d465`

## pseudocode

```c
__int64 __fastcall SelectClipPathImpl(__int64 a1, unsigned int a2)
{
  __int64 v4; // rax

  if ( (a1 & 0x7F0000) == 0x660000 )
    return 0;
  if ( (a1 & 0x7F0000) != 0x10000 )
  {
    v4 = pldcGet(a1);
    if ( !v4 )
    {
      GdiSetLastError(6);
      return 0;
    }
    if ( *(_DWORD *)(v4 + 12) == 2 && !(unsigned int)MF_SelectClipPath(a1, a2) )
      return 0;
  }
  return NtGdiSelectClipPath(a1, a2);
}

```

## disassembly

```asm
0x18005d410  mov     [rsp+arg_0], rbx
0x18005d415  push    rdi
0x18005d416  sub     rsp, 20h
0x18005d41a  mov     eax, ecx
0x18005d41c  mov     edi, edx
0x18005d41e  and     eax, 7F0000h
0x18005d423  mov     rbx, rcx
0x18005d426  cmp     eax, 660000h
0x18005d42b  jz      short loc_18005D453
0x18005d42d  cmp     eax, 10000h
0x18005d432  jz      short loc_18005D460
0x18005d434  call    cs:__imp_pldcGet
0x18005d43a  test    rax, rax
0x18005d43d  jz      short loc_18005D46D
0x18005d43f  cmp     dword ptr [rax+0Ch], 2
0x18005d443  jnz     short loc_18005D460
0x18005d445  mov     edx, edi
0x18005d447  mov     rcx, rbx
0x18005d44a  call    MF_SelectClipPath
0x18005d44f  test    eax, eax
0x18005d451  jnz     short loc_18005D460
0x18005d453  xor     eax, eax
0x18005d455  mov     rbx, [rsp+28h+arg_0]
0x18005d45a  add     rsp, 20h
0x18005d45e  pop     rdi
0x18005d45f  retn
0x18005d460  mov     edx, edi
0x18005d462  mov     rcx, rbx
0x18005d465  call    cs:__imp_NtGdiSelectClipPath
0x18005d46b  jmp     short loc_18005D455
0x18005d46d  mov     ecx, 6
0x18005d472  call    cs:__imp_GdiSetLastError
0x18005d478  jmp     short loc_18005D453
```
