# Helper::GetColorProfileFullPath(ushort const *,ushort *,ulong)

- ea: `0x180014284`
- end: `0x180014319`
- name: `?GetColorProfileFullPath@Helper@@YAJPEBGPEAGK@Z`
- size: `149`
- prototype: `signed int __fastcall(Helper *this, WCHAR *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f654`
- `0x180012438`

## callees

- `0x180009ed0`
- `0x180014284`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800142b7`
- `KERNEL32!GetLastError` at `0x1800142b7`
- `mscms!GetColorDirectoryW` at `0x1800142ab`
- `mscms!GetColorDirectoryW` at `0x1800142ab`

## pseudocode

```c
signed int __fastcall Helper::GetColorProfileFullPath(Helper *this, WCHAR *a2, unsigned __int16 *a3)
{
  unsigned __int64 v5; // rdx
  signed int result; // eax
  bool v7; // sf
  __int64 v8; // rax
  DWORD v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 520;
  if ( GetColorDirectoryW(0, a2, &v9) )
    goto LABEL_6;
  result = GetLastError();
  v7 = result < 0;
  if ( !result )
    return -2147467259;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
  {
LABEL_6:
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( a2[v8 - 1] == 92 )
      return StringCbCatW(a2, v5, (const unsigned __int16 *)this);
    result = StringCbCatW(a2, v5, L"\\");
    if ( result >= 0 )
      return StringCbCatW(a2, v5, (const unsigned __int16 *)this);
  }
  return result;
}

```

## disassembly

```asm
0x180014284  mov     rax, rsp
0x180014287  mov     [rax+8], rbx
0x18001428b  mov     [rax+10h], rsi
0x18001428f  mov     [rax+18h], r8d
0x180014293  push    rdi
0x180014294  sub     rsp, 20h
0x180014298  mov     rdi, rcx
0x18001429b  mov     dword ptr [rax+18h], 208h
0x1800142a2  xor     ecx, ecx; pMachineName
0x1800142a4  lea     r8, [rax+18h]; pdwSize
0x1800142a8  mov     rbx, rdx
0x1800142ab  call    cs:__imp_GetColorDirectoryW
0x1800142b1  xor     esi, esi
0x1800142b3  test    eax, eax
0x1800142b5  jnz     short loc_1800142CF
0x1800142b7  call    cs:__imp_GetLastError
0x1800142bd  test    eax, eax
0x1800142bf  jz      short loc_180014312
0x1800142c1  jle     short loc_1800142CD
0x1800142c3  movzx   eax, ax
0x1800142c6  or      eax, 80070000h
0x1800142cb  test    eax, eax
0x1800142cd  js      short loc_180014302
0x1800142cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800142d3  inc     rax
0x1800142d6  cmp     [rbx+rax*2], si
0x1800142da  jnz     short loc_1800142D3
0x1800142dc  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800142e2  jz      short loc_1800142F7
0x1800142e4  lea     r8, asc_18001CB4C; "\\"
0x1800142eb  mov     rcx, rbx; unsigned __int16 *
0x1800142ee  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800142f3  test    eax, eax
0x1800142f5  js      short loc_180014302
0x1800142f7  mov     r8, rdi; unsigned __int16 *
0x1800142fa  mov     rcx, rbx; unsigned __int16 *
0x1800142fd  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180014302  mov     rbx, [rsp+28h+arg_0]
0x180014307  mov     rsi, [rsp+28h+arg_8]
0x18001430c  add     rsp, 20h
0x180014310  pop     rdi
0x180014311  retn
0x180014312  mov     eax, 80004005h
0x180014317  jmp     short loc_180014302
```
