# TOKEN_KEY::ToHex(uchar *,ulong,STRU *)

- ea: `0x180011ca4`
- end: `0x180011d43`
- name: `?ToHex@TOKEN_KEY@@SAJPEAEKPEAVSTRU@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010fa0`

## callees

- `0x180011ca4`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011cce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011cce`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180011cbf`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180011cbf`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180011d32`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180011d32`

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::ToHex(unsigned __int8 *a1, unsigned int a2, struct STRU *a3)
{
  int v6; // edi
  unsigned __int16 *Str; // rax
  __int64 v8; // r9
  __int64 i; // r10
  __int64 v10; // r9
  unsigned int v11; // ecx

  v6 = STRU::Resize(a3, 4 * a2 + 2);
  if ( v6 >= 0 )
  {
    Str = STRU::QueryStr(a3);
    v8 = 0;
    for ( i = 0; (unsigned int)i < a2; v8 = (unsigned int)(v10 + 1) )
    {
      Str[v8] = (a1[i] >> 4) + 87 + (a1[i] >> 4 < 0xAu ? 0xFFD9 : 0);
      v10 = (unsigned int)(v8 + 1);
      v11 = a1[i] & 0xF;
      i = (unsigned int)(i + 1);
      Str[v10] = v11 + (v11 < 0xA ? 48 : 87);
    }
    STRU::SetLen(a3, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011ca4  push    rbx
0x180011ca6  push    rbp
0x180011ca7  push    rsi
0x180011ca8  push    rdi
0x180011ca9  sub     rsp, 28h
0x180011cad  mov     esi, edx
0x180011caf  mov     rbp, rcx
0x180011cb2  lea     edx, ds:2[rdx*4]
0x180011cb9  mov     rcx, r8
0x180011cbc  mov     rbx, r8
0x180011cbf  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180011cc5  mov     edi, eax
0x180011cc7  test    eax, eax
0x180011cc9  js      short loc_180011D38
0x180011ccb  mov     rcx, rbx
0x180011cce  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011cd4  xor     r9d, r9d
0x180011cd7  xor     r10d, r10d
0x180011cda  mov     r11, rax
0x180011cdd  test    esi, esi
0x180011cdf  jz      short loc_180011D2C
0x180011ce1  movzx   eax, byte ptr [r10+rbp]
0x180011ce6  shr     eax, 4
0x180011ce9  cmp     eax, 0Ah
0x180011cec  sbb     cx, cx
0x180011cef  add     ax, 57h ; 'W'
0x180011cf3  and     cx, 0FFD9h
0x180011cf8  add     cx, ax
0x180011cfb  mov     [r11+r9*2], cx
0x180011d00  inc     r9d
0x180011d03  movzx   ecx, byte ptr [r10+rbp]
0x180011d08  and     ecx, 0Fh
0x180011d0b  cmp     ecx, 0Ah
0x180011d0e  sbb     ax, ax
0x180011d11  inc     r10d
0x180011d14  and     ax, 0FFD9h
0x180011d18  add     ax, 57h ; 'W'
0x180011d1c  add     ax, cx
0x180011d1f  mov     [r11+r9*2], ax
0x180011d24  inc     r9d
0x180011d27  cmp     r10d, esi
0x180011d2a  jb      short loc_180011CE1
0x180011d2c  mov     edx, r9d
0x180011d2f  mov     rcx, rbx
0x180011d32  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180011d38  mov     eax, edi
0x180011d3a  add     rsp, 28h
0x180011d3e  pop     rdi
0x180011d3f  pop     rsi
0x180011d40  pop     rbp
0x180011d41  pop     rbx
0x180011d42  retn
```
