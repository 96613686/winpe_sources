# DhcpFSMCreateAddressAllocationThread

- ea: `0x1800a1af0`
- end: `0x1800a1cae`
- name: `DhcpFSMCreateAddressAllocationThread`
- size: `446`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800058cc`
- `0x180005934`
- `0x1800a0210`
- `0x1800a1af0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800a1bbc`
- `KERNEL32!WaitForSingleObject` at `0x1800a1bbc`
- `KERNEL32!CreateThread` at `0x1800a1b1a`
- `KERNEL32!CreateThread` at `0x1800a1b1a`
- `KERNEL32!GetLastError` at `0x1800a1b2e`
- `KERNEL32!GetLastError` at `0x1800a1b2e`
- `KERNEL32!CloseHandle` at `0x1800a1bcf`
- `KERNEL32!CloseHandle` at `0x1800a1bcf`
- `KERNEL32!HeapFree` at `0x1800a1c32`
- `KERNEL32!HeapFree` at `0x1800a1c52`
- `KERNEL32!HeapFree` at `0x1800a1c74`
- `KERNEL32!HeapFree` at `0x1800a1c91`
- `KERNEL32!HeapFree` at `0x1800a1c32`
- `KERNEL32!HeapFree` at `0x1800a1c52`
- `KERNEL32!HeapFree` at `0x1800a1c74`
- `KERNEL32!HeapFree` at `0x1800a1c91`

## pseudocode

```c
DWORD __fastcall DhcpFSMCreateAddressAllocationThread(__int64 a1, _QWORD *a2)
{
  HANDLE Thread; // rbp
  char LastError; // al
  DWORD result; // eax
  void *v6; // r8
  void *v7; // r8

  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DhcpAAFailoverAddressAllocation, a2, 0, 0);
  if ( Thread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids, a2[2]);
    result = WaitForSingleObject(Thread, 0xFFFFFFFF);
    if ( result )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        result = WPP_SF_SD(
                   *((_QWORD *)WPP_GLOBAL_Control + 2),
                   214,
                   (unsigned int)&WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids,
                   a2[2],
                   result);
      }
    }
    else
    {
      result = CloseHandle(Thread);
    }
    if ( a2 )
    {
      if ( *a2 )
      {
        v6 = *(void **)(*a2 + 8LL);
        if ( v6 )
        {
          HeapFree(gDhcpHeap, 0, v6);
          *(_QWORD *)(*a2 + 8LL) = 0;
        }
        HeapFree(gDhcpHeap, 0, (LPVOID)*a2);
        *a2 = 0;
      }
      v7 = (void *)a2[2];
      if ( v7 )
      {
        HeapFree(gDhcpHeap, 0, v7);
        a2[2] = 0;
      }
      return HeapFree(gDhcpHeap, 0, a2);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        212,
        (unsigned int)&WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids,
        a2[2],
        LastError);
    return DhcpFSMAddAllocComplete(a2[2]);
  }
  return result;
}

```

## disassembly

```asm
0x1800a1af0  mov     rax, rsp
0x1800a1af3  mov     [rax+8], rbx
0x1800a1af7  mov     [rax+10h], rbp
0x1800a1afb  push    rsi
0x1800a1afc  sub     rsp, 30h
0x1800a1b00  and     qword ptr [rax-10h], 0
0x1800a1b05  lea     r8, DhcpAAFailoverAddressAllocation; lpStartAddress
0x1800a1b0c  and     dword ptr [rax-18h], 0
0x1800a1b10  mov     rbx, rdx
0x1800a1b13  mov     r9, rdx; lpParameter
0x1800a1b16  xor     ecx, ecx; lpThreadAttributes
0x1800a1b18  xor     edx, edx; dwStackSize
0x1800a1b1a  call    cs:__imp_CreateThread
0x1800a1b21  nop     dword ptr [rax+rax+00h]
0x1800a1b26  mov     rbp, rax
0x1800a1b29  test    rax, rax
0x1800a1b2c  jnz     short loc_1800A1B81
0x1800a1b2e  call    cs:__imp_GetLastError
0x1800a1b35  nop     dword ptr [rax+rax+00h]
0x1800a1b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1b41  lea     rsi, WPP_GLOBAL_Control
0x1800a1b48  cmp     rcx, rsi
0x1800a1b4b  jz      short loc_1800A1B73
0x1800a1b4d  test    dword ptr [rcx+1Ch], 800000h
0x1800a1b54  jz      short loc_1800A1B73
0x1800a1b56  mov     r9, [rbx+10h]
0x1800a1b5a  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a1b61  mov     rcx, [rcx+10h]
0x1800a1b65  mov     edx, 0D4h
0x1800a1b6a  mov     [rsp+38h+var_18], eax
0x1800a1b6e  call    WPP_SF_SD
0x1800a1b73  mov     rcx, [rbx+10h]
0x1800a1b77  call    DhcpFSMAddAllocComplete
0x1800a1b7c  jmp     loc_1800A1C9D
0x1800a1b81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1b88  lea     rsi, WPP_GLOBAL_Control
0x1800a1b8f  cmp     rcx, rsi
0x1800a1b92  jz      short loc_1800A1BB6
0x1800a1b94  test    dword ptr [rcx+1Ch], 800000h
0x1800a1b9b  jz      short loc_1800A1BB6
0x1800a1b9d  mov     r9, [rbx+10h]
0x1800a1ba1  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a1ba8  mov     rcx, [rcx+10h]
0x1800a1bac  mov     edx, 0D5h
0x1800a1bb1  call    WPP_SF_S
0x1800a1bb6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a1bb9  mov     rcx, rbp; hHandle
0x1800a1bbc  call    cs:__imp_WaitForSingleObject
0x1800a1bc3  nop     dword ptr [rax+rax+00h]
0x1800a1bc8  test    eax, eax
0x1800a1bca  jnz     short loc_1800A1BDD
0x1800a1bcc  mov     rcx, rbp; hObject
0x1800a1bcf  call    cs:__imp_CloseHandle
0x1800a1bd6  nop     dword ptr [rax+rax+00h]
0x1800a1bdb  jmp     short loc_1800A1C0F
0x1800a1bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1be4  cmp     rcx, rsi
0x1800a1be7  jz      short loc_1800A1C0F
0x1800a1be9  test    dword ptr [rcx+1Ch], 800000h
0x1800a1bf0  jz      short loc_1800A1C0F
0x1800a1bf2  mov     r9, [rbx+10h]
0x1800a1bf6  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a1bfd  mov     rcx, [rcx+10h]
0x1800a1c01  mov     edx, 0D6h
0x1800a1c06  mov     [rsp+38h+var_18], eax
0x1800a1c0a  call    WPP_SF_SD
0x1800a1c0f  test    rbx, rbx
0x1800a1c12  jz      loc_1800A1C9D
0x1800a1c18  mov     rax, [rbx]
0x1800a1c1b  test    rax, rax
0x1800a1c1e  jz      short loc_1800A1C62
0x1800a1c20  mov     r8, [rax+8]; lpMem
0x1800a1c24  test    r8, r8
0x1800a1c27  jz      short loc_1800A1C46
0x1800a1c29  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a1c30  xor     edx, edx; dwFlags
0x1800a1c32  call    cs:__imp_HeapFree
0x1800a1c39  nop     dword ptr [rax+rax+00h]
0x1800a1c3e  mov     rax, [rbx]
0x1800a1c41  and     qword ptr [rax+8], 0
0x1800a1c46  mov     r8, [rbx]; lpMem
0x1800a1c49  xor     edx, edx; dwFlags
0x1800a1c4b  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a1c52  call    cs:__imp_HeapFree
0x1800a1c59  nop     dword ptr [rax+rax+00h]
0x1800a1c5e  and     qword ptr [rbx], 0
0x1800a1c62  mov     r8, [rbx+10h]; lpMem
0x1800a1c66  test    r8, r8
0x1800a1c69  jz      short loc_1800A1C85
0x1800a1c6b  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a1c72  xor     edx, edx; dwFlags
0x1800a1c74  call    cs:__imp_HeapFree
0x1800a1c7b  nop     dword ptr [rax+rax+00h]
0x1800a1c80  and     qword ptr [rbx+10h], 0
0x1800a1c85  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a1c8c  mov     r8, rbx; lpMem
0x1800a1c8f  xor     edx, edx; dwFlags
0x1800a1c91  call    cs:__imp_HeapFree
0x1800a1c98  nop     dword ptr [rax+rax+00h]
0x1800a1c9d  mov     rbx, [rsp+38h+arg_0]
0x1800a1ca2  mov     rbp, [rsp+38h+arg_8]
0x1800a1ca7  add     rsp, 30h
0x1800a1cab  pop     rsi
0x1800a1cac  retn
```
