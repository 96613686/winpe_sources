# GetGeneralPage(ITask *,ushort *,int,_PSP * *)

- ea: `0x1800105a8`
- end: `0x18001065b`
- name: `?GetGeneralPage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct ITask *, unsigned __int16 *, int, struct _PSP **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010098`
- `0x180010478`

## callees

- `0x180009ef8`
- `0x180009f38`
- `0x18000fd74`
- `0x180010264`
- `0x1800105a8`
- `0x18001b010`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageW` at `0x180010617`
- `COMCTL32!CreatePropertySheetPageW` at `0x180010617`

## pseudocode

```c
__int64 __fastcall GetGeneralPage(struct ITask *a1, unsigned __int16 *a2, int a3, struct _PSP **a4)
{
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rdi
  int JobPath; // eax
  CGeneralPage *v11; // rax
  CGeneralPage *v12; // rax
  CGeneralPage *v13; // r14
  struct _PSP *PropertySheetPageW; // rax
  void *Block; // [rsp+68h] [rbp+10h] BYREF

  Block = 0;
  if ( a2 )
  {
    v8 = 0;
    v9 = a2;
  }
  else
  {
    JobPath = GetJobPath(a1, (unsigned __int16 **)&Block);
    v9 = (unsigned __int16 *)Block;
    v8 = JobPath;
    if ( JobPath < 0 )
      goto LABEL_9;
  }
  v11 = (CGeneralPage *)operator new(0x318u);
  if ( !v11 )
    goto LABEL_8;
  v12 = CGeneralPage::CGeneralPage(v11, a1, v9, a3);
  v13 = v12;
  if ( !v12 )
    goto LABEL_8;
  PropertySheetPageW = CreatePropertySheetPageW((LPCPROPSHEETPAGEW)((char *)v12 + 8));
  if ( !PropertySheetPageW )
  {
    (**(void (__fastcall ***)(CGeneralPage *, __int64))v13)(v13, 1);
LABEL_8:
    v8 = -2147024882;
    goto LABEL_9;
  }
  *a4 = PropertySheetPageW;
LABEL_9:
  if ( v9 != a2 )
    operator delete(v9);
  return v8;
}

```

## disassembly

```asm
0x1800105a8  push    rbx
0x1800105aa  push    rbp
0x1800105ab  push    rsi
0x1800105ac  push    rdi
0x1800105ad  push    r14
0x1800105af  push    r15
0x1800105b1  sub     rsp, 28h
0x1800105b5  mov     [rsp+58h+Block], 0
0x1800105be  mov     r15, r9
0x1800105c1  mov     r14d, r8d
0x1800105c4  mov     rsi, rdx
0x1800105c7  mov     rbp, rcx
0x1800105ca  test    rdx, rdx
0x1800105cd  jz      short loc_1800105D6
0x1800105cf  xor     ebx, ebx
0x1800105d1  mov     rdi, rdx
0x1800105d4  jmp     short loc_1800105EB
0x1800105d6  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x1800105db  call    ?GetJobPath@@YAJPEAUITask@@PEAPEAG@Z; GetJobPath(ITask *,ushort * *)
0x1800105e0  mov     rdi, [rsp+58h+Block]
0x1800105e5  mov     ebx, eax
0x1800105e7  test    eax, eax
0x1800105e9  js      short loc_18001063A
0x1800105eb  mov     ecx, 318h; Size
0x1800105f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800105f5  test    rax, rax
0x1800105f8  jz      short loc_180010635
0x1800105fa  mov     r9d, r14d; int
0x1800105fd  mov     r8, rdi; unsigned __int16 *
0x180010600  mov     rdx, rbp; struct ITask *
0x180010603  mov     rcx, rax; this
0x180010606  call    ??0CGeneralPage@@QEAA@PEAUITask@@PEAGH@Z; CGeneralPage::CGeneralPage(ITask *,ushort *,int)
0x18001060b  mov     r14, rax
0x18001060e  test    rax, rax
0x180010611  jz      short loc_180010635
0x180010613  lea     rcx, [rax+8]; constPropSheetPagePointer
0x180010617  call    cs:__imp_CreatePropertySheetPageW
0x18001061d  test    rax, rax
0x180010620  jnz     short loc_180010656
0x180010622  mov     rcx, [r14]
0x180010625  mov     edx, 1
0x18001062a  mov     rax, [rcx]
0x18001062d  mov     rcx, r14
0x180010630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010635  mov     ebx, 8007000Eh
0x18001063a  cmp     rdi, rsi
0x18001063d  jz      short loc_180010647
0x18001063f  mov     rcx, rdi; Block
0x180010642  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010647  mov     eax, ebx
0x180010649  add     rsp, 28h
0x18001064d  pop     r15
0x18001064f  pop     r14
0x180010651  pop     rdi
0x180010652  pop     rsi
0x180010653  pop     rbp
0x180010654  pop     rbx
0x180010655  retn
0x180010656  mov     [r15], rax
0x180010659  jmp     short loc_18001063A
```
