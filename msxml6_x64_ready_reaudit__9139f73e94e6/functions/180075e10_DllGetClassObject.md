# DllGetClassObject

- ea: `0x180075e10`
- end: `0x180075f4e`
- name: `DllGetClassObject`
- size: `318`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180075e10`
- `0x18008703c`
- `0x18009402c`
- `0x180095e54`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800d355c`
- `0x18018c010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180075e80`
- `RPCRT4!NdrDllGetClassObject` at `0x180075e80`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  int i; // edx
  __int64 (__fastcall *v8)(); // r8
  int v9; // eax

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( !sub_18018C010() )
    return -2147467259;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&pProxyFileList, &pclsid, &pPSFactoryBuffer);
  if ( result )
  {
    for ( i = 0; (unsigned __int64)i < 0xC; ++i )
    {
      v8 = off_1801AFE10[i][1];
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)v8 && *(_QWORD *)rclsid->Data4 == *((_QWORD *)v8 + 1) )
      {
        sub_18008703C();
        return sub_18018C010();
      }
    }
    sub_18008703C();
    v9 = sub_180095E54();
    return sub_1800D355C(v9, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x180075e10  mov     [rsp+arg_10], r8
0x180075e15  push    rbx
0x180075e16  push    rsi
0x180075e17  push    rdi
0x180075e18  push    r14
0x180075e1a  sub     rsp, 48h
0x180075e1e  mov     rbx, r8
0x180075e21  mov     r14, rdx
0x180075e24  mov     rdi, rcx
0x180075e27  test    r8, r8
0x180075e2a  jnz     short loc_180075E36
0x180075e2c  mov     eax, 80070057h
0x180075e31  jmp     loc_180075F43
0x180075e36  mov     qword ptr [r8], 0
0x180075e3d  mov     rax, cs:qword_1801F76F0
0x180075e44  call    sub_18018C010
0x180075e49  test    rax, rax
0x180075e4c  jnz     short loc_180075E58
0x180075e4e  mov     eax, 80004005h
0x180075e53  jmp     loc_180075F43
0x180075e58  lea     rax, pPSFactoryBuffer
0x180075e5f  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180075e64  lea     rax, pclsid
0x180075e6b  mov     [rsp+68h+pclsid], rax; pclsid
0x180075e70  lea     r9, pProxyFileList; pProxyFileList
0x180075e77  mov     r8, rbx; ppv
0x180075e7a  mov     rdx, r14; riid
0x180075e7d  mov     rcx, rdi; rclsid
0x180075e80  call    cs:NdrDllGetClassObject
0x180075e87  nop     dword ptr [rax+rax+00h]
0x180075e8c  test    eax, eax
0x180075e8e  jz      loc_180075F43
0x180075e94  xor     edx, edx
0x180075e96  mov     [rsp+68h+var_34], edx
0x180075e9a  movsxd  rax, edx
0x180075e9d  cmp     rax, 0Ch
0x180075ea1  jnb     short loc_180075EE3
0x180075ea3  lea     rsi, off_1801AFE10
0x180075eaa  mov     rsi, [rsi+rax*8]
0x180075eae  mov     r8, [rsi+8]
0x180075eb2  mov     rax, [rdi]
0x180075eb5  cmp     rax, [r8]
0x180075eb8  jnz     short loc_180075EDF
0x180075eba  mov     rax, [rdi+8]
0x180075ebe  cmp     rax, [r8+8]
0x180075ec2  jnz     short loc_180075EDF
0x180075ec4  call    sub_18008703C
0x180075ec9  mov     rax, [rsi]
0x180075ecc  mov     r8, rbx
0x180075ecf  mov     rdx, r14
0x180075ed2  mov     rcx, rsi
0x180075ed5  mov     rax, [rax]
0x180075ed8  call    sub_18018C010
0x180075edd  jmp     short loc_180075F00
0x180075edf  inc     edx
0x180075ee1  jmp     short loc_180075E96
0x180075ee3  call    sub_18008703C
0x180075ee8  call    sub_180095E54
0x180075eed  mov     [rsp+68h+pclsid], rbx; PVOID
0x180075ef2  mov     r9, r14
0x180075ef5  mov     r8, rdi
0x180075ef8  mov     rcx, rax; int
0x180075efb  call    sub_1800D355C
0x180075f00  mov     [rsp+68h+var_38], eax
0x180075f04  jmp     short loc_180075F43
0x180075f06  call    sub_1800A3C08
0x180075f0b  mov     rax, [rsp+68h+arg_10]
0x180075f13  mov     qword ptr [rax], 0
0x180075f1a  mov     ecx, cs:TlsIndex
0x180075f20  mov     rax, gs:58h
0x180075f29  mov     edx, 8
0x180075f2e  mov     rax, [rax+rcx*8]
0x180075f32  mov     rcx, [rax+rdx]
0x180075f36  mov     rcx, [rcx+8]
0x180075f3a  call    sub_18009402C
0x180075f3f  mov     [rsp+68h+var_38], eax
0x180075f43  add     rsp, 48h
0x180075f47  pop     r14
0x180075f49  pop     rdi
0x180075f4a  pop     rsi
0x180075f4b  pop     rbx
0x180075f4c  retn
0x18017fc82  push    rbp
0x18017fc84  sub     rsp, 30h
0x18017fc88  mov     rbp, rdx
0x18017fc8b  call    sub_18009FEFC
0x18017fc90  nop
0x18017fc91  add     rsp, 30h
0x18017fc95  pop     rbp
0x18017fc96  retn
```
