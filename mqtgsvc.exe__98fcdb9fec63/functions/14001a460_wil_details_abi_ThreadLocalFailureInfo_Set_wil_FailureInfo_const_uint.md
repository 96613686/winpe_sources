# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14001a460`
- end: `0x14001a58c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `300`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001a924`

## callees

- `0x1400169fc`
- `0x140016a84`
- `0x140019514`
- `0x14001a2c8`
- `0x14001a2f0`
- `0x14001a460`
- `0x14001ceda`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001a513`
- `KERNEL32!HeapFree` at `0x14001a513`
- `KERNEL32!GetProcessHeap` at `0x14001a505`
- `KERNEL32!GetProcessHeap` at `0x14001a505`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  wchar_t **v5; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const wchar_t *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  char *v18; // rax
  wchar_t *v19; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  v5 = (wchar_t **)((char *)this + 56);
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), (const char *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
    v5 = (wchar_t **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = wil::details::WriteResultString<char const *>(v17, v16, *((wil::details **)a2 + 16), (char **)this + 4);
    v19 = wil::details::WriteResultString<wchar_t const *>(
            (wchar_t *)v18,
            (const wchar_t *)v16,
            *((wil::details **)a2 + 3),
            v5);
    memset_0(v19, 0, v16 - (const char *)v19);
  }
}

```

## disassembly

```asm
0x14001a460  push    rbx
0x14001a462  push    rbp
0x14001a463  push    rsi
0x14001a464  push    rdi
0x14001a465  push    r12
0x14001a467  push    r13
0x14001a469  push    r14
0x14001a46b  push    r15
0x14001a46d  sub     rsp, 28h
0x14001a471  mov     rsi, rcx
0x14001a474  mov     [rcx+4], r8d
0x14001a478  mov     eax, [rdx+8]
0x14001a47b  mov     r15, rdx
0x14001a47e  mov     [rcx+8], eax
0x14001a481  xor     ecx, ecx
0x14001a483  mov     [rsi+10h], rcx
0x14001a487  lea     r14, [rsi+38h]
0x14001a48b  movzx   eax, word ptr [rdx+40h]
0x14001a48f  mov     [rsi+18h], ax
0x14001a493  mov     al, [rdx]
0x14001a495  mov     [rsi+1Ah], al
0x14001a498  mov     [rsi+20h], rcx
0x14001a49c  mov     rax, [rdx+88h]
0x14001a4a3  mov     [rsi+28h], rax
0x14001a4a7  mov     rax, [rdx+90h]
0x14001a4ae  mov     [rsi+30h], rax
0x14001a4b2  mov     [r14], rcx
0x14001a4b5  mov     rcx, [rdx+80h]; this
0x14001a4bc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14001a4c1  mov     rcx, [r15+38h]; this
0x14001a4c5  mov     rbp, rax
0x14001a4c8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14001a4cd  mov     rcx, [r15+18h]; this
0x14001a4d1  add     rbp, rax
0x14001a4d4  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x14001a4d9  add     rbp, rax
0x14001a4dc  lea     rdi, [rsi+48h]
0x14001a4e0  cmp     qword ptr [rsi+40h], 0
0x14001a4e5  jz      short loc_14001A4EC
0x14001a4e7  cmp     [rdi], rbp
0x14001a4ea  jnb     short loc_14001A524
0x14001a4ec  mov     rdx, rbp; dwBytes
0x14001a4ef  mov     ecx, 8; dwFlags
0x14001a4f4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001a4f9  mov     r14, rax
0x14001a4fc  test    rax, rax
0x14001a4ff  jz      short loc_14001A520
0x14001a501  mov     rbx, [rsi+40h]
0x14001a505  call    cs:__imp_GetProcessHeap
0x14001a50b  mov     r8, rbx; lpMem
0x14001a50e  xor     edx, edx; dwFlags
0x14001a510  mov     rcx, rax; hHeap
0x14001a513  call    cs:__imp_HeapFree
0x14001a519  mov     [rsi+40h], r14
0x14001a51d  mov     [rdi], rbp
0x14001a520  lea     r14, [rsi+38h]
0x14001a524  mov     rcx, [rsi+40h]; Destination
0x14001a528  test    rcx, rcx
0x14001a52b  jz      short loc_14001A57B
0x14001a52d  mov     rbx, [rdi]
0x14001a530  lea     r9, [rsi+10h]
0x14001a534  mov     r8, [r15+38h]
0x14001a538  add     rbx, rcx
0x14001a53b  mov     rdx, rbx
0x14001a53e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14001a543  mov     r8, [r15+80h]
0x14001a54a  lea     r9, [rsi+20h]
0x14001a54e  mov     rdx, rbx
0x14001a551  mov     rcx, rax; Destination
0x14001a554  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14001a559  mov     r8, [r15+18h]
0x14001a55d  mov     r9, r14
0x14001a560  mov     rdx, rbx
0x14001a563  mov     rcx, rax; Destination
0x14001a566  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x14001a56b  sub     rbx, rax
0x14001a56e  xor     edx, edx; Val
0x14001a570  mov     r8, rbx; Size
0x14001a573  mov     rcx, rax; void *
0x14001a576  call    memset_0
0x14001a57b  add     rsp, 28h
0x14001a57f  pop     r15
0x14001a581  pop     r14
0x14001a583  pop     r13
0x14001a585  pop     r12
0x14001a587  pop     rdi
0x14001a588  pop     rsi
0x14001a589  pop     rbp
0x14001a58a  pop     rbx
0x14001a58b  retn
```
