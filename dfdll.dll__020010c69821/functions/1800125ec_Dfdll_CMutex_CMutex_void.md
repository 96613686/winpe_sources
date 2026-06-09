# Dfdll::CMutex::~CMutex(void)

- ea: `0x1800125ec`
- end: `0x180012656`
- name: `??1CMutex@Dfdll@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(Dfdll::CMutex *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012660`
- `0x18001f8f0`

## callees

- `0x1800125ec`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180012608`
- `KERNEL32!CloseHandle` at `0x180012608`

## pseudocode

```c
void __fastcall Dfdll::CMutex::~CMutex(Dfdll::CMutex *this)
{
  void *v2; // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &Dfdll::CMutex::`vftable';
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    CloseHandle(v2);
  *(_QWORD *)this = &Dfdll::CSynchronizationObject::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CPointerHolder<Dfdll::CString>::`vftable';
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v3 )
    (**v3)(v3, 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x1800125ec  push    rbx
0x1800125ee  sub     rsp, 20h
0x1800125f2  mov     rbx, rcx
0x1800125f5  lea     rax, ??_7CMutex@Dfdll@@6B@
0x1800125fc  mov     [rcx], rax
0x1800125ff  mov     rcx, [rcx+18h]; hObject
0x180012603  test    rcx, rcx
0x180012606  jz      short loc_18001260E
0x180012608  call    cs:__imp_CloseHandle
0x18001260e  lea     rax, ??_7CSynchronizationObject@Dfdll@@6B@
0x180012615  mov     [rbx], rax
0x180012618  lea     rax, ??_7?$CPointerHolder@VCString@Dfdll@@@Dfdll@@6B@
0x18001261f  mov     [rbx+8], rax
0x180012623  mov     rcx, [rbx+10h]
0x180012627  test    rcx, rcx
0x18001262a  jz      short loc_18001263D
0x18001262c  mov     rax, [rcx]
0x18001262f  mov     edx, 1
0x180012634  mov     rax, [rax]
0x180012637  call    cs:__guard_dispatch_icall_fptr
0x18001263d  and     qword ptr [rbx+10h], 0
0x180012642  lea     rax, ??_7CObject@Dfdll@@6B@
0x180012649  mov     [rbx+8], rax
0x18001264d  mov     [rbx], rax
0x180012650  add     rsp, 20h
0x180012654  pop     rbx
0x180012655  retn
```
