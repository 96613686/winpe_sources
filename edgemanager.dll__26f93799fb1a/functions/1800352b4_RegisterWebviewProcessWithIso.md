# RegisterWebviewProcessWithIso

- ea: `0x1800352b4`
- end: `0x1800353a6`
- name: `RegisterWebviewProcessWithIso`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800051c0`

## callees

- `0x1800352b4`
- `0x180035b88`

## import_xrefs

- `edgeIso!__imp_?IsoRegisterProcess@@YAJKKPEAK@Z` at `0x1800352d6`
- `edgeIso!__imp_?IsoRegisterProcess@@YAJKKPEAK@Z` at `0x1800352d6`
- `edgeIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAXW4_IsoMemoryTag@@@Z` at `0x18003535f`
- `edgeIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAXW4_IsoMemoryTag@@@Z` at `0x18003535f`
- `edgeIso!__imp_?IsoRegisterManagerComponent@@YAJKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180035313`
- `edgeIso!__imp_?IsoRegisterManagerComponent@@YAJKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180035313`

## pseudocode

```c
__int64 __fastcall RegisterWebviewProcessWithIso(unsigned int a1, unsigned int *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-30h]
  unsigned int v8; // [rsp+30h] [rbp-20h] BYREF
  __int64 v9; // [rsp+38h] [rbp-18h] BYREF
  struct _IsoComponent *v10; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+28h] BYREF

  v12 = 0;
  v3 = IsoRegisterProcess(0x40009u, a1, &v12);
  if ( v3 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v3,
      v7);
  v13 = 0;
  v10 = 0;
  v4 = IsoRegisterManagerComponent(v12, &v13, &v10);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v4,
      v7);
  v9 = 0;
  v8 = 0;
  LOWORD(v7) = 1060;
  v5 = IsoAllocSharedMemoryPerFlags(9, &v8, 360, &v9);
  if ( v5 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v5,
      v7);
  *(_DWORD *)(v9 + 8) = v12;
  *(_DWORD *)(v9 + 20) = v13;
  result = v8;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x1800352b4  mov     [rsp-8+arg_0], rbx
0x1800352b9  push    rbp
0x1800352ba  mov     rbp, rsp
0x1800352bd  sub     rsp, 50h
0x1800352c1  mov     rbx, rdx
0x1800352c4  mov     [rbp+arg_10], 0
0x1800352cb  mov     edx, ecx
0x1800352cd  lea     r8, [rbp+arg_10]
0x1800352d1  mov     ecx, 40009h
0x1800352d6  call    cs:__imp_?IsoRegisterProcess@@YAJKKPEAK@Z; IsoRegisterProcess(ulong,ulong,ulong *)
0x1800352dc  test    eax, eax
0x1800352de  jns     short loc_1800352F9
0x1800352e0  mov     rcx, [rbp+8]; this
0x1800352e4  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800352eb  mov     r9d, eax; char *
0x1800352ee  mov     edx, 0D9h; void *
0x1800352f3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800352f9  mov     ecx, [rbp+arg_10]
0x1800352fc  lea     r8, [rbp+var_10]
0x180035300  lea     rdx, [rbp+arg_18]
0x180035304  mov     [rbp+arg_18], 0
0x18003530b  mov     [rbp+var_10], 0
0x180035313  call    cs:__imp_?IsoRegisterManagerComponent@@YAJKPEAKPEAPEAU_IsoComponent@@@Z; IsoRegisterManagerComponent(ulong,ulong *,_IsoComponent * *)
0x180035319  test    eax, eax
0x18003531b  jns     short loc_180035336
0x18003531d  mov     rcx, [rbp+8]; this
0x180035321  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180035328  mov     r9d, eax; char *
0x18003532b  mov     edx, 0DDh; void *
0x180035330  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180035336  lea     r9, [rbp+var_18]
0x18003533a  mov     [rbp+var_18], 0
0x180035342  mov     r8d, 168h
0x180035348  mov     [rbp+var_20], 0
0x18003534f  lea     rdx, [rbp+var_20]
0x180035353  mov     word ptr [rsp+50h+var_30], 424h; int
0x18003535a  mov     ecx, 9
0x18003535f  call    cs:__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAXW4_IsoMemoryTag@@@Z; IsoAllocSharedMemoryPerFlags(ulong,ulong *,ulong,void * *,_IsoMemoryTag)
0x180035365  test    eax, eax
0x180035367  jns     short loc_180035382
0x180035369  mov     rcx, [rbp+8]; this
0x18003536d  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180035374  mov     r9d, eax; char *
0x180035377  mov     edx, 0E1h; void *
0x18003537c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180035382  mov     rcx, [rbp+var_18]
0x180035386  mov     eax, [rbp+arg_10]
0x180035389  mov     [rcx+8], eax
0x18003538c  mov     rax, [rbp+var_18]
0x180035390  mov     ecx, [rbp+arg_18]
0x180035393  mov     [rax+14h], ecx
0x180035396  mov     eax, [rbp+var_20]
0x180035399  mov     [rbx], eax
0x18003539b  mov     rbx, [rsp+50h+arg_0]
0x1800353a0  add     rsp, 50h
0x1800353a4  pop     rbp
0x1800353a5  retn
```
