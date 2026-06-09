# CExtSessionLogger::Delete(ushort const *)

- ea: `0x18004fd60`
- end: `0x180050008`
- name: `?Delete@CExtSessionLogger@@QEAAHPEBG@Z`
- size: `680`
- prototype: `__int64 __fastcall(CExtSessionLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18004fa30`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18004fd60`
- `0x1800585e8`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004fdf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004fdf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004feee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004feee`
- `OLEAUT32!__imp_SysAllocString` at `0x18004fe86`
- `OLEAUT32!__imp_SysAllocString` at `0x18004fe86`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fee4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ffdf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fee4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ffdf`

## string_xrefs

- `0x18004fe53`: `RSOP_ExtensionStatus.extensionGuid="%s"`
- `0x18004fd8b`: `CExtSessionLogger::Delete: Failed to initialize.`
- `0x18004fdae`: `CExtSessionLogger::Delete: Failed to initialize.`
- `0x18004fe1a`: `CExtSessionLogger::Delete: Not enough memory.`
- `0x18004fe3d`: `CExtSessionLogger::Delete: Not enough memory.`
- `0x18004fead`: `CExtSessionLogger::Delete: Failed to allocate memory.`
- `0x18004fed0`: `CExtSessionLogger::Delete: Failed to allocate memory.`
- `0x18004ff42`: `CExtSessionLogger::Delete: No extension status history to delete.`
- `0x18004ff67`: `CExtSessionLogger::Delete: No extension status history to delete.`
- `0x18004ff94`: `CExtSessionLogger::Delete: Failed to DeleteInstance for %s with 0x%x`
- `0x18004ffc2`: `CExtSessionLogger::Delete: Failed to DeleteInstance for %s with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CExtSessionLogger::Delete(CExtSessionLogger *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rbx
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  OLECHAR *v7; // rax
  OLECHAR *v8; // rdi
  OLECHAR *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  OLECHAR *v12; // [rsp+60h] [rbp+8h] BYREF
  __int64 v13; // [rsp+70h] [rbp+18h] BYREF
  OLECHAR *v14; // [rsp+78h] [rbp+20h]

  v2 = a2;
  if ( !*(_DWORD *)this )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CExtSessionLogger::Delete: Failed to initialize.");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CExtSessionLogger::Delete: Failed to initialize.");
      }
    }
    return 0;
  }
  if ( !a2 )
    v2 = L"{00000000-0000-0000-0000-000000000000}";
  v13 = 0;
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  v6 = v5 + 49;
  v7 = (OLECHAR *)LocalAlloc(0x40u, 2 * (v5 + 49));
  v8 = v7;
  v12 = v7;
  if ( !v7 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CExtSessionLogger::Delete: Not enough memory.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CExtSessionLogger::Delete: Not enough memory.");
      }
    }
    goto LABEL_21;
  }
  if ( (int)StringCchPrintfW(v7, v6, L"RSOP_ExtensionStatus.extensionGuid=\"%s\"", v2) < 0 )
  {
LABEL_21:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v12);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    return 0;
  }
  v9 = SysAllocString(v8);
  v14 = v9;
  if ( !v9 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CExtSessionLogger::Delete: Failed to allocate memory.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CExtSessionLogger::Delete: Failed to allocate memory.");
      }
    }
    SysFreeString(0);
    LocalFree(v8);
    return 0;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          v9,
          0,
          0,
          0);
  if ( v10 >= 0 )
  {
    v11 = 1;
  }
  else
  {
    if ( v10 == -2147217406 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CExtSessionLogger::Delete: No extension status history to delete.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CExtSessionLogger::Delete: No extension status history to delete.");
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CExtSessionLogger::Delete: Failed to DeleteInstance for %s with 0x%x", v9, (unsigned int)v10);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"CExtSessionLogger::Delete: Failed to DeleteInstance for %s with 0x%x",
          v9,
          (unsigned int)v10);
      }
    }
    v11 = 0;
  }
  SysFreeString(v9);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  return v11;
}

```

## disassembly

```asm
0x18004fd60  push    rbx
0x18004fd62  push    rbp
0x18004fd63  push    rsi
0x18004fd64  push    rdi
0x18004fd65  push    r14
0x18004fd67  sub     rsp, 30h
0x18004fd6b  mov     rbx, rdx
0x18004fd6e  mov     rsi, rcx
0x18004fd71  xor     ebp, ebp
0x18004fd73  cmp     [rcx], ebp
0x18004fd75  jnz     short loc_18004FDC6
0x18004fd77  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18004fd7d  jz      short loc_18004FDBF
0x18004fd7f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004fd86  test    rax, rax
0x18004fd89  jz      short loc_18004FD9C
0x18004fd8b  lea     rdx, aCextsessionlog_12; "CExtSessionLogger::Delete: Failed to in"...
0x18004fd92  lea     ecx, [rbp+2]
0x18004fd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd9a  jmp     short loc_18004FDBF
0x18004fd9c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18004fda3  jz      short loc_18004FDBF
0x18004fda5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004fdac  jz      short loc_18004FDBF
0x18004fdae  lea     rdx, aCextsessionlog_12; "CExtSessionLogger::Delete: Failed to in"...
0x18004fdb5  mov     ecx, 2; unsigned int
0x18004fdba  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004fdbf  xor     eax, eax
0x18004fdc1  jmp     loc_18004FFFD
0x18004fdc6  lea     rax, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18004fdcd  test    rbx, rbx
0x18004fdd0  cmovz   rbx, rax
0x18004fdd4  mov     [rsp+58h+arg_10], rbp
0x18004fdd9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fddd  inc     rax
0x18004fde0  cmp     [rbx+rax*2], bp
0x18004fde4  jnz     short loc_18004FDDD
0x18004fde6  lea     r14, [rax+31h]
0x18004fdea  lea     rdx, [r14+r14]; uBytes
0x18004fdee  mov     ecx, 40h ; '@'; uFlags
0x18004fdf3  call    cs:__imp_LocalAlloc
0x18004fdf9  mov     rdi, rax
0x18004fdfc  mov     [rsp+58h+arg_0], rax
0x18004fe01  test    rax, rax
0x18004fe04  jnz     short loc_18004FE50
0x18004fe06  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18004fe0c  jz      short loc_18004FE69
0x18004fe0e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004fe15  test    rax, rax
0x18004fe18  jz      short loc_18004FE2B
0x18004fe1a  lea     rdx, aCextsessionlog_8; "CExtSessionLogger::Delete: Not enough m"...
0x18004fe21  lea     ecx, [rdi+2]
0x18004fe24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe29  jmp     short loc_18004FE69
0x18004fe2b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18004fe32  jz      short loc_18004FE69
0x18004fe34  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004fe3b  jz      short loc_18004FE69
0x18004fe3d  lea     rdx, aCextsessionlog_8; "CExtSessionLogger::Delete: Not enough m"...
0x18004fe44  mov     ecx, 2; unsigned int
0x18004fe49  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004fe4e  jmp     short loc_18004FE69
0x18004fe50  mov     r9, rbx
0x18004fe53  lea     r8, aRsopExtensions_0; "RSOP_ExtensionStatus.extensionGuid=\"%s"...
0x18004fe5a  mov     rdx, r14; unsigned __int64
0x18004fe5d  mov     rcx, rdi; unsigned __int16 *
0x18004fe60  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe65  test    eax, eax
0x18004fe67  jns     short loc_18004FE83
0x18004fe69  lea     rcx, [rsp+58h+arg_0]
0x18004fe6e  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18004fe73  nop
0x18004fe74  lea     rcx, [rsp+58h+arg_10]
0x18004fe79  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004fe7e  jmp     loc_18004FDBF
0x18004fe83  mov     rcx, rdi; psz
0x18004fe86  call    cs:__imp_SysAllocString
0x18004fe8c  mov     rbx, rax
0x18004fe8f  mov     [rsp+58h+arg_18], rax
0x18004fe94  test    rax, rax
0x18004fe97  jnz     short loc_18004FEFA
0x18004fe99  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18004fe9f  jz      short loc_18004FEE2
0x18004fea1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004fea8  test    rax, rax
0x18004feab  jz      short loc_18004FEBE
0x18004fead  lea     rdx, aCextsessionlog_14; "CExtSessionLogger::Delete: Failed to al"...
0x18004feb4  lea     ecx, [rbx+2]
0x18004feb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004febc  jmp     short loc_18004FEE2
0x18004febe  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18004fec5  jz      short loc_18004FEE2
0x18004fec7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004fece  jz      short loc_18004FEE2
0x18004fed0  lea     rdx, aCextsessionlog_14; "CExtSessionLogger::Delete: Failed to al"...
0x18004fed7  mov     ecx, 2; unsigned int
0x18004fedc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004fee1  nop
0x18004fee2  xor     ecx, ecx; bstrString
0x18004fee4  call    cs:__imp_SysFreeString
0x18004feea  nop
0x18004feeb  mov     rcx, rdi; hMem
0x18004feee  call    cs:__imp_LocalFree
0x18004fef4  nop
0x18004fef5  jmp     loc_18004FDBF
0x18004fefa  mov     rcx, [rsi+8]
0x18004fefe  mov     rax, [rcx]
0x18004ff01  mov     [rsp+58h+var_38], rbp
0x18004ff06  xor     r9d, r9d
0x18004ff09  xor     r8d, r8d
0x18004ff0c  mov     rdx, rbx
0x18004ff0f  mov     rax, [rax+80h]
0x18004ff16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff1b  test    eax, eax
0x18004ff1d  jns     loc_18004FFD7
0x18004ff23  cmp     eax, 80041002h
0x18004ff28  jnz     short loc_18004FF7A
0x18004ff2a  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18004ff30  jz      loc_18004FFD3
0x18004ff36  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004ff3d  test    rax, rax
0x18004ff40  jz      short loc_18004FF55
0x18004ff42  lea     rdx, aCextsessionlog_0; "CExtSessionLogger::Delete: No extension"...
0x18004ff49  mov     ecx, 4
0x18004ff4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff53  jmp     short loc_18004FFD3
0x18004ff55  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18004ff5c  jz      short loc_18004FFD3
0x18004ff5e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004ff65  jz      short loc_18004FFD3
0x18004ff67  lea     rdx, aCextsessionlog_0; "CExtSessionLogger::Delete: No extension"...
0x18004ff6e  mov     ecx, 4; unsigned int
0x18004ff73  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004ff78  jmp     short loc_18004FFD3
0x18004ff7a  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18004ff80  jz      short loc_18004FFD3
0x18004ff82  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004ff89  test    r10, r10
0x18004ff8c  jz      short loc_18004FFAA
0x18004ff8e  mov     r9d, eax
0x18004ff91  mov     r8, rbx
0x18004ff94  lea     rdx, aCextsessionlog_1; "CExtSessionLogger::Delete: Failed to De"...
0x18004ff9b  mov     ecx, 4
0x18004ffa0  mov     rax, r10
0x18004ffa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffa8  jmp     short loc_18004FFD3
0x18004ffaa  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18004ffb1  jz      short loc_18004FFD3
0x18004ffb3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004ffba  jz      short loc_18004FFD3
0x18004ffbc  mov     r9d, eax
0x18004ffbf  mov     r8, rbx
0x18004ffc2  lea     rdx, aCextsessionlog_1; "CExtSessionLogger::Delete: Failed to De"...
0x18004ffc9  mov     ecx, 4; unsigned int
0x18004ffce  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004ffd3  mov     edi, ebp
0x18004ffd5  jmp     short loc_18004FFDC
0x18004ffd7  mov     edi, 1
0x18004ffdc  mov     rcx, rbx; bstrString
0x18004ffdf  call    cs:__imp_SysFreeString
0x18004ffe5  nop
0x18004ffe6  lea     rcx, [rsp+58h+arg_0]
0x18004ffeb  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18004fff0  nop
0x18004fff1  lea     rcx, [rsp+58h+arg_10]
0x18004fff6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004fffb  mov     eax, edi
0x18004fffd  add     rsp, 30h
0x180050001  pop     r14
0x180050003  pop     rdi
0x180050004  pop     rsi
0x180050005  pop     rbp
0x180050006  pop     rbx
0x180050007  retn
```
