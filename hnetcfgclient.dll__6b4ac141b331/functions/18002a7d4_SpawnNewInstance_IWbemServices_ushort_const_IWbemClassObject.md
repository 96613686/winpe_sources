# SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)

- ea: `0x18002a7d4`
- end: `0x18002a88f`
- name: `?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z`
- size: `187`
- prototype: `int(struct IWbemServices *, const unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000ddf0`
- `0x180010350`
- `0x180018560`
- `0x180019318`
- `0x18001f590`
- `0x180020ef0`
- `0x18002886c`
- `0x1800294f8`
- `0x18002a4f0`

## callees

- `0x18002a7d4`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a7fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a7fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a843`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a843`

## pseudocode

```c
__int64 __fastcall SpawnNewInstance(struct IWbemServices *a1, const unsigned __int16 *a2, struct IWbemClassObject **a3)
{
  OLECHAR *v5; // rdi
  struct IWbemServicesVtbl *lpVtbl; // rdx
  unsigned int v7; // ebx
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  *a3 = 0;
  v5 = SysAllocString(a2);
  if ( v5 )
  {
    lpVtbl = a1->lpVtbl;
    v9 = 0;
    v7 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))lpVtbl->GetObjectA)(
           a1,
           v5,
           0,
           0,
           &v9,
           0);
    SysFreeString(v5);
    if ( !v7 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v9 + 120LL))(v9, 0, a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18002a7d4  mov     [rsp+arg_0], rbx
0x18002a7d9  mov     [rsp+arg_8], rsi
0x18002a7de  push    rdi
0x18002a7df  sub     rsp, 40h
0x18002a7e3  mov     rbx, rcx
0x18002a7e6  mov     [rsp+48h+arg_10], 0
0x18002a7ef  mov     rcx, rdx; psz
0x18002a7f2  mov     qword ptr [r8], 0
0x18002a7f9  mov     rsi, r8
0x18002a7fc  call    cs:__imp_SysAllocString
0x18002a802  mov     rdi, rax
0x18002a805  test    rax, rax
0x18002a808  jz      short loc_18002A878
0x18002a80a  mov     rdx, [rbx]
0x18002a80d  lea     rcx, [rsp+48h+arg_10]
0x18002a812  mov     [rsp+48h+var_20], 0
0x18002a81b  xor     r9d, r9d
0x18002a81e  mov     [rsp+48h+var_28], rcx
0x18002a823  xor     r8d, r8d
0x18002a826  mov     rcx, rbx
0x18002a829  mov     [rsp+48h+arg_10], 0
0x18002a832  mov     rax, [rdx+30h]
0x18002a836  mov     rdx, rdi
0x18002a839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a83e  mov     rcx, rdi; bstrString
0x18002a841  mov     ebx, eax
0x18002a843  call    cs:__imp_SysFreeString
0x18002a849  test    ebx, ebx
0x18002a84b  jnz     short loc_18002A87D
0x18002a84d  mov     rcx, [rsp+48h+arg_10]
0x18002a852  mov     r8, rsi
0x18002a855  xor     edx, edx
0x18002a857  mov     rax, [rcx]
0x18002a85a  mov     rax, [rax+78h]
0x18002a85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a863  mov     rcx, [rsp+48h+arg_10]
0x18002a868  mov     ebx, eax
0x18002a86a  mov     rdx, [rcx]
0x18002a86d  mov     rax, [rdx+10h]
0x18002a871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a876  jmp     short loc_18002A87D
0x18002a878  mov     ebx, 8007000Eh
0x18002a87d  mov     rsi, [rsp+48h+arg_8]
0x18002a882  mov     eax, ebx
0x18002a884  mov     rbx, [rsp+48h+arg_0]
0x18002a889  add     rsp, 40h
0x18002a88d  pop     rdi
0x18002a88e  retn
```
