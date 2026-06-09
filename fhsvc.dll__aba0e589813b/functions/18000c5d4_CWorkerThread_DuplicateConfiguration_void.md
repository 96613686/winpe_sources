# CWorkerThread::DuplicateConfiguration(void)

- ea: `0x18000c5d4`
- end: `0x18000c79e`
- name: `?DuplicateConfiguration@CWorkerThread@@AEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c210`

## callees

- `0x180008f10`
- `0x180009690`
- `0x18000c5d4`
- `0x18000ca14`
- `0x18000d840`
- `0x1800107ac`
- `0x180013010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18000c620`
- `ADVAPI32!SetThreadToken` at `0x18000c73f`
- `ADVAPI32!SetThreadToken` at `0x18000c620`
- `ADVAPI32!SetThreadToken` at `0x18000c73f`
- `KERNEL32!GetLastError` at `0x18000c62a`
- `KERNEL32!GetLastError` at `0x18000c75b`
- `KERNEL32!GetLastError` at `0x18000c62a`
- `KERNEL32!GetLastError` at `0x18000c75b`

## pseudocode

```c
__int64 __fastcall CWorkerThread::DuplicateConfiguration(CWorkerThread *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rcx
  int v8; // eax
  struct IUnknown *v9; // rdx
  PVOID *v10; // rcx
  int v11; // eax
  signed int v12; // eax
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids);
  if ( SetThreadToken(0, *((HANDLE *)this + 4)) )
  {
    v7 = *((_QWORD *)this + 1);
    if ( v7 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7);
      if ( v8 < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
              (unsigned int)v8);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
            WPP_SF_ss(
              (unsigned int)v10[2],
              62,
              (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
              (unsigned int)"FALSE",
              (__int64)"IFhCatalog::Detach has failed");
        }
      }
      if ( *((_QWORD *)this + 1) )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 1, v9);
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 344LL))(*(_QWORD *)this, &v14);
    v3 = v11;
    if ( v11 >= 0 )
    {
      *((_DWORD *)this + 23) = 1;
      goto LABEL_26;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 63;
      v6 = (unsigned int)v11;
      goto LABEL_10;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 60;
      v6 = v3;
LABEL_10:
      WPP_SF_d(v4[2], v5, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v6);
    }
  }
LABEL_26:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
      (unsigned int)v12);
  }
  ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(&v14);
  return v3;
}

```

## disassembly

```asm
0x18000c5d4  push    rbx
0x18000c5d6  push    rbp
0x18000c5d7  push    rsi
0x18000c5d8  push    rdi
0x18000c5d9  sub     rsp, 38h
0x18000c5dd  mov     rdi, rcx
0x18000c5e0  mov     [rsp+58h+arg_0], 0
0x18000c5e9  lea     rsi, WPP_GLOBAL_Control
0x18000c5f0  lea     rbp, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x18000c5f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5fe  cmp     rcx, rsi
0x18000c601  jz      short loc_18000C61A
0x18000c603  test    byte ptr [rcx+1Ch], 2
0x18000c607  jz      short loc_18000C61A
0x18000c609  mov     edx, 3Bh ; ';'
0x18000c60e  mov     r8, rbp
0x18000c611  mov     rcx, [rcx+10h]
0x18000c615  call    WPP_SF_
0x18000c61a  mov     rdx, [rdi+20h]; Token
0x18000c61e  xor     ecx, ecx; Thread
0x18000c620  call    cs:__imp_SetThreadToken
0x18000c626  test    eax, eax
0x18000c628  jnz     short loc_18000C672
0x18000c62a  call    cs:__imp_GetLastError
0x18000c630  mov     ebx, eax
0x18000c632  test    eax, eax
0x18000c634  jle     short loc_18000C63F
0x18000c636  movzx   ebx, ax
0x18000c639  or      ebx, 80070000h
0x18000c63f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c646  cmp     rcx, rsi
0x18000c649  jz      loc_18000C73B
0x18000c64f  test    byte ptr [rcx+1Ch], 1
0x18000c653  jz      loc_18000C73B
0x18000c659  mov     edx, 3Ch ; '<'
0x18000c65e  mov     r9d, ebx
0x18000c661  mov     r8, rbp
0x18000c664  mov     rcx, [rcx+10h]
0x18000c668  call    WPP_SF_d
0x18000c66d  jmp     loc_18000C73B
0x18000c672  lea     rbx, [rdi+8]
0x18000c676  mov     rcx, [rbx]
0x18000c679  test    rcx, rcx
0x18000c67c  jz      short loc_18000C6F8
0x18000c67e  mov     rax, [rcx]
0x18000c681  mov     rax, [rax+28h]
0x18000c685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68a  test    eax, eax
0x18000c68c  jns     short loc_18000C6EA
0x18000c68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c695  cmp     rcx, rsi
0x18000c698  jz      short loc_18000C6EA
0x18000c69a  test    byte ptr [rcx+1Ch], 2
0x18000c69e  jz      short loc_18000C6BB
0x18000c6a0  mov     edx, 3Dh ; '='
0x18000c6a5  mov     r9d, eax
0x18000c6a8  mov     r8, rbp
0x18000c6ab  mov     rcx, [rcx+10h]
0x18000c6af  call    WPP_SF_d
0x18000c6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6bb  cmp     rcx, rsi
0x18000c6be  jz      short loc_18000C6EA
0x18000c6c0  test    byte ptr [rcx+1Ch], 4
0x18000c6c4  jz      short loc_18000C6EA
0x18000c6c6  mov     edx, 3Eh ; '>'
0x18000c6cb  lea     rax, aIfhcatalogDeta; "IFhCatalog::Detach has failed"
0x18000c6d2  mov     [rsp+58h+var_38], rax
0x18000c6d7  lea     r9, aFalse; "FALSE"
0x18000c6de  mov     r8, rbp
0x18000c6e1  mov     rcx, [rcx+10h]
0x18000c6e5  call    WPP_SF_ss
0x18000c6ea  cmp     qword ptr [rbx], 0
0x18000c6ee  jz      short loc_18000C6F8
0x18000c6f0  mov     rcx, rbx; struct IUnknown **
0x18000c6f3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000c6f8  mov     rcx, [rdi]
0x18000c6fb  mov     rax, [rcx]
0x18000c6fe  lea     rdx, [rsp+58h+arg_0]
0x18000c703  mov     rax, [rax+158h]
0x18000c70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c70f  mov     ebx, eax
0x18000c711  test    eax, eax
0x18000c713  jns     short loc_18000C734
0x18000c715  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c71c  cmp     rcx, rsi
0x18000c71f  jz      short loc_18000C73B
0x18000c721  test    byte ptr [rcx+1Ch], 1
0x18000c725  jz      short loc_18000C73B
0x18000c727  mov     edx, 3Fh ; '?'
0x18000c72c  mov     r9d, eax
0x18000c72f  jmp     loc_18000C661
0x18000c734  mov     dword ptr [rdi+5Ch], 1
0x18000c73b  xor     edx, edx; Token
0x18000c73d  xor     ecx, ecx; Thread
0x18000c73f  call    cs:__imp_SetThreadToken
0x18000c745  test    eax, eax
0x18000c747  jnz     short loc_18000C789
0x18000c749  mov     rax, cs:WPP_GLOBAL_Control
0x18000c750  cmp     rax, rsi
0x18000c753  jz      short loc_18000C789
0x18000c755  test    byte ptr [rax+1Ch], 1
0x18000c759  jz      short loc_18000C789
0x18000c75b  call    cs:__imp_GetLastError
0x18000c761  test    eax, eax
0x18000c763  jle     short loc_18000C76D
0x18000c765  movzx   eax, ax
0x18000c768  or      eax, 80070000h
0x18000c76d  mov     edx, 40h ; '@'
0x18000c772  mov     r9d, eax
0x18000c775  mov     r8, rbp
0x18000c778  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c77f  mov     rcx, [rcx+10h]
0x18000c783  call    WPP_SF_d
0x18000c788  nop
0x18000c789  lea     rcx, [rsp+58h+arg_0]
0x18000c78e  call    ??1?$CComPtrBase@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(void)
0x18000c793  mov     eax, ebx
0x18000c795  add     rsp, 38h
0x18000c799  pop     rdi
0x18000c79a  pop     rsi
0x18000c79b  pop     rbp
0x18000c79c  pop     rbx
0x18000c79d  retn
```
