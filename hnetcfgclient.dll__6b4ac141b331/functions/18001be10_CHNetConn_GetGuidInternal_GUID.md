# CHNetConn::GetGuidInternal(_GUID * *)

- ea: `0x18001be10`
- end: `0x18001c068`
- name: `?GetGuidInternal@CHNetConn@@IEAAJPEAPEAU_GUID@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct _GUID **)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018560`
- `0x18001bca0`
- `0x18001c070`
- `0x18001cf24`
- `0x18001e130`
- `0x18001ee3c`
- `0x18001fc90`
- `0x18001fe80`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001b110`
- `0x18001be10`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c026`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be7b`
- `OLEAUT32!__imp_VariantInit` at `0x18001be71`
- `OLEAUT32!__imp_VariantInit` at `0x18001be71`
- `OLEAUT32!__imp_VariantClear` at `0x18001bff6`
- `OLEAUT32!__imp_VariantClear` at `0x18001bff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001be8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001be8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c009`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001bfb9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001bfb9`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetGuidInternal(CHNetConn *this, struct _GUID **a2)
{
  int v4; // ebx
  LPVOID v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int ConnectionObject; // eax
  int v10; // eax
  bool v11; // sf
  HRESULT v12; // eax
  void *v13; // rcx
  VARIANTARG pvarg; // [rsp+40h] [rbp-58h] BYREF
  struct IWbemClassObject *v16; // [rsp+A0h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 13) )
    goto LABEL_34;
  v5 = CoTaskMemAlloc(0x10u);
  *((_QWORD *)this + 13) = v5;
  if ( !v5 )
  {
    v4 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 300;
      v8 = 2147942414LL;
LABEL_11:
      WPP_SF_d(v6[2], v7, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v8);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v16 = 0;
  ConnectionObject = CHNetConn::GetConnectionObject(this, &v16);
  v4 = ConnectionObject;
  if ( ConnectionObject < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 301;
      v8 = (unsigned int)ConnectionObject;
      goto LABEL_11;
    }
LABEL_31:
    v13 = (void *)*((_QWORD *)this + 13);
    if ( v13 )
    {
      CoTaskMemFree(v13);
      *((_QWORD *)this + 13) = 0;
    }
    goto LABEL_33;
  }
  if ( !ConnectionObject )
  {
    v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v16->lpVtbl->Get)(
            v16,
            L"Guid",
            0,
            &pvarg,
            0,
            0);
    v4 = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        302,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v10);
    }
    ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
    v11 = v4 < 0;
    if ( !v4 )
    {
      v12 = CLSIDFromString(pvarg.bstrVal, *((LPCLSID *)this + 13));
      v4 = v12;
      if ( v12 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          303,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)v12);
      }
      VariantClear(&pvarg);
      v11 = v4 < 0;
    }
    if ( v11 )
      goto LABEL_31;
  }
LABEL_33:
  if ( !v4 )
LABEL_34:
    *a2 = (struct _GUID *)*((_QWORD *)this + 13);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      304,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001be10  push    rbx
0x18001be12  push    rsi
0x18001be13  push    rdi
0x18001be14  push    r12
0x18001be16  push    r13
0x18001be18  push    r14
0x18001be1a  sub     rsp, 68h
0x18001be1e  mov     r14, rdx
0x18001be21  mov     rdi, rcx
0x18001be24  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be2b  lea     r12, WPP_GLOBAL_Control
0x18001be32  lea     r13, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001be39  cmp     rcx, r12
0x18001be3c  jz      short loc_18001BE5B
0x18001be3e  test    byte ptr [rcx+1Ch], 8
0x18001be42  jz      short loc_18001BE5B
0x18001be44  cmp     byte ptr [rcx+19h], 6
0x18001be48  jb      short loc_18001BE5B
0x18001be4a  mov     rcx, [rcx+10h]
0x18001be4e  mov     edx, 12Bh
0x18001be53  mov     r8, r13
0x18001be56  call    WPP_SF_
0x18001be5b  xorps   xmm0, xmm0
0x18001be5e  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18001be63  xor     eax, eax
0x18001be65  xor     ebx, ebx
0x18001be67  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18001be6c  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18001be71  call    cs:__imp_VariantInit
0x18001be77  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001be7b  call    cs:__imp_EnterCriticalSection
0x18001be81  cmp     [rdi+68h], rbx
0x18001be85  jnz     loc_18001C01B
0x18001be8b  lea     ecx, [rbx+10h]; cb
0x18001be8e  call    cs:__imp_CoTaskMemAlloc
0x18001be94  mov     [rdi+68h], rax
0x18001be98  test    rax, rax
0x18001be9b  jnz     short loc_18001BEDF
0x18001be9d  mov     ebx, 8007000Eh
0x18001bea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bea9  cmp     rcx, r12
0x18001beac  jz      loc_18001C000
0x18001beb2  test    byte ptr [rcx+1Ch], 8
0x18001beb6  jz      loc_18001C000
0x18001bebc  cmp     byte ptr [rcx+19h], 2
0x18001bec0  jb      loc_18001C000
0x18001bec6  mov     edx, 12Ch
0x18001becb  mov     r9d, ebx
0x18001bece  mov     rcx, [rcx+10h]
0x18001bed2  mov     r8, r13
0x18001bed5  call    WPP_SF_d
0x18001beda  jmp     loc_18001C000
0x18001bedf  lea     rdx, [rsp+98h+arg_0]; struct IWbemClassObject **
0x18001bee7  mov     [rsp+98h+arg_0], rbx
0x18001beef  mov     rcx, rdi; this
0x18001bef2  call    ?GetConnectionObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionObject(IWbemClassObject * *)
0x18001bef7  mov     ebx, eax
0x18001bef9  test    eax, eax
0x18001befb  jns     short loc_18001BF2B
0x18001befd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf04  cmp     rcx, r12
0x18001bf07  jz      loc_18001C000
0x18001bf0d  test    byte ptr [rcx+1Ch], 8
0x18001bf11  jz      loc_18001C000
0x18001bf17  cmp     byte ptr [rcx+19h], 2
0x18001bf1b  jb      loc_18001C000
0x18001bf21  mov     edx, 12Dh
0x18001bf26  mov     r9d, eax
0x18001bf29  jmp     short loc_18001BECE
0x18001bf2b  jnz     loc_18001C017
0x18001bf31  mov     rcx, [rsp+98h+arg_0]
0x18001bf39  lea     r9, [rsp+98h+pvarg]
0x18001bf3e  mov     [rsp+98h+var_70], 0
0x18001bf47  lea     rdx, ?c_wszGuid@@3QBGB; "Guid"
0x18001bf4e  xor     r8d, r8d
0x18001bf51  mov     [rsp+98h+var_78], 0
0x18001bf5a  mov     rax, [rcx]
0x18001bf5d  mov     rax, [rax+20h]
0x18001bf61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf66  mov     ebx, eax
0x18001bf68  test    eax, eax
0x18001bf6a  jns     short loc_18001BF98
0x18001bf6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf73  cmp     rcx, r12
0x18001bf76  jz      short loc_18001BF98
0x18001bf78  test    byte ptr [rcx+1Ch], 8
0x18001bf7c  jz      short loc_18001BF98
0x18001bf7e  cmp     byte ptr [rcx+19h], 2
0x18001bf82  jb      short loc_18001BF98
0x18001bf84  mov     rcx, [rcx+10h]
0x18001bf88  mov     edx, 12Eh
0x18001bf8d  mov     r9d, eax
0x18001bf90  mov     r8, r13
0x18001bf93  call    WPP_SF_d
0x18001bf98  mov     rcx, [rsp+98h+arg_0]
0x18001bfa0  mov     rax, [rcx]
0x18001bfa3  mov     rax, [rax+10h]
0x18001bfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfac  test    ebx, ebx
0x18001bfae  jnz     short loc_18001BFFE
0x18001bfb0  mov     rdx, [rdi+68h]; pclsid
0x18001bfb4  mov     rcx, qword ptr [rsp+98h+pvarg+8]; lpsz
0x18001bfb9  call    cs:__imp_CLSIDFromString
0x18001bfbf  mov     ebx, eax
0x18001bfc1  test    eax, eax
0x18001bfc3  jns     short loc_18001BFF1
0x18001bfc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfcc  cmp     rcx, r12
0x18001bfcf  jz      short loc_18001BFF1
0x18001bfd1  test    byte ptr [rcx+1Ch], 8
0x18001bfd5  jz      short loc_18001BFF1
0x18001bfd7  cmp     byte ptr [rcx+19h], 2
0x18001bfdb  jb      short loc_18001BFF1
0x18001bfdd  mov     rcx, [rcx+10h]
0x18001bfe1  mov     edx, 12Fh
0x18001bfe6  mov     r9d, eax
0x18001bfe9  mov     r8, r13
0x18001bfec  call    WPP_SF_d
0x18001bff1  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18001bff6  call    cs:__imp_VariantClear
0x18001bffc  test    ebx, ebx
0x18001bffe  jns     short loc_18001C017
0x18001c000  mov     rcx, [rdi+68h]; pv
0x18001c004  test    rcx, rcx
0x18001c007  jz      short loc_18001C017
0x18001c009  call    cs:__imp_CoTaskMemFree
0x18001c00f  mov     qword ptr [rdi+68h], 0
0x18001c017  test    ebx, ebx
0x18001c019  jnz     short loc_18001C022
0x18001c01b  mov     rax, [rdi+68h]
0x18001c01f  mov     [r14], rax
0x18001c022  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001c026  call    cs:__imp_LeaveCriticalSection
0x18001c02c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c033  cmp     rcx, r12
0x18001c036  jz      short loc_18001C058
0x18001c038  test    byte ptr [rcx+1Ch], 8
0x18001c03c  jz      short loc_18001C058
0x18001c03e  cmp     byte ptr [rcx+19h], 6
0x18001c042  jb      short loc_18001C058
0x18001c044  mov     rcx, [rcx+10h]
0x18001c048  mov     edx, 130h
0x18001c04d  mov     r9d, ebx
0x18001c050  mov     r8, r13
0x18001c053  call    WPP_SF_d
0x18001c058  mov     eax, ebx
0x18001c05a  add     rsp, 68h
0x18001c05e  pop     r14
0x18001c060  pop     r13
0x18001c062  pop     r12
0x18001c064  pop     rdi
0x18001c065  pop     rsi
0x18001c066  pop     rbx
0x18001c067  retn
```
