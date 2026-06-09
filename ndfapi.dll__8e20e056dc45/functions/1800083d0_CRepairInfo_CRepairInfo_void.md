# CRepairInfo::~CRepairInfo(void)

- ea: `0x1800083d0`
- end: `0x18000843d`
- name: `??1CRepairInfo@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CRepairInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800084c0`

## callees

- `0x180008b08`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800083ee`
- `ole32!CoTaskMemFree` at `0x1800083f8`
- `ole32!CoTaskMemFree` at `0x1800083ee`
- `ole32!CoTaskMemFree` at `0x1800083f8`

## pseudocode

```c
void __fastcall CRepairInfo::~CRepairInfo(CRepairInfo *this)
{
  *(_QWORD *)this = &CRepairInfo::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 17));
  CoTaskMemFree(*((LPVOID *)this + 1));
  FreeRepairInfos((struct tagRepairInfo *)((char *)this + 24), 1u, 0);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 36) = 0;
  memset_0((char *)this + 24, 0, 0x70u);
}

```

## disassembly

```asm
0x1800083d0  mov     [rsp+arg_0], rbx
0x1800083d5  push    rdi
0x1800083d6  sub     rsp, 20h
0x1800083da  lea     rax, ??_7CRepairInfo@@6B@; const CRepairInfo::`vftable'
0x1800083e1  mov     rdi, rcx
0x1800083e4  mov     [rcx], rax
0x1800083e7  mov     rcx, [rcx+88h]; pv
0x1800083ee  call    cs:__imp_CoTaskMemFree
0x1800083f4  mov     rcx, [rdi+8]; pv
0x1800083f8  call    cs:__imp_CoTaskMemFree
0x1800083fe  xor     r8d, r8d; int
0x180008401  lea     rcx, [rdi+18h]; pv
0x180008405  lea     edx, [r8+1]; unsigned int
0x180008409  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18000840e  xor     eax, eax
0x180008410  lea     rcx, [rdi+18h]; void *
0x180008414  xor     edx, edx; Val
0x180008416  mov     [rdi+88h], rax
0x18000841d  mov     [rdi+8], rax
0x180008421  mov     [rdi+10h], eax
0x180008424  lea     r8d, [rax+70h]; Size
0x180008428  mov     [rdi+90h], eax
0x18000842e  mov     rbx, [rsp+28h+arg_0]
0x180008433  add     rsp, 20h
0x180008437  pop     rdi
0x180008438  jmp     memset_0
```
