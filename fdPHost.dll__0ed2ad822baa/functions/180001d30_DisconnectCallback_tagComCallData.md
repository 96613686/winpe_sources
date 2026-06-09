# DisconnectCallback(tagComCallData *)

- ea: `0x180001d30`
- end: `0x180001eab`
- name: `?DisconnectCallback@@YAJPEAUtagComCallData@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001d30`
- `0x18000284c`
- `0x180002a00`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180001dcb`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180001dcb`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180001e98`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180001e98`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180001e16`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180001e16`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001e66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001e66`

## pseudocode

```c
__int64 __fastcall DisconnectCallback(struct tagComCallData *a1)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  void (__fastcall *v3)(_QWORD); // rax
  void (__fastcall *v4)(_QWORD); // rax
  HRESULT v5; // eax
  int v6; // edx
  bool v7; // cf
  HRESULT v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // edi
  bool v11; // cf
  __int64 j; // rbx
  HMODULE v13; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
  for ( i = 0; i != 2; ++i )
  {
    if ( *((_DWORD *)&g_arydwRegister + i) )
    {
      v2 = 7 * i;
      if ( qword_180007018[7 * i] )
      {
        v3 = (void (__fastcall *)(_QWORD))qword_180007028[v2 + 1];
        if ( v3 )
          v3(0);
        if ( qword_180007018[v2] )
        {
          v4 = (void (__fastcall *)(_QWORD))qword_180007018[v2 + 1];
          if ( v4 )
            v4(0);
        }
      }
      v5 = CoRevokeClassObject(*((_DWORD *)&g_arydwRegister + i));
      v6 = 0;
      if ( v5 )
        v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
      else
        v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        LOBYTE(v6) = !v7;
        if ( v6 )
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17);
      }
    }
  }
  v8 = CoDisconnectContext(0xFFFFFFFF);
  v9 = 0;
  v10 = v8;
  if ( v8 )
    v11 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v11 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  LOBYTE(v9) = !v11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (_DWORD)v9 )
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
  for ( j = 0; j != 2; ++j )
  {
    v13 = (HMODULE)qword_180007018[7 * j];
    if ( v13 )
      FreeLibrary(v13);
  }
  if ( g_pSharedService )
  {
    (*(void (__fastcall **)(struct CFdphostSharedService *, __int64))(*(_QWORD *)g_pSharedService + 16LL))(
      g_pSharedService,
      v9);
    g_pSharedService = 0;
  }
  CoFreeUnusedLibraries();
  return v10;
}

```

## disassembly

```asm
0x180001d30  push    rbx
0x180001d32  push    rdi
0x180001d33  push    r14
0x180001d35  push    r15
0x180001d37  sub     rsp, 38h
0x180001d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d42  lea     r15, WPP_GLOBAL_Control
0x180001d49  cmp     rcx, r15
0x180001d4c  jz      short loc_180001D69
0x180001d4e  cmp     byte ptr [rcx+19h], 4
0x180001d52  jb      short loc_180001D69
0x180001d54  mov     rcx, [rcx+10h]
0x180001d58  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x180001d5f  mov     edx, 10h
0x180001d64  call    WPP_SF_s
0x180001d69  xor     ebx, ebx
0x180001d6b  lea     r14, cs:180000000h
0x180001d72  cmp     dword ptr rva ?g_arydwRegister@@3PAKA[r14+rbx*4], 0; ulong near * g_arydwRegister ...
0x180001d7b  jz      loc_180001E06
0x180001d81  imul    rdi, rbx, 38h ; '8'
0x180001d85  cmp     qword ptr [rdi+r14+7018h], 0
0x180001d8e  jz      short loc_180001DC3
0x180001d90  mov     rax, [rdi+r14+7030h]
0x180001d98  test    rax, rax
0x180001d9b  jz      short loc_180001DA4
0x180001d9d  xor     ecx, ecx
0x180001d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da4  cmp     qword ptr [rdi+r14+7018h], 0
0x180001dad  jz      short loc_180001DC3
0x180001daf  mov     rax, [rdi+r14+7020h]
0x180001db7  test    rax, rax
0x180001dba  jz      short loc_180001DC3
0x180001dbc  xor     ecx, ecx
0x180001dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dc3  mov     ecx, dword ptr rva ?g_arydwRegister@@3PAKA[r14+rbx*4]; dwRegister
0x180001dcb  call    cs:__imp_CoRevokeClassObject
0x180001dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180001dd8  xor     edx, edx
0x180001dda  test    eax, eax
0x180001ddc  jnz     short loc_180001DE4
0x180001dde  cmp     byte ptr [rcx+19h], 4
0x180001de2  jmp     short loc_180001DE8
0x180001de4  cmp     byte ptr [rcx+19h], 2
0x180001de8  setnb   dl
0x180001deb  cmp     rcx, r15
0x180001dee  jz      short loc_180001E06
0x180001df0  test    edx, edx
0x180001df2  jz      short loc_180001E06
0x180001df4  mov     rcx, [rcx+10h]
0x180001df8  mov     edx, 11h
0x180001dfd  mov     [rsp+58h+var_38], eax
0x180001e01  call    WPP_SF_sd
0x180001e06  inc     rbx
0x180001e09  cmp     rbx, 2
0x180001e0d  jnz     loc_180001D72
0x180001e13  or      ecx, 0FFFFFFFFh; dwTimeout
0x180001e16  call    cs:__imp_CoDisconnectContext
0x180001e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e23  xor     edx, edx
0x180001e25  mov     edi, eax
0x180001e27  test    eax, eax
0x180001e29  jnz     short loc_180001E31
0x180001e2b  cmp     byte ptr [rcx+19h], 4
0x180001e2f  jmp     short loc_180001E35
0x180001e31  cmp     byte ptr [rcx+19h], 2
0x180001e35  setnb   dl
0x180001e38  cmp     rcx, r15
0x180001e3b  jz      short loc_180001E53
0x180001e3d  test    edx, edx
0x180001e3f  jz      short loc_180001E53
0x180001e41  mov     rcx, [rcx+10h]
0x180001e45  mov     edx, 12h
0x180001e4a  mov     [rsp+58h+var_38], edi
0x180001e4e  call    WPP_SF_sd
0x180001e53  xor     ebx, ebx
0x180001e55  imul    rax, rbx, 38h ; '8'
0x180001e59  mov     rcx, [rax+r14+7018h]; hLibModule
0x180001e61  test    rcx, rcx
0x180001e64  jz      short loc_180001E6C
0x180001e66  call    cs:__imp_FreeLibrary
0x180001e6c  inc     rbx
0x180001e6f  cmp     rbx, 2
0x180001e73  jnz     short loc_180001E55
0x180001e75  mov     rcx, cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA; CFdphostSharedService * g_pSharedService
0x180001e7c  test    rcx, rcx
0x180001e7f  jz      short loc_180001E98
0x180001e81  mov     rax, [rcx]
0x180001e84  mov     rax, [rax+10h]
0x180001e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e8d  mov     cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA, 0; CFdphostSharedService * g_pSharedService
0x180001e98  call    cs:__imp_CoFreeUnusedLibraries
0x180001e9e  mov     eax, edi
0x180001ea0  add     rsp, 38h
0x180001ea4  pop     r15
0x180001ea6  pop     r14
0x180001ea8  pop     rdi
0x180001ea9  pop     rbx
0x180001eaa  retn
```
