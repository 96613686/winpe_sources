# DeleteMMSAsInternal

- ea: `0x18002e6d0`
- end: `0x18002e943`
- name: `DeleteMMSAsInternal`
- size: `627`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011120`

## callees

- `0x18000e510`
- `0x18002e6d0`
- `0x18002f410`
- `0x18002f480`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18002e92a`
- `fwpuclnt!FwpmEngineClose0` at `0x18002e92a`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002e91b`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002e91b`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002e908`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002e908`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002e762`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002e762`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002e71a`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002e71a`
- `fwpuclnt!IkeextSaDeleteById0` at `0x18002e88a`
- `fwpuclnt!IkeextSaDeleteById0` at `0x18002e88a`
- `fwpuclnt!IkeextSaEnum0` at `0x18002e7bd`
- `fwpuclnt!IkeextSaEnum0` at `0x18002e7bd`

## pseudocode

```c
__int64 __fastcall DeleteMMSAsInternal(_DWORD *a1)
{
  DWORD v2; // eax
  DWORD v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r9
  __int64 v8; // r14
  _QWORD *v9; // r11
  IKEEXT_SA_DETAILS0 *v10; // rsi
  int matched; // eax
  DWORD v12; // eax
  HANDLE enumHandle; // [rsp+30h] [rbp-10h] BYREF
  UINT32 numEntriesReturned; // [rsp+78h] [rbp+38h] BYREF
  HANDLE engineHandle; // [rsp+80h] [rbp+40h] BYREF
  IKEEXT_SA_DETAILS0 **entries; // [rsp+88h] [rbp+48h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  entries = 0;
  numEntriesReturned = 0;
  v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v5 = 40;
LABEL_5:
    v6 = v4[2];
    v7 = v2;
    goto LABEL_38;
  }
  v2 = IkeextSaCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v3 = v2;
  if ( v2 == -2144206780 )
  {
    v3 = 0;
    goto LABEL_39;
  }
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v5 = 41;
    goto LABEL_5;
  }
  v2 = IkeextSaEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v5 = 42;
    goto LABEL_5;
  }
  if ( !numEntriesReturned )
    goto LABEL_39;
  if ( !entries )
    goto LABEL_41;
  v8 = 0;
  if ( !numEntriesReturned )
    goto LABEL_39;
  v9 = WPP_GLOBAL_Control;
  do
  {
    v10 = entries[v8];
    if ( *a1 != 2 )
    {
      if ( *a1 )
      {
        if ( *a1 != 1 || v10->ikeTraffic.ipVersion != FWP_IP_VERSION_V6 )
          goto LABEL_33;
        matched = MatchSAsV6(a1 + 22, a1 + 38, &v10->ikeTraffic.localV4Address, &v10->ikeTraffic.remoteV4Address);
      }
      else
      {
        if ( v10->ikeTraffic.ipVersion )
          goto LABEL_33;
        matched = MatchSAsV4(a1 + 22, a1 + 38, v10->ikeTraffic.localV4Address, v10->ikeTraffic.remoteV4Address);
      }
      if ( !matched )
        goto LABEL_33;
    }
    v12 = IkeextSaDeleteById0(engineHandle, v10->saId);
    if ( !v12 )
      goto LABEL_32;
    v3 = v12;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v12);
LABEL_32:
      v9 = WPP_GLOBAL_Control;
    }
LABEL_33:
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < numEntriesReturned );
  if ( v3 && v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
  {
    v6 = v9[2];
    v5 = 44;
    v7 = v3;
LABEL_38:
    WPP_SF_d(v6, v5, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v7);
  }
LABEL_39:
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
LABEL_41:
  if ( enumHandle )
    IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v3;
}

```

## disassembly

```asm
0x18002e6d0  mov     [rsp-28h+arg_0], rbx
0x18002e6d5  push    rbp
0x18002e6d6  push    rsi
0x18002e6d7  push    rdi
0x18002e6d8  push    r14
0x18002e6da  push    r15
0x18002e6dc  mov     rbp, rsp
0x18002e6df  sub     rsp, 40h
0x18002e6e3  xor     r9d, r9d; session
0x18002e6e6  mov     [rbp+arg_10], 0
0x18002e6ee  mov     r15, rcx
0x18002e6f1  mov     [rbp+enumHandle], 0
0x18002e6f9  lea     rax, [rbp+arg_10]
0x18002e6fd  mov     [rbp+entries], 0
0x18002e705  xor     r8d, r8d; authIdentity
0x18002e708  mov     [rbp+numEntriesReturned], 0
0x18002e70f  lea     edx, [r9+0Ah]; authnService
0x18002e713  mov     [rsp+40h+engineHandle], rax; engineHandle
0x18002e718  xor     ecx, ecx; serverName
0x18002e71a  call    cs:__imp_FwpmEngineOpen0
0x18002e720  mov     ebx, eax
0x18002e722  test    eax, eax
0x18002e724  jz      short loc_18002E758
0x18002e726  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e72d  lea     rdi, WPP_GLOBAL_Control
0x18002e734  cmp     rcx, rdi
0x18002e737  jz      loc_18002E8FD
0x18002e73d  test    byte ptr [rcx+1Ch], 10h
0x18002e741  jz      loc_18002E8FD
0x18002e747  mov     edx, 28h ; '('
0x18002e74c  mov     rcx, [rcx+10h]
0x18002e750  mov     r9d, eax
0x18002e753  jmp     loc_18002E8F1
0x18002e758  mov     rcx, [rbp+arg_10]; engineHandle
0x18002e75c  lea     r8, [rbp+enumHandle]; enumHandle
0x18002e760  xor     edx, edx; enumTemplate
0x18002e762  call    cs:__imp_IkeextSaCreateEnumHandle0
0x18002e768  mov     ebx, eax
0x18002e76a  cmp     eax, 80320044h
0x18002e76f  jnz     short loc_18002E778
0x18002e771  xor     ebx, ebx
0x18002e773  jmp     loc_18002E8FD
0x18002e778  test    eax, eax
0x18002e77a  jz      short loc_18002E7A4
0x18002e77c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e783  lea     rdi, WPP_GLOBAL_Control
0x18002e78a  cmp     rcx, rdi
0x18002e78d  jz      loc_18002E8FD
0x18002e793  test    byte ptr [rcx+1Ch], 10h
0x18002e797  jz      loc_18002E8FD
0x18002e79d  mov     edx, 29h ; ')'
0x18002e7a2  jmp     short loc_18002E74C
0x18002e7a4  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002e7a8  lea     rax, [rbp+numEntriesReturned]
0x18002e7ac  mov     rcx, [rbp+arg_10]; engineHandle
0x18002e7b0  lea     r9, [rbp+entries]; entries
0x18002e7b4  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x18002e7b8  mov     [rsp+40h+engineHandle], rax; numEntriesReturned
0x18002e7bd  call    cs:__imp_IkeextSaEnum0
0x18002e7c3  mov     ebx, eax
0x18002e7c5  test    eax, eax
0x18002e7c7  jz      short loc_18002E7F4
0x18002e7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7d0  lea     rdi, WPP_GLOBAL_Control
0x18002e7d7  cmp     rcx, rdi
0x18002e7da  jz      loc_18002E8FD
0x18002e7e0  test    byte ptr [rcx+1Ch], 10h
0x18002e7e4  jz      loc_18002E8FD
0x18002e7ea  mov     edx, 2Ah ; '*'
0x18002e7ef  jmp     loc_18002E74C
0x18002e7f4  mov     eax, [rbp+numEntriesReturned]
0x18002e7f7  test    eax, eax
0x18002e7f9  jz      loc_18002E8FD
0x18002e7ff  cmp     [rbp+entries], 0
0x18002e804  jz      loc_18002E90E
0x18002e80a  xor     r14d, r14d
0x18002e80d  test    eax, eax
0x18002e80f  jz      loc_18002E8FD
0x18002e815  mov     r11, cs:WPP_GLOBAL_Control
0x18002e81c  lea     rdi, WPP_GLOBAL_Control
0x18002e823  cmp     dword ptr [r15], 2
0x18002e827  mov     rax, [rbp+entries]
0x18002e82b  mov     rsi, [rax+r14*8]
0x18002e82f  jz      short loc_18002E883
0x18002e831  cmp     dword ptr [r15], 0
0x18002e835  jnz     short loc_18002E85B
0x18002e837  cmp     dword ptr [rsi+18h], 0
0x18002e83b  jnz     loc_18002E8C8
0x18002e841  mov     r9d, [rsi+2Ch]
0x18002e845  lea     rdx, [r15+98h]
0x18002e84c  mov     r8d, [rsi+1Ch]
0x18002e850  lea     rcx, [r15+58h]
0x18002e854  call    MatchSAsV4
0x18002e859  jmp     short loc_18002E87F
0x18002e85b  cmp     dword ptr [r15], 1
0x18002e85f  jnz     short loc_18002E8C8
0x18002e861  cmp     dword ptr [rsi+18h], 1
0x18002e865  jnz     short loc_18002E8C8
0x18002e867  lea     r9, [rsi+2Ch]
0x18002e86b  lea     r8, [rsi+1Ch]
0x18002e86f  lea     rdx, [r15+98h]
0x18002e876  lea     rcx, [r15+58h]
0x18002e87a  call    MatchSAsV6
0x18002e87f  test    eax, eax
0x18002e881  jz      short loc_18002E8C8
0x18002e883  mov     rdx, [rsi]; id
0x18002e886  mov     rcx, [rbp+arg_10]; engineHandle
0x18002e88a  call    cs:__imp_IkeextSaDeleteById0
0x18002e890  test    eax, eax
0x18002e892  jz      short loc_18002E8C1
0x18002e894  mov     ebx, eax
0x18002e896  mov     r11, cs:WPP_GLOBAL_Control
0x18002e89d  cmp     r11, rdi
0x18002e8a0  jz      short loc_18002E8C8
0x18002e8a2  test    byte ptr [r11+1Ch], 10h
0x18002e8a7  jz      short loc_18002E8C8
0x18002e8a9  mov     rcx, [r11+10h]
0x18002e8ad  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002e8b4  mov     edx, 2Bh ; '+'
0x18002e8b9  mov     r9d, eax
0x18002e8bc  call    WPP_SF_d
0x18002e8c1  mov     r11, cs:WPP_GLOBAL_Control
0x18002e8c8  inc     r14d
0x18002e8cb  cmp     r14d, [rbp+numEntriesReturned]
0x18002e8cf  jb      loc_18002E823
0x18002e8d5  test    ebx, ebx
0x18002e8d7  jz      short loc_18002E8FD
0x18002e8d9  cmp     r11, rdi
0x18002e8dc  jz      short loc_18002E8FD
0x18002e8de  test    byte ptr [r11+1Ch], 10h
0x18002e8e3  jz      short loc_18002E8FD
0x18002e8e5  mov     rcx, [r11+10h]
0x18002e8e9  mov     edx, 2Ch ; ','
0x18002e8ee  mov     r9d, ebx
0x18002e8f1  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002e8f8  call    WPP_SF_d
0x18002e8fd  cmp     [rbp+entries], 0
0x18002e902  jz      short loc_18002E90E
0x18002e904  lea     rcx, [rbp+entries]; p
0x18002e908  call    cs:__imp_FwpmFreeMemory0
0x18002e90e  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002e912  test    rdx, rdx
0x18002e915  jz      short loc_18002E921
0x18002e917  mov     rcx, [rbp+arg_10]; engineHandle
0x18002e91b  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x18002e921  mov     rcx, [rbp+arg_10]; engineHandle
0x18002e925  test    rcx, rcx
0x18002e928  jz      short loc_18002E930
0x18002e92a  call    cs:__imp_FwpmEngineClose0
0x18002e930  mov     eax, ebx
0x18002e932  mov     rbx, [rsp+40h+arg_0]
0x18002e937  add     rsp, 40h
0x18002e93b  pop     r15
0x18002e93d  pop     r14
0x18002e93f  pop     rdi
0x18002e940  pop     rsi
0x18002e941  pop     rbp
0x18002e942  retn
```
