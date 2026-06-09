# EAPTranslator::translate(_EAP_ATTRIBUTES &,IASTL::IASAttributeVector const &,ulong)

- ea: `0x18001c018`
- end: `0x18001c159`
- name: `?translate@EAPTranslator@@YAXAEAU_EAP_ATTRIBUTES@@AEBVIASAttributeVector@IASTL@@K@Z`
- size: `321`
- prototype: `void __fastcall(EAPTranslator *__hidden this, struct _EAP_ATTRIBUTES *, const struct IASTL::IASAttributeVector *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018fb0`
- `0x1800194b8`
- `0x18001ae80`

## callees

- `0x180001f0c`
- `0x18000c4a4`
- `0x18001be30`
- `0x18001c018`
- `0x1800254a0`
- `0x18002b472`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001c0e1`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001c0e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c063`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EAPTranslator::translate(
        EAPTranslator *this,
        struct _EAP_ATTRIBUTES *a2,
        const struct IASTL::IASAttributeVector *a3)
{
  int v3; // edi
  unsigned int v6; // r10d
  EAP_ATTRIBUTE *i; // r9
  SIZE_T v8; // rbx
  void *v9; // rax
  const struct _IASATTRIBUTE *v10; // r8
  unsigned int v11; // ebp
  __int64 j; // rbx
  _QWORD pExceptionObject[7]; // [rsp+20h] [rbp-38h] BYREF
  const char *v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = (int)a3;
  v6 = 0;
  for ( i = *(EAP_ATTRIBUTE **)&a2->dwNumberOfAttributes; i != a2->pAttribs; ++i )
  {
    if ( (_DWORD)a3 == -1 || ((unsigned int)a3 & *((_DWORD *)i->pValue + 1)) != 0 )
      ++v6;
  }
  *(_DWORD *)this = v6;
  v8 = 16LL * v6;
  v9 = CoTaskMemAlloc(v8);
  *((_QWORD *)this + 1) = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Not enough memory to allocate array of EAP_ATTRIBUTE");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0729333d348337bd43d2a4b59100ecc2_Traceguids, "NPSSVC");
    }
    v14 = "bad allocation";
    exception::exception((exception *)pExceptionObject, &v14, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  memset_0(v9, 0, v8);
  v11 = 0;
  for ( j = *(_QWORD *)&a2->dwNumberOfAttributes; (EAP_ATTRIBUTE *)j != a2->pAttribs; j += 16 )
  {
    if ( v3 == -1 || (v3 & *(_DWORD *)(*(_QWORD *)(j + 8) + 4LL)) != 0 )
      EAPTranslator::translate(
        (EAPTranslator *)(*((_QWORD *)this + 1) + 16LL * v11++),
        *(struct _EAP_ATTRIBUTE **)(j + 8),
        v10);
  }
}

```

## disassembly

```asm
0x18001c018  mov     [rsp+arg_8], rbx
0x18001c01d  mov     [rsp+arg_10], rbp
0x18001c022  push    rsi
0x18001c023  push    rdi
0x18001c024  push    r14
0x18001c026  sub     rsp, 40h
0x18001c02a  mov     edi, r8d
0x18001c02d  mov     rsi, rdx
0x18001c030  mov     r14, rcx
0x18001c033  xor     r10d, r10d
0x18001c036  mov     r9, [rdx]
0x18001c039  jmp     short loc_18001C050
0x18001c03b  cmp     edi, 0FFFFFFFFh
0x18001c03e  jz      short loc_18001C049
0x18001c040  mov     rax, [r9+8]
0x18001c044  test    [rax+4], edi
0x18001c047  jz      short loc_18001C04C
0x18001c049  inc     r10d
0x18001c04c  add     r9, 10h
0x18001c050  cmp     r9, [rdx+8]
0x18001c054  jnz     short loc_18001C03B
0x18001c056  mov     [rcx], r10d
0x18001c059  mov     ebx, r10d
0x18001c05c  shl     rbx, 4
0x18001c060  mov     rcx, rbx; cb
0x18001c063  call    cs:__imp_CoTaskMemAlloc
0x18001c069  mov     [r14+8], rax
0x18001c06d  test    rax, rax
0x18001c070  jnz     loc_18001C105
0x18001c076  lea     rcx, WPP_GLOBAL_Control
0x18001c07d  mov     rax, cs:WPP_GLOBAL_Control
0x18001c084  cmp     rax, rcx
0x18001c087  jz      short loc_18001C0C5
0x18001c089  cmp     byte ptr [rax+19h], 2
0x18001c08d  jb      short loc_18001C0C5
0x18001c08f  test    byte ptr [rax+1Ch], 4
0x18001c093  jz      short loc_18001C0C5
0x18001c095  lea     rcx, aNotEnoughMemor; "Not enough memory to allocate array of "...
0x18001c09c  call    WppDbgPrint
0x18001c0a1  mov     edx, 0Bh
0x18001c0a6  lea     r9, aNpssvc; "NPSSVC"
0x18001c0ad  lea     r8, WPP_0729333d348337bd43d2a4b59100ecc2_Traceguids
0x18001c0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0bb  mov     rcx, [rcx+10h]
0x18001c0bf  call    WPP_SF_s
0x18001c0c4  nop
0x18001c0c5  lea     rax, aBadAllocation; "bad allocation"
0x18001c0cc  mov     [rsp+58h+arg_0], rax
0x18001c0d1  mov     r8d, 1
0x18001c0d7  lea     rdx, [rsp+58h+arg_0]
0x18001c0dc  lea     rcx, [rsp+58h+pExceptionObject]
0x18001c0e1  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18001c0e7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001c0ee  mov     [rsp+58h+pExceptionObject], rax
0x18001c0f3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001c0fa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001c0ff  call    _CxxThrowException_0
0x18001c105  mov     r8, rbx; Size
0x18001c108  xor     edx, edx; Val
0x18001c10a  mov     rcx, rax; void *
0x18001c10d  call    memset_0
0x18001c112  xor     ebp, ebp
0x18001c114  mov     rbx, [rsi]
0x18001c117  jmp     short loc_18001C140
0x18001c119  cmp     edi, 0FFFFFFFFh
0x18001c11c  jz      short loc_18001C127
0x18001c11e  mov     rax, [rbx+8]
0x18001c122  test    [rax+4], edi
0x18001c125  jz      short loc_18001C13C
0x18001c127  mov     ecx, ebp
0x18001c129  shl     rcx, 4
0x18001c12d  add     rcx, [r14+8]; this
0x18001c131  mov     rdx, [rbx+8]; struct _EAP_ATTRIBUTE *
0x18001c135  call    ?translate@EAPTranslator@@YAHAEAU_EAP_ATTRIBUTE@@AEBU_IASATTRIBUTE@@@Z; EAPTranslator::translate(_EAP_ATTRIBUTE &,_IASATTRIBUTE const &)
0x18001c13a  inc     ebp
0x18001c13c  add     rbx, 10h
0x18001c140  cmp     rbx, [rsi+8]
0x18001c144  jnz     short loc_18001C119
0x18001c146  mov     rbx, [rsp+58h+arg_8]
0x18001c14b  mov     rbp, [rsp+58h+arg_10]
0x18001c150  add     rsp, 40h
0x18001c154  pop     r14
0x18001c156  pop     rdi
0x18001c157  pop     rsi
0x18001c158  retn
```
