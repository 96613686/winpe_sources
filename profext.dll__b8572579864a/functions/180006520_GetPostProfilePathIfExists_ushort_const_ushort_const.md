# GetPostProfilePathIfExists(ushort const *,ushort const * *)

- ea: `0x180006520`
- end: `0x180006615`
- name: `?GetPostProfilePathIfExists@@YAXPEBGPEAPEBG@Z`
- size: `245`
- prototype: `void __fastcall(LPCWSTR lpStringSource, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800064b0`

## callees

- `0x180006520`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800065ab`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800065ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006600`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180006570`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180006570`

## pseudocode

```c
void __fastcall GetPostProfilePathIfExists(LPCWSTR lpStringSource, const unsigned __int16 **a2)
{
  __int64 v4; // rbx
  int StringOrdinal; // eax
  WCHAR StringValue[264]; // [rsp+30h] [rbp-228h] BYREF

  *a2 = 0;
  memset_0(StringValue, 0, 0x208u);
  if ( (int)GetBasicProfileFolderPath(5, 0, StringValue, 260) >= 0 )
  {
    v4 = -1;
    StringOrdinal = FindStringOrdinal(0x400000u, lpStringSource, -1, StringValue, -1, 1);
    if ( StringOrdinal <= -1 )
    {
      if ( !GetLastError() )
        *a2 = lpStringSource;
    }
    else
    {
      do
        ++v4;
      while ( StringValue[v4] );
      *a2 = &lpStringSource[v4 + StringOrdinal];
    }
  }
}

```

## disassembly

```asm
0x180006520  mov     [rsp+arg_18], rsi
0x180006525  push    rdi
0x180006526  sub     rsp, 250h
0x18000652d  mov     rax, cs:__security_cookie
0x180006534  xor     rax, rsp
0x180006537  mov     [rsp+258h+var_18], rax
0x18000653f  mov     rsi, rdx
0x180006542  mov     qword ptr [rdx], 0
0x180006549  mov     rdi, rcx
0x18000654c  xor     edx, edx; Val
0x18000654e  lea     rcx, [rsp+258h+StringValue]; void *
0x180006553  mov     r8d, 208h; Size
0x180006559  call    memset_0
0x18000655e  mov     r9d, 104h
0x180006564  lea     r8, [rsp+258h+StringValue]
0x180006569  xor     edx, edx
0x18000656b  mov     ecx, 5
0x180006570  call    cs:__imp_GetBasicProfileFolderPath
0x180006577  nop     dword ptr [rax+rax+00h]
0x18000657c  test    eax, eax
0x18000657e  js      short loc_1800065DE
0x180006580  mov     [rsp+258h+arg_10], rbx
0x180006588  lea     r9, [rsp+258h+StringValue]; lpStringValue
0x18000658d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006594  mov     [rsp+258h+bIgnoreCase], 1; bIgnoreCase
0x18000659c  mov     r8d, ebx; cchSource
0x18000659f  mov     [rsp+258h+cchValue], ebx; cchValue
0x1800065a3  mov     rdx, rdi; lpStringSource
0x1800065a6  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x1800065ab  call    cs:__imp_FindStringOrdinal
0x1800065b2  nop     dword ptr [rax+rax+00h]
0x1800065b7  cmp     eax, ebx
0x1800065b9  jle     short loc_180006600
0x1800065bb  lea     rcx, [rsp+258h+StringValue]
0x1800065c0  inc     rbx
0x1800065c3  cmp     word ptr [rcx+rbx*2], 0
0x1800065c8  jnz     short loc_1800065C0
0x1800065ca  cdqe
0x1800065cc  add     rax, rbx
0x1800065cf  lea     rax, [rdi+rax*2]
0x1800065d3  mov     [rsi], rax
0x1800065d6  mov     rbx, [rsp+258h+arg_10]
0x1800065de  mov     rcx, [rsp+258h+var_18]
0x1800065e6  xor     rcx, rsp; StackCookie
0x1800065e9  call    __security_check_cookie
0x1800065ee  mov     rsi, [rsp+258h+arg_18]
0x1800065f6  add     rsp, 250h
0x1800065fd  pop     rdi
0x1800065fe  retn
0x180006600  call    cs:__imp_GetLastError
0x180006607  nop     dword ptr [rax+rax+00h]
0x18000660c  test    eax, eax
0x18000660e  jnz     short loc_1800065D6
0x180006610  mov     [rsi], rdi
0x180006613  jmp     short loc_1800065D6
```
