# CWorkerThread::ReleaseResources(void)

- ea: `0x180010894`
- end: `0x18001095c`
- name: `?ReleaseResources@CWorkerThread@@AEAAXXZ`
- size: `200`
- prototype: `void __fastcall(CWorkerThread *this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010848`

## callees

- `0x180007644`
- `0x180008f10`
- `0x180009780`
- `0x18000ca14`
- `0x180010894`
- `0x180013010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180010943`
- `KERNEL32!CloseHandle` at `0x180010943`
- `KERNEL32!CloseThreadpoolWork` at `0x1800108aa`
- `KERNEL32!CloseThreadpoolWork` at `0x1800108aa`

## pseudocode

```c
void __fastcall CWorkerThread::ReleaseResources(CWorkerThread *this, struct IUnknown *a2)
{
  struct _TP_WORK *v3; // rcx
  __int64 v4; // rcx
  int v5; // eax
  struct IUnknown *v6; // rdx
  void *v7; // rcx

  v3 = (struct _TP_WORK *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CloseThreadpoolWork(v3);
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 12) = 1;
  }
  if ( *((_QWORD *)this + 2) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 2, a2);
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
    if ( v5 < 0 )
    {
      v6 = (struct IUnknown *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
          (unsigned int)v5);
    }
    if ( *((_QWORD *)this + 1) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 1, v6);
  }
  ATL::CComPtr<IFhConfigMgrPriv>::operator=((__int64 *)this);
  ATL::CSimpleStringT<unsigned short,0>::Empty((_QWORD *)this + 3);
  v7 = (void *)*((_QWORD *)this + 4);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180010894  mov     [rsp+arg_0], rbx
0x180010899  push    rdi
0x18001089a  sub     rsp, 20h
0x18001089e  mov     rbx, rcx
0x1800108a1  mov     rcx, [rcx+28h]; pwk
0x1800108a5  test    rcx, rcx
0x1800108a8  jz      short loc_1800108BF
0x1800108aa  call    cs:__imp_CloseThreadpoolWork
0x1800108b0  mov     qword ptr [rbx+28h], 0
0x1800108b8  mov     dword ptr [rbx+30h], 1
0x1800108bf  lea     rcx, [rbx+10h]; struct IUnknown **
0x1800108c3  cmp     qword ptr [rcx], 0
0x1800108c7  jz      short loc_1800108CE
0x1800108c9  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800108ce  lea     rdi, [rbx+8]
0x1800108d2  mov     rcx, [rdi]
0x1800108d5  test    rcx, rcx
0x1800108d8  jz      short loc_180010929
0x1800108da  mov     rax, [rcx]
0x1800108dd  mov     rax, [rax+28h]
0x1800108e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e6  test    eax, eax
0x1800108e8  jns     short loc_18001091B
0x1800108ea  lea     rdx, WPP_GLOBAL_Control
0x1800108f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108f8  cmp     rcx, rdx
0x1800108fb  jz      short loc_18001091B
0x1800108fd  test    byte ptr [rcx+1Ch], 2
0x180010901  jz      short loc_18001091B
0x180010903  mov     edx, 41h ; 'A'
0x180010908  mov     r9d, eax
0x18001090b  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180010912  mov     rcx, [rcx+10h]
0x180010916  call    WPP_SF_d
0x18001091b  cmp     qword ptr [rdi], 0
0x18001091f  jz      short loc_180010929
0x180010921  mov     rcx, rdi; struct IUnknown **
0x180010924  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180010929  mov     rcx, rbx
0x18001092c  call    ??4?$CComPtr@UIFhConfigMgrPriv@@@ATL@@QEAAPEAUIFhConfigMgrPriv@@PEAU2@@Z; ATL::CComPtr<IFhConfigMgrPriv>::operator=(IFhConfigMgrPriv *)
0x180010931  lea     rcx, [rbx+18h]
0x180010935  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001093a  mov     rcx, [rbx+20h]; hObject
0x18001093e  test    rcx, rcx
0x180010941  jz      short loc_180010951
0x180010943  call    cs:__imp_CloseHandle
0x180010949  mov     qword ptr [rbx+20h], 0
0x180010951  mov     rbx, [rsp+28h+arg_0]
0x180010956  add     rsp, 20h
0x18001095a  pop     rdi
0x18001095b  retn
```
