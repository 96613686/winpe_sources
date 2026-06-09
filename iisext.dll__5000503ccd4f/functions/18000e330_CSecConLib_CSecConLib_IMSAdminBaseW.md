# CSecConLib::CSecConLib(IMSAdminBaseW *)

- ea: `0x18000e330`
- end: `0x18000e379`
- name: `??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z`
- size: `73`
- prototype: `CSecConLib *__fastcall(CSecConLib *__hidden this, struct IMSAdminBaseW *)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800086f0`
- `0x180008770`
- `0x180009200`
- `0x180009260`
- `0x1800092e0`
- `0x180009360`
- `0x1800093c0`
- `0x180009440`
- `0x180009650`
- `0x180009700`
- `0x1800097b0`
- `0x180009950`
- `0x180009a10`
- `0x180009a70`

## callees

- `0x180010570`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000e361`
- `ATL!__imp_AtlComPtrAssign` at `0x18000e361`

## pseudocode

```c
CSecConLib *__fastcall CSecConLib::CSecConLib(CSecConLib *this, struct IMSAdminBaseW *a2)
{
  CSecConLib *result; // rax

  *(_QWORD *)this = &CSecConLib::`vftable';
  CSafeAutoCriticalSection::CSafeAutoCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_QWORD *)this + 7) = 0;
  AtlComPtrAssign((char *)this + 56, a2);
  result = this;
  *((_BYTE *)this + 64) = 1;
  return result;
}

```

## disassembly

```asm
0x18000e330  mov     [rsp+arg_0], rbx
0x18000e335  push    rdi
0x18000e336  sub     rsp, 20h
0x18000e33a  lea     rax, ??_7CSecConLib@@6B@; const CSecConLib::`vftable'
0x18000e341  mov     rdi, rcx
0x18000e344  mov     [rcx], rax
0x18000e347  mov     rbx, rdx
0x18000e34a  add     rcx, 8; lpCriticalSection
0x18000e34e  call    ??0CSafeAutoCriticalSection@@QEAA@XZ; CSafeAutoCriticalSection::CSafeAutoCriticalSection(void)
0x18000e353  lea     rcx, [rdi+38h]
0x18000e357  mov     rdx, rbx
0x18000e35a  mov     qword ptr [rcx], 0
0x18000e361  call    cs:__imp_AtlComPtrAssign
0x18000e367  mov     rbx, [rsp+28h+arg_0]
0x18000e36c  mov     rax, rdi
0x18000e36f  mov     byte ptr [rdi+40h], 1
0x18000e373  add     rsp, 20h
0x18000e377  pop     rdi
0x18000e378  retn
```
