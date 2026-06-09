# CHtmlScanner::ScanTagBufferEx(wchar_t const *,wchar_t * &,uint &,wchar_t * &,uint &,int)

- ea: `0x18000cce0`
- end: `0x18000d038`
- name: `?ScanTagBufferEx@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI12H@Z`
- size: `856`
- prototype: `void __fastcall(wchar_t **this, const wchar_t *, wchar_t **, unsigned int *, wchar_t **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bea0`

## callees

- `0x180008210`
- `0x18000cce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ce94`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cf69`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ce94`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cf69`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cda0`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cdd6`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000ce2d`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cf38`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cf9a`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cda0`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cdd6`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000ce2d`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cf38`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000cf9a`

## string_xrefs

- `0x18000ce8a`: `xmlns`
- `0x18000cf5f`: `xmlns`

## pseudocode

```c
void __fastcall CHtmlScanner::ScanTagBufferEx(
        wchar_t **this,
        const wchar_t *a2,
        wchar_t **a3,
        unsigned int *a4,
        wchar_t **a5,
        unsigned int *a6,
        int a7)
{
  int v10; // esi
  wchar_t *v11; // r9
  int v12; // r8d
  int v13; // ebp
  int v14; // r13d
  wchar_t *v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  wchar_t *v18; // rcx
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  wchar_t *v22; // [rsp+60h] [rbp+8h]
  int v23; // [rsp+68h] [rbp+10h]

  CHtmlScanner::ReadTag((CHtmlScanner *)this, 1);
  v10 = 0;
  v11 = 0;
  *a4 = 0;
  v12 = 0;
  v13 = 0;
  v22 = 0;
  *a6 = 0;
  v14 = 0;
  *a3 = 0;
  *a5 = 0;
  v15 = this[2];
  v23 = 0;
  while ( v15 < &this[2][*((unsigned int *)this + 7)] )
  {
    v16 = *v15;
    if ( v10 == 6 )
    {
      if ( (_WORD)v16 == 34 )
      {
        if ( v12 )
          goto LABEL_32;
LABEL_36:
        v10 = 0;
      }
    }
    else
    {
      switch ( v10 )
      {
        case 0:
          v17 = _o_iswspace(v16);
          v12 = v23;
          if ( !v17 )
            v10 = 1;
          v18 = v15;
          if ( v17 )
            v18 = v22;
          v22 = v18;
          v19 = 0;
          v11 = v22;
          if ( v17 )
            v19 = v13;
          ++v15;
          v13 = v19;
          continue;
        case 1:
          if ( (_WORD)v16 == 58 )
          {
            if ( v13 == 5 && !(unsigned int)_o__wcsnicmp(L"xmlns", v11, 5, v11) )
            {
              v20 = v14++;
              if ( v20 == a7 )
                v23 = 1;
            }
            v11 = v22;
            v10 = 2;
            v12 = v23;
            *a5 = ++v15;
            *a6 = 0;
          }
          else
          {
            if ( (_WORD)v16 == 61 )
            {
LABEL_37:
              if ( v13 == 5 && !(unsigned int)_o__wcsnicmp(L"xmlns", v11, 5, v11) )
              {
                v21 = v14++;
                if ( v21 == a7 )
                  v23 = 1;
              }
              v10 = 4;
              break;
            }
            if ( (unsigned int)_o_iswspace(v16) )
              goto LABEL_33;
            v11 = v22;
            v12 = v23;
            v13 = v15 - v22 + 1;
            ++v15;
          }
          continue;
        case 2:
          if ( (_WORD)v16 == 61 )
          {
            v11 = v22;
            v10 = 4;
            v12 = v23;
            ++v15;
          }
          else if ( (unsigned int)_o_iswspace(v16) )
          {
LABEL_33:
            v11 = v22;
            v10 = 3;
            v12 = v23;
            ++v15;
          }
          else
          {
            ++*a6;
            v11 = v22;
            ++v15;
            v12 = v23;
          }
          continue;
        case 3:
          if ( (_WORD)v16 == 61 )
            goto LABEL_37;
          if ( !(unsigned int)_o_iswspace(v16) )
          {
            v22 = v15;
            v13 = 0;
            v10 = 1;
          }
          break;
        case 4:
          if ( (_WORD)v16 == 34 )
          {
            v11 = v22;
            v12 = v23;
            v10 = 6;
            *a3 = ++v15;
            continue;
          }
          if ( (_WORD)v16 != 9 && (_WORD)v16 != 32 )
          {
            if ( (_WORD)v16 == 39 )
            {
              v10 = 5;
              *a3 = v15 + 1;
            }
            else
            {
              *a3 = v15;
              v10 = 7;
            }
          }
          break;
        case 5:
          if ( (_WORD)v16 != 39 )
            break;
          if ( !v12 )
            goto LABEL_36;
          goto LABEL_32;
        case 7:
          if ( !(unsigned int)_o_iswspace(v16) )
            break;
          if ( !v23 )
            goto LABEL_36;
          goto LABEL_32;
        default:
          break;
      }
    }
    v11 = v22;
    ++v15;
    v12 = v23;
  }
  if ( v10 != 7 || !v12 )
  {
    *a3 = 0;
    *a4 = 0;
    return;
  }
LABEL_32:
  *a4 = v15 - *a3;
}

```

## disassembly

```asm
0x18000cce0  mov     [rsp+arg_10], rbx
0x18000cce5  mov     [rsp+arg_8], rdx
0x18000ccea  push    rbp
0x18000cceb  push    rsi
0x18000ccec  push    rdi
0x18000cced  push    r12
0x18000ccef  push    r13
0x18000ccf1  push    r14
0x18000ccf3  push    r15
0x18000ccf5  sub     rsp, 20h
0x18000ccf9  mov     edx, 1; int
0x18000ccfe  mov     r15, r9
0x18000cd01  mov     r14, r8
0x18000cd04  mov     rdi, rcx
0x18000cd07  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000cd0c  mov     r12, [rsp+58h+arg_28]
0x18000cd14  xor     esi, esi
0x18000cd16  mov     rax, [rsp+58h+arg_20]
0x18000cd1e  xor     r9d, r9d
0x18000cd21  mov     [r15], esi
0x18000cd24  xor     r8d, r8d
0x18000cd27  xor     ebp, ebp
0x18000cd29  mov     [rsp+58h+arg_0], r9
0x18000cd2e  mov     [r12], esi
0x18000cd32  xor     r13d, r13d
0x18000cd35  mov     [r14], rsi
0x18000cd38  mov     [rax], rsi
0x18000cd3b  mov     rbx, [rdi+10h]
0x18000cd3f  mov     dword ptr [rsp+58h+arg_8], r8d
0x18000cd44  mov     ecx, [rdi+1Ch]
0x18000cd47  lea     r10, __ImageBase
0x18000cd4e  mov     rax, [rdi+10h]
0x18000cd52  lea     rcx, [rax+rcx*2]
0x18000cd56  cmp     rbx, rcx
0x18000cd59  jnb     loc_18000CEDC
0x18000cd5f  movzx   ecx, word ptr [rbx]
0x18000cd62  cmp     esi, 6
0x18000cd65  jnz     short loc_18000CD81
0x18000cd67  cmp     cx, 22h ; '"'
0x18000cd6b  jz      loc_18000CF10
0x18000cd71  mov     r9, [rsp+58h+arg_0]; jumptable 000000018000CD94 default case, case 6
0x18000cd76  add     rbx, 2
0x18000cd7a  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000cd7f  jmp     short loc_18000CD44
0x18000cd81  cmp     esi, 7; switch 8 cases
0x18000cd84  ja      short def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cd86  movsxd  rax, esi
0x18000cd89  mov     edx, ds:(jpt_18000CD94 - 180000000h)[r10+rax*4]
0x18000cd91  add     rdx, r10
0x18000cd94  jmp     rdx; switch jump
0x18000cd96  cmp     cx, 3Dh ; '='; jumptable 000000018000CD94 case 2
0x18000cd9a  jz      loc_18000CE67
0x18000cda0  call    cs:__imp__o_iswspace
0x18000cda6  test    eax, eax
0x18000cda8  jnz     loc_18000CF20
0x18000cdae  inc     dword ptr [r12]
0x18000cdb2  mov     r9, [rsp+58h+arg_0]
0x18000cdb7  add     rbx, 2
0x18000cdbb  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000cdc0  jmp     short loc_18000CD44
0x18000cdc2  cmp     cx, 3Ah ; ':'; jumptable 000000018000CD94 case 1
0x18000cdc6  jz      loc_18000CE7F
0x18000cdcc  cmp     cx, 3Dh ; '='
0x18000cdd0  jz      loc_18000CF54
0x18000cdd6  call    cs:__imp__o_iswspace
0x18000cddc  test    eax, eax
0x18000cdde  jnz     loc_18000CF20
0x18000cde4  mov     r9, [rsp+58h+arg_0]
0x18000cde9  mov     rbp, rbx
0x18000cdec  sub     rbp, [rsp+58h+arg_0]
0x18000cdf1  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000cdf6  sar     rbp, 1
0x18000cdf9  inc     ebp
0x18000cdfb  add     rbx, 2
0x18000cdff  jmp     loc_18000CD44
0x18000ce04  cmp     cx, 22h ; '"'; jumptable 000000018000CD94 case 4
0x18000ce08  jnz     loc_18000CFB9
0x18000ce0e  mov     r9, [rsp+58h+arg_0]
0x18000ce13  lea     rax, [rbx+2]
0x18000ce17  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000ce1c  mov     esi, 6
0x18000ce21  mov     [r14], rax
0x18000ce24  add     rbx, 2
0x18000ce28  jmp     loc_18000CD44
0x18000ce2d  call    cs:__imp__o_iswspace; jumptable 000000018000CD94 case 0
0x18000ce33  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000ce38  mov     ecx, 1
0x18000ce3d  test    eax, eax
0x18000ce3f  cmovz   esi, ecx
0x18000ce42  mov     rcx, rbx
0x18000ce45  cmovnz  rcx, [rsp+58h+arg_0]
0x18000ce4b  mov     [rsp+58h+arg_0], rcx
0x18000ce50  xor     ecx, ecx
0x18000ce52  mov     r9, [rsp+58h+arg_0]
0x18000ce57  test    eax, eax
0x18000ce59  cmovnz  ecx, ebp
0x18000ce5c  add     rbx, 2
0x18000ce60  mov     ebp, ecx
0x18000ce62  jmp     loc_18000CD44
0x18000ce67  mov     r9, [rsp+58h+arg_0]
0x18000ce6c  mov     esi, 4
0x18000ce71  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000ce76  add     rbx, 2
0x18000ce7a  jmp     loc_18000CD44
0x18000ce7f  cmp     ebp, 5
0x18000ce82  jnz     short loc_18000CEAD
0x18000ce84  mov     r8d, 5
0x18000ce8a  lea     rcx, aXmlns; "xmlns"
0x18000ce91  mov     rdx, r9
0x18000ce94  call    cs:__imp__o__wcsnicmp
0x18000ce9a  test    eax, eax
0x18000ce9c  jnz     short loc_18000CEAD
0x18000ce9e  mov     eax, r13d
0x18000cea1  inc     r13d
0x18000cea4  cmp     eax, [rsp+58h+arg_30]
0x18000ceab  jz      short loc_18000CF06
0x18000cead  mov     rcx, [rsp+58h+arg_20]
0x18000ceb5  lea     rax, [rbx+2]
0x18000ceb9  mov     r9, [rsp+58h+arg_0]
0x18000cebe  mov     esi, 2
0x18000cec3  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000cec8  add     rbx, 2
0x18000cecc  mov     [rcx], rax
0x18000cecf  mov     dword ptr [r12], 0
0x18000ced7  jmp     loc_18000CD44
0x18000cedc  cmp     esi, 7
0x18000cedf  jz      loc_18000D009
0x18000cee5  xor     eax, eax
0x18000cee7  mov     qword ptr [r14], 0
0x18000ceee  mov     [r15], eax
0x18000cef1  mov     rbx, [rsp+58h+arg_10]
0x18000cef6  add     rsp, 20h
0x18000cefa  pop     r15
0x18000cefc  pop     r14
0x18000cefe  pop     r13
0x18000cf00  pop     r12
0x18000cf02  pop     rdi
0x18000cf03  pop     rsi
0x18000cf04  pop     rbp
0x18000cf05  retn
0x18000cf06  mov     dword ptr [rsp+58h+arg_8], 1
0x18000cf0e  jmp     short loc_18000CEAD
0x18000cf10  test    r8d, r8d
0x18000cf13  jz      short loc_18000CF4D
0x18000cf15  sub     rbx, [r14]
0x18000cf18  sar     rbx, 1
0x18000cf1b  mov     [r15], ebx
0x18000cf1e  jmp     short loc_18000CEF1
0x18000cf20  mov     r9, [rsp+58h+arg_0]
0x18000cf25  mov     esi, 3
0x18000cf2a  mov     r8d, dword ptr [rsp+58h+arg_8]
0x18000cf2f  add     rbx, 2
0x18000cf33  jmp     loc_18000CD44
0x18000cf38  call    cs:__imp__o_iswspace; jumptable 000000018000CD94 case 7
0x18000cf3e  test    eax, eax
0x18000cf40  jz      def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cf46  cmp     dword ptr [rsp+58h+arg_8], 0
0x18000cf4b  jnz     short loc_18000CF15
0x18000cf4d  xor     esi, esi
0x18000cf4f  jmp     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cf54  cmp     ebp, 5
0x18000cf57  jnz     short loc_18000CF8A
0x18000cf59  mov     r8d, 5
0x18000cf5f  lea     rcx, aXmlns; "xmlns"
0x18000cf66  mov     rdx, r9
0x18000cf69  call    cs:__imp__o__wcsnicmp
0x18000cf6f  test    eax, eax
0x18000cf71  jnz     short loc_18000CF8A
0x18000cf73  mov     eax, r13d
0x18000cf76  inc     r13d
0x18000cf79  cmp     eax, [rsp+58h+arg_30]
0x18000cf80  jnz     short loc_18000CF8A
0x18000cf82  mov     dword ptr [rsp+58h+arg_8], 1
0x18000cf8a  mov     esi, 4
0x18000cf8f  jmp     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cf94  cmp     cx, 3Dh ; '='; jumptable 000000018000CD94 case 3
0x18000cf98  jz      short loc_18000CF54
0x18000cf9a  call    cs:__imp__o_iswspace
0x18000cfa0  test    eax, eax
0x18000cfa2  jnz     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cfa8  mov     [rsp+58h+arg_0], rbx
0x18000cfad  xor     ebp, ebp
0x18000cfaf  mov     esi, 1
0x18000cfb4  jmp     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cfb9  cmp     cx, 9
0x18000cfbd  jz      def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cfc3  cmp     cx, 20h ; ' '
0x18000cfc7  jz      def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cfcd  cmp     cx, 27h ; '''
0x18000cfd1  jz      short loc_18000CFE0
0x18000cfd3  mov     [r14], rbx
0x18000cfd6  mov     esi, 7
0x18000cfdb  jmp     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cfe0  lea     rax, [rbx+2]
0x18000cfe4  mov     esi, 5
0x18000cfe9  mov     [r14], rax
0x18000cfec  jmp     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cff1  cmp     cx, 27h ; '''; jumptable 000000018000CD94 case 5
0x18000cff5  jnz     def_18000CD94; jumptable 000000018000CD94 default case, case 6
0x18000cffb  test    r8d, r8d
0x18000cffe  jnz     loc_18000CF15
0x18000d004  jmp     loc_18000CF4D
0x18000d009  test    r8d, r8d
0x18000d00c  jnz     loc_18000CF15
0x18000d012  jmp     loc_18000CEE5
```
