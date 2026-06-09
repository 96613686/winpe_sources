# CCcs::Free(void)

- ea: `0x18006095c`
- end: `0x1800609e2`
- name: `?Free@CCcs@@QEAAXXZ`
- size: `134`
- prototype: `void __fastcall(CCcs *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800608a0`
- `0x180060e44`

## callees

- `0x18002720c`
- `0x180060928`
- `0x18006095c`

## import_xrefs

- `USP10!ScriptFreeCache` at `0x1800609c0`
- `USP10!ScriptFreeCache` at `0x1800609c0`

## pseudocode

```c
void __fastcall CCcs::Free(CCcs *this)
{
  _DWORD *v1; // rdi

  *(_QWORD *)((char *)this + 28) = 0;
  v1 = (_DWORD *)((char *)this + 40);
  *((_DWORD *)this + 9) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( *((CCcs **)this + 6) == (CCcs *)((char *)this + 40) )
  {
    v1 = (_DWORD *)*((_QWORD *)this + 6);
  }
  else
  {
    CW32System::FreePv(*((void **)this + 6));
    *((_QWORD *)this + 6) = v1;
  }
  *v1 = 0;
  if ( *((_QWORD *)this + 9) )
    CCcs::DestroyFont(this);
  if ( *((_QWORD *)this + 10) && g_pusp )
    ScriptFreeCache((SCRIPT_CACHE *)this + 10);
  *((_BYTE *)this + 123) &= ~1u;
  *((_WORD *)this + 5) = 0;
}

```

## disassembly

```asm
0x18006095c  mov     [rsp+arg_0], rbx
0x180060961  push    rdi
0x180060962  sub     rsp, 20h
0x180060966  xor     eax, eax
0x180060968  mov     qword ptr [rcx+1Ch], 0
0x180060970  lea     rdi, [rcx+28h]
0x180060974  mov     [rcx+24h], eax
0x180060977  mov     rbx, rcx
0x18006097a  mov     [rcx+10h], rax
0x18006097e  mov     [rcx+18h], eax
0x180060981  cmp     [rcx+30h], rdi
0x180060985  jz      short loc_180060996
0x180060987  mov     rcx, [rcx+30h]; lpMem
0x18006098b  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180060990  mov     [rbx+30h], rdi
0x180060994  jmp     short loc_18006099A
0x180060996  mov     rdi, [rcx+30h]
0x18006099a  xor     eax, eax
0x18006099c  mov     [rdi], eax
0x18006099e  cmp     [rbx+48h], rax
0x1800609a2  jz      short loc_1800609AC
0x1800609a4  mov     rcx, rbx; this
0x1800609a7  call    ?DestroyFont@CCcs@@AEAAXXZ; CCcs::DestroyFont(void)
0x1800609ac  lea     rcx, [rbx+50h]; psc
0x1800609b0  cmp     qword ptr [rcx], 0
0x1800609b4  jz      short loc_1800609CC
0x1800609b6  cmp     cs:?g_pusp@@3PEAVCUniscribe@@EA, 0; CUniscribe * g_pusp
0x1800609be  jz      short loc_1800609CC
0x1800609c0  call    cs:__imp_ScriptFreeCache
0x1800609c7  nop     dword ptr [rax+rax+00h]
0x1800609cc  and     byte ptr [rbx+7Bh], 0FEh
0x1800609d0  xor     eax, eax
0x1800609d2  mov     [rbx+0Ah], ax
0x1800609d6  mov     rbx, [rsp+28h+arg_0]
0x1800609db  add     rsp, 20h
0x1800609df  pop     rdi
0x1800609e0  retn
```
