# StringCbCopyA(char *,unsigned __int64,char const *)

- ea: `0x140017a1c`
- end: `0x140017a6d`
- name: `?StringCbCopyA@@YAJPEAD_KPEBD@Z`
- size: `81`
- prototype: `__int64 __fastcall(char *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400140c8`
- `0x1400143a0`

## callees

- `0x140017a1c`

## pseudocode

```c
__int64 __fastcall StringCbCopyA(char *a1, __int64 a2, const char *a3)
{
  __int64 v4; // rax
  const char *v5; // rcx
  __int64 v6; // rdx
  char *v7; // rcx
  __int64 result; // rax

  v4 = 2147483646;
  v5 = "CredProvConsent";
  v6 = 8;
  do
  {
    if ( !v4 )
      break;
    if ( !*v5 )
      break;
    *a1++ = *v5++;
    --v4;
    --v6;
  }
  while ( v6 );
  v7 = a1 - 1;
  result = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v7 = a1;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x140017a1c  mov     r8, rcx
0x140017a1f  mov     eax, 7FFFFFFEh
0x140017a24  lea     rcx, aCredprovconsen; "CredProvConsent"
0x140017a2b  mov     edx, 8
0x140017a30  test    rax, rax
0x140017a33  jz      short loc_140017A4F
0x140017a35  mov     r9b, [rcx]
0x140017a38  test    r9b, r9b
0x140017a3b  jz      short loc_140017A4F
0x140017a3d  mov     [r8], r9b
0x140017a40  inc     rcx
0x140017a43  inc     r8
0x140017a46  dec     rax
0x140017a49  sub     rdx, 1
0x140017a4d  jnz     short loc_140017A30
0x140017a4f  mov     rax, rdx
0x140017a52  lea     rcx, [r8-1]
0x140017a56  neg     rax
0x140017a59  sbb     eax, eax
0x140017a5b  not     eax
0x140017a5d  and     eax, 8007007Ah
0x140017a62  test    rdx, rdx
0x140017a65  cmovnz  rcx, r8
0x140017a69  mov     byte ptr [rcx], 0
0x140017a6c  retn
```
