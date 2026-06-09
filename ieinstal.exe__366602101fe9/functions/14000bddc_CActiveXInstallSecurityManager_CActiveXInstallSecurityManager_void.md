# CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(void)

- ea: `0x14000bddc`
- end: `0x14000be20`
- name: `??1CActiveXInstallSecurityManager@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CActiveXInstallSecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000bfe0`

## callees

- `0x14000bddc`
- `0x140011010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000bdf8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000bdf8`

## pseudocode

```c
void __fastcall CActiveXInstallSecurityManager::~CActiveXInstallSecurityManager(CActiveXInstallSecurityManager *this)
{
  OLECHAR *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CActiveXInstallSecurityManager::`vftable';
  v2 = (OLECHAR *)*((_QWORD *)this + 2);
  if ( v2 )
    SysFreeString(v2);
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x14000bddc  push    rbx
0x14000bdde  sub     rsp, 20h
0x14000bde2  lea     rax, ??_7CActiveXInstallSecurityManager@@6B@; const CActiveXInstallSecurityManager::`vftable'
0x14000bde9  mov     rbx, rcx
0x14000bdec  mov     [rcx], rax
0x14000bdef  mov     rcx, [rcx+10h]; bstrString
0x14000bdf3  test    rcx, rcx
0x14000bdf6  jz      short loc_14000BE04
0x14000bdf8  call    cs:__imp_SysFreeString
0x14000bdff  nop     dword ptr [rax+rax+00h]
0x14000be04  mov     rcx, [rbx+18h]
0x14000be08  test    rcx, rcx
0x14000be0b  jz      short loc_14000BE19
0x14000be0d  mov     rax, [rcx]
0x14000be10  mov     rax, [rax+10h]
0x14000be14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be19  add     rsp, 20h
0x14000be1d  pop     rbx
0x14000be1e  retn
```
