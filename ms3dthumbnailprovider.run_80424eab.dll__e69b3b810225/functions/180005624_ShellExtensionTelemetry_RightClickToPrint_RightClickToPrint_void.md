# ShellExtensionTelemetry::RightClickToPrint::~RightClickToPrint(void)

- ea: `0x180005624`
- end: `0x180005741`
- name: `??1RightClickToPrint@ShellExtensionTelemetry@@QEAA@XZ`
- size: `285`
- prototype: `void __fastcall(ShellExtensionTelemetry::RightClickToPrint *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1800079a0`
- `0x18000a53b`

## callees

- `0x180001f44`
- `0x180002954`
- `0x180005240`
- `0x1800052b8`
- `0x180005624`
- `0x18000705c`
- `0x180009820`
- `0x18000b010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800056b8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800056b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ShellExtensionTelemetry::RightClickToPrint::~RightClickToPrint(
        ShellExtensionTelemetry::RightClickToPrint *this)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  char *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[160]; // [rsp+30h] [rbp-A8h] BYREF

  *(_QWORD *)this = &ShellExtensionTelemetry::RightClickToPrint::`vftable';
  if ( !*((_QWORD *)this + 35) )
    goto LABEL_13;
  wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    SRWLock);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( v2 && *v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
      {
        v4 = (char *)*((_QWORD *)this + 35);
        if ( v4 )
        {
          wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(v4 + 8);
          operator delete(v4);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v5 == 1 )
    {
      v6 = -2147024322;
      if ( (int)v5[22] < 0 )
        v6 = v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset_0(v10, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v10, v8);
      }
      if ( (int)v5[18] >= 0 )
        v5[18] = v6;
      v5[62] = v7 - 1;
      (*(void (__fastcall **)(ShellExtensionTelemetry::RightClickToPrint *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180005624  mov     [rsp+arg_8], rbx
0x180005629  mov     [rsp+arg_10], rsi
0x18000562e  push    rdi
0x18000562f  sub     rsp, 0D0h
0x180005636  mov     rbx, rcx
0x180005639  lea     rax, ??_7RightClickToPrint@ShellExtensionTelemetry@@6B@; const ShellExtensionTelemetry::RightClickToPrint::`vftable'
0x180005640  mov     [rcx], rax
0x180005643  cmp     qword ptr [rcx+118h], 0
0x18000564b  jz      short loc_1800056C3
0x18000564d  lea     rdx, [rsp+0D8h+SRWLock]
0x180005652  call    ?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180005657  mov     rcx, [rbx+118h]
0x18000565e  test    rcx, rcx
0x180005661  jz      short loc_18000566D
0x180005663  cmp     dword ptr [rcx], 1
0x180005666  jnz     short loc_18000566D
0x180005668  mov     sil, 1
0x18000566b  jmp     short loc_1800056AE
0x18000566d  xor     sil, sil
0x180005670  test    rcx, rcx
0x180005673  jz      short loc_1800056AE
0x180005675  or      eax, 0FFFFFFFFh
0x180005678  lock xadd [rcx], eax
0x18000567c  cmp     eax, 1
0x18000567f  jnz     short loc_1800056A3
0x180005681  mov     rdi, [rbx+118h]
0x180005688  test    rdi, rdi
0x18000568b  jz      short loc_1800056A3
0x18000568d  lea     rcx, [rdi+8]
0x180005691  call    ??1?$ActivityData@VMS3DPrintShellExtension@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005696  mov     edx, 110h
0x18000569b  mov     rcx, rdi; Block
0x18000569e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800056a3  mov     qword ptr [rbx+118h], 0
0x1800056ae  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x1800056b3  test    rcx, rcx
0x1800056b6  jz      short loc_1800056BE
0x1800056b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800056be  test    sil, sil
0x1800056c1  jz      short loc_180005708
0x1800056c3  mov     rcx, [rbx+110h]
0x1800056ca  cmp     dword ptr [rcx], 1
0x1800056cd  jnz     short loc_180005708
0x1800056cf  mov     eax, 8007023Eh
0x1800056d4  cmp     dword ptr [rcx+58h], 0
0x1800056d8  cmovl   eax, [rcx+58h]
0x1800056dc  mov     edx, [rcx+0F8h]
0x1800056e2  cmp     edx, 1
0x1800056e5  jl      short loc_180005724
0x1800056e7  cmp     dword ptr [rcx+48h], 0
0x1800056eb  jl      short loc_1800056F0
0x1800056ed  mov     [rcx+48h], eax
0x1800056f0  lea     eax, [rdx-1]
0x1800056f3  mov     [rcx+0F8h], eax
0x1800056f9  mov     rax, [rbx]
0x1800056fc  mov     rcx, rbx
0x1800056ff  mov     rax, [rax+8]
0x180005703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005708  mov     rcx, rbx
0x18000570b  lea     r11, [rsp+0D8h+var_8]
0x180005713  mov     rbx, [r11+18h]
0x180005717  mov     rsi, [r11+20h]
0x18000571b  mov     rsp, r11
0x18000571e  pop     rdi
0x18000571f  jmp     ??1?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005724  xor     edx, edx; Val
0x180005726  mov     r8d, 98h; Size
0x18000572c  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180005731  call    memset_0
0x180005736  lea     rcx, [rsp+0D8h+var_A8]; this
0x18000573b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
