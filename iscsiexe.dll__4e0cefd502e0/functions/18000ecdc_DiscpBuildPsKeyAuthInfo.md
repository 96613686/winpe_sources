# DiscpBuildPsKeyAuthInfo

- ea: `0x18000ecdc`
- end: `0x18000edb3`
- name: `DiscpBuildPsKeyAuthInfo`
- size: `215`
- prototype: `__int64 __fastcall(__int64, char, unsigned int, const void *, unsigned int Size, void *Src, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eeb0`
- `0x18001048c`
- `0x180010770`

## callees

- `0x180001cfe`
- `0x18000ecdc`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18000ed0e`
- `ISCSIUM!DiscpAllocMemory` at `0x18000ed0e`

## pseudocode

```c
__int64 __fastcall DiscpBuildPsKeyAuthInfo(
        __int64 a1,
        char a2,
        unsigned int a3,
        const void *a4,
        unsigned int Size,
        void *Src,
        _QWORD *a7)
{
  __int64 v8; // rbp
  unsigned int v11; // esi
  char *v12; // rax
  char *v13; // rbx
  char *v14; // rcx

  v8 = a3;
  v11 = a3 + 48 + Size;
  if ( v11 < a3 + 48 )
    return 87;
  v12 = (char *)DiscpAllocMemory(v11);
  v13 = v12;
  if ( !v12 )
    return 8;
  memset_0(v12, 0, v11);
  *(_DWORD *)v13 = 1;
  v13[16] = a2;
  *((_QWORD *)v13 + 1) = a1;
  *((_DWORD *)v13 + 5) = v8;
  if ( a4 )
  {
    *((_QWORD *)v13 + 3) = v13 + 48;
    memcpy_0(v13 + 48, a4, (unsigned int)v8);
  }
  else
  {
    *((_QWORD *)v13 + 3) = 0;
  }
  *((_DWORD *)v13 + 8) = Size;
  if ( Src )
  {
    v14 = &v13[v8 + 48];
    *((_QWORD *)v13 + 5) = v14;
    memcpy_0(v14, Src, Size);
  }
  else
  {
    *((_QWORD *)v13 + 5) = 0;
  }
  *a7 = v13;
  return 0;
}

```

## disassembly

```asm
0x18000ecdc  push    rbx
0x18000ecde  push    rbp
0x18000ecdf  push    rsi
0x18000ece0  push    rdi
0x18000ece1  push    r12
0x18000ece3  push    r14
0x18000ece5  push    r15
0x18000ece7  sub     rsp, 20h
0x18000eceb  mov     edi, dword ptr [rsp+58h+Size]
0x18000ecf2  mov     r14, r9
0x18000ecf5  mov     ebp, r8d
0x18000ecf8  mov     r15b, dl
0x18000ecfb  mov     r12, rcx
0x18000ecfe  lea     eax, [rbp+30h]
0x18000ed01  lea     esi, [rax+rdi]
0x18000ed04  cmp     esi, eax
0x18000ed06  jb      loc_18000ED9F
0x18000ed0c  mov     ecx, esi
0x18000ed0e  call    cs:__imp_DiscpAllocMemory
0x18000ed14  mov     rbx, rax
0x18000ed17  test    rax, rax
0x18000ed1a  jz      short loc_18000ED98
0x18000ed1c  mov     r8d, esi; Size
0x18000ed1f  xor     edx, edx; Val
0x18000ed21  mov     rcx, rax; void *
0x18000ed24  call    memset_0
0x18000ed29  mov     dword ptr [rbx], 1
0x18000ed2f  mov     [rbx+10h], r15b
0x18000ed33  mov     [rbx+8], r12
0x18000ed37  mov     [rbx+14h], ebp
0x18000ed3a  test    r14, r14
0x18000ed3d  jz      short loc_18000ED54
0x18000ed3f  lea     rcx, [rbx+30h]; void *
0x18000ed43  mov     r8d, ebp; Size
0x18000ed46  mov     rdx, r14; Src
0x18000ed49  mov     [rbx+18h], rcx
0x18000ed4d  call    memcpy_0
0x18000ed52  jmp     short loc_18000ED5C
0x18000ed54  mov     qword ptr [rbx+18h], 0
0x18000ed5c  mov     rdx, [rsp+58h+Src]; Src
0x18000ed64  mov     [rbx+20h], edi
0x18000ed67  test    rdx, rdx
0x18000ed6a  jz      short loc_18000ED81
0x18000ed6c  lea     rcx, [rbp+30h]
0x18000ed70  mov     r8, rdi; Size
0x18000ed73  add     rcx, rbx; void *
0x18000ed76  mov     [rbx+28h], rcx
0x18000ed7a  call    memcpy_0
0x18000ed7f  jmp     short loc_18000ED89
0x18000ed81  mov     qword ptr [rbx+28h], 0
0x18000ed89  mov     rax, [rsp+58h+arg_30]
0x18000ed91  mov     [rax], rbx
0x18000ed94  xor     eax, eax
0x18000ed96  jmp     short loc_18000EDA4
0x18000ed98  mov     eax, 8
0x18000ed9d  jmp     short loc_18000EDA4
0x18000ed9f  mov     eax, 57h ; 'W'
0x18000eda4  add     rsp, 20h
0x18000eda8  pop     r15
0x18000edaa  pop     r14
0x18000edac  pop     r12
0x18000edae  pop     rdi
0x18000edaf  pop     rsi
0x18000edb0  pop     rbp
0x18000edb1  pop     rbx
0x18000edb2  retn
```
