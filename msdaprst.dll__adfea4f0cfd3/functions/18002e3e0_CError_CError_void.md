# CError::CError(void)

- ea: `0x18002e3e0`
- end: `0x18002e46e`
- name: `??0CError@@QEAA@XZ`
- size: `142`
- prototype: `CError *__fastcall(CError *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002dd84`
- `0x18002ebdc`

## callees

- `0x18002e3e0`

## string_xrefs

- `0x18002e3f1`: `resource dll.`

## pseudocode

```c
CError *__fastcall CError::CError(CError *this)
{
  const char *v1; // r9
  __int64 v3; // r8
  __int64 v4; // rax
  char *v5; // rcx
  char *v6; // rax

  *((_DWORD *)this + 1033) = 0;
  v1 = "resource dll.";
  v3 = 261;
  *((GUID *)this + 1) = GUID_NULL;
  *((_QWORD *)this + 552) = &word_18003A4D6;
  v4 = 2147483646;
  *(_QWORD *)this = 0;
  *((GUID *)this + 275) = GUID_NULL;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 553) = 0;
  v5 = (char *)this + 4136;
  do
  {
    if ( !v4 )
      break;
    if ( !*v1 )
      break;
    *v5++ = *v1++;
    --v4;
    --v3;
  }
  while ( v3 );
  v6 = v5 - 1;
  if ( v3 )
    v6 = v5;
  *v6 = 0;
  return this;
}

```

## disassembly

```asm
0x18002e3e0  xor     r11d, r11d
0x18002e3e3  lea     rax, word_18003A4D6
0x18002e3ea  mov     [rcx+1024h], r11d
0x18002e3f1  lea     r9, aResourceDll; "resource dll."
0x18002e3f8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002e3ff  mov     rdx, rcx
0x18002e402  mov     r8d, 105h
0x18002e408  movdqu  xmmword ptr [rcx+10h], xmm0
0x18002e40d  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18002e414  mov     [rcx+1140h], rax
0x18002e41b  mov     eax, 7FFFFFFEh
0x18002e420  mov     [rcx], r11
0x18002e423  movdqu  xmmword ptr [rcx+1130h], xmm1
0x18002e42b  mov     [rcx+8], r11
0x18002e42f  mov     [rcx+1148h], r11
0x18002e436  add     rcx, 1028h
0x18002e43d  test    rax, rax
0x18002e440  jz      short loc_18002E45C
0x18002e442  mov     r10b, [r9]
0x18002e445  test    r10b, r10b
0x18002e448  jz      short loc_18002E45C
0x18002e44a  mov     [rcx], r10b
0x18002e44d  inc     r9
0x18002e450  inc     rcx
0x18002e453  dec     rax
0x18002e456  sub     r8, 1
0x18002e45a  jnz     short loc_18002E43D
0x18002e45c  test    r8, r8
0x18002e45f  lea     rax, [rcx-1]
0x18002e463  cmovnz  rax, rcx
0x18002e467  mov     [rax], r11b
0x18002e46a  mov     rax, rdx
0x18002e46d  retn
```
