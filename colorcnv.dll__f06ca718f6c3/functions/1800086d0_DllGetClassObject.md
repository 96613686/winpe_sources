# DllGetClassObject

- ea: `0x1800086d0`
- end: `0x1800087c9`
- name: `DllGetClassObject`
- size: `249`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800086d0`
- `0x1800087d0`
- `0x18000a6dc`
- `0x18002b010`

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
0x1800086d0  mov     [rsp+arg_0], rbx
0x1800086d5  push    rdi
0x1800086d6  sub     rsp, 20h
0x1800086da  mov     rbx, r8
0x1800086dd  mov     r8, rcx
0x1800086e0  test    rbx, rbx
0x1800086e3  jz      loc_1800087BB
0x1800086e9  mov     qword ptr [rbx], 0
0x1800086f0  mov     rax, [rdx]
0x1800086f3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800086fa  jnz     short loc_180008707
0x1800086fc  mov     rax, [rdx+8]
0x180008700  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180008707  test    rax, rax
0x18000870a  jnz     short loc_18000877F
0x18000870c  xor     ecx, ecx
0x18000870e  cmp     ecx, 1
0x180008711  jge     loc_1800087C2
0x180008717  lea     rdx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18000871e  movsxd  rdi, ecx
0x180008721  shl     rdi, 4
0x180008725  add     rdi, rdx
0x180008728  mov     rdx, [rdi]
0x18000872b  mov     rax, [rdx]
0x18000872e  sub     rax, [r8]
0x180008731  jnz     short loc_18000873B
0x180008733  mov     rax, [rdx+8]
0x180008737  sub     rax, [r8+8]
0x18000873b  test    rax, rax
0x18000873e  jnz     short loc_1800087A6
0x180008740  lea     ecx, [rax+18h]; Size
0x180008743  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008748  test    rax, rax
0x18000874b  jz      short loc_1800087AD
0x18000874d  mov     rdx, rdi; struct CComClassTemplate *
0x180008750  mov     rcx, rax; this
0x180008753  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x180008758  mov     [rbx], rax
0x18000875b  mov     rdx, rax
0x18000875e  test    rax, rax
0x180008761  jz      short loc_1800087B4
0x180008763  mov     rcx, [rax]
0x180008766  mov     rax, [rcx+8]
0x18000876a  mov     rcx, rdx
0x18000876d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008772  xor     eax, eax
0x180008774  mov     rbx, [rsp+28h+arg_0]
0x180008779  add     rsp, 20h
0x18000877d  pop     rdi
0x18000877e  retn
0x18000877f  mov     rax, [rdx]
0x180008782  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180008789  jnz     short loc_180008796
0x18000878b  mov     rax, [rdx+8]
0x18000878f  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180008796  test    rax, rax
0x180008799  jz      loc_18000870C
0x18000879f  mov     eax, 80004002h
0x1800087a4  jmp     short loc_180008774
0x1800087a6  inc     ecx
0x1800087a8  jmp     loc_18000870E
0x1800087ad  mov     qword ptr [rbx], 0
0x1800087b4  mov     eax, 8007000Eh
0x1800087b9  jmp     short loc_180008774
0x1800087bb  mov     eax, 80004003h
0x1800087c0  jmp     short loc_180008774
0x1800087c2  mov     eax, 80040111h
0x1800087c7  jmp     short loc_180008774
```
