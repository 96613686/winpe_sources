# UpdateArpCache

- ea: `0x180032a68`
- end: `0x180032c7a`
- name: `UpdateArpCache`
- size: `530`
- prototype: `__int64 __usercall@<rax>(struct in_addr in@<ecx>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180032164`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c164`
- `0x180032a68`
- `0x1800cda62`

## import_xrefs

- `IPHLPAPI!CreateIpNetEntry` at `0x180032bd3`
- `IPHLPAPI!CreateIpNetEntry` at `0x180032bd3`
- `IPHLPAPI!DeleteIpNetEntry` at `0x180032c04`
- `IPHLPAPI!DeleteIpNetEntry` at `0x180032c04`
- `WS2_32!__imp_inet_ntoa` at `0x180032b20`
- `WS2_32!__imp_inet_ntoa` at `0x180032b20`
- `KERNEL32!HeapAlloc` at `0x180032b5d`
- `KERNEL32!HeapAlloc` at `0x180032b5d`
- `KERNEL32!EnterCriticalSection` at `0x180032aa4`
- `KERNEL32!EnterCriticalSection` at `0x180032aa4`
- `KERNEL32!LeaveCriticalSection` at `0x180032aee`
- `KERNEL32!LeaveCriticalSection` at `0x180032aee`
- `KERNEL32!HeapFree` at `0x180032c52`
- `KERNEL32!HeapFree` at `0x180032c52`

## pseudocode

```c
__int64 __fastcall UpdateArpCache(struct in_addr in, DWORD a2, const void *a3, unsigned int a4, int a5)
{
  IF_INDEX v5; // ebp
  size_t v6; // rsi
  int v7; // ebx
  DWORD IpNetEntry; // ebx
  unsigned int i; // ecx
  __int64 v13; // rax
  __int64 v14; // rbx
  char *v15; // rax
  MIB_IPNETROW_LH *v16; // rax
  MIB_IPNETROW_LH *v17; // rdi
  _QWORD *v18; // rcx
  __int64 v19; // rdx

  v5 = 0;
  v6 = a4;
  v7 = 0;
  if ( a4 > 8 )
    return 87;
  EnterCriticalSection(lpCriticalSection);
  for ( i = 0; i < dword_18015766C; ++i )
  {
    if ( v7 )
      break;
    v13 = dword_180157678 * i;
    if ( *(_DWORD *)((char *)lpMem + v13 + 16) == in )
    {
      v5 = *(_DWORD *)((char *)lpMem + v13 + 20);
      v7 = 1;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v15 = inet_ntoa(in);
      WPP_SF_s(v14, 22, &WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids, v15);
    }
    return 2;
  }
  v16 = (MIB_IPNETROW_LH *)HeapAlloc(gDhcpHeap, 8u, 0x18u);
  v17 = v16;
  if ( v16 )
  {
    v16->dwIndex = v5;
    v16->dwPhysAddrLen = v6;
    memcpy_0(v16->bPhysAddr, a3, v6);
    v17->dwAddr = a2;
    v17->dwType = 3;
    if ( a5 == 1 )
    {
      IpNetEntry = CreateIpNetEntry(v17);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_26;
      v19 = 24;
    }
    else
    {
      IpNetEntry = DeleteIpNetEntry(v17);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_26;
      v19 = 25;
    }
    WPP_SF_D(v18[2], v19, &WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids, IpNetEntry);
LABEL_26:
    HeapFree(gDhcpHeap, 0, v17);
    return IpNetEntry;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids);
  return 14;
}

```

## disassembly

```asm
0x180032a68  mov     [rsp+arg_0], rbx
0x180032a6d  mov     [rsp+arg_8], rbp
0x180032a72  mov     [rsp+arg_10], rsi
0x180032a77  push    rdi
0x180032a78  push    r14
0x180032a7a  push    r15
0x180032a7c  sub     rsp, 20h
0x180032a80  xor     ebp, ebp
0x180032a82  mov     esi, r9d
0x180032a85  xor     ebx, ebx
0x180032a87  mov     r14, r8
0x180032a8a  mov     r15d, edx
0x180032a8d  mov     edi, ecx
0x180032a8f  cmp     r9d, 8
0x180032a93  jbe     short loc_180032A9D
0x180032a95  lea     ebx, [rbp+57h]
0x180032a98  jmp     loc_180032C5E
0x180032a9d  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x180032aa4  call    cs:__imp_EnterCriticalSection
0x180032aab  nop     dword ptr [rax+rax+00h]
0x180032ab0  mov     edx, cs:dword_18015766C
0x180032ab6  xor     ecx, ecx
0x180032ab8  test    edx, edx
0x180032aba  jz      short loc_180032AE7
0x180032abc  mov     r9, cs:lpMem
0x180032ac3  test    ebx, ebx
0x180032ac5  jnz     short loc_180032AE7
0x180032ac7  mov     eax, ecx
0x180032ac9  imul    eax, cs:dword_180157678
0x180032ad0  cmp     [rax+r9+10h], edi
0x180032ad5  jnz     short loc_180032AE1
0x180032ad7  mov     ebp, [rax+r9+14h]
0x180032adc  mov     ebx, 1
0x180032ae1  inc     ecx
0x180032ae3  cmp     ecx, edx
0x180032ae5  jb      short loc_180032AC3
0x180032ae7  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x180032aee  call    cs:__imp_LeaveCriticalSection
0x180032af5  nop     dword ptr [rax+rax+00h]
0x180032afa  test    ebx, ebx
0x180032afc  jnz     short loc_180032B4D
0x180032afe  mov     rbx, cs:WPP_GLOBAL_Control
0x180032b05  lea     rax, WPP_GLOBAL_Control
0x180032b0c  cmp     rbx, rax
0x180032b0f  jz      short loc_180032B43
0x180032b11  test    dword ptr [rbx+1Ch], 8000h
0x180032b18  jz      short loc_180032B43
0x180032b1a  mov     rbx, [rbx+10h]
0x180032b1e  mov     ecx, edi; in
0x180032b20  call    cs:__imp_inet_ntoa
0x180032b27  nop     dword ptr [rax+rax+00h]
0x180032b2c  mov     edx, 16h
0x180032b31  lea     r8, WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids
0x180032b38  mov     r9, rax
0x180032b3b  mov     rcx, rbx
0x180032b3e  call    WPP_SF_s
0x180032b43  mov     ebx, 2
0x180032b48  jmp     loc_180032C5E
0x180032b4d  mov     rcx, cs:gDhcpHeap; hHeap
0x180032b54  mov     edx, 8; dwFlags
0x180032b59  lea     r8d, [rdx+10h]; dwBytes
0x180032b5d  call    cs:__imp_HeapAlloc
0x180032b64  nop     dword ptr [rax+rax+00h]
0x180032b69  mov     rdi, rax
0x180032b6c  test    rax, rax
0x180032b6f  jnz     short loc_180032BAA
0x180032b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b78  lea     rax, WPP_GLOBAL_Control
0x180032b7f  cmp     rcx, rax
0x180032b82  jz      short loc_180032BA0
0x180032b84  test    dword ptr [rcx+1Ch], 8000h
0x180032b8b  jz      short loc_180032BA0
0x180032b8d  mov     rcx, [rcx+10h]
0x180032b91  lea     edx, [rdi+17h]
0x180032b94  lea     r8, WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids
0x180032b9b  call    WPP_SF_
0x180032ba0  mov     ebx, 0Eh
0x180032ba5  jmp     loc_180032C5E
0x180032baa  mov     r8, rsi; Size
0x180032bad  mov     [rax], ebp
0x180032baf  lea     rcx, [rax+8]; void *
0x180032bb3  mov     [rax+4], esi
0x180032bb6  mov     rdx, r14; Src
0x180032bb9  call    memcpy_0
0x180032bbe  cmp     [rsp+38h+arg_20], 1
0x180032bc3  mov     rcx, rdi; pArpEntry
0x180032bc6  mov     [rdi+10h], r15d
0x180032bca  mov     dword ptr [rdi+14h], 3
0x180032bd1  jnz     short loc_180032C04
0x180032bd3  call    cs:__imp_CreateIpNetEntry
0x180032bda  nop     dword ptr [rax+rax+00h]
0x180032bdf  mov     ebx, eax
0x180032be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180032be8  lea     rax, WPP_GLOBAL_Control
0x180032bef  cmp     rcx, rax
0x180032bf2  jz      short loc_180032C46
0x180032bf4  test    dword ptr [rcx+1Ch], 8000h
0x180032bfb  jz      short loc_180032C46
0x180032bfd  mov     edx, 18h
0x180032c02  jmp     short loc_180032C33
0x180032c04  call    cs:__imp_DeleteIpNetEntry
0x180032c0b  nop     dword ptr [rax+rax+00h]
0x180032c10  mov     ebx, eax
0x180032c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c19  lea     rax, WPP_GLOBAL_Control
0x180032c20  cmp     rcx, rax
0x180032c23  jz      short loc_180032C46
0x180032c25  test    dword ptr [rcx+1Ch], 8000h
0x180032c2c  jz      short loc_180032C46
0x180032c2e  mov     edx, 19h
0x180032c33  mov     rcx, [rcx+10h]
0x180032c37  lea     r8, WPP_f33428a7d5ee3af3a5c0f6a9d1e7c10d_Traceguids
0x180032c3e  mov     r9d, ebx
0x180032c41  call    WPP_SF_D
0x180032c46  mov     rcx, cs:gDhcpHeap; hHeap
0x180032c4d  mov     r8, rdi; lpMem
0x180032c50  xor     edx, edx; dwFlags
0x180032c52  call    cs:__imp_HeapFree
0x180032c59  nop     dword ptr [rax+rax+00h]
0x180032c5e  mov     rbp, [rsp+38h+arg_8]
0x180032c63  mov     eax, ebx
0x180032c65  mov     rbx, [rsp+38h+arg_0]
0x180032c6a  mov     rsi, [rsp+38h+arg_10]
0x180032c6f  add     rsp, 20h
0x180032c73  pop     r15
0x180032c75  pop     r14
0x180032c77  pop     rdi
0x180032c78  retn
```
