# Filter_SetNamespace

- ea: `0x180041858`
- end: `0x180041991`
- name: `Filter_SetNamespace`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180041540`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180007ea0`
- `0x180041858`

## import_xrefs

- `msvcrt!free` at `0x180041950`
- `msvcrt!free` at `0x180041961`
- `msvcrt!free` at `0x180041950`
- `msvcrt!free` at `0x180041961`
- `msvcrt!calloc` at `0x180041909`
- `msvcrt!calloc` at `0x180041909`
- `msvcrt!_wcsdup` at `0x18004192c`
- `msvcrt!_wcsdup` at `0x18004192c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180041898`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180041898`

## string_xrefs

- `0x18004188c`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Filter_SetNamespace(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // rdi
  __int64 v5; // rbx
  HMODULE ModuleHandleA; // rax
  size_t v7; // r14
  _QWORD *v8; // rbx
  __int64 v9; // r15
  __int64 v10; // rbp
  wchar_t *v11; // rax
  size_t i; // rbp
  void *v13; // rcx

  if ( !*(_QWORD *)(a1 + 24) )
  {
    v4 = a2 + 1;
    if ( !*(_DWORD *)(a1 + 64) && *v4 != 1 )
    {
      v5 = *(_QWORD *)(a1 + 48);
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(ModuleHandleA, 2129, v5);
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      return 0xFFFFFFFFLL;
    }
    if ( *v4 )
    {
      v7 = (unsigned int)*v4;
      v8 = calloc(v7, 8u);
      if ( v8 )
      {
        v9 = *a2;
        v10 = 0;
        if ( !v7 )
        {
LABEL_18:
          *(_QWORD *)(a1 + 168) = v8;
          if ( !v8 )
            return 0xFFFFFFFFLL;
          *(_DWORD *)(a1 + 176) = *v4;
          return 0;
        }
        while ( 1 )
        {
          v11 = _wcsdup(*(const wchar_t **)(v9 + 8 * v10));
          v8[v10] = v11;
          if ( !v11 )
            break;
          if ( ++v10 >= v7 )
            goto LABEL_18;
        }
        for ( i = 0; i < v7; ++i )
        {
          v13 = (void *)v8[i];
          if ( v13 )
            free(v13);
        }
        free(v8);
      }
      else
      {
        MI_ReportErrorDetails_OutOfMemory();
      }
      v8 = 0;
      goto LABEL_18;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180041858  push    rbx
0x18004185a  push    rbp
0x18004185b  push    rsi
0x18004185c  push    rdi
0x18004185d  push    r14
0x18004185f  push    r15
0x180041861  sub     rsp, 48h
0x180041865  cmp     qword ptr [rcx+18h], 0
0x18004186a  mov     r15, rdx
0x18004186d  mov     rsi, rcx
0x180041870  jnz     loc_180041982
0x180041876  cmp     dword ptr [rcx+40h], 0
0x18004187a  lea     rdi, [rdx+8]
0x18004187e  jnz     short loc_1800418F5
0x180041880  cmp     dword ptr [rdi], 1
0x180041883  jz      short loc_1800418F5
0x180041885  mov     rbx, [rcx+30h]
0x180041889  xorps   xmm0, xmm0
0x18004188c  lea     rcx, ModuleName; "mpunits.dll"
0x180041893  movups  [rsp+78h+var_48], xmm0
0x180041898  call    cs:__imp_GetModuleHandleA
0x18004189e  mov     r8, rbx
0x1800418a1  mov     edx, 851h
0x1800418a6  mov     rcx, rax
0x1800418a9  call    _Intlstr_FormatString_FormatMessage
0x1800418ae  mov     qword ptr [rsp+78h+var_48], rax
0x1800418b3  lea     r9, [rsp+78h+var_48]
0x1800418b8  mov     byte ptr [rsp+78h+var_48+8], 1
0x1800418bd  lea     rdx, aMi; "MI"
0x1800418c4  movaps  xmm0, [rsp+78h+var_48]
0x1800418c9  mov     r8d, 6
0x1800418cf  mov     [rsp+78h+var_50], 0; __int64
0x1800418d8  movdqa  [rsp+78h+var_48], xmm0
0x1800418de  mov     [rsp+78h+var_58], 0; __int64
0x1800418e7  lea     ecx, [r8-2]; int
0x1800418eb  call    MI_ReportErrorDetails_ForCustomError
0x1800418f0  jmp     loc_180041975
0x1800418f5  cmp     dword ptr [rdi], 0
0x1800418f8  jz      loc_180041982
0x1800418fe  mov     r14d, [rdi]
0x180041901  mov     edx, 8; Size
0x180041906  mov     ecx, r14d; Count
0x180041909  call    cs:__imp_calloc
0x18004190f  mov     rbx, rax
0x180041912  test    rax, rax
0x180041915  jnz     short loc_18004191E
0x180041917  call    MI_ReportErrorDetails_OutOfMemory
0x18004191c  jmp     short loc_180041967
0x18004191e  mov     r15, [r15]
0x180041921  xor     ebp, ebp
0x180041923  test    r14, r14
0x180041926  jz      short loc_180041969
0x180041928  mov     rcx, [r15+rbp*8]; String
0x18004192c  call    cs:__imp__wcsdup
0x180041932  mov     [rbx+rbp*8], rax
0x180041936  test    rax, rax
0x180041939  jz      short loc_180041945
0x18004193b  inc     rbp
0x18004193e  cmp     rbp, r14
0x180041941  jb      short loc_180041928
0x180041943  jmp     short loc_180041969
0x180041945  xor     ebp, ebp
0x180041947  mov     rcx, [rbx+rbp*8]; Block
0x18004194b  test    rcx, rcx
0x18004194e  jz      short loc_180041956
0x180041950  call    cs:__imp_free
0x180041956  inc     rbp
0x180041959  cmp     rbp, r14
0x18004195c  jb      short loc_180041947
0x18004195e  mov     rcx, rbx; Block
0x180041961  call    cs:__imp_free
0x180041967  xor     ebx, ebx
0x180041969  mov     [rsi+0A8h], rbx
0x180041970  test    rbx, rbx
0x180041973  jnz     short loc_18004197A
0x180041975  or      eax, 0FFFFFFFFh
0x180041978  jmp     short loc_180041984
0x18004197a  mov     eax, [rdi]
0x18004197c  mov     [rsi+0B0h], eax
0x180041982  xor     eax, eax
0x180041984  add     rsp, 48h
0x180041988  pop     r15
0x18004198a  pop     r14
0x18004198c  pop     rdi
0x18004198d  pop     rsi
0x18004198e  pop     rbp
0x18004198f  pop     rbx
0x180041990  retn
```
