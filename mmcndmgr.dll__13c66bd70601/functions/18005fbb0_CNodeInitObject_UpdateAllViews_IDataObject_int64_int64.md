# CNodeInitObject::UpdateAllViews(IDataObject *,__int64,__int64)

- ea: `0x18005fbb0`
- end: `0x18005fdd8`
- name: `?UpdateAllViews@CNodeInitObject@@UEAAJPEAUIDataObject@@_J1@Z`
- size: `552`
- prototype: `int(CNodeInitObject *__hidden this, struct IDataObject *, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180026a60`
- `0x18002ad38`
- `0x1800304c0`
- `0x18005fbb0`
- `0x1801344ea`
- `0x18013f010`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18005fc11`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18005fc11`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005fc07`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005fc07`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005fdab`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005fdab`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005fbdb`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005fbdb`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18005fd7e`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18005fd7e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fc51`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fc9b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fd0d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fd5c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fc51`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fc9b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fd0d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005fd5c`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005fbec`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005fbec`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fc65`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fcaf`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fd21`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fd70`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fc65`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fcaf`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fd21`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005fd70`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fc5b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fca5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fd17`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fd66`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fdb7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fc5b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fca5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fd17`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fd66`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005fdb7`

## string_xrefs

- `0x18005fbe1`: `IConsole2::UpdateAllViews`

## pseudocode

```c
__int64 __fastcall CNodeInitObject::UpdateAllViews(
        CNodeInitObject *this,
        struct IDataObject *a2,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  struct CMTSnapInNode *StaticParent; // rbx
  __int64 v12; // rax
  _QWORD *v13; // rbx
  _QWORD *v14; // r12
  __int64 v15; // rdi
  __int64 v16; // rax
  CComponent *v17; // rdi
  __int64 v18; // rax
  unsigned int v19; // ebx
  _BYTE v21[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v22[24]; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v23; // [rsp+90h] [rbp+30h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v21, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v21, L"IConsole2::UpdateAllViews");
  v8 = (const unsigned __int16 *)((char *)this + 216);
  if ( *((_QWORD *)this + 30) >= 8u )
    v8 = *(const unsigned __int16 **)v8;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v21, v8);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v21);
  v9 = *(_QWORD *)this;
  v23 = 0;
  (*(void (__fastcall **)(CNodeInitObject *, unsigned int *))(v9 + 184))(this, &v23);
  v10 = ScCheckPointers(v22, *((_QWORD *)this + 32), 2147549183LL);
  mmcerror::SC::operator=(v21, v10);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v21) )
  {
    StaticParent = CMTNode::GetStaticParent(*((CMTNode **)this + 32));
    v12 = ScCheckPointers(v22, StaticParent, 2147549183LL);
    mmcerror::SC::operator=(v21, v12);
    mmcerror::SC::~SC((mmcerror::SC *)v22);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(v21) )
    {
      v13 = (_QWORD *)*((_QWORD *)StaticParent + 56);
      while ( v13 )
      {
        v14 = (_QWORD *)*v13;
        v15 = _RTDynamicCast_0(v13[2], 0, &CNode `RTTI Type Descriptor', &CSnapInNode `RTTI Type Descriptor', 0);
        v16 = ScCheckPointers(v22, v15, 2147549183LL);
        mmcerror::SC::operator=(v21, v16);
        mmcerror::SC::~SC((mmcerror::SC *)v22);
        if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
          break;
        v13 = v14;
        v17 = (CComponent *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 32LL))(v15, v23);
        v18 = ScCheckPointers(v22, v17, 2147549183LL);
        mmcerror::SC::operator=(v21, v18);
        mmcerror::SC::~SC((mmcerror::SC *)v22);
        if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
          mmcerror::SC::TraceAndClear((mmcerror::SC *)v21);
        else
          CComponent::Notify(v17, a2, MMCN_VIEW_CHANGE, a3, a4);
      }
    }
  }
  v19 = mmcerror::SC::ToHr((mmcerror::SC *)v21);
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  return v19;
}

```

## disassembly

```asm
0x18005fbb0  mov     [rsp-28h+arg_8], rbx
0x18005fbb5  mov     [rsp-28h+arg_10], rsi
0x18005fbba  push    rbp
0x18005fbbb  push    rdi
0x18005fbbc  push    r12
0x18005fbbe  push    r14
0x18005fbc0  push    r15
0x18005fbc2  mov     rbp, rsp
0x18005fbc5  sub     rsp, 60h
0x18005fbc9  mov     r15, rdx
0x18005fbcc  mov     rbx, rcx
0x18005fbcf  xor     edx, edx
0x18005fbd1  lea     rcx, [rbp+var_30]
0x18005fbd5  mov     rsi, r9
0x18005fbd8  mov     r14, r8
0x18005fbdb  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18005fbe1  lea     rdx, aIconsole2Updat; "IConsole2::UpdateAllViews"
0x18005fbe8  lea     rcx, [rbp+var_30]
0x18005fbec  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18005fbf2  lea     rdx, [rbx+0D8h]
0x18005fbf9  cmp     qword ptr [rdx+18h], 8
0x18005fbfe  jb      short loc_18005FC03
0x18005fc00  mov     rdx, [rdx]
0x18005fc03  lea     rcx, [rbp+var_30]
0x18005fc07  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x18005fc0d  lea     rcx, [rbp+var_30]
0x18005fc11  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x18005fc17  mov     rax, [rbx]
0x18005fc1a  lea     rdx, [rbp+arg_0]
0x18005fc1e  mov     rcx, rbx
0x18005fc21  mov     [rbp+arg_0], 0
0x18005fc28  mov     rax, [rax+0B8h]
0x18005fc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc34  mov     rdx, [rbx+100h]
0x18005fc3b  lea     rcx, [rbp+var_18]
0x18005fc3f  mov     r8d, 8000FFFFh
0x18005fc45  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18005fc4a  mov     rdx, rax
0x18005fc4d  lea     rcx, [rbp+var_30]
0x18005fc51  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005fc57  lea     rcx, [rbp+var_18]
0x18005fc5b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005fc61  lea     rcx, [rbp+var_30]
0x18005fc65  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005fc6b  test    al, al
0x18005fc6d  jnz     loc_18005FDA7
0x18005fc73  mov     rcx, [rbx+100h]; this
0x18005fc7a  call    ?GetStaticParent@CMTNode@@QEAAPEAVCMTSnapInNode@@XZ; CMTNode::GetStaticParent(void)
0x18005fc7f  mov     r8d, 8000FFFFh
0x18005fc85  lea     rcx, [rbp+var_18]
0x18005fc89  mov     rdx, rax
0x18005fc8c  mov     rbx, rax
0x18005fc8f  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18005fc94  mov     rdx, rax
0x18005fc97  lea     rcx, [rbp+var_30]
0x18005fc9b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005fca1  lea     rcx, [rbp+var_18]
0x18005fca5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005fcab  lea     rcx, [rbp+var_30]
0x18005fcaf  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005fcb5  test    al, al
0x18005fcb7  jnz     loc_18005FDA7
0x18005fcbd  mov     rbx, [rbx+1C0h]
0x18005fcc4  test    rbx, rbx
0x18005fcc7  jz      loc_18005FDA7
0x18005fccd  mov     rcx, [rbx+10h]
0x18005fcd1  lea     r9, ??_R0?AVCSnapInNode@@@8; CSnapInNode `RTTI Type Descriptor'
0x18005fcd8  mov     r12, [rbx]
0x18005fcdb  lea     r8, ??_R0?AVCNode@@@8; CNode `RTTI Type Descriptor'
0x18005fce2  xor     edx, edx
0x18005fce4  mov     dword ptr [rsp+60h+var_40], 0
0x18005fcec  call    __RTDynamicCast_0
0x18005fcf1  mov     r8d, 8000FFFFh
0x18005fcf7  lea     rcx, [rbp+var_18]
0x18005fcfb  mov     rdx, rax
0x18005fcfe  mov     rdi, rax
0x18005fd01  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18005fd06  mov     rdx, rax
0x18005fd09  lea     rcx, [rbp+var_30]
0x18005fd0d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005fd13  lea     rcx, [rbp+var_18]
0x18005fd17  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005fd1d  lea     rcx, [rbp+var_30]
0x18005fd21  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005fd27  test    al, al
0x18005fd29  jnz     short loc_18005FDA7
0x18005fd2b  mov     rax, [rdi]
0x18005fd2e  mov     rcx, rdi
0x18005fd31  mov     edx, [rbp+arg_0]
0x18005fd34  mov     rbx, r12
0x18005fd37  mov     rax, [rax+20h]
0x18005fd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd40  mov     r8d, 8000FFFFh
0x18005fd46  lea     rcx, [rbp+var_18]
0x18005fd4a  mov     rdx, rax
0x18005fd4d  mov     rdi, rax
0x18005fd50  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18005fd55  mov     rdx, rax
0x18005fd58  lea     rcx, [rbp+var_30]
0x18005fd5c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005fd62  lea     rcx, [rbp+var_18]
0x18005fd66  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005fd6c  lea     rcx, [rbp+var_30]
0x18005fd70  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005fd76  test    al, al
0x18005fd78  jz      short loc_18005FD89
0x18005fd7a  lea     rcx, [rbp+var_30]
0x18005fd7e  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x18005fd84  jmp     loc_18005FCC4
0x18005fd89  mov     r9, r14; __int64
0x18005fd8c  mov     [rsp+60h+var_40], rsi; __int64
0x18005fd91  mov     r8d, 8017h; enum _MMC_NOTIFY_TYPE
0x18005fd97  mov     rdx, r15; struct IDataObject *
0x18005fd9a  mov     rcx, rdi; this
0x18005fd9d  call    ?Notify@CComponent@@QEAAJPEAUIDataObject@@W4_MMC_NOTIFY_TYPE@@_J2@Z; CComponent::Notify(IDataObject *,_MMC_NOTIFY_TYPE,__int64,__int64)
0x18005fda2  jmp     loc_18005FCC4
0x18005fda7  lea     rcx, [rbp+var_30]
0x18005fdab  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005fdb1  lea     rcx, [rbp+var_30]
0x18005fdb5  mov     ebx, eax
0x18005fdb7  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005fdbd  lea     r11, [rsp+60h+var_s0]
0x18005fdc2  mov     eax, ebx
0x18005fdc4  mov     rbx, [r11+38h]
0x18005fdc8  mov     rsi, [r11+40h]
0x18005fdcc  mov     rsp, r11
0x18005fdcf  pop     r15
0x18005fdd1  pop     r14
0x18005fdd3  pop     r12
0x18005fdd5  pop     rdi
0x18005fdd6  pop     rbp
0x18005fdd7  retn
```
