# ClientOperation::HcsGetResult(ushort * *,HCS_PROCESS_INFORMATION *)

- ea: `0x18002ab0c`
- end: `0x18002acc5`
- name: `?HcsGetResult@ClientOperation@@QEAAJPEAPEAGPEAUHCS_PROCESS_INFORMATION@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, unsigned __int16 **, struct HCS_PROCESS_INFORMATION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016110`
- `0x1800161d0`
- `0x18002accc`

## callees

- `0x180006c3c`
- `0x18000f1b4`
- `0x18002ab0c`
- `0x18002b26c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aca9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ab25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ab25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aca0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac92`

## string_xrefs

- `0x18002aba3`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClientOperation::HcsGetResult(
        PSRWLOCK SRWLock,
        unsigned __int16 **a2,
        struct HCS_PROCESS_INFORMATION *a3)
{
  __int64 v6; // r8
  const char *v7; // r9
  unsigned int Ptr; // ebp
  int v9; // ebp
  const unsigned __int16 *v10; // rdx
  unsigned __int16 *v11; // rdi
  LPVOID v12; // rax
  unsigned __int16 *v13; // rbx
  __int64 v14; // rdx
  PVOID v15; // rax
  PVOID v16; // rax
  PVOID v17; // rax
  unsigned __int16 *v18; // rax
  int v20[2]; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[8]; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  AcquireSRWLockExclusive(SRWLock);
  Ptr = (unsigned int)SRWLock[12].Ptr;
  if ( ((Ptr + 2143878891) & 0xFFFFFFFD) == 0 )
    goto LABEL_29;
  v20[1] = 0;
  v9 = (__int64)SRWLock[13].Ptr & 1;
  v20[0] = v9;
  *(_OWORD *)pv = 0;
  if ( !a2 || (v10 = (const unsigned __int16 *)SRWLock[11].Ptr) == 0 )
  {
    v11 = (unsigned __int16 *)pv[1];
    v13 = (unsigned __int16 *)pv[0];
    goto LABEL_11;
  }
  Details::ClientStringAllocator::make_string_nothrow((Details::ClientStringAllocator *)v20, v10, v6, v7);
  v11 = (unsigned __int16 *)pv[1];
  v12 = pv[1];
  v13 = (unsigned __int16 *)pv[0];
  v9 = v20[0];
  if ( !v20[0] )
    v12 = pv[0];
  if ( v12 || SLODWORD(SRWLock[12].Ptr) < 0 )
  {
LABEL_11:
    if ( a3 )
    {
      if ( ((HIDWORD(SRWLock[12].Ptr) - 10) & 0xFFFFFFFD) != 0 )
      {
        Ptr = -2147024809;
        v14 = 109;
        goto LABEL_9;
      }
      *(_OWORD *)&a3->ProcessId = 0;
      *(_OWORD *)&a3->StdOutput = 0;
      if ( SLODWORD(SRWLock[12].Ptr) >= 0 )
      {
        if ( !LOBYTE(SRWLock[23].Ptr) )
        {
          Ptr = -2143878883;
          v14 = 116;
          goto LABEL_9;
        }
        a3->ProcessId = (DWORD)SRWLock[19].Ptr;
        v15 = SRWLock[20].Ptr;
        SRWLock[20].Ptr = (PVOID)-1LL;
        a3->StdInput = v15;
        v16 = SRWLock[21].Ptr;
        SRWLock[21].Ptr = (PVOID)-1LL;
        a3->StdOutput = v16;
        v17 = SRWLock[22].Ptr;
        SRWLock[22].Ptr = (PVOID)-1LL;
        a3->StdError = v17;
        if ( LOBYTE(SRWLock[23].Ptr) )
        {
          `eh vector destructor iterator'(
            &SRWLock[20],
            8u,
            3u,
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
          LOBYTE(SRWLock[23].Ptr) = 0;
        }
      }
    }
    if ( a2 )
    {
      if ( v9 )
      {
        v18 = v11;
        v11 = 0;
      }
      else
      {
        v18 = v13;
        v13 = 0;
      }
      *a2 = v18;
    }
    Ptr = (unsigned int)SRWLock[12].Ptr;
    goto LABEL_25;
  }
  Ptr = -2143878886;
  v14 = 103;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\clientoperation.cpp",
    (const char *)Ptr,
    v20[0]);
LABEL_25:
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v13 )
    LocalFree(v13);
LABEL_29:
  ReleaseSRWLockExclusive(SRWLock);
  return Ptr;
}

```

## disassembly

```asm
0x18002ab0c  mov     [rsp+arg_18], rbx
0x18002ab11  push    rbp
0x18002ab12  push    rsi
0x18002ab13  push    rdi
0x18002ab14  push    r14
0x18002ab16  push    r15
0x18002ab18  sub     rsp, 40h
0x18002ab1c  mov     r14, r8
0x18002ab1f  mov     r15, rdx
0x18002ab22  mov     rsi, rcx
0x18002ab25  call    cs:__imp_AcquireSRWLockExclusive
0x18002ab2b  mov     ebp, [rsi+60h]
0x18002ab2e  lea     eax, [rbp+7FC8FEEBh]
0x18002ab34  test    eax, 0FFFFFFFDh
0x18002ab39  jz      loc_18002ACA6
0x18002ab3f  mov     [rsp+68h+var_44], 0
0x18002ab47  mov     ebp, [rsi+68h]
0x18002ab4a  and     ebp, 1
0x18002ab4d  mov     [rsp+68h+var_48], ebp; int
0x18002ab51  xorps   xmm0, xmm0
0x18002ab54  movdqu  xmmword ptr [rsp+68h+pv], xmm0
0x18002ab5a  test    r15, r15
0x18002ab5d  jz      short loc_18002ABB4
0x18002ab5f  mov     rdx, [rsi+58h]; unsigned __int16 *
0x18002ab63  test    rdx, rdx
0x18002ab66  jz      short loc_18002ABB4
0x18002ab68  lea     rcx, [rsp+68h+var_48]; this
0x18002ab6d  call    ?make_string_nothrow@ClientStringAllocator@Details@@QEAAXPEBG@Z; Details::ClientStringAllocator::make_string_nothrow(ushort const *)
0x18002ab72  mov     rdi, [rsp+68h+pv+8]
0x18002ab77  mov     rax, rdi
0x18002ab7a  mov     rbx, [rsp+68h+pv]
0x18002ab7f  mov     ebp, [rsp+68h+var_48]
0x18002ab83  test    ebp, ebp
0x18002ab85  cmovz   rax, rbx
0x18002ab89  test    rax, rax
0x18002ab8c  jnz     short loc_18002ABBE
0x18002ab8e  cmp     [rsi+60h], eax
0x18002ab91  jl      short loc_18002ABBE
0x18002ab93  mov     ebp, 8037011Ah
0x18002ab98  lea     edx, [rax+67h]; void *
0x18002ab9b  mov     rcx, [rsp+68h]; this
0x18002aba0  mov     r9d, ebp; char *
0x18002aba3  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\dll\\lib\\core\\c"...
0x18002abaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002abaf  jmp     loc_18002AC8A
0x18002abb4  mov     rdi, [rsp+68h+pv+8]
0x18002abb9  mov     rbx, [rsp+68h+pv]
0x18002abbe  test    r14, r14
0x18002abc1  jz      loc_18002AC6F
0x18002abc7  mov     eax, [rsi+64h]
0x18002abca  sub     eax, 0Ah
0x18002abcd  test    eax, 0FFFFFFFDh
0x18002abd2  jz      short loc_18002ABE0
0x18002abd4  mov     ebp, 80070057h
0x18002abd9  mov     edx, 6Dh ; 'm'
0x18002abde  jmp     short loc_18002AB9B
0x18002abe0  xorps   xmm0, xmm0
0x18002abe3  movups  xmmword ptr [r14], xmm0
0x18002abe7  movups  xmmword ptr [r14+10h], xmm0
0x18002abec  cmp     dword ptr [rsi+60h], 0
0x18002abf0  jl      short loc_18002AC6F
0x18002abf2  cmp     byte ptr [rsi+0B8h], 0
0x18002abf9  jnz     short loc_18002AC07
0x18002abfb  mov     ebp, 8037011Dh
0x18002ac00  mov     edx, 74h ; 't'
0x18002ac05  jmp     short loc_18002AB9B
0x18002ac07  mov     eax, [rsi+98h]
0x18002ac0d  mov     [r14], eax
0x18002ac10  lea     rcx, [rsi+0A0h]; void *
0x18002ac17  mov     rax, [rcx]
0x18002ac1a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002ac1e  mov     [rcx], rdx
0x18002ac21  mov     [r14+8], rax
0x18002ac25  mov     rax, [rsi+0A8h]
0x18002ac2c  mov     [rsi+0A8h], rdx
0x18002ac33  mov     [r14+10h], rax
0x18002ac37  mov     rax, [rsi+0B0h]
0x18002ac3e  mov     [rsi+0B0h], rdx
0x18002ac45  mov     [r14+18h], rax
0x18002ac49  cmp     byte ptr [rsi+0B8h], 0
0x18002ac50  jz      short loc_18002AC6F
0x18002ac52  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18002ac59  mov     edx, 8; unsigned __int64
0x18002ac5e  lea     r8d, [rdx-5]; unsigned __int64
0x18002ac62  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002ac67  nop
0x18002ac68  mov     byte ptr [rsi+0B8h], 0
0x18002ac6f  test    r15, r15
0x18002ac72  jz      short loc_18002AC87
0x18002ac74  test    ebp, ebp
0x18002ac76  jnz     short loc_18002AC7F
0x18002ac78  mov     rax, rbx
0x18002ac7b  xor     ebx, ebx
0x18002ac7d  jmp     short loc_18002AC84
0x18002ac7f  mov     rax, rdi
0x18002ac82  xor     edi, edi
0x18002ac84  mov     [r15], rax
0x18002ac87  mov     ebp, [rsi+60h]
0x18002ac8a  test    rdi, rdi
0x18002ac8d  jz      short loc_18002AC98
0x18002ac8f  mov     rcx, rdi; pv
0x18002ac92  call    cs:__imp_CoTaskMemFree
0x18002ac98  test    rbx, rbx
0x18002ac9b  jz      short loc_18002ACA6
0x18002ac9d  mov     rcx, rbx; hMem
0x18002aca0  call    cs:__imp_LocalFree
0x18002aca6  mov     rcx, rsi; SRWLock
0x18002aca9  call    cs:__imp_ReleaseSRWLockExclusive
0x18002acaf  mov     eax, ebp
0x18002acb1  mov     rbx, [rsp+68h+arg_18]
0x18002acb9  add     rsp, 40h
0x18002acbd  pop     r15
0x18002acbf  pop     r14
0x18002acc1  pop     rdi
0x18002acc2  pop     rsi
0x18002acc3  pop     rbp
0x18002acc4  retn
```
