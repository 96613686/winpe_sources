# RegistryRegRow::GetPropertyBag(ushort const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180026820`
- end: `0x180026b42`
- name: `?GetPropertyBag@RegistryRegRow@@UEAAJPEBGPEAUtagPROPVARIANT@@1@Z`
- size: `802`
- prototype: `int(RegistryRegRow *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006194`
- `0x180008fbc`
- `0x18000c910`
- `0x180026820`
- `0x18003b74c`
- `0x1800434c6`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026995`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026995`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800269ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800269ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026af2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026af2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026a7e`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::GetPropertyBag(
        RegistryRegRow *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  unsigned int v8; // esi
  unsigned __int16 *p_cValues; // rdi
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  unsigned __int16 *v13; // rax
  signed int v14; // ebx
  LSTATUS v15; // eax
  bool v16; // cc
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned int v20; // ebx
  unsigned int v21; // esi
  BYTE *v22; // rax
  BYTE *v23; // rax
  size_t v24; // r8
  DWORD v25; // esi
  signed int Property; // eax
  __int64 v28; // [rsp+0h] [rbp-60h] BYREF
  DWORD cValues; // [rsp+60h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+8h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp+10h]
  struct _FILETIME ftLastWriteTime; // [rsp+78h] [rbp+18h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  hKey = 0;
  cValues = 0;
  ftLastWriteTime = 0;
  v31 = *((_DWORD *)this + 35) + 2 + (unsigned int)safe_lstrlenW(a2);
  v8 = 2 * v31;
  if ( 2 * v31 > 0xFFFFFFFF )
    return 2147942934LL;
  p_cValues = 0;
  if ( !v8
    || v8 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)v8 + g_ulAdditionalProbeSize + 8 < v8
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_47;
  }
  v10 = v8 + 23LL;
  if ( v10 <= (unsigned __int64)v8 + 8 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
  v12 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
  p_cValues = (unsigned __int16 *)&cValues;
  if ( &v28 == (__int64 *)-96LL || (cValues = 1801679955, (p_cValues = (unsigned __int16 *)&hKey) == 0) )
  {
LABEL_47:
    if ( (unsigned __int64)v8 + 8 >= v8 )
    {
      v13 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
      p_cValues = v13;
      if ( v13 )
      {
        *(_DWORD *)v13 = 1885431112;
        p_cValues = v13 + 4;
      }
    }
  }
  if ( !p_cValues )
  {
LABEL_17:
    v14 = -2147024882;
    goto LABEL_37;
  }
  v14 = StringCchPrintfW(p_cValues, v31, L"%s\\%s", *((_QWORD *)this + 15), a2);
  if ( v14 >= 0 )
  {
    v15 = RegOpenKeyExW(*((HKEY *)this + 16), p_cValues, 0, 0x20019u, &hKey);
    if ( v15 == 2 )
    {
      v14 = 1;
      goto LABEL_37;
    }
    v16 = v15 <= 0;
    if ( v15
      || (v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, &ftLastWriteTime), v16 = v15 <= 0, v15) )
    {
      if ( v16 )
        v14 = v15;
      else
        v14 = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_37;
    }
    v17 = cValues;
    if ( cValues )
    {
      a3->lVal = cValues;
      v18 = (unsigned int)v17;
      v19 = 8 * v17;
      a3->vt = 4127;
      if ( v19 > 0xFFFFFFFF || (v20 = 24 * v18, (unsigned __int64)(24 * v18) > 0xFFFFFFFF) )
      {
        v14 = -2147024362;
        goto LABEL_37;
      }
      v21 = v19;
      v22 = (BYTE *)CoTaskMemAlloc((unsigned int)v19);
      a3->bstrblobVal.pData = v22;
      if ( v22 )
      {
        memset_0(v22, 0, v21);
        a4->lVal = cValues;
        a4->vt = 4108;
        v23 = (BYTE *)CoTaskMemAlloc(v20);
        a4->bstrblobVal.pData = v23;
        if ( v23 )
        {
          v24 = v20;
          v14 = 0;
          memset_0(v23, 0, v24);
          v25 = 0;
          if ( cValues )
          {
            do
            {
              Property = ReadProperty(
                           hKey,
                           v25,
                           (unsigned __int16 **)&a3->bstrblobVal.pData[8 * v25],
                           (struct tagPROPVARIANT *)&a4->bstrblobVal.pData[24 * v25]);
              v14 = Property;
              if ( Property )
                break;
              ++v25;
            }
            while ( v25 < cValues );
            if ( Property == 1 )
              v14 = 0;
          }
          goto LABEL_37;
        }
      }
      goto LABEL_17;
    }
  }
LABEL_37:
  if ( hKey )
    RegCloseKey(hKey);
  if ( p_cValues )
  {
    if ( *((_DWORD *)p_cValues - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180026820  push    rbp
0x180026822  push    rbx
0x180026823  push    rsi
0x180026824  push    rdi
0x180026825  push    r12
0x180026827  push    r13
0x180026829  push    r14
0x18002682b  push    r15
0x18002682d  sub     rsp, 98h
0x180026834  lea     rbp, [rsp+60h]
0x180026839  mov     rax, cs:__security_cookie
0x180026840  xor     rax, rbp
0x180026843  mov     [rbp+70h+var_48], rax
0x180026847  mov     r12, r9
0x18002684a  mov     r14, r8
0x18002684d  mov     r15, rdx
0x180026850  mov     r13, rcx
0x180026853  test    rdx, rdx
0x180026856  jz      loc_180026B20
0x18002685c  test    r8, r8
0x18002685f  jz      loc_180026B20
0x180026865  test    r9, r9
0x180026868  jz      loc_180026B20
0x18002686e  mov     rcx, rdx; unsigned __int16 *
0x180026871  mov     [rbp+70h+hKey], 0
0x180026879  mov     [rbp+70h+cValues], 0
0x180026880  mov     qword ptr [rbp+70h+ftLastWriteTime.dwLowDateTime], 0
0x180026888  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002688d  mov     ecx, [r13+8Ch]
0x180026894  add     ecx, 2
0x180026897  add     eax, ecx
0x180026899  mov     [rbp+70h+var_60], rax
0x18002689d  lea     rsi, [rax+rax]
0x1800268a1  mov     eax, 0FFFFFFFFh
0x1800268a6  cmp     rsi, rax
0x1800268a9  ja      loc_180026B19
0x1800268af  xor     edi, edi
0x1800268b1  test    esi, esi
0x1800268b3  jz      short loc_180026918
0x1800268b5  mov     ebx, esi
0x1800268b7  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800268be  ja      short loc_180026918
0x1800268c0  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800268c7  add     rcx, 8
0x1800268cb  add     rcx, rbx
0x1800268ce  cmp     rcx, rbx
0x1800268d1  jb      short loc_180026918
0x1800268d3  call    VerifyStackAvailable
0x1800268d8  test    eax, eax
0x1800268da  jz      short loc_180026918
0x1800268dc  lea     rax, [rbx+8]
0x1800268e0  lea     rcx, [rax+0Fh]
0x1800268e4  cmp     rcx, rax
0x1800268e7  ja      short loc_1800268F3
0x1800268e9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800268f3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800268f7  mov     rax, rcx
0x1800268fa  call    _alloca_probe
0x1800268ff  sub     rsp, rcx
0x180026902  lea     rdi, [rsp+0D0h+cValues]
0x180026907  test    rdi, rdi
0x18002690a  jz      short loc_180026918
0x18002690c  mov     dword ptr [rdi], 6B637453h
0x180026912  add     rdi, 8
0x180026916  jnz     short loc_180026941
0x180026918  mov     eax, esi
0x18002691a  lea     rcx, [rax+8]
0x18002691e  cmp     rcx, rax
0x180026921  jb      short loc_180026941
0x180026923  mov     rax, cs:g_pfnAllocate
0x18002692a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002692f  mov     rdi, rax
0x180026932  test    rax, rax
0x180026935  jz      short loc_180026941
0x180026937  mov     dword ptr [rax], 70616548h
0x18002693d  add     rdi, 8
0x180026941  test    rdi, rdi
0x180026944  jnz     short loc_180026950
0x180026946  mov     ebx, 8007000Eh
0x18002694b  jmp     loc_180026AE9
0x180026950  mov     r9, [r13+78h]
0x180026954  lea     r8, aSS; "%s\\%s"
0x18002695b  mov     rdx, [rbp+70h+var_60]; unsigned __int64
0x18002695f  mov     rcx, rdi; unsigned __int16 *
0x180026962  mov     [rsp+0D0h+phkResult], r15
0x180026967  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002696c  xor     r15d, r15d
0x18002696f  mov     ebx, eax
0x180026971  test    eax, eax
0x180026973  js      loc_180026AE9
0x180026979  mov     rcx, [r13+80h]; hKey
0x180026980  lea     rax, [rbp+70h+hKey]
0x180026984  mov     r9d, 20019h; samDesired
0x18002698a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002698f  xor     r8d, r8d; ulOptions
0x180026992  mov     rdx, rdi; lpSubKey
0x180026995  call    cs:__imp_RegOpenKeyExW
0x18002699b  cmp     eax, 2
0x18002699e  jnz     short loc_1800269A8
0x1800269a0  lea     ebx, [rax-1]
0x1800269a3  jmp     loc_180026AE9
0x1800269a8  test    eax, eax
0x1800269aa  jz      short loc_1800269C3
0x1800269ac  jg      short loc_1800269B5
0x1800269ae  mov     ebx, eax
0x1800269b0  jmp     loc_180026AE9
0x1800269b5  movzx   ebx, ax
0x1800269b8  or      ebx, 80070000h
0x1800269be  jmp     loc_180026AE9
0x1800269c3  mov     rcx, [rbp+70h+hKey]; hKey
0x1800269c7  lea     rax, [rbp+70h+ftLastWriteTime]
0x1800269cb  mov     [rsp+0D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800269d0  xor     r9d, r9d; lpReserved
0x1800269d3  mov     [rsp+0D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800269d8  lea     rax, [rbp+70h+cValues]
0x1800269dc  mov     [rsp+0D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800269e1  xor     r8d, r8d; lpcchClass
0x1800269e4  mov     [rsp+0D0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800269e9  xor     edx, edx; lpClass
0x1800269eb  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x1800269f0  mov     [rsp+0D0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800269f5  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800269fa  mov     [rsp+0D0h+phkResult], r15; lpcSubKeys
0x1800269ff  call    cs:__imp_RegQueryInfoKeyW
0x180026a05  test    eax, eax
0x180026a07  jnz     short loc_1800269AC
0x180026a09  mov     eax, [rbp+70h+cValues]
0x180026a0c  test    eax, eax
0x180026a0e  jz      loc_180026AE9
0x180026a14  mov     [r14+8], eax
0x180026a18  mov     ecx, eax
0x180026a1a  lea     rax, ds:0[rax*8]
0x180026a22  mov     word ptr [r14], 101Fh
0x180026a28  mov     edx, 0FFFFFFFFh
0x180026a2d  cmp     rax, rdx
0x180026a30  ja      loc_180026AE4
0x180026a36  lea     rbx, [rcx+rcx*2]
0x180026a3a  shl     rbx, 3
0x180026a3e  cmp     rbx, rdx
0x180026a41  ja      loc_180026AE4
0x180026a47  mov     ecx, eax; cb
0x180026a49  mov     esi, eax
0x180026a4b  call    cs:__imp_CoTaskMemAlloc
0x180026a51  mov     [r14+10h], rax
0x180026a55  test    rax, rax
0x180026a58  jz      loc_180026946
0x180026a5e  mov     r8d, esi; Size
0x180026a61  xor     edx, edx; Val
0x180026a63  mov     rcx, rax; void *
0x180026a66  call    memset_0
0x180026a6b  mov     eax, [rbp+70h+cValues]
0x180026a6e  mov     ecx, ebx; cb
0x180026a70  mov     [r12+8], eax
0x180026a75  mov     word ptr [r12], 100Ch
0x180026a7c  mov     esi, ebx
0x180026a7e  call    cs:__imp_CoTaskMemAlloc
0x180026a84  mov     [r12+10h], rax
0x180026a89  test    rax, rax
0x180026a8c  jz      loc_180026946
0x180026a92  mov     r8d, esi; Size
0x180026a95  xor     edx, edx; Val
0x180026a97  mov     rcx, rax; void *
0x180026a9a  mov     ebx, r15d
0x180026a9d  call    memset_0
0x180026aa2  mov     esi, r15d
0x180026aa5  cmp     [rbp+70h+cValues], r15d
0x180026aa9  jbe     short loc_180026AE9
0x180026aab  mov     rax, [r12+10h]
0x180026ab0  mov     edx, esi
0x180026ab2  lea     rcx, [rdx+rdx*2]
0x180026ab6  lea     r9, [rax+rcx*8]; struct tagPROPVARIANT *
0x180026aba  mov     rax, [r14+10h]
0x180026abe  mov     rcx, [rbp+70h+hKey]; hKey
0x180026ac2  lea     r8, [rax+rdx*8]; unsigned __int16 **
0x180026ac6  mov     edx, esi; unsigned int
0x180026ac8  call    ?ReadProperty@@YAJPEAUHKEY__@@KPEAPEAGPEAUtagPROPVARIANT@@@Z; ReadProperty(HKEY__ *,ulong,ushort * *,tagPROPVARIANT *)
0x180026acd  mov     ebx, eax
0x180026acf  test    eax, eax
0x180026ad1  jnz     short loc_180026ADA
0x180026ad3  inc     esi
0x180026ad5  cmp     esi, [rbp+70h+cValues]
0x180026ad8  jb      short loc_180026AAB
0x180026ada  cmp     eax, 1
0x180026add  jnz     short loc_180026AE9
0x180026adf  mov     ebx, r15d
0x180026ae2  jmp     short loc_180026AE9
0x180026ae4  mov     ebx, 80070216h
0x180026ae9  mov     rcx, [rbp+70h+hKey]; hKey
0x180026aed  test    rcx, rcx
0x180026af0  jz      short loc_180026AF8
0x180026af2  call    cs:__imp_RegCloseKey
0x180026af8  test    rdi, rdi
0x180026afb  jz      short loc_180026B15
0x180026afd  lea     rcx, [rdi-8]
0x180026b01  cmp     dword ptr [rcx], 70616548h
0x180026b07  jnz     short loc_180026B15
0x180026b09  mov     rax, cs:g_pfnFree
0x180026b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b15  mov     eax, ebx
0x180026b17  jmp     short loc_180026B25
0x180026b19  mov     eax, 80070216h
0x180026b1e  jmp     short loc_180026B25
0x180026b20  mov     eax, 80070057h
0x180026b25  mov     rcx, [rbp+70h+var_48]
0x180026b29  xor     rcx, rbp; StackCookie
0x180026b2c  call    __security_check_cookie
0x180026b31  lea     rsp, [rbp+38h]
0x180026b35  pop     r15
0x180026b37  pop     r14
0x180026b39  pop     r13
0x180026b3b  pop     r12
0x180026b3d  pop     rdi
0x180026b3e  pop     rsi
0x180026b3f  pop     rbx
0x180026b40  pop     rbp
0x180026b41  retn
```
