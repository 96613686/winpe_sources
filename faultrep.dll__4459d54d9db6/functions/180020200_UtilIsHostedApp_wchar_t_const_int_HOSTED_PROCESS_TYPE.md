# UtilIsHostedApp(wchar_t const *,int *,_HOSTED_PROCESS_TYPE *)

- ea: `0x180020200`
- end: `0x1800204a6`
- name: `?UtilIsHostedApp@@YAJPEB_WPEAHPEAW4_HOSTED_PROCESS_TYPE@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(const wchar_t *, int *, enum _HOSTED_PROCESS_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800190a0`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180020200`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002033a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002035b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002033a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002035b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020265`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041d`

## pseudocode

```c
__int64 __fastcall UtilIsHostedApp(const wchar_t *a1, int *a2, enum _HOSTED_PROCESS_TYPE *a3)
{
  __int64 v6; // rax
  const wchar_t *v7; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  const wchar_t *v10; // rdi
  DWORD LastError; // ebx
  unsigned int v12; // ebx
  void *v14[2]; // [rsp+20h] [rbp-89h] BYREF
  _WORD v15[8]; // [rsp+30h] [rbp-79h] BYREF
  WCHAR Buffer[64]; // [rsp+40h] [rbp-69h] BYREF

  *a2 = 0;
  v14[0] = v15;
  v15[0] = 0;
  v14[1] = v15;
  Buffer[0] = 0;
  *(_DWORD *)a3 = 3;
  if ( GetSystemDirectoryW(Buffer, 0x40u) - 1 > 0x3F )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, LastError);
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( !a1 )
      goto LABEL_29;
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = &a1[v6];
    while ( 1 )
    {
      v10 = v7;
      if ( v7 <= a1 )
        break;
      v8 = *--v7;
      LOWORD(v8) = v8 - 47;
      if ( (unsigned __int16)v8 <= 0x2Du )
      {
        v9 = 0x200000000801LL;
        if ( _bittest64(&v9, v8) )
          break;
      }
    }
    if ( v10 && v10 != a1 )
    {
      if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
             (__int64)v14,
             a1,
             v10 - a1 - 1) )
      {
        if ( !(unsigned int)_o__wcsicmp(Buffer, v14[0]) )
        {
          v12 = 0;
          while ( (unsigned int)_o__wcsicmp((&off_180062170)[2 * v12], v10) )
          {
            if ( ++v12 >= 2 )
              goto LABEL_21;
          }
          *a2 = 1;
          *(_DWORD *)a3 = *((_DWORD *)&off_180062170 + 4 * v12 + 2);
        }
LABEL_21:
        if ( *a2 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              *(unsigned int *)a3);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
        }
        LastError = 0;
      }
      else
      {
        LastError = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
            2147942414LL);
      }
    }
    else
    {
LABEL_29:
      LastError = -2147024809;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    }
  }
  if ( v14[0] != v15 )
    operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
  return LastError;
}

```

## disassembly

```asm
0x180020200  mov     [rsp-8+arg_18], rbx
0x180020205  push    rbp
0x180020206  push    rsi
0x180020207  push    rdi
0x180020208  push    r12
0x18002020a  push    r13
0x18002020c  push    r14
0x18002020e  push    r15
0x180020210  lea     rbp, [rsp-27h]
0x180020215  sub     rsp, 0D0h
0x18002021c  mov     rax, cs:__security_cookie
0x180020223  xor     rax, rsp
0x180020226  mov     [rbp+57h+var_40], rax
0x18002022a  xor     r12d, r12d
0x18002022d  lea     rax, [rbp+57h+var_D0]
0x180020231  mov     [rdx], r12d
0x180020234  mov     r14, rdx
0x180020237  mov     [rsp+100h+var_E0], rax
0x18002023c  mov     rbx, rcx
0x18002023f  lea     rax, [rbp+57h+var_D0]
0x180020243  mov     [rbp+57h+var_D0], r12w
0x180020248  lea     edx, [r12+40h]; uSize
0x18002024d  mov     [rsp+100h+var_D8], rax
0x180020252  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x180020256  mov     [rbp+57h+Buffer], r12w
0x18002025b  mov     r15, r8
0x18002025e  mov     dword ptr [r8], 3
0x180020265  call    cs:__imp_GetSystemDirectoryW
0x18002026b  dec     eax
0x18002026d  cmp     eax, 3Fh ; '?'
0x180020270  ja      loc_18002041D
0x180020276  test    rbx, rbx
0x180020279  jz      loc_1800203E8
0x18002027f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020283  inc     rax
0x180020286  cmp     [rbx+rax*2], r12w
0x18002028b  jnz     short loc_180020283
0x18002028d  lea     rcx, [rbx+rax*2]
0x180020291  jmp     short loc_1800202B4
0x180020293  sub     rcx, 2
0x180020297  movzx   eax, word ptr [rcx]
0x18002029a  sub     ax, 2Fh ; '/'
0x18002029e  cmp     ax, 2Dh ; '-'
0x1800202a2  ja      short loc_1800202B4
0x1800202a4  mov     rdx, 200000000801h
0x1800202ae  bt      rdx, rax
0x1800202b2  jb      short loc_1800202BC
0x1800202b4  mov     rdi, rcx
0x1800202b7  cmp     rcx, rbx
0x1800202ba  ja      short loc_180020293
0x1800202bc  test    rdi, rdi
0x1800202bf  jz      loc_1800203E8
0x1800202c5  cmp     rdi, rbx
0x1800202c8  jz      loc_1800203E8
0x1800202ce  mov     r8, rdi
0x1800202d1  lea     rcx, [rsp+100h+var_E0]
0x1800202d6  sub     r8, rbx
0x1800202d9  mov     rdx, rbx
0x1800202dc  sar     r8, 1
0x1800202df  dec     r8
0x1800202e2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800202e7  test    al, al
0x1800202e9  jnz     short loc_180020331
0x1800202eb  mov     ebx, 8007000Eh
0x1800202f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202f7  lea     rax, WPP_GLOBAL_Control
0x1800202fe  cmp     rcx, rax
0x180020301  jz      loc_180020463
0x180020307  test    byte ptr [rcx+1Ch], 1
0x18002030b  jz      loc_180020463
0x180020311  mov     rcx, [rcx+10h]
0x180020315  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18002031c  mov     edx, 3Ch ; '<'
0x180020321  mov     r9d, 8007000Eh
0x180020327  call    WPP_SF_d
0x18002032c  jmp     loc_180020463
0x180020331  mov     rdx, [rsp+100h+var_E0]
0x180020336  lea     rcx, [rbp+57h+Buffer]
0x18002033a  call    cs:__imp__o__wcsicmp
0x180020340  test    eax, eax
0x180020342  jnz     short loc_18002037D
0x180020344  mov     ebx, r12d
0x180020347  lea     r13, off_180062170; "svchost.exe"
0x18002034e  mov     esi, ebx
0x180020350  mov     rdx, rdi
0x180020353  add     rsi, rsi
0x180020356  mov     rcx, [r13+rsi*8+0]
0x18002035b  call    cs:__imp__o__wcsicmp
0x180020361  test    eax, eax
0x180020363  jz      short loc_18002036E
0x180020365  inc     ebx
0x180020367  cmp     ebx, 2
0x18002036a  jb      short loc_18002034E
0x18002036c  jmp     short loc_18002037D
0x18002036e  mov     dword ptr [r14], 1
0x180020375  mov     eax, [r13+rsi*8+8]
0x18002037a  mov     [r15], eax
0x18002037d  cmp     [r14], r12d
0x180020380  jz      short loc_1800203B5
0x180020382  mov     rcx, cs:WPP_GLOBAL_Control
0x180020389  lea     rax, WPP_GLOBAL_Control
0x180020390  cmp     rcx, rax
0x180020393  jz      short loc_1800203E3
0x180020395  test    byte ptr [rcx+1Ch], 4
0x180020399  jz      short loc_1800203E3
0x18002039b  mov     r9d, [r15]
0x18002039e  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800203a5  mov     rcx, [rcx+10h]
0x1800203a9  mov     edx, 3Dh ; '='
0x1800203ae  call    WPP_SF_d
0x1800203b3  jmp     short loc_1800203E3
0x1800203b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203bc  lea     rax, WPP_GLOBAL_Control
0x1800203c3  cmp     rcx, rax
0x1800203c6  jz      short loc_1800203E3
0x1800203c8  test    byte ptr [rcx+1Ch], 4
0x1800203cc  jz      short loc_1800203E3
0x1800203ce  mov     rcx, [rcx+10h]
0x1800203d2  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800203d9  mov     edx, 3Eh ; '>'
0x1800203de  call    WPP_SF_
0x1800203e3  mov     ebx, r12d
0x1800203e6  jmp     short loc_180020463
0x1800203e8  mov     ebx, 80070057h
0x1800203ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203f4  lea     rax, WPP_GLOBAL_Control
0x1800203fb  cmp     rcx, rax
0x1800203fe  jz      short loc_180020463
0x180020400  test    byte ptr [rcx+1Ch], 1
0x180020404  jz      short loc_180020463
0x180020406  mov     rcx, [rcx+10h]
0x18002040a  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x180020411  mov     edx, 3Bh ; ';'
0x180020416  call    WPP_SF_
0x18002041b  jmp     short loc_180020463
0x18002041d  call    cs:__imp_GetLastError
0x180020423  mov     ebx, eax
0x180020425  mov     rcx, cs:WPP_GLOBAL_Control
0x18002042c  lea     rax, WPP_GLOBAL_Control
0x180020433  cmp     rcx, rax
0x180020436  jz      short loc_180020456
0x180020438  test    byte ptr [rcx+1Ch], 1
0x18002043c  jz      short loc_180020456
0x18002043e  mov     rcx, [rcx+10h]
0x180020442  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x180020449  mov     edx, 3Ah ; ':'
0x18002044e  mov     r9d, ebx
0x180020451  call    WPP_SF_d
0x180020456  test    ebx, ebx
0x180020458  jle     short loc_180020463
0x18002045a  movzx   ebx, bx
0x18002045d  or      ebx, 80070000h
0x180020463  mov     rcx, [rsp+100h+var_E0]; void *
0x180020468  lea     rax, [rbp+57h+var_D0]
0x18002046c  cmp     rcx, rax
0x18002046f  jz      short loc_18002047D
0x180020471  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020478  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002047d  mov     eax, ebx
0x18002047f  mov     rcx, [rbp+57h+var_40]
0x180020483  xor     rcx, rsp; StackCookie
0x180020486  call    __security_check_cookie
0x18002048b  mov     rbx, [rsp+100h+arg_18]
0x180020493  add     rsp, 0D0h
0x18002049a  pop     r15
0x18002049c  pop     r14
0x18002049e  pop     r13
0x1800204a0  pop     r12
0x1800204a2  pop     rdi
0x1800204a3  pop     rsi
0x1800204a4  pop     rbp
0x1800204a5  retn
```
