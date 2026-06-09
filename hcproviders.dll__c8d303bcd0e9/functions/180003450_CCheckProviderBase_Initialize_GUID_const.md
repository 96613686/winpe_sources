# CCheckProviderBase::_Initialize(_GUID const &)

- ea: `0x180003450`
- end: `0x180003507`
- name: `?_Initialize@CCheckProviderBase@@IEAAJAEBU_GUID@@@Z`
- size: `183`
- prototype: `int(CCheckProviderBase *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007f20`

## callees

- `0x180003450`
- `0x180003510`
- `0x180004fc8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003463`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003463`
- `COMCTL32!__imp_DPA_Create` at `0x1800034a0`
- `COMCTL32!__imp_DPA_Create` at `0x1800034a0`

## pseudocode

```c
HRESULT __fastcall CCheckProviderBase::_Initialize(LPOLESTR *this, const struct _GUID *a2)
{
  HRESULT result; // eax
  void *v4; // rax
  OLECHAR *v5; // rdi
  HDPA v6; // rax
  LPOLESTR v7; // rax

  result = StringFromCLSID(a2, this + 2);
  if ( result >= 0 )
  {
    v4 = operator new(0x18u);
    if ( v4 && (v5 = (OLECHAR *)CCheckCollection<CCheckBase>::CCheckCollection<CCheckBase>(v4)) != 0 )
    {
      v6 = DPA_Create(1);
      *((_QWORD *)v5 + 2) = v6;
      if ( v6 )
      {
        v7 = *this;
        this[3] = v5;
        return (*((__int64 (__fastcall **)(LPOLESTR *))v7 + 7))(this);
      }
      else
      {
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v5 + 16LL))(v5);
        return -2147024882;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003450  push    rbx
0x180003452  sub     rsp, 20h
0x180003456  mov     rax, rdx
0x180003459  mov     rbx, rcx
0x18000345c  lea     rdx, [rcx+10h]; lplpsz
0x180003460  mov     rcx, rax; rclsid
0x180003463  call    cs:__imp_StringFromCLSID
0x18000346a  nop     dword ptr [rax+rax+00h]
0x18000346f  test    eax, eax
0x180003471  js      loc_180003500
0x180003477  mov     ecx, 18h; Size
0x18000347c  mov     [rsp+28h+arg_0], rdi
0x180003481  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003486  test    rax, rax
0x180003489  jz      short loc_1800034F4
0x18000348b  mov     rcx, rax
0x18000348e  call    ??0?$CCheckCollection@VCCheckBase@@@@IEAA@XZ; CCheckCollection<CCheckBase>::CCheckCollection<CCheckBase>(void)
0x180003493  mov     rdi, rax
0x180003496  test    rax, rax
0x180003499  jz      short loc_1800034F4
0x18000349b  mov     ecx, 1; cItemGrow
0x1800034a0  call    cs:__imp_DPA_Create
0x1800034a7  nop     dword ptr [rax+rax+00h]
0x1800034ac  mov     [rdi+10h], rax
0x1800034b0  test    rax, rax
0x1800034b3  jnz     short loc_1800034D7
0x1800034b5  mov     rcx, [rdi]
0x1800034b8  mov     ebx, 8007000Eh
0x1800034bd  mov     rax, [rcx+10h]
0x1800034c1  mov     rcx, rdi
0x1800034c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c9  mov     rdi, [rsp+28h+arg_0]
0x1800034ce  mov     eax, ebx
0x1800034d0  add     rsp, 20h
0x1800034d4  pop     rbx
0x1800034d5  retn
0x1800034d7  mov     rax, [rbx]
0x1800034da  mov     rcx, rbx
0x1800034dd  mov     [rbx+18h], rdi
0x1800034e1  mov     rax, [rax+38h]
0x1800034e5  mov     rdi, [rsp+28h+arg_0]
0x1800034ea  add     rsp, 20h
0x1800034ee  pop     rbx
0x1800034ef  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f4  mov     rdi, [rsp+28h+arg_0]
0x1800034f9  mov     ebx, 8007000Eh
0x1800034fe  mov     eax, ebx
0x180003500  add     rsp, 20h
0x180003504  pop     rbx
0x180003505  retn
```
