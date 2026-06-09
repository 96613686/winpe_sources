# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006f10`
- end: `0x180007046`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007394`

## callees

- `0x180002fd8`
- `0x180003050`
- `0x1800060a0`
- `0x180006d80`
- `0x180006da0`
- `0x180006f10`
- `0x18002737e`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180006fbf`
- `KERNEL32!GetProcessHeap` at `0x180006fbf`
- `KERNEL32!HeapFree` at `0x180006fcd`
- `KERNEL32!HeapFree` at `0x180006fcd`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x180006f10  push    rbx
0x180006f12  push    rbp
0x180006f13  push    rsi
0x180006f14  push    rdi
0x180006f15  push    r12
0x180006f17  push    r13
0x180006f19  push    r14
0x180006f1b  push    r15
0x180006f1d  sub     rsp, 28h
0x180006f21  mov     [rcx+4], r8d
0x180006f25  lea     r14, [rcx+38h]
0x180006f29  mov     eax, [rdx+8]
0x180006f2c  mov     rsi, rcx
0x180006f2f  mov     [rcx+8], eax
0x180006f32  mov     r15, rdx
0x180006f35  mov     qword ptr [rcx+10h], 0
0x180006f3d  movzx   eax, word ptr [rdx+40h]
0x180006f41  mov     [rcx+18h], ax
0x180006f45  mov     al, [rdx]
0x180006f47  mov     [rcx+1Ah], al
0x180006f4a  mov     qword ptr [rcx+20h], 0
0x180006f52  mov     rax, [rdx+88h]
0x180006f59  mov     [rcx+28h], rax
0x180006f5d  mov     rax, [rdx+90h]
0x180006f64  mov     [rcx+30h], rax
0x180006f68  mov     qword ptr [r14], 0
0x180006f6f  mov     rcx, [rdx+18h]; this
0x180006f73  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180006f78  mov     rcx, [r15+38h]; this
0x180006f7c  mov     rbp, rax
0x180006f7f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006f84  mov     rcx, [r15+80h]; this
0x180006f8b  add     rbp, rax
0x180006f8e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006f93  add     rbp, rax
0x180006f96  lea     rdi, [rsi+48h]
0x180006f9a  cmp     qword ptr [rsi+40h], 0
0x180006f9f  jz      short loc_180006FA6
0x180006fa1  cmp     [rdi], rbp
0x180006fa4  jnb     short loc_180006FDE
0x180006fa6  mov     rdx, rbp; dwBytes
0x180006fa9  mov     ecx, 8; dwFlags
0x180006fae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006fb3  mov     r14, rax
0x180006fb6  test    rax, rax
0x180006fb9  jz      short loc_180006FDA
0x180006fbb  mov     rbx, [rsi+40h]
0x180006fbf  call    cs:__imp_GetProcessHeap
0x180006fc5  mov     r8, rbx; lpMem
0x180006fc8  xor     edx, edx; dwFlags
0x180006fca  mov     rcx, rax; hHeap
0x180006fcd  call    cs:__imp_HeapFree
0x180006fd3  mov     [rsi+40h], r14
0x180006fd7  mov     [rdi], rbp
0x180006fda  lea     r14, [rsi+38h]
0x180006fde  mov     rcx, [rsi+40h]; Destination
0x180006fe2  test    rcx, rcx
0x180006fe5  jz      short loc_180007035
0x180006fe7  mov     rbx, [rdi]
0x180006fea  lea     r9, [rsi+10h]
0x180006fee  mov     r8, [r15+38h]
0x180006ff2  add     rbx, rcx
0x180006ff5  mov     rdx, rbx
0x180006ff8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006ffd  mov     r8, [r15+80h]
0x180007004  lea     r9, [rsi+20h]
0x180007008  mov     rdx, rbx
0x18000700b  mov     rcx, rax; Destination
0x18000700e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007013  mov     r8, [r15+18h]
0x180007017  mov     r9, r14
0x18000701a  mov     rdx, rbx
0x18000701d  mov     rcx, rax; Destination
0x180007020  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180007025  sub     rbx, rax
0x180007028  xor     edx, edx; Val
0x18000702a  mov     r8, rbx; Size
0x18000702d  mov     rcx, rax; void *
0x180007030  call    memset_0
0x180007035  add     rsp, 28h
0x180007039  pop     r15
0x18000703b  pop     r14
0x18000703d  pop     r13
0x18000703f  pop     r12
0x180007041  pop     rdi
0x180007042  pop     rsi
0x180007043  pop     rbp
0x180007044  pop     rbx
0x180007045  retn
```
