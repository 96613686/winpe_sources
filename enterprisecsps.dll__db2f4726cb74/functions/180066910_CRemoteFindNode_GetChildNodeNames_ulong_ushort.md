# CRemoteFindNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180066910`
- end: `0x180066ada`
- name: `?GetChildNodeNames@CRemoteFindNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(CRemoteFindNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180066910`
- `0x1800d6ed0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800669f2`
- `OLEAUT32!__imp_SysAllocString` at `0x180066a72`
- `OLEAUT32!__imp_SysAllocString` at `0x1800669f2`
- `OLEAUT32!__imp_SysAllocString` at `0x180066a72`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800669b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066a41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800669b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066a41`

## pseudocode

```c
__int64 __fastcall CRemoteFindNode::GetChildNodeNames(CRemoteFindNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  int i; // edi
  __int64 v6; // r14
  _QWORD *v7; // rsi
  _OWORD *v8; // rax
  BSTR v9; // rax
  _OWORD *v10; // rax
  BSTR v11; // rax
  __int64 v12; // rbx
  OLECHAR *psz; // [rsp+20h] [rbp-30h]
  const wchar_t *v15; // [rsp+28h] [rbp-28h]
  const wchar_t *v16; // [rsp+30h] [rbp-20h]
  const wchar_t *v17; // [rsp+38h] [rbp-18h]
  const wchar_t *v18; // [rsp+40h] [rbp-10h]
  const wchar_t *v19; // [rsp+48h] [rbp-8h]

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  i = 0;
  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( !*((_DWORD *)this + 11) )
  {
    psz = L"DesiredAccuracy";
    v15 = L"MaximumAge";
    v16 = L"Timeout";
    v17 = L"Location";
    v10 = CoTaskMemAlloc(0x20u);
    v7 = v10;
    if ( v10 )
    {
      *v10 = 0;
      v10[1] = 0;
      while ( (unsigned int)v6 < 4 )
      {
        v11 = SysAllocString((&psz)[v6]);
        v7[v6] = v11;
        if ( !v11 )
        {
LABEL_18:
          v12 = 0;
          for ( i = -2147024882; (unsigned int)v12 < (unsigned int)v6; v12 = (unsigned int)(v12 + 1) )
            SysFreeString((BSTR)v7[v12]);
          CoTaskMemFree(v7);
          return (unsigned int)i;
        }
        v6 = (unsigned int)(v6 + 1);
      }
      goto LABEL_6;
    }
    return (unsigned int)-2147024882;
  }
  if ( *((_DWORD *)this + 11) == 4 )
  {
    psz = L"Latitude";
    v15 = L"Longitude";
    v16 = L"Altitude";
    v17 = L"Accuracy";
    v18 = L"AltitudeAccuracy";
    v19 = L"Age";
    v8 = CoTaskMemAlloc(0x30u);
    v7 = v8;
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      v8[2] = 0;
      while ( (unsigned int)v6 < 6 )
      {
        v9 = SysAllocString((&psz)[v6]);
        v7[v6] = v9;
        if ( !v9 )
          goto LABEL_18;
        v6 = (unsigned int)(v6 + 1);
      }
      goto LABEL_6;
    }
    return (unsigned int)-2147024882;
  }
  v7 = 0;
  i = CCSPNodeImpl::GetChildNodeNames(this, a2, a3);
  if ( i >= 0 )
  {
LABEL_6:
    *a3 = (unsigned __int16 **)v7;
    *a2 = v6;
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180066910  push    rbp
0x180066912  push    rbx
0x180066913  push    rsi
0x180066914  push    rdi
0x180066915  push    r12
0x180066917  push    r14
0x180066919  push    r15
0x18006691b  mov     rbp, rsp
0x18006691e  sub     rsp, 50h
0x180066922  mov     r15, r8
0x180066925  mov     r12, rdx
0x180066928  test    rdx, rdx
0x18006692b  jz      loc_180066AC3
0x180066931  test    r8, r8
0x180066934  jz      loc_180066AC3
0x18006693a  xor     edi, edi
0x18006693c  xor     r14d, r14d
0x18006693f  mov     [rdx], edi
0x180066941  mov     [r8], rdi
0x180066944  cmp     [rcx+2Ch], edi
0x180066947  jz      loc_180066A10
0x18006694d  cmp     dword ptr [rcx+2Ch], 4
0x180066951  jz      short loc_180066970
0x180066953  xor     esi, esi
0x180066955  call    ?GetChildNodeNames@CCSPNodeImpl@@UEAAJPEAKPEAPEAPEAG@Z; CCSPNodeImpl::GetChildNodeNames(ulong *,ushort * * *)
0x18006695a  mov     edi, eax
0x18006695c  test    eax, eax
0x18006695e  js      loc_180066AC8
0x180066964  mov     [r15], rsi
0x180066967  mov     [r12], r14d
0x18006696b  jmp     loc_180066AC8
0x180066970  lea     rax, aLatitude; "Latitude"
0x180066977  mov     ecx, 30h ; '0'; cb
0x18006697c  mov     [rbp+psz], rax
0x180066980  lea     rax, aLongitude; "Longitude"
0x180066987  mov     [rbp+var_28], rax
0x18006698b  lea     rax, aAltitude; "Altitude"
0x180066992  mov     [rbp+var_20], rax
0x180066996  lea     rax, aAccuracy; "Accuracy"
0x18006699d  mov     [rbp+var_18], rax
0x1800669a1  lea     rax, aAltitudeaccura; "AltitudeAccuracy"
0x1800669a8  mov     [rbp+var_10], rax
0x1800669ac  lea     rax, aAge; "Age"
0x1800669b3  mov     [rbp+var_8], rax
0x1800669b7  call    cs:__imp_CoTaskMemAlloc
0x1800669be  nop     dword ptr [rax+rax+00h]
0x1800669c3  mov     rsi, rax
0x1800669c6  test    rax, rax
0x1800669c9  jnz     short loc_1800669D5
0x1800669cb  mov     edi, 8007000Eh
0x1800669d0  jmp     loc_180066AC8
0x1800669d5  xorps   xmm0, xmm0
0x1800669d8  movups  xmmword ptr [rax], xmm0
0x1800669db  movups  xmmword ptr [rax+10h], xmm0
0x1800669df  movups  xmmword ptr [rax+20h], xmm0
0x1800669e3  cmp     r14d, 6
0x1800669e7  jnb     loc_180066964
0x1800669ed  mov     rcx, [rbp+r14*8+psz]; psz
0x1800669f2  call    cs:__imp_SysAllocString
0x1800669f9  nop     dword ptr [rax+rax+00h]
0x1800669fe  mov     [rsi+r14*8], rax
0x180066a02  test    rax, rax
0x180066a05  jz      loc_180066A8C
0x180066a0b  inc     r14d
0x180066a0e  jmp     short loc_1800669E3
0x180066a10  lea     rax, aDesiredaccurac; "DesiredAccuracy"
0x180066a17  mov     ecx, 20h ; ' '; cb
0x180066a1c  mov     [rbp+psz], rax
0x180066a20  lea     rax, aMaximumage; "MaximumAge"
0x180066a27  mov     [rbp+var_28], rax
0x180066a2b  lea     rax, aTimeout; "Timeout"
0x180066a32  mov     [rbp+var_20], rax
0x180066a36  lea     rax, aLocation; "Location"
0x180066a3d  mov     [rbp+var_18], rax
0x180066a41  call    cs:__imp_CoTaskMemAlloc
0x180066a48  nop     dword ptr [rax+rax+00h]
0x180066a4d  mov     rsi, rax
0x180066a50  test    rax, rax
0x180066a53  jz      loc_1800669CB
0x180066a59  xorps   xmm0, xmm0
0x180066a5c  movups  xmmword ptr [rax], xmm0
0x180066a5f  movups  xmmword ptr [rax+10h], xmm0
0x180066a63  cmp     r14d, 4
0x180066a67  jnb     loc_180066964
0x180066a6d  mov     rcx, [rbp+r14*8+psz]; psz
0x180066a72  call    cs:__imp_SysAllocString
0x180066a79  nop     dword ptr [rax+rax+00h]
0x180066a7e  mov     [rsi+r14*8], rax
0x180066a82  test    rax, rax
0x180066a85  jz      short loc_180066A8C
0x180066a87  inc     r14d
0x180066a8a  jmp     short loc_180066A63
0x180066a8c  xor     ebx, ebx
0x180066a8e  mov     r15, rsi
0x180066a91  mov     edi, 8007000Eh
0x180066a96  test    r14d, r14d
0x180066a99  jz      short loc_180066AB2
0x180066a9b  mov     rcx, [r15+rbx*8]; bstrString
0x180066a9f  call    cs:__imp_SysFreeString
0x180066aa6  nop     dword ptr [rax+rax+00h]
0x180066aab  inc     ebx
0x180066aad  cmp     ebx, r14d
0x180066ab0  jb      short loc_180066A9B
0x180066ab2  mov     rcx, rsi; pv
0x180066ab5  call    cs:__imp_CoTaskMemFree
0x180066abc  nop     dword ptr [rax+rax+00h]
0x180066ac1  jmp     short loc_180066AC8
0x180066ac3  mov     edi, 80070057h
0x180066ac8  mov     eax, edi
0x180066aca  add     rsp, 50h
0x180066ace  pop     r15
0x180066ad0  pop     r14
0x180066ad2  pop     r12
0x180066ad4  pop     rdi
0x180066ad5  pop     rsi
0x180066ad6  pop     rbx
0x180066ad7  pop     rbp
0x180066ad8  retn
```
