# CNamespaceHandle::GetObjectW(IWbemPath *,ulong,ulong,IWmiDbHandle * *)

- ea: `0x1800157d0`
- end: `0x180015a05`
- name: `?GetObjectW@CNamespaceHandle@@QEAAJPEAUIWbemPath@@KKPEAPEAUIWmiDbHandle@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct IWbemPath *, __int64, char, struct IWmiDbHandle **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800038f0`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x1800157d0`
- `0x180015a10`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800158c3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800158c3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001591b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800159f4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001591b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800159f4`
- `wbemcomn!GetMemLogObject` at `0x180015846`
- `wbemcomn!GetMemLogObject` at `0x180015958`
- `wbemcomn!GetMemLogObject` at `0x1800159a9`
- `wbemcomn!GetMemLogObject` at `0x180015846`
- `wbemcomn!GetMemLogObject` at `0x180015958`
- `wbemcomn!GetMemLogObject` at `0x1800159a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015851`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015966`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800159b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015851`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015966`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800159b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::GetObjectW(
        CNamespaceHandle *this,
        struct IWbemPath *a2,
        __int64 a3,
        char a4,
        struct IWmiDbHandle **a5)
{
  unsigned int ObjectHandleByPath; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rsi
  __int64 v13; // r8
  int v14; // r9d
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  unsigned int v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, a3, a2);
  }
  if ( (a4 & 1) == 0 )
    return 2147500033LL;
  v17 = 0;
  ObjectHandleByPath = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, unsigned int *, _QWORD))a2->lpVtbl->GetText)(
                         a2,
                         32,
                         &v17,
                         0);
  if ( (int)(ObjectHandleByPath + 0x80000000) >= 0 && ObjectHandleByPath != -2147217348 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ObjectHandleByPath);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        ObjectHandleByPath);
    }
    return ObjectHandleByPath;
  }
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v17, 2u));
  v12 = v11;
  if ( v11 )
  {
    if ( ((int (__fastcall *)(struct IWbemPath *, __int64, unsigned int *, unsigned __int16 *))a2->lpVtbl->GetText)(
           a2,
           32,
           &v17,
           v11) >= 0 )
    {
      ObjectHandleByPath = CNamespaceHandle::GetObjectHandleByPath(this, v12, v13, v14, a5);
      CWin32DefaultArena::WbemMemFree(v12);
      return ObjectHandleByPath;
    }
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
    }
    CWin32DefaultArena::WbemMemFree(v12);
    return 2147749889LL;
  }
  else
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800157d0  mov     [rsp+arg_0], rbx
0x1800157d5  mov     [rsp+arg_8], rbp
0x1800157da  mov     [rsp+arg_10], r8d
0x1800157df  push    rsi
0x1800157e0  push    rdi
0x1800157e1  push    r14
0x1800157e3  sub     rsp, 40h
0x1800157e7  mov     ebx, r9d
0x1800157ea  mov     rdi, rdx
0x1800157ed  mov     rbp, rcx
0x1800157f0  lea     r14, WPP_GLOBAL_Control
0x1800157f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157fe  cmp     rcx, r14
0x180015801  jnz     short loc_18001587C
0x180015803  test    bl, 1
0x180015806  jz      loc_1800158A2
0x18001580c  mov     [rsp+58h+arg_10], 0
0x180015814  mov     rax, [rdi]
0x180015817  xor     r9d, r9d
0x18001581a  lea     r8, [rsp+58h+arg_10]
0x18001581f  mov     edx, 20h ; ' '
0x180015824  mov     rcx, rdi
0x180015827  mov     rax, [rax+20h]
0x18001582b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015830  mov     ebx, eax
0x180015832  mov     eax, 80000000h
0x180015837  lea     ecx, [rbx+rax]
0x18001583a  test    eax, ecx
0x18001583c  jnz     short loc_1800158A9
0x18001583e  cmp     ebx, 8004103Ch
0x180015844  jz      short loc_1800158A9
0x180015846  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001584c  mov     edx, ebx
0x18001584e  mov     rcx, rax
0x180015851  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015857  mov     rcx, cs:WPP_GLOBAL_Control
0x18001585e  cmp     rcx, r14
0x180015861  jnz     loc_180015927
0x180015867  mov     eax, ebx
0x180015869  mov     rbx, [rsp+58h+arg_0]
0x18001586e  mov     rbp, [rsp+58h+arg_8]
0x180015873  add     rsp, 40h
0x180015877  pop     r14
0x180015879  pop     rdi
0x18001587a  pop     rsi
0x18001587b  retn
0x18001587c  test    byte ptr [rcx+1Ch], 1
0x180015880  jz      short loc_180015803
0x180015882  cmp     byte ptr [rcx+19h], 5
0x180015886  jb      loc_180015803
0x18001588c  mov     edx, 5Eh ; '^'
0x180015891  mov     r9, rdi
0x180015894  mov     rcx, [rcx+10h]
0x180015898  call    WPP_SF_q
0x18001589d  jmp     loc_180015803
0x1800158a2  mov     eax, 80004001h
0x1800158a7  jmp     short loc_180015869
0x1800158a9  mov     ecx, [rsp+58h+arg_10]
0x1800158ad  mov     eax, 2
0x1800158b2  mul     rcx
0x1800158b5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800158bc  cmovb   rax, rcx
0x1800158c0  mov     rcx, rax
0x1800158c3  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800158c9  mov     rsi, rax
0x1800158cc  test    rax, rax
0x1800158cf  jz      loc_180015958
0x1800158d5  mov     [rsp+58h+var_28], rax
0x1800158da  mov     rax, [rdi]
0x1800158dd  mov     r9, rsi
0x1800158e0  lea     r8, [rsp+58h+arg_10]
0x1800158e5  mov     edx, 20h ; ' '
0x1800158ea  mov     rcx, rdi
0x1800158ed  mov     rax, [rax+20h]
0x1800158f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158f6  test    eax, eax
0x1800158f8  js      loc_1800159A9
0x1800158fe  mov     rax, [rsp+58h+arg_20]
0x180015906  mov     [rsp+58h+var_38], rax; struct IWmiDbHandle **
0x18001590b  mov     rdx, rsi; unsigned __int16 *
0x18001590e  mov     rcx, rbp; this
0x180015911  call    ?GetObjectHandleByPath@CNamespaceHandle@@IEAAJPEBGKKPEAPEAUIWmiDbHandle@@@Z; CNamespaceHandle::GetObjectHandleByPath(ushort const *,ulong,ulong,IWmiDbHandle * *)
0x180015916  mov     ebx, eax
0x180015918  mov     rcx, rsi
0x18001591b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015921  nop
0x180015922  jmp     loc_180015867
0x180015927  test    byte ptr [rcx+1Ch], 1
0x18001592b  jz      loc_180015867
0x180015931  cmp     byte ptr [rcx+19h], 2
0x180015935  jb      loc_180015867
0x18001593b  mov     edx, 5Fh ; '_'
0x180015940  mov     r9d, ebx
0x180015943  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001594a  mov     rcx, [rcx+10h]
0x18001594e  call    WPP_SF_d
0x180015953  jmp     loc_180015867
0x180015958  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001595e  mov     edx, 80041006h
0x180015963  mov     rcx, rax
0x180015966  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001596c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015973  cmp     rcx, r14
0x180015976  jz      short loc_18001599F
0x180015978  test    byte ptr [rcx+1Ch], 1
0x18001597c  jz      short loc_18001599F
0x18001597e  cmp     byte ptr [rcx+19h], 2
0x180015982  jb      short loc_18001599F
0x180015984  mov     edx, 60h ; '`'
0x180015989  mov     r9d, 80041006h
0x18001598f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180015996  mov     rcx, [rcx+10h]
0x18001599a  call    WPP_SF_d
0x18001599f  mov     eax, 80041006h
0x1800159a4  jmp     loc_180015869
0x1800159a9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800159af  mov     edx, 80041001h
0x1800159b4  mov     rcx, rax
0x1800159b7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800159bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159c4  cmp     rcx, r14
0x1800159c7  jz      short loc_1800159F1
0x1800159c9  test    byte ptr [rcx+1Ch], 1
0x1800159cd  jz      short loc_1800159F1
0x1800159cf  cmp     byte ptr [rcx+19h], 2
0x1800159d3  jb      short loc_1800159F1
0x1800159d5  mov     edx, 61h ; 'a'
0x1800159da  mov     r9d, 80041001h
0x1800159e0  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800159e7  mov     rcx, [rcx+10h]
0x1800159eb  call    WPP_SF_d
0x1800159f0  nop
0x1800159f1  mov     rcx, rsi
0x1800159f4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800159fa  nop
0x1800159fb  mov     eax, 80041001h
0x180015a00  jmp     loc_180015869
```
