# ATL::CComObject<CDCMCreator>::CreateInstance(ATL::CComObject<CDCMCreator> * *)

- ea: `0x180072468`
- end: `0x18007255a`
- name: `?CreateInstance@?$CComObject@VCDCMCreator@@@ATL@@SAJPEAPEAV12@@Z`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011d1c`

## callees

- `0x180026804`
- `0x1800723f0`
- `0x180072468`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18007249b`
- `MSDART!MpHeapAlloc` at `0x18007249b`
- `KERNEL32!InitializeCriticalSection` at `0x1800724bb`
- `KERNEL32!InitializeCriticalSection` at `0x1800724bb`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180072531`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180072531`

## pseudocode

```c
__int64 ATL::CComObject<CDCMCreator>::CreateInstance()
{
  unsigned int FreeThreadedMarshaler; // ebx
  __int64 v1; // rax
  char *v2; // rdi
  CDCMCreator *v3; // r14
  IUnknown *v4; // rax

  _DCMNonReusable = 0;
  FreeThreadedMarshaler = -2147024882;
  v1 = MpHeapAlloc(g_hHeapHandle, 19922944, 136);
  v2 = (char *)v1;
  if ( v1 )
  {
    ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(v1 + 8);
    InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 96));
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    *((_DWORD *)v2 + 18) = 0;
    *((_QWORD *)v2 + 10) = 0;
    v2[88] = 0;
    *(_QWORD *)v2 = &ATL::CComObject<CDCMCreator>::`vftable';
    _InterlockedIncrement(&dword_1800BE368);
  }
  else
  {
    v2 = 0;
  }
  v3 = (CDCMCreator *)v2;
  if ( v2 )
  {
    v4 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 72LL))(v2);
    FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v4, (LPUNKNOWN *)v2 + 7);
    if ( FreeThreadedMarshaler )
    {
      ATL::CComObject<CDCMCreator>::`scalar deleting destructor'(v2);
      v3 = 0;
    }
  }
  _DCMNonReusable = v3;
  return FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180072468  mov     [rsp+arg_0], rcx
0x18007246d  push    rbx
0x18007246e  push    rdi
0x18007246f  push    r14
0x180072471  sub     rsp, 20h
0x180072475  mov     cs:?_DCMNonReusable@@3PEAV?$CComObject@VCDCMCreator@@@ATL@@EA, 0; ATL::CComObject<CDCMCreator> * _DCMNonReusable
0x180072480  mov     ebx, 8007000Eh
0x180072485  mov     dword ptr [rsp+38h+arg_0], ebx
0x180072489  mov     edx, 1300000h
0x18007248e  mov     r8d, 88h
0x180072494  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18007249b  call    cs:__imp_MpHeapAlloc
0x1800724a1  mov     rdi, rax
0x1800724a4  mov     [rsp+38h+arg_8], rax
0x1800724a9  test    rax, rax
0x1800724ac  jz      short loc_1800724F7
0x1800724ae  lea     rcx, [rax+8]
0x1800724b2  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x1800724b7  lea     rcx, [rdi+60h]; lpCriticalSection
0x1800724bb  call    cs:__imp_InitializeCriticalSection
0x1800724c1  mov     qword ptr [rdi+38h], 0
0x1800724c9  mov     qword ptr [rdi+40h], 0
0x1800724d1  mov     dword ptr [rdi+48h], 0
0x1800724d8  mov     qword ptr [rdi+50h], 0
0x1800724e0  mov     byte ptr [rdi+58h], 0
0x1800724e4  lea     rax, ??_7?$CComObject@VCDCMCreator@@@ATL@@6B@; const ATL::CComObject<CDCMCreator>::`vftable'
0x1800724eb  mov     [rdi], rax
0x1800724ee  lock inc cs:dword_1800BE368
0x1800724f5  jmp     short loc_1800724F9
0x1800724f7  xor     edi, edi
0x1800724f9  mov     [rsp+38h+arg_8], rdi
0x1800724fe  mov     r14, rdi
0x180072501  mov     [rsp+38h+arg_10], rdi
0x180072506  jmp     short loc_180072516
0x180072508  mov     ebx, dword ptr [rsp+38h+arg_0]
0x18007250c  mov     r14, [rsp+38h+arg_10]
0x180072511  mov     rdi, [rsp+38h+arg_8]
0x180072516  test    rdi, rdi
0x180072519  jz      short loc_180072548
0x18007251b  mov     rax, [rdi]
0x18007251e  mov     rcx, rdi
0x180072521  mov     rax, [rax+48h]
0x180072525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007252a  mov     rcx, rax; punkOuter
0x18007252d  lea     rdx, [rdi+38h]; ppunkMarshal
0x180072531  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180072537  mov     ebx, eax
0x180072539  test    eax, eax
0x18007253b  jz      short loc_180072548
0x18007253d  mov     rcx, rdi; void *
0x180072540  call    ??_G?$CComObject@VCDCMCreator@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CDCMCreator>::`scalar deleting destructor'(uint)
0x180072545  xor     r14d, r14d
0x180072548  mov     cs:?_DCMNonReusable@@3PEAV?$CComObject@VCDCMCreator@@@ATL@@EA, r14; ATL::CComObject<CDCMCreator> * _DCMNonReusable
0x18007254f  mov     eax, ebx
0x180072551  add     rsp, 20h
0x180072555  pop     r14
0x180072557  pop     rdi
0x180072558  pop     rbx
0x180072559  retn
```
