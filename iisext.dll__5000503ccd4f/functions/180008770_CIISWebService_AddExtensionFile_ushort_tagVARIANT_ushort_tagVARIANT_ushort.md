# CIISWebService::AddExtensionFile(ushort *,tagVARIANT,ushort *,tagVARIANT,ushort *)

- ea: `0x180008770`
- end: `0x18000882b`
- name: `?AddExtensionFile@CIISWebService@@UEAAJPEAGUtagVARIANT@@010@Z`
- size: `187`
- prototype: `__int64 __fastcall(CIISWebService *this, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 *, struct tagVARIANT *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180008770`
- `0x18000e330`
- `0x18000e380`
- `0x18000e83c`

## pseudocode

```c
__int64 __fastcall CIISWebService::AddExtensionFile(
        CIISWebService *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        unsigned __int16 *a4,
        struct tagVARIANT *a5,
        unsigned __int16 *a6)
{
  bool v9; // bp
  bool v10; // si
  unsigned int v11; // ebx
  _BYTE v13[136]; // [rsp+40h] [rbp-88h] BYREF

  if ( !a2 || !a4 || !a6 )
    return 2147500035LL;
  v9 = 0;
  v10 = 0;
  if ( a5->vt == 11 )
    v9 = a5->iVal == -1;
  if ( a3->vt == 11 )
    v10 = a3->iVal == -1;
  CSecConLib::CSecConLib((CSecConLib *)v13, *((struct IMSAdminBaseW **)this + 15));
  v11 = CSecConLib::AddExtensionFile((CSecConLib *)v13, a2, v10, a4, v9, a6, *((const unsigned __int16 **)this + 9));
  CSiteCreator::~CSiteCreator((CSiteCreator *)v13);
  return v11;
}

```

## disassembly

```asm
0x180008770  push    rbx
0x180008772  push    rbp
0x180008773  push    rsi
0x180008774  push    rdi
0x180008775  push    r14
0x180008777  push    r15
0x180008779  sub     rsp, 98h
0x180008780  mov     rdi, r9
0x180008783  mov     r14, rdx
0x180008786  mov     r15, rcx
0x180008789  test    rdx, rdx
0x18000878c  jz      loc_180008816
0x180008792  test    r9, r9
0x180008795  jz      short loc_180008816
0x180008797  mov     rbx, [rsp+0C8h+arg_28]
0x18000879f  test    rbx, rbx
0x1800087a2  jz      short loc_180008816
0x1800087a4  mov     rax, [rsp+0C8h+arg_20]
0x1800087ac  xor     bpl, bpl
0x1800087af  xor     sil, sil
0x1800087b2  cmp     word ptr [rax], 0Bh
0x1800087b6  jnz     short loc_1800087C1
0x1800087b8  cmp     word ptr [rax+8], 0FFFFh
0x1800087bd  setz    bpl
0x1800087c1  cmp     word ptr [r8], 0Bh
0x1800087c6  jnz     short loc_1800087D2
0x1800087c8  cmp     word ptr [r8+8], 0FFFFh
0x1800087ce  setz    sil
0x1800087d2  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x1800087d6  lea     rcx, [rsp+0C8h+var_88]; this
0x1800087db  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x1800087e0  mov     rax, [r15+48h]
0x1800087e4  lea     rcx, [rsp+0C8h+var_88]; this
0x1800087e9  mov     [rsp+0C8h+var_98], rax; unsigned __int16 *
0x1800087ee  mov     r9, rdi; unsigned __int16 *
0x1800087f1  mov     [rsp+0C8h+var_A0], rbx; unsigned __int16 *
0x1800087f6  mov     r8b, sil; bool
0x1800087f9  mov     rdx, r14; Source
0x1800087fc  mov     [rsp+0C8h+var_A8], bpl; bool
0x180008801  call    ?AddExtensionFile@CSecConLib@@QEAAJPEBG_N0100@Z; CSecConLib::AddExtensionFile(ushort const *,bool,ushort const *,bool,ushort const *,ushort const *)
0x180008806  lea     rcx, [rsp+0C8h+var_88]; this
0x18000880b  mov     ebx, eax
0x18000880d  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180008812  mov     eax, ebx
0x180008814  jmp     short loc_18000881B
0x180008816  mov     eax, 80004003h
0x18000881b  add     rsp, 98h
0x180008822  pop     r15
0x180008824  pop     r14
0x180008826  pop     rdi
0x180008827  pop     rsi
0x180008828  pop     rbp
0x180008829  pop     rbx
0x18000882a  retn
```
