# ReadNegPolObjectsFromRegistry

- ea: `0x180039ae0`
- end: `0x180039c77`
- name: `ReadNegPolObjectsFromRegistry`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180039c80`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x180039ae0`
- `0x18003b070`
- `0x180042dd4`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall ReadNegPolObjectsFromRegistry(
        HKEY a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6)
{
  _QWORD *v6; // r14
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 result; // rax
  SIZE_T v17; // [rsp+30h] [rbp-58h] BYREF
  __int64 v18[10]; // [rsp+38h] [rbp-50h] BYREF

  v6 = a5;
  *a5 = 0;
  *a6 = 0;
  v18[0] = 0;
  v17 = 0;
  v10 = NsuSizeTMultiply(a4, 8, &v17);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_20;
    v12 = 24;
    goto LABEL_5;
  }
  v13 = IpsecAllocMem(v17);
  if ( !v13 )
  {
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_20;
    v12 = 25;
LABEL_5:
    WPP_SF_d(v11[2], v12, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v10);
    goto LABEL_20;
  }
  v14 = 0;
  v15 = 0;
  if ( a4 )
  {
    do
    {
      if ( !(unsigned int)UnMarshallRegistryNegPolObject(a1, a2, *(unsigned __int16 **)(a3 + 8 * v15), 1, v18) )
      {
        v13[v14] = v18[0];
        v14 = (unsigned int)(v14 + 1);
      }
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < a4 );
    v6 = a5;
    if ( (_DWORD)v14 )
    {
      *a5 = v13;
      result = 0;
      *a6 = v14;
      return result;
    }
  }
  v10 = 13;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, 13);
  FreeIpsecNegPolObjects(v13);
LABEL_20:
  *v6 = 0;
  result = v10;
  *a6 = 0;
  return result;
}

```

## disassembly

```asm
0x180039ae0  mov     rax, rsp
0x180039ae3  mov     [rax+8], rcx
0x180039ae7  push    rbx
0x180039ae8  push    rbp
0x180039ae9  push    rsi
0x180039aea  push    rdi
0x180039aeb  push    r12
0x180039aed  push    r13
0x180039aef  push    r14
0x180039af1  push    r15
0x180039af3  sub     rsp, 48h
0x180039af7  mov     r14, [rsp+88h+arg_20]
0x180039aff  mov     r13, rdx
0x180039b02  mov     r15, [rsp+88h+arg_28]
0x180039b0a  mov     r12, r8
0x180039b0d  mov     ecx, r9d
0x180039b10  lea     r8, [rax-58h]
0x180039b14  mov     edx, 8
0x180039b19  mov     ebp, r9d
0x180039b1c  mov     qword ptr [r14], 0
0x180039b23  mov     dword ptr [r15], 0
0x180039b2a  mov     qword ptr [rax-50h], 0
0x180039b32  mov     qword ptr [rax-58h], 0
0x180039b3a  call    NsuSizeTMultiply
0x180039b3f  mov     ebx, eax
0x180039b41  test    eax, eax
0x180039b43  jz      short loc_180039B83
0x180039b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b4c  lea     rax, WPP_GLOBAL_Control
0x180039b53  cmp     rcx, rax
0x180039b56  jz      loc_180039C56
0x180039b5c  test    byte ptr [rcx+1Ch], 10h
0x180039b60  jz      loc_180039C56
0x180039b66  mov     edx, 18h
0x180039b6b  mov     rcx, [rcx+10h]
0x180039b6f  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x180039b76  mov     r9d, ebx
0x180039b79  call    WPP_SF_d
0x180039b7e  jmp     loc_180039C56
0x180039b83  mov     rcx, [rsp+88h+var_58]
0x180039b88  call    IpsecAllocMem
0x180039b8d  mov     rdi, rax
0x180039b90  test    rax, rax
0x180039b93  jnz     short loc_180039BBE
0x180039b95  lea     ebx, [rax+0Eh]
0x180039b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b9f  lea     rax, WPP_GLOBAL_Control
0x180039ba6  cmp     rcx, rax
0x180039ba9  jz      loc_180039C56
0x180039baf  test    byte ptr [rcx+1Ch], 10h
0x180039bb3  jz      loc_180039C56
0x180039bb9  lea     edx, [rdi+19h]
0x180039bbc  jmp     short loc_180039B6B
0x180039bbe  xor     ebx, ebx
0x180039bc0  xor     esi, esi
0x180039bc2  test    ebp, ebp
0x180039bc4  jz      short loc_180039C18
0x180039bc6  mov     r14, [rsp+88h+hKey]
0x180039bce  mov     r8, [r12+rsi*8]
0x180039bd2  lea     rax, [rsp+88h+var_50]
0x180039bd7  mov     r9d, 1
0x180039bdd  mov     [rsp+88h+var_68], rax; __int64
0x180039be2  mov     rdx, r13
0x180039be5  mov     rcx, r14; hKey
0x180039be8  call    UnMarshallRegistryNegPolObject
0x180039bed  test    eax, eax
0x180039bef  jnz     short loc_180039BFC
0x180039bf1  mov     rax, [rsp+88h+var_50]
0x180039bf6  mov     [rdi+rbx*8], rax
0x180039bfa  inc     ebx
0x180039bfc  inc     esi
0x180039bfe  cmp     esi, ebp
0x180039c00  jb      short loc_180039BCE
0x180039c02  mov     r14, [rsp+88h+arg_20]
0x180039c0a  test    ebx, ebx
0x180039c0c  jz      short loc_180039C18
0x180039c0e  mov     [r14], rdi
0x180039c11  xor     eax, eax
0x180039c13  mov     [r15], ebx
0x180039c16  jmp     short loc_180039C66
0x180039c18  mov     ebx, 0Dh
0x180039c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c24  lea     rax, WPP_GLOBAL_Control
0x180039c2b  cmp     rcx, rax
0x180039c2e  jz      short loc_180039C4C
0x180039c30  test    byte ptr [rcx+1Ch], 10h
0x180039c34  jz      short loc_180039C4C
0x180039c36  mov     rcx, [rcx+10h]
0x180039c3a  lea     edx, [rbx+0Dh]
0x180039c3d  mov     r9d, ebx
0x180039c40  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x180039c47  call    WPP_SF_d
0x180039c4c  xor     edx, edx
0x180039c4e  mov     rcx, rdi; lpMem
0x180039c51  call    FreeIpsecNegPolObjects
0x180039c56  mov     qword ptr [r14], 0
0x180039c5d  mov     eax, ebx
0x180039c5f  mov     dword ptr [r15], 0
0x180039c66  add     rsp, 48h
0x180039c6a  pop     r15
0x180039c6c  pop     r14
0x180039c6e  pop     r13
0x180039c70  pop     r12
0x180039c72  pop     rdi
0x180039c73  pop     rsi
0x180039c74  pop     rbp
0x180039c75  pop     rbx
0x180039c76  retn
```
