# FwLuidToInterfaceNameBstr(_IP_ADAPTER_ADDRESSES_LH *,_GUID const *,ushort * *)

- ea: `0x18003203c`
- end: `0x180032255`
- name: `?FwLuidToInterfaceNameBstr@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@PEBU_GUID@@PEAPEAG@Z`
- size: `537`
- prototype: `int(struct _IP_ADAPTER_ADDRESSES_LH *, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003225c`

## callees

- `0x180005e0c`
- `0x180024cb0`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003203c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800320fc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800321e8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800320fc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800321e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003222c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003222c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800321b2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800321b2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800320ca`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800320ca`

## pseudocode

```c
__int64 __fastcall FwLuidToInterfaceNameBstr(
        struct _IP_ADAPTER_ADDRESSES_LH *a1,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rax
  unsigned __int16 *v8; // rax
  __int64 v9; // r9
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  LPOLESTR lpsz; // [rsp+20h] [rbp-49h] BYREF
  GUID pclsid; // [rsp+28h] [rbp-41h] BYREF
  wchar_t pszDest; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v17[78]; // [rsp+42h] [rbp-27h] BYREF

  lpsz = 0;
  *a3 = 0;
  pclsid = GUID_NULL;
  while ( 1 )
  {
    if ( !a1 )
    {
      v6 = StringFromCLSID(a2, &lpsz);
      if ( v6 >= 0 )
      {
        v12 = SysAllocString(lpsz);
        *a3 = v12;
        if ( v12 )
        {
          CoTaskMemFree(lpsz);
        }
        else
        {
          v9 = 2147942414LL;
          v6 = -2147024882;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 59;
            goto LABEL_20;
          }
        }
        return (unsigned int)v6;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v6;
      v11 = 58;
LABEL_19:
      v9 = (unsigned int)v6;
      goto LABEL_20;
    }
    pszDest = 0;
    memset_0(v17, 0, sizeof(v17));
    v6 = StringCchPrintfW(&pszDest, 0x27u, L"%S", a1->AdapterName, lpsz);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v6;
      v11 = 55;
      goto LABEL_19;
    }
    v6 = CLSIDFromString(&pszDest, &pclsid);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v6;
      v11 = 56;
      goto LABEL_19;
    }
    v7 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a2->Data1 )
      v7 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a2->Data4;
    if ( !v7 )
      break;
    a1 = a1->Next;
  }
  v8 = SysAllocString(a1->FriendlyName);
  *a3 = v8;
  if ( !v8 )
  {
    v9 = 2147942414LL;
    v6 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 57;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v9);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003203c  push    rbp
0x18003203e  push    rbx
0x18003203f  push    rsi
0x180032040  push    rdi
0x180032041  push    r14
0x180032043  lea     rbp, [rsp-37h]
0x180032048  sub     rsp, 0A0h
0x18003204f  mov     rax, cs:__security_cookie
0x180032056  xor     rax, rsp
0x180032059  mov     [rbp+57h+var_30], rax
0x18003205d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032064  mov     r14, r8
0x180032067  mov     [rbp+57h+lpsz], 0
0x18003206f  mov     rsi, rdx
0x180032072  mov     qword ptr [r8], 0
0x180032079  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18003207e  mov     rdi, rcx
0x180032081  test    rdi, rdi
0x180032084  jz      loc_1800321AB
0x18003208a  xor     eax, eax
0x18003208c  lea     rcx, [rbp+57h+var_7E]; void *
0x180032090  xor     edx, edx; Val
0x180032092  mov     [rbp+57h+pszDest], ax
0x180032096  lea     r8d, [rax+4Eh]; Size
0x18003209a  call    memset_0
0x18003209f  mov     r9, [rdi+10h]
0x1800320a3  lea     r8, aS_0; "%S"
0x1800320aa  mov     edx, 27h ; '''; cchDest
0x1800320af  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800320b3  call    StringCchPrintfW
0x1800320b8  mov     ebx, eax
0x1800320ba  test    eax, eax
0x1800320bc  js      loc_18003216D
0x1800320c2  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800320c6  lea     rcx, [rbp+57h+pszDest]; lpsz
0x1800320ca  call    cs:__imp_CLSIDFromString
0x1800320d1  nop     dword ptr [rax+rax+00h]
0x1800320d6  mov     ebx, eax
0x1800320d8  test    eax, eax
0x1800320da  js      short loc_180032145
0x1800320dc  mov     rax, qword ptr [rbp+57h+pclsid.Data1]
0x1800320e0  sub     rax, [rsi]
0x1800320e3  jnz     short loc_1800320ED
0x1800320e5  mov     rax, qword ptr [rbp+57h+pclsid.Data4]
0x1800320e9  sub     rax, [rsi+8]
0x1800320ed  test    rax, rax
0x1800320f0  jz      short loc_1800320F8
0x1800320f2  mov     rdi, [rdi+8]
0x1800320f6  jmp     short loc_180032081
0x1800320f8  mov     rcx, [rdi+48h]; psz
0x1800320fc  call    cs:__imp_SysAllocString
0x180032103  nop     dword ptr [rax+rax+00h]
0x180032108  mov     [r14], rax
0x18003210b  test    rax, rax
0x18003210e  jnz     loc_180032238
0x180032114  mov     r9d, 8007000Eh
0x18003211a  mov     ebx, r9d
0x18003211d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032124  lea     rax, WPP_GLOBAL_Control
0x18003212b  cmp     rcx, rax
0x18003212e  jz      loc_180032238
0x180032134  test    byte ptr [rcx+1Ch], 1
0x180032138  jz      loc_180032238
0x18003213e  mov     edx, 39h ; '9'
0x180032143  jmp     short loc_180032196
0x180032145  mov     rcx, cs:WPP_GLOBAL_Control
0x18003214c  lea     rax, WPP_GLOBAL_Control
0x180032153  cmp     rcx, rax
0x180032156  jz      loc_180032238
0x18003215c  test    byte ptr [rcx+1Ch], 1
0x180032160  jz      loc_180032238
0x180032166  mov     edx, 38h ; '8'
0x18003216b  jmp     short loc_180032193
0x18003216d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032174  lea     rax, WPP_GLOBAL_Control
0x18003217b  cmp     rcx, rax
0x18003217e  jz      loc_180032238
0x180032184  test    byte ptr [rcx+1Ch], 1
0x180032188  jz      loc_180032238
0x18003218e  mov     edx, 37h ; '7'
0x180032193  mov     r9d, ebx
0x180032196  mov     rcx, [rcx+10h]
0x18003219a  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800321a1  call    WPP_SF_d
0x1800321a6  jmp     loc_180032238
0x1800321ab  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800321af  mov     rcx, rsi; rclsid
0x1800321b2  call    cs:__imp_StringFromCLSID
0x1800321b9  nop     dword ptr [rax+rax+00h]
0x1800321be  mov     ebx, eax
0x1800321c0  test    eax, eax
0x1800321c2  jns     short loc_1800321E4
0x1800321c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321cb  lea     rax, WPP_GLOBAL_Control
0x1800321d2  cmp     rcx, rax
0x1800321d5  jz      short loc_180032238
0x1800321d7  test    byte ptr [rcx+1Ch], 1
0x1800321db  jz      short loc_180032238
0x1800321dd  mov     edx, 3Ah ; ':'
0x1800321e2  jmp     short loc_180032193
0x1800321e4  mov     rcx, [rbp+57h+lpsz]; psz
0x1800321e8  call    cs:__imp_SysAllocString
0x1800321ef  nop     dword ptr [rax+rax+00h]
0x1800321f4  mov     [r14], rax
0x1800321f7  test    rax, rax
0x1800321fa  jnz     short loc_180032228
0x1800321fc  mov     r9d, 8007000Eh
0x180032202  mov     ebx, r9d
0x180032205  mov     rcx, cs:WPP_GLOBAL_Control
0x18003220c  lea     rax, WPP_GLOBAL_Control
0x180032213  cmp     rcx, rax
0x180032216  jz      short loc_180032238
0x180032218  test    byte ptr [rcx+1Ch], 1
0x18003221c  jz      short loc_180032238
0x18003221e  mov     edx, 3Bh ; ';'
0x180032223  jmp     loc_180032196
0x180032228  mov     rcx, [rbp+57h+lpsz]; pv
0x18003222c  call    cs:__imp_CoTaskMemFree
0x180032233  nop     dword ptr [rax+rax+00h]
0x180032238  mov     eax, ebx
0x18003223a  mov     rcx, [rbp+57h+var_30]
0x18003223e  xor     rcx, rsp; StackCookie
0x180032241  call    __security_check_cookie
0x180032246  add     rsp, 0A0h
0x18003224d  pop     r14
0x18003224f  pop     rdi
0x180032250  pop     rsi
0x180032251  pop     rbx
0x180032252  pop     rbp
0x180032253  retn
```
