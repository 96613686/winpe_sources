# CIISWebService::ListWebServiceExtensions(tagVARIANT *)

- ea: `0x1800097b0`
- end: `0x180009853`
- name: `?ListWebServiceExtensions@CIISWebService@@UEAAJPEAUtagVARIANT@@@Z`
- size: `163`
- prototype: `int(CIISWebService *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180003c40`
- `0x1800097b0`
- `0x18000e330`
- `0x18000e380`
- `0x18000f674`

## pseudocode

```c
__int64 __fastcall CIISWebService::ListWebServiceExtensions(CIISWebService *this, struct tagVARIANT *a2)
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
  v5 = CSecConLib::ListWebServiceExtensions(
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
0x1800097b0  mov     rax, rsp
0x1800097b3  mov     [rax+8], rbx
0x1800097b7  mov     [rax+20h], rsi
0x1800097bb  push    rdi
0x1800097bc  sub     rsp, 70h
0x1800097c0  mov     dword ptr [rax+10h], 0
0x1800097c7  mov     rsi, rdx
0x1800097ca  mov     qword ptr [rax+18h], 0
0x1800097d2  mov     rbx, rcx
0x1800097d5  test    rdx, rdx
0x1800097d8  jnz     short loc_1800097E1
0x1800097da  mov     eax, 80004003h
0x1800097df  jmp     short loc_180009841
0x1800097e1  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x1800097e5  lea     rcx, [rsp+78h+var_58]; this
0x1800097ea  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x1800097ef  mov     rdx, [rbx+48h]; unsigned __int16 *
0x1800097f3  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x1800097fb  lea     r8, [rsp+78h+Block]; unsigned __int16 **
0x180009803  lea     rcx, [rsp+78h+var_58]; this
0x180009808  call    ?ListWebServiceExtensions@CSecConLib@@QEAAJPEBGPEAPEAGPEAK@Z; CSecConLib::ListWebServiceExtensions(ushort const *,ushort * *,ulong *)
0x18000980d  mov     rbx, [rsp+78h+Block]
0x180009815  mov     edi, eax
0x180009817  test    eax, eax
0x180009819  js      short loc_180009828
0x18000981b  mov     rdx, rsi; pvarg
0x18000981e  mov     rcx, rbx; psz
0x180009821  call    ?MakeVariantFromStringArray@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringArray(ushort *,tagVARIANT *)
0x180009826  mov     edi, eax
0x180009828  test    rbx, rbx
0x18000982b  jz      short loc_180009835
0x18000982d  mov     rcx, rbx; Block
0x180009830  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009835  lea     rcx, [rsp+78h+var_58]; this
0x18000983a  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x18000983f  mov     eax, edi
0x180009841  lea     r11, [rsp+78h+var_8]
0x180009846  mov     rbx, [r11+10h]
0x18000984a  mov     rsi, [r11+28h]
0x18000984e  mov     rsp, r11
0x180009851  pop     rdi
0x180009852  retn
```
