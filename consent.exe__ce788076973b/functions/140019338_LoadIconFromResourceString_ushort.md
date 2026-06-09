# LoadIconFromResourceString(ushort *)

- ea: `0x140019338`
- end: `0x140019496`
- name: `?LoadIconFromResourceString@@YAPEAUHICON__@@PEAG@Z`
- size: `350`
- prototype: `HICON __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000f4b8`

## callees

- `0x140019338`

## import_xrefs

- `USER32!LoadIconW` at `0x140019469`
- `USER32!LoadIconW` at `0x140019469`
- `msvcrt!_errno` at `0x14001943f`
- `msvcrt!_errno` at `0x140019458`
- `msvcrt!_errno` at `0x14001943f`
- `msvcrt!_errno` at `0x140019458`
- `msvcrt!_wtol` at `0x14001944b`
- `msvcrt!_wtol` at `0x14001944b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140019436`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140019436`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140019475`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140019475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001947e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001947e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400193b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400193b8`

## pseudocode

```c
HICON __fastcall LoadIconFromResourceString(unsigned __int16 *a1)
{
  HICON IconW; // r15
  unsigned int i; // ebx
  __int64 v4; // rsi
  __int64 v5; // rcx
  const wchar_t *v6; // rbp
  WCHAR *v7; // rax
  WCHAR *v8; // r14
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // rdi
  WCHAR *v11; // rcx
  HMODULE Library; // rbx
  unsigned __int16 v13; // di

  IconW = 0;
  if ( a1 && *a1 == 64 )
  {
    for ( i = 1; i < 0x7FFFFFFF; ++i )
    {
      if ( !a1[i] )
        break;
      if ( a1[i] == 44 )
        break;
    }
    v4 = i;
    v5 = i;
    if ( a1[v5] == 44 && a1[i + 1] == 45 )
    {
      v6 = &a1[i + 2];
      if ( *v6 )
      {
        v7 = (WCHAR *)CoTaskMemAlloc(v5 * 2);
        v8 = v7;
        if ( v7 )
        {
          if ( i )
          {
            if ( i <= 0x7FFFFFFFuLL && (v9 = i - 1, v9 <= 0x7FFFFFFE) )
            {
              v10 = a1 + 1;
              do
              {
                if ( !v9 )
                  break;
                if ( !*v10 )
                  break;
                *v7++ = *v10++;
                --v9;
                --v4;
              }
              while ( v4 );
              v11 = v7 - 1;
              if ( v4 )
                v11 = v7;
              *v11 = 0;
              if ( v4 && *v6 )
              {
                Library = LoadLibraryExW(v8, 0, 0x2Au);
                *_errno() = 0;
                v13 = _wtol(v6);
                if ( Library && !*_errno() )
                  IconW = LoadIconW(Library, (LPCWSTR)v13);
                FreeLibrary(Library);
              }
            }
            else
            {
              *v7 = 0;
            }
          }
          CoTaskMemFree(v8);
        }
      }
    }
  }
  return IconW;
}

```

## disassembly

```asm
0x140019338  push    rbx
0x14001933a  push    rbp
0x14001933b  push    rsi
0x14001933c  push    rdi
0x14001933d  push    r12
0x14001933f  push    r14
0x140019341  push    r15
0x140019343  sub     rsp, 20h
0x140019347  xor     r12d, r12d
0x14001934a  mov     rdi, rcx
0x14001934d  mov     r15d, r12d
0x140019350  test    rcx, rcx
0x140019353  jz      loc_140019484
0x140019359  cmp     word ptr [rcx], 40h ; '@'
0x14001935d  jnz     loc_140019484
0x140019363  lea     ebx, [r12+1]
0x140019368  lea     edx, [rbx+2Bh]
0x14001936b  mov     eax, ebx
0x14001936d  cmp     [rcx+rax*2], r12w
0x140019372  jz      short loc_140019384
0x140019374  cmp     [rcx+rax*2], dx
0x140019378  jz      short loc_140019384
0x14001937a  inc     ebx
0x14001937c  cmp     ebx, 7FFFFFFFh
0x140019382  jb      short loc_14001936B
0x140019384  mov     esi, ebx
0x140019386  lea     rcx, [rsi+rsi]; cb
0x14001938a  cmp     dx, [rcx+rdi]
0x14001938e  jnz     loc_140019484
0x140019394  lea     edx, [rbx+1]
0x140019397  mov     eax, 2Dh ; '-'
0x14001939c  cmp     ax, [rdi+rdx*2]
0x1400193a0  jnz     loc_140019484
0x1400193a6  lea     eax, [rbx+2]
0x1400193a9  lea     rbp, [rdi+rax*2]
0x1400193ad  cmp     [rbp+0], r12w
0x1400193b2  jz      loc_140019484
0x1400193b8  call    cs:__imp_CoTaskMemAlloc
0x1400193be  mov     r14, rax
0x1400193c1  test    rax, rax
0x1400193c4  jz      loc_140019484
0x1400193ca  test    ebx, ebx
0x1400193cc  jz      loc_14001947B
0x1400193d2  cmp     rsi, 7FFFFFFFh
0x1400193d9  ja      short loc_1400193E7
0x1400193db  lea     ecx, [rbx-1]
0x1400193de  cmp     rcx, 7FFFFFFEh
0x1400193e5  jbe     short loc_1400193F0
0x1400193e7  mov     [rax], r12w
0x1400193eb  jmp     loc_14001947B
0x1400193f0  add     rdi, 2
0x1400193f4  test    rcx, rcx
0x1400193f7  jz      short loc_140019415
0x1400193f9  movzx   edx, word ptr [rdi]
0x1400193fc  test    dx, dx
0x1400193ff  jz      short loc_140019415
0x140019401  mov     [rax], dx
0x140019404  add     rdi, 2
0x140019408  add     rax, 2
0x14001940c  dec     rcx
0x14001940f  sub     rsi, 1
0x140019413  jnz     short loc_1400193F4
0x140019415  test    rsi, rsi
0x140019418  lea     rcx, [rax-2]
0x14001941c  cmovnz  rcx, rax
0x140019420  mov     [rcx], r12w
0x140019424  jz      short loc_14001947B
0x140019426  cmp     [rbp+0], r12w
0x14001942b  jz      short loc_14001947B
0x14001942d  xor     edx, edx; hFile
0x14001942f  mov     rcx, r14; lpLibFileName
0x140019432  lea     r8d, [rdx+2Ah]; dwFlags
0x140019436  call    cs:__imp_LoadLibraryExW
0x14001943c  mov     rbx, rax
0x14001943f  call    cs:__imp__errno
0x140019445  mov     rcx, rbp; String
0x140019448  mov     [rax], r12d
0x14001944b  call    cs:__imp__wtol
0x140019451  mov     edi, eax
0x140019453  test    rbx, rbx
0x140019456  jz      short loc_140019472
0x140019458  call    cs:__imp__errno
0x14001945e  cmp     [rax], r12d
0x140019461  jnz     short loc_140019472
0x140019463  movzx   edx, di; lpIconName
0x140019466  mov     rcx, rbx; hInstance
0x140019469  call    cs:__imp_LoadIconW
0x14001946f  mov     r15, rax
0x140019472  mov     rcx, rbx; hLibModule
0x140019475  call    cs:__imp_FreeLibrary
0x14001947b  mov     rcx, r14; pv
0x14001947e  call    cs:__imp_CoTaskMemFree
0x140019484  mov     rax, r15
0x140019487  add     rsp, 20h
0x14001948b  pop     r15
0x14001948d  pop     r14
0x14001948f  pop     r12
0x140019491  pop     rdi
0x140019492  pop     rsi
0x140019493  pop     rbp
0x140019494  pop     rbx
0x140019495  retn
```
