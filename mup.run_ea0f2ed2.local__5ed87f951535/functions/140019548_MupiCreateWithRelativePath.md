# MupiCreateWithRelativePath

- ea: `0x140019548`
- end: `0x1400196d7`
- name: `MupiCreateWithRelativePath`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14001a370`

## callees

- `0x140001c10`
- `0x14000ff6c`
- `0x140017f00`
- `0x140019330`
- `0x140019548`
- `0x14001ca00`
- `0x14001cac0`
- `0x14001cb80`
- `0x14001ddf8`

## pseudocode

```c
__int64 __fastcall MupiCreateWithRelativePath(__int64 a1, char a2, _QWORD *a3)
{
  __int64 FileContext; // rsi
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx

  *a3 = 0;
  if ( *(_WORD *)(a1 + 88) >= 2u && **(_WORD **)(a1 + 96) == 92 )
  {
    v8 = -1073741811;
  }
  else
  {
    FileContext = MupFindFileContext(*(_QWORD *)(a1 + 64));
    if ( FileContext )
    {
      v8 = MupAllocFileContextForRelativeOpen((PCUNICODE_STRING)(a1 + 88));
      if ( !v8 )
      {
        MEMORY[0x90] = a1;
        MEMORY[0x98] = FileContext;
        if ( *(_QWORD *)(FileContext + 88) )
          v8 = MupSetupUndecoratedFileNameForRelativeOpen(0);
        if ( !v8 )
        {
          v9 = *(_QWORD *)(FileContext + 184);
          if ( v9 )
          {
            MEMORY[0xA8] = 0;
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 4));
          }
          else
          {
            v10 = *(_QWORD *)(FileContext + 168);
            if ( v10 )
              _InterlockedIncrement((volatile signed __int32 *)(v10 + 4));
            MEMORY[0xA8] = v10;
          }
          MEMORY[0xA0] = *(_DWORD *)(FileContext + 160);
          MEMORY[0xB8] = *(_QWORD *)(FileContext + 184);
          LOBYTE(v7) = 1;
          MupSaveProviderStrippedFileName(0, v7);
          LOBYTE(v11) = 1;
          MupSaveStrippedFileName(0, v11);
          v8 = MupInitializeUncHardeningFileContext(128, 248);
          if ( v8 >= 0 )
          {
            LOBYTE(v12) = a2;
            v8 = MupSetupRelatedSurrogateFileContextList(0, v12);
          }
        }
      }
    }
    else
    {
      v8 = -1073741808;
    }
  }
  *a3 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140019548  mov     rax, rsp
0x14001954b  mov     [rax+8], rbx
0x14001954f  mov     [rax+18h], r8
0x140019553  push    rsi
0x140019554  push    rdi
0x140019555  push    r12
0x140019557  push    r14
0x140019559  push    r15
0x14001955b  sub     rsp, 30h
0x14001955f  mov     r14, r8
0x140019562  mov     r12b, dl
0x140019565  mov     r15, rcx
0x140019568  mov     dword ptr [rax-38h], 0
0x14001956f  xor     edi, edi
0x140019571  mov     [rax+20h], rdi
0x140019575  mov     [r8], rdi
0x140019578  cmp     word ptr [rcx+58h], 2
0x14001957d  jb      short loc_14001958D
0x14001957f  mov     rax, [rcx+60h]
0x140019583  cmp     word ptr [rax], 5Ch ; '\'
0x140019587  jz      loc_14001966C
0x14001958d  mov     rcx, [rcx+40h]
0x140019591  call    MupFindFileContext
0x140019596  mov     rsi, rax
0x140019599  test    rax, rax
0x14001959c  jz      loc_140019677
0x1400195a2  lea     r8, [rsp+58h+P]
0x1400195a7  mov     rdx, rax
0x1400195aa  lea     rcx, [r15+58h]; Source
0x1400195ae  call    MupAllocFileContextForRelativeOpen
0x1400195b3  mov     ebx, eax
0x1400195b5  mov     [rsp+58h+var_38], eax
0x1400195b9  mov     rdi, [rsp+58h+P]
0x1400195be  test    eax, eax
0x1400195c0  jnz     loc_1400196A5
0x1400195c6  mov     [rdi+90h], r15
0x1400195cd  mov     [rdi+98h], rsi
0x1400195d4  cmp     qword ptr [rsi+58h], 0
0x1400195d9  jnz     loc_14001967E
0x1400195df  test    ebx, ebx
0x1400195e1  jnz     loc_1400196A5
0x1400195e7  mov     rax, [rsi+0B8h]
0x1400195ee  test    rax, rax
0x1400195f1  jnz     loc_140019691
0x1400195f7  mov     rax, [rsi+0A8h]
0x1400195fe  test    rax, rax
0x140019601  jz      short loc_140019607
0x140019603  lock inc dword ptr [rax+4]
0x140019607  mov     [rdi+0A8h], rax
0x14001960e  mov     eax, [rsi+0A0h]
0x140019614  mov     [rdi+0A0h], eax
0x14001961a  mov     rax, [rsi+0B8h]
0x140019621  mov     [rdi+0B8h], rax
0x140019628  mov     dl, 1
0x14001962a  mov     rcx, rdi
0x14001962d  call    MupSaveProviderStrippedFileName
0x140019632  mov     dl, 1
0x140019634  mov     rcx, rdi
0x140019637  call    MupSaveStrippedFileName
0x14001963c  lea     rdx, [rdi+0F8h]
0x140019643  lea     rcx, [rdi+80h]
0x14001964a  call    MupInitializeUncHardeningFileContext
0x14001964f  mov     ebx, eax
0x140019651  mov     [rsp+58h+var_38], eax
0x140019655  test    eax, eax
0x140019657  js      short loc_1400196A5
0x140019659  mov     dl, r12b
0x14001965c  mov     rcx, rdi
0x14001965f  call    MupSetupRelatedSurrogateFileContextList
0x140019664  mov     ebx, eax
0x140019666  mov     [rsp+58h+var_38], eax
0x14001966a  jmp     short loc_1400196A5
0x14001966c  mov     ebx, 0C000000Dh
0x140019671  mov     [rsp+58h+var_38], ebx
0x140019675  jmp     short loc_1400196A5
0x140019677  mov     ebx, 0C0000010h
0x14001967c  jmp     short loc_140019671
0x14001967e  mov     rcx, rdi
0x140019681  call    MupSetupUndecoratedFileNameForRelativeOpen
0x140019686  mov     ebx, eax
0x140019688  mov     [rsp+58h+var_38], eax
0x14001968c  jmp     loc_1400195DF
0x140019691  mov     qword ptr [rdi+0A8h], 0
0x14001969c  lock inc dword ptr [rax+4]
0x1400196a0  jmp     loc_14001960E
0x1400196a5  test    ebx, ebx
0x1400196a7  jnz     short loc_1400196C1
0x1400196a9  mov     [r14], rdi
0x1400196ac  mov     eax, ebx
0x1400196ae  mov     rbx, [rsp+58h+arg_0]
0x1400196b3  add     rsp, 30h
0x1400196b7  pop     r15
0x1400196b9  pop     r14
0x1400196bb  pop     r12
0x1400196bd  pop     rdi
0x1400196be  pop     rsi
0x1400196bf  retn
0x1400196c1  test    rdi, rdi
0x1400196c4  jz      short loc_1400196A9
0x1400196c6  mov     rcx, rdi; P
0x1400196c9  call    MupReleaseFileContext
0x1400196ce  mov     qword ptr [r14], 0
0x1400196d5  jmp     short loc_1400196AC
0x14001f490  push    rbp
0x14001f492  sub     rsp, 20h
0x14001f496  mov     rbp, rdx
0x14001f499  cmp     dword ptr [rbp+20h], 0
0x14001f49d  jnz     short loc_14001F4A3
0x14001f49f  test    cl, cl
0x14001f4a1  jz      short loc_14001F4BE
0x14001f4a3  mov     rcx, [rbp+78h]; P
0x14001f4a7  test    rcx, rcx
0x14001f4aa  jz      short loc_14001F4BE
0x14001f4ac  call    MupReleaseFileContext
0x14001f4b1  mov     rax, [rbp+70h]
0x14001f4b5  mov     qword ptr [rax], 0
0x14001f4bc  jmp     short loc_14001F4C9
0x14001f4be  mov     rcx, [rbp+70h]
0x14001f4c2  mov     rax, [rbp+78h]
0x14001f4c6  mov     [rcx], rax
0x14001f4c9  add     rsp, 20h
0x14001f4cd  pop     rbp
0x14001f4ce  retn
```
