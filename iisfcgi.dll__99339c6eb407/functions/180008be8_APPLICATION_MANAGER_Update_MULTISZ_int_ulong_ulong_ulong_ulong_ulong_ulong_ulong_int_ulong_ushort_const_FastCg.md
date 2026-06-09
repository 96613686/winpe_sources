# APPLICATION_MANAGER::Update(MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,ushort const *,FastCgiApplicationStdErrMode)

- ea: `0x180008be8`
- end: `0x180008d87`
- name: `?Update@APPLICATION_MANAGER@@QEAAXPEAVMULTISZ@@HKKKKKKKHKPEBGW4FastCgiApplicationStdErrMode@@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ae9c`

## callees

- `0x180007b00`
- `0x180008164`
- `0x180008be8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d58`
- `iisutil!?Equals@MULTISZ@@QEAAHPEAV1@@Z` at `0x180008c23`
- `iisutil!?Equals@MULTISZ@@QEAAHPEAV1@@Z` at `0x180008c23`
- `iisutil!?Equals@STRU@@QEBA_NPEBG@Z` at `0x180008cc1`
- `iisutil!?Equals@STRU@@QEBA_NPEBG@Z` at `0x180008cc1`

## pseudocode

```c
void __fastcall APPLICATION_MANAGER::Update(
        __int64 a1,
        struct MULTISZ *a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        const unsigned __int16 *a13,
        int a14)
{
  int v17; // eax
  int v18; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( MULTISZ::Equals((MULTISZ *)(a1 + 336), a2)
    && a3 == *(_DWORD *)(a1 + 448)
    && a5 == *(_DWORD *)(a1 + 484)
    && a6 == *(_DWORD *)(a1 + 452)
    && a7 == *(_DWORD *)(a1 + 456)
    && a8 == *(_DWORD *)(a1 + 460)
    && a9 == *(_DWORD *)(a1 + 464)
    && a10 == *(_DWORD *)(a1 + 468)
    && a11 == *(_DWORD *)(a1 + 500)
    && (!a13 || STRU::Equals((STRU *)(a1 + 272), a13)) )
  {
    v17 = a14;
    v18 = 0;
    if ( a14 == *(_DWORD *)(a1 + 328) )
      goto LABEL_16;
  }
  else
  {
    v17 = a14;
  }
  v18 = 1;
  ++*(_DWORD *)(a1 + 512);
LABEL_16:
  APPLICATION_MANAGER::InitCommon(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, v17);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( v18 )
    APPLICATION_MANAGER::Recycle((APPLICATION_MANAGER *)a1, 0, v18);
}

```

## disassembly

```asm
0x180008be8  mov     [rsp+arg_0], rbx
0x180008bed  mov     [rsp+arg_18], r9d
0x180008bf2  mov     [rsp+arg_8], rdx
0x180008bf7  push    rbp
0x180008bf8  push    rsi
0x180008bf9  push    rdi
0x180008bfa  push    r12
0x180008bfc  push    r13
0x180008bfe  push    r14
0x180008c00  push    r15
0x180008c02  sub     rsp, 70h
0x180008c06  mov     rbx, rcx
0x180008c09  mov     ebp, r8d
0x180008c0c  add     rcx, 10h; lpCriticalSection
0x180008c10  mov     rdi, rdx
0x180008c13  call    cs:__imp_EnterCriticalSection
0x180008c19  lea     rcx, [rbx+150h]
0x180008c20  mov     rdx, rdi
0x180008c23  call    cs:__imp_?Equals@MULTISZ@@QEAAHPEAV1@@Z; MULTISZ::Equals(MULTISZ *)
0x180008c29  mov     rsi, [rsp+0A8h+arg_60]
0x180008c31  mov     r14d, [rsp+0A8h+arg_50]
0x180008c39  mov     r15d, [rsp+0A8h+arg_48]
0x180008c41  mov     r12d, [rsp+0A8h+arg_40]
0x180008c49  mov     r13d, [rsp+0A8h+arg_38]
0x180008c51  test    eax, eax
0x180008c53  jz      loc_180008CDE
0x180008c59  cmp     ebp, [rbx+1C0h]
0x180008c5f  jnz     short loc_180008CDE
0x180008c61  mov     eax, [rsp+0A8h+arg_20]
0x180008c68  cmp     eax, [rbx+1E4h]
0x180008c6e  jnz     short loc_180008CDE
0x180008c70  mov     eax, [rsp+0A8h+arg_28]
0x180008c77  cmp     eax, [rbx+1C4h]
0x180008c7d  jnz     short loc_180008CDE
0x180008c7f  mov     eax, [rsp+0A8h+arg_30]
0x180008c86  cmp     eax, [rbx+1C8h]
0x180008c8c  jnz     short loc_180008CDE
0x180008c8e  cmp     r13d, [rbx+1CCh]
0x180008c95  jnz     short loc_180008CDE
0x180008c97  cmp     r12d, [rbx+1D0h]
0x180008c9e  jnz     short loc_180008CDE
0x180008ca0  cmp     r15d, [rbx+1D4h]
0x180008ca7  jnz     short loc_180008CDE
0x180008ca9  cmp     r14d, [rbx+1F4h]
0x180008cb0  jnz     short loc_180008CDE
0x180008cb2  test    rsi, rsi
0x180008cb5  jz      short loc_180008CCB
0x180008cb7  lea     rcx, [rbx+110h]
0x180008cbe  mov     rdx, rsi
0x180008cc1  call    cs:__imp_?Equals@STRU@@QEBA_NPEBG@Z; STRU::Equals(ushort const *)
0x180008cc7  test    al, al
0x180008cc9  jz      short loc_180008CDE
0x180008ccb  mov     eax, [rsp+0A8h+arg_68]
0x180008cd2  xor     edi, edi
0x180008cd4  cmp     eax, [rbx+148h]
0x180008cda  jz      short loc_180008CF0
0x180008cdc  jmp     short loc_180008CE5
0x180008cde  mov     eax, [rsp+0A8h+arg_68]
0x180008ce5  mov     edi, 1
0x180008cea  add     [rbx+200h], edi
0x180008cf0  mov     r9d, [rsp+0A8h+arg_18]
0x180008cf8  mov     r8d, ebp
0x180008cfb  mov     rdx, [rsp+0A8h+arg_8]
0x180008d03  mov     rcx, rbx
0x180008d06  mov     [rsp+0A8h+var_40], eax
0x180008d0a  mov     eax, [rsp+0A8h+arg_58]
0x180008d11  mov     [rsp+0A8h+var_48], rsi
0x180008d16  mov     [rsp+0A8h+var_50], eax
0x180008d1a  mov     eax, [rsp+0A8h+arg_30]
0x180008d21  mov     [rsp+0A8h+var_58], r14d
0x180008d26  mov     [rsp+0A8h+var_60], r15d
0x180008d2b  mov     [rsp+0A8h+var_68], r12d
0x180008d30  mov     [rsp+0A8h+var_70], r13d
0x180008d35  mov     [rsp+0A8h+var_78], eax
0x180008d39  mov     eax, [rsp+0A8h+arg_28]
0x180008d40  mov     [rsp+0A8h+var_80], eax
0x180008d44  mov     eax, [rsp+0A8h+arg_20]
0x180008d4b  mov     [rsp+0A8h+var_88], eax
0x180008d4f  call    ?InitCommon@APPLICATION_MANAGER@@QEAAJPEAVMULTISZ@@HKKKKKKKHKPEBGW4FastCgiApplicationStdErrMode@@@Z; APPLICATION_MANAGER::InitCommon(MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,ushort const *,FastCgiApplicationStdErrMode)
0x180008d54  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008d58  call    cs:__imp_LeaveCriticalSection
0x180008d5e  test    edi, edi
0x180008d60  jz      short loc_180008D6F
0x180008d62  mov     r8d, edi; int
0x180008d65  xor     edx, edx; int
0x180008d67  mov     rcx, rbx; this
0x180008d6a  call    ?Recycle@APPLICATION_MANAGER@@AEAAXHH@Z; APPLICATION_MANAGER::Recycle(int,int)
0x180008d6f  mov     rbx, [rsp+0A8h+arg_0]
0x180008d77  add     rsp, 70h
0x180008d7b  pop     r15
0x180008d7d  pop     r14
0x180008d7f  pop     r13
0x180008d81  pop     r12
0x180008d83  pop     rdi
0x180008d84  pop     rsi
0x180008d85  pop     rbp
0x180008d86  retn
```
