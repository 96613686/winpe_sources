# MULTISZ::AuxAppend(ushort const *,uint,int)

- ea: `0x1800033ac`
- end: `0x18000346d`
- name: `?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z`
- size: `193`
- prototype: `__int64 __fastcall(MULTISZ *__hidden this, const unsigned __int16 *Src, size_t Size, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180001d7c`
- `0x18000200c`
- `0x18000260c`
- `0x18000283c`

## callees

- `0x180003024`
- `0x1800033ac`
- `0x180003474`
- `0x180003605`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000345c`
- `KERNEL32!SetLastError` at `0x18000345c`

## pseudocode

```c
__int64 __fastcall MULTISZ::AuxAppend(MULTISZ *this, const unsigned __int16 *Src, size_t Size, int a4)
{
  size_t v5; // rdi
  int v7; // r10d
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx

  v5 = (unsigned int)Size;
  v7 = 2 * *((_DWORD *)this + 12);
  v8 = 0;
  if ( v7 != 4 )
    v8 = (unsigned int)(v7 - 2);
  v9 = (unsigned int)v8;
  v10 = v8 + (unsigned int)Size;
  if ( (unsigned __int64)(v10 + 4) > 0xFFFFFFFF )
    goto LABEL_9;
  if ( *((_DWORD *)this + 10) >= (unsigned int)(v10 + 4) )
  {
LABEL_8:
    memcpy_0((void *)(v9 + *((_QWORD *)this + 4)), Src, v5);
    *(_WORD *)(v9 + *((_QWORD *)this + 4) + v5) = 0;
    *(_WORD *)(v9 + *((_QWORD *)this + 4) + v5 + 2) = 0;
    *((_DWORD *)this + 12) = MULTISZ::CalcLength(*((const unsigned __int16 **)this + 4), (unsigned int *)this + 13);
    return 1;
  }
  v11 = v10 + (a4 != 0 ? 132LL : 4LL);
  if ( v11 > 0xFFFFFFFF )
  {
LABEL_9:
    SetLastError(0x216u);
  }
  else if ( (unsigned int)v11 <= *((_DWORD *)this + 10) || BUFFER::ReallocStorage(this, v11) )
  {
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800033ac  push    rbx
0x1800033ae  push    rbp
0x1800033af  push    rsi
0x1800033b0  push    rdi
0x1800033b1  sub     rsp, 28h
0x1800033b5  mov     eax, [rcx+30h]
0x1800033b8  mov     rbx, rcx
0x1800033bb  mov     edi, r8d
0x1800033be  mov     rbp, rdx
0x1800033c1  lea     r10d, [rax+rax]
0x1800033c5  xor     eax, eax
0x1800033c7  cmp     r10d, 4
0x1800033cb  lea     r8d, [r10-2]
0x1800033cf  cmovnz  eax, r8d
0x1800033d3  mov     r8d, 0FFFFFFFFh
0x1800033d9  mov     esi, eax
0x1800033db  lea     rcx, [rax+rdi]
0x1800033df  lea     rax, [rcx+4]
0x1800033e3  cmp     rax, r8
0x1800033e6  ja      short loc_180003457
0x1800033e8  cmp     [rbx+28h], eax
0x1800033eb  jnb     short loc_180003415
0x1800033ed  neg     r9d
0x1800033f0  sbb     rax, rax
0x1800033f3  and     eax, 80h
0x1800033f8  lea     rdx, [rax+4]
0x1800033fc  add     rdx, rcx; unsigned int
0x1800033ff  cmp     rdx, r8
0x180003402  ja      short loc_180003457
0x180003404  cmp     edx, [rbx+28h]
0x180003407  jbe     short loc_180003415
0x180003409  mov     rcx, rbx; this
0x18000340c  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180003411  test    al, al
0x180003413  jz      short loc_180003462
0x180003415  mov     rcx, [rbx+20h]
0x180003419  mov     r8, rdi; Size
0x18000341c  add     rcx, rsi; void *
0x18000341f  mov     rdx, rbp; Src
0x180003422  call    memcpy_0
0x180003427  mov     rcx, [rbx+20h]
0x18000342b  lea     rdx, [rbx+34h]; unsigned int *
0x18000342f  add     rcx, rsi
0x180003432  xor     eax, eax
0x180003434  mov     [rcx+rdi], ax
0x180003438  mov     rcx, [rbx+20h]
0x18000343c  add     rcx, rsi
0x18000343f  mov     [rcx+rdi+2], ax
0x180003444  mov     rcx, [rbx+20h]; unsigned __int16 *
0x180003448  call    ?CalcLength@MULTISZ@@SAKPEBGPEAK@Z; MULTISZ::CalcLength(ushort const *,ulong *)
0x18000344d  mov     [rbx+30h], eax
0x180003450  mov     eax, 1
0x180003455  jmp     short loc_180003464
0x180003457  mov     ecx, 216h; dwErrCode
0x18000345c  call    cs:__imp_SetLastError
0x180003462  xor     eax, eax
0x180003464  add     rsp, 28h
0x180003468  pop     rdi
0x180003469  pop     rsi
0x18000346a  pop     rbp
0x18000346b  pop     rbx
0x18000346c  retn
```
