# _PnpOpenPropertiesKey

- ea: `0x1800037f0`
- end: `0x180003be7`
- name: `_PnpOpenPropertiesKey`
- size: `1015`
- prototype: ``
- caller_count: `13`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001ab0`
- `0x180001f50`
- `0x180002a80`
- `0x180003210`
- `0x1800035b0`
- `0x18006ce0c`
- `0x18006eb80`
- `0x180071a84`
- `0x180071c04`
- `0x180076a1c`
- `0x180077590`
- `0x180079020`
- `0x180079478`

## callees

- `0x180001d20`
- `0x1800037f0`
- `0x180003bf0`
- `0x180003f50`
- `0x1800045b0`
- `0x18003bc80`
- `0x1800656b0`
- `0x180065ccc`

## import_xrefs

- `ntdll!NtClose` at `0x180003bdc`
- `ntdll!NtClose` at `0x180003bdc`
- `ntdll!RtlValidSecurityDescriptor` at `0x180003b0f`
- `ntdll!RtlValidSecurityDescriptor` at `0x180003b0f`
- `ntdll!RtlFreeHeap` at `0x180003a11`
- `ntdll!RtlFreeHeap` at `0x180003bce`
- `ntdll!RtlFreeHeap` at `0x180003a11`
- `ntdll!RtlFreeHeap` at `0x180003bce`
- `ntdll!RtlAllocateHeap` at `0x180003a50`
- `ntdll!RtlAllocateHeap` at `0x180003a50`

## pseudocode

```c
__int64 __fastcall PnpOpenPropertiesKey(__int64 a1, char *a2, _WORD *a3, ACCESS_MASK a4, char a5, int a6, void **a7)
{
  WCHAR *Heap; // rbx
  void *v8; // rsi
  int v9; // edi
  _WORD *v13; // rax
  __int64 v14; // rcx
  int v15; // edx
  int v16; // edi
  __int64 *v17; // rsi
  __int64 v18; // rax
  int v19; // eax
  char v21; // r14
  void *v22; // rbp
  __int64 v23; // rax
  char *v24; // rsi
  char *v25; // rcx
  int Key; // eax
  void **v27; // r14
  void *PropertiesSecurityDescriptor; // rax
  void *v29; // rdx
  int Tree; // eax
  void **v31; // [rsp+20h] [rbp-118h]
  __int64 v32; // [rsp+28h] [rbp-110h]
  unsigned int v33; // [rsp+40h] [rbp-F8h]
  _BYTE P[128]; // [rsp+60h] [rbp-D8h] BYREF

  Heap = 0;
  v8 = 0;
  v33 = a4;
  v9 = 0;
  *a7 = 0;
  if ( a3 )
  {
    v13 = a3;
    v14 = 512;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v14;
    }
    while ( v14 );
    if ( !v14 )
      return 3221225485LL;
    v15 = 512 - v14;
    if ( (unsigned __int64)(512 - v14) >= 0x30 )
    {
      v16 = v15 + 12;
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v15 + 12));
      if ( !Heap )
        return 3221225495LL;
    }
    else
    {
      Heap = (WCHAR *)P;
      v16 = 59;
    }
    v9 = RtlStringCchPrintfExW((int)Heap, v16, 0, 0, 2048, (__int64)L"%s\\%s", (char)L"Properties");
    if ( v9 < 0 )
      goto LABEL_16;
    if ( a1 && (v17 = (__int64 *)(a1 + 224), (v18 = *(_QWORD *)(a1 + 224)) != 0) )
    {
      if ( *(_BYTE *)(v18 + 16) )
        v19 = RegRtlOpenProtectedKeyTransacted((__int64)a2, (__int64)Heap, 0, v33, (__int64)a7);
      else
        v19 = RegRtlOpenKeyTransacted(a2, Heap, 0, v33, a7, *(_QWORD *)(v18 + 8));
    }
    else
    {
      v19 = RegRtlOpenKeyTransacted(a2, Heap, 0, v33, a7, 0);
      v17 = (__int64 *)(a1 + 224);
    }
    if ( v19 == -1073741444 )
    {
      v8 = 0;
      v9 = -1073741772;
      goto LABEL_16;
    }
    if ( v19 != -1073741772 || (v21 = a5) == 0 )
    {
      v8 = 0;
      v9 = v19;
      goto LABEL_16;
    }
    a4 = v33;
  }
  else
  {
    v21 = a5;
    v17 = (__int64 *)(a1 + 224);
  }
  v22 = 0;
  if ( !a1 || (v23 = *v17) == 0 )
  {
    v24 = a2;
    v32 = 0;
    v25 = a2;
    v31 = a7;
    goto LABEL_45;
  }
  v24 = a2;
  v32 = *(_QWORD *)(v23 + 8);
  v25 = a2;
  v31 = a7;
  if ( !*(_BYTE *)(v23 + 16) )
  {
LABEL_45:
    Key = RegRtlOpenKeyTransacted(v25, (const WCHAR *)L"Properties", 0, a4, v31, v32);
    goto LABEL_28;
  }
  Key = RegRtlOpenProtectedKeyTransacted((__int64)a2, (__int64)L"Properties", 0, a4, (__int64)a7);
LABEL_28:
  if ( Key != -1073741772 )
  {
    v27 = a7;
LABEL_30:
    if ( Key == -1073741444 )
    {
      v9 = -1073741772;
      goto LABEL_33;
    }
    if ( Key >= 0 )
    {
      if ( a3 )
      {
        v8 = *v27;
        v29 = *v27;
        *v27 = 0;
        Tree = PnpCtxRegCreateTree(a1, (_DWORD)v29, (_DWORD)a3, 0, v33, 0, v27, 0);
        if ( Tree == -1073741444 )
        {
          v9 = -1073741772;
        }
        else if ( Tree < 0 )
        {
          v9 = Tree;
        }
LABEL_34:
        if ( !v22 )
          goto LABEL_16;
        goto LABEL_35;
      }
LABEL_33:
      v8 = 0;
      goto LABEL_34;
    }
LABEL_52:
    v9 = Key;
    goto LABEL_33;
  }
  if ( !v21 )
    goto LABEL_52;
  PropertiesSecurityDescriptor = PnpGetPropertiesSecurityDescriptor();
  v22 = PropertiesSecurityDescriptor;
  if ( PropertiesSecurityDescriptor )
  {
    if ( !RtlValidSecurityDescriptor(PropertiesSecurityDescriptor) )
    {
      v8 = 0;
      v9 = -1073741595;
LABEL_35:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      goto LABEL_16;
    }
    v27 = a7;
    Key = PnpCtxRegCreateKey(a1, v24, L"Properties");
    goto LABEL_30;
  }
  v8 = 0;
  v9 = -1073741595;
LABEL_16:
  if ( Heap && Heap != (WCHAR *)P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v8 )
    NtClose(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800037f0  push    rbx
0x1800037f2  push    rbp
0x1800037f3  push    rsi
0x1800037f4  push    rdi
0x1800037f5  push    r12
0x1800037f7  push    r13
0x1800037f9  push    r14
0x1800037fb  push    r15
0x1800037fd  sub     rsp, 0F8h
0x180003804  mov     rax, cs:__security_cookie
0x18000380b  xor     rax, rsp
0x18000380e  mov     [rsp+138h+var_58], rax
0x180003816  mov     r14, [rsp+138h+arg_30]
0x18000381e  xor     ebx, ebx
0x180003820  xor     esi, esi
0x180003822  mov     [rsp+138h+var_F8], r9d
0x180003827  xor     edi, edi
0x180003829  mov     [rsp+138h+var_E0], rdx
0x18000382e  mov     [rsp+138h+var_E8], r14
0x180003833  mov     r12, r8
0x180003836  mov     [r14], rbx
0x180003839  mov     rbp, rdx
0x18000383c  mov     [rsp+138h+var_F0], rsi
0x180003841  mov     r13, rcx
0x180003844  test    r8, r8
0x180003847  jz      loc_180003AA8
0x18000384d  mov     edx, 200h
0x180003852  mov     rax, r8
0x180003855  mov     ecx, edx
0x180003857  cmp     [rax], bx
0x18000385a  jz      short loc_180003866
0x18000385c  add     rax, 2
0x180003860  sub     rcx, 1
0x180003864  jnz     short loc_180003857
0x180003866  xor     eax, eax
0x180003868  mov     r8d, 0C000000Dh
0x18000386e  test    rcx, rcx
0x180003871  cmovnz  r8d, eax
0x180003875  jz      loc_180003A2D
0x18000387b  sub     rdx, rcx
0x18000387e  cmp     rdx, 30h ; '0'
0x180003882  jnb     loc_180003A35
0x180003888  lea     rbx, [rsp+138h+P]
0x18000388d  mov     edi, 3Bh ; ';'
0x180003892  mov     [rsp+138h+var_100], r12
0x180003897  lea     rax, aSS; "%s\\%s"
0x18000389e  lea     r15, Args; "Properties"
0x1800038a5  mov     edx, edi; int
0x1800038a7  mov     qword ptr [rsp+138h+Args], r15; Args
0x1800038ac  xor     r9d, r9d; int
0x1800038af  mov     [rsp+138h+var_110], rax; __int64
0x1800038b4  xor     r8d, r8d; int
0x1800038b7  mov     rcx, rbx; int
0x1800038ba  mov     [rsp+138h+var_118], 800h; int
0x1800038c2  call    RtlStringCchPrintfExW
0x1800038c7  mov     edi, eax
0x1800038c9  test    eax, eax
0x1800038cb  js      short loc_18000392D
0x1800038cd  test    r13, r13
0x1800038d0  jz      loc_180003A6C
0x1800038d6  lea     rsi, [r13+0E0h]
0x1800038dd  mov     rax, [rsi]
0x1800038e0  test    rax, rax
0x1800038e3  jz      loc_180003A6C
0x1800038e9  mov     rcx, [rax+8]
0x1800038ed  xor     r8d, r8d
0x1800038f0  mov     rdx, rbx
0x1800038f3  mov     r9d, [rsp+138h+var_F8]
0x1800038f8  mov     [rsp+138h+var_110], rcx
0x1800038fd  mov     rcx, rbp
0x180003900  mov     qword ptr [rsp+138h+var_118], r14
0x180003905  cmp     [rax+10h], r8b
0x180003909  jz      loc_180003A1C
0x18000390f  call    _RegRtlOpenProtectedKeyTransacted
0x180003914  cmp     eax, 0C000017Ch
0x180003919  jz      loc_180003A99
0x18000391f  cmp     eax, 0C0000034h
0x180003924  jz      short loc_18000396F
0x180003926  mov     rsi, [rsp+138h+var_F0]
0x18000392b  mov     edi, eax
0x18000392d  test    rbx, rbx
0x180003930  jz      short loc_180003940
0x180003932  lea     rax, [rsp+138h+P]
0x180003937  cmp     rbx, rax
0x18000393a  jnz     loc_180003BBC
0x180003940  test    rsi, rsi
0x180003943  jnz     loc_180003BD9
0x180003949  mov     eax, edi
0x18000394b  mov     rcx, [rsp+138h+var_58]
0x180003953  xor     rcx, rsp; StackCookie
0x180003956  call    __security_check_cookie
0x18000395b  add     rsp, 0F8h
0x180003962  pop     r15
0x180003964  pop     r14
0x180003966  pop     r13
0x180003968  pop     r12
0x18000396a  pop     rdi
0x18000396b  pop     rsi
0x18000396c  pop     rbp
0x18000396d  pop     rbx
0x18000396e  retn
0x18000396f  movzx   r14d, [rsp+138h+arg_20]
0x180003978  test    r14b, r14b
0x18000397b  jz      short loc_180003926
0x18000397d  mov     r9d, [rsp+138h+var_F8]
0x180003982  xor     ebp, ebp
0x180003984  test    r13, r13
0x180003987  jz      loc_180003AC4
0x18000398d  mov     rax, [rsi]
0x180003990  test    rax, rax
0x180003993  jz      loc_180003AC4
0x180003999  mov     rcx, [rax+8]
0x18000399d  xor     r8d, r8d
0x1800039a0  cmp     [rax+10h], bpl
0x1800039a4  mov     rdx, r15
0x1800039a7  mov     rax, [rsp+138h+var_E8]
0x1800039ac  mov     rsi, [rsp+138h+var_E0]
0x1800039b1  mov     [rsp+138h+var_110], rcx
0x1800039b6  mov     rcx, rsi
0x1800039b9  mov     qword ptr [rsp+138h+var_118], rax
0x1800039be  jz      loc_180003AE1
0x1800039c4  call    _RegRtlOpenProtectedKeyTransacted
0x1800039c9  cmp     eax, 0C0000034h
0x1800039ce  jz      loc_180003AEB
0x1800039d4  mov     r14, [rsp+138h+var_E8]
0x1800039d9  cmp     eax, 0C000017Ch
0x1800039de  jz      short loc_180003A26
0x1800039e0  test    eax, eax
0x1800039e2  js      loc_180003B5B
0x1800039e8  test    r12, r12
0x1800039eb  jnz     loc_180003B62
0x1800039f1  mov     rsi, [rsp+138h+var_F0]
0x1800039f6  test    rbp, rbp
0x1800039f9  jz      loc_18000392D
0x1800039ff  mov     rcx, gs:60h
0x180003a08  mov     r8, rbp; P
0x180003a0b  xor     edx, edx; Flags
0x180003a0d  mov     rcx, [rcx+30h]; HeapHandle
0x180003a11  call    cs:__imp_RtlFreeHeap
0x180003a17  jmp     loc_18000392D
0x180003a1c  call    _RegRtlOpenKeyTransacted
0x180003a21  jmp     loc_180003914
0x180003a26  mov     edi, 0C0000034h
0x180003a2b  jmp     short loc_1800039F1
0x180003a2d  mov     eax, r8d
0x180003a30  jmp     loc_18000394B
0x180003a35  mov     rcx, gs:60h
0x180003a3e  lea     edi, [rdx+0Ch]
0x180003a41  mov     r8d, edi
0x180003a44  mov     edx, 8; Flags
0x180003a49  add     r8, r8; Size
0x180003a4c  mov     rcx, [rcx+30h]; HeapHandle
0x180003a50  call    cs:__imp_RtlAllocateHeap
0x180003a56  mov     rbx, rax
0x180003a59  test    rax, rax
0x180003a5c  jnz     loc_180003892
0x180003a62  mov     eax, 0C0000017h
0x180003a67  jmp     loc_18000394B
0x180003a6c  mov     r9d, [rsp+138h+var_F8]
0x180003a71  xor     r8d, r8d
0x180003a74  mov     [rsp+138h+var_110], 0
0x180003a7d  mov     rdx, rbx
0x180003a80  mov     rcx, rbp
0x180003a83  mov     qword ptr [rsp+138h+var_118], r14
0x180003a88  call    _RegRtlOpenKeyTransacted
0x180003a8d  lea     rsi, [r13+0E0h]
0x180003a94  jmp     loc_180003914
0x180003a99  mov     rsi, [rsp+138h+var_F0]
0x180003a9e  mov     edi, 0C0000034h
0x180003aa3  jmp     loc_18000392D
0x180003aa8  movzx   r14d, [rsp+138h+arg_20]
0x180003ab1  lea     rsi, [rcx+0E0h]
0x180003ab8  lea     r15, Args; "Properties"
0x180003abf  jmp     loc_180003982
0x180003ac4  mov     rax, [rsp+138h+var_E8]
0x180003ac9  xor     r8d, r8d
0x180003acc  mov     rsi, [rsp+138h+var_E0]
0x180003ad1  mov     rdx, r15
0x180003ad4  mov     [rsp+138h+var_110], rbp
0x180003ad9  mov     rcx, rsi
0x180003adc  mov     qword ptr [rsp+138h+var_118], rax
0x180003ae1  call    _RegRtlOpenKeyTransacted
0x180003ae6  jmp     loc_1800039C9
0x180003aeb  test    r14b, r14b
0x180003aee  jz      short loc_180003B5B
0x180003af0  call    _PnpGetPropertiesSecurityDescriptor
0x180003af5  mov     rbp, rax
0x180003af8  test    rax, rax
0x180003afb  jnz     short loc_180003B0C
0x180003afd  mov     rsi, [rsp+138h+var_F0]
0x180003b02  mov     edi, 0C00000E5h
0x180003b07  jmp     loc_18000392D
0x180003b0c  mov     rcx, rbp; SecurityDescriptor
0x180003b0f  call    cs:__imp_RtlValidSecurityDescriptor
0x180003b15  test    al, al
0x180003b17  jnz     short loc_180003B28
0x180003b19  mov     rsi, [rsp+138h+var_F0]
0x180003b1e  mov     edi, 0C00000E5h
0x180003b23  jmp     loc_1800039FF
0x180003b28  mov     eax, [rsp+138h+var_F8]
0x180003b2c  mov     r8, r15
0x180003b2f  mov     r14, [rsp+138h+var_E8]
0x180003b34  mov     rdx, rsi
0x180003b37  mov     [rsp+138h+var_100], 0
0x180003b40  mov     rcx, r13
0x180003b43  mov     qword ptr [rsp+138h+Args], r14
0x180003b48  mov     [rsp+138h+var_110], rbp
0x180003b4d  mov     [rsp+138h+var_118], eax
0x180003b51  call    _PnpCtxRegCreateKey
0x180003b56  jmp     loc_1800039D9
0x180003b5b  mov     edi, eax
0x180003b5d  jmp     loc_1800039F1
0x180003b62  mov     rsi, [r14]
0x180003b65  xor     r9d, r9d
0x180003b68  mov     eax, [rsp+138h+var_F8]
0x180003b6c  mov     rdx, rsi
0x180003b6f  mov     [rsp+138h+var_100], 0
0x180003b78  mov     r8, r12
0x180003b7b  mov     qword ptr [rsp+138h+Args], r14
0x180003b80  mov     rcx, r13
0x180003b83  mov     [rsp+138h+var_110], 0
0x180003b8c  mov     [rsp+138h+var_118], eax
0x180003b90  mov     qword ptr [r14], 0
0x180003b97  call    _PnpCtxRegCreateTree
0x180003b9c  cmp     eax, 0C000017Ch
0x180003ba1  jnz     short loc_180003BAD
0x180003ba3  mov     edi, 0C0000034h
0x180003ba8  jmp     loc_1800039F6
0x180003bad  test    eax, eax
0x180003baf  jns     loc_1800039F6
0x180003bb5  mov     edi, eax
0x180003bb7  jmp     loc_1800039F6
0x180003bbc  mov     rcx, gs:60h
0x180003bc5  mov     r8, rbx; P
0x180003bc8  xor     edx, edx; Flags
0x180003bca  mov     rcx, [rcx+30h]; HeapHandle
0x180003bce  call    cs:__imp_RtlFreeHeap
0x180003bd4  jmp     loc_180003940
0x180003bd9  mov     rcx, rsi; Handle
0x180003bdc  call    cs:__imp_NtClose
0x180003be2  jmp     loc_180003949
```
