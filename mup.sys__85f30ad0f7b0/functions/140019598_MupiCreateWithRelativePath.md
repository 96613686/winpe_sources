# MupiCreateWithRelativePath

- ea: `0x140019598`
- end: `0x140019727`
- name: `MupiCreateWithRelativePath`
- size: `399`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14001a3c0`

## callees

- `0x140001c10`
- `0x14000ff6c`
- `0x140017f50`
- `0x140019380`
- `0x140019598`
- `0x14001ca50`
- `0x14001cb10`
- `0x14001cbd0`
- `0x14001de48`

## pseudocode

```c
__int64 __fastcall MupiCreateWithRelativePath(__int64 a1, char a2, _QWORD *a3)
{
  __int64 FileContext; // rsi
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx

  *a3 = 0;
  if ( *(_WORD *)(a1 + 88) >= 2u && **(_WORD **)(a1 + 96) == 92 )
  {
    v7 = -1073741811;
  }
  else
  {
    FileContext = MupFindFileContext(*(_QWORD *)(a1 + 64));
    if ( FileContext )
    {
      v7 = MupAllocFileContextForRelativeOpen((PCUNICODE_STRING)(a1 + 88));
      if ( !v7 )
      {
        MEMORY[0x90] = a1;
        MEMORY[0x98] = FileContext;
        if ( *(_QWORD *)(FileContext + 88) )
          v7 = MupSetupUndecoratedFileNameForRelativeOpen(0);
        if ( !v7 )
        {
          v8 = *(_QWORD *)(FileContext + 184);
          if ( v8 )
          {
            MEMORY[0xA8] = 0;
            _InterlockedIncrement((volatile signed __int32 *)(v8 + 4));
          }
          else
          {
            v9 = *(_QWORD *)(FileContext + 168);
            if ( v9 )
              _InterlockedIncrement((volatile signed __int32 *)(v9 + 4));
            MEMORY[0xA8] = v9;
          }
          MEMORY[0xA0] = *(_DWORD *)(FileContext + 160);
          MEMORY[0xB8] = *(_QWORD *)(FileContext + 184);
          MupSaveProviderStrippedFileName(0, 1);
          LOBYTE(v10) = 1;
          MupSaveStrippedFileName(0, v10);
          v7 = MupInitializeUncHardeningFileContext((UNICODE_STRING *)0x80, (PUNICODE_STRING **)0xF8);
          if ( v7 >= 0 )
          {
            LOBYTE(v11) = a2;
            v7 = MupSetupRelatedSurrogateFileContextList(0, v11);
          }
        }
      }
    }
    else
    {
      v7 = -1073741808;
    }
  }
  *a3 = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140019598  mov     rax, rsp
0x14001959b  mov     [rax+8], rbx
0x14001959f  mov     [rax+18h], r8
0x1400195a3  push    rsi
0x1400195a4  push    rdi
0x1400195a5  push    r12
0x1400195a7  push    r14
0x1400195a9  push    r15
0x1400195ab  sub     rsp, 30h
0x1400195af  mov     r14, r8
0x1400195b2  mov     r12b, dl
0x1400195b5  mov     r15, rcx
0x1400195b8  mov     dword ptr [rax-38h], 0
0x1400195bf  xor     edi, edi
0x1400195c1  mov     [rax+20h], rdi
0x1400195c5  mov     [r8], rdi
0x1400195c8  cmp     word ptr [rcx+58h], 2
0x1400195cd  jb      short loc_1400195DD
0x1400195cf  mov     rax, [rcx+60h]
0x1400195d3  cmp     word ptr [rax], 5Ch ; '\'
0x1400195d7  jz      loc_1400196BC
0x1400195dd  mov     rcx, [rcx+40h]
0x1400195e1  call    MupFindFileContext
0x1400195e6  mov     rsi, rax
0x1400195e9  test    rax, rax
0x1400195ec  jz      loc_1400196C7
0x1400195f2  lea     r8, [rsp+58h+P]
0x1400195f7  mov     rdx, rax
0x1400195fa  lea     rcx, [r15+58h]; Source
0x1400195fe  call    MupAllocFileContextForRelativeOpen
0x140019603  mov     ebx, eax
0x140019605  mov     [rsp+58h+var_38], eax
0x140019609  mov     rdi, [rsp+58h+P]
0x14001960e  test    eax, eax
0x140019610  jnz     loc_1400196F5
0x140019616  mov     [rdi+90h], r15
0x14001961d  mov     [rdi+98h], rsi
0x140019624  cmp     qword ptr [rsi+58h], 0
0x140019629  jnz     loc_1400196CE
0x14001962f  test    ebx, ebx
0x140019631  jnz     loc_1400196F5
0x140019637  mov     rax, [rsi+0B8h]
0x14001963e  test    rax, rax
0x140019641  jnz     loc_1400196E1
0x140019647  mov     rax, [rsi+0A8h]
0x14001964e  test    rax, rax
0x140019651  jz      short loc_140019657
0x140019653  lock inc dword ptr [rax+4]
0x140019657  mov     [rdi+0A8h], rax
0x14001965e  mov     eax, [rsi+0A0h]
0x140019664  mov     [rdi+0A0h], eax
0x14001966a  mov     rax, [rsi+0B8h]
0x140019671  mov     [rdi+0B8h], rax
0x140019678  mov     dl, 1
0x14001967a  mov     rcx, rdi
0x14001967d  call    MupSaveProviderStrippedFileName
0x140019682  mov     dl, 1
0x140019684  mov     rcx, rdi
0x140019687  call    MupSaveStrippedFileName
0x14001968c  lea     rdx, [rdi+0F8h]
0x140019693  lea     rcx, [rdi+80h]
0x14001969a  call    MupInitializeUncHardeningFileContext
0x14001969f  mov     ebx, eax
0x1400196a1  mov     [rsp+58h+var_38], eax
0x1400196a5  test    eax, eax
0x1400196a7  js      short loc_1400196F5
0x1400196a9  mov     dl, r12b
0x1400196ac  mov     rcx, rdi
0x1400196af  call    MupSetupRelatedSurrogateFileContextList
0x1400196b4  mov     ebx, eax
0x1400196b6  mov     [rsp+58h+var_38], eax
0x1400196ba  jmp     short loc_1400196F5
0x1400196bc  mov     ebx, 0C000000Dh
0x1400196c1  mov     [rsp+58h+var_38], ebx
0x1400196c5  jmp     short loc_1400196F5
0x1400196c7  mov     ebx, 0C0000010h
0x1400196cc  jmp     short loc_1400196C1
0x1400196ce  mov     rcx, rdi
0x1400196d1  call    MupSetupUndecoratedFileNameForRelativeOpen
0x1400196d6  mov     ebx, eax
0x1400196d8  mov     [rsp+58h+var_38], eax
0x1400196dc  jmp     loc_14001962F
0x1400196e1  mov     qword ptr [rdi+0A8h], 0
0x1400196ec  lock inc dword ptr [rax+4]
0x1400196f0  jmp     loc_14001965E
0x1400196f5  test    ebx, ebx
0x1400196f7  jnz     short loc_140019711
0x1400196f9  mov     [r14], rdi
0x1400196fc  mov     eax, ebx
0x1400196fe  mov     rbx, [rsp+58h+arg_0]
0x140019703  add     rsp, 30h
0x140019707  pop     r15
0x140019709  pop     r14
0x14001970b  pop     r12
0x14001970d  pop     rdi
0x14001970e  pop     rsi
0x14001970f  retn
0x140019711  test    rdi, rdi
0x140019714  jz      short loc_1400196F9
0x140019716  mov     rcx, rdi; P
0x140019719  call    MupReleaseFileContext
0x14001971e  mov     qword ptr [r14], 0
0x140019725  jmp     short loc_1400196FC
0x14001f4e0  push    rbp
0x14001f4e2  sub     rsp, 20h
0x14001f4e6  mov     rbp, rdx
0x14001f4e9  cmp     dword ptr [rbp+20h], 0
0x14001f4ed  jnz     short loc_14001F4F3
0x14001f4ef  test    cl, cl
0x14001f4f1  jz      short loc_14001F50E
0x14001f4f3  mov     rcx, [rbp+78h]; P
0x14001f4f7  test    rcx, rcx
0x14001f4fa  jz      short loc_14001F50E
0x14001f4fc  call    MupReleaseFileContext
0x14001f501  mov     rax, [rbp+70h]
0x14001f505  mov     qword ptr [rax], 0
0x14001f50c  jmp     short loc_14001F519
0x14001f50e  mov     rcx, [rbp+70h]
0x14001f512  mov     rax, [rbp+78h]
0x14001f516  mov     [rcx], rax
0x14001f519  add     rsp, 20h
0x14001f51d  pop     rbp
0x14001f51e  retn
```
