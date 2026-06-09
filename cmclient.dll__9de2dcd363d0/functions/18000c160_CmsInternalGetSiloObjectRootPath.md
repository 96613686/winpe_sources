# CmsInternalGetSiloObjectRootPath

- ea: `0x18000c160`
- end: `0x18000c269`
- name: `CmsInternalGetSiloObjectRootPath`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000c160`
- `0x18000db50`
- `0x18000ee00`

## string_xrefs

- `0x18000c1c4`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c241`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetSiloObjectRootPath(__int64 a1, void *a2, unsigned int *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  void *v7; // rbx
  __int64 v8; // rax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  int v12[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *Src; // [rsp+60h] [rbp+18h] BYREF
  void **p_Src; // [rsp+68h] [rbp+20h] BYREF

  if ( !a3 || *a3 && !a2 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)0x80070057LL,
      v12[0]);
    return v6;
  }
  Src = 0;
  p_Src = &Src;
  *(_QWORD *)v12 = *(_QWORD *)(a1 + 24);
  v5 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         CmsRpcClt_GetSiloObjectRootPath,
         v12,
         &p_Src);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v5,
      v12[0]);
    if ( Src )
      MIDL_user_free(Src);
    return v6;
  }
  v7 = Src;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)Src + v8) );
  v9 = v8 + 1;
  v10 = *a3;
  *a3 = v9;
  if ( v10 < v9 )
  {
    if ( v7 )
      MIDL_user_free(v7);
    return 2147942522LL;
  }
  else
  {
    memcpy_0(a2, v7, 2LL * v9);
    if ( v7 )
      MIDL_user_free(v7);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c160  mov     [rsp+arg_0], rbx
0x18000c165  push    rbp
0x18000c166  push    rsi
0x18000c167  push    rdi
0x18000c168  sub     rsp, 30h
0x18000c16c  xor     ebp, ebp
0x18000c16e  mov     rdi, r8
0x18000c171  mov     rsi, rdx
0x18000c174  test    r8, r8
0x18000c177  jz      loc_18000C23C
0x18000c17d  cmp     [r8], ebp
0x18000c180  jbe     short loc_18000C18B
0x18000c182  test    rdx, rdx
0x18000c185  jz      loc_18000C23C
0x18000c18b  lea     rax, [rsp+48h+Src]
0x18000c190  mov     [rsp+48h+Src], rbp
0x18000c195  mov     [rsp+48h+arg_18], rax
0x18000c19a  lea     r8, [rsp+48h+arg_18]
0x18000c19f  mov     rax, [rcx+18h]
0x18000c1a3  lea     rdx, [rsp+48h+var_28]
0x18000c1a8  lea     rcx, CmsRpcClt_GetSiloObjectRootPath
0x18000c1af  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c1b4  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000c1b9  mov     ebx, eax
0x18000c1bb  test    eax, eax
0x18000c1bd  jns     short loc_18000C1E9
0x18000c1bf  mov     rcx, [rsp+48h]; this
0x18000c1c4  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c1cb  mov     r9d, eax; char *
0x18000c1ce  mov     edx, 17Ch; void *
0x18000c1d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1d8  mov     rcx, [rsp+48h+Src]; void *
0x18000c1dd  test    rcx, rcx
0x18000c1e0  jz      short loc_18000C25A
0x18000c1e2  call    MIDL_user_free
0x18000c1e7  jmp     short loc_18000C25A
0x18000c1e9  mov     rbx, [rsp+48h+Src]
0x18000c1ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c1f2  inc     rax
0x18000c1f5  cmp     [rbx+rax*2], bp
0x18000c1f9  jnz     short loc_18000C1F2
0x18000c1fb  lea     ecx, [rax+1]
0x18000c1fe  mov     eax, [rdi]
0x18000c200  mov     [rdi], ecx
0x18000c202  cmp     eax, ecx
0x18000c204  jb      short loc_18000C228
0x18000c206  mov     r8d, ecx
0x18000c209  mov     rdx, rbx; Src
0x18000c20c  add     r8, r8; Size
0x18000c20f  mov     rcx, rsi; void *
0x18000c212  call    memcpy_0
0x18000c217  test    rbx, rbx
0x18000c21a  jz      short loc_18000C224
0x18000c21c  mov     rcx, rbx; void *
0x18000c21f  call    MIDL_user_free
0x18000c224  xor     eax, eax
0x18000c226  jmp     short loc_18000C25C
0x18000c228  test    rbx, rbx
0x18000c22b  jz      short loc_18000C235
0x18000c22d  mov     rcx, rbx; void *
0x18000c230  call    MIDL_user_free
0x18000c235  mov     eax, 8007007Ah
0x18000c23a  jmp     short loc_18000C25C
0x18000c23c  mov     rcx, [rsp+48h]; this
0x18000c241  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c248  mov     ebx, 80070057h
0x18000c24d  mov     edx, 171h; void *
0x18000c252  mov     r9d, ebx; char *
0x18000c255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c25a  mov     eax, ebx
0x18000c25c  mov     rbx, [rsp+48h+arg_0]
0x18000c261  add     rsp, 30h
0x18000c265  pop     rdi
0x18000c266  pop     rsi
0x18000c267  pop     rbp
0x18000c268  retn
```
