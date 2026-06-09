# SettingStore::_CreateTask(SettingStore::POOL_TASK_TYPE,_GUID const *,SettingStore::HIVEID,SettingStore::TYPE,uchar const *,ulong,tagSAFEARRAY *,IStream *,SettingStore::POOL_TASK * *)

- ea: `0x180076a08`
- end: `0x180076aee`
- name: `?_CreateTask@SettingStore@@YAJW4POOL_TASK_TYPE@1@PEBU_GUID@@W4HIVEID@1@W4TYPE@1@PEBEKPEAUtagSAFEARRAY@@PEAUIStream@@PEAPEAUPOOL_TASK@1@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180076bdc`

## callees

- `0x1800580e6`
- `0x180075b30`
- `0x180076a08`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180076a31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180076a86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180076a31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180076a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076a1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076a75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076a1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076a75`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180076ab4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180076ab4`

## pseudocode

```c
__int64 __fastcall SettingStore::_CreateTask(
        int a1,
        __int64 a2,
        int a3,
        int a4,
        void *Src,
        unsigned int dwBytes,
        SAFEARRAY *psa,
        __int64 a8,
        _QWORD *a9)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  HANDLE v16; // rax
  void *v17; // rax
  unsigned int v18; // edx
  HRESULT v19; // edi

  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 8u, 0x38u);
  v15 = v14;
  if ( !v14 )
    return (unsigned int)-2147024882;
  v14[1] = a2;
  *(_DWORD *)v14 = a1;
  *((_DWORD *)v14 + 4) = a3;
  *((_DWORD *)v14 + 5) = a4;
  v14[6] = a8;
  if ( a8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a8 + 8LL))(a8);
  if ( dwBytes )
  {
    v16 = GetProcessHeap();
    v17 = HeapAlloc(v16, 8u, dwBytes);
    v15[3] = v17;
    if ( !v17 )
    {
      v19 = -2147024882;
      goto LABEL_10;
    }
    memcpy_0(v17, Src, dwBytes);
    *((_DWORD *)v15 + 8) = dwBytes;
  }
  v19 = SafeArrayCopy(psa, (SAFEARRAY **)v15 + 5);
  if ( v19 < 0 )
  {
LABEL_10:
    SettingStore::POOL_TASK::`scalar deleting destructor'((SettingStore::POOL_TASK *)v15, v18);
    return (unsigned int)v19;
  }
  *a9 = v15;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180076a08  push    rbx
0x180076a0a  push    rbp
0x180076a0b  push    rsi
0x180076a0c  push    rdi
0x180076a0d  push    r14
0x180076a0f  sub     rsp, 20h
0x180076a13  mov     edi, r9d
0x180076a16  mov     esi, r8d
0x180076a19  mov     rbp, rdx
0x180076a1c  mov     r14d, ecx
0x180076a1f  call    cs:__imp_GetProcessHeap
0x180076a25  mov     edx, 8; dwFlags
0x180076a2a  mov     rcx, rax; hHeap
0x180076a2d  lea     r8d, [rdx+30h]; dwBytes
0x180076a31  call    cs:__imp_HeapAlloc
0x180076a37  mov     rbx, rax
0x180076a3a  test    rax, rax
0x180076a3d  jz      loc_180076ADC
0x180076a43  mov     rcx, [rsp+48h+arg_38]
0x180076a4b  mov     [rax+8], rbp
0x180076a4f  mov     [rax], r14d
0x180076a52  mov     [rax+10h], esi
0x180076a55  mov     [rax+14h], edi
0x180076a58  mov     [rax+30h], rcx
0x180076a5c  test    rcx, rcx
0x180076a5f  jz      short loc_180076A6D
0x180076a61  mov     rax, [rcx]
0x180076a64  mov     rax, [rax+8]
0x180076a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a6d  mov     edi, dword ptr [rsp+48h+dwBytes]
0x180076a71  test    edi, edi
0x180076a73  jz      short loc_180076AA8
0x180076a75  call    cs:__imp_GetProcessHeap
0x180076a7b  mov     r8d, edi; dwBytes
0x180076a7e  mov     edx, 8; dwFlags
0x180076a83  mov     rcx, rax; hHeap
0x180076a86  call    cs:__imp_HeapAlloc
0x180076a8c  mov     [rbx+18h], rax
0x180076a90  test    rax, rax
0x180076a93  jz      short loc_180076ACD
0x180076a95  mov     rdx, [rsp+48h+Src]; Src
0x180076a9a  mov     r8d, edi; Size
0x180076a9d  mov     rcx, rax; void *
0x180076aa0  call    memcpy_0
0x180076aa5  mov     [rbx+20h], edi
0x180076aa8  mov     rcx, [rsp+48h+psa]; psa
0x180076ab0  lea     rdx, [rbx+28h]; ppsaOut
0x180076ab4  call    cs:__imp_SafeArrayCopy
0x180076aba  mov     edi, eax
0x180076abc  test    eax, eax
0x180076abe  js      short loc_180076AD2
0x180076ac0  mov     rcx, [rsp+48h+arg_40]
0x180076ac8  mov     [rcx], rbx
0x180076acb  jmp     short loc_180076AE1
0x180076acd  mov     edi, 8007000Eh
0x180076ad2  mov     rcx, rbx; this
0x180076ad5  call    ??_GPOOL_TASK@SettingStore@@QEAAPEAXI@Z; SettingStore::POOL_TASK::`scalar deleting destructor'(uint)
0x180076ada  jmp     short loc_180076AE1
0x180076adc  mov     edi, 8007000Eh
0x180076ae1  mov     eax, edi
0x180076ae3  add     rsp, 20h
0x180076ae7  pop     r14
0x180076ae9  pop     rdi
0x180076aea  pop     rsi
0x180076aeb  pop     rbp
0x180076aec  pop     rbx
0x180076aed  retn
```
