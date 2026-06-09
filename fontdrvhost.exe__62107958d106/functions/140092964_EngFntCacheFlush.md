# EngFntCacheFlush

- ea: `0x140092964`
- end: `0x140092a4f`
- name: `EngFntCacheFlush`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14007eac4`
- `0x140092168`

## callees

- `0x140075de0`
- `0x140092964`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x14009298e`
- `KERNEL32!TlsGetValue` at `0x14009298e`
- `KERNEL32!GetProcessHeap` at `0x140092a15`
- `KERNEL32!GetProcessHeap` at `0x140092a15`
- `KERNEL32!HeapFree` at `0x140092a24`
- `KERNEL32!HeapFree` at `0x140092a24`
- `win32u!NtGdiExtEscape` at `0x140092a0f`
- `win32u!NtGdiExtEscape` at `0x140092a0f`

## pseudocode

```c
__int64 __fastcall EngFntCacheFlush(__int64 a1, int a2)
{
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  __int64 v6; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v7; // [rsp+48h] [rbp-11h]
  int v8; // [rsp+4Ch] [rbp-Dh]
  int v9; // [rsp+50h] [rbp-9h]
  int v10; // [rsp+54h] [rbp-5h]
  __int64 v11; // [rsp+58h] [rbp-1h]
  __int128 v12; // [rsp+60h] [rbp+7h]
  __int128 v13; // [rsp+70h] [rbp+17h] BYREF
  wchar_t v14; // [rsp+80h] [rbp+27h]

  result = (__int64)TlsGetValue(g_tlsIndex);
  if ( result )
  {
    v7 = *(_DWORD *)(result + 100);
    v8 = *(_DWORD *)(a1 - 16);
    v9 = *(_DWORD *)(a1 - 12);
    v6 = 8;
    v10 = 0;
    v11 = a1;
    v12 = 0;
    if ( !a2 )
    {
      v14 = aUmfdhost[8];
      v13 = *(_OWORD *)L"UmfdHost";
      ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
        0,
        &v13,
        9,
        19,
        48,
        &v6,
        48,
        &v6);
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(a1 - 16));
    result = v7;
    if ( a2 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140092964  push    rbp
0x140092966  push    rbx
0x140092967  push    rsi
0x140092968  push    rdi
0x140092969  lea     rbp, [rsp-3Fh]
0x14009296e  sub     rsp, 98h
0x140092975  mov     rax, cs:__security_cookie
0x14009297c  xor     rax, rsp
0x14009297f  mov     [rbp+57h+var_28], rax
0x140092983  mov     rdi, rcx
0x140092986  mov     esi, edx
0x140092988  mov     ecx, cs:g_tlsIndex; dwTlsIndex
0x14009298e  call    cs:__imp_TlsGetValue
0x140092994  test    rax, rax
0x140092997  jz      loc_140092A37
0x14009299d  mov     eax, [rax+64h]
0x1400929a0  xorps   xmm0, xmm0
0x1400929a3  mov     [rbp+57h+var_68], eax
0x1400929a6  mov     eax, [rdi-10h]
0x1400929a9  mov     [rbp+57h+var_64], eax
0x1400929ac  mov     eax, [rdi-0Ch]
0x1400929af  mov     [rbp+57h+var_60], eax
0x1400929b2  mov     [rbp+57h+var_70], 8
0x1400929ba  mov     [rbp+57h+var_5C], 0
0x1400929c1  mov     [rbp+57h+var_58], rdi
0x1400929c5  movdqu  [rbp+57h+var_50], xmm0
0x1400929ca  test    esi, esi
0x1400929cc  jnz     short loc_140092A15
0x1400929ce  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x1400929d5  lea     ecx, [rsi+30h]
0x1400929d8  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x1400929df  mov     [rbp+57h+var_30], ax
0x1400929e3  lea     r9d, [rsi+13h]
0x1400929e7  lea     rax, [rbp+57h+var_70]
0x1400929eb  mov     [rsp+0B0h+var_78], rax
0x1400929f0  lea     r8d, [rsi+9]
0x1400929f4  mov     [rsp+0B0h+var_80], ecx
0x1400929f8  lea     rax, [rbp+57h+var_70]
0x1400929fc  mov     [rsp+0B0h+var_88], rax
0x140092a01  lea     rdx, [rbp+57h+var_40]
0x140092a05  mov     [rsp+0B0h+var_90], ecx
0x140092a09  xor     ecx, ecx
0x140092a0b  movups  [rbp+57h+var_40], xmm0
0x140092a0f  call    cs:__imp_NtGdiExtEscape
0x140092a15  call    cs:__imp_GetProcessHeap
0x140092a1b  lea     r8, [rdi-10h]; lpMem
0x140092a1f  xor     edx, edx; dwFlags
0x140092a21  mov     rcx, rax; hHeap
0x140092a24  call    cs:__imp_HeapFree
0x140092a2a  mov     eax, [rbp+57h+var_68]
0x140092a2d  test    esi, esi
0x140092a2f  mov     ecx, 1
0x140092a34  cmovnz  eax, ecx
0x140092a37  mov     rcx, [rbp+57h+var_28]
0x140092a3b  xor     rcx, rsp; StackCookie
0x140092a3e  call    __security_check_cookie
0x140092a43  add     rsp, 98h
0x140092a4a  pop     rdi
0x140092a4b  pop     rsi
0x140092a4c  pop     rbx
0x140092a4d  pop     rbp
0x140092a4e  retn
```
