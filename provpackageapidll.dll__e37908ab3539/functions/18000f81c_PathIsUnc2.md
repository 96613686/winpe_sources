# PathIsUnc2

- ea: `0x18000f81c`
- end: `0x18000f8ad`
- name: `PathIsUnc2`
- size: `145`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *, unsigned __int8 (__fastcall *)(_QWORD))`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f040`
- `0x18000f6b0`
- `0x18000fc10`
- `0x18000ff24`

## callees

- `0x18000f81c`
- `0x18000f8b4`
- `0x18000f960`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall PathIsUnc2(unsigned __int16 *a1, _QWORD *a2, unsigned __int8 (__fastcall *a3)(_QWORD))
{
  unsigned int v3; // ebx
  unsigned __int8 v7; // al
  __int64 v8; // rax

  v3 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3(*a1) && a3(a1[1]) )
  {
    if ( a1[2] == 63 )
    {
      if ( !StrIsEqualCaseInsensitive(a1 + 3, L"\\UNC\\", 5) )
        return v3;
      v8 = 8;
      v3 = 1;
    }
    else
    {
      v7 = PathIsVolumeGUIDWorker(a1) ^ 1;
      v3 = v7;
      if ( !v7 )
        return v3;
      v8 = 2LL * v7;
    }
    if ( a2 )
      *a2 = &a1[v8];
  }
  return v3;
}

```

## disassembly

```asm
0x18000f81c  push    rbx
0x18000f81e  push    rbp
0x18000f81f  push    rsi
0x18000f820  push    rdi
0x18000f821  sub     rsp, 28h
0x18000f825  xor     ebx, ebx
0x18000f827  mov     rbp, r8
0x18000f82a  mov     rsi, rdx
0x18000f82d  mov     rdi, rcx
0x18000f830  test    rdx, rdx
0x18000f833  jz      short loc_18000F838
0x18000f835  mov     [rdx], rbx
0x18000f838  movzx   ecx, word ptr [rcx]
0x18000f83b  mov     rax, rbp
0x18000f83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f843  test    al, al
0x18000f845  jz      short loc_18000F8A2
0x18000f847  movzx   ecx, word ptr [rdi+2]
0x18000f84b  mov     rax, rbp
0x18000f84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f853  test    al, al
0x18000f855  jz      short loc_18000F8A2
0x18000f857  cmp     word ptr [rdi+4], 3Fh ; '?'
0x18000f85c  jz      short loc_18000F874
0x18000f85e  mov     rcx, rdi; unsigned __int16 *
0x18000f861  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18000f866  xor     al, 1
0x18000f868  movzx   ebx, al
0x18000f86b  jz      short loc_18000F8A2
0x18000f86d  mov     eax, ebx
0x18000f86f  add     rax, rax
0x18000f872  jmp     short loc_18000F896
0x18000f874  lea     rcx, [rdi+6]; unsigned __int16 *
0x18000f878  mov     r8d, 5; int
0x18000f87e  lea     rdx, aUnc_0; "\\UNC\\"
0x18000f885  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18000f88a  test    al, al
0x18000f88c  jz      short loc_18000F8A2
0x18000f88e  mov     eax, 8
0x18000f893  lea     ebx, [rax-7]
0x18000f896  test    rsi, rsi
0x18000f899  jz      short loc_18000F8A2
0x18000f89b  lea     rcx, [rdi+rax*2]
0x18000f89f  mov     [rsi], rcx
0x18000f8a2  mov     eax, ebx
0x18000f8a4  add     rsp, 28h
0x18000f8a8  pop     rdi
0x18000f8a9  pop     rsi
0x18000f8aa  pop     rbp
0x18000f8ab  pop     rbx
0x18000f8ac  retn
```
