# CString::~CString(void)

- ea: `0x180019ee0`
- end: `0x180019f30`
- name: `??1CString@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CString *__hidden this)`
- caller_count: `94`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005c34`
- `0x180005ce4`
- `0x180005ebc`
- `0x180006a38`
- `0x180006c54`
- `0x1800078d0`
- `0x180007cb0`
- `0x1800081ec`
- `0x180008c30`
- `0x1800098ac`
- `0x180009b34`
- `0x18000b090`
- `0x18000b8fc`
- `0x18000c8c4`
- `0x18000f620`
- `0x18000fc54`
- `0x1800101b4`
- `0x18001058c`
- `0x180011500`
- `0x180011e00`
- `0x180011e90`
- `0x180012160`
- `0x1800121a4`
- `0x18001230c`
- `0x18001270c`
- `0x180012b10`
- `0x180012e94`
- `0x1800132b0`
- `0x18001387c`
- `0x180013b8c`
- `0x180013d44`
- `0x180014220`
- `0x180014604`
- `0x180014980`
- `0x180014ca8`
- `0x180014e68`
- `0x1800153b0`
- `0x180015560`
- `0x18001602c`
- `0x18001608c`
- `0x180016470`
- `0x180017060`
- `0x1800177fc`
- `0x1800180a8`
- `0x180018384`
- `0x1800184c0`
- `0x1800190e4`
- `0x1800196b0`
- `0x180019a54`
- `0x18001a888`

## callees

- `0x180001534`
- `0x180019ee0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f17`

## pseudocode

```c
void __fastcall CString::~CString(CString *this)
{
  __int64 v1; // rdx
  HLOCAL *v2; // rbx

  v1 = *((_QWORD *)this + 1);
  *(_QWORD *)this = &CString::`vftable';
  if ( v1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 12), 0xFFFFFFFF) == 1 )
    {
      v2 = (HLOCAL *)*((_QWORD *)this + 1);
      if ( v2 )
      {
        if ( *v2 )
          LocalFree(*v2);
        operator delete(v2);
      }
    }
  }
}

```

## disassembly

```asm
0x180019ee0  push    rbx
0x180019ee2  sub     rsp, 20h
0x180019ee6  mov     rdx, [rcx+8]
0x180019eea  lea     rax, ??_7CString@@6B@; const CString::`vftable'
0x180019ef1  mov     [rcx], rax
0x180019ef4  test    rdx, rdx
0x180019ef7  jz      short loc_180019F2A
0x180019ef9  or      eax, 0FFFFFFFFh
0x180019efc  lock xadd [rdx+0Ch], eax
0x180019f01  cmp     eax, 1
0x180019f04  jnz     short loc_180019F2A
0x180019f06  mov     rbx, [rcx+8]
0x180019f0a  test    rbx, rbx
0x180019f0d  jz      short loc_180019F2A
0x180019f0f  mov     rcx, [rbx]; hMem
0x180019f12  test    rcx, rcx
0x180019f15  jz      short loc_180019F1D
0x180019f17  call    cs:__imp_LocalFree
0x180019f1d  mov     edx, 18h; unsigned __int64
0x180019f22  mov     rcx, rbx; void *
0x180019f25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019f2a  add     rsp, 20h
0x180019f2e  pop     rbx
0x180019f2f  retn
```
