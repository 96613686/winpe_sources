# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007a4c`
- end: `0x180007b82`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007de4`

## callees

- `0x180005b2c`
- `0x1800063a8`
- `0x180006420`
- `0x180007788`
- `0x18000799c`
- `0x1800079bc`
- `0x180007a4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007afb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007afb`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  __int64 v6; // rbp
  const char *v7; // rdx
  __int64 v8; // rbp
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
0x180007a4c  push    rbx
0x180007a4e  push    rbp
0x180007a4f  push    rsi
0x180007a50  push    rdi
0x180007a51  push    r12
0x180007a53  push    r13
0x180007a55  push    r14
0x180007a57  push    r15
0x180007a59  sub     rsp, 28h
0x180007a5d  mov     [rcx+4], r8d
0x180007a61  lea     r14, [rcx+38h]
0x180007a65  mov     eax, [rdx+8]
0x180007a68  mov     rsi, rcx
0x180007a6b  mov     [rcx+8], eax
0x180007a6e  mov     r15, rdx
0x180007a71  mov     qword ptr [rcx+10h], 0
0x180007a79  movzx   eax, word ptr [rdx+40h]
0x180007a7d  mov     [rcx+18h], ax
0x180007a81  mov     al, [rdx]
0x180007a83  mov     [rcx+1Ah], al
0x180007a86  mov     qword ptr [rcx+20h], 0
0x180007a8e  mov     rax, [rdx+88h]
0x180007a95  mov     [rcx+28h], rax
0x180007a99  mov     rax, [rdx+90h]
0x180007aa0  mov     [rcx+30h], rax
0x180007aa4  mov     qword ptr [r14], 0
0x180007aab  mov     rcx, [rdx+18h]; this
0x180007aaf  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007ab4  mov     rcx, [r15+38h]; this
0x180007ab8  mov     rbp, rax
0x180007abb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007ac0  mov     rcx, [r15+80h]; this
0x180007ac7  add     rbp, rax
0x180007aca  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007acf  add     rbp, rax
0x180007ad2  lea     rdi, [rsi+48h]
0x180007ad6  cmp     qword ptr [rsi+40h], 0
0x180007adb  jz      short loc_180007AE2
0x180007add  cmp     [rdi], rbp
0x180007ae0  jnb     short loc_180007B1A
0x180007ae2  mov     rdx, rbp; dwBytes
0x180007ae5  mov     ecx, 8; dwFlags
0x180007aea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007aef  mov     r14, rax
0x180007af2  test    rax, rax
0x180007af5  jz      short loc_180007B16
0x180007af7  mov     rbx, [rsi+40h]
0x180007afb  call    cs:__imp_GetProcessHeap
0x180007b01  mov     r8, rbx; lpMem
0x180007b04  xor     edx, edx; dwFlags
0x180007b06  mov     rcx, rax; hHeap
0x180007b09  call    cs:__imp_HeapFree
0x180007b0f  mov     [rsi+40h], r14
0x180007b13  mov     [rdi], rbp
0x180007b16  lea     r14, [rsi+38h]
0x180007b1a  mov     rcx, [rsi+40h]; Destination
0x180007b1e  test    rcx, rcx
0x180007b21  jz      short loc_180007B71
0x180007b23  mov     rbx, [rdi]
0x180007b26  lea     r9, [rsi+10h]
0x180007b2a  mov     r8, [r15+38h]
0x180007b2e  add     rbx, rcx
0x180007b31  mov     rdx, rbx
0x180007b34  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007b39  mov     r8, [r15+80h]
0x180007b40  lea     r9, [rsi+20h]
0x180007b44  mov     rdx, rbx
0x180007b47  mov     rcx, rax; Destination
0x180007b4a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007b4f  mov     r8, [r15+18h]
0x180007b53  mov     r9, r14
0x180007b56  mov     rdx, rbx
0x180007b59  mov     rcx, rax; Destination
0x180007b5c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180007b61  sub     rbx, rax
0x180007b64  xor     edx, edx; Val
0x180007b66  mov     r8, rbx; Size
0x180007b69  mov     rcx, rax; void *
0x180007b6c  call    memset_0
0x180007b71  add     rsp, 28h
0x180007b75  pop     r15
0x180007b77  pop     r14
0x180007b79  pop     r13
0x180007b7b  pop     r12
0x180007b7d  pop     rdi
0x180007b7e  pop     rsi
0x180007b7f  pop     rbp
0x180007b80  pop     rbx
0x180007b81  retn
```
