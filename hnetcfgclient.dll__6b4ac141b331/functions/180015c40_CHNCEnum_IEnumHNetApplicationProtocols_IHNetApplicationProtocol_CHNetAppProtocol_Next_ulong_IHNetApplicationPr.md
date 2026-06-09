# CHNCEnum<IEnumHNetApplicationProtocols,IHNetApplicationProtocol,CHNetAppProtocol>::Next(ulong,IHNetApplicationProtocol * *,ulong *)

- ea: `0x180015c40`
- end: `0x180015e3f`
- name: `?Next@?$CHNCEnum@UIEnumHNetApplicationProtocols@@UIHNetApplicationProtocol@@VCHNetAppProtocol@@@@UEAAJKPEAPEAUIHNetApplicationProtocol@@PEAK@Z`
- size: `511`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001ec4`
- `0x18000feb4`
- `0x180015c40`
- `0x180022fe0`
- `0x18002d1d2`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015e08`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015e08`

## pseudocode

```c
__int64 __fastcall CHNCEnum<IEnumHNetApplicationProtocols,IHNetApplicationProtocol,CHNetAppProtocol>::Next(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rsi
  int v8; // ebx
  unsigned __int64 v9; // rax
  struct IWbemClassObject **v10; // rax
  struct IWbemClassObject **v11; // r15
  unsigned int v12; // ecx
  unsigned int v13; // edi
  CHNetAppProtocol *v14; // r14
  __int64 v15; // rcx
  __int64 i; // rdi
  struct IWbemClassObject *v17; // rdx
  unsigned int v20; // [rsp+78h] [rbp+10h] BYREF
  CHNetAppProtocol *v21; // [rsp+80h] [rbp+18h] BYREF

  v4 = a2;
  v20 = 0;
  v21 = 0;
  if ( !a3 )
    return (unsigned int)-2147467261;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( a2 == 1 || a4 )
  {
    memset_0(a3, 0, 8LL * a2);
    v9 = 8 * v4;
    if ( !is_mul_ok(v4, 8u) )
      v9 = -1;
    v10 = (struct IWbemClassObject **)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 8 * v4);
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct IWbemClassObject **, unsigned int *))(**(_QWORD **)(a1 + 64) + 32LL))(
             *(_QWORD *)(a1 + 64),
             0xFFFFFFFFLL,
             (unsigned int)v4,
             v11,
             &v20);
    }
    else
    {
      v8 = -2147024882;
    }
    v12 = v20;
    if ( v20 <= (unsigned int)v4 )
    {
      if ( v8 >= 0 )
      {
        v13 = 0;
        if ( v20 )
        {
          while ( 1 )
          {
            v8 = ATL::CComObject<CHNetAppProtocol>::CreateInstance(&v21);
            if ( v8 < 0 )
              break;
            v14 = v21;
            (*(void (__fastcall **)(CHNetAppProtocol *))(*(_QWORD *)v21 + 8LL))(v21);
            v8 = CHNetAppProtocol::Initialize(v14, *(struct IWbemServices **)(a1 + 72), v11[v13]);
            if ( v8 >= 0 )
              v8 = (**(__int64 (__fastcall ***)(CHNetAppProtocol *, GUID *, __int64))v14)(
                     v14,
                     &GUID_85d18b7f_3032_11d4_9348_00c04f8eeb71,
                     (__int64)a3 + 8 * (int)v13);
            (*(void (__fastcall **)(CHNetAppProtocol *))(*(_QWORD *)v14 + 16LL))(v14);
            if ( v8 < 0 )
              break;
            v12 = v20;
            if ( ++v13 >= v20 )
              goto LABEL_26;
          }
          while ( (--v13 & 0x80000000) == 0 )
          {
            v15 = *((_QWORD *)a3 + v13);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          v12 = v20;
        }
LABEL_26:
        for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
        {
          v17 = v11[i];
          if ( v17 )
          {
            ((void (__fastcall *)(struct IWbemClassObject *))v17->lpVtbl->Release)(v11[i]);
            v12 = v20;
          }
        }
      }
    }
    else
    {
      v8 = -2147418113;
    }
    if ( v11 )
    {
      operator delete[](v11);
      v12 = v20;
    }
    if ( v8 >= 0 )
    {
      if ( a4 )
        *a4 = v12;
      return v12 != v4;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015c40  mov     rax, rsp
0x180015c43  mov     [rax+20h], rbx
0x180015c47  mov     [rax+8], rcx
0x180015c4b  push    rbp
0x180015c4c  push    rsi
0x180015c4d  push    rdi
0x180015c4e  push    r12
0x180015c50  push    r13
0x180015c52  push    r14
0x180015c54  push    r15
0x180015c56  sub     rsp, 30h
0x180015c5a  mov     esi, edx
0x180015c5c  mov     rbp, r9
0x180015c5f  mov     dword ptr [rax+10h], 0
0x180015c66  mov     r12, r8
0x180015c69  mov     qword ptr [rax+18h], 0
0x180015c71  mov     r14, rcx
0x180015c74  test    r8, r8
0x180015c77  jnz     short loc_180015C83
0x180015c79  mov     ebx, 80004003h
0x180015c7e  jmp     loc_180015E25
0x180015c83  test    edx, edx
0x180015c85  jnz     short loc_180015C91
0x180015c87  mov     ebx, 80070057h
0x180015c8c  jmp     loc_180015E25
0x180015c91  cmp     esi, 1
0x180015c94  jz      short loc_180015C9B
0x180015c96  test    rbp, rbp
0x180015c99  jz      short loc_180015C79
0x180015c9b  lea     rdi, ds:0[rsi*8]
0x180015ca3  xor     edx, edx; Val
0x180015ca5  mov     r8, rdi; Size
0x180015ca8  mov     rcx, r12; void *
0x180015cab  call    memset_0
0x180015cb0  mov     eax, 8
0x180015cb5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180015cbc  mul     rsi
0x180015cbf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015cc6  cmovb   rax, rbx
0x180015cca  mov     rcx, rax; unsigned __int64
0x180015ccd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015cd2  mov     r15, rax
0x180015cd5  test    rax, rax
0x180015cd8  jz      short loc_180015D0D
0x180015cda  mov     r8, rdi; Size
0x180015cdd  xor     edx, edx; Val
0x180015cdf  mov     rcx, rax; void *
0x180015ce2  call    memset_0
0x180015ce7  mov     rcx, [r14+40h]
0x180015ceb  lea     r8, [rsp+68h+arg_8]
0x180015cf0  mov     [rsp+68h+var_48], r8
0x180015cf5  mov     r9, r15
0x180015cf8  mov     r8d, esi
0x180015cfb  mov     edx, ebx
0x180015cfd  mov     rax, [rcx]
0x180015d00  mov     rax, [rax+20h]
0x180015d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d09  mov     ebx, eax
0x180015d0b  jmp     short loc_180015D12
0x180015d0d  mov     ebx, 8007000Eh
0x180015d12  mov     ecx, [rsp+68h+arg_8]
0x180015d16  cmp     ecx, esi
0x180015d18  jbe     short loc_180015D24
0x180015d1a  mov     ebx, 8000FFFFh
0x180015d1f  jmp     loc_180015E00
0x180015d24  test    ebx, ebx
0x180015d26  js      loc_180015E00
0x180015d2c  xor     edi, edi
0x180015d2e  test    ecx, ecx
0x180015d30  jz      loc_180015DD8
0x180015d36  lea     rcx, [rsp+68h+arg_10]
0x180015d3e  call    ?CreateInstance@?$CComObject@VCHNetAppProtocol@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetAppProtocol>::CreateInstance(ATL::CComObject<CHNetAppProtocol> * *)
0x180015d43  mov     ebx, eax
0x180015d45  test    eax, eax
0x180015d47  js      short loc_180015DB8
0x180015d49  mov     r14, [rsp+68h+arg_10]
0x180015d51  mov     rcx, r14
0x180015d54  mov     rax, [r14]
0x180015d57  mov     rax, [rax+8]
0x180015d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d60  mov     rax, [rsp+68h+arg_0]
0x180015d65  mov     rcx, r14; this
0x180015d68  movsxd  r13, edi
0x180015d6b  mov     rdx, [rax+48h]; struct IWbemServices *
0x180015d6f  mov     r8, [r15+r13*8]; struct IWbemClassObject *
0x180015d73  call    ?Initialize@CHNetAppProtocol@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CHNetAppProtocol::Initialize(IWbemServices *,IWbemClassObject *)
0x180015d78  mov     ebx, eax
0x180015d7a  test    eax, eax
0x180015d7c  js      short loc_180015D99
0x180015d7e  mov     rax, [r14]
0x180015d81  lea     r8, [r12+r13*8]
0x180015d85  lea     rdx, _GUID_85d18b7f_3032_11d4_9348_00c04f8eeb71
0x180015d8c  mov     rcx, r14
0x180015d8f  mov     rax, [rax]
0x180015d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d97  mov     ebx, eax
0x180015d99  mov     rax, [r14]
0x180015d9c  mov     rcx, r14
0x180015d9f  mov     rax, [rax+10h]
0x180015da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015da8  test    ebx, ebx
0x180015daa  js      short loc_180015DB8
0x180015dac  mov     ecx, [rsp+68h+arg_8]
0x180015db0  inc     edi
0x180015db2  cmp     edi, ecx
0x180015db4  jb      short loc_180015D36
0x180015db6  jmp     short loc_180015DD8
0x180015db8  sub     edi, 1
0x180015dbb  js      short loc_180015DD4
0x180015dbd  mov     rcx, [r12+rdi*8]
0x180015dc1  test    rcx, rcx
0x180015dc4  jz      short loc_180015DB8
0x180015dc6  mov     rax, [rcx]
0x180015dc9  mov     rax, [rax+10h]
0x180015dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dd2  jmp     short loc_180015DB8
0x180015dd4  mov     ecx, [rsp+68h+arg_8]
0x180015dd8  xor     edi, edi
0x180015dda  test    ecx, ecx
0x180015ddc  jz      short loc_180015E00
0x180015dde  mov     rdx, [r15+rdi*8]
0x180015de2  test    rdx, rdx
0x180015de5  jz      short loc_180015DFA
0x180015de7  mov     rax, [rdx]
0x180015dea  mov     rcx, rdx
0x180015ded  mov     rax, [rax+10h]
0x180015df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df6  mov     ecx, [rsp+68h+arg_8]
0x180015dfa  inc     edi
0x180015dfc  cmp     edi, ecx
0x180015dfe  jb      short loc_180015DDE
0x180015e00  test    r15, r15
0x180015e03  jz      short loc_180015E12
0x180015e05  mov     rcx, r15
0x180015e08  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015e0e  mov     ecx, [rsp+68h+arg_8]
0x180015e12  test    ebx, ebx
0x180015e14  js      short loc_180015E25
0x180015e16  test    rbp, rbp
0x180015e19  jz      short loc_180015E1E
0x180015e1b  mov     [rbp+0], ecx
0x180015e1e  xor     ebx, ebx
0x180015e20  cmp     ecx, esi
0x180015e22  setnz   bl
0x180015e25  mov     eax, ebx
0x180015e27  mov     rbx, [rsp+68h+arg_18]
0x180015e2f  add     rsp, 30h
0x180015e33  pop     r15
0x180015e35  pop     r14
0x180015e37  pop     r13
0x180015e39  pop     r12
0x180015e3b  pop     rdi
0x180015e3c  pop     rsi
0x180015e3d  pop     rbp
0x180015e3e  retn
```
