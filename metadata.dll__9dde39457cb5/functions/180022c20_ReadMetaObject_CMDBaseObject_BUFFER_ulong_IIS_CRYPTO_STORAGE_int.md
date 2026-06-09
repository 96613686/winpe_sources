# ReadMetaObject(CMDBaseObject * &,BUFFER *,ulong,IIS_CRYPTO_STORAGE *,int)

- ea: `0x180022c20`
- end: `0x180022da5`
- name: `?ReadMetaObject@@YAJAEAPEAVCMDBaseObject@@PEAVBUFFER@@KPEAVIIS_CRYPTO_STORAGE@@H@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct CMDBaseObject **, struct BUFFER *, unsigned int, struct IIS_CRYPTO_STORAGE *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180021330`

## callees

- `0x180003d30`
- `0x180014ef8`
- `0x180014f60`
- `0x180015430`
- `0x180015808`
- `0x18001da80`
- `0x18001db5c`
- `0x180022c20`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180022d07`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180022d07`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022c60`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022c60`

## pseudocode

```c
__int64 __fastcall ReadMetaObject(
        struct CMDBaseObject **a1,
        struct BUFFER *a2,
        unsigned int a3,
        struct IIS_CRYPTO_STORAGE *a4,
        int a5)
{
  __int64 v6; // rbx
  char *Ptr; // rax
  int ObjectFromPath; // eax
  int inserted; // ebx
  int NameFromPath; // eax
  struct CMDBaseObject *BaseObject; // rax
  struct CMDBaseObject *v12; // rdi
  CMDBaseObject *v13; // rsi
  CMDBaseObject *v14; // rcx
  struct _FILETIME v16; // [rsp+30h] [rbp-D0h] BYREF
  char *v17; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME v18; // [rsp+40h] [rbp-C0h] BYREF
  char v19[2]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = a3;
  v16 = 0;
  Ptr = (char *)BUFFER::QueryPtr(a2);
  if ( (unsigned int)v6 <= 9 || Ptr[v6 - 1] )
    return (unsigned int)-2147024883;
  v18 = *(struct _FILETIME *)(Ptr + 1);
  v17 = Ptr + 9;
  ObjectFromPath = GetObjectFromPath((struct CMDBaseObject **)&v16, 0, 1, (const CHAR **)&v17, a5);
  inserted = ObjectFromPath;
  if ( ObjectFromPath == -2147024893 )
  {
    if ( a5 )
      NameFromPath = ExtractNameFromPath((unsigned __int16 **)&v17, (unsigned __int16 *)v19);
    else
      NameFromPath = ExtractNameFromPath(&v17, v19, 0);
    inserted = NameFromPath;
    if ( NameFromPath >= 0 )
    {
      if ( a5 )
        BaseObject = CMDBaseObject::CreateBaseObject((unsigned __int16 *)v19);
      else
        BaseObject = CMDBaseObject::CreateBaseObject(v19);
      v12 = BaseObject;
      if ( BaseObject )
      {
        if ( STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
        {
          v13 = (CMDBaseObject *)v16;
          v14 = (CMDBaseObject *)v16;
          v16 = *(struct _FILETIME *)(*(_QWORD *)&v16 + 224LL);
          inserted = CMDBaseObject::InsertChildObject(v14, v12);
          if ( inserted >= 0 )
          {
            CMDBaseObject::SetLastChangeTime(v13, &v16);
            CMDBaseObject::SetLastChangeTime(v12, &v18);
            *a1 = v12;
            return (unsigned int)inserted;
          }
        }
        else
        {
          inserted = -2147024882;
        }
        (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v12)(v12, 1);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else if ( ObjectFromPath >= 0 )
  {
    return (unsigned int)-2147024713;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180022c20  mov     [rsp-8+arg_10], rbx
0x180022c25  mov     [rsp-8+arg_18], rsi
0x180022c2a  push    rbp
0x180022c2b  push    rdi
0x180022c2c  push    r14
0x180022c2e  lea     rbp, [rsp-160h]
0x180022c36  sub     rsp, 260h
0x180022c3d  mov     rax, cs:__security_cookie
0x180022c44  xor     rax, rsp
0x180022c47  mov     [rbp+170h+var_20], rax
0x180022c4e  mov     r14, rcx
0x180022c51  mov     ebx, r8d
0x180022c54  mov     rcx, rdx
0x180022c57  mov     qword ptr [rsp+270h+var_240.dwLowDateTime], 0
0x180022c60  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022c66  cmp     ebx, 9
0x180022c69  jbe     loc_180022D77
0x180022c6f  cmp     byte ptr [rbx+rax-1], 0
0x180022c74  jnz     loc_180022D77
0x180022c7a  mov     rcx, [rax+1]
0x180022c7e  lea     r9, [rsp+270h+var_238]; char **
0x180022c83  mov     edi, [rbp+170h+arg_20]
0x180022c89  xor     edx, edx; unsigned int
0x180022c8b  mov     qword ptr [rsp+270h+var_230.dwLowDateTime], rcx
0x180022c90  add     rax, 9
0x180022c94  lea     rcx, [rsp+270h+var_240]; struct CMDBaseObject **
0x180022c99  mov     [rsp+270h+var_238], rax
0x180022c9e  mov     [rsp+270h+var_250], edi; int
0x180022ca2  lea     r8d, [rdx+1]; unsigned int
0x180022ca6  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180022cab  mov     ebx, eax
0x180022cad  cmp     eax, 80070003h
0x180022cb2  jnz     loc_180022D6C
0x180022cb8  lea     rdx, [rsp+270h+var_220]; char *
0x180022cbd  lea     rcx, [rsp+270h+var_238]; char **
0x180022cc2  test    edi, edi
0x180022cc4  jz      short loc_180022CCD
0x180022cc6  call    ?ExtractNameFromPath@@YAJPEAPEAGPEAG@Z; ExtractNameFromPath(ushort * *,ushort *)
0x180022ccb  jmp     short loc_180022CD5
0x180022ccd  xor     r8d, r8d; int
0x180022cd0  call    ?ExtractNameFromPath@@YAJAEAPEADPEADH@Z; ExtractNameFromPath(char * &,char *,int)
0x180022cd5  mov     ebx, eax
0x180022cd7  test    eax, eax
0x180022cd9  js      loc_180022D7C
0x180022cdf  lea     rcx, [rsp+270h+var_220]; char *
0x180022ce4  test    edi, edi
0x180022ce6  jz      short loc_180022CEF
0x180022ce8  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z; CMDBaseObject::CreateBaseObject(ushort *)
0x180022ced  jmp     short loc_180022CF4
0x180022cef  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAD@Z; CMDBaseObject::CreateBaseObject(char *)
0x180022cf4  mov     rdi, rax
0x180022cf7  test    rax, rax
0x180022cfa  jnz     short loc_180022D03
0x180022cfc  mov     ebx, 8007000Eh
0x180022d01  jmp     short loc_180022D7C
0x180022d03  lea     rcx, [rdi+8]
0x180022d07  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x180022d0d  test    eax, eax
0x180022d0f  jnz     short loc_180022D2B
0x180022d11  mov     ebx, 8007000Eh
0x180022d16  mov     rax, [rdi]
0x180022d19  mov     edx, 1
0x180022d1e  mov     rcx, rdi
0x180022d21  mov     rax, [rax]
0x180022d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d29  jmp     short loc_180022D7C
0x180022d2b  mov     rsi, qword ptr [rsp+270h+var_240.dwLowDateTime]
0x180022d30  mov     rdx, rdi; struct CMDBaseObject *
0x180022d33  mov     rcx, rsi; this
0x180022d36  mov     rax, [rsi+0E0h]
0x180022d3d  mov     qword ptr [rsp+270h+var_240.dwLowDateTime], rax
0x180022d42  call    ?InsertChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::InsertChildObject(CMDBaseObject *)
0x180022d47  mov     ebx, eax
0x180022d49  test    eax, eax
0x180022d4b  js      short loc_180022D16
0x180022d4d  lea     rdx, [rsp+270h+var_240]; struct _FILETIME *
0x180022d52  mov     rcx, rsi; this
0x180022d55  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180022d5a  lea     rdx, [rsp+270h+var_230]; struct _FILETIME *
0x180022d5f  mov     rcx, rdi; this
0x180022d62  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180022d67  mov     [r14], rdi
0x180022d6a  jmp     short loc_180022D7C
0x180022d6c  test    eax, eax
0x180022d6e  js      short loc_180022D7C
0x180022d70  mov     ebx, 800700B7h
0x180022d75  jmp     short loc_180022D7C
0x180022d77  mov     ebx, 8007000Dh
0x180022d7c  mov     eax, ebx
0x180022d7e  mov     rcx, [rbp+170h+var_20]
0x180022d85  xor     rcx, rsp; StackCookie
0x180022d88  call    __security_check_cookie
0x180022d8d  lea     r11, [rsp+270h+var_10]
0x180022d95  mov     rbx, [r11+30h]
0x180022d99  mov     rsi, [r11+38h]
0x180022d9d  mov     rsp, r11
0x180022da0  pop     r14
0x180022da2  pop     rdi
0x180022da3  pop     rbp
0x180022da4  retn
```
