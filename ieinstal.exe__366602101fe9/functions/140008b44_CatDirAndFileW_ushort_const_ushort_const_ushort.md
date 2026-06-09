# CatDirAndFileW(ushort const *,ushort const *,ushort * *)

- ea: `0x140008b44`
- end: `0x140008c6e`
- name: `?CatDirAndFileW@@YAHPEBG0PEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140004e20`

## callees

- `0x140001af3`
- `0x140008a0c`
- `0x140008b44`
- `0x14000b150`
- `0x14000bc68`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140008bcd`
- `ole32!CoTaskMemAlloc` at `0x140008bcd`
- `ole32!CoTaskMemFree` at `0x140008c21`
- `ole32!CoTaskMemFree` at `0x140008c35`
- `ole32!CoTaskMemFree` at `0x140008c49`
- `ole32!CoTaskMemFree` at `0x140008c21`
- `ole32!CoTaskMemFree` at `0x140008c35`
- `ole32!CoTaskMemFree` at `0x140008c49`

## pseudocode

```c
__int64 __fastcall CatDirAndFileW(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v3; // r14d
  char *v4; // rdi
  char *v5; // rbx
  char *v6; // rsi
  __int64 v7; // rbp
  int v9; // r15d
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebp
  char *v15; // rax
  unsigned int v16; // ecx
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  char *v19; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  pv = 0;
  v6 = 0;
  v19 = 0;
  v7 = -1;
  v9 = 2;
  if ( a1 )
  {
    v11 = WSZtoSZ((unsigned int)a1, a1, (char **)&pv);
    v4 = (char *)pv;
    if ( v11 < 0 )
      goto LABEL_12;
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)pv + v12) );
    v9 = v12 + 2;
  }
  v13 = WSZtoSZ((unsigned int)a1, a2, &v19);
  v5 = v19;
  if ( v13 >= 0 )
  {
    do
      ++v7;
    while ( v19[v7] );
    v14 = v9 + v7;
    v15 = (char *)CoTaskMemAlloc(v14);
    v6 = v15;
    if ( v15 )
    {
      memset_0(v15, 0, v14);
      if ( (unsigned int)CatDirAndFileA(v4, v5, v14, v6) )
      {
        if ( SZtoWSZ(v16, v6, a3) >= 0 )
          v3 = 1;
      }
    }
  }
LABEL_12:
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v6 )
    CoTaskMemFree(v6);
  return v3;
}

```

## disassembly

```asm
0x140008b44  mov     rax, rsp
0x140008b47  mov     [rax+10h], rbx
0x140008b4b  push    rbp
0x140008b4c  push    rsi
0x140008b4d  push    rdi
0x140008b4e  push    r12
0x140008b50  push    r13
0x140008b52  push    r14
0x140008b54  push    r15
0x140008b56  sub     rsp, 20h
0x140008b5a  xor     r14d, r14d
0x140008b5d  xor     edi, edi
0x140008b5f  xor     ebx, ebx
0x140008b61  mov     [rax+8], rdi
0x140008b65  xor     esi, esi
0x140008b67  mov     [rax+20h], rbx
0x140008b6b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140008b6f  mov     r13, r8
0x140008b72  lea     r15d, [r14+2]
0x140008b76  mov     r12, rdx
0x140008b79  test    rcx, rcx
0x140008b7c  jz      short loc_140008BA6
0x140008b7e  lea     r8, [rax+8]; char **
0x140008b82  mov     rdx, rcx; unsigned __int16 *
0x140008b85  call    ?WSZtoSZ@@YAJIPEBGPEAPEAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x140008b8a  mov     rdi, [rsp+58h+pv]
0x140008b8f  test    eax, eax
0x140008b91  js      loc_140008C19
0x140008b97  mov     rax, rbp
0x140008b9a  inc     rax
0x140008b9d  cmp     [rdi+rax], bl
0x140008ba0  jnz     short loc_140008B9A
0x140008ba2  lea     r15d, [rax+2]
0x140008ba6  lea     r8, [rsp+58h+arg_18]; char **
0x140008bab  mov     rdx, r12; unsigned __int16 *
0x140008bae  call    ?WSZtoSZ@@YAJIPEBGPEAPEAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x140008bb3  mov     rbx, [rsp+58h+arg_18]
0x140008bb8  test    eax, eax
0x140008bba  js      short loc_140008C19
0x140008bbc  inc     rbp
0x140008bbf  cmp     [rbx+rbp], sil
0x140008bc3  jnz     short loc_140008BBC
0x140008bc5  add     ebp, r15d
0x140008bc8  mov     ecx, ebp; cb
0x140008bca  mov     r15d, ebp
0x140008bcd  call    cs:__imp_CoTaskMemAlloc
0x140008bd4  nop     dword ptr [rax+rax+00h]
0x140008bd9  mov     rsi, rax
0x140008bdc  test    rax, rax
0x140008bdf  jz      short loc_140008C19
0x140008be1  mov     r8d, r15d; Size
0x140008be4  xor     edx, edx; Val
0x140008be6  mov     rcx, rax; void *
0x140008be9  call    memset_0
0x140008bee  mov     r9, rsi; char *
0x140008bf1  mov     r8d, ebp; unsigned int
0x140008bf4  mov     rdx, rbx; char *
0x140008bf7  mov     rcx, rdi; char *
0x140008bfa  call    ?CatDirAndFileA@@YAHPEBD0KPEAD@Z; CatDirAndFileA(char const *,char const *,ulong,char *)
0x140008bff  test    eax, eax
0x140008c01  jz      short loc_140008C19
0x140008c03  mov     r8, r13; unsigned __int16 **
0x140008c06  mov     rdx, rsi; char *
0x140008c09  call    ?SZtoWSZ@@YAJIPEBDPEAPEAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x140008c0e  test    eax, eax
0x140008c10  mov     ecx, 1
0x140008c15  cmovns  r14d, ecx
0x140008c19  test    rdi, rdi
0x140008c1c  jz      short loc_140008C2D
0x140008c1e  mov     rcx, rdi; pv
0x140008c21  call    cs:__imp_CoTaskMemFree
0x140008c28  nop     dword ptr [rax+rax+00h]
0x140008c2d  test    rbx, rbx
0x140008c30  jz      short loc_140008C41
0x140008c32  mov     rcx, rbx; pv
0x140008c35  call    cs:__imp_CoTaskMemFree
0x140008c3c  nop     dword ptr [rax+rax+00h]
0x140008c41  test    rsi, rsi
0x140008c44  jz      short loc_140008C55
0x140008c46  mov     rcx, rsi; pv
0x140008c49  call    cs:__imp_CoTaskMemFree
0x140008c50  nop     dword ptr [rax+rax+00h]
0x140008c55  mov     rbx, [rsp+58h+arg_8]
0x140008c5a  mov     eax, r14d
0x140008c5d  add     rsp, 20h
0x140008c61  pop     r15
0x140008c63  pop     r14
0x140008c65  pop     r13
0x140008c67  pop     r12
0x140008c69  pop     rdi
0x140008c6a  pop     rsi
0x140008c6b  pop     rbp
0x140008c6c  retn
```
