# TranslateConsoleTitle(wchar_t const *)

- ea: `0x18000811c`
- end: `0x1800082b3`
- name: `?TranslateConsoleTitle@@YAPEA_WPEB_W@Z`
- size: `407`
- prototype: `wchar_t *__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000752c`

## callees

- `0x180001980`
- `0x1800019bc`
- `0x180008070`
- `0x18000811c`
- `0x180018d18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000822b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000822b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008217`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008217`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800081e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800081e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000816a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000816a`

## pseudocode

```c
wchar_t *__fastcall TranslateConsoleTitle(const wchar_t *a1)
{
  wchar_t *v2; // rbx
  WCHAR *v3; // rax
  WCHAR *v4; // rbp
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r15
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  size_t v9; // r14
  HANDLE ProcessHeap; // rax
  wchar_t *result; // rax
  wchar_t *i; // rax
  unsigned __int64 v13; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int64 v14; // [rsp+80h] [rbp+18h] BYREF

  v14 = 0;
  v13 = 0;
  v2 = 0;
  v3 = (WCHAR *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
    return v2;
  if ( !GetWindowsDirectoryW(v3, 0x104u)
    || (int)StringCbLengthW(a1, 0x7FFFFFFFu, &v14) < 0
    || (int)StringCbLengthW(v4, 0x104u, &v13) < 0 )
  {
LABEL_15:
    operator delete(v4, v5);
    return v2;
  }
  v6 = v14 >> 1;
  v7 = v14 + 2;
  v8 = v13 >> 1;
  if ( (int)(v14 >> 1) >= (int)(v13 >> 1) && CompareStringOrdinal(a1, v8, v4, v8, 1) == 2 )
  {
    v7 -= v13;
    v9 = 24;
    a1 += (int)v8;
  }
  else
  {
    v9 = 0;
  }
  ProcessHeap = GetProcessHeap();
  result = (wchar_t *)HeapAlloc(ProcessHeap, 0, 2LL * ((int)v6 + (int)v8));
  v2 = result;
  if ( result )
  {
    memmove_0(result, L"%SystemRoot%", v9);
    v5 = 0;
    for ( i = &v2[v9 >> 1]; (unsigned int)v5 < v7; ++a1 )
    {
      if ( *a1 == 92 )
      {
        *i = 95;
      }
      else
      {
        *i = *a1;
        if ( !*a1 )
          goto LABEL_15;
      }
      v5 = (unsigned int)(v5 + 2);
      ++i;
    }
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x18000811c  mov     rax, rsp
0x18000811f  mov     [rax+8], rbx
0x180008123  push    rbp
0x180008124  push    rsi
0x180008125  push    rdi
0x180008126  push    r12
0x180008128  push    r13
0x18000812a  push    r14
0x18000812c  push    r15
0x18000812e  sub     rsp, 30h
0x180008132  xor     r13d, r13d
0x180008135  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000813c  mov     rsi, rcx
0x18000813f  mov     [rax+18h], r13
0x180008143  mov     ecx, 208h; unsigned __int64
0x180008148  mov     [rax+10h], r13
0x18000814c  mov     ebx, r13d
0x18000814f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008154  mov     rbp, rax
0x180008157  test    rax, rax
0x18000815a  jz      loc_18000829A
0x180008160  mov     edi, 104h
0x180008165  mov     rcx, rax; lpBuffer
0x180008168  mov     edx, edi; uSize
0x18000816a  call    cs:__imp_GetWindowsDirectoryW
0x180008171  nop     dword ptr [rax+rax+00h]
0x180008176  test    eax, eax
0x180008178  jz      loc_180008292
0x18000817e  lea     r8, [rsp+68h+arg_10]; unsigned __int64 *
0x180008186  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000818b  mov     rcx, rsi; wchar_t *
0x18000818e  call    ?StringCbLengthW@@YAJPEB_W_KPEA_K@Z; StringCbLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180008193  test    eax, eax
0x180008195  js      loc_180008292
0x18000819b  lea     r8, [rsp+68h+arg_8]; unsigned __int64 *
0x1800081a0  mov     edx, edi; unsigned __int64
0x1800081a2  mov     rcx, rbp; wchar_t *
0x1800081a5  call    ?StringCbLengthW@@YAJPEB_W_KPEA_K@Z; StringCbLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1800081aa  test    eax, eax
0x1800081ac  js      loc_180008292
0x1800081b2  mov     rdi, [rsp+68h+arg_10]
0x1800081ba  mov     rbx, [rsp+68h+arg_8]
0x1800081bf  mov     r15, rdi
0x1800081c2  shr     r15, 1
0x1800081c5  add     rdi, 2
0x1800081c9  shr     rbx, 1
0x1800081cc  cmp     r15d, ebx
0x1800081cf  jl      short loc_180008207
0x1800081d1  mov     r9d, ebx; cchCount2
0x1800081d4  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800081dc  mov     r8, rbp; lpString2
0x1800081df  mov     edx, ebx; cchCount1
0x1800081e1  mov     rcx, rsi; lpString1
0x1800081e4  call    cs:__imp_CompareStringOrdinal
0x1800081eb  nop     dword ptr [rax+rax+00h]
0x1800081f0  cmp     eax, 2
0x1800081f3  jnz     short loc_180008207
0x1800081f5  sub     rdi, [rsp+68h+arg_8]
0x1800081fa  lea     r14d, [r13+18h]
0x1800081fe  movsxd  rax, ebx
0x180008201  lea     rsi, [rsi+rax*2]
0x180008205  jmp     short loc_18000820A
0x180008207  mov     r14, r13
0x18000820a  lea     eax, [r15+rbx]
0x18000820e  mov     r12, rdi
0x180008211  movsxd  rbx, eax
0x180008214  add     rbx, rbx
0x180008217  call    cs:__imp_GetProcessHeap
0x18000821e  nop     dword ptr [rax+rax+00h]
0x180008223  mov     r8, rbx; dwBytes
0x180008226  xor     edx, edx; dwFlags
0x180008228  mov     rcx, rax; hHeap
0x18000822b  call    cs:__imp_HeapAlloc
0x180008232  nop     dword ptr [rax+rax+00h]
0x180008237  mov     rbx, rax
0x18000823a  test    rax, rax
0x18000823d  jz      short loc_18000829D
0x18000823f  mov     r8, r14; Size
0x180008242  lea     rdx, aSystemroot; "%SystemRoot%"
0x180008249  mov     rcx, rbx; void *
0x18000824c  call    memmove_0
0x180008251  shr     r14, 1
0x180008254  mov     edx, r13d
0x180008257  lea     rax, [rbx+r14*2]
0x18000825b  test    r12, r12
0x18000825e  jz      short loc_180008292
0x180008260  mov     r8d, 2
0x180008266  movzx   ecx, word ptr [rsi]
0x180008269  cmp     cx, 5Ch ; '\'
0x18000826d  jnz     short loc_180008276
0x18000826f  mov     word ptr [rax], 5Fh ; '_'
0x180008274  jmp     short loc_18000827F
0x180008276  mov     [rax], cx
0x180008279  cmp     [rsi], r13w
0x18000827d  jz      short loc_180008292
0x18000827f  mov     rcx, r8
0x180008282  add     edx, r8d; unsigned __int64
0x180008285  add     rax, rcx
0x180008288  add     rsi, r8
0x18000828b  mov     ecx, edx
0x18000828d  cmp     rcx, rdi
0x180008290  jb      short loc_180008266
0x180008292  mov     rcx, rbp; void *
0x180008295  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000829a  mov     rax, rbx
0x18000829d  mov     rbx, [rsp+68h+arg_0]
0x1800082a2  add     rsp, 30h
0x1800082a6  pop     r15
0x1800082a8  pop     r14
0x1800082aa  pop     r13
0x1800082ac  pop     r12
0x1800082ae  pop     rdi
0x1800082af  pop     rsi
0x1800082b0  pop     rbp
0x1800082b1  retn
```
