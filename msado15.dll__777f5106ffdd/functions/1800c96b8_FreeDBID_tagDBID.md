# FreeDBID(tagDBID *)

- ea: `0x1800c96b8`
- end: `0x1800c96f9`
- name: `?FreeDBID@@YAXPEAUtagDBID@@@Z`
- size: `65`
- prototype: `void __fastcall(struct tagDBID *pv)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800a61b4`
- `0x1800b87e0`

## callees

- `0x1800c96b8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c96d7`
- `ole32!CoTaskMemFree` at `0x1800c96e6`
- `ole32!CoTaskMemFree` at `0x1800c96d7`
- `ole32!CoTaskMemFree` at `0x1800c96e6`

## pseudocode

```c
void __fastcall FreeDBID(struct tagDBID *pv)
{
  LPOLESTR pwszName; // rcx

  if ( pv )
  {
    if ( (pv->eKind & 0xFFFFFFFD) == 0 )
    {
      pwszName = pv->uName.pwszName;
      if ( pwszName )
        CoTaskMemFree(pwszName);
    }
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x1800c96b8  test    rcx, rcx
0x1800c96bb  jz      short locret_1800C96F7
0x1800c96bd  push    rbx
0x1800c96be  sub     rsp, 20h
0x1800c96c2  test    dword ptr [rcx+10h], 0FFFFFFFDh
0x1800c96c9  mov     rbx, rcx
0x1800c96cc  jnz     short loc_1800C96E3
0x1800c96ce  mov     rcx, [rcx+18h]; pv
0x1800c96d2  test    rcx, rcx
0x1800c96d5  jz      short loc_1800C96E3
0x1800c96d7  call    cs:__imp_CoTaskMemFree
0x1800c96de  nop     dword ptr [rax+rax+00h]
0x1800c96e3  mov     rcx, rbx; pv
0x1800c96e6  call    cs:__imp_CoTaskMemFree
0x1800c96ed  nop     dword ptr [rax+rax+00h]
0x1800c96f2  add     rsp, 20h
0x1800c96f6  pop     rbx
0x1800c96f7  retn
```
