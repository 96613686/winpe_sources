# CIISWebService::QueryGroupIDStatus(ushort *,tagVARIANT *)

- ea: `0x180009950`
- end: `0x180009a08`
- name: `?QueryGroupIDStatus@CIISWebService@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `184`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x180001048`
- `0x180003c40`
- `0x180009950`
- `0x18000e330`
- `0x18000e380`
- `0x18000f908`

## pseudocode

```c
__int64 __fastcall CIISWebService::QueryGroupIDStatus(
        CIISWebService *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int v6; // eax
  void *v7; // rbx
  unsigned int VariantFromStringArray; // esi
  _BYTE v10[80]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v11; // [rsp+98h] [rbp+10h] BYREF
  void *Block; // [rsp+A8h] [rbp+20h] BYREF

  v11 = 0;
  Block = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v10, *((struct IMSAdminBaseW **)this + 15));
  v6 = CSecConLib::QueryGroupIDStatus(
         (CSecConLib *)v10,
         *((const unsigned __int16 **)this + 9),
         a2,
         (unsigned __int16 **)&Block,
         &v11);
  v7 = Block;
  VariantFromStringArray = v6;
  if ( v6 >= 0 )
    VariantFromStringArray = MakeVariantFromStringArray((OLECHAR *)Block, a3);
  if ( v7 )
    operator delete(v7);
  CSiteCreator::~CSiteCreator((CSiteCreator *)v10);
  return VariantFromStringArray;
}

```

## disassembly

```asm
0x180009950  mov     rax, rsp
0x180009953  mov     [rax+8], rbx
0x180009957  mov     [rax+18h], rsi
0x18000995b  push    rdi
0x18000995c  sub     rsp, 80h
0x180009963  mov     dword ptr [rax+10h], 0
0x18000996a  mov     rdi, r8
0x18000996d  mov     qword ptr [rax+20h], 0
0x180009975  mov     rbx, rdx
0x180009978  mov     rsi, rcx
0x18000997b  test    rdx, rdx
0x18000997e  jz      short loc_1800099EE
0x180009980  test    r8, r8
0x180009983  jz      short loc_1800099EE
0x180009985  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009989  lea     rcx, [rax-58h]; this
0x18000998d  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x180009992  mov     rdx, [rsi+48h]; unsigned __int16 *
0x180009996  lea     rax, [rsp+88h+arg_8]
0x18000999e  lea     r9, [rsp+88h+Block]; unsigned __int16 **
0x1800099a6  mov     [rsp+88h+var_68], rax; unsigned int *
0x1800099ab  mov     r8, rbx; unsigned __int16 *
0x1800099ae  lea     rcx, [rsp+88h+var_58]; this
0x1800099b3  call    ?QueryGroupIDStatus@CSecConLib@@QEAAJPEBG0PEAPEAGPEAK@Z; CSecConLib::QueryGroupIDStatus(ushort const *,ushort const *,ushort * *,ulong *)
0x1800099b8  mov     rbx, [rsp+88h+Block]
0x1800099c0  mov     esi, eax
0x1800099c2  test    eax, eax
0x1800099c4  js      short loc_1800099D3
0x1800099c6  mov     rdx, rdi; pvarg
0x1800099c9  mov     rcx, rbx; psz
0x1800099cc  call    ?MakeVariantFromStringArray@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringArray(ushort *,tagVARIANT *)
0x1800099d1  mov     esi, eax
0x1800099d3  test    rbx, rbx
0x1800099d6  jz      short loc_1800099E0
0x1800099d8  mov     rcx, rbx; Block
0x1800099db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099e0  lea     rcx, [rsp+88h+var_58]; this
0x1800099e5  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x1800099ea  mov     eax, esi
0x1800099ec  jmp     short loc_1800099F3
0x1800099ee  mov     eax, 80004003h
0x1800099f3  lea     r11, [rsp+88h+var_8]
0x1800099fb  mov     rbx, [r11+10h]
0x1800099ff  mov     rsi, [r11+20h]
0x180009a03  mov     rsp, r11
0x180009a06  pop     rdi
0x180009a07  retn
```
