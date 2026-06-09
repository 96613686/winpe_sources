# CPersistErrorCache::Exit(long,ulong)

- ea: `0x180016698`
- end: `0x180016719`
- name: `?Exit@CPersistErrorCache@@QEAAJJK@Z`
- size: `129`
- prototype: `__int64 __fastcall(CPersistErrorCache *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016584`
- `0x1800165e8`

## callees

- `0x180002770`
- `0x180016128`
- `0x180016698`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800166c9`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800166c9`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800166e0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800166e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistErrorCache::Exit(CPersistErrorCache *this, signed int a2, unsigned int a3)
{
  IErrorInfo *perrinfo; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 < 0 && !*((_QWORD *)this + 1) )
  {
    perrinfo = 0;
    if ( GetErrorInfo(0, &perrinfo) )
      CPersistErrorCache::AddInternalError(this, a2, a3);
    else
      SetErrorInfo(0, perrinfo);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
  }
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180016698  mov     rax, rsp
0x18001669b  mov     [rax+8], rbx
0x18001669f  mov     [rax+10h], rsi
0x1800166a3  push    rdi
0x1800166a4  sub     rsp, 20h
0x1800166a8  mov     esi, r8d
0x1800166ab  mov     ebx, edx
0x1800166ad  mov     rdi, rcx
0x1800166b0  test    edx, edx
0x1800166b2  jns     short loc_180016706
0x1800166b4  cmp     qword ptr [rcx+8], 0
0x1800166b9  jnz     short loc_180016706
0x1800166bb  mov     qword ptr [rax+20h], 0
0x1800166c3  lea     rdx, [rax+20h]; pperrinfo
0x1800166c7  xor     ecx, ecx; dwReserved
0x1800166c9  call    cs:__imp_GetErrorInfo
0x1800166d0  nop     dword ptr [rax+rax+00h]
0x1800166d5  test    eax, eax
0x1800166d7  jnz     short loc_1800166EE
0x1800166d9  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x1800166de  xor     ecx, ecx; dwReserved
0x1800166e0  call    cs:__imp_SetErrorInfo
0x1800166e7  nop     dword ptr [rax+rax+00h]
0x1800166ec  jmp     short loc_1800166FC
0x1800166ee  mov     r8d, esi; unsigned int
0x1800166f1  mov     edx, ebx; int
0x1800166f3  mov     rcx, rdi; this
0x1800166f6  call    ?AddInternalError@CPersistErrorCache@@QEAAXJK@Z; CPersistErrorCache::AddInternalError(long,ulong)
0x1800166fb  nop
0x1800166fc  lea     rcx, [rsp+28h+perrinfo]
0x180016701  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180016706  mov     eax, ebx
0x180016708  mov     rbx, [rsp+28h+arg_0]
0x18001670d  mov     rsi, [rsp+28h+arg_8]
0x180016712  add     rsp, 20h
0x180016716  pop     rdi
0x180016717  retn
```
