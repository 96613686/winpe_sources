# EuChangeEntryType

- ea: `0x1800126c8`
- end: `0x1800128db`
- name: `EuChangeEntryType`
- size: `531`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180013b90`
- `0x18001f380`
- `0x18001f930`
- `0x18001fa78`

## callees

- `0x180011a54`
- `0x1800126c8`
- `0x18003b57c`
- `0x18003b7ac`
- `0x18003c43c`
- `0x18003c860`

## import_xrefs

- `RASAPI32!DestroyPortNode` at `0x18001289f`
- `RASAPI32!DestroyPortNode` at `0x18001289f`
- `RASAPI32!ChangeEntryType` at `0x1800126ec`
- `RASAPI32!ChangeEntryType` at `0x1800126ec`
- `RASAPI32!CreatePortNode` at `0x1800127b9`
- `RASAPI32!CreatePortNode` at `0x1800127b9`
- `RASAPI32!SetDefaultModemSettings` at `0x180012888`
- `RASAPI32!SetDefaultModemSettings` at `0x180012888`
- `RASAPI32!CopyToPbport` at `0x180012873`
- `RASAPI32!CopyToPbport` at `0x180012873`
- `RASAPI32!DestroyLinkNode` at `0x180012700`
- `RASAPI32!DestroyLinkNode` at `0x180012700`
- `RASAPI32!CreateLinkNode` at `0x180012719`
- `RASAPI32!CreateLinkNode` at `0x180012719`
- `rtutils!TracePrintfExA` at `0x1800127a9`
- `rtutils!TracePrintfExA` at `0x1800127a9`

## string_xrefs

- `0x18001279d`: `No ports configured`

## pseudocode

```c
__int64 __fastcall EuChangeEntryType(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int v4; // r14d
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  _QWORD *LinkNode; // rdx
  int v9; // r15d
  __int64 v10; // rdx
  __int64 v11; // rbp
  __int64 PortNode; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rsi
  int v18; // ecx
  __int64 v19; // rax

  v3 = *(_QWORD *)(a1 + 872);
  v4 = a2;
  if ( (unsigned int)a2 > 0xFFFFFFFD )
    a2 = 1;
  ChangeEntryType(v3, a2);
  while ( 1 )
  {
    v6 = *(_QWORD *)(a1 + 872);
    v7 = **(_QWORD ***)(v6 + 32);
    if ( !v7 )
      break;
    DtlRemoveNode(*(_QWORD *)(v6 + 32), v7);
    DestroyLinkNode(v5);
  }
  LinkNode = (_QWORD *)CreateLinkNode();
  if ( !LinkNode )
    return 8;
  DtlAddNodeLast(*(_QWORD *)(*(_QWORD *)(a1 + 872) + 32LL), LinkNode);
  v9 = 0;
  v11 = *(_QWORD *)(v10 + 16);
  PortNode = 0;
  v13 = 0xFFFFFFFFLL;
  v14 = **(_QWORD **)(a1 + 880);
  if ( !v14 )
    goto LABEL_18;
  do
  {
    if ( v4 != -1 )
    {
      v15 = *(_QWORD *)(v14 + 16);
      if ( v4 == -2 )
      {
        if ( *(_DWORD *)(v15 + 44) == 2 )
          goto LABEL_15;
      }
      else if ( *(_DWORD *)(v15 + 44) != v4 )
      {
        goto LABEL_15;
      }
    }
    ++v9;
    if ( !PortNode )
      PortNode = v14;
LABEL_15:
    v14 = *(_QWORD *)(v14 + 8);
  }
  while ( v14 );
  if ( PortNode )
  {
    *(_DWORD *)(a1 + 904) = 0;
    goto LABEL_21;
  }
LABEL_18:
  v16 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "No ports configured");
  *(_DWORD *)(a1 + 904) = 1;
  PortNode = CreatePortNode(v16, v13);
  if ( PortNode )
  {
LABEL_21:
    v17 = *(_QWORD *)(PortNode + 16);
    if ( !v9 )
    {
      v18 = *(_DWORD *)(*(_QWORD *)(a1 + 872) + 24LL);
      if ( v18 == 1 )
      {
        *(_QWORD *)v17 = PszFromId(g_hinstDll, 0xE8u);
        v19 = StrDup(L"serial");
        *(_DWORD *)(v17 + 40) = 3;
        goto LABEL_27;
      }
      if ( v18 == 2 )
      {
        *(_QWORD *)v17 = PszFromId(g_hinstDll, 0x1F9u);
        v19 = StrDup(L"rastapi");
        *(_DWORD *)(v17 + 40) = 11;
      }
      else
      {
        *(_QWORD *)v17 = PszFromId(g_hinstDll, 0x63Au);
        v19 = StrDup(L"rastapi");
        *(_DWORD *)(v17 + 40) = 18;
LABEL_27:
        *(_DWORD *)(v17 + 48) |= 8u;
      }
      *(_QWORD *)(v17 + 24) = v19;
      *(_DWORD *)(v17 + 12) = 0;
    }
    CopyToPbport(v11, v17);
    if ( *(_DWORD *)(v11 + 40) == 3 || (*(_BYTE *)(v11 + 48) & 4) != 0 )
      SetDefaultModemSettings(v11);
  }
  if ( *(_DWORD *)(a1 + 904) )
  {
    if ( PortNode )
    {
      DestroyPortNode(PortNode);
LABEL_36:
      if ( *(_QWORD *)v11 && *(_QWORD *)(v11 + 24) )
      {
        AppendDisabledPorts(a1, v4);
        return 0;
      }
    }
  }
  else if ( PortNode )
  {
    goto LABEL_36;
  }
  return 8;
}

```

## disassembly

```asm
0x1800126c8  push    rbx
0x1800126ca  push    rbp
0x1800126cb  push    rsi
0x1800126cc  push    rdi
0x1800126cd  push    r14
0x1800126cf  push    r15
0x1800126d1  sub     rsp, 28h
0x1800126d5  mov     rbx, rcx
0x1800126d8  mov     rcx, [rcx+368h]
0x1800126df  mov     r14d, edx
0x1800126e2  cmp     edx, 0FFFFFFFDh
0x1800126e5  jbe     short loc_1800126EC
0x1800126e7  mov     edx, 1
0x1800126ec  call    cs:__imp_ChangeEntryType
0x1800126f2  jmp     short loc_180012706
0x1800126f4  mov     rcx, [rcx+20h]
0x1800126f8  call    DtlRemoveNode
0x1800126fd  mov     rcx, rdx
0x180012700  call    cs:__imp_DestroyLinkNode
0x180012706  mov     rcx, [rbx+368h]
0x18001270d  mov     rax, [rcx+20h]
0x180012711  mov     rdx, [rax]
0x180012714  test    rdx, rdx
0x180012717  jnz     short loc_1800126F4
0x180012719  call    cs:__imp_CreateLinkNode
0x18001271f  mov     rdx, rax
0x180012722  test    rax, rax
0x180012725  jz      loc_1800128C9
0x18001272b  mov     rcx, [rbx+368h]
0x180012732  mov     rcx, [rcx+20h]
0x180012736  call    DtlAddNodeLast
0x18001273b  mov     rax, [rbx+370h]
0x180012742  xor     r15d, r15d
0x180012745  mov     rbp, [rdx+10h]
0x180012749  xor     edi, edi
0x18001274b  or      edx, 0FFFFFFFFh
0x18001274e  mov     rcx, [rax]
0x180012751  test    rcx, rcx
0x180012754  jz      short loc_180012793
0x180012756  cmp     r14d, edx
0x180012759  jz      short loc_180012773
0x18001275b  mov     rax, [rcx+10h]
0x18001275f  cmp     r14d, 0FFFFFFFEh
0x180012763  jnz     short loc_18001276D
0x180012765  cmp     dword ptr [rax+2Ch], 2
0x180012769  jnz     short loc_180012773
0x18001276b  jmp     short loc_18001277D
0x18001276d  cmp     [rax+2Ch], r14d
0x180012771  jnz     short loc_18001277D
0x180012773  inc     r15d
0x180012776  test    rdi, rdi
0x180012779  cmovz   rdi, rcx
0x18001277d  mov     rcx, [rcx+8]
0x180012781  test    rcx, rcx
0x180012784  jnz     short loc_180012756
0x180012786  test    rdi, rdi
0x180012789  jz      short loc_180012793
0x18001278b  mov     [rbx+388h], ecx
0x180012791  jmp     short loc_1800127CB
0x180012793  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012799  cmp     ecx, edx
0x18001279b  jz      short loc_1800127AF
0x18001279d  lea     r8, aNoPortsConfigu; "No ports configured"
0x1800127a4  mov     edx, 0Ch; dwFlags
0x1800127a9  call    cs:__imp_TracePrintfExA
0x1800127af  mov     dword ptr [rbx+388h], 1
0x1800127b9  call    cs:__imp_CreatePortNode
0x1800127bf  mov     rdi, rax
0x1800127c2  test    rax, rax
0x1800127c5  jz      loc_18001288E
0x1800127cb  mov     rsi, [rdi+10h]
0x1800127cf  test    r15d, r15d
0x1800127d2  jnz     loc_18001286D
0x1800127d8  mov     rax, [rbx+368h]
0x1800127df  mov     ecx, [rax+18h]
0x1800127e2  cmp     ecx, 1
0x1800127e5  jnz     short loc_180012810
0x1800127e7  mov     rcx, cs:g_hinstDll; hInstance
0x1800127ee  mov     edx, 0E8h; uID
0x1800127f3  call    PszFromId
0x1800127f8  lea     rcx, aSerial; "serial"
0x1800127ff  mov     [rsi], rax
0x180012802  call    StrDup
0x180012807  mov     dword ptr [rsi+28h], 3
0x18001280e  jmp     short loc_18001285E
0x180012810  cmp     ecx, 2
0x180012813  mov     rcx, cs:g_hinstDll; hInstance
0x18001281a  jnz     short loc_18001283E
0x18001281c  mov     edx, 1F9h; uID
0x180012821  call    PszFromId
0x180012826  lea     rcx, aRastapi; "rastapi"
0x18001282d  mov     [rsi], rax
0x180012830  call    StrDup
0x180012835  mov     dword ptr [rsi+28h], 0Bh
0x18001283c  jmp     short loc_180012862
0x18001283e  mov     edx, 63Ah; uID
0x180012843  call    PszFromId
0x180012848  lea     rcx, aRastapi; "rastapi"
0x18001284f  mov     [rsi], rax
0x180012852  call    StrDup
0x180012857  mov     dword ptr [rsi+28h], 12h
0x18001285e  or      dword ptr [rsi+30h], 8
0x180012862  mov     [rsi+18h], rax
0x180012866  mov     dword ptr [rsi+0Ch], 0
0x18001286d  mov     rdx, rsi
0x180012870  mov     rcx, rbp
0x180012873  call    cs:__imp_CopyToPbport
0x180012879  cmp     dword ptr [rbp+28h], 3
0x18001287d  jz      short loc_180012885
0x18001287f  test    byte ptr [rbp+30h], 4
0x180012883  jz      short loc_18001288E
0x180012885  mov     rcx, rbp
0x180012888  call    cs:__imp_SetDefaultModemSettings
0x18001288e  cmp     dword ptr [rbx+388h], 0
0x180012895  jz      short loc_1800128A7
0x180012897  test    rdi, rdi
0x18001289a  jz      short loc_1800128C9
0x18001289c  mov     rcx, rdi
0x18001289f  call    cs:__imp_DestroyPortNode
0x1800128a5  jmp     short loc_1800128AC
0x1800128a7  test    rdi, rdi
0x1800128aa  jz      short loc_1800128C9
0x1800128ac  cmp     qword ptr [rbp+0], 0
0x1800128b1  jz      short loc_1800128C9
0x1800128b3  cmp     qword ptr [rbp+18h], 0
0x1800128b8  jz      short loc_1800128C9
0x1800128ba  mov     edx, r14d
0x1800128bd  mov     rcx, rbx
0x1800128c0  call    AppendDisabledPorts
0x1800128c5  xor     eax, eax
0x1800128c7  jmp     short loc_1800128CE
0x1800128c9  mov     eax, 8
0x1800128ce  add     rsp, 28h
0x1800128d2  pop     r15
0x1800128d4  pop     r14
0x1800128d6  pop     rdi
0x1800128d7  pop     rsi
0x1800128d8  pop     rbp
0x1800128d9  pop     rbx
0x1800128da  retn
```
