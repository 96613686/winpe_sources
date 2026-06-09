# ux::CLauncherMainTaskDialog::SetLauncherEnabled(bool)

- ea: `0x18000ab94`
- end: `0x18000ad01`
- name: `?SetLauncherEnabled@CLauncherMainTaskDialog@ux@@AEAAX_N@Z`
- size: `365`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *this, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000a4e8`

## callees

- `0x1800016e4`
- `0x18000ab94`
- `0x18000cbd4`
- `0x18000ccb0`
- `0x18000cd50`
- `0x18000ce70`
- `0x18000e948`
- `0x18000f288`
- `0x180011010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x18000abfa`
- `USER32!GetActiveWindow` at `0x18000abfa`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::SetLauncherEnabled(ux::CLauncherMainTaskDialog *this, char a2)
{
  HWND v4; // rax
  __int64 v5; // r8
  void *v6; // rax
  void *v7; // rbx
  __int64 v8; // rdx
  enum _FIRMWARE_TYPE Firmware; // eax
  char v10; // dl
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rdi
  void *v13; // [rsp+20h] [rbp-30h]
  __m128i v14; // [rsp+30h] [rbp-20h] BYREF
  __int128 v15; // [rsp+40h] [rbp-10h] BYREF
  HWND ActiveWindow; // [rsp+88h] [rbp+38h] BYREF

  v4 = (HWND)operator new(0x40u);
  ActiveWindow = v4;
  if ( v4 )
    v4 = (HWND)utils::CAsyncResult<bool>::CAsyncResult<bool>((__int64)v4, (__int64)this, v5);
  v14 = 0;
  std::tr1::shared_ptr<utils::CAsyncResult<bool>>::_Resetp<utils::CAsyncResult<bool>>(&v14, v4);
  v6 = operator new(0x28u);
  v7 = v6;
  v13 = v6;
  if ( v6 )
  {
    ActiveWindow = GetActiveWindow();
    LOBYTE(v8) = a2;
    v6 = (void *)CSetLauncherWorkItem::CSetLauncherWorkItem(v7, v8, &v14, &ActiveWindow, v13);
  }
  v15 = 0;
  std::tr1::shared_ptr<utils::IWorkItem>::_Resetp<CSetLauncherWorkItem>(&v15, v6);
  Firmware = utils::CMachine::GetFirmware();
  v10 = 0;
  if ( Firmware != FirmwareTypeUefi )
    v10 = a2;
  if ( v10 )
    utils::CThreadPool::StartUserWorkItem(&v15);
  else
    (**(void (__fastcall ***)(_QWORD))v15)(v15);
  v11 = (volatile signed __int32 *)_mm_srli_si128(_mm_load_si128(&v14), 8).m128i_u64[0];
  v14 = 0;
  v12 = (volatile signed __int32 *)*((_QWORD *)&v15 + 1);
  if ( *((_QWORD *)&v15 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v11 && !_InterlockedDecrement(v11 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
    if ( !_InterlockedDecrement(v11 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
}

```

## disassembly

```asm
0x18000ab94  mov     [rsp-18h+arg_0], rbx
0x18000ab99  push    rbp
0x18000ab9a  push    rsi
0x18000ab9b  push    rdi
0x18000ab9c  mov     rbp, rsp
0x18000ab9f  sub     rsp, 50h
0x18000aba3  movzx   edi, dl
0x18000aba6  mov     rbx, rcx
0x18000aba9  mov     [rbp+arg_10], 0
0x18000abb0  mov     ecx, 40h ; '@'; Size
0x18000abb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000abba  mov     [rbp+arg_18], rax
0x18000abbe  test    rax, rax
0x18000abc1  jz      short loc_18000ABCF
0x18000abc3  mov     rdx, rbx
0x18000abc6  mov     rcx, rax
0x18000abc9  call    ??0?$CAsyncResult@_N@utils@@QEAA@PEAVIAsyncCallback@1@PEAX@Z; utils::CAsyncResult<bool>::CAsyncResult<bool>(utils::IAsyncCallback *,void *)
0x18000abce  nop
0x18000abcf  xorps   xmm0, xmm0
0x18000abd2  movdqa  [rbp+var_20], xmm0
0x18000abd7  mov     rdx, rax
0x18000abda  lea     rcx, [rbp+var_20]
0x18000abde  call    ??$_Resetp@V?$CAsyncResult@_N@utils@@@?$shared_ptr@V?$CAsyncResult@_N@utils@@@tr1@std@@AEAAXPEAV?$CAsyncResult@_N@utils@@@Z; std::tr1::shared_ptr<utils::CAsyncResult<bool>>::_Resetp<utils::CAsyncResult<bool>>(utils::CAsyncResult<bool> *)
0x18000abe3  nop
0x18000abe4  mov     ecx, 28h ; '('; Size
0x18000abe9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000abee  mov     rbx, rax
0x18000abf1  mov     qword ptr [rbp+var_30], rax
0x18000abf5  test    rax, rax
0x18000abf8  jz      short loc_18000AC18
0x18000abfa  call    cs:__imp_GetActiveWindow
0x18000ac00  mov     [rbp+arg_18], rax
0x18000ac04  lea     r9, [rbp+arg_18]
0x18000ac08  lea     r8, [rbp+var_20]
0x18000ac0c  mov     dl, dil
0x18000ac0f  mov     rcx, rbx
0x18000ac12  call    ??0CSetLauncherWorkItem@@AEAA@_NAEBV?$shared_ptr@V?$CAsyncResult@_N@utils@@@tr1@std@@AEBVCWindow@ATL@@@Z; CSetLauncherWorkItem::CSetLauncherWorkItem(bool,std::tr1::shared_ptr<utils::CAsyncResult<bool>> const &,ATL::CWindow const &)
0x18000ac17  nop
0x18000ac18  xorps   xmm0, xmm0
0x18000ac1b  movdqu  [rbp+var_10], xmm0
0x18000ac20  mov     rdx, rax
0x18000ac23  lea     rcx, [rbp+var_10]
0x18000ac27  call    ??$_Resetp@VCSetLauncherWorkItem@@@?$shared_ptr@VIWorkItem@utils@@@tr1@std@@AEAAXPEAVCSetLauncherWorkItem@@@Z; std::tr1::shared_ptr<utils::IWorkItem>::_Resetp<CSetLauncherWorkItem>(CSetLauncherWorkItem *)
0x18000ac2c  nop
0x18000ac2d  call    ?GetFirmware@CMachine@utils@@SA?AW4_FIRMWARE_TYPE@@XZ; utils::CMachine::GetFirmware(void)
0x18000ac32  xor     edx, edx
0x18000ac34  cmp     eax, 2
0x18000ac37  cmovnz  edx, edi
0x18000ac3a  test    dl, dl
0x18000ac3c  jz      short loc_18000AC49
0x18000ac3e  lea     rcx, [rbp+var_10]
0x18000ac42  call    ?StartUserWorkItem@CThreadPool@utils@@SAXAEBV?$shared_ptr@VIWorkItem@utils@@@tr1@std@@@Z; utils::CThreadPool::StartUserWorkItem(std::tr1::shared_ptr<utils::IWorkItem> const &)
0x18000ac47  jmp     short loc_18000AC58
0x18000ac49  mov     rcx, qword ptr [rbp+var_10]
0x18000ac4d  mov     rax, [rcx]
0x18000ac50  mov     rax, [rax]
0x18000ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac58  movdqa  xmm0, [rbp+var_20]
0x18000ac5d  movdqa  [rbp+var_30], xmm0
0x18000ac62  psrldq  xmm0, 8
0x18000ac67  movq    rbx, xmm0
0x18000ac6c  xorps   xmm0, xmm0
0x18000ac6f  movdqa  [rbp+var_20], xmm0
0x18000ac74  mov     [rbp+arg_10], 1
0x18000ac7b  or      esi, 0FFFFFFFFh
0x18000ac7e  mov     rdi, qword ptr [rbp+var_10+8]
0x18000ac82  test    rdi, rdi
0x18000ac85  jz      short loc_18000ACBB
0x18000ac87  mov     eax, esi
0x18000ac89  lock xadd [rdi+8], eax
0x18000ac8e  add     eax, esi
0x18000ac90  jnz     short loc_18000ACBB
0x18000ac92  mov     rax, [rdi]
0x18000ac95  mov     rcx, rdi
0x18000ac98  mov     rax, [rax]
0x18000ac9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca0  mov     eax, esi
0x18000aca2  lock xadd [rdi+0Ch], eax
0x18000aca7  add     eax, esi
0x18000aca9  jnz     short loc_18000ACBB
0x18000acab  mov     rax, [rdi]
0x18000acae  mov     rcx, rdi
0x18000acb1  mov     rax, [rax+8]
0x18000acb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acba  nop
0x18000acbb  test    rbx, rbx
0x18000acbe  jz      short loc_18000ACF4
0x18000acc0  mov     eax, esi
0x18000acc2  lock xadd [rbx+8], eax
0x18000acc7  add     eax, esi
0x18000acc9  jnz     short loc_18000ACF4
0x18000accb  mov     rax, [rbx]
0x18000acce  mov     rcx, rbx
0x18000acd1  mov     rax, [rax]
0x18000acd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acd9  mov     eax, esi
0x18000acdb  lock xadd [rbx+0Ch], eax
0x18000ace0  add     eax, esi
0x18000ace2  jnz     short loc_18000ACF4
0x18000ace4  mov     rax, [rbx]
0x18000ace7  mov     rcx, rbx
0x18000acea  mov     rax, [rax+8]
0x18000acee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf3  nop
0x18000acf4  mov     rbx, [rsp+50h+arg_0]
0x18000acf9  add     rsp, 50h
0x18000acfd  pop     rdi
0x18000acfe  pop     rsi
0x18000acff  pop     rbp
0x18000ad00  retn
```
