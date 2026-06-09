# RegistryNotifier::Subscribe(void (*)(void *,void const *,ulong),void *)

- ea: `0x18006d580`
- end: `0x18006d750`
- name: `?Subscribe@RegistryNotifier@@UEAAXP6AXPEAXPEBXK@Z0@Z`
- size: `464`
- prototype: `void __fastcall(RegistryNotifier *__hidden this, void (*)(void *, const void *, unsigned int), void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18006d580`
- `0x18006d758`
- `0x180080430`
- `0x18009b668`
- `0x18009d024`
- `0x1800a2100`
- `0x1800b2dcc`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d69c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d69c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006d6ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006d6ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006d64d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006d64d`

## pseudocode

```c
void __fastcall RegistryNotifier::Subscribe(
        RegistryNotifier *this,
        void (*a2)(void *, const void *, unsigned int),
        void *a3)
{
  int v6; // eax
  struct _TP_WAIT *ThreadpoolWait; // rdi
  struct _TP_WAIT *v8; // rsi
  unsigned int LastError; // eax
  _QWORD *v10; // rax
  const ComError *v11; // [rsp+30h] [rbp-D8h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+48h] [rbp-C0h]
  int v14; // [rsp+58h] [rbp-B0h]
  int v15; // [rsp+5Ch] [rbp-ACh]
  int v16; // [rsp+60h] [rbp-A8h]
  void **v17; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v18; // [rsp+A8h] [rbp-60h]
  unsigned int v19; // [rsp+B8h] [rbp-50h]
  int v20; // [rsp+BCh] [rbp-4Ch]
  int v21; // [rsp+C0h] [rbp-48h]
  char v23; // [rsp+128h] [rbp+20h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(RegistryNotifier *))(*(_QWORD *)this + 16LL))(this) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids);
  }
  else
  {
    *((_QWORD *)this + 1) = a2;
    *((_QWORD *)this + 2) = a3;
    v6 = RegistryNotifier::SetupAsyncRegistryChangeEvent(this);
    try
    {
      if ( v6 < 0 )
      {
        v13 = 0;
        pExceptionObject = &ComError::`vftable';
        v14 = v6;
        v15 = 1059;
        v16 = 1;
        throw (ComError *)&pExceptionObject;
      }
      ThreadpoolWait = CreateThreadpoolWait(RegistryNotifier::RegistryChangeCallback, this, 0);
      v8 = (struct _TP_WAIT *)*((_QWORD *)this + 11);
      if ( v8 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
        wil::details::DestroyThreadPoolWait<0>::Destroy(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
      }
      *((_QWORD *)this + 11) = ThreadpoolWait;
      if ( !ThreadpoolWait )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v18 = 0;
        v17 = &ComError::`vftable';
        v19 = LastError;
        v20 = 1064;
        v21 = 1;
        throw (ComError *)&v17;
      }
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)this + 10), 0);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = (_QWORD *)((char *)this + 32);
        if ( *((_QWORD *)this + 7) > 7u )
          v10 = (_QWORD *)*v10;
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids,
          *((_QWORD *)this + 3),
          (__int64)v10);
      }
    }
    catch ( const ComError *v11 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          &WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids,
          *((unsigned int *)v11 + 6),
          *((_DWORD *)v11 + 7));
      (*(void (__fastcall **)(RegistryNotifier *))(*(_QWORD *)this + 24LL))(this);
      throw;
    }
  }
}

```

## disassembly

```asm
0x18006d580  mov     [rsp+arg_8], rbx
0x18006d585  mov     [rsp+arg_10], rsi
0x18006d58a  mov     [rsp+arg_0], rcx
0x18006d58f  push    rdi
0x18006d590  sub     rsp, 100h
0x18006d597  mov     rdi, r8
0x18006d59a  mov     rsi, rdx
0x18006d59d  mov     rbx, rcx
0x18006d5a0  mov     rax, [rcx]
0x18006d5a3  mov     rax, [rax+10h]
0x18006d5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5ac  test    al, al
0x18006d5ae  jz      short loc_18006D5F3
0x18006d5b0  lea     rax, WPP_GLOBAL_Control
0x18006d5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5be  cmp     rcx, rax
0x18006d5c1  jz      short loc_18006D5DE
0x18006d5c3  test    byte ptr [rcx+1Ch], 2
0x18006d5c7  jz      short loc_18006D5DE
0x18006d5c9  mov     edx, 28h ; '('
0x18006d5ce  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x18006d5d5  mov     rcx, [rcx+10h]
0x18006d5d9  call    WPP_SF_
0x18006d5de  lea     r11, [rsp+108h+var_8]
0x18006d5e6  mov     rbx, [r11+18h]
0x18006d5ea  mov     rsi, [r11+20h]
0x18006d5ee  mov     rsp, r11
0x18006d5f1  pop     rdi
0x18006d5f2  retn
0x18006d5f3  mov     [rbx+8], rsi
0x18006d5f7  mov     [rbx+10h], rdi
0x18006d5fb  mov     rcx, rbx; this
0x18006d5fe  call    ?SetupAsyncRegistryChangeEvent@RegistryNotifier@@AEAAJXZ; RegistryNotifier::SetupAsyncRegistryChangeEvent(void)
0x18006d603  test    eax, eax
0x18006d605  jns     short loc_18006D640
0x18006d607  xorps   xmm0, xmm0
0x18006d60a  movups  [rsp+108h+var_C0], xmm0
0x18006d60f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006d616  mov     [rsp+108h+pExceptionObject], rcx
0x18006d61b  mov     [rsp+108h+var_B0], eax
0x18006d61f  mov     [rsp+108h+var_AC], 423h
0x18006d627  mov     [rsp+108h+var_A8], 1
0x18006d62f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006d636  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18006d63b  call    _CxxThrowException_0
0x18006d640  xor     r8d, r8d; pcbe
0x18006d643  mov     rdx, rbx; pv
0x18006d646  lea     rcx, ?RegistryChangeCallback@RegistryNotifier@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18006d64d  call    cs:__imp_CreateThreadpoolWait
0x18006d653  mov     rdi, rax
0x18006d656  mov     rsi, [rbx+58h]
0x18006d65a  test    rsi, rsi
0x18006d65d  jz      short loc_18006D681
0x18006d65f  lea     rcx, [rsp+108h+arg_18]; this
0x18006d667  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006d66c  mov     rcx, rsi; pwa
0x18006d66f  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18006d674  lea     rcx, [rsp+108h+arg_18]; this
0x18006d67c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006d681  mov     [rbx+58h], rdi
0x18006d685  test    rdi, rdi
0x18006d688  jnz     short loc_18006D6F5
0x18006d68a  call    cs:__imp_GetLastError
0x18006d690  test    eax, eax
0x18006d692  jg      short loc_18006D69C
0x18006d694  call    cs:__imp_GetLastError
0x18006d69a  jmp     short loc_18006D6AA
0x18006d69c  call    cs:__imp_GetLastError
0x18006d6a2  movzx   eax, ax
0x18006d6a5  or      eax, 80070000h
0x18006d6aa  xorps   xmm0, xmm0
0x18006d6ad  movups  [rsp+108h+var_60], xmm0
0x18006d6b5  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006d6bc  mov     [rsp+108h+var_68], rcx
0x18006d6c4  mov     [rsp+108h+var_50], eax
0x18006d6cb  mov     [rsp+108h+var_4C], 428h
0x18006d6d6  mov     [rsp+108h+var_48], 1
0x18006d6e1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006d6e8  lea     rcx, [rsp+108h+var_68]; pExceptionObject
0x18006d6f0  call    _CxxThrowException_0
0x18006d6f5  xor     r8d, r8d; pftTimeout
0x18006d6f8  mov     rdx, [rbx+50h]; h
0x18006d6fc  mov     rcx, rdi; pwa
0x18006d6ff  call    cs:__imp_SetThreadpoolWait
0x18006d705  lea     rax, WPP_GLOBAL_Control
0x18006d70c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d713  cmp     rcx, rax
0x18006d716  jz      short loc_18006D74B
0x18006d718  test    byte ptr [rcx+1Ch], 1
0x18006d71c  jz      short loc_18006D74B
0x18006d71e  lea     rax, [rbx+20h]
0x18006d722  cmp     qword ptr [rax+18h], 7
0x18006d727  jbe     short loc_18006D72C
0x18006d729  mov     rax, [rax]
0x18006d72c  mov     edx, 29h ; ')'
0x18006d731  mov     [rsp+108h+var_E8], rax
0x18006d736  mov     r9, [rbx+18h]
0x18006d73a  lea     r8, WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids
0x18006d741  mov     rcx, [rcx+10h]
0x18006d745  call    WPP_SF_qS
0x18006d74a  nop
0x18006d74b  jmp     loc_18006D5DE
```
