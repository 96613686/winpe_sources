# ATMallocExt

- ea: `0x140038670`
- end: `0x140038702`
- name: `ATMallocExt`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `38`
- callee_count: `1`
- tags: ``

## callers

- `0x1400318d4`
- `0x140031ed8`
- `0x14003247c`
- `0x140032b84`
- `0x140033950`
- `0x1400348e0`
- `0x1400350dc`
- `0x140035410`
- `0x140035de4`
- `0x140037640`
- `0x140037bb8`
- `0x140038710`
- `0x140038730`
- `0x140038e74`
- `0x14003bff8`
- `0x14004ad44`
- `0x14004dbf0`
- `0x14004e708`
- `0x140052a4c`
- `0x140061930`
- `0x140072eb0`
- `0x140074b48`
- `0x14007dc80`
- `0x14007dfe0`
- `0x14007e450`
- `0x14007f17c`
- `0x14007fa74`
- `0x1400800f8`
- `0x140081220`
- `0x1400816b0`
- `0x1400816f0`
- `0x1400819f0`
- `0x1400823e0`
- `0x140082500`
- `0x1400825e8`
- `0x140083af8`
- `0x140083ef0`
- `0x14008421c`

## callees

- `0x140038670`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1400386b0`
- `KERNEL32!GlobalAlloc` at `0x1400386b0`

## pseudocode

```c
_DWORD *__fastcall ATMallocExt(unsigned __int64 a1, __int64 a2, char a3, char a4)
{
  _DWORD *result; // rax
  int v6; // ebx
  _DWORD *v7; // rax

  result = 0;
  if ( a1 <= 0xFFFFFFF7 )
  {
    v6 = a1;
    if ( a3 )
      atm += a1 + 8;
    result = GlobalAlloc(a4 != 0 ? 0x40 : 0, a1 + 8);
    if ( result )
    {
      if ( !a3 )
        v6 = -v6;
      *result = v6;
      v7 = result + 1;
      *v7 = 1700947009;
      return v7 + 1;
    }
    else if ( a3 )
    {
      atm += -8 - v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140038670  mov     [rsp+arg_0], rbx
0x140038675  push    rdi
0x140038676  sub     rsp, 30h
0x14003867a  mov     dil, r8b
0x14003867d  mov     rdx, rcx
0x140038680  xor     eax, eax
0x140038682  mov     ecx, 0FFFFFFF7h
0x140038687  cmp     rdx, rcx
0x14003868a  ja      short loc_1400386F7
0x14003868c  mov     ebx, edx
0x14003868e  test    r8b, r8b
0x140038691  jz      short loc_1400386A4
0x140038693  mov     ecx, cs:atm
0x140038699  add     ecx, 8
0x14003869c  add     ecx, edx
0x14003869e  mov     cs:atm, ecx
0x1400386a4  add     rdx, 8; dwBytes
0x1400386a8  neg     r9b
0x1400386ab  sbb     ecx, ecx
0x1400386ad  and     ecx, 40h; uFlags
0x1400386b0  call    cs:__imp_GlobalAlloc
0x1400386b6  mov     [rsp+38h+var_18], rax
0x1400386bb  test    rax, rax
0x1400386be  jz      short loc_1400386E5
0x1400386c0  test    dil, dil
0x1400386c3  jz      short loc_1400386E1
0x1400386c5  mov     [rax], ebx
0x1400386c7  add     rax, 4
0x1400386cb  mov     [rsp+38h+var_18], rax
0x1400386d0  mov     dword ptr [rax], 65626441h
0x1400386d6  add     rax, 4
0x1400386da  mov     [rsp+38h+var_18], rax
0x1400386df  jmp     short loc_1400386F7
0x1400386e1  neg     ebx
0x1400386e3  jmp     short loc_1400386C5
0x1400386e5  test    dil, dil
0x1400386e8  jz      short loc_1400386F7
0x1400386ea  mov     ecx, 0FFFFFFF8h
0x1400386ef  sub     ecx, ebx
0x1400386f1  add     cs:atm, ecx
0x1400386f7  mov     rbx, [rsp+38h+arg_0]
0x1400386fc  add     rsp, 30h
0x140038700  pop     rdi
0x140038701  retn
0x140096a3e  push    rbp
0x140096a40  sub     rsp, 20h
0x140096a44  mov     rbp, rdx
0x140096a47  add     rsp, 20h
0x140096a4b  pop     rbp
0x140096a4c  retn
```
