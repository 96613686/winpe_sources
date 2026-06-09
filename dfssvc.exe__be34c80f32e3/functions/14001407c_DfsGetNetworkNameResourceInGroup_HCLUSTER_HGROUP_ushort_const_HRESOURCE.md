# DfsGetNetworkNameResourceInGroup(_HCLUSTER *,_HGROUP *,ushort const *,_HRESOURCE * *)

- ea: `0x14001407c`
- end: `0x1400142b3`
- name: `?DfsGetNetworkNameResourceInGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEBGPEAPEAU_HRESOURCE@@@Z`
- size: `567`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, HGROUP hGroup, const unsigned __int16 *, struct _HRESOURCE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013ef4`

## callees

- `0x140012ed4`
- `0x14001407c`
- `0x1400148a4`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014221`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400141d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400141f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140014281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400141d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400141f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140014281`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x14001426b`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x14001426b`
- `CLUSAPI!OpenClusterResource` at `0x140014151`
- `CLUSAPI!OpenClusterResource` at `0x140014151`
- `CLUSAPI!ClusterGroupEnum` at `0x140014133`
- `CLUSAPI!ClusterGroupEnum` at `0x140014133`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x1400140ea`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x1400140ea`
- `CLUSAPI!CloseClusterResource` at `0x14001420d`
- `CLUSAPI!CloseClusterResource` at `0x14001423b`
- `CLUSAPI!CloseClusterResource` at `0x14001420d`
- `CLUSAPI!CloseClusterResource` at `0x14001423b`
- `RESUTILS!ResUtilFindSzProperty` at `0x1400141be`
- `RESUTILS!ResUtilFindSzProperty` at `0x1400141be`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x140014173`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x140014173`

## pseudocode

```c
__int64 __fastcall DfsGetNetworkNameResourceInGroup(
        HCLUSTER hCluster,
        HGROUP hGroup,
        unsigned __int16 *a3,
        struct _HRESOURCE **a4)
{
  DWORD ResourcePrivateProps; // ebx
  struct _HGROUPENUM *v5; // rsi
  struct _HRESOURCE *v6; // rdi
  DWORD v10; // r14d
  struct _HRESOURCE *v11; // rax
  LPWSTR pszPropertyValue; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwType; // [rsp+44h] [rbp-BCh] BYREF
  PVOID pPropertyList; // [rsp+48h] [rbp-B8h]
  WCHAR szResourceName[264]; // [rsp+50h] [rbp-B0h] BYREF

  ResourcePrivateProps = 0;
  v5 = 0;
  pszPropertyValue = 0;
  v6 = 0;
  if ( !hCluster || !hGroup || !a3 || !a4 )
  {
    ResourcePrivateProps = 87;
LABEL_25:
    v6 = 0;
    goto LABEL_26;
  }
  v5 = ClusterGroupOpenEnum(hGroup, 1u);
  if ( v5 )
  {
    v10 = 0;
    while ( !ResourcePrivateProps )
    {
      dwType = 0;
      cchName = 260;
      ResourcePrivateProps = ClusterGroupEnum(v5, v10, &dwType, szResourceName, &cchName);
      if ( !ResourcePrivateProps )
      {
        v11 = OpenClusterResource(hCluster, szResourceName);
        v6 = v11;
        if ( !v11 )
          goto LABEL_18;
        if ( ResUtilResourceTypesEqual(L"Network Name", v11) )
        {
          pPropertyList = 0;
          ResourcePrivateProps = GetResourcePrivateProps(v6);
          if ( !ResourcePrivateProps )
            ResourcePrivateProps = ResUtilFindSzProperty(pPropertyList, 0, L"DnsName", &pszPropertyValue);
          LocalFree(pPropertyList);
          if ( !CompareHostNames(pszPropertyValue, a3) )
            goto LABEL_19;
          if ( pszPropertyValue )
          {
            LocalFree(pszPropertyValue);
            pszPropertyValue = 0;
          }
        }
        CloseClusterResource(v6);
      }
      ++v10;
    }
    if ( ResourcePrivateProps == 259 )
      ResourcePrivateProps = 1168;
    goto LABEL_25;
  }
LABEL_18:
  ResourcePrivateProps = GetLastError();
LABEL_19:
  if ( ResourcePrivateProps )
  {
    if ( v6 )
      CloseClusterResource(v6);
    goto LABEL_25;
  }
LABEL_26:
  *a4 = v6;
  if ( v5 )
    ClusterGroupCloseEnum(v5);
  if ( pszPropertyValue )
    LocalFree(pszPropertyValue);
  return ResourcePrivateProps;
}

```

## disassembly

```asm
0x14001407c  push    rbp
0x14001407e  push    rbx
0x14001407f  push    rsi
0x140014080  push    rdi
0x140014081  push    r12
0x140014083  push    r13
0x140014085  push    r14
0x140014087  push    r15
0x140014089  lea     rbp, [rsp-178h]
0x140014091  sub     rsp, 278h
0x140014098  mov     rax, cs:__security_cookie
0x14001409f  xor     rax, rsp
0x1400140a2  mov     [rbp+1B0h+var_50], rax
0x1400140a9  xor     ebx, ebx
0x1400140ab  xor     esi, esi
0x1400140ad  and     [rsp+2B0h+pszPropertyValue], rbx
0x1400140b2  xor     edi, edi
0x1400140b4  mov     r12, r9
0x1400140b7  mov     r15, r8
0x1400140ba  mov     rax, rdx
0x1400140bd  mov     r13, rcx
0x1400140c0  test    rcx, rcx
0x1400140c3  jz      loc_140014258
0x1400140c9  test    rax, rax
0x1400140cc  jz      loc_140014258
0x1400140d2  test    r8, r8
0x1400140d5  jz      loc_140014258
0x1400140db  test    r9, r9
0x1400140de  jz      loc_140014258
0x1400140e4  lea     edx, [rbx+1]; dwType
0x1400140e7  mov     rcx, rax; hGroup
0x1400140ea  call    cs:__imp_ClusterGroupOpenEnum
0x1400140f1  nop     dword ptr [rax+rax+00h]
0x1400140f6  mov     rsi, rax
0x1400140f9  test    rax, rax
0x1400140fc  jz      loc_140014221
0x140014102  xor     r14d, r14d
0x140014105  test    ebx, ebx
0x140014107  jnz     loc_140014249
0x14001410d  and     [rsp+2B0h+dwType], ebx
0x140014111  lea     rax, [rsp+2B0h+cchName]
0x140014116  lea     r9, [rsp+2B0h+szResourceName]; lpszResourceName
0x14001411b  mov     [rsp+2B0h+lpcchName], rax; lpcchName
0x140014120  lea     r8, [rsp+2B0h+dwType]; lpdwType
0x140014125  mov     [rsp+2B0h+cchName], 104h
0x14001412d  mov     edx, r14d; dwIndex
0x140014130  mov     rcx, rsi; hGroupEnum
0x140014133  call    cs:__imp_ClusterGroupEnum
0x14001413a  nop     dword ptr [rax+rax+00h]
0x14001413f  mov     ebx, eax
0x140014141  test    eax, eax
0x140014143  jnz     loc_140014219
0x140014149  lea     rdx, [rsp+2B0h+szResourceName]; lpszResourceName
0x14001414e  mov     rcx, r13; hCluster
0x140014151  call    cs:__imp_OpenClusterResource
0x140014158  nop     dword ptr [rax+rax+00h]
0x14001415d  mov     rdi, rax
0x140014160  test    rax, rax
0x140014163  jz      loc_140014221
0x140014169  mov     rdx, rax; hResource
0x14001416c  lea     rcx, aNetworkName; "Network Name"
0x140014173  call    cs:__imp_ResUtilResourceTypesEqual
0x14001417a  nop     dword ptr [rax+rax+00h]
0x14001417f  test    eax, eax
0x140014181  jz      loc_14001420A
0x140014187  and     [rsp+2B0h+pPropertyList], 0
0x14001418d  lea     r8, [rsp+2B0h+cbPropertyListSize]
0x140014192  and     [rsp+2B0h+cbPropertyListSize], ebx
0x140014196  lea     rdx, [rsp+2B0h+pPropertyList]
0x14001419b  mov     rcx, rdi; hResource
0x14001419e  call    GetResourcePrivateProps
0x1400141a3  mov     ebx, eax
0x1400141a5  test    eax, eax
0x1400141a7  jnz     short loc_1400141CC
0x1400141a9  mov     edx, [rsp+2B0h+cbPropertyListSize]; cbPropertyListSize
0x1400141ad  lea     r9, [rsp+2B0h+pszPropertyValue]; pszPropertyValue
0x1400141b2  mov     rcx, [rsp+2B0h+pPropertyList]; pPropertyList
0x1400141b7  lea     r8, pszPropertyName; "DnsName"
0x1400141be  call    cs:__imp_ResUtilFindSzProperty
0x1400141c5  nop     dword ptr [rax+rax+00h]
0x1400141ca  mov     ebx, eax
0x1400141cc  mov     rcx, [rsp+2B0h+pPropertyList]; hMem
0x1400141d1  call    cs:__imp_LocalFree
0x1400141d8  nop     dword ptr [rax+rax+00h]
0x1400141dd  mov     rcx, [rsp+2B0h+pszPropertyValue]; unsigned __int16 *
0x1400141e2  mov     rdx, r15; unsigned __int16 *
0x1400141e5  call    ?CompareHostNames@@YAKPEAG0@Z; CompareHostNames(ushort *,ushort *)
0x1400141ea  test    eax, eax
0x1400141ec  jz      short loc_14001422F
0x1400141ee  mov     rcx, [rsp+2B0h+pszPropertyValue]; hMem
0x1400141f3  test    rcx, rcx
0x1400141f6  jz      short loc_14001420A
0x1400141f8  call    cs:__imp_LocalFree
0x1400141ff  nop     dword ptr [rax+rax+00h]
0x140014204  and     [rsp+2B0h+pszPropertyValue], 0
0x14001420a  mov     rcx, rdi; hResource
0x14001420d  call    cs:__imp_CloseClusterResource
0x140014214  nop     dword ptr [rax+rax+00h]
0x140014219  inc     r14d
0x14001421c  jmp     loc_140014105
0x140014221  call    cs:__imp_GetLastError
0x140014228  nop     dword ptr [rax+rax+00h]
0x14001422d  mov     ebx, eax
0x14001422f  test    ebx, ebx
0x140014231  jz      short loc_14001425F
0x140014233  test    rdi, rdi
0x140014236  jz      short loc_14001425D
0x140014238  mov     rcx, rdi; hResource
0x14001423b  call    cs:__imp_CloseClusterResource
0x140014242  nop     dword ptr [rax+rax+00h]
0x140014247  jmp     short loc_14001425D
0x140014249  cmp     ebx, 103h
0x14001424f  jnz     short loc_14001425D
0x140014251  mov     ebx, 490h
0x140014256  jmp     short loc_14001425D
0x140014258  mov     ebx, 57h ; 'W'
0x14001425d  xor     edi, edi
0x14001425f  mov     [r12], rdi
0x140014263  test    rsi, rsi
0x140014266  jz      short loc_140014277
0x140014268  mov     rcx, rsi; hGroupEnum
0x14001426b  call    cs:__imp_ClusterGroupCloseEnum
0x140014272  nop     dword ptr [rax+rax+00h]
0x140014277  mov     rcx, [rsp+2B0h+pszPropertyValue]; hMem
0x14001427c  test    rcx, rcx
0x14001427f  jz      short loc_14001428D
0x140014281  call    cs:__imp_LocalFree
0x140014288  nop     dword ptr [rax+rax+00h]
0x14001428d  mov     eax, ebx
0x14001428f  mov     rcx, [rbp+1B0h+var_50]
0x140014296  xor     rcx, rsp; StackCookie
0x140014299  call    __security_check_cookie
0x14001429e  add     rsp, 278h
0x1400142a5  pop     r15
0x1400142a7  pop     r14
0x1400142a9  pop     r13
0x1400142ab  pop     r12
0x1400142ad  pop     rdi
0x1400142ae  pop     rsi
0x1400142af  pop     rbx
0x1400142b0  pop     rbp
0x1400142b1  retn
```
