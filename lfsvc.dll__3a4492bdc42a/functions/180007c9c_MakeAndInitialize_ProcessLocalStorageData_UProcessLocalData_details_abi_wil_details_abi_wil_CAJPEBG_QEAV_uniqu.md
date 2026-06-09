# ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z

- ea: `0x180007c9c`
- end: `0x180007de7`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z`
- size: `331`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006308`

## callees

- `0x180004d48`
- `0x180006090`
- `0x180006698`
- `0x180006b7c`
- `0x180007c9c`
- `0x18000816c`
- `0x180008b68`
- `0x180009e10`

## string_xrefs

- `0x180007d43`: `semaphoreValue.CreateFromPointer(name, dataAlloc.get())`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
        unsigned __int16 *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rax
  wil::details::in1diag5 *v7; // rcx
  size_t *v8; // r8
  _QWORD *v9; // rbx
  int v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // edi
  void *v14; // rdx
  void *v15; // rdx
  __int64 v16; // rax
  void *v17; // rdx
  wil::details *v18; // [rsp+28h] [rbp-30h]
  int v19[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  v6 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, (unsigned __int64)a3);
  v9 = (_QWORD *)v6;
  if ( v6 )
  {
    *(_OWORD *)v19 = 0;
    if ( (v6 & 3) != 0 )
      wil::details::in1diag5::_FailFastImmediate_Unexpected(v7);
    v11 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v19,
            a1,
            v8,
            v6 >> 2);
    v13 = v11;
    if ( v11 >= 0 )
    {
      *(_DWORD *)v9 = 1;
      v9[1] = *a2;
      v16 = *(_QWORD *)v19;
      *a2 = 0;
      v9[2] = v16;
      v9[3] = *(_QWORD *)&v19[2];
      memset(v19, 0, sizeof(v19));
      memset_0((char *)v9 + 34, 0, 0x56u);
      *((_WORD *)v9 + 16) = 88;
      *((_DWORD *)v9 + 9) = 1;
      memset_0(v9 + 5, 0, 0x50u);
      *a3 = v9;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details **)v19, v17);
      return 0;
    }
    else
    {
      LODWORD(v18) = v11;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x14E,
        v12,
        "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
        "semaphoreValue.CreateFromPointer(name, dataAlloc.get())",
        v18,
        v19[0]);
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details **)v19, v14);
      wil::details::FreeProcessHeap((wil::details *)v9, v15);
      return v13;
    }
  }
  else
  {
    LODWORD(v18) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)v8,
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      "dataAlloc",
      v18,
      v19[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180007c9c  mov     [rsp+arg_18], rbx
0x180007ca1  push    rsi
0x180007ca2  push    rdi
0x180007ca3  push    r14
0x180007ca5  sub     rsp, 40h
0x180007ca9  mov     r14, rdx
0x180007cac  mov     qword ptr [r8], 0
0x180007cb3  mov     edx, 78h ; 'x'; dwBytes
0x180007cb8  mov     rdi, rcx
0x180007cbb  mov     rsi, r8
0x180007cbe  lea     ecx, [rdx-70h]; dwFlags
0x180007cc1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007cc6  mov     rbx, rax
0x180007cc9  test    rax, rax
0x180007ccc  jnz     short loc_180007D00
0x180007cce  mov     rcx, [rsp+58h]; this
0x180007cd3  lea     rdx, aDataalloc; "dataAlloc"
0x180007cda  mov     ebx, 8007000Eh
0x180007cdf  lea     r9, aWilDetailsAbiP_1; "wil::details_abi::ProcessLocalStorageDa"...
0x180007ce6  mov     dword ptr [rsp+58h+var_30], ebx; wil::details *
0x180007cea  mov     [rsp+58h+var_38], rdx; char *
0x180007cef  mov     edx, 14Bh; void *
0x180007cf4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180007cf9  mov     eax, ebx
0x180007cfb  jmp     loc_180007DD9
0x180007d00  xorps   xmm0, xmm0
0x180007d03  movdqu  xmmword ptr [rsp+58h+var_28], xmm0; int
0x180007d09  test    bl, 3
0x180007d0c  jz      short loc_180007D14
0x180007d0e  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
0x180007d14  mov     r9, rbx
0x180007d17  lea     rcx, [rsp+58h+var_28]; this
0x180007d1c  shr     r9, 2; unsigned __int64
0x180007d20  mov     rdx, rdi; unsigned __int16 *
0x180007d23  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007d28  mov     edi, eax
0x180007d2a  test    eax, eax
0x180007d2c  jns     short loc_180007D6A
0x180007d2e  mov     rcx, [rsp+58h]; this
0x180007d33  lea     r9, aWilDetailsAbiP_1; "wil::details_abi::ProcessLocalStorageDa"...
0x180007d3a  mov     dword ptr [rsp+58h+var_30], eax; wil::details *
0x180007d3e  mov     edx, 14Eh; void *
0x180007d43  lea     rax, aSemaphorevalue; "semaphoreValue.CreateFromPointer(name, "...
0x180007d4a  mov     [rsp+58h+var_38], rax; char *
0x180007d4f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180007d54  lea     rcx, [rsp+58h+var_28]; this
0x180007d59  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007d5e  mov     rcx, rbx; this
0x180007d61  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007d66  mov     eax, edi
0x180007d68  jmp     short loc_180007DD9
0x180007d6a  mov     edi, 1
0x180007d6f  lea     rcx, [rbx+22h]; void *
0x180007d73  mov     [rbx], edi
0x180007d75  xor     edx, edx; Val
0x180007d77  mov     rax, [r14]
0x180007d7a  mov     [rbx+8], rax
0x180007d7e  mov     rax, qword ptr [rsp+58h+var_28]
0x180007d83  lea     r8d, [rdi+55h]; Size
0x180007d87  mov     qword ptr [r14], 0
0x180007d8e  mov     [rbx+10h], rax
0x180007d92  mov     rax, qword ptr [rsp+58h+var_28+8]
0x180007d97  mov     [rbx+18h], rax
0x180007d9b  mov     qword ptr [rsp+58h+var_28], 0
0x180007da4  mov     qword ptr [rsp+58h+var_28+8], 0
0x180007dad  call    memset_0
0x180007db2  mov     word ptr [rbx+20h], 58h ; 'X'
0x180007db8  lea     rcx, [rbx+28h]; void *
0x180007dbc  xor     edx, edx; Val
0x180007dbe  mov     [rbx+24h], edi
0x180007dc1  lea     r8d, [rdi+4Fh]; Size
0x180007dc5  call    memset_0
0x180007dca  lea     rcx, [rsp+58h+var_28]; this
0x180007dcf  mov     [rsi], rbx
0x180007dd2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007dd7  xor     eax, eax
0x180007dd9  mov     rbx, [rsp+58h+arg_18]
0x180007dde  add     rsp, 40h
0x180007de2  pop     r14
0x180007de4  pop     rdi
0x180007de5  pop     rsi
0x180007de6  retn
```
