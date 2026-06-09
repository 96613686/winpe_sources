# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140006070`
- end: `0x1400060fb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005188`
- `0x140009240`
- `0x1400094a4`
- `0x140009b50`
- `0x140009c48`
- `0x14000e5f8`

## callees

- `0x140006070`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400060af`
- `msvcrt!_vsnwprintf` at `0x1400060af`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140006070  mov     [rsp+arg_10], r8
0x140006075  mov     qword ptr [rsp+Args], r9
0x14000607a  push    rbx
0x14000607b  push    rdi
0x14000607c  sub     rsp, 38h
0x140006080  mov     rax, rdx
0x140006083  mov     rdi, rcx
0x140006086  test    rdx, rdx
0x140006089  jz      short loc_1400060E2
0x14000608b  cmp     rax, 7FFFFFFFh
0x140006091  jbe     short loc_14000609A
0x140006093  mov     edx, 80070057h
0x140006098  jmp     short loc_1400060EC
0x14000609a  lea     rbx, [rdx-1]
0x14000609e  mov     [rsp+48h+var_28], 0
0x1400060a7  mov     rdx, rbx; BufferCount
0x1400060aa  lea     r9, [rsp+48h+Args]; Args
0x1400060af  call    cs:__imp__vsnwprintf
0x1400060b6  nop     dword ptr [rax+rax+00h]
0x1400060bb  test    eax, eax
0x1400060bd  js      short loc_1400060D5
0x1400060bf  cdqe
0x1400060c1  cmp     rax, rbx
0x1400060c4  ja      short loc_1400060D5
0x1400060c6  xor     edx, edx
0x1400060c8  cmp     rax, rbx
0x1400060cb  jnz     short loc_1400060F1
0x1400060cd  xor     eax, eax
0x1400060cf  mov     [rdi+rbx*2], ax
0x1400060d3  jmp     short loc_1400060F1
0x1400060d5  xor     eax, eax
0x1400060d7  mov     edx, 8007007Ah
0x1400060dc  mov     [rdi+rbx*2], ax
0x1400060e0  jmp     short loc_1400060F1
0x1400060e2  mov     edx, 80070057h
0x1400060e7  test    rax, rax
0x1400060ea  jz      short loc_1400060F1
0x1400060ec  xor     ecx, ecx
0x1400060ee  mov     [rdi], cx
0x1400060f1  mov     eax, edx
0x1400060f3  add     rsp, 38h
0x1400060f7  pop     rdi
0x1400060f8  pop     rbx
0x1400060f9  retn
```
