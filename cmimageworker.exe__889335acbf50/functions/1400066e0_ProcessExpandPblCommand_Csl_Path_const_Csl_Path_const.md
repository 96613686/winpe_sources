# ProcessExpandPblCommand(Csl::Path const &,Csl::Path const &)

- ea: `0x1400066e0`
- end: `0x1400067cc`
- name: `?ProcessExpandPblCommand@@YAJAEBVPath@Csl@@0@Z`
- size: `236`
- prototype: `__int64 __fastcall(const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400094c8`

## callees

- `0x1400020b0`
- `0x1400038bc`
- `0x140003b30`
- `0x1400046d4`
- `0x1400066e0`
- `0x140006fe4`
- `0x140007bd0`
- `0x140007d1c`

## import_xrefs

- `wcimage!WcExpandContainerWim` at `0x14000674c`
- `wcimage!WcExpandContainerWim` at `0x14000674c`

## pseudocode

```c
__int64 __fastcall ProcessExpandPblCommand(const unsigned __int16 **a1, const unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rbx
  const unsigned __int16 *v5; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v9[84]; // [rsp+20h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v4 = *a2;
  v5 = *a1;
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "ExpandPbl");
  *(_QWORD *)v9 = &WorkerEtwProvider::ExpandPbl::`vftable';
  WorkerEtwProvider::ExpandPbl::StartActivity((WorkerEtwProvider::ExpandPbl *)v9, v5, v4);
  v6 = WcExpandContainerWim(*a1, 1, *a2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v9);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)(unsigned int)v6,
      v9[0]);
  }
  *(_QWORD *)v9 = &WorkerEtwProvider::ExpandPbl::`vftable';
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v9);
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v9);
  return v7;
}

```

## disassembly

```asm
0x1400066e0  mov     [rsp+arg_10], rbx
0x1400066e5  mov     [rsp+arg_18], rbp
0x1400066ea  push    rsi
0x1400066eb  push    rdi
0x1400066ec  push    r14
0x1400066ee  sub     rsp, 180h
0x1400066f5  mov     rax, cs:__security_cookie
0x1400066fc  xor     rax, rsp
0x1400066ff  mov     [rsp+198h+var_28], rax
0x140006707  mov     rsi, rdx
0x14000670a  mov     r14, rcx
0x14000670d  mov     rbx, [rdx]
0x140006710  mov     rdi, [rcx]
0x140006713  lea     rdx, aExpandpbl; "ExpandPbl"
0x14000671a  lea     rcx, [rsp+198h+var_178]
0x14000671f  call    ??0?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140006724  lea     rbp, ??_7ExpandPbl@WorkerEtwProvider@@6B@; const WorkerEtwProvider::ExpandPbl::`vftable'
0x14000672b  mov     qword ptr [rsp+198h+var_178], rbp; int
0x140006730  mov     r8, rbx; unsigned __int16 *
0x140006733  mov     rdx, rdi; unsigned __int16 *
0x140006736  lea     rcx, [rsp+198h+var_178]; this
0x14000673b  call    ?StartActivity@ExpandPbl@WorkerEtwProvider@@QEAAXPEBG0@Z; WorkerEtwProvider::ExpandPbl::StartActivity(ushort const *,ushort const *)
0x140006740  nop
0x140006741  mov     r8, [rsi]
0x140006744  mov     edx, 1
0x140006749  mov     rcx, [r14]
0x14000674c  call    cs:__imp_WcExpandContainerWim
0x140006753  nop     dword ptr [rax+rax+00h]
0x140006758  mov     ebx, eax
0x14000675a  test    eax, eax
0x14000675c  jns     short loc_14000677C
0x14000675e  mov     rcx, [rsp+198h]; this
0x140006766  mov     r9d, eax; char *
0x140006769  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006770  mov     edx, 6Ch ; 'l'; void *
0x140006775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000677a  jmp     short loc_140006788
0x14000677c  lea     rcx, [rsp+198h+var_178]
0x140006781  call    ?Stop@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140006786  xor     ebx, ebx
0x140006788  mov     qword ptr [rsp+198h+var_178], rbp
0x14000678d  lea     rcx, [rsp+198h+var_178]
0x140006792  call    ?Destroy@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140006797  lea     rcx, [rsp+198h+var_178]
0x14000679c  call    ??1?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400067a1  mov     eax, ebx
0x1400067a3  mov     rcx, [rsp+198h+var_28]
0x1400067ab  xor     rcx, rsp; StackCookie
0x1400067ae  call    __security_check_cookie
0x1400067b3  lea     r11, [rsp+198h+var_18]
0x1400067bb  mov     rbx, [r11+30h]
0x1400067bf  mov     rbp, [r11+38h]
0x1400067c3  mov     rsp, r11
0x1400067c6  pop     r14
0x1400067c8  pop     rdi
0x1400067c9  pop     rsi
0x1400067ca  retn
```
