# LogConfig

- ea: `0x140002c48`
- end: `0x140002cf8`
- name: `LogConfig`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140002670`
- `0x14000b1c0`

## callees

- `0x140002c48`
- `0x140002d54`
- `0x140002e04`

## pseudocode

```c
__int64 __fastcall LogConfig(__int64 a1, __int64 a2, __int64 a3)
{
  int i; // ebx
  int v4; // edi
  __int64 v5; // r9
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1);
  for ( i = 0; i < 3; ++i )
  {
    v4 = 0;
    do
    {
      v5 = dword_140006064[4 * v4];
      if ( (int)v5 >= 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_dSD(
          WPP_GLOBAL_Control->AttachedDevice,
          v5 + (i << 6),
          2 * v4,
          i,
          (__int64)(&off_140006068)[2 * v4],
          *(int *)((char *)&g_config[16 * (unsigned __int64)(unsigned int)i] + v5));
      }
      result = 2LL * ++v4;
    }
    while ( ConfigSetting[4 * v4] );
  }
  return result;
}

```

## disassembly

```asm
0x140002c48  push    rbx
0x140002c4a  push    rbp
0x140002c4b  push    rsi
0x140002c4c  push    rdi
0x140002c4d  sub     rsp, 38h
0x140002c51  mov     r9, rcx
0x140002c54  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c5b  lea     rbp, WPP_GLOBAL_Control
0x140002c62  cmp     rcx, rbp
0x140002c65  jz      short loc_140002C77
0x140002c67  mov     eax, [rcx+2Ch]
0x140002c6a  test    al, 1
0x140002c6c  jz      short loc_140002C77
0x140002c6e  mov     rcx, [rcx+18h]
0x140002c72  call    WPP_SF_s
0x140002c77  xor     ebx, ebx
0x140002c79  lea     rsi, cs:140000000h
0x140002c80  xor     edi, edi
0x140002c82  movsxd  r8, edi
0x140002c85  add     r8, r8
0x140002c88  movsxd  r9, ds:rva dword_140006064[rsi+r8*8]
0x140002c90  test    r9d, r9d
0x140002c93  js      short loc_140002CD5
0x140002c95  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c9c  cmp     rcx, rbp
0x140002c9f  jz      short loc_140002CD5
0x140002ca1  mov     eax, [rcx+2Ch]
0x140002ca4  test    al, 1
0x140002ca6  jz      short loc_140002CD5
0x140002ca8  mov     rcx, [rcx+18h]
0x140002cac  mov     edx, ebx
0x140002cae  shl     rdx, 6
0x140002cb2  add     rdx, r9
0x140002cb5  mov     r9d, ebx
0x140002cb8  mov     eax, [rdx+rsi+77E0h]
0x140002cbf  mov     [rsp+58h+var_30], eax
0x140002cc3  mov     rax, ds:rva off_140006068[rsi+r8*8]; "nHwThreads" ...
0x140002ccb  mov     [rsp+58h+var_38], rax
0x140002cd0  call    WPP_SF_dSD
0x140002cd5  inc     edi
0x140002cd7  movsxd  rax, edi
0x140002cda  add     rax, rax
0x140002cdd  cmp     ds:rva ConfigSetting[rsi+rax*8], 0
0x140002ce5  jnz     short loc_140002C82
0x140002ce7  inc     ebx
0x140002ce9  cmp     ebx, 3
0x140002cec  jl      short loc_140002C80
0x140002cee  add     rsp, 38h
0x140002cf2  pop     rdi
0x140002cf3  pop     rsi
0x140002cf4  pop     rbp
0x140002cf5  pop     rbx
0x140002cf6  retn
```
