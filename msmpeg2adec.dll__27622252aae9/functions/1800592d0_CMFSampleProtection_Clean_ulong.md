# CMFSampleProtection::Clean(ulong)

- ea: `0x1800592d0`
- end: `0x180059430`
- name: `?Clean@CMFSampleProtection@@QEAAJK@Z`
- size: `352`
- prototype: `__int64 __fastcall(CMFSampleProtection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059170`
- `0x1800598f0`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x180054fe4`
- `0x1800592d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800593ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800593ef`

## pseudocode

```c
__int64 __fastcall CMFSampleProtection::Clean(CMFSampleProtection *this, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rdx
  char *i; // r10
  char v9; // cl
  char v10; // al
  _BYTE *v11; // r8
  _BYTE *v12; // r9
  unsigned __int8 j; // al
  __int64 v14; // rcx
  _DWORD v15[4]; // [rsp+20h] [rbp-138h]
  _BYTE v16[272]; // [rsp+30h] [rbp-128h] BYREF

  v2 = a2;
  memset_0(v16, 0, sizeof(v16));
  if ( (unsigned int)v2 >= 0x10 )
    return 2147942487LL;
  if ( *((_QWORD *)this + v2 + 50) )
  {
    SymCryptRc4Init(v16, (char *)this + 36, 20);
    v5 = v16[256];
    LOBYTE(v6) = v16[257];
    v7 = (char *)this + 4 * v2 + 528;
    for ( i = v7 + 4; v7 < i; v5 = (unsigned __int8)(v5 + 1) )
    {
      v9 = v16[v5];
      v6 = (unsigned __int8)(v9 + v6);
      v10 = v16[v6];
      v16[v5] = v10;
      v16[v6] = v9;
      *v7++ ^= v16[(unsigned __int8)(v9 + v10)];
    }
    v11 = (_BYTE *)*((_QWORD *)this + v2 + 50);
    v15[0] = -1749680893;
    if ( v11 )
    {
      v12 = &v11[*((unsigned int *)this + v2 + 132)];
      if ( v12 >= v11 )
      {
        for ( j = 0; v11 < v12; ++v11 )
        {
          v14 = j;
          j = (j + 1) & 3;
          *v11 = *((_BYTE *)v15 + v14);
        }
      }
    }
    CoTaskMemFree(*((LPVOID *)this + v2 + 50));
    *((_DWORD *)this + v2 + 132) = 0;
    *((_QWORD *)this + v2 + 50) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800592d0  mov     [rsp+arg_10], rbx
0x1800592d5  push    rdi
0x1800592d6  sub     rsp, 150h
0x1800592dd  mov     rax, cs:__security_cookie
0x1800592e4  xor     rax, rsp
0x1800592e7  mov     [rsp+158h+var_18], rax
0x1800592ef  mov     edi, edx
0x1800592f1  mov     rbx, rcx
0x1800592f4  xor     edx, edx; Val
0x1800592f6  lea     rcx, [rsp+158h+var_128]; void *
0x1800592fb  mov     r8d, 110h; Size
0x180059301  call    memset_0
0x180059306  cmp     edi, 10h
0x180059309  jb      short loc_180059315
0x18005930b  mov     eax, 80070057h
0x180059310  jmp     loc_18005940E
0x180059315  cmp     qword ptr [rbx+rdi*8+190h], 0
0x18005931e  jz      loc_18005940C
0x180059324  lea     rdx, [rbx+24h]
0x180059328  mov     r8d, 14h
0x18005932e  lea     rcx, [rsp+158h+var_128]
0x180059333  call    SymCryptRc4Init
0x180059338  movzx   r8d, [rsp+158h+var_28]
0x180059341  lea     rdx, [rbx+210h]
0x180059348  movzx   r9d, [rsp+158h+var_27]
0x180059351  lea     rdx, [rdx+rdi*4]
0x180059355  lea     r10, [rdx+4]
0x180059359  cmp     rdx, r10
0x18005935c  jnb     short loc_18005939B
0x18005935e  xchg    ax, ax
0x180059360  movzx   ecx, [rsp+r8+158h+var_128]
0x180059366  lea     rax, [rcx+r9]
0x18005936a  movzx   r9d, al
0x18005936e  movzx   eax, [rsp+r9+158h+var_128]
0x180059374  mov     [rsp+r8+158h+var_128], al
0x180059379  add     rax, rcx
0x18005937c  movzx   eax, al
0x18005937f  mov     [rsp+r9+158h+var_128], cl
0x180059384  movzx   ecx, [rsp+rax+158h+var_128]
0x180059389  lea     rax, [r8+1]
0x18005938d  xor     [rdx], cl
0x18005938f  inc     rdx
0x180059392  movzx   r8d, al
0x180059396  cmp     rdx, r10
0x180059399  jb      short loc_180059360
0x18005939b  mov     r8, [rbx+rdi*8+190h]
0x1800593a3  mov     [rsp+158h+var_138], 97B5FD03h
0x1800593ab  test    r8, r8
0x1800593ae  jz      short loc_1800593E7
0x1800593b0  mov     r9d, [rbx+rdi*4+210h]
0x1800593b8  add     r9, r8
0x1800593bb  cmp     r9, r8
0x1800593be  jb      short loc_1800593E7
0x1800593c0  xor     al, al
0x1800593c2  cmp     r8, r9
0x1800593c5  jnb     short loc_1800593E7
0x1800593c7  nop     word ptr [rax+rax+00000000h]
0x1800593d0  movzx   ecx, al
0x1800593d3  inc     al
0x1800593d5  and     al, 3
0x1800593d7  movzx   edx, byte ptr [rsp+rcx+158h+var_138]
0x1800593dc  mov     [r8], dl
0x1800593df  inc     r8
0x1800593e2  cmp     r8, r9
0x1800593e5  jb      short loc_1800593D0
0x1800593e7  mov     rcx, [rbx+rdi*8+190h]; pv
0x1800593ef  call    cs:__imp_CoTaskMemFree
0x1800593f6  nop     dword ptr [rax+rax+00h]
0x1800593fb  xor     eax, eax
0x1800593fd  mov     [rbx+rdi*4+210h], eax
0x180059404  mov     [rbx+rdi*8+190h], rax
0x18005940c  xor     eax, eax
0x18005940e  mov     rcx, [rsp+158h+var_18]
0x180059416  xor     rcx, rsp; StackCookie
0x180059419  call    __security_check_cookie
0x18005941e  mov     rbx, [rsp+158h+arg_10]
0x180059426  add     rsp, 150h
0x18005942d  pop     rdi
0x18005942e  retn
```
