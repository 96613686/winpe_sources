# GetStream(SmartClassPtr<CDiscReader,CDiscReader>,ulong,unsigned __int64,bool)

- ea: `0x18004f8bc`
- end: `0x18004fae6`
- name: `?GetStream@@YAPEAVCStreamROBase@@V?$SmartClassPtr@VCDiscReader@@V1@@@K_K_N@Z`
- size: `554`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000d7d0`

## callees

- `0x180005040`
- `0x1800063b8`
- `0x18000c8d0`
- `0x18001f27c`
- `0x180028568`
- `0x18002b0e4`
- `0x18004dc90`
- `0x18004f8bc`
- `0x18005b04c`
- `0x18005b564`
- `0x18005bda0`
- `0x18008170e`
- `0x180088010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18004f9ac`
- `ole32!CreateStreamOnHGlobal` at `0x18004f9ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
CStreamROBase *__fastcall GetStream(__int64 *a1, unsigned int a2, __int64 a3, char a4)
{
  void *v8; // rax
  __int64 v9; // rcx
  CStreamROBase *v10; // rbx
  PVOID *v11; // rcx
  CStreamEmbeddedIStreamRO *v12; // rdi
  __int64 v14; // [rsp+30h] [rbp-A8h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-A0h] BYREF
  CStreamROBase *v16; // [rsp+40h] [rbp-98h]
  _QWORD v17[5]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v18[16]; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp-58h]
  unsigned __int64 v20; // [rsp+F0h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
  v16 = 0;
  memset_0(v18, 0, 0x50u);
  ppstm = 0;
  v8 = operator new(0x58u);
  v17[0] = v8;
  if ( v8 )
  {
    v9 = *a1;
    v14 = v9;
    if ( v9 )
      ++*(_DWORD *)(v9 + 8);
    v10 = (CStreamROBase *)CStreamImportedDataRO::CStreamImportedDataRO(v8, &v14, a2, a3);
  }
  else
  {
    v10 = 0;
  }
  v16 = v10;
  if ( !a4 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  CStreamROBase::Stat(v10, (struct tagSTATSTG *)v18, 1u);
  if ( CreateStreamOnHGlobal(0, 1, &ppstm) >= 0 )
  {
    CStreamROBase::CopyTo(v10, ppstm, v19, &v20, &v20);
    v12 = (CStreamEmbeddedIStreamRO *)operator new(0x58u);
    v17[1] = v12;
    if ( v12 )
    {
      ATL::CComPtrBase<IStream>::CComPtrBase<IStream>(v17, ppstm);
      v12 = (CStreamEmbeddedIStreamRO *)CStreamEmbeddedIStreamRO::CStreamEmbeddedIStreamRO(v12);
    }
    if ( v10 )
      (**(void (__fastcall ***)(CStreamROBase *, __int64))v10)(v10, 1);
    v16 = v12;
    goto LABEL_22;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
LABEL_22:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 8) != 0 && *((_BYTE *)v11 + 65) >= 5u )
    WPP_SF_(v11[7], 21, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(a1);
  return v16;
}

```

## disassembly

```asm
0x18004f8bc  mov     [rsp+arg_8], rbx
0x18004f8c1  mov     [rsp+arg_18], rsi
0x18004f8c6  mov     [rsp+arg_0], rcx
0x18004f8cb  push    rdi
0x18004f8cc  push    r14
0x18004f8ce  push    r15
0x18004f8d0  sub     rsp, 0C0h
0x18004f8d7  mov     dil, r9b
0x18004f8da  mov     rbx, r8
0x18004f8dd  mov     r15d, edx
0x18004f8e0  mov     r14, rcx
0x18004f8e3  lea     rsi, WPP_GLOBAL_Control
0x18004f8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f8f1  cmp     rcx, rsi
0x18004f8f4  jz      short loc_18004F917
0x18004f8f6  test    byte ptr [rcx+44h], 8
0x18004f8fa  jz      short loc_18004F917
0x18004f8fc  cmp     byte ptr [rcx+41h], 5
0x18004f900  jb      short loc_18004F917
0x18004f902  mov     edx, 13h
0x18004f907  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004f90e  mov     rcx, [rcx+38h]
0x18004f912  call    WPP_SF_
0x18004f917  mov     [rsp+0D8h+var_98], 0
0x18004f920  xor     edx, edx; Val
0x18004f922  lea     r8d, [rdx+50h]; Size
0x18004f926  lea     rcx, [rsp+0D8h+var_68]; void *
0x18004f92b  call    memset_0
0x18004f930  mov     [rsp+0D8h+ppstm], 0
0x18004f939  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004f93e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f943  mov     [rsp+0D8h+var_90], rax
0x18004f948  test    rax, rax
0x18004f94b  jz      short loc_18004F975
0x18004f94d  mov     rcx, [r14]
0x18004f950  mov     [rsp+0D8h+var_A8], rcx
0x18004f955  test    rcx, rcx
0x18004f958  jz      short loc_18004F95D
0x18004f95a  inc     dword ptr [rcx+8]
0x18004f95d  mov     r9, rbx
0x18004f960  mov     r8d, r15d
0x18004f963  lea     rdx, [rsp+0D8h+var_A8]
0x18004f968  mov     rcx, rax
0x18004f96b  call    ??0CStreamImportedDataRO@@QEAA@V?$SmartClassPtr@VCDiscReader@@V1@@@K_K@Z; CStreamImportedDataRO::CStreamImportedDataRO(SmartClassPtr<CDiscReader,CDiscReader>,ulong,unsigned __int64)
0x18004f970  mov     rbx, rax
0x18004f973  jmp     short loc_18004F977
0x18004f975  xor     ebx, ebx
0x18004f977  mov     [rsp+0D8h+var_98], rbx
0x18004f97c  test    dil, dil
0x18004f97f  jnz     short loc_18004F98D
0x18004f981  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f988  jmp     loc_18004FA8E
0x18004f98d  mov     r8d, 1; unsigned int
0x18004f993  lea     rdx, [rsp+0D8h+var_68]; struct tagSTATSTG *
0x18004f998  mov     rcx, rbx; this
0x18004f99b  call    ?Stat@CStreamROBase@@QEAAXPEAUtagSTATSTG@@K@Z; CStreamROBase::Stat(tagSTATSTG *,ulong)
0x18004f9a0  lea     r8, [rsp+0D8h+ppstm]; ppstm
0x18004f9a5  mov     edx, 1; fDeleteOnRelease
0x18004f9aa  xor     ecx, ecx; hGlobal
0x18004f9ac  call    cs:__imp_CreateStreamOnHGlobal
0x18004f9b2  test    eax, eax
0x18004f9b4  jns     short loc_18004F9BB
0x18004f9b6  jmp     loc_18004FA57
0x18004f9bb  lea     rax, [rsp+0D8h+arg_10]
0x18004f9c3  mov     [rsp+0D8h+var_B8], rax; unsigned __int64 *
0x18004f9c8  lea     r9, [rsp+0D8h+arg_10]; unsigned __int64 *
0x18004f9d0  mov     r8, [rsp+0D8h+var_58]; unsigned __int64
0x18004f9d8  mov     rdx, [rsp+0D8h+ppstm]; struct IStream *
0x18004f9dd  mov     rcx, rbx; this
0x18004f9e0  call    ?CopyTo@CStreamROBase@@QEAAXPEAUIStream@@_KPEA_K2@Z; CStreamROBase::CopyTo(IStream *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x18004f9e5  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004f9ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f9ef  mov     rdi, rax
0x18004f9f2  mov     [rsp+0D8h+var_88], rax
0x18004f9f7  test    rdi, rdi
0x18004f9fa  jz      short loc_18004FA21
0x18004f9fc  mov     rdx, [rsp+0D8h+ppstm]
0x18004fa01  lea     rcx, [rsp+0D8h+var_90]
0x18004fa06  call    ??0?$CComPtrBase@UIStream@@@ATL@@IEAA@PEAUIStream@@@Z; ATL::CComPtrBase<IStream>::CComPtrBase<IStream>(IStream *)
0x18004fa0b  mov     r8d, 1
0x18004fa11  lea     rdx, [rsp+0D8h+var_90]
0x18004fa16  mov     rcx, rdi; this
0x18004fa19  call    ??0CStreamEmbeddedIStreamRO@@QEAA@V?$CComPtr@UIStream@@@ATL@@K@Z; CStreamEmbeddedIStreamRO::CStreamEmbeddedIStreamRO(ATL::CComPtr<IStream>,ulong)
0x18004fa1e  mov     rdi, rax
0x18004fa21  test    rbx, rbx
0x18004fa24  jz      short loc_18004FA39
0x18004fa26  mov     rax, [rbx]
0x18004fa29  mov     edx, 1
0x18004fa2e  mov     rcx, rbx
0x18004fa31  mov     rax, [rax]
0x18004fa34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa39  mov     [rsp+0D8h+var_98], rdi
0x18004fa3e  jmp     short loc_18004FA87
0x18004fa40  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18004fa44  lea     rsi, WPP_GLOBAL_Control
0x18004fa4b  mov     r14, [rsp+0D8h+arg_0]
0x18004fa53  test    eax, eax
0x18004fa55  jns     short loc_18004FA87
0x18004fa57  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa5e  cmp     rcx, rsi
0x18004fa61  jz      short loc_18004FAB5
0x18004fa63  test    byte ptr [rcx+44h], 4
0x18004fa67  jz      short loc_18004FA8E
0x18004fa69  cmp     byte ptr [rcx+41h], 3
0x18004fa6d  jb      short loc_18004FA8E
0x18004fa6f  mov     edx, 14h
0x18004fa74  mov     r9d, eax
0x18004fa77  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004fa7e  mov     rcx, [rcx+38h]
0x18004fa82  call    WPP_SF_d
0x18004fa87  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa8e  cmp     rcx, rsi
0x18004fa91  jz      short loc_18004FAB5
0x18004fa93  test    byte ptr [rcx+44h], 8
0x18004fa97  jz      short loc_18004FAB5
0x18004fa99  cmp     byte ptr [rcx+41h], 5
0x18004fa9d  jb      short loc_18004FAB5
0x18004fa9f  mov     edx, 15h
0x18004faa4  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004faab  mov     rcx, [rcx+38h]
0x18004faaf  call    WPP_SF_
0x18004fab4  nop
0x18004fab5  lea     rcx, [rsp+0D8h+ppstm]
0x18004faba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004fabf  nop
0x18004fac0  mov     rcx, r14; void *
0x18004fac3  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18004fac8  mov     rax, [rsp+0D8h+var_98]
0x18004facd  lea     r11, [rsp+0D8h+var_18]
0x18004fad5  mov     rbx, [r11+28h]
0x18004fad9  mov     rsi, [r11+38h]
0x18004fadd  mov     rsp, r11
0x18004fae0  pop     r15
0x18004fae2  pop     r14
0x18004fae4  pop     rdi
0x18004fae5  retn
```
