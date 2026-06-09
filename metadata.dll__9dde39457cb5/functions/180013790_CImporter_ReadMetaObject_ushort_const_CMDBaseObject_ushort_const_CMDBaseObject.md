# CImporter::ReadMetaObject(ushort const *,CMDBaseObject *,ushort const *,CMDBaseObject * *)

- ea: `0x180013790`
- end: `0x180013925`
- name: `?ReadMetaObject@CImporter@@AEAAJPEBGPEAVCMDBaseObject@@0PEAPEAV2@@Z`
- size: `405`
- prototype: `int(CImporter *__hidden this, const unsigned __int16 *, struct CMDBaseObject *, const unsigned __int16 *, struct CMDBaseObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180012ec0`

## callees

- `0x180004290`
- `0x180008a08`
- `0x180008a14`
- `0x1800132b4`
- `0x180013790`
- `0x180014f60`
- `0x180015430`
- `0x180031010`

## import_xrefs

- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x18001389d`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x18001389d`

## pseudocode

```c
__int64 __fastcall CImporter::ReadMetaObject(
        CImporter *this,
        const unsigned __int16 *a2,
        struct CMDBaseObject *a3,
        const unsigned __int16 *a4,
        struct CMDBaseObject **a5)
{
  __int64 v6; // rax
  int inserted; // ebx
  __int64 v10; // rdi
  unsigned __int16 *v11; // r12
  CImporter *v12; // rcx
  unsigned __int16 *v13; // rsi
  int v14; // ebx
  CImporter *v15; // rcx
  int v16; // eax
  CImporter *v17; // rcx
  struct CMDBaseObject *ChildObject; // rdi
  struct CMDBaseObject *BaseObject; // rax
  char *v21; // [rsp+20h] [rbp-58h] BYREF
  int v22[20]; // [rsp+28h] [rbp-50h] BYREF
  CImporter *v23; // [rsp+80h] [rbp+8h] BYREF

  v23 = this;
  v22[0] = 0;
  v6 = -1;
  inserted = -2147024882;
  do
    ++v6;
  while ( a2[v6] );
  v10 = -1;
  do
    ++v10;
  while ( a4[v10] );
  v11 = (unsigned __int16 *)operator new[](saturated_mul((int)v6 + 1, 2u));
  if ( v11 )
  {
    v13 = (unsigned __int16 *)operator new[](saturated_mul((int)v10 + 1, 2u));
    if ( v13 )
    {
      LODWORD(v21) = 0;
      LODWORD(v23) = 0;
      do
      {
        v14 = CImporter::EnumMDPath(v12, a2, v11, (int *)&v21);
        v16 = CImporter::EnumMDPath(v15, a4, v13, (int *)&v23);
      }
      while ( v14 );
      while ( v16 == 1 )
      {
        v21 = (char *)v13;
        ChildObject = CMDBaseObject::GetChildObject(a3, &v21, v22, 1);
        if ( !ChildObject )
        {
          BaseObject = CMDBaseObject::CreateBaseObject(v13);
          ChildObject = BaseObject;
          if ( !BaseObject )
          {
            inserted = -2147024882;
            goto LABEL_19;
          }
          if ( !STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
          {
            inserted = -2147024882;
LABEL_16:
            (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))ChildObject)(ChildObject, 1);
            goto LABEL_19;
          }
          inserted = CMDBaseObject::InsertChildObject(a3, ChildObject);
          if ( inserted < 0 )
            goto LABEL_16;
        }
        a3 = ChildObject;
        v16 = CImporter::EnumMDPath(v17, a4, v13, (int *)&v23);
      }
      inserted = 0;
      *a5 = a3;
    }
LABEL_19:
    operator delete(v11);
    if ( v13 )
      operator delete(v13);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180013790  mov     [rsp+arg_0], rcx
0x180013795  push    rbx
0x180013796  push    rbp
0x180013797  push    rsi
0x180013798  push    rdi
0x180013799  push    r12
0x18001379b  push    r13
0x18001379d  push    r14
0x18001379f  push    r15
0x1800137a1  sub     rsp, 38h
0x1800137a5  xor     r13d, r13d
0x1800137a8  mov     r14, r9
0x1800137ab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800137af  mov     [rsp+78h+var_50], r13d
0x1800137b4  mov     rax, rsi
0x1800137b7  mov     rbp, r8
0x1800137ba  mov     r15, rdx
0x1800137bd  mov     ebx, 8007000Eh
0x1800137c2  inc     rax
0x1800137c5  cmp     [rdx+rax*2], r13w
0x1800137ca  jnz     short loc_1800137C2
0x1800137cc  mov     rdi, rsi
0x1800137cf  inc     rdi
0x1800137d2  cmp     [r9+rdi*2], r13w
0x1800137d7  jnz     short loc_1800137CF
0x1800137d9  inc     eax
0x1800137db  movsxd  rcx, eax
0x1800137de  mov     eax, 2
0x1800137e3  mul     rcx
0x1800137e6  cmovb   rax, rsi
0x1800137ea  mov     rcx, rax; unsigned __int64
0x1800137ed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800137f2  mov     r12, rax
0x1800137f5  test    rax, rax
0x1800137f8  jz      loc_180013912
0x1800137fe  lea     eax, [rdi+1]
0x180013801  movsxd  rcx, eax
0x180013804  mov     eax, 2
0x180013809  mul     rcx
0x18001380c  cmovb   rax, rsi
0x180013810  mov     rcx, rax; unsigned __int64
0x180013813  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013818  mov     rsi, rax
0x18001381b  test    rax, rax
0x18001381e  jz      loc_1800138FD
0x180013824  mov     dword ptr [rsp+78h+var_58], r13d
0x180013829  mov     dword ptr [rsp+78h+arg_0], r13d
0x180013831  lea     r9, [rsp+78h+var_58]; int *
0x180013836  mov     r8, r12; unsigned __int16 *
0x180013839  mov     rdx, r15; unsigned __int16 *
0x18001383c  call    ?EnumMDPath@CImporter@@AEAAHPEBGPEAGPEAH@Z; CImporter::EnumMDPath(ushort const *,ushort *,int *)
0x180013841  lea     r9, [rsp+78h+arg_0]; int *
0x180013849  mov     r8, rsi; unsigned __int16 *
0x18001384c  mov     rdx, r14; unsigned __int16 *
0x18001384f  mov     ebx, eax
0x180013851  call    ?EnumMDPath@CImporter@@AEAAHPEBGPEAGPEAH@Z; CImporter::EnumMDPath(ushort const *,ushort *,int *)
0x180013856  test    ebx, ebx
0x180013858  jnz     short loc_180013831
0x18001385a  lea     r15d, [rbx+1]
0x18001385e  cmp     eax, r15d
0x180013861  jnz     loc_1800138EF
0x180013867  mov     r9d, r15d; int
0x18001386a  mov     [rsp+78h+var_58], rsi
0x18001386f  lea     r8, [rsp+78h+var_50]; int *
0x180013874  mov     rcx, rbp; this
0x180013877  lea     rdx, [rsp+78h+var_58]; char **
0x18001387c  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x180013881  mov     rdi, rax
0x180013884  test    rax, rax
0x180013887  jnz     short loc_1800138B8
0x180013889  mov     rcx, rsi; unsigned __int16 *
0x18001388c  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z; CMDBaseObject::CreateBaseObject(ushort *)
0x180013891  mov     rdi, rax
0x180013894  test    rax, rax
0x180013897  jz      short loc_1800138E8
0x180013899  lea     rcx, [rax+8]
0x18001389d  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x1800138a3  test    eax, eax
0x1800138a5  jz      short loc_1800138D0
0x1800138a7  mov     rdx, rdi; struct CMDBaseObject *
0x1800138aa  mov     rcx, rbp; this
0x1800138ad  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x1800138b2  mov     ebx, eax
0x1800138b4  test    eax, eax
0x1800138b6  js      short loc_1800138D5
0x1800138b8  lea     r9, [rsp+78h+arg_0]; int *
0x1800138c0  mov     r8, rsi; unsigned __int16 *
0x1800138c3  mov     rdx, r14; unsigned __int16 *
0x1800138c6  mov     rbp, rdi
0x1800138c9  call    ?EnumMDPath@CImporter@@AEAAHPEBGPEAGPEAH@Z; CImporter::EnumMDPath(ushort const *,ushort *,int *)
0x1800138ce  jmp     short loc_18001385E
0x1800138d0  mov     ebx, 8007000Eh
0x1800138d5  mov     rax, [rdi]
0x1800138d8  mov     edx, r15d
0x1800138db  mov     rcx, rdi
0x1800138de  mov     rax, [rax]
0x1800138e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138e6  jmp     short loc_1800138FD
0x1800138e8  mov     ebx, 8007000Eh
0x1800138ed  jmp     short loc_1800138FD
0x1800138ef  mov     rax, [rsp+78h+arg_20]
0x1800138f7  mov     ebx, r13d
0x1800138fa  mov     [rax], rbp
0x1800138fd  mov     rcx, r12; Block
0x180013900  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013905  test    rsi, rsi
0x180013908  jz      short loc_180013912
0x18001390a  mov     rcx, rsi; Block
0x18001390d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013912  mov     eax, ebx
0x180013914  add     rsp, 38h
0x180013918  pop     r15
0x18001391a  pop     r14
0x18001391c  pop     r13
0x18001391e  pop     r12
0x180013920  pop     rdi
0x180013921  pop     rsi
0x180013922  pop     rbp
0x180013923  pop     rbx
0x180013924  retn
```
