# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006900`
- end: `0x180006a2c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `300`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006dc4`

## callees

- `0x18000315c`
- `0x1800031e4`
- `0x180005c38`
- `0x180006768`
- `0x180006790`
- `0x180006900`
- `0x180023c5a`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800069a5`
- `KERNEL32!GetProcessHeap` at `0x1800069a5`
- `KERNEL32!HeapFree` at `0x1800069b3`
- `KERNEL32!HeapFree` at `0x1800069b3`

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
  const wchar_t *v8; // rdx
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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), (const char *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), v8) + v7;
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x180006900  push    rbx
0x180006902  push    rbp
0x180006903  push    rsi
0x180006904  push    rdi
0x180006905  push    r12
0x180006907  push    r13
0x180006909  push    r14
0x18000690b  push    r15
0x18000690d  sub     rsp, 28h
0x180006911  mov     rsi, rcx
0x180006914  mov     [rcx+4], r8d
0x180006918  mov     eax, [rdx+8]
0x18000691b  mov     r15, rdx
0x18000691e  mov     [rcx+8], eax
0x180006921  xor     ecx, ecx
0x180006923  mov     [rsi+10h], rcx
0x180006927  lea     r14, [rsi+38h]
0x18000692b  movzx   eax, word ptr [rdx+40h]
0x18000692f  mov     [rsi+18h], ax
0x180006933  mov     al, [rdx]
0x180006935  mov     [rsi+1Ah], al
0x180006938  mov     [rsi+20h], rcx
0x18000693c  mov     rax, [rdx+88h]
0x180006943  mov     [rsi+28h], rax
0x180006947  mov     rax, [rdx+90h]
0x18000694e  mov     [rsi+30h], rax
0x180006952  mov     [r14], rcx
0x180006955  mov     rcx, [rdx+80h]; this
0x18000695c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006961  mov     rcx, [r15+38h]; this
0x180006965  mov     rbp, rax
0x180006968  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000696d  mov     rcx, [r15+18h]; this
0x180006971  add     rbp, rax
0x180006974  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180006979  add     rbp, rax
0x18000697c  lea     rdi, [rsi+48h]
0x180006980  cmp     qword ptr [rsi+40h], 0
0x180006985  jz      short loc_18000698C
0x180006987  cmp     [rdi], rbp
0x18000698a  jnb     short loc_1800069C4
0x18000698c  mov     rdx, rbp; dwBytes
0x18000698f  mov     ecx, 8; dwFlags
0x180006994  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006999  mov     r14, rax
0x18000699c  test    rax, rax
0x18000699f  jz      short loc_1800069C0
0x1800069a1  mov     rbx, [rsi+40h]
0x1800069a5  call    cs:__imp_GetProcessHeap
0x1800069ab  mov     r8, rbx; lpMem
0x1800069ae  xor     edx, edx; dwFlags
0x1800069b0  mov     rcx, rax; hHeap
0x1800069b3  call    cs:__imp_HeapFree
0x1800069b9  mov     [rsi+40h], r14
0x1800069bd  mov     [rdi], rbp
0x1800069c0  lea     r14, [rsi+38h]
0x1800069c4  mov     rcx, [rsi+40h]; Destination
0x1800069c8  test    rcx, rcx
0x1800069cb  jz      short loc_180006A1B
0x1800069cd  mov     rbx, [rdi]
0x1800069d0  lea     r9, [rsi+10h]
0x1800069d4  mov     r8, [r15+38h]
0x1800069d8  add     rbx, rcx
0x1800069db  mov     rdx, rbx
0x1800069de  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800069e3  mov     r8, [r15+80h]
0x1800069ea  lea     r9, [rsi+20h]
0x1800069ee  mov     rdx, rbx
0x1800069f1  mov     rcx, rax; Destination
0x1800069f4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800069f9  mov     r8, [r15+18h]
0x1800069fd  mov     r9, r14
0x180006a00  mov     rdx, rbx
0x180006a03  mov     rcx, rax; Destination
0x180006a06  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180006a0b  sub     rbx, rax
0x180006a0e  xor     edx, edx; Val
0x180006a10  mov     r8, rbx; Size
0x180006a13  mov     rcx, rax; void *
0x180006a16  call    memset_0
0x180006a1b  add     rsp, 28h
0x180006a1f  pop     r15
0x180006a21  pop     r14
0x180006a23  pop     r13
0x180006a25  pop     r12
0x180006a27  pop     rdi
0x180006a28  pop     rsi
0x180006a29  pop     rbp
0x180006a2a  pop     rbx
0x180006a2b  retn
```
