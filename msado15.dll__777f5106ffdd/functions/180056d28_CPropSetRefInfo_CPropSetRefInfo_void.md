# CPropSetRefInfo::~CPropSetRefInfo(void)

- ea: `0x180056d28`
- end: `0x180056df3`
- name: `??1CPropSetRefInfo@@UEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CPropSetRefInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800657d0`

## callees

- `0x180011530`
- `0x180056d28`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180056d93`
- `ole32!CoTaskMemFree` at `0x180056dae`
- `ole32!CoTaskMemFree` at `0x180056dc3`
- `ole32!CoTaskMemFree` at `0x180056d93`
- `ole32!CoTaskMemFree` at `0x180056dae`
- `ole32!CoTaskMemFree` at `0x180056dc3`
- `OLEAUT32!__imp_VariantClear` at `0x180056d71`
- `OLEAUT32!__imp_VariantClear` at `0x180056d71`

## pseudocode

```c
void __fastcall CPropSetRefInfo::~CPropSetRefInfo(CPropSetRefInfo *this)
{
  unsigned int v1; // ebp
  LPVOID *v2; // rdi
  _QWORD *v4; // rdx
  __int64 v5; // rsi
  __int64 v6; // r14
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v1 = 0;
  v2 = (LPVOID *)((char *)this + 32);
  for ( *(_QWORD *)this = &CRsetPropRefInfo::`vftable'; v1 < *((_DWORD *)this + 10); ++v1 )
  {
    v4 = *v2;
    v5 = 32LL * v1;
    if ( *(_DWORD *)((char *)*v2 + v5 + 8) )
    {
      v6 = 0;
      do
      {
        VariantClear((VARIANTARG *)(v4[4 * v1] + 24LL + 48 * v6));
        v4 = *v2;
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < *(_DWORD *)((char *)*v2 + v5 + 8) );
    }
    v7 = (void *)v4[4 * v1];
    if ( v7 )
      CoTaskMemFree(v7);
  }
  if ( *v2 )
    CoTaskMemFree(*v2);
  v8 = (void *)*((_QWORD *)this + 7);
  if ( v8 )
    CoTaskMemFree(v8);
  v9 = (void *)*((_QWORD *)this + 9);
  if ( v9 )
    operator delete(v9);
  *(_QWORD *)this = &CStdPropRefInfo::`vftable';
}

```

## disassembly

```asm
0x180056d28  push    rbx
0x180056d2a  push    rbp
0x180056d2b  push    rsi
0x180056d2c  push    rdi
0x180056d2d  push    r14
0x180056d2f  sub     rsp, 20h
0x180056d33  xor     ebp, ebp
0x180056d35  lea     rax, ??_7CRsetPropRefInfo@@6B@; const CRsetPropRefInfo::`vftable'
0x180056d3c  lea     rdi, [rcx+20h]
0x180056d40  mov     rbx, rcx
0x180056d43  mov     [rcx], rax
0x180056d46  cmp     [rcx+28h], ebp
0x180056d49  jbe     short loc_180056DA6
0x180056d4b  mov     rdx, [rdi]
0x180056d4e  mov     esi, ebp
0x180056d50  shl     rsi, 5
0x180056d54  cmp     dword ptr [rsi+rdx+8], 0
0x180056d59  jbe     short loc_180056D8A
0x180056d5b  xor     r14d, r14d
0x180056d5e  mov     rax, [rdx+rsi]
0x180056d62  lea     rcx, [r14+r14*2]
0x180056d66  shl     rcx, 4
0x180056d6a  add     rax, 18h
0x180056d6e  add     rcx, rax; pvarg
0x180056d71  call    cs:__imp_VariantClear
0x180056d78  nop     dword ptr [rax+rax+00h]
0x180056d7d  mov     rdx, [rdi]
0x180056d80  inc     r14d
0x180056d83  cmp     r14d, [rdx+rsi+8]
0x180056d88  jb      short loc_180056D5E
0x180056d8a  mov     rcx, [rdx+rsi]; pv
0x180056d8e  test    rcx, rcx
0x180056d91  jz      short loc_180056D9F
0x180056d93  call    cs:__imp_CoTaskMemFree
0x180056d9a  nop     dword ptr [rax+rax+00h]
0x180056d9f  inc     ebp
0x180056da1  cmp     ebp, [rbx+28h]
0x180056da4  jb      short loc_180056D4B
0x180056da6  mov     rcx, [rdi]; pv
0x180056da9  test    rcx, rcx
0x180056dac  jz      short loc_180056DBA
0x180056dae  call    cs:__imp_CoTaskMemFree
0x180056db5  nop     dword ptr [rax+rax+00h]
0x180056dba  mov     rcx, [rbx+38h]; pv
0x180056dbe  test    rcx, rcx
0x180056dc1  jz      short loc_180056DCF
0x180056dc3  call    cs:__imp_CoTaskMemFree
0x180056dca  nop     dword ptr [rax+rax+00h]
0x180056dcf  mov     rcx, [rbx+48h]; void *
0x180056dd3  test    rcx, rcx
0x180056dd6  jz      short loc_180056DDD
0x180056dd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056ddd  lea     rax, ??_7CStdPropRefInfo@@6B@; const CStdPropRefInfo::`vftable'
0x180056de4  mov     [rbx], rax
0x180056de7  add     rsp, 20h
0x180056deb  pop     r14
0x180056ded  pop     rdi
0x180056dee  pop     rsi
0x180056def  pop     rbp
0x180056df0  pop     rbx
0x180056df1  retn
```
