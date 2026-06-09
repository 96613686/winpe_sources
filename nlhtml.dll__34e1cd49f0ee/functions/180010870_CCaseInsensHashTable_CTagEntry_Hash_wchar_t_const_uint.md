# CCaseInsensHashTable<CTagEntry *>::Hash(wchar_t const *,uint)

- ea: `0x180010870`
- end: `0x1800108ca`
- name: `?Hash@?$CCaseInsensHashTable@PEAVCTagEntry@@@@EEAAIPEB_WI@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180010870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001088f`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001088f`

## pseudocode

```c
__int64 __fastcall CCaseInsensHashTable<CTagEntry *>::Hash(__int64 a1, wint_t *a2, int a3)
{
  unsigned int v3; // ebx
  int i; // edi
  wint_t v6; // ax

  v3 = 0;
  for ( i = a3; i; --i )
  {
    v6 = towupper(*a2++);
    v3 = v6 + 31 * v3;
  }
  return v3 % 0xC7;
}

```

## disassembly

```asm
0x180010870  mov     [rsp+arg_0], rbx
0x180010875  mov     [rsp+arg_8], rsi
0x18001087a  push    rdi
0x18001087b  sub     rsp, 20h
0x18001087f  xor     ebx, ebx
0x180010881  mov     edi, r8d
0x180010884  mov     rsi, rdx
0x180010887  test    r8d, r8d
0x18001088a  jz      short loc_1800108A6
0x18001088c  movzx   ecx, word ptr [rsi]; C
0x18001088f  call    cs:__imp_towupper
0x180010895  imul    ebx, 1Fh
0x180010898  lea     rsi, [rsi+2]
0x18001089c  movzx   ecx, ax
0x18001089f  add     ebx, ecx
0x1800108a1  add     edi, 0FFFFFFFFh
0x1800108a4  jnz     short loc_18001088C
0x1800108a6  mov     rsi, [rsp+28h+arg_8]
0x1800108ab  mov     eax, 5254E78Fh
0x1800108b0  mul     ebx
0x1800108b2  shr     edx, 6
0x1800108b5  imul    eax, edx, 0C7h
0x1800108bb  sub     ebx, eax
0x1800108bd  mov     eax, ebx
0x1800108bf  mov     rbx, [rsp+28h+arg_0]
0x1800108c4  add     rsp, 20h
0x1800108c8  pop     rdi
0x1800108c9  retn
```
