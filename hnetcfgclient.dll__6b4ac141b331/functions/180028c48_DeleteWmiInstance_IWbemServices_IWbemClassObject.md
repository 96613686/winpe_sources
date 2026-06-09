# DeleteWmiInstance(IWbemServices *,IWbemClassObject *)

- ea: `0x180028c48`
- end: `0x180028cb4`
- name: `?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemClassObject *)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ebb0`
- `0x180014bc0`
- `0x180019b30`
- `0x18001ee3c`
- `0x18001f590`
- `0x1800236c0`
- `0x180024790`
- `0x18002886c`
- `0x18002ae64`

## callees

- `0x180028c48`
- `0x180029a74`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180028ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x180028ca1`

## pseudocode

```c
__int64 __fastcall DeleteWmiInstance(struct IWbemServices *a1, struct IWbemClassObject *a2)
{
  unsigned int WmiPathFromObject; // ebx
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF

  bstrString = 0;
  WmiPathFromObject = GetWmiPathFromObject(a2, &bstrString);
  if ( !WmiPathFromObject )
  {
    WmiPathFromObject = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, _QWORD, _QWORD))a1->lpVtbl->DeleteInstance)(
                          a1,
                          bstrString,
                          0,
                          0,
                          0);
    SysFreeString(bstrString);
  }
  return WmiPathFromObject;
}

```

## disassembly

```asm
0x180028c48  mov     [rsp+arg_0], rbx
0x180028c4d  push    rdi
0x180028c4e  sub     rsp, 30h
0x180028c52  mov     rax, rdx
0x180028c55  mov     [rsp+38h+bstrString], 0
0x180028c5e  mov     rdi, rcx
0x180028c61  lea     rdx, [rsp+38h+bstrString]; unsigned __int16 **
0x180028c66  mov     rcx, rax; struct IWbemClassObject *
0x180028c69  call    ?GetWmiPathFromObject@@YAJPEAUIWbemClassObject@@PEAPEAG@Z; GetWmiPathFromObject(IWbemClassObject *,ushort * *)
0x180028c6e  mov     ebx, eax
0x180028c70  test    eax, eax
0x180028c72  jnz     short loc_180028CA7
0x180028c74  mov     rax, [rdi]
0x180028c77  xor     r9d, r9d
0x180028c7a  mov     rdx, [rsp+38h+bstrString]
0x180028c7f  xor     r8d, r8d
0x180028c82  mov     rcx, rdi
0x180028c85  mov     [rsp+38h+var_18], 0
0x180028c8e  mov     rax, [rax+80h]
0x180028c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c9a  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180028c9f  mov     ebx, eax
0x180028ca1  call    cs:__imp_SysFreeString
0x180028ca7  mov     eax, ebx
0x180028ca9  mov     rbx, [rsp+38h+arg_0]
0x180028cae  add     rsp, 30h
0x180028cb2  pop     rdi
0x180028cb3  retn
```
