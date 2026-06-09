# CNamespaceHandle::InstanceToFile(IWbemClassObject *,ushort const *,ushort const *,ushort const *,__int64)

- ea: `0x18001fedc`
- end: `0x18002021f`
- name: `?InstanceToFile@CNamespaceHandle@@IEAAJPEAUIWbemClassObject@@PEBG11_J@Z`
- size: `835`
- prototype: `int(CNamespaceHandle *__hidden this, struct IWbemClassObject *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e370`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006960`
- `0x18001e134`
- `0x18001fedc`
- `0x1800203a0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001ffe1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001ffe1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002009b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180020158`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800201c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800201e8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002009b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180020158`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800201c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800201e8`
- `wbemcomn!GetMemLogObject` at `0x18001ff61`
- `wbemcomn!GetMemLogObject` at `0x18001ffef`
- `wbemcomn!GetMemLogObject` at `0x180020054`
- `wbemcomn!GetMemLogObject` at `0x180020117`
- `wbemcomn!GetMemLogObject` at `0x18001ff61`
- `wbemcomn!GetMemLogObject` at `0x18001ffef`
- `wbemcomn!GetMemLogObject` at `0x180020054`
- `wbemcomn!GetMemLogObject` at `0x180020117`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ff6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fffd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020062`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020122`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ff6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fffd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020062`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020122`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNamespaceHandle::InstanceToFile(
        CNamespaceHandle *this,
        struct IWbemClassObject *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6)
{
  int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  unsigned __int16 *Buf2; // rdi
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // esi
  __int64 v19; // r8
  CMemoryLog *v20; // rax
  unsigned int v21; // eax
  _QWORD v22[4]; // [rsp+30h] [rbp-20h] BYREF
  CNamespaceHandle *v23; // [rsp+80h] [rbp+30h] BYREF
  int v24; // [rsp+88h] [rbp+38h] BYREF

  v23 = this;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 519, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v22[0] = 0;
  v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID__IWmiObject,
         v22);
  if ( v9 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)v9);
    }
    return (unsigned int)v9;
  }
  v12 = v22[0];
  v22[1] = v22[0];
  LODWORD(v23) = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, CNamespaceHandle **, _QWORD))(*(_QWORD *)v22[0] + 656LL))(
    v22[0],
    0,
    0,
    &v23,
    0);
  v13 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc((unsigned int)((_DWORD)v23 + 144));
  Buf2 = v13;
  if ( !v13 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 521, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    if ( !v12 )
      return 2147749894LL;
    goto LABEL_24;
  }
  v22[2] = v13;
  if ( !A51Hash(a3, v13) )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 522, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(Buf2);
    if ( !v12 )
      return 2147749894LL;
LABEL_24:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    return 2147749894LL;
  }
  *((_QWORD *)Buf2 + 16) = g_nCurrentTime++;
  *((_QWORD *)Buf2 + 17) = a6;
  v24 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *, _QWORD *))(*(_QWORD *)v22[0] + 656LL))(
          v22[0],
          0,
          (unsigned int)v23,
          &v24,
          (_QWORD *)Buf2 + 18);
  if ( (v18 & 0x80000000) != 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, v18);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 523, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v18);
    }
    CWin32DefaultArena::WbemMemFree(Buf2);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    return v18;
  }
  if ( !dword_180058AFC || g_bShuttingDown )
  {
    v21 = 1255;
    goto LABEL_38;
  }
  v21 = CObjectHeap::WriteObject((CObjectHeap *)&qword_180058EF8, a4, a5, v24 + 144, (unsigned __int8 *)Buf2);
  if ( v21 )
  {
LABEL_38:
    v18 = A51TranslateErrorCode(v21, v17, v19);
    CWin32DefaultArena::WbemMemFree(Buf2);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    return v18;
  }
  CWin32DefaultArena::WbemMemFree(Buf2);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x18001fedc  mov     [rsp-28h+arg_10], rbx
0x18001fee1  mov     [rsp-28h+arg_18], rsi
0x18001fee6  mov     [rsp-28h+arg_0], rcx
0x18001feeb  push    rbp
0x18001feec  push    rdi
0x18001feed  push    r12
0x18001feef  push    r13
0x18001fef1  push    r14
0x18001fef3  mov     rbp, rsp
0x18001fef6  sub     rsp, 50h
0x18001fefa  mov     r14, r9
0x18001fefd  mov     rsi, r8
0x18001ff00  mov     rbx, rdx
0x18001ff03  lea     r13, WPP_GLOBAL_Control
0x18001ff0a  lea     r12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001ff11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff18  cmp     rcx, r13
0x18001ff1b  jz      short loc_18001FF3A
0x18001ff1d  test    byte ptr [rcx+1Ch], 1
0x18001ff21  jz      short loc_18001FF3A
0x18001ff23  cmp     byte ptr [rcx+19h], 5
0x18001ff27  jb      short loc_18001FF3A
0x18001ff29  mov     edx, 207h
0x18001ff2e  mov     r8, r12
0x18001ff31  mov     rcx, [rcx+10h]
0x18001ff35  call    WPP_SF_
0x18001ff3a  mov     [rbp+var_20], 0
0x18001ff42  mov     rax, [rbx]
0x18001ff45  lea     r8, [rbp+var_20]
0x18001ff49  lea     rdx, IID__IWmiObject
0x18001ff50  mov     rcx, rbx
0x18001ff53  mov     rax, [rax]
0x18001ff56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff5b  mov     ebx, eax
0x18001ff5d  test    eax, eax
0x18001ff5f  jns     short loc_18001FFA5
0x18001ff61  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001ff67  mov     edx, ebx
0x18001ff69  mov     rcx, rax
0x18001ff6c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001ff72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff79  cmp     rcx, r13
0x18001ff7c  jz      short loc_18001FF9E
0x18001ff7e  test    byte ptr [rcx+1Ch], 1
0x18001ff82  jz      short loc_18001FF9E
0x18001ff84  cmp     byte ptr [rcx+19h], 2
0x18001ff88  jb      short loc_18001FF9E
0x18001ff8a  mov     edx, 208h
0x18001ff8f  mov     r9d, ebx
0x18001ff92  mov     r8, r12
0x18001ff95  mov     rcx, [rcx+10h]
0x18001ff99  call    WPP_SF_d
0x18001ff9e  mov     eax, ebx
0x18001ffa0  jmp     loc_180020206
0x18001ffa5  mov     rbx, [rbp+var_20]
0x18001ffa9  mov     [rbp+var_18], rbx
0x18001ffad  mov     dword ptr [rbp+arg_0], 0
0x18001ffb4  mov     rax, [rbx]
0x18001ffb7  mov     [rsp+50h+Buf2], 0
0x18001ffc0  lea     r9, [rbp+arg_0]
0x18001ffc4  xor     r8d, r8d
0x18001ffc7  xor     edx, edx
0x18001ffc9  mov     rcx, rbx
0x18001ffcc  mov     rax, [rax+290h]
0x18001ffd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffd8  mov     ecx, dword ptr [rbp+arg_0]
0x18001ffdb  add     ecx, 90h
0x18001ffe1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001ffe7  mov     rdi, rax
0x18001ffea  test    rax, rax
0x18001ffed  jnz     short loc_180020041
0x18001ffef  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fff5  mov     edx, 80041006h
0x18001fffa  mov     rcx, rax
0x18001fffd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020003  mov     rcx, cs:WPP_GLOBAL_Control
0x18002000a  cmp     rcx, r13
0x18002000d  jz      short loc_180020033
0x18002000f  test    byte ptr [rcx+1Ch], 1
0x180020013  jz      short loc_180020033
0x180020015  cmp     byte ptr [rcx+19h], 2
0x180020019  jb      short loc_180020033
0x18002001b  mov     edx, 209h
0x180020020  mov     r9d, 80041006h
0x180020026  mov     r8, r12
0x180020029  mov     rcx, [rcx+10h]
0x18002002d  call    WPP_SF_d
0x180020032  nop
0x180020033  test    rbx, rbx
0x180020036  jz      short loc_1800200B7
0x180020038  mov     rax, [rbx]
0x18002003b  mov     rax, [rax+10h]
0x18002003f  jmp     short loc_1800200AE
0x180020041  mov     [rbp+var_10], rdi
0x180020045  mov     rdx, rdi; unsigned __int16 *
0x180020048  mov     rcx, rsi; unsigned __int16 *
0x18002004b  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x180020050  test    al, al
0x180020052  jnz     short loc_1800200C1
0x180020054  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002005a  mov     edx, 80041006h
0x18002005f  mov     rcx, rax
0x180020062  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020068  mov     rcx, cs:WPP_GLOBAL_Control
0x18002006f  cmp     rcx, r13
0x180020072  jz      short loc_180020098
0x180020074  test    byte ptr [rcx+1Ch], 1
0x180020078  jz      short loc_180020098
0x18002007a  cmp     byte ptr [rcx+19h], 2
0x18002007e  jb      short loc_180020098
0x180020080  mov     edx, 20Ah
0x180020085  mov     r9d, 80041006h
0x18002008b  mov     r8, r12
0x18002008e  mov     rcx, [rcx+10h]
0x180020092  call    WPP_SF_d
0x180020097  nop
0x180020098  mov     rcx, rdi
0x18002009b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800200a1  nop
0x1800200a2  test    rbx, rbx
0x1800200a5  jz      short loc_1800200B7
0x1800200a7  mov     rcx, [rbx]
0x1800200aa  mov     rax, [rcx+10h]
0x1800200ae  mov     rcx, rbx
0x1800200b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200b6  nop
0x1800200b7  mov     eax, 80041006h
0x1800200bc  jmp     loc_180020206
0x1800200c1  mov     rax, cs:?g_nCurrentTime@@3_JA; __int64 g_nCurrentTime
0x1800200c8  mov     [rdi+80h], rax
0x1800200cf  inc     cs:?g_nCurrentTime@@3_JA; __int64 g_nCurrentTime
0x1800200d6  mov     rax, [rbp+arg_28]
0x1800200da  mov     [rdi+88h], rax
0x1800200e1  mov     [rbp+arg_8], 0
0x1800200e8  mov     rcx, [rbp+var_20]
0x1800200ec  mov     rax, [rcx]
0x1800200ef  lea     rdx, [rdi+90h]
0x1800200f6  mov     [rsp+50h+Buf2], rdx
0x1800200fb  lea     r9, [rbp+arg_8]
0x1800200ff  mov     r8d, dword ptr [rbp+arg_0]
0x180020103  xor     edx, edx
0x180020105  mov     rax, [rax+290h]
0x18002010c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020111  mov     esi, eax
0x180020113  test    eax, eax
0x180020115  jns     short loc_18002017B
0x180020117  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002011d  mov     edx, esi
0x18002011f  mov     rcx, rax
0x180020122  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020128  mov     rcx, cs:WPP_GLOBAL_Control
0x18002012f  cmp     rcx, r13
0x180020132  jz      short loc_180020155
0x180020134  test    byte ptr [rcx+1Ch], 1
0x180020138  jz      short loc_180020155
0x18002013a  cmp     byte ptr [rcx+19h], 2
0x18002013e  jb      short loc_180020155
0x180020140  mov     edx, 20Bh
0x180020145  mov     r9d, esi
0x180020148  mov     r8, r12
0x18002014b  mov     rcx, [rcx+10h]
0x18002014f  call    WPP_SF_d
0x180020154  nop
0x180020155  mov     rcx, rdi
0x180020158  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002015e  nop
0x18002015f  test    rbx, rbx
0x180020162  jz      short loc_180020174
0x180020164  mov     rax, [rbx]
0x180020167  mov     rcx, rbx
0x18002016a  mov     rax, [rax+10h]
0x18002016e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020173  nop
0x180020174  mov     eax, esi
0x180020176  jmp     loc_180020206
0x18002017b  cmp     cs:dword_180058AFC, 0
0x180020182  jnz     short loc_18002018B
0x180020184  mov     eax, 4E7h
0x180020189  jmp     short loc_1800201BB
0x18002018b  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180020192  jnz     short loc_180020184
0x180020194  mov     r9d, [rbp+arg_8]
0x180020198  add     r9d, 90h; unsigned int
0x18002019f  mov     [rsp+50h+Buf2], rdi; Buf2
0x1800201a4  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x1800201a8  mov     rdx, r14; unsigned __int16 *
0x1800201ab  lea     rcx, qword_180058EF8; this
0x1800201b2  call    ?WriteObject@CObjectHeap@@QEAAJPEBG0KPEAE@Z; CObjectHeap::WriteObject(ushort const *,ushort const *,ulong,uchar *)
0x1800201b7  test    eax, eax
0x1800201b9  jz      short loc_1800201E5
0x1800201bb  mov     ecx, eax; int
0x1800201bd  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x1800201c2  mov     esi, eax
0x1800201c4  mov     rcx, rdi
0x1800201c7  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800201cd  nop
0x1800201ce  test    rbx, rbx
0x1800201d1  jz      short loc_1800201E3
0x1800201d3  mov     rcx, [rbx]
0x1800201d6  mov     rax, [rcx+10h]
0x1800201da  mov     rcx, rbx
0x1800201dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201e2  nop
0x1800201e3  jmp     short loc_180020174
0x1800201e5  mov     rcx, rdi
0x1800201e8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800201ee  nop
0x1800201ef  test    rbx, rbx
0x1800201f2  jz      short loc_180020204
0x1800201f4  mov     rax, [rbx]
0x1800201f7  mov     rcx, rbx
0x1800201fa  mov     rax, [rax+10h]
0x1800201fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020203  nop
0x180020204  xor     eax, eax
0x180020206  lea     r11, [rsp+50h+var_s0]
0x18002020b  mov     rbx, [r11+40h]
0x18002020f  mov     rsi, [r11+48h]
0x180020213  mov     rsp, r11
0x180020216  pop     r14
0x180020218  pop     r13
0x18002021a  pop     r12
0x18002021c  pop     rdi
0x18002021d  pop     rbp
0x18002021e  retn
```
