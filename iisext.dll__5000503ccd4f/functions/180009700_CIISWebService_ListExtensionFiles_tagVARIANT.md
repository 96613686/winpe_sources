# CIISWebService::ListExtensionFiles(tagVARIANT *)

- ea: `0x180009700`
- end: `0x1800097a3`
- name: `?ListExtensionFiles@CIISWebService@@UEAAJPEAUtagVARIANT@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(CIISWebService *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180003c40`
- `0x180009700`
- `0x18000e330`
- `0x18000e380`
- `0x18000f478`

## pseudocode

```c
__int64 __fastcall CIISWebService::ListExtensionFiles(CIISWebService *this, struct tagVARIANT *a2)
{
  int v5; // eax
  void *v6; // rbx
  unsigned int VariantFromStringArray; // edi
  _BYTE v8[80]; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v9; // [rsp+88h] [rbp+10h] BYREF
  void *Block; // [rsp+90h] [rbp+18h] BYREF

  v9 = 0;
  Block = 0;
  if ( !a2 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v8, *((struct IMSAdminBaseW **)this + 15));
  v5 = CSecConLib::ListExtensionFiles(
         (CSecConLib *)v8,
         *((const unsigned __int16 **)this + 9),
         (unsigned __int16 **)&Block,
         &v9);
  v6 = Block;
  VariantFromStringArray = v5;
  if ( v5 >= 0 )
    VariantFromStringArray = MakeVariantFromStringArray((OLECHAR *)Block, a2);
  if ( v6 )
    operator delete(v6);
  CSiteCreator::~CSiteCreator((CSiteCreator *)v8);
  return VariantFromStringArray;
}

```

## disassembly

```asm
0x180009700  mov     rax, rsp
0x180009703  mov     [rax+8], rbx
0x180009707  mov     [rax+20h], rsi
0x18000970b  push    rdi
0x18000970c  sub     rsp, 70h
0x180009710  mov     dword ptr [rax+10h], 0
0x180009717  mov     rsi, rdx
0x18000971a  mov     qword ptr [rax+18h], 0
0x180009722  mov     rbx, rcx
0x180009725  test    rdx, rdx
0x180009728  jnz     short loc_180009731
0x18000972a  mov     eax, 80004003h
0x18000972f  jmp     short loc_180009791
0x180009731  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009735  lea     rcx, [rsp+78h+var_58]; this
0x18000973a  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000973f  mov     rdx, [rbx+48h]; unsigned __int16 *
0x180009743  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x18000974b  lea     r8, [rsp+78h+Block]; unsigned __int16 **
0x180009753  lea     rcx, [rsp+78h+var_58]; this
0x180009758  call    ?ListExtensionFiles@CSecConLib@@QEAAJPEBGPEAPEAGPEAK@Z; CSecConLib::ListExtensionFiles(ushort const *,ushort * *,ulong *)
0x18000975d  mov     rbx, [rsp+78h+Block]
0x180009765  mov     edi, eax
0x180009767  test    eax, eax
0x180009769  js      short loc_180009778
0x18000976b  mov     rdx, rsi; pvarg
0x18000976e  mov     rcx, rbx; psz
0x180009771  call    ?MakeVariantFromStringArray@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringArray(ushort *,tagVARIANT *)
0x180009776  mov     edi, eax
0x180009778  test    rbx, rbx
0x18000977b  jz      short loc_180009785
0x18000977d  mov     rcx, rbx; Block
0x180009780  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009785  lea     rcx, [rsp+78h+var_58]; this
0x18000978a  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x18000978f  mov     eax, edi
0x180009791  lea     r11, [rsp+78h+var_8]
0x180009796  mov     rbx, [r11+10h]
0x18000979a  mov     rsi, [r11+28h]
0x18000979e  mov     rsp, r11
0x1800097a1  pop     rdi
0x1800097a2  retn
```
