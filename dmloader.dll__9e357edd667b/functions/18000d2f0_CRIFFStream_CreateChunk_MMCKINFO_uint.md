# CRIFFStream::CreateChunk(_MMCKINFO *,uint)

- ea: `0x18000d2f0`
- end: `0x18000d3b1`
- name: `?CreateChunk@CRIFFStream@@UEAAJPEAU_MMCKINFO@@I@Z`
- size: `193`
- prototype: `__int64 __fastcall(CRIFFStream *__hidden this, struct _MMCKINFO *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d2f0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CRIFFStream::CreateChunk(CRIFFStream *this, struct _MMCKINFO *a2, char a3)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 2) + 40LL))(
         *((_QWORD *)this + 2),
         0,
         1,
         &v10) < 0 )
    return 2289570069LL;
  a2->dwDataOffset = v10 + 8;
  if ( (a3 & 0x20) != 0 )
  {
    a2->ckid = 1179011410;
  }
  else
  {
    if ( (a3 & 0x40) == 0 )
    {
      v7 = 8;
      goto LABEL_9;
    }
    a2->ckid = 1414744396;
  }
  v7 = 12;
LABEL_9:
  v8 = *((_QWORD *)this + 2);
  v9 = 0;
  if ( (*(int (__fastcall **)(__int64, struct _MMCKINFO *, _QWORD, int *))(*(_QWORD *)v8 + 32LL))(v8, a2, v7, &v9) < 0
    || v9 != v7 )
  {
    return 2289570070LL;
  }
  a2->dwFlags = 0x10000000;
  return 0;
}

```

## disassembly

```asm
0x18000d2f0  mov     r11, rsp
0x18000d2f3  mov     [r11+10h], rbx
0x18000d2f7  mov     [r11+18h], rsi
0x18000d2fb  push    rdi
0x18000d2fc  sub     rsp, 30h
0x18000d300  mov     rsi, rcx
0x18000d303  mov     qword ptr [r11+20h], 0
0x18000d30b  mov     rcx, [rcx+10h]
0x18000d30f  lea     r9, [r11+20h]
0x18000d313  mov     rdi, rdx
0x18000d316  mov     ebx, r8d
0x18000d319  xor     edx, edx
0x18000d31b  mov     rax, [rcx]
0x18000d31e  lea     r8d, [rdx+1]
0x18000d322  mov     rax, [rax+28h]
0x18000d326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d32b  test    eax, eax
0x18000d32d  jns     short loc_18000D336
0x18000d32f  mov     eax, 88781115h
0x18000d334  jmp     short loc_18000D3A1
0x18000d336  mov     eax, dword ptr [rsp+38h+arg_18]
0x18000d33a  add     eax, 8
0x18000d33d  mov     [rdi+0Ch], eax
0x18000d340  test    bl, 20h
0x18000d343  jz      short loc_18000D34D
0x18000d345  mov     dword ptr [rdi], 46464952h
0x18000d34b  jmp     short loc_18000D358
0x18000d34d  test    bl, 40h
0x18000d350  jz      short loc_18000D35F
0x18000d352  mov     dword ptr [rdi], 5453494Ch
0x18000d358  mov     ebx, 0Ch
0x18000d35d  jmp     short loc_18000D364
0x18000d35f  mov     ebx, 8
0x18000d364  mov     rcx, [rsi+10h]
0x18000d368  lea     r9, [rsp+38h+arg_0]
0x18000d36d  mov     [rsp+38h+arg_0], 0
0x18000d375  mov     r8d, ebx
0x18000d378  mov     rdx, rdi
0x18000d37b  mov     rax, [rcx]
0x18000d37e  mov     rax, [rax+20h]
0x18000d382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d387  test    eax, eax
0x18000d389  js      short loc_18000D39C
0x18000d38b  cmp     [rsp+38h+arg_0], ebx
0x18000d38f  jnz     short loc_18000D39C
0x18000d391  mov     dword ptr [rdi+10h], 10000000h
0x18000d398  xor     eax, eax
0x18000d39a  jmp     short loc_18000D3A1
0x18000d39c  mov     eax, 88781116h
0x18000d3a1  mov     rbx, [rsp+38h+arg_8]
0x18000d3a6  mov     rsi, [rsp+38h+arg_10]
0x18000d3ab  add     rsp, 30h
0x18000d3af  pop     rdi
0x18000d3b0  retn
```
