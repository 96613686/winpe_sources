# DestroyCompletionEntry

- ea: `0x18002f268`
- end: `0x18002f303`
- name: `DestroyCompletionEntry`
- size: `155`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019b6c`
- `0x18002f160`

## callees

- `0x1800057f0`
- `0x18002f268`
- `0x18004d1a0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2c2`

## pseudocode

```c
__int64 __fastcall DestroyCompletionEntry(__int64 *a1)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  void *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( (xmmword_1800616A0 & 0x10) != 0 )
    result = WPP_SF_q(1028, 54, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, a1);
  if ( a1 && (v6 = *a1, v4 = v6, *a1 = 0, v4) )
  {
    v5 = *(void **)(v4 + 16);
    v3 = 0;
    if ( v5 )
    {
      CloseHandle(v5);
      *(_QWORD *)(v4 + 16) = 0;
    }
    result = DhcpPunycodeFree(&v6);
  }
  else
  {
    v3 = 87;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    return WPP_SF_D(1028, 55, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v3);
  return result;
}

```

## disassembly

```asm
0x18002f268  mov     [rsp+arg_8], rbx
0x18002f26d  push    rdi
0x18002f26e  sub     rsp, 20h
0x18002f272  mov     rbx, rcx
0x18002f275  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002f27c  jz      short loc_18002F297
0x18002f27e  mov     edx, 36h ; '6'
0x18002f283  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002f28a  mov     ecx, 404h
0x18002f28f  mov     r9, rbx
0x18002f292  call    WPP_SF_q
0x18002f297  test    rbx, rbx
0x18002f29a  jnz     short loc_18002F2A3
0x18002f29c  mov     ebx, 57h ; 'W'
0x18002f2a1  jmp     short loc_18002F2D6
0x18002f2a3  mov     rdi, [rbx]
0x18002f2a6  mov     [rsp+28h+arg_0], rdi
0x18002f2ab  mov     qword ptr [rbx], 0
0x18002f2b2  test    rdi, rdi
0x18002f2b5  jz      short loc_18002F29C
0x18002f2b7  mov     rcx, [rdi+10h]; hObject
0x18002f2bb  xor     ebx, ebx
0x18002f2bd  test    rcx, rcx
0x18002f2c0  jz      short loc_18002F2CC
0x18002f2c2  call    cs:__imp_CloseHandle
0x18002f2c8  mov     [rdi+10h], rbx
0x18002f2cc  lea     rcx, [rsp+28h+arg_0]
0x18002f2d1  call    DhcpPunycodeFree
0x18002f2d6  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002f2dd  jz      short loc_18002F2F8
0x18002f2df  mov     edx, 37h ; '7'
0x18002f2e4  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002f2eb  mov     ecx, 404h
0x18002f2f0  mov     r9d, ebx
0x18002f2f3  call    WPP_SF_D
0x18002f2f8  mov     rbx, [rsp+28h+arg_8]
0x18002f2fd  add     rsp, 20h
0x18002f301  pop     rdi
0x18002f302  retn
```
