# CActiveXInstallBroker::RegisterDllFile2(ushort *,ushort *,int,int)

- ea: `0x140005108`
- end: `0x140005180`
- name: `?RegisterDllFile2@CActiveXInstallBroker@@QEAAJPEAG0HH@Z`
- size: `120`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400081a0`
- `0x1400081d0`

## callees

- `0x140005108`
- `0x140005188`
- `0x140005e98`

## import_xrefs

- `urlmon!CompatFlagsFromClsid` at `0x140005139`
- `urlmon!CompatFlagsFromClsid` at `0x140005139`

## pseudocode

```c
HRESULT __fastcall CActiveXInstallBroker::RegisterDllFile2(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        int a5)
{
  HRESULT result; // eax
  DWORD v10[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD v11; // [rsp+70h] [rbp+8h] BYREF

  v11 = 0;
  v10[0] = 0;
  result = CompatFlagsFromClsid((CLSID *)((char *)this + 88), &v11, v10);
  if ( result >= 0 )
  {
    if ( (v11 & 0x1000000) != 0 )
      return CActiveXInstallBroker::STARegisterDllFile2((OLECHAR *)this, a2, a3, a4, a5);
    else
      return CActiveXInstallBroker::RegisterDllFile2Helper(this, a2, a3, a4, a5);
  }
  return result;
}

```

## disassembly

```asm
0x140005108  mov     rax, rsp
0x14000510b  push    rbx
0x14000510c  push    rbp
0x14000510d  push    rsi
0x14000510e  push    rdi
0x14000510f  sub     rsp, 48h
0x140005113  mov     rsi, r8
0x140005116  mov     dword ptr [rax+8], 0
0x14000511d  mov     rbp, rdx
0x140005120  mov     dword ptr [rax-38h], 0
0x140005127  mov     rbx, rcx
0x14000512a  lea     r8, [rax-38h]; pdwMiscStatusFlags
0x14000512e  add     rcx, 58h ; 'X'; pclsid
0x140005132  lea     rdx, [rax+8]; pdwCompatFlags
0x140005136  mov     edi, r9d
0x140005139  call    cs:__imp_CompatFlagsFromClsid
0x140005140  nop     dword ptr [rax+rax+00h]
0x140005145  test    eax, eax
0x140005147  js      short loc_140005176
0x140005149  test    [rsp+68h+arg_0], 1000000h
0x140005151  mov     r9d, edi; int
0x140005154  mov     eax, [rsp+68h+arg_20]
0x14000515b  mov     r8, rsi; unsigned __int16 *
0x14000515e  mov     [rsp+68h+var_48], eax; int
0x140005162  mov     rdx, rbp; unsigned __int16 *
0x140005165  mov     rcx, rbx; this
0x140005168  jz      short loc_140005171
0x14000516a  call    ?STARegisterDllFile2@CActiveXInstallBroker@@AEAAJPEAG0HH@Z; CActiveXInstallBroker::STARegisterDllFile2(ushort *,ushort *,int,int)
0x14000516f  jmp     short loc_140005176
0x140005171  call    ?RegisterDllFile2Helper@CActiveXInstallBroker@@AEAAJPEAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2Helper(ushort *,ushort *,int,int)
0x140005176  add     rsp, 48h
0x14000517a  pop     rdi
0x14000517b  pop     rsi
0x14000517c  pop     rbp
0x14000517d  pop     rbx
0x14000517e  retn
```
