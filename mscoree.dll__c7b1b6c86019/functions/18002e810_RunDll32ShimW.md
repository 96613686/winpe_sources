# RunDll32ShimW

- ea: `0x18002e810`
- end: `0x18002eaed`
- name: `RunDll32ShimW`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x180026980`

## callees

- `0x180002710`
- `0x180003740`
- `0x180003840`
- `0x180006420`
- `0x18000dec8`
- `0x18002e810`
- `0x180041ac0`
- `0x180041b20`
- `0x180041ec0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002e9fc`
- `KERNEL32!GetProcAddress` at `0x18002ea78`
- `KERNEL32!GetProcAddress` at `0x18002e9fc`
- `KERNEL32!GetProcAddress` at `0x18002ea78`
- `KERNEL32!WideCharToMultiByte` at `0x18002e9bb`
- `KERNEL32!WideCharToMultiByte` at `0x18002e9bb`

## string_xrefs

- `0x18002e9d8`: `Fusion.dll`
- `0x18002e9f5`: `CreateAssemblyNameObject`

## pseudocode

```c
__int64 __fastcall RunDll32ShimW(__int64 a1, __int64 a2, _WORD *a3, unsigned int a4)
{
  unsigned __int64 v7; // rbx
  __int64 v8; // r8
  wchar_t *v9; // rsi
  int LibraryShim_0; // ebx
  unsigned __int128 v11; // rax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // r15
  wchar_t *v15; // rax
  const WCHAR *v16; // r8
  WCHAR v17; // ax
  __int16 *i; // rdi
  __int16 v19; // ax
  __int64 v20; // rax
  int v21; // edx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  __int64 v26; // r8
  FARPROC ProcAddress; // rax
  __int64 v28; // r8
  FARPROC v29; // rax
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  int v32; // [rsp+48h] [rbp+8h] BYREF
  int v33; // [rsp+4Ch] [rbp+Ch] BYREF
  int v34; // [rsp+50h] [rbp+10h] BYREF
  unsigned int v35; // [rsp+54h] [rbp+14h]
  HMODULE hModule; // [rsp+58h] [rbp+18h] BYREF
  unsigned __int64 v37; // [rsp+60h] [rbp+20h] BYREF
  char v38; // [rsp+68h] [rbp+28h]
  wchar_t Source[264]; // [rsp+70h] [rbp+30h] BYREF

  v35 = a4;
  hModule = 0;
  *(_QWORD *)MultiByteStr = 0;
  v34 = 0;
  v33 = 0;
  v32 = 520;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  if ( !v7 )
    return (unsigned int)-2147024809;
  v37 = v7;
  v38 = 0;
  ClrSafeInt<unsigned __int64>::operator+=(&v37);
  if ( v38 )
  {
    v9 = 0;
    LibraryShim_0 = -2146233066;
  }
  else
  {
    v11 = v37 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v37, 2u) )
      *(_QWORD *)&v11 = v8;
    v12 = (wchar_t *)operator new(v11, *((const struct NoThrow **)&v11 + 1));
    v9 = v12;
    if ( v12 )
    {
      memmove(v12, a3, 2 * v7 + 2);
      v13 = wcschr(v9, 0x22u);
      if ( v13 && (v14 = v13 + 1, v15 = wcschr(v13 + 1, 0x22u), (v16 = v15) != 0) )
      {
        *v15 = 0;
        do
          v17 = *++v16;
        while ( *v16 && (v17 == 32 || v17 == 9) );
        for ( i = (__int16 *)(v16 + 1); ; ++i )
        {
          v19 = *i;
          if ( !*i || v19 == 32 || v19 == 9 )
            break;
        }
        *i = 0;
        v20 = -1;
        do
          ++v20;
        while ( v16[v20] );
        v21 = 2 * v20 + 2;
        v22 = v21 + 15LL;
        if ( v22 <= v21 )
          v22 = 0xFFFFFFFFFFFFFF0LL;
        v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
        v24 = alloca(v23);
        v25 = alloca(v23);
        if ( WideCharToMultiByte(0, 0, v16, -1, MultiByteStr, 2 * v20 + 1, 0, 0) )
        {
          LibraryShim_0 = LoadLibraryShim_0((wchar_t *)L"Fusion.dll", 0, v26, &g_hFusionMod);
          if ( LibraryShim_0 < 0 )
            goto LABEL_38;
          ProcAddress = GetProcAddress(g_hFusionMod, "CreateAssemblyNameObject");
          if ( ProcAddress )
          {
            LibraryShim_0 = ((__int64 (__fastcall *)(CHAR *, wchar_t *, __int64))ProcAddress)(MultiByteStr, v14, 1);
            if ( LibraryShim_0 >= 0 )
            {
              LibraryShim_0 = (*(__int64 (__fastcall **)(_QWORD, int *, wchar_t *))(**(_QWORD **)MultiByteStr + 64LL))(
                                *(_QWORD *)MultiByteStr,
                                &v32,
                                Source);
              if ( LibraryShim_0 >= 0 )
              {
                LibraryShim_0 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**(_QWORD **)MultiByteStr + 72LL))(
                                  *(_QWORD *)MultiByteStr,
                                  &v34,
                                  &v33);
                if ( LibraryShim_0 >= 0 )
                {
                  LibraryShim_0 = LoadLibraryShim_0(Source, 0, v28, &hModule);
                  if ( LibraryShim_0 >= 0 )
                  {
                    v29 = GetProcAddress(hModule, MultiByteStr);
                    if ( v29 )
                      LibraryShim_0 = ((__int64 (__fastcall *)(__int64, __int64, __int16 *, _QWORD))v29)(
                                        a1,
                                        a2,
                                        i + 1,
                                        v35);
                    else
                      LibraryShim_0 = -2147467262;
                  }
                }
              }
            }
            goto LABEL_38;
          }
        }
        LibraryShim_0 = -2147467259;
      }
      else
      {
        LibraryShim_0 = -2147024809;
      }
    }
    else
    {
      LibraryShim_0 = -2147024882;
    }
  }
LABEL_38:
  if ( *(_QWORD *)MultiByteStr )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)MultiByteStr + 16LL))(*(_QWORD *)MultiByteStr);
  if ( v9 )
    operator delete(v9);
  return (unsigned int)LibraryShim_0;
}

```

## disassembly

```asm
0x18002e810  push    rbp
0x18002e812  push    rbx
0x18002e813  push    rsi
0x18002e814  push    rdi
0x18002e815  push    r12
0x18002e817  push    r13
0x18002e819  push    r14
0x18002e81b  push    r15
0x18002e81d  sub     rsp, 298h
0x18002e824  lea     rbp, [rsp+40h]
0x18002e829  mov     rax, cs:__security_cookie
0x18002e830  xor     rax, rbp
0x18002e833  mov     [rbp+290h+var_50], rax
0x18002e83a  xor     r14d, r14d
0x18002e83d  mov     [rbp+290h+var_27C], r9d
0x18002e841  mov     [rbp+290h+hModule], r14
0x18002e845  mov     rdi, r8
0x18002e848  mov     qword ptr [rbp+290h+MultiByteStr], r14
0x18002e84c  mov     r13, rdx
0x18002e84f  mov     [rbp+290h+var_280], r14d
0x18002e853  mov     r12, rcx
0x18002e856  mov     [rbp+290h+var_284], r14d
0x18002e85a  mov     [rbp+290h+var_288], 208h
0x18002e861  test    r8, r8
0x18002e864  jz      loc_18002EAC3
0x18002e86a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e86e  mov     rbx, r8
0x18002e871  inc     rbx
0x18002e874  cmp     [rdi+rbx*2], r14w
0x18002e879  jnz     short loc_18002E871
0x18002e87b  test    rbx, rbx
0x18002e87e  jz      loc_18002EAC3
0x18002e884  lea     rcx, [rbp+290h+var_270]
0x18002e888  mov     [rbp+290h+var_270], rbx
0x18002e88c  mov     [rbp+290h+var_268], r14b
0x18002e890  call    ??Y?$ClrSafeInt@_K@@QEAAAEAV0@_K@Z; ClrSafeInt<unsigned __int64>::operator+=(unsigned __int64)
0x18002e895  cmp     [rbp+290h+var_268], r14b
0x18002e899  jz      short loc_18002E8A8
0x18002e89b  mov     rsi, r14
0x18002e89e  mov     ebx, 80131516h
0x18002e8a3  jmp     loc_18002EA9F
0x18002e8a8  mov     eax, 2
0x18002e8ad  mul     [rbp+290h+var_270]
0x18002e8b1  cmovb   rax, r8
0x18002e8b5  mov     rcx, rax; unsigned __int64
0x18002e8b8  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002e8bd  mov     rsi, rax
0x18002e8c0  test    rax, rax
0x18002e8c3  jnz     short loc_18002E8CF
0x18002e8c5  mov     ebx, 8007000Eh
0x18002e8ca  jmp     loc_18002EA9F
0x18002e8cf  lea     r8, ds:2[rbx*2]; Size
0x18002e8d7  mov     rdx, rdi; Src
0x18002e8da  mov     rcx, rsi; void *
0x18002e8dd  call    memmove
0x18002e8e2  mov     ebx, 22h ; '"'
0x18002e8e7  mov     rcx, rsi; Str
0x18002e8ea  mov     edx, ebx; Ch
0x18002e8ec  call    wcschr
0x18002e8f1  test    rax, rax
0x18002e8f4  jnz     short loc_18002E900
0x18002e8f6  mov     ebx, 80070057h
0x18002e8fb  jmp     loc_18002EA9F
0x18002e900  lea     r15, [rax+2]
0x18002e904  mov     edx, ebx; Ch
0x18002e906  mov     rcx, r15; Str
0x18002e909  call    wcschr
0x18002e90e  mov     r8, rax
0x18002e911  test    rax, rax
0x18002e914  jz      short loc_18002E8F6
0x18002e916  mov     [rax], r14w
0x18002e91a  jmp     short loc_18002E928
0x18002e91c  cmp     ax, 20h ; ' '
0x18002e920  jz      short loc_18002E928
0x18002e922  cmp     ax, 9
0x18002e926  jnz     short loc_18002E935
0x18002e928  add     r8, 2
0x18002e92c  movzx   eax, word ptr [r8]
0x18002e930  test    ax, ax
0x18002e933  jnz     short loc_18002E91C
0x18002e935  lea     rdi, [r8+2]
0x18002e939  jmp     short loc_18002E94B
0x18002e93b  cmp     ax, 20h ; ' '
0x18002e93f  jz      short loc_18002E953
0x18002e941  cmp     ax, 9
0x18002e945  jz      short loc_18002E953
0x18002e947  add     rdi, 2
0x18002e94b  movzx   eax, word ptr [rdi]
0x18002e94e  test    ax, ax
0x18002e951  jnz     short loc_18002E93B
0x18002e953  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002e957  mov     [rdi], r14w
0x18002e95b  mov     rax, r9
0x18002e95e  inc     rax
0x18002e961  cmp     [r8+rax*2], r14w
0x18002e966  jnz     short loc_18002E95E
0x18002e968  lea     edx, ds:2[rax*2]
0x18002e96f  movsxd  rax, edx
0x18002e972  lea     rcx, [rax+0Fh]
0x18002e976  cmp     rcx, rax
0x18002e979  ja      short loc_18002E985
0x18002e97b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002e985  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002e989  mov     rax, rcx
0x18002e98c  call    _alloca_probe
0x18002e991  sub     rsp, rcx
0x18002e994  lea     eax, [rdx-1]
0x18002e997  xor     edx, edx; dwFlags
0x18002e999  xor     ecx, ecx; CodePage
0x18002e99b  mov     [rsp+2D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18002e9a4  lea     r14, [rsp+2D0h+MultiByteStr]
0x18002e9a9  mov     [rsp+2D0h+lpDefaultChar], 0; lpDefaultChar
0x18002e9b2  mov     [rsp+2D0h+cbMultiByte], eax; cbMultiByte
0x18002e9b6  mov     [rsp+2D0h+lpMultiByteStr], r14; lpMultiByteStr
0x18002e9bb  call    cs:__imp_WideCharToMultiByte
0x18002e9c1  test    eax, eax
0x18002e9c3  jnz     short loc_18002E9CF
0x18002e9c5  mov     ebx, 80004005h
0x18002e9ca  jmp     loc_18002EA9F
0x18002e9cf  lea     r9, ?g_hFusionMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hFusionMod
0x18002e9d6  xor     edx, edx; wchar_t *
0x18002e9d8  lea     rcx, aFusionDll; "Fusion.dll"
0x18002e9df  call    LoadLibraryShim_0
0x18002e9e4  mov     ebx, eax
0x18002e9e6  test    eax, eax
0x18002e9e8  js      loc_18002EA9F
0x18002e9ee  mov     rcx, cs:?g_hFusionMod@@3PEAUHINSTANCE__@@EA; hModule
0x18002e9f5  lea     rdx, aCreateassembly; "CreateAssemblyNameObject"
0x18002e9fc  call    cs:__imp_GetProcAddress
0x18002ea02  test    rax, rax
0x18002ea05  jz      short loc_18002E9C5
0x18002ea07  xor     r9d, r9d
0x18002ea0a  lea     rcx, [rbp+290h+MultiByteStr]
0x18002ea0e  mov     rdx, r15
0x18002ea11  lea     r8d, [r9+1]
0x18002ea15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea1a  mov     ebx, eax
0x18002ea1c  test    eax, eax
0x18002ea1e  js      short loc_18002EA9F
0x18002ea20  mov     rcx, qword ptr [rbp+290h+MultiByteStr]
0x18002ea24  lea     r8, [rbp+290h+Source]
0x18002ea28  lea     rdx, [rbp+290h+var_288]
0x18002ea2c  mov     rax, [rcx]
0x18002ea2f  mov     rax, [rax+40h]
0x18002ea33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea38  mov     ebx, eax
0x18002ea3a  test    eax, eax
0x18002ea3c  js      short loc_18002EA9F
0x18002ea3e  mov     rcx, qword ptr [rbp+290h+MultiByteStr]
0x18002ea42  lea     r8, [rbp+290h+var_284]
0x18002ea46  lea     rdx, [rbp+290h+var_280]
0x18002ea4a  mov     rax, [rcx]
0x18002ea4d  mov     rax, [rax+48h]
0x18002ea51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea56  mov     ebx, eax
0x18002ea58  test    eax, eax
0x18002ea5a  js      short loc_18002EA9F
0x18002ea5c  lea     r9, [rbp+290h+hModule]
0x18002ea60  xor     edx, edx; wchar_t *
0x18002ea62  lea     rcx, [rbp+290h+Source]; Source
0x18002ea66  call    LoadLibraryShim_0
0x18002ea6b  mov     ebx, eax
0x18002ea6d  test    eax, eax
0x18002ea6f  js      short loc_18002EA9F
0x18002ea71  mov     rcx, [rbp+290h+hModule]; hModule
0x18002ea75  mov     rdx, r14; lpProcName
0x18002ea78  call    cs:__imp_GetProcAddress
0x18002ea7e  test    rax, rax
0x18002ea81  jnz     short loc_18002EA8A
0x18002ea83  mov     ebx, 80004002h
0x18002ea88  jmp     short loc_18002EA9F
0x18002ea8a  mov     r9d, [rbp+290h+var_27C]
0x18002ea8e  lea     r8, [rdi+2]
0x18002ea92  mov     rdx, r13
0x18002ea95  mov     rcx, r12
0x18002ea98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea9d  mov     ebx, eax
0x18002ea9f  mov     rcx, qword ptr [rbp+290h+MultiByteStr]
0x18002eaa3  test    rcx, rcx
0x18002eaa6  jz      short loc_18002EAB4
0x18002eaa8  mov     rax, [rcx]
0x18002eaab  mov     rax, [rax+10h]
0x18002eaaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eab4  test    rsi, rsi
0x18002eab7  jz      short loc_18002EAC8
0x18002eab9  mov     rcx, rsi; void *
0x18002eabc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002eac1  jmp     short loc_18002EAC8
0x18002eac3  mov     ebx, 80070057h
0x18002eac8  mov     eax, ebx
0x18002eaca  mov     rcx, [rbp+290h+var_50]
0x18002ead1  xor     rcx, rbp; StackCookie
0x18002ead4  call    __security_check_cookie
0x18002ead9  lea     rsp, [rbp+258h]
0x18002eae0  pop     r15
0x18002eae2  pop     r14
0x18002eae4  pop     r13
0x18002eae6  pop     r12
0x18002eae8  pop     rdi
0x18002eae9  pop     rsi
0x18002eaea  pop     rbx
0x18002eaeb  pop     rbp
0x18002eaec  retn
```
