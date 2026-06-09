# Smb2Fsctl_Receive

- ea: `0x14000f7c0`
- end: `0x14000f9f6`
- name: `Smb2Fsctl_Receive`
- size: `566`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000f7c0`
- `0x14000fa00`
- `0x1400372c0`

## import_xrefs

- `mrxsmb!RDR_PERF_ENTER` at `0x14000f7f0`
- `mrxsmb!RDR_PERF_ENTER` at `0x14000f7f0`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14000f8a2`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14000f8a2`

## pseudocode

```c
__int64 __fastcall Smb2Fsctl_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        _DWORD *a7)
{
  int v7; // ebx
  __int64 v8; // rcx
  _DWORD *v9; // r12
  __int64 v10; // r14
  int v12; // eax
  unsigned int v13; // esi
  unsigned int v14; // ebp
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int *v18; // rdx
  __int64 v19; // r9
  size_t v20; // r8
  unsigned int v21; // ecx
  unsigned int v22; // eax
  __int64 v23; // [rsp+80h] [rbp+8h] BYREF

  v23 = a1;
  v7 = *(_DWORD *)(a3 + 16);
  v8 = a2 + 880;
  v9 = a7;
  v10 = a2;
  LOBYTE(a2) = 35;
  RDR_PERF_ENTER(v8, a2);
  if ( (int)(v7 + 0x80000000) < 0
    || v7 == -2147483643
    || (v7 == -1073741811 || v7 == -1073741793) && *((_WORD *)v9 + 32) == 49 )
  {
    v14 = 0;
    if ( a4 >= 0x70 && *((_WORD *)v9 + 32) == 49 )
    {
      v13 = a5;
      if ( v7 < 0 )
      {
        v21 = v9[24];
        v18 = v9 + 24;
        if ( v21 < a5 )
        {
          v22 = a5 - v21;
          v16 = *(_DWORD *)(v10 + 744);
          if ( v16 >= v22 )
            v16 = v22;
        }
        else
        {
          v16 = 0;
        }
      }
      else
      {
        v16 = v9[25];
        if ( v16 > *(_DWORD *)(v10 + 744) || (v17 = v9[24], v18 = v9 + 24, v17 > a5) || v16 > a5 || v16 + v17 > a5 )
        {
          v7 = -1073741629;
          goto LABEL_8;
        }
      }
      *(_DWORD *)(v10 + 748) = v16;
      v19 = v23;
      *(_DWORD *)(v23 + 2444) = v9[25];
      v20 = *(unsigned int *)(v10 + 748);
      if ( (_DWORD)v20 && *v18 + v9[25] > a4 )
      {
        v14 = -1073741802;
        v13 = *v18;
      }
      else
      {
        memmove(*(void **)(v19 + 1736), (char *)v9 + *v18, v20);
      }
    }
    else
    {
      v13 = a5;
      v7 = -1073741629;
    }
  }
  else
  {
    a7 = 0;
    LODWORD(v23) = 0;
    v12 = Smb2QueryErrorDataFromResponse((__int64)(v9 + 16), a4, 0, &a7, (unsigned int *)&v23);
    if ( v12 < 0 )
    {
      v13 = a5;
      v7 = v12;
      v14 = 0;
    }
    else
    {
      if ( v7 == -1073741789 )
      {
        if ( (_DWORD)v23 == 4 )
          *(_DWORD *)(v10 + 748) = *a7;
        else
          *(_DWORD *)(v10 + 748) = 0;
      }
      v13 = a5;
      v14 = 0;
    }
  }
LABEL_8:
  *a6 = v13;
  v23 = (unsigned int)v7;
  SmbCseUpdateBufferContextStatus(v10, (unsigned int)v7);
  return v14;
}

```

## disassembly

```asm
0x14000f7c0  mov     [rsp+arg_0], rcx
0x14000f7c5  push    rbx
0x14000f7c6  push    rbp
0x14000f7c7  push    rsi
0x14000f7c8  push    rdi
0x14000f7c9  push    r12
0x14000f7cb  push    r13
0x14000f7cd  push    r14
0x14000f7cf  push    r15
0x14000f7d1  sub     rsp, 38h
0x14000f7d5  mov     ebx, [r8+10h]
0x14000f7d9  lea     rcx, [rdx+370h]
0x14000f7e0  mov     r12, [rsp+78h+arg_30]
0x14000f7e8  mov     r14, rdx
0x14000f7eb  mov     dl, 23h ; '#'
0x14000f7ed  mov     r15d, r9d
0x14000f7f0  call    cs:__imp_RDR_PERF_ENTER
0x14000f7f7  nop     dword ptr [rax+rax+00h]
0x14000f7fc  mov     ecx, 80000000h
0x14000f801  lea     eax, [rbx+rcx]
0x14000f804  test    ecx, eax
0x14000f806  jnz     loc_14000F8CF
0x14000f80c  cmp     ebx, 80000005h
0x14000f812  jz      loc_14000F8CF
0x14000f818  cmp     ebx, 0C000000Dh
0x14000f81e  jz      loc_14000F982
0x14000f824  cmp     ebx, 0C000001Fh
0x14000f82a  jz      loc_14000F982
0x14000f830  xor     edi, edi
0x14000f832  lea     rax, [rsp+78h+arg_0]
0x14000f83a  lea     r9, [rsp+78h+arg_30]
0x14000f842  mov     [rsp+78h+arg_30], rdi
0x14000f84a  xor     r8d, r8d
0x14000f84d  mov     dword ptr [rsp+78h+arg_0], edi
0x14000f854  mov     edx, r15d
0x14000f857  mov     [rsp+78h+var_58], rax
0x14000f85c  lea     rcx, [r12+40h]
0x14000f861  call    Smb2QueryErrorDataFromResponse
0x14000f866  test    eax, eax
0x14000f868  js      short loc_14000F8C2
0x14000f86a  cmp     ebx, 0C0000023h
0x14000f870  jz      loc_14000F9A6
0x14000f876  mov     esi, [rsp+78h+arg_20]
0x14000f87d  mov     ebp, edi
0x14000f87f  mov     rcx, [rsp+78h+arg_28]
0x14000f887  mov     [rcx], esi
0x14000f889  mov     rcx, r14
0x14000f88c  mov     dword ptr [rsp+78h+arg_0], ebx
0x14000f893  mov     dword ptr [rsp+78h+arg_0+4], edi
0x14000f89a  mov     rdx, [rsp+78h+arg_0]
0x14000f8a2  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14000f8a9  nop     dword ptr [rax+rax+00h]
0x14000f8ae  mov     eax, ebp
0x14000f8b0  add     rsp, 38h
0x14000f8b4  pop     r15
0x14000f8b6  pop     r14
0x14000f8b8  pop     r13
0x14000f8ba  pop     r12
0x14000f8bc  pop     rdi
0x14000f8bd  pop     rsi
0x14000f8be  pop     rbp
0x14000f8bf  pop     rbx
0x14000f8c0  retn
0x14000f8c2  mov     esi, [rsp+78h+arg_20]
0x14000f8c9  mov     ebx, eax
0x14000f8cb  mov     ebp, edi
0x14000f8cd  jmp     short loc_14000F87F
0x14000f8cf  xor     edi, edi
0x14000f8d1  mov     ebp, edi
0x14000f8d3  cmp     r15d, 70h ; 'p'
0x14000f8d7  jnb     short loc_14000F8E7
0x14000f8d9  mov     esi, [rsp+78h+arg_20]
0x14000f8e0  mov     ebx, 0C00000C3h
0x14000f8e5  jmp     short loc_14000F87F
0x14000f8e7  cmp     word ptr [r12+40h], 31h ; '1'
0x14000f8ee  jnz     short loc_14000F8D9
0x14000f8f0  mov     esi, [rsp+78h+arg_20]
0x14000f8f7  test    ebx, ebx
0x14000f8f9  js      loc_14000F994
0x14000f8ff  mov     ecx, [r12+64h]
0x14000f904  cmp     ecx, [r14+2E8h]
0x14000f90b  ja      loc_14000F9CA
0x14000f911  mov     eax, [r12+60h]
0x14000f916  lea     rdx, [r12+60h]
0x14000f91b  cmp     eax, esi
0x14000f91d  ja      loc_14000F9CA
0x14000f923  cmp     ecx, esi
0x14000f925  ja      loc_14000F9CA
0x14000f92b  add     eax, ecx
0x14000f92d  cmp     eax, esi
0x14000f92f  ja      loc_14000F9CA
0x14000f935  mov     [r14+2ECh], ecx
0x14000f93c  mov     r9, [rsp+78h+arg_0]
0x14000f944  mov     eax, [r12+64h]
0x14000f949  mov     [r9+98Ch], eax
0x14000f950  mov     r8d, [r14+2ECh]; Size
0x14000f957  test    r8d, r8d
0x14000f95a  jz      short loc_14000F96C
0x14000f95c  mov     ecx, [r12+64h]
0x14000f961  mov     r10d, [rdx]
0x14000f964  add     ecx, r10d
0x14000f967  cmp     ecx, r15d
0x14000f96a  ja      short loc_14000F9E9
0x14000f96c  mov     edx, [rdx]
0x14000f96e  mov     rcx, [r9+6C8h]; void *
0x14000f975  add     rdx, r12; Src
0x14000f978  call    memmove
0x14000f97d  jmp     loc_14000F87F
0x14000f982  cmp     word ptr [r12+40h], 31h ; '1'
0x14000f989  jnz     loc_14000F830
0x14000f98f  jmp     loc_14000F8CF
0x14000f994  mov     ecx, [r12+60h]
0x14000f999  lea     rdx, [r12+60h]
0x14000f99e  cmp     ecx, esi
0x14000f9a0  jb      short loc_14000F9D4
0x14000f9a2  mov     ecx, edi
0x14000f9a4  jmp     short loc_14000F935
0x14000f9a6  cmp     dword ptr [rsp+78h+arg_0], 4
0x14000f9ae  jnz     loc_140039C82
0x14000f9b4  mov     rax, [rsp+78h+arg_30]
0x14000f9bc  mov     ecx, [rax]
0x14000f9be  mov     [r14+2ECh], ecx
0x14000f9c5  jmp     loc_14000F876
0x14000f9ca  mov     ebx, 0C00000C3h
0x14000f9cf  jmp     loc_14000F87F
0x14000f9d4  mov     eax, esi
0x14000f9d6  sub     eax, ecx
0x14000f9d8  mov     ecx, [r14+2E8h]
0x14000f9df  cmp     ecx, eax
0x14000f9e1  cmovnb  ecx, eax
0x14000f9e4  jmp     loc_14000F935
0x14000f9e9  mov     ebp, 0C0000016h
0x14000f9ee  mov     esi, r10d
0x14000f9f1  jmp     loc_14000F87F
0x140039c82  mov     [r14+2ECh], edi
0x140039c89  jmp     loc_14000F876
```
