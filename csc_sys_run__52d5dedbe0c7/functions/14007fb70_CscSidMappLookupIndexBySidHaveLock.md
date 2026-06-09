# CscSidMappLookupIndexBySidHaveLock

- ea: `0x14007fb70`
- end: `0x14007fc32`
- name: `CscSidMappLookupIndexBySidHaveLock`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140012614`
- `0x14005c6c0`
- `0x1400720fc`
- `0x140080c40`

## callees

- `0x1400190ec`
- `0x14007fb70`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14007fbb8`
- `ntoskrnl!RtlEqualSid` at `0x14007fbb8`

## pseudocode

```c
__int64 __fastcall CscSidMappLookupIndexBySidHaveLock(__int64 a1, void *a2)
{
  unsigned __int16 v2; // si
  int v5; // r14d
  unsigned int i; // ebx
  __int64 v7; // rax

  v2 = 0;
  if ( *(_QWORD *)(a1 + 56) )
  {
    v5 = 0;
    for ( i = 0; ; ++i )
    {
      v7 = *(_QWORD *)(a1 + 56);
      if ( i >= *(_DWORD *)(v7 + 4) )
        break;
      if ( RtlEqualSid(a2, *(PSID *)(v7 + 16 * (i + 1LL))) )
      {
        v2 = i + 1;
        break;
      }
    }
  }
  else
  {
    v5 = 971;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, v2, v5);
  return v2;
}

```

## disassembly

```asm
0x14007fb70  mov     [rsp+arg_18], rsi
0x14007fb75  push    r14
0x14007fb77  sub     rsp, 30h
0x14007fb7b  mov     [rsp+38h+arg_8], rbp
0x14007fb80  xor     esi, esi
0x14007fb82  mov     rbp, rdx
0x14007fb85  mov     [rsp+38h+arg_10], rdi
0x14007fb8a  mov     rdi, rcx
0x14007fb8d  cmp     [rcx+38h], rsi
0x14007fb91  jz      short loc_14007FC0A
0x14007fb93  xor     r14d, r14d
0x14007fb96  mov     [rsp+38h+arg_0], rbx
0x14007fb9b  xor     ebx, ebx
0x14007fb9d  nop     dword ptr [rax]
0x14007fba0  mov     rax, [rdi+38h]
0x14007fba4  cmp     ebx, [rax+4]
0x14007fba7  jnb     short loc_14007FBCF
0x14007fba9  mov     edx, ebx
0x14007fbab  mov     rcx, rbp; Sid1
0x14007fbae  inc     rdx
0x14007fbb1  add     rdx, rdx
0x14007fbb4  mov     rdx, [rax+rdx*8]; Sid2
0x14007fbb8  call    cs:__imp_RtlEqualSid
0x14007fbbf  nop     dword ptr [rax+rax+00h]
0x14007fbc4  test    al, al
0x14007fbc6  jnz     short loc_14007FBCC
0x14007fbc8  inc     ebx
0x14007fbca  jmp     short loc_14007FBA0
0x14007fbcc  lea     esi, [rbx+1]
0x14007fbcf  mov     rbx, [rsp+38h+arg_0]
0x14007fbd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fbdb  lea     rax, WPP_GLOBAL_Control
0x14007fbe2  mov     rdi, [rsp+38h+arg_10]
0x14007fbe7  mov     rbp, [rsp+38h+arg_8]
0x14007fbec  cmp     rcx, rax
0x14007fbef  jz      short loc_14007FBFA
0x14007fbf1  test    dword ptr [rcx+2Ch], 40000h
0x14007fbf8  jnz     short loc_14007FC12
0x14007fbfa  movzx   eax, si
0x14007fbfd  mov     rsi, [rsp+38h+arg_18]
0x14007fc02  add     rsp, 30h
0x14007fc06  pop     r14
0x14007fc08  retn
0x14007fc0a  mov     r14d, 3CBh
0x14007fc10  jmp     short loc_14007FBD4
0x14007fc12  mov     rcx, [rcx+18h]
0x14007fc16  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14007fc1d  movzx   r9d, si
0x14007fc21  mov     edx, 10h
0x14007fc26  mov     [rsp+38h+var_18], r14d
0x14007fc2b  call    WPP_SF_Dd
0x14007fc30  jmp     short loc_14007FBFA
```
