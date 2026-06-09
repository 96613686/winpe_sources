# ProvisioningPaths::GetCosaFolderPath_MO(void)

- ea: `0x1800380d8`
- end: `0x1800381a1`
- name: `?GetCosaFolderPath_MO@ProvisioningPaths@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `201`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001a4a0`

## callees

- `0x1800021b4`
- `0x18000b030`
- `0x180021f40`
- `0x18003804c`
- `0x1800380d8`
- `0x180038278`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003815e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038176`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003815e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038176`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ProvisioningPaths::GetCosaFolderPath_MO()
{
  struct ProvisioningPaths *Instance; // rsi
  const void **v1; // rbx
  char *v2; // rdx
  unsigned __int64 v3; // r8
  __int64 v4; // rdi

  Instance = ProvisioningPaths::GetInstance();
  if ( !*((_QWORD *)Instance + 6) )
  {
    v1 = (const void **)operator new(0x20u);
    if ( v1 )
    {
      v2 = *(char **)ProvisioningPaths::GetCosaFolderPath();
      v1[3] = (const void *)7;
      v1[2] = 0;
      *(_WORD *)v1 = 0;
      if ( *(_WORD *)v2 )
      {
        v3 = -1;
        do
          ++v3;
        while ( *(_WORD *)&v2[2 * v3] );
      }
      else
      {
        v3 = 0;
      }
      std::wstring::assign(v1, v2, v3);
    }
    else
    {
      v1 = 0;
    }
    v4 = *((_QWORD *)Instance + 6);
    if ( v1 == (const void **)v4 )
    {
      v1 = (const void **)*((_QWORD *)Instance + 6);
    }
    else
    {
      if ( v4 )
      {
        if ( *(_QWORD *)(v4 + 24) >= 8u )
          operator delete(*(void **)v4);
        *(_QWORD *)(v4 + 24) = 7;
        *(_QWORD *)(v4 + 16) = 0;
        *(_WORD *)v4 = 0;
        operator delete((void *)v4);
      }
      *((_QWORD *)Instance + 6) = v1;
    }
    std::wstring::append(v1, (char *)L"\\MO");
  }
  return *((_QWORD *)Instance + 6);
}

```

## disassembly

```asm
0x1800380d8  push    rbx
0x1800380da  push    rbp
0x1800380db  push    rsi
0x1800380dc  push    rdi
0x1800380dd  sub     rsp, 28h
0x1800380e1  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x1800380e6  mov     rsi, rax
0x1800380e9  xor     ebp, ebp
0x1800380eb  cmp     [rax+30h], rbp
0x1800380ef  jnz     loc_180038194
0x1800380f5  lea     ecx, [rbp+20h]; Size
0x1800380f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800380fd  mov     rbx, rax
0x180038100  mov     [rsp+48h+arg_0], rax
0x180038105  test    rax, rax
0x180038108  jz      short loc_180038143
0x18003810a  call    ?GetCosaFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetCosaFolderPath(void)
0x18003810f  mov     rdx, [rax]; Src
0x180038112  mov     qword ptr [rbx+18h], 7
0x18003811a  mov     [rbx+10h], rbp
0x18003811e  mov     [rbx], bp
0x180038121  cmp     [rdx], bp
0x180038124  jnz     short loc_18003812B
0x180038126  mov     r8d, ebp
0x180038129  jmp     short loc_180038139
0x18003812b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003812f  inc     r8
0x180038132  cmp     [rdx+r8*2], bp
0x180038137  jnz     short loc_18003812F
0x180038139  mov     rcx, rbx; void *
0x18003813c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038141  jmp     short loc_180038146
0x180038143  mov     rbx, rbp
0x180038146  mov     rdi, [rsi+30h]
0x18003814a  cmp     rbx, rdi
0x18003814d  jz      short loc_180038182
0x18003814f  test    rdi, rdi
0x180038152  jz      short loc_18003817C
0x180038154  cmp     qword ptr [rdi+18h], 8
0x180038159  jb      short loc_180038164
0x18003815b  mov     rcx, [rdi]
0x18003815e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038164  mov     qword ptr [rdi+18h], 7
0x18003816c  mov     [rdi+10h], rbp
0x180038170  mov     [rdi], bp
0x180038173  mov     rcx, rdi
0x180038176  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003817c  mov     [rsi+30h], rbx
0x180038180  jmp     short loc_180038185
0x180038182  mov     rbx, rdi
0x180038185  lea     rdx, aMo; "\\MO"
0x18003818c  mov     rcx, rbx; Src
0x18003818f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180038194  mov     rax, [rsi+30h]
0x180038198  add     rsp, 28h
0x18003819c  pop     rdi
0x18003819d  pop     rsi
0x18003819e  pop     rbp
0x18003819f  pop     rbx
0x1800381a0  retn
```
