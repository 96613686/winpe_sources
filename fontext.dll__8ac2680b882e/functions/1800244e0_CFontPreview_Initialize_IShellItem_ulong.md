# CFontPreview::Initialize(IShellItem *,ulong)

- ea: `0x1800244e0`
- end: `0x180024562`
- name: `?Initialize@CFontPreview@@UEAAJPEAUIShellItem@@K@Z`
- size: `130`
- prototype: `__int64 __fastcall(CFontPreview *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800244e0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024543`

## pseudocode

```c
__int64 __fastcall CFontPreview::Initialize(CFontPreview *this, struct IShellItem *a2, unsigned int a3)
{
  struct IShellItemVtbl *lpVtbl; // rax
  int v6; // ebx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    pv = 0;
    v6 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))lpVtbl->GetDisplayName)(a2, 2147844096LL, &pv);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(char *, LPVOID, _QWORD))(*((_QWORD *)this - 1) + 24LL))((char *)this - 8, pv, a3);
      CoTaskMemFree(pv);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800244e0  mov     r11, rsp
0x1800244e3  mov     [r11+8], rbx
0x1800244e7  mov     [r11+18h], rsi
0x1800244eb  push    rdi
0x1800244ec  sub     rsp, 20h
0x1800244f0  mov     edi, r8d
0x1800244f3  mov     r9, rdx
0x1800244f6  mov     rsi, rcx
0x1800244f9  test    rdx, rdx
0x1800244fc  jz      short loc_18002454B
0x1800244fe  mov     rax, [rdx]
0x180024501  lea     r8, [r11+10h]
0x180024505  mov     edx, 80058000h
0x18002450a  mov     qword ptr [r11+10h], 0
0x180024512  mov     rcx, r9
0x180024515  mov     rax, [rax+28h]
0x180024519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002451e  mov     ebx, eax
0x180024520  test    eax, eax
0x180024522  js      short loc_180024550
0x180024524  mov     rdx, [rsp+28h+pv]
0x180024529  lea     rcx, [rsi-8]
0x18002452d  mov     rax, [rcx]
0x180024530  mov     r8d, edi
0x180024533  mov     rax, [rax+18h]
0x180024537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002453c  mov     rcx, [rsp+28h+pv]; pv
0x180024541  mov     ebx, eax
0x180024543  call    cs:__imp_CoTaskMemFree
0x180024549  jmp     short loc_180024550
0x18002454b  mov     ebx, 80070057h
0x180024550  mov     rsi, [rsp+28h+arg_10]
0x180024555  mov     eax, ebx
0x180024557  mov     rbx, [rsp+28h+arg_0]
0x18002455c  add     rsp, 20h
0x180024560  pop     rdi
0x180024561  retn
```
