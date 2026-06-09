# SNMPDeleteBoundaryFromInterface

- ea: `0x180034f44`
- end: `0x1800350d7`
- name: `SNMPDeleteBoundaryFromInterface`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007800`

## callees

- `0x180002978`
- `0x18000ac60`
- `0x1800316d0`
- `0x1800318b8`
- `0x180031b64`
- `0x180031cac`
- `0x180033c60`
- `0x180034f44`
- `0x18003cac0`
- `0x18003cce8`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180034f76`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003507d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003508c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180034f76`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003507d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003508c`
- `ntdll!RtlReleaseResource` at `0x180034fcb`
- `ntdll!RtlReleaseResource` at `0x18003505d`
- `ntdll!RtlReleaseResource` at `0x1800350b1`
- `ntdll!RtlReleaseResource` at `0x1800350be`
- `ntdll!RtlReleaseResource` at `0x180034fcb`
- `ntdll!RtlReleaseResource` at `0x18003505d`
- `ntdll!RtlReleaseResource` at `0x1800350b1`
- `ntdll!RtlReleaseResource` at `0x1800350be`

## string_xrefs

- `0x180034f85`: `SNMPDeleteBoundaryFromInterface: converting old ranges`
- `0x180035030`: `SNMPDeleteBoundaryFromInterface: converting new ranges`

## pseudocode

```c
__int64 __fastcall SNMPDeleteBoundaryFromInterface(unsigned int a1, int a2, int a3)
{
  __int64 BIfEntry; // rax
  void *v7; // rbp
  __int64 v9; // rsi
  int v10; // r15d
  _QWORD *v11; // rcx
  __int64 v12; // rbx
  _QWORD *v13; // r14
  unsigned int v14; // ebx
  __int128 v15; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v16[5]; // [rsp+30h] [rbp-58h] BYREF

  v15 = 0;
  v16[0] = 0;
  RtlAcquireResourceExclusive(&stru_18008C560, 1u);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"SNMPDeleteBoundaryFromInterface: converting old ranges");
  ConvertIfTableToRanges(a1, &v15);
  BIfEntry = FindBIfEntry(a1);
  v7 = (void *)BIfEntry;
  if ( BIfEntry )
  {
    v9 = BIfEntry + 40;
    v10 = 0;
    v11 = *(_QWORD **)(BIfEntry + 40);
    if ( v11 != (_QWORD *)(BIfEntry + 40) )
    {
      do
      {
        v12 = v11[2];
        v13 = (_QWORD *)*v11;
        if ( *(_DWORD *)(v12 + 16) == a2 && *(_DWORD *)(v12 + 20) == a3 )
        {
          DeleteBoundaryFromInterface(v11, v7);
          if ( !*(_DWORD *)(v12 + 24) && *(_QWORD *)(v12 + 32) == v12 + 32 )
          {
            DeleteScope((__int64 *)v12);
            v10 = 1;
          }
        }
        v11 = v13;
      }
      while ( v13 != (_QWORD *)v9 );
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"SNMPDeleteBoundaryFromInterface: converting new ranges");
    ConvertIfTableToRanges(a1, v16);
    RtlReleaseResource(&stru_18008C560);
    ProcessIfRangeDeltas(a1, &v15, v16);
    RtlAcquireResourceExclusive(&Resource, 1u);
    RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
    if ( v10 )
      ProcessSaveGlobalConfigInfo(1u);
    v14 = ProcessSaveInterfaceConfigInfo(a1);
    RtlReleaseResource(&stru_18008C4A0);
    RtlReleaseResource(&Resource);
    return v14;
  }
  else
  {
    FreeRangeList(&v15);
    RtlReleaseResource(&stru_18008C560);
    return 0;
  }
}

```

## disassembly

```asm
0x180034f44  push    rbx
0x180034f46  push    rbp
0x180034f47  push    rsi
0x180034f48  push    rdi
0x180034f49  push    r12
0x180034f4b  push    r13
0x180034f4d  push    r14
0x180034f4f  push    r15
0x180034f51  sub     rsp, 48h
0x180034f55  mov     r13d, edx
0x180034f58  mov     edi, ecx
0x180034f5a  xorps   xmm0, xmm0
0x180034f5d  lea     rcx, stru_18008C560; Resource
0x180034f64  xorps   xmm1, xmm1
0x180034f67  mov     dl, 1; Wait
0x180034f69  movups  [rsp+88h+var_68], xmm0
0x180034f6e  mov     r12d, r8d
0x180034f71  movups  [rsp+88h+var_58], xmm1
0x180034f76  call    cs:__imp_RtlAcquireResourceExclusive
0x180034f7c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180034f83  jz      short loc_180034F9F
0x180034f85  lea     r8, aSnmpdeleteboun_0; "SNMPDeleteBoundaryFromInterface: conver"...
0x180034f8c  lea     rdx, RasRtrmgrTraceInfo
0x180034f93  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180034f9a  call    McTemplateU0z_EventWriteTransfer
0x180034f9f  lea     rdx, [rsp+88h+var_68]
0x180034fa4  mov     ecx, edi
0x180034fa6  call    ConvertIfTableToRanges
0x180034fab  mov     ecx, edi
0x180034fad  call    FindBIfEntry
0x180034fb2  mov     rbp, rax
0x180034fb5  test    rax, rax
0x180034fb8  jnz     short loc_180034FD8
0x180034fba  lea     rcx, [rsp+88h+var_68]
0x180034fbf  call    FreeRangeList
0x180034fc4  lea     rcx, stru_18008C560; Resource
0x180034fcb  call    cs:__imp_RtlReleaseResource
0x180034fd1  xor     eax, eax
0x180034fd3  jmp     loc_1800350C6
0x180034fd8  lea     rsi, [rax+28h]
0x180034fdc  xor     r15d, r15d
0x180034fdf  mov     rcx, [rsi]; lpMem
0x180034fe2  cmp     rcx, rsi
0x180034fe5  jz      short loc_180035027
0x180034fe7  mov     rbx, [rcx+10h]
0x180034feb  mov     r14, [rcx]
0x180034fee  cmp     [rbx+10h], r13d
0x180034ff2  jnz     short loc_18003501F
0x180034ff4  cmp     [rbx+14h], r12d
0x180034ff8  jnz     short loc_18003501F
0x180034ffa  mov     rdx, rbp; LPVOID
0x180034ffd  call    DeleteBoundaryFromInterface
0x180035002  cmp     dword ptr [rbx+18h], 0
0x180035006  jnz     short loc_18003501F
0x180035008  lea     rax, [rbx+20h]
0x18003500c  cmp     [rax], rax
0x18003500f  jnz     short loc_18003501F
0x180035011  mov     rcx, rbx
0x180035014  call    DeleteScope
0x180035019  mov     r15d, 1
0x18003501f  mov     rcx, r14
0x180035022  cmp     r14, rsi
0x180035025  jnz     short loc_180034FE7
0x180035027  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003502e  jz      short loc_18003504A
0x180035030  lea     r8, aSnmpdeleteboun; "SNMPDeleteBoundaryFromInterface: conver"...
0x180035037  lea     rdx, RasRtrmgrTraceInfo
0x18003503e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180035045  call    McTemplateU0z_EventWriteTransfer
0x18003504a  lea     rdx, [rsp+88h+var_58]
0x18003504f  mov     ecx, edi
0x180035051  call    ConvertIfTableToRanges
0x180035056  lea     rcx, stru_18008C560; Resource
0x18003505d  call    cs:__imp_RtlReleaseResource
0x180035063  lea     r8, [rsp+88h+var_58]
0x180035068  mov     ecx, edi
0x18003506a  lea     rdx, [rsp+88h+var_68]
0x18003506f  call    ProcessIfRangeDeltas
0x180035074  mov     dl, 1; Wait
0x180035076  lea     rcx, Resource; Resource
0x18003507d  call    cs:__imp_RtlAcquireResourceExclusive
0x180035083  mov     dl, 1; Wait
0x180035085  lea     rcx, stru_18008C4A0; Resource
0x18003508c  call    cs:__imp_RtlAcquireResourceExclusive
0x180035092  test    r15d, r15d
0x180035095  jz      short loc_1800350A1
0x180035097  mov     ecx, 1
0x18003509c  call    ProcessSaveGlobalConfigInfo
0x1800350a1  mov     ecx, edi
0x1800350a3  call    ProcessSaveInterfaceConfigInfo
0x1800350a8  lea     rcx, stru_18008C4A0; Resource
0x1800350af  mov     ebx, eax
0x1800350b1  call    cs:__imp_RtlReleaseResource
0x1800350b7  lea     rcx, Resource; Resource
0x1800350be  call    cs:__imp_RtlReleaseResource
0x1800350c4  mov     eax, ebx
0x1800350c6  add     rsp, 48h
0x1800350ca  pop     r15
0x1800350cc  pop     r14
0x1800350ce  pop     r13
0x1800350d0  pop     r12
0x1800350d2  pop     rdi
0x1800350d3  pop     rsi
0x1800350d4  pop     rbp
0x1800350d5  pop     rbx
0x1800350d6  retn
```
