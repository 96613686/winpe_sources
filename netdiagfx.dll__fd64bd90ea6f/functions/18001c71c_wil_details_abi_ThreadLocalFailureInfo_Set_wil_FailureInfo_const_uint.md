# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001c71c`
- end: `0x18001c852`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c858`

## callees

- `0x180002808`
- `0x180002880`
- `0x1800032a4`
- `0x1800032c4`
- `0x18001b7f4`
- `0x18001c71c`
- `0x18002c802`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001c7d9`
- `KERNEL32!HeapFree` at `0x18001c7d9`
- `KERNEL32!GetProcessHeap` at `0x18001c7cb`
- `KERNEL32!GetProcessHeap` at `0x18001c7cb`

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
0x18001c71c  push    rbx
0x18001c71e  push    rbp
0x18001c71f  push    rsi
0x18001c720  push    rdi
0x18001c721  push    r12
0x18001c723  push    r13
0x18001c725  push    r14
0x18001c727  push    r15
0x18001c729  sub     rsp, 28h
0x18001c72d  mov     [rcx+4], r8d
0x18001c731  lea     r14, [rcx+38h]
0x18001c735  mov     eax, [rdx+8]
0x18001c738  mov     rsi, rcx
0x18001c73b  mov     [rcx+8], eax
0x18001c73e  mov     r15, rdx
0x18001c741  mov     qword ptr [rcx+10h], 0
0x18001c749  movzx   eax, word ptr [rdx+40h]
0x18001c74d  mov     [rcx+18h], ax
0x18001c751  mov     al, [rdx]
0x18001c753  mov     [rcx+1Ah], al
0x18001c756  mov     qword ptr [rcx+20h], 0
0x18001c75e  mov     rax, [rdx+88h]
0x18001c765  mov     [rcx+28h], rax
0x18001c769  mov     rax, [rdx+90h]
0x18001c770  mov     [rcx+30h], rax
0x18001c774  mov     qword ptr [r14], 0
0x18001c77b  mov     rcx, [rdx+18h]; this
0x18001c77f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001c784  mov     rcx, [r15+38h]; this
0x18001c788  mov     rbp, rax
0x18001c78b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001c790  mov     rcx, [r15+80h]; this
0x18001c797  add     rbp, rax
0x18001c79a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001c79f  add     rbp, rax
0x18001c7a2  lea     rdi, [rsi+48h]
0x18001c7a6  cmp     qword ptr [rsi+40h], 0
0x18001c7ab  jz      short loc_18001C7B2
0x18001c7ad  cmp     [rdi], rbp
0x18001c7b0  jnb     short loc_18001C7EA
0x18001c7b2  mov     rdx, rbp; dwBytes
0x18001c7b5  mov     ecx, 8; dwFlags
0x18001c7ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001c7bf  mov     r14, rax
0x18001c7c2  test    rax, rax
0x18001c7c5  jz      short loc_18001C7E6
0x18001c7c7  mov     rbx, [rsi+40h]
0x18001c7cb  call    cs:__imp_GetProcessHeap
0x18001c7d1  mov     r8, rbx; lpMem
0x18001c7d4  xor     edx, edx; dwFlags
0x18001c7d6  mov     rcx, rax; hHeap
0x18001c7d9  call    cs:__imp_HeapFree
0x18001c7df  mov     [rsi+40h], r14
0x18001c7e3  mov     [rdi], rbp
0x18001c7e6  lea     r14, [rsi+38h]
0x18001c7ea  mov     rcx, [rsi+40h]; Destination
0x18001c7ee  test    rcx, rcx
0x18001c7f1  jz      short loc_18001C841
0x18001c7f3  mov     rbx, [rdi]
0x18001c7f6  lea     r9, [rsi+10h]
0x18001c7fa  mov     r8, [r15+38h]
0x18001c7fe  add     rbx, rcx
0x18001c801  mov     rdx, rbx
0x18001c804  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001c809  mov     r8, [r15+80h]
0x18001c810  lea     r9, [rsi+20h]
0x18001c814  mov     rdx, rbx
0x18001c817  mov     rcx, rax; Destination
0x18001c81a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001c81f  mov     r8, [r15+18h]
0x18001c823  mov     r9, r14
0x18001c826  mov     rdx, rbx
0x18001c829  mov     rcx, rax; Destination
0x18001c82c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18001c831  sub     rbx, rax
0x18001c834  xor     edx, edx; Val
0x18001c836  mov     r8, rbx; Size
0x18001c839  mov     rcx, rax; void *
0x18001c83c  call    memset_0
0x18001c841  add     rsp, 28h
0x18001c845  pop     r15
0x18001c847  pop     r14
0x18001c849  pop     r13
0x18001c84b  pop     r12
0x18001c84d  pop     rdi
0x18001c84e  pop     rsi
0x18001c84f  pop     rbp
0x18001c850  pop     rbx
0x18001c851  retn
```
