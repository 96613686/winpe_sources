# ProcessScanResult(_TRUST_SCAN_CONTEXT *)

- ea: `0x180031cd8`
- end: `0x180031d67`
- name: `?ProcessScanResult@@YAKPEAU_TRUST_SCAN_CONTEXT@@@Z`
- size: `143`
- prototype: `unsigned int __fastcall(struct _TRUST_SCAN_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180031d70`

## callees

- `0x18000fd40`
- `0x180031abc`
- `0x180031cd8`

## import_xrefs

- `LSASRV!LsaIOpenPolicyTrusted` at `0x180031cf3`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180031cf3`
- `LSASRV!LsarClose` at `0x180031d54`
- `LSASRV!LsarClose` at `0x180031d54`
- `ntdll!RtlNtStatusToDosError` at `0x180031d26`
- `ntdll!RtlNtStatusToDosError` at `0x180031d26`

## pseudocode

```c
__int64 __fastcall ProcessScanResult(struct _TRUST_SCAN_CONTEXT *a1)
{
  int v2; // eax
  NTSTATUS v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v2 = LsaIOpenPolicyTrusted(&v7);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        (unsigned int)v2);
    v4 = RtlNtStatusToDosError(v3);
    goto LABEL_5;
  }
  if ( (*((_BYTE *)a1 + 40) & 8) != 0 )
  {
    v4 = ProcessForestTrustScanResult(v7, a1);
LABEL_5:
    v5 = v4;
    goto LABEL_9;
  }
  v5 = 0;
LABEL_9:
  if ( v7 )
    LsarClose(&v7);
  return v5;
}

```

## disassembly

```asm
0x180031cd8  mov     [rsp+arg_0], rbx
0x180031cdd  push    rdi
0x180031cde  sub     rsp, 20h
0x180031ce2  mov     rdi, rcx
0x180031ce5  mov     [rsp+28h+arg_8], 0
0x180031cee  lea     rcx, [rsp+28h+arg_8]
0x180031cf3  call    cs:__imp_LsaIOpenPolicyTrusted
0x180031cf9  mov     ebx, eax
0x180031cfb  test    eax, eax
0x180031cfd  jns     short loc_180031D30
0x180031cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d06  test    byte ptr [rcx+1Ch], 10h
0x180031d0a  jz      short loc_180031D24
0x180031d0c  mov     rcx, [rcx+10h]
0x180031d10  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x180031d17  mov     edx, 21h ; '!'
0x180031d1c  mov     r9d, eax
0x180031d1f  call    WPP_SF_d
0x180031d24  mov     ecx, ebx; Status
0x180031d26  call    cs:__imp_RtlNtStatusToDosError
0x180031d2c  mov     ebx, eax
0x180031d2e  jmp     short loc_180031D47
0x180031d30  test    byte ptr [rdi+28h], 8
0x180031d34  jz      short loc_180031D45
0x180031d36  mov     rcx, [rsp+28h+arg_8]; void *
0x180031d3b  mov     rdx, rdi; struct _TRUST_SCAN_CONTEXT *
0x180031d3e  call    ?ProcessForestTrustScanResult@@YAKPEAXPEAU_TRUST_SCAN_CONTEXT@@@Z; ProcessForestTrustScanResult(void *,_TRUST_SCAN_CONTEXT *)
0x180031d43  jmp     short loc_180031D2C
0x180031d45  xor     ebx, ebx
0x180031d47  cmp     [rsp+28h+arg_8], 0
0x180031d4d  jz      short loc_180031D5A
0x180031d4f  lea     rcx, [rsp+28h+arg_8]
0x180031d54  call    cs:__imp_LsarClose
0x180031d5a  mov     eax, ebx
0x180031d5c  mov     rbx, [rsp+28h+arg_0]
0x180031d61  add     rsp, 20h
0x180031d65  pop     rdi
0x180031d66  retn
```
