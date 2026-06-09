# CLanAdvancedPage::CLanAdvancedPage(IUnknown *,INetConnection *,int,int,int,IHNetConnection * * const,ulong,long,IHNetConnection *,IHNetCfgMgr *,IHNetIcsSettings *)

- ea: `0x18002b90c`
- end: `0x18002b9f8`
- name: `??0CLanAdvancedPage@@QEAA@PEAUIUnknown@@PEAUINetConnection@@HHHQEAPEAUIHNetConnection@@KJPEAU3@PEAUIHNetCfgMgr@@PEAUIHNetIcsSettings@@@Z`
- size: `236`
- prototype: `CLanAdvancedPage *__fastcall(CLanAdvancedPage *this, struct IUnknown *, struct INetConnection *, int, unsigned int, int, struct IHNetConnection **const pv, unsigned int, int, struct IUnknown *, struct IUnknown *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002c594`

## callees

- `0x18000a904`
- `0x18002b90c`
- `0x180065010`

## import_xrefs

- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x18002b9e3`
- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x18002b9e3`
- `ole32!CoTaskMemFree` at `0x18002b9dd`
- `ole32!CoTaskMemFree` at `0x18002b9dd`

## pseudocode

```c
CLanAdvancedPage *__fastcall CLanAdvancedPage::CLanAdvancedPage(
        CLanAdvancedPage *this,
        struct IUnknown *a2,
        struct INetConnection *a3,
        int a4,
        unsigned int a5,
        int a6,
        struct IHNetConnection **const pv,
        unsigned int a8,
        int a9,
        struct IUnknown *a10,
        struct IUnknown *a11,
        struct IUnknown *a12)
{
  int v13; // ecx
  BOOL v14; // eax
  struct IUnknown *v15; // rcx
  struct IUnknown *v16; // rcx
  struct IUnknown *v17; // rbx
  struct IHNetConnection **v18; // rcx

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CLanAdvancedPage::`vftable';
  *((_QWORD *)this + 2) = a3;
  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 8) = a4;
  *(_QWORD *)((char *)this + 36) = a5;
  *((_QWORD *)this + 6) = 0;
  v13 = a9;
  v14 = a4 && a9 == -1;
  *((_DWORD *)this + 14) = v14;
  *((_QWORD *)this + 8) = pv;
  *((_DWORD *)this + 19) = a8;
  *((_DWORD *)this + 18) = v13;
  v15 = a11;
  *((_QWORD *)this + 10) = a11;
  AddRefObj(v15);
  v16 = a12;
  *((_QWORD *)this + 11) = a12;
  AddRefObj(v16);
  v17 = a10;
  *((_QWORD *)this + 12) = a10;
  AddRefObj(v17);
  pv = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, struct IHNetConnection **const *))v17->lpVtbl[2].AddRef)(v17, &pv) >= 0 )
  {
    v18 = pv;
    *((_DWORD *)this + 11) = *((unsigned __int8 *)pv + 4);
    CoTaskMemFree(v18);
  }
  LinkWindow_RegisterClass();
  return this;
}

```

## disassembly

```asm
0x18002b90c  mov     [rsp+arg_8], rbx
0x18002b911  mov     [rsp+arg_0], rcx
0x18002b916  push    rdi
0x18002b917  sub     rsp, 20h
0x18002b91b  mov     rdi, rcx
0x18002b91e  mov     qword ptr [rcx+8], 0
0x18002b926  lea     rax, ??_7CLanAdvancedPage@@6B@; const CLanAdvancedPage::`vftable'
0x18002b92d  mov     [rcx], rax
0x18002b930  mov     [rcx+10h], r8
0x18002b934  mov     [rcx+18h], rdx
0x18002b938  mov     [rcx+20h], r9d
0x18002b93c  mov     eax, [rsp+28h+arg_20]
0x18002b940  mov     [rcx+24h], eax
0x18002b943  mov     dword ptr [rcx+28h], 0
0x18002b94a  mov     qword ptr [rcx+30h], 0
0x18002b952  mov     ecx, [rsp+28h+arg_40]
0x18002b956  test    r9d, r9d
0x18002b959  jz      short loc_18002B965
0x18002b95b  cmp     ecx, 0FFFFFFFFh
0x18002b95e  jnz     short loc_18002B965
0x18002b960  lea     eax, [rcx+2]
0x18002b963  jmp     short loc_18002B967
0x18002b965  xor     eax, eax
0x18002b967  mov     [rdi+38h], eax
0x18002b96a  mov     rax, [rsp+28h+pv]
0x18002b96f  mov     [rdi+40h], rax
0x18002b973  mov     eax, [rsp+28h+arg_38]
0x18002b977  mov     [rdi+4Ch], eax
0x18002b97a  mov     [rdi+48h], ecx
0x18002b97d  mov     rcx, [rsp+28h+arg_50]; struct IUnknown *
0x18002b985  mov     [rdi+50h], rcx
0x18002b989  call    ?AddRefObj@@YAKPEAUIUnknown@@@Z; AddRefObj(IUnknown *)
0x18002b98e  mov     rcx, [rsp+28h+arg_58]; struct IUnknown *
0x18002b996  mov     [rdi+58h], rcx
0x18002b99a  call    ?AddRefObj@@YAKPEAUIUnknown@@@Z; AddRefObj(IUnknown *)
0x18002b99f  mov     rbx, [rsp+28h+arg_48]
0x18002b9a4  mov     [rdi+60h], rbx
0x18002b9a8  mov     rcx, rbx; struct IUnknown *
0x18002b9ab  call    ?AddRefObj@@YAKPEAUIUnknown@@@Z; AddRefObj(IUnknown *)
0x18002b9b0  mov     [rsp+28h+pv], 0
0x18002b9b9  mov     rax, [rbx]
0x18002b9bc  lea     rdx, [rsp+28h+pv]
0x18002b9c1  mov     rcx, rbx
0x18002b9c4  mov     rax, [rax+38h]
0x18002b9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9cd  test    eax, eax
0x18002b9cf  js      short loc_18002B9E3
0x18002b9d1  mov     rcx, [rsp+28h+pv]; pv
0x18002b9d6  movzx   eax, byte ptr [rcx+4]
0x18002b9da  mov     [rdi+2Ch], eax
0x18002b9dd  call    cs:__imp_CoTaskMemFree
0x18002b9e3  call    cs:__imp_LinkWindow_RegisterClass
0x18002b9e9  nop
0x18002b9ea  mov     rax, rdi
0x18002b9ed  mov     rbx, [rsp+28h+arg_8]
0x18002b9f2  add     rsp, 20h
0x18002b9f6  pop     rdi
0x18002b9f7  retn
```
