# myGetSidFromRid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x18001e46c`
- end: `0x18001e4ee`
- name: `?myGetSidFromRid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001e5f8`
- `0x18001e660`

## callees

- `0x18001e46c`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e488`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e4db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e4db`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001e4b7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001e4b7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e4a2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e4a2`

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
0x18001e46c  mov     [rsp+arg_8], rbx
0x18001e471  mov     [rsp+cbSid], ecx
0x18001e475  push    rdi
0x18001e476  sub     rsp, 20h
0x18001e47a  mov     rbx, rdx
0x18001e47d  xor     ecx, ecx; uFlags
0x18001e47f  mov     edx, 44h ; 'D'; uBytes
0x18001e484  mov     [rsp+28h+cbSid], edx
0x18001e488  call    cs:__imp_LocalAlloc
0x18001e48e  mov     rdi, rax
0x18001e491  test    rax, rax
0x18001e494  jnz     short loc_18001E4AA
0x18001e496  mov     ebx, 8007000Eh
0x18001e49b  mov     ecx, 24E0019Ah
0x18001e4a0  mov     edx, ebx
0x18001e4a2  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e4a8  jmp     short loc_18001E4D8
0x18001e4aa  xor     edx, edx; DomainSid
0x18001e4ac  lea     r9, [rsp+28h+cbSid]; cbSid
0x18001e4b1  mov     r8, rdi; pSid
0x18001e4b4  lea     ecx, [rdx+16h]; WellKnownSidType
0x18001e4b7  call    cs:__imp_CreateWellKnownSid
0x18001e4bd  test    eax, eax
0x18001e4bf  jnz     short loc_18001E4D1
0x18001e4c1  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001e4c6  mov     ebx, eax
0x18001e4c8  mov     edx, eax
0x18001e4ca  mov     ecx, 24EA019Ah
0x18001e4cf  jmp     short loc_18001E4A2
0x18001e4d1  mov     [rbx], rdi
0x18001e4d4  xor     edi, edi
0x18001e4d6  xor     ebx, ebx
0x18001e4d8  mov     rcx, rdi; hMem
0x18001e4db  call    cs:__imp_LocalFree
0x18001e4e1  mov     eax, ebx
0x18001e4e3  mov     rbx, [rsp+28h+arg_8]
0x18001e4e8  add     rsp, 20h
0x18001e4ec  pop     rdi
0x18001e4ed  retn
```
