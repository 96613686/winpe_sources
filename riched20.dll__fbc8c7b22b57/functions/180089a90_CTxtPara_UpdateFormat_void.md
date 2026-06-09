# CTxtPara::UpdateFormat(void)

- ea: `0x180089a90`
- end: `0x180089b0f`
- name: `?UpdateFormat@CTxtPara@@AEAAJXZ`
- size: `127`
- prototype: `__int64 __fastcall(CTxtPara *__hidden this)`
- caller_count: `12`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180086bf0`
- `0x180086d60`
- `0x180086e0c`
- `0x180087000`
- `0x1800871f0`
- `0x1800875f0`
- `0x1800879d8`
- `0x180087c60`
- `0x180088040`
- `0x180088350`
- `0x180088a80`
- `0x180088fd0`

## callees

- `0x180045fe4`
- `0x18004a868`
- `0x180089a90`
- `0x180093bbe`

## pseudocode

```c
__int64 __fastcall CTxtPara::UpdateFormat(CTxtPara *this)
{
  CTxtRange *v2; // rcx
  const int *v4; // rax
  size_t v5; // r9

  v2 = (CTxtRange *)*((_QWORD *)this + 2);
  if ( v2 && (*((_BYTE *)this + 84) & 2) == 0 )
  {
    if ( !*((_QWORD *)v2 + 6) )
    {
      *((_DWORD *)this + 20) = 0;
      return 2147746303LL;
    }
    *((_DWORD *)this + 20) = CTxtRange::GetParaFormat(v2, (CTxtPara *)((char *)this + 24), 0);
    if ( *((__int16 *)this + 21) >= 0 )
    {
      v4 = CTabsArray::Deref(qword_1800A72C0, *((__int16 *)this + 21));
      memmove_0((char *)this + 88, v4, v5);
      *((_WORD *)this + 21) = -1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180089a90  mov     [rsp+arg_0], rbx
0x180089a95  push    rdi
0x180089a96  sub     rsp, 20h
0x180089a9a  mov     rbx, rcx
0x180089a9d  xor     edi, edi
0x180089a9f  mov     rcx, [rcx+10h]; this
0x180089aa3  test    rcx, rcx
0x180089aa6  jz      short loc_180089B01
0x180089aa8  test    byte ptr [rbx+54h], 2
0x180089aac  jnz     short loc_180089B01
0x180089aae  cmp     [rcx+30h], rdi
0x180089ab2  jnz     short loc_180089ABE
0x180089ab4  mov     [rbx+50h], edi
0x180089ab7  mov     eax, 800401FFh
0x180089abc  jmp     short loc_180089B03
0x180089abe  lea     rdx, [rbx+18h]; struct CParaFormat *
0x180089ac2  xor     r8d, r8d; unsigned int
0x180089ac5  call    ?GetParaFormat@CTxtRange@@QEBAKPEAVCParaFormat@@K@Z; CTxtRange::GetParaFormat(CParaFormat *,ulong)
0x180089aca  mov     [rbx+50h], eax
0x180089acd  cmp     [rbx+2Ah], di
0x180089ad1  jl      short loc_180089B01
0x180089ad3  movzx   r9d, byte ptr [rbx+29h]
0x180089ad8  movsx   edx, word ptr [rbx+2Ah]; int
0x180089adc  mov     rcx, cs:qword_1800A72C0; this
0x180089ae3  shl     r9, 2
0x180089ae7  call    ?Deref@CTabsArray@@QEBAPEBJJ@Z; CTabsArray::Deref(long)
0x180089aec  mov     rdx, rax; Src
0x180089aef  lea     rcx, [rbx+58h]; void *
0x180089af3  mov     r8, r9; Size
0x180089af6  call    memmove_0
0x180089afb  mov     word ptr [rbx+2Ah], 0FFFFh
0x180089b01  xor     eax, eax
0x180089b03  mov     rbx, [rsp+28h+arg_0]
0x180089b08  add     rsp, 20h
0x180089b0c  pop     rdi
0x180089b0d  retn
```
