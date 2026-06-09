# EngComputeGlyphSet

- ea: `0x18005daf0`
- end: `0x18005db6c`
- name: `EngComputeGlyphSet`
- size: `124`
- prototype: `FD_GLYPHSET *__stdcall(INT nCodePage, INT nFirstChar, INT cChars)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005daf0`
- `0x18005db74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005db1f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005db1f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005db5c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005db5c`
- `win32u!NtGdiEngComputeGlyphSet` at `0x18005db01`
- `win32u!NtGdiEngComputeGlyphSet` at `0x18005db01`

## pseudocode

```c
FD_GLYPHSET *__stdcall EngComputeGlyphSet(INT nCodePage, INT nFirstChar, INT cChars)
{
  FD_GLYPHSET *v3; // rbx
  _DWORD *v4; // rax
  _DWORD *v5; // rsi
  unsigned int v6; // edi
  FD_GLYPHSET *v7; // rax

  v3 = 0;
  v4 = (_DWORD *)NtGdiEngComputeGlyphSet(nCodePage, nFirstChar, cChars);
  v5 = v4;
  if ( v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      v7 = (FD_GLYPHSET *)GlobalAlloc(0, v6);
      v3 = v7;
      if ( v7 )
      {
        if ( !(unsigned int)CopyFD_GLYPHSET(v7, v5, v6) )
        {
          GlobalFree(v3);
          return 0;
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005daf0  mov     [rsp+arg_0], rbx
0x18005daf5  mov     [rsp+arg_8], rsi
0x18005dafa  push    rdi
0x18005dafb  sub     rsp, 20h
0x18005daff  xor     ebx, ebx
0x18005db01  call    cs:__imp_NtGdiEngComputeGlyphSet
0x18005db08  nop     dword ptr [rax+rax+00h]
0x18005db0d  mov     rsi, rax
0x18005db10  test    rax, rax
0x18005db13  jz      short loc_18005DB45
0x18005db15  mov     edi, [rax]
0x18005db17  test    edi, edi
0x18005db19  jz      short loc_18005DB45
0x18005db1b  mov     edx, edi; dwBytes
0x18005db1d  xor     ecx, ecx; uFlags
0x18005db1f  call    cs:__imp_GlobalAlloc
0x18005db26  nop     dword ptr [rax+rax+00h]
0x18005db2b  mov     rbx, rax
0x18005db2e  test    rax, rax
0x18005db31  jz      short loc_18005DB45
0x18005db33  mov     r8d, edi
0x18005db36  mov     rdx, rsi
0x18005db39  mov     rcx, rax
0x18005db3c  call    CopyFD_GLYPHSET
0x18005db41  test    eax, eax
0x18005db43  jz      short loc_18005DB59
0x18005db45  mov     rsi, [rsp+28h+arg_8]
0x18005db4a  mov     rax, rbx
0x18005db4d  mov     rbx, [rsp+28h+arg_0]
0x18005db52  add     rsp, 20h
0x18005db56  pop     rdi
0x18005db57  retn
0x18005db59  mov     rcx, rbx; hMem
0x18005db5c  call    cs:__imp_GlobalFree
0x18005db63  nop     dword ptr [rax+rax+00h]
0x18005db68  xor     ebx, ebx
0x18005db6a  jmp     short loc_18005DB45
```
