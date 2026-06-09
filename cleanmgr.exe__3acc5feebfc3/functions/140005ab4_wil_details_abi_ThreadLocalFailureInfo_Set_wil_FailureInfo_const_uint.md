# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005ab4`
- end: `0x140005bea`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140005e4c`

## callees

- `0x140003390`
- `0x140003c2c`
- `0x140003ca4`
- `0x1400056d8`
- `0x140005948`
- `0x140005968`
- `0x140005ab4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b71`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
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
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x140005ab4  push    rbx
0x140005ab6  push    rbp
0x140005ab7  push    rsi
0x140005ab8  push    rdi
0x140005ab9  push    r12
0x140005abb  push    r13
0x140005abd  push    r14
0x140005abf  push    r15
0x140005ac1  sub     rsp, 28h
0x140005ac5  mov     [rcx+4], r8d
0x140005ac9  lea     r14, [rcx+38h]
0x140005acd  mov     eax, [rdx+8]
0x140005ad0  mov     rsi, rcx
0x140005ad3  mov     [rcx+8], eax
0x140005ad6  mov     r15, rdx
0x140005ad9  mov     qword ptr [rcx+10h], 0
0x140005ae1  movzx   eax, word ptr [rdx+40h]
0x140005ae5  mov     [rcx+18h], ax
0x140005ae9  mov     al, [rdx]
0x140005aeb  mov     [rcx+1Ah], al
0x140005aee  mov     qword ptr [rcx+20h], 0
0x140005af6  mov     rax, [rdx+88h]
0x140005afd  mov     [rcx+28h], rax
0x140005b01  mov     rax, [rdx+90h]
0x140005b08  mov     [rcx+30h], rax
0x140005b0c  mov     qword ptr [r14], 0
0x140005b13  mov     rcx, [rdx+18h]; this
0x140005b17  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140005b1c  mov     rcx, [r15+38h]; this
0x140005b20  mov     rbp, rax
0x140005b23  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140005b28  mov     rcx, [r15+80h]; this
0x140005b2f  add     rbp, rax
0x140005b32  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140005b37  add     rbp, rax
0x140005b3a  lea     rdi, [rsi+48h]
0x140005b3e  cmp     qword ptr [rsi+40h], 0
0x140005b43  jz      short loc_140005B4A
0x140005b45  cmp     [rdi], rbp
0x140005b48  jnb     short loc_140005B82
0x140005b4a  mov     rdx, rbp; dwBytes
0x140005b4d  mov     ecx, 8; dwFlags
0x140005b52  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005b57  mov     r14, rax
0x140005b5a  test    rax, rax
0x140005b5d  jz      short loc_140005B7E
0x140005b5f  mov     rbx, [rsi+40h]
0x140005b63  call    cs:__imp_GetProcessHeap
0x140005b69  mov     r8, rbx; lpMem
0x140005b6c  xor     edx, edx; dwFlags
0x140005b6e  mov     rcx, rax; hHeap
0x140005b71  call    cs:__imp_HeapFree
0x140005b77  mov     [rsi+40h], r14
0x140005b7b  mov     [rdi], rbp
0x140005b7e  lea     r14, [rsi+38h]
0x140005b82  mov     rcx, [rsi+40h]; Destination
0x140005b86  test    rcx, rcx
0x140005b89  jz      short loc_140005BD9
0x140005b8b  mov     rbx, [rdi]
0x140005b8e  lea     r9, [rsi+10h]
0x140005b92  mov     r8, [r15+38h]
0x140005b96  add     rbx, rcx
0x140005b99  mov     rdx, rbx
0x140005b9c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005ba1  mov     r8, [r15+80h]
0x140005ba8  lea     r9, [rsi+20h]
0x140005bac  mov     rdx, rbx
0x140005baf  mov     rcx, rax; Destination
0x140005bb2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005bb7  mov     r8, [r15+18h]
0x140005bbb  mov     r9, r14
0x140005bbe  mov     rdx, rbx
0x140005bc1  mov     rcx, rax; Destination
0x140005bc4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140005bc9  sub     rbx, rax
0x140005bcc  xor     edx, edx; Val
0x140005bce  mov     r8, rbx; Size
0x140005bd1  mov     rcx, rax; void *
0x140005bd4  call    memset_0
0x140005bd9  add     rsp, 28h
0x140005bdd  pop     r15
0x140005bdf  pop     r14
0x140005be1  pop     r13
0x140005be3  pop     r12
0x140005be5  pop     rdi
0x140005be6  pop     rsi
0x140005be7  pop     rbp
0x140005be8  pop     rbx
0x140005be9  retn
```
