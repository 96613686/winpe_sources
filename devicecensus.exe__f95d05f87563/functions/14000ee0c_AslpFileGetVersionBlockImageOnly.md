# AslpFileGetVersionBlockImageOnly

- ea: `0x14000ee0c`
- end: `0x14000f0e1`
- name: `AslpFileGetVersionBlockImageOnly`
- size: `725`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000e18c`

## callees

- `0x140001ff2`
- `0x140007074`
- `0x14000bde8`
- `0x14000dd40`
- `0x14000eab4`
- `0x14000ee0c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14000f0c9`
- `ntdll!RtlFreeHeap` at `0x14000f0c9`
- `ntdll!RtlAllocateHeap` at `0x14000effc`
- `ntdll!RtlAllocateHeap` at `0x14000effc`

## string_xrefs

- `0x14000eedc`: `AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]`
- `0x14000ef38`: `AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockImageOnly(_QWORD *a1, unsigned __int16 **a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r8
  unsigned __int16 *v8; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned __int64 v11; // rdx
  int ImageResourceDirectoryRoot; // eax
  const char *v13; // r9
  __int64 v14; // r8
  int VersionBlockFromResourceRoot; // eax
  size_t v16; // r14
  void *v17; // r12
  unsigned __int64 v18; // rax
  char *v19; // rcx
  SIZE_T v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v23; // rsi
  unsigned __int16 *v24; // rax
  void *Src; // [rsp+40h] [rbp-48h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+18h] BYREF
  SIZE_T Size; // [rsp+A8h] [rbp+20h] BYREF

  v28 = 0;
  Src = 0;
  Size = 0;
  v7 = *(_QWORD *)(a4 + 64);
  if ( v7 )
  {
    v8 = 0;
    if ( *(_WORD *)(v7 + 2) >= 0x34u )
      v8 = (unsigned __int16 *)(v7 + 40);
    *a2 = v8;
    *a1 = *(_QWORD *)(a4 + 64);
    return 0;
  }
  v10 = AslFileMappingEnsure(a4);
  v9 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2288, "AslFileMappingEnsure failed [%x]", v10);
    return v9;
  }
  if ( *(_DWORD *)(a4 + 56) != 6 )
    return (unsigned int)-1073741687;
  ImageResourceDirectoryRoot = AslpFileGetImageResourceDirectoryRoot((unsigned __int64 *)&v28, v11, a4);
  v9 = ImageResourceDirectoryRoot;
  if ( ImageResourceDirectoryRoot < 0 )
  {
    if ( (unsigned int)(ImageResourceDirectoryRoot + 1073741687) <= 2 )
      return v9;
    v13 = "AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]";
    v14 = 2315;
LABEL_12:
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", v14, v13, v9);
    return v9;
  }
  VersionBlockFromResourceRoot = AslpFileGetVersionBlockFromResourceRoot((unsigned __int16 **)&Src, &Size, v28, a4);
  v9 = VersionBlockFromResourceRoot;
  if ( VersionBlockFromResourceRoot < 0 )
  {
    if ( (unsigned int)(VersionBlockFromResourceRoot + 1073741687) <= 2 )
      return v9;
    v13 = "AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]";
    v14 = 2323;
    goto LABEL_12;
  }
  v16 = Size;
  if ( !Size )
    return (unsigned int)-1073741687;
  v17 = Src;
  if ( !Src )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2335,
      "AslpFileGetVersionBlockFromResourceRoot returned null version block with status [%x]",
      VersionBlockFromResourceRoot);
    return (unsigned int)-1073741687;
  }
  if ( Size > 0x7FFF )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2341,
      "AslpFileGetVersionBlockFromResourceRoot returned version block size that is too large");
    return (unsigned int)-1073741687;
  }
  v18 = *(_QWORD *)(a4 + 32);
  if ( (unsigned __int64)Src < v18
    || (v19 = (char *)Src + Size, Src > (char *)Src + Size)
    || (v20 = *(_QWORD *)(a4 + 40), v21 = v20 + v18, (unsigned __int64)Src > v20 + v18)
    || (unsigned __int64)v19 < v18
    || (unsigned __int64)v19 > v21
    || v18 > v21
    || Size > v20 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2350, "Version block out of range");
    return (unsigned int)-1073741687;
  }
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
  v23 = Heap;
  if ( Heap )
  {
    memmove_0(Heap, v17, v16);
    if ( v16 < *v23 )
      *v23 = v16;
    v24 = v23 + 20;
    if ( v23[1] < 0x34u )
      v24 = 0;
    *a2 = v24;
    *a1 = v23;
    *(_QWORD *)(a4 + 64) = v23;
    return 0;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
}

```

## disassembly

```asm
0x14000ee0c  mov     rax, rsp
0x14000ee0f  mov     [rax+18h], r8
0x14000ee13  mov     [rax+8], rcx
0x14000ee17  push    rbx
0x14000ee18  push    rsi
0x14000ee19  push    rdi
0x14000ee1a  push    r12
0x14000ee1c  push    r13
0x14000ee1e  push    r14
0x14000ee20  push    r15
0x14000ee22  sub     rsp, 50h
0x14000ee26  mov     r15, r9
0x14000ee29  mov     r13, rdx
0x14000ee2c  mov     rdx, rcx
0x14000ee2f  xor     edi, edi
0x14000ee31  mov     [rax+18h], rdi
0x14000ee35  mov     [rax-48h], rdi
0x14000ee39  mov     esi, edi
0x14000ee3b  mov     [rax-50h], rdi
0x14000ee3f  mov     [rax+20h], rdi
0x14000ee43  mov     r8, [r9+40h]
0x14000ee47  test    r8, r8
0x14000ee4a  jz      short loc_14000EE6E
0x14000ee4c  lea     rax, [r8+28h]
0x14000ee50  mov     ecx, edi
0x14000ee52  cmp     word ptr [r8+2], 34h ; '4'
0x14000ee58  cmovnb  rcx, rax
0x14000ee5c  mov     [r13+0], rcx
0x14000ee60  mov     rax, [r9+40h]
0x14000ee64  mov     [rdx], rax
0x14000ee67  mov     ebx, edi
0x14000ee69  jmp     loc_14000F0B2
0x14000ee6e  mov     rcx, r15
0x14000ee71  call    AslFileMappingEnsure
0x14000ee76  mov     ebx, eax
0x14000ee78  test    eax, eax
0x14000ee7a  jns     short loc_14000EEA3
0x14000ee7c  mov     [rsp+88h+var_68], eax
0x14000ee80  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000ee87  mov     r8d, 8F0h
0x14000ee8d  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x14000ee94  mov     ecx, 1
0x14000ee99  call    AslLogCallPrintf
0x14000ee9e  jmp     loc_14000F0B2
0x14000eea3  cmp     dword ptr [r15+38h], 6
0x14000eea8  jz      short loc_14000EEB4
0x14000eeaa  mov     ebx, 0C0000089h
0x14000eeaf  jmp     loc_14000F0B2
0x14000eeb4  mov     r8, r15
0x14000eeb7  lea     rcx, [rsp+88h+arg_10]
0x14000eebf  call    AslpFileGetImageResourceDirectoryRoot
0x14000eec4  mov     ebx, eax
0x14000eec6  mov     [rsp+88h+var_58], eax
0x14000eeca  test    eax, eax
0x14000eecc  jns     short loc_14000EF03
0x14000eece  add     eax, 3FFFFF77h
0x14000eed3  cmp     eax, 2
0x14000eed6  jbe     loc_14000F083
0x14000eedc  lea     r9, aAslpfilegetima; "AslpFileGetImageResourceDirectoryRoot f"...
0x14000eee3  mov     r8d, 90Bh
0x14000eee9  mov     [rsp+88h+var_68], ebx
0x14000eeed  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x14000eef4  mov     ecx, 1
0x14000eef9  call    AslLogCallPrintf
0x14000eefe  jmp     loc_14000F083
0x14000ef03  mov     r9, r15
0x14000ef06  mov     r8, [rsp+88h+arg_10]
0x14000ef0e  lea     rdx, [rsp+88h+Size]
0x14000ef16  lea     rcx, [rsp+88h+Src]
0x14000ef1b  call    AslpFileGetVersionBlockFromResourceRoot
0x14000ef20  mov     ebx, eax
0x14000ef22  mov     [rsp+88h+var_58], eax
0x14000ef26  test    eax, eax
0x14000ef28  jns     short loc_14000EF47
0x14000ef2a  add     eax, 3FFFFF77h
0x14000ef2f  cmp     eax, 2
0x14000ef32  jbe     loc_14000F083
0x14000ef38  lea     r9, aAslpfilegetver_6; "AslpFileGetVersionBlockFromResourceRoot"...
0x14000ef3f  mov     r8d, 913h
0x14000ef45  jmp     short loc_14000EEE9
0x14000ef47  mov     r14, [rsp+88h+Size]
0x14000ef4f  test    r14, r14
0x14000ef52  jz      loc_14000F07A
0x14000ef58  mov     r12, [rsp+88h+Src]
0x14000ef5d  test    r12, r12
0x14000ef60  jnz     short loc_14000EF89
0x14000ef62  mov     [rsp+88h+var_68], ebx
0x14000ef66  lea     r9, aAslpfilegetver; "AslpFileGetVersionBlockFromResourceRoot"...
0x14000ef6d  mov     r8d, 91Fh
0x14000ef73  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x14000ef7a  lea     ecx, [r12+1]
0x14000ef7f  call    AslLogCallPrintf
0x14000ef84  jmp     loc_14000F07A
0x14000ef89  cmp     r14, 7FFFh
0x14000ef90  jbe     short loc_14000EFA4
0x14000ef92  lea     r9, aAslpfilegetver_2; "AslpFileGetVersionBlockFromResourceRoot"...
0x14000ef99  mov     r8d, 925h
0x14000ef9f  jmp     loc_14000F069
0x14000efa4  mov     rax, [r15+20h]
0x14000efa8  cmp     r12, rax
0x14000efab  jb      loc_14000F05C
0x14000efb1  lea     rcx, [r14+r12]
0x14000efb5  cmp     r12, rcx
0x14000efb8  ja      loc_14000F05C
0x14000efbe  mov     r8, [r15+28h]
0x14000efc2  lea     rdx, [r8+rax]
0x14000efc6  cmp     r12, rdx
0x14000efc9  ja      loc_14000F05C
0x14000efcf  cmp     rcx, rax
0x14000efd2  jb      loc_14000F05C
0x14000efd8  cmp     rcx, rdx
0x14000efdb  ja      short loc_14000F05C
0x14000efdd  cmp     rax, rdx
0x14000efe0  ja      short loc_14000F05C
0x14000efe2  cmp     r14, r8
0x14000efe5  ja      short loc_14000F05C
0x14000efe7  mov     rcx, gs:60h
0x14000eff0  mov     r8, r14; Size
0x14000eff3  mov     edx, 8; Flags
0x14000eff8  mov     rcx, [rcx+30h]; HeapHandle
0x14000effc  call    cs:__imp_RtlAllocateHeap
0x14000f002  mov     rsi, rax
0x14000f005  mov     [rsp+88h+var_50], rax
0x14000f00a  test    rax, rax
0x14000f00d  jnz     short loc_14000F016
0x14000f00f  mov     ebx, 0C0000017h
0x14000f014  jmp     short loc_14000F07F
0x14000f016  mov     r8, r14; Size
0x14000f019  mov     rdx, r12; Src
0x14000f01c  mov     rcx, rsi; void *
0x14000f01f  call    memmove_0
0x14000f024  movzx   eax, word ptr [rsi]
0x14000f027  cmp     r14, rax
0x14000f02a  jnb     short loc_14000F030
0x14000f02c  mov     [rsi], r14w
0x14000f030  lea     rax, [rsi+28h]
0x14000f034  cmp     word ptr [rsi+2], 34h ; '4'
0x14000f039  cmovb   rax, rdi
0x14000f03d  mov     [r13+0], rax
0x14000f041  mov     rax, [rsp+88h+arg_0]
0x14000f049  mov     [rax], rsi
0x14000f04c  mov     [r15+40h], rsi
0x14000f050  mov     rsi, rdi
0x14000f053  mov     [rsp+88h+var_50], rdi
0x14000f058  mov     ebx, edi
0x14000f05a  jmp     short loc_14000F07F
0x14000f05c  lea     r9, aVersionBlockOu; "Version block out of range"
0x14000f063  mov     r8d, 92Eh
0x14000f069  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x14000f070  mov     ecx, 1
0x14000f075  call    AslLogCallPrintf
0x14000f07a  mov     ebx, 0C0000089h
0x14000f07f  mov     [rsp+88h+var_58], ebx
0x14000f083  jmp     short loc_14000F0B2
0x14000f085  mov     ebx, eax
0x14000f087  mov     [rsp+88h+var_58], eax
0x14000f08b  mov     [rsp+88h+var_68], eax
0x14000f08f  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000f096  mov     r8d, 966h
0x14000f09c  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x14000f0a3  mov     ecx, 1
0x14000f0a8  call    AslLogCallPrintf
0x14000f0ad  mov     rsi, [rsp+88h+var_50]
0x14000f0b2  test    rsi, rsi
0x14000f0b5  jz      short loc_14000F0CF
0x14000f0b7  mov     rcx, gs:60h
0x14000f0c0  mov     r8, rsi; P
0x14000f0c3  xor     edx, edx; Flags
0x14000f0c5  mov     rcx, [rcx+30h]; HeapHandle
0x14000f0c9  call    cs:__imp_RtlFreeHeap
0x14000f0cf  mov     eax, ebx
0x14000f0d1  add     rsp, 50h
0x14000f0d5  pop     r15
0x14000f0d7  pop     r14
0x14000f0d9  pop     r13
0x14000f0db  pop     r12
0x14000f0dd  pop     rdi
0x14000f0de  pop     rsi
0x14000f0df  pop     rbx
0x14000f0e0  retn
0x140011836  push    rbp
0x140011838  sub     rsp, 30h
0x14001183c  mov     rbp, rdx
0x14001183f  mov     rax, [rcx]
0x140011842  xor     ecx, ecx
0x140011844  cmp     dword ptr [rax], 0C00000FDh
0x14001184a  setnz   cl
0x14001184d  mov     [rbp+34h], ecx
0x140011850  mov     eax, [rbp+34h]
0x140011853  add     rsp, 30h
0x140011857  pop     rbp
0x140011858  retn
```
