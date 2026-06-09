# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x140004648`
- end: `0x1400046b3`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `107`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f54`
- `0x14000a6dc`
- `0x14000f0a4`
- `0x14000fabc`
- `0x1400108d0`
- `0x1400109e0`
- `0x1400179d8`
- `0x14001ae94`

## callees

- `0x140004648`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, unsigned __int64 a2, wchar_t *a3)
{
  wchar_t *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140004648  xor     r10d, r10d
0x14000464b  mov     r9, rcx
0x14000464e  test    rdx, rdx
0x140004651  jz      short loc_1400046A4
0x140004653  cmp     rdx, 7FFFFFFFh
0x14000465a  jbe     short loc_140004663
0x14000465c  mov     eax, 80070057h
0x140004661  jmp     short loc_1400046AE
0x140004663  mov     eax, 7FFFFFFEh
0x140004668  test    rax, rax
0x14000466b  jz      short loc_14000468B
0x14000466d  movzx   ecx, word ptr [r8]
0x140004671  test    cx, cx
0x140004674  jz      short loc_14000468B
0x140004676  mov     [r9], cx
0x14000467a  add     r8, 2
0x14000467e  add     r9, 2
0x140004682  dec     rax
0x140004685  sub     rdx, 1
0x140004689  jnz     short loc_140004668
0x14000468b  test    rdx, rdx
0x14000468e  lea     rcx, [r9-2]
0x140004692  cmovnz  rcx, r9
0x140004696  neg     rdx
0x140004699  sbb     eax, eax
0x14000469b  not     eax
0x14000469d  and     eax, 8007007Ah
0x1400046a2  jmp     short loc_1400046AE
0x1400046a4  mov     eax, 80070057h
0x1400046a9  test    rdx, rdx
0x1400046ac  jz      short locret_1400046B2
0x1400046ae  mov     [rcx], r10w
0x1400046b2  retn
```
