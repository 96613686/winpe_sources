# CComPlusObject::`vector deleting destructor'(uint)

- ea: `0x180011220`
- end: `0x18001128d`
- name: `??_ECComPlusObject@@UEAAPEAXI@Z`
- size: `109`
- prototype: `CComPlusObject *__fastcall(CComPlusObject *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f418`
- `0x180011220`
- `0x18002bd10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001125b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001125b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011273`

## pseudocode

```c
CComPlusObject *__fastcall CComPlusObject::`vector deleting destructor'(CComPlusObject *this, char a2)
{
  int v3; // esi
  char *v4; // rdi

  v3 = a2 & 1;
  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    `eh vector destructor iterator'(
      this,
      0x28u,
      *((_QWORD *)this - 1),
      (void (*)(void *))CComPlusObject::~CComPlusObject);
    if ( v3 )
      CoTaskMemFree(v4);
    return (CComPlusObject *)v4;
  }
  else
  {
    CComPlusObject::~CComPlusObject(this);
    if ( v3 )
      CoTaskMemFree(this);
    return this;
  }
}

```

## disassembly

```asm
0x180011220  mov     [rsp+arg_0], rbx
0x180011225  mov     [rsp+arg_8], rsi
0x18001122a  push    rdi
0x18001122b  sub     rsp, 20h
0x18001122f  mov     rbx, rcx
0x180011232  mov     esi, edx
0x180011234  and     esi, 1
0x180011237  test    dl, 2
0x18001123a  jz      short loc_180011267
0x18001123c  lea     rdi, [rcx-8]
0x180011240  lea     r9, ??1CComPlusObject@@UEAA@XZ; void (*)(void *)
0x180011247  mov     r8, [rdi]; unsigned __int64
0x18001124a  mov     edx, 28h ; '('; unsigned __int64
0x18001124f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011254  test    esi, esi
0x180011256  jz      short loc_180011262
0x180011258  mov     rcx, rdi; pv
0x18001125b  call    cs:__imp_CoTaskMemFree
0x180011261  nop
0x180011262  mov     rax, rdi
0x180011265  jmp     short loc_18001127D
0x180011267  call    ??1CComPlusObject@@UEAA@XZ; CComPlusObject::~CComPlusObject(void)
0x18001126c  test    esi, esi
0x18001126e  jz      short loc_18001127A
0x180011270  mov     rcx, rbx; pv
0x180011273  call    cs:__imp_CoTaskMemFree
0x180011279  nop
0x18001127a  mov     rax, rbx
0x18001127d  mov     rbx, [rsp+28h+arg_0]
0x180011282  mov     rsi, [rsp+28h+arg_8]
0x180011287  add     rsp, 20h
0x18001128b  pop     rdi
0x18001128c  retn
```
