# mwDelete

- ea: `0x180003d64`
- end: `0x180003e57`
- name: `mwDelete`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003614`

## callees

- `0x180003410`
- `0x1800034a8`
- `0x180003568`
- `0x1800035d0`
- `0x180003d64`
- `0x1800050b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003e2d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003e2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e22`
- `USER32!PostThreadMessageW` at `0x180003e13`
- `USER32!PostThreadMessageW` at `0x180003e13`

## pseudocode

```c
__int64 __fastcall mwDelete(unsigned int *a1, char a2, __int64 a3)
{
  unsigned int *v6; // rdi
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // esi
  unsigned int v10; // edi
  DWORD v12; // ecx

  mwStop(a1);
  v6 = a1 + 19;
  if ( (a2 & 4) != 0 )
  {
    v7 = *(_DWORD *)(a3 + 8);
    if ( v7 > (unsigned int)bytes2time(a1, *v6, a1[2]) )
      return 282;
    v8 = RoundedBytePosition(a1, v7, a1[2]);
    v9 = *v6;
    if ( v8 <= *v6 )
      v9 = v8;
    if ( v9 == -1 )
      return 282;
  }
  else
  {
    v9 = a1[16];
  }
  if ( (a2 & 8) != 0 )
  {
    v10 = VerifyRangeEnd(a1, *(unsigned int *)(a3 + 12), 1);
    if ( v10 == -1 )
      return 282;
  }
  else
  {
    v10 = *v6;
  }
  if ( v10 < v9 )
    return 282;
  SetCurrentPosition(a1, v9);
  if ( v10 == v9 )
    return 0;
  v12 = a1[6];
  a1[18] = v10;
  a1[8] = 6;
  PostThreadMessageW(v12, 0x401u, 0, 0);
  while ( a1[8] != 2 )
  {
    LeaveCriticalSection(&CritSec);
    Sleep(0xAu);
    EnterCriticalSection(&CritSec);
  }
  return a1[35];
}

```

## disassembly

```asm
0x180003d64  push    rbx
0x180003d66  push    rbp
0x180003d67  push    rsi
0x180003d68  push    rdi
0x180003d69  push    r14
0x180003d6b  sub     rsp, 20h
0x180003d6f  mov     r14, r8
0x180003d72  mov     ebp, edx
0x180003d74  mov     rbx, rcx
0x180003d77  call    mwStop
0x180003d7c  lea     rdi, [rbx+4Ch]
0x180003d80  test    bpl, 4
0x180003d84  jz      short loc_180003DB8
0x180003d86  mov     r8d, [rbx+8]
0x180003d8a  mov     rcx, rbx
0x180003d8d  mov     edx, [rdi]
0x180003d8f  mov     esi, [r14+8]
0x180003d93  call    bytes2time
0x180003d98  cmp     esi, eax
0x180003d9a  ja      short loc_180003DE2
0x180003d9c  mov     r8d, [rbx+8]
0x180003da0  mov     edx, esi
0x180003da2  mov     rcx, rbx
0x180003da5  call    RoundedBytePosition
0x180003daa  mov     esi, [rdi]
0x180003dac  cmp     eax, esi
0x180003dae  cmovbe  esi, eax
0x180003db1  cmp     esi, 0FFFFFFFFh
0x180003db4  jz      short loc_180003DE2
0x180003db6  jmp     short loc_180003DBB
0x180003db8  mov     esi, [rbx+40h]
0x180003dbb  test    bpl, 8
0x180003dbf  jz      short loc_180003DDC
0x180003dc1  mov     edx, [r14+0Ch]
0x180003dc5  mov     r8d, 1
0x180003dcb  mov     rcx, rbx
0x180003dce  call    VerifyRangeEnd
0x180003dd3  mov     edi, eax
0x180003dd5  cmp     eax, 0FFFFFFFFh
0x180003dd8  jz      short loc_180003DE2
0x180003dda  jmp     short loc_180003DDE
0x180003ddc  mov     edi, [rdi]
0x180003dde  cmp     edi, esi
0x180003de0  jnb     short loc_180003DE9
0x180003de2  mov     eax, 11Ah
0x180003de7  jmp     short loc_180003E4C
0x180003de9  mov     edx, esi
0x180003deb  mov     rcx, rbx
0x180003dee  call    SetCurrentPosition
0x180003df3  cmp     edi, esi
0x180003df5  jnz     short loc_180003DFB
0x180003df7  xor     eax, eax
0x180003df9  jmp     short loc_180003E4C
0x180003dfb  mov     ecx, [rbx+18h]; idThread
0x180003dfe  xor     r9d, r9d; lParam
0x180003e01  xor     r8d, r8d; wParam
0x180003e04  mov     [rbx+48h], edi
0x180003e07  mov     edx, 401h; Msg
0x180003e0c  mov     dword ptr [rbx+20h], 6
0x180003e13  call    cs:__imp_PostThreadMessageW
0x180003e19  jmp     short loc_180003E40
0x180003e1b  lea     rcx, CritSec; lpCriticalSection
0x180003e22  call    cs:__imp_LeaveCriticalSection
0x180003e28  mov     ecx, 0Ah; dwMilliseconds
0x180003e2d  call    cs:__imp_Sleep
0x180003e33  lea     rcx, CritSec; lpCriticalSection
0x180003e3a  call    cs:__imp_EnterCriticalSection
0x180003e40  cmp     dword ptr [rbx+20h], 2
0x180003e44  jnz     short loc_180003E1B
0x180003e46  mov     eax, [rbx+8Ch]
0x180003e4c  add     rsp, 20h
0x180003e50  pop     r14
0x180003e52  pop     rdi
0x180003e53  pop     rsi
0x180003e54  pop     rbp
0x180003e55  pop     rbx
0x180003e56  retn
```
