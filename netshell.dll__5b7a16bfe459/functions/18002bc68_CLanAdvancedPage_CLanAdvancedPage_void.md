# CLanAdvancedPage::~CLanAdvancedPage(void)

- ea: `0x18002bc68`
- end: `0x18002bcee`
- name: `??1CLanAdvancedPage@@UEAA@XZ`
- size: `134`
- prototype: `void __fastcall(CLanAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002be30`

## callees

- `0x180018d74`
- `0x18002bc68`
- `0x18003f9fc`

## import_xrefs

- `SHELL32!__imp_LinkWindow_UnregisterClass` at `0x18002bcd6`
- `SHELL32!__imp_LinkWindow_UnregisterClass` at `0x18002bcd6`
- `ole32!CoTaskMemFree` at `0x18002bca5`
- `ole32!CoTaskMemFree` at `0x18002bca5`

## pseudocode

```c
void __fastcall CLanAdvancedPage::~CLanAdvancedPage(CLanAdvancedPage *this)
{
  bool v1; // zf
  __int64 i; // rdi

  v1 = *((_QWORD *)this + 8) == 0;
  *(_QWORD *)this = &CLanAdvancedPage::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 19); i = (unsigned int)(i + 1) )
      ReleaseObj(*(struct IUnknown **)(*((_QWORD *)this + 8) + 8 * i));
    CoTaskMemFree(*((LPVOID *)this + 8));
  }
  ReleaseObj(*((struct IUnknown **)this + 10));
  ReleaseObj(*((struct IUnknown **)this + 11));
  ReleaseObj(*((struct IUnknown **)this + 12));
  ReleaseObj(*((struct IUnknown **)this + 6));
  LinkWindow_UnregisterClass(hInst);
  CPropSheetPage::~CPropSheetPage(this);
}

```

## disassembly

```asm
0x18002bc68  mov     [rsp+arg_0], rbx
0x18002bc6d  push    rdi
0x18002bc6e  sub     rsp, 20h
0x18002bc72  cmp     qword ptr [rcx+40h], 0
0x18002bc77  lea     rax, ??_7CLanAdvancedPage@@6B@; const CLanAdvancedPage::`vftable'
0x18002bc7e  mov     [rcx], rax
0x18002bc81  mov     rbx, rcx
0x18002bc84  jz      short loc_18002BCAB
0x18002bc86  xor     edi, edi
0x18002bc88  cmp     [rcx+4Ch], edi
0x18002bc8b  jbe     short loc_18002BCA1
0x18002bc8d  mov     rcx, [rbx+40h]
0x18002bc91  mov     rcx, [rcx+rdi*8]; struct IUnknown *
0x18002bc95  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002bc9a  inc     edi
0x18002bc9c  cmp     edi, [rbx+4Ch]
0x18002bc9f  jb      short loc_18002BC8D
0x18002bca1  mov     rcx, [rbx+40h]; pv
0x18002bca5  call    cs:__imp_CoTaskMemFree
0x18002bcab  mov     rcx, [rbx+50h]; struct IUnknown *
0x18002bcaf  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002bcb4  mov     rcx, [rbx+58h]; struct IUnknown *
0x18002bcb8  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002bcbd  mov     rcx, [rbx+60h]; struct IUnknown *
0x18002bcc1  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002bcc6  mov     rcx, [rbx+30h]; struct IUnknown *
0x18002bcca  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002bccf  mov     rcx, cs:hInst
0x18002bcd6  call    cs:__imp_LinkWindow_UnregisterClass
0x18002bcdc  mov     rcx, rbx; this
0x18002bcdf  mov     rbx, [rsp+28h+arg_0]
0x18002bce4  add     rsp, 20h
0x18002bce8  pop     rdi
0x18002bce9  jmp     ??1CPropSheetPage@@UEAA@XZ; CPropSheetPage::~CPropSheetPage(void)
```
