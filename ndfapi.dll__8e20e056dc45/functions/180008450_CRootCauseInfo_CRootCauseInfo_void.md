# CRootCauseInfo::~CRootCauseInfo(void)

- ea: `0x180008450`
- end: `0x1800084a9`
- name: `??1CRootCauseInfo@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CRootCauseInfo *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180008c08`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000846b`
- `ole32!CoTaskMemFree` at `0x18000846b`

## pseudocode

```c
void __fastcall CRootCauseInfo::~CRootCauseInfo(CRootCauseInfo *this)
{
  *(_QWORD *)this = &CRootCauseInfo::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 1));
  FreeRootCauseInfos((struct tagRootCauseInfo *)((char *)this + 24), 1u, 0);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  memset_0((char *)this + 24, 0, 0x40u);
}

```

## disassembly

```asm
0x180008450  mov     [rsp+arg_0], rbx
0x180008455  push    rdi
0x180008456  sub     rsp, 20h
0x18000845a  lea     rax, ??_7CRootCauseInfo@@6B@; const CRootCauseInfo::`vftable'
0x180008461  mov     rdi, rcx
0x180008464  mov     [rcx], rax
0x180008467  mov     rcx, [rcx+8]; pv
0x18000846b  call    cs:__imp_CoTaskMemFree
0x180008471  xor     r8d, r8d; int
0x180008474  lea     rcx, [rdi+18h]; pv
0x180008478  lea     edx, [r8+1]; unsigned int
0x18000847c  call    ?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z; FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)
0x180008481  xor     edx, edx; Val
0x180008483  mov     qword ptr [rdi+8], 0
0x18000848b  lea     rcx, [rdi+18h]; void *
0x18000848f  mov     dword ptr [rdi+10h], 0
0x180008496  lea     r8d, [rdx+40h]; Size
0x18000849a  mov     rbx, [rsp+28h+arg_0]
0x18000849f  add     rsp, 20h
0x1800084a3  pop     rdi
0x1800084a4  jmp     memset_0
```
