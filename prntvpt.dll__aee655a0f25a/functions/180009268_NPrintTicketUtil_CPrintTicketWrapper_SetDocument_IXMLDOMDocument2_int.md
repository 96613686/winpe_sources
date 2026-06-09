# NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)

- ea: `0x180009268`
- end: `0x18000934e`
- name: `?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z`
- size: `230`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMDocument2 *, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002c80`
- `0x180008498`
- `0x18000856c`
- `0x180008848`
- `0x180008f20`
- `0x18000e608`
- `0x18001adb4`

## callees

- `0x180009268`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800092b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800092b9`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMDocument2 *a2,
        int a3)
{
  _QWORD *v6; // rsi
  HRESULT Instance; // edi
  __int64 v8; // rcx
  __int64 v9; // rcx

  if ( !a2 )
    return 2147942487LL;
  *((_QWORD *)this + 1) = a2;
  ((void (__fastcall *)(struct IXMLDOMDocument2 *))a2->lpVtbl->AddRef)(a2);
  *((_DWORD *)this + 9) = a3;
  v6 = (_QWORD *)((char *)this + 16);
  Instance = CoCreateInstance(&CLSID_MXNamespaceManager60, 0, 1u, &IID_IMXNamespaceManager, (LPVOID *)this + 2);
  if ( Instance < 0 )
    goto LABEL_7;
  Instance = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 360LL))(
               *((_QWORD *)this + 1),
               (char *)this + 24);
  if ( Instance < 0 )
    goto LABEL_7;
  if ( !*((_QWORD *)this + 3) )
  {
    Instance = -2147467259;
LABEL_7:
    v8 = *((_QWORD *)this + 1);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 1) = 0;
    }
    if ( *v6 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
      *v6 = 0;
    }
    v9 = *((_QWORD *)this + 3);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 3) = 0;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180009268  push    rbx
0x18000926a  push    rbp
0x18000926b  push    rsi
0x18000926c  push    rdi
0x18000926d  sub     rsp, 38h
0x180009271  mov     edi, r8d
0x180009274  mov     rbx, rcx
0x180009277  test    rdx, rdx
0x18000927a  jnz     short loc_180009286
0x18000927c  mov     eax, 80070057h
0x180009281  jmp     loc_180009345
0x180009286  mov     [rcx+8], rdx
0x18000928a  mov     rcx, rdx
0x18000928d  mov     rax, [rdx]
0x180009290  mov     rax, [rax+8]
0x180009294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009299  xor     edx, edx; pUnkOuter
0x18000929b  mov     [rbx+24h], edi
0x18000929e  lea     rsi, [rbx+10h]
0x1800092a2  lea     r9, IID_IMXNamespaceManager; riid
0x1800092a9  mov     [rsp+58h+ppv], rsi; ppv
0x1800092ae  lea     rcx, CLSID_MXNamespaceManager60; rclsid
0x1800092b5  lea     r8d, [rdx+1]; dwClsContext
0x1800092b9  call    cs:__imp_CoCreateInstance
0x1800092bf  mov     edi, eax
0x1800092c1  test    eax, eax
0x1800092c3  js      short loc_1800092EE
0x1800092c5  mov     rcx, [rbx+8]
0x1800092c9  lea     rdx, [rbx+18h]
0x1800092cd  mov     rax, [rcx]
0x1800092d0  mov     rax, [rax+168h]
0x1800092d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092dc  mov     edi, eax
0x1800092de  test    eax, eax
0x1800092e0  js      short loc_1800092EE
0x1800092e2  cmp     qword ptr [rbx+18h], 0
0x1800092e7  jnz     short loc_180009343
0x1800092e9  mov     edi, 80004005h
0x1800092ee  mov     rcx, [rbx+8]
0x1800092f2  test    rcx, rcx
0x1800092f5  jz      short loc_18000930B
0x1800092f7  mov     rax, [rcx]
0x1800092fa  mov     rax, [rax+10h]
0x1800092fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009303  mov     qword ptr [rbx+8], 0
0x18000930b  mov     rcx, [rsi]
0x18000930e  test    rcx, rcx
0x180009311  jz      short loc_180009326
0x180009313  mov     rax, [rcx]
0x180009316  mov     rax, [rax+10h]
0x18000931a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000931f  mov     qword ptr [rsi], 0
0x180009326  mov     rcx, [rbx+18h]
0x18000932a  test    rcx, rcx
0x18000932d  jz      short loc_180009343
0x18000932f  mov     rax, [rcx]
0x180009332  mov     rax, [rax+10h]
0x180009336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000933b  mov     qword ptr [rbx+18h], 0
0x180009343  mov     eax, edi
0x180009345  add     rsp, 38h
0x180009349  pop     rdi
0x18000934a  pop     rsi
0x18000934b  pop     rbp
0x18000934c  pop     rbx
0x18000934d  retn
```
