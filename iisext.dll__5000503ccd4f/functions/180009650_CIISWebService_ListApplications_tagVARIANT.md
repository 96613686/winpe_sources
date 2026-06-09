# CIISWebService::ListApplications(tagVARIANT *)

- ea: `0x180009650`
- end: `0x1800096f3`
- name: `?ListApplications@CIISWebService@@UEAAJPEAUtagVARIANT@@@Z`
- size: `163`
- prototype: `int(CIISWebService *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180001048`
- `0x180003c40`
- `0x180009650`
- `0x18000e330`
- `0x18000e380`
- `0x18000f298`

## pseudocode

```c
__int64 __fastcall CIISWebService::ListApplications(CIISWebService *this, struct tagVARIANT *a2)
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
  v5 = CSecConLib::ListApplications(
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
0x180009650  mov     rax, rsp
0x180009653  mov     [rax+8], rbx
0x180009657  mov     [rax+20h], rsi
0x18000965b  push    rdi
0x18000965c  sub     rsp, 70h
0x180009660  mov     dword ptr [rax+10h], 0
0x180009667  mov     rsi, rdx
0x18000966a  mov     qword ptr [rax+18h], 0
0x180009672  mov     rbx, rcx
0x180009675  test    rdx, rdx
0x180009678  jnz     short loc_180009681
0x18000967a  mov     eax, 80004003h
0x18000967f  jmp     short loc_1800096E1
0x180009681  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009685  lea     rcx, [rsp+78h+var_58]; this
0x18000968a  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000968f  mov     rdx, [rbx+48h]; unsigned __int16 *
0x180009693  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x18000969b  lea     r8, [rsp+78h+Block]; unsigned __int16 **
0x1800096a3  lea     rcx, [rsp+78h+var_58]; this
0x1800096a8  call    ?ListApplications@CSecConLib@@QEAAJPEBGPEAPEAGPEAK@Z; CSecConLib::ListApplications(ushort const *,ushort * *,ulong *)
0x1800096ad  mov     rbx, [rsp+78h+Block]
0x1800096b5  mov     edi, eax
0x1800096b7  test    eax, eax
0x1800096b9  js      short loc_1800096C8
0x1800096bb  mov     rdx, rsi; pvarg
0x1800096be  mov     rcx, rbx; psz
0x1800096c1  call    ?MakeVariantFromStringArray@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringArray(ushort *,tagVARIANT *)
0x1800096c6  mov     edi, eax
0x1800096c8  test    rbx, rbx
0x1800096cb  jz      short loc_1800096D5
0x1800096cd  mov     rcx, rbx; Block
0x1800096d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096d5  lea     rcx, [rsp+78h+var_58]; this
0x1800096da  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x1800096df  mov     eax, edi
0x1800096e1  lea     r11, [rsp+78h+var_8]
0x1800096e6  mov     rbx, [r11+10h]
0x1800096ea  mov     rsi, [r11+28h]
0x1800096ee  mov     rsp, r11
0x1800096f1  pop     rdi
0x1800096f2  retn
```
