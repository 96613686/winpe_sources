# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007060`
- end: `0x180007196`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800074e4`

## callees

- `0x180002b6c`
- `0x180002be4`
- `0x180005d40`
- `0x180006ed4`
- `0x180006ef4`
- `0x180007060`
- `0x18002e202`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000710f`
- `KERNEL32!GetProcessHeap` at `0x18000710f`
- `KERNEL32!HeapFree` at `0x18000711d`
- `KERNEL32!HeapFree` at `0x18000711d`

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
0x180007060  push    rbx
0x180007062  push    rbp
0x180007063  push    rsi
0x180007064  push    rdi
0x180007065  push    r12
0x180007067  push    r13
0x180007069  push    r14
0x18000706b  push    r15
0x18000706d  sub     rsp, 28h
0x180007071  mov     [rcx+4], r8d
0x180007075  lea     r14, [rcx+38h]
0x180007079  mov     eax, [rdx+8]
0x18000707c  mov     rsi, rcx
0x18000707f  mov     [rcx+8], eax
0x180007082  mov     r15, rdx
0x180007085  mov     qword ptr [rcx+10h], 0
0x18000708d  movzx   eax, word ptr [rdx+40h]
0x180007091  mov     [rcx+18h], ax
0x180007095  mov     al, [rdx]
0x180007097  mov     [rcx+1Ah], al
0x18000709a  mov     qword ptr [rcx+20h], 0
0x1800070a2  mov     rax, [rdx+88h]
0x1800070a9  mov     [rcx+28h], rax
0x1800070ad  mov     rax, [rdx+90h]
0x1800070b4  mov     [rcx+30h], rax
0x1800070b8  mov     qword ptr [r14], 0
0x1800070bf  mov     rcx, [rdx+18h]; this
0x1800070c3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800070c8  mov     rcx, [r15+38h]; this
0x1800070cc  mov     rbp, rax
0x1800070cf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800070d4  mov     rcx, [r15+80h]; this
0x1800070db  add     rbp, rax
0x1800070de  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800070e3  add     rbp, rax
0x1800070e6  lea     rdi, [rsi+48h]
0x1800070ea  cmp     qword ptr [rsi+40h], 0
0x1800070ef  jz      short loc_1800070F6
0x1800070f1  cmp     [rdi], rbp
0x1800070f4  jnb     short loc_18000712E
0x1800070f6  mov     rdx, rbp; dwBytes
0x1800070f9  mov     ecx, 8; dwFlags
0x1800070fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007103  mov     r14, rax
0x180007106  test    rax, rax
0x180007109  jz      short loc_18000712A
0x18000710b  mov     rbx, [rsi+40h]
0x18000710f  call    cs:__imp_GetProcessHeap
0x180007115  mov     r8, rbx; lpMem
0x180007118  xor     edx, edx; dwFlags
0x18000711a  mov     rcx, rax; hHeap
0x18000711d  call    cs:__imp_HeapFree
0x180007123  mov     [rsi+40h], r14
0x180007127  mov     [rdi], rbp
0x18000712a  lea     r14, [rsi+38h]
0x18000712e  mov     rcx, [rsi+40h]; Destination
0x180007132  test    rcx, rcx
0x180007135  jz      short loc_180007185
0x180007137  mov     rbx, [rdi]
0x18000713a  lea     r9, [rsi+10h]
0x18000713e  mov     r8, [r15+38h]
0x180007142  add     rbx, rcx
0x180007145  mov     rdx, rbx
0x180007148  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000714d  mov     r8, [r15+80h]
0x180007154  lea     r9, [rsi+20h]
0x180007158  mov     rdx, rbx
0x18000715b  mov     rcx, rax; Destination
0x18000715e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007163  mov     r8, [r15+18h]
0x180007167  mov     r9, r14
0x18000716a  mov     rdx, rbx
0x18000716d  mov     rcx, rax; Destination
0x180007170  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180007175  sub     rbx, rax
0x180007178  xor     edx, edx; Val
0x18000717a  mov     r8, rbx; Size
0x18000717d  mov     rcx, rax; void *
0x180007180  call    memset_0
0x180007185  add     rsp, 28h
0x180007189  pop     r15
0x18000718b  pop     r14
0x18000718d  pop     r13
0x18000718f  pop     r12
0x180007191  pop     rdi
0x180007192  pop     rsi
0x180007193  pop     rbp
0x180007194  pop     rbx
0x180007195  retn
```
