# UpdateOrStopService(IWbemServices *,ushort *,ulong)

- ea: `0x18002aa18`
- end: `0x18002ab29`
- name: `?UpdateOrStopService@@YAJPEAUIWbemServices@@PEAGK@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800274d0`

## callees

- `0x18002a898`
- `0x18002aa18`
- `0x18002ac5c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002aa41`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa41`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa92`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa92`

## pseudocode

```c
__int64 __fastcall UpdateOrStopService(struct IWbemServices *a1, unsigned __int16 *a2, int a3)
{
  OLECHAR *v5; // rdi
  struct IWbemServicesVtbl *lpVtbl; // r8
  int v7; // ebx
  _QWORD v9[3]; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v10 = a3;
  v11 = 0;
  v5 = SysAllocString(L"SELECT * FROM HNet_ConnectionProperties WHERE IsIcsPublic != FALSE or IsIcsPrivate != FALSE");
  if ( v5 )
  {
    lpVtbl = a1->lpVtbl;
    v11 = 0;
    v7 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, OLECHAR *, __int64, _QWORD, __int64 *))lpVtbl->ExecQuery)(
           a1,
           a2,
           v5,
           48,
           0,
           &v11);
    SysFreeString(v5);
    if ( !v7 )
    {
      v10 = 0;
      v9[0] = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *, int *))(*(_QWORD *)v11 + 32LL))(
             v11,
             0xFFFFFFFFLL,
             1,
             v9,
             &v10);
      if ( v7 >= 0 )
      {
        if ( v10 == 1 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
          UpdateService(0x81u);
        }
        else
        {
          StopService();
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002aa18  mov     rax, rsp
0x18002aa1b  mov     [rax+8], rbx
0x18002aa1f  mov     [rax+10h], rsi
0x18002aa23  mov     [rax+18h], r8d
0x18002aa27  push    rdi
0x18002aa28  sub     rsp, 50h
0x18002aa2c  mov     rbx, rcx
0x18002aa2f  mov     qword ptr [rax+20h], 0
0x18002aa37  lea     rcx, ?c_wszServiceCheckQuery@@3QBGB; "SELECT * FROM HNet_ConnectionProperties"...
0x18002aa3e  mov     rsi, rdx
0x18002aa41  call    cs:__imp_SysAllocString
0x18002aa47  mov     rdi, rax
0x18002aa4a  test    rax, rax
0x18002aa4d  jz      loc_18002AB12
0x18002aa53  mov     r8, [rbx]
0x18002aa56  lea     rcx, [rsp+58h+arg_18]
0x18002aa5b  mov     [rsp+58h+var_30], rcx
0x18002aa60  mov     r9d, 30h ; '0'
0x18002aa66  mov     rdx, rsi
0x18002aa69  mov     [rsp+58h+arg_18], 0
0x18002aa72  mov     rcx, rbx
0x18002aa75  mov     [rsp+58h+var_38], 0
0x18002aa7e  mov     rax, [r8+0A0h]
0x18002aa85  mov     r8, rdi
0x18002aa88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa8d  mov     rcx, rdi; bstrString
0x18002aa90  mov     ebx, eax
0x18002aa92  call    cs:__imp_SysFreeString
0x18002aa98  test    ebx, ebx
0x18002aa9a  jnz     short loc_18002AB17
0x18002aa9c  mov     rcx, [rsp+58h+arg_18]
0x18002aaa1  lea     rdx, [rsp+58h+arg_10]
0x18002aaa6  mov     [rsp+58h+arg_10], ebx
0x18002aaaa  lea     r9, [rsp+58h+var_18]
0x18002aaaf  mov     [rsp+58h+var_18], 0
0x18002aab8  lea     r8d, [rbx+1]
0x18002aabc  mov     [rsp+58h+var_38], rdx
0x18002aac1  or      edx, 0FFFFFFFFh
0x18002aac4  mov     rax, [rcx]
0x18002aac7  mov     rax, [rax+20h]
0x18002aacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aad0  mov     ebx, eax
0x18002aad2  test    eax, eax
0x18002aad4  js      short loc_18002AAFF
0x18002aad6  cmp     [rsp+58h+arg_10], 1
0x18002aadb  jnz     short loc_18002AAFA
0x18002aadd  mov     rcx, [rsp+58h+var_18]
0x18002aae2  mov     rdx, [rcx]
0x18002aae5  mov     rax, [rdx+10h]
0x18002aae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaee  mov     ecx, 81h; dwControl
0x18002aaf3  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x18002aaf8  jmp     short loc_18002AAFF
0x18002aafa  call    ?StopService@@YAXXZ; StopService(void)
0x18002aaff  mov     rcx, [rsp+58h+arg_18]
0x18002ab04  mov     rax, [rcx]
0x18002ab07  mov     rax, [rax+10h]
0x18002ab0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab10  jmp     short loc_18002AB17
0x18002ab12  mov     ebx, 8007000Eh
0x18002ab17  mov     rsi, [rsp+58h+arg_8]
0x18002ab1c  mov     eax, ebx
0x18002ab1e  mov     rbx, [rsp+58h+arg_0]
0x18002ab23  add     rsp, 50h
0x18002ab27  pop     rdi
0x18002ab28  retn
```
