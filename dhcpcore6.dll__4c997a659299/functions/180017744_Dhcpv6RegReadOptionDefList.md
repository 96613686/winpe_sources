# Dhcpv6RegReadOptionDefList

- ea: `0x180017744`
- end: `0x1800179bf`
- name: `Dhcpv6RegReadOptionDefList`
- size: `635`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180017438`

## callees

- `0x180007564`
- `0x180017744`
- `0x18003098c`

## string_xrefs

- `0x180017921`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\?\DHCPV6RequestOptions`
- `0x180017973`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\?\DHCPV6RequestOptions`
- `0x1800177f3`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Dhcpv6DomainSearchList`
- `0x180017848`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Dhcpv6DomainSearchList`
- `0x18001788a`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Dhcpv6Domain`
- `0x1800178df`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Dhcpv6Domain`
- `0x180017751`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Dhcpv6DNSServers`
- `0x1800177b1`: `SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters\Dhcpv6DNSServers`

## pseudocode

```c
__int64 Dhcpv6RegReadOptionDefList()
{
  const wchar_t *v0; // rcx
  __int64 v1; // rdx
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // rdx
  size_t v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 *v8; // rax
  __int64 v9; // rdx
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  size_t v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rdx
  const wchar_t *v19; // rcx
  __int64 v20; // rax
  const wchar_t *v21; // rcx
  __int64 v22; // rdx
  size_t v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 *v26; // rax
  __int64 v27; // rdi
  const wchar_t *v28; // rcx
  __int64 v29; // rax
  const wchar_t *v30; // rcx
  __int64 v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 *v34; // rax

  v0 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Dhcpv6DNSServers";
  v1 = 0;
  v2 = 68;
  do
  {
    v3 = &v0[v2];
    v4 = v1 + 2 * v2;
    v2 = -1;
    v0 = v3 + 1;
    v1 = v4 + 2;
    do
      ++v2;
    while ( v0[v2] );
  }
  while ( v2 );
  v5 = v1 + 2;
  v6 = DhcpAlloc(v1 + 66);
  v7 = v6;
  if ( v6 )
  {
    *(_QWORD *)(v6 + 16) = 23;
    *(_QWORD *)(v6 + 48) = v6 + 64;
    *(_QWORD *)(v6 + 24) = 0;
    *(_DWORD *)(v6 + 32) = 0;
    *(_DWORD *)(v6 + 56) = 3;
    *(_QWORD *)(v6 + 40) = 0;
    memcpy_0((void *)(v6 + 64), L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Dhcpv6DNSServers", v5);
    v8 = (__int64 *)off_180042088[0];
    if ( *(_UNKNOWN ***)off_180042088[0] != &Dhcpv6GlobalOptionDefList )
      goto LABEL_28;
    *(_QWORD *)v7 = &Dhcpv6GlobalOptionDefList;
    *(_QWORD *)(v7 + 8) = v8;
    *v8 = v7;
    off_180042088[0] = (_UNKNOWN **)v7;
  }
  v9 = 0;
  v10 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Dhcpv6DomainSearchList";
  v11 = 74;
  do
  {
    v12 = &v10[v11];
    v13 = v9 + 2 * v11;
    v11 = -1;
    v10 = v12 + 1;
    v9 = v13 + 2;
    do
      ++v11;
    while ( v10[v11] );
  }
  while ( v11 );
  v14 = v9 + 2;
  v15 = DhcpAlloc(v9 + 66);
  v16 = v15;
  if ( v15 )
  {
    *(_QWORD *)(v15 + 16) = 24;
    *(_QWORD *)(v15 + 48) = v15 + 64;
    *(_QWORD *)(v15 + 24) = 0;
    *(_DWORD *)(v15 + 32) = 0;
    *(_DWORD *)(v15 + 56) = 3;
    *(_QWORD *)(v15 + 40) = 0;
    memcpy_0(
      (void *)(v15 + 64),
      L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Dhcpv6DomainSearchList",
      v14);
    v17 = (__int64 *)off_180042088[0];
    if ( *(_UNKNOWN ***)off_180042088[0] != &Dhcpv6GlobalOptionDefList )
      goto LABEL_28;
    *(_QWORD *)v16 = &Dhcpv6GlobalOptionDefList;
    *(_QWORD *)(v16 + 8) = v17;
    *v17 = v16;
    off_180042088[0] = (_UNKNOWN **)v16;
  }
  v18 = 0;
  v19 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Dhcpv6Domain";
  v20 = 64;
  do
  {
    v21 = &v19[v20];
    v22 = v18 + 2 * v20;
    v20 = -1;
    v19 = v21 + 1;
    v18 = v22 + 2;
    do
      ++v20;
    while ( v19[v20] );
  }
  while ( v20 );
  v23 = v18 + 2;
  v24 = DhcpAlloc(v18 + 66);
  v25 = v24;
  if ( v24 )
  {
    *(_QWORD *)(v24 + 16) = 39;
    *(_QWORD *)(v24 + 48) = v24 + 64;
    *(_QWORD *)(v24 + 24) = 0;
    *(_DWORD *)(v24 + 32) = 0;
    *(_DWORD *)(v24 + 56) = 1;
    *(_QWORD *)(v24 + 40) = 0;
    memcpy_0((void *)(v24 + 64), L"SYSTEM\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Dhcpv6Domain", v23);
    v26 = (__int64 *)off_180042088[0];
    if ( *(_UNKNOWN ***)off_180042088[0] != &Dhcpv6GlobalOptionDefList )
      goto LABEL_28;
    *(_QWORD *)v25 = &Dhcpv6GlobalOptionDefList;
    *(_QWORD *)(v25 + 8) = v26;
    *v26 = v25;
    off_180042088[0] = (_UNKNOWN **)v25;
  }
  v27 = 0;
  v28 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\?\\DHCPV6RequestOptions";
  v29 = 85;
  do
  {
    v30 = &v28[v29];
    v31 = v27 + 2 * v29;
    v29 = -1;
    v28 = v30 + 1;
    v27 = v31 + 2;
    do
      ++v29;
    while ( v28[v29] );
  }
  while ( v29 );
  v32 = DhcpAlloc(v27 + 66);
  v33 = v32;
  if ( v32 )
  {
    *(_QWORD *)(v32 + 16) = 6;
    *(_QWORD *)(v32 + 40) = v32 + 64;
    *(_QWORD *)(v32 + 24) = 0;
    *(_DWORD *)(v32 + 32) = 0;
    *(_DWORD *)(v32 + 56) = 0;
    memcpy_0(
      (void *)(v32 + 64),
      L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\?\\DHCPV6RequestOptions",
      v27 + 2);
    *(_QWORD *)(v33 + 48) = 0;
    v34 = (__int64 *)off_180042088[0];
    if ( *(_UNKNOWN ***)off_180042088[0] != &Dhcpv6GlobalOptionDefList )
LABEL_28:
      __fastfail(3u);
    *(_QWORD *)v33 = &Dhcpv6GlobalOptionDefList;
    *(_QWORD *)(v33 + 8) = v34;
    *v34 = v33;
    off_180042088[0] = (_UNKNOWN **)v33;
  }
  return 0;
}

```

## disassembly

```asm
0x180017744  push    rbx
0x180017746  push    rbp
0x180017747  push    rsi
0x180017748  push    rdi
0x180017749  push    r14
0x18001774b  sub     rsp, 20h
0x18001774f  xor     esi, esi
0x180017751  lea     rcx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180017758  mov     edx, esi
0x18001775a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001775e  lea     eax, [rsi+44h]
0x180017761  lea     rcx, [rcx+rax*2]
0x180017765  lea     rdx, [rdx+rax*2]
0x180017769  mov     rax, r14
0x18001776c  lea     rcx, [rcx+2]
0x180017770  lea     rdx, [rdx+2]
0x180017774  inc     rax
0x180017777  cmp     [rcx+rax*2], si
0x18001777b  jnz     short loc_180017774
0x18001777d  test    rax, rax
0x180017780  jnz     short loc_180017761
0x180017782  lea     rdi, [rdx+2]
0x180017786  lea     rcx, [rdi+40h]
0x18001778a  call    DhcpAlloc
0x18001778f  lea     rbp, Dhcpv6GlobalOptionDefList
0x180017796  mov     rbx, rax
0x180017799  test    rax, rax
0x18001779c  jz      short loc_1800177F0
0x18001779e  lea     rcx, [rax+40h]; void *
0x1800177a2  mov     qword ptr [rax+10h], 17h
0x1800177aa  mov     r8, rdi; Size
0x1800177ad  mov     [rax+30h], rcx
0x1800177b1  lea     rdx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x1800177b8  mov     [rax+18h], rsi
0x1800177bc  mov     [rax+20h], esi
0x1800177bf  mov     dword ptr [rax+38h], 3
0x1800177c6  mov     [rax+28h], rsi
0x1800177ca  call    memcpy_0
0x1800177cf  mov     rax, cs:off_180042088
0x1800177d6  cmp     [rax], rbp
0x1800177d9  jnz     loc_180017999
0x1800177df  mov     [rbx], rbp
0x1800177e2  mov     [rbx+8], rax
0x1800177e6  mov     [rax], rbx
0x1800177e9  mov     cs:off_180042088, rbx
0x1800177f0  mov     rdx, rsi
0x1800177f3  lea     rcx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x1800177fa  mov     eax, 4Ah ; 'J'
0x1800177ff  lea     rcx, [rcx+rax*2]
0x180017803  lea     rdx, [rdx+rax*2]
0x180017807  mov     rax, r14
0x18001780a  lea     rcx, [rcx+2]
0x18001780e  lea     rdx, [rdx+2]
0x180017812  inc     rax
0x180017815  cmp     [rcx+rax*2], si
0x180017819  jnz     short loc_180017812
0x18001781b  test    rax, rax
0x18001781e  jnz     short loc_1800177FF
0x180017820  lea     rdi, [rdx+2]
0x180017824  lea     rcx, [rdi+40h]
0x180017828  call    DhcpAlloc
0x18001782d  mov     rbx, rax
0x180017830  test    rax, rax
0x180017833  jz      short loc_180017887
0x180017835  lea     rcx, [rax+40h]; void *
0x180017839  mov     qword ptr [rax+10h], 18h
0x180017841  mov     r8, rdi; Size
0x180017844  mov     [rax+30h], rcx
0x180017848  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x18001784f  mov     [rax+18h], rsi
0x180017853  mov     [rax+20h], esi
0x180017856  mov     dword ptr [rax+38h], 3
0x18001785d  mov     [rax+28h], rsi
0x180017861  call    memcpy_0
0x180017866  mov     rax, cs:off_180042088
0x18001786d  cmp     [rax], rbp
0x180017870  jnz     loc_180017999
0x180017876  mov     [rbx], rbp
0x180017879  mov     [rbx+8], rax
0x18001787d  mov     [rax], rbx
0x180017880  mov     cs:off_180042088, rbx
0x180017887  mov     rdx, rsi
0x18001788a  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180017891  mov     eax, 40h ; '@'
0x180017896  lea     rcx, [rcx+rax*2]
0x18001789a  lea     rdx, [rdx+rax*2]
0x18001789e  mov     rax, r14
0x1800178a1  lea     rcx, [rcx+2]
0x1800178a5  lea     rdx, [rdx+2]
0x1800178a9  inc     rax
0x1800178ac  cmp     [rcx+rax*2], si
0x1800178b0  jnz     short loc_1800178A9
0x1800178b2  test    rax, rax
0x1800178b5  jnz     short loc_180017896
0x1800178b7  lea     rdi, [rdx+2]
0x1800178bb  lea     rcx, [rdi+40h]
0x1800178bf  call    DhcpAlloc
0x1800178c4  mov     rbx, rax
0x1800178c7  test    rax, rax
0x1800178ca  jz      short loc_18001791E
0x1800178cc  lea     rcx, [rax+40h]; void *
0x1800178d0  mov     qword ptr [rax+10h], 27h ; '''
0x1800178d8  mov     r8, rdi; Size
0x1800178db  mov     [rax+30h], rcx
0x1800178df  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x1800178e6  mov     [rax+18h], rsi
0x1800178ea  mov     [rax+20h], esi
0x1800178ed  mov     dword ptr [rax+38h], 1
0x1800178f4  mov     [rax+28h], rsi
0x1800178f8  call    memcpy_0
0x1800178fd  mov     rax, cs:off_180042088
0x180017904  cmp     [rax], rbp
0x180017907  jnz     loc_180017999
0x18001790d  mov     [rbx], rbp
0x180017910  mov     [rbx+8], rax
0x180017914  mov     [rax], rbx
0x180017917  mov     cs:off_180042088, rbx
0x18001791e  mov     rdi, rsi
0x180017921  lea     rcx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x180017928  mov     eax, 55h ; 'U'
0x18001792d  lea     rcx, [rcx+rax*2]
0x180017931  lea     rdi, [rdi+rax*2]
0x180017935  mov     rax, r14
0x180017938  lea     rcx, [rcx+2]
0x18001793c  lea     rdi, [rdi+2]
0x180017940  inc     rax
0x180017943  cmp     [rcx+rax*2], si
0x180017947  jnz     short loc_180017940
0x180017949  test    rax, rax
0x18001794c  jnz     short loc_18001792D
0x18001794e  lea     rcx, [rdi+42h]
0x180017952  call    DhcpAlloc
0x180017957  mov     rbx, rax
0x18001795a  test    rax, rax
0x18001795d  jz      short loc_1800179B1
0x18001795f  lea     rcx, [rax+40h]; void *
0x180017963  mov     qword ptr [rax+10h], 6
0x18001796b  lea     r8, [rdi+2]; Size
0x18001796f  mov     [rax+28h], rcx
0x180017973  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18001797a  mov     [rax+18h], rsi
0x18001797e  mov     [rax+20h], esi
0x180017981  mov     [rax+38h], esi
0x180017984  call    memcpy_0
0x180017989  mov     [rbx+30h], rsi
0x18001798d  mov     rax, cs:off_180042088
0x180017994  cmp     [rax], rbp
0x180017997  jz      short loc_1800179A0
0x180017999  mov     ecx, 3
0x18001799e  int     29h; Win8: RtlFailFast(ecx)
0x1800179a0  mov     [rbx], rbp
0x1800179a3  mov     [rbx+8], rax
0x1800179a7  mov     [rax], rbx
0x1800179aa  mov     cs:off_180042088, rbx
0x1800179b1  xor     eax, eax
0x1800179b3  add     rsp, 20h
0x1800179b7  pop     r14
0x1800179b9  pop     rdi
0x1800179ba  pop     rsi
0x1800179bb  pop     rbp
0x1800179bc  pop     rbx
0x1800179bd  retn
```
