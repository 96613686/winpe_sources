# SockpCreateV4SubnetMap

- ea: `0x180042f74`
- end: `0x1800431a6`
- name: `SockpCreateV4SubnetMap`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003eb24`

## callees

- `0x18003aec4`
- `0x180042f74`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004302e`
- `ntdll!RtlFreeHeap` at `0x180043172`
- `ntdll!RtlFreeHeap` at `0x18004302e`
- `ntdll!RtlFreeHeap` at `0x180043172`
- `IPHLPAPI!FreeMibTable` at `0x180043007`
- `IPHLPAPI!FreeMibTable` at `0x1800430e8`
- `IPHLPAPI!FreeMibTable` at `0x180043146`
- `IPHLPAPI!FreeMibTable` at `0x180043007`
- `IPHLPAPI!FreeMibTable` at `0x1800430e8`
- `IPHLPAPI!FreeMibTable` at `0x180043146`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x180042f9a`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x180042f9a`

## pseudocode

```c
__int64 __fastcall SockpCreateV4SubnetMap(_BYTE *a1)
{
  unsigned int UnicastIpAddressTable; // eax
  __int64 v3; // rcx
  int v4; // ebx
  PMIB_UNICASTIPADDRESS_TABLE v5; // rcx
  _DWORD *v6; // r9
  __int64 NumEntries; // rbx
  __int64 v8; // rdx
  _DWORD *v10; // rax
  unsigned int v11; // edi
  unsigned int v12; // r11d
  unsigned __int64 v13; // r10
  unsigned __int64 v14; // r8
  __int64 v15; // rdx
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+38h] [rbp+18h] BYREF

  Table = 0;
  UnicastIpAddressTable = GetUnicastIpAddressTable(2u, &Table);
  v4 = UnicastIpAddressTable;
  if ( UnicastIpAddressTable )
  {
    if ( UnicastIpAddressTable == 232 )
    {
      *a1 = 0;
      v11 = 0;
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v3, 84, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, UnicastIpAddressTable);
      if ( v4 != 8 )
        v4 = 10107;
      v11 = v4;
    }
    v6 = SockSanSubnetMap;
    v5 = Table;
    goto LABEL_31;
  }
  v5 = Table;
  v6 = SockSanSubnetMap;
  NumEntries = Table->NumEntries;
  if ( (_DWORD)NumEntries == SockSanSubnetCount )
  {
    v8 = 0;
    if ( (_DWORD)NumEntries )
    {
      while ( Table->Table[v8].InterfaceIndex == *((_DWORD *)SockSanSubnetMap + 12 * v8 + 8)
           && Table->Table[v8].Address.Ipv4.sin_addr.S_un.S_addr == *((_DWORD *)SockSanSubnetMap + 12 * v8 + 1)
           && Table->Table[v8].OnLinkPrefixLength == *((_BYTE *)SockSanSubnetMap + 48 * v8 + 28) )
      {
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= (unsigned int)NumEntries )
          goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      if ( (_DWORD)v8 == (_DWORD)NumEntries )
      {
        FreeMibTable(Table);
        *a1 = 0;
        return 0;
      }
    }
  }
  if ( SockSanSubnetMap )
  {
    RtlFreeHeap(SockPrivateHeap, 0, SockSanSubnetMap);
    v5 = Table;
    v6 = 0;
    SockSanSubnetMap = 0;
  }
  if ( (_DWORD)NumEntries )
  {
    v10 = (_DWORD *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64, _DWORD *))SockAllocateHeapRoutine)(
                      SockPrivateHeap,
                      0,
                      48 * NumEntries,
                      v6);
    v5 = Table;
    v6 = v10;
    SockSanSubnetMap = v10;
  }
  if ( v6 || !(_DWORD)NumEntries )
  {
    v12 = 0;
    if ( (_DWORD)NumEntries )
    {
      v13 = 0;
      do
      {
        ++v12;
        v14 = v13;
        v15 = 6 * v13++;
        v6[2 * v15 + 1] = v5->Table[v14].Address.Ipv4.sin_addr.S_un.S_addr;
        LOBYTE(v6[2 * v15 + 7]) = Table->Table[v14].OnLinkPrefixLength;
        v6[2 * v15 + 8] = Table->Table[v14].InterfaceIndex;
        *(_QWORD *)&v6[2 * v15 + 10] = 0;
        v5 = Table;
      }
      while ( v12 < (unsigned int)NumEntries );
      *a1 = 1;
    }
    SockSanSubnetCount = NumEntries;
    FreeMibTable(v5);
    return 0;
  }
  v11 = 8;
LABEL_31:
  if ( v5 )
  {
    FreeMibTable(v5);
    v6 = SockSanSubnetMap;
    Table = 0;
  }
  if ( v6 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v6);
    SockSanSubnetMap = 0;
    SockSanSubnetCount = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x180042f74  mov     [rsp-8+arg_0], rbx
0x180042f79  mov     [rsp-8+arg_10], rdi
0x180042f7e  push    rbp
0x180042f7f  mov     rbp, rsp
0x180042f82  sub     rsp, 20h
0x180042f86  mov     rdi, rcx
0x180042f89  mov     [rbp+Table], 0
0x180042f91  mov     ecx, 2; Family
0x180042f96  lea     rdx, [rbp+Table]; Table
0x180042f9a  call    cs:__imp_GetUnicastIpAddressTable
0x180042fa1  nop     dword ptr [rax+rax+00h]
0x180042fa6  mov     ebx, eax
0x180042fa8  test    eax, eax
0x180042faa  jnz     loc_1800430F9
0x180042fb0  mov     rcx, [rbp+Table]; Memory
0x180042fb4  mov     r9, cs:SockSanSubnetMap
0x180042fbb  mov     ebx, [rcx]
0x180042fbd  cmp     ebx, cs:SockSanSubnetCount
0x180042fc3  jnz     short loc_18004301D
0x180042fc5  xor     edx, edx
0x180042fc7  test    ebx, ebx
0x180042fc9  jz      short loc_180043003
0x180042fcb  lea     r8, [rdx+rdx*2]
0x180042fcf  add     r8, r8
0x180042fd2  lea     r10, [rdx+rdx*4]
0x180042fd6  add     r10, r10
0x180042fd9  mov     eax, [r9+r8*8+20h]
0x180042fde  cmp     [rcx+r10*8+30h], eax
0x180042fe3  jnz     short loc_18004301D
0x180042fe5  mov     eax, [r9+r8*8+4]
0x180042fea  cmp     [rcx+r10*8+0Ch], eax
0x180042fef  jnz     short loc_18004301D
0x180042ff1  mov     al, [r9+r8*8+1Ch]
0x180042ff6  cmp     [rcx+r10*8+44h], al
0x180042ffb  jnz     short loc_18004301D
0x180042ffd  inc     edx
0x180042fff  cmp     edx, ebx
0x180043001  jb      short loc_180042FCB
0x180043003  cmp     edx, ebx
0x180043005  jnz     short loc_18004301D
0x180043007  call    cs:__imp_FreeMibTable
0x18004300e  nop     dword ptr [rax+rax+00h]
0x180043013  mov     byte ptr [rdi], 0
0x180043016  xor     eax, eax
0x180043018  jmp     loc_180043195
0x18004301d  test    r9, r9
0x180043020  jz      short loc_180043048
0x180043022  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180043029  mov     r8, r9; P
0x18004302c  xor     edx, edx; Flags
0x18004302e  call    cs:__imp_RtlFreeHeap
0x180043035  nop     dword ptr [rax+rax+00h]
0x18004303a  mov     rcx, [rbp+Table]
0x18004303e  xor     r9d, r9d
0x180043041  mov     cs:SockSanSubnetMap, r9
0x180043048  test    ebx, ebx
0x18004304a  jz      short loc_180043077
0x18004304c  mov     rcx, cs:SockPrivateHeap
0x180043053  lea     r8, [rbx+rbx*2]
0x180043057  mov     rax, cs:SockAllocateHeapRoutine
0x18004305e  xor     edx, edx
0x180043060  shl     r8, 4
0x180043064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043069  mov     rcx, [rbp+Table]
0x18004306d  mov     r9, rax
0x180043070  mov     cs:SockSanSubnetMap, rax
0x180043077  test    r9, r9
0x18004307a  jnz     short loc_180043089
0x18004307c  test    ebx, ebx
0x18004307e  jz      short loc_180043089
0x180043080  lea     edi, [r9+8]
0x180043084  jmp     loc_180043141
0x180043089  xor     r11d, r11d
0x18004308c  test    ebx, ebx
0x18004308e  jz      short loc_1800430E2
0x180043090  xor     r10d, r10d
0x180043093  lea     r8, [r10+r10*4]
0x180043097  inc     r11d
0x18004309a  add     r8, r8
0x18004309d  lea     rdx, [r10+r10*2]
0x1800430a1  add     rdx, rdx
0x1800430a4  inc     r10
0x1800430a7  mov     eax, [rcx+r8*8+0Ch]
0x1800430ac  mov     [r9+rdx*8+4], eax
0x1800430b1  mov     rax, [rbp+Table]
0x1800430b5  mov     cl, [rax+r8*8+44h]
0x1800430ba  mov     [r9+rdx*8+1Ch], cl
0x1800430bf  mov     rax, [rbp+Table]
0x1800430c3  mov     ecx, [rax+r8*8+30h]
0x1800430c8  mov     [r9+rdx*8+20h], ecx
0x1800430cd  mov     qword ptr [r9+rdx*8+28h], 0
0x1800430d6  mov     rcx, [rbp+Table]; Memory
0x1800430da  cmp     r11d, ebx
0x1800430dd  jb      short loc_180043093
0x1800430df  mov     byte ptr [rdi], 1
0x1800430e2  mov     cs:SockSanSubnetCount, ebx
0x1800430e8  call    cs:__imp_FreeMibTable
0x1800430ef  nop     dword ptr [rax+rax+00h]
0x1800430f4  jmp     loc_180043016
0x1800430f9  cmp     ebx, 0E8h
0x1800430ff  jnz     short loc_180043108
0x180043101  mov     byte ptr [rdi], 0
0x180043104  xor     edi, edi
0x180043106  jmp     short loc_180043136
0x180043108  test    byte ptr cs:xmmword_180063D60, 2
0x18004310f  jz      short loc_180043125
0x180043111  mov     edx, 54h ; 'T'
0x180043116  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18004311d  mov     r9d, ebx
0x180043120  call    WPP_SF_l
0x180043125  mov     edi, 8
0x18004312a  mov     eax, 277Bh
0x18004312f  cmp     ebx, edi
0x180043131  cmovnz  ebx, eax
0x180043134  mov     edi, ebx
0x180043136  mov     r9, cs:SockSanSubnetMap
0x18004313d  mov     rcx, [rbp+Table]; Memory
0x180043141  test    rcx, rcx
0x180043144  jz      short loc_180043161
0x180043146  call    cs:__imp_FreeMibTable
0x18004314d  nop     dword ptr [rax+rax+00h]
0x180043152  mov     r9, cs:SockSanSubnetMap
0x180043159  mov     [rbp+Table], 0
0x180043161  test    r9, r9
0x180043164  jz      short loc_180043193
0x180043166  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004316d  mov     r8, r9; P
0x180043170  xor     edx, edx; Flags
0x180043172  call    cs:__imp_RtlFreeHeap
0x180043179  nop     dword ptr [rax+rax+00h]
0x18004317e  mov     cs:SockSanSubnetMap, 0
0x180043189  mov     cs:SockSanSubnetCount, 0
0x180043193  mov     eax, edi
0x180043195  mov     rbx, [rsp+20h+arg_0]
0x18004319a  mov     rdi, [rsp+20h+arg_10]
0x18004319f  add     rsp, 20h
0x1800431a3  pop     rbp
0x1800431a4  retn
```
