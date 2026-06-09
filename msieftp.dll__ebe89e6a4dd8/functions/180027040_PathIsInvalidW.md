# PathIsInvalidW

- ea: `0x180027040`
- end: `0x180027108`
- name: `PathIsInvalidW`
- size: `200`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800217e4`
- `0x180021888`

## callees

- `0x180002240`
- `0x18000958c`
- `0x180027040`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18002705c`
- `SHLWAPI!PathIsRelativeW` at `0x18002705c`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800270e1`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800270e1`

## pseudocode

```c
_BOOL8 __fastcall PathIsInvalidW(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  unsigned __int64 v2; // rax
  const wchar_t *v4; // r9
  __int64 v5; // r8
  unsigned __int16 *v6; // rax
  __int64 v7; // rcx
  unsigned __int16 *v8; // rcx
  unsigned __int16 v9[16]; // [rsp+20h] [rbp-38h] BYREF

  v1 = a1;
  if ( !PathIsRelativeW(a1) )
  {
    v2 = -1;
    do
      ++v2;
    while ( v1[v2] );
    if ( v2 >= 0xE )
      return 0;
    v4 = L".\\";
    v5 = 16;
    v6 = v9;
    v7 = 2147483646;
    do
    {
      if ( !v7 )
        break;
      if ( !*v4 )
        break;
      *v6++ = *v4++;
      --v7;
      --v5;
    }
    while ( v5 );
    v8 = v6 - 1;
    if ( v5 )
      v8 = v6;
    *v8 = 0;
    StringCchCatW(v9, 0x10u, v1);
    v1 = v9;
  }
  return RtlIsDosDeviceName_U(v1) != 0;
}

```

## disassembly

```asm
0x180027040  mov     [rsp+arg_8], rbx
0x180027045  push    rdi
0x180027046  sub     rsp, 50h
0x18002704a  mov     rax, cs:__security_cookie
0x180027051  xor     rax, rsp
0x180027054  mov     [rsp+58h+var_18], rax
0x180027059  mov     rbx, rcx
0x18002705c  call    cs:__imp_PathIsRelativeW
0x180027062  xor     edi, edi
0x180027064  test    eax, eax
0x180027066  jnz     short loc_1800270DE
0x180027068  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002706c  inc     rax
0x18002706f  cmp     [rbx+rax*2], di
0x180027073  jnz     short loc_18002706C
0x180027075  cmp     rax, 0Eh
0x180027079  jb      short loc_18002707F
0x18002707b  xor     eax, eax
0x18002707d  jmp     short loc_1800270F0
0x18002707f  mov     r10d, 10h
0x180027085  lea     r9, asc_18002C060; ".\\"
0x18002708c  mov     r8d, r10d
0x18002708f  lea     rax, [rsp+58h+var_38]
0x180027094  mov     ecx, 7FFFFFFEh
0x180027099  test    rcx, rcx
0x18002709c  jz      short loc_1800270BB
0x18002709e  movzx   edx, word ptr [r9]
0x1800270a2  test    dx, dx
0x1800270a5  jz      short loc_1800270BB
0x1800270a7  mov     [rax], dx
0x1800270aa  add     r9, 2
0x1800270ae  add     rax, 2
0x1800270b2  dec     rcx
0x1800270b5  sub     r8, 1
0x1800270b9  jnz     short loc_180027099
0x1800270bb  test    r8, r8
0x1800270be  lea     rcx, [rax-2]
0x1800270c2  mov     r8, rbx; unsigned __int16 *
0x1800270c5  mov     rdx, r10; unsigned __int64
0x1800270c8  cmovnz  rcx, rax
0x1800270cc  mov     [rcx], di
0x1800270cf  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x1800270d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800270d9  lea     rbx, [rsp+58h+var_38]
0x1800270de  mov     rcx, rbx; Name
0x1800270e1  call    cs:__imp_RtlIsDosDeviceName_U
0x1800270e7  test    eax, eax
0x1800270e9  mov     ecx, edi
0x1800270eb  setnz   cl
0x1800270ee  mov     eax, ecx
0x1800270f0  mov     rcx, [rsp+58h+var_18]
0x1800270f5  xor     rcx, rsp; StackCookie
0x1800270f8  call    __security_check_cookie
0x1800270fd  mov     rbx, [rsp+58h+arg_8]
0x180027102  add     rsp, 50h
0x180027106  pop     rdi
0x180027107  retn
```
