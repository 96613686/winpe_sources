# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140013070`
- end: `0x1400131a6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140013408`

## callees

- `0x14000f32c`
- `0x140010ad3`
- `0x140011614`
- `0x14001168c`
- `0x140012f88`
- `0x140012fa8`
- `0x140013070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001311f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001311f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001312d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001312d`

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
0x140013070  push    rbx
0x140013072  push    rbp
0x140013073  push    rsi
0x140013074  push    rdi
0x140013075  push    r12
0x140013077  push    r13
0x140013079  push    r14
0x14001307b  push    r15
0x14001307d  sub     rsp, 28h
0x140013081  mov     [rcx+4], r8d
0x140013085  lea     r14, [rcx+38h]
0x140013089  mov     eax, [rdx+8]
0x14001308c  mov     rsi, rcx
0x14001308f  mov     [rcx+8], eax
0x140013092  mov     r15, rdx
0x140013095  mov     qword ptr [rcx+10h], 0
0x14001309d  movzx   eax, word ptr [rdx+40h]
0x1400130a1  mov     [rcx+18h], ax
0x1400130a5  mov     al, [rdx]
0x1400130a7  mov     [rcx+1Ah], al
0x1400130aa  mov     qword ptr [rcx+20h], 0
0x1400130b2  mov     rax, [rdx+88h]
0x1400130b9  mov     [rcx+28h], rax
0x1400130bd  mov     rax, [rdx+90h]
0x1400130c4  mov     [rcx+30h], rax
0x1400130c8  mov     qword ptr [r14], 0
0x1400130cf  mov     rcx, [rdx+18h]; this
0x1400130d3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400130d8  mov     rcx, [r15+38h]; this
0x1400130dc  mov     rbp, rax
0x1400130df  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400130e4  mov     rcx, [r15+80h]; this
0x1400130eb  add     rbp, rax
0x1400130ee  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400130f3  add     rbp, rax
0x1400130f6  lea     rdi, [rsi+48h]
0x1400130fa  cmp     qword ptr [rsi+40h], 0
0x1400130ff  jz      short loc_140013106
0x140013101  cmp     [rdi], rbp
0x140013104  jnb     short loc_14001313E
0x140013106  mov     rdx, rbp; dwBytes
0x140013109  mov     ecx, 8; dwFlags
0x14001310e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140013113  mov     r14, rax
0x140013116  test    rax, rax
0x140013119  jz      short loc_14001313A
0x14001311b  mov     rbx, [rsi+40h]
0x14001311f  call    cs:__imp_GetProcessHeap
0x140013125  mov     r8, rbx; lpMem
0x140013128  xor     edx, edx; dwFlags
0x14001312a  mov     rcx, rax; hHeap
0x14001312d  call    cs:__imp_HeapFree
0x140013133  mov     [rsi+40h], r14
0x140013137  mov     [rdi], rbp
0x14001313a  lea     r14, [rsi+38h]
0x14001313e  mov     rcx, [rsi+40h]; Destination
0x140013142  test    rcx, rcx
0x140013145  jz      short loc_140013195
0x140013147  mov     rbx, [rdi]
0x14001314a  lea     r9, [rsi+10h]
0x14001314e  mov     r8, [r15+38h]
0x140013152  add     rbx, rcx
0x140013155  mov     rdx, rbx
0x140013158  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14001315d  mov     r8, [r15+80h]
0x140013164  lea     r9, [rsi+20h]
0x140013168  mov     rdx, rbx
0x14001316b  mov     rcx, rax; Destination
0x14001316e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140013173  mov     r8, [r15+18h]
0x140013177  mov     r9, r14
0x14001317a  mov     rdx, rbx
0x14001317d  mov     rcx, rax; Destination
0x140013180  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140013185  sub     rbx, rax
0x140013188  xor     edx, edx; Val
0x14001318a  mov     r8, rbx; Size
0x14001318d  mov     rcx, rax; void *
0x140013190  call    memset_0
0x140013195  add     rsp, 28h
0x140013199  pop     r15
0x14001319b  pop     r14
0x14001319d  pop     r13
0x14001319f  pop     r12
0x1400131a1  pop     rdi
0x1400131a2  pop     rsi
0x1400131a3  pop     rbp
0x1400131a4  pop     rbx
0x1400131a5  retn
```
