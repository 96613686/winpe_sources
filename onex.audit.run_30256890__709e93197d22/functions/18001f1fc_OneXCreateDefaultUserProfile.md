# OneXCreateDefaultUserProfile

- ea: `0x18001f1fc`
- end: `0x18001f326`
- name: `OneXCreateDefaultUserProfile`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800091c4`
- `0x180017540`

## callees

- `0x180014870`
- `0x180014e20`
- `0x18001f1fc`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18001f22e`
- `MobileNetworking!AllocateMemory` at `0x18001f22e`
- `MobileNetworking!FreeMemory` at `0x18001f30e`
- `MobileNetworking!FreeMemory` at `0x18001f30e`

## string_xrefs

- `0x18001f21f`: `OneXCreateDefaultUserProfile`
- `0x18001f303`: `OneXCreateDefaultUserProfile`

## pseudocode

```c
__int64 __fastcall OneXCreateDefaultUserProfile(_QWORD *a1)
{
  unsigned int AlignedSize; // ebx
  int v3; // ecx
  __int64 v4; // rcx
  _DWORD *v5; // r9
  __int64 v6; // r10
  char *v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r10
  unsigned int v10; // r11d
  _DWORD *v12; // [rsp+38h] [rbp+18h] BYREF

  v12 = 0;
  AlignedSize = AllocateMemory(64, &v12, "OneXCreateDefaultUserProfile", 48);
  if ( AlignedSize )
    goto LABEL_8;
  *v12 = 2;
  v12[1] = 64;
  AlignedSize = GetAlignedSize(28, v12 + 4);
  if ( AlignedSize )
    goto LABEL_8;
  AlignedSize = GetAlignedSize((unsigned int)(v3 + 4), v12 + 3);
  if ( AlignedSize )
    goto LABEL_8;
  v5 = v12;
  v6 = (unsigned int)v12[4];
  v7 = (char *)v12 + v6 + 28;
  *(_DWORD *)((char *)v12 + v6) &= ~1u;
  *(_DWORD *)((char *)v5 + v6 + 20) = 0;
  AlignedSize = GetAlignedSize(v4, v7);
  if ( AlignedSize
    || (*(_DWORD *)(v9 + v8 + 24) = 0, *(_OWORD *)(v9 + v8 + 4) = 0, (AlignedSize = GetAlignedSize(28, v12 + 6)) != 0)
    || (AlignedSize = IncrementDwordByAlignedSize(v10)) != 0 )
  {
LABEL_8:
    FreeMemory(&v12, "OneXCreateDefaultUserProfile", 77);
  }
  else
  {
    v12[5] = 0;
    v12[2] &= ~1u;
    *a1 = v12;
  }
  return AlignedSize;
}

```

## disassembly

```asm
0x18001f1fc  mov     [rsp-8+arg_0], rbx
0x18001f201  mov     [rsp-8+arg_10], rdi
0x18001f206  push    rbp
0x18001f207  mov     rbp, rsp
0x18001f20a  sub     rsp, 20h
0x18001f20e  mov     rdi, rcx
0x18001f211  mov     [rbp+arg_8], 0
0x18001f219  mov     r9d, 30h ; '0'
0x18001f21f  lea     r8, aOnexcreatedefa_2; "OneXCreateDefaultUserProfile"
0x18001f226  lea     rdx, [rbp+arg_8]
0x18001f22a  lea     ecx, [r9+10h]
0x18001f22e  call    cs:__imp_AllocateMemory
0x18001f234  mov     ebx, eax
0x18001f236  test    eax, eax
0x18001f238  jnz     loc_18001F2FD
0x18001f23e  mov     rax, [rbp+arg_8]
0x18001f242  lea     ecx, [rbx+1Ch]
0x18001f245  mov     dword ptr [rax], 2
0x18001f24b  mov     rax, [rbp+arg_8]
0x18001f24f  mov     dword ptr [rax+4], 40h ; '@'
0x18001f256  mov     rdx, [rbp+arg_8]
0x18001f25a  add     rdx, 10h
0x18001f25e  call    GetAlignedSize
0x18001f263  mov     ebx, eax
0x18001f265  test    eax, eax
0x18001f267  jnz     loc_18001F2FD
0x18001f26d  mov     rdx, [rbp+arg_8]
0x18001f271  lea     r11d, [rcx+4]
0x18001f275  add     rdx, 0Ch
0x18001f279  mov     ecx, r11d
0x18001f27c  call    GetAlignedSize
0x18001f281  mov     ebx, eax
0x18001f283  test    eax, eax
0x18001f285  jnz     short loc_18001F2FD
0x18001f287  mov     r9, [rbp+arg_8]
0x18001f28b  mov     r10d, [r9+10h]
0x18001f28f  lea     rdx, [r9+1Ch]
0x18001f293  add     rdx, r10
0x18001f296  and     dword ptr [r10+r9], 0FFFFFFFEh
0x18001f29b  mov     [r10+r9+14h], eax
0x18001f2a0  call    GetAlignedSize
0x18001f2a5  mov     ebx, eax
0x18001f2a7  test    eax, eax
0x18001f2a9  jnz     short loc_18001F2FD
0x18001f2ab  mov     [r10+r9+18h], eax
0x18001f2b0  lea     ecx, [rax+1Ch]
0x18001f2b3  xorps   xmm0, xmm0
0x18001f2b6  movups  xmmword ptr [r10+r9+4], xmm0
0x18001f2bc  mov     rdx, [rbp+arg_8]
0x18001f2c0  add     rdx, 18h
0x18001f2c4  call    GetAlignedSize
0x18001f2c9  mov     ebx, eax
0x18001f2cb  test    eax, eax
0x18001f2cd  jnz     short loc_18001F2FD
0x18001f2cf  mov     rdx, [rbp+arg_8]
0x18001f2d3  mov     ecx, r11d
0x18001f2d6  add     rdx, 18h
0x18001f2da  call    IncrementDwordByAlignedSize
0x18001f2df  mov     ebx, eax
0x18001f2e1  test    eax, eax
0x18001f2e3  jnz     short loc_18001F2FD
0x18001f2e5  mov     rax, [rbp+arg_8]
0x18001f2e9  mov     [rax+14h], ebx
0x18001f2ec  mov     rax, [rbp+arg_8]
0x18001f2f0  and     dword ptr [rax+8], 0FFFFFFFEh
0x18001f2f4  mov     rax, [rbp+arg_8]
0x18001f2f8  mov     [rdi], rax
0x18001f2fb  jmp     short loc_18001F314
0x18001f2fd  mov     r8d, 4Dh ; 'M'
0x18001f303  lea     rdx, aOnexcreatedefa_2; "OneXCreateDefaultUserProfile"
0x18001f30a  lea     rcx, [rbp+arg_8]
0x18001f30e  call    cs:__imp_FreeMemory
0x18001f314  mov     rdi, [rsp+20h+arg_10]
0x18001f319  mov     eax, ebx
0x18001f31b  mov     rbx, [rsp+20h+arg_0]
0x18001f320  add     rsp, 20h
0x18001f324  pop     rbp
0x18001f325  retn
```
