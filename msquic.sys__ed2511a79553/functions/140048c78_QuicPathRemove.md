# QuicPathRemove

- ea: `0x140048c78`
- end: `0x140048d92`
- name: `QuicPathRemove`
- size: `282`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140015480`
- `0x14001e3b0`
- `0x140022950`
- `0x14002b5c4`
- `0x14002fbf8`

## callees

- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`
- `0x140048c78`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140048cfb`
- `ntoskrnl!_snprintf_s` at `0x140048cfb`

## string_xrefs

- `0x140048cab`: `Index < Connection->PathsCount`
- `0x140048cb7`: `C:\__w\1\s\msquic\src\core\path.c`
- `0x140048ce7`: `Path[%hhu] Removed`

## pseudocode

```c
__int64 __fastcall QuicPathRemove(__int64 a1, unsigned __int8 a2)
{
  int v2; // edi
  __int64 result; // rax
  __int64 v5; // rsi
  __int64 v6; // rcx
  unsigned int v7; // ecx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  v2 = a2;
  if ( a2 >= *(_BYTE *)(a1 + 275) )
    return CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\path.c", 59, "Index < Connection->PathsCount");
  v5 = 240LL * a2;
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] Removed", *(unsigned __int8 *)(v5 + a1 + 320));
    McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogInfo, a1, DstBuf);
  }
  v7 = *(unsigned __int8 *)(a1 + 275);
  if ( v2 + 1 < v7 )
    memmove((void *)(v5 + a1 + 320), (const void *)(v5 + a1 + 560), 240LL * (int)(v7 - v2 - 1));
  result = (unsigned __int8)--*(_BYTE *)(a1 + 275);
  *(_BYTE *)(240 * result + a1 + 321) &= ~1u;
  return result;
}

```

## disassembly

```asm
0x140048c78  mov     [rsp+arg_10], rbx
0x140048c7d  mov     [rsp+arg_18], rsi
0x140048c82  push    rdi
0x140048c83  sub     rsp, 0C0h
0x140048c8a  mov     rax, cs:__security_cookie
0x140048c91  xor     rax, rsp
0x140048c94  mov     [rsp+0C8h+var_18], rax
0x140048c9c  movzx   edi, dl
0x140048c9f  mov     rbx, rcx
0x140048ca2  cmp     dil, [rcx+113h]
0x140048ca9  jb      short loc_140048CC8
0x140048cab  lea     r8, aIndexConnectio; "Index < Connection->PathsCount"
0x140048cb2  mov     edx, 3Bh ; ';'
0x140048cb7  lea     rcx, aCW1SMsquicSrcC_6; "C:\\__w\\1\\s\\msquic\\src\\core\\path."...
0x140048cbe  call    CxPlatLogAssert
0x140048cc3  jmp     loc_140048D6C
0x140048cc8  mov     rcx, rdi
0x140048ccb  mov     edx, 80h; SizeInBytes
0x140048cd0  imul    rsi, rcx, 0F0h
0x140048cd7  test    cs:byte_14005C48B, dl
0x140048cdd  jz      short loc_140048D1B
0x140048cdf  movzx   eax, byte ptr [rsi+rbx+140h]
0x140048ce7  lea     r9, aPathHhuRemoved; "Path[%hhu] Removed"
0x140048cee  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140048cf2  mov     [rsp+0C8h+var_A8], eax
0x140048cf6  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140048cfb  call    cs:__imp__snprintf_s
0x140048d02  nop     dword ptr [rax+rax+00h]
0x140048d07  lea     r9, [rsp+0C8h+DstBuf]
0x140048d0c  mov     r8, rbx
0x140048d0f  lea     rdx, QuicConnLogInfo
0x140048d16  call    McTemplateU0ps_EtwWriteTransfer
0x140048d1b  movzx   ecx, byte ptr [rbx+113h]
0x140048d22  lea     eax, [rdi+1]
0x140048d25  cmp     eax, ecx
0x140048d27  jnb     short loc_140048D50
0x140048d29  sub     ecx, edi
0x140048d2b  lea     rdx, [rbx+230h]
0x140048d32  add     rdx, rsi; Src
0x140048d35  lea     eax, [rcx-1]
0x140048d38  cdqe
0x140048d3a  lea     rcx, [rbx+140h]
0x140048d41  imul    r8, rax, 0F0h; Size
0x140048d48  add     rcx, rsi; void *
0x140048d4b  call    memmove
0x140048d50  dec     byte ptr [rbx+113h]
0x140048d56  movzx   eax, byte ptr [rbx+113h]
0x140048d5d  imul    rcx, rax, 0F0h
0x140048d64  and     byte ptr [rcx+rbx+141h], 0FEh
0x140048d6c  mov     rcx, [rsp+0C8h+var_18]
0x140048d74  xor     rcx, rsp; StackCookie
0x140048d77  call    __security_check_cookie
0x140048d7c  lea     r11, [rsp+0C8h+var_8]
0x140048d84  mov     rbx, [r11+20h]
0x140048d88  mov     rsi, [r11+28h]
0x140048d8c  mov     rsp, r11
0x140048d8f  pop     rdi
0x140048d90  retn
```
