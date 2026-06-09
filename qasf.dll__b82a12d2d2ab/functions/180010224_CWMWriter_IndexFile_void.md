# CWMWriter::IndexFile(void)

- ea: `0x180010224`
- end: `0x180010353`
- name: `?IndexFile@CWMWriter@@IEAAJXZ`
- size: `303`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011dac`

## callees

- `0x180001020`
- `0x180001460`
- `0x18000e200`
- `0x180010224`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateIndexer` at `0x18001028f`
- `WMVCore!WMCreateIndexer` at `0x18001028f`
- `KERNEL32!CloseHandle` at `0x180010307`
- `KERNEL32!CloseHandle` at `0x180010307`
- `KERNEL32!CreateEventW` at `0x1800102a7`
- `KERNEL32!CreateEventW` at `0x1800102a7`
- `KERNEL32!WaitForSingleObject` at `0x1800102f6`
- `KERNEL32!WaitForSingleObject` at `0x1800102f6`

## pseudocode

```c
HRESULT __fastcall CWMWriter::IndexFile(CWMWriter *this)
{
  CWMWriterIndexerCallback *v2; // rax
  HRESULT result; // eax
  char *v4; // rsi
  int v5; // ebx
  HANDLE hHandle; // [rsp+30h] [rbp-28h] BYREF
  IWMIndexer *ppIndexer; // [rsp+38h] [rbp-20h] BYREF

  v2 = (CWMWriterIndexerCallback *)operator new(0x28u);
  if ( v2 )
    v2 = CWMWriterIndexerCallback::CWMWriterIndexerCallback(v2, this);
  if ( !v2 )
    return -2147024882;
  v4 = (char *)v2 + 24;
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v2 + 3) + 8LL))((__int64)v2 + 24);
  ppIndexer = 0;
  result = WMCreateIndexer(&ppIndexer);
  if ( result >= 0 )
  {
    hHandle = CreateEventW(0, 0, 0, 0);
    if ( hHandle )
    {
      v5 = ((__int64 (__fastcall *)(IWMIndexer *, _QWORD, char *, HANDLE *))ppIndexer->lpVtbl->StartIndexing)(
             ppIndexer,
             *((_QWORD *)this + 36),
             v4,
             &hHandle);
      if ( v5 >= 0 )
      {
        *((_DWORD *)this + 52) = 0;
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        v5 = *((_DWORD *)this + 52);
      }
      CloseHandle(hHandle);
    }
    else
    {
      v5 = -2147024882;
    }
    ((void (__fastcall *)(IWMIndexer *))ppIndexer->lpVtbl->Release)(ppIndexer);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180010224  mov     [rsp+arg_8], rbx
0x180010229  mov     [rsp+arg_10], rsi
0x18001022e  push    rdi
0x18001022f  sub     rsp, 50h
0x180010233  mov     rax, cs:__security_cookie
0x18001023a  xor     rax, rsp
0x18001023d  mov     [rsp+58h+var_18], rax
0x180010242  mov     rdi, rcx
0x180010245  mov     ecx, 28h ; '('; Size
0x18001024a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001024f  test    rax, rax
0x180010252  jz      short loc_18001025F
0x180010254  mov     rdx, rdi; struct CWMWriter *
0x180010257  mov     rcx, rax; this
0x18001025a  call    ??0CWMWriterIndexerCallback@@QEAA@PEAVCWMWriter@@@Z; CWMWriterIndexerCallback::CWMWriterIndexerCallback(CWMWriter *)
0x18001025f  test    rax, rax
0x180010262  jnz     short loc_18001026E
0x180010264  mov     eax, 8007000Eh
0x180010269  jmp     loc_180010336
0x18001026e  lea     rsi, [rax+18h]
0x180010272  mov     rax, [rsi]
0x180010275  mov     rcx, rsi
0x180010278  mov     rax, [rax+8]
0x18001027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010281  mov     [rsp+58h+ppIndexer], 0
0x18001028a  lea     rcx, [rsp+58h+ppIndexer]; ppIndexer
0x18001028f  call    cs:__imp_WMCreateIndexer
0x180010295  test    eax, eax
0x180010297  js      loc_180010336
0x18001029d  xor     r9d, r9d; lpName
0x1800102a0  xor     r8d, r8d; bInitialState
0x1800102a3  xor     edx, edx; bManualReset
0x1800102a5  xor     ecx, ecx; lpEventAttributes
0x1800102a7  call    cs:__imp_CreateEventW
0x1800102ad  mov     [rsp+58h+hHandle], rax
0x1800102b2  test    rax, rax
0x1800102b5  jnz     short loc_1800102BE
0x1800102b7  mov     ebx, 8007000Eh
0x1800102bc  jmp     short loc_18001030D
0x1800102be  mov     rcx, [rsp+58h+ppIndexer]
0x1800102c3  mov     rax, [rcx]
0x1800102c6  lea     r9, [rsp+58h+hHandle]
0x1800102cb  mov     r8, rsi
0x1800102ce  mov     rdx, [rdi+120h]
0x1800102d5  mov     rax, [rax+18h]
0x1800102d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102de  mov     ebx, eax
0x1800102e0  test    eax, eax
0x1800102e2  js      short loc_180010302
0x1800102e4  mov     dword ptr [rdi+0D0h], 0
0x1800102ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800102f1  mov     rcx, [rsp+58h+hHandle]; hHandle
0x1800102f6  call    cs:__imp_WaitForSingleObject
0x1800102fc  mov     ebx, [rdi+0D0h]
0x180010302  mov     rcx, [rsp+58h+hHandle]; hObject
0x180010307  call    cs:__imp_CloseHandle
0x18001030d  mov     rcx, [rsp+58h+ppIndexer]
0x180010312  mov     rax, [rcx]
0x180010315  mov     rax, [rax+10h]
0x180010319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001031e  mov     rax, [rsi]
0x180010321  mov     rcx, rsi
0x180010324  mov     rax, [rax+10h]
0x180010328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001032d  mov     eax, ebx
0x18001032f  jmp     short loc_180010336
0x180010331  mov     eax, 8007007Eh
0x180010336  mov     rcx, [rsp+58h+var_18]
0x18001033b  xor     rcx, rsp; StackCookie
0x18001033e  call    __security_check_cookie
0x180010343  mov     rbx, [rsp+58h+arg_8]
0x180010348  mov     rsi, [rsp+58h+arg_10]
0x18001034d  add     rsp, 50h
0x180010351  pop     rdi
0x180010352  retn
```
