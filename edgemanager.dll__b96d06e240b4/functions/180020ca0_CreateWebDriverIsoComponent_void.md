# CreateWebDriverIsoComponent(void)

- ea: `0x180020ca0`
- end: `0x180020dc7`
- name: `?CreateWebDriverIsoComponent@@YAJXZ`
- size: `295`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020c34`

## callees

- `0x180020ca0`
- `0x180020e38`
- `0x18002b530`
- `0x18002c5b0`
- `0x180035b88`

## import_xrefs

- `edgeIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x180020d7d`
- `edgeIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x180020d7d`
- `edgeIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180020cea`
- `edgeIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180020cea`

## pseudocode

```c
__int64 __fastcall CreateWebDriverIsoComponent(int (*a1)(struct _IsoCreationComponentData *))
{
  int IsoComponentDefinitions; // eax
  unsigned int v2; // ebx
  int ComponentByCreDat; // eax
  int v5; // [rsp+20h] [rbp-2D8h]
  int v6; // [rsp+20h] [rbp-2D8h]
  _DWORD v7[4]; // [rsp+50h] [rbp-2A8h] BYREF
  _BYTE v8[2]; // [rsp+60h] [rbp-298h] BYREF
  __int16 v9; // [rsp+62h] [rbp-296h]
  int v10; // [rsp+70h] [rbp-288h]
  int v11; // [rsp+78h] [rbp-280h]
  int v12; // [rsp+1CCh] [rbp-12Ch]
  int v13; // [rsp+200h] [rbp-F8h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  IsoComponentDefinitions = CWebDriverDispatcher::CreateIsoComponentDefinitions(a1);
  if ( IsoComponentDefinitions < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverdispatcher.cxx",
      (const char *)(unsigned int)IsoComponentDefinitions,
      v5);
  v2 = IsoGetIntegrity(1) | 0x2000;
  memset_0(v8, 0, 0x278u);
  v8[0] = 1;
  v9 = 632;
  v13 = 122;
  v12 = 2;
  v10 = 105;
  v11 = 0;
  v7[0] = 0;
  ComponentByCreDat = IsoCreateComponentByCreDat(v2, v8, 0, v7, 0, 0, 0, 0, 0);
  if ( ComponentByCreDat < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverdispatcher.cxx",
      (const char *)(unsigned int)ComponentByCreDat,
      v6);
  return 0;
}

```

## disassembly

```asm
0x180020ca0  mov     [rsp+arg_0], rbx
0x180020ca5  push    rdi
0x180020ca6  sub     rsp, 2F0h
0x180020cad  mov     rax, cs:__security_cookie
0x180020cb4  xor     rax, rsp
0x180020cb7  mov     [rsp+2F8h+var_18], rax
0x180020cbf  call    ?CreateIsoComponentDefinitions@CWebDriverDispatcher@@SAJP6AJPEAU_IsoCreationComponentData@@@Z@Z; CWebDriverDispatcher::CreateIsoComponentDefinitions(long (*)(_IsoCreationComponentData *))
0x180020cc4  test    eax, eax
0x180020cc6  jns     short loc_180020CE5
0x180020cc8  mov     rcx, [rsp+2F8h]; this
0x180020cd0  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180020cd7  mov     r9d, eax; char *
0x180020cda  mov     edx, 99h; void *
0x180020cdf  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180020ce5  mov     ecx, 1
0x180020cea  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180020cf0  mov     edi, 278h
0x180020cf5  lea     rcx, [rsp+2F8h+var_298]; void *
0x180020cfa  mov     ebx, eax
0x180020cfc  mov     r8d, edi; Size
0x180020cff  xor     edx, edx; Val
0x180020d01  bts     ebx, 0Dh
0x180020d05  call    memset_0
0x180020d0a  mov     [rsp+2F8h+var_2B8], 0
0x180020d12  lea     r9, [rsp+2F8h+var_2A8]
0x180020d17  mov     [rsp+2F8h+var_2C0], 0
0x180020d20  lea     rdx, [rsp+2F8h+var_298]
0x180020d25  mov     [rsp+2F8h+var_2C8], 0
0x180020d2e  xor     r8d, r8d
0x180020d31  mov     [rsp+2F8h+var_2D0], 0
0x180020d3a  mov     ecx, ebx
0x180020d3c  mov     qword ptr [rsp+2F8h+var_2D8], 0; int
0x180020d45  mov     [rsp+2F8h+var_298], 1
0x180020d4a  mov     [rsp+2F8h+var_296], di
0x180020d4f  mov     [rsp+2F8h+var_F8], 7Ah ; 'z'
0x180020d5a  mov     [rsp+2F8h+var_12C], 2
0x180020d65  mov     [rsp+2F8h+var_288], 69h ; 'i'
0x180020d6d  mov     [rsp+2F8h+var_280], 0
0x180020d75  mov     [rsp+2F8h+var_2A8], 0
0x180020d7d  call    cs:__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z; IsoCreateComponentByCreDat(ulong,_IsoCreationComponentData *,ushort const *,ulong *,ulong *,ulong *,_IsoWindowsContainer *,unsigned __int64 *,IsoCreationFailureTreatment)
0x180020d83  test    eax, eax
0x180020d85  jns     short loc_180020DA4
0x180020d87  mov     rcx, [rsp+2F8h]; this
0x180020d8f  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180020d96  mov     r9d, eax; char *
0x180020d99  mov     edx, 0ADh; void *
0x180020d9e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180020da4  xor     eax, eax
0x180020da6  mov     rcx, [rsp+2F8h+var_18]
0x180020dae  xor     rcx, rsp; StackCookie
0x180020db1  call    __security_check_cookie
0x180020db6  mov     rbx, [rsp+2F8h+arg_0]
0x180020dbe  add     rsp, 2F0h
0x180020dc5  pop     rdi
0x180020dc6  retn
```
