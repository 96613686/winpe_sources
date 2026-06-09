# NpCommonQueryVolumeInformation

- ea: `0x1400163d8`
- end: `0x1400164f0`
- name: `NpCommonQueryVolumeInformation`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140016390`

## callees

- `0x140001f40`
- `0x1400163d8`
- `0x1400164f8`

## pseudocode

```c
__int64 __fastcall NpCommonQueryVolumeInformation(_QWORD *a1)
{
  __int64 v1; // rsi
  __int64 v3; // rcx
  int v4; // edx
  unsigned int v5; // edi
  int v6; // edx
  unsigned int v7; // eax
  unsigned int v8; // edx
  __int64 result; // rax
  int v10; // edx
  int v11; // edx
  int v12; // edx
  unsigned int v13; // ebx
  size_t v14; // r8
  unsigned int v15; // [rsp+40h] [rbp+8h] BYREF

  v1 = a1[23];
  v3 = a1[3];
  v4 = *(_DWORD *)(v1 + 16);
  v5 = *(_DWORD *)(v1 + 8);
  v15 = v5;
  v6 = v4 - 1;
  if ( !v6 )
  {
    v7 = NpQueryFsVolumeInfo(v3, &v15);
    v5 = v15;
    v8 = v7;
    goto LABEL_3;
  }
  v10 = v6 - 2;
  if ( !v10 )
  {
    v8 = 0;
    *(_QWORD *)v3 = 0;
    v5 -= 24;
    *(_QWORD *)(v3 + 8) = 0;
    *(_DWORD *)(v3 + 16) = 1;
    *(_DWORD *)(v3 + 20) = 1;
    goto LABEL_3;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( v5 < 8 )
    {
      v8 = -2147483643;
      goto LABEL_3;
    }
    *(_QWORD *)v3 = 0;
    v5 -= 8;
    *(_DWORD *)v3 = 17;
    goto LABEL_17;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 != 2 )
    {
      v8 = -1073741637;
      goto LABEL_3;
    }
    v5 -= 32;
    *(_OWORD *)v3 = 0;
    *(_OWORD *)(v3 + 16) = 0;
LABEL_17:
    v8 = 0;
    goto LABEL_3;
  }
  v13 = v5 - 12;
  *(_DWORD *)v3 = 2;
  *(_DWORD *)(v3 + 4) = -1;
  *(_DWORD *)(v3 + 8) = 8;
  v14 = v5 - 12;
  v5 -= 20;
  if ( v13 < 8 )
    v5 = 0;
  else
    v14 = 8;
  memmove((void *)(v3 + 12), L"NPFS", v14);
  v8 = v13 < 8 ? 0x80000005 : 0;
LABEL_3:
  result = v8;
  a1[7] = *(_DWORD *)(v1 + 8) - v5;
  return result;
}

```

## disassembly

```asm
0x1400163d8  mov     rax, rsp
0x1400163db  mov     [rax+10h], rbx
0x1400163df  mov     [rax+18h], rbp
0x1400163e3  push    rsi
0x1400163e4  push    rdi
0x1400163e5  push    r14
0x1400163e7  sub     rsp, 20h
0x1400163eb  mov     rsi, [rcx+0B8h]
0x1400163f2  mov     r14, rcx
0x1400163f5  mov     rcx, [rcx+18h]
0x1400163f9  mov     edx, [rsi+10h]
0x1400163fc  mov     edi, [rsi+8]
0x1400163ff  mov     [rax+8], edi
0x140016402  sub     edx, 1
0x140016405  jnz     short loc_140016435
0x140016407  lea     rdx, [rax+8]
0x14001640b  call    NpQueryFsVolumeInfo
0x140016410  mov     edi, [rsp+38h+arg_0]
0x140016414  mov     edx, eax
0x140016416  mov     ecx, [rsi+8]
0x140016419  mov     eax, edx
0x14001641b  mov     rbx, [rsp+38h+arg_8]
0x140016420  sub     ecx, edi
0x140016422  mov     rbp, [rsp+38h+arg_10]
0x140016427  mov     [r14+38h], rcx
0x14001642b  add     rsp, 20h
0x14001642f  pop     r14
0x140016431  pop     rdi
0x140016432  pop     rsi
0x140016433  retn
0x140016435  sub     edx, 2
0x140016438  jz      loc_1400164D6
0x14001643e  sub     edx, 1
0x140016441  jz      short loc_1400164AE
0x140016443  sub     edx, 1
0x140016446  jz      short loc_140016463
0x140016448  cmp     edx, 2
0x14001644b  jz      short loc_140016454
0x14001644d  mov     edx, 0C00000BBh
0x140016452  jmp     short loc_140016416
0x140016454  xorps   xmm0, xmm0
0x140016457  add     edi, 0FFFFFFE0h
0x14001645a  movups  xmmword ptr [rcx], xmm0
0x14001645d  movups  xmmword ptr [rcx+10h], xmm0
0x140016461  jmp     short loc_1400164CF
0x140016463  lea     ebx, [rdi-0Ch]
0x140016466  mov     dword ptr [rcx], 2
0x14001646c  mov     ebp, 8
0x140016471  mov     dword ptr [rcx+4], 0FFFFFFFFh
0x140016478  cmp     ebx, ebp
0x14001647a  mov     [rcx+8], ebp
0x14001647d  mov     r8d, ebx
0x140016480  lea     edi, [rbx-8]
0x140016483  cmovnb  r8d, ebp; Size
0x140016487  xor     edx, edx
0x140016489  cmp     ebx, ebp
0x14001648b  cmovb   edi, edx
0x14001648e  add     rcx, 0Ch; void *
0x140016492  lea     rdx, aNpfs; "NPFS"
0x140016499  call    memmove
0x14001649e  cmp     ebx, ebp
0x1400164a0  mov     edx, 80000005h
0x1400164a5  sbb     eax, eax
0x1400164a7  and     edx, eax
0x1400164a9  jmp     loc_140016416
0x1400164ae  mov     ebp, 8
0x1400164b3  cmp     edi, ebp
0x1400164b5  jnb     short loc_1400164C1
0x1400164b7  mov     edx, 80000005h
0x1400164bc  jmp     loc_140016416
0x1400164c1  xor     eax, eax
0x1400164c3  mov     [rcx], rax
0x1400164c6  add     edi, 0FFFFFFF8h
0x1400164c9  mov     dword ptr [rcx], 11h
0x1400164cf  xor     edx, edx
0x1400164d1  jmp     loc_140016416
0x1400164d6  xor     edx, edx
0x1400164d8  mov     [rcx], rdx
0x1400164db  add     edi, 0FFFFFFE8h
0x1400164de  mov     [rcx+8], rdx
0x1400164e2  lea     eax, [rdx+1]
0x1400164e5  mov     [rcx+10h], eax
0x1400164e8  mov     [rcx+14h], eax
0x1400164eb  jmp     loc_140016416
```
