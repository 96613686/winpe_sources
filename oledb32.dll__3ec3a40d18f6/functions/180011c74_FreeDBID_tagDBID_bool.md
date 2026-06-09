# FreeDBID(tagDBID *,bool)

- ea: `0x180011c74`
- end: `0x180011d15`
- name: `?FreeDBID@@YAXPEAUtagDBID@@_N@Z`
- size: `161`
- prototype: `void __fastcall(struct tagDBID *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180011bf0`
- `0x180013394`
- `0x180077200`

## callees

- `0x180011c74`
- `0x18003c2e8`

## import_xrefs

- `MSDART!mpFree` at `0x180011cc9`
- `MSDART!mpFree` at `0x180011cd1`
- `MSDART!mpFree` at `0x180011cc9`
- `MSDART!mpFree` at `0x180011cd1`
- `ole32!CoTaskMemFree` at `0x180011ca9`
- `ole32!CoTaskMemFree` at `0x180011cc1`
- `ole32!CoTaskMemFree` at `0x180011ca9`
- `ole32!CoTaskMemFree` at `0x180011cc1`

## pseudocode

```c
void __fastcall FreeDBID(struct tagDBID *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // di
  GUID *pguid; // rcx
  LPOLESTR pwszName; // rcx

  v4 = a2;
  pguid = a1->uGuid.pguid;
  if ( pguid && a1->eKind - 3 <= 1 )
  {
    if ( (_BYTE)a2 )
      CoTaskMemFree(pguid);
    else
      mpFree(pguid, a2, a3, a4);
  }
  pwszName = a1->uName.pwszName;
  if ( pwszName && (a1->eKind & 0xFFFFFFFC) == 0 && a1->eKind != 1 )
  {
    if ( v4 )
      CoTaskMemFree(pwszName);
    else
      mpFree(pwszName, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180011c74  mov     [rsp+arg_0], rbx
0x180011c79  push    rdi
0x180011c7a  sub     rsp, 20h
0x180011c7e  mov     dil, dl
0x180011c81  mov     rbx, rcx
0x180011c84  mov     rcx, [rcx]; pv
0x180011c87  test    rcx, rcx
0x180011c8a  jnz     short loc_180011CB1
0x180011c8c  mov     rcx, [rbx+18h]; pv
0x180011c90  test    rcx, rcx
0x180011c93  jz      short loc_180011CD7
0x180011c95  test    dword ptr [rbx+10h], 0FFFFFFFCh
0x180011c9c  jnz     short loc_180011CD7
0x180011c9e  cmp     dword ptr [rbx+10h], 1
0x180011ca2  jz      short loc_180011CD7
0x180011ca4  test    dil, dil
0x180011ca7  jz      short loc_180011CD1
0x180011ca9  call    cs:__imp_CoTaskMemFree
0x180011caf  jmp     short loc_180011CD7
0x180011cb1  mov     eax, [rbx+10h]
0x180011cb4  sub     eax, 3
0x180011cb7  cmp     eax, 1
0x180011cba  ja      short loc_180011C8C
0x180011cbc  test    dil, dil
0x180011cbf  jz      short loc_180011CC9
0x180011cc1  call    cs:__imp_CoTaskMemFree
0x180011cc7  jmp     short loc_180011C8C
0x180011cc9  call    cs:__imp_mpFree
0x180011ccf  jmp     short loc_180011C8C
0x180011cd1  call    cs:__imp_mpFree
0x180011cd7  jmp     short loc_180011D0A
0x180011cd9  test    byte ptr cs:_bidGblFlags, 2
0x180011ce0  jz      short loc_180011D0A
0x180011ce2  mov     rax, cs:off_1800C8D88; "<FreeDBID|CATCH|ALL> "
0x180011ce9  test    rax, rax
0x180011cec  jz      short loc_180011D0A
0x180011cee  xor     r9d, r9d
0x180011cf1  mov     r8, cs:off_1800C8D88; "<FreeDBID|CATCH|ALL> "
0x180011cf8  mov     edx, 208C00h
0x180011cfd  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180011d04  call    _bidTraceA
0x180011d09  nop
0x180011d0a  mov     rbx, [rsp+28h+arg_0]
0x180011d0f  add     rsp, 20h
0x180011d13  pop     rdi
0x180011d14  retn
```
