# fsBCryptCreateHash(void *,void * *,uchar *,ulong,uchar *,ulong,ulong)

- ea: `0x1800320c0`
- end: `0x180032141`
- name: `?fsBCryptCreateHash@@YAJPEAXPEAPEAXPEAEK2KK@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *, void **, unsigned __int8 *, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180031c48`

## callees

- `0x1800320c0`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x1800320f6`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x1800320f6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032107`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032114`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032121`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003212e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032107`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032114`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180032121`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003212e`
- `bcrypt!BCryptCreateHash` at `0x1800320e5`
- `bcrypt!BCryptCreateHash` at `0x1800320e5`

## pseudocode

```c
__int64 __fastcall fsBCryptCreateHash(void *a1, void **a2, unsigned __int8 *a3, ULONG a4)
{
  unsigned int Hash; // ebx

  Hash = BCryptCreateHash(a1, a2, a3, a4, 0, 0, 0);
  if ( Hash || DbgIsSSActive(0x404u) )
  {
    CSPrintErrorLineFile(0x2D80C25u, Hash);
    CSPrintErrorLineFile(0x2D90C25u, a4);
    CSPrintErrorLineFile(0x2DA0C25u, 0);
    CSPrintErrorLineFile(0x2DB0C25u, 0);
  }
  return Hash;
}

```

## disassembly

```asm
0x1800320c0  mov     rax, rsp
0x1800320c3  mov     [rax+8], rbx
0x1800320c7  push    rdi
0x1800320c8  sub     rsp, 40h
0x1800320cc  mov     dword ptr [rax-18h], 0
0x1800320d3  mov     edi, r9d
0x1800320d6  mov     dword ptr [rax-20h], 0
0x1800320dd  mov     qword ptr [rax-28h], 0
0x1800320e5  call    cs:__imp_BCryptCreateHash
0x1800320eb  mov     ebx, eax
0x1800320ed  test    eax, eax
0x1800320ef  jnz     short loc_180032100
0x1800320f1  mov     ecx, 404h
0x1800320f6  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x1800320fc  test    eax, eax
0x1800320fe  jz      short loc_180032134
0x180032100  mov     edx, ebx
0x180032102  mov     ecx, 2D80C25h
0x180032107  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003210d  mov     edx, edi
0x18003210f  mov     ecx, 2D90C25h
0x180032114  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003211a  xor     edx, edx
0x18003211c  mov     ecx, 2DA0C25h
0x180032121  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032127  xor     edx, edx
0x180032129  mov     ecx, 2DB0C25h
0x18003212e  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032134  mov     eax, ebx
0x180032136  mov     rbx, [rsp+48h+arg_0]
0x18003213b  add     rsp, 40h
0x18003213f  pop     rdi
0x180032140  retn
```
