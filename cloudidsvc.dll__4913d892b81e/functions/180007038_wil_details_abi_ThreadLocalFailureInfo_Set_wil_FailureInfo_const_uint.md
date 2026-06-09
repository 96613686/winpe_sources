# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007038`
- end: `0x18000716e`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800073d0`

## callees

- `0x1800024f0`
- `0x180003d70`
- `0x180003de8`
- `0x180006854`
- `0x180006c78`
- `0x180006c98`
- `0x180007038`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070f5`

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
0x180007038  push    rbx
0x18000703a  push    rbp
0x18000703b  push    rsi
0x18000703c  push    rdi
0x18000703d  push    r12
0x18000703f  push    r13
0x180007041  push    r14
0x180007043  push    r15
0x180007045  sub     rsp, 28h
0x180007049  mov     [rcx+4], r8d
0x18000704d  lea     r14, [rcx+38h]
0x180007051  mov     eax, [rdx+8]
0x180007054  mov     rsi, rcx
0x180007057  mov     [rcx+8], eax
0x18000705a  mov     r15, rdx
0x18000705d  mov     qword ptr [rcx+10h], 0
0x180007065  movzx   eax, word ptr [rdx+40h]
0x180007069  mov     [rcx+18h], ax
0x18000706d  mov     al, [rdx]
0x18000706f  mov     [rcx+1Ah], al
0x180007072  mov     qword ptr [rcx+20h], 0
0x18000707a  mov     rax, [rdx+88h]
0x180007081  mov     [rcx+28h], rax
0x180007085  mov     rax, [rdx+90h]
0x18000708c  mov     [rcx+30h], rax
0x180007090  mov     qword ptr [r14], 0
0x180007097  mov     rcx, [rdx+18h]; this
0x18000709b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800070a0  mov     rcx, [r15+38h]; this
0x1800070a4  mov     rbp, rax
0x1800070a7  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800070ac  mov     rcx, [r15+80h]; this
0x1800070b3  add     rbp, rax
0x1800070b6  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800070bb  add     rbp, rax
0x1800070be  lea     rdi, [rsi+48h]
0x1800070c2  cmp     qword ptr [rsi+40h], 0
0x1800070c7  jz      short loc_1800070CE
0x1800070c9  cmp     [rdi], rbp
0x1800070cc  jnb     short loc_180007106
0x1800070ce  mov     rdx, rbp; dwBytes
0x1800070d1  mov     ecx, 8; dwFlags
0x1800070d6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800070db  mov     r14, rax
0x1800070de  test    rax, rax
0x1800070e1  jz      short loc_180007102
0x1800070e3  mov     rbx, [rsi+40h]
0x1800070e7  call    cs:__imp_GetProcessHeap
0x1800070ed  mov     r8, rbx; lpMem
0x1800070f0  xor     edx, edx; dwFlags
0x1800070f2  mov     rcx, rax; hHeap
0x1800070f5  call    cs:__imp_HeapFree
0x1800070fb  mov     [rsi+40h], r14
0x1800070ff  mov     [rdi], rbp
0x180007102  lea     r14, [rsi+38h]
0x180007106  mov     rcx, [rsi+40h]; Destination
0x18000710a  test    rcx, rcx
0x18000710d  jz      short loc_18000715D
0x18000710f  mov     rbx, [rdi]
0x180007112  lea     r9, [rsi+10h]
0x180007116  mov     r8, [r15+38h]
0x18000711a  add     rbx, rcx
0x18000711d  mov     rdx, rbx
0x180007120  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007125  mov     r8, [r15+80h]
0x18000712c  lea     r9, [rsi+20h]
0x180007130  mov     rdx, rbx
0x180007133  mov     rcx, rax; Destination
0x180007136  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000713b  mov     r8, [r15+18h]
0x18000713f  mov     r9, r14
0x180007142  mov     rdx, rbx
0x180007145  mov     rcx, rax; Destination
0x180007148  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000714d  sub     rbx, rax
0x180007150  xor     edx, edx; Val
0x180007152  mov     r8, rbx; Size
0x180007155  mov     rcx, rax; void *
0x180007158  call    memset_0
0x18000715d  add     rsp, 28h
0x180007161  pop     r15
0x180007163  pop     r14
0x180007165  pop     r13
0x180007167  pop     r12
0x180007169  pop     rdi
0x18000716a  pop     rsi
0x18000716b  pop     rbp
0x18000716c  pop     rbx
0x18000716d  retn
```
