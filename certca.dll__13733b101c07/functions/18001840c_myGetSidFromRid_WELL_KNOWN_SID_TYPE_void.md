# myGetSidFromRid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x18001840c`
- end: `0x18001848d`
- name: `?myGetSidFromRid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `129`
- prototype: `__int64 __fastcall(enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800185b4`
- `0x180018620`

## callees

- `0x180008400`
- `0x180012450`
- `0x18001840c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018428`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001847a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001847a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180018456`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180018456`

## pseudocode

```c
__int64 __fastcall myGetSidFromRid(enum WELL_KNOWN_SID_TYPE a1, void **a2)
{
  HLOCAL v3; // rax
  void *v4; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // ecx
  int v7; // edx
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 68;
  v3 = LocalAlloc(0, 0x44u);
  v4 = v3;
  if ( v3 )
  {
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, v3, &cbSid) )
    {
      *a2 = v4;
      v4 = 0;
      v5 = 0;
      goto LABEL_7;
    }
    v5 = myHLastError();
    v7 = v5;
    v6 = 619315610;
  }
  else
  {
    v5 = -2147024882;
    v6 = 618660250;
    v7 = -2147024882;
  }
  CSPrintErrorLineFile(v6, v7);
LABEL_7:
  LocalFree(v4);
  return v5;
}

```

## disassembly

```asm
0x18001840c  mov     [rsp+arg_8], rbx
0x180018411  mov     [rsp+cbSid], ecx
0x180018415  push    rdi
0x180018416  sub     rsp, 20h
0x18001841a  mov     rbx, rdx
0x18001841d  xor     ecx, ecx; uFlags
0x18001841f  mov     edx, 44h ; 'D'; uBytes
0x180018424  mov     [rsp+28h+cbSid], edx
0x180018428  call    cs:__imp_LocalAlloc
0x18001842e  mov     rdi, rax
0x180018431  test    rax, rax
0x180018434  jnz     short loc_180018449
0x180018436  mov     ebx, 8007000Eh
0x18001843b  mov     ecx, 24E0019Ah; unsigned int
0x180018440  mov     edx, ebx; int
0x180018442  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180018447  jmp     short loc_180018477
0x180018449  xor     edx, edx; DomainSid
0x18001844b  lea     r9, [rsp+28h+cbSid]; cbSid
0x180018450  mov     r8, rdi; pSid
0x180018453  lea     ecx, [rdx+16h]; WellKnownSidType
0x180018456  call    cs:__imp_CreateWellKnownSid
0x18001845c  test    eax, eax
0x18001845e  jnz     short loc_180018470
0x180018460  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018465  mov     ebx, eax
0x180018467  mov     edx, eax
0x180018469  mov     ecx, 24EA019Ah
0x18001846e  jmp     short loc_180018442
0x180018470  mov     [rbx], rdi
0x180018473  xor     edi, edi
0x180018475  xor     ebx, ebx
0x180018477  mov     rcx, rdi; hMem
0x18001847a  call    cs:__imp_LocalFree
0x180018480  mov     eax, ebx
0x180018482  mov     rbx, [rsp+28h+arg_8]
0x180018487  add     rsp, 20h
0x18001848b  pop     rdi
0x18001848c  retn
```
