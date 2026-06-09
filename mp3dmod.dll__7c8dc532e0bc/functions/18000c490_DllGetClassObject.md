# DllGetClassObject

- ea: `0x18000c490`
- end: `0x18000c589`
- name: `DllGetClassObject`
- size: `249`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c490`
- `0x18000c590`
- `0x18000e2bc`
- `0x180012010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  int i; // ecx
  const struct CComClassTemplate *v7; // rdi
  __int64 v8; // rax
  CClassFactory *v9; // rax
  CClassFactory *v10; // rax
  __int64 v12; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v5 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v5 )
    goto LABEL_5;
  v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
  if ( v12 )
    return -2147467262;
LABEL_5:
  for ( i = 0; ; ++i )
  {
    if ( i >= 1 )
      return -2147221231;
    v7 = (const struct CComClassTemplate *)(&g_ComClassTemplates + 2 * i);
    v8 = **(_QWORD **)v7 - *(_QWORD *)&rclsid->Data1;
    if ( !v8 )
      v8 = *(_QWORD *)(*(_QWORD *)v7 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v8 )
      break;
  }
  v9 = (CClassFactory *)operator new(0x18u);
  if ( v9 )
  {
    v10 = CClassFactory::CClassFactory(v9, v7);
    *ppv = v10;
    if ( v10 )
    {
      (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v10 + 8LL))(v10);
      return 0;
    }
  }
  else
  {
    *ppv = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x18000c490  mov     [rsp+arg_0], rbx
0x18000c495  push    rdi
0x18000c496  sub     rsp, 20h
0x18000c49a  mov     rbx, r8
0x18000c49d  mov     r8, rcx
0x18000c4a0  test    rbx, rbx
0x18000c4a3  jz      loc_18000C57B
0x18000c4a9  mov     qword ptr [rbx], 0
0x18000c4b0  mov     rax, [rdx]
0x18000c4b3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c4ba  jnz     short loc_18000C4C7
0x18000c4bc  mov     rax, [rdx+8]
0x18000c4c0  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c4c7  test    rax, rax
0x18000c4ca  jnz     short loc_18000C53F
0x18000c4cc  xor     ecx, ecx
0x18000c4ce  cmp     ecx, 1
0x18000c4d1  jge     loc_18000C582
0x18000c4d7  lea     rdx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18000c4de  movsxd  rdi, ecx
0x18000c4e1  shl     rdi, 4
0x18000c4e5  add     rdi, rdx
0x18000c4e8  mov     rdx, [rdi]
0x18000c4eb  mov     rax, [rdx]
0x18000c4ee  sub     rax, [r8]
0x18000c4f1  jnz     short loc_18000C4FB
0x18000c4f3  mov     rax, [rdx+8]
0x18000c4f7  sub     rax, [r8+8]
0x18000c4fb  test    rax, rax
0x18000c4fe  jnz     short loc_18000C566
0x18000c500  lea     ecx, [rax+18h]; Size
0x18000c503  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c508  test    rax, rax
0x18000c50b  jz      short loc_18000C56D
0x18000c50d  mov     rdx, rdi; struct CComClassTemplate *
0x18000c510  mov     rcx, rax; this
0x18000c513  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x18000c518  mov     [rbx], rax
0x18000c51b  mov     rdx, rax
0x18000c51e  test    rax, rax
0x18000c521  jz      short loc_18000C574
0x18000c523  mov     rcx, [rax]
0x18000c526  mov     rax, [rcx+8]
0x18000c52a  mov     rcx, rdx
0x18000c52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c532  xor     eax, eax
0x18000c534  mov     rbx, [rsp+28h+arg_0]
0x18000c539  add     rsp, 20h
0x18000c53d  pop     rdi
0x18000c53e  retn
0x18000c53f  mov     rax, [rdx]
0x18000c542  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000c549  jnz     short loc_18000C556
0x18000c54b  mov     rax, [rdx+8]
0x18000c54f  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000c556  test    rax, rax
0x18000c559  jz      loc_18000C4CC
0x18000c55f  mov     eax, 80004002h
0x18000c564  jmp     short loc_18000C534
0x18000c566  inc     ecx
0x18000c568  jmp     loc_18000C4CE
0x18000c56d  mov     qword ptr [rbx], 0
0x18000c574  mov     eax, 8007000Eh
0x18000c579  jmp     short loc_18000C534
0x18000c57b  mov     eax, 80004003h
0x18000c580  jmp     short loc_18000C534
0x18000c582  mov     eax, 80040111h
0x18000c587  jmp     short loc_18000C534
```
