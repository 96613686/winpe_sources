# mqrpcBindQMService(wchar_t const *,ulong,void *,ulong *,void * *)

- ea: `0x180013280`
- end: `0x1800133a2`
- name: `?mqrpcBindQMService@@YAJPEB_WKPEAXPEAKPEAPEAX@Z`
- size: `290`
- prototype: `int(const wchar_t *, unsigned int, void *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180011218`
- `0x180011864`
- `0x180013280`
- `0x18001373c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18001338a`
- `RPCRT4!RpcBindingFree` at `0x18001338a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall mqrpcBindQMService(wchar_t *a1, unsigned int a2, void *a3, unsigned int *a4, void **Binding)
{
  unsigned int v8; // ebp
  void **v9; // r14
  int BindingHandle; // esi
  void **v11; // rbx
  __int64 v12; // r8
  unsigned int v13; // edi
  void **v14; // rax

  v8 = *a4;
  v9 = Binding;
  *Binding = 0;
  Binding = 0;
  BindingHandle = CreateBindingHandle(a1, a3, v8, (RPC_BINDING_HANDLE *)&Binding);
  v11 = Binding;
  if ( !BindingHandle )
  {
    if ( *a4 == 1 || (BindingHandle = AddAuthentication(Binding, a1)) == 0 )
    {
      v13 = 0;
      v14 = v11;
      v11 = 0;
      *v9 = v14;
      goto LABEL_16;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 22), 44, v12, a2, v8, BindingHandle);
  }
  switch ( BindingHandle )
  {
    case 1703:
      *a4 = 1;
      v13 = -1072824319;
      break;
    case 1722:
      v13 = -1072824215;
      break;
    case 1753:
      v13 = -2147023143;
      break;
    default:
      v13 = -1072824319;
      if ( BindingHandle == 5 )
        v13 = -1072824283;
      break;
  }
LABEL_16:
  if ( v11 )
  {
    Binding = v11;
    RpcBindingFree((RPC_BINDING_HANDLE *)&Binding);
  }
  return v13;
}

```

## disassembly

```asm
0x180013280  mov     r11, rsp
0x180013283  push    rbx
0x180013284  push    rbp
0x180013285  push    rsi
0x180013286  push    rdi
0x180013287  push    r12
0x180013289  push    r14
0x18001328b  push    r15
0x18001328d  sub     rsp, 30h
0x180013291  mov     rdi, r9
0x180013294  mov     rax, r8
0x180013297  mov     r15d, edx
0x18001329a  mov     r12, rcx
0x18001329d  mov     ebp, [r9]
0x1800132a0  mov     r14, [rsp+68h+Binding]
0x1800132a8  mov     qword ptr [r14], 0
0x1800132af  mov     qword ptr [r11+28h], 0
0x1800132b7  lea     r9, [r11+28h]
0x1800132bb  mov     r8d, ebp; AuthnLevel
0x1800132be  mov     rdx, rax; IfSpec
0x1800132c1  call    _CreateBindingHandle
0x1800132c6  mov     esi, eax
0x1800132c8  mov     rbx, [rsp+68h+Binding]
0x1800132d0  test    eax, eax
0x1800132d2  jnz     short loc_180013328
0x1800132d4  cmp     dword ptr [rdi], 1
0x1800132d7  jz      short loc_18001333D
0x1800132d9  mov     r9d, ebp
0x1800132dc  mov     r8d, r15d
0x1800132df  mov     rdx, r12
0x1800132e2  mov     rcx, rbx
0x1800132e5  call    _AddAuthentication
0x1800132ea  mov     esi, eax
0x1800132ec  test    eax, eax
0x1800132ee  jz      short loc_18001333D
0x1800132f0  lea     rax, WPP_GLOBAL_Control
0x1800132f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132fe  cmp     rcx, rax
0x180013301  jz      short loc_180013328
0x180013303  test    byte ptr [rcx+0BCh], 1
0x18001330a  jz      short loc_180013328
0x18001330c  mov     edx, 2Ch ; ','
0x180013311  mov     [rsp+68h+var_40], esi
0x180013315  mov     [rsp+68h+var_48], ebp
0x180013319  mov     r9d, r15d
0x18001331c  mov     rcx, [rcx+0B0h]
0x180013323  call    WPP_SF_ddd
0x180013328  cmp     esi, 6A7h
0x18001332e  jnz     short loc_180013349
0x180013330  mov     dword ptr [rdi], 1
0x180013336  mov     edi, 0C00E0001h
0x18001333b  jmp     short loc_180013375
0x18001333d  xor     edi, edi
0x18001333f  mov     rax, rbx
0x180013342  xor     ebx, ebx
0x180013344  mov     [r14], rax
0x180013347  jmp     short loc_180013375
0x180013349  cmp     esi, 6BAh
0x18001334f  jnz     short loc_180013358
0x180013351  mov     edi, 0C00E0069h
0x180013356  jmp     short loc_180013375
0x180013358  cmp     esi, 6D9h
0x18001335e  jnz     short loc_180013367
0x180013360  mov     edi, 800706D9h
0x180013365  jmp     short loc_180013375
0x180013367  mov     edi, 0C00E0001h
0x18001336c  lea     eax, [rdi+24h]
0x18001336f  cmp     esi, 5
0x180013372  cmovz   edi, eax
0x180013375  test    rbx, rbx
0x180013378  jz      short loc_180013391
0x18001337a  mov     [rsp+68h+Binding], rbx
0x180013382  lea     rcx, [rsp+68h+Binding]; Binding
0x18001338a  call    cs:__imp_RpcBindingFree
0x180013390  nop
0x180013391  mov     eax, edi
0x180013393  add     rsp, 30h
0x180013397  pop     r15
0x180013399  pop     r14
0x18001339b  pop     r12
0x18001339d  pop     rdi
0x18001339e  pop     rsi
0x18001339f  pop     rbp
0x1800133a0  pop     rbx
0x1800133a1  retn
```
