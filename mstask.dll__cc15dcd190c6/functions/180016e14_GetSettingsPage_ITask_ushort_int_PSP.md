# GetSettingsPage(ITask *,ushort *,int,_PSP * *)

- ea: `0x180016e14`
- end: `0x180016f35`
- name: `?GetSettingsPage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z`
- size: `289`
- prototype: `int(struct ITask *, unsigned __int16 *, int, struct _PSP **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180010098`
- `0x180016dc8`

## callees

- `0x180009ef8`
- `0x180009f38`
- `0x18000fd74`
- `0x180016e14`
- `0x180017f60`
- `0x18001b010`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageW` at `0x180016ee7`
- `COMCTL32!CreatePropertySheetPageW` at `0x180016ee7`

## pseudocode

```c
__int64 __fastcall GetSettingsPage(struct ITask *a1, unsigned __int16 *a2, int a3, struct _PSP **a4)
{
  unsigned __int16 *v8; // rdi
  int JobPath; // eax
  int v10; // ebx
  CPropPage *v11; // rax
  CPropPage *v12; // rsi
  struct _PSP *PropertySheetPageW; // rax
  void *Block; // [rsp+20h] [rbp-38h] BYREF
  __int16 v16; // [rsp+68h] [rbp+10h] BYREF

  Block = 0;
  v16 = 0;
  if ( a2 )
  {
    v8 = a2;
  }
  else
  {
    JobPath = GetJobPath(a1, (unsigned __int16 **)&Block);
    v8 = (unsigned __int16 *)Block;
    v10 = JobPath;
    if ( JobPath < 0 )
      goto LABEL_9;
  }
  v10 = ((__int64 (__fastcall *)(struct ITask *, __int16 *))a1->lpVtbl->GetTriggerCount)(a1, &v16);
  if ( v10 >= 0 )
  {
    v11 = (CPropPage *)operator new(0x2B0u);
    v12 = v11;
    if ( !v11 )
    {
LABEL_8:
      v10 = -2147024882;
      goto LABEL_9;
    }
    CPropPage::CPropPage(v11, (const unsigned __int16 *)0x193, v8);
    *((_QWORD *)v12 + 83) = a1;
    *((_DWORD *)v12 + 170) = 0;
    *(_QWORD *)v12 = &CSettingsPage::`vftable';
    *((_QWORD *)v12 + 84) = 0;
    *((_DWORD *)v12 + 171) = a3;
    ((void (__fastcall *)(struct ITask *))a1->lpVtbl->AddRef)(a1);
    PropertySheetPageW = CreatePropertySheetPageW((LPCPROPSHEETPAGEW)((char *)v12 + 8));
    if ( !PropertySheetPageW )
    {
      (**(void (__fastcall ***)(CPropPage *, __int64))v12)(v12, 1);
      goto LABEL_8;
    }
    *a4 = PropertySheetPageW;
  }
LABEL_9:
  if ( v8 != a2 )
    operator delete(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180016e14  mov     [rsp+arg_0], rbx
0x180016e19  mov     [rsp+arg_10], rbp
0x180016e1e  push    rsi
0x180016e1f  push    rdi
0x180016e20  push    r12
0x180016e22  push    r14
0x180016e24  push    r15
0x180016e26  sub     rsp, 30h
0x180016e2a  xor     eax, eax
0x180016e2c  mov     [rsp+58h+Block], 0
0x180016e35  mov     [rsp+58h+arg_8], ax
0x180016e3a  mov     r15, r9
0x180016e3d  mov     r12d, r8d
0x180016e40  mov     rbp, rdx
0x180016e43  mov     r14, rcx
0x180016e46  test    rdx, rdx
0x180016e49  jz      short loc_180016E50
0x180016e4b  mov     rdi, rdx
0x180016e4e  jmp     short loc_180016E69
0x180016e50  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x180016e55  call    ?GetJobPath@@YAJPEAUITask@@PEAPEAG@Z; GetJobPath(ITask *,ushort * *)
0x180016e5a  mov     rdi, [rsp+58h+Block]
0x180016e5f  mov     ebx, eax
0x180016e61  test    eax, eax
0x180016e63  js      loc_180016F0A
0x180016e69  mov     rax, [r14]
0x180016e6c  lea     rdx, [rsp+58h+arg_8]
0x180016e71  mov     rcx, r14
0x180016e74  mov     rax, [rax+28h]
0x180016e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e7d  mov     ebx, eax
0x180016e7f  test    eax, eax
0x180016e81  js      loc_180016F0A
0x180016e87  mov     ecx, 2B0h; Size
0x180016e8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016e91  mov     rsi, rax
0x180016e94  test    rax, rax
0x180016e97  jz      short loc_180016F05
0x180016e99  mov     r8, rdi; unsigned __int16 *
0x180016e9c  mov     edx, 193h; unsigned __int16 *
0x180016ea1  mov     rcx, rax; this
0x180016ea4  call    ??0CPropPage@@QEAA@PEBGPEAG@Z; CPropPage::CPropPage(ushort const *,ushort *)
0x180016ea9  xor     ecx, ecx
0x180016eab  mov     [rsi+298h], r14
0x180016eb2  mov     [rsi+2A8h], ecx
0x180016eb8  lea     rax, ??_7CSettingsPage@@6B@; const CSettingsPage::`vftable'
0x180016ebf  mov     [rsi], rax
0x180016ec2  mov     rcx, r14
0x180016ec5  mov     qword ptr [rsi+2A0h], 0
0x180016ed0  mov     [rsi+2ACh], r12d
0x180016ed7  mov     rax, [r14]
0x180016eda  mov     rax, [rax+8]
0x180016ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ee3  lea     rcx, [rsi+8]; constPropSheetPagePointer
0x180016ee7  call    cs:__imp_CreatePropertySheetPageW
0x180016eed  test    rax, rax
0x180016ef0  jnz     short loc_180016F30
0x180016ef2  mov     rax, [rsi]
0x180016ef5  mov     edx, 1
0x180016efa  mov     rcx, rsi
0x180016efd  mov     rax, [rax]
0x180016f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f05  mov     ebx, 8007000Eh
0x180016f0a  cmp     rdi, rbp
0x180016f0d  jz      short loc_180016F17
0x180016f0f  mov     rcx, rdi; Block
0x180016f12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016f17  mov     rbp, [rsp+58h+arg_10]
0x180016f1c  mov     eax, ebx
0x180016f1e  mov     rbx, [rsp+58h+arg_0]
0x180016f23  add     rsp, 30h
0x180016f27  pop     r15
0x180016f29  pop     r14
0x180016f2b  pop     r12
0x180016f2d  pop     rdi
0x180016f2e  pop     rsi
0x180016f2f  retn
0x180016f30  mov     [r15], rax
0x180016f33  jmp     short loc_180016F0A
```
