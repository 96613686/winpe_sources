# PtFuncCompare

- ea: `0x1800e6d10`
- end: `0x1800e6d80`
- name: `PtFuncCompare`
- size: `112`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800f2540`

## callees

- `0x1800e6d10`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1800e6d48`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1800e6d48`

## pseudocode

```c
__int64 __fastcall PtFuncCompare(_QWORD *a1, _QWORD *a2)
{
  unsigned __int16 *v2; // rax
  const WCHAR *v3; // rcx
  unsigned __int64 v4; // r10
  unsigned __int16 *v5; // rax
  const WCHAR *v6; // r8
  LONG v7; // ecx

  v2 = (unsigned __int16 *)a1[1];
  if ( *(_BYTE *)a1 == 2 )
  {
    v3 = v2 + 8;
    ++v2;
  }
  else
  {
    v3 = (const WCHAR *)*((_QWORD *)v2 + 1);
  }
  v4 = *v2;
  v5 = (unsigned __int16 *)a2[1];
  if ( *(_BYTE *)a2 == 2 )
  {
    v6 = v5 + 8;
    ++v5;
  }
  else
  {
    v6 = (const WCHAR *)*((_QWORD *)v5 + 1);
  }
  v7 = RtlCompareUnicodeStrings(v3, v4 >> 1, v6, (unsigned __int64)*v5 >> 1, 0);
  if ( v7 <= 0 )
    return (unsigned int)(v7 >= 0) - 1;
  else
    return 1;
}

```

## disassembly

```asm
0x1800e6d10  sub     rsp, 38h
0x1800e6d14  cmp     byte ptr [rcx], 2
0x1800e6d17  mov     rax, [rcx+8]
0x1800e6d1b  jz      short loc_1800E6D70
0x1800e6d1d  mov     rcx, [rax+8]; String1
0x1800e6d21  cmp     byte ptr [rdx], 2
0x1800e6d24  movzx   r10d, word ptr [rax]
0x1800e6d28  mov     rax, [rdx+8]
0x1800e6d2c  jnz     short loc_1800E6D7A
0x1800e6d2e  lea     r8, [rax+10h]; String2
0x1800e6d32  add     rax, 2
0x1800e6d36  movzx   r9d, word ptr [rax]
0x1800e6d3a  mov     rdx, r10
0x1800e6d3d  shr     r9, 1; String2Length
0x1800e6d40  shr     rdx, 1; String1Length
0x1800e6d43  mov     [rsp+38h+CaseInSensitive], 0; CaseInSensitive
0x1800e6d48  call    cs:RtlCompareUnicodeStrings
0x1800e6d4f  nop     dword ptr [rax+rax+00h]
0x1800e6d54  mov     ecx, eax
0x1800e6d56  test    eax, eax
0x1800e6d58  jle     short loc_1800E6D65
0x1800e6d5a  mov     eax, 1
0x1800e6d5f  add     rsp, 38h
0x1800e6d63  retn
0x1800e6d65  xor     eax, eax
0x1800e6d67  test    ecx, ecx
0x1800e6d69  setns   al
0x1800e6d6c  dec     eax
0x1800e6d6e  jmp     short loc_1800E6D5F
0x1800e6d70  lea     rcx, [rax+10h]
0x1800e6d74  add     rax, 2
0x1800e6d78  jmp     short loc_1800E6D21
0x1800e6d7a  mov     r8, [rax+8]
0x1800e6d7e  jmp     short loc_1800E6D36
```
