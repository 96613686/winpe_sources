# SelectClipPathImpl

- ea: `0x180061480`
- end: `0x1800614fd`
- name: `SelectClipPathImpl`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180061480`
- `0x180061504`

## import_xrefs

- `GDI32!pldcGet` at `0x1800614a4`
- `GDI32!pldcGet` at `0x1800614a4`
- `GDI32!GdiSetLastError` at `0x1800614ef`
- `GDI32!GdiSetLastError` at `0x1800614ef`
- `win32u!NtGdiSelectClipPath` at `0x1800614dc`
- `win32u!NtGdiSelectClipPath` at `0x1800614dc`

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
0x180061480  mov     [rsp+arg_0], rbx
0x180061485  push    rdi
0x180061486  sub     rsp, 20h
0x18006148a  mov     eax, ecx
0x18006148c  mov     edi, edx
0x18006148e  and     eax, 7F0000h
0x180061493  mov     rbx, rcx
0x180061496  cmp     eax, 660000h
0x18006149b  jz      short loc_1800614C9
0x18006149d  cmp     eax, 10000h
0x1800614a2  jz      short loc_1800614D7
0x1800614a4  call    cs:__imp_pldcGet
0x1800614ab  nop     dword ptr [rax+rax+00h]
0x1800614b0  test    rax, rax
0x1800614b3  jz      short loc_1800614EA
0x1800614b5  cmp     dword ptr [rax+0Ch], 2
0x1800614b9  jnz     short loc_1800614D7
0x1800614bb  mov     edx, edi
0x1800614bd  mov     rcx, rbx
0x1800614c0  call    MF_SelectClipPath
0x1800614c5  test    eax, eax
0x1800614c7  jnz     short loc_1800614D7
0x1800614c9  xor     eax, eax
0x1800614cb  mov     rbx, [rsp+28h+arg_0]
0x1800614d0  add     rsp, 20h
0x1800614d4  pop     rdi
0x1800614d5  retn
0x1800614d7  mov     edx, edi
0x1800614d9  mov     rcx, rbx
0x1800614dc  call    cs:__imp_NtGdiSelectClipPath
0x1800614e3  nop     dword ptr [rax+rax+00h]
0x1800614e8  jmp     short loc_1800614CB
0x1800614ea  mov     ecx, 6
0x1800614ef  call    cs:__imp_GdiSetLastError
0x1800614f6  nop     dword ptr [rax+rax+00h]
0x1800614fb  jmp     short loc_1800614C9
```
