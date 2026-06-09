# ProcessCleanupCommand(Csl::Path const &)

- ea: `0x1400060a8`
- end: `0x140006182`
- name: `?ProcessCleanupCommand@@YAJAEBVPath@Csl@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(const unsigned __int16 **)`
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
- `0x1400060a8`
- `0x140006fe4`
- `0x1400078e4`
- `0x140007d1c`

## import_xrefs

- `wc_storage!WcDestroyLayer` at `0x140006105`
- `wc_storage!WcDestroyLayer` at `0x140006105`

## pseudocode

```c
__int64 __fastcall ProcessCleanupCommand(const unsigned __int16 **a1)
{
  const unsigned __int16 *v2; // rbx
  int v3; // eax
  unsigned int v4; // ebx
  int v6[84]; // [rsp+20h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v2 = *a1;
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v6,
    "Cleanup");
  *(_QWORD *)v6 = &WorkerEtwProvider::Cleanup::`vftable';
  WorkerEtwProvider::Cleanup::StartActivity((WorkerEtwProvider::Cleanup *)v6, v2);
  v3 = WcDestroyLayer(*a1, 1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v6);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)(unsigned int)v3,
      v6[0]);
  }
  *(_QWORD *)v6 = &WorkerEtwProvider::Cleanup::`vftable';
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v6);
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v6);
  return v4;
}

```

## disassembly

```asm
0x1400060a8  mov     [rsp+arg_8], rbx
0x1400060ad  mov     [rsp+arg_10], rsi
0x1400060b2  push    rdi
0x1400060b3  sub     rsp, 180h
0x1400060ba  mov     rax, cs:__security_cookie
0x1400060c1  xor     rax, rsp
0x1400060c4  mov     [rsp+188h+var_18], rax
0x1400060cc  mov     rdi, rcx
0x1400060cf  mov     rbx, [rcx]
0x1400060d2  lea     rdx, aCleanup; "Cleanup"
0x1400060d9  lea     rcx, [rsp+188h+var_168]
0x1400060de  call    ??0?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400060e3  lea     rsi, ??_7Cleanup@WorkerEtwProvider@@6B@; const WorkerEtwProvider::Cleanup::`vftable'
0x1400060ea  mov     qword ptr [rsp+188h+var_168], rsi; int
0x1400060ef  mov     rdx, rbx; unsigned __int16 *
0x1400060f2  lea     rcx, [rsp+188h+var_168]; this
0x1400060f7  call    ?StartActivity@Cleanup@WorkerEtwProvider@@QEAAXPEBG@Z; WorkerEtwProvider::Cleanup::StartActivity(ushort const *)
0x1400060fc  nop
0x1400060fd  mov     edx, 1
0x140006102  mov     rcx, [rdi]
0x140006105  call    cs:__imp_WcDestroyLayer
0x14000610c  nop     dword ptr [rax+rax+00h]
0x140006111  mov     ebx, eax
0x140006113  test    eax, eax
0x140006115  jns     short loc_140006135
0x140006117  mov     rcx, [rsp+188h]; this
0x14000611f  mov     r9d, eax; char *
0x140006122  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006129  mov     edx, 0E0h; void *
0x14000612e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006133  jmp     short loc_140006141
0x140006135  lea     rcx, [rsp+188h+var_168]
0x14000613a  call    ?Stop@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000613f  xor     ebx, ebx
0x140006141  mov     qword ptr [rsp+188h+var_168], rsi
0x140006146  lea     rcx, [rsp+188h+var_168]
0x14000614b  call    ?Destroy@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140006150  lea     rcx, [rsp+188h+var_168]
0x140006155  call    ??1?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000615a  mov     eax, ebx
0x14000615c  mov     rcx, [rsp+188h+var_18]
0x140006164  xor     rcx, rsp; StackCookie
0x140006167  call    __security_check_cookie
0x14000616c  lea     r11, [rsp+188h+var_8]
0x140006174  mov     rbx, [r11+18h]
0x140006178  mov     rsi, [r11+20h]
0x14000617c  mov     rsp, r11
0x14000617f  pop     rdi
0x140006180  retn
```
