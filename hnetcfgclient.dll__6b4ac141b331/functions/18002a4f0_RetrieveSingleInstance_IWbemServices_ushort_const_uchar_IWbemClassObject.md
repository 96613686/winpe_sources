# RetrieveSingleInstance(IWbemServices *,ushort const *,uchar,IWbemClassObject * *)

- ea: `0x18002a4f0`
- end: `0x18002a615`
- name: `?RetrieveSingleInstance@@YAJPEAUIWbemServices@@PEBGEPEAPEAUIWbemClassObject@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(struct IWbemServices *, const unsigned __int16 *, unsigned __int8, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180014520`
- `0x180017bf0`

## callees

- `0x18002a4f0`
- `0x18002a7d4`
- `0x18002ae64`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a526`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a526`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a572`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a572`

## pseudocode

```c
__int64 __fastcall RetrieveSingleInstance(
        struct IWbemServices *a1,
        const unsigned __int16 *a2,
        char a3,
        struct IWbemClassObject **a4)
{
  OLECHAR *v7; // rsi
  unsigned int v8; // ebx
  int v9; // eax
  int v11; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+6Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  v11 = 0;
  v7 = SysAllocString(L"HNet_FirewallLoggingSettings");
  if ( v7 )
  {
    v8 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, __int64))a1->lpVtbl->CreateInstanceEnum)(
           a1,
           v7,
           48);
    SysFreeString(v7);
    if ( !v8 )
    {
      *a4 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, struct IWbemClassObject **, int *))(MEMORY[0] + 32LL))(
             0,
             0xFFFFFFFFLL,
             1,
             a4,
             &v11);
      v8 = v9;
      if ( v9 >= 0 && v11 == 1 )
      {
        v8 = 0;
        ValidateFinishedWCOEnum(a1, 0);
      }
      else if ( v9 == 1 )
      {
        if ( a3 )
          v8 = SpawnNewInstance(a1, L"HNet_FirewallLoggingSettings", a4);
        else
          v8 = -2147020584;
      }
      (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x18002a4f0  mov     rax, rsp
0x18002a4f3  mov     [rax+8], rbx
0x18002a4f7  mov     [rax+18h], rbp
0x18002a4fb  mov     [rax+10h], rdx
0x18002a4ff  push    rsi
0x18002a500  push    rdi
0x18002a501  push    r14
0x18002a503  sub     rsp, 40h
0x18002a507  mov     rdi, rcx
0x18002a50a  mov     qword ptr [rax-28h], 0
0x18002a512  lea     rcx, ?c_wszHnetFWLoggingSettings@@3QBGB; "HNet_FirewallLoggingSettings"
0x18002a519  mov     dword ptr [rax+10h], 0
0x18002a520  mov     r14, r9
0x18002a523  mov     bpl, r8b
0x18002a526  call    cs:__imp_SysAllocString
0x18002a52c  mov     rsi, rax
0x18002a52f  test    rax, rax
0x18002a532  jnz     short loc_18002A53E
0x18002a534  mov     ebx, 8007000Eh
0x18002a539  jmp     loc_18002A600
0x18002a53e  mov     rax, [rdi]
0x18002a541  lea     rcx, [rsp+58h+var_28]
0x18002a546  xor     r9d, r9d
0x18002a549  mov     [rsp+58h+var_38], rcx
0x18002a54e  mov     rdx, rsi
0x18002a551  mov     [rsp+58h+var_28], 0
0x18002a55a  mov     rcx, rdi
0x18002a55d  mov     rax, [rax+90h]
0x18002a564  lea     r8d, [r9+30h]
0x18002a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a56d  mov     rcx, rsi; bstrString
0x18002a570  mov     ebx, eax
0x18002a572  call    cs:__imp_SysFreeString
0x18002a578  test    ebx, ebx
0x18002a57a  jnz     loc_18002A600
0x18002a580  mov     rcx, [rsp+58h+var_28]
0x18002a585  lea     rdx, [rsp+58h+arg_8]
0x18002a58a  mov     qword ptr [r14], 0
0x18002a591  lea     r8d, [rbx+1]
0x18002a595  mov     [rsp+58h+var_38], rdx
0x18002a59a  mov     r9, r14
0x18002a59d  or      edx, 0FFFFFFFFh
0x18002a5a0  mov     rax, [rcx]
0x18002a5a3  mov     rax, [rax+20h]
0x18002a5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5ac  mov     ebx, eax
0x18002a5ae  test    eax, eax
0x18002a5b0  js      short loc_18002A5CA
0x18002a5b2  cmp     [rsp+58h+arg_8], 1
0x18002a5b7  jnz     short loc_18002A5CA
0x18002a5b9  mov     rdx, [rsp+58h+var_28]; struct IEnumWbemClassObject *
0x18002a5be  xor     ebx, ebx
0x18002a5c0  mov     rcx, rdi; struct IWbemServices *
0x18002a5c3  call    ?ValidateFinishedWCOEnum@@YAXPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; ValidateFinishedWCOEnum(IWbemServices *,IEnumWbemClassObject *)
0x18002a5c8  jmp     short loc_18002A5EF
0x18002a5ca  cmp     eax, 1
0x18002a5cd  jnz     short loc_18002A5EF
0x18002a5cf  test    bpl, bpl
0x18002a5d2  jz      short loc_18002A5EA
0x18002a5d4  mov     r8, r14; struct IWbemClassObject **
0x18002a5d7  lea     rdx, ?c_wszHnetFWLoggingSettings@@3QBGB; "HNet_FirewallLoggingSettings"
0x18002a5de  mov     rcx, rdi; struct IWbemServices *
0x18002a5e1  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x18002a5e6  mov     ebx, eax
0x18002a5e8  jmp     short loc_18002A5EF
0x18002a5ea  mov     ebx, 800710D8h
0x18002a5ef  mov     rcx, [rsp+58h+var_28]
0x18002a5f4  mov     rax, [rcx]
0x18002a5f7  mov     rax, [rax+10h]
0x18002a5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a600  mov     rbp, [rsp+58h+arg_10]
0x18002a605  mov     eax, ebx
0x18002a607  mov     rbx, [rsp+58h+arg_0]
0x18002a60c  add     rsp, 40h
0x18002a610  pop     r14
0x18002a612  pop     rdi
0x18002a613  pop     rsi
0x18002a614  retn
```
