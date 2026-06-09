# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b230`
- end: `0x18000b366`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b6b4`

## callees

- `0x180001f78`
- `0x1800074e4`
- `0x18000755c`
- `0x18000a224`
- `0x18000b09c`
- `0x18000b0bc`
- `0x18000b230`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b2ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b2ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2df`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18000b230  push    rbx
0x18000b232  push    rbp
0x18000b233  push    rsi
0x18000b234  push    rdi
0x18000b235  push    r12
0x18000b237  push    r13
0x18000b239  push    r14
0x18000b23b  push    r15
0x18000b23d  sub     rsp, 28h
0x18000b241  mov     [rcx+4], r8d
0x18000b245  lea     r14, [rcx+38h]
0x18000b249  mov     eax, [rdx+8]
0x18000b24c  mov     rsi, rcx
0x18000b24f  mov     [rcx+8], eax
0x18000b252  mov     r15, rdx
0x18000b255  mov     qword ptr [rcx+10h], 0
0x18000b25d  movzx   eax, word ptr [rdx+40h]
0x18000b261  mov     [rcx+18h], ax
0x18000b265  mov     al, [rdx]
0x18000b267  mov     [rcx+1Ah], al
0x18000b26a  mov     qword ptr [rcx+20h], 0
0x18000b272  mov     rax, [rdx+88h]
0x18000b279  mov     [rcx+28h], rax
0x18000b27d  mov     rax, [rdx+90h]
0x18000b284  mov     [rcx+30h], rax
0x18000b288  mov     qword ptr [r14], 0
0x18000b28f  mov     rcx, [rdx+18h]; this
0x18000b293  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b298  mov     rcx, [r15+38h]; this
0x18000b29c  mov     rbp, rax
0x18000b29f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b2a4  mov     rcx, [r15+80h]; this
0x18000b2ab  add     rbp, rax
0x18000b2ae  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b2b3  add     rbp, rax
0x18000b2b6  lea     rdi, [rsi+48h]
0x18000b2ba  cmp     qword ptr [rsi+40h], 0
0x18000b2bf  jz      short loc_18000B2C6
0x18000b2c1  cmp     [rdi], rbp
0x18000b2c4  jnb     short loc_18000B2FE
0x18000b2c6  mov     rdx, rbp; dwBytes
0x18000b2c9  mov     ecx, 8; dwFlags
0x18000b2ce  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b2d3  mov     r14, rax
0x18000b2d6  test    rax, rax
0x18000b2d9  jz      short loc_18000B2FA
0x18000b2db  mov     rbx, [rsi+40h]
0x18000b2df  call    cs:__imp_GetProcessHeap
0x18000b2e5  mov     r8, rbx; lpMem
0x18000b2e8  xor     edx, edx; dwFlags
0x18000b2ea  mov     rcx, rax; hHeap
0x18000b2ed  call    cs:__imp_HeapFree
0x18000b2f3  mov     [rsi+40h], r14
0x18000b2f7  mov     [rdi], rbp
0x18000b2fa  lea     r14, [rsi+38h]
0x18000b2fe  mov     rcx, [rsi+40h]; Destination
0x18000b302  test    rcx, rcx
0x18000b305  jz      short loc_18000B355
0x18000b307  mov     rbx, [rdi]
0x18000b30a  lea     r9, [rsi+10h]
0x18000b30e  mov     r8, [r15+38h]
0x18000b312  add     rbx, rcx
0x18000b315  mov     rdx, rbx
0x18000b318  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b31d  mov     r8, [r15+80h]
0x18000b324  lea     r9, [rsi+20h]
0x18000b328  mov     rdx, rbx
0x18000b32b  mov     rcx, rax; Destination
0x18000b32e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b333  mov     r8, [r15+18h]
0x18000b337  mov     r9, r14
0x18000b33a  mov     rdx, rbx
0x18000b33d  mov     rcx, rax; Destination
0x18000b340  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000b345  sub     rbx, rax
0x18000b348  xor     edx, edx; Val
0x18000b34a  mov     r8, rbx; Size
0x18000b34d  mov     rcx, rax; void *
0x18000b350  call    memset_0
0x18000b355  add     rsp, 28h
0x18000b359  pop     r15
0x18000b35b  pop     r14
0x18000b35d  pop     r13
0x18000b35f  pop     r12
0x18000b361  pop     rdi
0x18000b362  pop     rsi
0x18000b363  pop     rbp
0x18000b364  pop     rbx
0x18000b365  retn
```
