# ProvisioningPaths::GetCosaFolderPath_OEM(void)

- ea: `0x1800381a8`
- end: `0x180038271`
- name: `?GetCosaFolderPath_OEM@ProvisioningPaths@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
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
- `0x1800381a8`
- `0x180038278`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003822e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038246`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003822e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180038246`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ProvisioningPaths::GetCosaFolderPath_OEM()
{
  struct ProvisioningPaths *Instance; // rsi
  const void **v1; // rbx
  char *v2; // rdx
  unsigned __int64 v3; // r8
  __int64 v4; // rdi

  Instance = ProvisioningPaths::GetInstance();
  if ( !*((_QWORD *)Instance + 5) )
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
    v4 = *((_QWORD *)Instance + 5);
    if ( v1 == (const void **)v4 )
    {
      v1 = (const void **)*((_QWORD *)Instance + 5);
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
      *((_QWORD *)Instance + 5) = v1;
    }
    std::wstring::append(v1, (char *)L"\\OEM");
  }
  return *((_QWORD *)Instance + 5);
}

```

## disassembly

```asm
0x1800381a8  push    rbx
0x1800381aa  push    rbp
0x1800381ab  push    rsi
0x1800381ac  push    rdi
0x1800381ad  sub     rsp, 28h
0x1800381b1  call    ?GetInstance@ProvisioningPaths@@CAAEAV1@XZ; ProvisioningPaths::GetInstance(void)
0x1800381b6  mov     rsi, rax
0x1800381b9  xor     ebp, ebp
0x1800381bb  cmp     [rax+28h], rbp
0x1800381bf  jnz     loc_180038264
0x1800381c5  lea     ecx, [rbp+20h]; Size
0x1800381c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800381cd  mov     rbx, rax
0x1800381d0  mov     [rsp+48h+arg_0], rax
0x1800381d5  test    rax, rax
0x1800381d8  jz      short loc_180038213
0x1800381da  call    ?GetCosaFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetCosaFolderPath(void)
0x1800381df  mov     rdx, [rax]; Src
0x1800381e2  mov     qword ptr [rbx+18h], 7
0x1800381ea  mov     [rbx+10h], rbp
0x1800381ee  mov     [rbx], bp
0x1800381f1  cmp     [rdx], bp
0x1800381f4  jnz     short loc_1800381FB
0x1800381f6  mov     r8d, ebp
0x1800381f9  jmp     short loc_180038209
0x1800381fb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800381ff  inc     r8
0x180038202  cmp     [rdx+r8*2], bp
0x180038207  jnz     short loc_1800381FF
0x180038209  mov     rcx, rbx; void *
0x18003820c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038211  jmp     short loc_180038216
0x180038213  mov     rbx, rbp
0x180038216  mov     rdi, [rsi+28h]
0x18003821a  cmp     rbx, rdi
0x18003821d  jz      short loc_180038252
0x18003821f  test    rdi, rdi
0x180038222  jz      short loc_18003824C
0x180038224  cmp     qword ptr [rdi+18h], 8
0x180038229  jb      short loc_180038234
0x18003822b  mov     rcx, [rdi]
0x18003822e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180038234  mov     qword ptr [rdi+18h], 7
0x18003823c  mov     [rdi+10h], rbp
0x180038240  mov     [rdi], bp
0x180038243  mov     rcx, rdi
0x180038246  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003824c  mov     [rsi+28h], rbx
0x180038250  jmp     short loc_180038255
0x180038252  mov     rbx, rdi
0x180038255  lea     rdx, aOem; "\\OEM"
0x18003825c  mov     rcx, rbx; Src
0x18003825f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180038264  mov     rax, [rsi+28h]
0x180038268  add     rsp, 28h
0x18003826c  pop     rdi
0x18003826d  pop     rsi
0x18003826e  pop     rbp
0x18003826f  pop     rbx
0x180038270  retn
```
