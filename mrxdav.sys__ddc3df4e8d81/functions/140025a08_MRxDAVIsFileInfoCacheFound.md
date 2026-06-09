# MRxDAVIsFileInfoCacheFound

- ea: `0x140025a08`
- end: `0x140025a97`
- name: `MRxDAVIsFileInfoCacheFound`
- size: `143`
- prototype: `unsigned __int8 __fastcall(__int64, __int64, _DWORD *, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140001de4`
- `0x140003698`
- `0x1400130e0`
- `0x14001f6c0`

## callees

- `0x140005b3c`
- `0x140005ce8`
- `0x140005e30`
- `0x140025a08`

## pseudocode

```c
unsigned __int8 __fastcall MRxDAVIsFileInfoCacheFound(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  unsigned __int8 v8; // bl

  v8 = 0;
  if ( (unsigned __int8)MRxDAVIsBasicFileInfoCacheFound(a1, a2, a3, a4) )
  {
    if ( *a3 )
      v8 = 1;
    else
      v8 = (unsigned __int8)MRxDAVIsStandardFileInfoCacheFound(a1, a2 + 40, a3, a4) != 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v8,
      *(_DWORD *)(a1 + 56) + 360,
      *a3,
      v8,
      *(_QWORD *)(a1 + 56) + 360LL);
  return v8;
}

```

## disassembly

```asm
0x140025a08  push    rbx
0x140025a0a  push    rbp
0x140025a0b  push    rsi
0x140025a0c  push    rdi
0x140025a0d  push    r14
0x140025a0f  sub     rsp, 30h
0x140025a13  mov     rbp, r9
0x140025a16  mov     rdi, r8
0x140025a19  mov     r14, rdx
0x140025a1c  mov     rsi, rcx
0x140025a1f  xor     bl, bl
0x140025a21  call    MRxDAVIsBasicFileInfoCacheFound
0x140025a26  test    al, al
0x140025a28  jz      short loc_140025A4A
0x140025a2a  cmp     dword ptr [rdi], 0
0x140025a2d  jnz     short loc_140025A48
0x140025a2f  lea     rdx, [r14+28h]
0x140025a33  mov     r9, rbp
0x140025a36  mov     r8, rdi
0x140025a39  mov     rcx, rsi
0x140025a3c  call    MRxDAVIsStandardFileInfoCacheFound
0x140025a41  test    al, al
0x140025a43  setnz   bl
0x140025a46  jmp     short loc_140025A4A
0x140025a48  mov     bl, 1
0x140025a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025a51  lea     rax, WPP_GLOBAL_Control
0x140025a58  cmp     rcx, rax
0x140025a5b  jz      short loc_140025A89
0x140025a5d  test    dword ptr [rcx+2Ch], 2000h
0x140025a64  jz      short loc_140025A89
0x140025a66  mov     r8, [rsi+38h]
0x140025a6a  mov     r9d, [rdi]
0x140025a6d  add     r8, 168h
0x140025a74  mov     rcx, [rcx+18h]
0x140025a78  movzx   edx, bl
0x140025a7b  mov     [rsp+58h+var_30], r8
0x140025a80  mov     [rsp+58h+var_38], edx
0x140025a84  call    WPP_SF_DDZ
0x140025a89  mov     al, bl
0x140025a8b  add     rsp, 30h
0x140025a8f  pop     r14
0x140025a91  pop     rdi
0x140025a92  pop     rsi
0x140025a93  pop     rbp
0x140025a94  pop     rbx
0x140025a95  retn
```
