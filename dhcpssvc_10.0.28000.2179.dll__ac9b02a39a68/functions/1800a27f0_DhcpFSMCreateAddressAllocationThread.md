# DhcpFSMCreateAddressAllocationThread

- ea: `0x1800a27f0`
- end: `0x1800a29bd`
- name: `DhcpFSMCreateAddressAllocationThread`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800058bc`
- `0x180005924`
- `0x1800a0ee8`
- `0x1800a27f0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800a28c2`
- `KERNEL32!WaitForSingleObject` at `0x1800a28c2`
- `KERNEL32!GetLastError` at `0x1800a2834`
- `KERNEL32!GetLastError` at `0x1800a2834`
- `KERNEL32!CloseHandle` at `0x1800a28d5`
- `KERNEL32!CloseHandle` at `0x1800a28d5`
- `KERNEL32!HeapFree` at `0x1800a2938`
- `KERNEL32!HeapFree` at `0x1800a295b`
- `KERNEL32!HeapFree` at `0x1800a2980`
- `KERNEL32!HeapFree` at `0x1800a29a0`
- `KERNEL32!HeapFree` at `0x1800a2938`
- `KERNEL32!HeapFree` at `0x1800a295b`
- `KERNEL32!HeapFree` at `0x1800a2980`
- `KERNEL32!HeapFree` at `0x1800a29a0`
- `KERNEL32!CreateThread` at `0x1800a2820`
- `KERNEL32!CreateThread` at `0x1800a2820`

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
0x1800a27f0  mov     rax, rsp
0x1800a27f3  mov     [rax+8], rbx
0x1800a27f7  mov     [rax+10h], rbp
0x1800a27fb  push    rsi
0x1800a27fc  sub     rsp, 30h
0x1800a2800  mov     rbx, rdx
0x1800a2803  mov     qword ptr [rax-10h], 0
0x1800a280b  mov     r9, rdx; lpParameter
0x1800a280e  mov     dword ptr [rax-18h], 0
0x1800a2815  xor     edx, edx; dwStackSize
0x1800a2817  lea     r8, DhcpAAFailoverAddressAllocation; lpStartAddress
0x1800a281e  xor     ecx, ecx; lpThreadAttributes
0x1800a2820  call    cs:__imp_CreateThread
0x1800a2827  nop     dword ptr [rax+rax+00h]
0x1800a282c  mov     rbp, rax
0x1800a282f  test    rax, rax
0x1800a2832  jnz     short loc_1800A2887
0x1800a2834  call    cs:__imp_GetLastError
0x1800a283b  nop     dword ptr [rax+rax+00h]
0x1800a2840  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2847  lea     rsi, WPP_GLOBAL_Control
0x1800a284e  cmp     rcx, rsi
0x1800a2851  jz      short loc_1800A2879
0x1800a2853  test    dword ptr [rcx+1Ch], 800000h
0x1800a285a  jz      short loc_1800A2879
0x1800a285c  mov     r9, [rbx+10h]
0x1800a2860  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a2867  mov     rcx, [rcx+10h]
0x1800a286b  mov     edx, 0D4h
0x1800a2870  mov     [rsp+38h+var_18], eax
0x1800a2874  call    WPP_SF_SD
0x1800a2879  mov     rcx, [rbx+10h]
0x1800a287d  call    DhcpFSMAddAllocComplete
0x1800a2882  jmp     loc_1800A29AC
0x1800a2887  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a288e  lea     rsi, WPP_GLOBAL_Control
0x1800a2895  cmp     rcx, rsi
0x1800a2898  jz      short loc_1800A28BC
0x1800a289a  test    dword ptr [rcx+1Ch], 800000h
0x1800a28a1  jz      short loc_1800A28BC
0x1800a28a3  mov     r9, [rbx+10h]
0x1800a28a7  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a28ae  mov     rcx, [rcx+10h]
0x1800a28b2  mov     edx, 0D5h
0x1800a28b7  call    WPP_SF_S
0x1800a28bc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a28bf  mov     rcx, rbp; hHandle
0x1800a28c2  call    cs:__imp_WaitForSingleObject
0x1800a28c9  nop     dword ptr [rax+rax+00h]
0x1800a28ce  test    eax, eax
0x1800a28d0  jnz     short loc_1800A28E3
0x1800a28d2  mov     rcx, rbp; hObject
0x1800a28d5  call    cs:__imp_CloseHandle
0x1800a28dc  nop     dword ptr [rax+rax+00h]
0x1800a28e1  jmp     short loc_1800A2915
0x1800a28e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a28ea  cmp     rcx, rsi
0x1800a28ed  jz      short loc_1800A2915
0x1800a28ef  test    dword ptr [rcx+1Ch], 800000h
0x1800a28f6  jz      short loc_1800A2915
0x1800a28f8  mov     r9, [rbx+10h]
0x1800a28fc  lea     r8, WPP_24214c4e0f5a3391c8ef029ed3faca73_Traceguids
0x1800a2903  mov     rcx, [rcx+10h]
0x1800a2907  mov     edx, 0D6h
0x1800a290c  mov     [rsp+38h+var_18], eax
0x1800a2910  call    WPP_SF_SD
0x1800a2915  test    rbx, rbx
0x1800a2918  jz      loc_1800A29AC
0x1800a291e  mov     rax, [rbx]
0x1800a2921  test    rax, rax
0x1800a2924  jz      short loc_1800A296E
0x1800a2926  mov     r8, [rax+8]; lpMem
0x1800a292a  test    r8, r8
0x1800a292d  jz      short loc_1800A294F
0x1800a292f  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a2936  xor     edx, edx; dwFlags
0x1800a2938  call    cs:__imp_HeapFree
0x1800a293f  nop     dword ptr [rax+rax+00h]
0x1800a2944  mov     rax, [rbx]
0x1800a2947  mov     qword ptr [rax+8], 0
0x1800a294f  mov     r8, [rbx]; lpMem
0x1800a2952  xor     edx, edx; dwFlags
0x1800a2954  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a295b  call    cs:__imp_HeapFree
0x1800a2962  nop     dword ptr [rax+rax+00h]
0x1800a2967  mov     qword ptr [rbx], 0
0x1800a296e  mov     r8, [rbx+10h]; lpMem
0x1800a2972  test    r8, r8
0x1800a2975  jz      short loc_1800A2994
0x1800a2977  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a297e  xor     edx, edx; dwFlags
0x1800a2980  call    cs:__imp_HeapFree
0x1800a2987  nop     dword ptr [rax+rax+00h]
0x1800a298c  mov     qword ptr [rbx+10h], 0
0x1800a2994  mov     rcx, cs:gDhcpHeap; hHeap
0x1800a299b  mov     r8, rbx; lpMem
0x1800a299e  xor     edx, edx; dwFlags
0x1800a29a0  call    cs:__imp_HeapFree
0x1800a29a7  nop     dword ptr [rax+rax+00h]
0x1800a29ac  mov     rbx, [rsp+38h+arg_0]
0x1800a29b1  mov     rbp, [rsp+38h+arg_8]
0x1800a29b6  add     rsp, 30h
0x1800a29ba  pop     rsi
0x1800a29bb  retn
```
