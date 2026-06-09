# GetDhcpServicedConnections

- ea: `0x18003f7e8`
- end: `0x18003f92e`
- name: `GetDhcpServicedConnections`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180028bd0`
- `0x180028c78`

## callees

- `0x180005670`
- `0x18003f7e8`
- `0x180047a48`
- `0x180047e3c`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003f81b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003f8b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003f81b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003f8b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f915`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f915`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f805`

## pseudocode

```c
__int64 __fastcall GetDhcpServicedConnections(_QWORD *a1, _DWORD *a2)
{
  _QWORD *v4; // rax
  size_t v5; // rdx
  _QWORD *v6; // r14
  unsigned int v7; // ebx
  LPVOID *v8; // rdi
  __int64 v9; // rsi
  const wchar_t *v10; // rcx
  HRESULT v11; // eax
  int v12; // ebp
  unsigned int v13; // ebp
  HLOCAL v14; // rax
  size_t pcbLength; // [rsp+60h] [rbp+18h] BYREF

  EnterCriticalSection(&DhcpGlobalNicListCritSect);
  v4 = LocalAlloc(0x40u, 8LL * DhcpGlobalAdaptersCount);
  *a1 = v4;
  v6 = v4;
  if ( v4 )
  {
    v8 = (LPVOID *)DhcpGlobalConnectedNICList;
    v9 = 0;
    v7 = 0;
    while ( 1 )
    {
      if ( v8 == &DhcpGlobalConnectedNICList )
      {
        *a2 = v9;
        goto LABEL_17;
      }
      v10 = (const wchar_t *)v8[7];
      pcbLength = 0;
      if ( !v10 )
        break;
      v11 = StringCbLengthW(v10, v5, &pcbLength);
      if ( v11 < 0 )
      {
        HIDWORD(pcbLength) = 108;
        goto LABEL_7;
      }
      v12 = pcbLength;
LABEL_11:
      v7 = WX_WIN32_FROM_HR((unsigned int)v11);
      if ( v7 )
        goto LABEL_15;
      v13 = v12 + 2;
      v14 = LocalAlloc(0x40u, v13);
      v6[v9] = v14;
      if ( !v14 )
        goto LABEL_2;
      memcpy_0(v14, v8[7], v13);
      v8 = (LPVOID *)*v8;
      v9 = (unsigned int)(v9 + 1);
    }
    v11 = -2147024809;
    HIDWORD(pcbLength) = 104;
LABEL_7:
    v12 = 0;
    goto LABEL_11;
  }
LABEL_2:
  v7 = 8;
LABEL_15:
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 75, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, v7);
LABEL_17:
  LeaveCriticalSection(&DhcpGlobalNicListCritSect);
  return v7;
}

```

## disassembly

```asm
0x18003f7e8  mov     [rsp+arg_8], rbx
0x18003f7ed  push    rbp
0x18003f7ee  push    rsi
0x18003f7ef  push    rdi
0x18003f7f0  push    r14
0x18003f7f2  push    r15
0x18003f7f4  sub     rsp, 20h
0x18003f7f8  mov     rbx, rcx
0x18003f7fb  mov     r15, rdx
0x18003f7fe  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x18003f805  call    cs:__imp_EnterCriticalSection
0x18003f80b  movsxd  rdx, cs:DhcpGlobalAdaptersCount
0x18003f812  mov     ecx, 40h ; '@'; uFlags
0x18003f817  shl     rdx, 3; uBytes
0x18003f81b  call    cs:__imp_LocalAlloc
0x18003f821  mov     [rbx], rax
0x18003f824  mov     r14, rax
0x18003f827  test    rax, rax
0x18003f82a  jnz     short loc_18003F836
0x18003f82c  mov     ebx, 8
0x18003f831  jmp     loc_18003F8EC
0x18003f836  mov     rdi, cs:DhcpGlobalConnectedNICList
0x18003f83d  xor     esi, esi
0x18003f83f  xor     ebx, ebx
0x18003f841  lea     rax, DhcpGlobalConnectedNICList
0x18003f848  cmp     rdi, rax
0x18003f84b  jz      loc_18003F8E5
0x18003f851  mov     rcx, [rdi+38h]; psz
0x18003f855  mov     dword ptr [rsp+48h+pcbLength+4], 0
0x18003f85d  mov     qword ptr [rsp+60h], 0
0x18003f866  mov     [rsp+48h+arg_0], 0
0x18003f86e  test    rcx, rcx
0x18003f871  jnz     short loc_18003F886
0x18003f873  mov     eax, 80070057h
0x18003f878  mov     dword ptr [rsp+48h+pcbLength+4], 68h ; 'h'
0x18003f880  mov     ebp, [rsp+48h+arg_0]
0x18003f884  jmp     short loc_18003F8A2
0x18003f886  lea     r8, [rsp+48h+pcbLength]; pcbLength
0x18003f88b  call    StringCbLengthW
0x18003f890  test    eax, eax
0x18003f892  jns     short loc_18003F89E
0x18003f894  mov     dword ptr [rsp+48h+pcbLength+4], 6Ch ; 'l'
0x18003f89c  jmp     short loc_18003F880
0x18003f89e  mov     ebp, dword ptr [rsp+48h+pcbLength]
0x18003f8a2  mov     ecx, eax
0x18003f8a4  call    WX_WIN32_FROM_HR
0x18003f8a9  mov     ebx, eax
0x18003f8ab  test    eax, eax
0x18003f8ad  jnz     short loc_18003F8EC
0x18003f8af  lea     ecx, [rbp+2]
0x18003f8b2  mov     ebp, ecx
0x18003f8b4  mov     edx, ecx; uBytes
0x18003f8b6  lea     ecx, [rax+40h]; uFlags
0x18003f8b9  call    cs:__imp_LocalAlloc
0x18003f8bf  mov     [r14+rsi*8], rax
0x18003f8c3  test    rax, rax
0x18003f8c6  jz      loc_18003F82C
0x18003f8cc  mov     rdx, [rdi+38h]; Src
0x18003f8d0  mov     r8d, ebp; Size
0x18003f8d3  mov     rcx, rax; void *
0x18003f8d6  call    memcpy_0
0x18003f8db  mov     rdi, [rdi]
0x18003f8de  inc     esi
0x18003f8e0  jmp     loc_18003F841
0x18003f8e5  mov     [r15], esi
0x18003f8e8  test    ebx, ebx
0x18003f8ea  jz      short loc_18003F90E
0x18003f8ec  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f8f3  jz      short loc_18003F90E
0x18003f8f5  mov     edx, 4Bh ; 'K'
0x18003f8fa  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f901  mov     ecx, 401h
0x18003f906  mov     r9d, ebx
0x18003f909  call    WPP_SF_D
0x18003f90e  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x18003f915  call    cs:__imp_LeaveCriticalSection
0x18003f91b  mov     eax, ebx
0x18003f91d  mov     rbx, [rsp+48h+arg_8]
0x18003f922  add     rsp, 20h
0x18003f926  pop     r15
0x18003f928  pop     r14
0x18003f92a  pop     rdi
0x18003f92b  pop     rsi
0x18003f92c  pop     rbp
0x18003f92d  retn
```
