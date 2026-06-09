# ExtractMatrixWithOffsets

- ea: `0x18001a7d0`
- end: `0x18001a94f`
- name: `ExtractMatrixWithOffsets`
- size: `383`
- prototype: `__int64 __fastcall(HPROFILE hProfile, TAGTYPE tag, unsigned int, unsigned __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180019f50`
- `0x180020c14`

## callees

- `0x1800042e0`
- `0x18001a7d0`
- `0x18001d15d`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x18001a878`
- `mscms!GetColorProfileElement` at `0x18001a878`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a851`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a851`

## pseudocode

```c
__int64 __fastcall ExtractMatrixWithOffsets(
        HPROFILE hProfile,
        TAGTYPE tag,
        unsigned int a3,
        unsigned __int64 a4,
        _QWORD *a5)
{
  DWORD v5; // ebx
  unsigned int v8; // ebx
  void *v9; // rax
  unsigned __int8 *v10; // rdx
  __int64 v11; // r8
  unsigned __int64 i; // rcx
  unsigned __int64 j; // rdx
  DWORD pcbElement; // [rsp+30h] [rbp-58h] BYREF
  WINBOOL pbReference; // [rsp+34h] [rbp-54h] BYREF
  _DWORD pElement[12]; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int8 v18[32]; // [rsp+68h] [rbp-20h] BYREF

  v5 = a4;
  pcbElement = 0;
  *a5 = 0;
  if ( a4 >= a3 )
    goto LABEL_2;
  pcbElement = 48;
  if ( a3 - a4 < 0x30 )
    goto LABEL_2;
  v9 = malloc_0(0x60u);
  *a5 = v9;
  if ( !v9 )
  {
    v8 = 8;
    goto LABEL_16;
  }
  pbReference = 0;
  SetLastError(0);
  if ( !GetColorProfileElement(hProfile, tag, v5, &pcbElement, pElement, &pbReference) )
  {
    v8 = 2012;
    goto LABEL_16;
  }
  if ( pcbElement != 48 )
  {
LABEL_2:
    v8 = 2011;
LABEL_16:
    DisposeIfPtr(*a5);
    return v8;
  }
  v8 = 0;
  v10 = (unsigned __int8 *)pElement;
  do
  {
    *(_DWORD *)v10 = v10[3] | ((v10[2] | ((v10[1] | (*v10 << 8)) << 8)) << 8);
    v10 += 4;
  }
  while ( v10 < v18 );
  v11 = *a5;
  for ( i = 0; i < 3; ++i )
  {
    for ( j = 0; j < 3; ++j )
      *(double *)(v11 + 24 * i + 8 * j) = (double)(int)pElement[3 * i + j] * 0.0000152587890625;
    *(double *)(v11 + 8 * i + 72) = (double)(int)pElement[i + 9] * 0.0000152587890625;
  }
  return v8;
}

```

## disassembly

```asm
0x18001a7d0  mov     [rsp+arg_10], rbx
0x18001a7d5  push    rbp
0x18001a7d6  push    rsi
0x18001a7d7  push    rdi
0x18001a7d8  sub     rsp, 70h
0x18001a7dc  mov     rax, cs:__security_cookie
0x18001a7e3  xor     rax, rsp
0x18001a7e6  mov     qword ptr [rsp+88h+var_20], rax
0x18001a7eb  mov     rdi, [rsp+88h+arg_20]
0x18001a7f3  mov     rbx, r9
0x18001a7f6  mov     eax, r8d
0x18001a7f9  mov     ebp, edx
0x18001a7fb  mov     [rsp+88h+pcbElement], 0
0x18001a803  mov     rsi, rcx
0x18001a806  mov     qword ptr [rdi], 0
0x18001a80d  cmp     r9, rax
0x18001a810  jb      short loc_18001A81C
0x18001a812  mov     ebx, 7DBh
0x18001a817  jmp     loc_18001A928
0x18001a81c  sub     rax, rbx
0x18001a81f  mov     [rsp+88h+pcbElement], 30h ; '0'
0x18001a827  cmp     rax, 30h ; '0'
0x18001a82b  jb      short loc_18001A812
0x18001a82d  mov     ecx, 60h ; '`'; Size
0x18001a832  call    malloc_0
0x18001a837  mov     [rdi], rax
0x18001a83a  test    rax, rax
0x18001a83d  jnz     short loc_18001A847
0x18001a83f  lea     ebx, [rax+8]
0x18001a842  jmp     loc_18001A928
0x18001a847  xor     ecx, ecx; dwErrCode
0x18001a849  mov     [rsp+88h+var_54], 0
0x18001a851  call    cs:__imp_SetLastError
0x18001a857  lea     rax, [rsp+88h+var_54]
0x18001a85c  mov     r8d, ebx; dwOffset
0x18001a85f  mov     [rsp+88h+pbReference], rax; pbReference
0x18001a864  lea     r9, [rsp+88h+pcbElement]; pcbElement
0x18001a869  lea     rax, [rsp+88h+var_50]
0x18001a86e  mov     edx, ebp; tag
0x18001a870  mov     rcx, rsi; hProfile
0x18001a873  mov     [rsp+88h+pElement], rax; pElement
0x18001a878  call    cs:__imp_GetColorProfileElement
0x18001a87e  test    eax, eax
0x18001a880  jz      loc_18001A923
0x18001a886  cmp     [rsp+88h+pcbElement], 30h ; '0'
0x18001a88b  jnz     short loc_18001A812
0x18001a88d  xor     ebx, ebx
0x18001a88f  lea     rdx, [rsp+88h+var_50]
0x18001a894  movzx   eax, byte ptr [rdx+1]
0x18001a898  movzx   ecx, byte ptr [rdx]
0x18001a89b  shl     ecx, 8
0x18001a89e  or      ecx, eax
0x18001a8a0  movzx   eax, byte ptr [rdx+2]
0x18001a8a4  shl     ecx, 8
0x18001a8a7  or      ecx, eax
0x18001a8a9  movzx   eax, byte ptr [rdx+3]
0x18001a8ad  shl     ecx, 8
0x18001a8b0  or      ecx, eax
0x18001a8b2  lea     rax, [rsp+88h+var_20]
0x18001a8b7  mov     [rdx], ecx
0x18001a8b9  add     rdx, 4
0x18001a8bd  cmp     rdx, rax
0x18001a8c0  jb      short loc_18001A894
0x18001a8c2  mov     r8, [rdi]
0x18001a8c5  xor     ecx, ecx
0x18001a8c7  movsd   xmm1, cs:__real@3ef0000000000000
0x18001a8cf  lea     rax, [rcx+rcx*2]
0x18001a8d3  xor     edx, edx
0x18001a8d5  lea     r9, [rsp+88h+var_50]
0x18001a8da  lea     r9, [r9+rax*4]
0x18001a8de  lea     rax, [rcx+rcx*2]
0x18001a8e2  lea     r10, [r8+rax*8]
0x18001a8e6  movd    xmm0, dword ptr [r9+rdx*4]
0x18001a8ec  cvtdq2pd xmm0, xmm0
0x18001a8f0  mulsd   xmm0, xmm1
0x18001a8f4  movsd   qword ptr [r10+rdx*8], xmm0
0x18001a8fa  inc     rdx
0x18001a8fd  cmp     rdx, 3
0x18001a901  jb      short loc_18001A8E6
0x18001a903  movd    xmm0, [rsp+rcx*4+88h+var_2C]
0x18001a909  cvtdq2pd xmm0, xmm0
0x18001a90d  mulsd   xmm0, xmm1
0x18001a911  movsd   qword ptr [r8+rcx*8+48h], xmm0
0x18001a918  inc     rcx
0x18001a91b  cmp     rcx, 3
0x18001a91f  jb      short loc_18001A8CF
0x18001a921  jmp     short loc_18001A930
0x18001a923  mov     ebx, 7DCh
0x18001a928  mov     rcx, [rdi]
0x18001a92b  call    DisposeIfPtr
0x18001a930  mov     eax, ebx
0x18001a932  mov     rcx, qword ptr [rsp+88h+var_20]
0x18001a937  xor     rcx, rsp; StackCookie
0x18001a93a  call    __security_check_cookie
0x18001a93f  mov     rbx, [rsp+88h+arg_10]
0x18001a947  add     rsp, 70h
0x18001a94b  pop     rdi
0x18001a94c  pop     rsi
0x18001a94d  pop     rbp
0x18001a94e  retn
```
