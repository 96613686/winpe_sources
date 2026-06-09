# NativeMsh::PwrshCommon::IdentifyHostDirectory(NativeMsh::HostEnvironment &)

- ea: `0x1800083e0`
- end: `0x1800085af`
- name: `?IdentifyHostDirectory@PwrshCommon@NativeMsh@@MEAAIAEAVHostEnvironment@2@@Z`
- size: `463`
- prototype: `__int64 __fastcall(NativeMsh::PwrshCommon *this, struct NativeMsh::HostEnvironment *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001c88`
- `0x180001e16`
- `0x180006100`
- `0x1800083e0`
- `0x1800096b0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800084e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008556`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800084e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008556`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180008582`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000859c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180008582`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000859c`

## string_xrefs

- `0x180008595`: `%windir%\System32\WindowsPowerShell\v1.0\`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::IdentifyHostDirectory(
        NativeMsh::PwrshCommon *this,
        struct NativeMsh::HostEnvironment *a2)
{
  __int64 *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // eax
  __int64 i; // rcx
  __int64 v9; // rsi
  WCHAR *v10; // rdx
  unsigned __int64 v11; // rdi
  void **v12; // rbx
  unsigned __int64 v13; // r15
  __int64 v14; // r14
  unsigned __int64 v15; // rcx
  void *Src[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v18; // [rsp+48h] [rbp-B8h]
  WCHAR v19[264]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = (__int64 *)*((_QWORD *)this + 2);
  v4 = *v3;
  v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v3 + 24))(v3, 0);
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, WCHAR *, __int64))(v4 + 16))(v3, v5, v19, 260);
  if ( !v6 )
    return 4294901760LL;
  for ( i = (unsigned int)(v6 - 1); (int)i >= 0; i = (unsigned int)(i - 1) )
  {
    if ( v19[i] == 92 )
      break;
  }
  v9 = (int)i;
  v10 = &v19[(int)i + 1];
  if ( v10 )
  {
    v11 = 7;
    v18 = 7;
    v17 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src, v10);
    v12 = (void **)((char *)a2 + 1040);
    if ( (void **)((char *)a2 + 1040) == Src )
    {
      v11 = v18;
    }
    else
    {
      if ( *((_QWORD *)a2 + 133) >= 8u )
        operator delete(*v12);
      *(_WORD *)v12 = 0;
      v13 = v18;
      v14 = v17;
      if ( v18 >= 8 )
      {
        *v12 = Src[0];
        Src[0] = 0;
      }
      else if ( v17 != -1 )
      {
        memcpy_0((char *)a2 + 1040, Src, 2 * (v17 + 1));
      }
      *((_QWORD *)a2 + 132) = v14;
      *((_QWORD *)a2 + 133) = v13;
      v18 = 7;
      v17 = 0;
      LOWORD(Src[0]) = 0;
    }
    if ( v11 >= 8 )
      operator delete(Src[0]);
  }
  v15 = 2 * v9 + 2;
  if ( v15 >= 0x208 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)v19 + v15) = 0;
  ExpandEnvironmentStringsW(v19, (LPWSTR)a2, 0x104u);
  ExpandEnvironmentStringsW(L"%windir%\\System32\\WindowsPowerShell\\v1.0\\", (LPWSTR)a2 + 260, 0x104u);
  return 0;
}

```

## disassembly

```asm
0x1800083e0  mov     [rsp-8+arg_10], rbx
0x1800083e5  mov     [rsp-8+arg_18], rsi
0x1800083ea  push    rbp
0x1800083eb  push    rdi
0x1800083ec  push    r13
0x1800083ee  push    r14
0x1800083f0  push    r15
0x1800083f2  lea     rbp, [rsp-170h]
0x1800083fa  sub     rsp, 270h
0x180008401  mov     rax, cs:__security_cookie
0x180008408  xor     rax, rsp
0x18000840b  mov     [rbp+190h+var_30], rax
0x180008412  mov     r13, rdx
0x180008415  mov     rdi, [rcx+10h]
0x180008419  mov     rbx, [rdi]
0x18000841c  xor     edx, edx
0x18000841e  mov     rcx, rdi
0x180008421  mov     rax, [rbx+18h]
0x180008425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842a  mov     r9d, 104h
0x180008430  lea     r8, [rsp+290h+var_240]
0x180008435  mov     rdx, rax
0x180008438  mov     rcx, rdi
0x18000843b  mov     rax, [rbx+10h]
0x18000843f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008444  test    eax, eax
0x180008446  jnz     short loc_180008478
0x180008448  mov     eax, 0FFFF0000h
0x18000844d  mov     rcx, [rbp+190h+var_30]
0x180008454  xor     rcx, rsp; StackCookie
0x180008457  call    __security_check_cookie
0x18000845c  lea     r11, [rsp+290h+var_20]
0x180008464  mov     rbx, [r11+40h]
0x180008468  mov     rsi, [r11+48h]
0x18000846c  mov     rsp, r11
0x18000846f  pop     r15
0x180008471  pop     r14
0x180008473  pop     r13
0x180008475  pop     rdi
0x180008476  pop     rbp
0x180008477  retn
0x180008478  lea     ecx, [rax-1]
0x18000847b  test    ecx, ecx
0x18000847d  js      short loc_18000848C
0x18000847f  cmp     [rsp+rcx*2+290h+var_240], 5Ch ; '\'
0x180008485  jz      short loc_18000848C
0x180008487  sub     ecx, 1
0x18000848a  jns     short loc_18000847F
0x18000848c  movsxd  rsi, ecx
0x18000848f  lea     rdx, [rsp+290h+var_23E]
0x180008494  lea     rdx, [rdx+rsi*2]; Src
0x180008498  test    rdx, rdx
0x18000849b  jz      loc_18000855C
0x1800084a1  mov     edi, 7
0x1800084a6  mov     [rsp+290h+var_248], rdi
0x1800084ab  mov     [rsp+290h+var_250], 0
0x1800084b4  xor     eax, eax
0x1800084b6  mov     word ptr [rsp+290h+Src], ax
0x1800084bb  lea     rcx, [rsp+290h+Src]; void *
0x1800084c0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800084c5  lea     rbx, [r13+410h]
0x1800084cc  lea     rax, [rsp+290h+Src]
0x1800084d1  cmp     rbx, rax
0x1800084d4  jz      short loc_180008546
0x1800084d6  cmp     qword ptr [rbx+18h], 8
0x1800084db  jb      short loc_1800084E6
0x1800084dd  mov     rcx, [rbx]
0x1800084e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800084e6  xor     eax, eax
0x1800084e8  mov     [rbx], ax
0x1800084eb  mov     r15, [rsp+290h+var_248]
0x1800084f0  mov     r14, [rsp+290h+var_250]
0x1800084f5  cmp     r15, 8
0x1800084f9  jnb     short loc_180008516
0x1800084fb  lea     r8, [r14+1]
0x1800084ff  test    r8, r8
0x180008502  jz      short loc_180008527
0x180008504  add     r8, r8; Size
0x180008507  lea     rdx, [rsp+290h+Src]; Src
0x18000850c  mov     rcx, rbx; void *
0x18000850f  call    memcpy_0
0x180008514  jmp     short loc_180008527
0x180008516  mov     rax, [rsp+290h+Src]
0x18000851b  mov     [rbx], rax
0x18000851e  mov     [rsp+290h+Src], 0
0x180008527  mov     [rbx+10h], r14
0x18000852b  mov     [rbx+18h], r15
0x18000852f  mov     [rsp+290h+var_248], rdi
0x180008534  mov     [rsp+290h+var_250], 0
0x18000853d  xor     eax, eax
0x18000853f  mov     word ptr [rsp+290h+Src], ax
0x180008544  jmp     short loc_18000854B
0x180008546  mov     rdi, [rsp+290h+var_248]
0x18000854b  cmp     rdi, 8
0x18000854f  jb      short loc_18000855C
0x180008551  mov     rcx, [rsp+290h+Src]
0x180008556  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000855c  lea     rcx, ds:2[rsi*2]
0x180008564  cmp     rcx, 208h
0x18000856b  jnb     short loc_1800085A9
0x18000856d  xor     eax, eax
0x18000856f  mov     [rsp+rcx+290h+var_240], ax
0x180008574  mov     r8d, 104h; nSize
0x18000857a  mov     rdx, r13; lpDst
0x18000857d  lea     rcx, [rsp+290h+var_240]; lpSrc
0x180008582  call    cs:__imp_ExpandEnvironmentStringsW
0x180008588  lea     rdx, [r13+208h]; lpDst
0x18000858f  mov     r8d, 104h; nSize
0x180008595  lea     rcx, Src; "%windir%\\System32\\WindowsPowerShell\\"...
0x18000859c  call    cs:__imp_ExpandEnvironmentStringsW
0x1800085a2  xor     eax, eax
0x1800085a4  jmp     loc_18000844D
0x1800085a9  call    __report_rangecheckfailure
```
