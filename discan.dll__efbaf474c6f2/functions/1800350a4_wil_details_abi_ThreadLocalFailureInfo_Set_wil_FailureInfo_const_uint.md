# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800350a4`
- end: `0x180035215`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180035308`

## callees

- `0x180031d4c`
- `0x1800343f8`
- `0x180034f24`
- `0x180034f44`
- `0x1800350a4`
- `0x1800375ee`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800351d9`
- `msvcrt!memcpy_s` at `0x1800351d9`
- `KERNEL32!HeapFree` at `0x18003515a`
- `KERNEL32!HeapFree` at `0x18003515a`
- `KERNEL32!GetProcessHeap` at `0x18003514c`
- `KERNEL32!GetProcessHeap` at `0x18003514c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x1800350a4  push    rbx
0x1800350a6  push    rbp
0x1800350a7  push    rsi
0x1800350a8  push    rdi
0x1800350a9  push    r12
0x1800350ab  push    r13
0x1800350ad  push    r14
0x1800350af  push    r15
0x1800350b1  sub     rsp, 28h
0x1800350b5  mov     [rcx+4], r8d
0x1800350b9  lea     rbx, [rcx+20h]
0x1800350bd  mov     eax, [rdx+8]
0x1800350c0  lea     rsi, [rcx+38h]
0x1800350c4  mov     [rcx+8], eax
0x1800350c7  xor     r12d, r12d
0x1800350ca  mov     [rcx+10h], r12
0x1800350ce  mov     rbp, rcx
0x1800350d1  movzx   eax, word ptr [rdx+40h]
0x1800350d5  mov     r14, rdx
0x1800350d8  mov     [rcx+18h], ax
0x1800350dc  mov     al, [rdx]
0x1800350de  mov     [rcx+1Ah], al
0x1800350e1  mov     [rbx], r12
0x1800350e4  mov     rax, [rdx+88h]
0x1800350eb  mov     [rcx+28h], rax
0x1800350ef  mov     rax, [rdx+90h]
0x1800350f6  mov     [rcx+30h], rax
0x1800350fa  mov     [rsi], r12
0x1800350fd  mov     rcx, [rdx+18h]; this
0x180035101  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180035106  mov     rcx, [r14+38h]; this
0x18003510a  mov     r15, rax
0x18003510d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180035112  mov     rcx, [r14+80h]; this
0x180035119  add     r15, rax
0x18003511c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180035121  add     r15, rax
0x180035124  lea     rdi, [rbp+48h]
0x180035128  cmp     [rbp+40h], r12
0x18003512c  jz      short loc_180035133
0x18003512e  cmp     [rdi], r15
0x180035131  jnb     short loc_18003516E
0x180035133  mov     rdx, r15; dwBytes
0x180035136  mov     ecx, 8; dwFlags
0x18003513b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180035140  mov     r12, rax
0x180035143  test    rax, rax
0x180035146  jz      short loc_18003516B
0x180035148  mov     rbx, [rbp+40h]
0x18003514c  call    cs:__imp_GetProcessHeap
0x180035152  mov     r8, rbx; lpMem
0x180035155  xor     edx, edx; dwFlags
0x180035157  mov     rcx, rax; hHeap
0x18003515a  call    cs:__imp_HeapFree
0x180035160  mov     [rbp+40h], r12
0x180035164  lea     rbx, [rbp+20h]
0x180035168  mov     [rdi], r15
0x18003516b  xor     r12d, r12d
0x18003516e  mov     rcx, [rbp+40h]; Destination
0x180035172  test    rcx, rcx
0x180035175  jz      loc_180035204
0x18003517b  mov     rdi, [rdi]
0x18003517e  lea     r9, [rbp+10h]
0x180035182  mov     r8, [r14+38h]
0x180035186  add     rdi, rcx
0x180035189  mov     rdx, rdi
0x18003518c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180035191  mov     r8, [r14+80h]
0x180035198  mov     r9, rbx
0x18003519b  mov     rdx, rdi
0x18003519e  mov     rcx, rax; Destination
0x1800351a1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800351a6  mov     rbx, rax
0x1800351a9  cmp     rax, rdi
0x1800351ac  jz      short loc_1800351EC
0x1800351ae  mov     rcx, [r14+18h]; this
0x1800351b2  test    rcx, rcx
0x1800351b5  jz      short loc_1800351EC
0x1800351b7  cmp     [rcx], r12w
0x1800351bb  jz      short loc_1800351EC
0x1800351bd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800351c2  mov     rdx, rdi
0x1800351c5  mov     r14, rax
0x1800351c8  sub     rdx, rbx; DestinationSize
0x1800351cb  cmp     rdx, rax
0x1800351ce  jb      short loc_1800351EC
0x1800351d0  mov     r8, rcx; Source
0x1800351d3  mov     r9, rax; SourceSize
0x1800351d6  mov     rcx, rbx; Destination
0x1800351d9  call    cs:__imp_memcpy_s
0x1800351df  test    rsi, rsi
0x1800351e2  jz      short loc_1800351E7
0x1800351e4  mov     [rsi], rbx
0x1800351e7  add     rbx, r14
0x1800351ea  jmp     short loc_1800351F4
0x1800351ec  test    rsi, rsi
0x1800351ef  jz      short loc_1800351F4
0x1800351f1  mov     [rsi], r12
0x1800351f4  sub     rdi, rbx
0x1800351f7  xor     edx, edx; Val
0x1800351f9  mov     r8, rdi; Size
0x1800351fc  mov     rcx, rbx; void *
0x1800351ff  call    memset_0
0x180035204  add     rsp, 28h
0x180035208  pop     r15
0x18003520a  pop     r14
0x18003520c  pop     r13
0x18003520e  pop     r12
0x180035210  pop     rdi
0x180035211  pop     rsi
0x180035212  pop     rbp
0x180035213  pop     rbx
0x180035214  retn
```
