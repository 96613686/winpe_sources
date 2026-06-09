# HandleException(ulong,ushort const *)

- ea: `0x180008930`
- end: `0x180008a30`
- name: `?HandleException@@YAXKPEBG@Z`
- size: `256`
- prototype: `void(unsigned int, const unsigned __int16 *)`
- caller_count: `36`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005d10`
- `0x1800061e0`
- `0x180007d10`
- `0x180007f80`
- `0x18000801c`
- `0x180008070`
- `0x180008190`
- `0x1800081c8`
- `0x180008230`
- `0x180008280`
- `0x1800082d0`
- `0x1800083ec`
- `0x180008440`
- `0x1800084a0`
- `0x1800084e4`
- `0x180008590`
- `0x180008608`
- `0x1800086f8`
- `0x18000879c`
- `0x180008cdc`
- `0x180008d24`
- `0x180008ffc`
- `0x180009044`
- `0x180009388`
- `0x18000a068`
- `0x18000a118`
- `0x18000a300`
- `0x18000aa00`
- `0x18000aa60`
- `0x18000ab20`
- `0x18000af14`
- `0x18000af64`
- `0x18000aff8`
- `0x18000b790`
- `0x18000bac8`
- `0x18000bfd4`

## callees

- `0x180002610`
- `0x1800026d0`
- `0x180003078`
- `0x180008930`
- `0x180012b40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008a11`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008a11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HandleException(unsigned int a1, unsigned __int16 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  int v6; // [rsp+20h] [rbp-88h]
  __int64 v7; // [rsp+40h] [rbp-68h] BYREF
  int v8; // [rsp+48h] [rbp-60h]
  void *Src[3]; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v10; // [rsp+68h] [rbp-40h]
  int v11; // [rsp+70h] [rbp-38h]

  v3 = a1;
  v10 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v11 = -1;
  std::wstring::append(Src, L"Exception 0x");
  v7 = v3;
  v4 = -1;
  v8 = -1;
  v5 = operator<<(Src, &v7);
  std::wstring::append(v5, L" thrown from ");
  if ( a2 )
  {
    if ( *a2 )
    {
      do
        ++v4;
      while ( a2[v4] );
    }
    std::wstring::append(v5, a2);
  }
  if ( v5[3] >= 8u )
    v5 = (_QWORD *)*v5;
  InternalTrace(L"windows\\oleacc\\msaatext\\DocWrapExcept.h", 0x17u, 3u, 0, v6, 0, (wchar_t *)v5);
  if ( v10 >= 8 )
    operator delete(Src[0]);
}

```

## disassembly

```asm
0x180008930  push    rbx
0x180008932  push    rbp
0x180008933  push    rsi
0x180008934  push    rdi
0x180008935  sub     rsp, 88h
0x18000893c  mov     rax, cs:__security_cookie
0x180008943  xor     rax, rsp
0x180008946  mov     [rsp+0A8h+var_30], rax
0x18000894b  mov     rsi, rdx
0x18000894e  mov     ebx, ecx
0x180008950  mov     [rsp+0A8h+var_40], 7
0x180008959  xor     ebp, ebp
0x18000895b  mov     [rsp+0A8h+var_48], rbp
0x180008960  mov     word ptr [rsp+0A8h+Src], bp
0x180008965  mov     [rsp+0A8h+var_38], 0FFFFFFFFh
0x18000896d  lea     r8d, [rbp+0Ch]
0x180008971  lea     rdx, aException0x; "Exception 0x"
0x180008978  lea     rcx, [rsp+0A8h+Src]; Src
0x18000897d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180008982  mov     [rsp+0A8h+var_68], rbx
0x180008987  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000898b  mov     [rsp+0A8h+var_60], edi
0x18000898f  lea     rdx, [rsp+0A8h+var_68]
0x180008994  lea     rcx, [rsp+0A8h+Src]; Src
0x180008999  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z; operator<<(TSTR &,WriteHex const &)
0x18000899e  mov     rbx, rax
0x1800089a1  lea     r8d, [rbp+0Dh]
0x1800089a5  lea     rdx, aThrownFrom; " thrown from "
0x1800089ac  mov     rcx, rax; Src
0x1800089af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800089b4  test    rsi, rsi
0x1800089b7  jz      short loc_1800089D9
0x1800089b9  cmp     [rsi], bp
0x1800089bc  jnz     short loc_1800089C2
0x1800089be  mov     edi, ebp
0x1800089c0  jmp     short loc_1800089CB
0x1800089c2  inc     rdi
0x1800089c5  cmp     [rsi+rdi*2], bp
0x1800089c9  jnz     short loc_1800089C2
0x1800089cb  mov     r8, rdi
0x1800089ce  mov     rdx, rsi; void *
0x1800089d1  mov     rcx, rbx; Src
0x1800089d4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800089d9  cmp     qword ptr [rbx+18h], 8
0x1800089de  jb      short loc_1800089E3
0x1800089e0  mov     rbx, [rbx]
0x1800089e3  mov     [rsp+0A8h+var_78], rbx; __int64
0x1800089e8  mov     [rsp+0A8h+var_80], ebp; int
0x1800089ec  xor     r9d, r9d
0x1800089ef  lea     edx, [r9+17h]; Value
0x1800089f3  lea     r8d, [r9+3]
0x1800089f7  lea     rcx, aWindowsOleaccM_0; "windows\\oleacc\\msaatext\\DocWrapExcep"...
0x1800089fe  call    InternalTrace
0x180008a03  nop
0x180008a04  cmp     [rsp+0A8h+var_40], 8
0x180008a0a  jb      short loc_180008A17
0x180008a0c  mov     rcx, [rsp+0A8h+Src]
0x180008a11  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008a17  mov     rcx, [rsp+0A8h+var_30]
0x180008a1c  xor     rcx, rsp; StackCookie
0x180008a1f  call    __security_check_cookie
0x180008a24  add     rsp, 88h
0x180008a2b  pop     rdi
0x180008a2c  pop     rsi
0x180008a2d  pop     rbp
0x180008a2e  pop     rbx
0x180008a2f  retn
```
