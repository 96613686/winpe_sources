# container::RegistryProvider::CreateMultipleNamespaceNodes(void *,std::vector<container::RegistryProvider::_VR_NSN_INFO,std::allocator<container::RegistryProvider::_VR_NSN_INFO>> const &)

- ea: `0x180028f54`
- end: `0x18002925f`
- name: `?CreateMultipleNamespaceNodes@RegistryProvider@container@@YAXPEAXAEBV?$vector@U_VR_NSN_INFO@RegistryProvider@container@@V?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@std@@@std@@@Z`
- size: `779`
- prototype: `void __fastcall(container::RegistryProvider *, const void ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18000d710`

## callees

- `0x180002ee4`
- `0x180002f1c`
- `0x180003614`
- `0x18000b4bc`
- `0x18000bdec`
- `0x180027938`
- `0x180028f54`
- `0x18002993c`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800291b1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800291b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800291d2`

## string_xrefs

- `0x1800291f9`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002920e`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x180029220`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x180029235`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002924a`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
void __fastcall container::RegistryProvider::CreateMultipleNamespaceNodes(
        container::RegistryProvider *a1,
        const void ***a2)
{
  char *v4; // rbx
  __int64 v5; // r14
  unsigned __int64 v6; // r13
  const void **i; // rcx
  _DWORD *v8; // r15
  const void **v9; // rdi
  int v10; // ecx
  unsigned __int64 v11; // rax
  unsigned __int16 v12; // dx
  char *v13; // r14
  unsigned int v14; // eax
  __int16 v15; // dx
  unsigned __int64 v16; // rax
  unsigned __int16 v17; // dx
  unsigned int v18; // eax
  __int16 v19; // dx
  const void *v20; // rdx
  const void **v21; // rsi
  const void *v22; // rdx
  void *v23; // rax
  unsigned __int64 v24; // rdx
  const char *v25; // r9
  int lpOutBuffer; // [rsp+20h] [rbp-48h]
  const void **v27; // [rsp+40h] [rbp-28h] BYREF
  const void *v28; // [rsp+48h] [rbp-20h] BYREF
  const void **j; // [rsp+50h] [rbp-18h]
  char *v30; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  int v32; // [rsp+B0h] [rbp+48h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v34; // [rsp+C0h] [rbp+58h]
  _DWORD *v35; // [rsp+C8h] [rbp+60h]

  BytesReturned = 0;
  v35 = 0;
  v4 = (char *)container::RegistryProvider::OpenRegistryDriver(a1);
  v30 = v4;
  v5 = 12;
  v34 = 12;
  v6 = 12;
  for ( i = *a2; i != a2[1]; i += 10 )
    v6 += 2 * ((__int64)i[6] + (_QWORD)i[2]) + 12;
  v8 = operator new[](v6);
  v35 = v8;
  *(_QWORD *)v8 = a1;
  v8[2] = -858993459 * (((char *)a2[1] - (char *)*a2) >> 4);
  v9 = *a2;
  for ( j = a2[1]; v9 != j; v9 += 10 )
  {
    v10 = 0;
    v11 = (unsigned __int64)v9[2];
    if ( v11 > 0xFFFF )
      v12 = -1;
    else
      v12 = (unsigned __int16)v9[2];
    if ( v11 > 0xFFFF )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        v11 > 0xFFFF ? (const char *)0xC0000095LL : 0,
        lpOutBuffer);
    v13 = (char *)v8 + v5;
    v14 = 2 * v12;
    if ( v14 > 0xFFFF )
      v15 = -1;
    else
      v15 = 2 * v12;
    *((_WORD *)v13 + 2) = v15;
    if ( v14 > 0xFFFF )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        v14 > 0xFFFF ? (const char *)0xC0000095LL : 0,
        lpOutBuffer);
    if ( *((_DWORD *)v9 + 18) )
      v10 = 4;
    v32 = v10;
    if ( *((_DWORD *)v9 + 17) )
    {
      v10 |= 2u;
      v32 = v10;
    }
    v16 = (unsigned __int64)v9[6];
    if ( v16 > 0xFFFF )
      v17 = -1;
    else
      v17 = (unsigned __int16)v9[6];
    if ( v16 > 0xFFFF )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0xCE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        v16 > 0xFFFF ? (const char *)0xC0000095LL : 0,
        lpOutBuffer);
    v18 = 2 * v17;
    if ( v18 > 0xFFFF )
      v19 = -1;
    else
      v19 = 2 * v17;
    *((_WORD *)v13 + 3) = v19;
    if ( v18 > 0xFFFF )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        v18 > 0xFFFF ? (const char *)0xC0000095LL : 0,
        lpOutBuffer);
    *(_DWORD *)v13 = *((_DWORD *)v9 + 16);
    *((_DWORD *)v13 + 2) = v10;
    if ( (unsigned __int64)v9[3] <= 7 )
      v20 = v9;
    else
      v20 = *v9;
    memcpy_0(v13 + 12, v20, *((unsigned __int16 *)v13 + 2));
    v21 = v9 + 4;
    if ( (unsigned __int64)v9[7] <= 7 )
      v22 = v9 + 4;
    else
      v22 = *v21;
    memcpy_0(
      &v13[2 * ((unsigned __int64)*((unsigned __int16 *)v13 + 2) >> 1) + 12],
      v22,
      *((unsigned __int16 *)v13 + 3));
    if ( (unsigned __int64)v9[7] > 7 )
      v21 = (const void **)*v21;
    v27 = v21;
    if ( (unsigned __int64)v9[3] <= 7 )
      v23 = v9;
    else
      v23 = (void *)*v9;
    v28 = v23;
    ContainerProvider::CreateRegNamespaceNode<unsigned short const *,unsigned short const *,unsigned long const &,unsigned long &>(
      &v28,
      &v27,
      v9 + 8,
      &v32);
    v5 = v34 + *((unsigned __int16 *)v13 + 3) + *((unsigned __int16 *)v13 + 2) + 12LL;
    v34 = v5;
  }
  if ( !DeviceIoControl(v4, 0x220014u, v8, v6, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v25);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  operator delete(v8, v24);
}

```

## disassembly

```asm
0x180028f54  push    rbp
0x180028f56  push    rbx
0x180028f57  push    rsi
0x180028f58  push    rdi
0x180028f59  push    r12
0x180028f5b  push    r13
0x180028f5d  push    r14
0x180028f5f  push    r15
0x180028f61  mov     rbp, rsp
0x180028f64  sub     rsp, 68h
0x180028f68  mov     rsi, rdx
0x180028f6b  mov     rdi, rcx
0x180028f6e  xor     r12d, r12d
0x180028f71  mov     [rbp+BytesReturned], r12d
0x180028f75  mov     [rbp+arg_18], r12
0x180028f79  call    ?OpenRegistryDriver@RegistryProvider@container@@YAPEAXXZ; container::RegistryProvider::OpenRegistryDriver(void)
0x180028f7e  mov     rbx, rax
0x180028f81  mov     [rbp+var_10], rax
0x180028f85  lea     r14d, [r12+0Ch]
0x180028f8a  mov     [rbp+arg_10], r14
0x180028f8e  mov     r13d, r14d
0x180028f91  mov     rcx, [rsi]
0x180028f94  jmp     short loc_180028FAA
0x180028f96  mov     rax, [rcx+30h]
0x180028f9a  add     rax, [rcx+10h]
0x180028f9e  lea     r13, [r13+rax*2+0]
0x180028fa3  add     r13, r14
0x180028fa6  add     rcx, 50h ; 'P'
0x180028faa  cmp     rcx, [rsi+8]
0x180028fae  jnz     short loc_180028F96
0x180028fb0  mov     rcx, r13; unsigned __int64
0x180028fb3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028fb8  mov     r15, rax
0x180028fbb  mov     [rbp+arg_18], rax
0x180028fbf  mov     [rax], rdi
0x180028fc2  mov     rcx, [rsi+8]
0x180028fc6  sub     rcx, [rsi]
0x180028fc9  sar     rcx, 4
0x180028fcd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180028fd7  imul    rcx, rax
0x180028fdb  mov     [r15+8], ecx
0x180028fdf  mov     rdi, [rsi]
0x180028fe2  mov     rax, [rsi+8]
0x180028fe6  mov     [rbp+var_18], rax
0x180028fea  cmp     rdi, rax
0x180028fed  jz      loc_18002918B
0x180028ff3  mov     r8d, 0FFFFh
0x180028ff9  mov     r11d, 0C0000095h
0x180028fff  mov     ecx, r12d
0x180029002  mov     rax, [rdi+10h]
0x180029006  cmp     rax, r8
0x180029009  ja      short loc_180029010
0x18002900b  movzx   edx, ax
0x18002900e  jmp     short loc_180029013
0x180029010  mov     edx, r8d
0x180029013  cmp     r8, rax
0x180029016  sbb     r9d, r9d
0x180029019  and     r9d, r11d; char *
0x18002901c  mov     r10, [rbp+40h]
0x180029020  cmp     rax, r8
0x180029023  ja      loc_1800291F9
0x180029029  add     r14, r15
0x18002902c  movzx   eax, dx
0x18002902f  add     eax, eax
0x180029031  cmp     eax, r8d
0x180029034  ja      short loc_18002903B
0x180029036  movzx   edx, ax
0x180029039  jmp     short loc_18002903E
0x18002903b  mov     edx, r8d
0x18002903e  cmp     r8d, eax
0x180029041  sbb     r9d, r9d
0x180029044  and     r9d, r11d; char *
0x180029047  mov     [r14+4], dx
0x18002904c  mov     r10, [rbp+40h]
0x180029050  cmp     eax, r8d
0x180029053  ja      loc_18002924A
0x180029059  mov     eax, 4
0x18002905e  cmp     [rdi+48h], r12d
0x180029062  cmovnz  ecx, eax
0x180029065  mov     [rbp+arg_0], ecx
0x180029068  cmp     [rdi+44h], r12d
0x18002906c  jz      short loc_180029074
0x18002906e  or      ecx, 2
0x180029071  mov     [rbp+arg_0], ecx
0x180029074  mov     rax, [rdi+30h]
0x180029078  cmp     rax, r8
0x18002907b  ja      short loc_180029082
0x18002907d  movzx   edx, ax
0x180029080  jmp     short loc_180029085
0x180029082  mov     edx, r8d
0x180029085  cmp     r8, rax
0x180029088  sbb     r9d, r9d
0x18002908b  and     r9d, r11d; char *
0x18002908e  mov     r10, [rbp+40h]
0x180029092  cmp     rax, r8
0x180029095  ja      loc_180029235
0x18002909b  movzx   eax, dx
0x18002909e  add     eax, eax
0x1800290a0  cmp     eax, r8d
0x1800290a3  ja      short loc_1800290AA
0x1800290a5  movzx   edx, ax
0x1800290a8  jmp     short loc_1800290AD
0x1800290aa  mov     edx, r8d
0x1800290ad  cmp     r8d, eax
0x1800290b0  sbb     r9d, r9d
0x1800290b3  and     r9d, r11d; char *
0x1800290b6  mov     [r14+6], dx
0x1800290bb  mov     r10, [rbp+40h]
0x1800290bf  cmp     eax, r8d
0x1800290c2  ja      loc_180029220
0x1800290c8  mov     eax, [rdi+40h]
0x1800290cb  mov     [r14], eax
0x1800290ce  mov     [r14+8], ecx
0x1800290d2  cmp     qword ptr [rdi+18h], 7
0x1800290d7  jbe     short loc_1800290DE
0x1800290d9  mov     rdx, [rdi]
0x1800290dc  jmp     short loc_1800290E1
0x1800290de  mov     rdx, rdi; Src
0x1800290e1  movzx   r8d, word ptr [r14+4]; Size
0x1800290e6  lea     rcx, [r14+0Ch]; void *
0x1800290ea  call    memcpy_0
0x1800290ef  lea     rsi, [rdi+20h]
0x1800290f3  cmp     qword ptr [rsi+18h], 7
0x1800290f8  jbe     short loc_1800290FF
0x1800290fa  mov     rdx, [rsi]
0x1800290fd  jmp     short loc_180029102
0x1800290ff  mov     rdx, rsi; Src
0x180029102  movzx   r8d, word ptr [r14+6]; Size
0x180029107  movzx   eax, word ptr [r14+4]
0x18002910c  shr     rax, 1
0x18002910f  add     rax, 6
0x180029113  lea     rcx, [r14+rax*2]; void *
0x180029117  call    memcpy_0
0x18002911c  cmp     qword ptr [rsi+18h], 7
0x180029121  jbe     short loc_180029126
0x180029123  mov     rsi, [rsi]
0x180029126  mov     [rbp+var_28], rsi
0x18002912a  cmp     qword ptr [rdi+18h], 7
0x18002912f  jbe     short loc_180029136
0x180029131  mov     rax, [rdi]
0x180029134  jmp     short loc_180029139
0x180029136  mov     rax, rdi
0x180029139  mov     [rbp+var_20], rax
0x18002913d  lea     r9, [rbp+arg_0]
0x180029141  lea     r8, [rdi+40h]
0x180029145  lea     rdx, [rbp+var_28]
0x180029149  lea     rcx, [rbp+var_20]
0x18002914d  call    ??$CreateRegNamespaceNode@PEBGPEBGAEBKAEAK@ContainerProvider@@SAX$$QEAPEBG0AEBKAEAK@Z; ContainerProvider::CreateRegNamespaceNode<ushort const *,ushort const *,ulong const &,ulong &>(ushort const * &&,ushort const * &&,ulong const &,ulong &)
0x180029152  movzx   ecx, word ptr [r14+4]
0x180029157  movzx   eax, word ptr [r14+6]
0x18002915c  add     rax, [rbp+arg_10]
0x180029160  lea     r14, [rcx+0Ch]
0x180029164  add     r14, rax
0x180029167  mov     [rbp+arg_10], r14
0x18002916b  add     rdi, 50h ; 'P'
0x18002916f  cmp     rdi, [rbp+var_18]
0x180029173  mov     r8d, 0FFFFh
0x180029179  mov     r12d, 0
0x18002917f  mov     r11d, 0C0000095h
0x180029185  jnz     loc_180028FFF
0x18002918b  mov     r9d, r13d; nInBufferSize
0x18002918e  mov     [rsp+68h+lpOverlapped], r12; lpOverlapped
0x180029193  lea     rax, [rbp+BytesReturned]
0x180029197  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18002919c  mov     [rsp+68h+nOutBufferSize], r12d; nOutBufferSize
0x1800291a1  mov     [rsp+68h+lpOutBuffer], r12; lpOutBuffer
0x1800291a6  mov     r8, r15; lpInBuffer
0x1800291a9  mov     edx, 220014h; dwIoControlCode
0x1800291ae  mov     rcx, rbx; hDevice
0x1800291b1  call    cs:__imp_DeviceIoControl
0x1800291b8  nop     dword ptr [rax+rax+00h]
0x1800291bd  mov     rcx, [rbp+40h]; this
0x1800291c1  test    eax, eax
0x1800291c3  jz      short loc_18002920E
0x1800291c5  lea     rax, [rbx-1]
0x1800291c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800291cd  ja      short loc_1800291DF
0x1800291cf  mov     rcx, rbx; hObject
0x1800291d2  call    cs:__imp_CloseHandle
0x1800291d9  nop     dword ptr [rax+rax+00h]
0x1800291de  nop
0x1800291df  mov     rcx, r15; void *
0x1800291e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800291e7  add     rsp, 68h
0x1800291eb  pop     r15
0x1800291ed  pop     r14
0x1800291ef  pop     r13
0x1800291f1  pop     r12
0x1800291f3  pop     rdi
0x1800291f4  pop     rsi
0x1800291f5  pop     rbx
0x1800291f6  pop     rbp
0x1800291f7  retn
0x1800291f9  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029200  mov     edx, 0BEh; void *
0x180029205  mov     rcx, r10; this
0x180029208  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002920e  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029215  mov     edx, 0FAh; void *
0x18002921a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029220  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029227  mov     edx, 0D3h; void *
0x18002922c  mov     rcx, r10; this
0x18002922f  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180029235  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002923c  mov     edx, 0CEh; void *
0x180029241  mov     rcx, r10; this
0x180029244  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002924a  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029251  mov     edx, 0C3h; void *
0x180029256  mov     rcx, r10; this
0x180029259  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
