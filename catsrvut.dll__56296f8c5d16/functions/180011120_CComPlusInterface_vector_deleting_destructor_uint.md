# CComPlusInterface::`vector deleting destructor'(uint)

- ea: `0x180011120`
- end: `0x18001118d`
- name: `??_ECComPlusInterface@@UEAAPEAXI@Z`
- size: `109`
- prototype: `CComPlusInterface *__fastcall(CComPlusInterface *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f418`
- `0x180011120`
- `0x18002bd10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001115b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001115b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011173`

## pseudocode

```c
CComPlusInterface *__fastcall CComPlusInterface::`vector deleting destructor'(CComPlusInterface *this, char a2)
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
      (void (*)(void *))CComPlusComponent::~CComPlusComponent);
    if ( v3 )
      CoTaskMemFree(v4);
    return (CComPlusInterface *)v4;
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
0x180011120  mov     [rsp+arg_0], rbx
0x180011125  mov     [rsp+arg_8], rsi
0x18001112a  push    rdi
0x18001112b  sub     rsp, 20h
0x18001112f  mov     rbx, rcx
0x180011132  mov     esi, edx
0x180011134  and     esi, 1
0x180011137  test    dl, 2
0x18001113a  jz      short loc_180011167
0x18001113c  lea     rdi, [rcx-8]
0x180011140  lea     r9, ??1CComPlusComponent@@UEAA@XZ; void (*)(void *)
0x180011147  mov     r8, [rdi]; unsigned __int64
0x18001114a  mov     edx, 28h ; '('; unsigned __int64
0x18001114f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011154  test    esi, esi
0x180011156  jz      short loc_180011162
0x180011158  mov     rcx, rdi; pv
0x18001115b  call    cs:__imp_CoTaskMemFree
0x180011161  nop
0x180011162  mov     rax, rdi
0x180011165  jmp     short loc_18001117D
0x180011167  call    ??1CComPlusObject@@UEAA@XZ; CComPlusObject::~CComPlusObject(void)
0x18001116c  test    esi, esi
0x18001116e  jz      short loc_18001117A
0x180011170  mov     rcx, rbx; pv
0x180011173  call    cs:__imp_CoTaskMemFree
0x180011179  nop
0x18001117a  mov     rax, rbx
0x18001117d  mov     rbx, [rsp+28h+arg_0]
0x180011182  mov     rsi, [rsp+28h+arg_8]
0x180011187  add     rsp, 20h
0x18001118b  pop     rdi
0x18001118c  retn
```
