# SeSddlSecurityDescriptorFromSDDL

- ea: `0x140045c88`
- end: `0x140045d44`
- name: `SeSddlSecurityDescriptorFromSDDL`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009b2c`

## callees

- `0x14000bb80`
- `0x14000be80`
- `0x140045c88`
- `0x140046470`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045ccd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045ccd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d2a`

## pseudocode

```c
__int64 __fastcall SeSddlSecurityDescriptorFromSDDL(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v3; // rdx
  SIZE_T v6; // r9
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  PVOID PoolWithTag; // rax
  void *v11; // r14
  ULONG v12; // edx
  unsigned int v13; // ebx

  v3 = *a1;
  v6 = v3 + 2;
  if ( a1[1] == v3 + 2 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = v3 >> 1;
    if ( !*(_WORD *)(v7 + 2 * v8) )
      return SepSddlSecurityDescriptorFromSDDLString(v7, v8, (__int64)a3);
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v6, 0x73546553u);
  v11 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, *a1 + 2LL);
    memmove(v11, *((const void **)a1 + 1), *a1);
    *((_WORD *)v11 + ((unsigned __int64)*a1 >> 1)) = 0;
    v13 = SepSddlSecurityDescriptorFromSDDLString((__int64)v11, v12, (__int64)a3);
    ExFreePoolWithTag(v11, 0);
    return v13;
  }
  else
  {
    *a3 = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140045c88  push    rbx
0x140045c8a  push    rbp
0x140045c8b  push    rsi
0x140045c8c  push    rdi
0x140045c8d  push    r14
0x140045c8f  sub     rsp, 20h
0x140045c93  movzx   edx, word ptr [rcx]
0x140045c96  xor     ebp, ebp
0x140045c98  movzx   eax, word ptr [rcx+2]
0x140045c9c  mov     rsi, r8
0x140045c9f  mov     rdi, rcx
0x140045ca2  lea     r9, [rdx+2]
0x140045ca6  cmp     rax, r9
0x140045ca9  jnz     short loc_140045CBF
0x140045cab  mov     rcx, [rcx+8]
0x140045caf  shr     rdx, 1
0x140045cb2  cmp     [rcx+rdx*2], bp
0x140045cb6  jnz     short loc_140045CBF
0x140045cb8  call    SepSddlSecurityDescriptorFromSDDLString
0x140045cbd  jmp     short loc_140045D38
0x140045cbf  mov     r8d, 73546553h; Tag
0x140045cc5  mov     rdx, r9; NumberOfBytes
0x140045cc8  mov     ecx, 1; PoolType
0x140045ccd  call    cs:__imp_ExAllocatePoolWithTag
0x140045cd4  nop     dword ptr [rax+rax+00h]
0x140045cd9  mov     r14, rax
0x140045cdc  test    rax, rax
0x140045cdf  jnz     short loc_140045CEB
0x140045ce1  mov     [rsi], rbp
0x140045ce4  mov     eax, 0C000009Ah
0x140045ce9  jmp     short loc_140045D38
0x140045ceb  movzx   r8d, word ptr [rdi]
0x140045cef  xor     edx, edx; Val
0x140045cf1  add     r8, 2; Size
0x140045cf5  mov     rcx, r14; void *
0x140045cf8  call    memset
0x140045cfd  movzx   r8d, word ptr [rdi]; Size
0x140045d01  mov     rcx, r14; void *
0x140045d04  mov     rdx, [rdi+8]; Src
0x140045d08  call    memmove
0x140045d0d  movzx   ecx, word ptr [rdi]
0x140045d10  mov     r8, rsi
0x140045d13  shr     rcx, 1
0x140045d16  mov     [r14+rcx*2], bp
0x140045d1b  mov     rcx, r14
0x140045d1e  call    SepSddlSecurityDescriptorFromSDDLString
0x140045d23  xor     edx, edx; Tag
0x140045d25  mov     rcx, r14; P
0x140045d28  mov     ebx, eax
0x140045d2a  call    cs:__imp_ExFreePoolWithTag
0x140045d31  nop     dword ptr [rax+rax+00h]
0x140045d36  mov     eax, ebx
0x140045d38  add     rsp, 20h
0x140045d3c  pop     r14
0x140045d3e  pop     rdi
0x140045d3f  pop     rsi
0x140045d40  pop     rbp
0x140045d41  pop     rbx
0x140045d42  retn
```
