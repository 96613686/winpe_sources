# GetApplicationPathFromWin32Manifest(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x18003fff4`
- end: `0x18004011f`
- name: `?GetApplicationPathFromWin32Manifest@@YAJPEAG_KPEA_K@Z`
- size: `299`
- prototype: `__int64 __fastcall(wchar_t *Destination, rsize_t SizeInWords, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009af4`

## callees

- `0x18000c1a8`
- `0x18003fff4`
- `0x180041ac0`
- `0x180041b20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004005a`
- `KERNEL32!GetLastError` at `0x18004005a`
- `KERNEL32!QueryActCtxW` at `0x18004004c`
- `KERNEL32!QueryActCtxW` at `0x1800400b1`
- `KERNEL32!QueryActCtxW` at `0x18004004c`
- `KERNEL32!QueryActCtxW` at `0x1800400b1`

## pseudocode

```c
__int64 __fastcall GetApplicationPathFromWin32Manifest(wchar_t *Destination, rsize_t SizeInWords, unsigned __int64 *a3)
{
  unsigned int v6; // esi
  unsigned __int64 v7; // rbx
  SIZE_T v8; // rax
  void *v9; // rsp
  __int64 v10; // rax
  SIZE_T pcbWrittenOrRequired; // [rsp+40h] [rbp+0h] BYREF
  int v13; // [rsp+5Ch] [rbp+1Ch]
  const wchar_t *v14; // [rsp+78h] [rbp+38h]

  pcbWrittenOrRequired = 0;
  v6 = 0;
  v7 = 0;
  if ( !QueryActCtxW(0, 0, 0, 2u, 0, 0, &pcbWrittenOrRequired) && GetLastError() == 122 )
  {
    v8 = pcbWrittenOrRequired + 15;
    if ( pcbWrittenOrRequired + 15 < pcbWrittenOrRequired )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( QueryActCtxW(0, 0, 0, 2u, &pcbWrittenOrRequired, pcbWrittenOrRequired, &pcbWrittenOrRequired)
      && v13 == 2
      && v14 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v14[v10] );
      v7 = v10 + 1;
      if ( v10 + 1 <= SizeInWords && Destination )
        wcscpy_s(Destination, SizeInWords, v14);
      else
        v6 = -2147024774;
    }
  }
  if ( a3 )
    *a3 = v7;
  return v6;
}

```

## disassembly

```asm
0x18003fff4  push    rbp
0x18003fff6  push    rbx
0x18003fff7  push    rsi
0x18003fff8  push    rdi
0x18003fff9  push    r12
0x18003fffb  push    r13
0x18003fffd  push    r14
0x18003ffff  push    r15
0x180040001  sub     rsp, 58h
0x180040005  lea     rbp, [rsp+40h]
0x18004000a  mov     rax, cs:__security_cookie
0x180040011  xor     rax, rbp
0x180040014  mov     [rbp+50h+var_48], rax
0x180040018  xor     r13d, r13d
0x18004001b  lea     rax, [rbp+50h+var_50]
0x18004001f  mov     [rsp+90h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x180040024  mov     r14, r8
0x180040027  mov     r12, rdx
0x18004002a  mov     [rsp+90h+cbBuffer], r13; cbBuffer
0x18004002f  mov     r15, rcx
0x180040032  mov     [rbp+50h+var_50], r13
0x180040036  lea     r9d, [r13+2]; ulInfoClass
0x18004003a  mov     [rsp+90h+pvBuffer], r13; pvBuffer
0x18004003f  xor     r8d, r8d; pvSubInstance
0x180040042  xor     edx, edx; hActCtx
0x180040044  xor     ecx, ecx; dwFlags
0x180040046  mov     esi, r13d
0x180040049  mov     ebx, r13d
0x18004004c  call    cs:__imp_QueryActCtxW
0x180040052  test    eax, eax
0x180040054  jnz     loc_1800400F8
0x18004005a  call    cs:__imp_GetLastError
0x180040060  cmp     eax, 7Ah ; 'z'
0x180040063  jnz     loc_1800400F8
0x180040069  mov     rcx, [rbp+50h+var_50]
0x18004006d  lea     rax, [rcx+0Fh]
0x180040071  cmp     rax, rcx
0x180040074  ja      short loc_180040080
0x180040076  mov     rax, 0FFFFFFFFFFFFFF0h
0x180040080  and     rax, 0FFFFFFFFFFFFFFF0h
0x180040084  call    _alloca_probe
0x180040089  sub     rsp, rax
0x18004008c  mov     r9d, 2; ulInfoClass
0x180040092  lea     rax, [rbp+50h+var_50]
0x180040096  xor     r8d, r8d; pvSubInstance
0x180040099  xor     edx, edx; hActCtx
0x18004009b  mov     [rsp+90h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x1800400a0  lea     rdi, [rsp+90h+var_50]
0x1800400a5  mov     [rsp+90h+cbBuffer], rcx; cbBuffer
0x1800400aa  xor     ecx, ecx; dwFlags
0x1800400ac  mov     [rsp+90h+pvBuffer], rdi; pvBuffer
0x1800400b1  call    cs:__imp_QueryActCtxW
0x1800400b7  test    eax, eax
0x1800400b9  jz      short loc_1800400F8
0x1800400bb  cmp     dword ptr [rdi+1Ch], 2
0x1800400bf  jnz     short loc_1800400F8
0x1800400c1  mov     r8, [rdi+38h]; Source
0x1800400c5  test    r8, r8
0x1800400c8  jz      short loc_1800400F8
0x1800400ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800400ce  inc     rax
0x1800400d1  cmp     [r8+rax*2], r13w
0x1800400d6  jnz     short loc_1800400CE
0x1800400d8  lea     rbx, [rax+1]
0x1800400dc  cmp     rbx, r12
0x1800400df  ja      short loc_1800400F3
0x1800400e1  test    r15, r15
0x1800400e4  jz      short loc_1800400F3
0x1800400e6  mov     rdx, r12; SizeInWords
0x1800400e9  mov     rcx, r15; Destination
0x1800400ec  call    wcscpy_s
0x1800400f1  jmp     short loc_1800400F8
0x1800400f3  mov     esi, 8007007Ah
0x1800400f8  test    r14, r14
0x1800400fb  jz      short loc_180040100
0x1800400fd  mov     [r14], rbx
0x180040100  mov     eax, esi
0x180040102  mov     rcx, [rbp+50h+var_48]
0x180040106  xor     rcx, rbp; StackCookie
0x180040109  call    __security_check_cookie
0x18004010e  lea     rsp, [rbp+18h]
0x180040112  pop     r15
0x180040114  pop     r14
0x180040116  pop     r13
0x180040118  pop     r12
0x18004011a  pop     rdi
0x18004011b  pop     rsi
0x18004011c  pop     rbx
0x18004011d  pop     rbp
0x18004011e  retn
```
