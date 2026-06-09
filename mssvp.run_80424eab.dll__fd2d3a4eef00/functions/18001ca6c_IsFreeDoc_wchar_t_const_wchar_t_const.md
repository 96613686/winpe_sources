# IsFreeDoc(wchar_t const *,wchar_t const *)

- ea: `0x18001ca6c`
- end: `0x18001cad5`
- name: `?IsFreeDoc@@YAHPEB_W0@Z`
- size: `105`
- prototype: `int(const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b814`
- `0x18001ce70`
- `0x18001ff80`

## callees

- `0x18001c9fc`
- `0x18001ca6c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cab2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cab2`

## pseudocode

```c
__int64 __fastcall IsFreeDoc(const wchar_t *a1, const wchar_t *a2)
{
  unsigned int i; // ebx

  if ( IsAttachment(a1) )
    return 0;
  for ( i = 0; i < 0xD; ++i )
  {
    if ( CompareStringW(0x7Fu, 1u, a2, -1, off_180040D60[i], -1) == 2 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001ca6c  mov     [rsp+arg_0], rbx
0x18001ca71  push    rdi
0x18001ca72  sub     rsp, 30h
0x18001ca76  mov     rdi, rdx
0x18001ca79  call    ?IsAttachment@@YAHPEB_W@Z; IsAttachment(wchar_t const *)
0x18001ca7e  test    eax, eax
0x18001ca80  jnz     short loc_18001CAC8
0x18001ca82  xor     ebx, ebx
0x18001ca84  cmp     ebx, 0Dh
0x18001ca87  jnb     short loc_18001CAC1
0x18001ca89  lea     rcx, off_180040D60; "MAPI/IPM.Note"
0x18001ca90  movsxd  rax, ebx
0x18001ca93  or      r9d, 0FFFFFFFFh; cchCount1
0x18001ca97  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001ca9f  mov     r8, rdi; lpString1
0x18001caa2  mov     rax, [rcx+rax*8]
0x18001caa6  lea     edx, [r9+2]; dwCmpFlags
0x18001caaa  mov     [rsp+38h+lpString2], rax; lpString2
0x18001caaf  lea     ecx, [rdx+7Eh]; Locale
0x18001cab2  call    cs:__imp_CompareStringW
0x18001cab8  cmp     eax, 2
0x18001cabb  jz      short loc_18001CAC8
0x18001cabd  inc     ebx
0x18001cabf  jmp     short loc_18001CA84
0x18001cac1  mov     eax, 1
0x18001cac6  jmp     short loc_18001CACA
0x18001cac8  xor     eax, eax
0x18001caca  mov     rbx, [rsp+38h+arg_0]
0x18001cacf  add     rsp, 30h
0x18001cad3  pop     rdi
0x18001cad4  retn
```
