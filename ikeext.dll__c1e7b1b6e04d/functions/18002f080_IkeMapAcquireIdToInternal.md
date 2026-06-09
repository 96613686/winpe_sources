# IkeMapAcquireIdToInternal

- ea: `0x18002f080`
- end: `0x18002f2e4`
- name: `IkeMapAcquireIdToInternal`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800116e0`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180013fb0`
- `0x180016730`
- `0x18002f080`
- `0x180050850`
- `0x18007b608`

## import_xrefs

- `fwpuclnt!FwpsOpenToken0` at `0x18002f1b0`
- `fwpuclnt!FwpsOpenToken0` at `0x18002f1b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2af`

## string_xrefs

- `0x18002f24d`: `FwpsOpenToken0`

## pseudocode

```c
__int64 __fastcall IkeMapAcquireIdToInternal(__int64 a1)
{
  bool v2; // zf
  __int64 v3; // rax
  __int64 v4; // rdx
  _DWORD *v5; // rax
  unsigned int v6; // edi
  __int64 SidFromToken; // rsi
  unsigned int v8; // r8d
  __int64 v9; // r9
  unsigned int i; // edx
  __int64 v11; // rbp
  DWORD v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v18; // [rsp+20h] [rbp-38h] BYREF
  HANDLE accessToken; // [rsp+28h] [rbp-30h] BYREF

  v2 = (*(_DWORD *)(a1 + 376) & 0x4000) == 0;
  accessToken = 0;
  v18 = 0;
  if ( !v2 )
  {
    v3 = *(_QWORD *)(a1 + 392);
    if ( !v3 )
    {
      v4 = 0;
LABEL_4:
      v5 = (_DWORD *)(v3 + 16);
      goto LABEL_5;
    }
    v8 = *(_DWORD *)(v3 + 16);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v3 + 24);
      for ( i = 0; i < v8; ++i )
      {
        if ( *(_DWORD *)(v9 + 24LL * i) == 1 && !*(_DWORD *)(v9 + 24LL * i + 4) && !*(_DWORD *)(v9 + 24LL * i + 8) )
          break;
      }
      v4 = *(_QWORD *)(a1 + 392);
      SidFromToken = 0;
      v5 = (_DWORD *)(v4 + 16);
LABEL_19:
      if ( !*v5 )
        return IkeReturnError(SidFromToken, "IkeMapAcquireIdToInternal");
      v6 = 0;
      while ( 1 )
      {
        v11 = 24LL * v6;
        v12 = FwpsOpenToken0(
                gIkeExtGlobals[68].OwningThread,
                *(LUID *)(*(_QWORD *)(v4 + 24) + v11 + 16),
                0xAu,
                &accessToken);
        if ( v12 )
        {
          SidFromToken = WfpReportSysErrorAsWinError(v13, "FwpsOpenToken0", v12, 1);
          if ( SidFromToken )
            goto LABEL_33;
          goto LABEL_37;
        }
        SidFromToken = GetSidFromToken(accessToken, &v18);
        if ( SidFromToken )
          goto LABEL_33;
        v14 = *(_QWORD *)(*(_QWORD *)(a1 + 392) + 24LL);
        if ( !*(_DWORD *)(v14 + v11 + 4) )
          break;
        if ( accessToken )
        {
          CloseHandle(accessToken);
LABEL_29:
          accessToken = 0;
        }
        ++v6;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 392) + 24LL) + v11 + 16) = v18;
        v4 = *(_QWORD *)(a1 + 392);
        if ( v6 >= *(_DWORD *)(v4 + 16) )
          goto LABEL_37;
      }
      if ( *(_DWORD *)(v14 + v11 + 8) )
        *(_QWORD *)(a1 + 408) = accessToken;
      else
        *(_QWORD *)(a1 + 400) = accessToken;
      goto LABEL_29;
    }
  }
  v4 = *(_QWORD *)(a1 + 392);
  v3 = v4;
  if ( !v4 )
    goto LABEL_4;
  v5 = (_DWORD *)(v4 + 16);
  if ( *(_DWORD *)(v4 + 16) )
    goto LABEL_18;
LABEL_5:
  if ( *(_DWORD *)(a1 + 312) != 2 || *(_DWORD *)(a1 + 372) != 1 )
  {
LABEL_18:
    SidFromToken = 0;
    if ( !v4 )
      return IkeReturnError(SidFromToken, "IkeMapAcquireIdToInternal");
    goto LABEL_19;
  }
  v6 = 0;
  SidFromToken = IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken(a1);
  if ( SidFromToken )
  {
LABEL_33:
    v15 = *(_QWORD *)(a1 + 392);
    if ( v15 )
    {
      for ( ; v6 < *(_DWORD *)(v15 + 16); v15 = *(_QWORD *)(a1 + 392) )
      {
        v16 = v6++;
        *(_QWORD *)(*(_QWORD *)(v15 + 24) + 24 * v16 + 16) = 0;
      }
      IkeFreeIpsecIdSids(v15);
    }
  }
LABEL_37:
  if ( accessToken )
    CloseHandle(accessToken);
  return IkeReturnError(SidFromToken, "IkeMapAcquireIdToInternal");
}

```

## disassembly

```asm
0x18002f080  mov     [rsp+arg_8], rbx
0x18002f085  mov     [rsp+arg_10], rbp
0x18002f08a  push    rsi
0x18002f08b  push    rdi
0x18002f08c  push    r14
0x18002f08e  sub     rsp, 40h
0x18002f092  mov     rax, cs:__security_cookie
0x18002f099  xor     rax, rsp
0x18002f09c  mov     [rsp+58h+var_28], rax
0x18002f0a1  xor     r14d, r14d
0x18002f0a4  mov     rbx, rcx
0x18002f0a7  test    dword ptr [rcx+178h], 4000h
0x18002f0b1  mov     [rsp+58h+accessToken], r14
0x18002f0b6  mov     [rsp+58h+var_38], r14
0x18002f0bb  jz      loc_18002F145
0x18002f0c1  mov     rax, [rcx+188h]
0x18002f0c8  test    rax, rax
0x18002f0cb  jnz     short loc_18002F103
0x18002f0cd  mov     rdx, rax
0x18002f0d0  add     rax, 10h
0x18002f0d4  cmp     dword ptr [rcx+138h], 2
0x18002f0db  jnz     loc_18002F166
0x18002f0e1  cmp     dword ptr [rcx+174h], 1
0x18002f0e8  jnz     short loc_18002F166
0x18002f0ea  mov     edi, r14d
0x18002f0ed  call    IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken
0x18002f0f2  mov     rsi, rax
0x18002f0f5  test    rax, rax
0x18002f0f8  jnz     loc_18002F264
0x18002f0fe  jmp     loc_18002F2A5
0x18002f103  mov     r8d, [rax+10h]
0x18002f107  test    r8d, r8d
0x18002f10a  jz      short loc_18002F145
0x18002f10c  mov     r9, [rax+18h]
0x18002f110  mov     edx, r14d
0x18002f113  mov     eax, edx
0x18002f115  lea     rcx, [rax+rax*2]
0x18002f119  cmp     dword ptr [r9+rcx*8], 1
0x18002f11e  jnz     short loc_18002F12E
0x18002f120  cmp     [r9+rcx*8+4], r14d
0x18002f125  jnz     short loc_18002F12E
0x18002f127  cmp     [r9+rcx*8+8], r14d
0x18002f12c  jz      short loc_18002F135
0x18002f12e  inc     edx
0x18002f130  cmp     edx, r8d
0x18002f133  jb      short loc_18002F113
0x18002f135  mov     rdx, [rbx+188h]
0x18002f13c  mov     rsi, r14
0x18002f13f  lea     rax, [rdx+10h]
0x18002f143  jmp     short loc_18002F172
0x18002f145  mov     rdx, [rcx+188h]
0x18002f14c  mov     rax, rdx
0x18002f14f  test    rdx, rdx
0x18002f152  jz      loc_18002F0D0
0x18002f158  cmp     [rdx+10h], r14d
0x18002f15c  lea     rax, [rdx+10h]
0x18002f160  jz      loc_18002F0D4
0x18002f166  mov     rsi, r14
0x18002f169  test    rdx, rdx
0x18002f16c  jz      loc_18002F2B5
0x18002f172  cmp     [rax], r14d
0x18002f175  jbe     loc_18002F2B5
0x18002f17b  mov     edi, r14d
0x18002f17e  xchg    ax, ax
0x18002f180  mov     rdx, [rdx+18h]
0x18002f184  lea     r9, [rsp+58h+accessToken]; accessToken
0x18002f189  mov     eax, edi
0x18002f18b  mov     r8d, 0Ah; desiredAccess
0x18002f191  lea     rcx, [rax+rax*2]
0x18002f195  mov     rdx, [rdx+rcx*8+10h]; modifiedId
0x18002f19a  lea     rbp, ds:0[rcx*8]
0x18002f1a2  mov     rcx, cs:gIkeExtGlobals
0x18002f1a9  mov     rcx, [rcx+0AB0h]; engineHandle
0x18002f1b0  call    cs:__imp_FwpsOpenToken0
0x18002f1b6  test    eax, eax
0x18002f1b8  jnz     loc_18002F247
0x18002f1be  mov     rcx, [rsp+58h+accessToken]; TokenHandle
0x18002f1c3  lea     rdx, [rsp+58h+var_38]
0x18002f1c8  call    GetSidFromToken
0x18002f1cd  mov     rsi, rax
0x18002f1d0  test    rax, rax
0x18002f1d3  jnz     loc_18002F264
0x18002f1d9  mov     rax, [rbx+188h]
0x18002f1e0  mov     rcx, [rax+18h]
0x18002f1e4  cmp     [rcx+rbp+4], r14d
0x18002f1e9  jnz     short loc_18002F209
0x18002f1eb  mov     rax, [rsp+58h+accessToken]
0x18002f1f0  cmp     [rcx+rbp+8], r14d
0x18002f1f5  jnz     short loc_18002F200
0x18002f1f7  mov     [rbx+190h], rax
0x18002f1fe  jmp     short loc_18002F219
0x18002f200  mov     [rbx+198h], rax
0x18002f207  jmp     short loc_18002F219
0x18002f209  mov     rcx, [rsp+58h+accessToken]; hObject
0x18002f20e  test    rcx, rcx
0x18002f211  jz      short loc_18002F21E
0x18002f213  call    cs:__imp_CloseHandle
0x18002f219  mov     [rsp+58h+accessToken], r14
0x18002f21e  mov     rax, [rbx+188h]
0x18002f225  inc     edi
0x18002f227  mov     rcx, [rax+18h]
0x18002f22b  mov     rax, [rsp+58h+var_38]
0x18002f230  mov     [rcx+rbp+10h], rax
0x18002f235  mov     rdx, [rbx+188h]
0x18002f23c  cmp     edi, [rdx+10h]
0x18002f23f  jb      loc_18002F180
0x18002f245  jmp     short loc_18002F2A5
0x18002f247  mov     r9d, 1
0x18002f24d  lea     rdx, aFwpsopentoken0; "FwpsOpenToken0"
0x18002f254  mov     r8d, eax
0x18002f257  call    WfpReportSysErrorAsWinError
0x18002f25c  mov     rsi, rax
0x18002f25f  test    rax, rax
0x18002f262  jz      short loc_18002F2A5
0x18002f264  mov     rdx, [rbx+188h]
0x18002f26b  test    rdx, rdx
0x18002f26e  jz      short loc_18002F2A5
0x18002f270  cmp     edi, [rdx+10h]
0x18002f273  jnb     short loc_18002F29D
0x18002f275  nop     word ptr [rax+rax+00000000h]
0x18002f280  mov     eax, edi
0x18002f282  inc     edi
0x18002f284  lea     rcx, [rax+rax*2]
0x18002f288  mov     rax, [rdx+18h]
0x18002f28c  mov     [rax+rcx*8+10h], r14
0x18002f291  mov     rdx, [rbx+188h]
0x18002f298  cmp     edi, [rdx+10h]
0x18002f29b  jb      short loc_18002F280
0x18002f29d  mov     rcx, rdx
0x18002f2a0  call    IkeFreeIpsecIdSids
0x18002f2a5  mov     rcx, [rsp+58h+accessToken]; hObject
0x18002f2aa  test    rcx, rcx
0x18002f2ad  jz      short loc_18002F2B5
0x18002f2af  call    cs:__imp_CloseHandle
0x18002f2b5  lea     rdx, aIkemapacquirei; "IkeMapAcquireIdToInternal"
0x18002f2bc  mov     rcx, rsi
0x18002f2bf  call    IkeReturnError
0x18002f2c4  mov     rcx, [rsp+58h+var_28]
0x18002f2c9  xor     rcx, rsp; StackCookie
0x18002f2cc  call    __security_check_cookie
0x18002f2d1  mov     rbx, [rsp+58h+arg_8]
0x18002f2d6  mov     rbp, [rsp+58h+arg_10]
0x18002f2db  add     rsp, 40h
0x18002f2df  pop     r14
0x18002f2e1  pop     rdi
0x18002f2e2  pop     rsi
0x18002f2e3  retn
```
