# CHNCEnum<IEnumHNetPortMappingProtocols,IHNetPortMappingProtocol,CHNetPortMappingProtocol>::Next(ulong,IHNetPortMappingProtocol * *,ulong *)

- ea: `0x1800168a0`
- end: `0x180016a9f`
- name: `?Next@?$CHNCEnum@UIEnumHNetPortMappingProtocols@@UIHNetPortMappingProtocol@@VCHNetPortMappingProtocol@@@@UEAAJKPEAPEAUIHNetPortMappingProtocol@@PEAK@Z`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001ec4`
- `0x180010218`
- `0x1800168a0`
- `0x180023db8`
- `0x18002d1d2`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180016a68`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180016a68`

## pseudocode

```c
__int64 __fastcall CHNCEnum<IEnumHNetPortMappingProtocols,IHNetPortMappingProtocol,CHNetPortMappingProtocol>::Next(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rsi
  int Instance; // ebx
  unsigned __int64 v9; // rax
  struct IWbemClassObject **v10; // rax
  struct IWbemClassObject **v11; // r15
  unsigned int v12; // ecx
  unsigned int v13; // edi
  CHNetPortMappingProtocol *v14; // r14
  __int64 v15; // rcx
  __int64 i; // rdi
  struct IWbemClassObject *v17; // rdx
  unsigned int v20; // [rsp+78h] [rbp+10h] BYREF
  CHNetPortMappingProtocol *v21; // [rsp+80h] [rbp+18h] BYREF

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
      Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct IWbemClassObject **, unsigned int *))(**(_QWORD **)(a1 + 64) + 32LL))(
                   *(_QWORD *)(a1 + 64),
                   0xFFFFFFFFLL,
                   (unsigned int)v4,
                   v11,
                   &v20);
    }
    else
    {
      Instance = -2147024882;
    }
    v12 = v20;
    if ( v20 <= (unsigned int)v4 )
    {
      if ( Instance >= 0 )
      {
        v13 = 0;
        if ( v20 )
        {
          while ( 1 )
          {
            Instance = ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance((volatile int **)&v21);
            if ( Instance < 0 )
              break;
            v14 = v21;
            (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v21 + 8LL))(v21);
            Instance = CHNetPortMappingProtocol::Initialize(v14, *(struct IWbemServices **)(a1 + 72), v11[v13]);
            if ( Instance >= 0 )
              Instance = (**(__int64 (__fastcall ***)(CHNetPortMappingProtocol *, GUID *, __int64))v14)(
                           v14,
                           &GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71,
                           (__int64)a3 + 8 * (int)v13);
            (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v14 + 16LL))(v14);
            if ( Instance < 0 )
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
      Instance = -2147418113;
    }
    if ( v11 )
    {
      operator delete[](v11);
      v12 = v20;
    }
    if ( Instance >= 0 )
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
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800168a0  mov     rax, rsp
0x1800168a3  mov     [rax+20h], rbx
0x1800168a7  mov     [rax+8], rcx
0x1800168ab  push    rbp
0x1800168ac  push    rsi
0x1800168ad  push    rdi
0x1800168ae  push    r12
0x1800168b0  push    r13
0x1800168b2  push    r14
0x1800168b4  push    r15
0x1800168b6  sub     rsp, 30h
0x1800168ba  mov     esi, edx
0x1800168bc  mov     rbp, r9
0x1800168bf  mov     dword ptr [rax+10h], 0
0x1800168c6  mov     r12, r8
0x1800168c9  mov     qword ptr [rax+18h], 0
0x1800168d1  mov     r14, rcx
0x1800168d4  test    r8, r8
0x1800168d7  jnz     short loc_1800168E3
0x1800168d9  mov     ebx, 80004003h
0x1800168de  jmp     loc_180016A85
0x1800168e3  test    edx, edx
0x1800168e5  jnz     short loc_1800168F1
0x1800168e7  mov     ebx, 80070057h
0x1800168ec  jmp     loc_180016A85
0x1800168f1  cmp     esi, 1
0x1800168f4  jz      short loc_1800168FB
0x1800168f6  test    rbp, rbp
0x1800168f9  jz      short loc_1800168D9
0x1800168fb  lea     rdi, ds:0[rsi*8]
0x180016903  xor     edx, edx; Val
0x180016905  mov     r8, rdi; Size
0x180016908  mov     rcx, r12; void *
0x18001690b  call    memset_0
0x180016910  mov     eax, 8
0x180016915  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001691c  mul     rsi
0x18001691f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016926  cmovb   rax, rbx
0x18001692a  mov     rcx, rax; unsigned __int64
0x18001692d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016932  mov     r15, rax
0x180016935  test    rax, rax
0x180016938  jz      short loc_18001696D
0x18001693a  mov     r8, rdi; Size
0x18001693d  xor     edx, edx; Val
0x18001693f  mov     rcx, rax; void *
0x180016942  call    memset_0
0x180016947  mov     rcx, [r14+40h]
0x18001694b  lea     r8, [rsp+68h+arg_8]
0x180016950  mov     [rsp+68h+var_48], r8
0x180016955  mov     r9, r15
0x180016958  mov     r8d, esi
0x18001695b  mov     edx, ebx
0x18001695d  mov     rax, [rcx]
0x180016960  mov     rax, [rax+20h]
0x180016964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016969  mov     ebx, eax
0x18001696b  jmp     short loc_180016972
0x18001696d  mov     ebx, 8007000Eh
0x180016972  mov     ecx, [rsp+68h+arg_8]
0x180016976  cmp     ecx, esi
0x180016978  jbe     short loc_180016984
0x18001697a  mov     ebx, 8000FFFFh
0x18001697f  jmp     loc_180016A60
0x180016984  test    ebx, ebx
0x180016986  js      loc_180016A60
0x18001698c  xor     edi, edi
0x18001698e  test    ecx, ecx
0x180016990  jz      loc_180016A38
0x180016996  lea     rcx, [rsp+68h+arg_10]
0x18001699e  call    ?CreateInstance@?$CComObject@VCHNetPortMappingProtocol@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance(ATL::CComObject<CHNetPortMappingProtocol> * *)
0x1800169a3  mov     ebx, eax
0x1800169a5  test    eax, eax
0x1800169a7  js      short loc_180016A18
0x1800169a9  mov     r14, [rsp+68h+arg_10]
0x1800169b1  mov     rcx, r14
0x1800169b4  mov     rax, [r14]
0x1800169b7  mov     rax, [rax+8]
0x1800169bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169c0  mov     rax, [rsp+68h+arg_0]
0x1800169c5  mov     rcx, r14; this
0x1800169c8  movsxd  r13, edi
0x1800169cb  mov     rdx, [rax+48h]; struct IWbemServices *
0x1800169cf  mov     r8, [r15+r13*8]; struct IWbemClassObject *
0x1800169d3  call    ?Initialize@CHNetPortMappingProtocol@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CHNetPortMappingProtocol::Initialize(IWbemServices *,IWbemClassObject *)
0x1800169d8  mov     ebx, eax
0x1800169da  test    eax, eax
0x1800169dc  js      short loc_1800169F9
0x1800169de  mov     rax, [r14]
0x1800169e1  lea     r8, [r12+r13*8]
0x1800169e5  lea     rdx, _GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71
0x1800169ec  mov     rcx, r14
0x1800169ef  mov     rax, [rax]
0x1800169f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f7  mov     ebx, eax
0x1800169f9  mov     rax, [r14]
0x1800169fc  mov     rcx, r14
0x1800169ff  mov     rax, [rax+10h]
0x180016a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a08  test    ebx, ebx
0x180016a0a  js      short loc_180016A18
0x180016a0c  mov     ecx, [rsp+68h+arg_8]
0x180016a10  inc     edi
0x180016a12  cmp     edi, ecx
0x180016a14  jb      short loc_180016996
0x180016a16  jmp     short loc_180016A38
0x180016a18  sub     edi, 1
0x180016a1b  js      short loc_180016A34
0x180016a1d  mov     rcx, [r12+rdi*8]
0x180016a21  test    rcx, rcx
0x180016a24  jz      short loc_180016A18
0x180016a26  mov     rax, [rcx]
0x180016a29  mov     rax, [rax+10h]
0x180016a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a32  jmp     short loc_180016A18
0x180016a34  mov     ecx, [rsp+68h+arg_8]
0x180016a38  xor     edi, edi
0x180016a3a  test    ecx, ecx
0x180016a3c  jz      short loc_180016A60
0x180016a3e  mov     rdx, [r15+rdi*8]
0x180016a42  test    rdx, rdx
0x180016a45  jz      short loc_180016A5A
0x180016a47  mov     rax, [rdx]
0x180016a4a  mov     rcx, rdx
0x180016a4d  mov     rax, [rax+10h]
0x180016a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a56  mov     ecx, [rsp+68h+arg_8]
0x180016a5a  inc     edi
0x180016a5c  cmp     edi, ecx
0x180016a5e  jb      short loc_180016A3E
0x180016a60  test    r15, r15
0x180016a63  jz      short loc_180016A72
0x180016a65  mov     rcx, r15
0x180016a68  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016a6e  mov     ecx, [rsp+68h+arg_8]
0x180016a72  test    ebx, ebx
0x180016a74  js      short loc_180016A85
0x180016a76  test    rbp, rbp
0x180016a79  jz      short loc_180016A7E
0x180016a7b  mov     [rbp+0], ecx
0x180016a7e  xor     ebx, ebx
0x180016a80  cmp     ecx, esi
0x180016a82  setnz   bl
0x180016a85  mov     eax, ebx
0x180016a87  mov     rbx, [rsp+68h+arg_18]
0x180016a8f  add     rsp, 30h
0x180016a93  pop     r15
0x180016a95  pop     r14
0x180016a97  pop     r13
0x180016a99  pop     r12
0x180016a9b  pop     rdi
0x180016a9c  pop     rsi
0x180016a9d  pop     rbp
0x180016a9e  retn
```
