# CRecFieldsRefInfo::~CRecFieldsRefInfo(void)

- ea: `0x18009c8f0`
- end: `0x18009c988`
- name: `??1CRecFieldsRefInfo@@UEAA@XZ`
- size: `152`
- prototype: `void __fastcall(CRecFieldsRefInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18009ca70`

## callees

- `0x18009c8f0`

## import_xrefs

- `MSDART!MpHeapFree` at `0x18009c957`
- `MSDART!MpHeapFree` at `0x18009c957`
- `ole32!CoTaskMemFree` at `0x18009c967`
- `ole32!CoTaskMemFree` at `0x18009c967`
- `ole32!CoTaskMemFree` at `0x18009c97c`
- `OLEAUT32!__imp_VariantClear` at `0x18009c92a`
- `OLEAUT32!__imp_VariantClear` at `0x18009c92a`

## pseudocode

```c
void __fastcall CRecFieldsRefInfo::~CRecFieldsRefInfo(CRecFieldsRefInfo *this)
{
  bool v1; // zf
  unsigned __int64 v3; // rax
  __int64 v4; // rdx

  v1 = *((_QWORD *)this + 4) == 0;
  *(_QWORD *)this = &CRecFieldsRefInfo::`vftable';
  if ( !v1 )
  {
    v1 = *((_QWORD *)this + 2) == 0;
    *((_QWORD *)this + 1) = 0;
    if ( !v1 )
    {
      v3 = 0;
      do
      {
        VariantClear(*(VARIANTARG **)(*((_QWORD *)this + 4) + 80 * v3));
        v3 = *((_QWORD *)this + 1) + 1LL;
        *((_QWORD *)this + 1) = v3;
      }
      while ( v3 < *((_QWORD *)this + 2) );
    }
    v4 = *((_QWORD *)this + 4);
    if ( v4 )
      MpHeapFree(g_hHeapHandle, v4);
  }
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 5));
}

```

## disassembly

```asm
0x18009c8f0  push    rbx
0x18009c8f2  sub     rsp, 20h
0x18009c8f6  cmp     qword ptr [rcx+20h], 0
0x18009c8fb  lea     rax, ??_7CRecFieldsRefInfo@@6B@; const CRecFieldsRefInfo::`vftable'
0x18009c902  mov     [rcx], rax
0x18009c905  mov     rbx, rcx
0x18009c908  jz      short loc_18009C963
0x18009c90a  cmp     qword ptr [rcx+10h], 0
0x18009c90f  mov     qword ptr [rcx+8], 0
0x18009c917  jbe     short loc_18009C947
0x18009c919  xor     eax, eax
0x18009c91b  mov     rcx, [rbx+20h]
0x18009c91f  lea     rax, [rax+rax*4]
0x18009c923  add     rax, rax
0x18009c926  mov     rcx, [rcx+rax*8]; pvarg
0x18009c92a  call    cs:__imp_VariantClear
0x18009c931  nop     dword ptr [rax+rax+00h]
0x18009c936  mov     rax, [rbx+8]
0x18009c93a  inc     rax
0x18009c93d  mov     [rbx+8], rax
0x18009c941  cmp     rax, [rbx+10h]
0x18009c945  jb      short loc_18009C91B
0x18009c947  mov     rdx, [rbx+20h]
0x18009c94b  test    rdx, rdx
0x18009c94e  jz      short loc_18009C963
0x18009c950  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18009c957  call    cs:__imp_MpHeapFree
0x18009c95e  nop     dword ptr [rax+rax+00h]
0x18009c963  mov     rcx, [rbx+18h]; pv
0x18009c967  call    cs:__imp_CoTaskMemFree
0x18009c96e  nop     dword ptr [rax+rax+00h]
0x18009c973  mov     rcx, [rbx+28h]
0x18009c977  add     rsp, 20h
0x18009c97b  pop     rbx
0x18009c97c  jmp     cs:__imp_CoTaskMemFree
```
