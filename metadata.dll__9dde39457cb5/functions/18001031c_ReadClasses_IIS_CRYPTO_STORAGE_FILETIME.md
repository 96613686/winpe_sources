# ReadClasses(IIS_CRYPTO_STORAGE *,_FILETIME *)

- ea: `0x18001031c`
- end: `0x18001046b`
- name: `?ReadClasses@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAU_FILETIME@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct IIS_CRYPTO_STORAGE *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180021c40`

## callees

- `0x18000ff10`
- `0x18001031c`
- `0x180022ab8`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18001043d`
- `IisRTL!PuDbgPrintW` at `0x18001043d`

## string_xrefs

- `0x18001041a`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x180010431`: `[ReadClasses] Could not read information for class: %s.\nReadClass failed with hr=0x%x.\n`
- `0x18001040f`: `ReadClasses`

## pseudocode

```c
__int64 __fastcall ReadClasses(struct IIS_CRYPTO_STORAGE *a1, struct _FILETIME *a2)
{
  int v4; // r9d
  __int64 result; // rax
  unsigned int i; // ebx
  unsigned int *v7; // rdx
  int Class; // eax
  __int64 v9; // [rsp+30h] [rbp-D0h]
  struct CMDBaseObject *v10; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v11[6]; // [rsp+48h] [rbp-B8h] BYREF
  void *v12[18]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[80]; // [rsp+F0h] [rbp-10h] BYREF

  v10 = 0;
  memset_0(v12, 0, 0x88u);
  v11[0] = 1;
  v11[1] = 9;
  v11[2] = 10;
  v11[3] = 14;
  result = ReadMetaObject(&v10, L"/Schema/Classes", a2, v4);
  if ( (int)result >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _BYTE *, void **))(**((_QWORD **)g_pGlobalISTHelper
                                                                                                 + 8)
                                                                                              + 32LL))(
                 *((_QWORD *)g_pGlobalISTHelper + 8),
                 i,
                 4,
                 v11,
                 v13,
                 v12);
      if ( (_DWORD)result == -2145318890 )
        break;
      if ( (int)result < 0 )
        return result;
      if ( (*(_DWORD *)v12[9] & 0x10000) == 0 )
      {
        Class = ReadClass(v12, v7, a1, a2);
        if ( Class < 0 && (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v9) = Class;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
            1513,
            "ReadClasses",
            L"[ReadClasses] Could not read information for class: %s.\nReadClass failed with hr=0x%x.\n",
            v12[1],
            v9);
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001031c  mov     [rsp-8+arg_10], rbx
0x180010321  push    rbp
0x180010322  push    rsi
0x180010323  push    rdi
0x180010324  lea     rbp, [rsp-50h]
0x180010329  sub     rsp, 150h
0x180010330  mov     rax, cs:__security_cookie
0x180010337  xor     rax, rsp
0x18001033a  mov     [rbp+60h+var_20], rax
0x18001033e  mov     rdi, rdx
0x180010341  mov     [rsp+160h+var_120], 0
0x18001034a  mov     rsi, rcx
0x18001034d  xor     edx, edx; Val
0x18001034f  lea     rcx, [rsp+160h+var_100]; void *
0x180010354  mov     r8d, 88h; Size
0x18001035a  call    memset_0
0x18001035f  mov     r8, rdi; struct _FILETIME *
0x180010362  mov     [rsp+160h+var_118], 1
0x18001036a  lea     rdx, aSchemaClasses; "/Schema/Classes"
0x180010371  mov     [rsp+160h+var_114], 9
0x180010379  lea     rcx, [rsp+160h+var_120]; struct CMDBaseObject **
0x18001037e  mov     [rsp+160h+var_110], 0Ah
0x180010386  mov     [rsp+160h+var_10C], 0Eh
0x18001038e  call    ?ReadMetaObject@@YAJAEAPEAVCMDBaseObject@@PEAGPEAU_FILETIME@@H@Z; ReadMetaObject(CMDBaseObject * &,ushort *,_FILETIME *,int)
0x180010393  test    eax, eax
0x180010395  js      loc_18001044C
0x18001039b  xor     ebx, ebx
0x18001039d  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x1800103a4  lea     rdx, [rsp+160h+var_100]
0x1800103a9  mov     [rsp+160h+var_138], rdx
0x1800103ae  lea     r9, [rsp+160h+var_118]
0x1800103b3  lea     rdx, [rbp+60h+var_70]
0x1800103b7  mov     r8d, 4
0x1800103bd  mov     [rsp+160h+var_140], rdx
0x1800103c2  mov     edx, ebx
0x1800103c4  mov     rcx, [rax+40h]
0x1800103c8  mov     rax, [rcx]
0x1800103cb  mov     rax, [rax+20h]
0x1800103cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d4  cmp     eax, 80210816h
0x1800103d9  jz      short loc_18001044A
0x1800103db  test    eax, eax
0x1800103dd  js      short loc_18001044C
0x1800103df  mov     rax, [rbp+60h+var_B8]
0x1800103e3  test    dword ptr [rax], 10000h
0x1800103e9  jnz     short loc_180010443
0x1800103eb  mov     r9, rdi; struct _FILETIME *
0x1800103ee  lea     rcx, [rsp+160h+var_100]; void **
0x1800103f3  mov     r8, rsi; struct IIS_CRYPTO_STORAGE *
0x1800103f6  call    ?ReadClass@@YAJPEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@PEAU_FILETIME@@@Z; ReadClass(void * *,ulong *,IIS_CRYPTO_STORAGE *,_FILETIME *)
0x1800103fb  test    eax, eax
0x1800103fd  jns     short loc_180010443
0x1800103ff  test    byte ptr cs:g_dwDebugFlags, 3
0x180010406  jz      short loc_180010443
0x180010408  mov     rcx, cs:g_pDebug
0x18001040f  lea     r9, aReadclasses; "ReadClasses"
0x180010416  mov     [rsp+160h+var_130], eax
0x18001041a  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x180010421  mov     rax, [rsp+160h+var_F8]
0x180010426  mov     r8d, 5E9h
0x18001042c  mov     [rsp+160h+var_138], rax
0x180010431  lea     rax, aReadclassesCou; "[ReadClasses] Could not read informatio"...
0x180010438  mov     [rsp+160h+var_140], rax
0x18001043d  call    cs:__imp_PuDbgPrintW
0x180010443  inc     ebx
0x180010445  jmp     loc_18001039D
0x18001044a  xor     eax, eax
0x18001044c  mov     rcx, [rbp+60h+var_20]
0x180010450  xor     rcx, rsp; StackCookie
0x180010453  call    __security_check_cookie
0x180010458  mov     rbx, [rsp+160h+arg_10]
0x180010460  add     rsp, 150h
0x180010467  pop     rdi
0x180010468  pop     rsi
0x180010469  pop     rbp
0x18001046a  retn
```
