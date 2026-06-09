# ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z

- ea: `0x180007df0`
- end: `0x180007f41`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z`
- size: `337`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180006498`

## callees

- `0x180002ecc`
- `0x180004d48`
- `0x180005cf8`
- `0x180006090`
- `0x180006698`
- `0x180006b7c`
- `0x180007df0`
- `0x18000816c`
- `0x180008b68`
- `0x180009e10`

## string_xrefs

- `0x180007e99`: `semaphoreValue.CreateFromPointer(name, dataAlloc.get())`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
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
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  void *v20; // rdx
  wil::details *v21; // [rsp+28h] [rbp-30h]
  int v22[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  v6 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, (unsigned __int64)a3);
  v9 = (_QWORD *)v6;
  if ( v6 )
  {
    *(_OWORD *)v22 = 0;
    if ( (v6 & 3) != 0 )
      wil::details::in1diag5::_FailFastImmediate_Unexpected(v7);
    v11 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v22,
            a1,
            v8,
            v6 >> 2);
    v13 = v11;
    if ( v11 >= 0 )
    {
      *(_DWORD *)v9 = 1;
      v9[1] = *a2;
      v16 = *(_QWORD *)v22;
      *a2 = 0;
      v9[2] = v16;
      v9[3] = *(_QWORD *)&v22[2];
      memset(v22, 0, sizeof(v22));
      memset_0(v9 + 5, 0, 0x108u);
      v9[4] = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v9 + 5), v17, v18, v19);
      wil::details_abi::SubscriptionList::SubscriptionList((wil::details_abi::SubscriptionList *)(v9 + 29));
      *a3 = v9;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details **)v22, v20);
      return 0;
    }
    else
    {
      LODWORD(v21) = v11;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x14E,
        v12,
        "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::MakeAndInitialize",
        "semaphoreValue.CreateFromPointer(name, dataAlloc.get())",
        v21,
        v22[0]);
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details **)v22, v14);
      wil::details::FreeProcessHeap((wil::details *)v9, v15);
      return v13;
    }
  }
  else
  {
    LODWORD(v21) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)v8,
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::MakeAndInitialize",
      "dataAlloc",
      v21,
      v22[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180007df0  mov     [rsp+arg_18], rbx
0x180007df5  push    rsi
0x180007df6  push    rdi
0x180007df7  push    r14
0x180007df9  sub     rsp, 40h
0x180007dfd  mov     r14, rdx
0x180007e00  mov     qword ptr [r8], 0
0x180007e07  mov     rdi, rcx
0x180007e0a  mov     edx, 130h; dwBytes
0x180007e0f  mov     ecx, 8; dwFlags
0x180007e14  mov     rsi, r8
0x180007e17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e1c  mov     rbx, rax
0x180007e1f  test    rax, rax
0x180007e22  jnz     short loc_180007E56
0x180007e24  mov     rcx, [rsp+58h]; this
0x180007e29  lea     rdx, aDataalloc; "dataAlloc"
0x180007e30  mov     ebx, 8007000Eh
0x180007e35  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x180007e3c  mov     dword ptr [rsp+58h+var_30], ebx; wil::details *
0x180007e40  mov     [rsp+58h+var_38], rdx; char *
0x180007e45  mov     edx, 14Bh; void *
0x180007e4a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180007e4f  mov     eax, ebx
0x180007e51  jmp     loc_180007F33
0x180007e56  xorps   xmm0, xmm0
0x180007e59  movdqu  xmmword ptr [rsp+58h+var_28], xmm0; int
0x180007e5f  test    bl, 3
0x180007e62  jz      short loc_180007E6A
0x180007e64  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
0x180007e6a  mov     r9, rbx
0x180007e6d  lea     rcx, [rsp+58h+var_28]; this
0x180007e72  shr     r9, 2; unsigned __int64
0x180007e76  mov     rdx, rdi; unsigned __int16 *
0x180007e79  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007e7e  mov     edi, eax
0x180007e80  test    eax, eax
0x180007e82  jns     short loc_180007EC0
0x180007e84  mov     rcx, [rsp+58h]; this
0x180007e89  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x180007e90  mov     dword ptr [rsp+58h+var_30], eax; wil::details *
0x180007e94  mov     edx, 14Eh; void *
0x180007e99  lea     rax, aSemaphorevalue; "semaphoreValue.CreateFromPointer(name, "...
0x180007ea0  mov     [rsp+58h+var_38], rax; char *
0x180007ea5  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180007eaa  lea     rcx, [rsp+58h+var_28]; this
0x180007eaf  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007eb4  mov     rcx, rbx; this
0x180007eb7  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007ebc  mov     eax, edi
0x180007ebe  jmp     short loc_180007F33
0x180007ec0  mov     dword ptr [rbx], 1
0x180007ec6  lea     rcx, [rbx+28h]; void *
0x180007eca  mov     rax, [r14]
0x180007ecd  xor     edx, edx; Val
0x180007ecf  mov     [rbx+8], rax
0x180007ed3  mov     r8d, 108h; Size
0x180007ed9  mov     rax, qword ptr [rsp+58h+var_28]
0x180007ede  mov     qword ptr [r14], 0
0x180007ee5  mov     [rbx+10h], rax
0x180007ee9  mov     rax, qword ptr [rsp+58h+var_28+8]
0x180007eee  mov     [rbx+18h], rax
0x180007ef2  mov     qword ptr [rsp+58h+var_28], 0
0x180007efb  mov     qword ptr [rsp+58h+var_28+8], 0
0x180007f04  call    memset_0
0x180007f09  xor     eax, eax
0x180007f0b  lea     rcx, [rbx+28h]; this
0x180007f0f  mov     [rbx+20h], rax
0x180007f13  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007f18  lea     rcx, [rbx+0E8h]; this
0x180007f1f  call    ??0SubscriptionList@details_abi@wil@@QEAA@XZ; wil::details_abi::SubscriptionList::SubscriptionList(void)
0x180007f24  lea     rcx, [rsp+58h+var_28]; this
0x180007f29  mov     [rsi], rbx
0x180007f2c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007f31  xor     eax, eax
0x180007f33  mov     rbx, [rsp+58h+arg_18]
0x180007f38  add     rsp, 40h
0x180007f3c  pop     r14
0x180007f3e  pop     rdi
0x180007f3f  pop     rsi
0x180007f40  retn
```
