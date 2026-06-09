# MakeTreeCopy(CMDBaseObject *,CMDBaseObject * &,char *,int)

- ea: `0x1800209e8`
- end: `0x180020be0`
- name: `?MakeTreeCopy@@YAJPEAVCMDBaseObject@@AEAPEAV1@PEADH@Z`
- size: `504`
- prototype: `__int64 __fastcall(struct CMDBaseObject *, struct CMDBaseObject **, char *, int)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x18001c580`
- `0x18001ca3c`
- `0x1800209e8`
- `0x180020be8`

## callees

- `0x1800035d0`
- `0x18000363c`
- `0x180003678`
- `0x1800053f0`
- `0x180007574`
- `0x180007810`
- `0x180014ef8`
- `0x180014f60`
- `0x180015430`
- `0x1800156ec`
- `0x1800209e8`
- `0x180031010`

## import_xrefs

- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180020a5c`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180020a5c`

## pseudocode

```c
__int64 __fastcall MakeTreeCopy(struct CMDBaseObject *a1, struct CMDBaseObject **a2, char *a3, int a4)
{
  char *Name; // rcx
  struct CMDBaseObject *BaseObject; // rax
  CMDBaseObject *v9; // rdi
  int TreeCopy; // ebx
  void (__fastcall **v11)(CMDBaseObject *, __int64); // rax
  int IsSchemaObject; // eax
  void **MainDataBuffer; // rax
  void **v15; // r15
  unsigned int v16; // esi
  unsigned int AllDataObjects; // r12d
  char *v18; // rdx
  _QWORD **v19; // rcx
  _QWORD *v20; // rax
  struct CMDBaseData *v21; // rdx
  _QWORD *v22; // rcx
  unsigned int v23; // r8d
  unsigned int v24; // esi
  struct CMDBaseObject *v25; // rax
  struct CMDBaseObject *v26; // [rsp+A0h] [rbp+18h] BYREF

  v26 = 0;
  if ( !a3 )
  {
    if ( !CMDBaseObject::GetName(a1, 1, 0) )
    {
LABEL_8:
      TreeCopy = -2147024882;
      *a2 = 0;
      return (unsigned int)TreeCopy;
    }
    Name = CMDBaseObject::GetName(a1, 1, 0);
    goto LABEL_4;
  }
  Name = a3;
  if ( a4 )
  {
LABEL_4:
    BaseObject = CMDBaseObject::CreateBaseObject((unsigned __int16 *)Name);
    goto LABEL_7;
  }
  BaseObject = CMDBaseObject::CreateBaseObject(a3);
LABEL_7:
  v9 = BaseObject;
  if ( !BaseObject )
    goto LABEL_8;
  if ( !STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
  {
    TreeCopy = -2147024882;
    (**(void (__fastcall ***)(CMDBaseObject *, __int64))v9)(v9, 1);
LABEL_11:
    v11 = *(void (__fastcall ***)(CMDBaseObject *, __int64))v9;
    *a2 = 0;
    (*v11)(v9, 1);
    return (unsigned int)TreeCopy;
  }
  IsSchemaObject = CMDBaseObject::IsSchemaObject(a1);
  TreeCopy = IsSchemaObject;
  if ( IsSchemaObject < 0 )
    goto LABEL_11;
  MainDataBuffer = GetMainDataBuffer(IsSchemaObject == 0);
  v15 = MainDataBuffer;
  if ( !MainDataBuffer )
  {
    TreeCopy = -2147024882;
    goto LABEL_11;
  }
  TreeCopy = 0;
  v16 = 0;
  AllDataObjects = CMDBaseObject::GetAllDataObjects(a1, MainDataBuffer, 0, 0, 0, 0, 0, 0);
  if ( AllDataObjects )
  {
    do
    {
      if ( TreeCopy < 0 )
        break;
      v18 = (char *)*v15;
      if ( v16 == *((_DWORD *)*v15 + 24) + 1 && (v19 = (_QWORD **)*((_QWORD *)v18 + 13)) != 0 )
      {
        if ( *v19 != (_QWORD *)(v18 + 80) )
        {
          *((_DWORD *)v18 + 24) = v16;
          v20 = *v19;
LABEL_27:
          *((_QWORD *)v18 + 13) = v20;
          v21 = (struct CMDBaseData *)*(v20 - 2);
          goto LABEL_28;
        }
      }
      else
      {
        *((_DWORD *)v18 + 24) = v16;
        v22 = v18 + 80;
        v20 = (_QWORD *)*((_QWORD *)v18 + 10);
        v23 = v16;
        if ( v16 )
        {
          while ( v20 != v22 )
          {
            v20 = (_QWORD *)*v20;
            if ( !--v23 )
              goto LABEL_26;
          }
        }
        else
        {
LABEL_26:
          if ( v20 != v22 )
            goto LABEL_27;
        }
      }
      *((_DWORD *)v18 + 24) = 0;
      *((_QWORD *)v18 + 13) = 0;
      v21 = 0;
LABEL_28:
      ++v16;
      TreeCopy = CMDBaseObject::SetDataObject(v9, v21);
    }
    while ( v16 < AllDataObjects );
  }
  FreeMainDataBuffer(v15);
  if ( TreeCopy < 0 )
    goto LABEL_11;
  v24 = 0;
  while ( 1 )
  {
    v25 = CMDBaseObject::EnumChildObject(a1, v24);
    if ( !v25 )
      break;
    TreeCopy = MakeTreeCopy(v25, &v26, 0, a4);
    if ( TreeCopy >= 0 )
      TreeCopy = CMDBaseObject::InsertChildObject(v9, v26);
    ++v24;
    if ( TreeCopy < 0 )
      goto LABEL_11;
  }
  *a2 = v9;
  return (unsigned int)TreeCopy;
}

```

## disassembly

```asm
0x1800209e8  mov     rax, rsp
0x1800209eb  push    rbx
0x1800209ec  push    rbp
0x1800209ed  push    rsi
0x1800209ee  push    rdi
0x1800209ef  push    r12
0x1800209f1  push    r13
0x1800209f3  push    r14
0x1800209f5  push    r15
0x1800209f7  sub     rsp, 48h
0x1800209fb  xor     r12d, r12d
0x1800209fe  mov     r13d, r9d
0x180020a01  mov     [rax+18h], r12
0x180020a05  mov     r14, rdx
0x180020a08  mov     rbp, rcx
0x180020a0b  test    r8, r8
0x180020a0e  jnz     short loc_180020A39
0x180020a10  lea     edx, [r12+1]; int
0x180020a15  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x180020a1a  test    rax, rax
0x180020a1d  jz      short loc_180020A4E
0x180020a1f  xor     r8d, r8d; unsigned int *
0x180020a22  lea     edx, [r12+1]; int
0x180020a27  mov     rcx, rbp; this
0x180020a2a  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x180020a2f  mov     rcx, rax; unsigned __int16 *
0x180020a32  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z; CMDBaseObject::CreateBaseObject(ushort *)
0x180020a37  jmp     short loc_180020A46
0x180020a39  mov     rcx, r8; char *
0x180020a3c  test    r13d, r13d
0x180020a3f  jnz     short loc_180020A32
0x180020a41  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAD@Z; CMDBaseObject::CreateBaseObject(char *)
0x180020a46  mov     rdi, rax
0x180020a49  test    rax, rax
0x180020a4c  jnz     short loc_180020A58
0x180020a4e  mov     ebx, 8007000Eh
0x180020a53  mov     [r14], r12
0x180020a56  jmp     short loc_180020A94
0x180020a58  lea     rcx, [rdi+8]
0x180020a5c  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x180020a62  test    eax, eax
0x180020a64  jnz     short loc_180020AA7
0x180020a66  mov     rax, [rdi]
0x180020a69  mov     edx, 1
0x180020a6e  mov     rcx, rdi
0x180020a71  mov     ebx, 8007000Eh
0x180020a76  mov     rax, [rax]
0x180020a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a7e  mov     rax, [rdi]
0x180020a81  mov     edx, 1
0x180020a86  mov     rcx, rdi
0x180020a89  mov     [r14], r12
0x180020a8c  mov     rax, [rax]
0x180020a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a94  mov     eax, ebx
0x180020a96  add     rsp, 48h
0x180020a9a  pop     r15
0x180020a9c  pop     r14
0x180020a9e  pop     r13
0x180020aa0  pop     r12
0x180020aa2  pop     rdi
0x180020aa3  pop     rsi
0x180020aa4  pop     rbp
0x180020aa5  pop     rbx
0x180020aa6  retn
0x180020aa7  mov     rcx, rbp; this
0x180020aaa  call    ?IsSchemaObject@CMDBaseObject@@QEAAJXZ; CMDBaseObject::IsSchemaObject(void)
0x180020aaf  mov     ebx, eax
0x180020ab1  test    eax, eax
0x180020ab3  js      short loc_180020A7E
0x180020ab5  mov     ecx, r12d
0x180020ab8  setz    cl; int
0x180020abb  call    ?GetMainDataBuffer@@YAPEAPEAXH@Z; GetMainDataBuffer(int)
0x180020ac0  mov     r15, rax
0x180020ac3  test    rax, rax
0x180020ac6  jnz     short loc_180020ACF
0x180020ac8  mov     ebx, 8007000Eh
0x180020acd  jmp     short loc_180020A7E
0x180020acf  mov     [rsp+88h+var_50], r12; unsigned int *
0x180020ad4  xor     r9d, r9d; unsigned int
0x180020ad7  mov     [rsp+88h+var_58], r12d; int
0x180020adc  xor     r8d, r8d; unsigned int
0x180020adf  mov     [rsp+88h+var_60], r12d; int
0x180020ae4  mov     rdx, r15; void **
0x180020ae7  mov     rcx, rbp; this
0x180020aea  mov     [rsp+88h+var_68], r12d; unsigned int
0x180020aef  mov     ebx, r12d
0x180020af2  call    ?GetAllDataObjects@CMDBaseObject@@QEAAKPEAPEAXKKKHHPEAK@Z; CMDBaseObject::GetAllDataObjects(void * *,ulong,ulong,ulong,int,int,ulong *)
0x180020af7  xor     esi, esi
0x180020af9  mov     r12d, eax
0x180020afc  test    eax, eax
0x180020afe  jz      short loc_180020B7A
0x180020b00  test    ebx, ebx
0x180020b02  js      short loc_180020B7A
0x180020b04  mov     rdx, [r15]
0x180020b07  mov     ecx, [rdx+60h]
0x180020b0a  inc     ecx
0x180020b0c  cmp     esi, ecx
0x180020b0e  jnz     short loc_180020B3D
0x180020b10  mov     rcx, [rdx+68h]
0x180020b14  test    rcx, rcx
0x180020b17  jz      short loc_180020B3D
0x180020b19  lea     rax, [rdx+50h]
0x180020b1d  cmp     [rcx], rax
0x180020b20  jz      short loc_180020B2A
0x180020b22  mov     [rdx+60h], esi
0x180020b25  mov     rax, [rcx]
0x180020b28  jmp     short loc_180020B61
0x180020b2a  mov     dword ptr [rdx+60h], 0
0x180020b31  mov     qword ptr [rdx+68h], 0
0x180020b39  xor     edx, edx
0x180020b3b  jmp     short loc_180020B69
0x180020b3d  mov     [rdx+60h], esi
0x180020b40  lea     rcx, [rdx+50h]
0x180020b44  mov     rax, [rcx]
0x180020b47  mov     r8d, esi
0x180020b4a  test    esi, esi
0x180020b4c  jz      short loc_180020B5C
0x180020b4e  cmp     rax, rcx
0x180020b51  jz      short loc_180020B2A
0x180020b53  mov     rax, [rax]
0x180020b56  add     r8d, 0FFFFFFFFh
0x180020b5a  jnz     short loc_180020B4E
0x180020b5c  cmp     rax, rcx
0x180020b5f  jz      short loc_180020B2A
0x180020b61  mov     [rdx+68h], rax
0x180020b65  mov     rdx, [rax-10h]; struct CMDBaseData *
0x180020b69  mov     rcx, rdi; this
0x180020b6c  call    ?SetDataObject@CMDBaseObject@@QEAAJPEAVCMDBaseData@@@Z; CMDBaseObject::SetDataObject(CMDBaseData *)
0x180020b71  inc     esi
0x180020b73  mov     ebx, eax
0x180020b75  cmp     esi, r12d
0x180020b78  jb      short loc_180020B00
0x180020b7a  mov     rcx, r15; Block
0x180020b7d  call    ?FreeMainDataBuffer@@YAXPEAPEAX@Z; FreeMainDataBuffer(void * *)
0x180020b82  xor     r12d, r12d
0x180020b85  test    ebx, ebx
0x180020b87  js      loc_180020A7E
0x180020b8d  mov     esi, r12d
0x180020b90  mov     edx, esi; unsigned int
0x180020b92  mov     rcx, rbp; this
0x180020b95  call    ?EnumChildObject@CMDBaseObject@@QEAAPEAV1@K@Z; CMDBaseObject::EnumChildObject(ulong)
0x180020b9a  test    rax, rax
0x180020b9d  jz      short loc_180020BD8
0x180020b9f  mov     r9d, r13d; int
0x180020ba2  lea     rdx, [rsp+88h+arg_10]; struct CMDBaseObject **
0x180020baa  xor     r8d, r8d; char *
0x180020bad  mov     rcx, rax; struct CMDBaseObject *
0x180020bb0  call    ?MakeTreeCopy@@YAJPEAVCMDBaseObject@@AEAPEAV1@PEADH@Z; MakeTreeCopy(CMDBaseObject *,CMDBaseObject * &,char *,int)
0x180020bb5  mov     ebx, eax
0x180020bb7  test    eax, eax
0x180020bb9  js      short loc_180020BCD
0x180020bbb  mov     rdx, [rsp+88h+arg_10]; struct CMDBaseObject *
0x180020bc3  mov     rcx, rdi; this
0x180020bc6  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x180020bcb  mov     ebx, eax
0x180020bcd  inc     esi
0x180020bcf  test    ebx, ebx
0x180020bd1  jns     short loc_180020B90
0x180020bd3  jmp     loc_180020A7E
0x180020bd8  mov     [r14], rdi
0x180020bdb  jmp     loc_180020A94
```
