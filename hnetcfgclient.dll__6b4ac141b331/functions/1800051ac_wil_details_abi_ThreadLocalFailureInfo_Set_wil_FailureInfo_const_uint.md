# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800051ac`
- end: `0x1800052e2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005544`

## callees

- `0x180003310`
- `0x180003388`
- `0x180004d28`
- `0x1800050c8`
- `0x1800050e8`
- `0x1800051ac`
- `0x18002d1d2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005269`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000525b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000525b`

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
0x1800051ac  push    rbx
0x1800051ae  push    rbp
0x1800051af  push    rsi
0x1800051b0  push    rdi
0x1800051b1  push    r12
0x1800051b3  push    r13
0x1800051b5  push    r14
0x1800051b7  push    r15
0x1800051b9  sub     rsp, 28h
0x1800051bd  mov     [rcx+4], r8d
0x1800051c1  lea     r14, [rcx+38h]
0x1800051c5  mov     eax, [rdx+8]
0x1800051c8  mov     rsi, rcx
0x1800051cb  mov     [rcx+8], eax
0x1800051ce  mov     r15, rdx
0x1800051d1  mov     qword ptr [rcx+10h], 0
0x1800051d9  movzx   eax, word ptr [rdx+40h]
0x1800051dd  mov     [rcx+18h], ax
0x1800051e1  mov     al, [rdx]
0x1800051e3  mov     [rcx+1Ah], al
0x1800051e6  mov     qword ptr [rcx+20h], 0
0x1800051ee  mov     rax, [rdx+88h]
0x1800051f5  mov     [rcx+28h], rax
0x1800051f9  mov     rax, [rdx+90h]
0x180005200  mov     [rcx+30h], rax
0x180005204  mov     qword ptr [r14], 0
0x18000520b  mov     rcx, [rdx+18h]; this
0x18000520f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005214  mov     rcx, [r15+38h]; this
0x180005218  mov     rbp, rax
0x18000521b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005220  mov     rcx, [r15+80h]; this
0x180005227  add     rbp, rax
0x18000522a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000522f  add     rbp, rax
0x180005232  lea     rdi, [rsi+48h]
0x180005236  cmp     qword ptr [rsi+40h], 0
0x18000523b  jz      short loc_180005242
0x18000523d  cmp     [rdi], rbp
0x180005240  jnb     short loc_18000527A
0x180005242  mov     rdx, rbp; dwBytes
0x180005245  mov     ecx, 8; dwFlags
0x18000524a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000524f  mov     r14, rax
0x180005252  test    rax, rax
0x180005255  jz      short loc_180005276
0x180005257  mov     rbx, [rsi+40h]
0x18000525b  call    cs:__imp_GetProcessHeap
0x180005261  mov     r8, rbx; lpMem
0x180005264  xor     edx, edx; dwFlags
0x180005266  mov     rcx, rax; hHeap
0x180005269  call    cs:__imp_HeapFree
0x18000526f  mov     [rsi+40h], r14
0x180005273  mov     [rdi], rbp
0x180005276  lea     r14, [rsi+38h]
0x18000527a  mov     rcx, [rsi+40h]; Destination
0x18000527e  test    rcx, rcx
0x180005281  jz      short loc_1800052D1
0x180005283  mov     rbx, [rdi]
0x180005286  lea     r9, [rsi+10h]
0x18000528a  mov     r8, [r15+38h]
0x18000528e  add     rbx, rcx
0x180005291  mov     rdx, rbx
0x180005294  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005299  mov     r8, [r15+80h]
0x1800052a0  lea     r9, [rsi+20h]
0x1800052a4  mov     rdx, rbx
0x1800052a7  mov     rcx, rax; Destination
0x1800052aa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800052af  mov     r8, [r15+18h]
0x1800052b3  mov     r9, r14
0x1800052b6  mov     rdx, rbx
0x1800052b9  mov     rcx, rax; Destination
0x1800052bc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800052c1  sub     rbx, rax
0x1800052c4  xor     edx, edx; Val
0x1800052c6  mov     r8, rbx; Size
0x1800052c9  mov     rcx, rax; void *
0x1800052cc  call    memset_0
0x1800052d1  add     rsp, 28h
0x1800052d5  pop     r15
0x1800052d7  pop     r14
0x1800052d9  pop     r13
0x1800052db  pop     r12
0x1800052dd  pop     rdi
0x1800052de  pop     rsi
0x1800052df  pop     rbp
0x1800052e0  pop     rbx
0x1800052e1  retn
```
