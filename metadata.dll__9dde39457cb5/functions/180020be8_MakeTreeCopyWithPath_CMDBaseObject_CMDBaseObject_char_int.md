# MakeTreeCopyWithPath(CMDBaseObject *,CMDBaseObject * &,char *,int)

- ea: `0x180020be8`
- end: `0x180020e05`
- name: `?MakeTreeCopyWithPath@@YAJPEAVCMDBaseObject@@AEAPEAV1@PEADH@Z`
- size: `541`
- prototype: `__int64 __fastcall(struct CMDBaseObject *, struct CMDBaseObject **, char *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c580`

## callees

- `0x180007810`
- `0x180014ef8`
- `0x180014f60`
- `0x180015430`
- `0x1800154b8`
- `0x18001da80`
- `0x1800209e8`
- `0x180020be8`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180020c6e`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180020c6e`

## pseudocode

```c
__int64 __fastcall MakeTreeCopyWithPath(struct CMDBaseObject *a1, struct CMDBaseObject **a2, char *a3, int a4)
{
  struct CMDBaseObject *v4; // r14
  struct CMDBaseObject *v5; // rbx
  CMDBaseObject *i; // rdi
  int v10; // eax
  struct CMDBaseObject *BaseObject; // rax
  int inserted; // esi
  char *Name; // rax
  CMDBaseObject *k; // rax
  struct CMDBaseObject *j; // rax
  struct CMDBaseObject *v17; // [rsp+20h] [rbp-258h] BYREF
  char *v18; // [rsp+28h] [rbp-250h] BYREF
  unsigned __int16 v19[256]; // [rsp+30h] [rbp-248h] BYREF

  v4 = 0;
  v18 = a3;
  v5 = 0;
  v17 = 0;
  for ( i = 0; ; i = v5 )
  {
    v10 = ExtractNameFromPath(&v18, (char *)v19, a4);
    if ( v10 < 0 )
      break;
    if ( a4 )
      BaseObject = CMDBaseObject::CreateBaseObject(v19);
    else
      BaseObject = CMDBaseObject::CreateBaseObject((char *)v19);
    v5 = BaseObject;
    if ( !BaseObject )
    {
      inserted = -2147024882;
      goto LABEL_30;
    }
    if ( !STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
    {
      inserted = -2147024882;
      (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v5)(v5, 1);
      goto LABEL_30;
    }
    if ( i )
    {
      inserted = CMDBaseObject::InsertChildObject(i, v5);
      if ( inserted < 0 )
      {
        (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v5)(v5, 1);
        goto LABEL_31;
      }
    }
  }
  if ( v10 == -2147024893 )
  {
    if ( v5 )
    {
      Name = CMDBaseObject::GetName(v5, 1, 0);
      i = (CMDBaseObject *)*((_QWORD *)v5 + 23);
      if ( !Name )
      {
        inserted = -2147024882;
        goto LABEL_28;
      }
    }
    else
    {
      Name = 0;
    }
    inserted = MakeTreeCopy(a1, &v17, Name, 1);
    if ( inserted >= 0 && i )
    {
      CMDBaseObject::RemoveChildObject(i, v5);
      v4 = v17;
      inserted = CMDBaseObject::InsertChildObject(i, v17);
      if ( inserted < 0 )
      {
        if ( v4 )
          (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v4)(v4, 1);
        v4 = 0;
      }
    }
    else
    {
      v4 = v17;
    }
    if ( !v5 )
    {
LABEL_29:
      if ( inserted >= 0 )
      {
        for ( j = (struct CMDBaseObject *)*((_QWORD *)v4 + 23); j; j = (struct CMDBaseObject *)*((_QWORD *)j + 23) )
          v4 = j;
        *a2 = v4;
        return (unsigned int)inserted;
      }
      goto LABEL_30;
    }
LABEL_28:
    (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v5)(v5, 1);
    goto LABEL_29;
  }
  inserted = v10;
LABEL_30:
  if ( !i )
    return (unsigned int)inserted;
LABEL_31:
  for ( k = (CMDBaseObject *)*((_QWORD *)i + 23); k; k = (CMDBaseObject *)*((_QWORD *)k + 23) )
    i = k;
  (**(void (__fastcall ***)(CMDBaseObject *, __int64))i)(i, 1);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180020be8  mov     [rsp+arg_18], rbx
0x180020bed  push    rbp
0x180020bee  push    rsi
0x180020bef  push    rdi
0x180020bf0  push    r12
0x180020bf2  push    r13
0x180020bf4  push    r14
0x180020bf6  push    r15
0x180020bf8  sub     rsp, 240h
0x180020bff  mov     rax, cs:__security_cookie
0x180020c06  xor     rax, rsp
0x180020c09  mov     [rsp+278h+var_48], rax
0x180020c11  xor     r14d, r14d
0x180020c14  mov     [rsp+278h+var_250], r8
0x180020c19  xor     ebx, ebx
0x180020c1b  mov     [rsp+278h+var_258], r14
0x180020c20  xor     edi, edi
0x180020c22  mov     ebp, r9d
0x180020c25  xor     esi, esi
0x180020c27  mov     r12, rdx
0x180020c2a  mov     r15, rcx
0x180020c2d  mov     r8d, ebp; int
0x180020c30  lea     rdx, [rsp+278h+var_248]; char *
0x180020c35  lea     rcx, [rsp+278h+var_250]; char **
0x180020c3a  call    ?ExtractNameFromPath@@YAJAEAPEADPEADH@Z; ExtractNameFromPath(char * &,char *,int)
0x180020c3f  mov     r13d, 1
0x180020c45  test    eax, eax
0x180020c47  js      loc_180020CD5
0x180020c4d  lea     rcx, [rsp+278h+var_248]; char *
0x180020c52  test    ebp, ebp
0x180020c54  jz      short loc_180020C5D
0x180020c56  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z; CMDBaseObject::CreateBaseObject(ushort *)
0x180020c5b  jmp     short loc_180020C62
0x180020c5d  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAD@Z; CMDBaseObject::CreateBaseObject(char *)
0x180020c62  mov     rbx, rax
0x180020c65  test    rax, rax
0x180020c68  jz      short loc_180020CCB
0x180020c6a  lea     rcx, [rax+8]
0x180020c6e  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x180020c74  test    eax, eax
0x180020c76  jz      short loc_180020CB0
0x180020c78  test    rdi, rdi
0x180020c7b  jz      short loc_180020C8E
0x180020c7d  mov     rdx, rbx; struct CMDBaseObject *
0x180020c80  mov     rcx, rdi; this
0x180020c83  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x180020c88  mov     esi, eax
0x180020c8a  test    eax, eax
0x180020c8c  js      short loc_180020C9A
0x180020c8e  mov     rdi, rbx
0x180020c91  test    esi, esi
0x180020c93  jns     short loc_180020C2D
0x180020c95  jmp     loc_180020D89
0x180020c9a  mov     rax, [rbx]
0x180020c9d  mov     edx, r13d
0x180020ca0  mov     rcx, rbx
0x180020ca3  mov     rax, [rax]
0x180020ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cab  jmp     loc_180020D89
0x180020cb0  mov     rax, [rbx]
0x180020cb3  mov     edx, r13d
0x180020cb6  mov     rcx, rbx
0x180020cb9  mov     esi, 8007000Eh
0x180020cbe  mov     rax, [rax]
0x180020cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cc6  jmp     loc_180020D84
0x180020ccb  mov     esi, 8007000Eh
0x180020cd0  jmp     loc_180020D84
0x180020cd5  cmp     eax, 80070003h
0x180020cda  jz      short loc_180020CE3
0x180020cdc  mov     esi, eax
0x180020cde  jmp     loc_180020D84
0x180020ce3  test    rbx, rbx
0x180020ce6  jz      short loc_180020D09
0x180020ce8  xor     r8d, r8d; unsigned int *
0x180020ceb  mov     edx, r13d; int
0x180020cee  mov     rcx, rbx; this
0x180020cf1  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x180020cf6  mov     rdi, [rbx+0B8h]
0x180020cfd  test    rax, rax
0x180020d00  jnz     short loc_180020D0B
0x180020d02  mov     esi, 8007000Eh
0x180020d07  jmp     short loc_180020D6F
0x180020d09  xor     eax, eax
0x180020d0b  mov     r9d, r13d; int
0x180020d0e  lea     rdx, [rsp+278h+var_258]; struct CMDBaseObject **
0x180020d13  mov     r8, rax; char *
0x180020d16  mov     rcx, r15; struct CMDBaseObject *
0x180020d19  call    ?MakeTreeCopy@@YAJPEAVCMDBaseObject@@AEAPEAV1@PEADH@Z; MakeTreeCopy(CMDBaseObject *,CMDBaseObject * &,char *,int)
0x180020d1e  mov     esi, eax
0x180020d20  test    eax, eax
0x180020d22  js      short loc_180020D65
0x180020d24  test    rdi, rdi
0x180020d27  jz      short loc_180020D65
0x180020d29  mov     rdx, rbx; struct CMDBaseObject *
0x180020d2c  mov     rcx, rdi; this
0x180020d2f  call    ?RemoveChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::RemoveChildObject(CMDBaseObject *)
0x180020d34  mov     r14, [rsp+278h+var_258]
0x180020d39  mov     rcx, rdi; this
0x180020d3c  mov     rdx, r14; struct CMDBaseObject *
0x180020d3f  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x180020d44  mov     esi, eax
0x180020d46  test    eax, eax
0x180020d48  jns     short loc_180020D6A
0x180020d4a  test    r14, r14
0x180020d4d  jz      short loc_180020D60
0x180020d4f  mov     rax, [r14]
0x180020d52  mov     edx, r13d
0x180020d55  mov     rcx, r14
0x180020d58  mov     rax, [rax]
0x180020d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d60  xor     r14d, r14d
0x180020d63  jmp     short loc_180020D6A
0x180020d65  mov     r14, [rsp+278h+var_258]
0x180020d6a  test    rbx, rbx
0x180020d6d  jz      short loc_180020D80
0x180020d6f  mov     rax, [rbx]
0x180020d72  mov     edx, r13d
0x180020d75  mov     rcx, rbx
0x180020d78  mov     rax, [rax]
0x180020d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d80  test    esi, esi
0x180020d82  jns     short loc_180020DBC
0x180020d84  test    rdi, rdi
0x180020d87  jz      short loc_180020DD8
0x180020d89  mov     rax, [rdi+0B8h]
0x180020d90  test    rax, rax
0x180020d93  jz      short loc_180020DA9
0x180020d95  mov     rdi, rax
0x180020d98  mov     rax, [rax+0B8h]
0x180020d9f  test    rax, rax
0x180020da2  jnz     short loc_180020D95
0x180020da4  test    rdi, rdi
0x180020da7  jz      short loc_180020DD8
0x180020da9  mov     rax, [rdi]
0x180020dac  mov     edx, r13d
0x180020daf  mov     rcx, rdi
0x180020db2  mov     rax, [rax]
0x180020db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dba  jmp     short loc_180020DD8
0x180020dbc  mov     rax, [r14+0B8h]
0x180020dc3  jmp     short loc_180020DCF
0x180020dc5  mov     r14, rax
0x180020dc8  mov     rax, [rax+0B8h]
0x180020dcf  test    rax, rax
0x180020dd2  jnz     short loc_180020DC5
0x180020dd4  mov     [r12], r14
0x180020dd8  mov     eax, esi
0x180020dda  mov     rcx, [rsp+278h+var_48]
0x180020de2  xor     rcx, rsp; StackCookie
0x180020de5  call    __security_check_cookie
0x180020dea  mov     rbx, [rsp+278h+arg_18]
0x180020df2  add     rsp, 240h
0x180020df9  pop     r15
0x180020dfb  pop     r14
0x180020dfd  pop     r13
0x180020dff  pop     r12
0x180020e01  pop     rdi
0x180020e02  pop     rsi
0x180020e03  pop     rbp
0x180020e04  retn
```
