# CVersionInfo::GetComponentDescription(ulong,ushort * *)

- ea: `0x180008100`
- end: `0x180008143`
- name: `?GetComponentDescription@CVersionInfo@@UEAAJKPEAPEAG@Z`
- size: `67`
- prototype: `__int64 __fastcall(CVersionInfo *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008100`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008132`
- `OLEAUT32!__imp_SysAllocString` at `0x180008132`

## pseudocode

```c
__int64 __fastcall CVersionInfo::GetComponentDescription(CVersionInfo *this, unsigned int a2, unsigned __int16 **a3)
{
  __int64 v3; // r9

  v3 = *((_QWORD *)this + 1);
  if ( a2 > (unsigned __int64)((*((_QWORD *)this + 2) - v3) >> 3) )
    return 2147942487LL;
  _mm_lfence();
  *a3 = SysAllocString(*(const OLECHAR **)(*(_QWORD *)(v3 + 8LL * a2) + 24LL));
  return 0;
}

```

## disassembly

```asm
0x180008100  push    rbx
0x180008102  sub     rsp, 20h
0x180008106  mov     r9, [rcx+8]
0x18000810a  mov     rbx, r8
0x18000810d  mov     rax, [rcx+10h]
0x180008111  sub     rax, r9
0x180008114  mov     r10d, edx
0x180008117  sar     rax, 3
0x18000811b  cmp     r10, rax
0x18000811e  jbe     short loc_180008127
0x180008120  mov     eax, 80070057h
0x180008125  jmp     short loc_18000813D
0x180008127  lfence
0x18000812a  mov     rcx, [r9+r10*8]
0x18000812e  mov     rcx, [rcx+18h]; psz
0x180008132  call    cs:__imp_SysAllocString
0x180008138  mov     [rbx], rax
0x18000813b  xor     eax, eax
0x18000813d  add     rsp, 20h
0x180008141  pop     rbx
0x180008142  retn
```
