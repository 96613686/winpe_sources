# ReadMetaObject(CMDBaseObject * &,ushort *,_FILETIME *,int)

- ea: `0x180022ab8`
- end: `0x180022c1a`
- name: `?ReadMetaObject@@YAJAEAPEAVCMDBaseObject@@PEAGPEAU_FILETIME@@H@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct CMDBaseObject **, unsigned __int16 *, struct _FILETIME *, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ff10`
- `0x18001031c`
- `0x180010714`
- `0x180021c40`

## callees

- `0x180003d30`
- `0x180014f60`
- `0x180015430`
- `0x180015808`
- `0x18001db5c`
- `0x180022ab8`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180022b82`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180022b82`

## pseudocode

```c
__int64 __fastcall ReadMetaObject(struct CMDBaseObject **a1, char *a2, struct _FILETIME *a3)
{
  int v3; // r9d
  int v5; // r9d
  struct _FILETIME v7; // rax
  int ObjectFromPath; // ebx
  struct CMDBaseObject *BaseObject; // rax
  struct CMDBaseObject *v10; // rdi
  CMDBaseObject *v11; // rsi
  CMDBaseObject *v12; // rcx
  struct _FILETIME v13; // [rsp+30h] [rbp-D0h] BYREF
  char *v14; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[256]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = *(unsigned __int16 *)a2;
  v13 = 0;
  v5 = v3 - 47;
  if ( !v5 )
    v5 = *((unsigned __int16 *)a2 + 1);
  if ( !v5 )
    return 0;
  v7 = *a3;
  v14 = a2;
  v15 = v7;
  ObjectFromPath = GetObjectFromPath((struct CMDBaseObject **)&v13, 0, 1, (const CHAR **)&v14, 1);
  if ( ObjectFromPath != -2147024893 )
  {
    if ( ObjectFromPath >= 0 )
      return (unsigned int)-2147024713;
    return (unsigned int)ObjectFromPath;
  }
  ObjectFromPath = ExtractNameFromPath((unsigned __int16 **)&v14, v16);
  if ( ObjectFromPath >= 0 )
  {
    BaseObject = CMDBaseObject::CreateBaseObject(v16);
    v10 = BaseObject;
    if ( BaseObject )
    {
      if ( STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
      {
        v11 = (CMDBaseObject *)v13;
        v12 = (CMDBaseObject *)v13;
        v13 = *(struct _FILETIME *)(*(_QWORD *)&v13 + 224LL);
        ObjectFromPath = CMDBaseObject::InsertChildObject(v12, v10);
        if ( ObjectFromPath >= 0 )
        {
          CMDBaseObject::SetLastChangeTime(v11, &v13);
          CMDBaseObject::SetLastChangeTime(v10, &v15);
          *a1 = v10;
          return (unsigned int)ObjectFromPath;
        }
      }
      else
      {
        ObjectFromPath = -2147024882;
      }
      (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v10)(v10, 1);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)ObjectFromPath;
}

```

## disassembly

```asm
0x180022ab8  mov     [rsp-8+arg_10], rbx
0x180022abd  mov     [rsp-8+arg_18], rsi
0x180022ac2  push    rbp
0x180022ac3  push    rdi
0x180022ac4  push    r14
0x180022ac6  lea     rbp, [rsp-160h]
0x180022ace  sub     rsp, 260h
0x180022ad5  mov     rax, cs:__security_cookie
0x180022adc  xor     rax, rsp
0x180022adf  mov     [rbp+170h+var_20], rax
0x180022ae6  movzx   r9d, word ptr [rdx]
0x180022aea  mov     r14, rcx
0x180022aed  mov     qword ptr [rsp+270h+var_240.dwLowDateTime], 0
0x180022af6  sub     r9d, 2Fh ; '/'
0x180022afa  jnz     short loc_180022B09
0x180022afc  movzx   r9d, word ptr [rdx+2]
0x180022b01  xor     eax, eax
0x180022b03  movzx   ecx, ax
0x180022b06  sub     r9d, ecx
0x180022b09  test    r9d, r9d
0x180022b0c  jnz     short loc_180022B15
0x180022b0e  xor     eax, eax
0x180022b10  jmp     loc_180022BF3
0x180022b15  mov     rax, [r8]
0x180022b18  lea     r9, [rsp+270h+var_238]; char **
0x180022b1d  mov     [rsp+270h+var_238], rdx
0x180022b22  lea     rcx, [rsp+270h+var_240]; struct CMDBaseObject **
0x180022b27  xor     edx, edx; unsigned int
0x180022b29  mov     qword ptr [rsp+270h+var_230.dwLowDateTime], rax
0x180022b2e  mov     [rsp+270h+var_250], 1; int
0x180022b36  lea     r8d, [rdx+1]; unsigned int
0x180022b3a  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180022b3f  mov     ebx, eax
0x180022b41  cmp     eax, 80070003h
0x180022b46  jnz     loc_180022BE7
0x180022b4c  lea     rdx, [rsp+270h+var_220]; unsigned __int16 *
0x180022b51  lea     rcx, [rsp+270h+var_238]; unsigned __int16 **
0x180022b56  call    ?ExtractNameFromPath@@YAJPEAPEAGPEAG@Z; ExtractNameFromPath(ushort * *,ushort *)
0x180022b5b  mov     ebx, eax
0x180022b5d  test    eax, eax
0x180022b5f  js      loc_180022BF1
0x180022b65  lea     rcx, [rsp+270h+var_220]; unsigned __int16 *
0x180022b6a  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z; CMDBaseObject::CreateBaseObject(ushort *)
0x180022b6f  mov     rdi, rax
0x180022b72  test    rax, rax
0x180022b75  jnz     short loc_180022B7E
0x180022b77  mov     ebx, 8007000Eh
0x180022b7c  jmp     short loc_180022BF1
0x180022b7e  lea     rcx, [rax+8]
0x180022b82  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x180022b88  test    eax, eax
0x180022b8a  jnz     short loc_180022BA6
0x180022b8c  mov     ebx, 8007000Eh
0x180022b91  mov     rax, [rdi]
0x180022b94  mov     edx, 1
0x180022b99  mov     rcx, rdi
0x180022b9c  mov     rax, [rax]
0x180022b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ba4  jmp     short loc_180022BF1
0x180022ba6  mov     rsi, qword ptr [rsp+270h+var_240.dwLowDateTime]
0x180022bab  mov     rdx, rdi; struct CMDBaseObject *
0x180022bae  mov     rcx, rsi; this
0x180022bb1  mov     rax, [rsi+0E0h]
0x180022bb8  mov     qword ptr [rsp+270h+var_240.dwLowDateTime], rax
0x180022bbd  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x180022bc2  mov     ebx, eax
0x180022bc4  test    eax, eax
0x180022bc6  js      short loc_180022B91
0x180022bc8  lea     rdx, [rsp+270h+var_240]; struct _FILETIME *
0x180022bcd  mov     rcx, rsi; this
0x180022bd0  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180022bd5  lea     rdx, [rsp+270h+var_230]; struct _FILETIME *
0x180022bda  mov     rcx, rdi; this
0x180022bdd  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180022be2  mov     [r14], rdi
0x180022be5  jmp     short loc_180022BF1
0x180022be7  test    ebx, ebx
0x180022be9  mov     eax, 800700B7h
0x180022bee  cmovns  ebx, eax
0x180022bf1  mov     eax, ebx
0x180022bf3  mov     rcx, [rbp+170h+var_20]
0x180022bfa  xor     rcx, rsp; StackCookie
0x180022bfd  call    __security_check_cookie
0x180022c02  lea     r11, [rsp+270h+var_10]
0x180022c0a  mov     rbx, [r11+30h]
0x180022c0e  mov     rsi, [r11+38h]
0x180022c12  mov     rsp, r11
0x180022c15  pop     r14
0x180022c17  pop     rdi
0x180022c18  pop     rbp
0x180022c19  retn
```
