# GetGuidFromBstr(wchar_t *,_GUID *)

- ea: `0x18001d3ac`
- end: `0x18001d408`
- name: `?GetGuidFromBstr@@YAJPEA_WPEAU_GUID@@@Z`
- size: `92`
- prototype: `int(wchar_t *, struct _GUID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005980`
- `0x1800196d0`
- `0x18001efb0`

## callees

- `0x18001d3ac`

## import_xrefs

- `ole32!CLSIDFromString` at `0x18001d3e0`
- `ole32!CLSIDFromString` at `0x18001d3e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d3c5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d3c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d3f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d3f5`

## pseudocode

```c
__int64 __fastcall GetGuidFromBstr(wchar_t *a1, struct _GUID *a2)
{
  const OLECHAR *v3; // rax
  OLECHAR *v4; // rdi
  HRESULT v6; // ebx

  if ( !a1 )
    a1 = (wchar_t *)&psz;
  v3 = SysAllocString(a1);
  v4 = (OLECHAR *)v3;
  if ( !v3 )
    return 2147942414LL;
  v6 = CLSIDFromString(v3, a2);
  if ( v6 < 0 )
    v6 = -1072824296;
  SysFreeString(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001d3ac  mov     [rsp+arg_0], rbx
0x18001d3b1  push    rdi
0x18001d3b2  sub     rsp, 20h
0x18001d3b6  mov     rbx, rdx
0x18001d3b9  test    rcx, rcx
0x18001d3bc  jnz     short loc_18001D3C5
0x18001d3be  lea     rcx, psz; psz
0x18001d3c5  call    cs:__imp_SysAllocString
0x18001d3cb  mov     rdi, rax
0x18001d3ce  test    rax, rax
0x18001d3d1  jnz     short loc_18001D3DA
0x18001d3d3  mov     eax, 8007000Eh
0x18001d3d8  jmp     short loc_18001D3FD
0x18001d3da  mov     rdx, rbx; pclsid
0x18001d3dd  mov     rcx, rdi; lpsz
0x18001d3e0  call    cs:__imp_CLSIDFromString
0x18001d3e6  mov     ebx, eax
0x18001d3e8  mov     rcx, rdi; bstrString
0x18001d3eb  test    ebx, ebx
0x18001d3ed  mov     eax, 0C00E0018h
0x18001d3f2  cmovs   ebx, eax
0x18001d3f5  call    cs:__imp_SysFreeString
0x18001d3fb  mov     eax, ebx
0x18001d3fd  mov     rbx, [rsp+28h+arg_0]
0x18001d402  add     rsp, 20h
0x18001d406  pop     rdi
0x18001d407  retn
```
