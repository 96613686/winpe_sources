# CSharePageOverwrite::_SetItemList(HWND__ *)

- ea: `0x18006939c`
- end: `0x18006950f`
- name: `?_SetItemList@CSharePageOverwrite@@AEAAXPEAUHWND__@@@Z`
- size: `371`
- prototype: `void(CSharePageOverwrite *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069110`

## callees

- `0x18000f720`
- `0x18001c4a8`
- `0x18001d1dc`
- `0x18001d9a0`
- `0x1800259bc`
- `0x1800575e8`
- `0x18006467c`
- `0x180065b00`
- `0x180066504`
- `0x180068328`
- `0x18006939c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800694e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800694e6`
- `USER32!ShowWindow` at `0x1800694c3`
- `USER32!ShowWindow` at `0x1800694c3`
- `USER32!GetDlgItem` at `0x1800694b5`
- `USER32!GetDlgItem` at `0x1800694b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSharePageOverwrite::_SetItemList(CSharePageOverwrite *this, HWND a2)
{
  _DWORD *v4; // rbx
  void *v5; // rcx
  int v6; // eax
  struct CResultItem **v7; // rsi
  int v8; // edi
  const WCHAR *Ptr; // rax
  unsigned int v10; // edx
  const struct _GUID *v11; // r8
  int v12; // ebp
  CResultItem *v13; // rax
  unsigned int v14; // edx
  HWND DlgItem; // rax
  __int64 i; // rdi
  CResultItem *v17; // rcx
  struct IShellItem *v18; // [rsp+50h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  v4 = *(_DWORD **)(*((_QWORD *)this + 2) + 80LL);
  if ( v4 )
    LODWORD(v4) = *v4;
  pv = 0;
  v18 = 0;
  if ( (int)ULongLongMult((int)v4, 8u, (unsigned __int64 *)&v18) >= 0 )
  {
    v6 = CTCoAllocPolicy::Alloc(v5, 1u, (unsigned __int64)v18, &pv);
    v7 = (struct CResultItem **)pv;
    if ( v6 >= 0 )
    {
      v8 = 0;
      while ( v8 < (int)v4 )
      {
        v18 = 0;
        Ptr = (const WCHAR *)DPA_GetPtr(*(HDPA *)(*((_QWORD *)this + 2) + 80LL), v8);
        v12 = SHSimpleItemFromAttributes(Ptr, v10, v11, (void **)&v18);
        if ( v12 >= 0 )
        {
          v13 = (CResultItem *)operator new(0x630u, (const struct std::nothrow_t *)std::nothrow);
          pv = v13;
          if ( v13 )
            v13 = CResultItem::CResultItem(v13, v18, 0, 0);
          if ( v13 )
          {
            v12 = 0;
            v7[v8] = v13;
          }
          else
          {
            v12 = -2147024882;
          }
        }
        ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v18);
        ++v8;
        if ( v12 < 0 )
          goto LABEL_17;
      }
      if ( (int)CResultsList::SetItems((HWND *)this + 6, v7, (unsigned int)v4) >= 0 )
      {
        DlgItem = GetDlgItem(a2, 4107);
        ShowWindow(DlgItem, 5);
      }
LABEL_17:
      for ( i = 0; (int)i < (int)v4; i = (unsigned int)(i + 1) )
      {
        v17 = v7[i];
        if ( v17 )
          CResultItem::`scalar deleting destructor'(v17, v14);
      }
      CoTaskMemFree(v7);
    }
  }
  GetUserAttention(a2, 1);
}

```

## disassembly

```asm
0x18006939c  mov     [rsp+arg_8], rbx
0x1800693a1  mov     [rsp+arg_18], rbp
0x1800693a6  push    rsi
0x1800693a7  push    rdi
0x1800693a8  push    r12
0x1800693aa  push    r14
0x1800693ac  push    r15
0x1800693ae  sub     rsp, 20h
0x1800693b2  mov     r15, rdx
0x1800693b5  mov     r14, rcx
0x1800693b8  mov     rax, [rcx+10h]
0x1800693bc  mov     rbx, [rax+50h]
0x1800693c0  test    rbx, rbx
0x1800693c3  jz      short loc_1800693C7
0x1800693c5  mov     ebx, [rbx]
0x1800693c7  xor     esi, esi
0x1800693c9  mov     [rsp+48h+pv], rsi
0x1800693ce  mov     [rsp+48h+arg_0], rsi
0x1800693d3  movsxd  rcx, ebx; unsigned __int64
0x1800693d6  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x1800693db  lea     edx, [rsi+8]; unsigned __int64
0x1800693de  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800693e3  test    eax, eax
0x1800693e5  js      loc_1800694EC
0x1800693eb  lea     r9, [rsp+48h+pv]; void **
0x1800693f0  mov     r8, [rsp+48h+arg_0]; unsigned __int64
0x1800693f5  lea     edx, [rsi+1]; unsigned int
0x1800693f8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800693fd  mov     rsi, [rsp+48h+pv]
0x180069402  test    eax, eax
0x180069404  js      loc_1800694EC
0x18006940a  xor     edi, edi
0x18006940c  cmp     edi, ebx
0x18006940e  jge     loc_18006949A
0x180069414  mov     [rsp+48h+arg_0], 0
0x18006941d  movsxd  r12, edi
0x180069420  mov     rcx, [r14+10h]
0x180069424  mov     rdx, r12; i
0x180069427  mov     rcx, [rcx+50h]; hdpa
0x18006942b  call    DPA_GetPtr
0x180069430  lea     r9, [rsp+48h+arg_0]; void **
0x180069435  mov     rcx, rax; pszPath
0x180069438  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x18006943d  mov     ebp, eax
0x18006943f  test    eax, eax
0x180069441  js      short loc_180069484
0x180069443  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006944a  mov     ecx, 630h; unsigned __int64
0x18006944f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180069454  mov     [rsp+48h+pv], rax
0x180069459  test    rax, rax
0x18006945c  jz      short loc_180069472
0x18006945e  xor     r9d, r9d; struct IShellItem *
0x180069461  xor     r8d, r8d; struct IShellItem *
0x180069464  mov     rdx, [rsp+48h+arg_0]; struct IShellItem *
0x180069469  mov     rcx, rax; this
0x18006946c  call    ??0CResultItem@@QEAA@PEAUIShellItem@@00@Z; CResultItem::CResultItem(IShellItem *,IShellItem *,IShellItem *)
0x180069471  nop
0x180069472  test    rax, rax
0x180069475  jz      short loc_18006947F
0x180069477  xor     ebp, ebp
0x180069479  mov     [rsi+r12*8], rax
0x18006947d  jmp     short loc_180069484
0x18006947f  mov     ebp, 8007000Eh
0x180069484  lea     rcx, [rsp+48h+arg_0]
0x180069489  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18006948e  inc     edi
0x180069490  test    ebp, ebp
0x180069492  jns     loc_18006940C
0x180069498  jmp     short loc_1800694C9
0x18006949a  lea     rcx, [r14+30h]; this
0x18006949e  mov     r8d, ebx; unsigned int
0x1800694a1  mov     rdx, rsi; struct CResultItem **
0x1800694a4  call    ?SetItems@CResultsList@@QEAAJPEAPEAVCResultItem@@K@Z; CResultsList::SetItems(CResultItem * *,ulong)
0x1800694a9  test    eax, eax
0x1800694ab  js      short loc_1800694C9
0x1800694ad  mov     edx, 100Bh; nIDDlgItem
0x1800694b2  mov     rcx, r15; hDlg
0x1800694b5  call    cs:__imp_GetDlgItem
0x1800694bb  mov     rcx, rax; hWnd
0x1800694be  mov     edx, 5; nCmdShow
0x1800694c3  call    cs:__imp_ShowWindow
0x1800694c9  xor     edi, edi
0x1800694cb  test    ebx, ebx
0x1800694cd  jle     short loc_1800694E3
0x1800694cf  mov     rcx, [rsi+rdi*8]; this
0x1800694d3  test    rcx, rcx
0x1800694d6  jz      short loc_1800694DD
0x1800694d8  call    ??_GCResultItem@@QEAAPEAXI@Z; CResultItem::`scalar deleting destructor'(uint)
0x1800694dd  inc     edi
0x1800694df  cmp     edi, ebx
0x1800694e1  jl      short loc_1800694CF
0x1800694e3  mov     rcx, rsi; pv
0x1800694e6  call    cs:__imp_CoTaskMemFree
0x1800694ec  mov     edx, 1; int
0x1800694f1  mov     rcx, r15; HWND
0x1800694f4  mov     rbx, [rsp+48h+arg_8]
0x1800694f9  mov     rbp, [rsp+48h+arg_18]
0x1800694fe  add     rsp, 20h
0x180069502  pop     r15
0x180069504  pop     r14
0x180069506  pop     r12
0x180069508  pop     rdi
0x180069509  pop     rsi
0x18006950a  jmp     ?GetUserAttention@@YAXPEAUHWND__@@H@Z; GetUserAttention(HWND__ *,int)
```
