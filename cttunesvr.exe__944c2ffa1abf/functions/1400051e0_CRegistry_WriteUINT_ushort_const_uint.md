# CRegistry::WriteUINT(ushort const *,uint)

- ea: `0x1400051e0`
- end: `0x140005226`
- name: `?WriteUINT@CRegistry@@QEAA_NPEBGI@Z`
- size: `70`
- prototype: `char __fastcall(CRegistry *this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140004c30`
- `0x140004d20`
- `0x140004dd0`

## callees

- `0x1400051e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000520b`
- `ADVAPI32!RegSetValueExW` at `0x14000520b`

## pseudocode

```c
char __fastcall CRegistry::WriteUINT(CRegistry *this, const unsigned __int16 *a2, int a3)
{
  char v3; // bl
  HKEY v4; // rcx
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  if ( *(_BYTE *)this )
  {
    v4 = (HKEY)*((_QWORD *)this + 1);
    v6 = a3;
    return RegSetValueExW(v4, a2, 0, 4u, (const BYTE *)&v6, 4u) == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1400051e0  mov     r11, rsp
0x1400051e3  push    rbx
0x1400051e4  sub     rsp, 30h
0x1400051e8  xor     bl, bl
0x1400051ea  cmp     [rcx], bl
0x1400051ec  jz      short loc_14000521E
0x1400051ee  mov     rcx, [rcx+8]; hKey
0x1400051f2  lea     rax, [r11+8]
0x1400051f6  mov     r9d, 4; dwType
0x1400051fc  mov     [r11+8], r8d
0x140005200  mov     [r11-10h], r9d
0x140005204  xor     r8d, r8d; Reserved
0x140005207  mov     [r11-18h], rax
0x14000520b  call    cs:__imp_RegSetValueExW
0x140005211  movzx   ebx, bl
0x140005214  mov     ecx, 1
0x140005219  test    eax, eax
0x14000521b  cmovz   ebx, ecx
0x14000521e  mov     al, bl
0x140005220  add     rsp, 30h
0x140005224  pop     rbx
0x140005225  retn
```
