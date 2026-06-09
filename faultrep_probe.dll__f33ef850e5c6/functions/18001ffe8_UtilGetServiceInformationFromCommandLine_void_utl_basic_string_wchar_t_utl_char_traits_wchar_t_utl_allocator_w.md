# UtilGetServiceInformationFromCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18001ffe8`
- end: `0x1800201f7`
- name: `?UtilGetServiceInformationFromCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001f924`

## callees

- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x18001ffe8`
- `0x18003a6b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800200a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020126`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800200a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020126`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18002007c`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18002007c`

## pseudocode

```c
__int64 __fastcall UtilGetServiceInformationFromCommandLine(void *a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  unsigned int ProcessCommandLine; // ebx
  int v8; // edi
  LPWSTR *v9; // r14
  LPWSTR v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  LPWSTR v15; // rdx
  __int64 v16; // r8
  LPCWSTR lpCmdLine[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v19[12]; // [rsp+30h] [rbp-18h] BYREF
  int pNumArgs; // [rsp+90h] [rbp+48h] BYREF

  lpCmdLine[0] = v19;
  lpCmdLine[1] = v19;
  v19[0] = 0;
  pNumArgs = 0;
  if ( !a1 )
  {
    ProcessCommandLine = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
      goto LABEL_32;
    }
    return ProcessCommandLine;
  }
  ProcessCommandLine = UtilGetProcessCommandLine(a1, (__int64)lpCmdLine);
  if ( (ProcessCommandLine & 0x80000000) != 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 92;
      v14 = ProcessCommandLine;
LABEL_31:
      WPP_SF_d(v12[2], v13, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v14);
    }
    goto LABEL_32;
  }
  v8 = 1;
  v9 = CommandLineToArgvW(lpCmdLine[0], &pNumArgs);
  if ( pNumArgs <= 1 )
    goto LABEL_32;
  while ( !(unsigned int)_o__wcsicmp(L"-k", v9[v8]) )
  {
    if ( v8 + 1 < pNumArgs )
    {
      v10 = v9[v8 + 1];
      if ( *v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a2,
                                 v10) )
        {
          ProcessCommandLine = -2147024882;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 90;
LABEL_16:
            v14 = 2147942414LL;
            goto LABEL_31;
          }
          goto LABEL_32;
        }
      }
    }
LABEL_23:
    if ( ++v8 >= pNumArgs )
      goto LABEL_32;
  }
  if ( (unsigned int)_o__wcsicmp(L"-s", v9[v8]) )
    goto LABEL_23;
  *a3 = 1;
  if ( v8 + 1 >= pNumArgs )
    goto LABEL_23;
  v15 = v9[v8 + 1];
  if ( !*v15 )
    goto LABEL_23;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a4, v15) )
    goto LABEL_23;
  ProcessCommandLine = -2147024882;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 91;
    goto LABEL_16;
  }
LABEL_32:
  if ( lpCmdLine[0] != v19 )
    operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
  return ProcessCommandLine;
}

```

## disassembly

```asm
0x18001ffe8  push    rbp
0x18001ffea  push    rbx
0x18001ffeb  push    rsi
0x18001ffec  push    rdi
0x18001ffed  push    r12
0x18001ffef  push    r13
0x18001fff1  push    r14
0x18001fff3  push    r15
0x18001fff5  mov     rbp, rsp
0x18001fff8  sub     rsp, 48h
0x18001fffc  xor     edi, edi
0x18001fffe  lea     rax, [rbp+var_18]
0x180020002  mov     [rbp+lpCmdLine], rax
0x180020006  lea     rax, [rbp+var_18]
0x18002000a  mov     [rbp+var_20], rax
0x18002000e  mov     r12, r9
0x180020011  mov     [rbp+var_18], di
0x180020015  mov     r15, r8
0x180020018  mov     [rbp+pNumArgs], edi
0x18002001b  mov     r13, rdx
0x18002001e  test    rcx, rcx
0x180020021  jnz     short loc_180020061
0x180020023  mov     ebx, 80070057h
0x180020028  mov     rcx, cs:WPP_GLOBAL_Control
0x18002002f  lea     rax, WPP_GLOBAL_Control
0x180020036  cmp     rcx, rax
0x180020039  jz      loc_1800201E4
0x18002003f  test    byte ptr [rcx+1Ch], 1
0x180020043  jz      loc_1800201E4
0x180020049  mov     rcx, [rcx+10h]
0x18002004d  lea     edx, [rdi+59h]
0x180020050  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x180020057  call    WPP_SF_
0x18002005c  jmp     loc_1800201CB
0x180020061  lea     rdx, [rbp+lpCmdLine]
0x180020065  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18002006a  mov     ebx, eax
0x18002006c  test    eax, eax
0x18002006e  js      loc_18002019A
0x180020074  mov     rcx, [rbp+lpCmdLine]; lpCmdLine
0x180020078  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x18002007c  call    cs:__imp_CommandLineToArgvW
0x180020082  mov     edi, 1
0x180020087  mov     r14, rax
0x18002008a  cmp     [rbp+pNumArgs], edi
0x18002008d  jle     loc_1800201CB
0x180020093  movsxd  rsi, edi
0x180020096  lea     rcx, aK; "-k"
0x18002009d  mov     rdx, [r14+rsi*8]
0x1800200a1  call    cs:__imp__o__wcsicmp
0x1800200a7  xor     ecx, ecx
0x1800200a9  test    eax, eax
0x1800200ab  jnz     short loc_18002011B
0x1800200ad  lea     eax, [rdi+1]
0x1800200b0  cmp     eax, [rbp+pNumArgs]
0x1800200b3  jge     loc_180020165
0x1800200b9  mov     rdx, [r14+rsi*8+8]
0x1800200be  cmp     cx, [rdx]
0x1800200c1  jz      loc_180020165
0x1800200c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800200cb  inc     r8
0x1800200ce  cmp     [rdx+r8*2], cx
0x1800200d3  jnz     short loc_1800200CB
0x1800200d5  mov     rcx, r13
0x1800200d8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800200dd  test    al, al
0x1800200df  jnz     loc_180020165
0x1800200e5  mov     ebx, 8007000Eh
0x1800200ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200f1  lea     rax, WPP_GLOBAL_Control
0x1800200f8  cmp     rcx, rax
0x1800200fb  jz      loc_1800201CB
0x180020101  test    byte ptr [rcx+1Ch], 1
0x180020105  jz      loc_1800201CB
0x18002010b  mov     edx, 5Ah ; 'Z'
0x180020110  mov     r9d, 8007000Eh
0x180020116  jmp     loc_1800201BB
0x18002011b  mov     rdx, [r14+rsi*8]
0x18002011f  lea     rcx, aS_0; "-s"
0x180020126  call    cs:__imp__o__wcsicmp
0x18002012c  xor     ecx, ecx
0x18002012e  test    eax, eax
0x180020130  jnz     short loc_180020165
0x180020132  lea     eax, [rdi+1]
0x180020135  mov     dword ptr [r15], 1
0x18002013c  cmp     eax, [rbp+pNumArgs]
0x18002013f  jge     short loc_180020165
0x180020141  mov     rdx, [r14+rsi*8+8]
0x180020146  cmp     cx, [rdx]
0x180020149  jz      short loc_180020165
0x18002014b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002014f  inc     r8
0x180020152  cmp     [rdx+r8*2], cx
0x180020157  jnz     short loc_18002014F
0x180020159  mov     rcx, r12
0x18002015c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180020161  test    al, al
0x180020163  jz      short loc_180020172
0x180020165  inc     edi
0x180020167  cmp     edi, [rbp+pNumArgs]
0x18002016a  jl      loc_180020093
0x180020170  jmp     short loc_1800201CB
0x180020172  mov     ebx, 8007000Eh
0x180020177  mov     rcx, cs:WPP_GLOBAL_Control
0x18002017e  lea     rax, WPP_GLOBAL_Control
0x180020185  cmp     rcx, rax
0x180020188  jz      short loc_1800201CB
0x18002018a  test    byte ptr [rcx+1Ch], 1
0x18002018e  jz      short loc_1800201CB
0x180020190  mov     edx, 5Bh ; '['
0x180020195  jmp     loc_180020110
0x18002019a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201a1  lea     rax, WPP_GLOBAL_Control
0x1800201a8  cmp     rcx, rax
0x1800201ab  jz      short loc_1800201CB
0x1800201ad  test    byte ptr [rcx+1Ch], 1
0x1800201b1  jz      short loc_1800201CB
0x1800201b3  mov     edx, 5Ch ; '\'
0x1800201b8  mov     r9d, ebx
0x1800201bb  mov     rcx, [rcx+10h]
0x1800201bf  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800201c6  call    WPP_SF_d
0x1800201cb  mov     rcx, [rbp+lpCmdLine]; void *
0x1800201cf  lea     rax, [rbp+var_18]
0x1800201d3  cmp     rcx, rax
0x1800201d6  jz      short loc_1800201E4
0x1800201d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800201df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800201e4  mov     eax, ebx
0x1800201e6  add     rsp, 48h
0x1800201ea  pop     r15
0x1800201ec  pop     r14
0x1800201ee  pop     r13
0x1800201f0  pop     r12
0x1800201f2  pop     rdi
0x1800201f3  pop     rsi
0x1800201f4  pop     rbx
0x1800201f5  pop     rbp
0x1800201f6  retn
```
