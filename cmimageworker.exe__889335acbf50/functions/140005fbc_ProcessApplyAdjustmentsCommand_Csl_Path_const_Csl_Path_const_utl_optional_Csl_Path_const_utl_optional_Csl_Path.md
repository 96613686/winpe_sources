# ProcessApplyAdjustmentsCommand(Csl::Path const &,Csl::Path const &,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &)

- ea: `0x140005fbc`
- end: `0x14000609f`
- name: `?ProcessApplyAdjustmentsCommand@@YAJAEBVPath@Csl@@0AEBV?$optional@VPath@Csl@@@utl@@1@Z`
- size: `227`
- prototype: `__int64 __fastcall(const unsigned __int16 **, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400094c8`

## callees

- `0x1400020b0`
- `0x1400038bc`
- `0x140003b30`
- `0x1400046d4`
- `0x140005fbc`
- `0x140006fe4`
- `0x140007798`
- `0x140007d1c`
- `0x14001694c`

## pseudocode

```c
__int64 __fastcall ProcessApplyAdjustmentsCommand(const unsigned __int16 **a1, __int64 *a2, __int64 a3, __int64 a4)
{
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-1A8h]
  _QWORD v14[42]; // [rsp+30h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v8 = (const unsigned __int16 *)*a2;
  v9 = *a1;
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "ApplyAdjustments");
  v14[0] = &WorkerEtwProvider::ApplyAdjustments::`vftable';
  WorkerEtwProvider::ApplyAdjustments::StartActivity((WorkerEtwProvider::ApplyAdjustments *)v14, v9, v8);
  v10 = Container::Manager::Image::ApplyAdjustments((__int64)a1, a2, a3, a4);
  v11 = v10;
  if ( v10 >= 0 )
  {
    wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v14);
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)(unsigned int)v10,
      v13);
  }
  v14[0] = &WorkerEtwProvider::ApplyAdjustments::`vftable';
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v14);
  return v11;
}

```

## disassembly

```asm
0x140005fbc  push    rbx
0x140005fbe  push    rbp
0x140005fbf  push    rsi
0x140005fc0  push    rdi
0x140005fc1  push    r12
0x140005fc3  push    r14
0x140005fc5  push    r15
0x140005fc7  sub     rsp, 190h
0x140005fce  mov     rax, cs:__security_cookie
0x140005fd5  xor     rax, rsp
0x140005fd8  mov     [rsp+1C8h+var_48], rax
0x140005fe0  mov     r15, r9
0x140005fe3  mov     rbp, r8
0x140005fe6  mov     r14, rdx
0x140005fe9  mov     rsi, rcx
0x140005fec  mov     rbx, [rdx]
0x140005fef  mov     rdi, [rcx]
0x140005ff2  lea     rdx, aApplyadjustmen_0; "ApplyAdjustments"
0x140005ff9  lea     rcx, [rsp+1C8h+var_198]
0x140005ffe  call    ??0?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140006003  lea     r12, ??_7ApplyAdjustments@WorkerEtwProvider@@6B@; const WorkerEtwProvider::ApplyAdjustments::`vftable'
0x14000600a  mov     [rsp+1C8h+var_198], r12
0x14000600f  mov     r8, rbx; unsigned __int16 *
0x140006012  mov     rdx, rdi; unsigned __int16 *
0x140006015  lea     rcx, [rsp+1C8h+var_198]; this
0x14000601a  call    ?StartActivity@ApplyAdjustments@WorkerEtwProvider@@QEAAXPEBG0@Z; WorkerEtwProvider::ApplyAdjustments::StartActivity(ushort const *,ushort const *)
0x14000601f  nop
0x140006020  mov     r9, r15
0x140006023  mov     r8, rbp
0x140006026  mov     rdx, r14
0x140006029  mov     rcx, rsi
0x14000602c  call    ?ApplyAdjustments@Image@Manager@Container@@YAJAEBVPath@Csl@@0AEBV?$optional@VPath@Csl@@@utl@@1_N@Z; Container::Manager::Image::ApplyAdjustments(Csl::Path const &,Csl::Path const &,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &,bool)
0x140006031  mov     ebx, eax
0x140006033  test    eax, eax
0x140006035  jns     short loc_140006055
0x140006037  mov     rcx, [rsp+1C8h]; this
0x14000603f  mov     r9d, eax; char *
0x140006042  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006049  mov     edx, 10Eh; void *
0x14000604e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006053  jmp     short loc_140006061
0x140006055  lea     rcx, [rsp+1C8h+var_198]
0x14000605a  call    ?Stop@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000605f  xor     ebx, ebx
0x140006061  mov     [rsp+1C8h+var_198], r12
0x140006066  lea     rcx, [rsp+1C8h+var_198]
0x14000606b  call    ?Destroy@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140006070  lea     rcx, [rsp+1C8h+var_198]
0x140006075  call    ??1?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000607a  mov     eax, ebx
0x14000607c  mov     rcx, [rsp+1C8h+var_48]
0x140006084  xor     rcx, rsp; StackCookie
0x140006087  call    __security_check_cookie
0x14000608c  add     rsp, 190h
0x140006093  pop     r15
0x140006095  pop     r14
0x140006097  pop     r12
0x140006099  pop     rdi
0x14000609a  pop     rsi
0x14000609b  pop     rbp
0x14000609c  pop     rbx
0x14000609d  retn
```
