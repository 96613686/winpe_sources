# FnValidateAndExpandQueuePath(wchar_t const *,wchar_t const * *,wchar_t * *)

- ea: `0x180021e3c`
- end: `0x180021ff6`
- name: `?FnValidateAndExpandQueuePath@@YA?AW4QUEUE_PATH_TYPE@@PEB_WPEAPEB_WPEAPEA_W@Z`
- size: `442`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b760`
- `0x18000e590`
- `0x18000fcf0`

## callees

- `0x180007e10`
- `0x18000a33c`
- `0x180021488`
- `0x180021e3c`
- `0x180022528`
- `0x180022dc8`

## import_xrefs

- `msvcrt!free` at `0x180021e93`
- `msvcrt!free` at `0x180021eb1`
- `msvcrt!free` at `0x180021f50`
- `msvcrt!free` at `0x180021fa3`
- `msvcrt!free` at `0x180021fc8`
- `msvcrt!free` at `0x180021fd5`
- `msvcrt!free` at `0x180021e93`
- `msvcrt!free` at `0x180021eb1`
- `msvcrt!free` at `0x180021f50`
- `msvcrt!free` at `0x180021fa3`
- `msvcrt!free` at `0x180021fc8`
- `msvcrt!free` at `0x180021fd5`
- `msvcrt!iswspace` at `0x180021e6f`
- `msvcrt!iswspace` at `0x180021ea5`
- `msvcrt!iswspace` at `0x180021e6f`
- `msvcrt!iswspace` at `0x180021ea5`
- `msvcrt!wcschr` at `0x180021f91`
- `msvcrt!wcschr` at `0x180021f91`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall FnValidateAndExpandQueuePath(wint_t *a1, _QWORD *a2, _QWORD *a3)
{
  wchar_t *v5; // rbx
  wint_t i; // ax
  unsigned int v7; // eax
  wchar_t *v8; // rdi

  v5 = a1;
  *a3 = 0;
  for ( i = *a1; i && iswspace(i); i = *v5 )
    ++v5;
  v7 = mqwcslen(v5);
  if ( v7 )
  {
    if ( !iswspace(v5[v7 - 1]) )
    {
      v8 = (wchar_t *)ParseMachineNameString(v5);
      if ( !*(_WORD *)ParseQueueNameString(v8) )
      {
        *a2 = ExpandPathName(v5);
        if ( !*a3 )
          *a3 = 0;
      }
    }
  }
  free(0);
  return 0;
}

```

## disassembly

```asm
0x180021e3c  mov     [rsp+arg_8], rbx
0x180021e41  mov     [rsp+arg_18], rsi
0x180021e46  push    rdi
0x180021e47  push    r12
0x180021e49  push    r13
0x180021e4b  push    r14
0x180021e4d  push    r15
0x180021e4f  sub     rsp, 20h
0x180021e53  mov     r14, r8
0x180021e56  mov     r15, rdx
0x180021e59  mov     rbx, rcx
0x180021e5c  xor     r12d, r12d
0x180021e5f  mov     [rsp+48h+arg_10], r12
0x180021e64  mov     [r8], r12
0x180021e67  movzx   eax, word ptr [rcx]
0x180021e6a  jmp     short loc_180021E80
0x180021e6c  movzx   ecx, ax; C
0x180021e6f  call    cs:__imp_iswspace
0x180021e75  test    eax, eax
0x180021e77  jz      short loc_180021E85
0x180021e79  add     rbx, 2
0x180021e7d  movzx   eax, word ptr [rbx]
0x180021e80  test    ax, ax
0x180021e83  jnz     short loc_180021E6C
0x180021e85  mov     rcx, rbx; wchar_t *
0x180021e88  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180021e8d  test    eax, eax
0x180021e8f  jnz     short loc_180021E9F
0x180021e91  xor     ecx, ecx; Block
0x180021e93  call    cs:__imp_free
0x180021e99  nop
0x180021e9a  jmp     loc_180021FDC
0x180021e9f  dec     eax
0x180021ea1  movzx   ecx, word ptr [rbx+rax*2]; C
0x180021ea5  call    cs:__imp_iswspace
0x180021eab  test    eax, eax
0x180021ead  jz      short loc_180021EBD
0x180021eaf  xor     ecx, ecx; Block
0x180021eb1  call    cs:__imp_free
0x180021eb7  nop
0x180021eb8  jmp     loc_180021FDC
0x180021ebd  mov     [rsp+48h+arg_0], r12d
0x180021ec2  mov     rcx, rbx; wchar_t *
0x180021ec5  call    ParseMachineNameString
0x180021eca  mov     rdi, rax
0x180021ecd  lea     rdx, [rsp+48h+arg_0]
0x180021ed2  mov     rcx, rax; wchar_t *
0x180021ed5  call    ParseQueueNameString
0x180021eda  mov     rdx, rax
0x180021edd  mov     esi, [rsp+48h+arg_0]
0x180021ee1  cmp     esi, 2
0x180021ee4  jnz     short loc_180021F5E
0x180021ee6  test    rdi, rdi
0x180021ee9  jz      short loc_180021F5E
0x180021eeb  test    rax, rax
0x180021eee  jz      short loc_180021F5E
0x180021ef0  mov     r8d, r12d
0x180021ef3  mov     rcx, rax
0x180021ef6  sub     rcx, rdi
0x180021ef9  lea     eax, [r8+1]
0x180021efd  cmp     word ptr [rdi], 2Fh ; '/'
0x180021f01  cmovnz  eax, r8d
0x180021f05  mov     r8d, eax
0x180021f08  add     rdi, 2
0x180021f0c  cmp     rdi, rdx
0x180021f0f  jb      short loc_180021EF9
0x180021f11  test    eax, eax
0x180021f13  jz      short loc_180021F5E
0x180021f15  sar     rcx, 1
0x180021f18  add     ecx, eax
0x180021f1a  cmp     ecx, 3Fh ; '?'
0x180021f1d  jbe     short loc_180021F5E
0x180021f1f  lea     rax, WPP_GLOBAL_Control
0x180021f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f2d  cmp     rcx, rax
0x180021f30  jz      short loc_180021F4E
0x180021f32  test    byte ptr [rcx+1Ch], 1
0x180021f36  jz      short loc_180021F4E
0x180021f38  mov     edx, 29h ; ')'
0x180021f3d  lea     r8, WPP_46d7352ff4ed31571a117a62feb2004e_Traceguids
0x180021f44  mov     rcx, [rcx+10h]
0x180021f48  call    WPP_SF_
0x180021f4d  nop
0x180021f4e  xor     ecx, ecx; Block
0x180021f50  call    cs:__imp_free
0x180021f56  nop
0x180021f57  xor     eax, eax
0x180021f59  jmp     loc_180021FDE
0x180021f5e  cmp     [rdx], r12w
0x180021f62  jz      short loc_180021FAE
0x180021f64  mov     r13d, 3Bh ; ';'
0x180021f6a  cmp     [rdx], r13w
0x180021f6e  jnz     short loc_180021FA1
0x180021f70  lea     eax, [rsi-1]
0x180021f73  cmp     eax, 1
0x180021f76  ja      short loc_180021FA1
0x180021f78  lea     rdi, [rdx+2]
0x180021f7c  mov     rcx, rdi; wchar_t *
0x180021f7f  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180021f84  dec     eax
0x180021f86  cmp     eax, 1Eh
0x180021f89  ja      short loc_180021FA1
0x180021f8b  mov     edx, r13d; Ch
0x180021f8e  mov     rcx, rdi; Str
0x180021f91  call    cs:__imp_wcschr
0x180021f97  test    rax, rax
0x180021f9a  jnz     short loc_180021FA1
0x180021f9c  lea     esi, [rax+4]
0x180021f9f  jmp     short loc_180021FAE
0x180021fa1  xor     ecx, ecx; Block
0x180021fa3  call    cs:__imp_free
0x180021fa9  nop
0x180021faa  xor     eax, eax
0x180021fac  jmp     short loc_180021FDE
0x180021fae  mov     r8, r14
0x180021fb1  xor     edx, edx
0x180021fb3  mov     rcx, rbx; wchar_t *
0x180021fb6  call    ExpandPathName
0x180021fbb  mov     [r15], rax
0x180021fbe  cmp     [r14], r12
0x180021fc1  jnz     short loc_180021FC6
0x180021fc3  mov     [r14], r12
0x180021fc6  xor     ecx, ecx; Block
0x180021fc8  call    cs:__imp_free
0x180021fce  nop
0x180021fcf  mov     eax, esi
0x180021fd1  jmp     short loc_180021FDE
0x180021fd3  xor     ecx, ecx; Block
0x180021fd5  call    cs:__imp_free
0x180021fdb  nop
0x180021fdc  xor     eax, eax
0x180021fde  mov     rbx, [rsp+48h+arg_8]
0x180021fe3  mov     rsi, [rsp+48h+arg_18]
0x180021fe8  add     rsp, 20h
0x180021fec  pop     r15
0x180021fee  pop     r14
0x180021ff0  pop     r13
0x180021ff2  pop     r12
0x180021ff4  pop     rdi
0x180021ff5  retn
```
