# DwDropIncomingCall

- ea: `0x1800023d4`
- end: `0x1800024b5`
- name: `DwDropIncomingCall`
- size: `225`
- prototype: `__int64 __fastcall(HCALL hCall)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000272c`

## callees

- `0x1800023d4`
- `0x18000d92c`
- `0x180023a14`
- `0x180023e24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800023f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800023f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023ff`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x180002455`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x180002455`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDrop` at `0x180002423`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDrop` at `0x180002423`

## string_xrefs

- `0x180002405`: `DwDropIncomingCall: Failed to allocate Zombie`
- `0x180002466`: `DwIncomingCall: lineDeallocateCall. RequestID = 0x%x`

## pseudocode

```c
__int64 __fastcall DwDropIncomingCall(HCALL hCall, int a2)
{
  __int64 v4; // rdx
  _DWORD *v5; // rbx
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD LastError; // edi
  unsigned int v9; // edi
  int v10; // eax
  __int64 v11; // rax
  unsigned int v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = 0;
  v5 = LocalAlloc(0x40u, 0x20u);
  if ( !v5 )
  {
    LastError = GetLastError();
    RasTapiTrace("DwDropIncomingCall: Failed to allocate Zombie");
    return LastError;
  }
  if ( a2 )
  {
    v10 = RasLineDrop(hCall, v4, v6, v7, &v13);
    v9 = v13;
    if ( v10 )
      goto LABEL_10;
  }
  else
  {
    v9 = lineDrop(hCall, 0, 0);
    if ( v9 > 0x80000000 )
    {
LABEL_9:
      lineDeallocateCall(hCall);
LABEL_11:
      RasTapiTrace("DwIncomingCall: lineDeallocateCall. RequestID = 0x%x");
      goto LABEL_12;
    }
  }
  if ( !v9 )
  {
    if ( !a2 )
      goto LABEL_9;
LABEL_10:
    RasLineCloseCall(hCall);
    goto LABEL_11;
  }
LABEL_12:
  v5[5] = hCall;
  v5[4] = v9;
  v5[6] = a2;
  v11 = ZombieCallList;
  if ( *(__int64 **)(ZombieCallList + 8) != &ZombieCallList )
    __fastfail(3u);
  *(_QWORD *)v5 = ZombieCallList;
  LastError = 0;
  *((_QWORD *)v5 + 1) = &ZombieCallList;
  *(_QWORD *)(v11 + 8) = v5;
  ZombieCallList = (__int64)v5;
  return LastError;
}

```

## disassembly

```asm
0x1800023d4  push    rbx
0x1800023d6  push    rbp
0x1800023d7  push    rsi
0x1800023d8  push    rdi
0x1800023d9  sub     rsp, 38h
0x1800023dd  mov     ebp, edx
0x1800023df  mov     [rsp+58h+arg_10], 0
0x1800023e7  mov     edx, 20h ; ' '; uBytes
0x1800023ec  mov     esi, ecx
0x1800023ee  lea     ecx, [rdx+20h]; uFlags
0x1800023f1  call    cs:__imp_LocalAlloc
0x1800023f7  mov     rbx, rax
0x1800023fa  test    rax, rax
0x1800023fd  jnz     short loc_180002418
0x1800023ff  call    cs:__imp_GetLastError
0x180002405  lea     rcx, aDwdropincoming; "DwDropIncomingCall: Failed to allocate "...
0x18000240c  mov     edi, eax
0x18000240e  call    RasTapiTrace
0x180002413  jmp     loc_1800024AA
0x180002418  mov     ecx, esi; hCall
0x18000241a  test    ebp, ebp
0x18000241c  jnz     short loc_180002434
0x18000241e  xor     r8d, r8d; dwSize
0x180002421  xor     edx, edx; lpsUserUserInfo
0x180002423  call    cs:__imp_lineDrop
0x180002429  mov     edi, eax
0x18000242b  cmp     eax, 80000000h
0x180002430  ja      short loc_180002453
0x180002432  jmp     short loc_18000244B
0x180002434  lea     rax, [rsp+58h+arg_10]
0x180002439  mov     [rsp+58h+var_38], rax
0x18000243e  call    RasLineDrop
0x180002443  mov     edi, [rsp+58h+arg_10]
0x180002447  test    eax, eax
0x180002449  jnz     short loc_18000245D
0x18000244b  test    edi, edi
0x18000244d  jnz     short loc_180002472
0x18000244f  test    ebp, ebp
0x180002451  jnz     short loc_18000245D
0x180002453  mov     ecx, esi; hCall
0x180002455  call    cs:__imp_lineDeallocateCall
0x18000245b  jmp     short loc_180002464
0x18000245d  mov     ecx, esi
0x18000245f  call    RasLineCloseCall
0x180002464  mov     edx, edi
0x180002466  lea     rcx, aDwincomingcall; "DwIncomingCall: lineDeallocateCall. Req"...
0x18000246d  call    RasTapiTrace
0x180002472  mov     [rbx+14h], esi
0x180002475  lea     rcx, ZombieCallList
0x18000247c  mov     [rbx+10h], edi
0x18000247f  mov     [rbx+18h], ebp
0x180002482  mov     rax, cs:ZombieCallList
0x180002489  cmp     [rax+8], rcx
0x18000248d  jz      short loc_180002496
0x18000248f  mov     ecx, 3
0x180002494  int     29h; Win8: RtlFailFast(ecx)
0x180002496  mov     [rbx], rax
0x180002499  xor     edi, edi
0x18000249b  mov     [rbx+8], rcx
0x18000249f  mov     [rax+8], rbx
0x1800024a3  mov     cs:ZombieCallList, rbx
0x1800024aa  mov     eax, edi
0x1800024ac  add     rsp, 38h
0x1800024b0  pop     rdi
0x1800024b1  pop     rsi
0x1800024b2  pop     rbp
0x1800024b3  pop     rbx
0x1800024b4  retn
```
