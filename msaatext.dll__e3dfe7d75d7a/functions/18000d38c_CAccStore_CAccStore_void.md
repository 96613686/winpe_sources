# CAccStore::CAccStore(void)

- ea: `0x18000d38c`
- end: `0x18000d542`
- name: `??0CAccStore@@QEAA@XZ`
- size: `438`
- prototype: `CAccStore *__fastcall(CAccStore *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000f3f0`
- `0x18000fd50`

## callees

- `0x180002610`
- `0x1800026d0`
- `0x180003078`
- `0x18000d38c`
- `0x18000e0b8`
- `0x180012b40`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d4fc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d4fc`
- `KERNEL32!CreateEventW` at `0x18000d511`
- `KERNEL32!CreateEventW` at `0x18000d511`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d440`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d440`

## string_xrefs

- `0x18000d46a`: `CoCreateInstance failed for CLSID_MSAAControl hr=`

## pseudocode

```c
CAccStore *__fastcall CAccStore::CAccStore(CAccStore *this)
{
  int ppv; // [rsp+20h] [rbp-29h]
  void *Src[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v5; // [rsp+68h] [rbp+1Fh]
  unsigned __int64 v6; // [rsp+70h] [rbp+27h]
  int v7; // [rsp+78h] [rbp+2Fh]

  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = std::_List_alloc<0,std::_List_base_types<DocInfo *>>::_Buynode0(this, 0, 0);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  if ( m_pTheStore )
    InternalTrace(L"windows\\oleacc\\msaatext\\msaastore.cpp", 0x68u, ppv, 0, (__int64)L"m_pTheStore == NULL");
  m_pTheStore = this;
  if ( CoCreateInstance(&CLSID_MSAAControl, 0, 1u, &IID_ITfMSAAControl, (LPVOID *)this + 8) )
  {
    v6 = 7;
    v5 = 0;
    LOWORD(Src[0]) = 0;
    v7 = -1;
    std::wstring::append(Src, L"CoCreateInstance failed for CLSID_MSAAControl hr=");
    operator<<(Src);
  }
  else
  {
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8)) )
      goto LABEL_9;
    v6 = 7;
    v5 = 0;
    LOWORD(Src[0]) = 0;
    v7 = -1;
    std::wstring::append(Src, L"SystemEnableMSAA failed hr=");
    operator<<(Src);
  }
  if ( v6 >= 8 )
    operator delete(Src[0]);
LABEL_9:
  *((_QWORD *)this + 6) = CreateEventW(0, 0, 1, L"MSAA_STORE_EVENT");
  return this;
}

```

## disassembly

```asm
0x18000d38c  mov     [rsp-8+arg_8], rbx
0x18000d391  mov     [rsp-8+arg_10], rsi
0x18000d396  push    rbp
0x18000d397  push    rdi
0x18000d398  push    r14
0x18000d39a  lea     rbp, [rsp-47h]
0x18000d39f  sub     rsp, 90h
0x18000d3a6  mov     rax, cs:__security_cookie
0x18000d3ad  xor     rax, rsp
0x18000d3b0  mov     [rbp+57h+var_20], rax
0x18000d3b4  mov     rdi, rcx
0x18000d3b7  mov     [rbp+57h+var_50], rcx
0x18000d3bb  xor     r14d, r14d
0x18000d3be  mov     [rcx+8], r14d
0x18000d3c2  mov     [rcx+10h], r14
0x18000d3c6  mov     [rcx+18h], r14
0x18000d3ca  mov     [rcx+20h], r14
0x18000d3ce  mov     [rcx+28h], r14
0x18000d3d2  xor     r8d, r8d
0x18000d3d5  xor     edx, edx
0x18000d3d7  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAUDocInfo@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<DocInfo *>>::_Buynode0(std::_List_node<DocInfo *,void *> *,std::_List_node<DocInfo *,void *> *)
0x18000d3dc  mov     [rdi+20h], rax
0x18000d3e0  mov     [rdi+30h], r14
0x18000d3e4  mov     [rdi+38h], r14
0x18000d3e8  lea     rbx, [rdi+40h]
0x18000d3ec  mov     [rbx], r14
0x18000d3ef  cmp     cs:?m_pTheStore@@3PEAVCAccStore@@EA, r14; CAccStore * m_pTheStore
0x18000d3f6  jz      short loc_18000D420
0x18000d3f8  lea     rax, aMPthestoreNull; "m_pTheStore == NULL"
0x18000d3ff  mov     [rsp+0A0h+var_70], rax; __int64
0x18000d404  mov     [rsp+0A0h+var_78], r14d; int
0x18000d409  xor     r9d, r9d
0x18000d40c  lea     edx, [r14+68h]; Value
0x18000d410  lea     r8d, [r14+8]
0x18000d414  lea     rcx, aWindowsOleaccM_1; "windows\\oleacc\\msaatext\\msaastore.cp"...
0x18000d41b  call    InternalTrace
0x18000d420  mov     cs:?m_pTheStore@@3PEAVCAccStore@@EA, rdi; CAccStore * m_pTheStore
0x18000d427  mov     [rsp+0A0h+ppv], rbx; ppv
0x18000d42c  lea     r9, IID_ITfMSAAControl; riid
0x18000d433  xor     edx, edx; pUnkOuter
0x18000d435  lea     r8d, [rdx+1]; dwClsContext
0x18000d439  lea     rcx, CLSID_MSAAControl; rclsid
0x18000d440  call    cs:__imp_CoCreateInstance
0x18000d446  mov     esi, eax
0x18000d448  test    eax, eax
0x18000d44a  jz      short loc_18000D495
0x18000d44c  mov     [rbp+57h+var_30], 7
0x18000d454  mov     [rbp+57h+var_38], r14
0x18000d458  mov     word ptr [rbp+57h+Src], r14w
0x18000d45d  mov     [rbp+57h+var_28], 0FFFFFFFFh
0x18000d464  mov     r8d, 31h ; '1'
0x18000d46a  lea     rdx, aCocreateinstan; "CoCreateInstance failed for CLSID_MSAAC"...
0x18000d471  lea     rcx, [rbp+57h+Src]; Src
0x18000d475  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000d47a  mov     [rbp+57h+var_60], rsi
0x18000d47e  mov     [rbp+57h+var_58], 0FFFFFFFFh
0x18000d485  lea     rdx, [rbp+57h+var_60]
0x18000d489  lea     rcx, [rbp+57h+Src]; Src
0x18000d48d  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z; operator<<(TSTR &,WriteHex const &)
0x18000d492  nop
0x18000d493  jmp     short loc_18000D4F1
0x18000d495  mov     rcx, [rbx]
0x18000d498  mov     rax, [rcx]
0x18000d49b  mov     rax, [rax+18h]
0x18000d49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4a4  mov     ebx, eax
0x18000d4a6  test    eax, eax
0x18000d4a8  jz      short loc_18000D502
0x18000d4aa  mov     [rbp+57h+var_30], 7
0x18000d4b2  mov     [rbp+57h+var_38], r14
0x18000d4b6  mov     word ptr [rbp+57h+Src], r14w
0x18000d4bb  mov     [rbp+57h+var_28], 0FFFFFFFFh
0x18000d4c2  mov     r8d, 1Bh
0x18000d4c8  lea     rdx, aSystemenablems; "SystemEnableMSAA failed hr="
0x18000d4cf  lea     rcx, [rbp+57h+Src]; Src
0x18000d4d3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000d4d8  mov     [rbp+57h+var_60], rbx
0x18000d4dc  mov     [rbp+57h+var_58], 0FFFFFFFFh
0x18000d4e3  lea     rdx, [rbp+57h+var_60]
0x18000d4e7  lea     rcx, [rbp+57h+Src]; Src
0x18000d4eb  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z; operator<<(TSTR &,WriteHex const &)
0x18000d4f0  nop
0x18000d4f1  cmp     [rbp+57h+var_30], 8
0x18000d4f6  jb      short loc_18000D502
0x18000d4f8  mov     rcx, [rbp+57h+Src]
0x18000d4fc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d502  lea     r9, aMsaaStoreEvent; "MSAA_STORE_EVENT"
0x18000d509  xor     edx, edx; bManualReset
0x18000d50b  xor     ecx, ecx; lpEventAttributes
0x18000d50d  lea     r8d, [rdx+1]; bInitialState
0x18000d511  call    cs:__imp_CreateEventW
0x18000d517  mov     [rdi+30h], rax
0x18000d51b  mov     rax, rdi
0x18000d51e  mov     rcx, [rbp+57h+var_20]
0x18000d522  xor     rcx, rsp; StackCookie
0x18000d525  call    __security_check_cookie
0x18000d52a  lea     r11, [rsp+0A0h+var_10]
0x18000d532  mov     rbx, [r11+28h]
0x18000d536  mov     rsi, [r11+30h]
0x18000d53a  mov     rsp, r11
0x18000d53d  pop     r14
0x18000d53f  pop     rdi
0x18000d540  pop     rbp
0x18000d541  retn
```
