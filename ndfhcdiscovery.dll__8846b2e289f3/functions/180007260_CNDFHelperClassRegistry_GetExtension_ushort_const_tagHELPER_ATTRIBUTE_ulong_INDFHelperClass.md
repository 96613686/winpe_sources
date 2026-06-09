# CNDFHelperClassRegistry::GetExtension(ushort const *,tagHELPER_ATTRIBUTE *,ulong,INDFHelperClass * *)

- ea: `0x180007260`
- end: `0x180007437`
- name: `?GetExtension@CNDFHelperClassRegistry@@UEAAJPEBGPEAUtagHELPER_ATTRIBUTE@@KPEAPEAUINDFHelperClass@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, LPCWSTR lpString1, struct tagHELPER_ATTRIBUTE *, unsigned int, struct INDFHelperClass **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006a6c`
- `0x180007260`
- `0x180007a20`
- `0x18000b0cc`
- `0x18000fff8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800072b0`
- `KERNEL32!EnterCriticalSection` at `0x1800072b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800072d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800072f6`
- `KERNEL32!LeaveCriticalSection` at `0x1800072d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800072f6`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::GetExtension(
        __int64 **this,
        LPCWSTR lpString1,
        struct tagHELPER_ATTRIBUTE *a3,
        unsigned int a4,
        struct INDFHelperClass **a5)
{
  struct INDFHelperClass **v9; // r15
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  int v11; // edi
  __int64 result; // rax
  __int64 v13; // rcx
  int v14; // edx
  int v15; // edi
  __int64 v16; // rbx
  int IsExtensionOf; // eax
  __int64 i; // rax
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+78h] [rbp+10h] BYREF

  if ( !lpString1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v9 = a5;
  if ( !a5 )
    return 2147942487LL;
  v10 = (struct _RTL_CRITICAL_SECTION *)(this + 82);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 82));
  try
  {
    if ( !*((_DWORD *)this + 158) )
    {
      v11 = CNDFHelperClassRegistry::InitializeData((CNDFHelperClassRegistry *)this);
      if ( v11 < 0 )
      {
        LeaveCriticalSection(v10);
        return (unsigned int)v11;
      }
      *((_DWORD *)this + 158) = 1;
    }
    LeaveCriticalSection(v10);
    v14 = 0;
    v15 = 0;
    v20 = 0;
    v16 = *this[75];
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( (__int64 *)v16 == this[75] )
          {
            if ( v14 >= 0 && !v15 )
            {
              if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
                McTemplateU0qqz_EventWriteTransfer(
                  v13,
                  (unsigned int)ExtensionError,
                  -2147024894,
                  464,
                  (__int64)lpString1);
              return (unsigned int)-2147024894;
            }
            return (unsigned int)v14;
          }
          IsExtensionOf = CNDFHelperClass::IsExtensionOf(*(CNDFHelperClass **)(v16 + 64), lpString1, a3, a4, &v20);
          v14 = IsExtensionOf;
          v15 = v20;
          if ( IsExtensionOf >= 0 )
          {
            if ( v20 )
            {
              v19 = 0;
              v14 = ATL::CComCreator<ATL::CComObject<CINDFHelperClassImpl>>::CreateInstance(
                      v13,
                      (unsigned int)IsExtensionOf,
                      &v19);
              if ( v14 >= 0 )
              {
                v13 = *(_QWORD *)(v16 + 64);
                *(_QWORD *)(v19 + 64) = v13;
                *v9 = (struct INDFHelperClass *)v19;
              }
            }
          }
        }
        while ( *(_BYTE *)(v16 + 25) );
        i = *(_QWORD *)(v16 + 16);
        if ( !*(_BYTE *)(i + 25) )
          break;
        for ( i = *(_QWORD *)(v16 + 8); !*(_BYTE *)(i + 25) && v16 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v16 = i;
LABEL_30:
        v16 = i;
      }
      v13 = *(_QWORD *)i;
      if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
        goto LABEL_30;
      do
      {
        v16 = v13;
        v13 = *(_QWORD *)v13;
      }
      while ( !*(_BYTE *)(v13 + 25) );
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( exception )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007260  mov     [rsp+arg_0], rbx
0x180007265  mov     [rsp+arg_10], rsi
0x18000726a  push    rdi
0x18000726b  push    r12
0x18000726d  push    r13
0x18000726f  push    r14
0x180007271  push    r15
0x180007273  sub     rsp, 40h
0x180007277  mov     r13d, r9d
0x18000727a  mov     r12, r8
0x18000727d  mov     r14, rdx
0x180007280  mov     rsi, rcx
0x180007283  test    rdx, rdx
0x180007286  jz      loc_180007417
0x18000728c  test    r8, r8
0x18000728f  jz      loc_180007417
0x180007295  mov     r15, [rsp+68h+arg_20]
0x18000729d  test    r15, r15
0x1800072a0  jz      loc_180007417
0x1800072a6  lea     rbx, [rcx+290h]
0x1800072ad  mov     rcx, rbx; lpCriticalSection
0x1800072b0  call    cs:__imp_EnterCriticalSection
0x1800072b7  nop     dword ptr [rax+rax+00h]
0x1800072bc  cmp     dword ptr [rsi+278h], 0
0x1800072c3  jnz     short loc_1800072F3
0x1800072c5  mov     rcx, rsi; this
0x1800072c8  call    ?InitializeData@CNDFHelperClassRegistry@@AEAAJXZ; CNDFHelperClassRegistry::InitializeData(void)
0x1800072cd  mov     edi, eax
0x1800072cf  test    eax, eax
0x1800072d1  jns     short loc_1800072E9
0x1800072d3  mov     rcx, rbx; lpCriticalSection
0x1800072d6  call    cs:__imp_LeaveCriticalSection
0x1800072dd  nop     dword ptr [rax+rax+00h]
0x1800072e2  mov     eax, edi
0x1800072e4  jmp     loc_18000741C
0x1800072e9  mov     dword ptr [rsi+278h], 1
0x1800072f3  mov     rcx, rbx; lpCriticalSection
0x1800072f6  call    cs:__imp_LeaveCriticalSection
0x1800072fd  nop     dword ptr [rax+rax+00h]
0x180007302  xor     r8d, r8d
0x180007305  mov     edx, r8d
0x180007308  mov     edi, r8d
0x18000730b  mov     [rsp+68h+arg_8], r8d
0x180007310  mov     rbx, [rsi+258h]
0x180007317  mov     rbx, [rbx]
0x18000731a  cmp     rbx, [rsi+258h]
0x180007321  jnz     short loc_18000735D
0x180007323  test    edx, edx
0x180007325  js      short loc_180007356
0x180007327  test    edi, edi
0x180007329  jnz     short loc_180007356
0x18000732b  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x180007332  jz      short loc_180007351
0x180007334  mov     [rsp+68h+var_48], r14
0x180007339  mov     r9d, 1D0h
0x18000733f  mov     r8d, 80070002h
0x180007345  lea     rdx, ExtensionError
0x18000734c  call    McTemplateU0qqz_EventWriteTransfer
0x180007351  mov     edx, 80070002h
0x180007356  mov     eax, edx
0x180007358  jmp     loc_18000741C
0x18000735d  lea     rax, [rsp+68h+arg_8]
0x180007362  mov     [rsp+68h+var_48], rax; int *
0x180007367  mov     r9d, r13d; unsigned int
0x18000736a  mov     r8, r12; struct tagHELPER_ATTRIBUTE *
0x18000736d  mov     rdx, r14; lpString1
0x180007370  mov     rcx, [rbx+40h]; this
0x180007374  call    ?IsExtensionOf@CNDFHelperClass@@QEAAJPEBGPEAUtagHELPER_ATTRIBUTE@@KPEAH@Z; CNDFHelperClass::IsExtensionOf(ushort const *,tagHELPER_ATTRIBUTE *,ulong,int *)
0x180007379  mov     edx, eax
0x18000737b  xor     r8d, r8d
0x18000737e  mov     edi, [rsp+68h+arg_8]
0x180007382  test    eax, eax
0x180007384  js      short loc_1800073B7
0x180007386  test    edi, edi
0x180007388  jz      short loc_1800073B7
0x18000738a  mov     [rsp+68h+var_38], r8
0x18000738f  lea     r8, [rsp+68h+var_38]
0x180007394  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCINDFHelperClassImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CINDFHelperClassImpl>>::CreateInstance(void *,_GUID const &,void * *)
0x180007399  mov     edx, eax
0x18000739b  xor     r8d, r8d
0x18000739e  test    eax, eax
0x1800073a0  js      short loc_1800073B7
0x1800073a2  mov     rcx, [rbx+40h]
0x1800073a6  mov     rax, [rsp+68h+var_38]
0x1800073ab  mov     [rax+40h], rcx
0x1800073af  mov     rax, [rsp+68h+var_38]
0x1800073b4  mov     [r15], rax
0x1800073b7  cmp     [rbx+19h], r8b
0x1800073bb  jnz     loc_18000731A
0x1800073c1  mov     rax, [rbx+10h]
0x1800073c5  cmp     [rax+19h], r8b
0x1800073c9  jnz     short loc_1800073E8
0x1800073cb  mov     rcx, [rax]
0x1800073ce  cmp     [rcx+19h], r8b
0x1800073d2  jnz     short loc_180007401
0x1800073d4  mov     rbx, rcx
0x1800073d7  mov     rax, [rcx]
0x1800073da  mov     rcx, rax
0x1800073dd  cmp     [rax+19h], r8b
0x1800073e1  jz      short loc_1800073D4
0x1800073e3  jmp     loc_18000731A
0x1800073e8  mov     rax, [rbx+8]
0x1800073ec  jmp     short loc_1800073FB
0x1800073ee  cmp     rbx, [rax+10h]
0x1800073f2  jnz     short loc_180007401
0x1800073f4  mov     rbx, rax
0x1800073f7  mov     rax, [rax+8]
0x1800073fb  cmp     [rax+19h], r8b
0x1800073ff  jz      short loc_1800073EE
0x180007401  mov     rbx, rax
0x180007404  jmp     loc_18000731A
0x180007409  mov     eax, 8007000Eh
0x18000740e  jmp     short loc_180007415
0x180007410  mov     eax, 80004005h
0x180007415  jmp     short loc_18000741C
0x180007417  mov     eax, 80070057h
0x18000741c  lea     r11, [rsp+68h+var_28]
0x180007421  mov     rbx, [r11+30h]
0x180007425  mov     rsi, [r11+40h]
0x180007429  mov     rsp, r11
0x18000742c  pop     r15
0x18000742e  pop     r14
0x180007430  pop     r13
0x180007432  pop     r12
0x180007434  pop     rdi
0x180007435  retn
```
