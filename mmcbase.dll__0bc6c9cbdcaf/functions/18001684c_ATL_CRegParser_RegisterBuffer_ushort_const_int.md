# ATL::CRegParser::RegisterBuffer(ushort const *,int)

- ea: `0x18001684c`
- end: `0x1800169c5`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z`
- size: `377`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800169cc`

## callees

- `0x180008670`
- `0x180016350`
- `0x18001650c`
- `0x18001684c`
- `0x180016a94`

## import_xrefs

- `msvcrt!free` at `0x1800169a6`
- `msvcrt!free` at `0x1800169a6`
- `msvcrt!malloc` at `0x180016879`
- `msvcrt!malloc` at `0x180016879`
- `KERNEL32!lstrcmpiW` at `0x1800168f5`
- `KERNEL32!lstrcmpiW` at `0x1800168f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001699d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001699d`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, WCHAR *a2, int a3)
{
  unsigned __int16 *v6; // rsi
  int Token; // ebx
  void *v9; // r14
  unsigned int i; // ebx
  HKEY v11; // rbp
  __int64 v12; // r15
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v6 )
    return 2147942414LL;
  Token = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
  if ( Token >= 0 )
  {
    v9 = pv;
    *(_QWORD *)this = pv;
    while ( 2 )
    {
      if ( **(_WORD **)this )
      {
        Token = ATL::CRegParser::NextToken(this, v6);
        if ( Token >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= 0xE )
              goto LABEL_20;
            if ( !lstrcmpiW(v6, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
              break;
          }
          v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
          if ( !v11 )
            goto LABEL_20;
          Token = ATL::CRegParser::NextToken(this, v6);
          if ( Token < 0 )
            break;
          if ( *v6 == 123 )
          {
            if ( !a3 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, v6, v11, 0, 0);
              if ( Token < 0 )
                break;
              goto LABEL_18;
            }
            v12 = *(_QWORD *)this;
            Token = ATL::CRegParser::RegisterSubkeys(this, v6, v11, a3, 0);
            if ( Token >= 0 )
            {
LABEL_18:
              ATL::CRegParser::SkipWhiteSpace(this);
              continue;
            }
            *(_QWORD *)this = v12;
            ATL::CRegParser::RegisterSubkeys(this, v6, v11, 0, 0);
          }
          else
          {
LABEL_20:
            Token = -2147352567;
          }
        }
      }
      break;
    }
    CoTaskMemFree(v9);
  }
  free(v6);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18001684c  mov     [rsp+arg_0], rbx
0x180016851  mov     [rsp+arg_8], rbp
0x180016856  push    rsi
0x180016857  push    rdi
0x180016858  push    r12
0x18001685a  push    r14
0x18001685c  push    r15
0x18001685e  sub     rsp, 30h
0x180016862  mov     rdi, rcx
0x180016865  mov     [rsp+58h+pv], 0
0x18001686e  mov     ecx, 2000h; Size
0x180016873  mov     r12d, r8d
0x180016876  mov     rbx, rdx
0x180016879  call    cs:__imp_malloc
0x18001687f  mov     rsi, rax
0x180016882  test    rax, rax
0x180016885  jnz     short loc_180016891
0x180016887  mov     eax, 8007000Eh
0x18001688c  jmp     loc_1800169AE
0x180016891  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x180016896  mov     rdx, rbx; unsigned __int16 *
0x180016899  mov     rcx, rdi; this
0x18001689c  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)
0x1800168a1  mov     ebx, eax
0x1800168a3  test    eax, eax
0x1800168a5  js      loc_1800169A3
0x1800168ab  mov     r14, [rsp+58h+pv]
0x1800168b0  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800168b7  mov     [rdi], r14
0x1800168ba  mov     rcx, [rdi]
0x1800168bd  xor     eax, eax
0x1800168bf  cmp     ax, [rcx]
0x1800168c2  jz      loc_18001699A
0x1800168c8  mov     rdx, rsi; unsigned __int16 *
0x1800168cb  mov     rcx, rdi; this
0x1800168ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800168d3  mov     ebx, eax
0x1800168d5  test    eax, eax
0x1800168d7  js      loc_18001699A
0x1800168dd  xor     ebx, ebx
0x1800168df  cmp     ebx, 0Eh
0x1800168e2  jnb     loc_180016995
0x1800168e8  movsxd  rbp, ebx
0x1800168eb  mov     rcx, rsi; lpString1
0x1800168ee  add     rbp, rbp
0x1800168f1  mov     rdx, [r15+rbp*8]; lpString2
0x1800168f5  call    cs:__imp_lstrcmpiW
0x1800168fb  test    eax, eax
0x1800168fd  jz      short loc_180016903
0x1800168ff  inc     ebx
0x180016901  jmp     short loc_1800168DF
0x180016903  mov     rbp, [r15+rbp*8+8]
0x180016908  test    rbp, rbp
0x18001690b  jz      loc_180016995
0x180016911  mov     rdx, rsi; unsigned __int16 *
0x180016914  mov     rcx, rdi; this
0x180016917  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001691c  mov     ebx, eax
0x18001691e  test    eax, eax
0x180016920  js      short loc_18001699A
0x180016922  mov     eax, 7Bh ; '{'
0x180016927  cmp     ax, [rsi]
0x18001692a  jnz     short loc_180016995
0x18001692c  mov     [rsp+58h+var_38], 0; int
0x180016934  mov     r8, rbp; HKEY
0x180016937  mov     rdx, rsi; unsigned __int16 *
0x18001693a  mov     rcx, rdi; this
0x18001693d  test    r12d, r12d
0x180016940  jz      short loc_18001695C
0x180016942  mov     r15, [rdi]
0x180016945  mov     r9d, r12d; int
0x180016948  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001694d  mov     ebx, eax
0x18001694f  test    eax, eax
0x180016951  js      short loc_180016977
0x180016953  lea     r15, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001695a  jmp     short loc_18001696A
0x18001695c  xor     r9d, r9d; int
0x18001695f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016964  mov     ebx, eax
0x180016966  test    eax, eax
0x180016968  js      short loc_18001699A
0x18001696a  mov     rcx, rdi; this
0x18001696d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180016972  jmp     loc_1800168BA
0x180016977  xor     r9d, r9d; int
0x18001697a  mov     [rdi], r15
0x18001697d  mov     r8, rbp; HKEY
0x180016980  mov     [rsp+58h+var_38], 0; int
0x180016988  mov     rdx, rsi; unsigned __int16 *
0x18001698b  mov     rcx, rdi; this
0x18001698e  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016993  jmp     short loc_18001699A
0x180016995  mov     ebx, 80020009h
0x18001699a  mov     rcx, r14; pv
0x18001699d  call    cs:__imp_CoTaskMemFree
0x1800169a3  mov     rcx, rsi; Block
0x1800169a6  call    cs:__imp_free
0x1800169ac  mov     eax, ebx
0x1800169ae  mov     rbx, [rsp+58h+arg_0]
0x1800169b3  mov     rbp, [rsp+58h+arg_8]
0x1800169b8  add     rsp, 30h
0x1800169bc  pop     r15
0x1800169be  pop     r14
0x1800169c0  pop     r12
0x1800169c2  pop     rdi
0x1800169c3  pop     rsi
0x1800169c4  retn
```
