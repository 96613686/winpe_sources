# CRootCauseInfo::`vector deleting destructor'(uint)

- ea: `0x180008500`
- end: `0x180008578`
- name: `??_ECRootCauseInfo@@UEAAPEAXI@Z`
- size: `120`
- prototype: `CRootCauseInfo *__fastcall(CRootCauseInfo *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180008500`
- `0x180008c08`
- `0x18001f652`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000855f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000855f`
- `ole32!CoTaskMemFree` at `0x180008522`
- `ole32!CoTaskMemFree` at `0x180008522`

## pseudocode

```c
CRootCauseInfo *__fastcall CRootCauseInfo::`vector deleting destructor'(CRootCauseInfo *this, char a2)
{
  *(_QWORD *)this = &CRootCauseInfo::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 1));
  FreeRootCauseInfos((struct tagRootCauseInfo *)((char *)this + 24), 1u, 0);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  memset_0((char *)this + 24, 0, 0x40u);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008500  mov     [rsp+arg_0], rbx
0x180008505  mov     [rsp+arg_8], rsi
0x18000850a  push    rdi
0x18000850b  sub     rsp, 20h
0x18000850f  lea     rax, ??_7CRootCauseInfo@@6B@; const CRootCauseInfo::`vftable'
0x180008516  mov     rsi, rcx
0x180008519  mov     [rcx], rax
0x18000851c  mov     edi, edx
0x18000851e  mov     rcx, [rcx+8]; pv
0x180008522  call    cs:__imp_CoTaskMemFree
0x180008528  xor     r8d, r8d; int
0x18000852b  lea     rcx, [rsi+18h]; pv
0x18000852f  lea     edx, [r8+1]; unsigned int
0x180008533  call    ?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z; FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)
0x180008538  xor     edx, edx; Val
0x18000853a  mov     qword ptr [rsi+8], 0
0x180008542  lea     rcx, [rsi+18h]; void *
0x180008546  mov     dword ptr [rsi+10h], 0
0x18000854d  lea     r8d, [rdx+40h]; Size
0x180008551  call    memset_0
0x180008556  test    dil, 1
0x18000855a  jz      short loc_180008565
0x18000855c  mov     rcx, rsi
0x18000855f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008565  mov     rbx, [rsp+28h+arg_0]
0x18000856a  mov     rax, rsi
0x18000856d  mov     rsi, [rsp+28h+arg_8]
0x180008572  add     rsp, 20h
0x180008576  pop     rdi
0x180008577  retn
```
