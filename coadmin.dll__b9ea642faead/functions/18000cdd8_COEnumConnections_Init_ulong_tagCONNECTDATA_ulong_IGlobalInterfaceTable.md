# COEnumConnections::Init(ulong,tagCONNECTDATA *,ulong,IGlobalInterfaceTable *)

- ea: `0x18000cdd8`
- end: `0x18000cfcb`
- name: `?Init@COEnumConnections@@QEAAJKPEAUtagCONNECTDATA@@KPEAUIGlobalInterfaceTable@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(COEnumConnections *__hidden this, unsigned int, struct tagCONNECTDATA *, unsigned int, struct IGlobalInterfaceTable *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c9a0`
- `0x18000ca70`

## callees

- `0x1800010bc`
- `0x18000cdd8`
- `0x18000d5e0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall COEnumConnections::Init(
        COEnumConnections *this,
        unsigned int a2,
        struct tagCONNECTDATA *a3,
        int a4,
        struct IGlobalInterfaceTable *a5)
{
  void *v8; // rax
  int v9; // ebx
  struct IGlobalInterfaceTable *v10; // r13
  unsigned int v11; // r15d
  __int64 v12; // r12
  __int64 v13; // rdi
  struct IUnknown *v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // r8
  struct IUnknown *v18; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v19; // [rsp+80h] [rbp+40h] BYREF
  struct tagCONNECTDATA *v20; // [rsp+90h] [rbp+50h]

  v20 = a3;
  *((_DWORD *)this + 7) = a2;
  *((_DWORD *)this + 6) = a4;
  v19 = 0;
  v18 = 0;
  v8 = operator new[](saturated_mul(a2, 0x10u));
  *((_QWORD *)this + 4) = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    goto LABEL_22;
  }
  v9 = 0;
  if ( !a2 )
  {
LABEL_22:
    v14 = v19;
    goto LABEL_23;
  }
  v10 = a5;
  v11 = 0;
  if ( !a5 )
  {
    v15 = 0;
    do
    {
      v16 = v15;
      *(_DWORD *)(*((_QWORD *)this + 4) + v16 * 16 + 8) = a3[v16].dwCookie;
      *(_QWORD *)(v16 * 16 + *((_QWORD *)this + 4)) = 0;
      if ( v9 >= 0 )
        v9 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64))a3[v16].pUnk->lpVtbl->QueryInterface)(
               a3[v16].pUnk,
               &IID_IMSAdminBaseSink_W,
               *((_QWORD *)this + 4) + v16 * 16);
      ++v15;
    }
    while ( v15 < a2 );
    goto LABEL_22;
  }
  v12 = 0;
  do
  {
    v13 = 2 * v12;
    *(_DWORD *)(*((_QWORD *)this + 4) + 8 * v13 + 8) = v20[v12].dwCookie;
    *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v13) = 0;
    if ( v9 < 0
      || (v9 = ((__int64 (__fastcall *)(struct IGlobalInterfaceTable *, _QWORD, GUID *, struct IUnknown **))v10->lpVtbl->GetInterfaceFromGlobal)(
                 v10,
                 *(unsigned int *)(*((_QWORD *)this + 4) + 16 * v12 + 8),
                 &IID_IUnknown,
                 &v19),
          v9 < 0) )
    {
      v14 = v19;
    }
    else
    {
      v14 = v19;
      if ( v19 )
      {
        v9 = SetSinkCallbackSecurityBlanket(v19);
        if ( v9 >= 0 )
        {
          v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v19->lpVtbl->QueryInterface)(
                 v19,
                 &IID_IMSAdminBaseSink_W,
                 &v18);
          if ( v9 >= 0 )
          {
            v9 = SetSinkCallbackSecurityBlanket(v18);
            if ( v9 >= 0 )
            {
              *(_QWORD *)(*((_QWORD *)this + 4) + 16 * v12) = v18;
              v18 = 0;
            }
          }
        }
        ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
        v14 = 0;
        v19 = 0;
      }
    }
    ++v11;
    ++v12;
  }
  while ( v11 < a2 );
LABEL_23:
  if ( v14 )
  {
    ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
    v19 = 0;
  }
  if ( v18 )
    ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000cdd8  mov     [rsp-38h+arg_8], rbx
0x18000cddd  mov     [rsp-38h+arg_10], r8
0x18000cde2  push    rbp
0x18000cde3  push    rsi
0x18000cde4  push    rdi
0x18000cde5  push    r12
0x18000cde7  push    r13
0x18000cde9  push    r14
0x18000cdeb  push    r15
0x18000cded  mov     rbp, rsp
0x18000cdf0  sub     rsp, 40h
0x18000cdf4  mov     r14d, edx
0x18000cdf7  mov     rsi, rcx
0x18000cdfa  mov     [rcx+1Ch], r14d
0x18000cdfe  mov     eax, 10h
0x18000ce03  mov     [rcx+18h], r9d
0x18000ce07  mov     r12, r8
0x18000ce0a  mul     r14
0x18000ce0d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ce14  mov     [rbp+arg_0], 0
0x18000ce1c  mov     [rbp+var_10], 0
0x18000ce24  cmovb   rax, rcx
0x18000ce28  mov     rcx, rax; unsigned __int64
0x18000ce2b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ce30  mov     [rsi+20h], rax
0x18000ce34  test    rax, rax
0x18000ce37  jz      loc_18000CF7A
0x18000ce3d  xor     ebx, ebx
0x18000ce3f  test    r14d, r14d
0x18000ce42  jz      loc_18000CF7F
0x18000ce48  mov     r13, [rbp+arg_20]
0x18000ce4c  xor     r15d, r15d
0x18000ce4f  test    r13, r13
0x18000ce52  jz      loc_18000CF32
0x18000ce58  xor     r12d, r12d
0x18000ce5b  mov     rax, [rbp+arg_10]
0x18000ce5f  mov     rdi, r12
0x18000ce62  mov     rcx, [rsi+20h]
0x18000ce66  add     rdi, rdi
0x18000ce69  mov     eax, [rax+rdi*8+8]
0x18000ce6d  mov     [rcx+rdi*8+8], eax
0x18000ce71  mov     rax, [rsi+20h]
0x18000ce75  mov     qword ptr [rax+rdi*8], 0
0x18000ce7d  test    ebx, ebx
0x18000ce7f  js      loc_18000CF1D
0x18000ce85  mov     rax, [r13+0]
0x18000ce89  lea     r9, [rbp+arg_0]
0x18000ce8d  mov     rdx, [rsi+20h]
0x18000ce91  lea     r8, IID_IUnknown
0x18000ce98  mov     rcx, r13
0x18000ce9b  mov     rax, [rax+28h]
0x18000ce9f  mov     edx, [rdx+rdi*8+8]
0x18000cea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea8  mov     ebx, eax
0x18000ceaa  test    eax, eax
0x18000ceac  js      short loc_18000CF1D
0x18000ceae  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18000ceb2  test    rcx, rcx
0x18000ceb5  jz      short loc_18000CF21
0x18000ceb7  call    ?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z; SetSinkCallbackSecurityBlanket(IUnknown *)
0x18000cebc  mov     ebx, eax
0x18000cebe  test    eax, eax
0x18000cec0  js      short loc_18000CF05
0x18000cec2  mov     rcx, [rbp+arg_0]
0x18000cec6  lea     r8, [rbp+var_10]
0x18000ceca  lea     rdx, IID_IMSAdminBaseSink_W
0x18000ced1  mov     rax, [rcx]
0x18000ced4  mov     rax, [rax]
0x18000ced7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cedc  mov     ebx, eax
0x18000cede  test    eax, eax
0x18000cee0  js      short loc_18000CF05
0x18000cee2  mov     rcx, [rbp+var_10]; struct IUnknown *
0x18000cee6  call    ?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z; SetSinkCallbackSecurityBlanket(IUnknown *)
0x18000ceeb  mov     ebx, eax
0x18000ceed  test    eax, eax
0x18000ceef  js      short loc_18000CF05
0x18000cef1  mov     rax, [rbp+var_10]
0x18000cef5  mov     rcx, [rsi+20h]
0x18000cef9  mov     [rcx+rdi*8], rax
0x18000cefd  mov     [rbp+var_10], 0
0x18000cf05  mov     rcx, [rbp+arg_0]
0x18000cf09  mov     rax, [rcx]
0x18000cf0c  mov     rax, [rax+10h]
0x18000cf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf15  xor     ecx, ecx
0x18000cf17  mov     [rbp+arg_0], rcx
0x18000cf1b  jmp     short loc_18000CF21
0x18000cf1d  mov     rcx, [rbp+arg_0]
0x18000cf21  inc     r15d
0x18000cf24  inc     r12
0x18000cf27  cmp     r15d, r14d
0x18000cf2a  jb      loc_18000CE5B
0x18000cf30  jmp     short loc_18000CF83
0x18000cf32  xor     edi, edi
0x18000cf34  mov     rcx, [rsi+20h]
0x18000cf38  mov     r8d, edi
0x18000cf3b  shl     r8, 4
0x18000cf3f  mov     eax, [r8+r12+8]
0x18000cf44  mov     [rcx+r8+8], eax
0x18000cf49  mov     rax, [rsi+20h]
0x18000cf4d  mov     [r8+rax], r15
0x18000cf51  test    ebx, ebx
0x18000cf53  js      short loc_18000CF71
0x18000cf55  mov     rcx, [r8+r12]
0x18000cf59  add     r8, [rsi+20h]
0x18000cf5d  mov     rdx, [rcx]
0x18000cf60  mov     rax, [rdx]
0x18000cf63  lea     rdx, IID_IMSAdminBaseSink_W
0x18000cf6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf6f  mov     ebx, eax
0x18000cf71  inc     edi
0x18000cf73  cmp     edi, r14d
0x18000cf76  jb      short loc_18000CF34
0x18000cf78  jmp     short loc_18000CF7F
0x18000cf7a  mov     ebx, 8007000Eh
0x18000cf7f  mov     rcx, [rbp+arg_0]
0x18000cf83  test    rcx, rcx
0x18000cf86  jz      short loc_18000CF9C
0x18000cf88  mov     rax, [rcx]
0x18000cf8b  mov     rax, [rax+10h]
0x18000cf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf94  mov     [rbp+arg_0], 0
0x18000cf9c  mov     rcx, [rbp+var_10]
0x18000cfa0  test    rcx, rcx
0x18000cfa3  jz      short loc_18000CFB1
0x18000cfa5  mov     rax, [rcx]
0x18000cfa8  mov     rax, [rax+10h]
0x18000cfac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb1  mov     eax, ebx
0x18000cfb3  mov     rbx, [rsp+40h+arg_8]
0x18000cfbb  add     rsp, 40h
0x18000cfbf  pop     r15
0x18000cfc1  pop     r14
0x18000cfc3  pop     r13
0x18000cfc5  pop     r12
0x18000cfc7  pop     rdi
0x18000cfc8  pop     rsi
0x18000cfc9  pop     rbp
0x18000cfca  retn
```
