# VerifyIsExeOrTlb(LoadInfo *)

- ea: `0x180032b04`
- end: `0x180032bc1`
- name: `?VerifyIsExeOrTlb@@YAJPEAULoadInfo@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct LoadInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180044c0c`

## callees

- `0x180032b04`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x180032b46`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x180032b46`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x180032b25`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x180032b73`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x180032bb1`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x180032b25`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x180032b73`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x180032bb1`

## pseudocode

```c
__int64 __fastcall VerifyIsExeOrTlb(struct LoadInfo *a1)
{
  unsigned int v2; // edi
  LONG v3; // eax
  LONG v4; // ebp
  _WORD *v5; // rsi

  v2 = -2147287038;
  v3 = _llseek(*((_DWORD *)a1 + 2), 0, 1);
  v4 = v3;
  if ( v3 != -1 && (!v3 || _llseek(*((_DWORD *)a1 + 2), 0, 0) != -1) )
  {
    v5 = (_WORD *)((char *)a1 + 36);
    if ( _lread(*((_DWORD *)a1 + 2), (char *)a1 + 36, 0x40u) != -1 )
    {
      if ( *v5 == 23117 )
      {
        if ( *((_DWORD *)a1 + 6) == -1 )
          *((_DWORD *)a1 + 6) = 1;
        *((_DWORD *)a1 + 7) = 1;
        v2 = 0;
        goto LABEL_8;
      }
      if ( *(_DWORD *)v5 == 1196706899 )
      {
LABEL_13:
        *((_DWORD *)a1 + 4) = 1;
        if ( *((_DWORD *)a1 + 6) == -1 )
          v2 = 0;
        goto LABEL_8;
      }
      if ( *(_DWORD *)v5 == 1413894989 )
      {
        *((_DWORD *)a1 + 5) = 1;
        goto LABEL_13;
      }
    }
LABEL_8:
    _llseek(*((_DWORD *)a1 + 2), v4, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x180032b04  push    rbx
0x180032b06  push    rbp
0x180032b07  push    rsi
0x180032b08  push    rdi
0x180032b09  push    r14
0x180032b0b  sub     rsp, 20h
0x180032b0f  mov     rbx, rcx
0x180032b12  mov     r14d, 1
0x180032b18  mov     ecx, [rcx+8]; hFile
0x180032b1b  mov     r8d, r14d; iOrigin
0x180032b1e  xor     edx, edx; lOffset
0x180032b20  mov     edi, 80030002h
0x180032b25  call    cs:__imp__llseek
0x180032b2b  mov     ebp, eax
0x180032b2d  cmp     eax, 0FFFFFFFFh
0x180032b30  jz      short loc_180032B79
0x180032b32  test    eax, eax
0x180032b34  jnz     short loc_180032BA9
0x180032b36  mov     ecx, [rbx+8]; hFile
0x180032b39  lea     rsi, [rbx+24h]
0x180032b3d  mov     rdx, rsi; lpBuffer
0x180032b40  mov     r8d, 40h ; '@'; uBytes
0x180032b46  call    cs:__imp__lread
0x180032b4c  cmp     eax, 0FFFFFFFFh
0x180032b4f  jz      short loc_180032B6B
0x180032b51  mov     eax, 5A4Dh
0x180032b56  cmp     [rsi], ax
0x180032b59  jnz     short loc_180032B86
0x180032b5b  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x180032b5f  jnz     short loc_180032B65
0x180032b61  mov     [rbx+18h], r14d
0x180032b65  mov     [rbx+1Ch], r14d
0x180032b69  xor     edi, edi
0x180032b6b  mov     ecx, [rbx+8]; hFile
0x180032b6e  xor     r8d, r8d; iOrigin
0x180032b71  mov     edx, ebp; lOffset
0x180032b73  call    cs:__imp__llseek
0x180032b79  mov     eax, edi
0x180032b7b  add     rsp, 20h
0x180032b7f  pop     r14
0x180032b81  pop     rdi
0x180032b82  pop     rsi
0x180032b83  pop     rbp
0x180032b84  pop     rbx
0x180032b85  retn
0x180032b86  cmp     dword ptr [rsi], 47544C53h
0x180032b8c  jz      short loc_180032B9A
0x180032b8e  cmp     dword ptr [rsi], 5446534Dh
0x180032b94  jnz     short loc_180032B6B
0x180032b96  mov     [rbx+14h], r14d
0x180032b9a  xor     ecx, ecx
0x180032b9c  mov     [rbx+10h], r14d
0x180032ba0  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x180032ba4  cmovz   edi, ecx
0x180032ba7  jmp     short loc_180032B6B
0x180032ba9  mov     ecx, [rbx+8]; hFile
0x180032bac  xor     r8d, r8d; iOrigin
0x180032baf  xor     edx, edx; lOffset
0x180032bb1  call    cs:__imp__llseek
0x180032bb7  cmp     eax, 0FFFFFFFFh
0x180032bba  jz      short loc_180032B79
0x180032bbc  jmp     loc_180032B36
```
