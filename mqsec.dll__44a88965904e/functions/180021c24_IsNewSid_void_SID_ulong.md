# IsNewSid(void *,_SID * *,ulong *)

- ea: `0x180021c24`
- end: `0x180021cff`
- name: `?IsNewSid@@YAHPEAXPEAPEAU_SID@@PEAK@Z`
- size: `219`
- prototype: `__int64 __fastcall(PSID pSourceSid, struct _SID **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180023160`
- `0x180024b90`
- `0x180024dbc`

## callees

- `0x1800049ac`
- `0x18001722c`
- `0x180021c24`

## import_xrefs

- `msvcrt!free` at `0x180021ccb`
- `msvcrt!free` at `0x180021ce0`
- `msvcrt!free` at `0x180021ccb`
- `msvcrt!free` at `0x180021ce0`
- `ADVAPI32!CopySid` at `0x180021c80`
- `ADVAPI32!CopySid` at `0x180021c80`
- `ADVAPI32!EqualSid` at `0x180021c4c`
- `ADVAPI32!EqualSid` at `0x180021c4c`
- `ADVAPI32!GetLengthSid` at `0x180021c61`
- `ADVAPI32!GetLengthSid` at `0x180021c61`
- `KERNEL32!GetLastError` at `0x180021c8a`
- `KERNEL32!GetLastError` at `0x180021c8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsNewSid(PSID pSourceSid, struct _SID **a2, unsigned int *a3)
{
  __int64 i; // rbx
  DWORD LengthSid; // edi
  struct _SID *v9; // rbx
  DWORD LastError; // eax
  __int64 v11; // rax

  for ( i = 0; (unsigned int)i < *a3; i = (unsigned int)(i + 1) )
  {
    if ( EqualSid(pSourceSid, a2[i]) )
      return 0;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v9 = (struct _SID *)MmAllocate(LengthSid);
  if ( CopySid(LengthSid, v9, pSourceSid) )
  {
    v11 = *a3;
    a2[v11] = v9;
    *a3 = v11 + 1;
    free(0);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, LastError);
    free(v9);
  }
  return 1;
}

```

## disassembly

```asm
0x180021c24  mov     [rsp+arg_0], rbx
0x180021c29  mov     [rsp+arg_8], rbp
0x180021c2e  push    rsi
0x180021c2f  push    rdi
0x180021c30  push    r14
0x180021c32  sub     rsp, 20h
0x180021c36  mov     rsi, r8
0x180021c39  mov     r14, rdx
0x180021c3c  mov     rbp, rcx
0x180021c3f  xor     ebx, ebx
0x180021c41  mov     rcx, rbp; pSid
0x180021c44  cmp     ebx, [rsi]
0x180021c46  jnb     short loc_180021C61
0x180021c48  mov     rdx, [r14+rbx*8]; pSid2
0x180021c4c  call    cs:__imp_EqualSid
0x180021c52  test    eax, eax
0x180021c54  jnz     short loc_180021C5A
0x180021c56  inc     ebx
0x180021c58  jmp     short loc_180021C41
0x180021c5a  xor     eax, eax
0x180021c5c  jmp     loc_180021CEC
0x180021c61  call    cs:__imp_GetLengthSid
0x180021c67  mov     edi, eax
0x180021c69  mov     ecx, eax; unsigned __int64
0x180021c6b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180021c70  mov     rbx, rax
0x180021c73  mov     [rsp+38h+arg_10], rax
0x180021c78  mov     r8, rbp; pSourceSid
0x180021c7b  mov     rdx, rax; pDestinationSid
0x180021c7e  mov     ecx, edi; nDestinationSidLength
0x180021c80  call    cs:__imp_CopySid
0x180021c86  test    eax, eax
0x180021c88  jnz     short loc_180021CD4
0x180021c8a  call    cs:__imp_GetLastError
0x180021c90  lea     rdx, WPP_GLOBAL_Control
0x180021c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c9e  cmp     rcx, rdx
0x180021ca1  jz      short loc_180021CC8
0x180021ca3  test    byte ptr [rcx+10Ch], 1
0x180021caa  jz      short loc_180021CC8
0x180021cac  mov     edx, 0Ah
0x180021cb1  mov     r9d, eax
0x180021cb4  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180021cbb  mov     rcx, [rcx+100h]
0x180021cc2  call    WPP_SF_d
0x180021cc7  nop
0x180021cc8  mov     rcx, rbx; Block
0x180021ccb  call    cs:__imp_free
0x180021cd1  nop
0x180021cd2  jmp     short loc_180021CE7
0x180021cd4  mov     eax, [rsi]
0x180021cd6  mov     [r14+rax*8], rbx
0x180021cda  inc     eax
0x180021cdc  mov     [rsi], eax
0x180021cde  xor     ecx, ecx; Block
0x180021ce0  call    cs:__imp_free
0x180021ce6  nop
0x180021ce7  mov     eax, 1
0x180021cec  mov     rbx, [rsp+38h+arg_0]
0x180021cf1  mov     rbp, [rsp+38h+arg_8]
0x180021cf6  add     rsp, 20h
0x180021cfa  pop     r14
0x180021cfc  pop     rdi
0x180021cfd  pop     rsi
0x180021cfe  retn
```
