# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008864`
- end: `0x1800088ff`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `155`
- prototype: `HRESULT __fastcall(unsigned __int16 *, __int64, WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004790`
- `0x180005ac0`

## callees

- `0x180008864`
- `0x180008944`

## pseudocode

```c
HRESULT __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, WCHAR *a3)
{
  HRESULT result; // eax
  __int64 v5; // r11
  __int64 v6; // rcx
  WCHAR *v7; // rdx
  size_t i; // r11
  WCHAR *v9; // rcx
  size_t v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  result = StringLengthWorkerW(&psz, 0x80u, &v10);
  if ( result >= 0 )
  {
    v6 = 2147483646;
    v7 = &psz + v10;
    for ( i = v5 - v10; i; --i )
    {
      if ( !v6 )
        break;
      if ( !*a3 )
        break;
      *v7++ = *a3++;
      --v6;
    }
    v9 = v7 - 1;
    if ( i )
      v9 = v7;
    result = i == 0 ? 0x8007007A : 0;
    *v9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008864  mov     rax, rsp
0x180008867  mov     [rax+8], rbx
0x18000886b  mov     [rax+18h], rsi
0x18000886f  mov     [rax+10h], rdx
0x180008873  push    rdi
0x180008874  sub     rsp, 20h
0x180008878  mov     r11d, 80h
0x18000887e  lea     rsi, psz
0x180008885  mov     rbx, r8
0x180008888  xor     edi, edi
0x18000888a  mov     edx, r11d; cchMax
0x18000888d  mov     [rax+10h], rdi
0x180008891  mov     rcx, rsi; psz
0x180008894  lea     r8, [rax+10h]; pcchLength
0x180008898  call    StringLengthWorkerW
0x18000889d  test    eax, eax
0x18000889f  js      short loc_1800088EF
0x1800088a1  mov     rax, [rsp+28h+arg_8]
0x1800088a6  mov     ecx, 7FFFFFFEh
0x1800088ab  lea     rdx, [rsi+rax*2]
0x1800088af  sub     r11, rax
0x1800088b2  jz      short loc_1800088D5
0x1800088b4  test    rcx, rcx
0x1800088b7  jz      short loc_1800088D5
0x1800088b9  movzx   eax, word ptr [rbx]
0x1800088bc  test    ax, ax
0x1800088bf  jz      short loc_1800088D5
0x1800088c1  mov     [rdx], ax
0x1800088c4  add     rbx, 2
0x1800088c8  add     rdx, 2
0x1800088cc  dec     rcx
0x1800088cf  sub     r11, 1
0x1800088d3  jnz     short loc_1800088B4
0x1800088d5  test    r11, r11
0x1800088d8  lea     rcx, [rdx-2]
0x1800088dc  cmovnz  rcx, rdx
0x1800088e0  neg     r11
0x1800088e3  sbb     eax, eax
0x1800088e5  not     eax
0x1800088e7  and     eax, 8007007Ah
0x1800088ec  mov     [rcx], di
0x1800088ef  mov     rbx, [rsp+28h+arg_0]
0x1800088f4  mov     rsi, [rsp+28h+arg_10]
0x1800088f9  add     rsp, 20h
0x1800088fd  pop     rdi
0x1800088fe  retn
```
