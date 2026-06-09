# CreateVersionDirectory(ushort *,ushort const *,ushort *,unsigned __int64)

- ea: `0x180006130`
- end: `0x180006252`
- name: `?CreateVersionDirectory@@YAJPEAGPEBG0_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, wchar_t *Destination, rsize_t SizeInWords)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002aec8`
- `0x18003145c`

## callees

- `0x180006130`
- `0x18000c1a8`
- `0x18000d614`
- `0x18000d8f0`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1800061e5`
- `KERNEL32!GetFullPathNameW` at `0x1800061e5`

## pseudocode

```c
__int64 __fastcall CreateVersionDirectory(wchar_t *Source, wchar_t *a2, wchar_t *Destination, rsize_t SizeInWords)
{
  unsigned __int64 v4; // rax
  __int64 v6; // rbx
  LPWSTR FilePart; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  v4 = -1;
  FilePart = 0;
  v6 = -1;
  do
    ++v6;
  while ( Source[v6] );
  do
    ++v4;
  while ( a2[v4] );
  if ( ~v6 < v4 || ~(v4 + v6) < 2 )
    return 2147500037LL;
  if ( v4 + v6 + 2 > SizeInWords )
    return 2147942522LL;
  wcscpy_s(Destination, SizeInWords, Source);
  if ( Destination[v6 - 1] != 92 )
    wcscat_s(Destination, SizeInWords, L"\\");
  wcscat_s(Destination, SizeInWords, a2);
  if ( GetFullPathNameW(Destination, 0x104u, Buffer, &FilePart) - 1 > 0x102 )
    return 2147942561LL;
  else
    return wcsicmp(Buffer, Destination) != 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x180006130  push    rbx
0x180006132  push    rbp
0x180006133  push    rsi
0x180006134  push    rdi
0x180006135  sub     rsp, 258h
0x18000613c  mov     rax, cs:__security_cookie
0x180006143  xor     rax, rsp
0x180006146  mov     [rsp+278h+var_38], rax
0x18000614e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006155  mov     [rsp+278h+FilePart], 0
0x18000615e  mov     rsi, r8
0x180006161  mov     rbx, rax
0x180006164  mov     rbp, r9
0x180006167  mov     rdi, rdx
0x18000616a  mov     r8, rcx; Source
0x18000616d  nop     dword ptr [rax]
0x180006170  inc     rbx
0x180006173  cmp     word ptr [rcx+rbx*2], 0
0x180006178  jnz     short loc_180006170
0x18000617a  nop     word ptr [rax+rax+00h]
0x180006180  inc     rax
0x180006183  cmp     word ptr [rdx+rax*2], 0
0x180006188  jnz     short loc_180006180
0x18000618a  mov     rcx, rbx
0x18000618d  not     rcx
0x180006190  cmp     rcx, rax
0x180006193  jb      loc_180006226
0x180006199  lea     rcx, [rax+rbx]
0x18000619d  mov     rax, rcx
0x1800061a0  not     rax
0x1800061a3  cmp     rax, 2
0x1800061a7  jb      short loc_180006226
0x1800061a9  lea     rax, [rcx+2]
0x1800061ad  cmp     rax, rbp
0x1800061b0  ja      short loc_18000622D
0x1800061b2  mov     rdx, rbp; SizeInWords
0x1800061b5  mov     rcx, rsi; Destination
0x1800061b8  call    wcscpy_s
0x1800061bd  cmp     word ptr [rsi+rbx*2-2], 5Ch ; '\'
0x1800061c3  jnz     short loc_180006234
0x1800061c5  mov     r8, rdi; Source
0x1800061c8  mov     rdx, rbp; SizeInWords
0x1800061cb  mov     rcx, rsi; Destination
0x1800061ce  call    wcscat_s
0x1800061d3  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x1800061d8  mov     edx, 104h; nBufferLength
0x1800061dd  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x1800061e2  mov     rcx, rsi; lpFileName
0x1800061e5  call    cs:__imp_GetFullPathNameW
0x1800061eb  dec     eax
0x1800061ed  cmp     eax, 102h
0x1800061f2  ja      short loc_18000624B
0x1800061f4  mov     rdx, rsi; String2
0x1800061f7  lea     rcx, [rsp+278h+Buffer]; String1
0x1800061fc  call    _wcsicmp
0x180006201  neg     eax
0x180006203  sbb     eax, eax
0x180006205  and     eax, 80070057h
0x18000620a  mov     rcx, [rsp+278h+var_38]
0x180006212  xor     rcx, rsp; StackCookie
0x180006215  call    __security_check_cookie
0x18000621a  add     rsp, 258h
0x180006221  pop     rdi
0x180006222  pop     rsi
0x180006223  pop     rbp
0x180006224  pop     rbx
0x180006225  retn
0x180006226  mov     eax, 80004005h
0x18000622b  jmp     short loc_18000620A
0x18000622d  mov     eax, 8007007Ah
0x180006232  jmp     short loc_18000620A
0x180006234  lea     r8, asc_18004C8C0; "\\"
0x18000623b  mov     rdx, rbp; SizeInWords
0x18000623e  mov     rcx, rsi; Destination
0x180006241  call    wcscat_s
0x180006246  jmp     loc_1800061C5
0x18000624b  mov     eax, 800700A1h
0x180006250  jmp     short loc_18000620A
```
