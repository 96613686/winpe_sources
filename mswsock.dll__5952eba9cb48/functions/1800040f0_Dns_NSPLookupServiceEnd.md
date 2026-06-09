# Dns_NSPLookupServiceEnd

- ea: `0x1800040f0`
- end: `0x180004222`
- name: `Dns_NSPLookupServiceEnd`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800040f0`
- `0x180004228`
- `0x180038104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004149`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004149`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004118`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000420e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000420e`

## pseudocode

```c
__int64 __fastcall Dns_NSPLookupServiceEnd(_DWORD *a1)
{
  char v2; // al
  _DWORD *v3; // rbx
  _DWORD *i; // rax

  v2 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_(1025, 28, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids);
    v2 = xmmword_180063D60;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_(1025, 29, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids);
      v2 = xmmword_180063D60;
    }
  }
  v3 = 0;
  if ( (v2 & 2) != 0 )
  {
    WPP_SF_(1025, 16, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 17, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids);
  }
  EnterCriticalSection(&g_RnrLock);
  for ( i = ListAnchor; i != (_DWORD *)&ListAnchor; i = *(_DWORD **)i )
  {
    if ( i == a1 )
    {
      ++i[9];
      v3 = i;
      break;
    }
  }
  LeaveCriticalSection(&g_RnrLock);
  if ( v3 )
  {
    v3[11] |= 1u;
    RnrCtx_Release(v3);
    RnrCtx_Release(v3);
    return 0;
  }
  else
  {
    SetLastError(6u);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x1800040f0  mov     [rsp+arg_0], rbx
0x1800040f5  push    rdi
0x1800040f6  sub     rsp, 20h
0x1800040fa  mov     rdi, rcx
0x1800040fd  mov     al, byte ptr cs:xmmword_180063D60
0x180004103  test    al, 2
0x180004105  jnz     short loc_180004185
0x180004107  xor     ebx, ebx
0x180004109  test    al, 2
0x18000410b  jnz     loc_1800041CA
0x180004111  lea     rcx, g_RnrLock; lpCriticalSection
0x180004118  call    cs:__imp_EnterCriticalSection
0x18000411f  nop     dword ptr [rax+rax+00h]
0x180004124  mov     rax, cs:ListAnchor
0x18000412b  lea     rcx, ListAnchor
0x180004132  cmp     rax, rcx
0x180004135  jz      short loc_180004142
0x180004137  cmp     rax, rdi
0x18000413a  jnz     short loc_180004180
0x18000413c  inc     dword ptr [rax+24h]
0x18000413f  mov     rbx, rax
0x180004142  lea     rcx, g_RnrLock; lpCriticalSection
0x180004149  call    cs:__imp_LeaveCriticalSection
0x180004150  nop     dword ptr [rax+rax+00h]
0x180004155  test    rbx, rbx
0x180004158  jz      loc_180004209
0x18000415e  or      dword ptr [rbx+2Ch], 1
0x180004162  mov     rcx, rbx
0x180004165  call    RnrCtx_Release
0x18000416a  mov     rcx, rbx
0x18000416d  call    RnrCtx_Release
0x180004172  xor     eax, eax
0x180004174  mov     rbx, [rsp+28h+arg_0]
0x180004179  add     rsp, 20h
0x18000417d  pop     rdi
0x18000417e  retn
0x180004180  mov     rax, [rax]
0x180004183  jmp     short loc_18000412B
0x180004185  mov     edx, 1Ch
0x18000418a  lea     r8, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids
0x180004191  mov     ecx, 401h
0x180004196  call    WPP_SF_
0x18000419b  mov     al, byte ptr cs:xmmword_180063D60
0x1800041a1  test    al, 2
0x1800041a3  jz      loc_180004107
0x1800041a9  mov     edx, 1Dh
0x1800041ae  lea     r8, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids
0x1800041b5  mov     ecx, 401h
0x1800041ba  call    WPP_SF_
0x1800041bf  mov     al, byte ptr cs:xmmword_180063D60
0x1800041c5  jmp     loc_180004107
0x1800041ca  mov     edx, 10h
0x1800041cf  lea     r8, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids
0x1800041d6  mov     ecx, 401h
0x1800041db  call    WPP_SF_
0x1800041e0  mov     al, byte ptr cs:xmmword_180063D60
0x1800041e6  test    al, 2
0x1800041e8  jz      loc_180004111
0x1800041ee  mov     edx, 11h
0x1800041f3  lea     r8, WPP_1bf4e907990e34109b4356408ced46e7_Traceguids
0x1800041fa  mov     ecx, 401h
0x1800041ff  call    WPP_SF_
0x180004204  jmp     loc_180004111
0x180004209  mov     ecx, 6; dwErrCode
0x18000420e  call    cs:__imp_SetLastError
0x180004215  nop     dword ptr [rax+rax+00h]
0x18000421a  or      eax, 0FFFFFFFFh
0x18000421d  jmp     loc_180004174
```
