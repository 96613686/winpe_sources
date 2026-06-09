# ColorDataController::RunRestricted(void)

- ea: `0x1800125ec`
- end: `0x1800126b7`
- name: `?RunRestricted@ColorDataController@@QEAAJXZ`
- size: `203`
- prototype: `HRESULT __fastcall(ColorDataController *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f654`
- `0x18000fc80`
- `0x180010ddc`

## callees

- `0x1800125ec`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180012640`
- `ole32!CoCreateInstance` at `0x180012640`

## pseudocode

```c
HRESULT __fastcall ColorDataController::RunRestricted(ColorDataController *this)
{
  bool v1; // zf
  HRESULT result; // eax
  int v4; // esi
  __int64 v5; // rcx
  int v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 2) == 0;
  ppv = 0;
  v6 = 0;
  if ( !v1 && !*((_DWORD *)this + 2) )
    return 0;
  result = CoCreateInstance(&CLSID_ColorDataProxy, 0, 1u, &IID_IColorDataProxy, &ppv);
  if ( result >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 24LL))(ppv, &v6);
    if ( v4 >= 0 )
    {
      v5 = *((_QWORD *)this + 2);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *((_QWORD *)this + 2) = ppv;
      *((_DWORD *)this + 6) = v6;
      *((_DWORD *)this + 2) = 0;
    }
    else
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800125ec  mov     rax, rsp
0x1800125ef  mov     [rax+18h], rbx
0x1800125f3  mov     [rax+20h], rsi
0x1800125f7  push    rdi
0x1800125f8  sub     rsp, 30h
0x1800125fc  cmp     qword ptr [rcx+10h], 0
0x180012601  mov     rbx, rcx
0x180012604  mov     qword ptr [rax+10h], 0
0x18001260c  mov     dword ptr [rax+8], 0
0x180012613  jz      short loc_180012622
0x180012615  cmp     dword ptr [rcx+8], 0
0x180012619  jnz     short loc_180012622
0x18001261b  xor     eax, eax
0x18001261d  jmp     loc_1800126A7
0x180012622  xor     edx, edx; pUnkOuter
0x180012624  lea     rax, [rsp+38h+arg_8]
0x180012629  lea     r9, IID_IColorDataProxy; riid
0x180012630  mov     [rsp+38h+ppv], rax; ppv
0x180012635  lea     rcx, CLSID_ColorDataProxy; rclsid
0x18001263c  lea     r8d, [rdx+1]; dwClsContext
0x180012640  call    cs:__imp_CoCreateInstance
0x180012646  test    eax, eax
0x180012648  js      short loc_1800126A7
0x18001264a  mov     rcx, [rsp+38h+arg_8]
0x18001264f  lea     rdx, [rsp+38h+arg_0]
0x180012654  mov     rax, [rcx]
0x180012657  mov     rax, [rax+18h]
0x18001265b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012660  mov     esi, eax
0x180012662  test    eax, eax
0x180012664  jns     short loc_180012679
0x180012666  mov     rcx, [rsp+38h+arg_8]
0x18001266b  mov     rdx, [rcx]
0x18001266e  mov     rax, [rdx+10h]
0x180012672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012677  jmp     short loc_1800126A5
0x180012679  mov     rcx, [rbx+10h]
0x18001267d  test    rcx, rcx
0x180012680  jz      short loc_18001268E
0x180012682  mov     rax, [rcx]
0x180012685  mov     rax, [rax+10h]
0x180012689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001268e  mov     rax, [rsp+38h+arg_8]
0x180012693  mov     [rbx+10h], rax
0x180012697  mov     eax, [rsp+38h+arg_0]
0x18001269b  mov     [rbx+18h], eax
0x18001269e  mov     dword ptr [rbx+8], 0
0x1800126a5  mov     eax, esi
0x1800126a7  mov     rbx, [rsp+38h+arg_10]
0x1800126ac  mov     rsi, [rsp+38h+arg_18]
0x1800126b1  add     rsp, 30h
0x1800126b5  pop     rdi
0x1800126b6  retn
```
