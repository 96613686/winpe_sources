# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002cfa0`
- end: `0x18002d0d6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002d428`

## callees

- `0x180027328`
- `0x1800273a0`
- `0x18002b85c`
- `0x18002ce14`
- `0x18002ce34`
- `0x18002cfa0`
- `0x180031642`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002d05d`
- `KERNEL32!HeapFree` at `0x18002d05d`
- `KERNEL32!GetProcessHeap` at `0x18002d04f`
- `KERNEL32!GetProcessHeap` at `0x18002d04f`

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
0x18002cfa0  push    rbx
0x18002cfa2  push    rbp
0x18002cfa3  push    rsi
0x18002cfa4  push    rdi
0x18002cfa5  push    r12
0x18002cfa7  push    r13
0x18002cfa9  push    r14
0x18002cfab  push    r15
0x18002cfad  sub     rsp, 28h
0x18002cfb1  mov     [rcx+4], r8d
0x18002cfb5  lea     r14, [rcx+38h]
0x18002cfb9  mov     eax, [rdx+8]
0x18002cfbc  mov     rsi, rcx
0x18002cfbf  mov     [rcx+8], eax
0x18002cfc2  mov     r15, rdx
0x18002cfc5  mov     qword ptr [rcx+10h], 0
0x18002cfcd  movzx   eax, word ptr [rdx+40h]
0x18002cfd1  mov     [rcx+18h], ax
0x18002cfd5  mov     al, [rdx]
0x18002cfd7  mov     [rcx+1Ah], al
0x18002cfda  mov     qword ptr [rcx+20h], 0
0x18002cfe2  mov     rax, [rdx+88h]
0x18002cfe9  mov     [rcx+28h], rax
0x18002cfed  mov     rax, [rdx+90h]
0x18002cff4  mov     [rcx+30h], rax
0x18002cff8  mov     qword ptr [r14], 0
0x18002cfff  mov     rcx, [rdx+18h]; this
0x18002d003  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002d008  mov     rcx, [r15+38h]; this
0x18002d00c  mov     rbp, rax
0x18002d00f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002d014  mov     rcx, [r15+80h]; this
0x18002d01b  add     rbp, rax
0x18002d01e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002d023  add     rbp, rax
0x18002d026  lea     rdi, [rsi+48h]
0x18002d02a  cmp     qword ptr [rsi+40h], 0
0x18002d02f  jz      short loc_18002D036
0x18002d031  cmp     [rdi], rbp
0x18002d034  jnb     short loc_18002D06E
0x18002d036  mov     rdx, rbp; dwBytes
0x18002d039  mov     ecx, 8; dwFlags
0x18002d03e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002d043  mov     r14, rax
0x18002d046  test    rax, rax
0x18002d049  jz      short loc_18002D06A
0x18002d04b  mov     rbx, [rsi+40h]
0x18002d04f  call    cs:__imp_GetProcessHeap
0x18002d055  mov     r8, rbx; lpMem
0x18002d058  xor     edx, edx; dwFlags
0x18002d05a  mov     rcx, rax; hHeap
0x18002d05d  call    cs:__imp_HeapFree
0x18002d063  mov     [rsi+40h], r14
0x18002d067  mov     [rdi], rbp
0x18002d06a  lea     r14, [rsi+38h]
0x18002d06e  mov     rcx, [rsi+40h]; Destination
0x18002d072  test    rcx, rcx
0x18002d075  jz      short loc_18002D0C5
0x18002d077  mov     rbx, [rdi]
0x18002d07a  lea     r9, [rsi+10h]
0x18002d07e  mov     r8, [r15+38h]
0x18002d082  add     rbx, rcx
0x18002d085  mov     rdx, rbx
0x18002d088  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002d08d  mov     r8, [r15+80h]
0x18002d094  lea     r9, [rsi+20h]
0x18002d098  mov     rdx, rbx
0x18002d09b  mov     rcx, rax; Destination
0x18002d09e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002d0a3  mov     r8, [r15+18h]
0x18002d0a7  mov     r9, r14
0x18002d0aa  mov     rdx, rbx
0x18002d0ad  mov     rcx, rax; Destination
0x18002d0b0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18002d0b5  sub     rbx, rax
0x18002d0b8  xor     edx, edx; Val
0x18002d0ba  mov     r8, rbx; Size
0x18002d0bd  mov     rcx, rax; void *
0x18002d0c0  call    memset_0
0x18002d0c5  add     rsp, 28h
0x18002d0c9  pop     r15
0x18002d0cb  pop     r14
0x18002d0cd  pop     r13
0x18002d0cf  pop     r12
0x18002d0d1  pop     rdi
0x18002d0d2  pop     rsi
0x18002d0d3  pop     rbp
0x18002d0d4  pop     rbx
0x18002d0d5  retn
```
